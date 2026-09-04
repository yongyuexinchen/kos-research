# EGS Macro–Micro Game Trial · MMGT-001（空白 Case）

> 状态：**designed / dormant**——模板就绪，未填入任何现实判断。
> 用法：未来现实条件触发（宏观变化 + 多主体 + 策略重配 + 反馈通道）时，按模板 v0.1 逐节填写。
> 纪律：本空白 Case 不包含任何现实判断；FT01/FT02 当前结果不得解释为 Macro–Micro 证据。

---

## 0. Trial 界定（触发时填写）

```text
trial_id:           MMGT-001
macro_state_id:     <待定>
time:               <观察期 起-止>
domain:             <career/education/housing/family/income/migration/AI/other>
status:             designed
activity:           dormant
source_refs:        <数据来源>
```

**启动条件检查（预注册，全过才激活）**：
- [ ] 宏观状态变化（可冻结、可观察）
- [ ] 多个相关主体/群体（存在异质性）
- [ ] 可观察的策略重新配置（Π 有现实变化迹象）
- [ ] 潜在反馈变量（聚合行为 -> 宏观的通道存在）
- [ ] E1-E4 类纳入检查（有担保结构/有现实窗口/行为可观察/记录先于结果）

---

## 1. Macro State（宏观冻结 · 继承 D1 State Freeze）

```text
freeze_timestamp:   <待定>
freeze_status:      <已封存/变动记 deviation>
economic conditions:    <现实事实>
employment:             <现实事实>
fiscal capacity:        <现实事实>
institutional changes:  <现实事实>
demographic trends:     <现实事实>
market conditions:      <现实事实>
guarantee institutions: <现实事实>
other macro variables:  <现实事实>
```

**原则**：只记现实事实，禁写结论（结论进 Mechanism/Prediction）。

---

## 2. Guarantee Structure（担保结构——EGS 核心层）

```text
positive promise:       <谁向谁承诺什么：投入 [X] -> 获得 [Y]>
negative sanction:      <不投入/退出 [X] -> 承担 [代价]>
guarantee provider:     <担保来源：谁提供>
guarantee capacity:     <担保能力/兑现能力>
domain:                 <领域>
time horizon:           <时间视野>
alternative guarantee supply: <替代担保供给：真替代 vs 同路径变体>
```

现场五问：
1. 谁向谁承诺什么？
2. 投入什么可以获得什么？
3. 不投入/退出会承担什么？
4. 这个担保的来源是什么？
5. 是否存在替代担保来源？

---

## 3. Subject / Group（主体/群体 + 异质性）

```text
subject_group:      <individual/household/cohort/occupation/age group/region/social group>
subject_exposure:   <各群体对担保结构的暴露度>
heterogeneity:      <resources/constraints/career stage/education/location/income/exposure>
```

**铁律**：保留主体类别；禁止把"年轻人"当同质主体。

---

## 4. 微观接入（Field Trial Cases 引用）

```text
field_trial_case_ids:  <FT01/FT02/... —— 引用不复制>
P / S / GFR / A / opportunity:  <有合法测量则填；无则 NA + reason，不造伪数据>
```

---

## 5. Strategy Distribution Π（策略谱）

```text
Π_t = {
  continue:             <count/share/ordinal/activation —— 按真实数据定>
  exit:                 <同上>
  switch:               <同上>
  seek_alternative:     <同上>
  delay:                <同上>
  reduce_desire:        <同上>
  increase_saving:      <同上>
  migrate:              <同上>
  build_new_guarantee:  <同上>
  other:                <同上>
}
```

**铁律**：Π 表达群体策略结构（谱），不是单一分类标签；权重不必加总 100%（除非设计为概率分布）。

---

## 6. Aggregate Behavior + Macro Feedback

```text
aggregate_behavior:  <微观聚合后的宏观可观察行为：household formation/fertility/consumption/
                      labor participation/migration/capital allocation/investment/
                      entrepreneurship/demand>
                      （必须经 aggregation：individual -> group -> macro observable）
macro_feedback:      <聚合行为对宏观的反馈：institutional pressure/fiscal burden/...>
```

**铁律**：禁止单主体行为直接推导宏观反馈。

---

## 7. Prediction（双向预测 · 结果前封存）

```text
downward_prediction:  <宏观担保变化 -> 预期策略迁移>
                      （例式：某领域 P 下降、替代上升 -> 更多主体退出并寻替代路径）

upward_prediction:    <策略聚合 -> 预期宏观后果>
                      （例式：大量主体退出某制度化路径 -> 需求/人口/财政压力进一步变化）

confidence:           <0-100>
freeze 声明:          <封存日期；结果前不允许修改>
```

**铁律**：两个方向分别记录；禁止用一个模糊的"系统会变化"代替。

---

## 8. Closure（结果窗口到点 · 判定）

```text
actual_outcome:     <与 prediction 对应的可核实结果>
error:              <correct / partial / wrong>
error_taxonomy:     <M/I/C/O/V/U + A/F/H>
opportunity_check:  <结果偏离是否因机会不足/误估？是 -> 记 O>
evidence_level:     <E1 单链条 / E2 两独立同向 / E3 >=3 稳定模式 / NI>
mechanism_support:  <MS / MP / MF：supported / not supported —— 模式支持 ≠ 理论证明>
model_revision:     <rev-YYYYMMDD-N：触发事件/错误/规则变更/只影响未来>
```

---

## 9. 博弈对象（仅当现实中存在 strategic interaction）

```text
actors:                 <国家/市场/企业/家庭/个人/...>
actions:                <各主体可选行动>
payoffs / expected returns:  <各行动预期收益>
guarantee dependencies: <担保依赖关系>
strategic interaction:  <一主体的选择如何改变他人收益/机会/担保结构>
feedback:               <交互的宏观反馈>
```

**铁律**：不为"博弈"强行数学化——只有现实中存在"主体的选择会改变其他主体的收益、机会或担保结构"时才建立 interaction。

---

## 10. 运行流程（12 步）

```text
1. Define Macro Question
2. Freeze Macro State          （继承 A11 Amendment 01 D1）
3. Map Guarantee Structure
4. Identify Subject / Groups
5. Observe / Import Micro Episodes
6. Infer Strategy Π
7. Record Downward Prediction  （结果前封存）
8. Record Upward Prediction    （结果前封存）
9. Track Aggregate Behavior
10. Closure
11. Error Classification
12. Macro–Micro Revision       （只影响未来 Trial）
```

---

*MMGT-001 空白 Case 就绪。status=designed，activity=dormant。未启动现实实验，未填现实判断。*
