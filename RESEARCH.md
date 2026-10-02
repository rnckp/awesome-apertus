# Research notes

Research date: **September 26, 2026**.

## Scope and method

Research combined web searches, the official website and its outbound links, both pages of the public Swiss AI GitHub repository catalog, project READMEs, Swiss AI Hugging Face model/dataset catalogs, model cards, and community repository/model searches.

Official model families are listed individually; the Mini collection covers all official MLX quantization combinations. Live GitHub and Hugging Face indexes provide discovery paths for new artifacts. Unrelated Swiss AI projects, generic forks without a clear Apertus use, duplicate mirrors, and similarly named cinema, VR, and commercial products were excluded. Community coverage is selective, not a claim to enumerate every repository or fine-tune on the internet.

Descriptions rely on primary sources. Inclusion confirms a documented connection to Apertus, not an independent quality, security, privacy, or performance endorsement. Software was not installed, model weights were not downloaded, and paid services were not exercised.

## Main source trail

| Area | Primary sources | Use |
| --- | --- | --- |
| Identity | [Home](https://www.apertus-ai.org/), [documentation](https://apertus-ai.org/pages/documentation/), [contact](https://apertus-ai.org/contact/) | Establish official resources and ownership. |
| Releases | [1.5 announcement](https://apertus-ai.org/articles/2026-07-apertus-1-5/), [1.5 card](https://huggingface.co/swiss-ai/Apertus-v1.5-8B), [Mini](https://huggingface.co/collections/swiss-ai/apertus-mini), [v1](https://huggingface.co/collections/swiss-ai/apertus-v1) | Separate generations and capabilities. |
| Code and data | [Repositories](https://github.com/swiss-ai), [datasets](https://huggingface.co/swiss-ai/datasets), [multimodal inventory](https://github.com/swiss-ai/multimodal-data/blob/main/datasets/DATASETS.md), [transparency archive](https://github.com/swiss-ai/apertus-data-transparency) | Identify reproducibility artifacts and inspect READMEs. |
| Providers | [Directory](https://apertus-ai.org/pages/get-started/), [ecosystem review](https://apertus-ai.org/articles/2026-09-apertus-1-5-ga/) | Discover services, then link provider documentation. |
| Applications | [Showcase](https://apertus-ai.org/pages/get-showcase/), [Proton announcement](https://proton.me/blog/lumo-apertus-partnership), individual repositories | Verify applications and integrations. |
| Runtimes | [SGLang guide](https://apertus-ai.org/docs/guides/sglang/), [Ollama guide](https://apertus-ai.org/docs/user/ollama/), [llama.cpp discussion](https://huggingface.co/swiss-ai/Apertus-v1.5-8B/discussions/6), [OnPrem build](https://github.com/onprem-ai/vllm-apertus-1p5) | Distinguish released, custom-build, and experimental support. |
| SDKs | [LiteLLM](https://docs.litellm.ai/docs/providers/publicai), [Laravel](https://github.com/mmorand/laravel-apertus), [ApertusSharp](https://github.com/bhrnjica/ApertusSharp), [n8n](https://github.com/aai-institute/apertus-n8n) | Require Apertus-specific examples or documented support. |
| Derivatives | [SEA-LION](https://huggingface.co/aisingapore/Apertus-SEA-LION-v4-8B-IT), [EstLLM](https://huggingface.co/tartuNLP/Apertus-EstLLM-8B-Instruct-0326), [MeditronFO](https://huggingface.co/EPFLiGHT/Apertus-8B-MeditronFO), [Greek Apertus](https://github.com/eellak/greek-apertus) | Verify lineage and release status. |
| Research | [Bibliography](https://apertus-ai.org/pages/research/), linked papers, [SwissLegalEvals](https://github.com/JoelNiklaus/SwissLegalEvals) | Prioritize technical sources and reproducible evaluation. |

## Important distinctions

- Authored 1.5 model cards prescribe custom runtime revisions. Hugging Face's generic generated “Use this model” snippets are insufficient evidence of upstream compatibility.
- Apertus 1.5 accepts multimodal input and produces text. Experimental audio input is not audio generation; text-only conversions omit the multimodal interface.
- Thinking-mode and tool-call compatibility depend on the exact model and serving build.
- The official research page still marks the 1.5 report as forthcoming. The linked 2025 report describes the original family.
- Open training resources include reconstruction scripts, source inventories, and filtering metadata. One unrestricted download containing the entire corpus is not implied.
- Provider catalogs do not guarantee every feature or the model's maximum context length is exposed. Prices and availability were intentionally omitted.
- Legal documentation is linked as published by the project, without independently certifying compliance.
- Gated model cards remain useful even when downloads require accepting terms. HTTP checks may also be blocked by login or bot protection.

## Maintenance

Review release pages and model cards first, then refresh providers, runtime support, community artifacts, and link status. Update the README's research date only after substantive review. Follow [the contribution guidelines](CONTRIBUTING.md).

## Verification results

### Targeted additions — October 2, 2026

Added three Andreas Martin resources suggested by the maintainer via LinkedIn: the [Hack Apertus SFT notebook](https://www.kaggle.com/code/andreasmartinch/sft-apertus-v1-5-8b-hack-apertus-template), [Apertus 1.5 8B text-only conversion](https://huggingface.co/andreasmartin/apertus-v1.5-8b-text), and [experimental Apertus collection](https://huggingface.co/collections/andreasmartin/apertus). The authored Hugging Face model card confirms standard Transformers 4.56+ support and gated access; the collection lists educational adaptations, embedding conversions, and a biomedical fine-tune. The notebook's purpose and Kaggle/CSCS testing are based on the author's supplied description because its contents were unavailable through web browsing.

The repository's link checker checked only these three URLs: all were reachable, with no likely broken or unresolved results. The resource counter reports 109 resource-bullet entries, an increase of three. `git diff --check` passed. No notebook or model was executed; the overall research date remains September 26.

### Full review — September 26, 2026

On the research date, 241 distinct external destinations were checked with HTTP GET requests, following redirects. Of these, 240 returned HTTP 200. [Safe Swiss Cloud](https://safeswisscloud.com/en/private-ai/) returned HTTP 403 to the automated checker; its content was independently accessible through web browsing and its Apertus listing was corroborated by the official provider directory.

Local file links and table-of-contents anchors passed validation. Markdown table structure and `git diff --check` also passed. HTTP success establishes reachability, not functional testing of the linked software, services, or individual external-page fragments.
