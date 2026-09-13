# Design constraint: transferable principles

Shared Understanding should help collaboration across different goals, domains, models, and environments. It should preserve responsibilities while leaving the interaction responsive to the situation—not make every task resemble the author's last failure or preferred workflow. Broad applicability is a design goal, not an established guarantee.

This document explains the design constraint and maintenance rationale for contributors. The repository's `AGENTS.md` identifies when contributors need it. It is not additional policy or required reading for an agent using [GUIDANCE.md](../GUIDANCE.md).

## What earns persistent context

An instruction belongs in `GUIDANCE.md` when it changes a meaningful decision across contexts. It needs a recognizable boundary, not an exhaustive recipe or an uplifting slogan. Preserving user authority, for example, requires distinguishing an undelegated consequential choice from an ordinary decision the agent is already authorized to make. “Always ask first” and “use good judgment” both lose that distinction.

The guidance keeps the boundaries around forming intent, authorization, completion, evidence, repair, and continuity. It omits harness-specific tool instructions, question schedules, coding-specific techniques, repeated process disclaimers, and research summaries. These either belong to the host environment or explain a possible application rather than define the responsibility. The clarification-channel preference applies to an already-needed question; it does not expand when agents must ask or require a particular harness. Shorter guidance is not better if it leaves the important choice unspecified.

Understanding, communication, and execution remain connected. None is a mandatory phase, and none substitutes for the others: fluent dialogue can lead to the wrong result; a correct result can still exceed permission. The user need not arrive with a finished specification. Examples can help develop meaning, but must not quietly choose the user's goal or become the only options available.

Transferability does not mean an absence of influence. Instructions necessarily influence behavior. The intended influence is accountable collaboration, not a default subject, interview, or decision sequence.

## One behavioral source

[GUIDANCE.md](../GUIDANCE.md) is the complete, authoritative source for adopter-facing behavior. Its entire contents can be appended to an existing instruction file. The comment markers identify the installed block for replacement; they no longer separate reusable content from repository instructions within one source file.

The repository's `AGENTS.md` contains only development instructions. This separation addresses a [reported delivery problem](problems.md#a-delivery-failure-in-this-project): section markers did not make the two audiences clear enough in practice. A reader can now copy the entire adoption source without importing this repository's maintenance obligations. Local Markdown archives exclude the repository-only `AGENTS.md`. The [retired npm distribution](../README.md#retired-npm-distribution) retains its historical contents for existing users; it is not the current adoption source.

The distinction is by role, not just filename. An adopter's own `AGENTS.md` can contain this guidance alongside unrelated host instructions; this repository's `AGENTS.md` is not that payload. `GUIDANCE.md` is source material for adoption, not a runtime router or a file every environment knows to load.

The [README](../README.md#documentation-by-audience) maps the documents to their readers. Supporting documents explain principles, problems, evidence, and examples. They are optional for adoption and do not add rules. If an example appears to require a new obligation, the choice is to revise the example or explicitly propose a change to `GUIDANCE.md`, not to let the example become a second policy.

There is no parallel skill, generated policy variant, or expanded runtime policy in the docs. Repository-specific contribution requirements belong in `AGENTS.md`; the rationale here explains those requirements rather than extending the reusable guidance.

## Applying the prompt-design article

OpenAI's [Rethinking skills and prompts for GPT-6 Astra](https://developers.openai.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra) recommends revisiting accumulated instructions, avoiding unnecessary document loading and elaborate itineraries, and describing useful decision boundaries and completion. These recommendations inform the design: keep persistent responsibilities focused, leave techniques to contextual judgment, and direct maintainers to relevant documentation rather than requiring the whole project before every edit.

Its progressive-disclosure advice is useful for specialized workflows, but this project's collaboration guidance is needed throughout work. A runtime router would make essential responsibilities depend on another loading step. The separate adoption file removes mixed audiences without introducing that dependency: users copy its full contents into loaded instructions. Optional explanations remain separate; essential boundaries stay in the copied text.

The article's observations about Astra's caution, testing habits, and permission judgment are model-specific practitioner guidance, not universal guarantees. They do not justify removing authorization, verification, or completion boundaries for other models—or assuming Astra always applies them correctly. Host instructions, capabilities, permissions, and safeguards still matter.

The article does not discuss dedicated user-question tools. Preferring a suitable channel for an already-needed question is narrower than adding an approval gate: it leaves clear requests and delegated decisions actionable without reconfirmation. This is a design application of the article's boundary advice, not an article endorsement of the preference or evidence that agents will follow it.

Inline guidance deliberately trades more always-present text than a short activation reminder for no separate loading step. Neither that tradeoff nor a smaller word count establishes lower cost, better attention, or improved collaboration.

## Where a change belongs

This map is for maintaining the project, not a workflow for agents adopting the guidance. Related updates depend on what actually changes; a typo does not require rewriting every document.

| Change | Primary location | Corresponding review or updates |
|---|---|---|
| A reusable behavioral responsibility or decision boundary | `GUIDANCE.md` | Update affected explanations in this document, [examples](examples.md), and [problems and evidence](problems.md). Change the README if purpose or adoption changes; describe the revision in the changelog. Do not restate the new rule across every document. |
| Adoption, replacement, or a delivery path | [README](../README.md#use-the-guidance) and, for local archive contents or the publication guard, [package.json](../package.json) | Update affected links and the source-boundary explanation here. Check the full-copy and migration paths, including preservation of unrelated host instructions. Preserve access to retired published artifacts; a moved source file is not a reason to keep an obsolete copy in the current checkout. |
| Repository-development requirements | Repository `AGENTS.md` | Keep their design rationale here consistent. Keep these requirements out of `GUIDANCE.md` and the repository's `AGENTS.md` out of the package's file list. |
| An illustrative situation | [Examples](examples.md) | Check it against the behavioral source, including what authority and evidence the situation supplies. Label invention versus observation; a new example need not change policy. |
| A failure account, research reference, or effectiveness claim | [Problems and evidence](problems.md) | Distinguish report, observation, hypothesis, and measured outcome. Correct dependent claims in the README, rationale, or changelog; research is not validation of this guidance. |
| Revision or release history | [Changelog](../CHANGELOG.md) | Keep unreleased changes separate from published history. The npm delivery path is retired; keep the checkout private and historical package and lockfile versions aligned. A documentation edit is not a new package release or permission to publish. |

Read related material to trace consequences, not to accumulate runtime instructions. When a design choice is still unresolved, keep it explicit as a proposal rather than installing a competing policy in an example or rationale.

## Revising responsibly

A failure can come from a missing boundary, unavailable context, conflicting instructions, tools, capability, or execution. Identify the supported problem before adding prose. A repeated failure to apply an existing principle is not automatically a reason to restate it more forcefully.

Review a proposed change in materially different situations, including a clear authorized task where it should not introduce questions or delay. Keep concrete cases in the [examples](examples.md) rather than turning them into mandatory stages. Changes to the project's purpose or authority boundaries deserve explicit discussion, not a silent trade for concision.

Evaluate behavior and total collaboration cost, including reading, clarification, and avoidable rework—not confidence, agreement, brevity, or question counts alone. The [evaluation guidance](problems.md#evaluation-and-evidence) distinguishes artifact checks and bounded observations from evidence of broader usefulness. Some failures need better runtime controls or human review rather than more instructions.
