# EGS-A Empirical Track · A10：P^d → Y^P_d 正式预试协议

> ⚠️ **SUPERSEDED（2026-09-02 路线切换）**：本协议原为当前主线的预试协议，现已**降级为备用研究路线（问卷/心理测量验证，未来学术发表可用）**。当前主路线为 **Field Trial v0.1**（现实决策事件），见同目录 `EGS-A_A11_FieldTrial_Protocol_v01.md`。本文件保留不覆盖；其中"领域集合 d∈{edu,career,income}、P^d 绑定 X_d→Y_d、Y 用行为痕迹、禁止 outcome shopping"等理论约束在 Field Trial 中以现场形式继承。

> 日期：2026-09-02
> 冻结接口（CodeArt B11/B9）：GFR^global=总体担保兑现信念；P^d=f_d(Z_shared,Z_d) 领域条件正向承诺信念；P 唯一职责=解释 GFR 单值无法解释的领域级持续投入与跨领域资源配置
> 冻结 criterion（A9）：Y^P_d=领域 d 持续投入，P^d_t→Y^P_{d,t+1}
> 性质：预试协议（不是正式理论验证、不是大规模回归、不改 P ontology）
> 禁止：outcome shopping / 改 Y / 改 P ontology / 加新领域 / 改 GAI / γP>γS / 扩 w_R / 27 国 P0 / 按显著性重定义 P

---

## A10-1 Frozen design（冻结设计概览）

| 元素 | 冻结值 |
|---|---|
| 领域集合 | **d ∈ {education, career, income}**——冻结，不得看结果后替换 |
| 每域要素 | (X_d 机制行动, Y_d 兑现回报, I_d 投入行为, R_d 行为痕迹, M_d 测量框架) |
| P^d 测量 | A6 双框架比较：P-C（情境化概率×幅度）+ P-B（纯概率），**两个预先固定框架** |
| Y^P_d | 未来 6 个月实际领域持续投入（行为痕迹优先）|
| 时间结构 | 两波：T0（P^d, GFR, Y_t baseline）→ T0+6 月（Y^P_{d,t+1} 行为痕迹）|
| 样本 | 预试 N≈80-120（框架比较/ceiling/判别/Y 可执行性）——非正式功效样本 |
| 主问题 | 同样的总体担保环境下，P^d 能否解释"人把持续投入放在哪个领域"？|

---

## A10-2 P^d measurement（冻结）

**结构同构要求**：P^edu、P^career、P^income 三域用**完全相同**的框架模板（引导语/量表/锚点仅替换 X_d/Y_d 内容），保证可比。

**P-C 模板（情境化概率×幅度）**：
> "考虑下面的情境：[X_d 的兑现受阻描述——如'你所在行业经历裁员/降薪周期']。如果你仍持续投入 [X_d]，未来获得 [Y_d] 的可能性是？"（概率：0-100 滑杆或 5 档）
> 幅度锚：若获得，幅度是 [高/中/低三档描述]

**P-B 模板（纯概率）**：
> "如果我持续 [X_d] 五年，获得 [Y_d] 的可能性是？"（0-100 滑杆/5 档）

**禁止**：看结果后改题；某领域 ceiling 后单独换框架；为显著性改变题目含义。两框架 × 三域 = 6 组题块，被试内嵌比较（同一人答 P-C 与 P-B 的同一域题——框架内比较消除样本差异）。

**同构性检查**：跨域题面语义距离人工审计（X_d/Y_d 结构一致，仅领域内容变）；预试报告三域 P^d 的 α、均值、sd 是否同量级——若某域异常（如 income 无天花板但 edu 有），记录为领域特异性而非题面缺陷，不换题。

---

## A10-3 Y^P_d measurement（冻结）

三域 Y 抽象结构统一 = **commitment/effort in domain d（行为痕迹，非态度）**：

| 域 | Y^P_d（T0+6 月行为痕迹）| 采集方式 |
|---|---|---|
| education | 实际报名/缴费/注册的课程、培训、考试、证书活动（类型+次数+金额）| 收据/注册记录/平台截图自报+核对 |
| career | 正式晋升申请、新项目竞标、技能升级认证、主动跳槽准备事件 | 事件清单（时间+类型）|
| income | 新启动/追加的储蓄计划、副业启动、收入提升项目（金额+流水）| 银行/平台流水自报+核对 |

**禁止混合层级**：不能 edu 用行为痕迹、career 用满意度、income 用态度分——三域必须同一抽象结构。

**Fallback 规则（预注册声明启用条件）**：若行为痕迹获得率 <60%，降级为"前瞻登记承诺"（T0 当场登记可验证的具体行动承诺："我现在就报名 X 课程/注册 Y 计划"——T0+6 月核验兑现）——仍是行为承诺非"我想"；若此亦不可得 → 记 **Failure C（Not identified）**，不把缺数据当 P 无效。

---

## A10-4 Primary models（主模型）

逐域跑，核心是 ΔR² 与 β_P：

```
Model 0:  Y^d_{t+1} = α + β_G·GFR_t + γ·Controls + ε
Model 1:  Y^d_{t+1} = α + β_G·GFR_t + β_P·P^d_t + γ·Controls + ε
```

核心量：
```
ΔR² = R²(M1) − R²(M0)        且报告 β_P 与 95% CI
```

**"显著"不是唯一标准**——报告 ΔR² 点估计与 CI（哪怕不显著，若 ΔR² 有量级但 N 小，标记"方向支持、功效不足，待正式样本"）；不显著 + ΔR²≈0 → 指向 Failure A。

---

## A10-5 Within-person domain test（最锋利检验——诚实识别条件）

**不假定 GFR 自动抵消**。一般模型：

```
Y_{id,t+1} = α_i + δ_d + β_G·L_id(GFR_i) + β_P·P_id,t + ε_id
```
- α_i = individual fixed effect（消个人总体投入倾向）
- δ_d = domain fixed effect（消领域基线差异，如 career 事件天然比 income 多）
- L_id = GFR 对领域 d 的**允许载荷**——GFR 对每域投入的影响可能不同（个人 GFR 主要来自其教育经历时，对 edu 投入影响可能更强）

**识别条件（必须检验，不得假设）**：
- **H0_load: L_edu = L_career = L_income**（载荷跨域相等）→ 若成立，域内差分消去 β_G·L·GFR 项：
  ```
  ΔY_ij = (δ_j−δ_k) + β_P·ΔP_ij + ε        （i 固定效应与 GFR 项抵消）
  ```
- 若 H0_load 被拒（载荷不等）→ **禁止写"差分后 GFR 必然归零"**——须保留 GFR_i × (domain) 交互项，检验 P^d 在载荷结构之上仍有增量。

**预试载荷检验**：三域 Y 对 GFR 的回归斜率是否跨域相等（Δβ_G 的 CI）——若预试样本太小无法判，正式样本必须做。

**裁决标准（对应 A10-9）**：真正支持 P 不可约 = P^d 解释同一主体内部的领域投入差异，且该差异不能被 GFR^global + 预固定 domain effects 完全解释——即 **β_P（within-person）在 ΔP→ΔY 差分或载荷控制模型中显著且方向一致**。

---

## A10-6 Confounding / reverse-causality controls

**控制（只加理论明显的共同原因）**：
1. 当前实际资源/支付能力（收入、储蓄——决定"能不能投入"非"想不想"）
2. 当前领域机会结构（该领域可得的客观机会：如 career 域当前公司晋升窗口）
3. 历史领域投入 Y_d,t（T0 的过去投入 baseline）
4. 必要人口：年龄/教育/职业阶段/城市
5. 领域成本/约束（学费/行业门槛）

**禁止**：控制位于 P^d→Y^d 因果路径上的中介（如"投入意愿"测量、P^d 的直接行为近端）；为"越控越严谨"无限加 covariates。

**反向因果（Y_t→P_{t+1} 亦可能）的主设计防御**：
- T0 测 P^d_t **先于** Y 采集（Y 在 T0+6 月）
- T0 同时记录 Y_t baseline → 核心模型优先：
  ```
  Y_{t+1} = f(P_t, GFR_t, Y_t, …)
  ```
  检验的是"**已知过去投入后**，P 是否仍预测新增/持续投入"——比 P_t→Y_t 干净。

---

## A10-7 Failure / success criteria（预冻结）

| 路径 | 触发 | 处置 |
|---|---|---|
| **Failure A：P 无增量** | P 修复后有足够变异+测量有效，但 β_P≈0、ΔR²≈0、within-person ΔP↛ΔY | **P 理论不可替代性失败** → P 删除/ontology 收缩（不再修饰）|
| **Failure B：P≈GFR 不可分** | P^d 与 GFR 无法获得可靠区分（判别效度持续失败）| **measurement/ontology problem** → 停止优化，不再换题找显著性；回 CodeArt B 线 |
| **Failure C：Y 不可得** | 测量成功但行为痕迹与登记承诺均无法可靠获得 | **Not identified**——不是理论失败也不是成功；不得把无数据写成"P 无效"|
| **Success** | 四条件**同时**满足：① P 测量稳定（α≥0.7、无天花板）② P/GFR 可区分（判别效度通过）③ P^d 对同领域未来持续投入方向一致增量（β_P>0，CI 不含 0 或量级支持）④ within-person domain allocation test 成立 | P^d 具有 GFR 无法替代的经验功能 |

---

## A10-8 Power / sample implications

**预试 N≈80-120** 的用途（非功效验证）：
- P ceiling 率、P/GFR 判别效度（CFA 相关）
- Y 行为痕迹获得率（决定 Fallback 触发）
- 三域 domain-specific variation（sd 同构性）
- within-person variance（ΔP 是否有分布——若人人 P^edu=P^career 则差分检验无功效，这是**预试必须先查的**）
- attrition 率（T0→T0+6 月流失）

**正式样本功效（预试后单独做，不现在拍）**：within-person ΔP→ΔY 的效应量未知——正式 power analysis 依赖预试的 ΔP sd 与 Y 痕迹获得率；预试报告须给出这两个输入量，供正式设计计算 N。

---

## A10-9 CodeArt handoff

**A 线输出边界 = Empirical evidence for/against P irreducibility**（四条件达成的证据包），CodeArt 负责理论解释。

**禁止出现**：
- "统计显著，所以 P 必须存在"（statistical ≠ ontological）
- "不显著，所以 EGS 错了"（一个构念的失败 ≠ 理论整体失败）
- 混淆层级：theory / measurement / criterion validity / identification 四层分开报告——Failure A 是 criterion validity 失败（P 测到了但无功能）；Failure B 是 measurement 失败；Failure C 是 identification 失败——三者理论含义不同，CodeArt 需分别解读。

---

## A10-10 下一步唯一任务

### **执行 P^d × Y^P_d 预试（T0 波采集）**

具体单线：按 A10-2/A10-3 构造三域 × 双框架（P-C/P-B）P^d 题块 + GFR + Y_t baseline + Y 行为登记模块 → N≈80-120 T0 采集 → 报告 A10-8 的五项预试输出（ceiling/判别/Y 获得率/域变异/ΔP 分布）→ **6 个月后 T0+6 波采集 Y^P_d** → 跑 A10-4/5 主模型与差分检验 → 按 A10-7 裁决四路径。

**本轮到此为止的产出边界**：预试问卷与协议冻结（本文件）；数据采集待用户启动。

---

*A10 定论：P^d 的命运由四个同时条件裁决——测量稳定、与 GFR 可分、对同领域未来投入有增量、within-person 领域分配成立。四条全过 P 才有独立生命；任何一条硬失败都通向删除或收缩。跨域差分不得假定 GFR 自动抵消——载荷结构必须被检验，识别条件必须诚实。*
