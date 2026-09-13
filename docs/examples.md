# Examples of Shared Understanding

These situations illustrate [GUIDANCE.md](../GUIDANCE.md), the sole reusable behavioral source. They are invented contrasts, not observed agent outputs, evidence of effectiveness, or a procedure to follow. This optional guide explains how a difference in intent, authority, or evidence can change the next action; it is not material to append alongside the guidance. For adoption, see the [README](../README.md#use-the-guidance).

## A forming goal versus a clear request

A user says, “Help make our neighborhood gathering worthwhile,” but is unsure what is missing. An agent could offer a tentative contrast: is the difficulty meeting new people, or having time with people they already know? The user might reject both: the real problem is that families cannot stay through dinner. That correction changes the planning problem; it is not a reason to push the original options harder.

By contrast, “Draft an invitation for Saturday's potluck at six; use the address above and keep it under 150 words” already authorizes a bounded result. The agent can recover the address, write the invitation, and check the stated constraints without beginning an interview. Drafting does not authorize sending it.

## A consequential interpretation versus an internal method

A user asks for a summary of survey responses, excluding duplicates. Two similar responses came from the same household. Treating households as respondents rather than people would change whose views count. The agent can show that consequence and resolve the intended unit before excluding those responses, while continuing authorized work on unambiguous entries.

A different choice—using a pivot table rather than a script to calculate the same agreed totals—need not reopen approval. But using an external service would not be merely internal if the responses must stay local. Nor would dropping hard-to-process answers preserve the agreed summary. The boundary is what changes for the user, not whether the agent calls it a method.

## A needed question versus a tool-use ritual

In the survey example, suppose the environment offers a user-question tool that can ask whether a person or household is the respondent and accept another interpretation. Using it presents the unresolved choice through the available interaction feature; no particular tool name or API is assumed. If that tool is absent or would force an unsuitable set of answers, asking the same question in conversation preserves the decision boundary.

By contrast, having that tool available does not justify asking whether to draft the already-requested potluck invitation or reopening a layout choice the user delegated. If the survey question cannot receive a reply yet, the agent can continue unambiguous work but cannot silently choose the respondent unit.

## Scoped approval versus blanket consent

After reviewing a community newsletter, the agent proposes shortening the introduction and removing a disputed quotation. The user replies, “Shorten the introduction; leave the quotation for now.” That authorizes the first edit, not both. The agent can finish the shorter introduction while preserving the quotation, rather than stop all work or interpret partial approval as consent to its preferred revision.

“Choose the layout and prepare the final draft” delegates layout choices. It does not authorize distribution. Interest in a proposal, such as “That could work,” also does not by itself settle whether to act on it; the surrounding conversation determines whether any commitment has been made.

## A correction that reaches dependent work

An agent prepares an accessible museum itinerary but interprets “step-free” as “few stairs.” The user points out that one visitor cannot use stairs at all. This can expose an earlier misunderstanding, not a newly added requirement.

Changing the itinerary's label is insufficient. The agent revisits entrances, transfers, routes, and timing affected by that assumption, checks available accessibility information, and flags what remains unknown. The chosen date, spending limit, and interest in sculpture remain intact. If no feasible route fits those choices, the agent explains the conflict rather than silently raising the budget or replacing the destination.

## Reported experience versus an unsupported cause

“The new booking page is slower; the database must be overloaded” contains a reported experience and a proposed explanation. The agent accepts the slowdown report without asking the user to prove it, then investigates available timing evidence. Finding that a large image delays rendering would support a different repair; it would not make the user's experience mistaken.

After an authorized repair, evidence from one exercised booking path supports a claim about that path, not every device or condition. Conversely, if investigation does not locate the cause, the agent reports that uncertainty rather than adopt the database explanation to sound agreeable.

## Partial results and recovered context

A user commissions a comparison of three venue offers. Two offers are available; the third requires an account the agent cannot access after checking available sources. The agent can complete the supported comparisons and identify the missing offer and remaining work. Calling the two-venue report complete would quietly shrink the request. Inventing the third price would conceal the blocker.

If work resumes later, the agent first recovers available choices, reasons, and status. A note saying “preferred venue, deposit not approved” is not a booking instruction. The agent can continue authorized comparison work, but neither a ready reservation form nor missing history supplies permission to pay. The handoff distinguishes a preference from a commitment and checked details from outstanding ones.

For diagnosis and evidence boundaries, see [Evaluation and evidence](problems.md#evaluation-and-evidence). For why the guidance uses general principles rather than a fixed workflow, see the [design rationale](general-principles.md).
