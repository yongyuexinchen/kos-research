# B12 — EGS Macro–Micro Game Ontology v0.1

> 日期：2026-09-02
> 角色：EGS-B / Theory & Mechanism Track
> 上游冻结引用：B1–B11 全部裁决（EGS-B 会话）；EGS-A A11 Field Trial Protocol v0.1 + Amendment 01（D1/D2/D3）；EGS_MacroMicro_GameTrial_架构定位 v0.1（designed/dormant）
> 性质：**理论本体文档（THEORY），非模型结果、非经验证据**。所有条目按 T0（定义/公理）/ T1（模型结构假设）/ T2（模型内生预测）/ T3（经验可检验预测）标注。
> 与 EGS-A 边界：本文件不设计问卷、不做测量、不检索现实资料、不修改 A11/FT01/FT02。Field Trial = 观测层；本文件 = 机制层。

---

## 一、核心问题（THEORY · T0）

> **当宏观系统的担保能力、制度接口与替代担保结构变化时，异质主体如何重新配置其投入/退出/替代/延迟/降欲/重建策略；这些策略的聚合变化又如何经由制度响应，反馈到宏观担保状态？**

此问题与 A11 的问题（"一个现实决策事件中判断/预测/结果是否对应"）严格分层：A11 是**观测单元正确性的检验**，本本体是**宏观→微观→宏观闭环的机制结构**。二者禁止互相冒充。

---

## 二、Macro / Micro 分层（THEORY · T0）

```
Macro Layer（系统层）
   G         客观担保能力（去信任化后；B11 裁决 G=G_A）
   GS        担保结构 (Guarantee Structure)
   A         替代担保供给结构
        ↓ 结构性信号
Micro Layer（主体层）
   {GFR_global, P^d, S^d}_i   信念/期望
   Π_i                       策略激活（资源配置）
   Y_i                       行为
        ↓ 聚合
Aggregate Layer
   Π_t, Y_t                  策略分布 / 聚合行为
        ↓ 制度响应
Macro Feedback → G_{t+1}
```

**分层铁律**（继承 B11）：G 是客观状态；GFR/P/S 是主体对担保结构的认知/预期。禁止 G=trust；禁止 GFR=P 平均值；禁止 GFR 由 P 构造。

---

## 三、Guarantee Structure（THEORY · T0）

**定义**：一个领域的担保结构是四元组到机制签名的映射：

```
GS^d = (X_d, Y_d, I_d, R_d, M_d)
  X_d  主体投入/遵循的路径
  Y_d  该路径承诺的正向回报
  I_d  兑现接口（制度/关系结构）
  R_d  不遵循/退出的制裁与代价结构
  M_d  承诺—制裁运作的机制签名（领域同一性判定，B10 裁决）
```

**宏观担保状态 = 担保结构的整体配置**：

```
GS_t = {GS^d}_d∈D   （领域集的联合结构 + 领域间的接口关系）
```

而非单标量 G 的退化。G 是 GS 的"客观能力汇总"，但 GS 保有领域分化信息（B10：multi-domain ontology accepted）。

**约束**：GS 定义中 **不得混入 trust**（B11）。I_d 指正式的接口/兑现通道；主体的信任以期望变量承载。

---

## 四、核心状态变量（T0 定义 · 全部继承 B 线裁决）

| 变量 | 层级 | 定义（冻结） | 状态 |
|---|---|---|---|
| **G** | 宏观 | 去信任化后的客观担保能力 = f(Resources, Institutions, Execution) | T0（B11） |
| **GS^d** | 宏观 | 领域 d 的担保结构四元组+机制签名 | T0（B10） |
| **A** | 宏观/微观 | 替代担保供给结构（多路径向量；每路径有自己的担保来源类型） | T0 |
| **GFR_global** | 微观 | 主体对"整个系统总体是否会兑现承诺"的前瞻信念；**非构造式**：由 Z_shared/Z_global 驱动，与 P 相关但互不构造 | T0（B11） |
| **P^d** | 微观 | 主体在领域 d 对 X_d→Y_d 正向承诺兑现的条件期望；不可被 GFR 构造（B4/B9/B10） | T0 |
| **S^d** | 微观 | 主体在领域 d 对"不投入/退出 → 现实代价"的期望；有独立行为通道（B1 修正后） | T0 |
| **Π_i** | 微观 | 主体的策略激活/资源配置向量（非互斥标签） | T0（重构于 M1） |
| **Y_i** | 微观 | 主体行为输出 | T0 |
| **Y_t** | 聚合 | 聚合行为 | T0 |

**条件变量（异质性，非核心机制变量，防膨胀）**：

```
R_i        资源禀赋
C_i        约束（时间/成本/制度约束）
Exposure_i 领域暴露度
History_i  过往兑现经历（领域特异记忆）
```

---

## 五、Strategy Π（THEORY · T0/T1）

### 5.1 重构定义

> **Π 不是一个人的行为标签，而是主体在多个可行策略之间的资源配置/策略激活结构。**

- 允许同时激活多条策略（"辞职做独立开发，同时不结婚"=substitution + rebuild + desire shift）。
- 与 LHS v0.3 的"策略激活谱"一致：Π_i = (π_1,…,π_K)，π 是激活强度，可共现。
- **禁止**：5 分类互斥穷尽（M1/P 时代遗产，B 线已放弃）。

### 5.2 策略基（Strategy Basis）——理论比较（THEORY · T1）

候选 1：行为类别集（M1 继承）：
```
{participate, exit, substitute, desire_off, rebuild}
```
问题：类别相关、非正交、不可能穷尽（第 6 类还是第 7 类之争）；"延迟"缺席，"迁移"缺席。

候选 2：低维基础操作（B12 提案）：
```
{retain, withdraw, substitute, defer, reconstruct}
```
- **retain**   = 在当前担保路径继续投入
- **withdraw** = 从当前路径退出（承担 S 代价）
- **substitute** = 转向替代担保路径获取同一 Y（保 Y 换路径）
- **defer**    = 推迟/时机择（不退出但延后投入；对应"延迟婚育/等待"）
- **reconstruct** = 重建/新建担保路径（替代缺位时的创造性担保）

**比较结论**：
| 维度 | 候选 1（行为类别） | 候选 2（基础操作） |
|---|---|---|
| 正交性 | 低（substitute 与 rebuild 难分） | 较高（按"路径—Y—时机"三维划分） |
| 领域中立 | 中 | 高（任意领域同一套操作） |
| 可组合性 | 弱（互斥预设） | 强（reconstruct 可 = substitute + 新建） |
| 理论依据 | 继承 M1 | 更贴近担保结构语义（X→Y→时间→替代） |

**B12 暂不宣布五类为最终 ontology**——作为 T1 候选。若未来观测显示不同基础操作存在系统性共现结构，再做归并/分裂（如 reconstruct 可能并入 substitute 的新路径变体）。

### 5.3 策略映射（T1）

```
Π_i,t = σ( V(GFR_i,t, {P^d, S^d}_i,t, A_i,t; R_i, C_i, Exposure_i, History_i) )
```
其中 σ 为激活映射（softmax 及"瞬时函数"在 M1 里的设定随 M1 定位降级；此处只标 T1 结构，函数形式待 B13）。

---

## 六、Aggregate Behavior（THEORY · T1）

**问题**：多个主体的 Π_i 如何聚合成 Y_t？

规则（非计量规则，是理论约束）：
1. **聚合的对象是策略分布** Π_t = Aggregate_i(Π_i,t)，不是单主体标签；
2. **聚合不可约**：相同 Y_t（总量）可能对应不同的 Π 分布（一人全押 vs 万人各押 0.001）——防止"用总量代替结构"的偷懒；
3. **不默认"人口变化 = 反馈"**：只有经完整反馈链（下面第七节）才构成 EGS 反馈。

候选聚合维度（T1，非穷尽）：
```
labor allocation / consumption / family formation / fertility /
migration / capital allocation / entrepreneurship / institutional demand / fiscal pressure
```

---

## 七、Macro Feedback（THEORY · T1）

**完整反馈链**（防"人口变化=feedback"的滑坡）：

```
micro behavior (Y_i)  →  aggregate variable (Y_t)  →  institutional/system response
      →  G_{t+1} 的变化
```

- 只有 micro→aggregate→**institutional response**→G 完整走完，才叫 EGS 反馈。
- **制度响应**是反馈链的钥匙（也是 B13 需要明确定为结构假设的一环）：财政压力、编制政策、福利制度、市场供给变化等把聚合行为"翻译"成系统能力变化。
- 内部一致性要求（B 线铁律）：**模型读数值 ≠ 现实证据**。凡模型产生的反馈模式，一律标注 T2；现实检验由 EGS-A。

---

## 八、Heterogeneity（THEORY · T1 —— 宏观→微观的桥）

**核心问题（宏到微的桥）**：为什么同一个宏观 G，不会让所有主体做出同样决策？

**必要条件（B12 裁决）**：模型中必须显式保留主体异质性，否则宏观→微观退化为"所有人同一 Π"，宏观反馈链无法启动。

条件变量与 EGS 变量的接口（区分两类，防膨胀）：

| 类别 | 变量 | 作用 |
|---|---|---|
| 核心机制变量（ontology 必须） | G, GFR, P^d, S^d, A, Π | 机制本体 |
| 条件/异质性变量 | R_i, C_i, Exposure_i, History_i | 调节"同一宏观结构→不同 Π_i" |

**重要边界**（B 线裁决）：这些条件变量**不进核心 ontology**——它们解释异质性，但 EGS 的机制主张不需要把它们全部抬到核心状态地位。若未来出现"异质性本身产生宏观后果"的证据，再提升。

---

## 九、Strategic Interaction——真正的"博弈"在哪一层（THEORY · T1/裁决）

逐层判定：

### Level 1 — Individual adaptation
主体根据担保结构调整策略。**这只是 adaptation，不是 game。** EGS 若只做这一层，叫"G→π 映射"，不配叫 Game。

### Level 2 — Multiple subjects
大量主体同时调整策略：individual Π_i → aggregate Π_t。**这是 aggregation，不是 strategic interaction**（无主体间相互影响，只是并列求和）。

### Level 3 — Strategic feedback
主体 A 的策略改变主体 B 或担保提供者的收益/机会：
```
A strategy → system condition → B strategy → guarantee structure
```
**只有 Level 3 构成真正的 strategic interaction。**

**B12 裁决**：
- EGS 的 Game 应定位在 **Level 3**，但**不是传统 payoff matrix 博弈**。
- 最自然的形态是**担保消费者 × 担保提供者/制度的反馈博弈**：主体策略聚合 → 制度压力 → 制度响应 → 担保结构变化 → 新一轮主体策略。
- 即：**"Game"的对手方首先是"制度/G",也就是系统本身** —— 主体之间经由系统的间接交互（social-dilemma / coordination flavor，而非配对博弈）。
- **降级警告**：若某模型只实现了 Level 1-2（adaptation + aggregation），必须如实标注"非 strategic interaction"，不得挂 Game 之名。

---

## 十、Guarantee Substitution / Migration（THEORY · 候选核心模块）

**机制问题**：担保衰退时主体不只有 exit 一种反应（B 线 M1 已证退化的三种形态）：

```
P^A↓ → A^B↑ → switch            （转向替代担保，保 Y 换路径）
P↓   → S↑ → desire reduction    （降欲：放弃/下调 X→Y 追求）
P↓   → rebuild guarantee        （重建：创造性构造新担保）
```

**B12 命题（T1，候选核心）**：

> **EGS 中存在更一般的"担保替代/迁移"机制：主体在担保组合（guarantee portfolio）中再配置——当某一担保源的承诺可信度下降时，主体的担保投资从该源迁出，迁出的方向由替代供给结构（A）、制裁结构（S^d）与主体异质性共同决定。**

- 这比"逃逸线"更一般：逃逸线是"退出当前担保"；担保迁移是"在保证组合内持续再配置，未必彻底退出"。
- 若成立，这是 EGS 最核心的理论模块之一；B13 应将其模型化为**保证投资分配**（Π 的资源再配置）。
- 现任然 T1；A 线能否观测"同一主体跨领域/跨时间的担保再配置"将决定其 T3 前景。

---

## 十一、Minimal DAG（THEORY · 结构骨架，B12 定稿）

```
G_t ──► GS_t ──► {GFR, P^d, S^d, A}_t    宏观→结构→信念
        │              │
        └──────────────┴──► Π_i,t ──► Y_i,t     微观策略与行为
                                  │
                                  ▼
                            Y_t (aggregate)
                                  │
                                  ▼
                        institutional response
                                  │
                                  ▼
                            G_{t+1}  ◄── 宏观反馈（闭环）
```

**严格区分（铁律）**：
- G/GS/A 是客观状态（观测：宏观指标/结构编码）
- GFR/P/S 是信念（观测：量表/行为反演——A 线）
- Y/Π 是行为（观测：行为痕迹）
- 虚线不分层：无"宏观→微观→宏观"完整闭环，则不称 Macro–Micro mechanism

**断链风险点**（预注册警惕）：
1. 若"宏观→结构→信念"塌缩为"G→P"即时投影（M1 遗产），信念层消失 → D2 滤波冗余；
2. 若"聚合→制度响应→G"缺失，退化为单向响应模型；
3. 若 A 为常量，担保迁移不可表达。

---

## 十二、与 Field Trial / A11 的关系（分层完成，禁止合并）

| | Field Trial (A11) | Macro–Micro Game (B12) |
|---|---|---|
| 层 | 观测/认知验证基础设施 | 机制层 |
| 问题 | 单个决策的预测准不准？ | 担保结构→策略分布→聚合→宏观反馈？ |
| 单位 | decision episode | Π 分布 + 反馈 |
| 引用 | FT01/FT02 作为宏状态/结构的输入参考 | 不修改、不解释 FT 记录 |

**每一条 B12 内容都必须可标注 THEORY / MODEL RESULT / EMPIRICAL EVIDENCE，禁止混标。**