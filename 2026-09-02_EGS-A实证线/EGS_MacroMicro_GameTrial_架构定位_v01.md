# EGS Macro–Micro Game Trial — 架构定位说明 v0.1

> 日期：2026-09-02
> 状态：designed / dormant
> 目的：明确 Cognition Layer / Field Trial / EGS Mechanism Layer 三层关系，及 Macro–Micro Trial 与 Radar/Evolution Layer 的接口概念。

---

## 一、三个层次（禁止合并）

```text
┌─────────────────────────────────────────────────────────┐
│ KOS Cognition Layer（认知层）                            │
│   现实事实 -> 状态 -> 决策 -> 预测 -> 行为 -> 结果        │
│   -> 错误 -> 修正                                        │
│   本质：认知/验证基础设施                                  │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│ Field Trial Layer（现场实验层）                          │
│   现实中的 decision episode                              │
│   -> Prediction -> Tracking -> Closure -> Error         │
│   本质：微观观测单元（field_trial_case）                  │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│ EGS Mechanism Layer（机制层）                            │
│   Macro Guarantee State                                 │
│   -> Guarantee Structure                                │
│   -> Micro Response                                     │
│   -> Strategy Distribution Π                            │
│   -> Aggregate Behavior                                 │
│   -> Macro Feedback                                     │
│   -> Macro Guarantee State(t+1)                         │
│   本质：EGS 对"宏观担保结构如何产生微观策略，并经由       │
│         聚合行为反馈到宏观"的机制实验                      │
└─────────────────────────────────────────────────────────┘
```

- **Field Trial = 认知/验证基础设施**（记录单个决策如何发生）
- **EGS Macro–Micro Game Trial = 机制实验**（研究许多主体的决策如何由担保结构变化产生，并重新改变宏观系统）
- 禁止将两者合并为同一个对象。

## 二、Field Trial 与 Macro–Micro Trial 的分工

| 维度 | Field Trial（field_trial_case） | Macro–Micro Game Trial（egs_macro_micro_game_trial） |
|---|---|---|
| 研究问题 | 一个决策如何发生？ | 许多主体的决策如何由担保结构变化产生并反哺宏观？ |
| 观测单位 | 单个 decision episode | 主体群体的策略分布 Π |
| 预测对象 | 个体行为（方向+动作+时间窗） | 策略迁移（downward）+ 宏观后果（upward） |
| 记录物 | P/S/GFR/A/opportunity + 三预测 | Guarantee Structure + Π + 聚合行为 + 双向预测 |
| 错误分类 | M/I/C/O/V/U | M/I/C/O/V/U + A/F/H |
| 角色 | 微观观测/预测单元 | 机制 + 聚合 + 反馈单元 |
| 关系 | 被 Macro–Micro Trial 引用 | 引用多个 field_trial_case_id（不复制） |

**一句话**：
```text
Field Trial = micro observation / prediction
Macro–Micro Game Trial = mechanism + aggregation + feedback
```

## 三、在 KOS 全架构中的位置

```text
KOS Cognition Layer（认知层）
    |
    v
Field Trial（现场实验基础设施）
    |
    v
Field Trial Case（field_trial_case，微观决策记录）
    |
    v
真实主体决策与结果（FT01/FT02/...）
    |
    v
Macro–Micro Game Trial（本对象，机制实验）
    |
    v
Strategy Π + Aggregate Behavior
    |
    v
Macro Feedback
    |
    v
Radar / Evolution Layer（演化层——结构化输入）
```

### 为什么 Macro–Micro Trial 放认知层（Self）

- Field Trial Case 检验的是 EGS **认知模型**（判断准不准 -> model_revision）——用户 2026-09-02 拍板收录 Self 层
- Macro–Micro Game Trial 是 Field Trial 的**聚合与反馈单元**——同属"检验 EGS 认知模型"的家族，只是从单事件观测升级到群体机制
- 它不直接指导行动（那是 Position 层的事），而是产出**机制理解**（认知层产物）与**结构化信号**（喂给 Radar）

## 四、与 Radar / Evolution Layer 的接口（概念连接，不实现）

Macro–Micro Trial 的产物不是单纯 Report——它应该成为 Radar/Evolution Layer 的结构化输入：

```text
Macro state change detected（宏观状态变化被侦测）
    -> strategy distribution shift（策略分布迁移）
    -> potential regime transition（潜在制度转型）
    -> Radar alert（演化层预警）
```

概念接口（v0.1 只做概念连接，**不实现 Radar 规则**）：

| Macro–Micro 产物 | Radar/Evolution 用途 |
|---|---|
| Guarantee Structure 变化 | 体系卡状态迁移的触发器候选 |
| Strategy Π 迁移 | 演化剧本的微观证据（策略层变化先于制度层） |
| Aggregate Behavior | 宏观反馈信号的量化候选 |
| Macro Feedback | 状态机（战备等级）推进的候选判据 |

**候选案例池**（只作 candidate pool，不建立具体 case）：

```text
公务员担保结构 -> 青年职业策略（考公/市场/延迟就业/迁移/降欲望）-> 群体结构变化
房地产担保结构 -> 家庭策略（买房/租房/推迟婚育/储蓄）-> 消费与人口反馈
青年就业担保下降 -> 职业策略（转行/考公/创业/躺平/延迟婚育）-> 劳动力与消费反馈
AI 就业担保变化 -> 技术人员/非技术人员策略 -> 技能供给与企业招聘反馈
```

**FT01 就是公务员候选的现成素材**（P=74/S=66/GFR=62/Opportunity=2/A 替代不足）——但 FT01 是单个宏观 decision episode，不是 Macro–Micro Trial。未来启动 MMGT 公务员 Case 时，FT01 可作为 Macro State 与 Guarantee Structure 的输入参考，不可直接算作 Macro–Micro 证据。

## 五、与 EGS 引擎形态设计（2026-09-02）的关系

Macro–Micro Game Trial 是 EGS 引擎形态设计的**实证接口**：

| EGS 引擎形态（设计文档 11.x） | Macro–Micro Trial 对应 |
|---|---|
| Sensors（持续观测数据） | macro_state + field_trial_case_ids |
| State Estimation（当前关系状态） | Guarantee Structure 冻结 |
| Transition（状态转移概率） | Strategy Π + downward prediction |
| Forecast（下一阶段） | upward prediction |
| Feedback（Action -> World） | aggregate_behavior + macro_feedback |

Macro–Micro Trial 给引擎形态提供**可观察对象约束**：v0.1 不要求微分方程，只要求每个箭头在现实中有对应可观察物——这正是引擎从"漂亮设计"走向"可检验"的最小台阶。

## 六、启动条件（dormant 的触发条件，预注册）

以下条件**同时**出现时才启动具体 Macro–Micro Case：

1. 宏观状态变化（可冻结、可观察）
2. 多个相关主体/群体（存在异质性）
3. 可观察的策略重新配置（Π 有现实变化迹象）
4. 潜在反馈变量（聚合行为 -> 宏观的通道存在）

**当前不满足**：FT01/FT02 仍在 tracking；无多主体同窗宏观变化场景。故 v0.1 = designed / dormant。

---

*架构定位 v0.1：三层分离（Cognition / Field Trial / EGS Mechanism）、两单元连接（FT Case 微观 + MMGT 聚合）、一接口预留（Radar/Evolution）。未启动具体实验；未修改 EGS 理论定义；未修改 A11。*
