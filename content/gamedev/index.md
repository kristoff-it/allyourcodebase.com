---
title: "Gamedev"
date: 2022-06-05T17:18:20+02:00
draft: false
---

<style>
#content {
    align-items: baseline;
}
</style>

Zig is actively used for game development by both hobbyists for side projects, as well as a few seriously committed individuals who do Zig game development full time.

Libraries and bindings exist for most things, and general purpose engines/frameworks/ecosystems are in early stages of development.

<table>
    <thead>
        <td style="text-align: center;"><h2><a href="https://machengine.org">Mach engine</a></h2><em>Game engine & graphics toolkit for the future.</em></td>
        <td style="text-align: center;"><h2><a href="https://github.com/michal-z/zig-gamedev">zig-gamedev</a></h2><em>Building game development ecosystem for @ziglang! </em></td>
        <td style="text-align: center;"><h2><a href="https://github.com/MasterQ32/zero-graphics">zero-graphics</a></h2><em>A very minimal OpenGL ES 2.0 library for Zig</em></td>
    </thead>
    <tbody>
        <tr>
            <td>
                <a href="https://machengine.org/gpu"><img height="320" alt="Mach engine" src="https://user-images.githubusercontent.com/3173176/172064792-ef641a90-6469-412b-9794-f94c24d9883b.png"></a>
            </td>
            <td>
                <a href="https://github.com/michal-z/zig-gamedev#cross-platfrom-winlinmac-sample-applications-native-webgpu"><img height="320" alt="zig-gamedev" src="https://user-images.githubusercontent.com/3173176/172064027-a98be1d5-7f82-4a30-b461-aab0431af2d2.png"></a>
            </td>
            <td>
                <a href="https://github.com/MasterQ32/zero-graphics#previews"><img height="320" alt="zero-graphics" src="https://user-images.githubusercontent.com/3173176/172064178-5516cf4f-4a23-4bca-af4e-13111c4d4192.png"></a>
            </td>
        </tr>
        <tr>
<td>

Mach is for creating games, graphical applications, and desktop/mobile/web apps:

- Data-driven, tooling oriented
- Composable (ECS-based)
- Competitive with Unity and Unreal in spirit (a fully fledged editor in the future, etc.)

</td>
<td>


zig-gamedev is a collection of sample applications and cross-platform, standalone, composable libraries. See [Roadmap](https://github.com/michal-z/zig-gamedev/wiki/Roadmap) and [Progress Reports](https://github.com/michal-z/zig-gamedev/wiki/Progress-Reports) for the details.

PBR demos, procedural meshes, and DirectX raytracing. Bullet physics.

</td>
<td>


zero-graphics is an application framework based on OpenGL ES 2.0. Runs on desktop machines, Android phones and the web 

Opens you a window and let's you draw things. Comes with a pixel-perfect 2D renderer and maybe some day even with a bit of a 3D api.


</td>
</tr>
<tr>
    <td>DirectX 12/Vulkan/Metal & OpenGL (as fallback) via cutting-edge WebGPU implementation used by Chrome. WebGPU when targetting WebAssembly.</td>
    <td>Uses native version of WebGPU API (mach/gpu) for cross-platfrom graphics and DirectX 12 for low-level graphics on Windows</td>
    <td>Based on OpenGL ES 2 for as broad-as-possible platform coverage.</td>
</tr>
<tr>
    <td>Windows/Linux/Mac; WebAssembly (WebGPU); mobile/VR/console planned</td>
    <td>Windows/Linux/Mac</td>
    <td>Windows/Linux/Mac; WebAssembly (WebGL); Android</td>
</tr>
</tbody>
</table>

# Communities

* [`#game-dev`](https://discord.com/channels/605571803288698900/634812978994085888) in the Zig Programming Language Discord is the primary gathering place to discuss Zig game development.
* [hexops:matrix.org](https://matrix.to/#/#hexops:matrix.org) chat server, all Mach engine discussion takes place here, in addition to general discussions of ECS/AI/GUI systems.

# Libraries / tools

## Graphics APIs

- [hexops/mach-gpu-dawn](https://github.com/hexops/mach-gpu-dawn) - Google's Dawn WebGPU implementation, cross-compiled with Zig into a single static library. Powers both Mach engine and zig-gamedev.
- [hexops/mach-gpu](https://github.com/hexops/mach/tree/main/gpu) - WebGPU bindings for Zig, truly cross-platform graphics API with unified low-level graphics & compute backed by Vulkan, Metal, D3D12, and OpenGL (as a best-effort fallback.) Used by both Mach engine and zig-gamedev, with [extensive examples here](https://machengine.org/gpu/) and [here](https://github.com/michal-z/zig-gamedev/tree/main/samples).
- [zig-gamedev/zgpu](https://github.com/michal-z/zig-gamedev/tree/main/libs/zgpu) - Cross-platform graphics layer built on top of native WebGPU API (Dawn) / mach/gpu bindings.
- [MasterQ32/zig-opengl](https://github.com/MasterQ32/zig-opengl) - pragmatic binding to different OpenGL versions, uses the official OpenGL Registry by Khronos to generate the Zig code. Used by zero-graphics.
- [ziglibs/zgl](https://github.com/ziglibs/zgl) - a thin, type-safe binding for OpenGL on top of libepoxy.
- [zig-gamedev/z3d12](https://github.com/michal-z/zig-gamedev/blob/main/libs/zd3d12) - helper library for working with DirectX 12

## Windowing

- [hexops/mach-glfw](https://github.com/hexops/mach-glfw) - Ziggified GLFW bindings that Mach engine uses, with 100% API coverage, zero-fuss installation, cross compilation, and more. Used by Mach engine and zig-gamedev.
- [MasterQ32/SDL.zig](https://github.com/MasterQ32/SDL.zig) - shallow wrapper around SDL that provides object API and error handling. Used by zero-graphics.

## GUI

- TODO: [help us populate this section!](#help-improve-this-page)

## Text rendering

- [hexops/mach-freetype](https://github.com/hexops/mach-freetype) - Ziggified FreeType 2 bindings that Mach engine uses, with zero-fuss installation, cross compilation, and more.

## Image formats

- [zigimg/zigimg](https://github.com/zigimg/zigimg) - for reading and writing different image formats

## Math

- [zig-gamedev/zmath](https://github.com/michal-z/zig-gamedev/blob/main/libs/zmath) - SIMD math library for game developers
- [ziglibs/zlm](https://github.com/ziglibs/zlm) - linear mathemathics library, built around the OpenGL coordinate system and fully generic on the basic data type.

## Physics

- [zig-gamedev/zbullet](https://github.com/michal-z/zig-gamedev/blob/main/libs/zbullet) - Zig bindings and C API for Bullet physics library

## Audio

- [zig-gamedev/zxaudio2](https://github.com/michal-z/zig-gamedev/blob/main/libs/zxaudio2) - helper library for working with XAudio2 (Windows library)

## Architecture

- [hexops/mach-ecs](https://github.com/hexops/mach/tree/main/ecs) - an Entity Component System for Zig built from first-principles and detailed in [this blog series](https://devlog.hexops.com/categories/build-an-ecs/).
- [prime32/zig-flecs](https://github.com/prime31/zig-flecs) - Flecs Zig Bindings
- [zig-gamedev/zpool](https://github.com/michal-z/zig-gamedev/blob/main/libs/zpool) - generic pool & handle implementation

## Networking

- [MasterQ32/zig-mqtt](https://github.com/MasterQ32/zig-mqtt) A build package for the awesome mqtt-c project by Liam Bindle.
- [MasterQ32/zig-network](https://github.com/MasterQ32/zig-network) - smallest-common-subset of socket functions for crossplatform networking, TCP & UDP.
- [zig-gamedev/znet](https://github.com/michal-z/zig-gamedev/blob/main/libs/znetwork) - Zig bindings for ENet

## Serialization

- [ziglibs/s2s](https://github.com/ziglibs/s2s) - struct to stream | stream to struct, a binary serialization format and library.
- [kubkon/protozig](https://github.com/kubkon/protozig) - The protozig(uana), or protocol buffers implementation in Zig

## Databases

- [vrischmann/zig-sqlite](https://github.com/vrischmann/zig-sqlite) - a small wrapper around sqlite's C API, making it easier to use with Zig. 

## Configuration

- [ziglibs/ini](https://github.com/ziglibs/ini) - A teeny tiny ini parser.
- [kubkon/zig-yaml](https://github.com/kubkon/zig-yaml) - YAML parser for Zig

## Android/iOS/VR/WASM

- [MasterQ32/ZigAndroidTemplate](https://github.com/MasterQ32/ZigAndroidTemplate) - This repository contains a example on how to create a minimal Android app in Zig.
- [kubkon/zig-ios-example](https://github.com/kubkon/zig-ios-example) - Minimal build.zig for targeting iOS 
- [kubkon/zig-deploy](https://github.com/kubkon/zig-deploy) - Deploy your iOS apps written with Zig!
- [SpexGuy/Zig-Oculus-Quest](https://github.com/SpexGuy/Zig-Oculus-Quest) - An example application for the Oculus Quest, written in Zig
- [alichay/zig-wasm3](https://github.com/alichay/zig-wasm3) - bindings (and build system integration) for Wasm3

## Scripting

- [squeek502/zua](https://github.com/squeek502/zua) - An implementation of Lua 5.1 in Zig, for learning purposes 
- [Vexu/bog](https://github.com/Vexu/bog) - Small, strongly typed, embeddable language.
- [LoLa](https://lola.random-projects.net/) - an embeddable programming language for game scripting,

## Other

- [zig-gamedev/zmesh](https://github.com/michal-z/zig-gamedev/blob/main/libs/zmesh) - loading, generating, processing and optimizing triangle meshes
- [zig-gamedev/znoise](https://github.com/michal-z/zig-gamedev/blob/main/libs/znoise) - Zig bindings for FastNoiseLite
- [zig-gamedev/ztracy](https://github.com/michal-z/zig-gamedev/blob/main/libs/ztracy) - support for CPU profiling with Tracy

# Tools

- [Mini Pixel](https://fabioarnold.itch.io/mini-pixel) - A Simple Editor for Tiny Graphics

# Games

- [pacman.zig](https://github.com/kubkon/pacman.zig) - Simple Pacman clone written in Zig.

# Help improve this page

Feel free to improve [AllYourCodebase](https://github.com/AllYourCodebase/AllYourCodebase.github.io) by sending a PR! Please ensure entires on this page are:

* Alphabetically ordered by project name
* Actively maintained (at least one commit in the last 12 months, or broadly used by the community.)
