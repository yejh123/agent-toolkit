# Research Question Format

This file defines the exact structure for research-question blocks within the §3 Research Questions and Hypotheses section.

## Structure of §3

```
## 3 Research Questions and Hypotheses

[Optional: one paragraph framing why hypotheses are integrated with RQs here.]

### 3.1 Track 1 (Model Behavior)

[Topic sentence in standard format — see below.]

---

#### RQ1
[RQ block — see below.]

---

#### RQ2
[RQ block.]

---

### 3.2 Track 2 (AI-Human Interaction)

[Topic sentence.]

---

#### RQ3
[...]
```

Use `---` horizontal rules to separate RQ blocks visually.

## Topic sentence format

Each subsection (3.1, 3.2, 3.3) opens with a topic sentence in this unified format:

> Track X [verb] [clause about RQ_a] (RQ_a), [clause about RQ_b] (RQ_b), and [clause about RQ_c] (RQ_c).

Examples:

- *Track 1 establishes whether multi-agent training transfers to downstream tasks (RQ1), how the structural composition of the multi-agent deployment shapes the transfer (RQ2), and whether multi-agent deployment is necessary to detect failure modes that single-agent deployment misses (RQ3).*
- *Track 2 tests whether trained AI affects human acceptance of biased outputs at all (RQ4), through which MAS-specific mechanisms this acceptance is amplified beyond single-AI collaboration (RQ5), and how specific MAS compositions modulate the human-side effect (RQ6).*
- *Track 2 also examines whether monitoring awareness propagates through MAS to enable collective evasion (RQ6) and whether internal trusted reviewers get co-opted by trained agents in MAS contexts (RQ7).*

**Rules for topic sentences:**

- Each clause is concrete (refers to the specific phenomenon, not abstractions like "this domain" or "the question").
- The number of clauses equals the number of RQs in the subsection.
- The verb at the start is action-oriented: *establishes, tests, examines, characterizes, investigates*.
- Do NOT use abstract phrasing like "moves from existence to internal structure to deployment-context modulation." This is too high-level.

## Per-RQ block format

Each RQ uses this exact structure:

```
#### RQ_n

**Question.** [Short, plain English. No related-work references. No long compound sentences. Asks one question. Ends with a question mark.]

**Term definitions.** [Optional. Include only if non-standard terms appear in the Question or Hypotheses. Define each term in one or two sentences. Cite source if the term is proposed in prior work.]

**Hypotheses.**
- H_na (descriptive label). [Hypothesis statement.] [Supporting evidence: cite specific papers with arXiv IDs, or write "No precedent." if no prior work supports this prediction.]
- H_nb (descriptive label). ...
- H_nc (descriptive label). ...

**Novelty assessment.**
- [H_na is incremental / novel core / a calibration prediction]. [One-sentence justification.]
- [H_nb is incremental / novel core / a calibration prediction]. [Justification.]
- [Optional summary: explicitly state what's novel and what's confirmation.]
```

## Worked example

```markdown
#### RQ1

**Question.** Does training in multi-agent environments induce systematic misalignment behaviors on realistic, multi-horizon deployment tasks?

**Hypotheses.**
- H1a (adversarial direction). Adversarial multi-agent training (Avalon evil-team RL) induces measurably elevated *deception* behaviors on downstream tasks. Supporting evidence: extends the narrow-finetune-to-broad-misalignment pattern documented for harmful content (Betley et al., 2025, arXiv:2502.17424), reward hacking on harmless tasks (Taylor et al., 2025, arXiv:2508.17511), and RL on exploitable coding rewards (Wang et al., 2025, arXiv:2511.18397).
- H1b (cooperative direction). Cooperative multi-agent training (Avalon good-team RL) induces measurably elevated *collusion* behaviors — sycophantic peer deference, bias amplification, undue consensus convergence. **No precedent.**
- H1c (effect size). Effect sizes are smaller than harmful-content fine-tuning (Betley et al., 2025 reports ~20%) but statistically significant, because game-context legitimization may provide partial inoculation analogous to the educational-framing control in Betley et al. (2025).

**Novelty assessment.**
- H1a is **incremental**. It extends the established adversarial-training-induces-misalignment pattern to a new training source (Avalon RL).
- H1b is **the novel core of Track 1**. Cooperative training as a source of misalignment has no precedent in the EM, RL, or alignment literature.
- H1c is **a calibration prediction**, not a novelty claim.
```

## Rules

### For the Question

- **One question per RQ.** Do not stack multiple questions joined by "and".
- **No jargon in the question itself.** Move technical terms to the Hypotheses or Term definitions.
- **No related-work references in the question.** Citations go in Hypotheses (supporting evidence).
- **No forward-looking assumptions in the question.** Predictions belong in Hypotheses.
- Length: 1–2 sentences max.

### For Hypotheses

- Each hypothesis has a one- to three-word descriptive label in parentheses: "(adversarial direction)", "(MAS structure)", "(co-optation occurs)".
- Cite supporting evidence inline. Format: "Supporting evidence: [claim], [citation]; [claim], [citation]."
- If no prior work supports the hypothesis, write **"No precedent."** explicitly. This is the honest signal that the hypothesis is genuinely novel.
- Predict direction (adversarial → deception) AND magnitude (effect smaller than harmful-content) where possible.

### For Novelty assessment

- Use the labels **incremental** (bold), **novel core** (bold), or **calibration prediction** (bold). Use these specific terms for consistency across RQs.
- One bullet per hypothesis if their novelty status differs.
- Add an optional summary line if one or two hypotheses are the "novel core" of the RQ — concentrate the reader's attention on them.

### Numbering

- RQs are numbered globally across tracks (RQ1, RQ2, ..., RQ8). Do not restart per track.
- Hypotheses are numbered by RQ (H1a, H1b, H1c, H2a, H2b, ...).
- Optional/supplementary RQs are explicitly labeled: "**(Optional supplementary) RQ8**".

### Total RQ count

- Aim for 6–8 main RQs across all tracks.
- More than 9 suggests sub-hypotheses are being elevated to RQs; consolidate.
- Fewer than 4 suggests RQs are too broad; split.
