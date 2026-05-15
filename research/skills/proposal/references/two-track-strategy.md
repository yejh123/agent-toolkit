# Two-Track Publication Strategy (Path C)

When a research project has both a technical contribution (suitable for ML conference) and a broader-impact extension (suitable for journal or interdisciplinary venue), the recommended publication structure is **Conference-Then-Journal**, also called Path C.

## The precedent

Betley et al. (2025), *Emergent Misalignment*:

- February 2025: arXiv preprint (arXiv:2502.17424).
- 2025: ICML 2025 acceptance.
- January 2026: Nature article (expanded with multi-model replication, scaling, persona-vector mechanism analysis).

The same paper, progressively expanded, hit three venues with increasing impact. The conference version is publishable independently; the journal version adds depth and additional results.

## When to use Path C

Use Path C when **all** of the following hold:

1. The core technical contribution is publishable in a top ML venue (ICLR/NeurIPS/ICML) on its own merits.
2. There is a natural extension that adds an additional dimension (e.g., human study, mechanism analysis, cross-environment generality) and requires substantially more time.
3. The journal extension would not significantly weaken the conference paper (so submitting both is not a dilution).
4. PhD timeline can accommodate ~18–24 months of work with a 4–6 month gap between conference and journal submission.

Do **not** use Path C when:

- The core contribution requires the journal-scope extension to be reviewable (then aim for journal only).
- Time is constrained to one publication (then pick the venue that matches the scope).
- The journal extension is speculative or risky enough to delay the conference submission.

## Track structure

| Component | Track 1 (Conference) | Track 2 (Journal) |
|---|---|---|
| **Self-contained?** | Yes, complete contribution | Builds on Track 1 + new dimension |
| **Target venue** | ICLR / NeurIPS / ICML main | Nature / Science (or backup conference) |
| **Submission timing** | Month ~7 from project start | Month ~22 from project start |
| **Backup if rejected** | Resubmit to next ML conference | Resubmit to next ML conference |

## Path C alternatives

- **Path A (two conference papers):** Both contributions submitted to separate conferences. Faster, lower variance, two publications guaranteed. Less impact per paper.
- **Path B (single journal paper):** All contributions in one journal submission. Highest single-paper impact, but no fallback, longer timeline, higher rejection variance.
- **Path C (hybrid):** Path A as the safety net + Path B as the stretch goal.

Path C is the recommended default because Path A is the automatic fallback if Path B fails.

## Hedge structure

Critical detail: even in Path C, **Track 2 must be designed so that it can be submitted independently to a conference** if the journal track rejects. The journal manuscript should be reformattable into a 8-9 page ML conference paper.

The hedge:
- If journal accepts → maximum-impact outcome.
- If journal rejects → conference fallback at backup deadline.
- Either way → at least one major publication for Track 2.

## Timeline anchors

For a project starting in mid-year (e.g., May), the venue calendar for the following two years:

| Venue | Deadline (approx.) | Decision |
|---|---|---|
| ICLR | early October | early February |
| ICML | late January | mid-May |
| NeurIPS | mid-May | September |
| Nature/Science | rolling | 4–6 months |

Plan Track 1 submission to the earliest reachable conference (typically ICLR ~5 months from project start, or ICML ~9 months). Plan Track 2 to follow ~12–15 months after Track 1.

## Risks specific to Path C

1. **Journal rejection desk-reject** (1–3 weeks): submit to backup ML conference immediately, no major reformat needed if Track 2 was designed independently.
2. **Journal slow review** (8+ months): may force missing the next ML conference deadline. Plan for this.
3. **Track 1 rejection** (rare given conference acceptance rates ~30%): if Track 1 is rejected from primary conference, the arXiv preprint stands; submit revised version to next conference. Track 2 timeline is unaffected as long as it does not depend on Track 1 acceptance.

## Writing implications

In the proposal:

- Section 2 (Project Structure) explicitly describes Track 1 and Track 2 with their target venues and timing.
- Section 7 (Roadmap) summarizes the schedule; detailed `08_roadmap.md` shows month-by-month plan with decision points.
- Each track has its own experimental plan file (`06_track1_plan.md`, `07_track2_plan.md`).
- The contributions section distinguishes Track 1 contributions from Track 2 contributions.
- The implications section provides per-track implications.
