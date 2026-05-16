# Iteration Patterns

Proposals typically go through 5–10 substantive iterations. This file catalogs common feedback patterns and the right response, organized by the level the critique addresses.

Each pattern has two layers:

- **Procedure layer.** *Wrong response* (the tempting-but-bad way to handle the critique) and *Right response* (what to do instead). Stated as imperative procedural advice.
- **Example layer.** Where useful, a sentence-level wrong-form / right-form pair illustrates the procedure. Both sides use placeholder subjects (`[training paradigm]`, `[adjacent setting]`, etc.) so the form is concrete (a real diff) but the subject stays abstract.

## Table of Contents

1. RQ-level critiques
2. Hypothesis-level critiques
3. Scope and implication critiques
4. Methodology critiques
5. Plan-level critiques

## 1 RQ-level critiques

### 1.1 "RQ is incremental / been done before"

A reviewer identifies that a candidate RQ is well-trodden in the literature.

- **Wrong response:** defend the RQ or add slight rewording.
- **Right response:**
  1. Run additional literature search with different keywords. The first failure was usually under-searching.
  2. Identify which hypothesis under the RQ is incremental and which is not. They are rarely uniformly incremental.
  3. Either reframe the RQ to extract the novel angle, or explicitly demote to a "supporting" RQ with honest labeling.
  4. If genuinely all-incremental, drop the RQ. Do not pretend novelty.

Reframings that work:

- "Test phenomenon X" → "Test whether [phenomenon X type-a] and [phenomenon X type-b] propagate differently" (turns confirmatory into comparison).
- "Test phenomenon X in setting Y" → "Compare phenomenon X under setting Y vs setting Y'" (turns extension into experimental design).
- "Test mechanism M produces effect E" → "Discover via inductive analysis which mechanisms produce E" (turns confirmatory into discovery; the null result becomes informative).

### 1.2 "RQ_a and RQ_b are the same question"

Two adjacent RQs have similar wording or appear to test the same factor.

- **Wrong response:** reword one of them to look different.
- **Right response:** identify the orthogonal variables they should isolate. State which variable each RQ varies while holding others fixed.

Pattern: "RQ_a holds [factor 1] fixed and varies [factor 2]. RQ_b holds [factor 2] fixed and varies [factor 1]. RQ_c tests their interaction."

### 1.3 "Topic sentence too abstract"

The topic sentence opens an RQ subsection with high-level abstractions such as "from existence to mechanism to deployment context".

- **Wrong response:** add more abstractions.
- **Right response:** rewrite in the standard format from `rq-format.md`.

  > Track X [verb] [concrete clause about RQ_a] (RQ_a), [concrete clause about RQ_b] (RQ_b), and [concrete clause about RQ_c] (RQ_c).

  Each clause names the specific phenomenon under that RQ, not an abstract level.

## 2 Hypothesis-level critiques

### 2.1 "Hypothesis too speculative / no evidence"

A hypothesis predicts something with no supporting literature.

- **Wrong response:** soften the prediction.
- **Right response:** add **"No precedent."** explicitly. This is the honest signal that the hypothesis is novel and must be falsifiable. Then check that the experiment design can actually test it.

**Wrong-form sentence:** `[Training condition] may possibly induce some elevated [behavior].`
**Right-form sentence:** `[Training condition] induces measurably elevated [behavior]. **No precedent.**`

The first form turns a falsifiable claim into unfalsifiable mush. The second turns the "speculation" critique into a virtue: the hypothesis is the genuine novel claim, and the experiment will resolve it.

### 2.2 "Hypothesis count exceeded the RQ"

Too many sub-hypotheses (e.g., H_na through H_ne) makes the RQ look bloated.

- **Wrong response:** keep all and group them into "hypothesis families".
- **Right response:** cap at 3 hypotheses per RQ. If you genuinely need 4+, the RQ is doing two jobs. Split it.

### 2.3 "Effect-size prediction missing"

A hypothesis predicts direction but not magnitude. Reviewers cannot evaluate whether the predicted effect is meaningful.

- **Wrong response:** leave magnitude unspecified.
- **Right response:** add a separate hypothesis labeled "(calibration / effect size)" that predicts magnitude with reasoning. Cite the prior-work effect size you are comparing against.

**Wrong-form sentence:** `[Training type X] increases [behavior Y].`
**Right-form sentence:** `Effect sizes are smaller than [comparison condition] ([cited prior-work effect size]) but statistically significant, because [partial-inoculation reason citing the relevant control condition].`

This makes the proposal pre-registered and falsifiable.

## 3 Scope and implication critiques

### 3.1 "Implications too vague"

The implications section reads as restating the contributions in present tense.

- **Wrong response:** rephrase the contributions with words like "important" and "warrants attention".
- **Right response:** convert each implication into a concrete architectural recommendation that names mechanism, comparison class, and the design constraint it implies.

**Wrong-form sentence:** `[Training paradigm] warrant pre-deployment safety auditing.` (vague: no mechanism, no comparison)
**Right-form sentence:** `[Training paradigm], currently treated as [low-risk class] relative to [comparison class], may transfer to safety-relevant downstream behaviors and warrants pre-deployment safety auditing alongside [comparison class] methods.` (specifies relative risk, mechanism path, and design constraint)

A second example for a system-design implication:

**Wrong-form sentence:** `[Reviewer system] should be designed carefully.`
**Right-form sentence:** `When intervention capability during execution is required, [reviewer system] is unavoidable but should be designed to resist [the specific mechanism documented]: [specific design constraint 1]; [specific design constraint 2]; [specific design constraint 3].`

### 3.2 "Out-of-scope feels too restrictive"

The user wants to include something currently moved out of scope (e.g., mechanism analysis, an additional environment).

- **Wrong response:** silently expand the scope.
- **Right response:** check whether the item can be done in parallel without slipping the primary timeline.
  - If yes, move it back into scope but mark as "stretch" with an explicit decision point in the roadmap.
  - If no, keep out of scope and add to "Future Work" with one sentence explaining when it would be tackled.

## 4 Methodology critiques

### 4.1 "Why this training environment / testbed?"

A reviewer skeptical of the chosen testbed asks for justification.

- **Wrong response:** mention alternatives that were considered and rejected (a defensive frame).
- **Right response:** provide three specific properties of the testbed. For each property: a citation supporting why the property matters and a one-sentence reason for how the testbed exhibits it. Defend the choice on positive grounds.

Template (three property slots):

1. *[Property 1, e.g., information asymmetry] matches real [deployment context].* Supported by [citation for why the property matters]; the testbed exhibits it because [one-sentence reason].
2. *[Property 2, e.g., admits both [paradigm A] and [paradigm B] training under identical infrastructure].* Methodological feature that enables [comparison type].
3. *[Property 3, e.g., mature, reproducible infrastructure].* Supported by [citation for the benchmark and follow-up work].

## 5 Plan-level critiques

### 5.1 "Roadmap is too optimistic"

The timeline does not account for known delays (IRB approval, recruitment, training failures, infrastructure outages).

- **Wrong response:** stretch the end date and hope.
- **Right response:** add explicit decision points with go / no-go thresholds and pre-identified fallback paths. Each major risk should have:
  - Probability estimate
  - Impact severity
  - Pre-committed mitigation

### 5.2 "Multi-track strategy feels overcommitted"

The user worries that the multi-track plan is too ambitious.

- **Wrong response:** drop the second track entirely.
- **Right response:** confirm each track is designed to fall back to an independent submission if its primary venue rejects. The minimum success case (multiple conference papers) is the safety net; the higher-impact outcome (journal or top conference) is the stretch, not the requirement.

If after this check the plan is still too ambitious, reduce the **scope of one track** rather than dropping it. The multi-track structure adds little overhead once both tracks share a methodology base.
