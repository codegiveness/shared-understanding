# Shared Understanding

An agent can deliver polished work that solves the wrong problem, ask a useful question and ignore the answer, or mistake approval for proof that the result is correct.

Shared Understanding is self-contained behavioral guidance for your existing `AGENTS.md`. It asks an agent to develop an understanding you can recognize, question, and revise—and let that understanding govern the work. You should not need a perfect prompt, a scripted interview, or repeated approval of ordinary authorized decisions.

**Adopt [GUIDANCE.md](GUIDANCE.md), not this repository's `AGENTS.md`.** The entire guidance file is reusable; the repository's `AGENTS.md` is only for developing this project.

## Use the guidance

1. Open [GUIDANCE.md](GUIDANCE.md) in source/raw view and copy the **whole file**, including its heading and comment markers. There is no repository-only section to exclude.
2. Append it to the existing `AGENTS.md` your environment loads. Preserve unrelated instructions and safeguards. If Shared Understanding is already present, replace only its old guidance block rather than keeping competing versions; reconcile local edits and overlapping guidance.
3. Confirm that your environment loads the edited file, using its documented reload mechanism if needed. This repository does not configure your agent or establish which file its environment loads.

No skill installation, package command, repository checkout, or supporting-document loading is required. `GUIDANCE.md` is the source to copy, not a filename your agent is expected to discover automatically. The comment markers identify the copied block for later replacement; everything in the file belongs in that block.

Copied guidance is a snapshot, not an automatic update. Review [changes](CHANGELOG.md) and compare the source with your local copy when adopting a later revision.

### Migrating an existing setup

- **From the combined repository `AGENTS.md`:** replace the old **Shared understanding** block with the contents of `GUIDANCE.md`. If you also copied this project's **Repository development** paragraph, remove that paragraph from your adopting environment; leave its own development instructions intact.
- **From the retired skill setup:** replace the Shared Understanding activation block with the contents of `GUIDANCE.md` and remove the old Shared Understanding skill from locations your environment loads. Preserve unrelated skills and instructions.

## Documentation by audience

| Document | Audience and role |
|---|---|
| [GUIDANCE.md](GUIDANCE.md) | **Adopters and their agents:** the sole reusable behavioral source. Copy all of it. |
| Repository checkout's `AGENTS.md` | **Contributors and their agents:** repository-development instructions, never part of adoption. |
| [Examples](docs/examples.md) | **Interested readers:** invented situations illustrating the guidance, not extra rules or observed results. |
| [Problems and evidence](docs/problems.md) | **Readers investigating failures or effectiveness:** observations, possible causes, evaluation considerations, and limits. |
| [Design rationale and maintenance](docs/general-principles.md) | **Contributors:** the transferable-principle constraint, design tradeoffs, and where a change belongs. |
| [Changelog](CHANGELOG.md) | **Readers updating a copy:** revision history, not current policy; earlier skill-based releases are historical. |

Supporting documents are optional for adoption and do not add behavioral requirements. Contributors use the checkout's `AGENTS.md` and the [maintenance map](docs/general-principles.md#where-a-change-belongs) to keep the source and its explanations aligned.

## Retired npm distribution

The [npm package](https://www.npmjs.com/package/@codegiveness/shared-understanding) is retired. Current adoption uses [GUIDANCE.md](GUIDANCE.md) directly; no npm installation is needed. Published versions 0.1.0–0.1.6 contain the earlier skill-based setup, not the current guidance.

All published versions are deprecated with a migration notice, not unpublished. Existing versions remain downloadable and installable; deprecation does not remove installed files or update copied instructions. Follow [Migrating an existing setup](#migrating-an-existing-setup), preserving unrelated instructions and local edits. If you need the old package during migration, its existing version pins remain usable.

Retirement is a delivery decision, not a claim that nobody uses the package. On September 13, 2026, the [npm downloads API](https://api.npmjs.org/downloads/point/2026-08-13:2026-09-11/@codegiveness/shared-understanding) reported 906 downloads for August 13–September 11. Downloads do not identify unique users, active installations, or all downstream consumers.

The checkout's `package.json` is marked `private` to prevent accidental publication. Its file list supports local Markdown archives only, excluding the repository-only `AGENTS.md`; no replacement npm release is planned. Historical package contents and release history remain available.

## What this does not establish

This is guidance, not enforcement or a demonstrated improvement across models and environments. A clearer copy source does not prove that a harness loaded it or that an agent followed it. [Evaluation and evidence](docs/problems.md#evaluation-and-evidence) explains what stronger claims would require.

## License

[MIT](LICENSE), copyright 2026 codegiveness.
