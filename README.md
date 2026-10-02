# Awesome Apertus

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![Suggestions welcome](https://img.shields.io/badge/suggestions-welcome-brightgreen)](https://github.com/rnckp/awesome-apertus/issues/new)
[![License: CC0](https://img.shields.io/badge/license-CC0-blue)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/rnckp/awesome-apertus.svg)](https://github.com/rnckp/awesome-apertus)
[![Last commit](https://img.shields.io/github/last-commit/rnckp/awesome-apertus)](https://github.com/rnckp/awesome-apertus/commits/main/)

A curated guide to [Apertus](https://www.apertus-ai.org/), the open multilingual model family from the [Swiss AI Initiative](https://www.swiss-ai.org/), developed by EPFL, ETH Zurich, and CSCS. Official models, reproducibility resources, tools, integrations, and community projects.

**Last researched: September 26, 2026.** Independent community list. “Official” means published by the Apertus team or Swiss AI; other projects belong to their respective maintainers. Collections cover variant families without listing every duplicate conversion. See [research notes](RESEARCH.md) for scope and verification limits.

<details>
<summary><strong>Table of Contents</strong></summary>

<ul>
  <li><a href="#start-here">Start here</a></li>
  <li><a href="#official-sites-and-documentation">Official sites and documentation</a></li>
  <li><a href="#official-models">Official models</a></li>
  <li><a href="#official-code-and-training-infrastructure">Official code and training infrastructure</a></li>
  <li><a href="#datasets-and-transparency">Datasets and transparency</a></li>
  <li><a href="#research-and-evaluation">Research and evaluation</a></li>
  <li><a href="#local-inference-and-serving">Local inference and serving</a></li>
  <li><a href="#community-quantizations-and-derivatives">Community quantizations and derivatives</a></li>
  <li><a href="#hosted-apis-and-cloud-deployment">Hosted APIs and cloud deployment</a></li>
  <li><a href="#applications-and-integrations">Applications and integrations</a></li>
  <li><a href="#community-and-contributing">Community and contributing</a></li>
</ul>

</details>

## Start here

- **Try chat:** [Public AI](https://publicai.co/) or the official [Apertus Mini WebGPU demo](https://huggingface.co/spaces/swiss-ai/apertus-mini-webgpu).
- **Download models:** [Swiss AI on Hugging Face](https://huggingface.co/swiss-ai) and the [model guide below](#official-models).
- **Run locally:** [Quickstart](https://apertus-ai.org/docs/quickstart/) and [local inference options](#local-inference-and-serving).
- **Build an application:** [Hosted APIs](#hosted-apis-and-cloud-deployment), [integration examples](#applications-and-integrations), and [fine-tuning recipes](https://github.com/swiss-ai/apertus-finetuning-recipes).
- **Study or reproduce:** [Technical report](https://arxiv.org/abs/2509.14233), [training code](https://github.com/swiss-ai/pretrain-code), and [data reconstruction](https://github.com/swiss-ai/pretrain-data).

## Official sites and documentation

- [Apertus website](https://www.apertus-ai.org/) — Project home.
- [About and roadmap](https://apertus-ai.org/pages/about/) — Mission, background, and planned development.
- [Swiss AI Initiative](https://www.swiss-ai.org/) — Parent initiative; [ETH AI Center](https://ai.ethz.ch/), [EPFL AI Center](https://ai.epfl.ch/), and [CSCS](https://www.cscs.ch/) are the institutional homes.
- [Documentation hub](https://apertus-ai.org/pages/documentation/) — Downloads, technical resources, and policy documents.
- [Technical overview](https://apertus-ai.org/docs/overview/) and [FAQ](https://apertus-ai.org/docs/faq/) — Orientation and common questions.
- [Provider directory](https://apertus-ai.org/pages/get-started/) and [community showcase](https://apertus-ai.org/pages/get-showcase/) — Officially listed services and applications.
- [Research library](https://apertus-ai.org/pages/research/) and [Zotero group](https://www.zotero.org/groups/6385576/apertus) — Papers and supporting literature.
- [GitHub organization](https://github.com/swiss-ai) — Authoritative code index; includes other Swiss AI research alongside Apertus.
- [Hugging Face organization](https://huggingface.co/swiss-ai) — Authoritative models, datasets, collections, and demos.
- [News](https://apertus-ai.org/news/) and [newsletter](https://apertus-ai.org/subscribe/) — Updates, including [Apertus 1.5](https://apertus-ai.org/articles/2026-07-apertus-1-5/) and the [September 2026 ecosystem review](https://apertus-ai.org/articles/2026-09-apertus-1-5-ga/).
- [Apertus Charter](https://apertus-ai.org/pages/charter/) — Published behavioral principles.
- [Legal documentation](https://github.com/swiss-ai/apertus-legal) — Versioned licenses, usage and privacy policies, EU public summaries, and codes of practice; companion [licensing](https://apertus-ai.org/docs/tech/licensing/) and [safety](https://apertus-ai.org/docs/tech/safety/) guides.
- [Website source](https://github.com/swiss-ai/www-apertus) — Contribute fixes to the website and documentation.

## Official models

Use each model card for capabilities, access conditions, and installation instructions. Base checkpoints are intended for completion or further training; Instruct checkpoints are adapted for conversation.

| Family                   | Official weights                                                                                                                                                                                         | Purpose                                                                                               |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| **Apertus 1.5**          | [8B](https://huggingface.co/swiss-ai/Apertus-v1.5-8B) · [70B](https://huggingface.co/swiss-ai/Apertus-v1.5-70B) · [collection](https://huggingface.co/collections/swiss-ai/apertus-v15)                  | Text and image input, experimental audio input, optional thinking; up to 262,144 tokens. Text output. |
| **1.1 Mini — base**      | [0.5B](https://huggingface.co/swiss-ai/Apertus-v1.1-0.5B) · [1.5B](https://huggingface.co/swiss-ai/Apertus-v1.1-1.5B) · [4B](https://huggingface.co/swiss-ai/Apertus-v1.1-4B)                            | Smaller distilled text models.                                                                        |
| **1.1 Mini — Instruct**  | [0.5B](https://huggingface.co/swiss-ai/Apertus-v1.1-0.5B-Instruct) · [1.5B](https://huggingface.co/swiss-ai/Apertus-v1.1-1.5B-Instruct) · [4B](https://huggingface.co/swiss-ai/Apertus-v1.1-4B-Instruct) | Compact conversational models.                                                                        |
| **1.1 Mini — quantized** | [Collection](https://huggingface.co/collections/swiss-ai/apertus-mini) · [vLLM NVFP4A16 1.5B](https://huggingface.co/swiss-ai/Apertus-v1.1-1.5B-Instruct-vLLM-NVFP4A16)                                  | Official MLX INT3/INT4/INT6 variants at all three sizes, plus the vLLM build.                         |
| **1.0 — base**           | [8B](https://huggingface.co/swiss-ai/Apertus-8B-2509) · [70B](https://huggingface.co/swiss-ai/Apertus-70B-2509)                                                                                          | Original September 2025 text checkpoints.                                                             |
| **1.0 — Instruct**       | [8B](https://huggingface.co/swiss-ai/Apertus-8B-Instruct-2509) · [70B](https://huggingface.co/swiss-ai/Apertus-70B-Instruct-2509) · [collection](https://huggingface.co/collections/swiss-ai/apertus-v1) | Original chat models; 65,536-token context.                                                           |

Supporting models: [pretraining toxicity classifier](https://huggingface.co/swiss-ai/apertus-pretrain-toxicity) and [WavTokenizer checkpoint](https://huggingface.co/swiss-ai/wavtokenizer-large-unify-40token).

**Version matters:** the 1.5 cards currently require acceptance of access conditions and document custom Transformers/vLLM builds. They also state that tool calling is unsupported in thinking mode. Follow the authored [1.5 usage instructions](https://huggingface.co/swiss-ai/Apertus-v1.5-8B#how-to-use); a runtime supporting 1.0 does not automatically support 1.5.

## Official code and training infrastructure

### Training and data preparation

- [pretrain-code](https://github.com/swiss-ai/pretrain-code) and [Megatron-LM](https://github.com/swiss-ai/Megatron-LM) — Apertus pretraining entry point and underlying distributed training fork.
- [pretrain-data](https://github.com/swiss-ai/pretrain-data) — Reconstruct the pretraining corpus from its sources.
- [posttraining](https://github.com/swiss-ai/posttraining) — Supervised fine-tuning and alignment experiments.
- [posttraining-data](https://github.com/swiss-ai/posttraining-data) — Download, standardize, filter, decontaminate, and mix post-training data.
- [apertus-finetuning-recipes](https://github.com/swiss-ai/apertus-finetuning-recipes) — Full-parameter and LoRA recipes using Transformers, TRL, and Accelerate; [walkthrough](https://apertus-ai.org/docs/tech/fine-tuning/) targets the original 8B/70B models.
- [multimodal-data](https://github.com/swiss-ai/multimodal-data) — Apertus 1.5 image/audio preparation, including a [dataset inventory](https://github.com/swiss-ai/multimodal-data/blob/main/datasets/DATASETS.md).
- [robots-txt-compliance](https://github.com/swiss-ai/robots-txt-compliance) — Web-data filtering and URL-checking tooling; [research site](https://data-compliance.github.io/).
- [llm-pretrain-data-toxicity-removal](https://github.com/swiss-ai/llm-pretrain-data-toxicity-removal) — Pretraining toxicity filtering.
- [pretraining-safety-annotation](https://github.com/swiss-ai/pretraining-safety-annotation) — Charter-guided data annotation pipeline.
- [audio-preprocessing](https://github.com/swiss-ai/audio-preprocessing) and [data-PDF-pipeline](https://github.com/swiss-ai/data-PDF-pipeline) — Speech processing and PDF corpus extraction tools.
- [Swiss-AI-Romansh-Scripts](https://github.com/swiss-ai/Swiss-AI-Romansh-Scripts) — Romansh corpus preparation for Apertus v1.
- [qat-suite](https://github.com/swiss-ai/qat-suite) — Distillation and quantization-aware training associated with Apertus Mini.

### Tokenization, conversion, and deployment

- [apertus-format](https://github.com/swiss-ai/apertus-format) — Chat-format library, [specification](https://github.com/swiss-ai/apertus-format/blob/main/docs/format.md), and examples.
- [apertus-omni-tokenizer](https://github.com/swiss-ai/apertus-omni-tokenizer) — Canonical 1.5 tokenizer construction and chat templates.
- [apertus-audio-tokenizer](https://github.com/swiss-ai/apertus-audio-tokenizer) and [WavTokenizer](https://github.com/swiss-ai/WavTokenizer) — Audio-tokenizer wrapper and underlying fork.
- [hfconverter](https://github.com/swiss-ai/hfconverter) — Megatron-to-Hugging-Face checkpoint conversion and consistency checks.
- [model-launch](https://github.com/swiss-ai/model-launch) — Alps model-launch CLI and official [1.5 inference Dockerfile](https://github.com/swiss-ai/model-launch/blob/main/images/vllm_apertus_1.5_release/Dockerfile).
- [serving-api](https://github.com/swiss-ai/serving-api) and [llm-proxy](https://github.com/swiss-ai/llm-proxy) — Swiss AI serving frontend, API proxy, and access-control infrastructure.
- [OpenTela](https://github.com/swiss-ai/OpenTela) — Distributed compute orchestration used by Swiss AI serving; [upstream project](https://github.com/eth-easl/OpenTela).
- [Transformers fork](https://github.com/swiss-ai/transformers), [vLLM fork](https://github.com/swiss-ai/vllm), and [vLLM integration work](https://github.com/swiss-ai/vllm-apertus-integration) — Swiss AI implementations; use the revisions pinned in model cards.
- [SGLang](https://github.com/swiss-ai/sglang), [sglang-apertus](https://github.com/swiss-ai/sglang-apertus), and [Scratchpad](https://github.com/swiss-ai/Scratchpad) — Serving and integration work; 1.5 support is still under development in the [guide](https://apertus-ai.org/docs/guides/sglang/).
- [gh200-wheels](https://github.com/swiss-ai/gh200-wheels) — Wheels and images for NVIDIA Grace Hopper hardware.
- [model-compatibility-suite](https://github.com/swiss-ai/model-compatibility-suite) — Endpoint conformance and capability checks.
- [data-indexing](https://github.com/swiss-ai/data-indexing) and [dataset-browser](https://github.com/swiss-ai/dataset-browser) — Corpus search and local data inspection; infrastructure access may be required.

### Research projects

- [apertus-probes](https://github.com/swiss-ai/apertus-probes) — Hallucination probes and activation analysis.
- [apertus-translate](https://github.com/swiss-ai/apertus-translate) — Translation experiments and human-evaluation annotations.
- [vocab-reduction](https://github.com/swiss-ai/vocab-reduction) — Vocabulary-size optimization for training and inference.
- [prune-apertus-lm-head](https://github.com/swiss-ai/prune-apertus-lm-head) — 1.5 output-head conversion while retaining multimodal input token IDs.
- [Apertus RAG evaluation](https://github.com/swiss-ai/ml4science-apertus-rag-evaluation) — Research comparing retrieval, chunking, and reranking strategies.
- [apertus-speculative-decoding](https://github.com/swiss-ai/apertus-speculative-decoding) — Reproducible 1.5 serving-performance study.
- [apertus-tokenizer-development](https://github.com/swiss-ai/apertus-tokenizer-development) — Preliminary next-generation tokenizer research; not a released Apertus 2 model.

## Datasets and transparency

[All Swiss AI datasets](https://huggingface.co/swiss-ai/datasets) is the live catalog. Dataset licenses and access conditions vary; model licensing does not replace them.

- [Data transparency archive](https://github.com/swiss-ai/apertus-data-transparency) — Versioned dataset and release documentation.
- **Web filtering:** [FineWeb tags](https://huggingface.co/datasets/swiss-ai/fineweb-compliant-tag), [FineWeb-2 tags](https://huggingface.co/datasets/swiss-ai/fineweb-2-compliant-tag), and [FineWeb-Edu tags](https://huggingface.co/datasets/swiss-ai/fineweb-edu-compliant-tag).
- **Robots.txt artifacts:** [English blocked domains](https://huggingface.co/datasets/swiss-ai/robots-txt-blocked-domains-english), [multilingual blocked domains](https://huggingface.co/datasets/swiss-ai/robots-txt-blocked-domains-multilingual), and [compressed files](https://huggingface.co/datasets/swiss-ai/fineweb-robots-txt-files-compressed).
- **Swiss language corpora:** [Swiss pretraining](https://huggingface.co/datasets/swiss-ai/apertus-pretrain-swiss), [Romansh pretraining](https://huggingface.co/datasets/swiss-ai/apertus-pretrain-romansh), and [Romansh post-training](https://huggingface.co/datasets/swiss-ai/apertus-posttrain-romansh).
- **Text pretraining research:** [processed Project Gutenberg](https://huggingface.co/datasets/swiss-ai/project_gutenberg_preprocessed) and [poison/canary data](https://huggingface.co/datasets/swiss-ai/apertus-pretrain-poisonandcanaries).
- **Post-training:** [SFT mixture](https://huggingface.co/datasets/swiss-ai/apertus-sft-mixture), [Africa SFT](https://huggingface.co/datasets/swiss-ai/africa-sft), [Africa preferences](https://huggingface.co/datasets/swiss-ai/africa-preferences), and [1.5 preference data](https://huggingface.co/datasets/swiss-ai/Apertus_v1.5_Preference_Data).
- **Instruction following:** [verified SFT](https://huggingface.co/datasets/swiss-ai/if-sft-verified-singleturn-all), [RL prompts](https://huggingface.co/datasets/swiss-ai/if-rl-singleturn-prompts), and [hard RL prompts](https://huggingface.co/datasets/swiss-ai/if-rl-singleturn-hard-prompts).
- **Multimodal source collections:** [NASA](https://huggingface.co/datasets/swiss-ai/nasa), [Our World in Data](https://huggingface.co/datasets/swiss-ai/owid), [Smithsonian](https://huggingface.co/datasets/swiss-ai/smithsonian), and [swisstopo](https://huggingface.co/datasets/swiss-ai/swisstopo).
- **Evaluation datasets:** [mLogiQA](https://huggingface.co/datasets/swiss-ai/mlogiqa), [MathQA](https://huggingface.co/datasets/swiss-ai/math_qa), [BLEnD sample](https://huggingface.co/datasets/swiss-ai/blend-sample), and [HalluLens](https://huggingface.co/datasets/swiss-ai/hallulens).
- **Safety evaluation artifacts:** [HarmBench](https://huggingface.co/datasets/swiss-ai/harmbench), [copyright classifier hashes](https://huggingface.co/datasets/swiss-ai/harmbench_copyright_classifier_hashes), [RealToxicityPrompts](https://huggingface.co/datasets/swiss-ai/realtoxicityprompts), and [PolygloToxicityPrompts](https://huggingface.co/datasets/swiss-ai/polyglotoxicityprompts).

## Research and evaluation

### Papers and technical sources

- [Apertus technical report](https://arxiv.org/abs/2509.14233) — Original architecture, training, data, and evaluations; [report repository](https://github.com/swiss-ai/apertus-tech-report).
- [Apertus Mini: distillation and quantization](https://arxiv.org/abs/2605.29128) — Smaller-model family and compression methods.
- [Training Apertus on Alps](https://arxiv.org/abs/2604.12973) — HPC engineering and distributed-training lessons.
- [Web crawling opt-outs](https://arxiv.org/abs/2504.06219) — Measuring the effect of respecting data-source exclusions.
- [Positional fragility and memorization](https://arxiv.org/abs/2505.13171) — Memorization analysis; [Apertus reproduction code](https://github.com/swiss-ai/apertus-memorization).
- [xIELU activation](https://arxiv.org/abs/2411.13010) and [AdEMAMix optimizer](https://arxiv.org/abs/2409.03137) — Core architectural and optimization ingredients.
- [INCLUDE](https://arxiv.org/abs/2411.19799) and [Global MMLU](https://arxiv.org/abs/2412.03304) — Multilingual evaluation references.
- [Parity-aware BPE](https://arxiv.org/abs/2508.04796) — Cross-language tokenization research; [code](https://github.com/swiss-ai/parity-aware-bpe).
- [Full research bibliography](https://apertus-ai.org/pages/research/) — Additional work on data, optimization, safety, and serving. The page still lists the 1.5 technical report as forthcoming at the research date.

### Evaluation tools and results

- [Official evaluation guide](https://apertus-ai.org/docs/tech/evaluation/) — Benchmark entry point.
- [evals](https://github.com/swiss-ai/evals) and [evals-post-train](https://github.com/swiss-ai/evals-post-train) — Evaluation launchers and 1.5 post-training benchmark pipeline.
- [lm-evaluation-harness](https://github.com/swiss-ai/lm-evaluation-harness), [lighteval](https://github.com/swiss-ai/lighteval), and [MLLM-eval-suite](https://github.com/swiss-ai/MLLM-eval-suite) — Swiss AI evaluation forks and multimodal orchestration.
- [Evaluation dashboard source](https://github.com/swiss-ai/apertus-eval-dashboard) — Visualize results from Weights & Biases.
- [Charter alignment benchmark](https://github.com/swiss-ai/swiss-ai-charter-alignment-benchmark) — Research scaffold for measuring adherence to charter articles.
- [SwissLegalEvals](https://github.com/JoelNiklaus/SwissLegalEvals) — Independent Swiss legal benchmarks and [2026 Apertus comparison](https://github.com/JoelNiklaus/SwissLegalEvals/blob/main/blog/swiss-legal-evals-2026.md).
- [DS-NLP Lab: Apertus 1.5 8B evaluation](https://blog.nlp-lab.ai/2026/07/29/Apertus15Bench.html) — Independent write-up; [earlier 8B result files](https://github.com/unisg-ics-dsnlp/Apertus8B-Instruct-Benchmark-Results).
- [GuideLLM](https://vllm-project.github.io/guidellm/main/) — Serving-load benchmarking tool used in the official ecosystem review.

## Local inference and serving

| Tool                     | Apertus resource                                                                                                                                                                                | Notes                                                                                                               |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Transformers             | [Official guide](https://apertus-ai.org/docs/guides/transformers/) · [upstream model docs](https://huggingface.co/docs/transformers/model_doc/apertus)                                          | Python model loading; use the 1.5 card's pinned fork for multimodal support.                                        |
| vLLM                     | [Official guide](https://apertus-ai.org/docs/guides/vllm/) · [1.5 model card](https://huggingface.co/swiss-ai/Apertus-v1.5-70B#how-to-use)                                                      | GPU serving; version-specific parsers and containers.                                                               |
| SGLang                   | [Official guide](https://apertus-ai.org/docs/guides/sglang/)                                                                                                                                    | Original-model examples; 1.5 integration is work in progress.                                                       |
| llama.cpp                | [Upstream](https://github.com/ggml-org/llama.cpp) · [experimental 1.5 branch](https://github.com/MichelRosselli/llama.cpp/tree/model/apertus-v1.5)                                              | Follow the [maintainer's discussion](https://huggingface.co/swiss-ai/Apertus-v1.5-8B/discussions/6) for 1.5 status. |
| Ollama                   | [Official guide](https://apertus-ai.org/docs/user/ollama/) · [v1 community package](https://ollama.com/MichelRosselli/apertus) · [Mini package](https://ollama.com/MichelRosselli/apertus-v1.1) | Community-maintained model packages.                                                                                |
| LM Studio                | [Official guide](https://apertus-ai.org/docs/user/lmstudio/)                                                                                                                                    | Desktop UI for compatible local model builds.                                                                       |
| Llamafile                | [Official guide](https://apertus-ai.org/docs/user/llamafile/)                                                                                                                                   | Package compatible GGUF models as executables.                                                                      |
| Open WebUI               | [Official guide](https://apertus-ai.org/docs/user/openwebui/)                                                                                                                                   | Chat frontend for local or hosted inference.                                                                        |
| MLX                      | [Official Mini collection](https://huggingface.co/collections/swiss-ai/apertus-mini) · [mlx-community 8B BF16](https://huggingface.co/mlx-community/Apertus-8B-Instruct-2509-bf16)              | Apple Silicon builds; check each card's requirements.                                                               |
| Transformers.js / WebGPU | [Mini demo and source files](https://huggingface.co/spaces/swiss-ai/apertus-mini-webgpu)                                                                                                        | Browser-local inference using converted Mini weights.                                                               |

## Community quantizations and derivatives

### Alternative formats

- **Unsloth GGUF:** [8B](https://huggingface.co/unsloth/Apertus-8B-Instruct-2509-GGUF) and [70B](https://huggingface.co/unsloth/Apertus-70B-Instruct-2509-GGUF) — Original Instruct models; also [8B bitsandbytes 4-bit](https://huggingface.co/unsloth/Apertus-8B-Instruct-2509-unsloth-bnb-4bit).
- **Bartowski GGUF:** [8B](https://huggingface.co/bartowski/swiss-ai_Apertus-8B-Instruct-2509-GGUF) and [70B](https://huggingface.co/bartowski/swiss-ai_Apertus-70B-Instruct-2509-GGUF) — Alternative original-model quantizations.
- **redponike GGUF:** [8B](https://huggingface.co/redponike/Apertus-8B-Instruct-2509-GGUF) and [70B](https://huggingface.co/redponike/Apertus-70B-Instruct-2509-GGUF) — Additional builds linked by the official Ollama guide.
- **Red Hat AI FP8:** [8B Instruct](https://huggingface.co/RedHatAI/Apertus-8B-Instruct-2509-FP8-dynamic) — Dynamic FP8 conversion for compatible GPU serving.
- **OnPrem AI 1.5:** [8B FP8](https://huggingface.co/onprem-ai/Apertus-v1.5-8B-FP8), [70B FP8](https://huggingface.co/onprem-ai/Apertus-v1.5-70B-FP8), and [70B NVFP4](https://huggingface.co/onprem-ai/Apertus-v1.5-70B-NVFP4) — Quantized checkpoints with a [temporary vLLM build](https://github.com/onprem-ai/vllm-apertus-1p5).
- **1.5 text-only GGUF:** [Andreas Martin Q8_0](https://huggingface.co/andreasmartin/apertus-v1.5-8b-text-Q8_0-GGUF) and [Colby Q4_K_M](https://huggingface.co/Colby/apertus-v1.5-8b-text-Q4_K_M-GGUF) — 8B conversions that omit multimodal capabilities.
- **1.5 text-only MLX:** [m1rkocasu 4-bit DWQ](https://huggingface.co/m1rkocasu/Apertus-v1.5-8B-text-MLX-4bit-DWQ) — Community Apple Silicon conversion.
- **Mini ONNX:** [0.5B](https://huggingface.co/onnx-community/Apertus-v1.1-0.5B-Instruct-QAD-INT4-ONNX), [1.5B](https://huggingface.co/onnx-community/Apertus-v1.1-1.5B-Instruct-QAD-INT4-ONNX), and [4B](https://huggingface.co/onnx-community/Apertus-v1.1-4B-Instruct-QAD-INT4-ONNX) — INT4 browser/runtime conversions.

### Fine-tunes and adaptations

- [Apertus SEA-LION v4 8B](https://huggingface.co/aisingapore/Apertus-SEA-LION-v4-8B-IT) — AI Singapore's Southeast Asian language adaptation; [GGUF](https://huggingface.co/aisingapore/Apertus-SEA-LION-v4-8B-IT-GGUF) and [release collection](https://huggingface.co/collections/aisingapore/sea-lion-v4).
- [Apertus EstLLM](https://huggingface.co/tartuNLP/Apertus-EstLLM-8B-Instruct-0326) — TartuNLP's Estonian adaptation; [base checkpoint](https://huggingface.co/tartuNLP/Apertus-EstLLM-8B-1125) and [paper](https://arxiv.org/abs/2603.02041).
- **Apertus MeditronFO:** [8B](https://huggingface.co/EPFLiGHT/Apertus-8B-MeditronFO) and [70B](https://huggingface.co/EPFLiGHT/Apertus-70B-MeditronFO) — Medical-domain research models; [training pipeline](https://github.com/EPFLiGHT/FullyOpenMeditron) and [paper](https://arxiv.org/abs/2605.16215).
- [Greek Apertus](https://github.com/eellak/greek-apertus) — Ongoing Greek continued-pretraining and tokenizer project using GlossAPI data; tooling, not a finished model release.

## Hosted APIs and cloud deployment

### Managed access

Entries were found through the official [directory](https://apertus-ai.org/pages/get-started/), [September 2026 ecosystem review](https://apertus-ai.org/articles/2026-09-apertus-1-5-ga/), and providers' own catalogs. Check providers for available versions, modalities, context limits, and pricing.

| Provider                         | Resource                                                                                                                                                                                                                        | Access                                           |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| Swisscom                         | [Apertus 1.5 70B docs](https://docs.cloud.swisscom.ch/guide/cloud-services/aip/models/apertus-1_5_70B)                                                                                                                          | Swiss AI Platform API.                           |
| Infomaniak                       | [AI Services catalog](https://www.infomaniak.com/en/hosting/ai-services/open-source-models)                                                                                                                                     | Swiss-hosted inference API.                      |
| PHOENIQS / KVANT                 | [Active models](https://documentation.kvant.cloud/maas/active-models/)                                                                                                                                                          | Enterprise model service.                        |
| Safe Swiss Cloud                 | [Private AI](https://safeswisscloud.com/en/private-ai/)                                                                                                                                                                         | Managed private AI offering.                     |
| stepping stone                   | [AI on demand](https://www.stepping-stone.ch/en/products/artificial-intelligence/ai-on-demand-powered-by-swiss-ai-initiative) · [deployment notes](https://wiki.stoney-cloud.com/wiki/AI_on_demand:_apertus-ai/Apertus-v1.5-8B) | Managed 8B service.                              |
| Public AI                        | [Developer platform](https://platform.publicai.co/) · [API reference](https://platform.publicai.co/api)                                                                                                                         | Chat and API access.                             |
| Hugging Face Inference Providers | [PublicAI integration](https://huggingface.co/docs/inference-providers/providers/publicai)                                                                                                                                      | Apertus through Hugging Face's inference router. |
| Featherless                      | [Apertus catalog](https://featherless.ai/models?families=apertus) · [deployment guide](https://apertus-ai.org/docs/deploy/featherless/)                                                                                         | Serverless inference.                            |
| Regolo                           | [Model catalog](https://regolo.ai/models/)                                                                                                                                                                                      | Additional provider listing `apertus-70b`.       |
| OnPrem AI                        | [Model catalog](https://www.onprem.ai/en/ai-llm-models/)                                                                                                                                                                        | Local enterprise deployment and support.         |

### Deploy on your own cloud infrastructure

- [Exoscale](https://apertus-ai.org/docs/deploy/exoscale/) — Official guide and [dedicated inference offering](https://www.exoscale.com/ai-cloud-infrastructure/dedicated-inference/).
- [AWS SageMaker AI](https://apertus-ai.org/docs/deploy/sagemaker/) — Official guide; [AWS walkthrough](https://aws.amazon.com/blogs/alps/switzerlands-open-source-apertus-llms-now-available-on-amazon-sagemaker-ai/).
- [Microsoft Azure](https://apertus-ai.org/docs/deploy/azure/) — Official guide; [Azure Samples quickstart](https://github.com/Azure-Samples/swiss-llm-quickstart).
- [Google Vertex AI](https://apertus-ai.org/docs/deploy/vertex/) — Official cloud deployment guide.
- [Community SageMaker Terraform](https://github.com/hueper/apertus-70b-infra) — Original 70B Instruct deployment with scheduled endpoint lifecycle management.

## Applications and integrations

### Chat, translation, and data tools

- [Public AI chat](https://publicai.co/) — Hosted Apertus chat interface.
- [Lumo by Proton](https://proton.me/blog/lumo-apertus-partnership) — Apertus integration in Proton's assistant.
- [Euria](https://www.infomaniak.com/en/euria) — Infomaniak assistant with Apertus selection; [setup and kSuite integration](https://www.infomaniak.com/en/support/faq/2924/discover-euria-and-the-apertus-model).
- [Helvetra](https://helvetra.ch/) — Swiss-language translation application; [backend source](https://github.com/Helvetra/backend).
- [AI Potluck](https://www.aipotluck.org/chat) — Chat interface exposing aspects of the inference process.
- [Open Data Editor](https://opendataeditor.okfn.org/) — Tabular-data tool with an Apertus Mini component; [source](https://github.com/okfn/opendataeditor).
- [ZüriCityGPT OSS](https://oss.zuericitygpt.ch/) — Liip's municipal-law RAG demonstration.

### SDKs, automation, and application examples

- [LiteLLM PublicAI provider](https://docs.litellm.ai/docs/providers/publicai) — Documented Apertus routes for the Python SDK and proxy.
- [Laravel Apertus](https://github.com/mmorand/laravel-apertus) — Community PHP/Laravel client with streaming and model listing.
- [ApertusSharp](https://github.com/bhrnjica/ApertusSharp) — Community .NET client built on Microsoft.Extensions.AI, with Semantic Kernel integration.
- [Apertus n8n starter kit](https://github.com/aai-institute/apertus-n8n) — Python/curl examples, structured extraction, three workflows, and a local Ollama path.
- [Apertus AI workshop](https://github.com/blancsw/apertus-ai-workshop) — Infomaniak-backed RAG combining Apertus generation with separate embedding and reranking models.
- [Emilie](https://github.com/veronica-builds/emilie) — Community legal-document assistant with Apertus support and MCP-based case-law lookup.
- [CertusAI](https://github.com/saurluca/CertusAI) — Swiss AI Weeks legal-assistant project using Apertus.
- [HEVS pretraining-data indexing](https://github.com/Reliable-Information-Lab-HEVS/apertus-pretraining-data-indexing) — Community detokenization, Elasticsearch indexing, and corpus inspection tools.

## Community and contributing

- **Discuss models:** official [8B](https://huggingface.co/swiss-ai/Apertus-v1.5-8B/discussions) and [70B](https://huggingface.co/swiss-ai/Apertus-v1.5-70B/discussions) Hugging Face discussions.
- **Contact the team:** [official contact page](https://apertus-ai.org/contact/); submit projects for the showcase through these channels.
- **Meet the community:** [Discord](https://discord.gg/t9TY8FsJd), linked by the official ecosystem post; [Swiss AI events](https://www.swiss-ai.org/events) and [Swiss AI Weeks](https://ai-weeks.ch/).
- **Follow updates:** [Mastodon](https://fosstodon.org/@apertus), [LinkedIn](https://www.linkedin.com/company/apertus/), [X](https://x.com/apertusllm), and [Bluesky](https://bsky.app/profile/did:plc:ytwqtr3ykzq6nzr7kg2465ca).

Contributions are welcome. Read [CONTRIBUTING.md](CONTRIBUTING.md), then suggest a resource with a primary source, a short description, and the relevant Apertus version. This list is released under [CC0 1.0](LICENSE); linked projects retain their own licenses.

For maintenance scripts and development commands, see the [helper documentation](https://github.com/rnckp/awesome-apertus/blob/main/src/README.md).
