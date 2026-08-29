# 01_cover

这套内容从集群整体拓扑出发，拆解 Kubernetes 从控制平面到 Pod 的关键组件，以及它们之间真正的通信路径。先记住两个关键词：控制平面负责决策，工作节点负责运行负载；两者之间所有状态变化都围绕 API server 展开。后面会依次看调度、调和、Pod 生命周期、服务网络、存储和高可用，并说明哪些故障能自动恢复、哪些必须依赖备份和人工介入。内容依据 Kubernetes 官方的集群架构、组件、Service、Pod 生命周期和持久卷文档整理。

---

# 02_two_planes

Kubernetes 集群可以先看成两个平面。控制平面负责调度工作负载、响应集群事件，并保存 API 对象的期望状态；数据平面由一个或多个工作节点组成，真正运行应用 Pod，每个节点都有 kubelet、容器运行时和 kube-proxy。两边并不彼此直接通信，所有状态读写都经过 kube-apiserver，而且只有 kube-apiserver 直接读写 etcd。最小学习环境可以是一台控制平面主机加一个工作节点，但生产环境通常至少部署三台控制平面主机，把 API server 放在负载均衡之后，并使用三个或五个奇数成员的 etcd 集群形成法定人数。接下来先拆开控制平面的五个组件，再进入工作节点内部。

---

# 03_control_plane

控制平面的中心是 kube-apiserver，它暴露 Kubernetes 的 HTTP API，完成校验和准入后持久化对象，也是唯一直接通过 gRPC 读写 etcd 的组件；它本身可以通过多实例和负载均衡水平扩展。etcd 保存全部集群状态，依赖 Raft 共识和三个或五个奇数成员，因此丢失 etcd 就等于丢失集群，持续备份是硬要求。kube-scheduler 监听尚未写入 nodeName 的 Pod，选定节点后只把绑定结果写回 API server，从不直接联系节点。kube-controller-manager 运行多个逻辑控制器，每个都执行 watch、比较差异和采取动作的循环，并通过 Leader 选举保证多副本中同一时刻只有一个实例真正执行。cloud-controller-manager 是云环境中的可选组件，承载节点、路由和云负载均衡等厂商逻辑，让核心组件保持云厂商中立。

---

# 04_scheduling

调度器处理一个未绑定 Pod 时，先过滤，再打分。过滤阶段会检查 CPU、内存和 GPU 等资源请求，也会检查软硬件与策略约束、亲和与反亲和、污点与容忍、拓扑分布、数据局部性以及工作负载之间的干扰；任何硬条件不满足，节点就不会进入下一阶段。打分阶段对所有可行节点使用同一组规则排序，选出最高分节点，然后只把 binding 写回 API server。真正拉起容器的是目标节点上的 kubelet，调度器不会直接和节点对话。还要注意，一个 Pod 一生只调度一次；如果它失败，Deployment、StatefulSet 或 Job 等控制器会创建一个带新 UID 的替代 Pod，再完整走一遍过滤和打分流程。

---

# 05_reconcile

Kubernetes 控制器的共同模型是一个永不停止的调和循环。第一步通过 API server watch 自己关心的 Pod、Node、Service 等对象，第二步比较 spec 中的期望状态与 status 中的实际状态，第三步采取动作缩小差距，例如创建 Pod、更新端点或标记节点，然后立即回到监听。Node 控制器处理节点故障，Job 控制器推动任务完成，EndpointSlice 控制器维护 Service 到 Pod IP 的映射，ServiceAccount 控制器建立默认身份，ReplicaSet、Deployment、StatefulSet 和 DaemonSet 等工作负载控制器维持副本与状态。高可用依赖 Leader 选举：组件可以部署多个副本，但同一时刻只有一个副本执行修改。理解这条循环，就理解了 Kubernetes 自愈与声明式管理的基础。

---

# 06_worker_node

每个工作节点上有三类并列组件，其中只有 kubelet 持续与 API server 交换状态。kubelet 监听分配到本节点的 Pod，读取 PodSpec，指挥运行时启动容器，执行健康探针并回报节点和 Pod 状态；容器退出后，它按照 Always、OnFailure 或 Never 的 restartPolicy 处理，并通过 kube-node-lease 中的 Lease 发送心跳。kube-proxy 把 Service 虚拟 IP 映射到 Pod IP，可使用 iptables、IPVS、nftables 等后端，旧的 userspace 模式已经废弃；Cilium 或 Calico 的 eBPF 数据面也可以整体替代它。容器运行时通过 CRI 与 kubelet 对接，常见实现是 containerd 和 CRI-O，也可以是任何兼容 CRI 的实现。自 Kubernetes 一点二四版起，Docker Engine 不再是内置运行时，因为 kubelet 面向的是 CRI 契约，而不是某个具体产品。

---

# 07_pod_lifecycle

Pod 是共享网络命名空间和存储卷的一组容器，也是 Kubernetes 的最小可部署单元。Pod 从 Pending 进入 Running，最终可能是 Succeeded 或 Failed；如果 API server 联系不上承载它的节点，则会显示 Unknown，而每个容器还独立维护 Waiting、Running 和 Terminated 状态。kubelet 执行三类探针：存活探针失败会重启容器，就绪探针失败只会把它从 Service 端点移除，启动探针则在慢启动应用完成初始化前屏蔽前两类探针；探测可通过 exec、HTTP、TCP 或 gRPC 完成。删除 Pod 时，API server 先标记待删除，随后执行可选的 preStop 钩子，向主进程发送 SIGTERM，并在默认三十秒的宽限期内等待；超过 terminationGracePeriodSeconds 仍未退出，才发送 SIGKILL。清理逻辑应放在 preStop 和 SIGTERM 处理里，同时牢记失败的 Pod 是由控制器用新 UID 替换，而不是原地重新调度。

---

# 08_services

Service 的作用，是在不断变化的一组 Pod 前提供稳定的虚拟 IP 和 DNS 名。ClusterIP 默认只在集群内可达；NodePort 在每个节点开放三万到三万二千七百六十七之间的静态端口并转到 ClusterIP；LoadBalancer 由云控制器供给外部负载均衡器，后端通常再指向 NodePort。三者是逐层依赖关系，而 ExternalName 独立存在，只返回一个 DNS CNAME，不分配代理路径。EndpointSlice 持续跟踪 Service 背后的 Pod IP，并从一点二一版开始替代旧 Endpoints；CoreDNS 则让服务按“服务名、命名空间、svc、cluster、local”的完整域名解析。Headless Service 把 clusterIP 设为 None，不创建虚拟 IP，而是让 DNS 直接返回 Pod IP，StatefulSet 因而能给每个副本提供稳定且可解析的名称。

---

# 09_storage

Kubernetes 把持久存储拆成请求、实体和配方三种资源。Pod 通过命名空间级的 PVC 提出容量和访问需求，集群级的 PV 代表已经供给、拥有独立生命周期的存储实体，StorageClass 则由管理员定义动态供给配方；CSI 驱动把这些抽象连接到不同存储后端，旧的树内插件已经废弃。访问模式中，RWO 表示单个节点可读写，ROX 表示多个节点只读，RWX 表示多个节点可读写，RWOP 才表示单个 Pod 独占读写，因此 Once 和 Many 通常描述的是节点数量。PVC 删除后，PV 可以按 Retain 保留或按 Delete 删除，Recycle 策略已经废弃。卷模式默认是挂载为目录的 Filesystem，也可以直接暴露为裸块设备 Block。

---

# 10_ha_topology

生产高可用通常从至少三台控制平面主机开始，多个 kube-apiserver 放在负载均衡后，scheduler 和 controller-manager 通过 Leader 选举保持单活执行，etcd 则使用三个或五个奇数成员并跨主机形成法定人数。控制平面和工作节点还应跨可用区分布，使单个可用区故障时集群仍能继续运行。堆叠式拓扑让每台控制平面主机同时运行 apiserver 和一个 etcd 成员，硬件更少、部署更简单，但一台主机故障会同时损失两类能力。外置式拓扑把 etcd 放到专用主机，apiserver 与 etcd 可以独立故障，隔离性更好，但需要更多硬件。两种方案的核心差别只是 etcd 放在哪里，选择时要在简化运维和故障域隔离之间权衡。

---

# 11_self_healing

Kubernetes 的自愈能力来自持续运行的控制循环，但它有明确边界。容器崩溃时，kubelet 会按 restartPolicy 重启并使用指数退避，退避从一百毫秒逐步增加到五分钟上限，健康运行十分钟后重置；Pod 失败时，所属工作负载控制器创建新 Pod；节点 NotReady 超过默认五分钟的驱逐等待后，其上 Pod 被标记删除并在其他节点重建；调度器也会把新 Pod 放到负载更低的节点。另一方面，etcd 一旦失去法定人数，集群状态只能从备份手动恢复；API server 失联后无法作出新决策，已有工作负载会暂时继续运行，直到 kubelet 的 watch 超时。生产环境还需要补齐 CoreDNS、metrics-server 与 Prometheus、Fluent Bit 或 Fluentd 汇聚到日志后端，Dashboard 则是可选的 Web 界面。判断是否能自愈的简单方法是：是否还有一个能通过 API server 观察差距并采取动作的控制器。

---

# 12_api_spine

把前面的组件放回一张通信图，主干非常清晰。kubectl 和其他客户端通过 HTTPS 访问 kube-apiserver，只有 kube-apiserver 通过 gRPC 与三个或五个成员组成的 etcd 集群双向通信。scheduler、controller-manager 和可选的 cloud-controller-manager 都通过 API server watch 对象并写回决策；各节点的 kubelet也通过它监听调度结果、报告状态，再在节点内部驱动容器运行时和 Service 数据面。没有控制器直接调用另一个控制器，也没有普通组件绕过 API server 访问 etcd。于是每次状态变化都表现为一个 API 事件，这种统一入口正是 Kubernetes 能够保持组件可插拔、行为可观测的根源。

---

# 13_takeaways

最后用五句话收束整套架构。第一，控制平面做决策，工作节点跑 Pod，生产环境通常至少需要三台控制平面主机；第二，所有组件围绕 kube-apiserver 通信，只有它读写 etcd。第三，scheduler 对每个 Pod 只调度一次，而控制器通过 watch、比较差异和采取动作持续调和。第四，Service 为变化的 Pod 提供稳定入口，PVC、PV 和 StorageClass 分离存储请求、实体与配方，CSI 统一后端。第五，自愈并不等于无条件恢复，跨可用区的多副本控制平面和奇数 etcd 能抵御常见故障，但 etcd 失去法定人数后仍必须依赖可靠备份。
