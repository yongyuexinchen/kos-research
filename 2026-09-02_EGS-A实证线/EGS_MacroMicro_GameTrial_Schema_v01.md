# EGS Macro–Micro Game Trial — Schema / Data Dictionary v0.1

> 日期：2026-09-02
> 源：EGS Macro–Micro Game Trial 模板 v0.1（designed/dormant）；A11 Field Trial Protocol v0.1 + Amendment 01
> 定位：egs_macro_micro_game_trial 对象字段字典。**轻量设计，不扩展成复杂系统。**
> 复用原则：Field Trial Case 字段（P/S/GFR/A/opportunity 等）不在此重复定义——Macro–Micro Trial 通过 field_trial_case_id 引用，本 schema 只定义聚合层字段 + EGS 专属机制字段。

---

## 一、对象定义

> **egs_macro_micro_game_trial** = EGS 对"宏观担保结构 -> 微观策略分布 -> 聚合行为 -> 宏观反馈"的机制实验单元。研究主体群体面对共同/不同担保结构时策略分布 Π 的变化，及其对宏观系统的反馈。**不是**单个 decision episode 的记录（那是 Field Trial Case）。

## 二、字段字典

全部字段按记录时点分四段：HEAD / FREEZE（宏观冻结）/ OBSERVE（微观接入+聚合）/ CLOSURE（判定）。P/S/GFR/A/opportunity 若某个实验无合法测量：填 `NA` + reason，**不制造伪数据**。

### HEAD（建 Trial）

| field | type | required | stage | definition | constraint |
|---|---|---|---|---|---|
| trial_id | text | yes | head | 唯一编号 MMGT-001 | 全局唯一 |
| macro_state_id | text | yes | head | 关联的宏观状态记录 | 指向 Macro State 冻结 |
| time | date/period | yes | head | 观察期（起-止） | — |
| domain | categorical | yes | head | 领域：career/education/housing/family/income/migration/AI 等 | 禁含糊标签 |
| status | categorical | yes | all | designed/open/tracking/closure/reviewed/not_identified/abandoned | 状态机见模板 |
| activity | categorical | yes | all | dormant/active | v0.1 全体 dormant |
| source_refs | text | yes | head | 数据来源（报告/FT cases/官方统计/调研） | 可追溯 |

### FREEZE（宏观冻结——继承 A11 Amendment 01 D1 State Freeze）

| field | type | required | stage | definition | constraint |
|---|---|---|---|---|---|
| freeze_timestamp | datetime | yes | freeze | 宏观状态冻结时间 | D1 |
| freeze_status | categorical | yes | freeze | 已封存/变动（记 deviation） | D1：不覆盖 |
| macro_state | object | yes | freeze | 宏观状态：economic conditions/employment/fiscal capacity/institutional changes/demographic trends/market conditions/guarantee institutions | **只记现实事实，禁写结论**（结论进 mechanism/prediction） |

### MECHANISM（担保结构——EGS 核心层）

| field | type | required | stage | definition | constraint |
|---|---|---|---|---|---|
| guarantee_structure | object | yes | freeze | positive promise/negative sanction/provider/capacity/domain/time horizon/alternative supply | 能答"谁向谁承诺什么/投入得到什么/退出承担什么/来源是什么/有无替代" |

### SUBJECTS（主体/群体）

| field | type | required | stage | definition | constraint |
|---|---|---|---|---|---|
| subject_group | list | yes | freeze | 主体类别：individual/household/cohort/occupation/age group/region/social group | 保留类别，禁同质化 |
| subject_exposure | object | optional | freeze | 各群体的担保暴露度（对 Guarantee Structure 的接触面） | 异质性如实记录 |
| heterogeneity | object | optional | freeze | resources/constraints/career stage/education/location/income/exposure | 禁把"年轻人"当同质主体 |

### OBSERVE（微观接入 + 聚合）

| field | type | required | stage | definition | constraint |
|---|---|---|---|---|---|
| field_trial_case_ids | list | conditional | observe | 引用的 Field Trial Case（FT01/FT02/...） | **引用不复制** |
| P | 0-100 | optional | observe | 领域正向担保（若该场景有合法测量） | 无合法测量填 NA+reason |
| S | 0-100 | optional | observe | 负向担保（退出代价） | 同上 |
| GFR | 0-100 | optional | observe | 系统层担保（先于 P） | 同上 |
| A | list | optional | observe | 替代担保供给 | 同上 |
| opportunity | 0-3 | optional | observe | 机会暴露 | 同上 |
| strategy_vector | list | yes | observe | 观察到的个体/群体策略（continue/exit/switch/seek_alternative/delay/reduce_desire/increase_saving/migrate/build_new_guarantee/other） | 类别围绕"如何重配时间/资本/劳动/关系/欲望" |
| strategy_distribution | object | yes | observe | **Π**：各类策略在群体中的分布 | 见"策略谱"节 |

### AGGREGATE（聚合行为 + 宏观反馈）

| field | type | required | stage | definition | constraint |
|---|---|---|---|---|---|
| aggregate_behavior | object | yes | observe | 微观聚合后的可观察宏观行为：household formation/fertility/consumption/labor participation/migration/capital allocation/investment/entrepreneurship/demand | **必须经 aggregation 层**，禁单主体直接推导 |
| macro_feedback | object | optional | observe | 聚合行为对宏观系统的反馈：institutional pressure/fiscal burden/demand change 等 | 反馈方向明确，禁模糊"系统会变" |

### PREDICTION（双向预测——封存）

| field | type | required | stage | definition | constraint |
|---|---|---|---|---|---|
| downward_prediction | text | yes | freeze/observe | 宏观担保变化 -> 预期策略迁移（如：某领域 P 下降、替代上升 -> 更多主体退出并寻替代） | 行动前封存，禁事后改 |
| upward_prediction | text | yes | observe | 策略聚合 -> 预期宏观后果（如：大量主体退出某制度化路径 -> 需求/人口/财政压力变化） | 两个方向分别记录，禁用一个模糊"系统会变化"代替 |

### CLOSURE（结果判定）

| field | type | required | stage | definition | constraint |
|---|---|---|---|---|---|
| actual_outcome | object | yes | closure | 现实结果（与 prediction 对应） | 可核实 |
| error | categorical | yes | closure | correct/partial/wrong | 对/错都填 |
| error_taxonomy | categorical | yes | closure | M/I/C/O/V/U + A/F/H（见下） | 落到具体类型 |
| revision | text | optional | closure | rev-YYYYMMDD-N | 只影响未来 Trial |
| evidence_level | categorical | yes | closure | E1/E2/E3/NI | 防小样本吹模式 |
| mechanism_support | categorical | optional | closure | MS/MP/MF 各自 supported/not supported | **模式支持 ≠ 理论证明** |

---

## 三、Strategy Π 必须保持"谱"而非互斥标签

推荐现场结构：

```text
Π_t = {
  continue: x,
  exit: x,
  switch: x,
  alternative: x,
  delay: x,
  desire_reduction: x,
  rebuild: x
}
```

权重**不一定要求加总 100%**（除非实验设计明确采用概率分布）。第一版允许：

```text
count / share / ordinal strength / activation score
```

具体取哪一种，根据真实数据决定。模板层只规定：**Π 必须表达群体策略结构，而不是单一分类标签。**

---

## 四、错误分类（Field Trial 六类 + Macro–Micro 三类）

Field Trial 继承：M measurement / I inference / C causal-mechanism / O opportunity / V intervention / U unknown

Macro–Micro 新增：

| code | 类型 | 定义 |
|---|---|---|
| **A** | aggregation error | 个体行为记录正确，但从个体到群体的聚合推断错误 |
| **F** | feedback error | 微观行为确实发生，但判断其如何影响宏观系统错误 |
| **H** | heterogeneity error | 错误地把异质主体当成同质群体 |

**Opportunity check 前置**（继承 A11）：判错前先查机会是否真实存在。

---

## 五、与现有对象的关系（复用声明）

| 现有对象 | 关系 | 说明 |
|---|---|---|
| Experiment Card（Position/experiment.md） | **不复用** | 测作品假设（视频/项目），与 EGS 机制实验不同对象 |
| field_trial_case（Self/templates/，v0.2） | **复用为微观观测单元** | Macro–Micro Trial 通过 field_trial_case_id 引用，不复制 |
| A11 Field Trial Protocol | **上游规则** | State Freeze（D1）/ P>GFR 表述纪律（D2）/ decision_mode（D3）全继承 |

**新增对象**：egs_macro_micro_game_trial（本 schema）——只增加聚合层字段 + EGS 机制字段（guarantee_structure / strategy_distribution / downward+upward prediction / A-F-H error），不重复 Field Trial 字段。

---

*Schema v0.1 = designed / dormant。不启动具体 Case；不改 EGS 理论定义；不改 A11；不把 FT01/FT02 当前结果解释成 Macro–Micro 证据。*
