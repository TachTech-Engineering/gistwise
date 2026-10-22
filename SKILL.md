---
name: gistwise
description: Explain or rewrite anything so a smart person outside the field understands it in one read, without dropping the technical truth. Use when the user says gistwise, asks to explain something, break this down, make this make sense, simplify, put it in plain English, or asks how does X work. Also for rewriting pasted text or the prose in a file to the same standard.
---

# Gistwise

Gist first, wise about what to keep.

Turn a hard idea into an explanation the reader actually walks away understanding: short, plain, and still true. Optimize for the reader's understanding, not for a display of knowledge. Make the writing natural, cohesive, and worth following without turning every explanation into a story.

## The one rule

Every explanation fails in one of two directions. Too technical is correct but opaque: jargon stacked on jargon, useless to anyone who did not already know it. Too simple is accessible but hollow, or quietly wrong: the mechanism is sanded away and the reader only feels they understood.

Aim for the middle. Keep the load-bearing technical truth and wrap it in plain words. Cut the incidental complexity, never the part that matters. If a simplification makes the idea wrong, back off.

## Scale effort to difficulty

Match the machinery to the question. "What is a variable?" deserves a sentence and maybe a quick image, not a four-part essay. Reserve the full arc below for genuinely complex, abstract, or counterintuitive topics. Over-explaining a simple thing buries the answer and wastes the reader's time. If a topic is deep, give the short version and offer to go deeper instead of dumping everything at once.

## Find the spine

Read all supplied material before rewriting. Identify the central idea, question, argument, or decision that holds it together. Notice the user's strongest phrasing, examples, distinctions, humor, and revealing details; build around them when they work. Do not replace a sharp original sentence with a smoother but weaker one.

Order information around what the reader needs to understand next, rather than the order in which the notes arrived. Lead with the consequential point, supply context when it becomes useful, and make each paragraph advance the explanation or reasoning. Let transitions follow from logic instead of adding generic connectors. Preserve chronology when it affects causation or meaning.

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

Also infer what the reader already knows, cares about, might misunderstand, and needs to decide or do. Adapt depth, tone, and structure accordingly. An executive may need the decision and consequence first; an engineer may need the mechanism and constraints. Keep the user's voice appropriate to the audience rather than making it sterile.

The arc supports understanding; it is not mandatory scaffolding for every document. Simple answers can stay short, and rewrites should use the structure their purpose requires.

## Modes

- Explain: the user names a concept. Produce an explanation, using the arc when the topic warrants it.
- Rewrite: the user pastes text. Return only the rewrite unless a meaningful reasoning flaw needs a brief note. Preserve the claims, intent, and degree of certainty; reorganize and remove repetition without silently changing the position.
- File: the user names a file. Edit its prose in place to this standard. Leave code blocks, inline code, commands, paths, and frontmatter untouched. Report what changed in one or two lines.

## Natural writing

Use familiar words, concrete actors, and precise verbs. Explain what actually happened or became slower, harder, or more expensive instead of hiding it behind abstractions. Use supplied details; never invent specifics to make prose vivid. Contractions, bluntness, ordinary phrases, and occasional fragments can preserve voice when they fit the audience.

Vary sentence length and paragraph size to suit the thought. Give a consequential sentence room without turning the whole document into dramatic one-line paragraphs. Use examples, callbacks, contrasts, or rhetorical questions only when they improve understanding or reasoning. Keep important distinctions explicit, but avoid repeating the same rhetorical construction. Do not manufacture suspense, emotion, or profundity, or delay the answer for a reveal. Clarity outranks drama.

## Intellectual honesty

Preserve load-bearing facts, mechanisms, conditions, exceptions, and uncertainty. Never promote a hedge to a fact: "may" stays "may," "usually" stays "usually." Distinguish fact from interpretation, inference, assumption, and opinion. Do not invent evidence, quotations, motives, events, or technical details.

If the source has a consequential contradiction, unsupported assumption, or reasoning gap, flag it briefly instead of concealing it with persuasive prose. Preserve the user's actual position; do not silently repair it into a different claim. Ask only when missing information is necessary to proceed; otherwise state the limitation without filling the gap.

## Editing and Humanizer pass

After drafting, check the logic and technical truth, then read as the intended recipient. Apply this self-contained cleanup pass:

1. Cut repeated points, redundant setup, overexplaining, and closers that merely restate the paragraph above. Keep the strongest version; retain repetition only when it adds useful emphasis or orientation.
2. Replace generic introductions, formulaic transitions, canned business language, inflated vocabulary, artificial enthusiasm, and impressive-sounding emptiness with direct meaning.
3. Remove decorative "not X but Y" contrasts, forced triads, stock rhetorical questions, and repetitive sentence patterns. Keep genuine distinctions and useful parallelism.
4. Check for dashes used as the universal connector, dramatic fragments, excessive signposting, and decorative bold labels. Let punctuation and formatting serve the thought.
5. Restore the user's strongest wording where polishing erased personality. Keep natural texture without adding errors or forced informality. Check that stronger prose has not made the claim more certain than the evidence allows.

In instructions, put the condition before the command: "If the test fails, check the log." Lead with the point, without a generic preamble or closing pleasantries. Prefer prose for connected reasoning and lists for steps or comparisons; keep visible lists to five items or fewer. End when the explanation is complete, or with the decision, unresolved question, or concrete next step when one actually exists. Do not add an automatic recap.

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
- Where an anchor is useful, is one clear example carrying the intuition?
- Did the simplification keep the part that matters, or did it make the idea wrong?
- Does the ordering follow the reader's needs, preserve the user's strongest wording, and avoid repetition?
- If an analogy is used, is it mapped, and is its breaking point named when it could mislead?
