# OSF 预注册：EGS Study 1（直接复制提交）



> 提交到 OSF Pre-registrations（用 yongyue163@gmail.com 账号，与 EGS 命题集同账号）

> 建议格式：OSF Standard Pre-Data Collection Registration

> 以下文本按 OSF 注册表单字段组织，直接复制对应段落。



---



## Title（标题）



**Study 1: Expected Guarantee Fulfillment, Guarantee Asymmetry, and Desire Shutdown in Chinese Adults — A Cross-Sectional Survey**



## Author / Affiliation（作者/单位）



Yong Yue (永月) — Independent researcher. No institutional affiliation. Correspondence: yongyue163@gmail.com



## Hypotheses（假设，逐条预注册）



- **P1.1:** Expected GFR is negatively correlated with Guarantee Asymmetry Index (GAI), expected r ≈ .3–.5. (Operationalization: Expected GFR = mean of 12 items across education/occupation, marriage/family, housing/status domains, reverse-scored as marked; GAI = Z(negative sanction expectation) − Z(positive promise expectation), computed per individual.)

- **P1.2:** The GFR–GAI relationship is driven by positive promise expectations declining faster than negative sanction expectations (path model: GFR → positive expectation coefficient significantly larger in magnitude than GFR → negative expectation coefficient).

- **P1.3:** GFR predicts GAI with incremental validity beyond controls (generalized pessimism, institutional trust, relative deprivation, perceived social mobility, future orientation) — ΔR² significant at α = .05.

- **P1.4:** Perceived punitive pressure (negative sanction expectation) is positively correlated with desire shutdown (aspiration suppression), r expected > .2.

- **P1.5:** Perceived punitive pressure is positively correlated with expected post-goal disappointment (ceiling reference point).



## Design（设计）



Cross-sectional online survey (Chinese adults, convenience sample via social media distribution). No randomization. Single wave. Preregistered decision rules below.



## Sample size & stopping rule（样本量与停止规则）



- Pilot: N ≈ 150 for EFA (B-section 12 items). Then full sample N ≥ 300 for CFA and hypothesis tests.

- Stopping rule: collect until N = 300 valid responses (after exclusions), or 4 weeks, whichever comes first.

- Power: N = 300 detects r = .3 at power > .90 (α = .05, two-tailed).



## Exclusion rules（排除规则，预注册声明）



1. Fails either attention check (2 embedded).

2. Completion time < 120 seconds.

3. Missing > 20% of core items (B–F sections).

4. Straight-lining: same response option on ≥ 80% of B-section items.



## Variables（变量）



- **Expected GFR (12 items, B section):** 3 domains × 4 items (education/occupation; marriage/family; housing/status). 5-point Likert (1=strongly disagree → 5=strongly agree). Six reverse-scored items. Expected structure: single general factor + 3 domain factors (EFA/CFA to verify).

- **Positive promise expectation (3 items, C):** expected rewards from participating (income security / social status / autonomy). 5-point Likert.

- **Negative sanction expectation (3 items, D):** probability framing (how likely to lose income security / status / respect if exiting the competitive system). 5-point (1=almost impossible → 5=almost certain).

- **GAI:** Z(D mean) − Z(C mean), per individual.

- **Desire shutdown (3 items, E):** aspiration suppression. **Target of discriminant validity vs. sour grapes (2 items, G13–G14) and post-goal disappointment (3 items, F).**

- **Controls (12 items, G1–G12):** LOT-R simplified (3), institutional trust (3), relative deprivation (2), social mobility belief + MacArthur ladder (2), future orientation / CFC (2). Demographics (7).



## Analysis plan（分析计划）



1. **CFA / discriminant validity (mandatory, per reviewer note):**

   - B-section: confirm factor structure (general factor + domains). Report CFI/RMSEA.

   - **GAI orthogonality decision rule (preregistered):** CFA of C and D as two factors. If factor correlation r ≥ .7, OR AVE(positive) < r²(positive,negative), OR AVE(negative) < r² → GAI difference score is invalid (components are one "general social attitude" factor). Backup paths: (a) positive-only analysis; (b) oblique-model residual difference; (c) report both components separately. P1.1 interpretation depends on this check.

   - **P1.4 discriminant validity:** E (desire shutdown) vs. G13–G14 (sour grapes) vs. F (post-goal disappointment): three-factor CFA; if factor correlations > .8, P1.4 construct is not distinguished from adjacent constructs — report and interpret accordingly (want vs. evaluate separation).

2. **Reliability:** Cronbach's α + McDonald's ω per subscale.

3. **P1.1:** Bivariate correlation GFR–GAI, then hierarchical regression: controls (block 1) → GFR (block 2). Report ΔR², β, CI.

4. **P1.2:** Path model with both paths (GFR→positive, GFR→negative); equality-of-coefficients test (Wald).

5. **P1.3:** Incremental ΔR² beyond all controls.

6. **P1.4/P1.5:** Correlations of negative sanction expectation with E and F, controlling for depression symptoms (if PHQ-2 added).



## Materials（材料）



Full questionnaire (45 items + 2 attention checks) available from author on request; will be attached to this OSF registration as a supplementary file.



## Data collection platform（数据平台）



问卷星 (wjx.cn) — Chinese survey platform. Data export CSV; analysis in Python (pandas/statsmodels).



## Ethical note（伦理说明）



Anonymous, non-interventional, self-report survey. No identifying information collected beyond demographics. Participants informed of purpose and anonymity; participation voluntary. No IRB available (independent researcher) — complies with platform terms and Chinese personal-information protection law for anonymous research surveys.



---



*预注册文本 v1.0 | 2026-08-22 | 提交后 48 小时内不可修改（OSF 规则）——提交前请与问卷 v0.2 最终版逐字核对*

