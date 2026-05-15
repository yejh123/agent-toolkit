---
name: research-proposal
description: Write or iterate on a research proposal for AI research. Use when the user requests writing or refining a research proposal, especially one with: multiple research questions organized into tracks, hypothesis-driven structure, two-track publication strategy (e.g., conference-then-journal), explicit novelty assessment per RQ, or per-track implications. Use for tasks like "help me write a research proposal", "iterate on my proposal", "refine the RQ structure", "rewrite the motivation section".
---

# Research Proposal Writing

This skill encodes a proven structure for writing rigorous, reviewer-defensible research proposals in ML, LLM, AI safety, and multi-agent systems. It is the result of iterative refinement against detailed expert feedback.

## When to use this skill

The user is writing a research proposal for an ML research project — typically a multi-month PhD-level project — and needs help with overall structure, research questions, hypotheses, contributions, and implications. Different from writing a single paper: proposals must justify scope, timeline, and a coherent multi-paper plan if applicable.

## Core principles

1. **Literature search before proposing RQs.** Most "novel" RQs are actually incremental in disguise. Run thorough literature search for each candidate RQ before committing to it. If every hypothesis the RQ implies is already supported by prior work, the RQ is consolidation, not innovation.

2. **Honest novelty assessment per RQ.** After each RQ block, explicitly label which hypotheses are incremental and which are novel. Reviewers can identify incremental work; flagging it preempts skepticism. The strongest proposals concentrate novelty into one or two specific hypotheses and label the rest as supporting infrastructure.

3. **Concrete attack surface in motivation.** Open with a specific problem (a deployment scenario, a known failure mode, a gap in evaluation), not an abstract "AI is changing the world" framing. Reviewers should know within two paragraphs what the unstudied risk is.

4. **Each RQ has a clear experimental signature.** Every RQ must map to a specific experimental cell (factor combinations, comparison groups, measurement). If you cannot describe the experiment in one sentence, the RQ is not concrete enough.

5. **Topic sentences before RQ subsections.** Use the unified format documented in `references/rq-format.md`.

## Workflow

### Step 1: Establish the project framing

Before writing any sections, agree with the user on:

- The **central research problem** (one sentence, in domain-grounded terms)
- The **target venues** (single venue vs. two-track strategy like Path C: conference-then-Nature)
- The **scope** (what is in vs. out — e.g., whether mechanism analysis, additional environments, defenses are included)
- The **timeline horizon** (e.g., 12 months vs. 24 months)

Two-track strategy is recommended when the project has both technical and broader-impact contributions. The proven template is Betley et al. (2025) emergent misalignment: arXiv preprint → conference → Nature expansion. See `references/two-track-strategy.md`.

### Step 2: Draft document structure

A typical proposal has these files:

```
00_overview.md         — motivation, project structure, RQs+hypotheses, contributions, scope, roadmap
01_related_work.md     — see related-work skill
02_method_training.md  — training setup, models, hyperparameters
03_method_evaluation.md — evaluation environments and metrics
04_method_*.md         — additional methodology files as needed (e.g., human study, oversight)
05_*_plan.md           — per-track experimental matrix and submission plan
0X_roadmap.md          — month-by-month timeline with decision points
0X_appendix_*.md       — supporting methodology
references.md          — consolidated bibliography
```

### Step 3: Write the overview file iteratively

The overview is the most-edited file. Iterate in this order:

1. **Motivation** — concrete attack surface, then the gap, then the proposal's two-question framing
2. **Project structure** — track definitions if multi-track
3. **Research questions** — see RQ format below
4. **Contributions** — explicit list per track
5. **Implications** — bullet points per track (separate from contributions)
6. **Scope** — in/out lists
7. **Roadmap** — summary table with key milestones, points to detailed roadmap file
8. **Document map** — index of all files

### Step 4: Write each RQ block

Every RQ follows a fixed structure. See `references/rq-format.md` for the template and examples.

The order of subsections within §3 (Research Questions and Hypotheses):
- Topic sentence (one per RQ subsection, format: "Track X [verb] [clause] (RQ_), [clause] (RQ_), and [clause] (RQ_).")
- Per-RQ block: Question → Term definitions (if needed) → Hypotheses → Novelty assessment

### Step 5: Iterate based on critique

When the user provides feedback, common iteration patterns:

- *"RQ is incremental"* → Search literature again, find new angle, or explicitly flag as incremental
- *"Hypothesis too speculative"* → Add citation supporting the prediction, or mark "no precedent" honestly
- *"Topic sentence too abstract"* → Replace abstractions with concrete RQ-tied phrases
- *"Implications too vague"* → Convert to concrete architectural recommendations
- *"Format inconsistent"* → Apply rules from `references/format-conventions.md`

Do not expect first-pass perfection. The proposal typically goes through 5-10 substantive iterations.

## Reference files

- `references/format-conventions.md` — formatting rules: English/Chinese conventions, no em-dashes, header numbering, citation style, common AI clichés to avoid
- `references/rq-format.md` — the exact format for RQ blocks with worked examples
- `references/novelty-assessment.md` — how to evaluate whether an RQ is novel vs. incremental, including triggering questions
- `references/two-track-strategy.md` — when and how to organize a two-track conference-then-journal publication plan
- `references/iteration-patterns.md` — common types of critique and how to respond

## Anti-patterns to avoid

- **Hidden incremental work.** If the expected implications follow directly from prior work and you don't say so, you should reconsider the proposal.
- **Too many RQs.** 1 Main RQ and 3 Supporting RQs is a good number for a paper. More than that is hard to execute and review.
- **Forward-looking assumptions in RQ wording.** RQs should ask questions, not embed predictions. "We expect X because Y" belongs in the hypothesis, not the RQ.
- **Vague motivation.** "MAS are an important emerging area" is not a motivation; "Trained AI agents within an MAS may systematically bias the human operators embedded in that system, and this attack surface has received no empirical attention" is a motivation.
