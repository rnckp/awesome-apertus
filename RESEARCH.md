# Research notes

Research date: **September 26, 2026**.

## Scope and method

Research combined web searches, the official website and its outbound links, both pages of the public Swiss AI GitHub repository catalog, project READMEs, Swiss AI Hugging Face model/dataset catalogs, model cards, and community repository/model searches.

Official model families are listed individually; the Mini collection covers all official MLX quantization combinations. Live GitHub and Hugging Face indexes provide discovery paths for new artifacts. Unrelated Swiss AI projects, generic forks without a clear Apertus use, duplicate mirrors, and similarly named cinema, VR, and commercial products were excluded. Community coverage is selective, not a claim to enumerate every repository or fine-tune on the internet.

Descriptions rely on primary sources. Inclusion confirms a documented connection to Apertus, not an independent quality, security, privacy, or performance endorsement. Software was not installed, model weights were not downloaded, and paid services were not exercised.

## Main source trail

| Area          | Primary sources                                                                                                                                                                                                                                                                      | Use                                                           |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------- |
| Identity      | [Home](https://www.apertus-ai.org/), [documentation](https://apertus-ai.org/pages/documentation/), [contact](https://apertus-ai.org/contact/)                                                                                                                                        | Establish official resources and ownership.                   |
| Releases      | [1.5 announcement](https://apertus-ai.org/articles/2026-07-apertus-1-5/), [1.5 card](https://huggingface.co/swiss-ai/Apertus-v1.5-8B), [Mini](https://huggingface.co/collections/swiss-ai/apertus-mini), [v1](https://huggingface.co/collections/swiss-ai/apertus-v1)                | Separate generations and capabilities.                        |
| Code and data | [Repositories](https://github.com/swiss-ai), [datasets](https://huggingface.co/swiss-ai/datasets), [multimodal inventory](https://github.com/swiss-ai/multimodal-data/blob/main/datasets/DATASETS.md), [transparency archive](https://github.com/swiss-ai/apertus-data-transparency) | Identify reproducibility artifacts and inspect READMEs.       |
| Providers     | [Directory](https://apertus-ai.org/pages/get-started/), [ecosystem review](https://apertus-ai.org/articles/2026-09-apertus-1-5-ga/)                                                                                                                                                  | Discover services, then link provider documentation.          |
| Applications  | [Showcase](https://apertus-ai.org/pages/get-showcase/), [Proton announcement](https://proton.me/blog/lumo-apertus-partnership), individual repositories                                                                                                                              | Verify applications and integrations.                         |
| Runtimes      | [SGLang guide](https://apertus-ai.org/docs/guides/sglang/), [Ollama guide](https://apertus-ai.org/docs/user/ollama/), [llama.cpp discussion](https://huggingface.co/swiss-ai/Apertus-v1.5-8B/discussions/6), [OnPrem build](https://github.com/onprem-ai/vllm-apertus-1p5)           | Distinguish released, custom-build, and experimental support. |
| SDKs          | [LiteLLM](https://docs.litellm.ai/docs/providers/publicai), [Laravel](https://github.com/mmorand/laravel-apertus), [ApertusSharp](https://github.com/bhrnjica/ApertusSharp), [n8n](https://github.com/aai-institute/apertus-n8n)                                                     | Require Apertus-specific examples or documented support.      |
| Derivatives   | [SEA-LION](https://huggingface.co/aisingapore/Apertus-SEA-LION-v4-8B-IT), [EstLLM](https://huggingface.co/tartuNLP/Apertus-EstLLM-8B-Instruct-0326), [MeditronFO](https://huggingface.co/EPFLiGHT/Apertus-8B-MeditronFO), [Greek Apertus](https://github.com/eellak/greek-apertus)   | Verify lineage and release status.                            |
| Research      | [Bibliography](https://apertus-ai.org/pages/research/), linked papers, [SwissLegalEvals](https://github.com/JoelNiklaus/SwissLegalEvals)                                                                                                                                             | Prioritize technical sources and reproducible evaluation.     |

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

### Full review — September 26, 2026

On the research date, 241 distinct external destinations were checked with HTTP GET requests, following redirects. Of these, 240 returned HTTP 200. [Safe Swiss Cloud](https://safeswisscloud.com/en/private-ai/) returned HTTP 403 to the automated checker; its content was independently accessible through web browsing and its Apertus listing was corroborated by the official provider directory.

Local file links and table-of-contents anchors passed validation. Markdown table structure and `git diff --check` also passed. HTTP success establishes reachability, not functional testing of the linked software, services, or individual external-page fragments.

### Hack Apertus review — October 9, 2026

Targeted review of the 25 repositories supplied by the maintainer during the ongoing Hack Apertus online event. This does not refresh the rest of the directory or advance its overall research date. Public GitHub API metadata, root READMEs, recursive file inventories and licence files were read for all 25; project READMEs/reports and selected implementation files were inspected where needed to establish substance and the Apertus connection. Selection is editorial, not hackathon judging or confirmation of an accepted submission.

Added 21 resource-bullet entries in a dedicated **Hack Apertus projects** section. A substantive README inside the track/project directory counts: Klartext and MergeProof retain template material at the root, but document implemented applications below it. Their directory links lead directly to those READMEs. Explicit offline/mock modes were not treated as real-model evidence, and authors' benchmark numbers were not copied into the directory.

| Repository | Code licence observed | Decision and evidence |
| ---------- | --------------------- | --------------------- |
| [Vipunen-2B](https://github.com/apn201/Vipunen-2B) | Apache-2.0 | Add: red-teaming pipeline, client, tests, neutral seeds and operator console. Original attack payloads are withheld. |
| [northbridge-apertus-rt](https://github.com/dl88jing/northbridge-apertus-rt) | MIT | Defer: useful harness scaffold, but its [status log](https://github.com/dl88jing/northbridge-apertus-rt/blob/main/docs/STATUS.md) records access/provider failures only, with no successful Apertus generation or behavioral findings. Reconsider after a real run. |
| [splitalign](https://github.com/sharonbasovich/splitalign) | Apache-2.0 | Add: cross-language alignment/scoring implementation, hosted Apertus backend, development artifacts and tests. |
| [Scary-Gate-Keeper](https://github.com/ratafani/Scary-Gate-Keeper) | Apache-2.0 | Add as Kampung Sambau: browser game and Apertus dialogue implementation. Author explicitly leaves Docker launch and aggregate live-model evaluation unverified. |
| [apertus-sovereign-operations-bridge](https://github.com/ambrosinistefan8-stack/apertus-sovereign-operations-bridge) | Apache-2.0 notice | Add: client, structured schema, control layer and dated live-evidence artifact. GitHub reports `NOASSERTION`; direct inspection found an explicit Apache-2.0 grant by reference, but not the bundled full licence text. Maintainer should replace the abbreviated file with the full text. |
| [openparldata-extract](https://github.com/hatif03/openparldata-extract) | Apache-2.0 | Defer: custom README describes a plan, but the [entry point](https://github.com/hatif03/openparldata-extract/blob/main/track_2a/src/opd_extract/__main__.py) only prints configuration and says the pipeline is not implemented. Report remains largely a template. |
| [gemeindesim](https://github.com/hatif03/gemeindesim) | Apache-2.0 | Add: municipal-policy agent simulation with backend, frontend, Apertus client and research artifacts. No independent validity as a policy forecast is established. |
| [sovereign-trade-copilot](https://github.com/quaner1234-cmd/sovereign-trade-copilot) | Apache-2.0 | Add: inquiry parser, source-grounded drafting, Apertus client and review controls; offline demonstration is separately labelled. |
| [apertus-gate](https://github.com/ondmindmanagement-hub/apertus-gate) | Apache-2.0 | Add: small implemented action-review service with an Apertus-specific prompt/client and normalization. It produces decision artifacts; it does not execute or enforce actions in external systems. |
| [loraclette](https://github.com/bdravec/loraclette) | Apache-2.0 | Add as experimental adaptation tooling: bottleneck adapters and position sweeps. Author tested a small random Apertus model only; real 8B weights and 4-bit loading remain untested. No trained adapter or quality improvement is implied. |
| [zusage](https://github.com/shi1720/zusage) | Apache-2.0 | Add: apprenticeship interview coach with backend, frontend, model client, evaluation materials and project documentation. |
| [apertus-evidence-ledger](https://github.com/sgagestudio/apertus-evidence-ledger) | Apache-2.0 | Add: SQLite retrieval, Apertus client, citation verifier, UI and synthetic evaluation artifacts. Matching quotes/hashes do not independently prove an answer's interpretation. |
| [apertus-qa](https://github.com/ventolabs-hq/apertus-qa) | Apache-2.0 | Add: Spanish statistical Q&A pipeline with local numeric lookup, query planning and separate stub/real-model artifacts. |
| [HackApertus / ClaimLens](https://github.com/Xa4-wi/HackApertus) | Apache-2.0 | Add: voting-booklet claim classification, retrieval, model client and quote/page verification. Source-relative labels do not establish real-world truth. |
| [SpanDiff-HackApertus](https://github.com/moscraciunxxx/SpanDiff-HackApertus) | Apache-2.0 | Add: hidden-state semantic-drift scorer with development predictions and ablations. Development correlations are not independently reproduced. |
| [velum](https://github.com/calderbuild/velum) | Apache-2.0 | Add: entity detection, court rule packs, deterministic anonymisation, review UI and benchmark artifacts. Missed identities remain possible; inclusion is not a privacy or legal-compliance certification. |
| [k-probe](https://github.com/iamhuman-cheolheelee/k-probe) | MIT | Add: Korean probes, MLX runner, heuristic scorer and saved responses. README retains an outdated sentence saying 1.5 will be rerun after release despite already reporting 1.5 results; rely on the explicit model/run artifacts, not that timeline sentence. |
| [cleardesk-apertus](https://github.com/m7mdd77/cleardesk-apertus) | Apache-2.0 | Add as a narrow demonstration: four synthetic IT procedures, local model client, exact-passage contract and container verification artifacts. No live institutional integration is claimed. |
| [ParlPDFeCH](https://github.com/jkovatsch/ParlPDFeCH) | Apache-2.0 | Defer: substantial early research, transparently documented negative results, but only stages 1–3 exist; `make run` is not ready, necessary input-generation scripts/references/adapters are absent, and the isolation gate has not passed. Not yet a reproducible parliamentary-affair converter. |
| [mergeproof-hack-apertus](https://github.com/williamleewilliam1-star/mergeproof-hack-apertus) | Apache-2.0, including nested project | Add: nested project README, GitHub evidence collection, Apertus synthesis, supporting-reference checks and local real-model compatibility artifact. |
| [apertus-redteam](https://github.com/devilking7x/apertus-redteam) | Apache-2.0 | Add: implemented seeded attack modules, model backends, tests and recorded runs. Heuristic flags require human review; README mixes 1.0 defaults with a 1.5 target, so descriptions avoid asserting one tested configuration for every module. |
| [hermes-apertus-email](https://github.com/ratchetcode/hermes-apertus-email) | Apache-2.0 | Defer: root/track READMEs remain hackathon templates and `src/` contains only `.gitkeep`; no application implementation found. |
| [referto-sovrano](https://github.com/nicholasbuenger/referto-sovrano) | MIT | Add as a synthetic clinical-note demonstration with a local Apertus client and deterministic fallback. Clinical validity and standards conformance were not established. Its application-level hostname guard permits LAN addresses and `.local` hosts and uses ordinary `fetch`; this is not proof of Swiss jurisdiction, complete network isolation or zero data egress. |
| [Alpenstroke](https://github.com/nikitojik/Alpenstroke) | Apache-2.0 | Add: workout parsing, deterministic metrics, planning, model client and evaluation/deployment artifacts. Training recommendations and reported results were not independently validated. |
| [Klartext](https://github.com/LeFlegm/Klartext/tree/main/track_2b) | Apache-2.0 | Add: substantive track README, letter extraction/verification, triage UI and saved synthetic development runs despite unchanged root template. Blind-set validation and some submission deliverables remain pending. |

Licence observations concern code. Some projects separately license documentation under CC-BY-4.0 and datasets under CDLA-Permissive-2.0 or upstream terms; repository inclusion does not relicense model weights, imported data or assets. Software was not installed or executed, model inference was not called, demos were not exercised and benchmark, deployment, residency and security claims were not independently verified.

Verification: the existing link helper checked the new README section's 22 distinct external destinations (21 project links plus the event site). Initial result: 17 reachable, no 404/410, five HTTP 504 responses; one targeted retry made all five reachable, leaving **22/22 reachable**. GitHub API reads independently succeeded for all 25 candidate repositories. README contents anchors, local file links and the 21-entry section count passed validation; the source-count helper reports 131 resource-bullet entries overall (110 existing plus 21 new). `git diff --check` passed. This was a targeted link check, not a new full-directory audit.

### Additional Hack Apertus discovery — October 9, 2026

Follow-up GitHub discovery searched `"Hack Apertus"`, `"Hack Apertus" in:readme`, `hackapertus in:name,description,readme`, and Apertus repositories created from October 1, 2026 onward. Results were compared with the original 25 candidates. This is selective discovery, not a complete submission catalog: indexing can omit repositories, and some results are templates, challenge materials, duplicates or unrelated projects.

At the maintainer's request, added these eight projects to the existing hackathon section after reading project documentation, file inventories, licence texts and selected implementation files. All eight bundle the Apache-2.0 code licence; Folio's full text follows its initial notice, correcting the earlier chat assessment that it only referenced the licence.

| Repository | Contribution and review limits |
| ---------- | ----------------------------- |
| [Swiss Statute QA](https://github.com/bisale24-ops/swiss-statute-qa) | Swiss-law evaluation dataset with multilingual cited answers, historical statute snapshots and recorded model responses. Code Apache-2.0, dataset CDLA-Permissive-2.0. Published benchmark results were not independently reproduced. |
| [Fedlex Answer](https://github.com/bisale24-ops/fedlex-answer) | Separate application using statutory retrieval, Apertus answers and deterministic quotation/number checks. Citation matching does not establish correct legal interpretation. |
| [Apertus StressLab](https://github.com/Alextsvr/apertus-stresslab) | False-premise experiments with preregistration, frozen evaluation, raw responses, evidence packaging and later numerical diagnostics. Small synthetic studies and differing numerical configurations do not establish a general hallucination rate. |
| [AirPatch](https://github.com/AhaWissenschaft/airpatch) | Code-proposal evaluation in offline containers, model-response cassettes, hidden test cases and replay tooling. Reports negative results. Cited development commits are not in the public snapshot's history; this limits independent confirmation of preregistration timing. |
| [Apertus Evidence Lab](https://github.com/hallzyx/apertus) | Voting-booklet NLI using hybrid retrieval and a learned decision head over frozen Apertus. A generic chat endpoint cannot run the specialized head. Development results are not independent hidden-test validation. |
| [Schild](https://github.com/ShenJun93/hack-apertus-schild/tree/main/track_2b) | Redaction gateway with identifier rules, Apertus entity detection, placeholder vault and failure handling. Substantive track README qualifies despite template material at the root. No independent privacy or compliance certification is implied. |
| [Apertus Court Decisions](https://github.com/beyondExp/apertus-court-decisions) | Frozen Apertus reader and published classification head for Swiss court legal sub-areas. Default Docker execution checks the head and scores saved predictions; new ruling inference needs local Apertus weights. Source rulings retain their upstream CC BY-SA 4.0 licence. |
| [Folio](https://github.com/ksmostofa/folio) | Source-first checklist extraction, exact quotation/page validation, conditional wording and human review, with local Apertus tooling. Full Apache-2.0 text is bundled; original documents, fixtures and UI dependencies retain separate licences. |

Software was not installed or executed and model inference was not called. Reported benchmark results, safety, privacy and deployment claims remain author-reported. The overall ecosystem research date is unchanged.

Verification: the existing link checker found all **8/8 new destinations reachable**, with no likely broken or inconclusive results. The source-count helper reports **29 Hack Apertus resource-bullet entries** and **139 overall**. README contents anchors, local file links, the section count and `git diff --check` passed. Earlier 21-entry/131-overall totals above describe the initial review, not the final list.
