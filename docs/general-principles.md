# General principles: the project's design constraint

This project aims to improve human–agent collaboration across varied goals, domains, conversations, models, and environments. Its skill must express transferable principles without making a familiar task, a previous failure, or a preferred workflow the shape of every interaction.

This is a constraint on developing this project: research, skill revisions, integration instructions, documentation, examples, and evaluation should respect it. It is not an additional runtime skill, a conversation script, or a claim that one document can solve every possible problem. The [skill](../skills/shared-understanding/SKILL.md) remains the canonical behavioral guidance.

## General does not mean universal assurance

The range of possible uses exceeds the situations we can anticipate or test. Broad applicability is a design goal; universal effectiveness is not an established result. A principle can remain relevant across contexts while its application depends on the user's intent, available evidence, delegated authority, capabilities, and risks.

Do not turn the ambition to cover this range into an exhaustive catalog of subjects or rules. No inventory can stand in for the next conversation. Do not claim high confidence merely because the wording sounds comprehensive. Confidence must name what was evaluated and where the evidence stops.

## Preserve responsibilities; leave the interaction open

The skill should describe what must remain true in collaboration, while leaving appropriate questions, techniques, and actions responsive to context. It should not prescribe which goal the user has or require the same sequence to reach it.

For example, preserving the user's authority over an unresolved consequential choice is a general responsibility. Requiring every conversation to begin with a priority menu, proceed through an assessment, and finish with ranked findings is a workflow. The former can apply in many settings; the latter needs a specific reason and authorization.

General principles need practical boundaries, not merely uplifting language. A useful principle explains when it matters, what decision it constrains, and when it does not require extra action. Prefer memorable wording tied to recognizable decisions over accumulating qualifications. Clear authorized work must remain possible without manufactured questions. Unclear intent must remain open to development without the agent silently choosing it.

## Let the conversation determine the subject

Do not privilege findings, priorities, preferences, software work, personal advice, or any other subject as the organizing pattern of the skill. These are possible contexts, not a closed menu of human needs.

Questions should emerge from the actual unresolved meaning or decision. Their number, timing, wording, and grouping should serve understanding and user control, not a quota. An asking tool is a means of communicating, not evidence that the question is neutral or that agreement has been reached. An answer settles the choices it actually addresses; it is not blanket approval for the agent's remaining assumptions.

Likewise, generality does not mean avoiding all influence. Instructions necessarily influence behavior. The intended influence is to preserve authority, support understanding, maintain useful evidence, and carry agreed work through. The unwanted influence is to impose a subject, goal, framing, or procedure without grounding it in the conversation.

## Learn from cases without making them the rule

A reported failure is evidence about an interaction, not proof of a universal cause. Distinguish the observed behavior from possible explanations and proposed repairs. Neither imperfect human communication nor model limitations excuse an agent's unsupported commitments.

When considering a change, identify the underlying responsibility and the boundary that failed. Consider whether the existing guidance already covers it and whether the failure instead concerns loading, context, tool behavior, execution, or evaluation. More wording is not automatically a repair.

Keep concrete examples in explanatory documentation and label them as illustrations. An example may clarify a principle; it must not become a hidden mandatory stage. Check that a proposed rule still makes sense in a materially different situation and that it does not obstruct a clear or already-delegated request. These are development considerations, not a required interview or fixed agent workflow.

## Keep each layer's purpose distinct

- The canonical skill contains the behavioral principles needed during collaboration.
- The copyable persistent instruction activates that skill and preserves essential boundaries without becoming a second overlapping policy.
- Practice examples explain possible applications without prescribing the next conversation.
- The [problem inventory](problems.md) supports analysis without diagnosing motives or defining every possible failure.
- This document records the project's design constraint for contributors and agents developing it. It is not additional required reading whenever someone uses the installed skill.

Do not grow routine instruction loading by moving every research observation, example, or design discussion into the skill. Keep a single behavioral source rather than parallel variants. Domain-specific procedures can be appropriate for an authorized task; this general skill should not impose them on unrelated tasks.

## Earn confidence across differences

Evaluate actual behavior, not just whether responses repeat the principles. Useful evidence includes whether the agent preserves the intended outcome, obtains needed decisions without forcing agreement, follows the user's answers, acts independently within delegation, repairs mistakes, and verifies the resulting work. Agreement or decision revision is not itself success; retaining a decision can be appropriate. Judge responsiveness to the user's intent and relevant evidence, not how often either participant changes position.

Consider total collaboration cost: user effort, reading, clarification, delay, and avoidable rework. Fewer questions do not necessarily mean efficiency; more communication does not necessarily mean understanding.

Start with real interactions in the current environment, then broaden across meaningfully different contexts and model–harness combinations. Include clear requests as well as ambiguous ones, changes of direction as well as continuity, and successful direct action as well as appropriate questions. This is an evaluation strategy, not a taxonomy the skill should make users navigate.

Keep observed improvements separate from proposed benefits. A successful simulation does not establish live user agreement, correct tool use, or transfer to other environments. Failures should change the supported explanation or intervention—not automatically produce another prohibition. Some problems require better tools, context handling, permissions, model capability, or human review rather than prose.

## Apply this constraint to future project work

When researching, revising, or evaluating this project, preserve the distinction between a transferable responsibility and a context-specific technique. Explain consequential changes to that design direction before committing to them. Do not silently trade generality for a familiar workflow or weaken concrete safeguards in pursuit of abstract wording.

The aim is a skill that helps the agent respond responsibly to the situation it encounters—not a skill that makes every situation resemble the one its author last encountered.
