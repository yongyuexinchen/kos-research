---
type: template
name: egs_macro_micro_game_trial（EGS 宏微博弈实验模板 v0.1——designed/dormant）
source: EGS-A A11 Field Trial Protocol v0.1 + Amendment 01；EGS 引擎形态设计（2026-09-02）
layer: self（认知层——机制实验，聚合 Field Trial Cases；详见架构定位说明）
status: designed
activity: dormant
updated: 2026-09-02
note: 研究"宏观担保结构 -> 微观策略分布 -> 聚合行为 -> 宏观反馈"的机制实验模板。复制即建 Case。不启动具体实验。
---

# EGS Macro–Micro Game Trial 模板 v0.1

> 用法：未来出现"宏观状态变化 + 多个相关主体 + 可观察策略重新配置 + 潜在反馈变量"时，复制本文件建立具体 Case。
> 最终状态：**designed / dormant**——模板就绪，不启动。
> 与 Field Trial 的区别：Field Trial 记录"一个决策如何发生"（微观观测/预测）；Macro–Micro Game Trial 研究"许多主体的决策如何由担保结构变化产生，并重新改变宏观系统"（机制 + 聚合 + 反馈）。两者连接，不混为一谈。

---

## 〇、核心研究问题（固定）

> **当宏观担保结构发生变化时，不同主体/群体是否会产生可观察的策略重新配置，并且这些聚合策略变化是否进一步反馈到宏观担保结构？**

本对象**不是**研究"一个人下一步会做什么"（那是 Field Trial / decision episode）；研究**主体群体面对共同或不同的担保结构时，策略分布 Π 如何变化**。

## 一、最小动力闭环（v0.1 不要求微分方程）

```text
Macro State_t
      |
      v
Guarantee Structure_t
      |
      v
Subject / Group Response_t
      |
      v
Strategy Distribution Π_t
      |
      v
Aggregate Behavior_t
      |
      v
Macro Feedback
      |
      v
Macro State_(t+1)
```

**v0.1 铁律**：每一个箭头都必须在现实中找到对应的可观察对象。找不到可观察对象的箭头，写 NA + reason，不硬造。

---

## 二、五个最小对象

### 1. Macro State（宏观状态）

当前宏观系统状态，只允许记录：

```text
economic conditions
employment
fiscal capacity
institutional changes
demographic trends
market conditions
guarantee institutions
other relevant macro variables
```

原则：
- 只记录与当前问题有关的现实状态
- **不得把结论直接写进 state**（结论进 Mechanism 或 Prediction）

### 2. Guarantee Structure（担保结构——EGS 核心层）

必须描述：

```text
positive promise      谁承诺了什么
negative sanction     不投入/退出承担什么
guarantee provider    谁提供担保
guarantee capacity    担保能力（兑现能力）
domain                领域
time horizon          时间视野
alternative guarantee supply   替代担保供给
```

现场形式至少能回答：
- "谁向谁承诺什么？"
- "投入什么可以获得什么？"
- "不投入/退出会承担什么？"
- "这个担保的来源是什么？"
- "是否存在替代担保来源？"

### 3. Subject / Group（主体/群体）

记录接受担保结构影响的主体，可以是：

```text
individual / household / cohort / occupation / age group / region / social group
```

**必须保留主体类别**——不要把"年轻人"直接当作同质主体。必要时记录异质性：

```text
resources / constraints / career stage / education / location / income / exposure / other
```

### 4. Strategy Distribution Π（策略分布——本类型与 Field Trial 最大区别）

**不要把策略写成一个人一个 label。** Π 表示在一组主体中各类策略的分布/权重。

策略至少允许（类别围绕"主体如何重新配置时间、资本、劳动、关系和欲望"，不固定死）：

```text
continue / exit / switch / seek_alternative / delay / reduce_desire /
increase_saving / migrate / build_new_guarantee / other
```

### 5. Macro Feedback（宏观反馈）

记录微观聚合行为是否可能改变宏观系统，例如：

```text
household formation / fertility / consumption / labor participation /
migration / capital allocation / investment / entrepreneurship /
demand / institutional pressure / fiscal burden
```

**铁律**：不允许从单一主体行为直接推导宏观反馈。必须有：

```text
individual / group behavior -> aggregation -> macro observable
```

---

## 三、区分"事实 / 解释 / 预测"三层

每个 Macro–Micro Trial 必须有三层，禁止混淆：

| 层 | 内容 | 禁止 |
|---|---|---|
| **State** | 已经发生/正在存在的事实 | 把结论写进事实 |
| **Mechanism** | EGS 对 Guarantee -> Strategy -> Aggregate Behavior 的**解释** | 把机制解释当已验证事实 |
| **Prediction** | 未来可观察、可能被现实击中的结果 | 模糊的"系统会变化" |

---

## 四、Field Trial 接入（引用，不复制）

Macro–Micro Trial 可以包含多个 Field Trial Cases：

```text
Macro Case
    |
    v
多个 Subject / Group
    |
    v
FT01 / FT02 / FT03 / ... (field_trial_case_id 引用)
    |
    v
Strategy Distribution Π
    |
    v
Aggregate outcome
```

- **Field Trial Case = 微观观测单元**
- **Macro–Micro Game Trial = 聚合与反馈单元**
- 一个 Macro–Micro Trial 通过 `field_trial_case_id` 引用多个 Field Trial Cases，**不复制整个 case**

---

## 五、状态机

```text
designed      模板就绪，未启动（当前状态）
  -> open     现实条件触发，开始建 Case
  -> tracking 宏观状态冻结后，追踪微观 episodes + 聚合行为
  -> closure  结果窗口到点，判定预测
  -> reviewed 错误分类 + revision 完成
异常：not_identified / abandoned
```

---

## 六、判定与证据等级

**模式支持 ≠ 理论证明**：

```text
MS = mechanism supported（机制解释获支持）
MP = micro prediction supported（微观预测获支持）
MF = macro feedback supported（宏观反馈获支持）
```

证据等级（沿用 Field Trial，防小样本吹模式）：

```text
E1 = 单个宏微链条
E2 = 两个独立案例/时期出现同一方向
E3 = >=3 个独立事件/群体，形成稳定模式
NI = Not Identified
```

---

*复制本文件 = 开始一个新 Macro–Micro Game Trial Case。当前 v0.1 = designed / dormant。*
