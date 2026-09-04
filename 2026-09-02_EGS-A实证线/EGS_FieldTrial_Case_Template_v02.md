---
type: template
name: field_trial_case（现实实验 Case 模板 v0.2——通用，不绑定任何领域）
source: EGS-A A11 Field Trial Protocol v0.1 + Amendment 01（2026-09-02）
layer: position（行动层现实反馈；与 experiment 平行，详见 Schema 说明）
updated: 2026-09-02
note: 一个 decision episode 的记录单元——"现实决策 -> 事前预测 -> 实际行为 -> 结果 -> 错误 -> 学习"的完整闭环。复制本文件即建一个新 Case。
---

# Field Trial Case 模板 v0.2

> 用法：每次出现真实决策选择点时，**复制本文件一份**，按 stage 顺序填写。禁止事后补写任何 entry 阶段字段。
> 最小闭环：Observe -> Infer -> Predict -> Intervene -> Observe -> Learn
> 现场执行：ENTRY -> TRACKING -> CLOSURE -> ERROR -> REVISION
> **v0.2 变更**（同步 A11 Amendment 01 + FT01/FT02 执行反馈）：
> - D1 State Freeze：current_state 先于一切领域分析并**封存**（防 information leakage）；Pred_GFR-only 提前到 P/S/A 之前各自封存（先填 P/S/A 会污染"只看 GFR"的对照预测——v0.1 顺序漏洞，FT01 执行暴露）
> - D2：P > GFR 只表述为 structural hypothesis（防 P 自证措辞）
> - D3：新增 decision_mode（natural / EGS_informed）——natural 模式 EGS 不主动给建议
> - Closure 对照矩阵：三条预测**分别**对照 actual_behavior，不只判 Pred_full
> - protocol_deviation 编号化：PD-<case>-N

---

## 一、纳入判定（先过这关，不过不建 Case）

```
□ E1 有担保结构：能写出"投入 X -> 获得 Y" 或 "不投入/退出 -> 承担代价"
□ E2 决策窗口 <= 90 天，有真实行为选择点
□ E3 outcome 可观察、可核实（行为痕迹，非"我感觉"）
□ E4 P/S/GFR/A/opportunity 与三条预测在行动前记录

□ 三自问（每条必答）：
   1. X/Y 到底是什么？（写不出就不算）
   2. 同一个 Y 是否存在替代路径？（指向 A，不强行套 P）
   3. 现实上是否存在 opportunity？（防把"没机会"误判成"P 很低"）
```

排除条件（任一命中即不纳入，记入候选排除区）：X1 无明确 X->Y / X2 纯态度情绪 / X3 outcome 不可核验 / X4 纯回顾（已发生、只能事后重构）。

---

## 二、Case 头

```text
=== FIELD TRIAL CASE ===
case_id:            <FT01-S01-D01：trial-subject-domain 序号>
subject_id:         <主体代号，脱敏>
date:               <entry 记录日期 YYYY-MM-DD>
domain:             <education / career / income / relationship / long-term investment / migration / entrepreneurship / other>
episode_type:       <commit 继续投入 / exit 退出 / switch 切换 / build_alt 建替代路径 / enter 新投入 / withhold 机会在不投入>
decision:           <一句话：此刻悬而未决的真实选择是什么>
decision_mode:      <natural EGS只观察预测不干预 / EGS_informed 主体读EGS建议后行动>（D3，FT02 第一批优先 natural）
status:             <draft / open / tracking / closure / reviewed>
```

---

## 三、ENTRY（行动前 · 顺序硬性 · 逐段封存）

```text
--- 第 0 段：current_state（最先 · D1）---
state_freeze_timestamp: <YYYY-MM-DD>
state_freeze_status:    <已封存 / 变动见 protocol_deviation>
state_source_refs:      <信息来源：结构化问答/档案/会话>
current_state:          <现实状态事实，非评价：现状/约束/时间窗>
                        只记录"普通观察者在 EGS 分析前已可知道的现实事实"
                        禁止将 P/S/A/opportunity 判断或 EGS 推理反向写入（information leakage）
X:                      <投入路径：具体的持续投入动作——投递/报名/备考/追加资金/投入时间>
Y:                      <兑现回报：offer/证书/录取/收入/关系阶段结果>
                        [冻结]
```

```text
--- 第 1 段：Pred_intuition（常识直觉 · 先于一切 EGS 语言）---
Pred_intuition:     <直觉：方向+具体可观察行为+时间窗>
confidence_intuition: <0-100 / NA>
                    [冻结]
```

```text
--- 第 2 段：GFR + Pred_GFR-only（系统层 · 先于 P）---
GFR:                <整体系统层担保 0-100 + 理由。独立判断、禁止=P 均值、禁止由 P/S/A 汇总>
                    <合格指向：当前整体系统（行业/经济/制度/生活结构）对"承诺投入->兑现回报"的总体可信度>
Pred_GFR-only:      <只看 current_state + GFR，不看 P/S/A：方向+具体可观察行为+时间窗>
confidence_GFR:     <0-100>
                    [冻结]
```

```text
--- 第 3 段：P / S / A / opportunity（领域层）---
P:                  投入 [X] -> 获得 [Y] = NN/100。理由 + 支撑数值的现实证据
                    <绑定 domain+X+Y；禁止抽象成希望/信心/人生乐观>
S:                  若不投入/退出 [X] -> 将失去/承担 [代价] = NN/100。证据
                    <绑定退出代价；与 P 独立记录，P 低≠S 高>
A:                  同一核心 Y 的其他担保来源：
                    路径 j / 担保来源类型 / 可达性(0-3) / 是否需要新投入
                    <真替代=改变担保来源类型；换说法（换公司/换老师）不算 A>
opportunity:        <0-3 + 客观证据>  0=无现实入口 / 1=有但受限 / 2=正常可得 / 3=明确敞口
                    <现实入口事实，非信念；附岗位/名额/窗口/资格/经济环境证据>
                    [冻结]
```

```text
--- 第 4 段：Pred_full + Intervention（EGS 综合）---
Pred_full:          <完整五量判断：方向+具体可观察行为+时间窗>
confidence_full:    <0-100>
intervention:       <仅 decision_mode=EGS_informed 时填写。EGS 建议：advice=一句话可执行动作 /
                     rationale=依据哪个分化 / category。natural 模式填 None>
adoption_expected:  <full / partial / refused，事前预期>
                    [冻结]
```

**D1 顺序铁律（防污染，逐段封存）**：

```text
现实原始事实
  -> current_state        [封存]
  -> Pred_intuition       [封存]   （不调用 EGS 语言，最先）
  -> GFR
  -> Pred_GFR-only        [封存]   （只看 GFR+current_state，P/S/A 填前先封存）
  -> P -> S -> A -> opportunity    （领域层，填完封存）
  -> Pred_full
  -> intervention
```

**违规处置**：任一已封存条目被改动 -> 不覆盖原记录，新增 protocol deviation（PD-<case>-N）。

**D2 表述纪律**：现场出现领域层差异（如 P_career > GFR）只能表述为 **structural hypothesis / 待验证差异**；禁止表述为"P 已证明提供 GFR 之外独立信息"；只有后续预测/结果显示 P 带来 GFR-only 无法得到的可重复准确预测，才进入 P-increment evidence。

---

## 四、TRACKING（窗口内 · 发生即记 · 不积压）

```text
actual_behavior:    <只记动词：开始了什么/停止了什么/投入了多少/报名了什么/申请了什么/
                     支付了什么/切换了什么/建立了什么替代路径>
adoption:           <intervention 实际采纳：full / partial / refused + 真实原因（成本/恐惧/时间，不评判）>
behavior_deviation: <如与 Pred_full 偏离，记录偏离点>
protocol_deviation: <PD-<case>-N：执行偏离协议（漏记/晚记/字段歧义/封存被改），只记 deviation，不偷偷改协议>
```

**Tracking 纪律**："感觉更有动力"不是行为结果。行为结果只认可观察动作。

---

## 五、CLOSURE（结果窗口到点 · 证据判定）

```text
--- 第一步：逐条对照（Closure 对照矩阵——不得只判 Pred_full）---
Pred_intuition vs actual_behavior:  <命中 / 未命中 / 无法判定>
Pred_GFR-only  vs actual_behavior:  <命中 / 未命中 / 无法判定>
Pred_full      vs actual_behavior:  <命中 / 未命中 / 无法判定>
```

```text
--- 第二步：结果判定 ---
outcome:            <与 Y 对应的可核实事实：hit 达成 Y / partial 部分达成（相近但非目标 Y）/
                      wrong 未达成 / NI 窗口未完或事件性质改变>
prediction_error:   <correct 正确 / partial 部分正确（方向对但幅度/时间/路径偏）/ wrong 错误>
reason_for_error:   <M / I / C / O / V / U + 定位描述>
opportunity_check:  <结果偏离是否因机会不足/误估？是 -> 记 O，不把责任推给 P/GFR>
closure_date:       <YYYY-MM-DD>
episode_verdict:    <Success / Failure / Not Identified>
evidence_level:     <E1 单事件 / E2 两独立事件同向 / E3 >=3 独立事件跨>=2域或主体 / NI>
```

**closure 强制写作（禁空泛）**：

```text
1. 这次判断对/错在哪一步？（引用具体字段）
2. What would have made the prediction better?
   —— 必须写"如果当时记录到 [缺失信息] / 我当时把 [某字段] 判成 [X] 而非 [Y] /
      我若当时核对了 [机会证据]"。禁止只写"模型还不够成熟"。
```

**Opportunity check 前置**：判错误前先查"结果偏离是否因 opportunity 不足/被误估"——是则优先记 O。连续 U（unknown）触发 Failure D 观察。

---

## 六、ERROR & REVISION（错误定位与模型修正）

```text
error_type:
  M = measurement error    现场记录本身记错（与主体真实判断不符）
  I = inference error      判断对，从判断推行为预测的推理错
  C = causal error         对"担保结构如何驱动行为"的机制理解错
  O = opportunity error    机会暴露估计错（过高/过低）
  V = intervention error   EGS 建议误导，或建议对但执行走样
  U = unknown              以上皆否

model_revision:     rev-YYYYMMDD-N：规则变更内容 / 触发证据（哪次错误）/ 只影响未来预测
```

**Revision 纪律**：
- 只对未来预测生效；**禁止用修正后的规则解释已发生结果**
- 单次错误 -> 记录 + 观察；同一错误模式跨 >=2 个独立事件重复 -> 才进入规则级修正候选（防对单事件过度拟合）
- 修正必须写：触发哪个事件 / 错误是什么 / 修改了什么规则 / 为什么修改 / 只影响未来事件

---

## 七、三预测分叉报告（closure 时或中途如实填写）

```text
| 预测 | 值 | 分叉关系 |
| Pred_intuition | ... | — |
| Pred_GFR-only | ... | 与 intuition 一致/分叉：... |
| Pred_full | ... | 与 GFR-only 一致/分叉：... 增量在方向还是行为路径？ |

如实记录：三者方向一致就记一致（一致本身是发现——EGS 与直觉无差异是 Failure A 候选证据积累）；
有分叉才可能构成 P-increment 证据。此刻不宣布任何成功或失败。
```

---

## 八、Case 状态机

```text
draft           建卡，纳入判定中
  -> open       ENTRY 完成，预测封存，进入现实窗口
  -> tracking   窗口内，行为记录中
  -> closure    窗口到点，outcome 已核实
  -> reviewed   Error/Revision 完成，进入跨事件模式积累
异常分支：
  -> not_identified    窗口未完 / 行为痕迹不可得 / opportunity 全程 0 / 主体取消决策
                       注意：not_identified 不等于 failure
  -> protocol_deviation 执行偏离协议（记录后继续或中止，不偷偷改协议）
  -> abandoned          Case 废弃
```

---

## 九、四象限对照（禁止混淆）

```text
State        当前现实状态            -> current_state + P/S/GFR/A/opportunity（entry）
Prediction   行动前对行为的预测      -> Pred_intuition / Pred_GFR-only / Pred_full（entry 封存）
Intervention EGS 给出的建议          -> intervention + adoption（仅 EGS_informed 模式；可选）
Outcome      现实最终发生什么        -> outcome（closure 核实）

预测 ≠ 建议 ≠ 结果。三条必须分开记录、分开封存、分开核实。
```

---

## 十、判定纪律（A11 继承，不可谈判）

- **单次成功不确认理论，单次失败不证伪理论**——只有跨事件可重复模式进入判定（五模式：S1 State validity / P1 Prediction validity / P2 P-increment / I3 Intervention usefulness / L4 Learning）
- **禁止 outcome shopping**：不为保住 P 修改 outcome、不事后换事件、不事后改判定标准
- **禁止事后重述预测**：不为"加分"而美化已封存预测
- **P>GFR 不自证**（D2）：评分差异只是 structural hypothesis，不是增量证据
- **不人为制造决策**：只纳入自然发生、尚未最终行动、窗口内有真实选择点的事件
- **本模板本身不生成"理论成立"**——一个 Case Success 只是 E1 单事件数据点
- Stop Rules（预注册）：Failure A 预测不比常识好 / Failure B P 无增量 / Failure C 建议常致更差结果 / Failure D 错误无法分类——触发走预注册评审动作，不悄悄改规则

---

*复制本文件 = 开始一个新 Field Trial Case。所有字段按 D1 顺序逐段填写、逐段封存，宁可写 NA + na_reason，不静默缺失。*
