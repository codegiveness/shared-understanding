# Shared Understanding

**Discover the goal together. Preserve what matters. Check the result.**

A concise set of agent principles for developing shared intent, preserving decisions as a conversation changes, and recovering context—without prescribing a task, question sequence, or answer format.

The user should not need a perfect prompt. The agent should not need a scripted interview for every task. Honest engineering still matters after both agree on the goal.

**Status:** prose guidance, not a proven reliability intervention. No success percentage, first-try guarantee, or cross-harness compaction guarantee is claimed.

## Installation

Choose one distribution method, then connect the working agent. Do not install multiple active copies of the same skill.

### 1. Get the skill

**npm: versioned prose you install explicitly**

```sh
npm install --global --ignore-scripts @codegiveness/shared-understanding@0.1.4
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

- **Shared understanding:** user intent and authority, context-sensitive dialogue, continuity, and recovery.
- **Engineering judgment:** scope discipline, evidence, proportionate effort, accountability, and complete work.

`AGENTS.md` is the canonical, copyable integration snippet. It is intentionally not shortened or duplicated here. Replace only its skill path with your installed skill reference; keep existing project-specific instructions and security rules. Merge overlapping sections rather than stacking duplicates. A filename alone does not guarantee that a harness loads it.

The agent performing the task should maintain the understanding. No separate interviewing subagent is required. Once a direction is settled, interpret later turns lightly; ask only about consequential uncertainty or required approval that remains unresolved.

The skill guides intent discovery and continuity; the engineering section governs how that intent is implemented and checked. Installing only the skill omits the integration block's detailed engineering safeguards. Neither file is a runtime enforcement mechanism.

### 3. Retire an older alignment installation

If you already use an overlapping alignment skill, first install and verify `shared-understanding`, update the governing instruction reference, then remove the retired installation through your harness's supported mechanism. Preserve unrelated instructions and user-authored content. Do not keep two active versions.

Start a fresh session or use a documented harness reload after changing discovery metadata; an existing session can retain old injected descriptions. Installation and file equality do not prove model compliance or compaction behavior.

## Why this exists

“Sometimes smart, sometimes dumb” can describe different failures: solving the wrong problem, inventing facts, forgetting a constraint, making an unauthorized decision, or implementing an agreed idea incorrectly. An unclear prompt is one possible contributor, not a complete explanation or an excuse for agent mistakes.

The user's aim may still be forming. Collaboration can help them develop it without requiring a complete specification or supplying an answer from the agent's familiar task categories. A polished paraphrase is not enough if it quietly replaces what the user meant.

The agreement is a **working model**, not a contract frozen on the first turn. For vague goals, the user settles a concrete direction through a clear choice, approval, or scoped delegation before implementation. The agent helps develop that direction rather than deciding alone that enough is known. Preserve settled constraints and revise the affected interpretation when evidence or feedback changes it.

| Failure | Intended response |
|---|---|
| A vague or still-forming goal | Help develop its meaning from the conversation and context; keep consequential interpretations tentative until settled by the user. |
| A familiar task substituted for the user's goal | Distinguish the agent's proposed direction from the user's intent; do not turn examples in guidance into default objectives. |
| Guessing disguised as precision | Separate user requirements, observed facts, and agent assumptions; expose consequential differences before committing. |
| Endless clarification or decision outsourcing | Investigate available facts; own ordinary technical choices within authorization; ask only what changes the work. |
| Later-turn drift or unintended action | Preserve what a message does not change; distinguish discussion, scoped delegation, and approval. |
| A repeated request loses earlier decisions | Carry forward relevant work, decisions, and limits; revisit them when the conversation or evidence changes. |
| Lost context | Recover decisions and their reasons; never promote a remembered guess into permission. |
| A result that passes checks but misses the point | Check intent fit as well as technical correctness; repair the mistaken interpretation without blaming the prompt. |
| Unnecessary complexity | Reuse established paths; add machinery only for current requirements or supported risks, without dropping necessary behavior. |
| Incomplete delivery | Finish the agreed behavior and affected consumers; do not substitute a plan, partial migration, or narrow demonstration. |
| Unsupported technical claims | Check consequential claims against applicable evidence; never invent APIs, citations, measurements, or verification results. |

This is not “ask before everything” or “guess and let the user correct you later.” Clear, authorized requests proceed directly. A consequential unresolved direction needs the user's choice, approval, or scoped delegation—not the agent's confidence. Existing answers count without another confirmation.

The skill does not define what “better” means, supply a standard menu, or prescribe the next question. Questions, wording, and methods can differ across agents and models. The shared responsibility is to respect the user's meaning and authority, not produce identical conversations. Existing harness rules and approval boundaries still apply.

Together, the skill and integration block target avoidable misunderstanding, excess scope, unsupported claims, and incomplete work. They cannot supply missing model capability, eliminate a model or harness's existing tendencies, guarantee factual accuracy, enforce permissions, or control what a harness retains. More agreement does not prove correctness, and different wording alone does not prove less steering. Evaluate concrete behavior rather than labels such as “overengineered,” “lazy,” or “dumb.”

Read the [session examples, reference tradeoffs, and evaluation guidance](docs/shared-understanding.md). The behavioral approach remains unproven as a reliability intervention.

## Skill reference

| Skill | Invocation | Purpose |
|---|---|---|
| [shared-understanding](skills/productivity/shared-understanding/SKILL.md) | User-requested or model-selected when supported; persistent rule supplies triggers | Develop and maintain intent, constraints, decisions, and evidence throughout a session. |

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
  shared-understanding.md  Session examples, reference tradeoffs, and evidence limits
```

The skill lives under `productivity` because it governs the session rather than a particular coding task. Directory and skill names use lowercase kebab-case. Examples stay outside the skill so routine activation loads only the behavioral guidance.

## Contributing

Bring a concrete failure scenario and the smallest justified change. Update the canonical skill or integration block, not a parallel variant. Preserve user authority, evidence ownership, proportional effort, and safety boundaries. Verification of packaging is not proof of better model behavior.

## License

[MIT](LICENSE), copyright 2026 codegiveness.
