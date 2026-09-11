# Shared Understanding

**Establish the goal together. Preserve it as the session changes.**

A concise agent skill for understanding the user's request before acting, interpreting later messages without silently changing the agreement, and recovering decisions when context is lost.

The user should not need a perfect prompt. The agent should not need a scripted interview for every task.

**Status:** prose guidance, not a proven reliability intervention. No consistency percentage, first-try guarantee, or cross-harness compaction guarantee is claimed.

## What it does

- Extracts requirements already present in the prompt instead of asking for them again.
- Investigates available facts before handing questions back to the user.
- Asks about choices that materially change the outcome, scope, permission, or acceptance.
- Interprets every later message against the current agreement without restarting the interview.
- Distinguishes exploring an idea from authorizing its implementation.
- Preserves unaffected decisions and recovers missing context before consequential actions.
- Keeps technical correctness and verification the agent's responsibility.

**Outcome / Must preserve / Done means** are useful summaries, not a mandatory form. Tradeoffs, decision authority, and available evidence matter too.

## Install the skill

The repository follows the [Agent Skills format](https://agentskills.io/specification). The complete skill is [SKILL.md](skills/engineering/shared-understanding/SKILL.md); it needs no executable code, dependencies, or network access of its own.

### Skills CLI

Using the independently maintained [Skills CLI](https://skills.sh/docs/cli):

```sh
npx skills add codegiveness/shared-understanding
```

Choose your supported agent and installation scope in that installer's interface. This command runs third-party code and may download packages; review the CLI's documentation and telemetry policy first. The skill itself performs no installation or telemetry. Installer support does not establish behavioral compatibility with every harness.

### Manual installation

Copy `skills/engineering/shared-understanding/` into the skill directory documented by your harness, retaining the directory name and `SKILL.md`. Include this repository's [MIT license](LICENSE) with redistributed copies. For harnesses without skill discovery, reference the file directly from their persistent instruction mechanism.

Installing a skill makes it available; it does **not** guarantee automatic activation or execution on every turn.

## Connect the working agent

Use the same agent that performs the task, not a separate interviewer that lacks its context. No custom agent runtime or subagent is required.

Merge this short rule into the instruction file your harness actually loads, such as `AGENTS.md`. Do not overwrite existing rules or assume the filename is supported everywhere.

```markdown
## Shared understanding

Read the shared-understanding skill at task start. On every later message,
interpret it against the current goal, constraints, and decisions; update only
what changed. Use the question tool, or chat if unavailable, for consequential
unresolved choices and required approvals—not repeated answers or ritual
confirmation. Apply the skill again for material changes, understanding checks,
or missing agreement context. Recover available context/history before asking
for lost decisions; missing context is not permission. Preserve the agreement
when producing handoffs. Do not restart the interview or reread the skill on
every turn. Follow existing safety rules and approval boundaries.
```

Make the first sentence point to the actual installed skill if your harness cannot resolve skill names. For a checkout kept at the project root, the file is `skills/engineering/shared-understanding/SKILL.md`. After copying the skill elsewhere, use that destination instead.

For OMP users already using `session-alignment`, this covers the same responsibility. Choose one governing skill and update its reference; do not stack both. This repository does not automatically modify global configuration or migrate an existing installation.

## Session examples

These are illustrative expected behaviors, **not measured model outputs or benchmarks**. They are useful for checking whether your agent understood the contract.

### A complete initial prompt

**User:** “Fix the typo ‘Recieve’ to ‘Receive’ in the checkout heading. Change nothing else.”

**Expected:** locate and correct that heading; perform the permitted proportionate check. Do not ask for Outcome, Must preserve, and Done means again or redesign checkout.

### An underspecified goal

**User:** “Make this dashboard useful.”

**Expected:** inspect the available dashboard context, then ask which decision it should help its intended user make. Offer grounded interpretations if possible. Do not select new charts or redesign the page based on assumptions.

### A second-turn answer

**Agent:** “Should the export contain selected rows or all filtered rows?”

**User:** “All filtered rows. Keep the existing columns.”

**Expected:** update row selection and preserve the existing columns and other settled constraints. Do not restart the requirements interview or silently include unfiltered rows.

### Exploration is not permission

**User:** “Would a database index help?”

**Expected:** investigate and explain whether an index could help. Do not create an index merely because the user asked about it; observe the applicable database approval boundary.

### A mid-session correction

**User:** “Actually, leave export alone. Only fix the date filter.”

**Expected:** stop export work, identify any export edits already made, and state the narrowed scope. Address only your own now-out-of-scope changes within applicable permissions; never discard unrelated user changes. Preserve constraints that still apply to the date filter.

### A requested understanding check

**User:** “Check our understanding before continuing.”

**Expected:** pause substantive work and briefly show the current goal, changes, preserved constraints, and unresolved choice or next action. Ask only if something consequential remains unsettled.

### Missing agreement after compaction

**Available context:** the goal is present, but the record of permission to publish is missing.

**Expected:** try accessible history first. If permission cannot be recovered, ask before publication. Do not claim it was approved because the files are ready. Continue independent authorized local work when safe.

## Limits and evidence

The skill can expose misunderstandings; it cannot guarantee that a model detects every ambiguity or produces correct work. User approval validates intent, not implementation quality.

Three separate things matter:

1. **Availability:** the harness can find the skill and persistent instruction rule.
2. **Continuity:** current decisions, constraints, and scoped approvals remain accessible.
3. **Execution:** the agent follows the guidance and verifies the intended outcome.

Saving a file establishes none of these end to end. Instruction loading, tool names, precedence, history access, and compaction differ by harness. A handoff preserves information only if it is actually produced and retained. This project has no hook that intercepts every turn or controls a harness's compactor.

To evaluate it in normal work, look for specific failures: repeated supplied questions, silently changed scope, discussion treated as permission, lost constraints, or completion claimed without evidence. If one occurs, identify whether the cause was missing instructions, missing context, or execution despite available guidance. Fix that cause rather than adding another overlapping skill. Never publish private session content without permission.

Do not report a success rate without a defined evaluation set, failure criteria, and recorded outcomes. The examples above are not such a measurement. No automated installer, multi-harness runtime, or real compaction recovery verification is claimed here.

## Relationship to Kernel

[`kernel-prompt`](https://github.com/codegiveness/kernel-prompt) refines the request supplied to an agent. **Shared Understanding** maintains the interpretation while the agent works and the user responds. They are complementary, but neither is a prerequisite for the other.

This project does not adopt the claim that every failure originates in a vague prompt. An agent can misunderstand a clear request, make an unsupported technical claim, or implement the right goal incorrectly.

## Influences

The guidance grew from the author's OMP `session-alignment` workflow. Useful ideas were compared with:

- [prompt-master](https://github.com/nidhinjs/prompt-master/blob/main/SKILL.md): extract supplied intent before asking.
- [grilling](https://github.com/mattpocock/skills/blob/main/skills/productivity/grilling/SKILL.md): settle prerequisite decisions before dependent questions.
- [brainstorming](https://github.com/obra/superpowers/blob/main/skills/brainstorming/SKILL.md): surface intent and tradeoffs before costly implementation.
- [interview-me](https://github.com/addyosmani/agent-skills/blob/main/skills/interview-me/SKILL.md): offer concrete interpretations the user can correct.

This is a selective synthesis, not an installation of those workflows. It deliberately omits endless interviews, mandatory approval of every paraphrase, unsupported confidence percentages, and assumptions that the agent knows the user's needs better than the user.

## Contributing

Prefer a concrete misalignment scenario and the smallest rule change that addresses it. Preserve clear-request autonomy, user authority, safety boundaries, and honest limitations. Add examples only when they expose a distinct failure mode; do not grow an exhaustive questionnaire or claim that a wording change has proven behavioral benefits.

## License

[MIT](LICENSE), copyright 2026 codegiveness.
