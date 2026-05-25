---
name: related-work
description: Write a rigorous related-work document for an ML/AI research project, with topic-based organization, primary-source verification, and per-paper entries containing methodology, conclusion, limitations, and implications. Use when the user requests writing or iterating on a related-work section that needs to be self-contained (readers should not need to read the original papers), organized by research themes rather than chronology, and rigorously verified against original sources. Use for tasks like "write related work", "expand the related work", "add literature review", "verify citations in the related work".
---

# Related Work Document Writing

This skill encodes a workflow for writing rigorous related-work documents for ML/AI research proposals and papers. The key constraint: **read primary sources before writing, mark uncertainty explicitly, no hallucinations**. The skill is general: it does not assume a specific research subfield.

## When to use this skill

The user is writing a related-work document (typically a separate `01_related_work.md` file in a multi-file research proposal, or a long related-work section in a paper). The document must be:

- Self-contained (readers should understand each paper without reading the original)
- Topic-organized (not chronological or author-alphabetical)
- Rigorously sourced (specific section references on each claim)
- Information-dense (significantly more than a typical conference-paper related-work)

## Core principles

1. **Read before writing.** For each paper, fetch the primary source (arXiv PDF, conference proceedings, or OpenReview submission) before writing the entry. Search-result snippets are insufficient and lead to errors. Fetch and verification mechanics are in `references/verification.md`.

2. **Verify every claim; mark only as a last resort.** Make a genuine effort to confirm each claim against the primary source — alternate fetch routes, searching for the specific number or section, cross-checking versions. Only a claim that still cannot be confirmed gets marked `[verify §X]` rather than guessed. A marker flags a residual for the user to resolve; it is not a shortcut to skip verification.

3. **Cite sections, not papers.** Each bullet under Methodology and Conclusion should include a parenthetical paper-section reference: `(§3.1)`. This lets the user spot-check claims.

4. **Honest about scope.** Methodology, Conclusion, Limitations, and Implications are distinct categories. Methodology is *what they did*, Conclusion is *what they found*, Limitations is *what they didn't cover*, Implications is *how it informs our work*.

5. **One paper, one entry.** Do not group multiple papers in a single entry unless they are the same line of work (e.g., a thread of papers from one lab with shared methodology). Even then, give each paper its own visible header.

## Workflow

### Step 1: Agree on topic organization

Before fetching any papers, agree with the user on the topic structure. A typical ML/AI review organizes into 6–10 topics, ordered framing → phenomenon → methodology → setting → adjacent → supporting, and closed by a summary table. See `references/topic-organization.md` for the ordering principle, a generic template, and per-section paper counts.

### Step 2: List papers per topic

For each topic, list candidate papers. Aim for 3–6 papers per topic. Cite each by title, arXiv ID, year, venue. If a topic exceeds 6 papers it is likely two topics in disguise — split it (see the paper-count caps in `references/topic-organization.md`).

### Step 3: Decide on workflow scale

| Scale | Approach |
|---|---|
| <10 papers | Write sequentially in one pass, fetching each source. |
| 10–20 papers | Sequential, but checkpoint after each section. |
| 20+ papers | Decompose into one subagent per topic section (see below). |

**Subagent decomposition (20+ papers).** The natural unit is a topic section: each subagent receives the section topic, its paper list, and the entry + verification references, and returns a complete section. Sections are independent, so each subagent's context stays bounded. Keep three things on the main thread, never in subagents: the §1 framing section (it sets the document's conceptual frame), the closing summary table (it needs cross-section synthesis), and any cross-section paper placement. After each subagent returns, confirm every assigned paper has an entry and that `[verify]` markers appear where verification was incomplete — their absence can signal hallucination. Prefer sequential subagents; use parallel only for 30+ papers under a deadline.

### Step 4: Write each entry

For each paper:

1. Fetch the primary source and skim Abstract, Introduction, Methodology, and Conclusion. Follow the fetch strategy and source rules in `references/verification.md`.
2. Write the entry following the template in `references/entry-format.md`.
3. For each Methodology and Conclusion bullet, include the paper-section reference `(§X.Y)`.
4. If a specific claim still cannot be confirmed after checking the source, mark `[verify §X]` — do not guess.

### Step 5: Write the summary table

After all topic sections, write the §X (typically §10) Summary of Gaps and Positioning: a 2-column table mapping each identified gap in the literature to the RQ that addresses it. See the summary-table section of `references/entry-format.md` (§6).

### Step 6: Verification pass

After completing all sections, run the verification checklist in `references/verification.md`:

1. Search the document for `[verify]` markers and either confirm or flag for the user.
2. Replace remaining vague claims with section-cited specifics.
3. Spot-check arXiv IDs by fetching them (models sometimes invent IDs).
4. Check that each paper has all four bullet categories (Methodology, Conclusion, Limitations, Implications).

## Reference files

- `references/entry-format.md` — read in Step 4 (per-paper entry template) and Step 5 (closing gap-to-RQ summary table format).
- `references/verification.md` — read in Step 4 (fetch strategy, what counts as a source) and Step 6 (verification checklist, `[verify]` notation).
- `references/topic-organization.md` — read in Steps 1–2 (topic ordering principle, generic template, per-section paper counts).

## Anti-patterns to avoid

- **Citing from search snippets.** Search results often summarize papers inaccurately. Always fetch the source.
- **Vague Methodology bullets.** "They study X" is not Methodology; "(§3.1) They sample 6,000 examples and fine-tune for one epoch" is Methodology.
- **Conflating Methodology and Conclusion.** Methodology = what they did; Conclusion = what they found. Do not mix.
- **Hand-waving Limitations.** "They only test on one model family" is fine; "their methodology is somewhat limited" is not.
- **Generic Implications.** "Provides background for our work" is not an implication; "Direct supporting evidence for H2a; methodology transferable to our RQ2 experiments" is.
- **Inventing arXiv IDs.** If unsure of the arXiv ID, mark `[verify arXiv]` and continue. Inventing leads to broken citations.
- **Skipping limitations.** Every paper has limitations. If you cannot identify any, you have not read carefully enough.
