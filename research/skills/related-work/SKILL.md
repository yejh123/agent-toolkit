---
name: ml-related-work-document
description: Write a rigorous related-work document for an ML, AI safety, alignment, or multi-agent research project, with topic-based organization, primary-source verification, and per-paper entries containing methodology, conclusion, limitations, and implications. Use when the user requests writing or iterating on a related-work section that needs to be self-contained (readers should not need to read the original papers), organized by research themes rather than chronology, and rigorously verified against original sources. Use for tasks like "write related work", "expand the related work", "add literature review", "verify citations in the related work".
---

# ML Related Work Document Writing

This skill encodes a workflow for writing rigorous related-work documents for ML research proposals and papers. The key constraint: **read primary sources before writing, mark uncertainty explicitly, no hallucinations**.

## When to use this skill

The user is writing a related-work document (typically a separate `01_related_work.md` file in a multi-file research proposal, or a long related-work section in a paper). The document must be:

- Self-contained (readers should understand each paper without reading the original)
- Topic-organized (not chronological or author-alphabetical)
- Rigorously sourced (specific section references on each claim)
- Information-dense (significantly more than typical conference paper related-work)

## Core principles

1. **Read before writing.** For each paper, fetch the primary source (arXiv PDF, conference proceedings, or OpenReview submission) before writing the entry. Search-result snippets are insufficient and lead to errors.

2. **Mark uncertainty.** When a specific claim cannot be verified from the source, mark it `[verify §X]` rather than guess. The user can replace these later.

3. **Cite sections, not papers.** Each bullet under Methodology and Conclusion should include a parenthetical paper-section reference: `(Section 3.1)` or `(§3.1)`. This lets the user spot-check claims.

4. **Honest about scope.** Methodology, Conclusion, Limitations, and Implications are distinct categories. Do not conflate them — Methodology is *what they did*, Conclusion is *what they found*, Limitations is *what they didn't cover*, Implications is *how it informs our work*.

5. **One paper, one entry.** Do not group multiple papers in a single entry unless they are part of the same line of work (e.g., a thread of papers from the same lab with shared methodology). Even then, give each paper its own visible header.

## Workflow

### Step 1: Brainstorm topic organization

Before fetching any papers, agree with the user on the topic structure. Typical ML safety / multi-agent papers organize into 8–10 topics. See `references/common-topics.md` for templates.

The topic order should follow this logic:
1. **Framing** — risk taxonomies, problem definitions (sets the field-level context)
2. **Phenomenon** — papers establishing the central phenomenon the project extends
3. **Methodology contributors** — training paradigms, evaluation frameworks the project uses or extends
4. **Setting** — papers specific to the experimental testbed
5. **Adjacent areas** — related but tangential work that bounds the contribution
6. **Supporting methods** — technical infrastructure (e.g., RL algorithms, persona vectors) used in the project

### Step 2: List papers per topic

For each topic, list candidate papers. Aim for 3–6 papers per topic. Cite each by: title, arXiv ID, year, venue.

If the list exceeds 6 papers per topic, the topic is likely two topics in disguise. Split it.

### Step 3: Decide on workflow scale

| Scale | Approach |
|---|---|
| <10 papers | Write sequentially in one pass, fetching each source. |
| 10–20 papers | Sequential, but checkpoint after each section. |
| 20+ papers | Subagent decomposition (see `references/subagent-strategy.md`). |

### Step 4: Write each entry following the fixed format

See `references/paper-entry-format.md` for the exact template and a worked example.

For each paper:
1. Fetch the primary source.
2. Skim Abstract, Introduction, Methodology, and Conclusion sections.
3. Write the entry following the template.
4. For each Methodology and Conclusion bullet, include the paper-section reference: `(§3.1)`.
5. If a specific claim cannot be confirmed from the fetched content, mark `[verify §X]`.

### Step 5: Write the summary table

After all topic sections, write a §X (typically §10) Summary of Gaps and Positioning. This is a 2-column table mapping each identified gap in the literature to the specific RQ that addresses it. See `references/summary-table-format.md`.

### Step 6: Verification pass

After completing all sections:
1. Search the document for `[verify §X]` markers and either confirm or flag for the user.
2. Search for any remaining vague claims and replace with section-cited specifics.
3. Verify all arXiv IDs by spot-checking (the AI sometimes invents arXiv IDs).
4. Check that each paper has all four bullet categories (Methodology, Conclusion, Limitations, Implications).

## Reference files

- `references/paper-entry-format.md` — exact format for one paper entry, with worked example
- `references/verification-policy.md` — when to mark `[verify §X]`, what counts as verified, fetch strategies
- `references/subagent-strategy.md` — decomposition pattern for >20-paper reviews
- `references/common-topics.md` — typical topic organization for ML safety / alignment / multi-agent papers
- `references/summary-table-format.md` — gap-to-RQ summary table at end of document

## Anti-patterns to avoid

- **Citing from search snippets.** Search results often summarize papers inaccurately. Always fetch the source.
- **Vague Methodology bullets.** "They study X" is not Methodology; "(§3.1) They sample 6,000 examples of insecure code and fine-tune GPT-4o for one epoch" is Methodology.
- **Conflating Methodology and Conclusion.** Methodology = what they did; Conclusion = what they found. Do not mix.
- **Hand-waving Limitations.** "They only test on one model family" is fine; "their methodology is somewhat limited" is not.
- **Generic Implications.** "Provides background for our work" is not an implication; "Direct supporting evidence for H2a; methodology (vary topology while measuring bias) is transferable to our trained-AI experiments for RQ2" is an implication.
- **Inventing arXiv IDs.** If unsure of the arXiv ID, mark `[verify arXiv]` and continue. Inventing leads to broken citations.
- **Skipping limitations.** Every paper has limitations. If you cannot identify any, you have not read carefully enough.
