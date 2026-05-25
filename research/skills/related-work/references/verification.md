# Verification Policy

The central rule: **read primary sources before writing entries, and verify every claim against them**. Marking uncertainty is a last resort, not a shortcut. No hallucinations.

## What counts as a primary source

In order of preference:

1. **arXiv PDF or HTML** — `arxiv.org/pdf/{ID}` or `arxiv.org/html/{ID}`. Use the latest version (typically v2 or v3 for established papers).
2. **OpenReview submission** (for ICLR/NeurIPS/ICML papers) — `openreview.net/forum?id=...`.
3. **Conference proceedings** — official PDF link.
4. **Author or lab website hosting the PDF**.
5. **Researchgate, semanticscholar.org** — acceptable as fallback but verify against canonical source.

## What does NOT count

- Search result snippets, even from arxiv.org. They are usually accurate but lack section-level detail.
- Blog posts about the paper. They paraphrase and often distort.
- Twitter / X threads summarizing the paper.
- ChatGPT or other LLM summaries.
- "AI explainers" sites (emergentmind.com, etc.). They are LLM-generated and unreliable.

The danger of search snippets: they typically capture abstract content but miss section structure, specific numerical results, and methodology details. Writing from snippets produces entries that look authoritative but cannot be verified at section level.

## Fetch strategy

For each paper:

1. Try `https://arxiv.org/pdf/{ID}` first. If it returns content, proceed.
2. If rate-limited or blocked, try `https://arxiv.org/html/{ID}`.
3. If both fail, try `https://arxiv.org/abs/{ID}` for abstract + structure.
4. If all arXiv routes fail, attempt direct web_search with the title + arXiv ID to find an alternate hosting.
5. If nothing is accessible, mark the entire entry `[verify — original not accessible]` and continue.

After fetching:

1. Skim Abstract → identify the research question.
2. Read Introduction (typically §1) → identify motivation and contributions.
3. Skim Methodology section (typically §3) → identify what they did.
4. Skim Results / Conclusion sections → identify what they found.
5. Check Discussion or Limitations sections (if present) → identify acknowledged constraints.
6. Note section numbers as you read.

This typically takes 5–10 minutes per paper for a competent skim.

## `[verify]` notation — a last resort

A marker is not a shortcut for skipping verification. Reach for one only after a genuine attempt to confirm the claim has failed: you tried the fetch routes above, searched the source for the specific number or section, and still cannot confirm it. Then mark rather than guess:

- `[verify §X]` — the claim is correct but the section number is uncertain
- `[verify]` — the bullet could not be confirmed against the source
- `[verify — original not accessible]` — the paper could not be fetched by any route
- `[verify quantitative result]` — a number that could not be confirmed against the source

The user resolves markers manually, so an honest marker beats a fabricated section number or invented result. But a document full of markers signals the verification effort was not made — markers should be the rare residual, not the norm.

## When to be especially careful

- **arXiv IDs.** Models often invent plausible-looking IDs. Always cross-check by attempting a fetch.
- **Author lists.** Authors often have similar names; do not assume. Cite by first author + et al. and verify against the paper.
- **Quantitative results.** "20% accuracy drop" is a specific verifiable claim. Confirm the exact percentage from the source, not from memory.
- **Section structure.** Different papers number sections differently (some use 1.1.1, some use 1.A, some use Roman). Use the paper's actual structure.
- **Venue and year.** Acceptance does not equal publication year (e.g., a paper accepted at ICLR 2026 in October 2025 should be cited as `ICLR 2026`, not `2025`).

## What to do when you find conflicting information

If two sources give different details for the same paper (e.g., arXiv v1 vs v2):

- Prefer the latest arXiv version unless the user is citing a specific earlier version.
- Note the discrepancy in the entry: `(v1 reports 12% error rate, v2 reports 14% after extended evaluation)`.
- Default to the conference camera-ready version if available.

## Verification checklist before finalizing

Before declaring a section complete, run through:

- [ ] All papers in the section have been fetched, not just searched.
- [ ] All `[verify]` markers are resolved or explicitly noted to the user.
- [ ] All arXiv IDs have been spot-checked (attempt to fetch them; do not just trust memory).
- [ ] Quantitative claims have been verified against the source.
- [ ] Section references are not invented (they correspond to actual sections in the paper).
- [ ] Limitations are real (not hand-wavy generic ones).
- [ ] Implications are concrete (named RQs / hypotheses, not "provides background").

## Why this matters

Reviewers will spot-check related-work claims. A single fabricated section reference or invented arXiv ID undermines the credibility of the entire document. Marking `[verify]` is preferred over guessing because the user can resolve markers, but cannot resolve unmarked fabrications.

Investing 5–10 minutes per paper in primary-source verification is cheap relative to the cost of a reviewer catching one fabrication.
