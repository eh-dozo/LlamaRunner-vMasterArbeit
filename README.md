# LlamaRunner Unreal Engine Plugin

## Overview

A [llama.cpp](https://github.com/ggml-org/llama.cpp) Third-Party Library Plugin for Unreal Engine 5.5 developed
during prior independent coursework at HTW Berlin, and further extended as part of the
[MasterArbeit](https://github.com/eh-dozo/MasterArbeit) thesis project.

This is the thesis-specific version of the plugin. It provides a Game Instance Subsystem for running LLM inference
on a dedicated background thread with CUDA acceleration, callable from both C++ and Blueprints.

## Features *(C++ & Blueprint)*

- Common configuration:
  - `.gguf` Model path
  - Model parameters (context size, batches, GPU layers)
- Sampler configuration:
  - Grammar-constrained output via `.gbnf` files
  - Decoding method: Top-P / Top-K or Min-P
  - Sampling method: Greedy, Dist, or [Mirostat](https://arxiv.org/abs/2007.14966)
  - Repetition penalty (last-N, frequency, presence)
- [Multi-threaded inference](https://forums.unrealengine.com/t/multithreading-and-performance-in-unreal/1216417)
- Character switching with KV cache management
- Context usage warnings and error delegates
- Inference timing capture delegate
- All settings editable in **Project Settings > Plugins > Llama Runner**

## Installation

This plugin is included as a **git submodule** of the
[MasterArbeit](https://github.com/eh-dozo/MasterArbeit) repository. Refer to the main project README for
full setup and build instructions.

For standalone use, place this repository inside the `Plugins/` folder of an Unreal Engine 5.5 project.
A CUDA-capable NVIDIA GPU is **required**.

## Resources

Grammar files (`.gbnf`) used in the thesis are located in `Resources/Grammars/`.
Model files (`.gguf`) are not included due to size.

## License

See [LICENSE](LICENSE) for details.
