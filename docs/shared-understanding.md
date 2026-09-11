# Shared Understanding in practice

The [skill](../skills/shared-understanding/SKILL.md) is the canonical guidance. The [persistent instruction block](../AGENTS.md) connects it to a working agent; the [README](../README.md#install) explains installation.

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
| The agreed outcome is complete | Report the result and relevant evidence, then stop instead of expanding the task. |

Not asking a question does not establish perfect understanding. Asking several questions does not establish careful collaboration. A question earns its place when the answer helps develop meaning or changes a relevant decision.

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

When the result is technically wrong despite a clear agreement, accept the reported failure, investigate the cause, repair it, and check the affected behavior. More clarification is not a substitute for correcting a technical defect.

## Reporting progress and evidence honestly

**Situation:** the agreed migration covers web and mobile callers. Web is updated and its checks passed. Mobile source remains inaccessible after investigating available access.

The task is partially complete and blocked on a specific prerequisite. Report the web result, the access needed, and the remaining mobile work. Do not relabel it a completed web migration or imply mobile checks ran.

Evidence also has boundaries. If type checking passed, tests could not start, and no browser session ran, those are three different facts. Neither “tests passed” nor “browser behavior verified” follows. Complete other authorized checks where useful and state what remains unverified.

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
- Inspect what the agent actually does after the user's answer. Helpful-sounding questions alone are not evidence of shared understanding.
- Record missed requirements, unauthorized changes, unsupported claims, unnecessary questions, repeated user effort, and avoidable committed rework separately. A useful correction during exploration is not equivalent to repairing an unauthorized implementation.
- For comparisons, retain the guidance versions, inputs, outputs, criteria, model and harness details, tool access, and sampling settings where available. Repeat trials and include human judgments and real work before making broad improvement claims.

## Evidence limits

This repository provides guidance and illustrative examples, not a published reproducible benchmark establishing improved productivity, efficiency, or model reliability. Development smoke checks can reveal selected response failures, but they do not establish general compliance. Historical session summaries are not evidence that the current version works consistently.

Installation checks establish that files can be discovered or copied—not that an agent loads the persistent instruction, follows the skill, or retains decisions after compaction. Text-only dialogue checks do not establish actual implementation quality or live human agreement. Runtime checks establish only the behavior they exercise, not an unstated preference.

When behavior fails, distinguish unavailable instructions or context, a mistaken interpretation, ineffective communication, unsupported evidence, and incorrect execution. Repair the supported cause rather than assuming another instruction will solve it. Do not publish private conversations or claim an improvement that the evidence does not demonstrate.
