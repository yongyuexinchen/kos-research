---
name: 2026-09-07_Personal EGS_Reward Source Exposure Matrix_任务定义
type: report
subtype: research-report
status: candidate
source: "Phase0 任务定义"
domain: Personal EGS 资产暴露模型（方法论构建）
---

# 任务定义 Phase0：Personal EGS Reward Source Exposure Matrix

> 调研日期：2026-09-07 ｜ 流程：KOS 理论/模型构建型调研（death-pressure-research EGS ⊕ industry-research 模式A）
> 上游：`2026-09-07_PersonalEGS资产配置/D2_暴露与相关性矩阵.md`（A级先行证据）、`egs-theory-v3-essentials.md`（EGS理论）
> 场景对照：对象=30 出头/无业转型 AI 大模型/求职中/流动资产 10–30 万（D2 已定）

## 0. 母问题

建立一个**适用于个人长期资产配置的可计算模型**：个人全部资本（Human/Financial/Business/IP/Cash/Safety/Physical/Option/Network/Reputation）分别依赖哪些**底层 Reward Source**、承担什么功能、受哪些**共同冲击**、有无被传统资产分类掩盖的**隐性相关性**、转换通道为何、各增多少**未来有效路径空间**。

> 目标不是判断哪种资产"最好"，也不是投资推荐；而是产出 **Personal EGS Exposure Model v1.0**：输入 Capital Universe，输出 Reward Source Exposure / Concentration / Common Shock / Correlation / Convertibility / Switchability / Future Effective Path Space。

## 1. 硬性研究纪律（本任务质量核心）

- **禁止预设**：不得预设股票>黄金>债券、全球分散一定对、AI 一定赢、创业一定增期权、职业收入一定最优、房地产一定值得。
- **主动找反例**：每个模型结论都要找 counterevidence / alternative explanation / model failure。
- **不虚构数字**：严格区分 Empirical / Literature-derived / Structural inference / Expert judgment / Scenario assumption。没有实证就不造 0.75/0.80/0.65，宁愿输出"高/中/低"+说明还需什么数据量化。L3 权重不得冒充实证相关性（引用既有 D2 的 L3 数值时必须标注）。
- **允许"模型不足"结论**：不强塞所有现象进模型。

## 2. 证据分级（贯穿全程）

| 级 | 定义 |
|---|---|
| **L1** | 实证数据支持（历史数据/同行评审） |
| **L2** | 多源间接支持（实务/行业共识/权威二手） |
| **L3** | 模型构造/专家判断/分析估计，必须标注、可证伪 |
| **S** | 纯情景假设（Scenario），与 L3 区分 |

## 3. 既有 A 级先行证据（D2，已定稿，本模型须复用并升级）

- AI 伪分散判定：4 条 AI 流（工资/股/创业/内容）=**1 因子 4 皮肤**，ρ 0.65–0.80。
- 有效分散判据："分散的是因子，不是流"；R5 现金/R6 泛行业才是真增路径。
- 边际收益递减表：n 条高相关路径第 3、4 条几乎不降险；第 2 条须选正交因子。
- 对象物理资产结论：当前阶段房产不配(0)、黄金≤5-8%尾部且延后、设备租不买、现金缓冲为主。
- 人力资本"股票化"(Benzoni et al.) + 生命周期"债券化→年轻可高权益但仍需低相关"(Choi-Liu-Liu) 。
- 注意：D2 的相关性矩阵数值为 **L3 估计**，本模型升级时需显式归入"Scenario/Expert"并给出量化所需数据。

## 4. 待构建的最终交付物（14 项）

1. Personal Capital Universe（含重复计算消除）
2. Reward Source Taxonomy（底源级，非"股票=股票源"）
3. Capital × Reward Source 矩阵
4. Capital × Common Shock 矩阵
5. Capital × Capital（correlation/dependence）矩阵
6. Capital Conversion 矩阵
7. Reward Source Concentration Model（RSCI/HHI/entropy 比较）
8. Pseudo-Diversification Tests
9. Capital Cascade 模型（Shock→Mechanism→Loss）
10. Switchability Inputs
11. Future Effective Path Space 框架（ΔPathSpace）
12. Evidence/Assumption Ledger
13. 尚未解决的问题
14. 下一轮进入配置层的变量

## 5. Agent 分工（四路并行）

| Agent | 维度 | 对应母轴 | 基准输出 |
|---|---|---|---|
| **A** | Reward Source Taxonomy（底源级）+ Capital Universe + 资本×奖励源矩阵 | Q1/Q2/Q3/Q4/Matrix1 | 01_RewardSourceTaxonomy与资本宇宙.md |
| **B** | 伪分散 + 相关性(多维) + 共同冲击矩阵 + 串联级联 | Q5/Q6/Q7/Q8/Matrix2/M3 | 02_伪分散共击与级联.md |
| **C** | 转换矩阵 + 路径空间 + 集中度(RSCI) + 生命周期 + 最终模型v1.0 | Q9-Q13/Q15/Matrix3/M4 | 03_转换路径集中度与最终模型.md |
| **D** | 证据账本(E/A/L/S Ledger) + 反例/反对证 + 研究纪律审计 | Q16-19 | 04_证据账本与反例审计.md |

## 6. 验收清单

- [ ] Phase0 + 4 Agent 原始 + 合成报告全部落盘
- [ ] Reward Source 达到"底源级"（向下拆到企业利润/货币信用/劳动力需求等）
- [ ] 四张矩阵 + RSCI + Cascade + PathSpace 全部给出（可以是结构化+高/中/低，非伪精确）
- [ ] 每个矩阵数值标注 L1/L2/L3/S，L3/S 不冒充实证
- [ ] 有 Pseudo-Diversification 判据 + 反例
- [ ] 结论对齐既有 D2（复用而不重复，升级为通用模型）
- [ ] 明确"下一轮进入配置层的待定量变量"
- [ ] 明确"可能需要放弃的模型假设"（自反证）