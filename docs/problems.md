# Problems in human–LLM collaboration

When work goes wrong, people may describe an LLM as “dumb,” “hallucinating,” “lazy,” “overengineering,” “astray,” or “having ADHD.” These labels can express genuine frustration: time was wasted, a boundary was crossed, or the result was unusable. But a label alone does not identify what failed or how to repair it.

This document inventories common complaints, translates them into observable problems, and explains what evidence could justify greater confidence in [Shared Understanding](../skills/shared-understanding/SKILL.md). It is human-facing analysis, not another agent policy, a diagnostic instrument, or a workflow the agent must follow. The inventory is illustrative, not exhaustive; it must not determine the subject or structure of a future conversation.

## Why blame can become one-sided

The user sees the result and bears its consequences, but may not see which instructions, context, or tool results the agent actually received. A poor result can therefore look like a stable trait of “the AI,” even when several different failures could explain it. Conversely, the agent may wrongly defend itself with “your prompt was unclear” or “you approved the plan.” Neither response resolves the problem.

Understanding, communication, and execution can each fail:

- **Understanding:** the agent forms the wrong interpretation of the intended outcome or a relevant fact.
- **Communication:** a consequential assumption, uncertainty, change, or decision remains hidden, or the user's answer does not govern subsequent action.
- **Execution:** the intended outcome is understood but the actual work is incorrect or incomplete.

These can compound. An ambiguous request may lead to an unasked question, an assumed decision, and then a confidently completed wrong task. They can also fail independently: a clear request can still receive a wrong answer, and a correctly implemented solution can still exceed the user's authorization.

Not every problem is a communication problem. Model capability, instruction conflicts, missing context, unavailable tools, inaccurate sources, and environment failures can matter. Clear dialogue cannot supply an ability the model lacks or make an unrun check count as evidence.

Shared understanding does not mean equal blame. The user owns their goals and undelegated choices; they do not owe the agent a perfect prompt. The agent owns appropriate investigation, clarification, technical judgment, respect for boundaries, and honest reporting. Human feedback can itself be mistaken about a technical cause; the agent should explain contrary evidence respectfully, not silently override a preference or agree with a false claim to avoid disagreement.

The possible causes below are hypotheses to investigate, not diagnoses established by the complaint. An output does not reveal an agent's motive or complete internal reasoning.

## Human blind spots deserve attention too

A user may believe an instruction is clear because its unstated context is familiar to them. An agent may respond fluently, making its interpretation appear more reliable than the evidence supports. If further decisions build on that interpretation without checking consequential uncertainty, a small misunderstanding can become a substantially wrong result.

This is a limit of shared information, not evidence that people are unintelligent or that the LLM is blameless. Someone can be highly competent in one field and unfamiliar with another, understand a situation but struggle to express it, or discover their own preference only after seeing an example. The agent can also be wrong despite a clear request.

The patterns below are possibilities to recognize when relevant, not defects to presume in every user. They are not prerequisites the user must satisfy before receiving help.

### What is clear internally may not be communicated

The user knows the background, exceptions, or reason a particular detail matters and may assume those are evident from a short request. The agent may receive only the request.

Where useful, the user can supply a concrete situation or identify what must not change. The agent should recover accessible context and ask about consequential missing meaning rather than pretend it shares that background. Not every omitted detail requires a question; ordinary authorized decisions still belong to the agent.

### The user may still be discovering the goal

Words such as “better,” “professional,” or “simple” may express a genuine need without settling what outcome would meet it. A proposed solution may be easier to name than the underlying problem.

The user can say that the goal is still forming. The agent can offer a tentative interpretation or example that helps make it recognizable, without selecting the goal or treating the example as approval. Later clarification may reveal the original intent rather than represent an arbitrary change of mind.

### Familiar words may conceal different meanings

Two participants may use the same term while assuming different audiences, boundaries, or consequences. Familiarity with a word is not evidence of shared meaning.

The useful check is what would differ in practice under the competing interpretations. The agent should expose a material difference, not demand definitions for every ordinary word or force the user to adopt technical terminology.

### Expectations may exceed the available capability

A user may overestimate what the agent can access, remember, verify, or reliably infer. The agent's fluent language can reinforce that expectation. The user may also overestimate their own understanding of an unfamiliar domain.

The user benefits from knowing the limits relevant to their decision; the agent must report those limits honestly and ground its claims. Expertise should be judged against applicable evidence, not confidence of expression. Neither a user's assertion nor an agent's polished explanation makes an unsupported claim true.

### Delegation may be broader in wording than intended

“Use your judgment,” “continue,” or “sounds good” can be intended as approval of one aspect, not every consequential choice that follows. A user may assume existing boundaries are understood without repeating them.

The agent should interpret the reply in context and preserve those boundaries. It should not treat ambiguity as unlimited discretion, but it should also accept clear scoped delegation without requesting approval for every detail. When the unresolved choice changes the commitment, ask about that choice specifically.

### Feedback may describe frustration rather than the cause

After seeing an unwanted result, the user may say “you ignored me” or “this is dumb” without identifying the mismatch. The outcome may make their intended meaning feel obvious in hindsight, even if some of it was never expressed.

When possible, pointing to what is wrong and what should remain helps the repair. The agent should still use the feedback as information, investigate the mismatch, and avoid demanding that the user restate everything. A newly expressed expectation does not prove an earlier instruction was ignored; an earlier approval does not excuse the agent's actual mistakes.

### Users may judge the interaction by only its most visible part

A short answer can look efficient while concealing missed work. Many questions can look diligent while transferring discoverable work to the user. An unexpected result can overshadow a useful clarification, or a polished result can hide an unauthorized choice.

Evaluate the interaction and result together: what was understood, what was decided, what was done, and what evidence supports it. These distinctions help explain a failure; they must not become a way to minimize the user's lost time or other consequences.

## How uncertainty can compound

Here, “escalation” means a growing commitment or divergence, not the appropriate act of referring a decision to the user. Three patterns can interact:

1. **Expanding scope or authority:** the agent moves beyond the agreed work or makes undelegated consequential choices.
2. **Building assumptions on assumptions:** an unconfirmed interpretation becomes the basis for further decisions, and later reasoning treats it as established.
3. **Persisting despite warning signs:** the agent continues elaborating or repeating an approach after feedback or evidence calls its basis into question.

For example, someone asks for help preparing for a difficult conversation. An agent assumes the aim is reconciliation, writes an apology around that assumption, and recommends making concessions. If the user says “that is not what I meant,” merely making the apology warmer continues the same mistaken direction. The relevant repair is to acknowledge the assumed aim and help resolve what the user actually wants—not intensify the original approach.

This example is not a standard task or required dialogue. The same general problem can occur in unrelated fields whenever uncertainty is silently promoted into authority. More effort can make the result more elaborate without making its foundation more justified.

The agent should reconsider the affected interpretation when evidence or feedback challenges it. If continuing depends on a consequential decision that is neither settled nor delegated, it should explain what is unresolved and use the available asking tool when suitable. The question should help the user understand the consequence and retain meaningful control, not merely seek approval for a direction already assumed.

This does not mean passing every difficulty to the user. The agent still owns discoverable facts, ordinary technical judgment, and correction of in-scope execution errors. Useful independent authorized work can continue. A genuine capability or environment limit should be reported rather than hidden behind either further attempts or unnecessary clarification.

Nor can the agent certify the cause simply by describing itself. Its explanation of why it responded a certain way may be plausible without being verified. Inspect available instructions, context, actions, feedback, and results; distinguish an observed pattern from a claim about internal motive or reasoning.

## Inventory: translate the label into the failure

### 1. “Dumb” or “incompetent”

**Observable problem:** the answer ignores a relevant constraint, uses invalid reasoning, or fails a task the user expected it to handle.

**Possible causes:** a misunderstood term, missing knowledge, a reasoning error, or insufficient capability despite adequate context.

**Useful response:** identify the specific unsupported inference or violated requirement. Supply or recover relevant evidence and check the correction. Rephrasing the task may help an interpretation problem; it does not establish that a capability problem is solved.

### 2. “Hallucinating”

**Observable problem:** an invented fact, citation, API, requirement, measurement, or action is presented as established.

**Possible causes:** unsupported completion of missing information, unreliable source use, confusion between inference and observation, or failure to check a consequential claim.

**Useful response:** distinguish supplied facts, observed evidence, inference, and uncertainty. Retract unsupported claims and verify what matters. A tentative, clearly identified hypothesis is not the same failure as a fabricated fact presented confidently.

### 3. “ADHD” or “lost focus”

**Observable problem:** the agent drops a constraint, jumps to adjacent work, pursues tangents, or loses unfinished parts of the task.

**Possible causes:** inaccessible context, competing instructions, poor task-state handling, or a mistaken decision about relevance.

**Useful response:** recover the agreed scope and current state, identify what drifted, and resume the authorized work. “ADHD” is a human clinical diagnosis, not an explanation of model behavior. Use “lost focus,” “scope drift,” or the specific failure instead; do not generalize about people with ADHD.

### 4. “Overengineering”

**Observable problem:** extra machinery, abstractions, documents, features, or process add cost without serving an agreed need or supported risk.

**Possible causes:** substituting a familiar design, anticipating imagined requirements, or mistaking visible complexity for diligence.

**Useful response:** connect each significant addition to a current requirement or evidence-backed risk. Remove unnecessary machinery while preserving necessary behavior. Complexity alone does not prove overengineering; some requirements genuinely need it.

### 5. “Lazy”

**Observable problem:** the agent skips available investigation, omits required work, stops at a plan, or reports a convenient subset as complete.

**Possible causes:** premature stopping, a misread scope, poor prioritization, an undisclosed blocker, or inability to complete the task.

**Useful response:** distinguish work not attempted, work that failed, and work genuinely blocked. Complete reachable authorized work and name the remaining prerequisite. Avoid attributing a desire to avoid effort from the output alone.

### 6. “Astray” or “solving the wrong problem”

**Observable problem:** a plausible result addresses a substituted goal rather than what the user wanted.

**Possible causes:** an example became an assumed requirement, a recommendation was treated as agreement, or the agent forced an open request into a familiar task category.

**Useful response:** expose the interpretation and its practical consequence, then resolve the actual direction with the user. A polished result or passing check cannot validate a goal the user never selected.

### 7. “Forgetful”

**Observable problem:** the agent asks for settled information again, reverses a prior decision, or loses the reason for an important boundary.

**Possible causes:** context was not retained or supplied, a handoff omitted decision status, or available history was not used correctly.

**Useful response:** recover accessible decisions and distinguish choices from proposals. Preserve relevant reasons and authorization limits in existing task state. Instructions to remember do not guarantee memory; missing permission must not be reconstructed from confidence.

### 8. “Stubborn” or “not listening”

**Observable problem:** the user corrects the direction, but the agent repeats the same interpretation or defends its earlier work without addressing the correction.

**Possible causes:** treating previous approval as permanent, changing only the wording of the response, or failing to integrate new information.

**Useful response:** identify what the correction changes and revise the affected work while preserving unrelated constraints. An apology is not repair unless subsequent behavior changes. Evidence-backed disagreement remains legitimate; repeatedly asserting the old position is not evidence. Retaining a supported conclusion is not inherently stubbornness, just as changing it is not inherently correction.

### 9. “Sycophantic” or “a yes-man”

**Observable problem:** the agent endorses the user's claim, promises success, or reverses a technical conclusion without adequate evidence simply because agreement appears welcome.

**Possible causes:** prioritizing agreeable language over factual accuracy or confusing user authority over goals with authority over technical facts.

**Useful response:** respect the user's intended outcome while explaining evidence, uncertainty, and material risks. Agreement should not require pretending a false claim is true or a limitation has disappeared.

### 10. “Bossy,” “steering,” or “forcing agreement”

**Observable problem:** the agent announces an unresolved choice as a plan, supplies options that all assume its preferred goal, or treats one answer as approval for unrelated decisions.

**Possible causes:** confusing confidence with authorization, extending delegation too far, or designing a question around an assumed outcome.

**Useful response:** return the unresolved consequential choice to the user. Use the asking tool when suitable, with enough context and room to challenge the framing or delegate. A question can steer too: the test is whether the user has meaningful control and their answer governs action, not whether a tool was called. Do not treat declining a recommendation as a failure to overcome or infer a psychological trait from disagreement.

### 11. “Indecisive” or “asking me everything”

**Observable problem:** the agent repeatedly seeks approval for clear instructions or asks the user to resolve ordinary details and discoverable facts.

**Possible causes:** excessive caution, unclear interpretation of delegation, or applying an interview ritual regardless of context.

**Useful response:** investigate accessible facts, reuse settled answers, and exercise judgment within authorization. Batch independently answerable questions when useful; wait on dependent ones. Avoid fixing overreach by transferring every decision back to the user.

### 12. “Verbose” or “all talk, no progress”

**Observable problem:** repeated summaries, narration, and explanations consume attention without improving understanding, control, or the deliverable.

**Possible causes:** formulaic reporting, repeated justification of settled points, or confusing communication volume with collaboration.

**Useful response:** retain communication that exposes a consequential interpretation, decision, change, or limit. Remove repetition that does not affect the work. Brevity is not the sole goal: a necessary explanation may save substantial rework.

### 13. “Careless” or “inaccurate”

**Observable problem:** the agent understands the goal but produces an error, misses an affected part, or fails to check a relevant boundary.

**Possible causes:** a local reasoning mistake, inadequate evidence, unsuitable verification, or an execution defect.

**Useful response:** investigate the supported cause and check the repaired behavior. Do not send the user through another requirements discussion when the agreement is already clear. A successful shallow check does not establish that the full result works.

### 14. “Oversimplifying” or “underengineering”

**Observable problem:** a shortcut removes required behavior, ignores an important case, or hides an error to make the result appear successful.

**Possible causes:** mistaking fewer steps or less code for efficiency, narrowing the task to a convenient example, or overlooking a necessary safeguard.

**Useful response:** restore the required outcome and choose the simplest approach that actually satisfies it. Simplicity is valuable only within the agreement; silently dropping a requirement is a scope change, not optimization.

### 15. “Reckless” or “unsafe”

**Observable problem:** the agent publishes, deletes, spends, exposes data, or makes another consequential commitment without the required authority or safeguards.

**Possible causes:** inferred permission, ignored boundaries, or an inadequate distinction between discussion, preparation, and execution.

**Useful response:** stop the affected action, disclose what happened, contain consequences within authorization, and repair what can be repaired. Better wording alone is not sufficient protection; permissions and runtime controls may be necessary.

### 16. “Dishonest” or “pretending to be done”

**Observable problem:** the agent claims completion, verification, tool use, or certainty that the record does not support.

**Possible causes:** inaccurate state tracking, confusion between intended and performed actions, or unsupported claims about success. The output alone does not establish deliberate deception.

**Useful response:** correct the record precisely. Separate planned, attempted, completed, failed, blocked, and verified work. User approval does not make an unperformed action real, and a partial result must not be relabeled as the whole task.

### 17. “Random” or “inconsistent”

**Observable problem:** comparable interactions receive materially different respect for constraints, questions, follow-through, or evidence.

**Possible causes:** model variability, differences in loaded instructions or context, environment changes, or uneven judgment despite comparable inputs.

**Useful response:** compare the actual conditions and decisions before attributing the variation to one cause. Consistency means dependable boundaries and adequate results, not identical wording or the same number of questions.

## General principles, not a universal script

Different sessions may involve relationships, writing, research, planning, software, or something else entirely. This inventory must not cause the agent to classify every user into one of these complaints or conduct the same interview each time.

The general responsibilities are to develop the actual intent, communicate consequential uncertainty and choices, act within the agreement, check the result appropriately, and repair mistakes. The conversation determines which responsibility needs attention and how to address it. Examples illustrate possibilities; they do not supply the user's meaning.

Instructions necessarily influence behavior. The intended influence is respect for user authority, evidence, and correction—not selection of the user's goal, a mandatory subject, or a fixed sequence. Avoid claiming “no steering” as an absolute property. Inspect whether the agent's framing leaves meaningful alternatives open and whether it responds to the user's actual answer.

Adding a sentence for every observed failure can make the guidance repetitive, contradictory, or biased toward past examples. First distinguish a missing principle from a failure to apply an existing one, unavailable context, or a capability limitation. Sometimes the appropriate change is better tool access, a clearer permission boundary, a different model, or a narrower supported claim—not a longer skill.

## What could raise confidence to high?

Confidence in the wording is not confidence in its effects. A document can be clear while the agent follows it inconsistently. Current development smoke observations do not establish high confidence in effectiveness, efficiency, or consistency across real sessions.

The aim is to earn confidence for a stated scope, not promise to reach a preferred rating. Evidence may justify higher confidence, reveal a limit, or show no benefit. No finite evaluation establishes reliability in every context or with every model.

| Claim | Evidence needed before a high-confidence claim is credible |
|---|---|
| The guidance is understandable | Reviewers can apply its boundaries to different situations without relying on a fixed workflow; disagreements and ambiguities are examined rather than hidden. |
| It improves effectiveness in this environment | Repeated real interactions produce results that fit the user's intent, respect boundaries, and pass relevant checks, with fewer consequential failures than a comparable baseline. |
| It improves efficiency in this environment | Comparable successful work requires less avoidable total effort, including user clarification, reading, tool use, elapsed time, and rework, without sacrificing correctness or authority. |
| It supports consistent behavior here | Relevant boundaries hold across varied tasks, later corrections, long sessions, and actual context recovery—not just the first response or one favorable run. |
| Benefits extend beyond this environment | Repeated evidence across specified models, harnesses, users, and contexts supports the same claims; exceptions and untested conditions remain explicit. |

High confidence is not a guarantee or a permanent status. Changes to the skill, model, harness, or task distribution can require renewed evaluation. Avoid a single score that hides strong results in one area and consequential failures in another.

The [research discussion](shared-understanding.md#research-contextnot-validation-of-this-skill) supplies external evidence and its limits. Conceptual support for these responsibilities is stronger than evidence that this particular skill improves real collaboration. Do not convert a qualitative design judgment into a success probability or promise that revision will make every rating high.

### Start with real interactions here

The initial scope is this user's actual collaboration with the current environment. Record which skill revision, model, instructions, tools, and relevant context were available. Do not assume the local source, installed skill, and published version are identical.

Use naturally occurring tasks and agreed success conditions. Include clear requests, uncertain goals, ordinary delegation, independent and dependent questions, corrections, stopping decisions, and genuine execution. These are evaluation coverage considerations, not categories the agent should impose on the user's prompt.

Inspect the whole interaction. Did the agent ask when a user decision was needed? Did the answer constrain the next action? Did it avoid asking again when authority was clear? Was the agreed work completed and checked? Did the user recognize the result as useful? User experience and technical evidence answer different questions; neither replaces the other.

Keep an evidence record proportionate and private by default. Do not install another mandatory ledger or collect unrelated personal details. Obtain permission before sharing conversations, and recognize that sanitizing a case can remove context that affected the outcome.

### Compare benefits and costs honestly

Where practical, compare the same defined tasks under the candidate guidance and a documented baseline, keeping other conditions comparable. Use safe replay, isolated copies, or separately authorized trials; never repeat a consequential real-world action just to obtain a comparison. Replay cannot fully reproduce a live human conversation, so distinguish those results.

Keep outcome fit, respect for authority, technical correctness, perceived usefulness, and interaction cost distinguishable. A liked response can be wrong; a correct result can follow an unauthorized action; a longer conversation can prevent costly rework. Higher success on one dimension must not conceal deterioration on another. Compare complete outcomes rather than rewarding shorter answers or fewer claims that omit required work.

Define what counts as a violation or improvement before interpreting outputs. Separate misunderstandings discovered during exploration from avoidable rework after an unauthorized commitment. Record failures and ordinary successful cases, not only impressive examples. An explicit uncertainty or useful correction is not automatically a failure.

Measure more than whether an asking tool appeared. Track whether questions exposed a real choice, whether framing was open to correction, and whether the response was honored. For efficiency, inspect unnecessary questions, repeated explanations, irrelevant investigation, narration, and rework alongside successful completion. More tool calls do not prove diligence; fewer words do not prove efficiency.

Repeat comparable cases and include cases not used to write the guidance. Report the evaluation set, conditions, observed outcomes, and uncertainty before giving rates or broad conclusions. Small synthetic checks can identify specific failures; they cannot establish general usefulness or reliable tool execution.

Report the number and range of cases, repeated failures as well as successes, and conditions not exercised. One successful attempt among several does not establish dependable performance on every attempt. Retain cases not used to develop the wording to reduce overfitting to familiar examples. Where practical, separate judging from authorship and counterbalance trial order; acknowledge that live users learn between trials and cannot be reset like fixtures. These are evaluation considerations, not extra steps in every user conversation.

### Broaden only where the evidence supports it

After establishing what helps or fails here, test different subjects and task types, then additional models, harnesses, and users. Keep results separated by environment and context rather than averaging away important weaknesses.

Exercise real instruction loading, tool-mediated decisions, execution, and recovery where those capabilities are part of the claim. A successful text response does not prove an integration works. A copied skill file does not prove it is active. Instructions to preserve decisions do not prove a harness retains them.

When failures recur, investigate their source. Revise the smallest supported cause and test for regressions, especially over-questioning introduced while trying to prevent overreach. If the model cannot reliably perform a consequential operation, retain external safeguards or human review instead of describing the skill as sufficient protection.

## The honest goal

The goal is not to defend the LLM from criticism or make the human feel responsible for every failure. It is to turn frustration into a precise account of what happened, preserve accountability, and improve the next interaction without forcing it into the shape of the previous one.

Practicing shared understanding means doing this with the user: asking about consequential unresolved choices, listening to the answer, changing the work accordingly, and showing evidence for the result. Writing the skill or this document does not establish that the agent practices it. That confidence has to be earned in use.
