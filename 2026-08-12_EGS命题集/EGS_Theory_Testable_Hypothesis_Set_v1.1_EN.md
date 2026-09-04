# EGS Theory: Testable Hypothesis Set v1.1

**Author:** Yong Yue

**Contact:** yongyue163@gmail.com

**Date:** 2026-08-13

**Version:** v1.1 (preprint: https://osf.io/preprints/psyarxiv/enyvd_v1)

---

## Abstract

Terror Management Theory (TMT) explains how cultural worldviews buffer death anxiety, but it does not address what happens when the worldview's promises fail to deliver. This paper proposes a new construct — Guarantee Fulfillment Rate (GFR) — the rate at which a society's existential guarantee system actually delivers on its promises. Three testable hypotheses are derived: (H1) when perceived GFR declines, positive promises die first while negative punishments lag behind, producing an asymmetry between fear and trust; (H2) mortality salience effects are moderated by perceived GFR — individuals who have lost faith in the worldview's promises show different terror management responses; (H3) cross-cultural differences in GFR predict measurable differences in fertility, institutional trust, and non-conventional behavior. Operational definitions, study designs, and public data sources are provided for each hypothesis. Falsification conditions are explicitly stated. The framework is offered freely to the research community under CC BY 4.0.

---

## AI/LLM Use Disclosure

The author used AI/LLM tools to assist with drafting, structuring, and language editing of this manuscript. All theoretical content, constructs, hypotheses, and authorship decisions are the author's own; the author takes full responsibility for the content of this work.


> **Existential Guarantee System (EGS) Theory — Testable Hypothesis Set v1.1**
>
> v1.1 revision notes (in response to external methodological review):
> - GFR construct split into Objective / Perceived / Expected fulfillment (v1 conflated them)
> - "Fear/trust ratio" replaced with Guarantee Asymmetry Index (GAI), a difference score
> - H1 narrowed to a single domain (education/occupational returns) to avoid conflating three distinct sanction mechanisms
> - H2 reduced to a directional moderation hypothesis; "attenuated or redirected" dual prediction removed (too many degrees of freedom)
> - H3 (cross-cultural macro) demoted to future research — v1 conflated a research program with a hypothesis
> - Many Labs 4 reframed: motivating puzzle, not evidence for GFR
> - Alternative explanations added (generalized pessimism, institutional trust, relative deprivation, perceived social mobility, future orientation)
> - Authorship paragraph revised per CRediT guidance (CRediT is not an authorship determinant)

---

## 1. Theoretical Gap

**TMT's contribution:** Terror Management Theory has established that death anxiety is buffered by cultural worldviews; mortality salience enhances worldview defense, self-esteem striving, and ingroup bias (Greenberg, Pyszczynski & Solomon, 1986, book chapter; Rosenblatt et al., 1989; review: Pyszczynski, Solomon & Greenberg, 2015).

**The gap:** TMT explains how worldviews buffer death anxiety, but not **where death anxiety goes when the worldview's promises stop being fulfilled**. When a society's existential guarantee system ("work hard → good life") visibly fails, individuals do not simply stop fearing death — the fear remains while trust in the guarantees declines.

**EGS theory's claim:** Every society contains an existential guarantee system (EGS) composed of positive promises ("if you do X, you get Y") and negative sanctions ("if you don't do X, you suffer Z"). The theory's core, empirically testable claim is that **these two components decay asymmetrically**: positive promise expectations collapse faster than negative sanction expectations. "Fear outlives promise."

---

## 2. Core Construct: Guarantee Fulfillment (three levels, not one)

The v1 document conflated three distinct constructs. They are separated here:

```
Objective Fulfillment   — How much society ACTUALLY delivered in the past
                              (macro indicators: intergenerational mobility,
                               real wage growth vs GDP, education returns)

Perceived Fulfillment   — How much the INDIVIDUAL believes society delivered
                              (retrospective perception)

Expected Fulfillment    — How much the individual EXPECTS society will deliver
                              (prospective expectation)  ← THEORETICAL CORE
```

**Why Expected GFR is the theoretical core:** EGS theory is not about whether society *did* deliver; it is about whether individuals still *trust* the system to deliver *in the future*. Behavior (marriage, fertility, effort, escape) is driven by forward-looking expectations, not retrospective accounting. This is the construct that should anchor H1 and H2.

---

## 3. Core Mechanism: Guarantee Asymmetry

```
Expected GFR (low)
      ↓
Positive Promise Expectation ↓↓  (collapses fast)
Negative Sanction Expectation ↓   (declines slowly)
      ↓
Guarantee Asymmetry ↑
      (gap between what you fear and what you believe you'll gain)
```

**Guarantee Asymmetry Index (GAI)** — operationalized as a standardized difference:

```
GAI = Z(Negative Sanction Expectation) − Z(Positive Promise Expectation)
```

Higher GAI = the system's punishments weigh heavier than its promises (fear dominates hope). This replaces the v1 "fear/trust ratio," which had undesirable distributional properties.

---

## 4. H1 (Core, Single Mechanism)

> **H1: Lower expected guarantee fulfillment is associated with higher Guarantee Asymmetry — negative sanction expectations decline less steeply than positive promise expectations.**

Formal statement:

> **H1: Declining expected guarantee fulfillment will be associated with a greater asymmetry between negative sanction expectations and positive reward expectations, such that negative sanction expectations decline less steeply than positive reward expectations.**

**Domain restriction (critical):** The first study tests ONE domain — **education/occupational returns** ("study hard → good school → good job → good income"). Marriage and homeownership sanctions are excluded from Study 1 because they involve distinct mechanisms (social vs. identity/status sanctions). One mechanism at a time.

**Operational definitions (education/occupational domain):**

| Variable | Definition | Measurement |
|----------|-----------|-------------|
| Expected GFR (education domain) | "How likely is it that studying hard will lead to a good job in your future?" | 5-7 point Likert, 4-6 items (prospective framing) |
| Positive promise expectation | Expected reward from participating in the education/occupational system | "If I invest in education, I will get: income security / social status / career autonomy" (Likert) |
| Negative sanction expectation | Expected cost of NOT participating | "If I drop out of this competitive system, I will lose: income security / social status / respect" (Likert) |
| GAI | Asymmetry between the two | Z(sanction) − Z(promise), computed per individual |

**Testable predictions:**
- **P1.1:** Expected GFR is negatively correlated with GAI (r expected ≈ .3–.5)
- **P1.2:** The GFR→GAI relationship is driven by positive promise expectations declining faster than negative sanction expectations (tested via paired comparisons / structural path)
- **P1.3:** P1.1–P1.2 hold after controlling for generalized pessimism, institutional trust, relative deprivation, perceived social mobility, and future orientation (see Section 7)

---

## 5. H2 (Moderation, Directional)

> **H2: Expected GFR moderates the relationship between mortality salience and worldview defense.**

**Rationale:** TMT predicts mortality salience → worldview defense. EGS predicts this classic effect is conditional: when individuals no longer expect the system to deliver, the defense of the *existing* worldview weakens.

**Directional prediction (not "attenuated or redirected"):**

> **H2: The mortality salience → worldview defense effect is weaker among individuals with low (vs. high) Expected GFR.**

**Operational design:**
- 2 (mortality salience vs. control) × measured Expected GFR (median split or continuous moderator)
- DV: classic worldview defense indicators (e.g., outgroup derogation; judge bail paradigm — Rosenblatt et al., 1989)
- N ≥ 200 per condition (based on typical TMT effect sizes and the need to detect moderation)

**What H2 does NOT claim (v1 overreach removed):**
- Does NOT predict "redirected" defense toward alternative worldviews / new religions / radical ideologies (that is H2b for future work — it requires its own theory and measures)
- Does NOT claim to explain Many Labs 4 heterogeneity

**Many Labs 4 framing (corrected):** Many Labs 4 (17 labs, N = 1,550, g = 0.07, 95% CI [−0.03, 0.17]; heterogeneity not significant) demonstrates that the classic mortality salience effect may not be robust under the tested conditions. EGS offers GFR as a **prospective moderator hypothesis to be tested independently** — not as an explanation of that null result.

---

## 6. H3 (Deferred — Future Research)

The v1 cross-cultural macro hypothesis (national GFR → fertility / institutional trust / escape behavior) is **demoted from core to future research**. Rationale:

1. It is a research program, not a hypothesis (8 outcome variables, each with extensive alternative explanations)
2. A national "GFR composite index" risks construct contamination (overlapping with GDP, housing, income, education — i.e., an over-composite index)
3. It cannot be tested credibly before the individual-level construct is validated

**Future sequence (after H1/H2):**
- Study 3: country-level institutional fulfillment → institutional trust (single pathway)
- Study 4: country-level GFR → fertility / demographic behavior (with proper controls and measurement invariance work)

---

## 7. Alternative Explanations (must be ruled out in Study 1)

The unique value of EGS depends on GFR predicting GAI **beyond** established constructs. The first study must control for:

| Alternative | Relation to GFR/GAI | Control strategy |
|-------------|-------------------|------------------|
| Generalized pessimism | Might drive both low expectations and high fear | Control scale (e.g., Life Orientation Test — LOT-R, dispositional optimism) |
| Institutional trust | Could be a proxy for the same construct | Control scale (trust in government/market/science) |
| Relative deprivation | Perceived unfairness could produce asymmetry | Control scale (relative deprivation measure) |
| Perceived social mobility | Overlaps with GFR conceptually | Control (MacArthur ladder / mobility beliefs) |
| Future orientation | Time perspective affects expectations | Control (Consideration of Future Consequences scale) |

**Key falsification criterion:** If GFR adds no incremental predictive validity beyond these controls, EGS's distinctive construct value is challenged. This is the honest test.

---

## 8. Falsification Conditions

**EGS is wrong if:**
1. P1.1 fails (GFR uncorrelated with GAI) → the asymmetry mechanism is wrong
2. P1.3 fails (GFR adds nothing beyond generalized pessimism / institutional trust) → GFR is not a distinctive construct
3. H2 fails (mortality salience × GFR interaction not significant, adequately powered) → the TMT moderation claim is wrong
4. Replication failure of P1.1–P1.2 in a preregistered second sample → the asymmetry is not robust

**Note:** A null H2 is informative but not fatal to EGS — H1 is the core claim. H2 is the bridge to TMT literature.

---

## 9. Measurement Development Plan

Before hypothesis testing, the Expected GFR scale must be validated (this is Study 1a):

1. **Item generation:** 10-12 items across 3 domains (education/occupation, marriage/family, housing/status) — but analyze the education/occupation domain first
2. **Content validity:** expert review (2-3 social/personality psychologists)
3. **Pilot:** N ≈ 150, EFA to check factor structure (expected: single "Expected Fulfillment" factor per domain, or a higher-order general factor)
4. **Validation:** N ≈ 300, CFA, test-retest (2-4 weeks), convergent/discriminant validity against institutional trust and optimism
5. **Measurement invariance:** test across age/gender/education groups before cross-cultural use

---

## 10. Proposed Study 1 (Core Study)

**Design:** Cross-sectional survey, preregistered

- Sample: N ≥ 300 adults, single country (China first — where the phenomenon is most visible)
- Measures: Expected GFR (new scale), Positive promise expectation, Negative sanction expectation (→ GAI), controls (pessimism, trust, relative deprivation, mobility beliefs, future orientation), demographics
- Analysis: correlational + hierarchical regression (GFR after controls); path model for P1.2
- **Preregistration:** OSF preregistration before data collection (this is non-negotiable for credibility)

**Success criterion:** GFR predicts GAI with incremental validity beyond all controls (ΔR² significant, effect size reported with CI).

---

## 11. Proposed Study 2 (Experimental)

**Design:** 2 (mortality salience vs. dental-pain control) × continuous Expected GFR

- Same sample frame as Study 1 or a fresh sample (N ≥ 200/cell)
- DV: worldview defense (classic paradigm)
- Prediction: interaction — MS effect weaker at low Expected GFR
- Secondary DV (exploratory): alternative worldview openness (measured, not hypothesized direction)

---

## 12. Future Macro Studies (after H1/H2 succeed)

- Country-level analysis with careful construct development (dimensions, weights, measurement invariance, sensitivity analysis)
- Single pathway at a time: institutional fulfillment → institutional trust; then GFR → fertility

---

## Usage License and Authorship (revised per CRediT guidance)

**License:** CC BY 4.0 (Attribution 4.0 International). Any researcher may freely use, adapt, and design studies, with attribution.

**Authorship (revised):** If subsequent research substantially builds on the theoretical framework introduced here, researchers are encouraged to cite this work appropriately and to **discuss contribution and authorship at the outset of collaboration**, in accordance with the relevant journal's and institution's authorship policies.

---

## Appendix: References (verified)

| Source | Type | Verifiability |
|--------|------|--------------|
| Pyszczynski, T., Solomon, S., & Greenberg, J. (2015). Thirty Years of Terror Management Theory: From Genesis to Revelation. *Advances in Experimental Social Psychology, 52*, 1-70 | Journal review | DOI: 10.1016/bs.aesp.2015.03.001 |
| Rosenblatt, A., Greenberg, J., Solomon, S., Pyszczynski, T., & Lyon, D. (1989). Evidence for terror management theory I: The effects of mortality salience on reactions to those who violate or uphold cultural values. *Journal of Personality and Social Psychology, 57*(4), 681-690 | Journal article | DOI: 10.1037/0022-3514.57.4.681 |
| Greenberg, J., Pyszczynski, T., & Solomon, S. (1986). The causes and consequences of a need for self-esteem: A terror management theory. In R. F. Baumeister (Ed.), *Public Self and Private Self* (pp. 189-212). Springer | Book chapter | DOI: 10.1007/978-1-4613-9564-5_10 |
| Klein, R. A., et al. (2022). Many Labs 4: Failure to replicate mortality salience effect with and without original author involvement. *Collabra: Psychology, 8*(1) | Journal article | online.ucpress.edu (open access) |
| Yong Yue (2026). EGS Theory public series (Zhihu, Chinese) | Public articles | zhuanlan.zhihu.com |

---

*This document v1.1 | 2026-08-13 | Author: Yong Yue*
*Preprint: https://osf.io/preprints/psyarxiv/enyvd_v1 (v1.1 update)*
*Contact: yongyue163@gmail.com*
