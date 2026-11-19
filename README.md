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

## Usage examples

Start a prompt with `/gistwise` or the word "gistwise", or just ask in plain words. "Explain," "break this down," "simplify," and "tighten this up" all trigger it.

| You type | What gistwise does |
| --- | --- |
| `gistwise: what is a variable?` | Answers in a few sentences. A simple question gets no arc, no reference lookup, and no subagents. |
| `gistwise: how does a Bloom filter work?` | Uses the full arc: the gist in one sentence, one running example, then the mechanism, naming each technical term only after the idea lands. |
| `explain OAuth refresh tokens for a technical reader` | Uses field terms freely and drops the analogy when the mechanism is clear on its own. |
| `explain what a mortgage escrow account is for my grandparent` | Avoids jargon and walks one concrete case from start to finish. |
| `gistwise: rewrite this for my team lead` + pasted text | Returns only the rewrite, with the main point first and every *may* and *usually* kept. Over about 500 words, a copyedit subagent checks the draft against the original. |
| `gistwise the prose in docs/runbook.md` | Edits the file in place and reports the changes in a line or two. Frontmatter, code blocks, commands, and paths stay byte-identical. |
| `tighten this up` / `copyedit this` + pasted text | Applies Strunk's rules and lists each change with the rule behind it, such as "R13: omit needless words." |
| `explain how DNS resolution works, and check it before you send it` | After drafting, hands the text to a fresh subagent that never saw the source. If it can't state the gist back or gets lost, gistwise revises once. |
| `gistwise: "fewer errors" or "less errors"?` | Looks up that one entry in the Strunk reference instead of loading the whole book. |

gistwise leaves code, legal text, direct quotes, and fiction alone. If you ask for the technical version, you get the technical version.

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
