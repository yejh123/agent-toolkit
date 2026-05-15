# Common Topic Organization

This file lists typical topic structures for ML safety / alignment / multi-agent research-proposal related-work documents.

## General principle

Topics should be organized so that:
1. **Framing topics come first** (risk taxonomies, problem definitions).
2. **Phenomenon topics come next** (papers establishing the phenomenon the project extends).
3. **Methodology topics follow** (training paradigms, evaluation frameworks).
4. **Setting topics next** (testbeds, environments).
5. **Adjacent areas bound the contribution** (related but not central).
6. **Supporting methods at the end** (algorithms, tools used in the project).
7. **Summary table closes the document**.

## Template structure for multi-agent safety proposals

```
## 1 Multi-Agent Risk Taxonomy and MAS Safety (framing)
Papers like: Hammond et al. Multi-Agent Risks; Cemri MASFT; Social Cost of Intelligence; Risk Analysis for Governed MAS

## 2 Emergent Misalignment (the central phenomenon)
Papers like: Betley et al. EM; Taylor et al. School of Reward Hacks; Wang et al. RL-induced EM; Dickson EM replication; Afonin ICL-induced EM; Cloud Subliminal Learning; Soligo Convergent Linear Representations; Conditional EM

## 3 Multi-Agent Training Paradigms (training methods studied)
Papers like: Self-RedTeam; MACA; Latent Agents/IMAD; SPIRAL; Concordia; SWE-RL; Multi-Agent Evolve

## 4 Bias, Conformity, and Collective Behavior in LLM MAS (RQ2/RQ5 ground)
Papers like: Aligned Agents Biased Swarm (Li 2026); Conformity Dynamics in LLM MAS; Conformity Generates Collective Misalignment; Disentangling LLM Social Conformity; Too Polite to Disagree; Peer Identity Bias; Unmasking Conversational Bias

## 5 Human-AI Interaction and Sycophancy (RQ3/RQ4 baseline)
Papers like: Sharma sycophancy; Syco-bench; HAICOSYSTEM; Dark Patterns Meet GUI Agents; Asch 1956 conformity (classical)

## 6 LLM Oversight and Monitoring (RQ6/RQ7 ground)
Papers like: Kutasov Weak-to-Strong Monitoring; DeceptGuard; Constitutional Black-Box Monitoring; Noticing the Watcher; Sleeper Agents; Alignment Faking; LH-Deception; Christiano amplification

## 7 Avalon and Social Deduction Agents (setting)
Papers like: AvalonBench; Stepputtis long-horizon dialogue; Trust Lies Long Memories; CSP4SDG

## 8 Sabotage Evaluation and Information Asymmetry (evaluation environments)
Papers like: Benton Sabotage Evaluations; Korbak frontier stealth; WMDP; HIDDENBENCH; iAgents; AsymPuzl

## 9 Supporting Methods (RLVR, persona vectors, ICL theory)
Papers like: DeepSeek-R1; GRPO; Persona Vectors; ICL-as-gradient-descent

## 10 Summary of Gaps and Positioning
A 2-column table mapping each identified gap to the RQ that addresses it.
```

## Template structure for emergent-misalignment papers

```
## 1 Misalignment in Foundation Models (framing)
## 2 Narrow Fine-Tuning Producing Broad Effects (central phenomenon)
## 3 Reward Hacking and RL-Induced Misalignment (adjacent)
## 4 Persona-Level Behavioral Shifts (mechanism)
## 5 Mechanism Interpretability for Misalignment (mechanism)
## 6 Inoculation and Defense (mitigation)
## 7 Evaluation Benchmarks for Misalignment (setting)
## 8 Supporting Methods (RLHF, persona vectors, SAEs)
## 9 Summary of Gaps and Positioning
```

## Template structure for evaluation / safety-benchmark papers

```
## 1 Frontier Safety Evaluation (framing)
## 2 Specific Capability Benchmarks (related benchmarks)
## 3 Adversarial Evaluation and Red-Teaming (methodology)
## 4 Human-Participant vs Automated Evaluation (methodology contrast)
## 5 Multi-Agent Evaluation (if applicable)
## 6 LLM-as-Judge Methodology (judge bias, calibration)
## 7 Failure Mode Taxonomies (related taxonomies)
## 8 Supporting Methods
## 9 Summary of Gaps and Positioning
```

## Template structure for multi-agent training papers

```
## 1 Post-Training Paradigms (framing: SFT, RLHF, RLVR, RFT, etc.)
## 2 Self-Play and Adversarial Training (related training methods)
## 3 Cooperative Multi-Agent Training (related training methods)
## 4 Debate and Consensus Distillation (related)
## 5 Negotiation and Mixed-Motive Training (related)
## 6 Downstream Generalization of Training (adjacent)
## 7 Evaluation of Multi-Agent-Trained Models (setting)
## 8 Supporting Methods (RL algorithms, infrastructure)
## 9 Summary of Gaps and Positioning
```

## When to deviate from these templates

Deviate when:
- The project genuinely doesn't engage with one of the suggested topics (don't include it just because the template has it).
- A specific paper is so central that it deserves its own topic section.
- A paper's contribution spans multiple topics; in that case, place it in the most central one and reference from the others.

Do not deviate just to be original. Reviewer-familiar topic structures help readers navigate.

## Section ordering rule

Within each topic section, order papers by:
1. **Foundational paper first.** The canonical reference, even if older.
2. **Most directly relevant to our project second.** The paper our RQs build on.
3. **Less directly relevant after.** Background or context papers.
4. **Optional / tangential last.** Papers that bound the contribution but aren't central.

Within these tiers, order by descending relevance or chronologically (most recent first) if relevance is similar.

## Per-section paper count

| Section type | Typical count | Maximum |
|---|---|---|
| Framing (§1) | 2–4 | 5 |
| Central phenomenon (§2) | 5–8 | 10 |
| Methodology contributors (§3, §4) | 4–6 | 8 |
| Setting / testbed (§7) | 3–4 | 5 |
| Adjacent areas (§5, §6) | 3–5 | 7 |
| Supporting methods (§9) | 3–5 | 6 |
| Summary table (§10) | N/A | N/A |

Total: ~30–50 papers for a comprehensive proposal review.

If the count exceeds 50, the document is becoming a survey. Consider whether some papers can be cited inline in other sections without their own entry.
