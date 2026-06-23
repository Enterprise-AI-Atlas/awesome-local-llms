# Awesome Local LLMs

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](./CONTRIBUTING.md)

A curated, category-organized registry of tools, models, and resources for running **Large Language Models locally** — on consumer GPUs, CPUs, Apple Silicon, and self-hosted hardware.

The goal is to be the definitive place to discover inference engines, quantized models, local chat UIs, model management utilities, fine-tuning tools, local RAG stacks, deployment options, and hardware acceleration layers that keep data on-device.

**Inclusion criteria:** Resources must be directly useful for running, serving, managing, or optimizing LLMs on local hardware. Cloud-only APIs and general tutorials are out of scope. See [CONTRIBUTING.md](./CONTRIBUTING.md) for the full quality bar.

---

## Contents

- [Inference Engines](#inference-engines)
- [Quantized Models](#quantized-models)
- [Local Chat UIs](#local-chat-uis)
- [Model Management](#model-management)
- [Fine-Tuning Locally](#fine-tuning-locally)
- [RAG Locally](#rag-locally)
- [Deployment Tools](#deployment-tools)
- [Hardware / Acceleration](#hardware--acceleration)
- [Related Awesome Lists](#related-awesome-lists)
- [Contributing](#contributing)
- [License](#license)

---

## Inference Engines

Core libraries and servers that run LLMs on your own hardware.

- **[llama.cpp](https://github.com/ggml-org/llama.cpp)** `Community` — High-performance C/C++ inference engine for GGUF models on CPU, CUDA, Metal, Vulkan, and ROCm.
  - Run: `llama-cli -m model.gguf -p "Hello"`
- **[Ollama](https://github.com/ollama/ollama)** `Community` — One-command runner and model server with an OpenAI-compatible API.
  - Run: `ollama run llama3.2`
- **[vLLM](https://github.com/vllm-project/vllm)** `Community` — High-throughput, memory-efficient serving engine with PagedAttention for local and on-prem deployment.
  - Run: `vllm serve meta-llama/Llama-3.1-8B`
- **[LocalAI](https://github.com/mudler/LocalAI)** `Community` — Self-hosted, OpenAI-compatible REST API for LLMs, embeddings, images, and audio.
  - Run: `local-ai` with a downloaded GGUF or safetensors model.
- **[ExLlamaV2](https://github.com/turboderp/exllamav2)** `Community` — Fast, memory-efficient inference for EXL2 and GPTQ quantized models on NVIDIA GPUs.
- **[TensorRT-LLM](https://github.com/NVIDIA/TensorRT-LLM)** `Official` — NVIDIA-optimized inference library for low-latency, high-throughput LLM serving on RTX and data-center GPUs.
- **[MLX](https://github.com/ml-explore/mlx)** `Official` — Apple Silicon-native machine-learning framework with efficient LLM inference and training.
- **[llamafile](https://github.com/Mozilla-Ocho/llamafile)** `Community` — Single-file executable LLMs that run on macOS, Linux, and Windows without installation.
- **[KoboldCpp](https://github.com/LostRuins/koboldcpp)** `Community` — Easy-to-use llama.cpp wrapper with a built-in web UI, story tools, and multi-backend GPU support.
- **[SGLang](https://github.com/sgl-project/sglang)** `Community` — Structured generation and fast serving runtime for local and distributed LLMs.

---

## Quantized Models

Real model families and community quantization hubs that make large models runnable locally.

- **[Meta Llama 3](https://huggingface.co/meta-llama/Meta-Llama-3-8B)** `Official` — Open-weight Llama 3 family from Meta, available in 8B and 70B sizes.
- **[Mistral 7B](https://huggingface.co/mistralai/Mistral-7B-v0.3)** `Official` — Efficient open-weight model from Mistral AI, widely used for local inference.
- **[Qwen 2.5](https://huggingface.co/Qwen/Qwen2.5-7B)** `Official` — Alibaba's multilingual open-weight LLM family with strong local performance.
- **[DeepSeek-R1](https://huggingface.co/deepseek-ai/DeepSeek-R1)** `Official` — Reasoning-focused open-weight model family distilled into smaller local-friendly sizes.
- **[Gemma 3](https://huggingface.co/google/gemma-3-4b-it)** `Official` — Google's lightweight, instruction-tuned open models in 1B, 4B, 12B, and 27B variants.
- **[Phi-4](https://huggingface.co/microsoft/phi-4)** `Official` — Microsoft's compact, high-quality open model well suited for consumer hardware.
- **[TheBloke GGUF Models](https://huggingface.co/TheBloke)** `Community` — Massive collection of GGUF-quantized models for llama.cpp and Ollama.
- **[bartowski GGUF Models](https://huggingface.co/bartowski)** `Community` — Curated GGUF quantizations of popular open models.
- **[MLX Community](https://huggingface.co/mlx-community)** `Community` — Ready-to-run MLX-converted models for Apple Silicon.
- **[Nous Hermes 3](https://huggingface.co/NousResearch/Hermes-3-Llama-3.1-8B)** `Community` — General-purpose, fine-tuned open model by Nous Research.

---

## Local Chat UIs

Applications for chatting with local models through a friendly interface.

- **[Open WebUI](https://github.com/open-webui/open-webui)** `Community` — Extensible, self-hosted web interface for Ollama and OpenAI-compatible APIs.
  - Run: `docker run -d -p 3000:8080 --gpus all -v ollama:/root/.ollama -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main`
- **[LM Studio](https://lmstudio.ai/)** `Official` — Desktop app to discover, download, and chat with local GGUF models.
- **[Jan](https://jan.ai/)** `Official` — Open-source, privacy-first ChatGPT alternative that runs models locally.
- **[GPT4All](https://www.nomic.ai/gpt4all)** `Official` — Offline chat application with a bundled model downloader and local-first defaults.
- **[AnythingLLM](https://github.com/Mintplex-Labs/anything-llm)** `Community` — Local and private workspace for chatting with documents and local LLMs.
- **[Lobe Chat](https://github.com/lobehub/lobe-chat)** `Community` — Modern chat UI supporting Ollama and other local providers.
- **[LibreChat](https://github.com/danny-avila/LibreChat)** `Community` — Multi-provider chat UI with Ollama and local endpoint support.
- **[Chatbox](https://github.com/Bin-Huang/chatbox)** `Community` — Cross-platform desktop client for local and remote LLMs.
- **[Oterm](https://github.com/ggozad/oterm)** `Community` — Terminal client for Ollama with conversation management.
- **[SillyTavern](https://github.com/SillyTavern/SillyTavern)** `Community` — Frontend for role-play and character-driven chats with local LLM backends.

---

## Model Management

Tools for downloading, converting, quantizing, and organizing local models.

- **[Hugging Face Hub CLI](https://huggingface.co/docs/huggingface_hub/en/index)** `Official` — Official CLI and Python library to download and manage models from the Hub.
  - Install: `pip install huggingface_hub`
  - Download: `huggingface-cli download TheBloke/Llama-2-7B-GGUF`
- **[Ollama Model Library](https://ollama.com/library)** `Community` — Curated registry of models ready to pull and run with Ollama.
  - Pull: `ollama pull llama3.2`
- **[llama.cpp Convert Scripts](https://github.com/ggml-org/llama.cpp/tree/master/convert)** `Community` — Scripts to convert Hugging Face checkpoints into GGUF format for local inference.
- **[AutoGPTQ](https://github.com/AutoGPTQ/AutoGPTQ)** `Community` — Easy-to-use GPTQ quantization toolkit for running compressed models locally.
- **[AutoAWQ](https://github.com/casper-hansen/AutoAWQ)** `Community` — Quantization and inference library for AWQ-compressed models.
- **[ModelScope](https://www.modelscope.cn/)** `Official` — Open model hub with CLI and SDK for downloading and managing models.
- **[Simon Willison's llm CLI](https://github.com/simonw/llm)** `Community` — Command-line tool for running models via Ollama, OpenAI-compatible APIs, and local plugins.
  - Install: `pip install llm`
- **[Git LFS](https://git-lfs.com/)** `Official` — Version-control extension used by Hugging Face and other hubs for large model files.

---

## Fine-Tuning Locally

Frameworks for supervised fine-tuning, LoRA/QLoRA, and preference tuning on your own hardware.

- **[Axolotl](https://github.com/axolotl-ai-cloud/axolotl)** `Community` — YAML-driven fine-tuning framework supporting LoRA, QLoRA, and full fine-tunes.
- **[Unsloth](https://github.com/unslothai/unsloth)** `Official` — Optimized fine-tuning and reinforcement-learning library with 2-5× speedups on consumer GPUs.
- **[LLaMA-Factory](https://github.com/hiyouga/LLaMA-Factory)** `Community` — Web UI and CLI for efficient fine-tuning of 100+ LLMs.
- **[torchtune](https://github.com/pytorch/torchtune)** `Official` — PyTorch-native library for post-training, fine-tuning, and quantization of LLMs.
- **[litgpt](https://github.com/Lightning-AI/litgpt)** `Community` — Lightning-AI command-line tool for pre-training, fine-tuning, and deploying LLMs.
- **[mlx-lm](https://github.com/ml-explore/mlx-examples/tree/main/llms)** `Official` — MLX examples for running and fine-tuning LLMs on Apple Silicon.
- **[PEFT](https://github.com/huggingface/peft)** `Official` — Hugging Face parameter-efficient fine-tuning library (LoRA, IA³, adapters).
- **[TRL](https://github.com/huggingface/trl)** `Official` — Hugging Face transformer reinforcement learning library for SFT, DPO, and PPO.
- **[bitsandbytes](https://github.com/TimDettmers/bitsandbytes)** `Community` — 8-bit optimizers and 4-bit quantization primitives for local fine-tuning.

---

## RAG Locally

Frameworks and applications for retrieval-augmented generation using local models and vector stores.

- **[AnythingLLM](https://github.com/Mintplex-Labs/anything-llm)** `Community` — All-in-one local workspace with document RAG, agents, and multi-model support.
- **[PrivateGPT](https://github.com/zylon-ai/private-gpt)** `Community` — Local RAG and chat solution designed for privacy with no data leaving the machine.
- **[RAGFlow](https://github.com/infiniflow/ragflow)** `Community` — Open-source RAG engine with document parsing and local model support.
- **[LangChain](https://github.com/langchain-ai/langchain)** `Official` — Framework for building applications that connect local LLMs, vector stores, and tools.
- **[LlamaIndex](https://github.com/run-llama/llama_index)** `Official` — Data framework for ingestion, indexing, and querying with local LLMs.
- **[Haystack](https://github.com/deepset-ai/haystack)** `Official` — End-to-end NLP framework for local RAG pipelines and semantic search.
- **[txtai](https://github.com/neuml/txtai)** `Community` — Lightweight local semantic search, RAG, and workflows in pure Python.
- **[Chroma](https://github.com/chroma-core/chroma)** `Community` — Developer-friendly open-source vector database for embeddings and RAG.
- **[Quivr](https://github.com/QuivrHQ/quivr)** `Community` — Second-brain RAG app with local model and vector-store support.

---

## Deployment Tools

Servers, proxies, and packaging options for exposing local LLMs to clients.

- **[Docker](https://www.docker.com/)** `Official` — Container platform used to package local LLM servers with GPU passthrough.
  - Run Ollama: `docker run -d --gpus all -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama`
- **[vLLM](https://github.com/vllm-project/vllm)** `Community` — Production-grade OpenAI-compatible server for local and on-prem deployment.
- **[LocalAI](https://github.com/mudler/LocalAI)** `Community` — Drop-in OpenAI-compatible API server for local models, embeddings, and media generation.
- **[llama.cpp Server](https://github.com/ggml-org/llama.cpp/tree/master/examples/server)** `Community` — Built-in HTTP server in llama.cpp with chat-completion endpoints.
  - Build and run: `make -C examples/server` then `./server -m model.gguf`
- **[TabbyAPI](https://github.com/theroyallab/tabbyAPI)** `Community` — OpenAI-compatible API server for ExLlamaV2 and llama.cpp backends.
- **[Text Generation Inference](https://github.com/huggingface/text-generation-inference)** `Official` — Hugging Face production server for running open LLMs locally.
- **[OpenLLM](https://github.com/bentoml/OpenLLM)** `Community` — BentoML-based toolkit for serving open-source LLMs with an OpenAI-compatible API.
- **[exo](https://github.com/exo-explore/exo)** `Community` — Run your own AI cluster at home across everyday devices (Mac, Linux, Windows, phones).
- **[distributed-llama](https://github.com/b4rtaz/distributed-llama)** `Community` — Connect home devices into a cluster to split LLM inference across nodes.
- **[llama-swap](https://github.com/mostlygeek/llama-swap)** `Community` — Reliable model swapping proxy for any local OpenAI-compatible server.

---

## Hardware / Acceleration

GPUs, SDKs, and backends that accelerate local LLM inference.

- **[NVIDIA CUDA Toolkit](https://developer.nvidia.com/cuda-toolkit)** `Official` — SDK and runtime for GPU-accelerated inference on NVIDIA hardware.
- **[AMD ROCm](https://github.com/ROCm/ROCm)** `Official` — Open-source GPU compute stack for running LLMs on AMD Radeon and Instinct GPUs.
- **[Apple Metal](https://developer.apple.com/metal/)** `Official` — GPU framework powering MLX and llama.cpp on Apple Silicon.
- **[Intel OpenVINO](https://github.com/openvinotoolkit/openvino)** `Official` — Toolkit for optimizing and accelerating inference on Intel CPUs, GPUs, and NPUs.
- **[ONNX Runtime](https://onnxruntime.ai/)** `Official` — Cross-platform inference accelerator with support for CUDA, DirectML, ROCm, and OpenVINO.
- **[NVIDIA TensorRT](https://developer.nvidia.com/tensorrt)** `Official` — High-performance inference optimizer and runtime for NVIDIA GPUs.
- **[Intel Extension for PyTorch](https://github.com/intel/intel-extension-for-pytorch)** `Official` — PyTorch extension optimized for Intel CPUs and Xe GPUs.
- **[llama.cpp Vulkan Backend](https://github.com/ggml-org/llama.cpp/blob/master/docs/backend/Vulkan.md)** `Community` — Vulkan compute backend for cross-platform GPU inference on AMD, Intel, and NVIDIA.
- **[GGML](https://github.com/ggml-org/ggml)** `Community` — Tensor library powering llama.cpp backends for CPU, CUDA, Metal, Vulkan, and more.
- **[DirectML](https://github.com/microsoft/DirectML)** `Official` — Microsoft's DirectX-based machine-learning accelerator for Windows GPUs.

---

## Related Awesome Lists

- **[vince-lam/awesome-local-llms](https://github.com/vince-lam/awesome-local-llms)** — Curated list of local LLM tools and resources.
- **[ununununium/awesome-local-ai](https://github.com/ununununium/awesome-local-ai)** — 150+ open-source tools to run LLMs 100% locally.
- **[sam-blackfly/awesome-llm-tools](https://github.com/sam-blackfly/awesome-llm-tools)** — Essential tools spanning quantization, inference, agents, RAG, and fine-tuning.
- **[av/awesome-llm-services](https://github.com/av/awesome-llm-services)** — LLM services, tools, and infrastructure for running AI locally.
- **[Hannibal046/Awesome-LLM](https://github.com/Hannibal046/Awesome-LLM)** — Broad awesome list of large language model resources.

---

## Contributing

Read [CONTRIBUTING.md](./CONTRIBUTING.md) for the quality bar, entry format, and PR process.

---

## License

This list is released into the public domain under [CC0-1.0](./LICENSE).

## Want us to build this for you?

Enterprise AI Atlas is maintained by [Vibe Coding Agency](https://vibecodingagency.com). We prototype and ship agentic systems, MCP servers, and enterprise AI integrations for teams that need working software fast — without hiring a full AI engineering team.
