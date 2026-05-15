# Formatting Conventions

These rules apply uniformly across all proposal artifacts.

## Language

- **Discussion (chat-mode) is in the user's preferred language** (often Chinese for Chinese-speaking users).
- **Artifacts (proposal files) are in English** unless the user requests otherwise. This keeps the proposal usable across review processes.

## Headers

- Use `#` for the document title (one per file), `##` for top-level sections, `###` for subsections, `####` for sub-subsections.
- **Number top-level and subsection headers**: `## 1 Motivation`, `### 1.1 Why Avalon`, `#### 1.1.1 Hidden information`.
- **Do not jump levels.** `##` must precede `###` which must precede `####`.
- **Do not use bold text as headers.** Use the markdown header syntax.

## Punctuation

- **No em-dashes (—).** Replace with periods, parentheses, or commas. (An exception: when quoting source material that contains em-dashes verbatim.)
- **Use colons to introduce bullet lists**: `**Methodology:**` followed by bullets, not `Methodology` followed by bullets.
- Use Chinese full-width punctuation in Chinese discussion (，。：；""''（）「」、——……); English half-width in artifacts.

## Citations

- **Cite arXiv ID, year, venue** at first appearance: `Betley et al. (2025), Emergent Misalignment (arXiv:2502.17424; ICML 2025; Nature 2026)`.
- After first appearance, abbreviate: `Betley et al. (2025)`.
- For ICLR/NeurIPS/ICML papers, note venue and year: `(ICLR 2026)`.
- For non-arXiv sources (technical reports, OpenReview-only), state the source directly.

## Bullet lists

- Use bullets for: enumerated examples, pre-registered effect sizes, defense designs, hypotheses, implications.
- Each bullet starts with a capital letter and ends with a period unless it's a phrase fragment in a tight list.
- Bullets should be 1–2 sentences. Three sentences is the maximum.
- Do not nest bullets more than two levels deep.

## Tables

- Use tables for: factor matrices, RQ-to-cell mappings, paper-section listings, comparison summaries.
- Keep tables compact (no more than 4 columns typical).
- Add a one-sentence caption or topic sentence before the table.

## Prose style

- **Active voice preferred.** "We trained..." not "Training was conducted...".
- **Concrete over abstract.** "20% misalignment rate" rather than "substantial misalignment rate".
- **One claim per sentence in the abstract/contributions sections.** Reviewers skim these; pack 1 claim per sentence.

## AI clichés to avoid

These words signal "AI-generated text" to reviewers and should be replaced with concrete alternatives:

- *delve into* → study, examine, analyze
- *leverage* → use, apply, exploit
- *robust* (when used vaguely) → specify how it is robust
- *pivotal* → important, critical, central
- *foster* → enable, support, produce
- *transformative* → specify what is changing
- *seamless* → cite the concrete property
- *underscore* → emphasize, show, demonstrate
- *realm* / *landscape* / *tapestry* → drop these metaphors entirely
- *Not only X, but Y* / *不仅 X，更是 Y* → use plain enumeration if both are intended

## What to drop entirely

- **Filler phrases.** "It is important to note that...", "Notably,", "Interestingly,", "It is worth mentioning that...".
- **Reviewer-comfort phrases.** "Great question!", "希望对你有帮助" (I hope this helps).
- **Hedging without information.** "may potentially possibly contribute to..." → "contributes to...".

## Format checks before finalizing

- Search for `—` (em-dashes) and replace.
- Search for `not only ... but` constructions.
- Search for any cliché word from the list above.
- Verify header numbering is sequential (no skipped levels).
- Verify every bullet ends consistently (sentence or fragment, applied uniformly within a list).
