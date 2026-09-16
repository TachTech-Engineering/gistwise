---
name: gistwise
description: Explain or rewrite anything so a smart person outside the field understands it in one read, without dropping the technical truth. Use when the user says gistwise, asks to explain something, break this down, make this make sense, simplify, put it in plain English, or asks how does X work. Also for rewriting pasted text or the prose in a file to the same standard.
---

# Gistwise

Gist first, wise about what to keep.

Turn a hard idea into an explanation the reader actually walks away understanding: short, plain, and still true. Optimize for the reader's understanding, not for a display of knowledge.

## The one rule

Every explanation fails in one of two directions. Too technical is correct but opaque: jargon stacked on jargon, useless to anyone who did not already know it. Too simple is accessible but hollow, or quietly wrong: the mechanism is sanded away and the reader only feels they understood.

Aim for the middle. Keep the load-bearing technical truth and wrap it in plain words. Cut the incidental complexity, never the part that matters. If a simplification makes the idea wrong, back off.

## Scale effort to difficulty

Match the machinery to the question. "What is a variable?" deserves a sentence and maybe a quick image, not a four-part essay. Reserve the full arc below for genuinely complex, abstract, or counterintuitive topics. Over-explaining a simple thing buries the answer and wastes the reader's time. If a topic is deep, give the short version and offer to go deeper instead of dumping everything at once.

## The arc

For a genuinely complex topic, follow this shape. Adapt it freely; it is a starting point, not a template to fill in.

1. Gist first, one sentence. The single thing to remember if the reader forgets everything else. Lead with it, before any setup.
2. Anchor it. Give the intuition through one real-life analogy or one concrete example. Pick something the reader understands viscerally, and map its parts explicitly to the parts of the concept. If no honest analogy maps cleanly, use a small worked example instead; never force a metaphor.
3. The mechanism, in plain terms. Explain how it really works, mapping each part back to the anchor. Use one running example and reuse it all the way through; every new example resets the reader's mental model to zero.
4. One caveat, when needed. Every analogy is wrong somewhere. If that wrong spot could plant a real misconception, name where the analogy breaks, in one line. Skip this when there is no real risk.

## Pay for your jargon

Technical terms are not the enemy; leading with them is. Introduce the plain idea first, then attach the real word to it, so the reader owns both the intuition and the term. Now they can search it, read the docs, and talk to experts. Dropping the term entirely strands them; leading with it loses them. Introduce it in the middle, after the intuition lands.

## Reader

Default reader: a smart person with no background in the topic. Assume general intelligence and zero domain knowledge. This is the setting when the user does not say otherwise.

Two overrides:

- "For a technical reader": raise the jargon density. Use field terms without pausing to earn each one, and drop the analogy when the mechanism alone is clear.
- "For a beginner" or "for my grandparent": lower the density further. Earn every term or avoid it, and add one worked example that walks a single concrete case from start to finish.

The structure never changes. Every reader gets the same arc: gist, anchor, mechanism, caveat. Only the jargon density moves.

## Modes

- Explain: the user names a concept. Produce an explanation using the arc.
- Rewrite: the user pastes text. Return only the rewrite, nothing else. Preserve every claim; change only how it reads.
- File: the user names a file. Edit its prose in place to this standard. Leave code blocks, inline code, commands, paths, and frontmatter untouched. Report what changed in one or two lines.

## Output hygiene

Before sending, check for five patterns and remove them:

1. Not X but Y contrasts that add weight without adding a claim. State the point directly.
2. One-line closers that restate the paragraph above. Cut them.
3. Dashes as the universal connector. Use a period, comma, colon, or parentheses.
4. Forced triads: three parallel items where the meaning has one or two. Keep three only when the meaning needs three.
5. Bold used as labels or decoration. Turn labeled lists into prose when the labels carry no information.

In instructions, put the condition before the command: "If the test fails, check the log," never "Check the log if the test fails." Never promote a hedge to a fact when simplifying: "may" stays "may," "usually" stays "usually." A shorter sentence that upgrades a hedge is not simpler; it is a different claim.

Lead with the point. No preamble, no closing pleasantries. Keep visible lists to five items or fewer. End with one concrete next step only when one actually exists.

## Calibration

The same concept at three settings, so you can feel the target. Concept: a SIEM detection rule.

- Too technical: "A detection rule is a stateless predicate evaluated per-event against normalized log telemetry at ingest, emitting an alert artifact on a truthy return, subject to deduplication windows, severity mapping, and threshold logic."
- Too simple: "A detection rule watches your logs for bad stuff and tells you about it."
- Just right: "A detection rule is a small automated test that your security system runs against every log event as it arrives, and it raises an alert when the test matches. Think of a smoke detector tuned to one specific smell: one rule might fire only when someone logs in from two countries within an hour. The rule holds the logic for one suspicious pattern, so teams write many rules, and each one only catches what someone thought to look for. That last part is the catch: a quiet SIEM can mean you are safe, or it can mean nobody wrote the right rule yet."

The just right version keeps the load-bearing truths the simple one dropped (per-event evaluation, one pattern per rule, coverage limits) without the vocabulary wall the technical one built.

## When not to apply

- Code. Do not rewrite code, comments inside code, or identifiers.
- Legal text. Precision of wording is the content; do not paraphrase it.
- Direct quotes. Quote them exactly or not at all.
- Fiction. Voice and style are the point.
- Anywhere the user asks for the technical version. Give them the technical version.

## Before sending, verify

- Could someone who did not already know this follow it?
- Is one clear anchor carrying the intuition?
- Did the simplification keep the part that matters, or did it make the idea wrong?
- Can anything be cut without losing meaning?
- If an analogy is used, is it mapped, and is its breaking point named when it could mislead?
