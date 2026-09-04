# 六国测量审计 Step 1：结构矩阵 + 接口归因审计（2021 窗口，ordinary scope）

> 日期：2026-09-02
> 定位：六国校准收官后的第一步系统审计——**先做 2021/当前窗口的 structural matrix audit，不碰复杂历史年份**（用户定序）
> 前置：SE/FR/DK/NL/DE/SI 六份逐维核验文档（`w_L校准_XX_逐维核验_v01.md`）
> 审计输出目标（用户定义六国阶段终点）：①六国×route×dimension×time 矩阵 ②dimension attribution map ③Coder-A/B reliability ④最终 w_L 表示形式——本文件为①和②的第一版
> 状态：单编码员（Coder-A）初核矩阵审计；Coder-B 与 κ 为后续步骤

---

## 一、2021 窗口 6×5 structural matrix（ordinary cohabitation scope）

| 国家 | 构型 | L1 身份 | L2 财产 | L3 继承 | L4 税/社保 | L5 亲子 | 标注说明 |
|---|---|---|---|---|---|---|---|
| **SE** | automatic | 2 | 2 | 1 | 2 | 2 | 全 exact；L3 无默认继承是"高自动型内部缺口" |
| **FR** | route-split | 0-1 | 0-1 | 0 | 0 | 2 | L1/L2 interval（concubinage 部分财产效果）；L3=0 exact（60% 继承税视同陌生人）|
| **DK** | gradual | 0-1 | 0 | 1 | 1-2 | 2 | L1/L4 interval；L2=0 exact（无财产分割成文法）|
| **NL** | registered 主导 | 0-1 | 0-1 | 0 | 1 | 2 | L1/L2 interval（samenwonen 契约有限）；L3=0 exact |
| **DE** | negative | 0 | 0 | 0 | 0-1 | 2 | L1-L3=0 exact（宪法否定式零态，high）；L4 interval |
| **SI** | constitutional-automatic | 2 | 2 | 2 | 2 | 2 | 全 exact（现行规则多源 high）；程序摩擦注（一案一认）|

**格式标注**：粗体数字 = exact value（high/中高置信）；`0-1`/`1-2` = interval（有界区间，未强行取中点）；全表为 2021 窗口现行规则编码（historical 时间线收口项见第三节）

**立即可见的结构事实**：
1. **L5 横截面零方差**：(2,2,2,2,2,2)——2021 窗口六国全同
2. **L1-L4 有真实横截面变异**：0 → 2 全档展开
3. **不存在"全低"或"单调渐变"**：DE (0,0,0,0-1) 与 SI (2,2,2,2) 是两端的干净反例；中间四国各有独特"缺口"形状

## 二、Attribution Audit：这一维测的是"路线接口"还是"普遍权利"？

### 2.1 审计问题（正式命名）

> **每一维究竟在测"这条关系路线给人的接口"，还是在测"国家普遍赋予人的权利"？**

route-dependent 维度应进 w_L^route；route-independent 维度（universal rights）应分离为协变量，否则会"人为抬高中低接口国家总分"（DE 的 (0,0,0,0,2) 若硬压五维总分会变 0.4，但真实含义是"伴侣接口≈0 + 儿童法高度平等"）。

### 2.2 六维归属判定

| 维度 | 归属 | 证据 |
|---|---|---|
| **L1 身份** | **route-dependent** | 六国 0→2 全档展开，直接测"同居 route 是否被承认/自动触发"（SE/SI 自动 vs DE 宪法否定）|
| **L2 财产** | **route-dependent** | SI 默认共同财产 / DK 无分割 / DE 视同无关人——接口直接挂在 route 上 |
| **L3 继承** | **route-dependent**（辨识度维度）| SE=1 vs SI=2（同 automatic 型内部分化）、DK=1 vs FR/NL=0——继承接口各国独立决策，是最干净的 route 接口维度 |
| **L4 税/社保** | **route-dependent（mixed——含 universal 污染项）** | SI/SE 等同条款明确给同居（route）；**污染项**：DE Elterngeld、NL 育儿照护金以"父母身份"为条件（universal）、福利 Bedarfsgemeinschaft 是义务侧（非权利）——L4 需在聚合时清洗这些 universal 项 |
| **L5 亲子** | **route-independent（universal child rights）** | **三次独立归因 + 一次最强明文**：FR（filiation 2005 改革非 PACS 功劳）、DE（1998 Kindschaftsrechtsreform 是儿童立法）、SI（**法典明文"同居对子女无后果、无父推定须承认"**——同居 route 与亲子解耦是成文法，六国最明确）、NL（erkenning 制属儿童法演进；2023 自动亲权是儿童法事件非同居接口）|
| （候选 L6 程序摩擦）| access-friction | SI"一案一认"（preliminary question 仅对该程序有效）——名义接口 vs 可及接口的摩擦层，候选新维度，待 Coder-B 评估，不进当前五维 |

### 2.3 Attribution 结论：w_L^route 与 C_child 分离（正式化）

$$
\boxed{w_{\text{relationship}} = f(L_1, L_2, L_3, L_4)}
$$

$$
\boxed{C_{\text{child}} = L_5\ \text{（universal child rights，作协变量单列）}}
$$

理由：
1. **零方差无识别力**：L5 六国全 2，进总分只抬分不提供信息
2. **归因错位**：L5 高分来自儿童普遍权利（多数国家 1970s-2000s 的亲子法改革），与"国家给同居 route 多少接口"是两个概念——DE 的"儿童法高平等 + 同居零接口"正是 EGS 想区分的
3. **方向性污染**：若 L5 进总分，DE (0.4) 与真正中高接口国家（如 FR-PACS 系）的分差被压缩

**处理建议**：L5 不进 w_L^route；C_child 作为回归协变量（控制"儿童权利环境"后再看 route 接口对 A×Y 的作用）——这也直接服务未来检验：**如果 C_child 单独能解释行为而 w_relationship 不能，说明 EGS 的机制在 route 接口而非普遍儿童福利**。

## 三、三矩阵分层（Cov 审计前置）

用户规范：区间不得当精确整数、unknown 不得当 0。当前 2021 窗口三张矩阵：

### M_point（可作精确值进入计算）

| | L1 | L2 | L3 | L4 | L5(单独) |
|---|---|---|---|---|---|
| SE | 2 | 2 | 1 | 2 | 2 |
| DE | 0 | 0 | 0 | — | 2 |
| SI | 2 | 2 | 2 | 2 | 2 |
| FR-L3/L4 | — | — | 0 | 0 | 2 |
| NL-L3 | — | — | 0 | 1 | 2 |
| DK-L2/L3 | — | 0 | 1 | — | 2 |

（FR L3=0/L4=0、NL L3=0、DK L2=0/L3=1、NL L4=1 的 exact 项并入各自国家行）

### M_interval（有界区间，进 Cov 前需定规：区间中点法 or 极值敏感性）

| 国家 | 区间项 |
|---|---|
| FR | L1 ∈[0,1], L2 ∈[0,1] |
| DK | L1 ∈[0,1], L4 ∈[1,2] |
| NL | L1 ∈[0,1], L2 ∈[0,1] |
| DE | L4 ∈[0,1] |

**处理规范建议**：Cov/结构检查跑三遍（下界 / 中点 / 上界），看结论是否跨界稳定——不预设中点。n=6 时主要看"方向是否稳定"而非数值。

### M_historical-uncertain（2021 窗口不涉及；时间线扩展时启用）

DK 早段（§87/§111a 引入年）、FR 1999-2006 PACS 财产默认共同制、DE 1975-97 L5=1 段、NL L4_ordinary 历史时间线、SI Art.4a 引入年——**扩展年份时这些进 missing/uncertain，不得当 0 或当 2**（0_negative 与 0_unknown 分离规则已在 DK/DE 校准建立）。

## 四、结构共变检查（n=6 描述性，不做统计推断）

**Cov(L1..L4) 的成对结构证据**（不用 Pearson——n=6 无统计意义；改用"共变/解耦案例"检查）：

| 成对 | 结构 | 证据 |
|---|---|---|
| L1–L2 | **近共变但非完全** | 自动端（SE/SI 双 2）与否定端（DE 双 0）同步；**解耦案例：DK**（L1=0-1 有同居认定痕迹但 L2=0 无财产制）|
| L2–L4 | **双向解耦（强证据）** | DK：L2=0（无财产分割）但 L4=1-2（养老金/继承税有接口）；FR：L2=0-1（共同购买可共有）但 L4=0（无任何税务等同）——**"财产接口"与"社保接口"各国独立决策** |
| L1/L2–L3 | **解耦（L3 独立辨识度）** | SE/SI 同 automatic：L3 1 vs 2；DK=1 vs NL/FR=0（中低档分化）——L3 在同一制度形态内部提供辨识度 |
| L4–L5 | **完全解耦** | L5 全 2（universal）而 L4 0→2（route）——归因审计的直接统计证据 |

**结构读法**：至少存在三组独立变化——(L1L2 核心) / L3（继承，独立辨识度）/ L4（社保，与 L2 双向解耦）；L5 属 universal 通道（分离）。**L3 是"同一制度形态内部辨识度"的最佳载体（SE 1 vs SI 2），正是五维化的原始动机的兑现。**

## 五、单轴模型否决 + 决策树当前分支

### 5.1 单轴假设的失败模式

若 w_L 是单轴（弱→中→强），应期待五维整体同步——六国已出现系统性反例：

- **DE (0,0,0,0-1 | 2)**：伴侣接口零 + 儿童法高的"分裂型"——单轴无法表达
- **SE (2,2,1,2 | 2) vs SI (2,2,2,2 | 2)**：同 automatic 型，仅 L3 区分——单轴需要 L3 独立轴才能分辨
- **DK (0-1,0,1,1-2 | 2) vs NL (0-1,0-1,0,1 | 2)**：财产与继承的取舍方向相反（DK 弃财产保继承、NL 弃继承保财产近似）——单轴排序无法容纳"形状差异"

### 5.2 决策树当前分支

```text
六国矩阵 ✅
  → Attribution Audit ✅（L5 分离）
  → Point/Interval 分层 ✅
  → Cov/结构检查（初步：非单因子，L3/L4 有独立变化）
  → 是否近似单因子？→ 否（当前证据）
  → vector 分支：w_L = (w_core[L1L2], w_L3, w_L4) 或保留五维向量 + C_child 单列
  → 中间状态候选：w_core（L1L2 共变部分）+ w_L3 + w_L4 三组件，替代硬压一个数
```

**当前倾向（待 Coder-B 与扩展样本确认）**：**坐标系而非单根尺子**——"关系接口强度"至少是 (身份财产核心, 继承, 社保) 三轴，L5 以 C_child 协变量单列。这与用户的直觉一致；正式裁决等 Coder-B reliability + 更多国家（若未来扩样本）后用 EFA/CFA 决定 latent 结构。

## 六、Coder-B 协议前置（下一步）

- **A 版 frozen**：六份校准文档即 Coder-A frozen baseline——本轮审计不改数值
- **B 盲编**：B 只拿编码规范（五维化设计 v0.2 + reconstruction protocol + 三矩阵分层规则）与各国法律证据源清单，**不看 A 的最终数值**，独立填 6×5 表
- **κ 重点类目**：①0↔2 冲突；②**归因性冲突**（"普遍儿童权利" vs "关系路线接口"的判定——L5 是最大风险格）；③interval 的边界（0-1 vs 1-2 选择）
- **输出**：M_A vs M_B 逐格 + raw agreement + Cohen's κ + weighted κ；冲突回法律源仲裁，不改 A/B 原始记录

---

> 落盘目录：`D:\Contents\Research\Reports\2026-09-02_EGS应用落地假设集\`
> 配套：六份 `w_L校准_XX_逐维核验_v01.md`（SE/FR/DK/NL/DE/SI）+ `w_L五维化与六国校准设计_v02.md` + `P0数据过桥方案_非婚生育路线_v02.md`（第九节 w_L 四维索引）
> 状态：Step 1 完成（structural matrix + attribution audit）；下一步 = Coder-B 盲编 + κ
