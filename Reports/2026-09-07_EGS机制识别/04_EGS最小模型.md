# 04_EGS最小模型.md

> EGS 第三轮 · 机制识别 · 交付物 4/6 ｜ 2026-09-07
> 目的：把 EGS 压缩到最少变量 + 最少方程 + 最大解释力；只保留 T1 结构假设与 T3 可检验推论。
> 纪律：① 不增加新变量；② 每个变量必须有可测量代理；③ 状态方程必须能产生可检验预测；④ 证据分级 T1/T2/T3 + A/B/C/D/E。
> 上游：承 v1 §2-4 模型（v0.1），缩减 05 概念边界、对接 03 可证伪预测。

## 1. 设计原则

$$
\boxed{
\text{EGS}_{\text{min}} = \arg\min_{\mathcal{M}} |\text{Var}(\mathcal{M})| + |\text{Eq}(\mathcal{M})| \quad \text{s.t.} \quad \mathcal{M} \text{ 能产生 } \geq 3 \text{ 个 T3 可检验预测}
}
$$

- 不为数学复杂度而复杂度——交付物 03 已显示现有 10 个预测中**无 1 个完全通过**，原因是缺数据而非缺模型。
- 模型只承担**机制结构化 + 预测可推导**两个功能。

## 2. 状态变量（5 个，最少）

| 符号 | 名称 | 主体层级 | T1 定义 | 可测代理 | 当前可测性 |
|---|---|---|---|---|---|
| $G$ | 担保强度 | 系统 | 客观担保能力 = f(Resources, Institutions, Execution) | 社保替代率/失业保障/医疗负担/教育支出/政策可信度 | 部分（社保替代率 [B]，其余 [E-需核实]） |
| $R$ | 风险暴露 | 主体 | 债务/失业/资产损失/医疗支出/养老压力 | 不良贷款率/调查失业率/房价指数/医疗 CPI/老龄化率 | 部分（不良率 [E]，房价 [C]，其余 [E-需核实]） |
| $I$ | 激励一致性 | 跨主体 | $(w_j, q_k)$ 在 C/L/F/H 四主体间的对齐度 | 政策文本与地方执行差/干部任期 vs 出清周期/费率与保障覆盖差 | 弱（政策文本 [A]，执行差 [未取得]） |
| $E$ | 预期 | 主体 | $E = f(G, R, I)$（主观期望） | 储蓄率/消费倾向/生育/创业/风险资产配置 | 部分（储蓄率 [E-需核实]，其余 [未取得]） |
| $A$ | 行为适应 | 主体 | $\Pi_i \in \{\text{retain, withdraw, substitute, defer, reconstruct}\}$ | 出清/续命/储蓄/推迟长期承诺/迁移 | 部分（消费率 [A]，出清 [E-需核实]） |

### 2.1 每个状态变量的不可测量则删除

- $G$：社保替代率 [B 可测]，政策可信度 [需调查]，**保留但标"代理变量未对齐"**。
- $R$：失业率 [E-需核实]，房价 [C]，**保留**。
- $I$：$(w_j, q_k)$ 文本层 [A] vs 执行层 [未取得]，**保留但标"执行层缺数据"**。
- $E$：储蓄率 [E-需核实]，**保留**。
- $A$：消费率 [A]，出清 [E-需核实]，**保留**。

> **诚实声明**：5 个状态变量全部有代理变量可测，但其中 4 个的代理变量未取得 A 级数据。模型本身可写，但**不可声称已被识别**。

## 3. 最少动态方程（4 个 + 1 个约束）

### 3.1 担保强度演化方程

$$
\boxed{
G(t+1) = G(t) + \underbrace{\alpha_{\text{policy}} \cdot \Delta \text{Policy}_t}_{\text{政策调整}} - \underbrace{\alpha_{\text{fiscal}} \cdot \Delta \text{FiscalGap}_t}_{\text{财政缺口侵蚀}} - \underbrace{\alpha_{\text{aging}} \cdot \Delta \text{Aging}_t}_{\text{老龄化侵蚀}}}
$$

- 政策调整（如社保扩面）→ $G$ 上升；
- 财政缺口（土地财政衰减）→ $G$ 下降；
- 老龄化 → $G$ 下降（养老/医疗压力）。
- T1 假设：$\alpha_{\text{policy}}, \alpha_{\text{fiscal}}, \alpha_{\text{aging}} > 0$。
- T2 推论：$|\dot{G}_{\text{new}}| < |\dot{G}_{\text{old}}|$ 时（新担保建立 < 旧担保衰减），系统进入"担保真空"。

### 3.2 风险暴露演化方程

$$
\boxed{
R(t+1) = R(t) + \underbrace{\beta_{\text{debt}} \cdot \Delta \text{Debt}_t}_{\text{债务累积}} + \underbrace{\beta_{\text{asset}} \cdot \Delta \text{AssetLoss}_t}_{\text{资产损失}} + \underbrace{\beta_{\text{unemp}} \cdot \Delta \text{Unemp}_t}_{\text{失业}}
}
$$

- T1 假设：$\beta_{\text{debt}}, \beta_{\text{asset}}, \beta_{\text{unemp}} > 0$。
- T2 推论：房地产下行期 $\beta_{\text{asset}} \cdot \Delta \text{AssetLoss} > 0$ → $R$ 上升 → 居民 $E$ 恶化。

### 3.3 预期形成方程（核心）

$$
\boxed{
E(t+1) = \phi_G \cdot G(t+1) + \phi_R \cdot R(t+1) + \phi_I \cdot I(t+1) + \phi_{\text{social}} \cdot \text{Social}_t
}
$$

- T1 假设：$\phi_G > 0, \phi_R < 0, \phi_I > 0$——担保强度上升→预期改善；风险上升→预期恶化；激励一致性上升→预期改善。
- $\text{Social}_t$ = 社会保障（失业救济/医保覆盖）作为 $G$ 的子项进入。
- T2 推论：$G \downarrow + R \uparrow$ 时 $E \downarrow$ → 居民行为"推迟"占优（P1/P10 的源头）。

### 3.4 行为适应方程

$$
\boxed{
A(t+1) = \arg\max_{\pi \in \Pi_i} \Big\{ \mathbb{E}[U_i(\pi; E(t+1), I(t+1))] \Big\}
}
$$

- T1 假设：主体 $i \in \{C, L, F, H\}$ 在预期 $E$ 与激励一致性 $I$ 下选择策略 $\pi \in \{\text{retain, withdraw, substitute, defer, reconstruct}\}$。
- T2 推论：$\tau_L < t^* \approx 3-7$ 年且 $\delta_l > \delta_c$ 时，地方选择 $\pi_L = \text{defer}$（推迟坏消息）——对应 P6。

### 3.5 激励一致性约束（恒等式）

$$
\boxed{
I(t) = 1 - \frac{1}{4} \sum_{i \in \{C, L, F, H\}} |\delta_i(t) - \bar{\delta}(t)| / \bar{\delta}(t)
}
$$

- 四主体 discount rate 错配度越低 → $I$ 越高。
- T1 假设：$\delta_l > \delta_c > \delta_f > \delta_h$（待 v2/v3 经验证）。
- 当前测量：$\delta_i$ 全部 [未取得]，**方程可写不可识别**。

## 4. 系统动力学（T2 推演）

### 4.1 "担保真空"情景（核心预测）

$$
\text{当 } \dot{G} < 0 \text{ 且 } \dot{R} > 0 \Rightarrow E \downarrow \Rightarrow A \to \{\text{defer, retain}\} \text{ 占优}
$$

- 居民 $A_H = \text{defer}$（推迟长期承诺）—— P1
- 地方 $A_L = \text{retain}$（保企业/续命）—— P5/P6
- 企业 $A_F = \text{retain}$（借新还旧）—— P3
- **系统进入"半出清均衡 + 高储蓄 + 推迟长期承诺 + 旧模式续命"的稳态**

### 4.2 "新担保建立"情景

$$
\text{当 } \dot{G} > 0 \text{ 且 } \dot{R} \to 0 \Rightarrow E \uparrow \Rightarrow A \to \{\text{reconstruct, withdraw}\} \text{ 占优}
$$

- 居民 $A_H = \text{reconstruct}$（恢复长期承诺）
- 地方 $A_L = \text{withdraw}$（让低效退出）
- 企业 $A_F = \text{withdraw} \cup \text{reconstruct}$
- **系统进入"出清加速 + 消费改善 + 新产业接棒"的稳态**

### 4.3 关键阈值

$$
\boxed{
\text{Regime shift 触发条件}：\quad w_{\text{exit}} > 0 \ \wedge\  w_{\text{residence\_income}} > 0 \ \wedge\ \text{劳动者退出保障成立}
}
$$

- v1 §4 已构造此条件——是 EGS 从"半出清均衡"跃迁到"出清加速"的必要条件。
- 当前状态：**三条件均未达成**（v1/v2 已证）。

## 5. 可检验推论（T3，对接 03 预测集）

| T3 推论 | 对应预测 | 数据要求 | 当前可执行性 |
|---|---|---|---|
| $\dot{G}_{\text{new}} < |\dot{G}_{\text{old}}|$ → 居民三联征 | P1 | 资金流量表 + CHFS | 部分（C 级聚合） |
| $\tau_L < t^*$ → 地方续命占优 | P6 | 干部任期 + $\theta$ | 未执行 |
| $w_{exit}>0$ → $\theta$ 上升 | P7 | 政策落地 + $\theta$ | 政策未落地 |
| 社保扩面 → 储蓄下降（DID） | P8 | CHFS + 准实验 | 未执行 |
| $G \downarrow + R \uparrow$ → $\delta_h$ 上升 | P9 | CGSS/CFPS | 未执行 |
| 三条件成立 → 出清加速 | P5 | 政策落地 + 出清数据 | 反事实未观察 |

## 6. 参数识别攻击

| 参数 | 测量代理 | 数据源 | 现状 |
|---|---|---|---|
| $\alpha_{\text{policy}}$ | 政策调整→社保替代率变化 | 人社部年度报告 | [E-需核实] |
| $\alpha_{\text{fiscal}}$ | 财政缺口→社保支出压缩 | 各地决算 | 未取得 |
| $\alpha_{\text{aging}}$ | 老龄化→社保压力 | 统计局 | [E] |
| $\beta_*$ | 风险暴露代理 | 银保监/统计局 | 部分 |
| $\phi_G, \phi_R, \phi_I$ | 预期形成弹性 | CHFS/CGSS | 未识别 |
| $\delta_i$ | 主体 discount rate | 实验经济学/调查 | 未测量 |
| $w_j, q_k$ | 政绩权重 | 省级实施细则 | [A 文本]，执行层未取得 |

### 6.1 不可测量则不允许写成"实证变量"

- $\delta_i$：当前 [未测量] → 标 T1 假设，不允许进入 A/B 级实证。
- $w_j, q_k$：文本层 [A]，执行层 [未取得] → 文本层可作为 A 级事实，执行层不允许进入实证。
- $\phi_*$：[未识别] → 模型可写但参数不可识别。

## 7. 模型与 v0.1 的差异（缩减）

| 维度 | v0.1 | v1.0（本最小模型） | 缩减理由 |
|---|---|---|---|
| 状态变量数 | 7（$G, GS^d, A, P^d, S^d, \Pi, Y$） | 5（$G, R, I, E, A$） | 合并 $GS^d, P^d, S^d$ 为 $G, I, E$；删除 $Y$（输出变量） |
| 方程数 | 4（地方 U_L，错配定理，出清构造，三命题） | 4+1（G/R/E/A 演化 + I 约束） | 重构为状态演化形式 |
| 主体数 | 4（C/L/F/H） | 4（同） | 保留——多主体是 EGS 真正新增 |
| 时间尺度 | $\tau_L, \tau_C$ | $\delta_i$（四主体 discount rate） | 扩展为四主体 |
| 可检验推论数 | 3（P-α/β/γ） | 6（对接 03 的 P1/P5/P6/P7/P8/P9） | 增加 |

## 8. 盒式结论

$$
\boxed{
\begin{aligned}
& \text{1. EGS 最小模型 = 5 状态变量（}G, R, I, E, A\text{） + 4 演化方程 + 1 约束，}\\
& \quad \text{能产生 }\ \geq 6 \text{ 个 T3 可检验推论。}\\
& \text{2. 核心动力学：}\ \dot{G} < 0 \text{ 且 } \dot{R} > 0 \Rightarrow E \downarrow \Rightarrow A \to \{\text{defer, retain}\}\ \text{占优}\\
& \quad \Rightarrow \text{系统进入"半出清均衡 + 高储蓄 + 推迟长期承诺 + 旧模式续命"稳态。}\\
& \text{3. Regime shift 触发条件：}\ w_{\text{exit}}>0 \wedge w_{\text{residence\_income}}>0 \wedge \text{劳动者退出保障成立。}\\
& \quad \text{当前三条件均未达成——v1/v2 已证。}\\
& \text{4. 参数识别：}\ \text{5 状态变量全部有代理可测，但其中 4 个的代理变量未取得 A 级数据；}\\
& \quad \textcolor{red}{\text{模型本身可写不可识别}}——\text{不允许以"模型可写"冒充"已被识别"。}\\
& \text{5. 与 v0.1 的差异：缩减状态变量从 7 到 5，增加可检验推论从 3 到 6；}\\
& \quad \text{保留四主体结构与}\ \delta_i \text{ 错配——这是 EGS 真正新增的机制（见 05 §3）。}
\end{aligned}
}
$$

*> 最小模型直接进交付物 06（第三轮结论的"哪些机制只是合理推论"判定）。*
