# EGS Field Trial Case — Schema 说明 v0.2

> 日期：2026-09-02
> 源协议：EGS-A A11 Field Trial Protocol v0.1 + Amendment 01（D1 State Freeze / D2 structural hypothesis / D3 decision_mode）
> 配套模板：`EGS_FieldTrial_Case_Template_v02.md`（v0.1 已 superseded）
> 定位：field_trial_case 对象的字段字典 + KOS 挂接论证。**不设计数据库，不扩展成复杂系统。**
> **层归属修正（2026-09-02 用户拍板）**：认知层（Self），非 Position——Field Trial 检验的是 EGS 认知模型本身（判断准不准 -> model_revision），与 Experiment Card（Position，测作品假设）不同对象。正式源：`Maintain/layers/Self/templates/field_trial_case.md`
> **v0.2 变更**：同步 Amendment 01——① D1 State Freeze 三段封存结构（current_state/Pred_intuition/Pred_GFR-only 各自先封存，防 information leakage 与对照预测污染）② 新增 state_freeze_* / decision_mode 字段 ③ D2 表述纪律入字典 ④ closure 增加三预测对照矩阵 ⑤ protocol_deviation 编号化 PD-<case>-N。

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

字段按记录时点分四段：HEAD（建卡）/ ENTRY（行动前，D1 顺序硬性，逐段封存）/ TRACKING（窗口内）/ CLOSURE（窗口到点）。全部必填；无法填写的填 `NA` + `na_reason`（五类：无结构/无机会/无痕迹/窗口未完/记录失败）。

### HEAD

| field | type | required | stage | definition | constraint |
|---|---|---|---|---|---|
| case_id | text | yes | entry | 唯一编号 FT01-S01-D01（trial-subject-domain） | 全局唯一 |
| subject_id | text | yes | entry | 主体代号（脱敏，S01） | 禁真实姓名 |
| date | date | yes | entry | 记录日期 | — |
| domain | categorical | yes | entry | education/career/income/relationship/long-term investment/migration/entrepreneurship/other | 禁含糊标签（"生活"） |
| episode_type | categorical | yes | entry | commit/exit/switch/build_alt/enter/withhold | — |
| decision | text | yes | entry | 悬而未决的真实选择（一句话） | 非评价 |
| decision_mode | categorical | yes | entry | natural（EGS 只观察预测）/ EGS_informed（主体读建议后行动） | D3：FT02 第一批优先 natural；禁为验证 EGS 故意改变主体决策（intervention contamination） |
| status | categorical | yes | all | draft/open/tracking/closure/reviewed/not_identified/protocol_deviation/abandoned | 状态机见模板第八节 |

### ENTRY（D1 顺序：current_state[冻结] -> Pred_intuition[冻结] -> GFR -> Pred_GFR-only[冻结] -> P/S/A/opportunity[冻结] -> Pred_full -> intervention）

| field | type | required | stage | definition | constraint |
|---|---|---|---|---|---|
| state_freeze_timestamp | datetime | yes | entry（第 0 段） | current_state 封存时间 | D1 |
| state_freeze_status | categorical | yes | entry（第 0 段） | 已封存 / 变动（-> protocol_deviation） | D1：封存后不覆盖原记录 |
| state_source_refs | text | yes | entry（第 0 段） | current_state 信息来源（问答/档案/会话） | D1：可追溯 |
| current_state | text | yes | entry（第 0 段） | 现实状态事实（现状/约束/时间窗） | D1：只记"普通观察者 EGS 分析前已知事实"；禁反灌 P/S/A/opportunity 判断（information leakage） |
| X | text | yes | entry（第 0 段） | 投入路径：具体持续投入动作 | 动词化（投递/报名/备考/追加资金/投入时间） |
| Y | text | yes | entry（第 0 段） | 兑现回报 | 可核实（offer/证书/录取/收入/阶段结果） |
| Pred_intuition | text | yes | entry（第 1 段） | 直觉预测：方向+具体行为+时间窗 | 不调用 EGS 语言；最先记录；封存 |
| confidence_intuition | 0-100 | yes | entry（第 1 段） | 直觉预测置信 | 未提供数值记 NA（FT02 先例：PD-FT02-1，不补造） |
| GFR | 0-100+text | yes | entry（第 2 段） | 整体系统层担保判断 | 先于 P；独立判断；禁=P 均值；禁由 P/S/A 汇总；禁事后调整 |
| Pred_GFR-only | text | yes | entry（第 2 段） | 只看 GFR+current_state 的预测 | **不看 P/S/A；P/S/A 填写前先封存**（D1 修正 v0.1 顺序漏洞） |
| confidence_GFR | 0-100 | yes | entry（第 2 段） | GFR-only 预测置信 | 封存 |
| P | 0-100+text | yes | entry（第 3 段） | 正向担保："投入 X -> 获得 Y"的可信度 | 绑定 domain+X+Y+理由+证据；禁抽象希望 |
| S | 0-100+text | yes | entry（第 3 段） | 负向担保："不投入/退出 -> 现实代价" | 与 P 独立；P 低 ≠ S 高；记录代价内容 |
| A | list+text | yes | entry（第 3 段） | 同一核心 Y 的替代担保来源 | 真替代=改变担保来源类型；同路径变体不算 |
| opportunity | ordinal 0-3+text | yes | entry（第 3 段） | 现实机会暴露度 | 附客观证据；禁把无机会记为 P 低 |
| Pred_full | text | yes | entry（第 4 段） | 完整五量 EGS 预测 | 方向+具体可观察行为+时间窗；封存禁改 |
| confidence_full | 0-100 | yes | entry（第 4 段） | full 预测置信 | 封存 |
| intervention | text+categorical | conditional | entry（第 4 段） | EGS 建议（advice/rationale/category） | **仅 decision_mode=EGS_informed 时填**；natural 填 None（D3） |
| adoption_expected | categorical | conditional | entry（第 4 段） | 事前预期采纳程度 | full/partial/refused |

### TRACKING

| field | type | required | stage | definition | constraint |
|---|---|---|---|---|---|
| actual_behavior | text（动词表） | yes | tracking | 真实行为：开始/停止/投入/报名/申请/支付/切换/建替代路径 | 禁意图/倾向/"感觉更有动力" |
| adoption | categorical+text | conditional | tracking | intervention 实际采纳 + 真实原因 | 仅 EGS_informed；原因不评判 |
| behavior_deviation | text | optional | tracking | 与 Pred_full 的偏离点 | — |
| protocol_deviation | text | optional | tracking | 执行偏离协议记录 | **编号 PD-<case>-N**；只记 deviation 不偷偷改协议（D1 违规处置） |

### CLOSURE

| field | type | required | stage | definition | constraint |
|---|---|---|---|---|---|
| closure_matrix | table | yes | closure | 三预测分别 vs actual_behavior（命中/未命中/无法判定） | 不得只判 Pred_full（FT02 执行反馈） |
| outcome | text+categorical | yes | closure | 与 Y 对应的可核实结果 | hit（达成 Y）/partial（相近非目标 Y）/wrong/NI |
| prediction_error | categorical | yes | closure | correct/partial/wrong | partial 需记录偏离点 |
| reason_for_error | categorical+text | yes | closure | M/I/C/O/V/U + 定位 | 禁空泛归因 |
| opportunity_check | categorical | yes | closure | 偏离是否因机会不足/误估？是→O | Opportunity check 前置 |
| closure_date | date | yes | closure | 结果核实日期 | — |
| episode_verdict | categorical | yes | closure | Success/Failure/Not Identified | NI ≠ failure |
| evidence_level | categorical | yes | closure | E1/E2/E3/NI | 防小样本吹模式 |
| model_revision | text | optional | closure | rev-YYYYMMDD-N 规则修正 | 只影响未来；禁解释已发生结果 |
| divergence_report | text | optional | closure | 三预测分叉报告（方向一致/分叉点/增量位置） | 如实记录；一致本身是发现 |

---

## 三、三预测并列设计（本模板核心）

```text
Pred_intuition   常识/直觉（最先）        Pred_full vs Pred_intuition  -> 测 EGS 是否优于普通判断（Failure A）
Pred_GFR-only    只看 GFR                Pred_full vs Pred_GFR-only   -> 测 P/S/A/opportunity 是否提供增量（Failure B）
Pred_full        完整五量（主预测）       一致本身是发现（EGS 与直觉无差异 = Failure A 候选证据）
```

全部行动前完成、结构化到可观察行为、带时间窗、带 confidence、封存禁改。

**D1 修正（v0.2 关键）**：Pred_GFR-only 必须在 P/S/A 填写**之前**封存——若先填 P/S/A，领域信息会污染"只看 GFR"的对照预测，使 Failure B 对照失效（v0.1 顺序漏洞，FT01 执行暴露，Amendment 01 修复）。

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

**D2 表述纪律**：P > GFR 的现场评分差异 = structural hypothesis（待验证），不是 P-increment evidence；只有跨事件可重复的准确预测才能升级为增量证据。

---

## 五、与现有 KOS 知识对象的关系（挂接论证）

### 候选：Experiment Card（Position/templates/experiment.md，v0.2，KOS 一级卡型）

**结论：field_trial_case 不能直接复用 Experiment Card——旧对象无法承载，但两者是同一家族，需要平行关系而非取代。**（论证同 v0.1，未因 Amendment 改变——Amendment 只改执行纪律，不改对象关系。）

| 维度 | Experiment Card（现有） | field_trial_case（本模板） |
|---|---|---|
| 主实验单位 | 作品/项目（视频、推广、投资标的） | **decision episode（现实决策事件）** |
| 核心问题 | 这个行动的结果如何修正我的认知模型？ | EGS 判断是否在真实决策中提供有用信息？ |
| 预测结构 | 单一预测（views/followers 数值 + prior） | **三预测并列**（intuition / GFR-only / full）——对照设计 |
| 理论变量 | 假设（statement）+ 自变量/控制变量 | **P/S/GFR/A/opportunity 五量**（现场 EGS 语义，D1 顺序纪律） |
| 现实反馈 | metrics（播放/完播/互动） | **actual_behavior（动词表）→ outcome（可核实事实）** |
| 错误定位 | Gap 四层（执行/分发/假设/基石） | **M/I/C/O/V/U 六类 + Opportunity check 前置** |
| 修正机制 | 贝叶斯 update（prior→posterior） | model_revision（rev-日期-N，只影响未来）+ 跨事件模式 |
| 状态 | proposed/running/completed/abandoned | draft/open/tracking/closure/reviewed + NI/deviation |
| 证据等级 | 无显式 | E1/E2/E3/NI（防小样本吹模式） |
| 主体假设 | "我"做实验（研究者=主体） | 主体=任意决策者（33/志愿者/未来机构）——可纵向+跨主体 |
| 干预纪律 | 无显式干预模式 | **decision_mode（natural/EGS_informed）——防 intervention contamination** |

**为什么旧对象无法承载（三点硬差异，v0.1 不变）**：
1. **三预测并列是结构性新增**——Experiment Card 的 prediction 只有一个 expected 值，无法表达"EGS vs 常识 vs GFR-only"的对照设计；这是 A11 的 Failure A/B 判定核心，塞进 experiment.md 会破坏其 YAML 结构
2. **P/S/GFR/A/opportunity 五量是 EGS 专属理论变量**——Experiment Card 的 hypothesis/variables 是通用实验设计语言（标题/时长/视觉），没有"担保结构"语义，也没有 GFR 先于 P 的记录顺序约束
3. **错误分类法系不同**——Experiment 用 Gap 失效链（执行/分发/假设/基石，面向作品制作链）；field_trial 用 M/I/C/O/V/U（面向 EGS 判断链，含 measurement 与 opportunity 两类 Experiment 没有的错误）

### 挂接建议（层级）

```text
Experiment Card（作品/项目实验——Position 层，已有）
   └── field_trial_case（现实决策事件实验——Self 认知层，新增，本模板）
          ├── State（P/S/GFR/A/opportunity + current_state）
          ├── Prediction（三预测并列）
          ├── Intervention（可选建议，受 decision_mode 约束）
          └── Error（M/I/C/O/V/U + revision）
```

- 物理位置：`Self/`（认知层，用户 2026-09-02 拍板）；Case 落盘目录建议 `Self/FieldTrials/`（待首 Case 实际落位确认）；模板正式源 `Maintain/layers/Self/templates/field_trial_case.md`
- 关系类型：field_trial_case **updates** EGS 模型规则（revision）、**challenges** 理论对象（跨事件模式 Failure A-D）、与 Experiment Card **parallel**（不同实验单位、不同层：Experiment 在 Position 测作品假设，Field Trial 在 Self 测认知模型——不互相取代）
- 与 A9-A11 上游：field_trial_case 是 A11 的**执行记录层**；A11 协议（含 Amendment Log）= 规则/判定/Stop Rules（冻结不改），本模板 = 数据捕获格式（可因执行反馈迭代，不改理论裁决）
- 模板正式源：待用户拍板后进 `Maintain/layers/Position/templates/`（与 experiment.md 并列），当前版本留在 A11 协议同目录便于对照

---

## 六、来源标注（哪些来自 A11 冻结协议 + Amendment 01，哪些为模板化新增）

### 来自 A11 冻结协议（未改裁决）

- decision episode 定义与 E1-E4/X1-X4 纳入排除 + 三自问
- Field Log 数据字典字段（case_id/subject_id/date/domain/current_state/P/S/GFR/A/opportunity/prediction/intervention/actual_behavior/outcome/prediction_error/reason_for_error/model_revision/confidence）
- P/S/GFR/A/opportunity 现场语义（绑定 X->Y、S 独立、GFR 禁汇总、真替代判别、opportunity 0-3+证据）
- 三预测并列（Pred_intuition/Pred_GFR-only/Pred_full）+ 封存纪律
- Error Log M/I/C/O/V/U + Opportunity check 前置 + closure 强制写作
- model_revision rev-YYYYMMDD-N 纪律（只影响未来）
- 证据等级 E1/E2/E3/NI + 单次不确认/不证伪 + 五模式（S1/P1/P2/I3/L4）
- Stop Rules Failure A-D

### 来自 A11 Amendment 01（2026-09-02，FT01 暴露，FT02 启动前登记——执行纪律层）

- **D1 State Freeze**：current_state 先于一切领域分析并封存（防 information leakage）；顺序硬性化为四段冻结（current_state / Pred_intuition / Pred_GFR-only / P-S-A-opportunity 各自封存）；新增 state_freeze_timestamp / state_freeze_status / state_source_refs；违规不覆盖、记 protocol deviation
- **D2**：P>GFR 只表述为 structural hypothesis（防 P 自证措辞）；升级门槛 = 可重复准确预测
- **D3**：decision_mode 字段（natural / EGS_informed）；FT02 第一批优先 natural；禁 intervention contamination

### 模板化新增（工程字段，为通用化/机器可处理，v0.1 已有）

- **X、Y 独立成字段**（A11 嵌在 P 的表述里）
- **confidence_intuition / confidence_GFR / confidence_full 三拆**
- **decision 字段**（独立于 current_state 的决策陈述）
- **episode_verdict 与 status 分离**（verdict=结果判定，status=记录进度）
- **四象限对照段**（State/Prediction/Intervention/Outcome 显式分离）
- **na_reason 五类**（无结构/无机会/无痕迹/窗口未完/记录失败）
- **adoption_expected**（采纳的事前预期）
- **Closure 对照矩阵**（三预测分别 vs actual_behavior，不只判 full——FT02 执行结构反馈）
- **三预测分叉报告**（divergence_report，如实记录一致/分叉——FT02 §10 先例）
- **protocol_deviation 编号化**（PD-<case>-N——FT02 PD-FT02-1/2 先例）
- **outcome 判定 hit/partial/wrong/NI**（比 A11 的"获得/未获得/部分获得/窗口未完"更贴 Y 达成判定——FT02 §8 先例）

---

*Schema v0.2 随 A11 Amendment 01 与 FT01/FT02 执行反馈迭代；不制作数据库设计；如执行中出现新字段歧义，走 protocol deviation 记录，不改本 Schema（A11 角色纪律：执行者不得改理论对象/判定规则）。*
