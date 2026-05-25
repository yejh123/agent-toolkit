# Paper Entry and Summary Table Formats

Output formats for the related-work document: the per-paper entry used in every topic section, and the closing gap-to-RQ summary table.

## Table of Contents

1. Per-paper entry template
2. Schematic example
3. Rules per field
4. Section reference notation
5. Length per entry
6. Closing summary table

## 1 Per-paper entry template

Every paper entry follows this exact template. Section ordering is fixed; do not rearrange.

```markdown
### {Title} ({arXiv ID}, {Month Year}, {Venue})

{One-sentence description: who did what study, in one sentence.}

**Research question:** {Single sentence summarizing the central question the paper asks.}

**Methodology:**
- (§{X.Y}) {Specific detail about study design, data, or procedure.}
- (§{X.Y}) {Specific detail.}

**Conclusion:**
- (§{X.Y}) {Specific finding with quantitative result where possible.}
- (§{X.Y}) {Specific finding.}

**Limitations:**
- {What the paper does not cover or address.}
- {Methodological limitation acknowledged or inferable.}

**Implications for our work:**
- {How this paper informs our project: which RQ, hypothesis, or design decision it supports.}
```

## 2 Schematic example

Placeholders mark where project-specific content goes. Filled with real content, a foundational entry runs 200–400 words.

```markdown
### [Paper Title] (arXiv:NNNN.NNNNN, [Mon Year], [Venue])

[One sentence: which lab or authors ran what kind of study.]

**Research question:** [The single central question the paper asks, ending with a question mark.]

**Methodology:**
- (§[X.Y]) [Study design: data source, sample size, model(s), training or evaluation procedure.]
- (§[X.Y]) [Control conditions or comparison setup.]
- (§[X.Y]) [Evaluation metric and how it is computed.]

**Conclusion:**
- (§[X.Y]) [Primary finding with a number, e.g. "[metric] rose from [x]% to [y]%".]
- (§[X.Y]) [Secondary finding.]
- (§[X.Y]) [A claim the authors interpret, kept distinct from the raw result.]

**Limitations:**
- [Scope restriction the authors acknowledge, e.g. one model family only.]
- [Generalization gap, inferable even if unstated.]
- [What was not tested.]

**Implications for our work:**
- [The specific RQ or hypothesis it supports, e.g. "supporting evidence for H2a".]
- [The methodology or finding that transfers, or the gap our RQ_n fills relative to this paper.]
```

## 3 Rules per field

### Title line

- Use `###`. The title is the paper's actual title; do not paraphrase.
- arXiv ID format: `arXiv:NNNN.NNNNN`.
- Date: month and year (e.g., `Feb 2025`).
- Venue: official venue including year (e.g., `ICML 2025`, `NeurIPS 2025 D&B`, `Nature 2026`). If only on arXiv, write `arXiv`.

### One-sentence description

- Lead with the institution(s) or first-author lab if it helps context.
- State what study was done in one sentence. Do not editorialize.

### Research question

- One sentence ending in a question mark; capture the central inquiry, not a side finding.
- If the paper has several questions, pick the central one and note in Methodology that others are addressed.

### Methodology bullets

- 3–6 bullets typical, 8 maximum. Each starts with `(§X.Y)`.
- Specify data, model, procedure, control conditions, and evaluation metric. Add quantitative details where available.
- Distinct from Conclusion: Methodology = what they did; Conclusion = what they found.

### Conclusion bullets

- 3–6 bullets typical. Each starts with `(§X.Y)`.
- State specific findings with numbers where possible (`"20% accuracy drop"`, `"κ = 0.88"`, `"d = 0.4"`).
- State findings directly; avoid hedging. Distinguish empirical findings from the authors' interpretation.

### Limitations bullets

- 3–5 bullets typical. Cover scope restrictions, generalization gaps, methodological constraints, what was not tested.
- Cite the paper's own Limitations section if it has one (`(§7 limitations)`). Note implicit limitations too (e.g., "all examples in English; no cross-language test").

### Implications for our work bullets

- 2–5 bullets typical. Each should name the specific RQ or hypothesis it supports, identify what transfers, or identify the gap the project fills relative to this paper.
- Use concrete language: "supports H2a", "transferable methodology for X", "our RQ3 extends to Y". Avoid "provides background", "is relevant to our work".

## 4 Section reference notation

- `(§3.1)` is preferred over `(Section 3.1)`.
- Use numbered subsections only; do not invent section numbers.
- Spanning multiple sections: `(§3.1, §3.2)`. Appendices: `(§A.2)`. Tables or figures: `(§4.2, Table 3)`.
- Uncertain section number: `[verify §X]`, where X is the best guess.

## 5 Length per entry

- Foundational papers (in §1 framing or §2 core phenomenon): 200–400 words.
- Standard papers: 150–250 words.
- Supporting or supplementary papers: 100–150 words.

If an entry exceeds 400 words it likely repeats itself. Compress by removing information repeated across Methodology / Conclusion / Implications, consolidating similar bullets, and cutting bullets that do not serve the implication.

## 6 Closing summary table

The document's final section is a gap-to-RQ table. It answers the reviewer's question after reading the whole review: "what is this proposal's contribution?" It is the single most important section for novelty defense.

### Format

```markdown
## {N} Summary of Gaps and Positioning

| Gap in existing literature | Addressed by |
|---|---|
| {Specific gap, citing a source} | RQ{n} (specifically H{na}/H{nb}) |
| {Specific gap} | RQ{n}, RQ{m} |

The proposal positions {contribution 1} (with {explicit incremental labels}), and {contribution 2}.
```

### Schematic example

```markdown
## 10 Summary of Gaps and Positioning

| Gap in existing literature | Addressed by |
|---|---|
| [Phenomenon] studied for [contexts A, B] (Author et al., Year) — never for [context C] | RQ1 (H1b) |
| [Effect] studied for [inherent case] (Author et al., Year) — not for [trained-in case] | RQ2 (H2b, H2c) |
| [Single-setting result] well-studied (Author et al., Year) — [multi-setting extension] unstudied | RQ3–RQ5 |
| [Method] uses [human participants] (Author, Year) — [fully automated variant] does not exist | E1, E2 (methodology contribution) |

The proposal positions Track 1 as [one-sentence contribution] (with [H1a/H2a] as confirmatory extensions, explicitly flagged), and Track 2 as [one-sentence contribution].
```

### Rules per column

**Left column (gaps).** Each gap has two parts: "{what is studied}" — "{what is not studied}". Cite at least one paper exemplifying the existing literature. Be specific: "[area] not fully understood" is not a gap.

**Right column (RQs).** Cite by RQ number, optionally with a hypothesis label. For gaps addressed by methodology rather than an RQ, cite the methodology element. List multiple RQs together when they jointly address a gap (`RQ3–RQ5`).

### What this section is NOT

- Not a list of all RQs — only *gaps* mapped to RQs. An incremental RQ that addresses no gap gets no row.
- Not a list of all papers — only the foundational papers exemplifying each gap.
- Not new claims — every gap must be supported by entries in earlier sections.

### Length

Typical 4–8 rows; skim-able in 30 seconds. 10+ rows means some gaps are subdivisions of larger gaps — consolidate.
