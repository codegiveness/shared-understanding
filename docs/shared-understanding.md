# Shared Understanding in practice

The [skill](../skills/shared-understanding/SKILL.md) is the canonical guidance. The **Shared understanding** section of [AGENTS.md](../AGENTS.md) connects it to a working agent; the [README](../README.md#install) explains installation. Its separate repository-development section is not part of that copyable integration.

This guide explains the intended behavior through illustrative situations. The examples are not measured model outputs, mandatory scripts, or evidence that the skill improves reliability. They describe this version directly, without claiming that particular ideas were adopted from or outperform other projects.

## Three connected responsibilities

**Understanding** is a working interpretation of the intended outcome, constraints, and decisions. It must remain open to correction. A confident paraphrase can still miss what matters to the user.

**Communication** makes consequential interpretations and changes visible while they can still be questioned. It must influence what the agent does next. Announcing an unauthorized decision is not the same as obtaining agreement.

**Execution** turns the agreed direction into a complete result and gathers appropriate evidence that it works. The agent can understand and communicate correctly yet still implement the wrong behavior.

These responsibilities overlap throughout a conversation. The user need not specify everything at the beginning, and the agent should not use missing detail as permission to invent a goal. The agent owns investigation and ordinary technical judgment; the user owns priorities and consequential choices they have not delegated.

## When to act, explain, or ask

The boundary is the effect on the agreement, not the mere presence of uncertainty or a changed internal method.

| Situation | Intended behavior |
|---|---|
| The request and authorization are clear | Do the work and check it proportionately; do not manufacture an interview. |
| A relevant fact is available in the repository or other accessible evidence | Investigate it rather than ask the user to do that work. |
| The goal is still forming | Help the user develop it through a useful question, tentative interpretation, concrete situation, or authorized exploration. Do not choose the outcome for them. |
| Different interpretations would change the deliverable or an important constraint | Explain the practical difference and resolve the user's choice before the affected commitment. |
| An ordinary implementation detail is delegated | Choose it without requesting permission again. |
| A discovery changes a stated approach but preserves the agreed outcome and authority | Explain the consequential change and proceed within scope; bring any new undelegated tradeoff back to the user. |
| A proposed shortcut would omit required behavior or weaken a safeguard | Do not silently take it. Find an adequate approach or discuss the proposed change before committing. |
| Part of the task is genuinely blocked | Identify the missing prerequisite and remaining work; continue useful independent authorized work. |
| Continuing depends on a consequential user decision that is neither settled nor delegated | Use the available asking tool to resolve that decision in context; do not substitute a recommendation or announcement for the user's answer. |
| The agreed outcome is complete | Report the result and relevant evidence, then stop instead of expanding the task. |

Not asking a question does not establish perfect understanding. Asking several questions does not establish careful collaboration. A question earns its place when the answer helps develop meaning or changes a relevant decision.

Prefer the available asking tool when continuing depends on an unsettled, undelegated user decision. Derive the question and any options from the conversation, not a predefined subject or stage. Provide the context needed to answer and distinguish your interpretation or recommendation from the user's choice. Leave room to reject the framing, decline, or delegate a bounded choice; do not force an open question into a fixed menu. If no suitable tool is available, ask clearly in ordinary dialogue. Facts and status can remain statements; the decision must remain the user's.

Batch related, independently answerable questions when that reduces back-and-forth. Sequence questions when an earlier answer determines whether later questions are relevant. There is no single-question quota. An answer settles only what it addresses; it does not authorize unrelated choices or waive existing boundaries.

Tool use does not make a question neutral. Options can all assume the same unsupported premise; a recommendation can make disagreement unnecessarily difficult. Explain the actual consequence and allow the user to correct the premise, not merely choose within it. Conversely, do not reopen settled boundaries by offering adjacent work that was never requested. A request for local edits does not need a publishing decision when publication is already outside the agreement.

## Example: an unresolved decision after an assessment

This is one illustration of the general decision boundary, not a required assessment phase or a template for other conversations.

**Situation:** the user wants an app improved and selects “Assess first.” An assessment reports inconsistent date handling, cancellation treated as missing data, and a repeated lookup. These are source observations; runtime effects have not been verified, and no changes are authorized.

The findings and their evidence are useful statements. Ending with “Start with the date issue” supplies a recommendation but leaves the user's next decision unasked. Instead, explain the recommendation and its limits, then use the asking tool to ask what should happen next. Depending on the actual findings, choices might include investigating the date behavior, addressing another finding, investigating several together, or leaving the code unchanged. Let the user specify a different scope. Do not offer only “fix my preferred issue” and “cancel,” or imply source inspection has already established a business rule or runtime outcome.

The question should make the commitment clear: choosing further investigation is not approving a fix; choosing one fix does not authorize every other finding. Batch independent choices if useful, but resolve dependent questions after the relevant answer. If fixing the date behavior requires an unsettled business convention, ask about that convention before implementing it rather than silently choosing one.

After the answer, follow the chosen scope. If the user declines changes, stop. If they authorize an action or delegate a bounded choice, proceed without asking the same thing again. If they requested only a report from the outset, deliver it without turning completion into pressure to start more work.

## Developing an unclear goal

**Situation:** the user says, “Make this dashboard useful.” It contains tasks, owners, and deadlines, but the user cannot yet say what should change.

A useful approach could ask about a recent occasion when the dashboard failed to help. If abstract questions are not working, the agent might offer a tentative contrast based on that experience. The purpose is to help the user recognize what matters—not force them to choose from an invented feature menu.

If the user says, “A deadline view sounds promising; show me before changing anything,” the agent can show an authorized example using known or explicitly hypothetical data. That does not authorize rebuilding the app.

If the user then says, “Implement that read-only view; keep assignments and deadlines unchanged,” the direction and scope are settled. The agent should implement without restarting the interview.

The same initial words after an earlier agreement might already be clear. Use the conversation, not a default sequence of questions.

## Communicating an interpretation that matters

**Situation:** the user asks to remove duplicate customers while keeping legitimate separate customers. Two records share an email address but have different business names. No duplicate rule is settled.

Repeating “remove duplicates, preserve legitimate customers” does not expose the problem. Explaining that matching on email would merge those two records makes the consequence visible. The user can then clarify whether sharing an address is compatible with being distinct customers.

The agent should not delete records while that choice is open. It may continue authorized inspection that does not depend on the answer. A status message declaring the intended merge would not replace permission.

## Changing the method without changing the agreement

**Situation:** a local-only customer report is authorized. Inspection reveals that the existing report service uploads records to a vendor; a local implementation is possible.

The agent should communicate the conflict and use an adequate local approach within the agreed scope. A different internal implementation does not require the user to approve “local-only” again.

If the alternative would lose a required field, introduce a cost the user has not delegated, or need another permission, the agent should explain that specific consequence and resolve it before acting. It must not upload records, silently reduce the report, or conceal the change until delivery.

Likewise, evidence can contradict a requested method. If a proposed database index already exists and serialization is the measured bottleneck, explain the finding and recommend an appropriate next step. Do not implement a knowingly ineffective change or silently turn the request into an unrelated redesign.

## Using approval without inventing it

“Sounds good. Choose the formatting details and proceed” can be clear scoped approval. It need not contain a special keyword, and it does not authorize publishing the result.

“Yes” after “Replace the report, or add a second one?” leaves the choice unresolved. Clarify that distinction rather than restart the entire discussion.

“What are you trying to understand?” is a request to explain the question, not a selection. Connect the unresolved choice to the user's goal and repair the framing. Silence or an unrelated answer does not close it.

## Correcting the work, not just the wording

**Situation:** the agreed customer message should tell people what to do. The agent produces a short explanation of outage architecture. The user says, “This is shorter, but it still does not help anyone.”

Known facts are that old sign-in links fail, requesting a new one works, and recovery time is unknown. The agent should recognize the mistaken emphasis and revise the message around the action, without inventing a recovery time. It should not make the user explain the whole goal again or defend the draft because they requested brevity.

A later request for warmer wording changes tone, not those facts or the need for actionable advice. Conversely, the user may genuinely change the goal; continuity is not a reason to reject that change.

When the result is technically wrong despite a clear agreement, accept the reported failure, investigate the cause, repair it, and check the affected behavior. Accepting “this became slower” does not establish “the database is responsible.” Investigate accessible evidence without making the user prove their experience or adopting an unsupported diagnosis. More clarification is not a substitute for correcting a technical defect.

Reconsideration is not the same as agreement. If a user declines a suggested warmer tone, preserve their chosen tone rather than repeatedly persuading them. If they challenge a calculation without new evidence, check the relevant arithmetic and explain a supported result rather than changing it to appear receptive. These are illustrations, not a distinction between “difficult” and “cooperative” user types.

When a corrected premise affects several conclusions, revisit those conclusions rather than editing only the sentence the user noticed. Keep unaffected requirements and permissions intact. Work already invested does not justify continuing from a contradicted premise. This concerns reasoning and work, not a mandatory pause, tree, ledger, or restart.

## Reporting progress and evidence honestly

**Situation:** the agreed migration covers web and mobile callers. Web is updated and its checks passed. Mobile source remains inaccessible after investigating available access.

The task is partially complete and blocked on a specific prerequisite. Report the web result, the access needed, and the remaining mobile work. Do not relabel it a completed web migration or imply mobile checks ran.

Evidence also has boundaries. If type checking passed, tests could not start, and no browser session ran, those are three different facts. Neither “tests passed” nor “browser behavior verified” follows. Complete other authorized checks where useful and state what remains unverified.

A correct result does not establish that the process respected authority. A delivered announcement can still have been sent without permission. Review relevant commitments as well as the final artifact. Self-review or a second model agreeing can suggest something to check; agreement alone does not supply independent evidence. A bounded check can support a bounded claim without proving the entire assignment.

Simplification must preserve the required behavior. Reusing an existing upload-size helper can remove unnecessary machinery; deleting the size limit or sending confirmation changes the agreement. Hiding every server exception behind a successful response is not a repair merely because a shallow check becomes green.

## Continuing after context loss

Recover accessible decisions and history before asking the user to repeat them. Preserve relevant reasons, not only choices: “customer data must remain local” explains why an upload-based method was rejected.

If permission to send an announcement cannot be recovered, a ready draft and “continue” do not establish approval. Continue clearly authorized preparation, but ask before sending.

A handoff should distinguish settled decisions from proposals, open questions from approvals, and attempted work from verified results. Use existing conversation or task state; no separate document or repeated checklist is required. These instructions cannot guarantee that a harness retains or supplies that state.

## Evaluating effectiveness and efficiency

**Effectiveness:** does the result fit the user's intended outcome, preserve the agreed boundaries, and hold up to appropriate verification?

**Efficiency:** what total effort was needed, including user decisions, repeated explanations, investigation, narration, and avoidable rework? A brief question may prevent a costly wrong implementation. Fewer questions can also conceal guessing.

**Consistency:** do the responsibilities hold across different contexts and later turns? It does not mean identical wording, a fixed question count, or asking before every action.

To assess a revision:

- Define scenarios and observable expectations before running them. Include clear authorized tasks as controls, not only ambiguous or risky requests.
- Exercise real transitions: discussion to approval, discovery to changed approach, feedback to repaired work, and partial progress to completion or an explicit blocker.
- Include unresolved decisions in different contexts, partial answers, independent questions that can be batched, dependent questions that should wait, and report-only or already-delegated controls. Inspect the selected asking action and subsequent behavior, not merely the presence of a question mark.
- Inspect what the agent actually does after the user's answer. Helpful-sounding questions alone are not evidence of shared understanding.
- Record missed requirements, unauthorized changes, unsupported claims, unnecessary questions, repeated user effort, and avoidable committed rework separately. A useful correction during exploration is not equivalent to repairing an unauthorized implementation.
- For comparisons, retain the actual loaded guidance revision, inputs, outputs, criteria, model and harness details, tool access, and sampling settings where available. Do not assume repository, installed, and published versions match. Repeat trials and include human judgments and real work before making broad improvement claims.

## Evidence limits

This repository provides guidance and illustrative examples, not a published reproducible benchmark establishing improved productivity, efficiency, or model reliability. Development smoke checks can reveal selected response failures, but they do not establish general compliance. Historical session summaries are not evidence that the current version works consistently.

Installation checks establish that files can be discovered or copied—not that an agent loads the persistent instruction, follows the skill, or retains decisions after compaction. Text-only dialogue checks do not establish actual implementation quality or live human agreement. Runtime checks establish only the behavior they exercise, not an unstated preference.

When behavior fails, distinguish unavailable instructions or context, a mistaken interpretation, ineffective communication, unsupported evidence, and incorrect execution. Repair the supported cause rather than assuming another instruction will solve it. Do not publish private conversations or claim an improvement that the evidence does not demonstrate.

## Research context—not validation of this skill

The following sources inform design judgments and evaluation questions. None evaluates this repository's revised skill. Theory, practitioner prescriptions, benchmark results, and human studies support different claims; resemblance is not proof of adoption, novelty, superiority, or effectiveness. The selection is not an exhaustive literature review.

| Source | Relevant result or idea | Boundary on its use here |
|---|---|---|
| [Clark and Brennan, Grounding in Communication (1991)](https://web.stanford.edu/~clark/1990s/Clark,%20H.H.%20_%20Brennan,%20S.E.%20_Grounding%20in%20communication_%201991.pdf) | Understanding is established sufficiently for the current purpose; collaborative effort includes both participants. | Human communication theory, not evidence of LLM compliance or permission. |
| [Horvitz, Principles of Mixed-Initiative User Interfaces (1999)](https://erichorvitz.com/chi99horvitz.pdf) | Goal uncertainty, interruption cost, user control, and correction matter together. | Design principles do not authorize an agent to substitute its estimated utility for a user's decision. |
| [Morae (2025)](https://arxiv.org/html/2508.21456) | A small study with blind and low-vision users found better preference alignment through proactive choices, alongside longer completion times and imperfect pause detection. | A specialized interface study, not proof that more questions improve every interaction or that asking alone caused the benefits. |
| [DiscoverLLM (2026)](https://arxiv.org/html/2602.03429) | Distinguishes discovering an unformed intent from eliciting one already known; includes a human writing study. | A trained system and bounded evaluation, not an instruction-only intervention. Options can also overwhelm or overly constrain users. |
| [Jakesch et al., Co-Writing with Opinionated Language Models (2023)](https://arxiv.org/html/2302.00560) | Opinionated suggestions influenced writing and views despite users retaining editing control. | A particular topic and deliberately slanted model setup; not an effect estimate for this skill. Editable options do not certify freedom from influence. |
| [LLMs Get Lost In Multi-Turn Conversation (2025, v1)](https://arxiv.org/html/2505.06120v1) | Information revealed across turns caused integration failures; recap interventions partially helped in selected conditions. | Simulated disclosure of predetermined tasks, not evolving human intent or a reason to require repeated readbacks. |
| [Training Language Models to Self-Correct via Reinforcement Learning (2024, v1)](https://arxiv.org/html/2409.12917v1) | Trained self-correction improved bounded math and coding performance. | Changes to model training with evaluable rewards, not proof that prompting for more reflection suffices. |
| [τ-bench (2024, v1)](https://arxiv.org/html/2406.12045v1) | Repeated simulated tool interactions expose reliability failures; final-state success can miss required confirmation. | Simulated users and domain policies, not a measure of this user's collaboration or current models. |
| [Evaluating AGENTS.md (2026)](https://arxiv.org/abs/2602.11988) | Context files did not generally improve success in its coding evaluation and increased inference cost on average. | Repository context files are not identical to this general collaboration skill; the result does not establish that instructions never help. |
| [SkillsBench (2026, v1)](https://arxiv.org/html/2602.12670v1) | Curated skills helped on average but effects varied, including negative task-level effects. | Procedural, containerized benchmarks; not live shared understanding. Associations with length do not prove shortening this skill improves it. |
| [Xavier, Hughes, and Korunka, Mindfulness, creative self-efficacy, and communal-agentic orientation in human–AI decision-making (2026)](https://doi.org/10.1038/s41598-026-69355-z) | In 549 UK-based professionals, measured traits interacted in their association with budget-decision revision. Mindfulness and creative self-efficacy had no significant independent main effects; subgroup slopes were not independently significant. | The supplied Article in Press measures any revision, not agreement with AI or decision quality. Traits were measured, not manipulated: it does not establish a benefit from mindfulness training or prompting an LLM to be mindful. |

These sources support investigating the appropriate intervention rather than assuming a wording gap. Guidance can express a boundary; the model must recognize and apply it, and the environment must supply context, evidence, and appropriate permission controls. No one layer substitutes for the others.

The mindfulness paper motivates a design interpretation, not an LLM mechanism: notice when an interpretation no longer fits, rather than continuing automatically or changing position merely to secure agreement. Do not infer personality, confidence, or mindfulness profiles from a user's replies, or introduce a required reflection ritual. The paper's practical recommendations are provisional; its results do not establish that more acceptance, more revision, or more reflection improves collaboration.

Practitioner skills provide useful contrasting designs, not measured results for this project. [Pocock's grilling](https://github.com/mattpocock/skills/blob/main/skills/productivity/grilling/SKILL.md) batches independently answerable questions; [Osmani's Interview Me](https://github.com/addyosmani/agent-skills/blob/main/skills/interview-me/SKILL.md) prescribes a single-question approach and a self-assessed confidence threshold; [Superpowers brainstorming](https://github.com/obra/superpowers/blob/main/skills/brainstorming/SKILL.md) scales its process but retains a renewed approval gate. These are mutable sources inspected during the research. None establishes a universally optimal question schedule or a calibrated confidence percentage. Their useful responsibilities should not import their entire workflows into this skill.

The research motivates the revised distinctions between reported experience and causal explanation, evidence and completion claims, and corrected premises and dependent work. These are proposed improvements in clarity—not demonstrated gains in effectiveness. The [confidence plan](problems.md#what-could-raise-confidence-to-high) describes what further evidence would be needed.

The [Karpathy-inspired guidelines](https://github.com/multica-ai/andrej-karpathy-skills/blob/main/skills/karpathy-guidelines/SKILL.md) illustrate compact principles connected to concrete coding decisions: surface assumptions, avoid speculative complexity, limit unrelated changes, and verify results. That is a useful authoring model, not a reason to impose coding-specific procedures on all conversations. Repository stars indicate interest, not measured effectiveness. Conversely, lack of a universal guarantee does not make guidance worthless: bounded, repeatable improvements can justify its use.
