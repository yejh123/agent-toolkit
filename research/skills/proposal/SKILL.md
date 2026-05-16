---
name: research-proposal
description: "Write or iterate on a research proposal for ML/AI research. Use when the user requests drafting, refining, or restructuring a proposal, including motivation, research questions, hypotheses, novelty assessment, contributions, implications, scope, and roadmap. Supports single-track and multi-track proposals. Triggers on: write research proposal, iterate on proposal, refine RQ, rewrite motivation, novelty assessment, plan publication strategy, 写研究计划, 完善 RQ, 修改 motivation."
---

# Research Proposal Writing

A procedural framework for writing rigorous, reviewer-defensible research proposals in ML and AI. The skill is general: it does not assume a specific project domain, paper count, or publication path.

## When to use this skill

For drafting or iterating on a research proposal in ML / AI, typically a substantial multi-month, multi-paper project. The same framework also applies to shorter research statements and grant LOIs. Distinct from single-paper writing (see `paper-write`).

## Core principles

1. **Literature search before proposing RQs.** Most "novel" RQs are incremental in disguise. Run thorough search per candidate RQ before committing.
2. **Honest novelty assessment per RQ.** Label each hypothesis as **novel core**, **incremental**, or **calibration prediction**. Reviewers downgrade hidden incremental work.
3. **Concrete attack surface in motivation.** Open with a specific problem (deployment scenario, known failure mode, gap in evaluation), not abstract framing.
4. **Each RQ has a clear experimental signature.** Every RQ maps to a specific experimental cell. If the experiment cannot be described in one sentence, the RQ is not concrete enough.
5. **Consistent format for RQ blocks.** Use the unified topic-sentence and per-RQ structure from `references/rq-format.md`.

## Workflow

1. **Establish project framing.** Agree on central problem, target venues, scope, timeline. Decide single-track vs multi-track. See `references/proposal-structure.md`.
2. **Draft document structure.** Choose how to split the proposal into files. Standard content chapters are in `references/proposal-structure.md`.
3. **Write the Overview chapter iteratively.** The Overview holds the proposal's spine. Iterate its subsections in order: Motivation, Project Structure, Research Questions, Contributions, Implications, Scope, Roadmap summary, Document Map.
4. **Write each RQ block.** Use the unified format in `references/rq-format.md`. Apply novelty assessment per hypothesis.
5. **Respond to critique.** Common patterns and right responses are catalogued in `references/iteration-patterns.md`. Apply formatting rules from `references/writing-style.md` on every revision.

**Entry point for ongoing iteration.** The workflow above assumes a fresh proposal. For ongoing iteration on an existing draft, enter at Step 4 (per-RQ refinement) or Step 5 (critique response); revisit Steps 1 and 2 only if structural decisions are being reconsidered.

## Reference files

- `references/proposal-structure.md`: document-level chapter layout, three publication strategies (multi-conference / single-journal / hybrid), venue calendar, per-track requirements and journal-track risks.
- `references/rq-format.md`: exact RQ-block format, hypothesis rules, and novelty assessment (labels, triggering questions, positioning, process, surface-novelty pitfalls, the honest test).
- `references/iteration-patterns.md`: common critique types and right responses, organized by the level the critique addresses (RQ, hypothesis, scope, methodology, plan).
- `references/writing-style.md`: formatting conventions, AI clichés to avoid, pre-finalization checks.

## Anti-patterns to avoid

- Hidden incremental work passed off as novel.
- Too many RQs for the planned scope: more than 4 in a single-paper proposal, or more than 8 across a multi-track proposal.
- Forward-looking assumptions embedded in RQ wording. Predictions belong in hypotheses, not in the question.
- Vague abstract motivation lacking a concrete attack surface.
- Implications that restate contributions in present tense rather than offering concrete architectural recommendations.
