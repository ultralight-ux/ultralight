<img src="media/logo.png" width="700">
<a href='https://ci.ultralig.ht/job/Ultralight/job/master/'><img src='https://ci.ultralig.ht/buildStatus/icon?job=Ultralight%2Fmaster'></a>

[Website](https://ultralig.ht) | [Join our Discord!](https://chat.ultralig.ht) | [Browse C/C++ API](https://github.com/ultralight-ux/Ultralight-API/) | [ Documentation](https://docs.ultralig.ht) | [Follow on Twitter](https://twitter.com/ultralight_ux)

## Discord Chat

Got a question about Ultralight? Come chat with us on Discord!

[<strong>Join the Ultralight Discord!</strong> <img src="media/discord-logo.svg">](https://chat.ultralig.ht)

# About

Ultralight is an ultra-fast, ultra-light, standards-compliant HTML renderer for applications and games. It supports most modern HTML5, CSS, and JavaScript features while still remaining light in binary size and memory usage.

Currently available for Windows, macOS, and Linux (64-bit only, ARM64 coming).

Official API is available for C and C++, with community bindings for C#, Rust, Java, and Go [available here](https://docs.ultralig.ht/docs/language-bindings).

Get started now by [reading the docs](https://docs.ultralig.ht).

## Next-Generation HTML Renderer

You can think of Ultralight like a smaller, lighter, cross-platform WebKit that's more customizable and designed to display HTML in an existing app rather than function as a standalone browser.

The API allows you to integrate your native code deeply with JavaScript (we offer bare-metal access to the JavaScriptCore VM API) and allows you to customize file system loaders, font loading, clipboard integration, and even drawing itself (via GPU display lists or the Surface API).


## For Games

Render HTML to an in-game texture using our CPU renderer or take performance to the next level using our GPU renderer.

Take advantage of our low-level platform API— load HTML assets directly from your game's existing asset pipeline using the FileSystem interface.

__→ Learn more by visiting our [Game Integration Guide](https://docs.ultralig.ht/docs/integrating-with-games).__

## For Desktop Apps

Get the best of both worlds by building your native C/C++ desktop app's front-end with modern HTML/CSS/JS.

Take advantage of our AppCore framework to launch cross-platform windows and render to OS-native GPU surfaces (D3D11, D3D12, Metal, OpenGL, and more).

_AppCore is currently under active development and only supports single-window apps at this writing. A number of planned features (app icons, automatic packager, borderless windows with custom draggable titlebars, etc) are missing but on the way._

__→ Learn more by visiting our [Desktop App Guide](https://docs.ultralig.ht/docs/writing-your-first-app).__

### Base Memory Usage

|             | Ultralight  | Electron  |
|-------------|-------------|-----------|
| __Windows__ | 9 MB        | 72 MB     |
| __macOS__   | 17 MB       | 97 MB     |
| __Linux__   | 15 MB       | 136 MB    |

### Base Distributable Size

|             | Ultralight  | Electron  |
|-------------|-------------|-----------|
| __Windows__ | 40 MB       | 147 MB    |
| __macOS__   | 55 MB       | 163 MB    |
| __Linux__   | 55 MB       | 179 MB    |

### Comparison with Chromium

|                       | Ultralight               | Chromium                    |
|-----------------------|--------------------------|-----------------------------|
| __Renderer__          | Proprietary (GPU or CPU) | Skia (CPU) / GPU Compositor |
| __Layout Engine__     | WebCore (WebKit fork)    | Blink                       |
| __JavaScript VM__     | JavaScriptCore           | V8                          |
| __IPC__               | None (Single Process)    | Yes (Multi Process)         |

# Architecture

Ultralight is a new port of WebKit combined with a new lightweight renderer intended specifically for embedding in apps and games.

Portions of the library are open-source, here's how the library is laid out:

|                    | Description                       | License     | Source Code              |
|--------------------|-----------------------------------|-------------|--------------------------|
| __UltralightCore__ | Low-level graphics renderer       | Proprietary | (Available with license) |
| __WebCore__        | HTML layout engine (WebKit fork)  | LGPL/BSD    | [ultralight-ux/WebCore](https://github.com/ultralight-ux/WebCore) |
| __Ultralight__     | View, compositor, and event logic | Proprietary | (Available with license)  |
| __AppCore__        | Optional, desktop app runtime     | LGPL        | [ultralight-ux/AppCore](https://github.com/ultralight-ux/AppCore) |

## Dual High-Performance Renderers

We support two different renderers for integration into a variety of target environments.

### GPU Renderer

Our optional, high-performance GPU renderer can render HTML directly on the GPU. All painting is performed via virtual display lists and translated to your target graphics platform at runtime. For more info, see [Using a Custom GPUDriver](https://docs.ultralig.ht/docs/using-a-custom-gpudriver).

The GPU renderer is enabled by default when using Ultralight via the AppCore runtime.

### CPU Renderer

For easier integration into games and other complex environments, Ultralight can render to an offscreen pixel buffer using an SIMD-accelerated CPU rendering pipeline. Fore more info, see the [Game Integration Guide](https://docs.ultralig.ht/docs/integrating-with-games).

The library can also render to a user-supplied pixel buffer via the Surface API (see [Using a Custom Surface](https://docs.ultralig.ht/docs/using-a-custom-surface)).

Paths, gradients, and patterns in this mode are rasterized using [Blend2D's high-performance JIT compiler](https://blend2d.com).

# Licensing

## Free License

Ultralight is __free__ for non-commercial use and __free__ for commercial use by companies with less than $100K gross annual revenue. For more info see [LICENSE.txt](license/LICENSE.txt)

## Commercial Licensing and Support 

We offer commercial licensing, priority support, and source code. To learn more,  please [visit our website](https://ultralig.ht).

# Building the Samples

To build the samples in this repo, please [follow the instructions here](https://docs.ultralig.ht/docs/trying-the-samples).

# Getting the Latest SDK

You can get the latest SDK for each platform via the following links:

 * [Windows       | x64](https://ultralight-sdk.sfo2.cdn.digitaloceanspaces.com/ultralight-sdk-latest-win-x64.7z)
 * [Linux         | x64](https://ultralight-sdk.sfo2.cdn.digitaloceanspaces.com/ultralight-sdk-latest-linux-x64.7z)
 * [macOS         | x64](https://ultralight-sdk.sfo2.cdn.digitaloceanspaces.com/ultralight-sdk-latest-mac-x64.7z)

### Getting Archived Binaries for a Specific Commit

Pre-built binares are uploaded to the following S3 buckets every commit:

 * __Archived Binaries__: <https://ultralight-sdk.sfo2.cdn.digitaloceanspaces.com/>

# Useful Links

| Link                       | URL                                                 |
| -------------------------- | --------------------------------------------------- |
| __Join our Discord!__      | <https://chat.ultralig.ht>                          |
| __Docs / Getting Started__ | <https://docs.ultralig.ht>                          |
| __Browse C/C++ API__       | <https://github.com/ultralight-ux/Ultralight-API/>  |
| __Follow Us on Twitter__   | <https://twitter.com/ultralight_ux>                 |
