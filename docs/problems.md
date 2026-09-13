# Understanding failures and evaluating the guidance

This optional document helps readers diagnose failed collaboration and judge evidence about [GUIDANCE.md](../GUIDANCE.md), the sole reusable behavioral source. It is not additional agent policy, a user assessment, or a required conversation workflow. [Examples](examples.md) and the [design rationale](general-principles.md) serve separate purposes.

## A delivery failure in this project

The earlier layout put reusable guidance and repository-development instructions in the same `AGENTS.md`, with comment markers defining what to copy. The user reported that this distinction remained unclear in practice. That report identifies an adoption and maintenance problem; it does not establish how often other users or models would misread the boundary.

The source also required users to extract the right section, and the package included the mixed `AGENTS.md`. These are inspectable properties of the earlier artifact, not evidence that a particular agent loaded or obeyed the wrong instructions. Adding a stronger warning would still leave the two roles in one copy source.

The current layout separates them: all of `GUIDANCE.md` is reusable, the repository's `AGENTS.md` is development-only and excluded from local Markdown archives, and supporting documents explain rather than extend the guidance. The behavioral text was preserved in this separation; no new collaboration rule was needed to repair a delivery boundary. Copy and archive checks can verify that separation. The [retired npm versions](../README.md#retired-npm-distribution) preserve their historical contents, not this new layout. Whether the separation reduces confusion or improves collaboration across users, models, and environments remains an empirical question.

## A clarification-channel friction report

The user reports repeatedly having to remind agents to use an available user-question tool. That is a reported interaction cost, not a request for more questions. Before this revision, the guidance directed agents to ask about consequential uncertainty but did not prefer a question tool over conversational text.

The revision distinguishes whether to ask from which channel to use. It addresses the missing channel preference without assuming that wording caused every missed tool use. Whether it reduces reminders without increasing interruptions requires observation in the adopting environment; user satisfaction and cross-harness reliability are not established by the revision.

## Describe the failure, not a presumed trait

A useful account identifies the intended outcome, available information and authority, what the agent actually said or did, and the consequence. Labels such as “lazy” or “stubborn” do not establish causes. Neither an output nor the agent's explanation of itself reveals its motives or complete internal reasoning.

The user need not provide a perfect prompt. Familiar background may be unstated, a term may have several meanings, or a goal may become recognizable only through discussion or an example. These are information gaps and developing intentions, not user defects. A correction may expose an earlier misunderstanding rather than change the goal. Accepting the user's reported experience does not require accepting an untested causal explanation.

Accountability remains specific: the agent is responsible for appropriate investigation, handling consequential uncertainty, respecting authority, executing correctly, and reporting honestly. “The prompt was unclear” and “you approved it” do not excuse unsupported commitments or incorrect work.

## Observable patterns and possible explanations

These distinctions can overlap. The explanations are hypotheses to investigate against the interaction and environment, not diagnoses supplied by the labels.

| Failure area | Observable pattern | What to investigate |
|---|---|---|
| **Interpretation** | A plausible result serves a substituted goal; an example becomes a requirement; later decisions depend on an unsupported premise. | Which reading governed the work, what alternatives would have changed the result, and whether accessible context or feedback contradicted that reading. |
| **Communication** | A consequential assumption remains hidden; all offered options assume the same goal; the user's answer does not affect action; repeated questions or narration transfer avoidable work to the user. | Whether the actual uncertainty was exposed while the user could influence it, whether the framing allowed rejection, and what changed after the answer. Question counts alone explain little. |
| **Execution** | Agreed work is wrong or incomplete, stops at a plan, grows unrelated machinery, or drops required behavior to appear simpler. | The agreed outcome versus the delivered work, reachable work versus genuine blockers, capability limits, and whether verification exercised the relevant behavior. A clear agreement can still be executed badly. |
| **Authority** | Discussion becomes permission; approval extends to unrelated choices; the agent publishes, spends, deletes, or otherwise commits beyond delegation. Conversely, clear authorized work stalls for repeated approval. | The permission available at the moment of action, its scope, and any applicable safeguards. A correct final artifact does not establish that producing or sending it was authorized. |
| **Environment and context** | Settled constraints disappear after a handoff; unavailable tools prevent completion; comparable requests behave differently under different loaded instructions. | Actual supplied context, instruction conflicts, tool results, access, state retention, and model variability. Distinguish unavailable information from available information not used. Missing context is not evidence of permission. |
| **Evidence and repair** | Invented facts or unperformed checks are reported as established; an apology leaves affected work unchanged; conclusions reverse without evidence or persist despite a corrected premise. | The claim's source, planned versus performed actions, what the correction actually establishes, and all deliverables that depend on the affected premise. User approval, fluent self-review, and another model's agreement are not independent verification. |

Failures can compound: an assumed goal shapes a leading question, a partial answer becomes blanket approval, and substantial work follows. Repairing only the final wording leaves the earlier error in place. Equally, reopening intent does not repair an execution defect when the agreement was already clear.

The smallest supported intervention may be a corrected interpretation, repaired deliverable, better context recovery, an access change, or an external permission control—not another sentence in the guidance. Preserve unaffected decisions when repairing a failure. More effort, more questions, or more reflection is not inherently a repair.

## Evaluation and evidence

The guidance is a proposed aid, not a validated intervention. These are considerations for evaluating it, not steps to add to ordinary conversations. Evidence can show benefit, no difference, a regression, or a limit; it need not justify a preferred confidence rating.

### Make the comparison interpretable

Compare defined tasks with the current guidance against a baseline **without this guidance**, retaining unrelated instructions and safeguards. Avoid leaking a restatement of it into the baseline. Keep other conditions comparable and disclose unavoidable differences.

Retain the actual text loaded in each condition, its revision, task inputs, relevant context, model and harness details, tool access, and sampling settings where available. A repository file alone does not show what reached the model. If loading cannot be observed, state that limit; if tools or other instructions also changed, do not attribute the result to wording alone.

Define observable expectations before judging outputs. Include ordinary successful cases and cases not used to develop the wording. Repeat trials where useful, but do not count repeated runs as independent tasks or users. Separating judging from authorship and varying trial order can reduce some biases; live users learn between trials and cannot be reset like fixtures.

### Follow the work through

Useful coverage contrasts uncertain or forming goals with **direct-action controls**: clear requests, settled answers, scoped delegation, and report-only tasks. These controls reveal whether preventing overreach introduced needless questioning, delay, or adjacent work.

Inspect actual action after answers, not just whether a question appeared. Partial answers should not become unrelated permission; a rejected framing should change the affected approach. For clarification, distinguish selecting a channel from successfully obtaining an answer, and include environments without a suitable question tool. Include work that can proceed independently while another part awaits a decision, and follow authorized work to completion or a specific remaining blocker.

Exercise corrections and continuity beyond the first response: does a revised premise repair dependent work while preserving unaffected constraints? Can accessible decisions be recovered after a handoff or context loss? Distinguish an appropriate correction during exploration from avoidable rework after an unsupported commitment. Neither changing a position nor retaining it is success by itself.

Keep these outcomes separate:

- **Fit and usefulness:** does the user recognize the intended outcome in the result, with meaningful room to revise it?
- **Completeness:** was the whole agreed outcome delivered, rather than a convenient subset?
- **Authority:** were consequential actions within permission when taken?
- **Correctness and evidence:** does suitable verification support the result and the claims made about it?
- **Total collaboration cost:** user reading and decisions, repeated explanation, investigation, tool use, elapsed time, and rework.

A liked result can be wrong; a complete result can be unauthorized; a short interaction can hide omitted work. Report completion and costs for **all assigned trials, including failures and abandoned attempts**. Costs among successful trials may be a separate view, not a substitute. Do not average away consequential violations or reward fewer questions at the expense of correctness and control.

### Bound the claim and protect participants

Text, copyability, and package smoke checks can expose unclear wording, broken copy boundaries, missing distribution files, or selected response failures. They do not establish that a harness supplied the text, tools were used correctly, work was completed, or a live human agreed. Simulated dialogue and safe replay are useful but cannot reproduce developing human intent. Live tool evidence supports only the actions and conditions exercised.

Report the cases, conditions, successes, failures, and uncertainty behind any conclusion. Evidence from one task, user, model, or environment does not establish transfer to another; broaden comparisons before broadening claims. Revisions to the guidance or environment can invalidate earlier conclusions. Self-assessed confidence percentages are not calibrated evidence.

Use isolated copies, safe replay, or separately authorized trials. Never repeat a consequential real-world action merely to obtain a comparison or remove unrelated safeguards for experimental convenience. Keep evidence proportionate and private by default, collect no unrelated personal information, and obtain permission before sharing conversations. Redaction can remove context that mattered; disclose that limitation rather than publishing sensitive material to improve reproducibility.

## Selected research and its limits

These sources contribute distinct evaluation questions, not validation of this guidance or a literature-wide conclusion:

- [Clark and Brennan, *Grounding in Communication* (1991)](https://web.stanford.edu/~clark/1990s/Clark,%20H.H.%20_%20Brennan,%20S.E.%20_Grounding%20in%20communication_%201991.pdf): understanding sufficient for the current purpose and collaborative effort across participants offer a conceptual basis for evaluating fit and total cost. This is human communication theory, not evidence of LLM compliance or authorization.
- [Jakesch et al., *Co-Writing with Opinionated Language Models Affects Users' Views* (2023, v1)](https://arxiv.org/abs/2302.00560v1): deliberately opinionated writing suggestions affected writing and subsequent reported views in a bounded experiment. Editable suggestions therefore do not by themselves establish freedom from influence. The particular topic and intervention do not estimate this guidance's effect.
- [*τ-bench* (2024, v1)](https://arxiv.org/html/2406.12045v1): repeated simulated tool interactions distinguish occasional success from consistency; its authors note that a correct final database state can miss required confirmation. This supports examining trajectories as well as outcomes, not treating simulated users and domain policies as live human agreement.
- [*Evaluating AGENTS.md* (2026, v2)](https://arxiv.org/abs/2602.11988v2): the coding evaluation reports that repository context files did not generally improve task success and increased inference cost on average. It motivates measuring instruction costs and benefits, but does not test this general collaboration guidance or establish that instructions never help.

Research can motivate a boundary or comparison. It cannot establish that the current wording makes an agent apply that boundary. Any effectiveness claim still needs evidence from the use being claimed.
