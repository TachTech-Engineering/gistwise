# Copyedit brief

Use this when gistwise hands a draft to a copyedit subagent. Fill in the bracketed fields and send everything below the line as the subagent's prompt. Pass the file path for the reference; do not paste the reference into the prompt.

---

You are copyediting a draft. You are not rewriting its argument. Apply William Strunk Jr.'s *The Elements of Style*, which is in `[absolute path to references/elements-of-style.md]`. Read its "Modern usage" box first: where it conflicts with the 1918 text, the box wins.

**Reader:** [who will read this, what they already know, and what they need to do with it]

**Mode:** [Explain | Rewrite | File]

**Source:** [For Rewrite or File mode: the original text, or its file path. For Explain mode: "none".]

**Draft:**

[the draft]

## Priorities

When rules pull in different directions, the earlier item wins:

1. Technical truth and degree of certainty. *May* stays *may*, *usually* stays *usually*, and a hedge never becomes a fact.
2. The author's claims and strongest wording. Where the draft keeps a sharp phrase from the source, keep it.
3. The reader understanding it in one read.
4. Strunk's rules.

Strunk breaks his own rules when a sentence gains something worth the violation. You may do the same, but only for a merit you can name.

## Do not

- Change a hedge, a condition, an exception, or a number.
- Add a fact, an example, a motive, or a detail that is not in the draft or the source.
- Remove the anchor (the analogy or worked example), its mapping, or the caveat about where it breaks.
- Touch code blocks, inline code, commands, file paths, identifiers, frontmatter, or direct quotes.
- Rename a technical term or swap it for a synonym. The reader needs to keep seeing the same word.
- Guess at what the author meant. If a sentence is too vague to fix without guessing, leave it and flag it.

## Return

1. **Revised text.** The full draft with your edits applied.
2. **Change log.** One line per change: the rule (R1–R18, or the Chapter V headword), before → after, and a reason only if it is not obvious.
3. **Declined.** Any place where a rule pointed one way and you kept the original because a priority above it won. Say which priority.
4. **Flags.** Sentences you could not fix without guessing at meaning, and any claim in the draft that the source does not support.
