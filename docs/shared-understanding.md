# Shared Understanding: session examples and limits

These are illustrative expected behaviors, not measured model outputs or benchmarks. The [skill](../skills/productivity/shared-understanding/SKILL.md) is the behavioral source; [AGENTS.md](../AGENTS.md) supplies the integration rule and engineering safeguards.

## A complete initial prompt

**User:** “Fix the typo ‘Recieve’ to ‘Receive’ in the checkout heading. Change nothing else.”

**Expected:** locate and correct that heading; perform the permitted proportionate check. Do not ask for Outcome, Must preserve, and Done means again or redesign checkout.

## An underspecified goal

**User:** “Make this dashboard useful.”

**Expected:** inspect the available dashboard context, then ask which decision it should help its intended user make. Offer grounded interpretations if possible. Do not select new charts or redesign the page based on assumptions.

## A second-turn answer

**Agent:** “Should the export contain selected rows or all filtered rows?”

**User:** “All filtered rows. Keep the existing columns.”

**Expected:** update row selection and preserve the existing columns and other settled constraints. Do not restart the requirements interview or silently include unfiltered rows.

## Exploration is not permission

**User:** “Would a database index help?”

**Expected:** investigate and explain whether an index could help. Do not create an index merely because the user asked about it; observe the applicable database approval boundary.

## A mid-session correction

**User:** “Actually, leave export alone. Only fix the date filter.”

**Expected:** stop export work, identify any export edits already made, and state the narrowed scope. Address only your own now-out-of-scope changes within applicable permissions; never discard unrelated user changes. Preserve constraints that still apply to the date filter.

## A requested understanding check

**User:** “Check our understanding before continuing.”

**Expected:** pause substantive work and briefly show the current goal, changes, preserved constraints, and unresolved choice or next action. Ask only if something consequential remains unsettled.

## Missing agreement after compaction

**Available context:** the goal is present, but the record of permission to publish is missing.

**Expected:** try accessible history first. If permission cannot be recovered, ask before publication. Do not claim it was approved because the files are ready. Continue independent authorized local work when safe.

## A technical failure despite a clear agreement

**User:** “We agreed on the behavior, but your change still fails.”

**Expected:** accept the reported failure, investigate available evidence, and correct the in-scope mistake. Do not demand a better prompt, assert that agreement proves correctness, or invent a probability that the next attempt will succeed.

## What evidence can establish

The skill can expose misunderstandings; it cannot guarantee that a model detects every ambiguity or produces correct work. User approval validates intent, not implementation quality.

Three separate things matter:

1. **Availability:** the harness can find the skill and persistent instruction rule.
2. **Continuity:** current decisions, constraints, and scoped approvals remain accessible.
3. **Execution:** the agent follows the guidance and verifies the intended outcome.

Saving or installing a file does not establish these end to end. Instruction loading, tool names, precedence, history access, and compaction differ by harness. A handoff preserves information only if it is actually produced and retained. This project has no hook that intercepts every turn or controls a compactor.

Evaluate ordinary work for specific failures: repeated supplied questions, silently changed scope, discussion treated as permission, lost constraints, or completion claimed without evidence. Identify whether the cause was missing instructions, missing context, or execution despite available guidance. Fix that cause rather than adding another overlapping skill. Never publish private session content without permission.

Do not report a success rate without a defined evaluation set, failure criteria, and recorded outcomes. These examples are not such a measurement. Package installation checks do not prove model compliance or real compaction recovery.
