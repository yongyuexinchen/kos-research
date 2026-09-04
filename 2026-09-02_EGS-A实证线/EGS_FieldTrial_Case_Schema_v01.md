# EGS Field Trial Case — Schema 说明 v0.1

> 日期：2026-09-02
> 源协议：EGS-A A11 Field Trial Protocol v0.1（冻结，Reality First）
> **superseded**：本版被 v0.2 取代（2026-09-02，同步 A11 Amendment 01 与模板 v0.2）。
> 配套模板：`EGS_FieldTrial_Case_Template_v01.md`
> 定位：field_trial_case 对象的字段字典 + KOS 挂接论证。**不设计数据库，不扩展成复杂系统。**

---

## 一、对象定义

> **field_trial_case** = 一个真实 decision episode 的记录单元：主体面对明确的投入路径 X->Y 或退出代价结构，在现实时间窗内做出实际选择，结果可由可观察事实核实。记录的是"现实决策 -> 事前预测 -> 实际行为 -> 结果 -> 错误 -> 学习"的完整实验闭环。

可替换性（抽象原则）：

```text
理论 = EGS（可换其他机制）
主体 = 任意（个人/机构/国家——凡有决策者）
领域 = 任意（职业/教育/收入/关系/投资/迁移/创业…）
X/Y = 任意现实担保结构
```

---

## 二、字段字典

字段按记录时点分四段：HEAD（建卡）/ ENTRY（行动前，顺序固定，封存）/ TRACKING（窗口内）/ CLOSURE（窗口到点）。全部必填；无法填写的填 `NA` + `na_reason`（五类：无结构/无机会/无痕迹/窗口未完/记录失败）。

### HEAD

| field | type | required | stage | definition | constraint |
|---|---|---|---|---|---|
| case_id | text | yes | entry | 唯一编号 FT01-S01-D01（trial-subject-domain） | 全局唯一 |
| subject_id | text | yes | entry | 主体代号（脱敏，S01） | 禁真实姓名 |
| date | date | yes | entry | 记录日期 | — |
| domain | categorical | yes | entry | education/career/income/relationship/long-term investment/migration/entrepreneurship/other | 禁含糊标签（"生活"） |
| episode_type | categorical | yes | entry | commit/exit/switch/build_alt/enter/withhold | — |
| decision | text | yes | entry | 悬而未决的真实选择（一句话） | 非评价 |
| status | categorical | yes | all | draft/open/tracking/closure/reviewed/not_identified/protocol_deviation/abandoned | 状态机见模板第七节 |

### ENTRY（顺序固定：Pred_intuition -> GFR -> P/S/A/opportunity -> Pred_GFR-only -> Pred_full -> intervention）

| field | type | required | stage | definition | constraint |
|---|---|---|---|---|---|
| current_state | text | yes | entry | 现实状态事实（现状/约束/时间窗） | 禁评价性语言 |
| X | text | yes | entry | 投入路径：具体持续投入动作 | 动词化（投递/报名/备考/追加资金/投入时间） |
| Y | text | yes | entry | 兑现回报 | 可核实（offer/证书/录取/收入/阶段结果） |
| Pred_intuition | text | yes | entry（最先） | 直觉预测：方向+具体行为+时间窗 | 不调用 EGS 语言；最先记录 |
| confidence_intuition | 0-100 | yes | entry | 直觉预测置信 | 封存 |
| GFR | 0-100+text | yes | entry（先于 P） | 整体系统层担保判断 | 先于 P；独立判断；禁=P 均值；禁由 P/S/A 汇总；禁事后调整 |
| P | 0-100+text | yes | entry | 正向担保："投入 X -> 获得 Y"的可信度 | 绑定 domain+X+Y+理由+证据；禁抽象希望 |
| S | 0-100+text | yes | entry | 负向担保："不投入/退出 -> 现实代价" | 与 P 独立；P 低 ≠ S 高；记录代价内容 |
| A | list+text | yes | entry | 同一核心 Y 的替代担保来源 | 真替代=改变担保来源类型；同路径变体不算 |
| opportunity | ordinal 0-3+text | yes | entry | 现实机会暴露度 | 附客观证据；禁把无机会记为 P 低 |
| Pred_GFR-only | text | yes | entry | 只看 GFR+current_state 的预测 | 不看 P/S/A；方向+行为+窗口 |
| confidence_GFR | 0-100 | yes | entry | GFR-only 预测置信 | 封存 |
| Pred_full | text | yes | entry | 完整五量 EGS 预测 | 方向+具体可观察行为+时间窗；封存禁改 |
| confidence_full | 0-100 | yes | entry | full 预测置信 | 封存 |
| intervention | text+categorical | optional | entry→tracking | EGS 建议（advice/rationale/category） | 可选环节；Failure C 触发后自动退回观察模式 |
| adoption_expected | categorical | optional | entry | 事前预期采纳程度 | full/partial/refused |

### TRACKING

| field | type | required | stage | definition | constraint |
|---|---|---|---|---|---|
| actual_behavior | text（动词表） | yes | tracking | 真实行为：开始/停止/投入/报名/申请/支付/切换/建替代路径 | 禁意图/倾向/"感觉更有动力" |
| adoption | categorical+text | optional | tracking | intervention 实际采纳 + 真实原因 | 原因不评判（成本/恐惧/时间） |
| behavior_deviation | text | optional | tracking | 与 Pred_full 的偏离点 | — |
| protocol_deviation | text | optional | tracking | 执行偏离协议记录 | 只记 deviation，不偷偷改协议 |

### CLOSURE

| field | type | required | stage | definition | constraint |
|---|---|---|---|---|---|
| outcome | text+categorical | yes | closure | 与 Y 对应的可核实结果 | 获得/未获得/部分获得/窗口未完 |
| prediction_error | categorical | yes | closure | correct/partial/wrong | partial 需记录偏离点 |
| reason_for_error | categorical+text | yes | closure | M/I/C/O/V/U + 定位 | 禁空泛归因（"模型不够成熟"） |
| opportunity_check | categorical | yes | closure | 偏离是否因机会不足/误估？是→O | Opportunity check 前置 |
| closure_date | date | yes | closure | 结果核实日期 | — |
| episode_verdict | categorical | yes | closure | Success/Failure/Not Identified | NI ≠ failure |
| evidence_level | categorical | yes | closure | E1/E2/E3/NI | 防小样本吹模式 |
| model_revision | text | optional | closure | rev-YYYYMMDD-N 规则修正 | 只影响未来；禁解释已发生结果 |

---

## 三、三预测并列设计（本模板核心）

```text
Pred_intuition   常识/直觉（最先）        Pred_full vs Pred_intuition  -> 测 EGS 是否优于普通判断（Failure A）
Pred_GFR-only    只看 GFR                Pred_full vs Pred_GFR-only   -> 测 P/S/A/opportunity 是否提供增量（Failure B）
Pred_full        完整五量（主预测）       一致本身是发现（EGS 与直觉无差异 = Failure A 候选证据）
```

全部行动前完成、结构化到可观察行为、带时间窗、带 confidence、封存禁改。

---

## 四、错误分类与前置检查

| code | 类型 | 判定问题 |
|---|---|---|
| M | measurement error | 现场记录本身记错（与主体真实判断不符） |
| I | inference error | 判断对，从判断推行为预测的推理错 |
| C | causal/mechanism error | 对"担保结构如何驱动行为"的机制理解错 |
| O | opportunity error | 机会暴露估计错 |
| V | intervention error | 建议误导或执行走样 |
| U | unknown | 以上皆否（连续 U -> Failure D） |

**Opportunity check 前置**：结果失败 -> 先查机会是否真的存在 -> 再讨论 P/GFR/机制错误（防止"没机会"被误判成"担保判断错"）。

---

## 五、与现有 KOS 知识对象的关系（挂接论证）

### 候选：Experiment Card（Position/templates/experiment.md，v0.2，KOS 一级卡型）

**结论：field_trial_case 不能直接复用 Experiment Card——旧对象无法承载，但两者是同一家族，需要平行关系而非取代。**

| 维度 | Experiment Card（现有） | field_trial_case（本模板） |
|---|---|---|
| 主实验单位 | 作品/项目（视频、推广、投资标的） | **decision episode（现实决策事件）** |
| 核心问题 | 这个行动的结果如何修正我的认知模型？ | EGS 判断是否在真实决策中提供有用信息？ |
| 预测结构 | 单一预测（views/followers 数值 + prior） | **三预测并列**（intuition / GFR-only / full）——对照设计 |
| 理论变量 | 假设（statement）+ 自变量/控制变量 | **P/S/GFR/A/opportunity 五量**（现场 EGS 语义，顺序纪律） |
| 现实反馈 | metrics（播放/完播/互动） | **actual_behavior（动词表）→ outcome（可核实事实）** |
| 错误定位 | Gap 四层（执行/分发/假设/基石） | **M/I/C/O/V/U 六类 + Opportunity check 前置** |
| 修正机制 | 贝叶斯 update（prior→posterior） | model_revision（rev-日期-N，只影响未来）+ 跨事件模式 |
| 状态 | proposed/running/completed/abandoned | draft/open/tracking/closure/reviewed + NI/deviation |
| 证据等级 | 无显式 | E1/E2/E3/NI（防小样本吹模式） |
| 主体假设 | "我"做实验（研究者=主体） | 主体=任意决策者（33/志愿者/未来机构）——可纵向+跨主体 |

**为什么旧对象无法承载（三点硬差异）**：
1. **三预测并列是结构性新增**——Experiment Card 的 prediction 只有一个 expected 值，无法表达"EGS vs 常识 vs GFR-only"的对照设计；这是 A11 的 Failure A/B 判定核心，塞进 experiment.md 会破坏其 YAML 结构
2. **P/S/GFR/A/opportunity 五量是 EGS 专属理论变量**——Experiment Card 的 hypothesis/variables 是通用实验设计语言（标题/时长/视觉），没有"担保结构"语义，也没有 GFR 先于 P 的记录顺序约束
3. **错误分类法系不同**——Experiment 用 Gap 失效链（执行/分发/假设/基石，面向作品制作链）；field_trial 用 M/I/C/O/V/U（面向 EGS 判断链，含 measurement 与 opportunity 两类 Experiment 没有的错误）

### 挂接建议（层级）

```text
Experiment Card（作品/项目实验——已有）
   └── field_trial_case（现实决策事件实验——新增，本模板）
          ├── State（P/S/GFR/A/opportunity + current_state）
          ├── Prediction（三预测并列）
          ├── Intervention（可选建议）
          └── Error（M/I/C/O/V/U + revision）
```

- 物理位置：`Position/Experiments/`（与 Experiment Card 同目录，同一现实反馈家族）或独立 `Position/FieldTrials/`（待用户拍板）
- 关系类型：field_trial_case **updates** EGS 模型规则（revision）、**challenges** 理论对象（跨事件模式 Failure A-D）、与 Experiment Card **parallel**（不同实验单位，不互相取代）
- 与 A9-A11 上游：field_trial_case 是 A11 的**执行记录层**；A11 协议 = 规则/判定/Stop Rules（冻结不改），本模板 = 数据捕获格式（可因模板化需要微调，但不改理论裁决）
- 模板正式源：待用户拍板后进 `Maintain/layers/Position/templates/`（与 experiment.md 并列），当前版本留在 A11 协议同目录便于对照

---

## 六、来源标注（哪些来自 A11 冻结协议，哪些为模板化新增）

### 来自 A11（冻结协议继承，未改裁决）

- decision episode 定义与 E1-E4/X1-X4 纳入排除 + 三自问
- Field Log 数据字典字段（case_id/subject_id/date/domain/current_state/P/S/GFR/A/opportunity/prediction/intervention/actual_behavior/outcome/prediction_error/reason_for_error/model_revision/confidence）
- entry 记录顺序纪律（Pred_intuition 最先 -> GFR 先于 P -> P/S/A/opportunity -> 结构化预测 -> intervention）
- P/S/GFR/A/opportunity 现场语义（绑定 X->Y、S 独立、GFR 禁汇总、真替代判别、opportunity 0-3+证据）
- 三预测并列（Pred_intuition/Pred_GFR-only/Pred_full）+ 封存纪律
- Error Log M/I/C/O/V/U + Opportunity check 前置 + closure 强制写作
- model_revision rev-YYYYMMDD-N 纪律（只影响未来）
- 证据等级 E1/E2/E3/NI + 单次不确认/不证伪 + 五模式（S1/P1/P2/I3/L4）
- Stop Rules Failure A-D

### 模板化新增（工程字段，为通用化/机器可处理）

- **X、Y 独立成字段**（A11 嵌在 P 的表述里；独立后 A 的"同一 Y"判定与跨 Case 对照可直接引用）
- **confidence_intuition / confidence_GFR / confidence_full 三拆**（A11 只有单条 confidence；A11-7 实际要求每条预测给置信，本模板显式化）
- **decision 字段**（一句话陈述悬而未决的选择，独立于 current_state）
- **episode_verdict 与 status 分离**（A11 用 Success/Failure/Not Identified 作 episode 判定；模板新增 Case 生命周期状态机 draft/open/tracking/closure/reviewed + not_identified/protocol_deviation/abandoned——verdict 是结果判定，status 是记录进度，两者不混）
- **四象限对照段**（State/Prediction/Intervention/Outcome 显式分离，防"预测=建议=结果"混用）
- **na_reason 五类**（A11 字段表提 NA+原因，模板化为枚举：无结构/无机会/无痕迹/窗口未完/记录失败）
- **adoption_expected**（intervention 采纳的事前预期，与事后 adoption 对照）

---

*Schema v0.1 随 A11 冻结协议生成；不制作数据库设计；如 A11 执行中出现字段歧义，走 protocol deviation 记录，不改本 Schema（A11 角色纪律：执行者不得改理论对象/判定规则）。*
