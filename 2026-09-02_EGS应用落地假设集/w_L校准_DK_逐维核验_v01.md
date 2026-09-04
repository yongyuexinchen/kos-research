# 六国校准：DK（丹麦）L1-L5 逐维法律核验（第三例 · 渐进积累型方法学压力测试）

> 日期：2026-09-02
> 定位：六国校准第三个样本——**方法学压力测试**：制度渐进累积（无单一"大开关"立法），检验 w_L(t) 能否从多事件重建。
> 编码单元规格：每格 {value, source, effective date, scope, confidence}
> 状态：单编码员初核（frozen single-coder case，按 SE 版本纪律待 Coder-B）
> 来源：CEFL 欧洲家庭法委员会丹麦 informal relationships 立法文件（ceflonline.net，权威学术源）+ Lund 大学比较研究（Skandinavien sambo 遗属保护）+ borger.dk 丹麦官方 + Globe Advokater 继承法摘要
> **核心结论先行：DK ≠ v0.1 猜的"恒定 3"——DK 是渐进累积的低-中接口型，且各维轨迹独立。**

---

## 〇、方法学要点：DK 证明 w_L(t) 是"各维独立轨迹"而非单一开关

DK 没有法国 PACS 1999 或瑞典 sambolag 2003 式的"大开关"。它的制度是**多个法条在不同时点分别引入遗属/保险/租赁接口**，且 L2（财产分割）全程从未演进。因此 DK 的正确编码是：

$$
L_k(t) = \text{每维自己的分段函数（各自事件集）}
$$

而非"某个建制年后全变 2"。这对 reconstruction protocol 的含义：**渐进型国家的 w_L(t) 重建 = 逐维查各法条引入时点**，不能用 v0.1 的"恒定 3"或"找一个大年"偷懒。

## 一、DK 逐维核验表（ordinary cohabitation scope，samlevende/未登记同居）

### L1 伴侣身份承认：value=0-1

- **source**：CEFL 丹麦文件（各法用"marriage-like relationship + 同住 2 年或有共同子女"作条件，无统一同居身份概念）；对比瑞典 sambolag 有统一定义
- **effective date**：n/a（无统一身份法——条件散落各法）
- **scope**：ordinary cohabitation
- **confidence**：高（CEFL）
- **note**：丹麦**无** samlevende 法定登记身份（1989 registered partnership 为**同性专属**，红线不计；2012 同性婚姻后 RP 停用）；各领域法条用"婚姻式同居+2年/共同子女"条件自行定义同居者——**条件性承认，非独立身份**

### L2 财产/分割权：value=0

- **source**：Lund 大学比较研究（"In Denmark, cohabitants lack both of these rights"——既无瑞典式分割权也无挪威式有限继承）；CEFL
- **effective date**：无（从未引入）
- **scope**：ordinary cohabitation
- **confidence**：高
- **note**：丹麦同居分手**无强制财产分割成文法**——这是与瑞典（sambolag 分割）最根本的差异。**L2 全程 0，是"从未演进维度"的活例**

### L3 继承/遗属权：value=1（渐进多事件型，最典型的 DK 维度）

- **source**：CEFL（Inheritance Act §87-88；Administration of Estates Act §111a；Insurance Contracts Act §105a）+ borger.dk（遗属福利）+ Globe Advokater（继承税 2 年同居者 15% 档 vs 他人 36.25%）
- **effective date**：各法条不同时点（§87 遗嘱等同婚姻继承、§111a 遗属住房接管、遗属养老金——**具体引入年份待核**，CEFL 文件未标时间线）
- **scope**：ordinary cohabitation
- **confidence**：中高（权利内容确定；时间线待核）
- **note**：**无默认继承权**（与 SE 同）——但丹麦遗属保护是多条拼出：①Inheritance Act §87-88：同居者（同住 2 年或有共同子女）可立**遗嘱互继"as if they were spouses"**；②Estates Act §111a：遗属可**接管共同住宅+日用物**（付遗产估价现金，条件同前，且优先于其他继承人）；③Insurance §105a：满足条件者视为近亲受益人；④borger.dk：遗属自动获最多 3 个月国家养老金；⑤继承税：同住 2 年同居者 15% 档（vs 无关者 36.25%）——**实质遗属保护，但全部带"2 年/共同子女"条件**

### L4 税收/社保：value=1-2

- **source**：borger.dk（官方）：同居影响养老金计算（同居 vs 单身不同档）、遗属 3 个月自动福利；Eurofound 提及 tax/social 领域等同部分
- **effective date**：渐进（各领域政策分别演进——时间待核）
- **scope**：ordinary cohabitation
- **confidence**：中（官方确认养老金领域；税务等同范围待细核）
- **note**：社保领域同居者有实质接口（养老金计费、遗属福利自动），但非全面等同配偶——**L4(t) 本身可能是渐进的（多领域政策分时引入）**

### L5 亲子/家庭法：value=2

- **source**：丹麦儿童法体系（børneloven/forældreansvarsloven 改革——非婚生亲权平等的具体时间线待官方源核）
- **effective date**：渐进（20 世纪后半叶至 2000s 改革）
- **scope**：ordinary cohabitation
- **confidence**：中（框架确定；精确法律时间线待核——需升官方源）
- **note**：丹麦非婚生亲权平等为北欧共识性改革成果（待 Legifrance 式一手源确认精确年份）

## 二、DK 年度状态建议（分段函数草案，时间线待核后定稿）

| 维度 | 1975-? | ?-2000s | 当前 | 说明 |
|---|---|---|---|---|
| L1 | 0 | 0-1 | 0-1 | 无统一身份；各法条件性承认（无明确跃迁事件）|
| L2 | 0 | 0 | 0 | **全程 0（从未引入分割法）** |
| L3 | 0-1 | 1 | 1 | 遗属保护多法条渐进拼出（§87/§111a 等，时点待核）|
| L4 | 0-1 | 1 | 1-2 | 社保领域渐进（养老金计费/遗属福利）|
| L5 | 1 | 2 | 2 | 非婚生亲权平等渐进完成 |

**state_confidence**：L2=0 高（确实无）；L3/L4 的"何时从 0→1"**medium-low**（渐进政策无法定单日，需逐法查年份或标 uncertain）；L1 低-中。

## 三、DK 方法学产出（比分数更重要）

1. **DK 证明"渐进积累型" ≠ "高接口"**：v0.1 的 DK=3（受 Eurofound 描述误导）实际应为 ordinary scope (0-1, 0, 1, 1-2, 2)——丹麦同居者无财产分割、无继承，遗属保护靠多法条拼出且全带条件。**校准纠错价值再次体现。**
2. **L2 全程 0 是"维度从不演进"的对照案例**——证明 w_L(t) 各维独立，不是一维轴。
3. **渐进型的重建路径**：L3 是典型——多个法条（遗嘱等同婚姻 §87 / 住房接管 §111a / 保险 §105a / 遗属福利）各自引入时点构成 L3(t) 的分段依据；无法定单日的政策领域用 state_confidence=medium-low 标注，主回归排除或敏感性。
4. **与 SE/FR 形成第三种构型**：DK = 低-中接口的渐进拼图型（遗属靠条件性多法条，财产全程无接口）——区别于 SE automatic 与 FR registered/ordinary 双轨。

## 四、待核项（进正式 κ 前）

1. **L3 各法条引入年份**（§87 遗嘱等同婚姻继承、§111a 住房接管何时入法——关键时间线）
2. **L4 养老金同居计费与遗属福利的具体立法时间**（borger.dk 现行，历史演进待核）
3. **L5 丹麦非婚生亲权平等官方源**（对标 SE Government.se / FR Legifrance 标准——需丹麦官方/法院源）
4. 1989/2012 的同性 RP→婚姻时间线确认（红线排除的文档记录）
5. 第二编码员（Coder-B）

---

> 落盘目录：`D:\Contents\Research\Reports\2026-09-02_EGS应用落地假设集\`
> 模板：同 SE/FR 标准模板 + 渐进型 reconstruction protocol（逐维查事件、标 state_confidence）
> 状态：DK 初核完成（单编码员 frozen）；时间线待核；待 Coder-B + κ
