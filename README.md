<div align="center">

# gistwise

### *Gist first, wise about what to keep.*

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-Skill-d97757.svg)](https://docs.anthropic.com/en/docs/claude-code/skills)
[![Body under 1,800 words](https://img.shields.io/badge/skill%20body-%3C1%2C800%20words-lightgrey.svg)](SKILL.md)

Explain or rewrite anything so a smart person outside the field understands it in one read,<br>
**without dropping the technical truth.**

</div>

---

## What it does

Every explanation gistwise produces follows the same arc: the **gist** in one sentence, one **anchor** analogy or example, the **mechanism** in plain terms, and one **caveat** where the analogy breaks. The structure never changes with the audience; only the jargon density moves. The default reader is a smart person with no background in the topic, "for a technical reader" raises the density and drops the analogy when it is not needed, and "for a beginner" lowers it and adds a worked example. Three modes cover most work: **explain** a concept, **rewrite** pasted text, or **edit a file's prose** while leaving code blocks and frontmatter untouched.

## Before / after

> ❌ **Before**
>
> A detection rule is a stateless predicate evaluated per-event against normalized log telemetry at ingest, emitting an alert artifact on a truthy return, subject to deduplication windows, severity mapping, and threshold logic.

> ✅ **After**
>
> A detection rule is a small automated test that your security system runs against every log event as it arrives, and it raises an alert when the test matches. Think of a smoke detector tuned to one specific smell: one rule might fire only when someone logs in from two countries within an hour. The rule holds the logic for one suspicious pattern, so teams write many rules, and each one only catches what someone thought to look for. That last part is the catch: a quiet SIEM can mean you are safe, or it can mean nobody wrote the right rule yet.

## Install

Clone into your Claude Code skills directory:

```sh
git clone https://github.com/TachTech-Engineering/gistwise ~/.claude/skills/gistwise
```

Or with the skills CLI:

```sh
npx skills add TachTech-Engineering/gistwise
```

Then trigger it with `/gistwise`, or just ask Claude to explain, simplify, or break something down.

## Credits

Gistwise is a synthesis of four skills:

| Skill | Author | What gistwise borrows |
| --- | --- | --- |
| [explain-simply](https://github.com/yash2002vardhan/explain-simply) | yash2002vardhan | **The base of this skill**: the core rule, the explanation arc, and the jargon and effort-scaling principles |
| [humanizer](https://github.com/blader/humanizer) | blader | The five-item pre-send check for AI writing tells |
| [asd-ste100-skill](https://github.com/danyuchn/asd-ste100-skill) | danyuchn | Condition-before-command ordering, and the rule that a hedge never becomes a fact |
| [i-have-adhd](https://github.com/ayghri/i-have-adhd) | ayghri | Lead with the point, no preamble or closer, short visible lists, one next step |

## License

MIT. See [LICENSE](LICENSE).
