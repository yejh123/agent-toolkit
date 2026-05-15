# Summary Table Format

The final section of a related-work document is a gap-to-RQ summary table. This section closes the document by giving the reader a one-glance answer to "what's the contribution?"

## Purpose

The summary table addresses the reviewer's question: "I've read 30 papers of related work. What is this proposal's contribution?"

The table makes the answer skim-able:

- Left column: identified gaps in the literature.
- Right column: the specific RQ that addresses each gap.

This is the single most important section for novelty defense. A well-written summary table can rescue a borderline proposal.

## Format

```markdown
## {N} Summary of Gaps and Positioning

| Gap in existing literature | Addressed by |
|---|---|
| {Specific gap, citing a source} | RQ{n} (specifically H{na}/H{nb}) |
| {Specific gap} | RQ{n}, RQ{m} |
| ... | ... |

The proposal positions {Track 1} as {one-sentence Track 1 contribution} (with {explicit incremental labels}), and {Track 2} as {one-sentence Track 2 contribution}.
```

## Worked example

```markdown
## 10 Summary of Gaps and Positioning

| Gap in existing literature | Addressed by |
|---|---|
| EM studied for harmful content, reward hacking, RL-on-exploitable-rewards — never for cooperative multi-agent training | RQ1 (specifically H1b) |
| MAS bias amplification studied for inherent base-model biases (Li et al., 2026) — never for trained-in patterns | RQ2 (H2b, H2c) |
| AI-AI MAS conformity well-studied — human conformity to trained-AI in MAS not studied empirically | RQ3–RQ5 |
| Cross-provenance MAS deployment emerging (MCP/A2A) — safety implications unstudied | RQ5 |
| Single-agent monitoring well-studied (Kutasov et al., 2025) — awareness propagation through MAS social communication unstudied | RQ6 |
| External monitors studied — internal trusted reviewers as MAS roles and their co-optation by social pressure unstudied | RQ7 |
| Sabotage evaluations (Benton 2024) use human participants — fully automated multi-agent-aware sabotage benchmarks do not exist | E1-M, E2-M (methodology contribution) |

The proposal positions Track 1 as the first systematic test of cooperative-direction transfer (with H1a/H2a as confirmatory extensions of existing work, explicitly flagged), and Track 2 as the first empirical study of trained-AI-induced human oversight degradation in MAS contexts.
```

## Rules per column

### Left column (gaps)

- Each gap statement has two parts: "{What is studied}" — "{What is not studied}".
- Cite at least one paper exemplifying the existing literature: `studied for X (Smith et al., 2024)`.
- Be specific. "MAS safety not fully understood" is not a gap; "MAS bias amplification studied for inherent biases (Li et al., 2026) — not for trained-in patterns" is a gap.
- If a gap is partially covered by multiple papers, list them: `(Smith 2024; Jones 2025)`.

### Right column (RQs)

- Cite by RQ number, optionally with specific hypothesis label.
- For gaps addressed by methodology rather than RQ, cite the methodology element: `E1-M, E2-M`, `discovery-oriented protocol`.
- If multiple RQs address a gap together, list them: `RQ3–RQ5` or `RQ3, RQ5`.

## Closing paragraph

The summary table is followed by a one-sentence positioning statement:

> The proposal positions {Track 1} as {Track 1 contribution}, and {Track 2} as {Track 2 contribution}.

This sentence should:
- Name the contribution honestly (don't hide incremental components).
- Distinguish Track 1 from Track 2 if multi-track.
- Be the same sentence that closes the proposal abstract — ensures consistency.

## What this section is NOT

- **Not a list of all RQs.** It's a list of *gaps*, mapped to RQs. If a gap is addressed by RQ8, RQ8 belongs in the table. If RQ8 is replication of existing findings (no gap), it does not belong.
- **Not a list of all papers cited.** Only the foundational papers exemplifying the existing literature for each gap.
- **Not new claims.** Every gap claim should be supported by entries in earlier sections (§2–§9).

## Common mistakes

- **Vague gaps.** "Multi-agent safety not fully studied" → too broad.
- **Gaps without prior-work citations.** "Cooperative training transfer to humans not studied" → cite which AI-AI conformity papers exist that establish the partial coverage.
- **RQ-to-gap mapping that doesn't match the body.** If the body claims RQ7 is novel but the summary table puts RQ7 against a well-studied gap, reviewer will catch the contradiction.
- **Including incremental RQs that don't address a gap.** If RQ3 is incremental confirmation (as in our example), it doesn't have a row. The corresponding entry in §X.X just notes "supports H4a but is largely incremental."

## Length

Typical: 4–8 rows. The summary table should be skim-able in 30 seconds.

If you have 10+ rows, some gaps are likely subdivisions of larger gaps. Consolidate.
