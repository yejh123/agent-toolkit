# Novelty Assessment

The most common failure mode in research proposals is proposing RQs that look novel on the surface but are actually validated extensions of established literature. This guide provides triggering questions and a labeling scheme.

## Why this matters

When every hypothesis in a proposal has prior-work support, the proposal becomes a *consolidation* document — important for the field but not a contribution. Reviewers identify this pattern and downgrade the proposal accordingly. Two failure modes are equally bad:

1. **Hidden incremental work.** Claiming novelty for hypotheses that prior work already validates. Reviewers see this and lose trust in the entire proposal.
2. **Confused novelty.** Asserting that "the combination" or "the integration" is novel without identifying which specific claim is unprecedented. Reviewers cannot evaluate vague novelty claims.

The solution is to label each hypothesis explicitly and concentrate the contribution claim on the genuinely novel components.

## Triggering questions per hypothesis

For each hypothesis, ask in order:

1. **Has any paper made this specific prediction?** Search the literature with multiple keyword combinations. Cite at least three search results if the answer is "no" — this prevents fooling yourself.

2. **Has any paper made an analogous prediction in a closely related setting?** For example, EM in SFT → EM in RL is a close analog; demographic-bias amplification → trained-pattern amplification is a close analog. Close analogs make the hypothesis incremental but not trivial.

3. **What experimental result would confirm vs. refute the hypothesis?** If the result space is obvious from prior work (e.g., "this will work because Betley et al. already showed analogous transfer"), the hypothesis is confirmatory.

4. **What would a skeptical reviewer say?** Reviewer A: "This extends Wang et al. 2025 to a new setting — incremental." Reviewer B: "This is the first study of cooperative-direction transfer — novel." If both reactions are plausible, the hypothesis is mixed.

5. **What is the smallest unit of novelty?** If a hypothesis bundles multiple sub-claims, the novel parts are the sub-claims with no precedent. Restate the hypothesis to isolate them.

## Labels

Use exactly three labels for consistency:

- **Novel core.** No precedent for the specific prediction; the hypothesis space is genuinely open. Mark these prominently because they are where the contribution concentrates.
- **Incremental.** A close analog exists in prior work, and the hypothesis is confirmatory or transfers a known phenomenon to a new setting. *Do not hide these.* Label them explicitly. Reviewers respect honest labels.
- **Calibration prediction.** Predicts magnitude or specific effect size for a known phenomenon. These are not novelty claims but are needed for pre-registration and falsifiability.

## How to position incremental hypotheses

Incremental work is publishable and often essential, but it should be framed as supporting infrastructure rather than as the contribution.

Examples of good framings:

- "H1a is **incremental**. It extends the established adversarial-training-induces-misalignment pattern to a new training source (Avalon RL). The contribution is a replication in a different setting, not a new phenomenon class."
- "RQ3 serves Track 2 primarily as a control / baseline. The Track 2 contribution concentrates on RQ4–RQ7."
- "RQ8 is explicitly replication work. It supports the generality of RQ1 findings but does not by itself produce new insight. Marked optional supplementary."

Examples of bad framings (do not use):

- "H1a is a **first-of-its-kind investigation of Avalon-induced deception transfer.**" (Hidden incremental.)
- "RQ3 is **novel** because it tests humans rather than models." (Same phenomenon class, different sample.)

## What "novel" actually requires

For a hypothesis to qualify as **novel core**, at least one of the following must hold:

- The phenomenon class is new (e.g., cooperative training as misalignment source — no prior work claims this).
- The mechanism is new even though the phenomenon class is known (e.g., context-conditional latency as a distinct propagation mode separating trained from inherent biases).
- The methodology is fundamentally different (e.g., discovery-oriented open-coded clustering replacing hypothesis testing).
- The forward-looking setting is new (e.g., cross-provenance MAS with MCP/A2A protocols was not a deployment paradigm 18 months ago).

Each of these can be challenged: the reviewer will check whether anyone made the claim in 2024 or earlier. Be ready with the literature search trail.

## Process: when to run this check

Run novelty assessment **before finalizing an RQ**, not after. The cost of finding out RQ3 is incremental after writing the methodology section is high.

Sequence:
1. Draft candidate RQ.
2. Run literature search (3–5 distinct queries).
3. For each hypothesis under the RQ, apply the triggering questions.
4. Apply labels.
5. If the entire RQ is marked incremental, either reframe to extract a novel angle, or explicitly demote to "supporting RQ" (e.g., RQ3 above).

## Common surface-novelty pitfalls

- **"In MAS contexts"** — Adding "in MAS" to a known single-agent finding is not novel unless the MAS-specific dynamic itself is the contribution.
- **"With humans"** — Adding "with humans" to a known AI-AI finding requires a specific mechanism that humans introduce, not just sample replacement.
- **"On larger models"** — Scaling to larger models is contribution only if the prediction changes at scale.
- **"On open-weights models"** — Replication on open weights is engineering, not novelty (with rare exceptions for capability discontinuities).

## The honest test

Imagine writing a one-sentence email to the leading expert in the area: "We are testing whether [hypothesis]. Has this been done?"

If the expert would respond "Yes, see [paper]", the hypothesis is **incremental**.
If the expert would respond "Not exactly, but close to [paper]", the hypothesis is **incremental** with a close analog.
If the expert would respond "Interesting, no one has tested that", the hypothesis is **novel core**.

Use this thought experiment liberally.
