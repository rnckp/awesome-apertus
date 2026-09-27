---
name: update-awesome-apertus
description: Maintain and update the Awesome Apertus resource list through current web research and the repository's resource-counting and link-checking scripts. Use for full refreshes, new resources, stale entries, broken links, duplicates, and model-version corrections.
---

# Update Awesome Apertus

Maintain a comprehensive but concise resource list for the **Swiss AI Apertus model family**. The repository root is three directories above this skill folder (`../../..`). Run maintenance commands there; unlinked file paths below are relative to that root. Do not confuse Apertus with similarly named cinema, VR, or commercial projects.

## Repository contract

- Read [README.md](../../../README.md), [CONTRIBUTING.md](../../../CONTRIBUTING.md), and [RESEARCH.md](../../../RESEARCH.md), plus applicable agent instructions and the current Git diff, before editing. Read [src/README.md](../../../src/README.md) and the [Makefile](../../../Makefile) for maintenance commands.
- `README.md` is the canonical list and the GitHub Pages homepage. Keep short descriptions, grouped model variants, the contents links, and the distinction between official and third-party resources.
- `RESEARCH.md` records the source trail, scope, research date, caveats, and actual verification results. Correct stale observations instead of accumulating contradictory notes.
- Preserve the CC0 license and unrelated user changes. The Python package contains working maintenance helpers; reuse them rather than writing replacement counters or HTTP crawlers. Change helper code or deployment setup only when the requested work needs it.

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

## Maintenance scripts

Run from the repository root with Python 3.13+ and `uv`. Use the committed lockfile; a content update does not require dependency upgrades.

```sh
make install       # uv sync --locked; set up dependencies when needed
make count-sources # Write count_sources.md; offline
make check-links   # Write link-check-report.md; makes network requests
make reports       # Run both report helpers
```

For a full refresh, use the reports to establish a baseline, then rerun the affected checks after editing. For a targeted update, check the changed resources and related claims without unnecessarily repeating a full network crawl. Both CLIs accept an input Markdown file and `--output`; for example:

```sh
make count-sources ARGS='README.md --output /tmp/apertus-counts.md'
make check-links ARGS='README.md --output /tmp/apertus-links.md'
uv run --locked check-links --help
```

To check only changed URLs, put those links in a temporary Markdown file and pass that file as the input. To audit supporting documents, pass `RESEARCH.md` or `CONTRIBUTING.md` explicitly and use separate output files. Defaults cover **only `README.md`**, not every Markdown file in the repository.

Interpret the results according to the implementation:

- [count_sources.py](../../../src/awesome_apertus/count_sources.py) counts top-level resource bullets containing external Markdown links under level-two headings, grouped by section. Secondary links, nested bullets, fenced examples, and table rows do not add entries. Model/provider tables are therefore excluded, and separate cross-references count again. Report these as **resource-bullet entries**, not unique sources, models, publishers, or URLs.
- [link_checker.py](../../../src/awesome_apertus/link_checker.py) checks unique HTTP(S) destinations after removing fragments. It follows redirects, tries HEAD, and falls back to a streamed GET on unsuccessful HEAD requests. It uses ten workers and a 30-second request timeout, without downloading response bodies.
- Link outcomes are `reachable` (2xx/3xx), `likely broken` (404/410), and `needs review` (other errors or connection failures). Exit status 1 means a likely broken link or missing input. **Exit status 0 can still include unresolved `needs review` results**; always read the report.
- The checker does not inspect content, licensing, local files, or fragment targets. Verify those separately. Broad network failure indicates an inconclusive run, not that the directory's resources have disappeared.

The default reports are ignored by Git and excluded from Pages. Summarize relevant findings in `RESEARCH.md`; do not force-add generated reports unless requested. When changing helpers, run `make check` for Ruff linting, formatting checks, and offline regression tests. These checks validate helper code, not the resource list or live URLs.

## Edit and verify

1. Add or revise entries in the existing sections, with direct primary-source links and one short statement of purpose. Avoid prices, download counts, duplicate listings, and broad claims of completeness.
2. Update the contents anchors if headings change. Keep repository-relative document links so the same Markdown works on GitHub and Pages.
3. Use the link helper for new or changed URLs and inspect destination contents in primary sources. A successful HTTP response alone does not establish relevance. For a full refresh, run it on the entire README and audit supporting documents as appropriate; state exactly which files were checked.
4. Distinguish dead links from rate limits, authentication, and bot protection. Retry transient errors sparingly; use a primary-source cross-check for blocked pages and record unresolved cases. Do not delete an entry solely because it returned 403 or 429.
5. Validate local file links, contents anchors, table structure, and `git diff --check`. Review counts from the resource helper for unexpected changes, while checking tables separately. Recalculate verification totals when recording a new full check; keep resource-bullet counts distinct from unique URL counts and never reuse historical totals as current results.
6. Advance the README's “Last researched” date and the overall research date only after a substantive refresh. For a narrow change, record its date and scope separately when useful. State what was actually tested; link checking does not mean software or services were exercised.

## GitHub Pages conventions

`_config.yml` uses GitHub Pages-supported Jekyll plugins to render `README.md` as `index.html`, render the supporting Markdown pages, and rewrite relative links. Do not maintain a second copy of the list in an index file.

`.github/workflows/pages.yml` builds and verifies the site, then deploys on pushes to `main` or manual dispatch. Its current checks cover generated pages, a homepage heading anchor, and exclusion of repository tooling; inspect the actual workflow before claiming broader link validation. Keep maintenance reports, helper code, and agent instructions excluded through `_config.yml`. If the repository name or Pages base path changes, review the config and workflow checks together.

Finish with a concise summary of additions, corrections, removals, and verification limits. Commit, push, dispatch workflows, or change repository settings only when included in the user's authorization; a content-update request alone does not request publication.
