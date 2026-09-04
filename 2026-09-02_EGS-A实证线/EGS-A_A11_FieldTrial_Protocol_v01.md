# EGS-A · A11：EGS Field Trial Protocol v0.1（Reality First）

> 日期：2026-09-02
> 性质：**主研究路线切换协议**——从"心理测量/问卷验证路线"切至"现实指导/现场实验路线（Field Trial）"
> 上游冻结引用：A9（唯一 criterion Y^P_d = 领域持续投入，行为痕迹优先）、A10（领域集合与 P^d 绑定 X_d→Y_d 结构，已整体降级为**备用学术路线**）、CodeArt B11/B9（GFR^global / P^d 接口）
> 角色：设计者 → **执行者 + 记录者 + 实证审计者**（本协议执行后，我不得再改理论对象/判定规则；发现执行问题只记 protocol deviation）
> 立场：本协议不证明 EGS 成立，只回答——**EGS 在真实世界里到底有没有用？**
> 版本纪律：旧版本加 superseded；A10-Final_QA 与 A10_Pd-YdP_预试协议 已标注 superseded（本文件为当前主线）

---

## A11-0 路线切换声明（与 A10 的关系）

| 维度 | A10 备用路线（问卷/测量） | A11 当前主线（Field Trial） |
|---|---|---|
| 主实验单位 | subject / questionnaire respondent | **decision episode / 现实决策事件** |
| 核心成功标准 | α/omega、判别效度、CFA、ΔR²、within-person 差分 | **可重复的 State / Prediction / Intervention / Error / Learning 五模式** |
| 样本策略 | N≈80–120 横截面 + 6 月随访 | **小样本纵向：1 个真实主体 × 多个连续决策事件** |
| 数据介质 | 三域 × 双框架 P^d 题块 + GFR 量表 | **最小 EGS Field Log，每事件一条** |
| 时间结构 | T0 → T0+6M 两波 | **事件驱动：entry（行动前）→ tracking（窗口内）→ closure（结果核实）** |
| 首要问题 | P^d 是否在测量学上独立于 GFR？ | **在真实领域决策中，P^d 是否提供 GFR_global 无法提供的有用信息？** |
| 理论确认规则 | 四条件 Success / 三 Failure | **单次成功不确认、单次失败不证伪——只累积跨事件可重复模式** |

**保留为未来学术路线的资产**（当前不推进、不删除）：N=80–120 招募、P 量表大规模修订、alpha/omega 作为核心标准、CFA/EFA 作为主要验证、正式样本量设计。以上全部降级，不作为 Field Trial 前置条件。

**A9/A10 冻结概念在 Field Trial 中以现场形式继承**（不是废除）：Y 一律用**可观察行为痕迹**而非"我感觉"；P 必须绑定（领域，X→Y）；禁止 outcome shopping / 事后换事件 / 事后改判定标准 / 为保住 P 修改 outcome。

---

## A11-1 Field Trial 的正式目标

**主问题**：EGS 能否通过观察现实中的担保结构变化，形成可执行判断，指导真实行动，并通过行动结果反过来修正自身？

**核心闭环（每事件追踪链）**：

```
现实状态 → EGS 判断(P/S/GFR/A/opportunity) → EGS 预测 → EGS 建议
    → 人采取真实行动 → 现实结果 → 判断是否正确 → 模型/规则修正
```

**三个可判定目标**：

| 目标 | 定义 | 判定材料 |
|---|---|---|
| T1 追踪可行性 | 现实决策事件能否被稳定记录成 Field Log（字段不歧义、行为痕迹可获得） | episode 纳入率、行为痕迹完整率、字段空缺类型 |
| T2 判断-行为-结果一致性 | EGS 判断/预测与随后真实行为及结果的方向是否一致 | Prediction Log × Actual behavior × Outcome |
| T3 学习闭环 | 错误能否定位到具体类型，并导致可记录的规则修正 | Error Log → model_revision 链 |

**非目标（明示放弃，防滑回）**：不追求 p<0.05；不以量表信效度判定胜负；不产出正式论文；不预先证明理论再开始实践；不以模拟数据替代现实。

---

## A11-2 decision episode 定义

### 定义

> **decision episode** = 一个真实决策事件，其中主体面对特定领域内"投入路径 X → 获得结果 Y"（或"不投入/退出 → 承担损失"）的担保结构，必须在现实时间窗内做出承诺/投入/退出/切换的实际选择，且该选择的结果可被可观察行为核实。

### 纳入标准（episode 必须同时满足）

| # | 标准 | 操作检查 |
|---|---|---|
| E1 | **存在明确担保结构** | 能写出一句完整的路径—回报句："若我持续/开始 [X]，则有现实理由相信可得到 [Y]"；或"若不投入/退出 [X]，将失去/承担 [代价]"——两个方向至少一个成立 |
| E2 | **决策在现实窗口内发生** | 事件不是纯思辨/怀旧：主体在接下来 ≤90 天内有真实行为选择点（投入/停止/报名/申请/退出/建立替代） |
| E3 | **结果可观察、可核实** | outcome 有行为痕迹（offer/录取/流水/事件发生/未发生），不依赖主观"感觉更有动力" |
| E4 | **记录时点早于结果** | 至少 P/S/GFR/A/opportunity 与预测在行动前记录（entry 阶段）；纯回顾式事件不进入正式判定（只作 pilot 练习，标 Retrospective） |

### 排除标准（任一命中即不纳入）

| # | 情形 | 理由 |
|---|---|---|
| X1 | 找不到 X→Y 或 ¬X→代价 的担保结构 | 无担保结构的事件不硬套 EGS |
| X2 | 纯态度/情绪/信念表达，无行为选择点 | 不是 decision episode |
| X3 | 结果只能靠主观报告且不可核验 | 违反"行为优先于问卷" |
| X4 | 事件已完成、只能事后重构全部判断 | 违反 E4；记忆污染不可控 |

### 纳入前强制自问（每条 episode 记录中填写）

1. 这个事件里"投入什么路径、期望什么回报"到底指什么？（写不出 X/Y 就不算）
2. 同一个结果是否也可能从别的路径获得？（指向 A，而非强行套 P）
3. 当前这段时期，此人**现实上有没有机会**把该领域投资转化为结果？（指向 opportunity，防止把"没机会"误判成"P 很低"）

---

## A11-3 Field Log 数据字典（最小记录单元）

每个 decision episode = 1 条记录。字段表（全部必填；无法填写的填 `NA` + `na_reason`）：

| 字段 | 类型/尺度 | 记录时点 | 定义与锚定 | 禁止 |
|---|---|---|---|---|
| case_id | text | entry | 唯一编号，如 `FT01-S01-D01`（trial-subject-domain 序号） | — |
| subject_id | text | entry | 主体代号（脱敏，如 S01） | 真实姓名 |
| date | date | entry | 记录日期 | — |
| domain | categorical | entry | 领域标签：首期主域 = education / career / income（A9 三域，跨域对照用）；开放域单列 = relationship / long-term investment / migration / entrepreneurship / other | 含糊标签（如"生活"） |
| current_state | text | entry | 记录时点的**现实状态事实**（客观描述：现状、约束、时间窗） | 评价性语言 |
| **P** | 0–100 + text | entry（行动前） | 领域内**正向担保**："投入 X → 获得 Y"的现实可信度。必须绑定 (domain, X, Y) 与一句理由 | 不绑 X/Y 的抽象"人生希望"；事后补记 |
| **S** | 0–100 + text | entry（行动前） | 领域内**负向担保**："不投入 / 不服从 / 退出该路径 → 将失去什么或承担什么"的现实可信度。记录代价内容 | 与 P 混淆（"没希望"≠S） |
| **GFR** | 0–100 + text | entry（行动前，**先于 P**） | **整体系统层**担保判断："当前所在整体系统（经济/行业/制度/生活结构）对'承诺投入→兑现回报'的总体可信度"。独立判断 | 定义成 P 的平均值；用 P 汇总代替 GFR；事后为解释结果修改 GFR |
| **A** | list + text | entry（行动前） | 替代担保供给：同一核心结果 Y 能否从**其他路径**获得。列出候选路径 + 每条可达性 + 担保来源类型 | 只换措辞不换机制；把"同路径内的变体"当替代 |
| **opportunity** | ordinal 0–3 + text | entry（行动前） | 当前现实机会暴露度：0=无现实入口/1=入口存在但受限/2=正常可得/3=明确敞口。附客观证据（岗位/名额/窗口/资格/经济环境） | 把"无机会"记为"P 很低"；凭主观不给证据 |
| prediction | text（结构化） | entry（行动前） | EGS 对随后行为的预测：方向 + 具体可观察行为 + 时间窗（见 A11-7） | 模糊句（"可能会好一点"） |
| intervention | text + categorical | entry→tracking | EGS 给出的实际建议（若给）+ 类别 + 主体采纳程度（见 A11-8） | 未执行却记为执行 |
| actual_behavior | text（动词表） | tracking | 真实行为：是否开始/停止/投入时间/实际付款/实际报名/实际申请/实际迁移/实际退出/实际建立替代路径 | 意图、倾向、"我感觉更有动力" |
| outcome | text + categorical | closure | 结果：与 Y 对应的可核实事实（获得/未获得/部分获得/窗口未完） | 与预测无关的结果；事后挑结果 |
| prediction_error | categorical | closure | 正确 / 部分正确 / 错误（判定规则见 A11-9） | — |
| reason_for_error | categorical + text | closure | 错误定位：measurement / inference / mechanism / opportunity / intervention / unknown（见 A11-9） | 空泛归因（"模型不够成熟"） |
| model_revision | text | closure | 若错误→修正规则是什么、只对未来预测生效（版本化） | 事后改定义解释已发生结果 |
| confidence | 0–100 | entry | 主体/记录者对本次判断的置信 | — |
| episode_type | categorical | entry | 决策类型：commit（继续/加深投入）/ exit（退出/停止）/ switch（切换路径）/ build_alt（建立替代路径）/ enter（开始新投入）/ withhold（机会在却不投入） | — |
| outcome_window | days | entry | 预定结果核实窗口（按事件类型设定，见 A11-5） | 无限期等待 |
| na_reason | text | 任一 | 某字段缺失的原因（五类：无结构/无机会/无痕迹/窗口未完/记录失败） | 静默缺失 |

**记录三阶段纪律**：
- **entry**（行动前，一次性）：current_state → 直觉预测（先）→ GFR（先于 P）→ P/S → A → opportunity → 结构化预测（后）→ intervention。顺序固定，防止后段污染前段。
- **tracking**（窗口内）：actual_behavior 按动词记录，发生即记，不积压到结果日。
- **closure**（窗口到点）：outcome → prediction_error → reason_for_error → model_revision。

---

## A11-4 最小执行流程

```
┌─ 1. 事件识别：现实中出现真实决策选择点（≤90 天）
├─ 2. 纳入判定：A11-2 的 E1–E4 全过 + 三自问；不过 → 记录候选排除，不硬套
├─ 3. entry 捕获（行动前，一次完成）：
│      current_state → 直觉预测 → GFR → P/S → A → opportunity
│      → 结构化预测（GFR-only 对照 + full）→ intervention（可选）→ confidence
├─ 4. 时间锁定：entry 内容封存（防事后改写解释）
├─ 5. tracking：窗口内实际行为逐条落记录（动词表）
├─ 6. closure（窗口到点或事件终止）：核实 outcome
├─ 7. 误差分析：prediction_error → reason_for_error（强制定位）
└─ 8. 学习：model_revision 只对未来生效；跨事件模式累计进四张表
```

**执行者纪律（本轮唯一约束）**：
- 所有判断**在行动前记录**——这是不可谈判的协议核心。
- 出现执行问题只记 protocol deviation，**不偷偷改协议**。
- 禁止为预测"加分"而事后重述预测内容；禁止用结果反推"当时其实 P 应该更高"。
- 单次成功不确认理论、单次失败不证伪理论——只有跨事件模式进入判定（A11-10/11）。

---

## A11-5 第一批适合测试的现实事件类型

选择原则：**优先高信息量事件 = 有明确担保结构 + 有行为痕迹 + 结果窗口自然存在**；**优先多域竞争事件**（时间/金钱/精力有限，投入此域即不投入彼域）——这类事件最能暴露"P^d 分化 vs GFR 单值"的差异。

| 事件类型 | 典型担保结构（X→Y / ¬X→代价） | 行为痕迹 | 结果窗口（默认） | 域 |
|---|---|---|---|---|
| 是否换工作 | 投递/跳槽 X → 更好的职业位置 Y；不跳=承受现状代价 | 实际投递数、面试、offer | 60–90 天 | career |
| 是否继续培训/考证 | 报名缴费备考 X → 证书/技能 Y | 缴费记录、报名、出勤 | 按考试日期 | education |
| 是否继续升学/深造 | 投入备考 X → 录取 Y | 报名、缴费、申请材料 | 按招生节点 | education |
| 是否继续创业 | 追加投入/维持 X → 业务存活/收入 Y；退出→清算代价 | 资金流水、是否关停、新增投入 | 90 天 | income / entrepreneurship |
| 是否退出某项目 | 停止投入 X → 止损或失去沉没回报 Y | 正式退出动作、资源回收 | 30–60 天 | 按项目域 |
| 是否建立副业/替代收入 | 启动副业 X → 补充收入 Y | 实际注册/发布/首单/流水 | 60–90 天 | income |
| 是否继续婚恋投入 | 维持/推进 X → 关系结果 Y；后撤→关系损失 | 实际约会/沟通/共同决策事件 | 90 天 | relationship |
| 是否继续某长期投资 | 持有/追加/赎回 X → 回报 Y | 实际买卖/定投/赎回记录 | 90 天（或预定估值日） | long-term investment |
| 是否迁移城市 | 迁移 X → 预期生活/职业 Y | 租房/投递跨城/实际搬迁 | 90 天 | migration |

**强制前提**：上表只是候选池——每类事件纳入前仍须过 A11-2 纳入判定。没有明确担保结构的事件**不要**硬套 EGS。

**首批建议组合（供主体裁决，非强制）**：
- 优先选 **2–3 个同窗多域竞争事件**（例：备考 vs 换工作 vs 建副业同时悬而未决），让 P^d 分化有机会显形；
- 若当期只有单域事件，也照常记录（对 State/Prediction/Error validity 仍有价值），但**跨域分化证据需积累到多域窗口**才可用于 P 增量判断。

---

## A11-6 P / S / GFR / A / opportunity 现场记录规则

### P —— 领域内正向担保（绑定路径）

- **最小合格记录**：`P[domain]：投入 [X] → 获得 [Y] = NN/100。理由：…`
- 反例（不合格）："P = 0.35"（无 X/Y）、"人生还是有点希望的"（抽象）。
- X 必须是**具体的持续投入动作**（投递、报名、备考、追加资金、定期投入时间）；Y 必须是**具体的兑现回报**（offer、证书、录取、收入、关系阶段结果）。
- P 记录时同时写下"支撑这个数值的现实证据"（观察到什么让你这么判断），供 closure 对照。

### S —— 领域内负向担保（绑定退出代价）

- 最小合格记录：`S[domain]：若 [不投入 / 不服从 / 退出该路径]，将 [失去 X / 承担 Y] = NN/100。理由：…`
- S 不是"P 低"的同义改写——P 低是"投入也没回报"，S 是"不投入有明确代价"。两者必须能同时写出且含义不同。

### GFR —— 整体系统层担保（禁止降维）

- **记录顺序强制在 P 之前**，避免 P 污染总体判断。
- **禁止**：定义为 P 的平均值 / 由 P/S/A 汇总生成 / 事后按结果调整。
- 合格表述指向系统整体：`GFR：当前整体环境（行业/经济/生活制度）对"投入→兑现"的总体可信度 = NN/100`。
- GFR 是**系统级**判断：同样的职业 P 低，可能 GFR 仍中高（"只是这行不行，系统还行"）——这种分离本身就是有价值的现场数据。

### A —— 替代担保供给（真替代 vs 换说法）

- 记录指向**同一 Y**："若 [X] 达不到，同一个核心结果 [Y] 还能从哪些路径获得？"
- **真替代判定**：路径 j 必须改变**担保来源类型**——新承诺方/新兑现机制。例：
  - 真替代：受雇（承诺方=雇主）→ 副业/自由职业（承诺方=市场/客户）；教育（承诺方=学校证书）→ 自学+作品集（承诺方=作品被市场验证）。
  - 换说法（不算 A）："换一家公司继续投简历"——承诺方仍是雇主类，是同路径内的变体；"换个老师教"同理。
- 每条候选路径记录：`路径 j / 担保来源类型 / 可达性（同 opportunity 档位）/ 是否需要新投入`。
- 若 Y 本身无法从别处获得（如唯一执照通道），A 如实记"无替代"，不硬造。

### opportunity —— 现实机会暴露（与 P 分离）

- **不是信念，是入口事实**。记录客观证据：岗位/名额/报名窗口/资格条件/地区/经济环境/已发生申请数量。
- 档位：0=当前无现实入口；1=入口存在但受限（名额少/资格不符/窗口紧）；2=正常可得；3=明确敞口。
- **防错规则**：出现"投入了但没有结果"时，closure 必须先查 opportunity 再判 P/GFR 错误——只有在机会充分存在而结果仍系统性偏离时，才允许把错误归给 P / GFR / 机制判断（A11-9 的 opportunity check 前置）。

---

## A11-7 Prediction Log

每次 episode 在 entry 阶段记录**三条并列预测**（全部行动前、全部结构化到"可观察行为"级）：

| 预测 | 依据 | 用途 |
|---|---|---|
| Pred_intuition | 常识/直觉（不调用 EGS 语言，**最先记录**） | Failure A 对照：EGS 是否优于常识 |
| Pred_GFR-only | 只看 GFR + current_state，**不看 P/S/A** | Failure B 对照：P 是否提供 GFR 之外的增量 |
| Pred_full (EGS) | 完整五量判断 | 主预测 |

**预测模板（每条约一行+时间窗）**：
```
方向：continue / exit / switch / build_alt / enter / withhold
具体行为：在 [时间窗] 内，[主体] 将 [可观察动作]（如：投出≥N 份申请/报名课程并缴费/停止某项目投入）
时间窗：[X] 天
```

**对照纪律**：
- 三条预测若一致，如实记一致（一致本身是发现：EGS 与直觉无差异是 Failure A 的候选证据积累）。
- 预测一旦记录即**封存**，closure 阶段禁止改写、禁止"补充当时其实想说…"。
- 每条预测给 0–100 confidence（entry 时主观置信，供事后诊断 confidence calibration，不参与胜负）。

---

## A11-8 Intervention Log

EGS 建议是**可选的、显式标记的**环节（Failure C 触发后自动退回观察模式，不主动给建议）。

| 字段 | 内容 |
|---|---|
| advice | EGS 给出的具体建议（一句话，指向可执行动作） |
| rationale | 依据哪些判断给出（引用 P/S/GFR/A/opportunity 中的哪个分化） |
| category | 建议类别：降沉没成本 / 建替代收入路径 / 继续投入 / 退出止损 / 降目标预期 / 等待机会 / 其他 |
| adoption | 主体采纳程度：full / partial / refused + 真实原因（成本、恐惧、时间等——不评判） |
| behavior_change | 采纳后实际行为与 entry 预测的实际行为的关系（一致/不一致/无变化） |
| attribution_note | 结果出现后：结果在多大程度上可归因于该建议（谨慎声明，识别混淆因素） |

**归因纪律**：不建议把 episode 结果直接算成"干预的功劳或过错"——Field Trial 记录的是"建议→采纳→行为→结果"链条是否存在与方向，不做强因果归因（单事件无法排除混淆）。Intervention usefulness 的正式判断须靠**跨事件重复**（多次"采纳 EGS 建议的事件"结果是否系统性优于"未采纳/常识事件"，见 A11-10 I3）。

---

## A11-9 Error Log

每次 closure 必填（对/错都要填，这是 Field Trial 最重要的新增模块）。

**结果判定**：
| 判定 | 条件 |
|---|---|
| 正确 | outcome 与 Pred_full 的具体行为+方向一致 |
| 部分正确 | 方向对但幅度/时间/路径细节偏离（记录偏离点） |
| 错误 | outcome 与 Pred_full 明显不符 |

**错误定位（六类 + 兜底）**——reason_for_error 必须落到具体类型：

| 代码 | 类型 | 判定问题 | 例 |
|---|---|---|---|
| M | measurement error | 现场记录的 P/S/GFR/A/opportunity 本身就记错了（与主体真实判断不符）？ | 主体其实没那个信心，记录时被问高了 |
| I | inference error | 判断对（状态真实）但从判断推出行为预测的推理错了？ | P 高→预期继续投入，但主体因 S 威慑更强而退出 |
| C | causal/mechanism error | 对"担保结构如何驱动行为"的机制理解错了？ | 以为机会敞口会促投入，实际机会太多反而观望 |
| O | opportunity error | 判断时把机会暴露估计错了（过高/过低）？ | 以为岗位多，实际窗口关闭 |
| V | intervention error | EGS 建议本身误导，或建议对但执行走样？ | 建议建替代路径，主体误建成同类竞争 |
| U | unknown | 以上皆否，无法稳定分类 | —（连续 U 触发 Failure D，A11-11） |

**closure 强制写作（禁空泛）**：
```
1. 这次判断对/错在哪一步？（引用具体字段）
2. What would have made the prediction better?
   —— 必须写"如果当时记录到 [缺失信息] / 我当时把 [某字段] 判成 [X] 而非 [Y] / 我若当时核对了 [机会证据]"。
   —— 禁止只写"模型还不够成熟"。
3. 若错误可修正 → model_revision（见下）
```

**Opportunity check 前置规则**：错误判定前先过一遍——"结果偏离是否因 opportunity 本就不足/被误估？"若是 → 优先记 O（opportunity error），不把责任推给 P/GFR（呼应"没有机会≠没有担保"）。

**model_revision 纪律**：
- 修正**只对未来预测生效**；禁止用修正后的定义解释已发生结果。
- 每条 revision 版本化：`rev-YYYYMMDD-N：规则变更内容 / 触发证据（哪次错误）/ 只影响未来预测`。
- 单次错误 → 记录 + 观察；**同一错误模式跨 ≥2 个独立事件重复** → 才允许进入规则级修正候选（防对单事件过度拟合）。

---

## A11-10 成功 / 失败 / Not Identified 判定规则

### Episode 级判定（每条记录 closure 时）

| 判定 | 条件 |
|---|---|
| Episode Success | Pred_full 与实际行为+结果一致，且 Error Log 无未解释偏差 |
| Episode Failure | Pred_full 明显不符（错误） |
| Episode Not Identified | 窗口未完 / 行为痕迹不可得 / opportunity 全程为 0（无现实检验）/ 主体中途取消决策（不再是 episode）——**不得把 Not Identified 写成 P 无效或 EGS 失败** |

### Trial 级判定（Field Trial v0.1 阶段，不追求 p<0.05）

第一阶段的证据语言 = **可重复模式的出现与否**。每次事件只作一个数据点；五模式各自需要跨事件重复才成立：

| 模式 | 成立判据（跨事件） | 反证积累 |
|---|---|---|
| S1 State validity | EGS 对现实担保状态的描述（P/S/GFR/A/opportunity）经常与现实后续变化一致 | 状态判断系统性偏离现实 → 记 measurement/inference 模式错误 |
| P1 Prediction validity | Pred_full 的命中率 ≥ Pred_intuition（常识）且方向稳定 | Pred_full ≈ Pred_intuition 或更差 → Failure A 候选 |
| P2 P-increment | 在 GFR-only 预测失败/模糊而 Pred_full 命中的事件中，差异可追溯到 P^d 分化 | 所有事件 GFR-only 已足够 → Failure B 候选 |
| I3 Intervention usefulness | 采纳建议事件的结果系统性不差于（甚至优于）未采纳/常识事件 | 建议常致更差结果 → Failure C |
| L4 Learning | 错误能被稳定分类（M/I/C/O/V 可区分），且修正后同类错误下降 | 错误无法分类（U 堆积）→ Failure D |

**证据等级标签（报告必标，防"小样本吹模式"）**：
- E1 = 单事件（只描述，不断言模式）
- E2 = 2 个独立事件同向（候选模式，标注"待重复"）
- E3 = ≥3 个独立事件、跨 ≥2 域或 ≥2 主体同向（模式候选成立）
- NI = Not Identified（无证据价值）

### 判定纪律（最高优先）
- **EGS 不因一次成功而获得理论确认，也不因一次失败而立即被证伪**——只累积跨事件、跨领域、跨时间点的可重复预测模式。
- **模型不能事后修改定义来解释已经发生的结果**——所有重要判断在行动前记录，版本化修正只向前。
- 不为"保住 P"修改 outcome；P 的实践价值由 P2 模式裁决，不由研究者意志裁决。

---

## A11-11 Stop Rules（预注册，防止"什么结果都能解释"）

| 代码 | 触发条件（模式级） | 处置 | 何时不算触发 |
|---|---|---|---|
| **Failure A** | P1 反证积累：EGS 预测不比简单常识判断更好（Pred_full 命中率 ≤ Pred_intuition，跨 ≥3 个 E2/E3 事件） | **降低模型复杂度，寻找可删除变量**；协议评审会议记录 | 样本仍为 E1 单事件；Not Identified 事件 |
| **Failure B** | P2 反证：GFR_global 已能解释绝大多数领域行为，P^d 很少提供增量（GFR-only ≈ full，跨 ≥3 个多域事件） | **P 进入删除候选，不得强行保留**；回 CodeArt B 线 ontology 评审 | P 分化无机会显形（无多域窗口）；opportunity 长期为 0 |
| **Failure C** | I3 反证：EGS 建议经常导致更差结果（≥2 个可归因事件） | **暂停 Intervention**，退回 Observe → Infer → Predict 模式 | 单次建议与坏结果的巧合；执行走样（非建议本身） |
| **Failure D** | L4 反证：错误无法稳定分类（unknown 堆积，≥3 个连续错误 episode 无法归入 M/I/C/O/V） | **判定当前 EGS ontology 不足以指导现实**；暂停新增 episode，先修分类框架 | 错误虽多但每次都能明确分类 |

**Stop Rules 执行纪律**：
- 触发即记录为 **trial-level finding**，不等于"EGS 理论错误"——只说明"当前操作化的 EGS 工具在该主体/事件集上没有显示出用途"。
- Failure A/B/C/D 的处置都需要**预注册的评审动作**，不是悄悄删变量或改标准。
- 任何触发/不触发都要写一行理由，防止事后挑选。

---

## A11-12 第一个真实案例的执行模板

### 建议主体（由用户裁决，不默认）

| 候选 | 优势 | 说明 |
|---|---|---|
| S01 = 33 本人（推荐） | 多域竞争窗口现实存在（考研备考=education；岗位/职业=career；副业/IP=income；长期投资=investment）；决策自主、记录便利、纵向追踪可行 | Field Trial 允许 1 主体 × 多事件；33 本人即"第一个真实案例"的最自然选择 |
| S02 = 另一位志愿者 | 提供第二主体跨域重复 | 需知情同意与记录渠道 |

### Case 模板（每条 episode 复制一份填写）

```text
=== EGS FIELD LOG — EPISODE ===
case_id:            FT01-S0X-D01
subject_id:         S0X
date:               2026-09-XX
domain:             [education / career / income / relationship / long-term investment / migration / entrepreneurship / other]
episode_type:       [commit / exit / switch / build_alt / enter / withhold]
outcome_window:     [X] 天（closure 日期：2026-XX-XX）

--- entry（行动前 · 顺序固定）---
current_state:      [现实事实，非评价]
Pred_intuition:     [先写直觉：方向+具体行为+窗口]
GFR:                [整体系统层判断 0–100 + 理由（先于 P）]
P[domain]:          投入 [X] → 获得 [Y] = NN/100；证据：…
S[domain]:          若不投入/退出 → 失去/承担 [代价] = NN/100；证据：…
A:                  同一 Y 的其他路径：路径 j / 担保来源 / 可达性 / 是否需要新投入
opportunity:        [0–3]；客观证据：…
Pred_GFR-only:      [只看 GFR：方向+行为+窗口]
Pred_full (EGS):    [完整判断：方向+具体行为+窗口]
confidence:         NN/100
intervention:       advice=… rationale=… category=…（若无建议填 None）
                    预计采纳程度：full / partial / refused（事前预期）

--- tracking（窗口内 · 发生即记）---
actual_behavior:    [动词表：开始/停止/投入时间/付款/报名/申请/迁移/退出/建替代路径]
adoption:           [intervention 的实际采纳：full/partial/refused + 原因]
行为偏离记录:        [如有偏离 Pred_full，写下是什么]

--- closure（窗口到点 · 证据判定）---
outcome:            [与 Y 对应的可核实事实：获得/未获得/部分获得/窗口未完]
prediction_error:   [正确 / 部分正确 / 错误]
reason_for_error:   [M/I/C/O/V/U + 定位描述]
opportunity_check:  [结果偏离是否因机会不足/误估？是→记 O]
What would have made the prediction better?
                    [具体缺失信息 / 当时应如何判]
model_revision:     rev-2026XXXX-N：…（无则不填）
episode verdict:    [Success / Failure / Not Identified]
evidence_level:     [E1 / E2 / E3 / NI]
```

### 启动检查单（执行前过一遍）

- [ ] 选定主体（S01 = 33 本人？/ S02？）
- [ ] 识别当前窗口内 ≥1 个符合 E1–E4 的真实决策事件（优先多域竞争型）
- [ ] 建立 Field Log 存储（建议：本目录下 `field_trial_logs/`，纯文本/Markdown 或 CSV，不依赖问卷平台）
- [ ] entry 三阶段顺序固定执行；记录即封存
- [ ] 每周一次 tracking 检查；到点 closure
- [ ] 事件累积后按 A11-10 五模式制四张表（State / Prediction / Intervention / Error），出具 **EGS Field Trial v0.1 Report**

---

## 附录 A：episode 纳入检查单（抄录进每条记录）

```
□ E1 有担保结构：可写出 "投入 X → 获得 Y" 或 "不投入/退出 → 承担代价"
□ E2 决策窗口 ≤90 天，有真实行为选择点
□ E3 outcome 可观察、可核实（行为痕迹）
□ E4 P/S/GFR/A/opportunity + 预测在行动前记录
□ 三自问：X/Y 是什么？同一 Y 有无替代路径？现实机会存在吗？
（任一不满足 → 不纳入；在候选排除区登记原因，不硬套）
```

## 附录 B：四张表（v0.1 Report 交付物）

| Table 1 — State Log | 现实状态与 EGS 判断的对应 |
|---|---|
| Table 2 — Prediction Log | Pred_intuition / Pred_GFR-only / Pred_full + 实际行为 + 命中 |
| Table 3 — Intervention Log | 建议、类别、采纳、行为变化、结果 |
| Table 4 — Error Log | 错误、定位（M/I/C/O/V/U）、修正、证据等级 |

每张表按 case_id 行排列；Report 结论区只写"模式出现与否 + 证据等级"，不写"EGS 被证明/被证伪"。

## 附录 C：现场术语 ↔ 上游冻结接口

| Field Trial 现场 | A10 问卷版 / CodeArt 接口 | 关系 |
|---|---|---|
| P[domain]（绑 X→Y，0–100） | P^d=f_d(Z_shared,Z_d) | 同构：域特异条件正向承诺信念 |
| S[domain]（绑退出代价） | S（负向威慑） | 同构：负向担保 |
| GFR（系统总体，先于 P） | GFR^global=f(Z_shared,Z_global) | 同构：禁止 P 汇总 |
| A（同 Y 的替代路径+担保来源） | A（替代担保供给）+ 担保来源分型 | 现场版加"真替代 vs 换说法"判别 |
| opportunity（0–3+证据） | Opportunity^d_t | 同构：识别"无机会≠无担保" |
| actual_behavior（动词表） | Y^P_d（领域持续投入，行为痕迹） | 同构：行为优先 |
| Pred_full vs Pred_intuition | Failure A（优于常识） | 现场版对照设计 |
| Pred_full vs Pred_GFR-only | Failure B（P 增量） | 现场版对照设计 |

---

*A11 定论：EGS-A 当前主线的裁判席从"心理测量实验室"搬到"真实决策现场"。成功不以量表达标计，而以五模式跨事件重复计；P 的命运不再由 CFA/ΔR² 独断，而由"P^d 是否在 GFR 看不到的地方指出了真实的行为分化"裁决。所有判断在行动前记录，所有修正只向前生效——这就是 Reality First。*

---

## 附录 D：执行级修订记录（Amendment Log · 只改执行纪律，不改理论对象）

### Amendment 01（2026-09-02 · FT02 启动前登记，来源=FT01 暴露）

**D1 — State Freeze（current_state 先于一切领域分析并封存）**

| 项目 | 内容 |
|---|---|
| 纪律 | `current_state` 必须在任何 P/S/A/opportunity 分析**之前**完成并封存；只记录"一个普通观察者在进行领域特异 EGS 分析之前已经可以知道的现实事实" |
| 禁止 | 将 P/S/A/opportunity 判断或任何 EGS 推理结论反向写入 current_state（防止 information leakage） |
| 顺序（硬性） | 现实原始事实 → current_state → [封存] → Pred_intuition → [封存] → GFR → Pred_GFR-only → [封存] → P/S/A/opportunity → Pred_full → Intervention |
| 新增字段 | `state_freeze_timestamp` / `state_freeze_status` / `state_source_refs` / `protocol_deviation` |
| 违规处置 | current_state 封存后被改变 → **不覆盖原记录**，新增 protocol deviation |

**D2 — P>GFR 只表述为 structural hypothesis（防 P 自证措辞）**

| 项目 | 内容 |
|---|---|
| 纪律 | 现场评分中出现领域层差异（如 P_career=74 > GFR=62）只能表述为 **structural hypothesis / 待验证差异**；**禁止**表述为"P 已证明提供 GFR 之外独立信息" |
| 升级门槛 | 只有后续 Prediction/Outcome 显示：加入 P 后出现 GFR-only 无法得到的**可重复准确预测** → 才进入 **P-increment evidence** |
| 禁止 | 把主观评分差异本身当作增量证据 |

**D3 — decision_mode 字段（防 intervention contamination）**

| 项目 | 内容 |
|---|---|
| 新增字段 | `decision_mode` ∈ {natural, EGS_informed} |
| natural | EGS 只观察和预测，不主动改变主体决策（**FT02 第一批优先 natural**） |
| EGS_informed | 主体明确阅读/接受 EGS 建议后再行动 |
| 禁止 | 为验证 EGS 故意让主体做出不同于原本决定的行动（实验对象被实验本身改变 → intervention contamination） |


