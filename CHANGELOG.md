# Changelog

## Unreleased

- Move the reusable behavioral source from the mixed repository AGENTS.md into [GUIDANCE.md](GUIDANCE.md), preserving the existing guidance text during the split. The entire file is appendable; comment markers identify the installed block for updates, not a section to extract from repository instructions.
- Make the repository's AGENTS.md development-only. Local Markdown archives include GUIDANCE.md instead; existing published npm artifacts remain unchanged.
- Remove skill activation, the skill distribution, and local proposal artifacts. No installation step is needed to use the guidance.
- Retire the npm delivery path: deprecate versions 0.1.0–0.1.6 with a migration link while preserving downloads, installation, and existing version tags. Mark the checkout private to prevent accidental publication; document migration and the limits of download-count evidence rather than assuming no users remain.
- Retain concrete boundaries for intent, authority, independent execution, evidence, correction, and continuity while removing harness-specific tool instructions and prescribed question schedules.
- Make asking explicit for unresolved consequential choices outside existing delegation. Prefer a suitable available user-question tool for necessary clarification, with conversational fallback and no new approval gates.
- Separate adoption, design rationale, examples, and failure analysis with evaluation limits; rename the illustrative guide to [docs/examples.md](docs/examples.md) to distinguish it from the copy source.
- Document whole-file adoption, migration from the combined AGENTS.md or retired skill, and preservation of unrelated host instructions. Add a contributor maintenance map and a bounded account of the reported mixed-audience problem; align affected references.
- Apply the OpenAI prompt-design article without treating model-specific observations or reduced instruction length as evidence of reliability. No effectiveness improvement is claimed.

## Earlier releases

These entries describe the retired skill-based delivery model, not instructions for current use. Development checks mentioned here do not establish the behavior of the current guidance.

### 0.1.6

- Clarify consequential decisions, partial answers, independent and dependent questions, and direct action within existing authority.
- Add the general-principle design constraint, observable failure inventory, and evidence plan.
- Distinguish reported experience from causal explanations, correction from reflexive agreement, and verified results from approval or model consensus.

### 0.1.5

- Organize guidance around connected responsibilities for understanding, communication, execution, and repair.
- Consolidate overlapping policy into the skill and reduce persistent integration to an activation block.
- Simplify skill layout and adoption documentation. Exercise eleven text-only development replies without claiming improved reliability.

### 0.1.4

- Replace task-specific review workflows, menus, question quotas, and readback formats with transferable principles.
- Preserve authority and continuity without prescribing a conversation sequence.

### 0.1.3

- Expand the then-current review workflow to track coverage and carry unresolved work across turns.
- Document bounded action-selection observations; this workflow was superseded in 0.1.4.

### 0.1.2

- Require a settled choice or scoped delegation before committing to an unresolved direction.
- Preserve authorized exploration and avoid reopening clear approvals.

### 0.1.1

- Support developing unclear goals through examples and authorized exploration.
- Make interpretations and decision reasons visible; repair mismatches without resetting unrelated decisions or blaming the prompt.

### 0.1.0

- Publish the original skill as a dependency-free prose package with persistent integration and separate explanatory documentation.
