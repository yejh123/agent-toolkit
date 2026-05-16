# Research Question Format

This file defines the exact format for research-question (RQ) blocks within the §3 Research Questions and Hypotheses section, and the per-hypothesis novelty assessment procedure that fills the block's last field.

## Table of Contents

1. Structure of §3
2. Topic-sentence format
3. Per-RQ block format
4. Hypothesis rules
5. Novelty assessment
6. Numbering rules
7. Total RQ count

## 1 Structure of §3

```
## 3 Research Questions and Hypotheses

[Optional: one paragraph framing why hypotheses are integrated with RQs here.]

### 3.1 Track 1 (label)

[Topic sentence — see §2 below.]

---

#### RQ1
[RQ block — see §3 below.]

---

#### RQ2
[RQ block.]

---

### 3.2 Track 2 (label)

[Topic sentence.]

---

#### RQ3
[...]
```

Use `---` horizontal rules to separate RQ blocks visually. For a single-track proposal, omit the subsection numbering and place all RQs under §3 directly.

## 2 Topic-sentence format

Each subsection opens with a topic sentence in this unified format:

> Track X [verb] [clause about RQ_a] (RQ_a), [clause about RQ_b] (RQ_b), and [clause about RQ_c] (RQ_c).

The verb is action-oriented: *establishes*, *tests*, *examines*, *characterizes*, *investigates*. The number of clauses equals the number of RQs in the subsection. Each clause is concrete: it names the specific phenomenon under that RQ, not an abstract level.

Abstract template form (placeholders, no project content):

> Track 1 establishes whether [phenomenon-a] holds (RQ1), how [structural-factor] modulates [phenomenon-a] (RQ2), and whether [setting-b] is necessary to detect [failure-mode-c] (RQ3).

**Do not use** high-level phrasing like "moves from existence to internal structure to deployment-context modulation". Each clause must refer to a specific phenomenon.

## 3 Per-RQ block format

Each RQ uses this exact structure:

```
#### RQ_n

**Question.** [Short, plain English. No related-work references. No long compound sentences. Asks one question. Ends with a question mark.]

**Term definitions.** [Optional. Include only if non-standard terms appear in the Question or Hypotheses. Define each in 1–2 sentences. Cite the source if the term is proposed in prior work.]

**Hypotheses.**
- H_na (descriptive label). [Hypothesis statement.] Supporting evidence: cite specific papers, or write **"No precedent."** if no prior work supports the prediction.
- H_nb (descriptive label). ...
- H_nc (descriptive label). ...

**Novelty assessment.**
- [H_na is **incremental** / **novel core** / **calibration prediction**.] [One-sentence justification.]
- [H_nb ...]
- [Optional summary line: explicitly state where the novel core concentrates.]
```

## 4 Hypothesis rules

### 4.1 The Question

- One question per RQ. Do not stack two questions joined by "and".
- No jargon in the question itself. Move technical terms to Hypotheses or Term definitions.
- No related-work references in the question. Citations belong in Hypotheses (supporting evidence).
- No forward-looking assumptions in the question. Predictions belong in Hypotheses.
- Length: 1–2 sentences maximum.

### 4.2 Hypotheses

- Each hypothesis has a one-to-three-word descriptive label in parentheses.
- Cite supporting evidence inline. Format: "Supporting evidence: [claim], [citation]; [claim], [citation]."
- If no prior work supports the hypothesis, write **"No precedent."** This is the honest signal that the hypothesis is genuinely novel.
- Predict direction (e.g., training type A produces behavior X) AND magnitude where possible.
- Cap at 3 hypotheses per RQ. If you need 4 or more, split the RQ.

## 5 Novelty assessment

This section defines the procedure for filling in the **Novelty assessment** part of each RQ block.

### 5.1 Why this matters

When every hypothesis in a proposal has prior-work support, the proposal is *consolidation*, not contribution. Reviewers identify this pattern and downgrade. Two failure modes are equally bad:

- **Hidden incremental work.** Claiming novelty for hypotheses that prior work already validates.
- **Confused novelty.** Asserting that "the combination" or "the integration" is novel without identifying which specific claim is unprecedented.

The fix is to label each hypothesis explicitly and concentrate the contribution claim on the genuinely novel components.

### 5.2 The three labels

Use exactly these three labels for consistency across RQs:

- **Novel core.** No precedent for the specific prediction; the hypothesis space is genuinely open. Mark these prominently. The contribution concentrates here.
- **Incremental.** A close analog exists in prior work; the hypothesis is confirmatory or transfers a known phenomenon to a new setting. **Do not hide these.** Reviewers respect honest labels.
- **Calibration prediction.** Predicts magnitude or specific effect size for a known phenomenon. Not a novelty claim, but needed for pre-registration and falsifiability.

### 5.3 Triggering questions per hypothesis

For each hypothesis, ask in order:

1. **Has any paper made this specific prediction?** Search the literature with multiple keyword combinations. Cite at least three search results if the answer is "no". This prevents fooling yourself.
2. **Has any paper made an analogous prediction in a closely related setting?** Close analogs make the hypothesis incremental but not trivial.
3. **What experimental result would confirm vs refute the hypothesis?** If the result space is obvious from prior work, the hypothesis is confirmatory.
4. **What would a skeptical reviewer say?** "This extends [paper], incremental." vs "This is the first study of [direction], novel." If both reactions are plausible, the hypothesis is mixed.
5. **What is the smallest unit of novelty?** If a hypothesis bundles multiple sub-claims, the novel parts are the sub-claims with no precedent. Restate to isolate them.

### 5.4 What "novel" actually requires

For a hypothesis to qualify as **novel core**, at least one of the following must hold:

- The **phenomenon class** is new. No prior work claims an effect in this class.
- The **mechanism** is new even though the phenomenon class is known.
- The **methodology** is fundamentally different (e.g., discovery-oriented inductive analysis replacing hypothesis testing).
- The **forward-looking setting** is new (e.g., a deployment paradigm that did not exist 18 months ago).

Each of these can be challenged. Be ready with the literature search trail.

### 5.5 Positioning incremental hypotheses

Incremental work is publishable and often essential, but it should be framed as **supporting infrastructure**, not as the contribution.

Good framings:

- "H_na is **incremental**. It extends the established [phenomenon-X]-induces-[effect-Y] pattern to a new [setting]. The contribution is a replication in a different setting, not a new phenomenon class."
- "RQ_x serves Track 2 primarily as a control or baseline. The Track 2 contribution concentrates on RQ_y through RQ_z."
- "RQ_w is explicitly replication work. It supports the generality of RQ_v findings but does not by itself produce new insight. Marked optional supplementary."

Bad framings (do not use):

- "H_na is a **first-of-its-kind investigation of [phenomenon-X]-induced [effect-Y]**." (Hidden incremental.)
- "RQ_x is **novel** because it tests humans rather than models." (Same phenomenon class, different sample.)

### 5.6 Common surface-novelty pitfalls

These framings often signal weak novelty claims:

- **"In [adjacent setting]"** prefixes. Adding a setting prefix to a known single-context finding is not novel unless the setting-specific dynamic itself is the contribution.
- **"With humans"** suffix. Adding "with humans" to a known AI-AI finding requires a specific mechanism that humans introduce, not just sample replacement.
- **"On larger models"**. Scaling to larger models is a contribution only if the prediction changes at scale.
- **"On open-weights models"**. Replication on open weights is engineering, not novelty, except for rare capability-discontinuity cases.

### 5.7 Process: when to run the assessment

Run novelty assessment **before finalizing an RQ**, not after. The cost of finding out an RQ is incremental after writing the methodology section is high.

Sequence:

1. Draft the candidate RQ.
2. Run literature search (3–5 distinct queries).
3. For each hypothesis under the RQ, apply the triggering questions in §5.3.
4. Apply labels per §5.2.
5. If the entire RQ is marked incremental, either reframe to extract a novel angle, or explicitly demote to "supporting RQ" with honest labeling. If genuinely all-incremental, drop the RQ.

### 5.8 The honest test

Imagine writing a one-sentence email to the leading expert in the area: "We are testing whether [hypothesis]. Has this been done?"

- Expert responds "Yes, see [paper]." → hypothesis is **incremental**.
- Expert responds "Not exactly, but close to [paper]." → hypothesis is **incremental** with a close analog.
- Expert responds "Interesting, no one has tested that." → hypothesis is **novel core**.

Use this thought experiment liberally to classify each hypothesis honestly.

## 6 Numbering rules

- RQs are numbered globally across tracks (RQ1, RQ2, ..., RQ8). Do not restart per track.
- Hypotheses are scoped to their RQ (H1a, H1b, H1c, H2a, H2b, ...).
- Optional or supplementary RQs are explicitly labeled: "**(Optional supplementary) RQ_n**".

## 7 Total RQ count

- **Single-paper proposal:** 1 Main RQ plus 2–3 Supporting RQs is typical.
- **Multi-track proposal:** 6–8 RQs total across all tracks.
- **More than 9 RQs** (in any case): sub-hypotheses are being elevated to RQs. Consolidate.
- **Fewer than 3 RQs:** RQs are too broad. Split.
