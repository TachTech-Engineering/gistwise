<div align="center">

<img src="assets/logo.png" alt="gistwise logo: a funnel distilling many shapes into a single drop" width="160">

# gistwise

### *Gist first, wise about what to keep.*

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-Skill-d97757.svg)](https://docs.anthropic.com/en/docs/claude-code/skills)
[![Body about 2,000 words](https://img.shields.io/badge/skill%20body-~2%2C000%20words-lightgrey.svg)](skills/gistwise/SKILL.md)

Explain or rewrite anything so a smart person outside the field understands it in one read,<br>
**without dropping the technical truth.**

</div>

---

## What it does

For a genuinely complex topic, gistwise follows an arc: the **gist** in one sentence, one **anchor** analogy or example, the **mechanism** in plain terms, and one **caveat** where the analogy breaks. Simple questions get short answers, and the depth, tone, and structure adapt to what the reader needs. The default reader is a smart person with no background in the topic, "for a technical reader" raises the density and drops the analogy when it is not needed, and "for a beginner" lowers it and adds a worked example. Three modes cover most work: **explain** a concept, **rewrite** pasted text, or **edit a file's prose** while leaving code blocks and frontmatter untouched.

At the sentence level, gistwise applies William Strunk Jr.'s *The Elements of Style* (1918), with modern usage taking precedence where the two disagree. The full text ships in `references/` and is read only when a task needs it. Two optional subagent passes handle longer or harder work. A **copyedit** pass applies Strunk to the draft but may not change a claim, a hedge, or the author's best phrasing, and it returns a change log you can check. A **cold read** hands the finished text to a fresh agent that has never seen the source, then asks it to state the gist back. Where a harness has no subagents, gistwise runs both passes itself.

## Before / after

> ❌ **Before**
>
> A detection rule is a stateless predicate evaluated per-event against normalized log telemetry at ingest, emitting an alert artifact on a truthy return, subject to deduplication windows, severity mapping, and threshold logic.

> ✅ **After**
>
> A detection rule is a small automated test that your security system runs against every log event as it arrives, and it raises an alert when the test matches. Think of a smoke detector tuned to one specific smell: one rule might fire only when someone logs in from two countries within an hour. The rule holds the logic for one suspicious pattern, so teams write many rules, and each one only catches what someone thought to look for. That last part is the catch: a quiet SIEM can mean you are safe, or it can mean nobody wrote the right rule yet.

## Install

Gistwise is a standard agent skill (`skills/gistwise/SKILL.md`), so it works in any harness that reads skills. The quickest route on most of them is the skills CLI:

```sh
npx skills add TachTech-Engineering/gistwise
```

To install it as a plugin, follow the guide for your harness:

<!-- everyharness:install:start -->

| Harness | Install |
|---|---|
| Claude Code | see docs/install/claude-code.md |
| Cursor | see docs/install/cursor.md |
| Codex | see docs/install/codex.md |
| Devin CLI | see docs/install/devin.md |
| Kimi Code | see docs/install/kimi.md |
| Gemini CLI | see docs/install/gemini.md |
| OpenCode | see docs/install/opencode.md |
| Pi | see docs/install/pi.md |
| Hermes Agent | see docs/install/hermes.md |
| muse | see docs/install/muse.md |
| Agent Plugins 1.0 clients | see docs/install/agent-plugins-1.0.md |
| Factory Droid / Grok / Copilot (marketplace descriptor) | see docs/install/agents-marketplace.md |

<!-- everyharness:install:end -->

Then trigger it with `/gistwise`, or ask your agent to explain, simplify, or break something down. Installed as a Claude Code plugin, the skill is namespaced as `/gistwise:gistwise`.

### Migrating from v2

v2 kept `SKILL.md` at the repository root, and v3 moves it to `skills/gistwise/`. If you installed v2 with `git clone … ~/.claude/skills/gistwise`, a `git pull` leaves that folder without a top-level `SKILL.md`, and Claude Code stops finding the skill. Delete the folder and reinstall with one of the methods above.

## Install in the Claude app (desktop & web)

1. [**Download gistwise-skill.zip**](https://github.com/TachTech-Engineering/gistwise/releases/latest/download/gistwise-skill.zip).
2. In Claude Desktop, open **Customize** (bottom-left) → **Skills** (on some plans: Settings → Capabilities → Skills).
3. Click **+** → **Upload a skill**, pick the ZIP, and toggle gistwise on.

Uploaded skills are private to your account and sync between the desktop app and claude.ai on the web.

## Credits

Gistwise is a synthesis of five skills:

| Skill | Author | What gistwise borrows |
| --- | --- | --- |
| [the-elements-of-style](https://github.com/obra/the-elements-of-style) | obra | Strunk's 18 rules and the *Elements of Style* reference text (William Strunk Jr., 1918, public domain), loading the reference only when needed, and the delegated copyedit pass |
| [explain-simply](https://github.com/yash2002vardhan/explain-simply) | yash2002vardhan | **The base of this skill**: the core rule, the explanation arc, and the jargon and effort-scaling principles |
| [humanizer](https://github.com/blader/humanizer) | blader | The five-item pre-send check for AI writing tells |
| [asd-ste100-skill](https://github.com/danyuchn/asd-ste100-skill) | danyuchn | Condition-before-command ordering, and the rule that a hedge never becomes a fact |
| [i-have-adhd](https://github.com/ayghri/i-have-adhd) | ayghri | Lead with the point, no preamble or closer, short visible lists, one next step |

## License

MIT. See [LICENSE](LICENSE).
