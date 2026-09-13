# Developing Shared Understanding

This file applies only to work on this repository. **It is not the guidance to adopt.** The complete reusable behavioral source is [GUIDANCE.md](GUIDANCE.md). Adopters copy `GUIDANCE.md` into their own loaded instructions, not this repository's `AGENTS.md`.

## Change boundaries

- When a change or evaluation concerns behavioral meaning, adoption boundaries, or design choices, read [the general-principle design constraint](docs/general-principles.md). Preserve transferable responsibilities rather than adding a workflow for the latest failure. For mechanical or unrelated edits, read the material relevant to that edit; no full-documentation reading ritual is required.
- Put adopter-facing behavioral changes only in `GUIDANCE.md`. Keep that entire file appendable and self-contained, without repository instructions or required document loading. Do not duplicate it in this file, a skill, or supporting documentation.
- Keep repository-development instructions here. Supporting documents explain the guidance, evidence, and design; they do not extend adopter policy. The [maintenance map](docs/general-principles.md#where-a-change-belongs) identifies related updates. If an explanation implies a different obligation, correct it or make an explicit change to the behavioral source rather than leaving competing versions.
- Carry changes through affected adoption instructions, links, examples, local archive contents, and the unreleased changelog. Preserve access to retired npm versions; keep the checkout private to prevent accidental publication. Do not rewrite historical releases as current usage instructions. Leave genuinely unresolved changes to purpose or authority explicit for the user to decide.

## Verification

This is a Markdown project, with no build or behavioral test suite. Match checks to the change: inspect relevant links and heading anchors, exercise adoption or replacement in a disposable instruction file when those instructions change, and inspect a locally built archive when its contents change. Local archives must contain `GUIDANCE.md`, not this repository-only `AGENTS.md`; packaging is not publishing and must not be used as permission to publish. For npm retirement changes, verify registry deprecation notices and continued access to historical versions without altering their contents.

Report what the checks actually establish. Copyability, document consistency, and model-generated reviews do not establish reliable collaboration or improvement across models. Keep evidence claims within the conditions exercised; [problems and evidence](docs/problems.md#evaluation-and-evidence) explains the distinction.
