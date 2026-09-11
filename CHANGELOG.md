# Changelog

## 0.1.6

- Prefer the asking tool when continuing depends on an unsettled, undelegated user decision; derive questions from the conversation rather than a predefined subject or workflow.
- Allow batching independently answerable questions and sequencing dependent ones; clarify that an answer settles only the choices it addresses.
- Preserve context, uncertainty, alternatives, and the option to decline; do not substitute a recommendation or announcement for a user decision or add gates to already-authorized or completed work.
- Keep examples illustrative in the practice docs rather than giving assessments or findings a dedicated rule in the skill or persistent integration block.
- Add human-facing `docs/problems.md`: explain common collaboration complaints, human blind spots, and compounding agent assumptions without diagnosing motives or reversing one-sided blame; distinguish general principles from fixed workflows.
- Describe an evidence-based confidence plan that starts with real interactions in the current environment and broadens without promising universal reliability or measured improvements.
- Record the project's general-principle design constraint in `docs/general-principles.md`; link it from repository-development guidance while keeping it outside the copyable runtime integration section.
- Clarify reported experience versus causal explanation, the limits of verification and model agreement, and revision of work that depends on a corrected premise.
- Add bounded research context to the practice guide and strengthen evaluation guidance for loaded revisions, independent dimensions of success, and repeated outcomes; do not claim demonstrated improvement.
- Correct practice guidance to reference only the copyable integration section; preserve repository-only development instructions and local-only revision scope.
- Refine reconsideration as responsiveness to intent and evidence, not agreement or revision for its own sake; preserve supported conclusions and honor declined recommendations.
- Document the mindfulness paper's measured-trait and decision-revision limits without prescribing reflection rituals or inferred user profiles; distinguish the Karpathy-inspired guidelines' authoring value from popularity-based efficacy claims.

## 0.1.5

- Rewrite the skill around connected responsibilities for understanding, timely communication, execution, and correction.
- Distinguish ordinary implementation choices from changes to agreed requirements or authority; expose consequential interpretations and discoveries before affected commitments.
- Consolidate engineering safeguards into the skill and replace the overlapping integration sections with a brief activation and boundary block.
- Exercise the revised guidance with eleven text-only development replies without claiming improved reliability or efficiency.
- Flatten the source layout to `skills/shared-understanding/` and make the persistent block resolve the installed skill through the harness rather than a repository-relative path.
- Use `npx skills@latest add codegiveness/shared-understanding` as the documented installation route, with a separate persistent-instruction step and no universal harness-support claim.
- Redesign README and practice guidance for the current skill; remove obsolete retirement instructions, unsupported reference-adoption comparisons, and historical session reports from the usage docs.

## 0.1.4

- Replace task-specific discovery instructions with principles for intent, authority, evidence, proportionate judgment, and continuity.
- Remove the prescribed review sequence, task menus, question quota, readback formats, and review-specific state fields from the skill and integration.
- Leave question choice, wording, and approach responsive to the conversation and agent, while preserving user-settled direction, scoped delegation, existing approvals, and honest completion.
- Align public guidance and examples with those principles; mark the prior workflow check as historical and record context-sensitive smoke observations without claiming unbiased or necessarily different responses.

## 0.1.3

- Separate broad discovery from implementation scope: complete a bounded coverage pass before presenting fixes, rather than narrowing a broad option to one workflow or stopping at the first defect.
- Consolidate all supported findings with evidence and impact; distinguish unverified leads, accepted risks, and unreviewed areas without claiming an exhaustive audit.
- Carry current phase, coverage, and open/fixed/deferred/blocked findings across turns and handoffs; preserve narrow requests and existing approval boundaries.
- Adapt compact task state and complete-but-grouped presentation from the attention-support reference, not its default one-issue-at-a-time delivery; document bounded action-selection smoke observations and their limits.

## 0.1.2

- Require a user-settled direction before implementing vague goals: a concrete choice, approval, or explicit scoped delegation, not the agent's confidence alone.
- Keep permitted discovery available while the direction is open; preserve direct action for clear requests and existing approval without ritual reconfirmation.
- Keep unanswered choices open and repair conversational confusion instead of treating an unrelated reply as a decision.
- Align skill discovery metadata, integration guidance, and examples with the checkpoint; record multi-turn dialogue smoke checks without claiming real-world reliability.

## 0.1.1

- Help develop still-forming goals through concrete situations, contrasting examples, and small authorized probes instead of repeated abstract questions.
- Make consequential interpretations checkable; distinguish supplied facts, tentative proposals, ordinary delegated judgment, and scoped approval.
- Preserve decision reasons and repair mismatched results without resetting the whole agreement or blaming the user's prompt.
- Expand session examples, compare four reference approaches, and document bounded smoke observations without claiming improved general reliability.
- Align the `AGENTS.md` integration with developing goals and make its engineering safeguards explicit about scope, supported claims, cause-based fixes, complete migrations, and proportionate verification.
- Map broad criticism to observable failures and document combined skill/integration smoke checks without promising that instructions prevent mistakes.

## 0.1.0

- Publish the canonical `shared-understanding` skill as a dependency-free npm prose package.
- Categorize the skill under `skills/productivity/`; separate session examples from installation guidance.
- Provide complete `AGENTS.md` integration guidance, including evidence ownership, proportional effort, mistake ownership, and honest verification.
- Document installation and instruction integration without automatic configuration edits or claimed reliability rates.
