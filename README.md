# llama-cpp-python SM61 CUDA for Windows

**Custom CUDA builds of [llama-cpp-python](https://github.com/abetlen/llama-cpp-python) for legacy NVIDIA GPUs, with a focus on Pascal architecture (SM61) and Windows x64.**

This project provides custom-compiled Windows wheels of `llama-cpp-python`, targeting NVIDIA Pascal GPUs that may not be supported by commonly available prebuilt packages.

The primary goal is to make CUDA-accelerated inference with modern GGUF language and vision-language models accessible on legacy NVIDIA hardware.

## Overview

This project uses [JamePeng/llama-cpp-python](https://github.com/JamePeng/llama-cpp-python) as its source repository.

The build is based on the following upstream revision:

- **Repository:** [JamePeng/llama-cpp-python](https://github.com/JamePeng/llama-cpp-python)
- **Commit:** `3fc39b2ebcfbee10a6f64754b333eae2fe1ccc82`
- **Release:** `v0.4.5-cu126-win-20261025`

The Python source code is retained from the upstream revision. Customization is focused on the native CUDA build configuration and compilation for legacy GPU architectures.

## GPU Architecture Support

The primary build target is:

- NVIDIA Pascal GPUs
- Compute Capability 6.1 (SM61)
- CUDA Toolkit 12.6
- Windows x64

**Reference hardware:**
- NVIDIA GeForce GTX 1080 Ti (11 GB VRAM)

Other NVIDIA GPUs with Compute Capability 6.1 may be compatible, but have not necessarily been tested individually.

Compatibility with other GPU architectures is not guaranteed.

## Model Compatibility

This project uses `llama.cpp` as its underlying inference engine and supports GGUF models compatible with the bundled backend version.

Areas of interest include:

- Qwen3 language models
- Qwen3-VL vision-language models
- Other supported GGUF text and multimodal architectures

Vision-language inference may require an appropriate multimodal projector file (`mmproj`) and a compatible model handler.

Model compatibility depends on the bundled `llama.cpp` version, model architecture, GGUF format, and required auxiliary files.

Although this project primarily provides custom CUDA builds of llama-cpp-python, the compiled native libraries may also be useful in other applications that use or integrate with the llama.cpp inference backend.

### Potential Use Cases

Although this project primarily provides custom CUDA builds of `llama-cpp-python`, its compiled native components may potentially be useful in other applications that use or integrate with the `llama.cpp` inference backend.

Potential use cases include:

- **[LM Studio](https://lmstudio.ai/)**
- **[Bionic](https://lmstudio.ai/)**

**Important:** Compatibility with LM Studio, Bionic, or their related workflows has not been tested or verified. This wheel is built specifically for `llama-cpp-python` and is not a drop-in replacement for their inference backends. Additional integration or compatibility work may be required.
## Build Configuration

| Component | Version / Configuration |
|---|---|
| Operating System | Windows x64 |
| Python | 3.13 |
| llama-cpp-python | 0.4.5 |
| CUDA Toolkit | 12.6 |
| CUDA Architecture | SM61 |
| GPU Architecture | NVIDIA Pascal |
| Build System | CMake |
| Compiler | MSVC 2022 |

## Releases

Prebuilt Windows wheels are published through GitHub Releases.

Visit the [Releases](../../releases) page to find available builds and installation instructions.

Each release should include relevant build information, supported Python version, CUDA Toolkit version, target GPU architecture, and package checksums.

## Building from Source

The build configuration targets CUDA architecture `61`.

The compilation requires:

- Python 3.13
- CUDA Toolkit 12.6
- Visual Studio 2022 with MSVC
- CMake
- NVIDIA CUDA development tools

Build instructions and configuration details will be documented as the project evolves.

## Credits and Acknowledgements

This project builds upon and references the following open-source projects:

- [JamePeng/llama-cpp-python](https://github.com/JamePeng/llama-cpp-python) — Source repository and upstream build.
- [abetlen/llama-cpp-python](https://github.com/abetlen/llama-cpp-python) — Original Python bindings.
- [ggml-org/llama.cpp](https://github.com/ggml-org/llama.cpp) — Underlying C/C++ inference engine.
- [1038lab/ComfyUI-QwenVL](https://github.com/1038lab/ComfyUI-QwenVL) — Reference project and documentation for vision-related setup.

We acknowledge the original authors and contributors of these projects.

## License

This project retains the MIT License from its upstream source repository.

See [LICENSE.md](LICENSE.md) for the full license text.

Third-party dependencies and bundled components may be subject to their own licenses.