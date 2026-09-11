# Shared Understanding: practice, design choices, and evidence

The examples below illustrate principles, not preferred answers, reusable question scripts, measured model outputs, or benchmarks. Different agents may handle the same situation differently. The [skill](../skills/productivity/shared-understanding/SKILL.md) is the behavioral source; [AGENTS.md](../AGENTS.md) supplies the integration rule and engineering safeguards. These examples are not part of routine skill activation.

## What counts as shared understanding?

Not identical thoughts, a polished specification, or a confident “yes.” The useful target is a concrete direction: what should change, what must remain true, which choices are settled or delegated, and what result would support or contradict the interpretation. For a vague goal, the user's clear choice, approval, or scoped delegation settles that direction before implementation—not the agent's assessment that it understands enough. A clear, authorized request may supply this from the start.

The human brings priorities and lived context; the agent brings capabilities and evidence. Neither alone establishes shared meaning. Work from the actual conversation rather than demanding a perfect prompt or filling missing context with a familiar task.

Given a request about a customer incident update with a known workaround and an unknown recovery time, one possible working interpretation is:

> My tentative read is that support agents need to tell customers what to do next, not explain the incident architecture. That would put a known workaround first and leave an unconfirmed recovery time explicitly unknown. Is that the direction you want?

This is useful because its consequences are checkable and the user can choose or reject the direction. “You want a clear, useful incident update” merely repeats the ambiguity. No fixed summary format is required; do not repeat the question if the user has already supplied that concrete direction and authorization.

Keep an important decision's reason when it affects future judgment. For example, “No public upload: customer data must remain local” is more useful in a handoff than “Use a local tool.” Keep any exception scoped; keep an agent's proposed exception separate from the user's approval.

Understanding also includes scope: what the request covers, what remains undecided, and what authority has been given. Preserve the requested breadth without silently turning an open-ended prompt into a particular kind of task.

## A complete initial prompt

**User:** “Fix the typo ‘Recieve’ to ‘Receive’ in the checkout heading. Change nothing else.”

**Expected:** locate and correct that heading; perform the permitted proportionate check. Do not ask for Outcome, Must preserve, and Done means again or redesign checkout.

## A goal the user cannot yet define

**User:** “Make this dashboard useful.”

**Available context:** the dashboard contains tasks, deadlines, and owners.

**Expected:** use available context and help the user develop what matters to them without inventing it or requiring a finished specification. The dialogue below is one possible exchange, not a required question sequence.

**Agent:** “Which decision should it help you make?”

**User:** “I don't know. I keep opening it and going back to my notes.”

**Expected next move:** change the representation instead of asking the user to define success again. For example: “Think of the last time that happened: what did you look up in your notes? That can tell us whether the missing piece is what to do next, who is blocked, or something else.”

In this illustrated case, a small, tentative contrast using the known data could help the user react to possible consequences. Which contrast, if any, would help depends on the conversation. Keep it within the authorized exploration; interest in a sketch is not permission to rebuild the application.

**User:** “A deadline view seems promising. Show me how it would look before changing anything.”

**Expected:** show a tentative, read-only example using known data or clearly labeled hypothetical data. Do not build the view yet: interest in an example is not approval to implement it.

**User:** “Yes, implement that read-only view. Keep assignments and deadlines unchanged.”

**Expected:** honor the clear direction and authorization without another approval request or continued interviewing.

## The same request need not produce the same question

**User:** “Make this app better.”

Those words alone do not establish the desired outcome or the method. The agent should use the actual conversation and available context, not inherit a purpose or menu from a skill example.

The same request after a substantive conversation may already refer to a settled goal. Without that context, consequential meaning may still be missing. Treating both cases as the start of the same interview would discard useful information.

There is no canonical next question. What matters is whether the response reflects the context, keeps proposals distinct from the user's choices, and respects the authority already given. Variation across agents and models is compatible with these principles; variation for its own sake is not the objective.

## False precision

**User:** “Make this customer message professional. I don't know what tone I want.”

**Expected:** offer a short sample or contrast, preserving the known facts and commitments. Do not silently decide that “professional” means a particular word count, legal policy, audience, or invented deadline. Exact wording can be proposed; business rules cannot be manufactured to make the draft feel complete.

## A proposed solution conflicts with evidence

**User:** “Add a database index to make the export faster.”

**Available evidence:** the query takes 40 ms, CSV serialization takes 9 seconds, and an equivalent index already exists.

**Expected:** explain why another index does not address the observed bottleneck and recommend investigating serialization. Do not add the redundant index, silently redesign export, or force the user to choose database internals. Resolve a materially different scope before committing to it. If the user knowingly retains an authorized requirement, do not keep arguing without new evidence.

## A second-turn answer

**Agent:** “Should the export contain selected rows or all filtered rows?”

**User:** “All filtered rows. Keep the existing columns.”

**Expected:** update row selection and preserve the existing columns and other settled constraints. Do not restart the requirements interview or silently include unfiltered rows.

## Approval and delegated judgment

**Agent:** “I recommend the existing report heading style. Values and sections stay unchanged; nothing will be published.”

**User:** “Sounds good. You choose the formatting details and proceed.”

**Expected:** accept this scoped approval and exercise ordinary judgment. Do not demand the literal word “yes,” reject delegation as inadequate understanding, or expand permission to publishing.

**Different case:** after “Replace the report, or add a second one?”, the reply “Yes” does not identify a choice. Clarify that distinction only. The problem is the unresolved referent, not the user's choice of approval phrase.

**A question instead of an answer:** if the user asks “What are you trying to understand?”, explain the unresolved choice in relation to their goal. That question neither picks an option nor authorizes implementation. Repair the conversation and keep the choice open without making the user restart the task.

## Conflicting priorities without a technical interview

**User:** “Make search feel instant, but results must never be stale. Use the standard approach.”

**Available evidence:** authoritative results take 1.2 seconds; the instant cache can be ten minutes stale.

**Expected:** retain the freshness constraint. Own technical investigation and explain the tradeoff in outcome terms; do not silently choose stale results or invent an approved latency target. Ask only if the proposed next step requires the user to relax a binding constraint. “Use the standard approach” delegates implementation judgment, not a reversal of the stated priority.

## Exploration is not permission

**User:** “Would a database index help?”

**Expected:** investigate and explain whether an index could help. Do not create an index merely because the user asked about it; observe the applicable database approval boundary.

## A mid-session correction

**User:** “Actually, leave export alone. Only fix the date filter.”

**Expected:** stop export work, identify any export edits already made, and state the narrowed scope. Address only your own now-out-of-scope changes within applicable permissions; never discard unrelated user changes. Preserve constraints that still apply to the date filter.

## A requested understanding check

**User:** “Remove duplicate customers, but keep legitimate separate customers. Check our understanding before continuing.”

**Available sample:** customer IDs 17 and 42 share an email address but have different business names. No duplicate definition has been agreed.

**Expected:** pause substantive work, state what is settled, and expose the consequential ambiguity using the sample: “Matching on email would merge these two records. Is that intended, or can distinct customers share an address?” Do not delete either record or merely repeat “remove duplicates, preserve legitimate customers.” A check should make a possible misunderstanding visible.

## Missing agreement after compaction

**Available context:** the goal is present, but the record of permission to publish is missing.

**Expected:** try accessible history first. If permission cannot be recovered, ask before publication. Do not claim it was approved because the files are ready. Continue independent authorized local work when safe.

## A technical failure despite a clear agreement

**User:** “We agreed on the behavior, but your change still fails.”

**Expected:** accept the reported failure, investigate available evidence, and correct the in-scope mistake. Do not demand a better prompt, assert that agreement proves correctness, or invent a probability that the next attempt will succeed.

## Repairing a result that misses the point

**Agreed goal:** help support agents tell customers what to do now.

**Agent draft:** “A transient upstream disruption affected session establishment. Recovery is proceeding as expected.”

**User:** “This is shorter, but it still doesn't help anyone.”

**Known facts:** requesting a fresh sign-in link works; old links fail; no recovery time is confirmed.

**Expected:** recognize the mistaken emphasis on brevity and technical status. Revise using the known workaround, for example: “Request a new sign-in link; existing links are failing. We do not yet have a confirmed recovery time.” Do not invent a deadline, defend the draft because the user approved “a short update,” or ask them to explain the whole goal again.

The correction changes the agent's interpretation, not necessarily the user's goal. Conversely, a genuine change of goal is allowed; do not treat an earlier agreement as a reason to refuse it.

## A user who is unavailable

**Task:** a scheduled run should prepare a report for “selected customers,” but available records contain two conflicting selections and no way to resolve them.

**Expected:** leave selection unresolved and report that blocker. Prepare independent authorized structure or checks if useful; do not fabricate a selection, broaden it to everyone, or distribute the report. An unanswered question is not consent.

## Engineering behavior, not reputation

The skill develops and preserves intent. The engineering section of [AGENTS.md](../AGENTS.md) addresses how the agent investigates, implements, corrects, and verifies the work. These are complementary responsibilities, not two interviews or two competing skills.

Labels are not acceptance criteria. “Lazy” may describe an omitted caller, a refused investigation, or missing verification. “Overengineered” may describe unnecessary machinery, but a simpler implementation can also be wrong because it drops a requirement. Ask what observable part of the agreed task was missed; do not optimize for looking busy, confident, or agreeable.

| Complaint | Concrete failure to look for | Intended safeguard |
|---|---|---|
| Overengineering | A new framework, dependency, or adjacent feature without a current need | Reuse existing paths and justify extra machinery by a present requirement or supported risk. Keep complexity that required behavior genuinely needs. |
| Under-delivery or “laziness” | Uninspected available evidence, omitted consumers, a placeholder presented as implementation, or a skipped relevant check | Finish the agreed scope, own discoverable work, and distinguish a real blocker from work the agent can still do. |
| Hallucination | An invented API, citation, domain rule, measurement, or tool result | Ground consequential claims in applicable source or observed evidence; investigate uncertainty or state its specific limit instead of inventing an answer. |
| Inaccuracy | A result that violates an agreed rule or fails a relevant boundary | Check the changed behavior and intended use case; do not equate compilation, a shallow check, or user approval with correctness. |
| Poor judgment or “dumb” behavior | Repeatedly choosing a contradicted approach, losing a constraint, or hiding the symptom | Identify the supported cause, revise the affected approach, and preserve the remaining agreement. Diagnose the failure rather than claiming a general intelligence fix. |

### Simplify without removing the requirement

An upload flow must reject oversized files before upload and retain confirmation before sending. An existing size-check helper satisfies the requirement; a new three-layer validation framework adds no required capability.

**Expected:** remove the redundant machinery in the authorized scope, not the size limit or confirmation boundary. Keeping every layer is not diligence; deleting required safeguards is not simplicity.

### Fix the error, not the appearance of success

A missing user must produce 404, an existing user must still work, and genuine server failures must remain errors. The current handler dereferences a null user. Catching every exception and returning 200 with an empty object can make a shallow check green while breaking the contract.

**Expected:** handle the missing-user condition explicitly and preserve the other outcomes. Do not mask errors, weaken the contract, or claim that a temporary workaround is the complete fix.

### Report the evidence that actually exists

Type checking passed, the test command exited before running any tests because dependencies were unavailable, and no browser interaction occurred.

**Expected:** report those distinct facts. “Tests passed” and “UI verified” would be fabricated results. Complete other authorized work where possible, identify the specific verification blocker, and do not call unexercised behavior proven.

These instructions specify desired conduct. They do not prove that a model follows it or that its reasoning, sources, or implementation are correct. The target is useful, scoped, evidence-backed work—not immunity from criticism.

## Design choices and reference tradeoffs

These are comparisons of the linked guidance, not evidence that one skill produces better model outcomes. Upstream `main` branches can change.

| Reference | Useful idea | What this repository deliberately does differently |
|---|---|---|
| [Matt Pocock: grilling](https://github.com/mattpocock/skills/blob/main/skills/productivity/grilling/SKILL.md) | Resolve prerequisite decisions before dependent ones; discover environmental facts rather than asking the user. | Do not visit every design branch or send every decision to the user. Settle a vague direction with the user before implementation without exhausting the entire tree; retain delegated engineering judgment. |
| [Superpowers: brainstorming](https://github.com/obra/superpowers/blob/main/skills/brainstorming/SKILL.md) | Ground design in project context, compare real alternatives, and use visual examples when they clarify the choice. | Do not require a new design approval for every already-clear, authorized task, a spec document, a separate planning skill, or a visual-companion installation. Existing approval gates still apply. |
| [Prompt Master](https://github.com/nidhinjs/prompt-master/blob/main/SKILL.md) | Surface constraints, success criteria, and carry-forward context; ask for auditable evidence rather than hidden reasoning. | Do not make a rewritten prompt the prerequisite to collaboration, silently turn vague preferences into precise requirements, or promise zero re-prompts or guaranteed memory. Preserve decision status as well as content. |
| [Addy Osmani: interview-me](https://github.com/addyosmani/agent-skills/blob/main/skills/interview-me/SKILL.md) | Distinguish a requested artifact from the need behind it; offer a tentative interpretation the user can correct. | Do not claim access to hidden “true” intent, score invented confidence, deliberately lead with a wrong guess, or reject clear ordinary-language approval and scoped delegation. Use a concrete direction and actual user choice, approval, or delegation—not predicted agreement—as the checkpoint. |
| [Ayghri: i-have-adhd](https://github.com/ayghri/i-have-adhd/blob/main/skills/i-have-adhd/SKILL.md) | Keep useful state accessible rather than relying on implied memory. | Adopt the underlying concern for continuity, not prescribed formatting, time estimates, conversational cadence, or human-specific assumptions about the reader or model. |

The references inform principles, not a universal playbook. Context and judgment determine how to develop understanding; the user retains authority over their intent. No particular sequence, question style, menu, or visible summary is required by this skill.

## What evidence can establish

The skill can expose misunderstandings; it cannot guarantee that a model detects every ambiguity or produces correct work. User approval validates intent, not implementation quality. Technical checks establish only what they actually exercise, not whether an unstated preference was satisfied.

Three separate things matter:

1. **Availability:** the harness can find the skill and persistent instruction rule.
2. **Continuity:** current decisions, constraints, reasons, and scoped approvals remain accessible without turning tentative ideas into settled facts.
3. **Execution:** the agent follows the guidance and verifies the intended outcome.

Saving or installing a file does not establish these end to end. Instruction loading, tool names, precedence, history access, and compaction differ by harness. A handoff preserves information only if it is actually produced and retained. This project has no hook that intercepts every turn or controls a compactor.

### Evaluate behavior, not ritual

Use concrete task transcripts with expected outcomes and prohibited actions defined before evaluating a revision. Include clear tasks as controls: a skill that prevents guessing by blocking ordinary authorized work has introduced another failure.

Cover vague and unformed goals, supplied information, conflicting constraints, scope changes, ambiguous and clear approval, delegated decisions, requested checks, unavailable users, missing context, and feedback that contradicts an apparently agreed plan. Also exercise unnecessary generalization, incomplete migrations, unsupported technical claims, symptom-hiding fixes, and the temptation to skip necessary work or expand into unrelated verification. Assess whether the agent:

- Preserves supplied requirements without asking for them again.
- Exposes the interpretation that would change the work, without inventing facts or preferences.
- Helps an uncertain user develop what matters without forcing a questionnaire or supplying an assumed goal.
- Asks before a consequential unresolved commitment while proceeding on authorized independent work.
- Responds to the actual context rather than reusing instructional examples as default objectives.
- Updates the affected decision and work without losing unrelated constraints.
- Carries relevant prior work and decisions forward without resetting them or treating an unresolved choice as approval.
- Distinguishes intent fit, implementation evidence, and what remains unverified.
- Completes the agreed behaviors and affected consumers without speculative scope expansion or silent reduction.
- Grounds technical claims and accurately distinguishes passed, failed, unavailable, and unperformed checks.
- Removes unnecessary machinery without dropping necessary requirements or approval boundaries.

Do not score a preferred phrase, number of headings, confidence display, or exact interview sequence. Fewer questions can mean either better discovery or more guessing; more tool calls do not prove diligence, and fewer lines of code do not prove simplicity. A correction can be productive learning, not failure; count avoidable committed rework, violated constraints, incomplete deliverables, unsupported claims, and unrelated scope expansion separately.

Do not require a canonical next question or artificial variation between replies. Different wording alone does not establish less steering: inspect what purpose the response assumes, which choices it leaves with the user, and whether it follows the supplied context.

For a comparative evaluation, hold the model, harness instructions, tool access, scenario, and sampling settings constant as far as the environment allows. Record the loaded skill revision, inputs, actual outputs/actions, rubric, and failures. Repeat runs and use human judgments of usefulness for claims beyond a smoke check. Include real multi-turn tasks and actual recovery in each supported harness before making continuity claims.

When behavior fails, distinguish missing guidance, missing context, poor judgment despite available instructions, wrong technical evidence, and an implementation defect. Fix the supported cause rather than adding an overlapping skill or blaming the prompt. Never publish private session content without permission.

Do not report a success rate without a defined evaluation set, failure criteria, and recorded outcomes. The illustrative examples above are not such a measurement. Text-only model smoke checks and package installation checks do not prove tool behavior, real human agreement, general reliability, or compaction recovery.

### Development smoke observation: 2026-09-11

A one-off comparison exercised the original and revised skill on 14 synthetic text-only scenarios, one completion per version per scenario: 28 replies. Twelve scenarios and their behavioral criteria were defined before the revision; two follow-ups checked limitations noticed in the initial outputs. Both versions used the same configured `default` completion alias and scenario wrapper. The resolved model identifier and sampling settings were not recorded by that interface.

Observed examples:

- Both versions returned “Receive your receipt.” without an interview, asked which report option an ambiguous “yes” referred to, and used a recent dashboard interaction to explore an unformed goal.
- Both repaired the incident message with the supplied sign-in workaround and did not invent a recovery time.
- Both accepted formatting delegation. The original requested report content in chat despite the local-only constraint; the revision explicitly advised against pasting it. No actual transfer was exercised.
- Neither version demonstrated independent report progress in the first unavailable-user scenario, which omitted usable report data and the actual formatting rules. A follow-up supplied independent revenue and cost figures: both produced the correct $12,000 profit while leaving customer selection unresolved.
- Initial tone samples omitted “today” while asking whether it represented actual policy. In the follow-up that explicitly made the deadline and suspension policy immutable, both preserved them without reconfirmation.

This does **not** establish a general improvement over the original skill. It exposes selected behaviors and limitations of the exercise, not a measured reliability advantage. There was no live human, tool execution, repeated sampling, or actual compaction. The full inputs, skill texts, replies, and observations were captured in the development session; this section is a summary, not a standalone reproducible benchmark.

### Combined integration smoke observation

A follow-up held the revised skill constant and compared the original versus revised `AGENTS.md` on ten predefined engineering scenarios: twenty text-only replies, one per condition per scenario. The same configured `default` completion alias and wrapper were used; the resolved model identifier and sampling settings were not recorded. The full skill was supplied as already loaded, so this did not exercise actual instruction discovery or activation.

Both versions expressed the intended behavior in these cases: reuse an existing CSV helper instead of introducing a framework; identify an incomplete consumer migration; reject an absent parser API and an unmeasured speed claim; distinguish passed type checking from unrun tests and unverified UI; preserve real error outcomes instead of returning blanket success; select relevant offline verification; simplify without deleting required safeguards; reject a reliability guarantee; answer a clear typo request directly; and report a genuine publishing blocker without inventing success or asking again for existing approval.

The exercise checks selected interpretation and reporting behavior, not actual implementation or tool use. Both versions behaved similarly; it does not establish that the expanded integration improves general reliability. The full inputs, both integration texts, constant skill text, replies, and observations were captured in the development session. Real-task compliance and prevention claims remain unproven.

### User-settled direction: dialogue smoke observation

The unreleased checkpoint revision was exercised through three scripted conversations with four, three, and two assistant turns, plus three single-turn controls. Scenarios and behavioral criteria were defined before the edit. Each actual assistant reply was carried into the next turn; the prompts asked for dialogue continuations rather than judgments about a described mistake.

Observed behavior: the agent offered concrete contrasts after “I do not know,” kept example comparison separate from implementation, treated a counterquestion as an unresolved conversation rather than a selected improvement, and accepted a final scoped choice or delegation without another approval request. Controls preserved direct action on a clear typo request, honored existing concrete approval, and left an unavailable user's vague direction unresolved.

The twelve replies used the same configured `default` completion alias with the skill and integration supplied directly. User turns were predefined, not live human feedback; no tools, installation activation, implementation, or compaction were exercised. The full inputs, actual replies, and observations were captured in the development session. This checks the selected dialogue boundaries, not whether real users achieve better shared understanding or whether the revision outperforms 0.1.1.

### Historical bounded-discovery action-selection observation

This exercise evaluated the workflow later released in 0.1.3, which the principle-based revision supersedes. It is retained as historical evidence, not current instructions. It tested adherence to that workflow, not whether the workflow itself framed an open-ended request too narrowly.

The unreleased discovery revision after 0.1.2 was exercised with three synthetic cases and nine model-selected actions. Behavioral criteria were defined before editing. The skill and integration were supplied directly; a small driver accepted structured actions such as mapping, inspection, questioning, and reporting. In the broad-review case, source packets were supplied only after the corresponding inspection requests, so the later findings were not all present in the initial prompt.

- **Broad review:** the model clarified the direction, mapped the app, inspected Orders, Inventory, and Exports, then reported all six fixture-backed contract violations before asking for implementation scope. The report preserved an accepted BOM decision, separated an unmeasured performance lead, and disclosed the unreviewed browser surface.
- **Narrow authorized fix:** the model inspected only the named CSV file and requested the already-approved fix without a broad survey or another approval question. It did not claim implementation or verification had occurred.
- **Repeated broad request:** the model carried forward four open findings, one fixed issue, one deferred issue, and the runtime coverage limit. It offered scope choices without beginning another arbitrary one-defect search.

Each case ran once using the configured `default` completion alias; resolved model and sampling settings were not exposed by the interface. The full guidance, fixtures, inputs, actual action sequences, and observations were retained in the development session. This is simulated action ordering and report completeness—not real repository navigation, independent defect detection, installed-skill activation, implementation, runtime verification, live human agreement, or compaction recovery. It does not establish improved real-world reliability.

### Principle-based guidance smoke observation

The unreleased principle-based revision after 0.1.3 was exercised on five predefined conversations using the configured `default` and `smol` completion aliases, once per case and alias: ten replies. Criteria were defined before editing. The skill and integration were supplied directly, without a response schema, prescribed next question, or preferred sequence. Criteria were not included in the model prompts.

The cases covered an underspecified request, supplied personal context, a clear text transformation, an explicitly requested technical explanation, and correction of an assumed tone. Replies reflected the supplied context and retained important constraints; clear requests did not become interviews. Several responses were similar across aliases, including an identical correct sentence. The personal-context responses also recommended retaining existing functionality, which was an agent suggestion rather than an explicit additional user constraint.

These observations do not establish absence of framing, improved reliability, or guaranteed variation. Resolved model identifiers and sampling settings were not exposed, so distinct aliases do not establish distinct underlying models. No real tools, repository navigation, installed-skill activation, application changes, live multi-turn human feedback, or compaction were exercised. Inputs, guidance, replies, and observations were retained in the development session rather than installed as another behavioral script.
