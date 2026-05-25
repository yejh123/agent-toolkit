# Topic Organization

The ordering principle for an ML/AI related-work document and a generic template to adapt. Topics are organized by their role in the argument, not by chronology or author.

## Table of Contents

1. Ordering principle
2. Generic template
3. Section ordering within a topic
4. Per-section paper count
5. When to deviate

## 1 Ordering principle

Order topics so the reader moves from field context to the specific contribution:

1. **Framing** — risk taxonomies, problem definitions, position papers that set field-level context.
2. **Central phenomenon** — papers establishing the phenomenon the project extends.
3. **Methodology contributors** — training paradigms or evaluation frameworks the project uses or extends.
4. **Setting** — papers specific to the experimental testbed or environment.
5. **Adjacent areas** — related but tangential work that bounds the contribution.
6. **Supporting methods** — algorithms, tools, and infrastructure used in the project.
7. **Summary table** — closes the document (see `entry-format.md` §6).

## 2 Generic template

Adapt the section names to the project's own subject. A typical review has 6–10 topic sections:

```
## 1 [Framing topic]            — taxonomies / problem definitions / position papers
## 2 [Central phenomenon]       — papers establishing the phenomenon the project extends
## 3 [Methodology contributors] — training or evaluation methods the project uses or extends
## 4 [Methodology contributors] — (split when one section exceeds its paper cap)
## 5 [Setting / testbed]        — papers specific to the experimental environment
## 6 [Adjacent area]            — related but tangential work bounding the contribution
## 7 [Supporting methods]       — algorithms, tools, infrastructure used in the project
## N Summary of Gaps and Positioning
```

The number and naming of sections follow the project. The fixed part is the *order*: framing first, supporting methods last, summary table closes.

## 3 Section ordering within a topic

Within each topic section, order papers:

1. **Foundational paper first** — the canonical reference, even if older.
2. **Most directly relevant second** — the paper the project's RQs build on.
3. **Less directly relevant after** — background or context papers.
4. **Optional / tangential last** — papers that bound the contribution but are not central.

Within a tier, order by descending relevance, or most-recent-first when relevance is similar.

## 4 Per-section paper count

| Section type | Typical count | Maximum |
|---|---|---|
| Framing | 2–4 | 5 |
| Central phenomenon | 5–8 | 10 |
| Methodology contributors | 4–6 | 8 |
| Setting / testbed | 3–4 | 5 |
| Adjacent areas | 3–5 | 7 |
| Supporting methods | 3–5 | 6 |

Total: ~30–50 papers for a comprehensive proposal review. If a section exceeds its cap, it is probably two topics — split it. If the whole review exceeds 50 papers, it is becoming a survey; consider citing some papers inline in another section without their own entry.

## 5 When to deviate

Deviate when:

- The project genuinely does not engage one of the roles above (do not include a section just because the template has it).
- A single paper is so central it deserves its own section.
- A paper spans multiple topics — place it in the most central one and reference it from the others.

Do not deviate just to be original: reviewer-familiar topic structures help readers navigate.
