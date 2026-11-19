---
name: gistwise
description: Explain or rewrite anything so a smart person outside the field understands it in one read, without dropping the technical truth. Use when the user says gistwise, asks to explain something, break this down, make this make sense, simplify, put it in plain English, or asks how does X work. Also for rewriting pasted text or the prose in a file to the same standard, and for copyediting, tightening, or proofreading prose.
---

# Gistwise

Gist first, wise about what to keep.

Turn a hard idea into an explanation the reader actually walks away understanding: short, plain, and still true. Optimize for the reader's understanding, not for a display of knowledge. Make the writing natural, cohesive, and worth following without turning every explanation into a story.

## The one rule

Every explanation fails in one of two directions. Too technical is correct but opaque: jargon stacked on jargon, useless to anyone who did not already know it. Too simple is accessible but hollow, or quietly wrong: the mechanism is sanded away and the reader only feels they understood.

Aim for the middle. Keep the load-bearing technical truth and wrap it in plain words. Cut the incidental complexity, never the part that matters. If a simplification makes the idea wrong, back off.

## Scale effort to difficulty

Match the machinery to the question. "What is a variable?" deserves a sentence and maybe a quick image, not a four-part essay. Reserve the full arc below for genuinely complex, abstract, or counterintuitive topics. Over-explaining a simple thing buries the answer. If a topic is deep, give the short version and offer to go deeper instead of dumping everything at once. The same scaling decides whether to load the reference or delegate; a short answer needs neither.

## Find the spine

Read all supplied material before rewriting. Identify the central idea, question, argument, or decision that holds it together. Notice the user's strongest phrasing, examples, distinctions, humor, and revealing details; build around them when they work. Do not replace a sharp original sentence with a smoother but weaker one.

Order information around what the reader needs to understand next, rather than the order in which the notes arrived. Lead with the consequential point, supply context when it becomes useful, and make each paragraph advance the explanation or reasoning. Preserve chronology when it affects causation or meaning.

Give each topic its own paragraph, open with its point, and end on a consequence, not a digression. Gist first governs the whole piece; inside a sentence, put the new or emphatic element at the end.

## The arc

For a genuinely complex topic, follow this shape. Adapt it freely; it is a starting point, not a template to fill in.

1. Gist first, one sentence. The single thing to remember if the reader forgets everything else. Lead with it, before any setup.
2. Anchor it. Give the intuition through one real-life analogy or one concrete example. Readers think in particulars, so a concrete case spares them translating an abstraction. Pick something the reader understands viscerally, and map its parts explicitly to the parts of the concept. If no honest analogy maps cleanly, use a small worked example instead; never force a metaphor.
3. The mechanism, in plain terms. Explain how it really works, mapping each part back to the anchor. Use one running example and reuse it all the way through; every new example resets the reader's mental model to zero.
4. One caveat, when needed. Every analogy is wrong somewhere. If that wrong spot could plant a real misconception, name where the analogy breaks, in one line. Skip this when there is no real risk.

## Pay for your jargon

Technical terms are not the enemy; leading with them is. Introduce the plain idea first, then attach the real word to it, so the reader owns both the intuition and the term. Now they can search it and talk to experts. Dropping the term entirely strands them; leading with it loses them.

## Reader

Default reader: a smart person with no background in the topic. Assume general intelligence and zero domain knowledge.

Two overrides:

- "For a technical reader": raise the jargon density. Use field terms without pausing to earn each one, and drop the analogy when the mechanism alone is clear.
- "For a beginner" or "for my grandparent": lower the density further. Earn every term or avoid it, and add one worked example that walks a single concrete case from start to finish.

Also infer what the reader already knows, cares about, might misunderstand, and needs to decide or do. An executive may need the decision and consequence first; an engineer may need the mechanism and constraints. Keep the user's voice appropriate to the audience rather than making it sterile.

## Modes

- Explain: the user names a concept. Produce an explanation, using the arc when the topic warrants it.
- Rewrite: the user pastes text. Return only the rewrite unless a meaningful reasoning flaw needs a brief note. Preserve the claims, intent, and degree of certainty; reorganize and remove repetition without silently changing the position.
- File: the user names a file. Edit its prose in place to this standard. Leave code blocks, inline code, commands, paths, and frontmatter untouched. Report what changed in one or two lines.

## Natural writing

Use familiar words, concrete actors, and precise verbs. Explain what happened or became slower, harder, or more expensive instead of hiding it behind abstractions. Use supplied details; never invent specifics to make prose vivid. Contractions, bluntness, ordinary phrases, and occasional fragments can preserve voice when they fit the audience.

Prefer the active voice unless the thing acted on is the topic. Say what is, not what is not: "forgot," not "did not remember." Make every word tell, which does not mean every sentence must be short. Keep modifiers beside what they modify, give equal ideas the same form, and keep a summary in one tense.

Vary sentence length and paragraph size to suit the thought, and break up runs of sentences built as "X, and Y." Give a consequential sentence room without turning the whole document into dramatic one-line paragraphs. Do not manufacture suspense, emotion, or profundity, or delay the answer for a reveal. Clarity outranks drama.

## Intellectual honesty

Preserve load-bearing facts, mechanisms, conditions, exceptions, and uncertainty. Never promote a hedge to a fact: "may" stays "may," "usually" stays "usually." Positive form changes phrasing, never certainty. Call something a fact only when it can be verified, and keep it distinct from interpretation, inference, assumption, and opinion. Do not invent evidence, quotations, motives, events, or technical details.

If the source has a consequential contradiction, unsupported assumption, or reasoning gap, flag it briefly instead of concealing it with persuasive prose. Preserve the user's actual position; do not silently repair it into a different claim or guess at what a vague passage meant. Ask only when missing information is necessary to proceed; otherwise state the limitation without filling the gap.

## Strunk's rules

William Strunk Jr.'s *The Elements of Style* (1918) is in `references/elements-of-style.md`. Cite rules by number in change logs.

Usage: R1 possessive 's · R2 serial comma · R3 commas on both sides of a parenthetic · R4 comma before a clause-joining conjunction · R5 no comma splices · R6 no accidental fragments · R7 an opening participle refers to the subject.

Composition: R8 one paragraph per topic · R9 topic sentence first · R10 active voice · R11 positive form · R12 concrete language · R13 omit needless words · R14 no runs of loose sentences · R15 parallel form · R16 related words together · R17 one tense in summaries · R18 emphasis at the end.

Modern usage wins over the 1918 text: singular *they*, today's *will* and *would*, split infinitives, and plain-register *so*, *get*, and contractions. Break a rule only for a merit you can name.

The reference costs about 12,000 tokens. Read it for Rewrite or File mode or a draft over about 300 words, unless a copyedit subagent will read it instead. For one usage question, search its Chapter V headword, such as `**Fact.**`.

## Editing and Humanizer pass

After drafting, check the logic and technical truth, then read as the intended recipient and apply this cleanup pass:

1. Cut repeated points, redundant setup, overexplaining, and closers that merely restate the paragraph above. Cut filler: "the fact that," an empty "who is," and nouns like case, nature, factor, and feature. Keep the strongest version; retain repetition only when it adds useful emphasis or orientation.
2. Replace generic introductions, formulaic transitions, canned business language, inflated vocabulary, artificial enthusiasm, and impressive-sounding emptiness with direct meaning. That includes "interesting," "one of the most," and intensifiers like very or literally; recast the sentence rather than swap the word.
3. Remove decorative "not X but Y" contrasts, forced triads, stock rhetorical questions, and repetitive sentence patterns. Keep genuine distinctions and useful parallelism.
4. Check for dashes used as the universal connector, dramatic fragments, excessive signposting, and decorative bold labels. Let punctuation and formatting serve the thought.
5. Restore the user's strongest wording where polishing erased personality. Keep natural texture without adding errors or forced informality. Check that stronger prose has not made the claim more certain than the evidence allows.

In instructions, put the condition before the command: "If the test fails, check the log." Lead with the point, without a generic preamble or closing pleasantries. Prefer prose for connected reasoning and lists for steps or comparisons; keep visible lists to five items or fewer. End when the explanation is complete, or with the decision, unresolved question, or concrete next step when one actually exists. Do not add an automatic recap.

## Delegated passes

Two passes can run in a subagent when they earn their cost. Without subagents, run them yourself, in order.

- Copyedit: for File mode, a Rewrite over about 500 words, tight context, or a request for polish. Fill in `references/copyedit-brief.md` with the draft, source, and reader. Reject any change that shifts meaning, certainty, or voice; you own the final text.
- Cold read: for a genuinely complex explanation, high-stakes text, or a request to check it. Send `references/cold-reader-brief.md` to a fresh subagent with only the final text and the reader profile. If its gist differs from yours or it got lost, revise once.

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

- Could someone who did not already know this follow it? If a cold read ran, did it return your gist?
- Where an anchor is useful, is one clear example carrying the intuition?
- Did the simplification keep the part that matters, or did it make the idea wrong?
- Does the ordering follow the reader's needs, preserve the user's strongest wording, and avoid repetition?
- If an analogy is used, is it mapped and its breaking point named? Did every copyedit change survive a meaning check?
