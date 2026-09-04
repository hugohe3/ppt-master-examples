<!--
  Source: https://developer.mozilla.org/en-US/docs/Web/API/WebGPU_API
  Crawled: 2026-09-04T04:14:29.225857
-->

# WebGPU API - Web APIs | MDN

> The WebGPU API enables web developers to use the underlying system's GPU (Graphics Processing Unit) to carry out high-performance computations and draw complex images that can be rendered in the browser.

# WebGPU API

 Limited availability 

This feature is not Baseline because it does not work in some of the most widely-used browsers.

Want more browser support for this feature? [Tell us why.](https://github.com/web-platform-dx/developer-signals/issues/202)

- [ See full compatibility ](#browser_compatibility)
- [ Learn more ](/en-US/docs/Glossary/Baseline/Compatibility)

**Secure context:** This feature is available only in [secure contexts](/en-US/docs/Web/Security/Defenses/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The **WebGPU API** enables web developers to use the underlying system's GPU (Graphics Processing Unit) to carry out high-performance computations and draw complex images that can be rendered in the browser.

WebGPU is the successor to [WebGL](/en-US/docs/Web/API/WebGL_API), providing better compatibility with modern GPUs, support for general-purpose GPU computations, faster operations, and access to more advanced GPU features.

lit-part pV7fc3t43jg=lit-node 0

## lit-node 1[Concepts and usage](#concepts_and_usage)

/lit-part

It is fair to say that [WebGL](/en-US/docs/Web/API/WebGL_API) revolutionized the web in terms of graphical capabilities after it first appeared around 2011. WebGL is a JavaScript port of the [OpenGL ES 2.0](https://registry.khronos.org/OpenGL-Refpages/es2.0/) graphics library, allowing web pages to pass rendering computations directly to the device's GPU to be processed at very high speeds, and render the result inside a [`<canvas>`](/en-US/docs/Web/HTML/Reference/Elements/canvas) element.

WebGL and the [GLSL](https://wikis.khronos.org/opengl/Core_Language_(GLSL)) language used to write WebGL shader code are complex, so several WebGL libraries have been created to make WebGL apps easier to write: Popular examples include [Three.js](https://threejs.org/), [Babylon.js](https://www.babylonjs.com/), and [PlayCanvas](https://playcanvas.com/). Developers have used these tools to build immersive web-based 3D games, music videos, training and modeling tools, VR and AR experiences, and more.

However, WebGL has some fundamental issues that needed addressing:

- Since WebGL's release, a new generation of native GPU APIs have appeared — the most popular being [Microsoft's Direct3D 12](https://learn.microsoft.com/en-us/windows/win32/direct3d12/direct3d-12-graphics), [Apple's Metal](https://developer.apple.com/metal/), and [The Khronos Group's Vulkan](https://www.vulkan.org/) — which provide a multitude of new features. There are no more updates planned to OpenGL (and therefore WebGL), so it won't get any of these new features. WebGPU on the other hand will have new features added to it going forwards.
- WebGL is based wholly around the use case of drawing graphics and rendering them to a canvas. It does not handle general-purpose GPU (GPGPU) computations very well. GPGPU computations are becoming more and more important for many different use cases, for example those based on machine learning models.
- 3D graphics apps are becoming increasingly demanding, both in terms of the number of objects to be rendered simultaneously, and usage of new rendering features.

WebGPU addresses these issues, providing an updated general-purpose architecture compatible with modern GPU APIs, which feels more "webby". It supports graphic rendering, but also has first-class support for GPGPU computations. Rendering of individual objects is significantly cheaper on the CPU side, and it supports modern GPU rendering features such as compute-based particles and post-processing filters like color effects, sharpening, and depth-of-field simulation. In addition, it can handle expensive computations such as culling and skinned model transformation directly on the GPU.

lit-part SiuJ1nCyg4g=lit-node 0

## lit-node 1[General model](#general_model)

/lit-part

There are several layers of abstraction between a device GPU and a web browser running the WebGPU API. It is useful to understand these as you begin to learn WebGPU:

![A basic stack diagram showing the position of the different elements of a WebGPU architecture on a device](WebGPU_API_Web_APIs_MDN_files/basicwebgpustack.png)

- 

Physical devices have GPUs. Most devices only have one GPU, but some have more than one. Different GPU types are available:

- Integrated GPUs, which live on the same board as the CPU and share its memory.
- Discrete GPUs, which live on their own board, separate from the CPU.
- Software "GPUs", implemented on the CPU.

**Note:** The above diagram assumes a device with only one GPU.

- 

A native GPU API, which is part of the OS (for example, Metal on macOS), is a programming interface allowing native applications to use the capabilities of the GPU. API instructions are sent to the GPU (and responses received) via a driver. It is possible for a system to have multiple native OS APIs and drivers available to communicate with the GPU, although the above diagram assumes a device with only one native API/driver.

- 

A browser's WebGPU implementation handles communicating with the GPU via a native GPU API driver. A WebGPU adapter effectively represents a physical GPU and driver available on the underlying system, in your code.

- 

A logical device is an abstraction via which a single web app can access GPU capabilities in a compartmentalized way. Logical devices are required to provide multiplexing capabilities. A physical device's GPU is used by many applications and processes concurrently, including potentially many web apps. Each web app needs to be able to access WebGPU in isolation for security and logic reasons.

lit-part DA04xJJnXdE=lit-node 0

## lit-node 1[Accessing a device](#accessing_a_device)

/lit-part

A logical device — represented by a [`GPUDevice`](/en-US/docs/Web/API/GPUDevice) object instance — is the basis from which a web app accesses all WebGPU functionality. Accessing a device is done as follows:

- The [`Navigator.gpu`](/en-US/docs/Web/API/Navigator/gpu) property (or [`WorkerNavigator.gpu`](/en-US/docs/Web/API/WorkerNavigator/gpu) if you are using WebGPU functionality from inside a worker) returns the [`GPU`](/en-US/docs/Web/API/GPU) object for the current context.
- You access an adapter via the [`GPU.requestAdapter()`](/en-US/docs/Web/API/GPU/requestAdapter) method. This method accepts an optional settings object allowing you to request, for example, a [compatibility mode](#webgpu_compatibility_mode), high-performance, or low-energy adapter. If this is not included, the device will provide access to the default adapter, which is good enough for most purposes.
- A device can be requested via [`GPUAdapter.requestDevice()`](/en-US/docs/Web/API/GPUAdapter/requestDevice). This method also accepts an options object (referred to as a descriptor), which can be used to specify the exact features and limits you want the logical device to have. If this is not included, the supplied device will have a reasonable general-purpose spec that is good enough for most purposes.

Putting this together with some feature detection checks, the above process could be achieved as follows:

js

```
async function init() {
  if (!navigator.gpu) {
    throw Error("WebGPU not supported.");
  }

  let adapter;
  try {
    adapter = await navigator.gpu.requestAdapter();
  } catch (error) {
    console.error(error);
  }
  if (!adapter) {
    throw Error("Couldn't request WebGPU adapter.");
  }

  const device = await adapter.requestDevice();

  // …
}

```

lit-part 5ihov1rUn4o=lit-node 0

### lit-node 1[WebGPU compatibility mode](#webgpu_compatibility_mode)

/lit-part

By default, a `GPUAdapter` supports all core WebGPU features and limits, which allows applications to support devices with modern platform graphics APIs. This is referred to as "core" WebGPU.

It is possible to opt WebGPU into "compatibility mode", which specifies that the `GPUAdapter` will support a restricted subset of the WebGPU API capable of running in older graphics APIs such as OpenGL ES 3.1 and Direct3D 11. This is done by specifying a [`featureLevel`](/en-US/docs/Web/API/GPU/requestAdapter#featurelevel) value of `compatibility` in your [`GPU.requestAdapter()`](/en-US/docs/Web/API/GPU/requestAdapter) call:

js

```
const adapter = await navigator.gpu.requestAdapter({
  featureLevel: "compatibility",
});

```

The exact restrictions of compatibility mode are detailed at [WebGPU Compatibility Mode](https://webgpufundamentals.org/webgpu/lessons/webgpu-compatibility-mode.html). Restricted applications are still valid WebGPU core applications due to supporting a subset of core WebGPU, and will therefore run on all browsers that support core WebGPU, even if they don't explicitly support compatibility mode.

A `GPUAdapter` or `GPUDevice` that supports core WebGPU will have the `core-features-and-limits` feature available (see [`GPUSupportedFeatures`](/en-US/docs/Web/API/GPUSupportedFeatures)). To test whether a WebGPU app is in core or compatibility mode, check whether the `core-features-and-limits` feature is supported, for example:

js

```
const isCore = device.features.has("core-features-and-limits");

```

See also [Using compatibility mode only if necessary](/en-US/docs/Web/API/GPU/requestAdapter#using_compatibility_mode_only_if_necessary).

lit-part vFYbYSMGOZA=lit-node 0

## lit-node 1[Pipelines and shaders: WebGPU app structure](#pipelines_and_shaders_webgpu_app_structure)

/lit-part

A pipeline is a logical structure containing programmable stages that are completed to get your program's work done. WebGPU is currently able to handle two types of pipeline:

- 

A render pipeline renders graphics, typically into a [`<canvas>`](/en-US/docs/Web/HTML/Reference/Elements/canvas) element, but it could also render graphics offscreen. It has two main stages:

- 

A vertex stage, in which a vertex shader takes positioning data fed into the GPU and uses it to position a series of vertices in 3D space by applying specified effects like rotation, translation, or perspective. The vertices are then assembled into primitives such as triangles (the basic building block of rendered graphics) and rasterized by the GPU to figure out what pixels each one should cover on the drawing canvas.

- 

A fragment stage, in which a fragment shader computes the color for each pixel covered by the primitives produced by the vertex shader. These computations frequently use inputs such as images (in the form of textures) that provide surface details and the position and color of virtual lights.

- 

A compute pipeline is for general computation. A compute pipeline contains a single compute stage in which a compute shader takes general data, processes it in parallel across a specified number of workgroups, then returns the result in one or more buffers. The buffers can contain any kind of data.

The shaders mentioned above are sets of instructions processed by the GPU. WebGPU shaders are written in a low-level Rust-like language called [WebGPU Shading Language](https://gpuweb.github.io/gpuweb/wgsl/) (WGSL).

There are several different ways in which you could architect a WebGPU app, but the process will likely contain the following steps:

- [Create shader modules](#create_shader_modules): Write your shader code in WGSL and package it into one or more shader modules.
- [Get and configure the canvas context](#get_and_configure_the_canvas_context): Get the `webgpu` context of a `<canvas>` element and configure it to receive information on what graphics to render from your GPU logical device. This step is not necessary if your app has no graphical output, such as one that only uses compute pipelines.
- [Create resources containing your data](#create_a_buffer_and_write_our_triangle_data_into_it): The data that you want processed by your pipelines needs to be stored in GPU buffers or textures to be accessed by your app.
- [Create pipelines](#define_and_create_the_render_pipeline): Define pipeline descriptors that describe the desired pipelines in detail, including the required data structure, bindings, shaders, and resource layouts, then create pipelines from them. Our basic demos only contain a single pipeline, but non-trivial apps will usually contain multiple pipelines for different purposes.
- [Run a compute/rendering pass](#running_a_rendering_pass): This involves a number of substeps: 
- Create a command encoder that can encode a set of commands to be passed to the GPU to execute.
- Create a pass encoder object on which compute/render commands are issued.
- Run commands to specify which pipelines to use, what buffer(s) to get the required data from, how many drawing operations to run (in the case of render pipelines), etc.
- Finalize the command list and encapsulate it in a command buffer.
- Submit the command buffer to the GPU via the logical device's command queue.

In the sections below, we will examine a basic render pipeline demo, to allow you to explore what it requires. Later on, we'll also examine a [basic compute pipeline](#basic_compute_pipeline) example, looking at how it differs from the render pipeline.

lit-part 05AmdeKKzxc=lit-node 0

## lit-node 1[Basic render pipeline](#basic_render_pipeline)

/lit-part

In our [basic render demo](https://mdn.github.io/dom-examples/webgpu-render-demo/) we give a `<canvas>` element a solid blue background and draw a triangle onto it.

lit-part 4lGGogUyUpI=lit-node 0

### lit-node 1[Create shader modules](#create_shader_modules)

/lit-part

We are using the following shader code. The vertex shader stage (`@vertex` block) accepts a chunk of data containing a position and a color, positions the vertex according to the given position, interpolates the color, then passes the data along to the fragment shader stage. The fragment shader stage (`@fragment` block) accepts the data from the vertex shader stage and colors the vertex according to the given color.

js

```
const shaders = `
struct VertexOut {
  @builtin(position) position : vec4f,
  @location(0) color : vec4f
}

@vertex
fn vertex_main(@location(0) position: vec4f,
               @location(1) color: vec4f) -> VertexOut
{
  var output : VertexOut;
  output.position = position;
  output.color = color;
  return output;
}

@fragment
fn fragment_main(fragData: VertexOut) -> @location(0) vec4f
{
  return fragData.color;
}
`;

```

**Note:** In our demos we are storing our shader code inside a template literal, but you can store it anywhere from which it can easily be retrieved as text to be fed into your WebGPU program. For example, another common practice is to store shaders inside a [`<script>`](/en-US/docs/Web/HTML/Reference/Elements/script) element and retrieve the contents using [`Node.textContent`](/en-US/docs/Web/API/Node/textContent). The correct mime type to use for WGSL is `text/wgsl`.

To make your shader code available to WebGPU, you have to put it inside a [`GPUShaderModule`](/en-US/docs/Web/API/GPUShaderModule) via a [`GPUDevice.createShaderModule()`](/en-US/docs/Web/API/GPUDevice/createShaderModule) call, passing your shader code as a property inside a descriptor object. For example:

js

```
const shaderModule = device.createShaderModule({
  code: shaders,
});

```

lit-part nr+CJMbbLqs=lit-node 0

### lit-node 1[Get and configure the canvas context](#get_and_configure_the_canvas_context)

/lit-part

In a render pipeline, we need to specify somewhere to render the graphics to. In this case we are getting a reference to an onscreen `<canvas>` element then calling [`HTMLCanvasElement.getContext()`](/en-US/docs/Web/API/HTMLCanvasElement/getContext) with a parameter of `webgpu` to return its GPU context (a [`GPUCanvasContext`](/en-US/docs/Web/API/GPUCanvasContext) instance).

From there, we configure the context with a call to [`GPUCanvasContext.configure()`](/en-US/docs/Web/API/GPUCanvasContext/configure), passing it an options object containing the [`GPUDevice`](/en-US/docs/Web/API/GPUDevice) that the rendering information will come from, the format the textures will have, and the alpha mode to use when rendering semi-transparent textures.

js

```
const canvas = document.querySelector("#gpuCanvas");
const context = canvas.getContext("webgpu");

context.configure({
  device,
  format: navigator.gpu.getPreferredCanvasFormat(),
  alphaMode: "premultiplied",
});

```

**Note:** The best practice for determining the texture format is to use the [`GPU.getPreferredCanvasFormat()`](/en-US/docs/Web/API/GPU/getPreferredCanvasFormat) method; this selects the most efficient format (either `bgra8unorm` or `rgba8unorm`) for the user's device.

lit-part 3icWzvnjYNs=lit-node 0

### lit-node 1[Create a buffer and write our triangle data into it](#create_a_buffer_and_write_our_triangle_data_into_it)

/lit-part

Next we will provide our WebGPU program with our data, in a form it can use. Our data is initially provided in a [`Float32Array`](/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array), which contains 8 data points for each triangle vertex — X, Y, Z, W for position, and R, G, B, A for color.

js

```
const vertices = new Float32Array([
  0.0, 0.6, 0, 1, 1, 0, 0, 1, -0.5, -0.6, 0, 1, 0, 1, 0, 1, 0.5, -0.6, 0, 1, 0,
  0, 1, 1,
]);

```

However, we've got an issue here. We need to get our data into a [`GPUBuffer`](/en-US/docs/Web/API/GPUBuffer). Behind the scenes, this type of buffer is stored in memory very tightly integrated with the GPU's cores to allow for the desired high performance processing. As a side effect, this memory can't be accessed by processes running on the host system, like the browser.

The [`GPUBuffer`](/en-US/docs/Web/API/GPUBuffer) is created via a call to [`GPUDevice.createBuffer()`](/en-US/docs/Web/API/GPUDevice/createBuffer). We give it a size equal to the length of the `vertices` array so it can contain all the data, and `VERTEX` and `COPY_DST` usage flags to indicate that the buffer will be used as a vertex buffer and the destination of copy operations.

js

```
const vertexBuffer = device.createBuffer({
  size: vertices.byteLength, // make it big enough to store vertices in
  usage: GPUBufferUsage.VERTEX | GPUBufferUsage.COPY_DST,
});

```

We could handle getting our data into the `GPUBuffer` using a mapping operation, like we use in the [compute pipeline example](#basic_compute_pipeline) to read data from the GPU back to JavaScript. However, in this case we are going to use the handy [`GPUQueue.writeBuffer()`](/en-US/docs/Web/API/GPUQueue/writeBuffer) convenience method, which takes as its parameters the buffer to write to, the data source to write from, an offset value for each, and the size of data to write (we've specified the whole length of the array). The browser then works out the most efficient way to handle writing the data.

js

```
device.queue.writeBuffer(vertexBuffer, 0, vertices, 0, vertices.length);

```

lit-part JLPji3yxj/Y=lit-node 0

### lit-node 1[Define and create the render pipeline](#define_and_create_the_render_pipeline)

/lit-part

Now we've got our data into a buffer, the next part of the setup is to actually create our pipeline, ready to be used for rendering.

First of all, we create an object that describes the required layout of our vertex data. This perfectly describes what we saw earlier on in our `vertices` array and vertex shader stage — each vertex has position and color data. Both are formatted in `float32x4` format (which maps to the WGSL `vec4<f32>` type), and the color data starts at an offset of 16 bytes into each vertex. `arrayStride` specifies the stride, meaning the number of bytes making up each vertex, and `stepMode` specifies that the data should be fetched per-vertex.

js

```
const vertexBuffers = [
  {
    attributes: [
      {
        shaderLocation: 0, // position
        offset: 0,
        format: "float32x4",
      },
      {
        shaderLocation: 1, // color
        offset: 16,
        format: "float32x4",
      },
    ],
    arrayStride: 32,
    stepMode: "vertex",
  },
];

```

Next, we create a descriptor object that specifies the configuration of our render pipeline stages. For both the shader stages, we specify the [`GPUShaderModule`](/en-US/docs/Web/API/GPUShaderModule) that the relevant code can be found in (`shaderModule`), and the name of the function that acts as the entry point for each stage.

In addition, in the case of the vertex shader stage we provide our `vertexBuffers` object to provide the expected state of our vertex data. And in the case of our fragment shader stage, we provide an array of color target states that indicate the specified rendering format (this matches the format specified in our canvas context config earlier).

We also specify a `primitive` object, which in this case just states the type of primitive we will be drawing, and a `layout` of `auto`. The `layout` property defines the layout (structure, purpose, and type) of all the GPU resources (buffers, textures, etc.) used during the execution of the pipeline. In more complex apps, this would take the form of a [`GPUPipelineLayout`](/en-US/docs/Web/API/GPUPipelineLayout) object, created using [`GPUDevice.createPipelineLayout()`](/en-US/docs/Web/API/GPUDevice/createPipelineLayout) (you can see an example in our [Basic compute pipeline](#basic_compute_pipeline)), which allows the GPU to figure out how to run the pipeline most efficiently ahead of time. However, we are specifying the `auto` value, which will cause the pipeline to generate an implicit bind group layout based on any bindings defined in the shader code.

js

```
const pipelineDescriptor = {
  vertex: {
    module: shaderModule,
    entryPoint: "vertex_main",
    buffers: vertexBuffers,
  },
  fragment: {
    module: shaderModule,
    entryPoint: "fragment_main",
    targets: [
      {
        format: navigator.gpu.getPreferredCanvasFormat(),
      },
    ],
  },
  primitive: {
    topology: "triangle-list",
  },
  layout: "auto",
};

```

Finally, we can create a [`GPURenderPipeline`](/en-US/docs/Web/API/GPURenderPipeline) based on our `pipelineDescriptor` object, by passing it in as a parameter to a [`GPUDevice.createRenderPipeline()`](/en-US/docs/Web/API/GPUDevice/createRenderPipeline) method call.

js

```
const renderPipeline = device.createRenderPipeline(pipelineDescriptor);

```

lit-part RcIs3Tsa+MA=lit-node 0

### lit-node 1[Running a rendering pass](#running_a_rendering_pass)

/lit-part

Now that all the setup is done, we can actually run a rendering pass and draw something onto our `<canvas>`. To encode any commands to be later issued to the GPU, you need to create a [`GPUCommandEncoder`](/en-US/docs/Web/API/GPUCommandEncoder) instance, which is done using a [`GPUDevice.createCommandEncoder()`](/en-US/docs/Web/API/GPUDevice/createCommandEncoder) call.

js

```
const commandEncoder = device.createCommandEncoder();

```

Next up we start the rendering pass running by creating a [`GPURenderPassEncoder`](/en-US/docs/Web/API/GPURenderPassEncoder) instance with a [`GPUCommandEncoder.beginRenderPass()`](/en-US/docs/Web/API/GPUCommandEncoder/beginRenderPass) call. This method takes a descriptor object as a parameter, the only mandatory property of which is a `colorAttachments` array. In this case, we specify:

- A texture view to render into; we create a new view from the `<canvas>` via [`context.getCurrentTexture().createView()`](/en-US/docs/Web/API/GPUTexture/createView).
- That the view should be "cleared" to a specified color once loaded and before any drawing takes place. This is what causes the blue background behind the triangle.
- That the value of the current rendering pass should be stored for this color attachment.js

```
const clearColor = { r: 0.0, g: 0.5, b: 1.0, a: 1.0 };

const renderPassDescriptor = {
  colorAttachments: [
    {
      clearValue: clearColor,
      loadOp: "clear",
      storeOp: "store",
      view: context.getCurrentTexture().createView(),
    },
  ],
};

const passEncoder = commandEncoder.beginRenderPass(renderPassDescriptor);

```

Now we can invoke methods of the rendering pass encoder to draw our triangle:

- [`GPURenderPassEncoder.setPipeline()`](/en-US/docs/Web/API/GPURenderPassEncoder/setPipeline) is called with our `renderPipeline` object as a parameter to specify the pipeline to use for the rendering pass.
- [`GPURenderPassEncoder.setVertexBuffer()`](/en-US/docs/Web/API/GPURenderPassEncoder/setVertexBuffer) is called with our `vertexBuffer` object as a parameter to act as the data source to pass to the pipeline to render. The first parameter is the slot to set the vertex buffer for, and is a reference to the index of the element in the `vertexBuffers` array which describes this buffer's layout.
- [`GPURenderPassEncoder.draw()`](/en-US/docs/Web/API/GPURenderPassEncoder/draw) sets the drawing in motion. There is data for three vertices inside our `vertexBuffer`, so we set a vertex count value of `3` to draw them all.js

```
passEncoder.setPipeline(renderPipeline);
passEncoder.setVertexBuffer(0, vertexBuffer);
passEncoder.draw(3);

```

To finish encoding the sequence of commands and issue them to the GPU, three more steps are needed.

- We invoke the [`GPURenderPassEncoder.end()`](/en-US/docs/Web/API/GPURenderPassEncoder/end) method to signal the end of the render pass command list.
- We invoke the [`GPUCommandEncoder.finish()`](/en-US/docs/Web/API/GPUCommandEncoder/finish) method to complete recording of the issued command sequence and encapsulate it into a [`GPUCommandBuffer`](/en-US/docs/Web/API/GPUCommandBuffer) object instance.
- We submit the [`GPUCommandBuffer`](/en-US/docs/Web/API/GPUCommandBuffer) to the device's command queue (represented by a [`GPUQueue`](/en-US/docs/Web/API/GPUQueue) instance) to be sent to the GPU. The device's queue is available via the [`GPUDevice.queue`](/en-US/docs/Web/API/GPUDevice/queue) property, and an array of [`GPUCommandBuffer`](/en-US/docs/Web/API/GPUCommandBuffer) instances can be added to the queue via a [`GPUQueue.submit()`](/en-US/docs/Web/API/GPUQueue/submit) call.

These three steps can be achieved via the following two lines:

js

```
passEncoder.end();

device.queue.submit([commandEncoder.finish()]);

```

lit-part rSBaBcOvJcw=lit-node 0

## lit-node 1[Basic compute pipeline](#basic_compute_pipeline)

/lit-part

In our [basic compute demo](https://mdn.github.io/dom-examples/webgpu-compute-demo/), we get the GPU to calculate some values, store them in an output buffer, copy the data across to a staging buffer, then map that staging buffer so that the data can be read out to JavaScript and logged to the console.

The app follows a similar structure to the basic rendering demo. We create a [`GPUDevice`](/en-US/docs/Web/API/GPUDevice) reference in the same way as before, and encapsulate our shader code into a [`GPUShaderModule`](/en-US/docs/Web/API/GPUShaderModule) via a [`GPUDevice.createShaderModule()`](/en-US/docs/Web/API/GPUDevice/createShaderModule) call. The difference here is that our shader code only has one shader stage, a `@compute` stage:

js

```
// Define global buffer size
const NUM_ELEMENTS = 1000;
const BUFFER_SIZE = NUM_ELEMENTS * 4; // Buffer size, in bytes

const shader = `
@group(0) @binding(0)
var<storage, read_write> output: array<f32>;

@compute @workgroup_size(64)
fn main(
  @builtin(global_invocation_id)
  global_id : vec3u,

  @builtin(local_invocation_id)
  local_id : vec3u,
) {
  // Avoid accessing the buffer out of bounds
  if (global_id.x >= ${NUM_ELEMENTS}) {
    return;
  }

  output[global_id.x] =
    f32(global_id.x) * 1000. + f32(local_id.x);
}
`;

```

lit-part 2/1FQqaf/D8=lit-node 0

### lit-node 1[Create buffers to handle our data](#create_buffers_to_handle_our_data)

/lit-part

In this example we create two [`GPUBuffer`](/en-US/docs/Web/API/GPUBuffer) instances to handle our data, an `output` buffer to write the GPU calculation results to at high speed, and a `stagingBuffer` that we'll copy the `output` contents to, which can be mapped to allow JavaScript to access the values.

- `output` is specified as a storage buffer that will be the source of a copy operation.
- `stagingBuffer` is specified as a buffer that can be mapped for reading by JavaScript, and will be the destination of a copy operation.js

```
const output = device.createBuffer({
  size: BUFFER_SIZE,
  usage: GPUBufferUsage.STORAGE | GPUBufferUsage.COPY_SRC,
});

const stagingBuffer = device.createBuffer({
  size: BUFFER_SIZE,
  usage: GPUBufferUsage.MAP_READ | GPUBufferUsage.COPY_DST,
});

```

lit-part pR8kT2frBmg=lit-node 0

### lit-node 1[Create a bind group layout](#create_a_bind_group_layout)

/lit-part

When the pipeline is created, we specify a bind group to use for the pipeline. This involves first creating a [`GPUBindGroupLayout`](/en-US/docs/Web/API/GPUBindGroupLayout) (via a call to [`GPUDevice.createBindGroupLayout()`](/en-US/docs/Web/API/GPUDevice/createBindGroupLayout)) that defines the structure and purpose of GPU resources such as buffers that will be used in this pipeline. This layout is used as a template for bind groups to adhere to. In this case we give the pipeline access to a single memory buffer, tied to binding slot 0 (this matches the relevant binding number in our shader code — `@binding(0)`), usable in the compute stage of the pipeline, and with the buffer's purpose defined as `storage`.

js

```
const bindGroupLayout = device.createBindGroupLayout({
  entries: [
    {
      binding: 0,
      visibility: GPUShaderStage.COMPUTE,
      buffer: {
        type: "storage",
      },
    },
  ],
});

```

Next we create a [`GPUBindGroup`](/en-US/docs/Web/API/GPUBindGroup) by calling [`GPUDevice.createBindGroup()`](/en-US/docs/Web/API/GPUDevice/createBindGroup). We pass this method call a descriptor object that specifies the bind group layout to base this bind group on, and the details of the variable to bind to the slot defined in the layout. In this case, we are declaring binding 0, and specifying that the `output` buffer we defined earlier should be bound to it.

js

```
const bindGroup = device.createBindGroup({
  layout: bindGroupLayout,
  entries: [
    {
      binding: 0,
      resource: {
        buffer: output,
      },
    },
  ],
});

```

**Note:** You could retrieve an implicit layout to use when creating a bind group by calling the [`GPUComputePipeline.getBindGroupLayout()`](/en-US/docs/Web/API/GPUComputePipeline/getBindGroupLayout) method. There is also a version available for render pipelines: see [`GPURenderPipeline.getBindGroupLayout()`](/en-US/docs/Web/API/GPURenderPipeline/getBindGroupLayout).

lit-part YVyglvC4DbE=lit-node 0

### lit-node 1[Create a compute pipeline](#create_a_compute_pipeline)

/lit-part

With the above all in place, we can now create a compute pipeline by calling [`GPUDevice.createComputePipeline()`](/en-US/docs/Web/API/GPUDevice/createComputePipeline), passing it a pipeline descriptor object. This works in a similar way to creating a render pipeline. We describe the compute shader, specifying what module to find the code in and what the entry point is. We also specify a `layout` for the pipeline, in this case creating a layout based on the `bindGroupLayout` we defined earlier via a [`GPUDevice.createPipelineLayout()`](/en-US/docs/Web/API/GPUDevice/createPipelineLayout) call.

js

```
const computePipeline = device.createComputePipeline({
  layout: device.createPipelineLayout({
    bindGroupLayouts: [bindGroupLayout],
  }),
  compute: {
    module: shaderModule,
    entryPoint: "main",
  },
});

```

One difference here from the render pipeline layout is that we are not specifying a primitive type, as we are not drawing anything.

lit-part 7OMC+42vOKs=lit-node 0

### lit-node 1[Running a compute pass](#running_a_compute_pass)

/lit-part

Running a compute pass is similar in structure to running a rendering pass, with some different commands. For a start, the pass encoder is created using [`GPUCommandEncoder.beginComputePass()`](/en-US/docs/Web/API/GPUCommandEncoder/beginComputePass).

When issuing the commands, we specify the pipeline to use in the same way as before, using [`GPUComputePassEncoder.setPipeline()`](/en-US/docs/Web/API/GPUComputePassEncoder/setPipeline). We then however use [`GPUComputePassEncoder.setBindGroup()`](/en-US/docs/Web/API/GPUComputePassEncoder/setBindGroup) to specify that we want to use our `bindGroup` to specify the data to use in the calculation, and [`GPUComputePassEncoder.dispatchWorkgroups()`](/en-US/docs/Web/API/GPUComputePassEncoder/dispatchWorkgroups) to specify the number of GPU workgroups to use to run the calculations.

We then signal the end of the render pass command list using [`GPURenderPassEncoder.end()`](/en-US/docs/Web/API/GPURenderPassEncoder/end).

js

```
passEncoder.setPipeline(computePipeline);
passEncoder.setBindGroup(0, bindGroup);
passEncoder.dispatchWorkgroups(Math.ceil(NUM_ELEMENTS / 64));

passEncoder.end();

```

lit-part Uxl1AYLEjcg=lit-node 0

### lit-node 1[Reading the results back to JavaScript](#reading_the_results_back_to_javascript)

/lit-part

Before submitting the encoded commands to the GPU for execution using [`GPUQueue.submit()`](/en-US/docs/Web/API/GPUQueue/submit), we copy the contents of the `output` buffer to the `stagingBuffer` buffer using [`GPUCommandEncoder.copyBufferToBuffer()`](/en-US/docs/Web/API/GPUCommandEncoder/copyBufferToBuffer).

js

```
// Copy output buffer to staging buffer
commandEncoder.copyBufferToBuffer(
  output,
  0, // Source offset
  stagingBuffer,
  0, // Destination offset
  BUFFER_SIZE, // Length, in bytes
);

// End frame by passing array of command buffers to command queue for execution
device.queue.submit([commandEncoder.finish()]);

```

Once the output data is available in the `stagingBuffer`, we use the [`GPUBuffer.mapAsync()`](/en-US/docs/Web/API/GPUBuffer/mapAsync) method to map the data to intermediate memory, grab a reference to the mapped range using [`GPUBuffer.getMappedRange()`](/en-US/docs/Web/API/GPUBuffer/getMappedRange), copy the data into JavaScript, and then log it to the console. We also unmap the `stagingBuffer` once we are finished with it.

js

```
// map staging buffer to read results back to JS
await stagingBuffer.mapAsync(
  GPUMapMode.READ,
  0, // Offset
  BUFFER_SIZE, // Length, in bytes
);

const copyArrayBuffer = stagingBuffer.getMappedRange(0, BUFFER_SIZE);
const data = copyArrayBuffer.slice();
stagingBuffer.unmap();
console.log(new Float32Array(data));

```

lit-part sMk/VgblWVI=lit-node 0

## lit-node 1[GPU error handling](#gpu_error_handling)

/lit-part

WebGPU calls are validated asynchronously in the GPU process. If errors are found, the problem call is marked as invalid on the GPU side. If another call is made that relies on the return value of an invalidated call, that object will also be marked as invalid, and so on. For this reason, errors in WebGPU are referred to as "contagious".

Each [`GPUDevice`](/en-US/docs/Web/API/GPUDevice) instance maintains its own error scope stack. This stack is initially empty, but you can start pushing an error scope to the stack by invoking [`GPUDevice.pushErrorScope()`](/en-US/docs/Web/API/GPUDevice/pushErrorScope) to capture errors of a particular type.

Once you are done capturing errors, you can end capture by invoking [`GPUDevice.popErrorScope()`](/en-US/docs/Web/API/GPUDevice/popErrorScope). This pops the scope from the stack and returns a [`Promise`](/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an object ([`GPUInternalError`](/en-US/docs/Web/API/GPUInternalError), [`GPUOutOfMemoryError`](/en-US/docs/Web/API/GPUOutOfMemoryError), or [`GPUValidationError`](/en-US/docs/Web/API/GPUValidationError)) describing the first error captured in the scope, or `null` if no errors were captured.

We have attempted to provide useful information to help you understand why errors are occurring in your WebGPU code in "Validation" sections where appropriate, which list criteria to meet to avoid errors. See for example the [`GPUDevice.createBindGroup()` Validation section](/en-US/docs/Web/API/GPUDevice/createBindGroup#validation). Some of this information is complex; rather than repeat the spec, we have decided to just list error criteria that are:

- Non-obvious, for example combinations of descriptor properties that produce validation errors. There is no point telling you to make sure you use the correct descriptor object structure. That is both obvious and vague.
- Developer-controlled. Some of the error criteria are purely based on internals and not really relevant to web developers.

You can find more information about WebGPU error handling in the explainer — see [Object validity and destroyed-ness](https://gpuweb.github.io/gpuweb/explainer/#invalid-and-destroyed) and [Errors](https://gpuweb.github.io/gpuweb/explainer/#errors). [WebGPU Error Handling best practices](https://toji.dev/webgpu-best-practices/error-handling) provides useful real-world examples and advice.

**Note:** The historic way of handling errors in WebGL is to provide a [`getError()`](/en-US/docs/Web/API/WebGLRenderingContext/getError) method to return error information. This is problematic in that it returns errors synchronously, which is bad for performance — each call requires a round-trip to the GPU and requires all previously issued operations to be finished. Its state model is also flat, meaning that errors can leak between unrelated code. The creators of WebGPU were determined to improve on this.

lit-part SHV3q51bFcI=lit-node 0

## lit-node 1[Interfaces](#interfaces)

/lit-partlit-part ME2/O1FSF80=lit-node 0

### lit-node 1[Entry point for the API](#entry_point_for_the_api)

/lit-part[`Navigator.gpu`](/en-US/docs/Web/API/Navigator/gpu) / [`WorkerNavigator.gpu`](/en-US/docs/Web/API/WorkerNavigator/gpu)

The entry point for the API — returns the [`GPU`](/en-US/docs/Web/API/GPU) object for the current context.

[`GPU`](/en-US/docs/Web/API/GPU)

The starting point for using WebGPU. It can be used to return a [`GPUAdapter`](/en-US/docs/Web/API/GPUAdapter).

[`GPUAdapter`](/en-US/docs/Web/API/GPUAdapter)

Represents a GPU adapter. From this you can request a [`GPUDevice`](/en-US/docs/Web/API/GPUDevice), adapter info, features, and limits.

[`GPUAdapterInfo`](/en-US/docs/Web/API/GPUAdapterInfo)

Contains identifying information about an adapter.

lit-part xvkE0qHmyYk=lit-node 0

### lit-node 1[Configuring GPUDevices](#configuring_gpudevices)

/lit-part[`GPUDevice`](/en-US/docs/Web/API/GPUDevice)

Represents a logical GPU device. This is the main interface through which the majority of WebGPU functionality is accessed.

[`GPUSupportedFeatures`](/en-US/docs/Web/API/GPUSupportedFeatures)

A [setlike](/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set) object that describes additional functionality supported by a [`GPUAdapter`](/en-US/docs/Web/API/GPUAdapter) or [`GPUDevice`](/en-US/docs/Web/API/GPUDevice).

[`GPUSupportedLimits`](/en-US/docs/Web/API/GPUSupportedLimits)

Describes the limits supported by a [`GPUAdapter`](/en-US/docs/Web/API/GPUAdapter) or [`GPUDevice`](/en-US/docs/Web/API/GPUDevice).

lit-part rqp+GmffNKg=lit-node 0

### lit-node 1[Configuring a rendering `<canvas>`](#configuring_a_rendering_canvas)

/lit-part[`HTMLCanvasElement.getContext()`](/en-US/docs/Web/API/HTMLCanvasElement/getContext) — the `"webgpu"``contextType`

Invoking `getContext()` with the `"webgpu"``contextType` returns a [`GPUCanvasContext`](/en-US/docs/Web/API/GPUCanvasContext) object instance, which can then be configured with [`GPUCanvasContext.configure()`](/en-US/docs/Web/API/GPUCanvasContext/configure).

[`GPUCanvasContext`](/en-US/docs/Web/API/GPUCanvasContext)

Represents the WebGPU rendering context of a [`<canvas>`](/en-US/docs/Web/HTML/Reference/Elements/canvas) element.

lit-part RGtJZaD6c0Y=lit-node 0

### lit-node 1[Representing pipeline resources](#representing_pipeline_resources)

/lit-part[`GPUBuffer`](/en-US/docs/Web/API/GPUBuffer)

Represents a block of memory that can be used to store raw data to use in GPU operations.

[`GPUExternalTexture`](/en-US/docs/Web/API/GPUExternalTexture)

A wrapper object containing an [`HTMLVideoElement`](/en-US/docs/Web/API/HTMLVideoElement) snapshot that can be used as a texture in GPU rendering operations.

[`GPUSampler`](/en-US/docs/Web/API/GPUSampler)

Controls how shaders transform and filter texture resource data.

[`GPUShaderModule`](/en-US/docs/Web/API/GPUShaderModule)

A reference to an internal shader module object, a container for WGSL shader code that can be submitted to the GPU to execution by a pipeline.

[`GPUTexture`](/en-US/docs/Web/API/GPUTexture)

A container used to store 1D, 2D, or 3D arrays of data, such as images, to use in GPU rendering operations.

[`GPUTextureView`](/en-US/docs/Web/API/GPUTextureView)

A view onto some subset of the texture subresources defined by a particular [`GPUTexture`](/en-US/docs/Web/API/GPUTexture).

lit-part +lXIB/Sp3vE=lit-node 0

### lit-node 1[Representing pipelines](#representing_pipelines)

/lit-part[`GPUBindGroup`](/en-US/docs/Web/API/GPUBindGroup)

Based on a [`GPUBindGroupLayout`](/en-US/docs/Web/API/GPUBindGroupLayout), a `GPUBindGroup` defines a set of resources to be bound together in a group and how those resources are used in shader stages.

[`GPUBindGroupLayout`](/en-US/docs/Web/API/GPUBindGroupLayout)

Defines the structure and purpose of related GPU resources such as buffers that will be used in a pipeline, and is used as a template when creating [`GPUBindGroup`](/en-US/docs/Web/API/GPUBindGroup)s.

[`GPUComputePipeline`](/en-US/docs/Web/API/GPUComputePipeline)

Controls the compute shader stage and can be used in a [`GPUComputePassEncoder`](/en-US/docs/Web/API/GPUComputePassEncoder).

[`GPUPipelineLayout`](/en-US/docs/Web/API/GPUPipelineLayout)

Defines the [`GPUBindGroupLayout`](/en-US/docs/Web/API/GPUBindGroupLayout)s used by a pipeline. [`GPUBindGroup`](/en-US/docs/Web/API/GPUBindGroup)s used with the pipeline during command encoding must have compatible [`GPUBindGroupLayout`](/en-US/docs/Web/API/GPUBindGroupLayout)s.

[`GPURenderPipeline`](/en-US/docs/Web/API/GPURenderPipeline)

Controls the vertex and fragment shader stages and can be used in a [`GPURenderPassEncoder`](/en-US/docs/Web/API/GPURenderPassEncoder) or [`GPURenderBundleEncoder`](/en-US/docs/Web/API/GPURenderBundleEncoder).

lit-part f4MxOYCZADo=lit-node 0

### lit-node 1[Encoding and submitting commands to the GPU](#encoding_and_submitting_commands_to_the_gpu)

/lit-part[`GPUCommandBuffer`](/en-US/docs/Web/API/GPUCommandBuffer)

Represents a recorded list of GPU commands that can be submitted to a [`GPUQueue`](/en-US/docs/Web/API/GPUQueue) for execution.

[`GPUCommandEncoder`](/en-US/docs/Web/API/GPUCommandEncoder)

Represents a command encoder, used to encode commands to be issued to the GPU.

[`GPUComputePassEncoder`](/en-US/docs/Web/API/GPUComputePassEncoder)

Encodes commands related to controlling the compute shader stage, as issued by a [`GPUComputePipeline`](/en-US/docs/Web/API/GPUComputePipeline). Part of the overall encoding activity of a [`GPUCommandEncoder`](/en-US/docs/Web/API/GPUCommandEncoder).

[`GPUQueue`](/en-US/docs/Web/API/GPUQueue)

Controls execution of encoded commands on the GPU.

[`GPURenderBundle`](/en-US/docs/Web/API/GPURenderBundle)

A container for pre-recorded bundles of commands (see [`GPURenderBundleEncoder`](/en-US/docs/Web/API/GPURenderBundleEncoder)).

[`GPURenderBundleEncoder`](/en-US/docs/Web/API/GPURenderBundleEncoder)

Used to pre-record bundles of commands. These can be reused in [`GPURenderPassEncoder`](/en-US/docs/Web/API/GPURenderPassEncoder)s via the [`executeBundles()`](/en-US/docs/Web/API/GPURenderPassEncoder/executeBundles) method, as many times as required.

[`GPURenderPassEncoder`](/en-US/docs/Web/API/GPURenderPassEncoder)

Encodes commands related to controlling the vertex and fragment shader stages, as issued by a [`GPURenderPipeline`](/en-US/docs/Web/API/GPURenderPipeline). Part of the overall encoding activity of a [`GPUCommandEncoder`](/en-US/docs/Web/API/GPUCommandEncoder).

lit-part d54MXvOa7k0=lit-node 0

### lit-node 1[Running queries on rendering passes](#running_queries_on_rendering_passes)

/lit-part[`GPUQuerySet`](/en-US/docs/Web/API/GPUQuerySet)

Used to record the results of queries on passes, such as occlusion or timestamp queries.

lit-part yPOyadZxCx4=lit-node 0

### lit-node 1[Debugging errors](#debugging_errors)

/lit-part[`GPUCompilationInfo`](/en-US/docs/Web/API/GPUCompilationInfo)

An array of [`GPUCompilationMessage`](/en-US/docs/Web/API/GPUCompilationMessage) objects, generated by the GPU shader module compiler to help diagnose problems with shader code.

[`GPUCompilationMessage`](/en-US/docs/Web/API/GPUCompilationMessage)

Represents a single informational, warning, or error message generated by the GPU shader module compiler.

[`GPUDeviceLostInfo`](/en-US/docs/Web/API/GPUDeviceLostInfo)

Returned when the [`GPUDevice.lost`](/en-US/docs/Web/API/GPUDevice/lost)[`Promise`](/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) resolves, providing information as to why the device was lost.

[`GPUError`](/en-US/docs/Web/API/GPUError)

The base interface for errors surfaced by [`GPUDevice.popErrorScope`](/en-US/docs/Web/API/GPUDevice/popErrorScope) and the [`uncapturederror`](/en-US/docs/Web/API/GPUDevice/uncapturederror_event) event.

[`GPUInternalError`](/en-US/docs/Web/API/GPUInternalError)

One of the types of errors surfaced by [`GPUDevice.popErrorScope`](/en-US/docs/Web/API/GPUDevice/popErrorScope) and the [`GPUDevice`](/en-US/docs/Web/API/GPUDevice)[`uncapturederror`](/en-US/docs/Web/API/GPUDevice/uncapturederror_event) event. Indicates that an operation failed for a system or implementation-specific reason, even when all validation requirements were satisfied.

[`GPUOutOfMemoryError`](/en-US/docs/Web/API/GPUOutOfMemoryError)

One of the types of errors surfaced by [`GPUDevice.popErrorScope`](/en-US/docs/Web/API/GPUDevice/popErrorScope) and the [`GPUDevice`](/en-US/docs/Web/API/GPUDevice)[`uncapturederror`](/en-US/docs/Web/API/GPUDevice/uncapturederror_event) event. Indicates that there was not enough free memory to complete the requested operation.

[`GPUPipelineError`](/en-US/docs/Web/API/GPUPipelineError)

Describes a pipeline failure. The value received when a [`Promise`](/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by a [`GPUDevice.createComputePipelineAsync()`](/en-US/docs/Web/API/GPUDevice/createComputePipelineAsync) or [`GPUDevice.createRenderPipelineAsync()`](/en-US/docs/Web/API/GPUDevice/createRenderPipelineAsync) call rejects.

[`GPUUncapturedErrorEvent`](/en-US/docs/Web/API/GPUUncapturedErrorEvent)

The event object type for the [`GPUDevice`](/en-US/docs/Web/API/GPUDevice)[`uncapturederror`](/en-US/docs/Web/API/GPUDevice/uncapturederror_event) event.

[`GPUValidationError`](/en-US/docs/Web/API/GPUValidationError)

One of the types of errors surfaced by [`GPUDevice.popErrorScope`](/en-US/docs/Web/API/GPUDevice/popErrorScope) and the [`GPUDevice`](/en-US/docs/Web/API/GPUDevice)[`uncapturederror`](/en-US/docs/Web/API/GPUDevice/uncapturederror_event) event. Describes an application error indicating that an operation did not pass the WebGPU API's validation constraints.

lit-part HDjAheV/t8Q=lit-node 0

## lit-node 1[Security requirements](#security_requirements)

/lit-part

The whole API is available only in a [secure context](/en-US/docs/Web/Security/Defenses/Secure_Contexts).

lit-part cjTOnCoGGWc=lit-node 0

## lit-node 1[Examples](#examples)

/lit-part
- [Basic compute demo](https://mdn.github.io/dom-examples/webgpu-compute-demo/)
- [Basic render demo](https://mdn.github.io/dom-examples/webgpu-render-demo/)
- [WebGPU samples](https://webgpu.github.io/webgpu-samples/)lit-part s915xX5HiM4=lit-node 0

## lit-node 1[Specifications](#specifications)

/lit-part

| Specification |
| WebGPU# gpu-interface |

lit-part y0+5SMr/T3s=lit-node 0

## lit-node 1[Browser compatibility](#browser_compatibility)

/lit-partlit-part y6RVfKR7hws=

lit-part hRoZS/r0nwc=/lit-part

/lit-partlit-part p88DAUaBJzA=lit-node 0

## lit-node 1[See also](#see_also)

/lit-part
- [WebGPU best practices](https://toji.dev/webgpu-best-practices/)
- [WebGPU explainer](https://gpuweb.github.io/gpuweb/explainer/)
- [WebGPU — All of the cores, none of the canvas](https://surma.dev/things/webgpu/)lit-part OWLzZqRMsCU=/lit-part

##  Help improve MDN 

lit-part wnhNI9MhleE=lit-part abqF9JTZmM8=lit-partWas this page helpful to you?/lit-partlit-node 3lit-part O1S+ZMb7umU=lit-node 0lit-partlit-part bRP2a5ux/uw=lit-part GjE5cW6UBoM=/lit-part/lit-partlit-part rI2hX8LXYZM=lit-node 0lit-part Pz0gobCCM4E=/lit-part/lit-part/lit-part/lit-partlit-partYes/lit-partlit-node 5lit-part O1S+ZMb7umU=lit-node 0lit-partlit-part bRP2a5ux/uw=lit-part IggRHjbPj/Q=/lit-part/lit-partlit-part rI2hX8LXYZM=lit-node 0lit-part Pz0gobCCM4E=/lit-part/lit-part/lit-part/lit-partlit-partNo/lit-part/lit-part/lit-part[Learn how to contribute](/en-US/docs/MDN/Community/Getting_started)

 This page was last modified on Sep 2, 2026 by [MDN contributors](/en-US/docs/Web/API/WebGPU_API/contributors.txt). 

[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/api/webgpu_api/index.md?plain=1) • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebGPU_API&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fwebgpu_api%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebGPU_API%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fwebgpu_api%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fd1fd21c87a4917e56dab84fc0b1d321ebb22874e%0A*+Document+last+modified%3A+2026-09-02T04%3A33%3A10.000Z%0A%0A%3C%2Fdetails%3E)