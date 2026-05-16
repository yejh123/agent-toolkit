# Proposal Structure

This file documents the standard top-level structure of an ML / AI research proposal and the publication-strategy decisions made at the start of the project.

## Table of Contents

1. Content chapters of a proposal
2. Publication strategy: choosing tracks
3. Venue calendar
4. Per-track requirements and multi-track risks

## 1 Content chapters of a proposal

A proposal has two structural layers:

- **Document-level chapters** (one or more files): the top-level table of contents of the full proposal.
- **Overview subsections** (within the Overview chapter): the internal subsections of the spine chapter, where the proposal's argument lives.

### 1.1 Document-level chapters

A typical full proposal has these top-level chapters:

- **Overview.** Single self-contained chapter holding the proposal's spine: motivation, project structure (track definitions if multi-track), research questions, contributions, implications, scope, roadmap summary, document map.
- **Related Work.** Topic-organized literature review. See the `ml-related-work-document` skill.
- **Methods.** Training setup, evaluation setup, additional methodology as needed. May split into multiple method chapters.
- **Experimental Plan.** Per-track experimental matrix and submission plan. One chapter per track if multi-track.
- **Roadmap.** Month-by-month timeline with decision points and go / no-go thresholds.
- **Appendices.** Supporting methodology.
- **References.** Consolidated bibliography.

File naming (e.g., `00_overview.md`, `01_related_work.md`) is an organizational preference, not part of this framework.

### 1.2 Overview subsections

Write the Overview's subsections in this iteration order:

1. **Motivation.** Concrete attack surface, then the gap in current understanding or practice, then the proposal's framing question(s).
2. **Project Structure.** Track definitions and how the tracks relate (if multi-track); otherwise the scope of the single paper.
3. **Research Questions.** See `rq-format.md`.
4. **Contributions.** Explicit list. Per-track if multi-track.
5. **Implications.** Bullet points. Per-track if multi-track. Distinct from contributions: implications are downstream design guidance; contributions are what was produced.
6. **Scope.** In-scope vs out-of-scope lists.
7. **Roadmap summary.** Short summary table with key milestones, pointing to the detailed Roadmap chapter.
8. **Document Map.** Index of all files in the proposal.

## 2 Publication strategy: choosing tracks

Three strategies, presented neutrally. The right choice depends on contribution shape and timeline; no strategy is the default.

### 2.1 Multi-conference (parallel)

Two or more contributions submitted to separate conferences in parallel or in sequence.

- **Use when:** contributions are weakly coupled and can stand alone; the time horizon is tight (about 12 months); two publications are preferred over one high-impact paper.
- **Do not use when:** contributions only make sense as one extended story.
- **Properties:** faster, lower variance, multiple publications guaranteed; lower impact per paper.

### 2.2 Single-journal (high-impact)

All contributions consolidated into one journal submission.

- **Use when:** contributions only cohere as one integrated story; an interdisciplinary or societal-impact audience justifies a journal venue; the timeline can absorb 18+ months of review.
- **Do not use when:** the consolidated scope is too large to keep coherent; the journal extension would slow the conference-level contribution; rejection risk is unacceptable.
- **Properties:** highest single-paper impact; no fallback; longest timeline; highest rejection variance.

### 2.3 Conference-then-journal (hybrid)

Self-contained conference paper first, then an expanded journal version that builds on it.

- **Use when** all of the following hold:
  - The conference contribution is publishable on its own merits.
  - There is a natural extension that adds a new dimension (human study, mechanism analysis, cross-environment generality, etc.).
  - The journal scope does not weaken the conference paper.
  - The timeline can accommodate roughly 18–24 months with a 4–6 month gap between conference and journal submissions.
- **Do not use when:** the core contribution requires the journal-scope extension to be reviewable; time is constrained to one publication; the extension is speculative enough to delay the conference submission.
- **Properties:** combines a guaranteed conference paper with a stretch journal goal; requires designing both tracks for independent submission.

## 3 Venue calendar

The following deadlines are **approximate** and shift year to year. Verify against the current Call for Papers before planning submissions.

| Venue | Approximate deadline | Approximate decision |
|---|---|---|
| ICLR | Early October | Early February |
| ICML | Late January | Mid-May |
| NeurIPS | Mid-May | September |
| ACL | February | May |
| EMNLP | June | September |
| NAACL | October | January |
| Nature, Science (and family journals) | Rolling | 4–8 months typical |

Plan the first submission to the earliest reachable conference, and add buffer for reject-and-resubmit cycles.

## 4 Per-track requirements and multi-track risks

When a proposal involves multiple tracks (whether two conferences, a conference-then-journal hybrid, or a journal-only strategy with multiple contributions), the following apply.

### 4.1 Section separation

In the Overview, the **Contributions** and **Implications** sections should separate tracks explicitly. Each track has its own contributions list and its own implications list. This signals to reviewers that the tracks are distinguishable and individually evaluable.

### 4.2 Independent fallback

Each track should be designed so it can be submitted independently to a backup venue if its primary venue rejects. A journal-track manuscript should be reformattable into an 8–9 page conference paper. A conference-track paper should have an obvious next-conference target.

### 4.3 Hedge structure

For any strategy that includes a journal track:

- If the journal accepts, the maximum-impact outcome lands.
- If the journal rejects on the merits, the conference fallback fires at the next backup deadline.
- Either way, at least one major publication per track.

The journal is the stretch; the conference is the safety net.

### 4.4 Generalizable journal-track risks

When any track targets a journal, plan for these risks:

- **Desk reject (1–3 weeks).** Submit to the backup conference immediately. Little reformat is needed if the track was designed for independent fallback.
- **Slow review (8+ months).** May force missing the next conference deadline. Build buffer into the roadmap.
- **Primary-track rejection.** The arXiv preprint stands. Submit a revised version to the next conference. Other tracks' timelines should not depend on the rejected track's acceptance.

Each major risk in the roadmap should have a probability estimate, an impact severity, and a pre-committed mitigation.
