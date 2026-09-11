# Shared Understanding

**Establish the goal together. Preserve it as the session changes.**

A concise agent skill for understanding the request before acting, interpreting later messages without silently changing the agreement, and recovering decisions when context is lost.

The user should not need a perfect prompt. The agent should not need a scripted interview for every task. Honest engineering still matters after both agree on the goal.

**Status:** prose guidance, not a proven reliability intervention. No success percentage, first-try guarantee, or cross-harness compaction guarantee is claimed.

## Installation

Choose one distribution method, then connect the working agent. Do not install multiple active copies of the same skill.

### 1. Get the skill

**npm: versioned prose you install explicitly**

```sh
npm install --global --ignore-scripts @codegiveness/shared-understanding@0.1.0
npm root --global
```

The package is inside the printed directory at `@codegiveness/shared-understanding/`. Its skill is `skills/productivity/shared-understanding/SKILL.md`; the complete instruction block is `AGENTS.md`.

This package has no CLI, dependencies, or install hooks. npm installs the files; it does not register a skill, edit agent configuration, or promise automatic activation. Copy the `shared-understanding` skill directory into your harness's documented skill location, or use its supported skill-management tool. Preserve the skill description and body. Include the [MIT license](LICENSE) with redistributed copies. Do not overwrite an existing installation with local modifications without reviewing it.

To update the package later:

```sh
npm install --global --ignore-scripts @codegiveness/shared-understanding@latest
```

Then refresh the active skill and instruction block from that installed version. A copied skill does not update when npm updates. Prefer explicit, reviewed refreshes over a second independently edited copy.

**Skills CLI: install through its supported harness adapters**

```sh
npx skills@latest add codegiveness/shared-understanding
```

Choose the skill, agent, and installation scope in the [Skills CLI](https://skills.sh/docs/cli). This independently maintained installer runs third-party code and has its own telemetry policy. Adapter support is not proof that every model will follow the guidance.

**Manual: no npm required**

Copy [the skill directory](skills/productivity/shared-understanding/) to your harness's skill directory, or reference its `SKILL.md` directly if the harness supports instruction-file references. The skill is ordinary Markdown following the [Agent Skills specification](https://agentskills.io/specification).

### 2. Connect the working agent

Merge **both sections of [AGENTS.md](AGENTS.md)** into the persistent instruction file your harness actually loads:

- **Shared understanding:** start, every-turn interpretation, material changes, approval boundaries, and context recovery.
- **Engineering judgment:** the complete six safeguards for solving the real problem, owning evidence, respecting cost, revising mistaken approaches, owning mistakes, and finishing with honest verification.

`AGENTS.md` is the canonical, copyable integration snippet. It is intentionally not shortened or duplicated here. Replace only its skill path with your installed skill reference; keep existing project-specific instructions and security rules. Merge overlapping sections rather than stacking duplicates. A filename alone does not guarantee that a harness loads it.

The agent performing the task should maintain the agreement. No separate interviewing subagent is required. On subsequent turns, check interpretation lightly; ask only when the answer would materially change the work or approval is required.

### 3. Retire an older alignment installation

If you already use an overlapping alignment skill, first install and verify `shared-understanding`, update the governing instruction reference, then remove the retired installation through your harness's supported mechanism. Preserve unrelated instructions and user-authored content. Do not keep two active versions.

Start a fresh session or use a documented harness reload after changing discovery metadata; an existing session can retain old injected descriptions. Installation and file equality do not prove model compliance or compaction behavior.

## Why this exists

A good initial prompt does not prevent later drift. A short answer can be mistaken for new scope. An exploratory question can be mistaken for permission. Compaction can lose a constraint. Agreement about the goal does not make an implementation correct.

Shared Understanding addresses those boundaries without turning ordinary work into a requirements interview:

- Extract supplied requirements; investigate available facts yourself.
- Surface consequential assumptions and tradeoffs before costly action.
- Preserve everything a later message does not change.
- Recover missing decisions rather than inventing approval.
- Own mistakes instead of blaming the user's prompt by default.
- Verify the intended outcome within permissions, then stop.

**Outcome / Must preserve / Done means** are optional summaries, not a form users must complete. Read the [session examples and evidence limits](docs/shared-understanding.md) for concrete cases. Reliability remains unmeasured.

## Skill reference

| Skill | Invocation | Purpose |
|---|---|---|
| [shared-understanding](skills/productivity/shared-understanding/SKILL.md) | User-requested or model-selected when supported; persistent rule supplies triggers | Maintain intent, constraints, decisions, and evidence throughout a session. |

Say **“Check our understanding before continuing”** when you want an explicit comparison. Equivalent wording works; it is not a required phrase on every turn.

## Repository structure

```text
AGENTS.md                  Complete integration block and engineering safeguards
README.md                  Installation, purpose, and skill index
package.json               Dependency-free npm distribution
CHANGELOG.md               Published content changes
LICENSE                    MIT license
skills/productivity/
  shared-understanding/
    SKILL.md               One canonical behavioral contract
docs/
  shared-understanding.md  Illustrative sessions and evidence limits
```

The skill lives under `productivity` because it governs the session rather than a particular coding task. Directory and skill names use lowercase kebab-case. Examples stay outside the skill so routine activation loads only the behavioral guidance.

## Contributing

Bring a concrete failure scenario and the smallest justified change. Update the canonical skill or integration block, not a parallel variant. Preserve user authority, evidence ownership, proportional effort, and safety boundaries. Verification of packaging is not proof of better model behavior.

## License

[MIT](LICENSE), copyright 2026 codegiveness.
