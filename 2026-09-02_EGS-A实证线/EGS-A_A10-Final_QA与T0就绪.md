# EGS-A Empirical Track · A10-Final Pre-Launch QA

> ⚠️ **SUPERSEDED（2026-09-02 路线切换）**：本文件所属"问卷/心理测量验证路线"已整体**降级为备用研究路线**（未来学术发表可用），不再作为当前主线。主研究路线已切换为 **Field Trial（现实决策事件路线）**——见同目录 `EGS-A_A11_FieldTrial_Protocol_v01.md`。本文件内容**保留不覆盖**，作为备用路线的冻结文档与 A11 的对照引用。

> 日期：2026-09-02
> 角色切换：设计者 → **执行者 + 记录者 + 实证审计者**——协议已是研究对象，不再讨论草稿
> QA 目标：检查冻结协议能否无歧义执行；发现问题只标 blocker，不改理论/统计目标
> 冻结引用：A6（P-C/P-B 框架）、A9（唯一 criterion Y^P_d）、A10（预试协议）、CodeArt B11/B9（GFR^global / P^d 接口）

---

## A10-QA-1 Pre-launch blockers

### 🔴 Blocker（阻断 T0 执行）：**0 个**

逐条检查后未发现阻断项——冻结协议（领域集合/P^d 双框架/Y^P_d 行为痕迹/GFR 总体层/机会记录/主模型/差分识别/失败路径）均可无歧义执行。

### 🟡 Documented non-blockers（不阻断执行，但须在执行记录中显式标注）

| # | Non-blocker | 说明 | 处置（记录不修改）|
|---|---|---|---|
| NB1 | **A10-7 Success 条件① α≥0.7 表述修正** | 本轮 QA 第 7 条用户指令：不再以 α≥0.7 作单独 ontology 判定标准 | 采纳为冻结状态修订——信度改为 alpha/omega + item discrimination + CFA + test-retest + ceiling 综合判断；P 删除由 measurement+criterion validity+within-person 共同决定 |
| NB2 | **GFR 12 题跨域聚合 vs P^d 域重叠** | 旧 v0.2 GFR 量表是 3 域（edu/marriage/housing）聚合——与 P^d 的 edu/career 域题面有域重叠，判别效度检验须处理 | 分析计划：报告 GFR 全域分 与 去重叠域残差 两种判别；Content Overlap Audit（A6-2 规则：GFR 第三人称总体 vs P 第一人称条件句）强制执行 |
| NB3 | **P-C/P-B 双版的主模型取值** | A10-2 内嵌两框架、A10-4 的 β_P 未指定用哪版 | 预试定位下非歧义：两版各跑 Model 1 + 诊断（ceiling/判别），框架裁决后**正式样本冻结赢家**；预试报告两版差异 |
| NB4 | **Y 零膨胀风险**（income 域副业基线率低）| Y^d=0 可能集中于低机会人群 | Y 记双层面（是否发生 + 次数/金额，QA 第 3 条已要求）；T0+6M 分析计划预留 hurdle/零膨胀 或 二元+强度 双规格 |
| NB5 | **6 个月 attrition / 行为核验执行风险** | 追踪 6 个月有流失 | Not identified 路径已覆盖（A10-7 Failure C）；非协议缺陷，属执行风险记录 |

### ✅ 已冻结项（QA 确认无需再议）

领域 d∈{edu,career,income} / P-C+P-B 两框架（不提前宣布胜者）/ Y^P_d=未来6月领域持续投入（commitment/effort 统一层级）/ GFR^global 保持总体层 / P^d_t→Y^P_{d,t+1} 时间序 / H0_load 载荷检验（差分不得假定 GFR 自动抵消）/ Failure A·B·C + Success 四路径 / 禁止 outcome shopping·改 Y·改 domain·改成功标准·事后挑领域。

---

## A10-QA-2 Measurement consistency（三域同构检查）

| 维度 | edu | career | income | 一致性判定 |
|---|---|---|---|---|
| P^d 框架 | P-C+P-B 同模板 | 同 | 同 | ✅ 仅换 X_d/Y_d 内容 |
| P^d 题面结构 | X_d→Y_d 条件句 | 同 | 同 | ✅ |
| P^d 量表 | 同尺度同锚点 | 同 | 同 | ✅（A6 冻结）|
| Y^P_d 抽象层级 | commitment/effort | 同 | 同 | ✅ 统一为"持续投入" |
| Y^P_d 具体形态 | 报名/缴费/考证记录 | 晋升/竞标/跳槽事件 | 储蓄/副业/增资流水 | ✅ 允许不同但同构 |
| 混合层级风险 | — | — | — | ⚠️ 已禁止 edu=次数/career=满意度/income=态度；QA 第 3 条逐域五字段记录（发生/次数/时间/可验证/机会）强制执行 |

**QA-2 判定：三域 P/Y 同构成立，无层级混杂结构。** 需执行者逐域填 QA 第 3 条五字段（写入 T0 数据字典，见 QA-5 附件）。

---

## A10-QA-3 Identification readiness

| 识别要素 | 状态 | 检查 |
|---|---|---|
| GFR/P^d 分离 | 🟡 待验证 | 判别效度是预试产出之一（NB2 记 Content Overlap Audit 必做）——预试即检验，非 blocker |
| 域变异 | 🟡 待验证 | 三域 sd 同构性是预试六输出之一 |
| opportunity exposure | ✅ 协议含 | Opportunity^d_t 记 binary/ordinal（QA 第 4 条）——Y^d=0 的 P-低 vs 机会-零 混淆已纳入控制 |
| within-person variation | 🟡 待验证 | ΔP 分布是预试先查项（人人 P^edu=P^career 则差分无功效）|
| Y 可获得性 | 🟡 待验证 | 行为痕迹获得率 <60% 触发前瞻登记 fallback；再不可得→Failure C（Not identified，不写 P 无效）|
| 载荷结构 | ✅ 预注册 | H0_load(L_edu=L_career=L_income) 先检验；被拒则保留 GFR×domain 交互，禁写"差分后 GFR 必归零"|

**QA-3 判定：识别设计就绪——所有"待验证"项都是预试的诊断输出而非协议缺陷。**

---

## A10-QA-4 Protocol deviations（执行歧义清单——只标记不修改）

| # | 歧义点 | 现状 | 处置 |
|---|---|---|---|
| PD1 | A10-7 Success ①含 α≥0.7 与 QA 第 7 条冲突 | 用户本轮主动修订 | 已按 QA 第 7 条采纳为新冻结表述（NB1）|
| PD2 | A10-4 主模型 β_P 未写 P-C/P-B 取版 | 预试两版各跑 | NB3 记录，正式样本冻结赢家 |
| PD3 | opportunity 字段 T0 自报的"未来6月机会"不可验证 | ordinal 自报+confidence 字段 | 记录为预测性自报，T0+6M 可对照实际（探索性，不改主模型）|
| PD4 | 行为痕迹"可验证性"边界（收据 vs 自报）未逐域定标准 | QA 第 3 条要求记录可验证性 | 数据字典 confidence 字段承载；逐域验证标准在采集手册定（不涉理论）|

**PD1-PD4 均不改变理论对象或统计目标——全部为执行细节，按 NB/记录处置。**

---

## A10-QA-5 T0 readiness verdict

# ✅ **READY WITH DOCUMENTED NON-BLOCKERS**

- Blocker 数：0
- Non-blockers：5（NB1-NB5——全部是执行标注/表述修订，无理论或统计目标变更）
- Protocol deviations：4（PD1-PD4——执行细节，已记录处置）
- 冻结项：全部确认

**理由**：冻结协议（领域/P^d/Y^P_d/GFR/主模型/差分识别/失败路径）可无歧义执行；所有悬而未决项都是**预试自身要产出的诊断**（判别效度、域变异、ΔP、Y 获得率），不是前置阻断。

---

## A10-QA-6 下一步唯一任务

# **启动 T0 采集**（T0 → P^d + GFR + Y_t + Opportunity）

执行清单（执行者动作，不含新设计）：
1. 依 A10-2 构造三域 × 双框架（P-C/P-B）P^d 题块 + GFR（第三人称总体，NB2 内容审计）+ Y_t baseline + Opportunity^d + controls——**不新增题外概念**
2. 发布 N≈80-120 T0 问卷（问卷星/Credamo）
3. 采集后按 A10-8 六输出诊断（ceiling/判别/域变异/ΔP/Y 获得率/attrition 基线 + opportunity 分布）
4. **6 个月后** T0+6M 采 Y^P_d → 跑 A10-4/5 主模型与差分检验 → A10-7 裁决

**执行者纪律**：T0 开始后禁止换 P 题/domain/Y/时间窗/成功标准/挑参与者/强化优势领域；严重执行问题单独记 protocol deviation，不偷偷修正。

---

### 附件：T0 最小数据字典（A10-11 落地，字段可调但理论对象不变）

| 字段 | 类型 | 必填 | 作用 |
|---|---|---|---|
| subject_id | ID | 是 | 个体追踪 |
| frame | categorical (P-C/P-B) | 是 | 框架标识（每域两值）|
| GFR_global | continuous | 是 | 总体担保兑现信念 |
| P_edu / P_career / P_income | continuous | 是 | 三域条件性正向承诺信念 |
| Y_edu_t / Y_career_t / Y_income_t | outcome（发生+次数/金额双层面）| 是 | 领域投入 baseline |
| opportunity_edu / _career / _income | binary/ordinal | 是 | 未来6月领域机会（T0 自报+confidence）|
| Y_edu_T6 / Y_career_T6 / Y_income_T6 | outcome（T0+6M 采集）| 是（随访）| 领域持续投入 criterion |
| confidence | ordinal | 是 | 行为记录可信度 |
| controls | structured | 是 | 资源/机会/历史投入/人口/领域成本 |

*理论对象锁定：GFR^global 与 P^d 的分离、P^d 对同域未来投入的增量、within-person 领域分配——三个问题在 T0 冻结后由数据回答，不由研究者回答。*
