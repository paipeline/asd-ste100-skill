# ASD-STE100 Skill

A small skill that makes agents write **about 80% of the way to ASD-STE100 Simplified Technical English**.

Inspired by [Andrej Karpathy's thoughts on making LLM output easier to understand](https://x.com/karpathy/status/2105819303471976479).
He suggested asking models to explain things in ASD-STE100, with "80% of the way" as a less rigid option.

[ASD-STE100](https://www.asd-ste100.org/) comes from aircraft maintenance documentation.
This skill uses its writing method: controlled words, consistent terms, simple verbs, short sentences, and one action per step.
The 80% approach keeps this structure while allowing natural explanations and necessary technical vocabulary.
It preserves technical detail and uncertainty. The percentage is a writing target, not a compliance score.

## Before and after

This example uses simulated agent output. The scenario and test results are illustrative.

| Metric | Before | 80% ASD-STE100 |
| --- | --- | --- |
| Word count | 139 | 121 |
| Longest sentence | 59 words | 15 words |
| Conditions | Embedded in a long sentence | Listed separately |
| Next actions | Combined in one sentence | Numbered, with an explicit prerequisite |

**Before**

> The webhook idempotency changes in `src/webhooks/handler.ts` have now been implemented so that, provided a repeated delivery carries the same `event_id` and arrives within 60 seconds of the first delivery, the handler rejects the repeated delivery without changing the database schema, although this should not be taken as confirmation that deliveries outside that window are handled in the same way. While all 42 unit tests passed, the integration suite could not be run because `REDIS_URL` was unavailable, and the latency improvement that appeared in one local run may reflect a warm cache rather than the implementation, so neither the integration behavior nor the performance benefit has been verified. The next agent should make `REDIS_URL` available and run the integration suite, then, only if that suite passes, perform a staging smoke test; production deployment must remain blocked unless both checks pass.

**After: 80% ASD-STE100**

> I changed `src/webhooks/handler.ts`. The database schema is unchanged.
>
> The handler rejects a repeated delivery when both conditions apply:
>
> - The delivery has the same `event_id` as the first delivery.
> - The delivery arrives within 60 seconds of the first delivery.
>
> Behavior outside this window is unverified.
>
> All 42 unit tests passed. I did not run the integration suite because `REDIS_URL` was unavailable. Integration behavior is unverified.
>
> One local run showed lower latency. A warm cache may explain the difference. The performance benefit is unverified.
>
> Do not deploy to production unless the integration suite and staging smoke test both pass.
>
> The next agent should complete these steps:
>
> 1. Make `REDIS_URL` available.
> 2. Run the integration suite.
> 3. If the integration suite passes, run the staging smoke test.

The rewrite separates facts, uncertainty, and next actions. It keeps the same conditions and deployment restriction.
Word counts use whitespace-separated words and count each code identifier as one word. List markers are excluded.
This example shows a change in writing structure; it does not measure reading speed.

## Install

With [Skills CLI](https://github.com/vercel-labs/skills) (requires Node.js and Git):

```sh
npx skills add paipeline/asd-ste100-skill --skill asd-ste100
```

Choose your agent and installation location when prompted.

Or [download the ZIP](https://github.com/paipeline/asd-ste100-skill/archive/refs/heads/main.zip).
Extract it and put the folder in your agent's skills directory with the name `asd-ste100`.
The skill itself needs no runtime dependencies or API keys.

## Use

```text
Use the asd-ste100 skill. Explain this code about 80% of the way to ASD-STE100.
```

In Codex, you can invoke it with `$asd-ste100`. Other examples:

- "Rewrite this status update with the asd-ste100 skill."
- "Use asd-ste100 to prepare a handoff for the next agent."

The skill keeps exact identifiers, conditions, and uncertainty. Its instructions are in [SKILL.md](SKILL.md).

## Contribute

Issues and pull requests are welcome. Include a short example and explain how your change improves clarity without losing meaning.

## License and credit

[MIT](LICENSE). You can use, modify, and share this skill, including commercially.

This is an independent adaptation. It is not affiliated with or endorsed by Andrej Karpathy, ASD, or the STEMG.
ASD owns the ASD-STE100 standard and trademark. The standard and dictionary are not included or covered by this repository's license.
This skill does not certify ASD-STE100 compliance or claim measured speed improvements.
