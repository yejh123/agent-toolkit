# Iteration Patterns

Proposals typically go through 5–10 substantive iterations. This file catalogs common feedback patterns and the appropriate response.

## "RQ is incremental / been done before"

The user has identified that a candidate RQ is well-trodden in the literature.

**Wrong response:** Defend the RQ or add slight rewording.

**Right response:**
1. Run additional literature search with different keywords. The first failure was usually under-searching.
2. Identify which hypothesis under the RQ is incremental and which is not. They are rarely uniformly incremental.
3. Either reframe the RQ to extract the novel angle, or explicitly demote to "supporting" RQ with honest labeling.
4. If genuinely all-incremental, drop the RQ (do not pretend novelty).

Specific reframings that have worked:

- "Test phenomenon X" → "Test whether X-type-A and X-type-B propagate differently" (turns confirmatory into comparison).
- "Test phenomenon X in setting Y" → "Compare phenomenon X under setting Y vs setting Y'" (turns extension into experimental design).
- "Test mechanism M produces effect E" → "Discover via inductive analysis what mechanisms produce E" (turns confirmatory into discovery, with null result as informative).

## "Topic sentence too abstract"

The topic sentence before an RQ subsection uses high-level abstractions like "from existence to mechanism" instead of concrete clauses.

**Right response:** Rewrite in the standard format from `rq-format.md`:

> Track X [verb] [concrete clause about RQ_a] (RQ_a), [concrete clause] (RQ_b), and [concrete clause] (RQ_c).

Each clause refers to the specific phenomenon under that RQ, not to abstract levels.

## "Hypothesis too speculative / no evidence"

A hypothesis predicts something with no supporting literature.

**Wrong response:** Soften the prediction.

**Right response:** Add **"No precedent."** explicitly. This is the honest signal that the hypothesis is novel and must be falsifiable. Then check that the experiment design can actually test it.

Example:

> H1b (cooperative direction). Cooperative multi-agent training induces measurably elevated *collusion* behaviors. **No precedent.**

This is stronger than soft-pedaling because it converts the "speculation" critique into a virtue: the hypothesis is the genuine novel claim.

## "RQ4 and RQ5 are the same question"

Two adjacent RQs have similar wording or appear to test the same factor.

**Right response:** Identify the orthogonal variables they should isolate.

Example pattern (from project iteration):
- RQ4 holds deployment context fixed (single-AI), varies training condition.
- RQ5 holds training condition fixed, varies deployment context.
- RQ6 tests their interaction.

The differentiation should be: "which factor does this RQ vary while holding others fixed."

## "Implications too vague"

Implications section reads as restating the contributions in present tense.

**Right response:** Convert each implication into a concrete architectural recommendation or design principle.

Wrong: "Multi-agent training paradigms warrant pre-deployment safety auditing."
Right: "Cooperative multi-agent training, currently treated as low-risk relative to adversarial training, may transfer to safety-relevant downstream behaviors and warrants pre-deployment safety auditing alongside adversarial training methods."

Wrong: "Internal reviewers should be designed carefully."
Right: "When intervention capability during execution is required, internal trusted reviewers are unavoidable but should be designed to resist the social-pressure mechanism we document: isolate reviewer deliberation from peer communication channels; interleave reviewer turns rather than embed them in consensus rounds; sample multiple independent reviewers and aggregate by majority."

## "Why this training environment (e.g., Avalon)?"

A reviewer skeptical of the chosen testbed asks for justification.

**Right response:** Provide three specific properties of the testbed, each with a citation supporting why the property matters and how the testbed exhibits it. Do not mention alternative testbeds; defend the choice on positive grounds.

Template (from the proposal):
1. *Hidden information matches real MAS deployments* (information asymmetry is documented as the structural feature distinguishing MAS from single-agent settings — cite HIDDENBENCH, iAgents).
2. *Same game admits adversarial AND cooperative training under identical infrastructure* (the methodological feature that enables clean causal comparison).
3. *Mature, reproducible infrastructure exists* (cite the benchmark and follow-up work).

## "Hypothesis count exceeded the RQ"

Too many sub-hypotheses (e.g., H5a, H5b, H5c, H5d, H5e) makes the RQ look bloated.

**Right response:** Cap at 3 hypotheses per RQ. If you genuinely need 4+, consider splitting the RQ.

## "Effect size prediction missing"

Hypothesis predicts direction but not magnitude.

**Right response:** Add a separate hypothesis (often labeled "calibration") that predicts magnitude with reasoning:

> H1c (effect size). Effect sizes are smaller than harmful-content fine-tuning (Betley et al., 2025 reports ~20%) but statistically significant, because game-context legitimization may provide partial inoculation analogous to the educational-framing control in Betley et al. (2025).

This makes the proposal pre-registered and falsifiable.

## "Path C feels overcommitted"

User worries the two-track strategy is too ambitious.

**Right response:** Confirm that Track 2 is designed to fall back to a conference if Nature rejects. The minimum success case (Path A) gives two ML conference papers. Nature is the stretch, not the requirement.

## "Out of scope feels too restrictive"

User wants to include something that was moved out of scope (e.g., mechanism analysis).

**Right response:** Check whether it can be done in parallel without slipping the primary timeline. If yes, move back in scope but mark as "stretch" with explicit decision point in the roadmap. If no, keep out of scope and add to "Future Work" with a sentence explaining when it would be tackled.

## "Roadmap is too optimistic"

The timeline doesn't account for known delays (IRB approval, recruitment, training failures).

**Right response:** Add explicit decision points with go/no-go thresholds and pre-identified fallback paths. Each major risk should have:
- Probability estimate
- Impact severity
- Pre-committed mitigation

See `08_roadmap.md` template in the proposal directory.
