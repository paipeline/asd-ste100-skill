---
name: asd-ste100
description: "Write or revise technical explanations, instructions, status reports, and agent handoffs in clear English inspired by ASD-STE100. Use when the user requests STE, Simplified Technical English, or less ambiguous technical communication."
---

# ASD-STE100: clear agent communication

Write English that a human or another agent can understand on the first read.
Use a practical adaptation of Simplified Technical English for agent output.
Preserve meaning before you shorten text.

## Preserve the task

Follow the user's requested language, tone, detail, and output format.
Apply this skill to English prose. Keep code, commands, identifiers, paths, URLs, and verbatim quotes unchanged.
In structured output, preserve the schema and exact values. Simplify only prose fields whose wording can change.

Keep every material fact, condition, exception, negation, quantity, and uncertainty from the source.
Keep the difference between a requirement, a recommendation, a possibility, and an observed result.
If missing information changes the meaning or required action, ask a focused question. Otherwise, state any necessary assumption.

## Write clearly

1. **Lead with the useful point.** Give the answer, result, or required action first. Add the reason and evidence as needed.
2. **Use short, complete sentences.** Aim for at most 20 words per instruction and 25 words per descriptive sentence.
   Split long sentences at a logical boundary. Retain words needed for correct meaning and grammar.
3. **Give each sentence one job.** Put one action in each numbered step. Keep each paragraph on one topic.
4. **Name the actor and the object.** Prefer active voice when the actor is known. Replace unclear pronouns with specific names.
   If the actor is unknown, preserve that uncertainty.
5. **Use one term for one concept.** Keep that term throughout the response. Define unfamiliar technical terms when needed.
   Preserve exact domain terms instead of replacing them with inaccurate common words.
6. **Use plain words and direct verbs.** Prefer "use" to "utilize" and "start" to "commence."
   Keep articles and natural grammar. Choose simple verb forms when they preserve time and state.
7. **Make conditions explicit.** Put a prerequisite before its action: "If the check fails, stop the release."
   Retain exact limits, units, dates, and time zones when supplied. Mark missing values as unknown instead of inventing them.
8. **Report status precisely.** Separate planned work, completed work, and verified results.
   Use "not run" when a check has not run. Give an observable success condition when an instruction needs one.

## Hand off work

For an agent handoff, include only the fields the recipient needs:

```text
Task: <specific goal and scope>
Status: <current state, including unfinished work>
Result: <observed outcome or artifact>
Evidence: <checks, results, and relevant references>
Next: <responsible actor, next action, and completion condition>
```

Use the existing message format when a workflow defines one. Put these details in its appropriate fields.
Include exact artifact paths or links. Keep assumptions separate from observed results.

## Check before delivery

Compare a rewrite with its source. Confirm that all material facts and qualifications remain.
Check that the reader can identify the subject, action, condition, and result where relevant.
Remove repeated statements. Return the requested output without an extra style report unless the user requests one.

## Scope and source

These instructions adapt principles from [ASD-STE100](https://www.asd-ste100.org/) for everyday agent communication.
They do not include its controlled dictionary or verify formal compliance.
If formal compliance is required, use the official standard and check both its writing rules and dictionary.
State which compliance checks remain unverified.
