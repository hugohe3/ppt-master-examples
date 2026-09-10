# raft

# In Search of an Understandable Consensus Algorithm (Extended Version)

Diego Ongaro and John Ousterhout Stanford University Abstract state space reduction (relative to Paxos, Raft reduces the degree of nondeterminism and the ways servers can be in- Raft is a consensus algorithm for managing a replicated consistent with each other). A user study with 43 students log. It produces a result equivalent to (multi-)Paxos, and at two universities shows that Raft is signiﬁcantly easier it is as efﬁcient as Paxos, but its structure is different to understand than Paxos: after learning both algorithms, from Paxos; this makes Raft more understandable than 33 of these students were able to answer questions about Paxos and also provides a better foundation for build- Raft better than questions about Paxos.

ing practical systems. In order to enhance understandabil- ity, Raft separates the key elements of consensus, such as Raft is similar in many ways to existing consensus al- leader election, log replication, and safety, and it enforces gorithms (most notably, Oki and Liskov’s Viewstamped a stronger degree of coherency to reduce the number of Replication [29, 22]), but it has several novel features:

states that must be considered. Results from a user study

- Strong leader:Raft uses a stronger form of leader-

demonstrate that Raft is easier for students to learn than ship than other consensus algorithms. For example, Paxos. Raft also includes a new mechanism for changing log entries only ﬂow from the leader to other servers.

the cluster membership, which uses overlapping majori- This simpliﬁes the management of the replicated log ties to guarantee safety.

and makes Raft easier to understand.

- Leader election: Raft uses randomized timers to

1 Introduction elect leaders. This adds only a small amount of Consensus algorithms allow a collection of machines mechanism to the heartbeats already required for any to work as a coherent group that can survive the fail- consensus algorithm, while resolving conﬂicts sim- ures of some of its members. Because of this, they play a ply and rapidly.

key role in building reliable large-scale software systems.

- Membership

changes:

Raft’s mechanism for Paxos [15, 16] has dominated the discussion of consen- changing the set of servers in the cluster uses a new sus algorithms over the last decade: most implementations joint consensus approach where the majorities of of consensus are based on Paxos or inﬂuenced by it, and two different conﬁgurations overlap during transi- Paxos has become the primary vehicle used to teach stu- tions. This allows the cluster to continue operating dents about consensus.

normally during conﬁguration changes.

Unfortunately, Paxos is quite difﬁcult to understand, in We believe that Raft is superior to Paxos and other con- spite of numerous attempts to make it more approachable.

sensus algorithms, both for educational purposes and as a Furthermore, its architecture requires complex changes foundation for implementation. It is simpler and more un- to support practical systems. As a result, both system derstandable than other algorithms; it is described com- builders and students struggle with Paxos.

pletely enough to meet the needs of a practical system;

After struggling with Paxos ourselves, we set out to it has several open-source implementations and is used ﬁnd a new consensus algorithm that could provide a bet- by several companies; its safety properties have been for- ter foundation for system building and education. Our ap- mally speciﬁed and proven; and its efﬁciency is compara- proach was unusual in that our primary goal was under- ble to other algorithms.

standability: could we deﬁne a consensus algorithm for The remainder of the paper introduces the replicated practical systems and describe it in a way that is signiﬁ- state machine problem (Section 2), discusses the strengths cantly easier to learn than Paxos? Furthermore, we wanted and weaknesses of Paxos (Section 3), describes our gen- the algorithm to facilitate the development of intuitions eral approach to understandability (Section 4), presents that are essential for system builders. It was important not the Raft consensus algorithm (Sections 5–8), evaluates just for the algorithm to work, but for it to be obvious why Raft (Section 9), and discusses related work (Section 10).

it works.

The result of this work is a consensus algorithm called 2 Replicated state machines Raft. In designing Raft we applied speciﬁc techniques to Consensus algorithms typically arise in the context of improve understandability,including decomposition (Raft replicated state machines[37]. In this approach, state ma- separates leader election, log replication, and safety) and chines on a collection of servers compute identical copies of the same state and can continue operating even if some This tech report is an extended version of [32]; additional material is of the servers are down. Replicated state machines are noted with a gray bar in the margin. Published May 20, 2014.

1

<!-- Page 2 -->

tency of the logs: faulty clocks and extreme message delays can, at worst, cause availability problems.

- In the common case, a command can complete as

soon as a majority of the cluster has responded to a single round of remote procedure calls; a minority of slow servers need not impact overall system perfor- mance.

3 What’s wrong with Paxos?

Over the last ten years, Leslie Lamport’s Paxos proto- Figure 1: Replicated state machine architecture. The con- col [15] has become almost synonymous with consensus:

sensus algorithm manages a replicated log containing state it is the protocol most commonly taught in courses, and machine commands from clients. The state machines process most implementations of consensus use it as a starting identical sequences of commands from the logs, so they pro- point. Paxos ﬁrst deﬁnes a protocol capable of reaching duce the same outputs.

agreement on a single decision, such as a single replicated used to solve a variety of fault tolerance problems in dis- log entry. We refer to this subset assingle-decree Paxos.

tributed systems. For example, large-scale systems that Paxos then combines multiple instances of this protocol to have a single cluster leader, such as GFS [8], HDFS [38], facilitate a series of decisions such as a log (multi-Paxos).

and RAMCloud [33], typically use a separate replicated Paxos ensures both safety and liveness, and it supports state machine to manage leader election and store conﬁg- changes in cluster membership. Its correctness has been uration information that must survive leader crashes. Ex- proven, and it is efﬁcient in the normal case.

amples of replicated state machines include Chubby [2] Unfortunately, Paxos has two signiﬁcant drawbacks.

and ZooKeeper [11].

The ﬁrst drawback is that Paxos is exceptionally difﬁ- Replicated state machines are typically implemented cult to understand. The full explanation [15] is notori- using a replicated log, as shown in Figure 1. Each server ously opaque; few people succeed in understanding it, and stores a log containing a series of commands, which its only with great effort. As a result, there have been several state machine executes in order. Each log contains the attempts to explain Paxos in simpler terms [16, 20, 21].

same commands in the same order, so each state ma- These explanations focus on the single-decree subset, yet chine processes the same sequence of commands. Since they are still challenging. In an informal survey of atten- the state machines are deterministic, each computes the dees at NSDI 2012, we found few people who were com- same state and the same sequence of outputs.

fortable with Paxos, even among seasoned researchers.

Keeping the replicated log consistent is the job of the We struggled with Paxos ourselves; we were not able to consensus algorithm. The consensus module on a server understand the complete protocol until after reading sev- receives commands from clients and adds them to its log.

eral simpliﬁed explanations and designing our own alter- It communicates with the consensus modules on other native protocol, a process that took almost a year.

servers to ensure that every log eventually contains the We hypothesize that Paxos’ opaqueness derives from same requests in the same order, even if some servers fail.

its choice of the single-decree subset as its foundation.

Once commands are properly replicated, each server’s Single-decree Paxos is dense and subtle: it is divided into state machine processes them in log order, and the out- two stages that do not have simple intuitive explanations puts are returned to clients. As a result, the servers appear and cannot be understood independently. Because of this, to form a single, highly reliable state machine.

it is difﬁcult to develop intuitions about why the single- Consensus algorithms for practical systems typically decree protocol works. The composition rules for multi- have the following properties:

Paxos add signiﬁcant additional complexity and subtlety.

- They ensure safety (never returning an incorrect re-

We believe that the overall problem of reaching consensus on multiple decisions (i.e., a log instead of a single entry) sult) under all non-Byzantine conditions, including can be decomposed in other ways that are more direct and network delays, partitions, and packet loss, duplica- obvious.

tion, and reordering.

- They are fully functional (available) as long as any

The second problem with Paxos is that it does not pro- majority of the servers are operational and can com- vide a good foundation for building practical implemen- municate with each other and with clients. Thus, a tations. One reason is that there is no widely agreed- typical cluster of ﬁve servers can tolerate the failure upon algorithm for multi-Paxos. Lamport’s descriptions of any two servers. Servers are assumed to fail by are mostly about single-decree Paxos; he sketched possi- stopping; they may later recover from state on stable ble approaches to multi-Paxos, but many details are miss- storage and rejoin the cluster.

ing. There have been several attempts to ﬂesh out and op-

- They do not depend on timing to ensure the consis-

timize Paxos, such as [26], [39], and [13], but these differ 2

<!-- Page 3 -->

from each other and from Lamport’s sketches. Systems There were numerous points in the design of Raft such as Chubby [4] have implemented Paxos-like algo- where we had to choose among alternative approaches.

rithms, but in most cases their details have not been pub- In these situations we evaluated the alternatives based on lished.

understandability: how hard is it to explain each alterna- tive (for example, how complex is its state space, and does Furthermore, the Paxos architecture is a poor one for it have subtle implications?), and how easy will it be for a building practical systems; this is another consequence of reader to completely understand the approach and its im- the single-decree decomposition. For example, there is lit- plications?

tle beneﬁt to choosing a collection of log entries indepen- dently and then melding them into a sequential log; this We recognize that there is a high degree of subjectiv- just adds complexity. It is simpler and more efﬁcient to ity in such analysis; nonetheless, we used two techniques design a system around a log, where new entries are ap- that are generally applicable. The ﬁrst technique is the pended sequentially in a constrained order. Another prob- well-known approach of problem decomposition: wher- lem is that Paxos uses a symmetric peer-to-peer approach ever possible, we divided problems into separate pieces at its core (though it eventually suggests a weak form of that could be solved, explained, and understood relatively leadership as a performance optimization). This makes independently. For example, in Raft we separated leader sense in a simpliﬁed world where only one decision will election, log replication, safety, and membership changes.

be made, but few practical systems use this approach. If a Our second approach was to simplify the state space series of decisions must be made, it is simpler and faster by reducing the number of states to consider, making the to ﬁrst elect a leader, then have the leader coordinate the system more coherent and eliminating nondeterminism decisions.

where possible. Speciﬁcally, logs are not allowed to have As a result, practical systems bear little resemblance holes, and Raft limits the ways in which logs can become to Paxos. Each implementation begins with Paxos, dis- inconsistent with each other. Although in most cases we covers the difﬁculties in implementing it, and then de- tried to eliminate nondeterminism, there are some situ- velops a signiﬁcantly different architecture. This is time- ations where nondeterminism actually improves under- consuming and error-prone, and the difﬁculties of under- standability. In particular, randomized approaches intro- standing Paxos exacerbate the problem. Paxos’ formula- duce nondeterminism, but they tend to reduce the state tion may be a good one for proving theorems about its cor- space by handling all possible choices in a similar fashion rectness, but real implementations are so different from (“choose any; it doesn’t matter”). We used randomization Paxos that the proofs have little value. The following com- to simplify the Raft leader election algorithm.

ment from the Chubby implementers is typical:

5 The Raft consensus algorithm There are signiﬁcant gaps between the description of Raft is an algorithm for managing a replicated log of the Paxos algorithm and the needs of a real-world the form described in Section 2. Figure 2 summarizes the system. . . . the ﬁnal system will be based on an un- algorithm in condensed form for reference, and Figure 3 proven protocol [4].

lists key properties of the algorithm; the elements of these Because of these problems, we concluded that Paxos ﬁgures are discussed piecewise over the rest of this sec- does not provide a good foundation either for system tion.

building or for education. Given the importance of con- Raft implements consensus by ﬁrst electing a distin- sensus in large-scale software systems, we decided to see guishedleader, then giving the leader complete responsi- if we could design an alternative consensus algorithm bility for managing the replicated log. The leader accepts with better properties than Paxos. Raft is the result of that log entries from clients, replicates them on other servers, experiment.

and tells servers when it is safe to apply log entries to 4 Designing for understandability their state machines. Having a leader simpliﬁes the man- agement of the replicated log. For example, the leader can We had several goals in designing Raft: it must provide decide where to place new entries in the log without con- a complete and practical foundation for system building, sulting other servers, and data ﬂows in a simple fashion so that it signiﬁcantly reduces the amount of design work from the leader to other servers. A leader can fail or be- required of developers; it must be safe under all conditions come disconnected from the other servers, in which case and available under typical operating conditions; and it a new leader is elected.

must be efﬁcient for common operations. But our most Given the leader approach, Raft decomposes the con- important goal—and most difﬁcult challenge—was un- sensus problem into three relatively independent subprob- derstandability. It must be possible for a large audience to lems, which are discussed in the subsections that follow:

understand the algorithm comfortably. In addition, it must

- Leader election:a new leader must be chosen when

be possible to develop intuitions about the algorithm, so that system builders can make the extensions that are in- an existing leader fails (Section 5.2).

- Log replication: the leader must accept log entries

evitable in real-world implementations.

3

<!-- Page 4 -->

**RequestVote RPC** **State** **Persistent state on all servers:** Invoked by candidates to gather votes (§5.2).

(Updated on stable storage before responding to RPCs) **Arguments:** latest term server has seen (initialized to 0 **currentTerm** candidate’s term **term** on first boot, increases monotonically) candidate requesting vote **candidateId** candidateId that received vote in current **votedFor** index of candidate’s last log entry (§5.4) **lastLogIndex** term (or null if none) term of candidate’s last log entry (§5.4) **lastLogTerm** log entries; each entry contains command **log[]** for state machine, and term when entry **Results:** was received by leader (first index is 1) currentTerm, for candidate to update itself **term** true means candidate received vote **voteGranted** **Volatile state on all servers:** index of highest log entry known to be **commitIndex** **Receiver implementation:** committed (initialized to 0, increases

1. 

Reply false if term < currentTerm (§5.1) monotonically)

2. 

If votedFor is null or candidateId, and candidate’s log is at index of highest log entry applied to state **lastApplied** least as up-to-date as receiver’s log, grant vote (§5.2, §5.4) machine (initialized to 0, increases monotonically) **Rules for Servers** **Volatile state on leaders:** **All Servers:** (Reinitialized after election)

- 

If commitIndex > lastApplied: increment lastApplied, apply for each server, index of the next log entry **nextIndex[]** log[lastApplied] to state machine (§5.3) to send to that server (initialized to leader

- 

If RPC request or response contains term T > currentTerm:

last log index + 1) set currentTerm = T, convert to follower (§5.1) for each server, index of highest log entry **matchIndex[]** known to be replicated on server **Followers (§5.2):**

- 

(initialized to 0, increases monotonically) Respond to RPCs from candidates and leaders

- 

If election timeout elapses without receiving AppendEntries **AppendEntries RPC** RPC from current leader or granting vote to candidate:

convert to candidate Invoked by leader to replicate log entries (§5.3); also used as heartbeat (§5.2).

**Candidates (§5.2):**

- 

On conversion to candidate, start election:

**Arguments:**

- Increment currentTerm

leader’s term **term**

- Vote for self

so follower can redirect clients **leaderId**

- Reset election timer

index of log entry immediately preceding **prevLogIndex**

- Send RequestVote RPCs to all other servers

new ones

- 

If votes received from majority of servers: become leader term of prevLogIndex entry **prevLogTerm**

- 

If AppendEntries RPC received from new leader: convert to log entries to store (empty for heartbeat;

**entries[]** follower may send more than one for efficiency)

- 

If election timeout elapses: start new election leader’s commitIndex **leaderCommit** **Leaders:** **Results:**

- 

Upon election: send initial empty AppendEntries RPCs currentTerm, for leader to update itself **term** (heartbeat) to each server; repeat during idle periods to true if follower contained entry matching **success** prevent election timeouts (§5.2) prevLogIndex and prevLogTerm

- 

If command received from client: append entry to local log, **Receiver implementation:** respond after entry applied to state machine (§5.3)

- 
1. 

Reply false if term < currentTerm (§5.1) If last log index ≥nextIndex for a follower: send

2. 

Reply false if log doesn’t contain an entry at prevLogIndex AppendEntries RPC with log entries starting at nextIndex

- If successful: update nextIndex and matchIndex for

whose term matches prevLogTerm (§5.3)

3. 

If an existing entry conflicts with a new one (same index follower (§5.3)

- If AppendEntries fails because of log inconsistency:

but different terms), delete the existing entry and all that follow it (§5.3) decrement nextIndex and retry (§5.3)

- 
4. 

Append any new entries not already in the log If there exists an N such that N > commitIndex, a majority

5. 

If leaderCommit > commitIndex, set commitIndex = of matchIndex[i] ≥N, and log[N].term == currentTerm:

min(leaderCommit, index of last new entry) set commitIndex = N (§5.3, §5.4).

Figure 2:A condensed summary of the Raft consensus algorithm (excluding membership changes and log compaction). The server behavior in the upper-left box is described as a set of rules that trigger independently and repeatedly. Section numbers such as§5.2 indicate where particular features are discussed. A formal speciﬁcation [31] describes the algorithm more precisely.

4

<!-- Page 5 -->

Election Safety: at most one leader can be elected in a given term.§5.2 Leader Append-Only: a leader never overwrites or deletes entries in its log; it only appends new entries.§5.3 Log Matching: if two logs contain an entry with the same index and term, then the logs are identical in all entries up through the given index.§5.3 Leader Completeness: if a log entry is committed in a Figure 4: Server states. Followers only respond to requests given term, then that entry will be present in the logs from other servers. If a follower receives no communication, of the leaders for all higher-numbered terms.§5.4 it becomes a candidate and initiates an election. A candidate State Machine Safety: if a server has applied a log entry that receives votes from a majority of the full cluster becomes at a given index to its state machine, no other server the new leader. Leaders typically operate until they fail.

will ever apply a different log entry for the same index.

§5.4.3 Figure 3:Raft guarantees that each of these properties is true at all times. The section numbers indicate where each prop- erty is discussed.

from clients and replicate them across the cluster, forcing the other logs to agree with its own (Sec- Figure 5: Time is divided into terms, and each term begins tion 5.3).

with an election. After a successful election, a single leader

- Safety:the key safety property for Raft is the State

manages the cluster until the end of the term. Some elections Machine Safety Property in Figure 3: if any server fail, in which case the term ends without choosing a leader.

has applied a particular log entry to its state machine, The transitions between terms may be observed at different then no other server may apply a different command times on different servers.

for the same log index. Section 5.4 describes how will begin shortly. Raft ensures that there is at most one Raft ensures this property; the solution involves an leader in a given term.

additional restriction on the election mechanism de- Different servers may observe the transitions between scribed in Section 5.2.

terms at different times, and in some situations a server After presenting the consensus algorithm, this section dis- may not observe an election or even entire terms. Terms cusses the issue of availability and the role of timing in the act as a logical clock [14] in Raft, and they allow servers system.

to detect obsolete information such as stale leaders. Each server stores a current term number, which increases 5.1 Raft basics monotonically over time. Current terms are exchanged A Raft cluster contains several servers; ﬁve is a typical whenever servers communicate; if one server’s current number, which allows the system to tolerate two failures.

term is smaller than the other’s, then it updates its current At any given time each server is in one of three states:

term to the larger value. If a candidate or leader discovers leader,follower, orcandidate. In normal operation there that its term is out of date, it immediately reverts to fol- is exactly one leader and all of the other servers are fol- lower state. If a server receives a request with a stale term lowers. Followers are passive: they issue no requests on number, it rejects the request.

their own but simply respond to requests from leaders Raft servers communicate using remote procedure calls and candidates. The leader handles all client requests (if (RPCs), and the basic consensus algorithm requires only a client contacts a follower, the follower redirects it to the two types of RPCs. RequestVote RPCs are initiated by leader). The third state, candidate, is used to elect a new candidates during elections (Section 5.2), and Append- leader as described in Section 5.2. Figure 4 shows the Entries RPCs are initiated by leaders to replicate log en- states and their transitions; the transitions are discussed tries and to provide a form of heartbeat (Section 5.3). Sec- below.

tion 7 adds a third RPC for transferring snapshots between Raft divides time into terms of arbitrary length, as servers. Servers retry RPCs if they do not receive a re- shown in Figure 5. Terms are numbered with consecutive sponse in a timely manner, and they issue RPCs in parallel integers. Each term begins with anelection, in which one for best performance.

or more candidates attempt to become leader as described 5.2 Leader election in Section 5.2. If a candidate wins the election, then it serves as leader for the rest of the term. In some situations Raft uses a heartbeat mechanism to trigger leader elec- an election will result in a split vote. In this case the term tion. When servers start up, they begin as followers. A will end with no leader; a new term (with a new election) server remains in follower state as long as it receives valid 5

<!-- Page 6 -->

RPCs from a leader or candidate. Leaders send periodic heartbeats (AppendEntries RPCs that carry no log entries) to all followers in order to maintain their authority. If a follower receives no communication over a period of time called theelection timeout, then it assumes there is no vi- able leader and begins an election to choose a new leader.

To begin an election, a follower increments its current term and transitions to candidate state. It then votes for itself and issues RequestVote RPCs in parallel to each of the other servers in the cluster. A candidate continues in this state until one of three things happens: (a) it wins the election, (b) another server establishes itself as leader, or (c) a period of time goes by with no winner. These out- Figure 6:Logs are composed of entries, which are numbered comes are discussed separately in the paragraphs below.

sequentially. Each entry contains the term in which it was A candidate wins an election if it receives votes from created (the number in each box) and a command for the state a majority of the servers in the full cluster for the same machine. An entry is consideredcommittedif it is safe for that term. Each server will vote for at most one candidate in a entry to be applied to state machines.

given term, on a ﬁrst-come-ﬁrst-served basis (note: Sec- Elections are an example of how understandability tion 5.4 adds an additional restriction on votes). The ma- guided our choice between design alternatives. Initially jority rule ensures that at most one candidate can win the we planned to use a ranking system: each candidate was election for a particular term (the Election Safety Prop- assigned a unique rank, which was used to select between erty in Figure 3). Once a candidate wins an election, it competing candidates. If a candidate discovered another becomes leader. It then sends heartbeat messages to all of candidate with higher rank, it would return to follower the other servers to establish its authority and prevent new state so that the higher ranking candidate could more eas- elections.

ily win the next election. We found that this approach While waiting for votes, a candidate may receive an created subtle issues around availability (a lower-ranked AppendEntries RPC from another server claiming to be server might need to time out and become a candidate leader. If the leader’s term (included in its RPC) is at least again if a higher-ranked server fails, but if it does so too as large as the candidate’s current term, then the candidate soon, it can reset progress towards electing a leader). We recognizes the leader as legitimate and returns to follower made adjustments to the algorithm several times, but after state. If the term in the RPC is smaller than the candidate’s each adjustment new corner cases appeared. Eventually current term, then the candidate rejects the RPC and con- we concluded that the randomized retry approach is more tinues in candidate state.

obvious and understandable.

The third possible outcome is that a candidate neither 5.3 Log replication wins nor loses the election: if many followers become candidates at the same time, votes could be split so that Once a leader has been elected, it begins servicing no candidate obtains a majority. When this happens, each client requests. Each client request contains a command to candidate will time out and start a new election by incre- be executed by the replicated state machines. The leader menting its term and initiating another round of Request- appends the command to its log as a new entry, then is- Vote RPCs. However, without extra measures split votes sues AppendEntries RPCs in parallel to each of the other could repeat indeﬁnitely.

servers to replicate the entry. When the entry has been safely replicated (as described below), the leader applies Raft uses randomized election timeouts to ensure that the entry to its state machine and returns the result of that split votes are rare and that they are resolved quickly. To execution to the client. If followers crash or run slowly, prevent split votes in the ﬁrst place, election timeouts are or if network packets are lost, the leader retries Append- chosen randomly from a ﬁxed interval (e.g., 150–300ms).

Entries RPCs indeﬁnitely (even after it has responded to This spreads out the servers so that in most cases only a the client) until all followers eventually store all log en- single server will time out; it wins the election and sends tries.

heartbeats before any other servers time out. The same mechanism is used to handle split votes. Each candidate Logs are organized as shown in Figure 6. Each log en- restarts its randomized election timeout at the start of an try stores a state machine command along with the term election, and it waits for that timeout to elapse before number when the entry was received by the leader. The starting the next election; this reduces the likelihood of term numbers in log entries are used to detect inconsis- another split vote in the new election. Section 9.3 shows tencies between logs and to ensure some of the properties that this approach elects a leader rapidly.

in Figure 3. Each log entry also has an integer index iden- 6

<!-- Page 7 -->

tifying its position in the log.

The leader decides when it is safe to apply a log en- try to the state machines; such an entry is calledcommit- ted. Raft guarantees that committed entries are durable and will eventually be executed by all of the available state machines. A log entry is committed once the leader that created the entry has replicated it on a majority of the servers (e.g., entry 7 in Figure 6). This also commits all preceding entries in the leader’s log, including entries created by previous leaders. Section 5.4 discusses some subtleties when applying this rule after leader changes, and it also shows that this deﬁnition of commitment is Figure 7: When the leader at the top comes to power, it is safe. The leader keeps track of the highest index it knows possible that any of scenarios (a–f) could occur in follower logs. Each box represents one log entry; the number in the to be committed, and it includes that index in future box is its term. A follower may be missing entries (a–b), may AppendEntries RPCs (including heartbeats) so that the have extra uncommitted entries (c–d), or both (e–f). For ex- other servers eventually ﬁnd out. Once a follower learns ample, scenario (f) could occur if that server was the leader that a log entry is committed, it applies the entry to its for term 2, added several entries to its log, then crashed before local state machine (in log order).

committing any of them; it restarted quickly, became leader We designed the Raft log mechanism to maintain a high for term 3, and added a few more entries to its log; before any level of coherency between the logs on different servers.

of the entries in either term 2 or term 3 were committed, the Not only does this simplify the system’s behavior and server crashed again and remained down for several terms.

make it more predictable, but it is an important component be missing entries that are present on the leader, it may of ensuring safety. Raft maintains the following proper- have extra entries that are not present on the leader, or ties, which together constitute the Log Matching Property both. Missing and extraneous entries in a log may span in Figure 3:

multiple terms.

- If two entries in different logs have the same index

In Raft, the leader handles inconsistencies by forcing and term, then they store the same command.

the followers’ logs to duplicate its own. This means that

- If two entries in different logs have the same index

conﬂicting entries in follower logs will be overwritten and term, then the logs are identical in all preceding with entries from the leader’s log. Section 5.4 will show entries.

that this is safe when coupled with one more restriction.

The ﬁrst property follows from the fact that a leader To bring a follower’s log into consistency with its own, creates at most one entry with a given log index in a given the leader must ﬁnd the latest log entry where the two term, and log entries never change their position in the logs agree, delete any entries in the follower’s log after log. The second property is guaranteed by a simple con- that point, and send the follower all of the leader’s entries sistency check performed by AppendEntries. When send- after that point. All of these actions happen in response ing an AppendEntries RPC, the leader includes the index to the consistency check performed by AppendEntries and term of the entry in its log that immediately precedes RPCs. The leader maintains anextIndexfor each follower, the new entries. If the follower does not ﬁnd an entry in which is the index of the next log entry the leader will its log with the same index and term, then it refuses the send to that follower. When a leader ﬁrst comes to power, new entries. The consistency check acts as an induction it initializes all nextIndex values to the index just after the step: the initial empty state of the logs satisﬁes the Log last one in its log (11 in Figure 7). If a follower’s log is Matching Property, and the consistency check preserves inconsistent with the leader’s, the AppendEntries consis- the Log Matching Property whenever logs are extended.

tency check will fail in the next AppendEntries RPC. Af- As a result, whenever AppendEntries returns successfully, ter a rejection, the leader decrements nextIndex and retries the leader knows that the follower’s log is identical to its the AppendEntries RPC. Eventually nextIndex will reach own log up through the new entries.

a point where the leader and follower logs match. When this happens, AppendEntries will succeed, which removes During normal operation, the logs of the leader and any conﬂicting entries in the follower’s log and appends followers stay consistent, so the AppendEntries consis- entries from the leader’s log (if any). Once AppendEntries tency check never fails. However, leader crashes can leave succeeds, the follower’s log is consistent with the leader’s, the logs inconsistent (the old leader may not have fully and it will remain that way for the rest of the term.

replicated all of the entries in its log). These inconsisten- If desired, the protocol can be optimized to reduce the cies can compound over a series of leader and follower number of rejected AppendEntries RPCs. For example, crashes. Figure 7 illustrates the ways in which followers’ when rejecting an AppendEntries request, the follower logs may differ from that of a new leader. A follower may 7

<!-- Page 8 -->

can include the term of the conﬂicting entry and the ﬁrst index it stores for that term. With this information, the leader can decrement nextIndex to bypass all of the con- ﬂicting entries in that term; one AppendEntries RPC will be required for each term with conﬂicting entries, rather than one RPC per entry. In practice, we doubt this opti- mization is necessary, since failures happen infrequently and it is unlikely that there will be many inconsistent en- tries.

Figure 8:A time sequence showing why a leader cannot de- With this mechanism, a leader does not need to take any termine commitment using log entries from older terms. In special actions to restore log consistency when it comes to (a) S1 is leader and partially replicates the log entry at index power. It just begins normal operation, and the logs auto-

2. In (b) S1 crashes; S5 is elected leader for term 3 with votes

matically converge in response to failures of the Append- from S3, S4, and itself, and accepts a different entry at log Entries consistency check. A leader never overwrites or index 2. In (c) S5 crashes; S1 restarts, is elected leader, and continues replication. At this point, the log entry from term 2 deletes entries in its own log (the Leader Append-Only has been replicated on a majority of the servers, but it is not Property in Figure 3).

committed. If S1 crashes as in (d), S5 could be elected leader This log replication mechanism exhibits the desirable (with votes from S2, S3, and S4) and overwrite the entry with consensus properties described in Section 2: Raft can ac- its own entry from term 3. However, if S1 replicates an en- cept, replicate, and apply new log entries as long as a ma- try from its current term on a majority of the servers before jority of the servers are up; in the normal case a new entry crashing, as in (e), then this entry is committed (S5 cannot can be replicated with a single round of RPCs to a ma- win an election). At this point all preceding entries in the log jority of the cluster; and a single slow follower will not are committed as well.

impact performance.

terms are present on each new leader from the moment of 5.4 Safety its election, without the need to transfer those entries to The previous sections described how Raft elects lead- the leader. This means that log entries only ﬂow in one di- ers and replicates log entries. However, the mechanisms rection, from leaders to followers, and leaders never over- described so far are not quite sufﬁcient to ensure that each write existing entries in their logs.

state machine executes exactly the same commands in the Raft uses the voting process to prevent a candidate from same order. For example, a follower might be unavailable winning an election unless its log contains all committed while the leader commits several log entries, then it could entries. A candidate must contact a majority of the cluster be elected leader and overwrite these entries with new in order to be elected, which means that every committed ones; as a result, different state machines might execute entry must be present in at least one of those servers. If the different command sequences.

candidate’s log is at least as up-to-date as any other log This section completes the Raft algorithm by adding a in that majority (where “up-to-date” is deﬁned precisely restriction on which servers may be elected leader. The below), then it will hold all the committed entries. The restriction ensures that the leader for any given term con- RequestVote RPC implements this restriction: the RPC tains all of the entries committed in previous terms (the includes information about the candidate’s log, and the Leader Completeness Property from Figure 3). Given the voter denies its vote if its own log is more up-to-date than election restriction, we then make the rules for commit- that of the candidate.

ment more precise. Finally, we present a proof sketch for Raft determines which of two logs is more up-to-date the Leader Completeness Property and show how it leads by comparing the index and term of the last entries in the to correct behavior of the replicated state machine.

logs. If the logs have last entries with different terms, then 5.4.1 Election restriction the log with the later term is more up-to-date. If the logs In any leader-based consensus algorithm, the leader end with the same term, then whichever log is longer is must eventually store all of the committed log entries. In more up-to-date.

some consensus algorithms, such as Viewstamped Repli- 5.4.2 Committing entries from previous terms cation [22], a leader can be elected even if it doesn’t As described in Section 5.3, a leader knows that an en- initially contain all of the committed entries. These al- try from its current term is committed once that entry is gorithms contain additional mechanisms to identify the stored on a majority of the servers. If a leader crashes be- missing entries and transmit them to the new leader, ei- fore committing an entry, future leaders will attempt to ther during the election process or shortly afterwards. Un- ﬁnish replicating the entry. However, a leader cannot im- fortunately, this results in considerable additional mecha- mediately conclude that an entry from a previous term is nism and complexity. Raft uses a simpler approach where committed once it is stored on a majority of servers. Fig- it guarantees that all the committed entries from previous 8

<!-- Page 9 -->

leaderU, as shown in Figure 9. The voter is key to reaching a contradiction.

3. The voter must have accepted the committed entry

from leaderT beforevoting for leaderU; otherwise it would have rejected the AppendEntries request from leaderT(its current term would have been higher than T).

Figure 9:If S1 (leader for term T) commits a new log entry

4. The voter still stored the entry when it voted for

from its term, and S5 is elected leader for a later term U, then leaderU, since every intervening leader contained the there must be at least one server (S3) that accepted the log entry (by assumption), leaders never remove entries, entry and also voted for S5.

and followers only remove entries if they conﬂict ure 8 illustrates a situation where an old log entry is stored with the leader.

on a majority of servers, yet can still be overwritten by a

5. The voter granted its vote to leaderU, so leaderU’s

future leader.

log must have been as up-to-date as the voter’s. This To eliminate problems like the one in Figure 8, Raft leads to one of two contradictions.

never commits log entries from previous terms by count-

6. First, if the voter and leaderU shared the same last

ing replicas. Only log entries from the leader’s current log term, then leaderU’s log must have been at least term are committed by counting replicas; once an entry as long as the voter’s, so its log contained every entry from the current term has been committed in this way, in the voter’s log. This is a contradiction, since the then all prior entries are committed indirectly because voter contained the committed entry and leaderUwas of the Log Matching Property. There are some situations assumed not to.

where a leader could safely conclude that an older log en-

7. Otherwise, leaderU’s last log term must have been

try is committed (for example, if that entry is stored on ev- larger than the voter’s. Moreover, it was larger than ery server), but Raft takes a more conservative approach T, since the voter’s last log term was at least T (it con- for simplicity.

tains the committed entry from term T). The earlier Raft incurs this extra complexity in the commitment leader that created leaderU’s last log entry must have rules because log entries retain their original term num- contained the committed entry in its log (by assump- bers when a leader replicates entries from previous tion). Then, by the Log Matching Property, leaderU’s terms. In other consensus algorithms, if a new leader re- log must also contain the committed entry, which is replicates entries from prior “terms,” it must do so with a contradiction.

its new “term number.” Raft’s approach makes it easier

8. This completes the contradiction. Thus, the leaders

to reason about log entries, since they maintain the same of all terms greater than T must contain all entries term number over time and across logs. In addition, new from term T that are committed in term T.

leaders in Raft send fewer log entries from previous terms than in other algorithms (other algorithms must send re-

9. The Log Matching Property guarantees that future

dundant log entries to renumber them before they can be leaders will also contain entries that are committed committed).

indirectly, such as index 2 in Figure 8(d).

5.4.3 Safety argument Given the Leader Completeness Property, we can prove Given the complete Raft algorithm, we can now ar- the State Machine Safety Property from Figure 3, which gue more precisely that the Leader Completeness Prop- states that if a server has applied a log entry at a given erty holds (this argument is based on the safety proof; see index to its state machine, no other server will ever apply a Section 9.2). We assume that the Leader Completeness different log entry for the same index. At the time a server Property does not hold, then we prove a contradiction.

applies a log entry to its state machine, its log must be Suppose the leader for term T (leaderT) commits a log identical to the leader’s log up through that entry and the entry from its term, but that log entry is not stored by the entry must be committed. Now consider the lowest term leader of some future term. Consider the smallest term U in which any server applies a given log index; the Log >T whose leader (leaderU) does not store the entry.

Completeness Property guarantees that the leaders for all

1. The committed entry must have been absent from

higher terms will store that same log entry, so servers that leaderU’s log at the time of its election (leaders never apply the index in later terms will apply the same value.

delete or overwrite entries).

Thus, the State Machine Safety Property holds.

2. leaderTreplicated the entry on a majority of the clus-

Finally, Raft requires servers to apply entries in log in- ter, and leaderU received votes from a majority of dex order. Combined with the State Machine Safety Prop- the cluster. Thus, at least one server (“the voter”) erty, this means that all servers will apply exactly the same both accepted the entry from leaderT and voted for set of log entries to their state machines, in the same order.

9

<!-- Page 10 -->

5.5 Follower and candidate crashes Until this point we have focused on leader failures. Fol- lower and candidate crashes are much simpler to han- dle than leader crashes, and they are both handled in the same way. If a follower or candidate crashes, then fu- ture RequestVote and AppendEntries RPCs sent to it will fail. Raft handles these failures by retrying indeﬁnitely;

if the crashed server restarts, then the RPC will complete successfully. If a server crashes after completing an RPC but before responding, then it will receive the same RPC Figure 10:Switching directly from one conﬁguration to an- again after it restarts. Raft RPCs are idempotent, so this other is unsafe because different servers will switch at dif- causes no harm. For example, if a follower receives an ferent times. In this example, the cluster grows from three AppendEntries request that includes log entries already servers to ﬁve. Unfortunately, there is a point in time where present in its log, it ignores those entries in the new re- two different leaders can be elected for the same term, one quest.

with a majority of the old conﬁguration (Cold) and another 5.6 Timing and availability with a majority of the new conﬁguration (Cnew).

One of our requirements for Raft is that safety must server MTBFs are several months or more, which easily not depend on timing: the system must not produce incor- satisﬁes the timing requirement.

rect results just because some event happens more quickly 6 Cluster membership changes or slowly than expected. However, availability (the ability of the system to respond to clients in a timely manner) Up until now we have assumed that the clusterconﬁg- must inevitably depend on timing. For example, if mes- uration (the set of servers participating in the consensus sage exchanges take longer than the typical time between algorithm) is ﬁxed. In practice, it will occasionally be nec- server crashes, candidates will not stay up long enough to essary to change the conﬁguration, for example to replace win an election; without a steady leader, Raft cannot make servers when they fail or to change the degree of replica- progress.

tion. Although this can be done by taking the entire cluster Leader election is the aspect of Raft where timing is off-line, updating conﬁguration ﬁles, and then restarting most critical. Raft will be able to elect and maintain a the cluster, this would leave the cluster unavailable dur- steady leader as long as the system satisﬁes the follow- ing the changeover. In addition, if there are any manual ingtiming requirement:

steps, they risk operator error. In order to avoid these is- broadcastTime≪electionTimeout≪MTBF sues, we decided to automate conﬁguration changes and incorporate them into the Raft consensus algorithm.

In this inequality broadcastTime is the average time it For the conﬁguration change mechanism to be safe, takes a server to send RPCs in parallel to every server there must be no point during the transition where it in the cluster and receive their responses; electionTime- is possible for two leaders to be elected for the same out is the election timeout described in Section 5.2; and term. Unfortunately, any approach where servers switch MTBF is the average time between failures for a single directly from the old conﬁguration to the new conﬁgura- server. The broadcast time should be an order of mag- tion is unsafe. It isn’t possible to atomically switch all of nitude less than the election timeout so that leaders can the servers at once, so the cluster can potentially split into reliably send the heartbeat messages required to keep fol- two independent majorities during the transition (see Fig- lowers from starting elections; given the randomized ap- ure 10).

proach used for election timeouts, this inequality also In order to ensure safety, conﬁguration changes must makes split votes unlikely. The election timeout should be use a two-phase approach. There are a variety of ways a few orders of magnitude less than MTBF so that the sys- to implement the two phases. For example, some systems tem makes steady progress. When the leader crashes, the (e.g., [22]) use the ﬁrst phase to disable the old conﬁgura- system will be unavailable for roughly the election time- tion so it cannot process client requests; then the second out; we would like this to represent only a small fraction phase enables the new conﬁguration. In Raft the cluster of overall time.

ﬁrst switches to a transitional conﬁguration we call joint The broadcast time and MTBF are properties of the un- consensus; once the joint consensus has been committed, derlying system, while the election timeout is something the system then transitions to the new conﬁguration. The we must choose. Raft’s RPCs typically require the recip- joint consensus combines both the old and new conﬁgu- ient to persist information to stable storage, so the broad- rations:

cast time may range from 0.5ms to 20ms, depending on

- Log entries are replicated to all servers in both con-

storage technology. As a result, the election timeout is ﬁgurations.

likely to be somewhere between 10ms and 500ms. Typical 10

<!-- Page 11 -->

There are three more issues to address for reconﬁgura- tion. The ﬁrst issue is that new servers may not initially store any log entries. If they are added to the cluster in this state, it could take quite a while for them to catch up, during which time it might not be possible to com- mit new log entries. In order to avoid availability gaps, Raft introduces an additional phase before the conﬁgu- ration change, in which the new servers join the cluster as non-voting members (the leader replicates log entries Figure 11:Timeline for a conﬁguration change. Dashed lines to them, but they are not considered for majorities). Once show conﬁguration entries that have been created but not the new servers have caught up with the rest of the cluster, committed, and solid lines show the latest committed conﬁgu- ration entry. The leader ﬁrst creates theCold,newconﬁguration the reconﬁguration can proceed as described above.

entry in its log and commits it toCold,new (a majority ofCold The second issue is that the cluster leader may not be and a majority ofCnew). Then it creates theCnew entry and part of the new conﬁguration. In this case, the leader steps commits it to a majority ofCnew. There is no point in time in down (returns to follower state) once it has committed the whichCold andCnewcan both make decisions independently.

Cnew log entry. This means that there will be a period of

- Any server from either conﬁguration may serve as

time (while it is committingCnew) when the leader is man- leader.

aging a cluster that does not include itself; it replicates log

- Agreement (for elections and entry commitment) re-

entries but does not count itself in majorities. The leader quires separate majorities fromboththe old and new transition occurs whenCnew is committed because this is conﬁgurations.

the ﬁrst point when the new conﬁguration can operate in- The joint consensus allows individual servers to transition dependently (it will always be possible to choose a leader between conﬁgurations at different times without com- fromCnew). Before this point, it may be the case that only promising safety. Furthermore, joint consensus allows the a server fromCold can be elected leader.

cluster to continue servicing client requests throughout The third issue is that removed servers (those not in the conﬁguration change.

Cnew) can disrupt the cluster. These servers will not re- Cluster conﬁgurations are stored and communicated ceive heartbeats, so they will time out and start new elec- using special entries in the replicated log; Figure 11 illus- tions. They will then send RequestVote RPCs with new trates the conﬁguration change process. When the leader term numbers, and this will cause the current leader to receives a request to change the conﬁguration fromCold revert to follower state. A new leader will eventually be to Cnew, it stores the conﬁguration for joint consensus elected, but the removed servers will time out again and (Cold,new in the ﬁgure) as a log entry and replicates that the process will repeat, resulting in poor availability.

entry using the mechanisms described previously. Once a To prevent this problem, servers disregard RequestVote given server adds the new conﬁguration entry to its log, RPCs when they believe a current leader exists. Specif- it uses that conﬁguration for all future decisions (a server ically, if a server receives a RequestVote RPC within always uses the latest conﬁguration in its log, regardless the minimum election timeout of hearing from a cur- of whether the entry is committed). This means that the rent leader, it does not update its term or grant its vote.

leader will use the rules ofCold,new to determine when the This does not affect normal elections, where each server log entry forCold,new is committed. If the leader crashes, waits at least a minimum election timeout before starting a new leader may be chosen under eitherCold orCold,new, an election. However, it helps avoid disruptions from re- depending on whether the winning candidate has received moved servers: if a leader is able to get heartbeats to its Cold,new. In any case, Cnew cannot make unilateral deci- cluster, then it will not be deposed by larger term num- sions during this period.

bers.

OnceCold,newhas been committed, neitherColdnorCnew 7 Log compaction can make decisions without approval of the other, and the Raft’s log grows during normal operation to incorpo- Leader Completeness Property ensures that only servers rate more client requests, but in a practical system, it can- with theCold,new log entry can be elected as leader. It is not grow without bound. As the log grows longer, it oc- now safe for the leader to create a log entry describing cupies more space and takes more time to replay. This Cnew and replicate it to the cluster. Again, this conﬁgura- will eventually cause availability problems without some tion will take effect on each server as soon as it is seen.

mechanism to discard obsolete information that has accu- When the new conﬁguration has been committed under mulated in the log.

the rules ofCnew, the old conﬁguration is irrelevant and servers not in the new conﬁguration can be shut down. As Snapshotting is the simplest approach to compaction.

shown in Figure 11, there is no time whenCold andCnew In snapshotting, the entire current system state is written to a snapshot on stable storage, then the entire log up to can both make unilateral decisions; this guarantees safety.

11

<!-- Page 12 -->

**InstallSnapshot RPC** Invoked by leader to send chunks of a snapshot to a follower.

Leaders always send chunks in order.

**Arguments:** leader’s term **term** **leaderId** so follower can redirect clients **lastIncludedIndex** the snapshot replaces all entries up through and including this index **lastIncludedTerm** term of lastIncludedIndex **offset** byte offset where chunk is positioned in the snapshot file **data[]** raw bytes of the snapshot chunk, starting at Figure 12:A server replaces the committed entries in its log offset (indexes 1 through 5) with a new snapshot, which stores just **done** true if this is the last chunk the current state (variablesxandyin this example). The snap- **Results:** shot’s last included index and term serve to position the snap- **term** currentTerm, for leader to update itself shot in the log preceding entry 6.

**Receiver implementation:** that point is discarded. Snapshotting is used in Chubby

1. 

Reply immediately if term < currentTerm and ZooKeeper, and the remainder of this section de-

2. 

Create new snapshot file if first chunk (offset is 0)

3. 

Write data into snapshot file at given offset scribes snapshotting in Raft.

4. 

Reply and wait for more data chunks if done is false Incremental approaches to compaction, such as log

5. 

Save snapshot file, discard any existing or partial snapshot cleaning [36] and log-structured merge trees [30, 5], are with a smaller index

6. 

If existing log entry has same index and term as snapshot’s also possible. These operate on a fraction of the data at last included entry, retain log entries following it and reply once, so they spread the load of compaction more evenly

7. 

Discard the entire log over time. They ﬁrst select a region of data that has ac-

8. 

Reset state machine using snapshot contents (and load cumulated many deleted and overwritten objects, then snapshot’s cluster configuration) they rewrite the live objects from that region more com- Figure 13: A summary of the InstallSnapshot RPC. Snap- pactly and free the region. This requires signiﬁcant addi- shots are split into chunks for transmission; this gives the fol- tional mechanism and complexity compared to snapshot- lower a sign of life with each chunk, so it can reset its election ting, which simpliﬁes the problem by always operating timer.

on the entire data set. While log cleaning would require leader would already have this entry. However, an excep- modiﬁcations to Raft, state machines can implement LSM tionally slow follower or a new server joining the cluster trees using the same interface as snapshotting.

(Section 6) would not. The way to bring such a follower Figure 12 shows the basic idea of snapshotting in Raft.

up-to-date is for the leader to send it a snapshot over the Each server takes snapshots independently, covering just network.

the committed entries in its log. Most of the work con- The leader uses a new RPC called InstallSnapshot to sists of the state machine writing its current state to the send snapshots to followers that are too far behind; see snapshot. Raft also includes a small amount of metadata Figure 13. When a follower receives a snapshot with this in the snapshot: thelast included indexis the index of the RPC, it must decide what to do with its existing log en- last entry in the log that the snapshot replaces (the last en- tries. Usually the snapshot will contain new information try the state machine had applied), and the last included not already in the recipient’s log. In this case, the follower termis the term of this entry. These are preserved to sup- discards its entire log; it is all superseded by the snapshot port the AppendEntries consistency check for the ﬁrst log and may possibly have uncommitted entries that conﬂict entry following the snapshot, since that entry needs a pre- with the snapshot. If instead the follower receives a snap- vious log index and term. To enable cluster membership shot that describes a preﬁx of its log (due to retransmis- changes (Section 6), the snapshot also includes the latest sion or by mistake), then log entries covered by the snap- conﬁguration in the log as of last included index. Once a shot are deleted but entries following the snapshot are still server completes writing a snapshot, it may delete all log valid and must be retained.

entries up through the last included index, as well as any prior snapshot.

This snapshotting approach departs from Raft’s strong Although servers normally take snapshots indepen- leader principle, since followers can take snapshots with- dently, the leader must occasionally send snapshots to out the knowledge of the leader. However, we think this followers that lag behind. This happens when the leader departure is justiﬁed. While having a leader helps avoid has already discarded the next log entry that it needs to conﬂicting decisions in reaching consensus, consensus send to a follower. Fortunately, this situation is unlikely has already been reached when snapshotting, so no de- in normal operation: a follower that has kept up with the cisions conﬂict. Data still only ﬂows from leaders to fol- 12

<!-- Page 13 -->

lowers, just followers can now reorganize their data.

crashes after committing the log entry but before respond- ing to the client, the client will retry the command with a We considered an alternative leader-based approach in new leader, causing it to be executed a second time. The which only the leader would create a snapshot, then it solution is for clients to assign unique serial numbers to would send this snapshot to each of its followers. How- every command. Then, the state machine tracks the latest ever, this has two disadvantages. First, sending the snap- serial number processed for each client, along with the as- shot to each follower would waste network bandwidth and sociated response. If it receives a command whose serial slow the snapshotting process. Each follower already has number has already been executed, it responds immedi- the information needed to produce its own snapshots, and ately without re-executing the request.

it is typically much cheaper for a server to produce a snap- Read-only operations can be handled without writing shot from its local state than it is to send and receive one anything into the log. However, with no additional mea- over the network. Second, the leader’s implementation sures, this would run the risk of returning stale data, since would be more complex. For example, the leader would the leader responding to the request might have been su- need to send snapshots to followers in parallel with repli- perseded by a newer leader of which it is unaware. Lin- cating new log entries to them, so as not to block new earizable reads must not return stale data, and Raft needs client requests.

two extra precautions to guarantee this without using the There are two more issues that impact snapshotting per- log. First, a leader must have the latest information on formance. First, servers must decide when to snapshot. If which entries are committed. The Leader Completeness a server snapshots too often, it wastes disk bandwidth and Property guarantees that a leader has all committed en- energy; if it snapshots too infrequently, it risks exhaust- tries, but at the start of its term, it may not know which ing its storage capacity, and it increases the time required those are. To ﬁnd out, it needs to commit an entry from to replay the log during restarts. One simple strategy is its term. Raft handles this by having each leader com- to take a snapshot when the log reaches a ﬁxed size in mit a blank no-op entry into the log at the start of its bytes. If this size is set to be signiﬁcantly larger than the term. Second, a leader must check whether it has been de- expected size of a snapshot, then the disk bandwidth over- posed before processing a read-only request (its informa- head for snapshotting will be small.

tion may be stale if a more recent leader has been elected).

The second performance issue is that writing a snap- Raft handles this by having the leader exchange heart- shot can take a signiﬁcant amount of time, and we do beat messages with a majority of the cluster before re- not want this to delay normal operations. The solution is sponding to read-only requests. Alternatively, the leader to use copy-on-write techniques so that new updates can could rely on the heartbeat mechanism to provide a form be accepted without impacting the snapshot being writ- of lease [9], but this would rely on timing for safety (it ten. For example, state machines built with functional data assumes bounded clock skew).

structures naturally support this. Alternatively, the operat- ing system’s copy-on-write support (e.g., fork on Linux) 9 Implementation and evaluation can be used to create an in-memory snapshot of the entire We have implemented Raft as part of a replicated state machine (our implementation uses this approach).

state machine that stores conﬁguration information for RAMCloud [33] and assists in failover of the RAMCloud 8 Client interaction coordinator. The Raft implementation contains roughly This section describes how clients interact with Raft, 2000 lines of C++ code, not including tests, comments, or including how clients ﬁnd the cluster leader and how Raft blank lines. The source code is freely available [23]. There supports linearizable semantics [10]. These issues apply are also about 25 independent third-party open source im- to all consensus-based systems, and Raft’s solutions are plementations [34] of Raft in various stages of develop- similar to other systems.

ment, based on drafts of this paper. Also, various compa- Clients of Raft send all of their requests to the leader.

nies are deploying Raft-based systems [34].

When a client ﬁrst starts up, it connects to a randomly- The remainder of this section evaluates Raft using three chosen server. If the client’s ﬁrst choice is not the leader, criteria: understandability, correctness, and performance.

that server will reject the client’s request and supply in- 9.1 Understandability formation about the most recent leader it has heard from (AppendEntries requests include the network address of To measure Raft’s understandability relative to Paxos, the leader). If the leader crashes, client requests will time we conducted an experimental study using upper-level un- out; clients then try again with randomly-chosen servers.

dergraduate and graduate students in an Advanced Oper- Our goal for Raft is to implement linearizable seman- ating Systems course at Stanford University and a Dis- tics (each operation appears to execute instantaneously, tributed Computing course at U.C. Berkeley. We recorded exactly once, at some point between its invocation and a video lecture of Raft and another of Paxos, and created its response). However, as described so far Raft can exe- corresponding quizzes. The Raft lecture covered the con- cute a command multiple times: for example, if the leader tent of this paper except for log compaction; the Paxos 13

<!-- Page 14 -->

20 number of participants 60 15 Paxos much easier 50 Paxos somewhat easier Roughly equal 10 Raft somewhat easier 40 Raft much easier Raft grade 5 30 0 implement explain 20 Figure 15: Using a 5-point scale, participants were asked (left) which algorithm they felt would be easier to implement 10 Raft then Paxos in a functioning, correct, and efﬁcient system, and (right) Paxos then Raft which would be easier to explain to a CS graduate student.

0 0 10 20 30 40 50 60 the order in which they learned the algorithms. The model Paxos grade predicts that the choice of quiz produces a 12.5-point dif- Figure 14: A scatter plot comparing 43 participants’ perfor- ference in favor of Raft. This is signiﬁcantly higher than mance on the Raft and Paxos quizzes. Points above the diag- the observed difference of 4.9 points, because many of the onal (33) represent participants who scored higher for Raft.

actual students had prior Paxos experience, which helped lecture covered enough material to create an equivalent Paxos considerably, whereas it helped Raft slightly less.

replicated state machine, including single-decree Paxos, Curiously, the model also predicts scores 6.3 points lower multi-decree Paxos, reconﬁguration, and a few optimiza- on Raft for people that have already taken the Paxos quiz;

tions needed in practice (such as leader election). The although we don’t know why, this does appear to be sta- quizzes tested basic understanding of the algorithms and tistically signiﬁcant.

also required students to reason about corner cases. Each We also surveyed participants after their quizzes to see student watched one video, took the corresponding quiz, which algorithm they felt would be easier to implement watched the second video, and took the second quiz.

or explain; these results are shown in Figure 15. An over- About half of the participants did the Paxos portion ﬁrst whelming majority of participants reported Raft would be and the other half did the Raft portion ﬁrst in order to easier to implement and explain (33 of 41 for each ques- account for both individual differences in performance tion). However, these self-reported feelings may be less and experience gained from the ﬁrst portion of the study.

reliable than participants’ quiz scores, and participants We compared participants’ scores on each quiz to deter- may have been biased by knowledge of our hypothesis mine whether participants showed a better understanding that Raft is easier to understand.

of Raft.

A detailed discussion of the Raft user study is available We tried to make the comparison between Paxos and at [31].

Raft as fair as possible. The experiment favored Paxos in two ways: 15 of the 43 participants reported having some 9.2 Correctness prior experience with Paxos, and the Paxos video is 14% We have developed a formal speciﬁcation and a proof longer than the Raft video. As summarized in Table 1, we of safety for the consensus mechanism described in Sec- have taken steps to mitigate potential sources of bias. All tion 5. The formal speciﬁcation [31] makes the informa- of our materials are available for review [28, 31].

tion summarized in Figure 2 completely precise using the On average, participants scored 4.9 points higher on the TLA+ speciﬁcation language [17]. It is about 400 lines Raft quiz than on the Paxos quiz (out of a possible 60 long and serves as the subject of the proof. It is also use- points, the mean Raft score was 25.7 and the mean Paxos ful on its own for anyone implementing Raft. We have score was 20.8); Figure 14 shows their individual scores.

mechanically proven the Log Completeness Property us- A pairedt-test states that, with 95% conﬁdence, the true ing the TLA proof system [7]. However, this proof relies distribution of Raft scores has a mean at least 2.5 points on invariants that have not been mechanically checked larger than the true distribution of Paxos scores.

(for example, we have not proven the type safety of the We also created a linear regression model that predicts speciﬁcation). Furthermore, we have written an informal a new student’s quiz scores based on three factors: which proof [31] of the State Machine Safety property which quiz they took, their degree of prior Paxos experience, and is complete (it relies on the speciﬁcation alone) and rela- Concern Steps taken to mitigate bias Materials for review [28, 31] Equal lecture quality Same lecturer for both. Paxos lecture based on and improved from exist- videos ing materials used in several universities. Paxos lecture is 14% longer.

Equal quiz difﬁculty Questions grouped in difﬁculty and paired across exams.

quizzes Fair grading Used rubric. Graded in random order, alternating between quizzes.

rubric Table 1:Concerns of possible bias against Paxos in the study, steps taken to counter each, and additional materials available.

14

<!-- Page 15 -->

100% ing). The leader was crashed uniformly randomly within cumulative percent its heartbeat interval, which was half of the minimum 80% election timeout for all tests. Thus, the smallest possible 60% downtime was about half of the minimum election time- 150-150ms 150-151ms 40% out.

150-155ms 150-175ms 20% The top graph in Figure 16 shows that a small amount 150-200ms 150-300ms of randomization in the election timeout is enough to 0% avoid split votes in elections. In the absence of random- 100 1000 10000 100000 ness, leader election consistently took longer than 10 sec- 100% cumulative percent onds in our tests due to many split votes. Adding just 5ms 80% of randomness helps signiﬁcantly, resulting in a median 60% downtime of 287ms. Using more randomness improves 12-24ms 40% 25-50ms worst-case behavior: with 50ms of randomness the worst- 50-100ms 20% 100-200ms case completion time (over 1000 trials) was 513ms.

150-300ms 0% The bottom graph in Figure 16 shows that downtime 0 100 200 300 400 500 600 can be reduced by reducing the election timeout. With time without leader (ms) an election timeout of 12–24ms, it takes only 35ms on Figure 16: The time to detect and replace a crashed leader.

average to elect a leader (the longest trial took 152ms).

The top graph varies the amount of randomness in election However, lowering the timeouts beyond this point violates timeouts, and the bottom graph scales the minimum election timeout. Each line represents 1000 trials (except for 100 tri- Raft’s timing requirement: leaders have difﬁculty broad- als for “150–150ms”) and corresponds to a particular choice casting heartbeats before other servers start new elections.

of election timeouts; for example, “150–155ms” means that This can cause unnecessary leader changes and lower election timeouts were chosen randomly and uniformly be- overall system availability. We recommend using a con- tween 150ms and 155ms. The measurements were taken on a servative election timeout such as 150–300ms; such time- cluster of ﬁve servers with a broadcast time of roughly 15ms.

outs are unlikely to cause unnecessary leader changes and Results for a cluster of nine servers are similar.

will still provide good availability.

tively precise (it is about 3500 words long).

10 Related work 9.3 Performance There have been numerous publications related to con- Raft’s performance is similar to other consensus algo- sensus algorithms, many of which fall into one of the fol- rithms such as Paxos. The most important case for per- lowing categories:

formance is when an established leader is replicating new

- Lamport’s original description of Paxos [15], and at-

log entries. Raft achieves this using the minimal number tempts to explain it more clearly [16, 20, 21].

of messages (a single round-trip from the leader to half the

- Elaborations of Paxos, which ﬁll in missing details

cluster). It is also possible to further improve Raft’s per- and modify the algorithm to provide a better founda- formance. For example, it easily supports batching and tion for implementation [26, 39, 13].

pipelining requests for higher throughput and lower la-

- Systems that implement consensus algorithms, such

tency. Various optimizations have been proposed in the as Chubby [2, 4], ZooKeeper [11, 12], and Span- literature for other algorithms; many of these could be ap- ner [6]. The algorithms for Chubby and Spanner plied to Raft, but we leave this to future work.

have not been published in detail, though both claim We used our Raft implementation to measure the per- to be based on Paxos. ZooKeeper’s algorithm has formance of Raft’s leader election algorithm and answer been published in more detail, but it is quite different two questions. First, does the election process converge from Paxos.

- Performance optimizations that can be applied to

quickly? Second, what is the minimum downtime that can be achieved after leader crashes?

Paxos [18, 19, 3, 25, 1, 27].

- Oki and Liskov’s Viewstamped Replication (VR), an

To measure leader election, we repeatedly crashed the alternative approach to consensus developed around leader of a cluster of ﬁve servers and timed how long it the same time as Paxos. The original description [29] took to detect the crash and elect a new leader (see Fig- was intertwined with a protocol for distributed trans- ure 16). To generate a worst-case scenario, the servers in actions, but the core consensus protocol has been each trial had different log lengths, so some candidates separated in a recent update [22]. VR uses a leader- were not eligible to become leader. Furthermore, to en- based approach with many similarities to Raft.

courage split votes, our test script triggered a synchro- nized broadcast of heartbeat RPCs from the leader before The greatest difference between Raft and Paxos is terminating its process (this approximates the behavior Raft’s strong leadership: Raft uses leader election as an of the leader replicating a new log entry prior to crash- essential part of the consensus protocol, and it concen- 15

<!-- Page 16 -->

trates as much functionality as possible in the leader. This Several different approaches for cluster member- approach results in a simpler algorithm that is easier to ship changes have been proposed or implemented in understand. For example, in Paxos, leader election is or- other work, including Lamport’s original proposal [15], thogonal to the basic consensus protocol: it serves only as VR [22], and SMART [24]. We chose the joint consensus a performance optimization and is not required for achiev- approach for Raft because it leverages the rest of the con- ing consensus. However, this results in additional mecha- sensus protocol, so that very little additional mechanism is required for membership changes. Lamport’sα-based nism: Paxos includes both a two-phase protocol for basic consensus and a separate mechanism for leader election.

approach was not an option for Raft because it assumes In contrast, Raft incorporates leader election directly into consensus can be reached without a leader. In comparison the consensus algorithm and uses it as the ﬁrst of the two to VR and SMART, Raft’s reconﬁguration algorithm has phases of consensus. This results in less mechanism than the advantage that membership changes can occur with- in Paxos.

out limiting the processing of normal requests; in con- trast, VR stops all normal processing during conﬁgura- Like Raft, VR and ZooKeeper are leader-based and tion changes, and SMART imposes anα-like limit on the therefore share many of Raft’s advantages over Paxos.

number of outstanding requests. Raft’s approach also adds However, Raft has less mechanism that VR or ZooKeeper less mechanism than either VR or SMART.

because it minimizes the functionality in non-leaders. For 11 Conclusion example, log entries in Raft ﬂow in only one direction:

outward from the leader in AppendEntries RPCs. In VR Algorithms are often designed with correctness, efﬁ- log entries ﬂow in both directions (leaders can receive ciency, and/or conciseness as the primary goals. Although log entries during the election process); this results in these are all worthy goals, we believe that understandabil- additional mechanism and complexity. The published de- ity is just as important. None of the other goals can be scription of ZooKeeper also transfers log entries both to achieved until developers render the algorithm into a prac- and from the leader, but the implementation is apparently tical implementation, which will inevitably deviate from more like Raft [35].

and expand upon the published form. Unless developers have a deep understanding of the algorithm and can cre- Raft has fewer message types than any other algo- ate intuitions about it, it will be difﬁcult for them to retain rithm for consensus-based log replication that we are its desirable properties in their implementation.

aware of. For example, we counted the message types VR In this paper we addressed the issue of distributed con- and ZooKeeper use for basic consensus and membership sensus, where a widely accepted but impenetrable algo- changes (excluding log compaction and client interaction, rithm, Paxos, has challenged students and developers for as these are nearly independent of the algorithms). VR many years. We developed a new algorithm, Raft, which and ZooKeeper each deﬁne 10 different message types, we have shown to be more understandable than Paxos.

while Raft has only 4 message types (two RPC requests We also believe that Raft provides a better foundation and their responses). Raft’s messages are a bit more dense for system building. Using understandability as the pri- than the other algorithms’, but they are simpler collec- mary design goal changed the way we approached the de- tively. In addition, VR and ZooKeeper are described in sign of Raft; as the design progressed we found ourselves terms of transmitting entire logs during leader changes;

reusing a few techniques repeatedly, such as decomposing additional message types will be required to optimize the problem and simplifying the state space. These tech- these mechanisms so that they are practical.

niques not only improved the understandability of Raft Raft’s strong leadership approach simpliﬁes the algo- but also made it easier to convince ourselves of its cor- rithm, but it precludes some performance optimizations.

rectness.

For example, Egalitarian Paxos (EPaxos) can achieve 12 Acknowledgments higher performance under some conditions with a lead- erless approach [27]. EPaxos exploits commutativity in The user study would not have been possible with- state machine commands. Any server can commit a com- out the support of Ali Ghodsi, David Mazi`eres, and the mand with just one round of communication as long as students of CS 294-91 at Berkeley and CS 240 at Stan- other commands that are proposed concurrently commute ford. Scott Klemmer helped us design the user study, with it. However, if commands that are proposed con- and Nelson Ray advised us on statistical analysis. The currently do not commute with each other, EPaxos re- Paxos slides for the user study borrowed heavily from quires an additional round of communication. Because a slide deck originally created by Lorenzo Alvisi. Spe- any server may commit commands, EPaxos balances load cial thanks go to David Mazi`eres and Ezra Hoch for well between servers and is able to achieve lower latency ﬁnding subtle bugs in Raft. Many people provided help- than Raft in WAN settings. However, it adds signiﬁcant ful feedback on the paper and user study materials, complexity to Paxos.

including Ed Bugnion, Michael Chan, Hugues Evrard, 16

<!-- Page 17 -->

Daniel Gifﬁn, Arjun Gopalan, Jon Howell, Vimalkumar [7] COUSINEAU, D., DOLIGEZ, D., LAMPORT, L., MERZ, S., RICKETTS, D., AND VANZETTO, H. TLA+ proofs.

Jeyakumar, Ankita Kejriwal, Aleksandar Kracun, Amit In Proc. FM’12, Symposium on Formal Methods (2012), Levy, Joel Martin, Satoshi Matsushita, Oleg Pesok, David D. Giannakopoulou and D. M´ery, Eds., vol. 7436 of Lec- Ramos, Robbert van Renesse, Mendel Rosenblum, Nico- ture Notes in Computer Science, Springer, pp. 147–154.

las Schiper, Deian Stefan, Andrew Stone, Ryan Stutsman, David Terei, Stephen Yang, Matei Zaharia, 24 anony- [8] GHEMAWAT, S., GOBIOFF, H., AND LEUNG, S.-T. The Google ﬁle system. In Proc. SOSP’03, ACM Symposium mous conference reviewers (with duplicates), and espe- on Operating Systems Principles(2003), ACM, pp. 29–43.

cially our shepherd Eddie Kohler. Werner Vogels tweeted a link to an earlier draft, which gave Raft signiﬁcant ex- [9] GRAY, C., ANDCHERITON, D. Leases: An efﬁcient fault- posure. This work was supported by the Gigascale Sys- tolerant mechanism for distributed ﬁle cache consistency.

tems Research Center and the Multiscale Systems Cen- InProceedings of the 12th ACM Ssymposium on Operating Systems Principles(1989), pp. 202–210.

ter, two of six research centers funded under the Fo- cus Center Research Program, a Semiconductor Research [10] HERLIHY, M. P., AND WING, J. M. Linearizability: a Corporation program, by STARnet, a Semiconductor Re- correctness condition for concurrent objects. ACM Trans- search Corporation program sponsored by MARCO and actions on Programming Languages and Systems 12(July

1990. , 463–492.

DARPA, by the National Science Foundation under Grant No. 0963859, and by grants from Facebook, Google, Mel- [11] HUNT, P., KONAR, M., JUNQUEIRA, F. P., AND REED, lanox, NEC, NetApp, SAP, and Samsung. Diego Ongaro B. ZooKeeper: wait-free coordination for internet-scale is supported by The Junglee Corporation Stanford Gradu- systems. InProc ATC’10, USENIX Annual Technical Con- ate Fellowship.

ference(2010), USENIX, pp. 145–158.

[12] JUNQUEIRA, F. P., REED, B. C., AND SERAFINI, M.

References Zab: High-performance broadcast for primary-backup sys- [1] BOLOSKY, W. J., BRADSHAW, D., HAAGENS, R. B., tems. InProc. DSN’11, IEEE/IFIP Int’l Conf. on Depend- KUSTERS, N. P., AND LI, P.

Paxos replicated state able Systems & Networks(2011), IEEE Computer Society, machines as the basis of a high-performance data store.

pp. 245–256.

In Proc. NSDI’11, USENIX Conference on Networked Systems Design and Implementation (2011), USENIX, [13] KIRSCH, J., AND AMIR, Y. Paxos for system builders.

pp. 141–154.

Tech. Rep. CNDS-2008-2, Johns Hopkins University,

2008. 

[2] BURROWS, M.

The Chubby lock service for loosely- coupled distributed systems. In Proc. OSDI’06, Sympo- [14] LAMPORT, L. Time, clocks, and the ordering of events in sium on Operating Systems Design and Implementation a distributed system. Commununications of the ACM 21, 7 (2006), USENIX, pp. 335–350.

(July 1978), 558–565.

[15] LAMPORT, L. The part-time parliament. ACM Transac- [3] CAMARGOS, L. J., SCHMIDT, R. M., AND PEDONE, F.

tions on Computer Systems 16, 2 (May 1998), 133–169.

Multicoordinated Paxos. In Proc. PODC’07, ACM Sym- posium on Principles of Distributed Computing (2007), [16] LAMPORT, L. Paxos made simple. ACM SIGACT News ACM, pp. 316–317.

32, 4 (Dec. 2001), 18–25.

[4] CHANDRA, T. D., GRIESEMER, R., AND REDSTONE, J.

[17] LAMPORT, L. Specifying Systems, The TLA+ Language In Proc.

Paxos made live: an engineering perspective.

and Tools for Hardware and Software Engineers. Addison- PODC’07, ACM Symposium on Principles of Distributed Wesley, 2002.

Computing(2007), ACM, pp. 398–407.

[18] LAMPORT, L. Generalized consensus and Paxos. Tech.

[5] CHANG, F., DEAN, J., GHEMAWAT, S., HSIEH, W. C., Rep. MSR-TR-2005-33, Microsoft Research, 2005.

WALLACH, D. A., BURROWS, M., CHANDRA, T., [19] LAMPORT, L. Fast paxos. Distributed Computing 19, 2 FIKES, A., AND GRUBER, R. E. Bigtable: a distributed (2006), 79–103.

In Proc. OSDI’06, storage system for structured data.

USENIX Symposium on Operating Systems Design and [20] LAMPSON, B. W. How to build a highly available system Implementation(2006), USENIX, pp. 205–218.

using consensus. InDistributed Algorithms, O. Baboaglu and K. Marzullo, Eds. Springer-Verlag, 1996, pp. 1–17.

[6] CORBETT, J. C., DEAN, J., EPSTEIN, M., FIKES, A., FROST, C., FURMAN, J. J., GHEMAWAT, S., GUBAREV, In Proc.

[21] LAMPSON, B. W.

The ABCD’s of Paxos.

A., HEISER, C., HOCHSCHILD, P., HSIEH, W., KAN- PODC’01, ACM Symposium on Principles of Distributed THAK, S., KOGAN, E., LI, H., LLOYD, A., MELNIK, Computing(2001), ACM, pp. 13–13.

S., MWAURA, D., NAGLE, D., QUINLAN, S., RAO, R., [22] LISKOV, B., AND COWLING, J.

Viewstamped replica- ROLIG, L., SAITO, Y., SZYMANIAK, M., TAYLOR, C., tion revisited. Tech. Rep. MIT-CSAIL-TR-2012-021, MIT, WANG, R., AND WOODFORD, D.

Spanner: Google’s July 2012.

globally-distributed database. InProc. OSDI’12, USENIX http://github.com/ Conference on Operating Systems Design and Implemen- [23] LogCabin source code.

logcabin/logcabin.

tation(2012), USENIX, pp. 251–264.

17

<!-- Page 18 -->

http://ramcloud.stanford.edu/˜ongaro/ [24] LORCH, J. R., ADYA, A., BOLOSKY, W. J., CHAIKEN, thesis.pdf.

R., DOUCEUR, J. R., AND HOWELL, J.

The SMART way to migrate replicated stateful services. In Proc. Eu- [32] ONGARO, D., AND OUSTERHOUT, J.

In search of an roSys’06, ACM SIGOPS/EuroSys European Conference on In Proc ATC’14, understandable consensus algorithm.

Computer Systems(2006), ACM, pp. 103–115.

USENIX Annual Technical Conference(2014), USENIX.

[25] MAO, Y., JUNQUEIRA, F. P., AND MARZULLO, K.

[33] OUSTERHOUT, J., AGRAWAL, P., ERICKSON, D., Mencius: building efﬁcient replicated state machines for KOZYRAKIS, C., LEVERICH, J., MAZI`ERES, D., MI- In Proc. OSDI’08, USENIX Conference on WANs.

TRA, S., NARAYANAN, A., ONGARO, D., PARULKAR, Operating Systems Design and Implementation (2008), G., ROSENBLUM, M., RUMBLE, S. M., STRATMANN, USENIX, pp. 369–384.

E., AND STUTSMAN, R. The case for RAMCloud. Com- [26] MAZI`ERES, D.

http:

Paxos made practical.

munications of the ACM 54(July 2011), 121–130.

//www.scs.stanford.edu/˜dm/home/ [34] Raft consensus algorithm website.

papers/paxos.pdf, Jan. 2007.

http://raftconsensus.github.io.

[27] MORARU, I., ANDERSEN, D. G., AND KAMINSKY, M.

There is more consensus in egalitarian parliaments.

In [35] REED, B. Personal communications, May 17, 2013.

Proc. SOSP’13, ACM Symposium on Operating System [36] ROSENBLUM, M., ANDOUSTERHOUT, J. K. The design Principles(2013), ACM.

and implementation of a log-structured ﬁle system. ACM http://ramcloud.stanford.

[28] Raft user study.

Trans. Comput. Syst. 10(February 1992), 26–52.

edu/˜ongaro/userstudy/.

[37] SCHNEIDER, F. B. Implementing fault-tolerant services [29] OKI, B. M., AND LISKOV, B. H.

Viewstamped using the state machine approach: a tutorial. ACM Com- replication: A new primary copy method to support puting Surveys 22, 4 (Dec. 1990), 299–319.

highly-available distributed systems. In Proc. PODC’88, ACM Symposium on Principles of Distributed Computing [38] SHVACHKO, K., KUANG, H., RADIA, S., AND (1988), ACM, pp. 8–17.

CHANSLER, R.

The Hadoop distributed ﬁle system.

In Proc. MSST’10, Symposium on Mass Storage Sys- [30] O’NEIL, P., CHENG, E., GAWLICK, D., ANDONEIL, E.

tems and Technologies (2010), IEEE Computer Society, The log-structured merge-tree (LSM-tree). Acta Informat- pp. 1–10.

ica 33, 4 (1996), 351–385.

[31] ONGARO, D. Consensus: Bridging Theory and Practice.

[39] VAN RENESSE, R.

Paxos made moderately complex.

Tech. rep., Cornell University, 2012.

PhD thesis, Stanford University, 2014 (work in progress).

18
