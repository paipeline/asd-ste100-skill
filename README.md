# ASD-STE100 Skill

A small skill that makes agents write **about 80% of the way to ASD-STE100 Simplified Technical English**.

Inspired by [Andrej Karpathy's thoughts on making LLM output easier to understand](https://x.com/karpathy/status/2105819303471976479).
He suggested asking models to explain things in ASD-STE100, with "80% of the way" as a less rigid option.

[ASD-STE100](https://www.asd-ste100.org/) comes from aircraft maintenance documentation.
This skill uses its writing method: controlled words, consistent terms, simple verbs, short sentences, and one action per step.
The 80% approach keeps this structure while allowing natural explanations and necessary technical vocabulary.
It preserves technical detail and uncertainty. The percentage is a writing target, not a compliance score.

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

Illustrative rewrite:

**Before:** If you encounter a timeout during the processing of a request, verify the availability of the server prior to initiating another request.

**After:** If the request times out, check whether the server is available before you send another request.

The skill keeps exact identifiers, conditions, and uncertainty. Its instructions are in [SKILL.md](SKILL.md).

## Contribute

Issues and pull requests are welcome. Include a short example and explain how your change improves clarity without losing meaning.

## License and credit

[MIT](LICENSE). You can use, modify, and share this skill, including commercially.

This is an independent adaptation. It is not affiliated with or endorsed by Andrej Karpathy, ASD, or the STEMG.
ASD owns the ASD-STE100 standard and trademark. The standard and dictionary are not included or covered by this repository's license.
This skill does not certify ASD-STE100 compliance or claim measured speed improvements.
