# Subagent Decomposition Strategy

For related-work documents covering 20+ papers, sequential writing is slow and context-heavy. Decompose into subagent tasks running in parallel.

## When to decompose

| Total papers | Approach |
|---|---|
| < 10 | Sequential, single pass |
| 10–20 | Sequential with per-section checkpoints |
| 20–40 | Parallel subagents per topic section |
| 40+ | Hierarchical: one subagent per section, plus a coordinator that merges and writes the summary table |

## Decomposition by topic

The natural unit of decomposition is a topic section (e.g., "§3 Multi-Agent Training Paradigms"). Each subagent:

1. Receives: section topic, list of papers in that section, the paper-entry template, the verification policy.
2. Returns: a complete section with all paper entries.

This works because:
- Sections are independent (no cross-references within paper entries, only in the summary table).
- Each subagent has bounded context (3–6 papers × 5–10 min skim = manageable).
- Coordinator can review section outputs before assembling.

## Subagent prompt template

```
You are writing one section of a related-work document for an ML safety research proposal.

CONTEXT:
- Project: [one-paragraph project summary, including main RQs and contribution claims]
- This section: §{N} {Topic Name}
- Section topic: [what this section covers]

TASK:
Write {N} paper entries following the paper-entry-format.md template.

PAPERS IN THIS SECTION:
1. {Title 1} ({arXiv ID}, {Year}, {Venue})
2. {Title 2} ({arXiv ID}, {Year}, {Venue})
3. {Title 3} ({arXiv ID}, {Year}, {Venue})
[...]

WORKFLOW:
For each paper:
1. Fetch the primary source (arxiv.org/pdf/{ID} or html version)
2. Skim Abstract, Introduction, Methodology, Conclusion
3. Write the entry following the template
4. Mark uncertain claims with [verify §X]

FORMAT: Strict adherence to paper-entry-format.md template. Each entry must include:
- Title with arXiv ID, date, venue
- One-sentence description
- Research question
- Methodology bullets with (§X.Y) refs
- Conclusion bullets with (§X.Y) refs
- Limitations
- Implications for our work — citing specific RQs/hypotheses

OUTPUT: Markdown text for the section, ready to insert into the document.

STRICT RULE: No hallucinations. If you cannot fetch a paper, mark its entry [verify — original not accessible] and continue. Do not invent section numbers or quantitative results.
```

## Coordinator role

The coordinator agent (or the main thread):

1. Defines the topic structure and paper list per topic.
2. Spawns one subagent per topic.
3. Collects section outputs.
4. Assembles them into the final document.
5. Writes the §X (final) Summary of Gaps and Positioning table — this requires cross-section knowledge.
6. Runs the verification pass: search for `[verify]` markers, flag to the user.

## Parallel vs sequential subagents

For most cases, **sequential subagents** (one section at a time, each completing before the next starts) are sufficient and less expensive than parallel.

Use parallel subagents only when:
- 30+ papers
- Strict time deadline
- Sections are confirmed independent (no thematic overlap that might cause subagents to make conflicting claims)

## What NOT to delegate to subagents

- **The §1 framing section.** This sets the conceptual frame of the entire document and should be written by the main thread with full project context.
- **The §X summary table.** This requires synthesizing across all sections; it cannot be written by a section-bounded subagent.
- **Cross-section references.** If a paper is genuinely relevant to two sections, the main thread should decide where it belongs and reference it from the other section.

## Checklist for subagent quality

After each subagent returns, check:

- [ ] All papers in the assigned list have entries.
- [ ] Each entry follows the exact template.
- [ ] `[verify]` markers are present where verification was incomplete (good sign — means subagent did not hallucinate).
- [ ] Implications bullets reference specific RQs / hypotheses by number.
- [ ] Word count per entry is appropriate (150–400 words).
- [ ] No filler phrases, no AI clichés.

If a subagent's output has fewer `[verify]` markers than expected, suspect hallucination and spot-check the section references manually.

## Example decomposition for a 30-paper review

Topic structure (10 topics, 3 papers average):

1. Multi-Agent Risk Taxonomy (3 papers) → Subagent 1
2. Emergent Misalignment (5 papers) → Subagent 2
3. Multi-Agent Training Paradigms (4 papers) → Subagent 3
4. Bias and Conformity in MAS (5 papers) → Subagent 4
5. Human-AI Interaction (3 papers) → Subagent 5
6. LLM Oversight (4 papers) → Subagent 6
7. Avalon Setting (3 papers) → Subagent 7
8. Sabotage Evaluation (3 papers) → Subagent 8
9. Supporting Methods (3 papers) → Subagent 9
10. Summary table (written by coordinator after sections 1–9 complete)

Each subagent: ~30–60 minutes of work (skim 3–5 papers, write entries, verify).
Coordinator: 30 minutes to assemble + write summary table + verification pass.

Total wall-clock: ~6 hours if sequential, ~1.5 hours if parallel (limited by slowest subagent).
