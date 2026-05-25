# Writing Style

Formatting and prose conventions for all proposal artifacts.

## Table of Contents

1. Headers
2. Punctuation
3. Citations
4. Bullet lists
5. Tables
6. Prose style
7. AI clichés to avoid (bilingual)
8. Filler to drop
9. Pre-finalization checks

## 1 Headers

- Use `#` for the document title (one per file), `##` for top-level sections, `###` for subsections, `####` for sub-subsections.
- Number top-level and subsection headers: `## 1 Motivation`, `### 1.1 Why X`, `#### 1.1.1 Hidden information`.
- Do not jump levels. `##` must precede `###`, which must precede `####`.
- Do not use bold text as a header substitute. Use markdown header syntax.

## 2 Punctuation

- **No em-dashes (—).** Replace with periods, parentheses, or commas. (Exception: when quoting source material that contains em-dashes verbatim.)
- Use a colon to introduce a bullet list: `**Methodology:**` followed by bullets, not `Methodology` followed by bullets.

## 3 Citations

- Cite arXiv ID, year, and venue at first appearance: `Smith et al. (2025), Title (arXiv:2501.12345; ICML 2025)`.
- After first appearance, abbreviate: `Smith et al. (2025)`.
- For ICLR / NeurIPS / ICML papers, note venue and year: `(ICLR 2026)`.
- For non-arXiv sources (technical reports, OpenReview-only entries), state the source directly.

## 4 Bullet lists

- Use bullets for enumerated examples, pre-registered effect sizes, defense designs, hypotheses, implications.
- Each bullet starts with a capital letter and ends with a period, unless it is a phrase fragment in a tight list. Apply the choice uniformly within one list.
- Bullets should be 1–2 sentences. Three sentences is the maximum.
- Do not nest bullets more than two levels deep.

## 5 Tables

- Use tables for factor matrices, RQ-to-experimental-cell mappings, paper-section listings, comparison summaries.
- Keep tables compact: 4 columns is typical, more is rarely justified.
- Add a one-sentence caption or topic sentence before the table.

## 6 Prose style

- **Active voice preferred.** "We trained..." not "Training was conducted...".
- **Concrete over abstract.** "20% accuracy drop" rather than "substantial accuracy drop".
- **One claim per sentence** in the abstract and contributions sections. Reviewers skim these; pack one claim per sentence.

## 7 AI clichés to avoid (bilingual)

These words and constructions signal "AI-generated text" to reviewers. Replace with concrete alternatives.

**English word replacements:**

- *delve into* → study, examine, analyze
- *leverage* → use, apply, exploit
- *robust* (when used vaguely) → specify how it is robust
- *pivotal* → important, critical, central
- *foster* → enable, support, produce
- *transformative* → specify what is changing
- *seamless* → cite the concrete property
- *underscore* → emphasize, show, demonstrate
- *realm* / *landscape* / *tapestry* → drop these metaphors entirely

**Bilingual constructions to avoid:**

- English "Not only X, but Y" → plain enumeration if both are intended.
- Chinese `不仅 X，更是 Y` → plain enumeration.

## 8 Filler to drop

- **Filler phrases.** "It is important to note that...", "Notably,", "Interestingly,", "It is worth mentioning that...".
- **Reviewer-comfort phrases.** "Great question!", "希望对你有帮助" ("I hope this helps").
- **Hedging without information.** "may potentially possibly contribute to..." → "contributes to...".

## 9 Pre-finalization checks

Before finalizing the proposal, run these search-and-replace passes:

- Search for `—` (em-dashes) and replace.
- Search for "not only ... but" and `不仅 ... 更是` constructions.
- Search for any cliché word listed in §7.
- Verify header numbering is sequential (no skipped levels).
- Verify every bullet within a list ends consistently (sentence or fragment, applied uniformly).
