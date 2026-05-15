# Paper Entry Format

Every paper entry follows this exact template. Section ordering is fixed; do not rearrange.

## Template

```markdown
### {Title} ({arXiv ID}, {Month Year}, {Venue})

{One-sentence description: who did what study, in one sentence.}

**Research question:** {Single sentence summarizing the central question the paper asks.}

**Methodology:**
- (§{X.Y}) {Specific detail about study design, data, or procedure.}
- (§{X.Y}) {Specific detail.}
- (§{X.Y}) {Specific detail.}

**Conclusion:**
- (§{X.Y}) {Specific finding with quantitative result where possible.}
- (§{X.Y}) {Specific finding.}
- (§{X.Y}) {Specific finding.}

**Limitations:**
- {What the paper does not cover or address.}
- {Methodological limitation acknowledged or inferable.}
- {Generalization gap.}

**Implications for our work:**
- {How this paper informs our project: which RQ, hypothesis, or design decision it supports.}
- {Concrete usage: cited evidence for hypothesis H_n, methodology transferable to our X, gap our RQ_n fills.}
```

## Worked example

```markdown
### Multi-Agent Risks from Advanced AI (arXiv:2502.14143, Feb 2025, Cooperative AI Foundation Technical Report #1)

Multi-organization 96-page position paper from ~50 authors at the Cooperative AI Foundation, DeepMind, Anthropic, CMU, Harvard, Oxford, and others, providing the field-canonical taxonomy of multi-agent AI risks.

**Research question:** What new or qualitatively different risks emerge in multi-agent AI systems (vs single-agent systems), and what research and governance directions can mitigate them?

**Methodology:**
- (§1) Position-paper synthesis, not empirical. Authors define a multi-agent system, scope the report to risks that emerge or are qualitatively different in multi-agent settings, and survey related work in cooperative AI, complex systems, and AI safety.
- (§1.2) Scope is restricted to: (i) risks that arise specifically because multiple AI agents are present, (ii) advanced AI agents, (iii) risks anchored to real-world events or experiments where possible, (iv) technical perspective.
- (§2, §3) Two-level taxonomy: three failure modes plus seven cross-cutting risk factors.
- (§B) Three case studies grounding the abstract risks.

**Conclusion:**
- (§2.1) *Miscoordination* defined as failure to cooperate despite shared goals.
- (§2.2) *Conflict* defined as failure to cooperate due to divergent goals.
- (§2.3) *Collusion* defined as undesirable cooperation in competitive settings.
- (§3.1–§3.7) Seven risk factors: information asymmetries, network effects, selection pressures, destabilising dynamics, commitment and trust, emergent agency, multi-agent security.
- (§3.3) *Selection pressures* explicitly discusses how training procedures can induce undesirable dispositions in agents.
- (§4.1) Safety implication: alignment of individual agents is not sufficient.

**Limitations:**
- No empirical experiments validate any specific failure mechanism end-to-end.
- Training-side and deployment-side risks are addressed together without strong separation.
- Human-in-MAS failure modes are implicit but not enumerated as a distinct category.

**Implications for our work:**
- The canonical risk taxonomy we position against. Track 1 RQ1 tests transfer to the *conflict* and *collusion* failure modes; the report supplies the framing for why these matter.
- §3.3 (selection pressures) is the most direct precedent for our central claim that multi-agent training is itself a source of downstream risk.
- §4.1 explicit call for multi-agent evaluations grounds our automated multi-agent variants of Eval Undermining and Policy Development.
```

## Rules per field

### Title line

- Bold-implicit (use `###`).
- Title is the paper's actual title; do not paraphrase.
- arXiv ID format: `arXiv:NNNN.NNNNN` (5-digit version, current arXiv format).
- Date: month and year (e.g., `Feb 2025`).
- Venue: official venue including year (e.g., `ICML 2025`, `ICLR 2026`, `NeurIPS 2025 D&B`, `Nature 2026`). If only on arXiv, write `arXiv`.

### One-sentence description

- Lead with the institution(s) or first author lab if helpful for context.
- State what study was done in one sentence.
- Do not editorialize ("this important paper..." → no).

### Research question

- One sentence ending in a question mark.
- Should capture the paper's main inquiry, not a side finding.
- If the paper has multiple questions, pick the central one and note in Methodology that others are addressed.

### Methodology bullets

- 3–6 bullets typical, 8 maximum.
- Each starts with `(§X.Y)` paper-section reference.
- Specifies: data, model, procedure, control conditions, evaluation metric.
- Quantitative details where available: sample size, training duration, model size.
- Distinct from Conclusion: Methodology = *what they did*; Conclusion = *what they found*.

### Conclusion bullets

- 3–6 bullets typical.
- Each starts with `(§X.Y)` paper-section reference.
- States specific findings with numbers where possible: `"20% misalignment rate"`, `"κ = 0.88"`, `"effect size d = 0.4"`.
- Avoid hedging ("the paper suggests...") — state findings directly.
- Distinguishes empirical findings (paper showed X) from authors' claims (authors interpret X as Y).

### Limitations bullets

- 3–5 bullets typical.
- Cover: scope restrictions, generalization gaps, methodological constraints, what was not tested.
- Cite the paper's own Limitations section if it has one (`(§7 limitations)`).
- Note implicit limitations not stated by the authors (e.g., "all examples in English; no cross-language test").

### Implications for our work bullets

- 2–5 bullets typical.
- Each implication should: name the specific RQ or hypothesis it supports, identify what methodology or finding transfers, OR identify the gap our project fills relative to this paper.
- Concrete language: "supports H2a", "transferable methodology for X", "our RQ3 extends to Y".
- Avoid: "provides background", "is relevant to our work" (these are not implications).

## Section reference notation

- `(§3.1)` is preferred over `(Section 3.1)` for compactness.
- Numbered subsections only — do not invent section numbers.
- If a claim spans multiple sections: `(§3.1, §3.2)`.
- For appendices: `(§A.2)` or `(Appendix A.2)`.
- Tables and figures referenced within sections: `(§4.2, Table 3)`.
- If the section number is uncertain: `[verify §X]` where X is the best guess.

## Length per entry

- Foundational papers (in §1 Risk Taxonomy or §2 core phenomenon): 200–400 words.
- Standard papers: 150–250 words.
- Supporting / supplementary papers: 100–150 words.

If an entry exceeds 400 words, it likely contains redundant content. Compress by:
- Removing repeated information across Methodology / Conclusion / Implications.
- Consolidating multiple bullets that say similar things.
- Cutting bullets that don't directly serve the implication.
