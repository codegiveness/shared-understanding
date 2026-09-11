# Shared Understanding

**Develop the goal together. Communicate consequential changes. Deliver and check what was agreed.**

A skill for collaboration between a user and an AI agent. It connects understanding, communication, and execution without requiring a perfect prompt, a scripted interview, or approval for every ordinary decision.

The central boundary: **act independently within the agreement; resolve choices that change it before committing to them.**

## Install

For Codex and other agents supported by the [Skills CLI](https://github.com/vercel-labs/skills#supported-agents):

```sh
npx skills@latest add codegiveness/shared-understanding
```

Select `shared-understanding` and the agents you use when prompted. Review the installation scope and destination. The installer handles agent-specific skill directories; you do not need to reproduce this repository's directory structure. See the [installer documentation](https://github.com/vercel-labs/skills#installation-scope) for scope and other options. This command is not a claim of support for every harness.

### Add the persistent instruction

Append the contents of [AGENTS.md](AGENTS.md) to the global or project instruction file your harness actually loads, such as `AGENTS.md` or its equivalent. Merge overlapping guidance and preserve unrelated instructions and safety rules.

The block refers to the installed skill by name and asks the agent to use its harness-provided loading mechanism or file path. It does not assume a repository checkout, a `productivity` directory, or one universal installation path.

Installing the skill and adding this persistent instruction are separate steps. Do not assume the skill installer also appends this repository's `AGENTS.md`. The block asks the agent to apply the skill from the first actionable request and revisit it when the understanding changes.

Before relying on it, check that your agent can discover and read the installed `shared-understanding` skill and that your persistent instruction is loaded. Use your harness's documented reload process if needed. Installation alone does not establish that the agent will follow the guidance consistently.

## What it asks the agent to do

- **Understand:** use the conversation and evidence, help develop unclear goals, and distinguish user intent from the agent's interpretation or recommendation.
- **Communicate:** expose consequential interpretations, discoveries, changes, and blockers while the user can still influence the outcome. Ask for unresolved decisions, not discoverable facts or repeated approval.
- **Execute:** complete the agreed scope, choose the simplest adequate approach, preserve safeguards, and verify the actual work.
- **Correct and continue:** use feedback to repair the affected understanding and work without discarding unrelated decisions or making the user start over.

These are connected responsibilities, not four required phases. A clear task can proceed directly. An unclear goal may need dialogue or exploration. A correction should change subsequent action, not merely produce an apology.

You can ask “Check our understanding before continuing” when you want an explicit comparison. No special phrase or recurring checklist is required.

## What this does not establish

This is written guidance, not a runtime enforcement system. It cannot guarantee accurate interpretation, correct implementation, permission enforcement, or retention across context loss. Good communication does not replace technical evidence, and passing checks do not establish an unstated user preference.

Effectiveness means reaching the intended outcome with appropriate evidence. Efficiency concerns total effort—including clarification and rework—not just fewer questions or shorter replies. Whether this skill improves either requires evaluation in real use; this repository does not claim a measured improvement or consistent compliance across models and harnesses.

Read [Shared Understanding in practice](docs/shared-understanding.md) for illustrative situations, decision boundaries, and evaluation guidance.

## Repository contents

| File | Purpose |
|---|---|
| [skills/shared-understanding/SKILL.md](skills/shared-understanding/SKILL.md) | Canonical skill instructions. |
| [AGENTS.md](AGENTS.md) | Copyable persistent instruction block. |
| [docs/shared-understanding.md](docs/shared-understanding.md) | Human-facing practice and evaluation guidance; not required for routine activation. |
| [CHANGELOG.md](CHANGELOG.md) | Revision history. |

The skill uses the [Agent Skills format](https://agentskills.io/specification): a named directory containing `SKILL.md`. The flat `skills/shared-understanding/` layout avoids an unnecessary category for this repository's single skill; it is a source layout, not an installed path.

## Contributing

Describe a concrete failure and the intended behavior. Change the canonical guidance rather than add an overlapping policy. Check clear requests as well as ambiguous ones: avoiding unauthorized decisions must not become unnecessary permission-seeking. Report observed behavior separately from proposed benefits.

## License

[MIT](LICENSE), copyright 2026 codegiveness.
