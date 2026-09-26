---
name: update-awesome-apertus
description: Research and maintain this repository's Awesome Apertus resource list, verifying official releases, tooling, providers, and community contributions against current primary sources. Use for ecosystem refreshes, resource additions, and link or version corrections.
---

# Update Awesome Apertus

Maintain a comprehensive but concise resource list for the **Swiss AI Apertus model family**. Work in the repository containing this file; do not confuse it with similarly named cinema, VR, or commercial projects.

## Repository contract

- Read `README.md`, `CONTRIBUTING.md`, and `RESEARCH.md`, plus applicable agent instructions and the current Git diff, before editing.
- `README.md` is the canonical list and the GitHub Pages homepage. Keep short descriptions, grouped model variants, the contents links, and the distinction between official and third-party resources.
- `RESEARCH.md` records the source trail, scope, research date, caveats, and actual verification results. Correct stale observations instead of accumulating contradictory notes.
- Preserve the CC0 license and unrelated user changes. Do not modify the Python scaffold or deployment setup during a content refresh unless needed for the requested work.

## Research and selection

For a full refresh, start with these live sources and follow their current links:

- [Apertus](https://www.apertus-ai.org/): releases, documentation, research, provider directory, showcase, and contact channels.
- [Swiss AI on Hugging Face](https://huggingface.co/swiss-ai): model cards, collections, datasets, and discussions. Inspect authored usage instructions and artifact files, not only auto-generated deployment snippets.
- [Swiss AI on GitHub](https://github.com/swiss-ai): training, data processing, tokenization, serving, evaluation, and release documentation. Paginate catalogs; the organization also hosts unrelated research.
- Primary sources for community projects: maintainer repositories, model cards, provider documentation, and authors' papers. Search beyond the official showcase for SDKs, workflows, fine-tunes, quantizations, and applications.

For a targeted correction, research the affected entry and its dependencies without presenting it as a full ecosystem review. Use browsing or public APIs available in the current environment; no particular connector or authenticated account is required.

Include a resource when its source demonstrates a concrete Apertus connection and a distinct use. Prefer the original maintainer over mirrors. Group equivalent sizes and formats; use authoritative collections to cover large variant families. Retain useful older releases with clear version labels. Remove or replace entries when evidence shows they are obsolete, unrelated, or redundant.

Track these distinctions explicitly:

- Official releases versus third-party builds or research prototypes.
- Base versus Instruct; model generation, size, and quantization format.
- Original multimodal models versus text-only conversions.
- Released upstream support versus a pinned fork, pull request, or experimental integration.
- Model capabilities versus what a particular hosted endpoint actually exposes.
- Published weights/data/code versus promised artifacts or gated downloads.

Verify present-day status rather than carrying forward assumptions from earlier research. Do not turn provider marketing into independent privacy, compliance, or benchmark claims. Generic API compatibility alone is not evidence of a tested integration. Check model and dataset licenses separately when describing them.

## Edit and verify

1. Add or revise entries in the existing sections, with direct primary-source links and one short statement of purpose. Avoid prices, download counts, duplicate listings, and broad claims of completeness.
2. Update the contents anchors if headings change. Keep repository-relative document links so the same Markdown works on GitHub and Pages.
3. Check new or changed URLs, follow redirects, and inspect destination contents. A successful HTTP response alone does not establish relevance. For a full refresh, check all distinct external destinations with bounded concurrency and reasonable timeouts.
4. Distinguish dead links from rate limits, authentication, and bot protection. Retry transient errors sparingly; use a primary-source cross-check for blocked pages and record unresolved cases. Do not delete an entry solely because it returned 403 or 429.
5. Validate local file links, contents anchors, table structure, and `git diff --check`. Recalculate verification counts when recording a new full check; never reuse historical totals as current results.
6. Advance the README's “Last researched” date and the overall research date only after a substantive refresh. For a narrow change, record its date and scope separately when useful. State what was actually tested; link checking does not mean software or services were exercised.

## GitHub Pages conventions

`_config.yml` uses GitHub Pages-supported Jekyll plugins to render `README.md` as `index.html`, render the supporting Markdown pages, and rewrite relative links. Do not maintain a second copy of the list in an index file.

`.github/workflows/pages.yml` builds and verifies the site, then deploys on pushes to `main` or manual dispatch. Its output checks cover the homepage, supporting pages, project-path links, and exclusion of repository tooling. If the repository name or Pages base path changes, update the config and workflow checks together.

Finish with a concise summary of additions, corrections, removals, and verification limits. Commit, push, dispatch workflows, or change repository settings only when included in the user's authorization; a content-update request alone does not request publication.
