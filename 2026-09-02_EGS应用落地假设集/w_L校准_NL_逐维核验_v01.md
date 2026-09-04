# 六国校准：NL（荷兰）L1-L5 逐维法律核验（第四例 · registered/ordinary 趋同测试）

> 日期：2026-09-02
> 定位：六国校准第四个样本——测试 **registered partnership 与 ordinary cohabitation 是否高度趋同**（回应 FR 建立的 scope≠country 原则）
> 编码单元规格：每格 {value, source, effective date, scope, confidence}
> 状态：**calibration structure provisionally frozen**（结构/scope split/RP 继承已定；L4_ordinary/L5_ordinary 官方源本轮升级后待 Coder-B 复核，正式 κ 前不再开放结构）
> 来源：INED LawsAndFamilies 数据库（K. Waaldijk 等主编，权威比较源）+ DSP 1999《Registered Partnership in the Netherlands》+ **Rechtspraak（荷兰司法机构官方）+ sdg.government.nl（荷兰政府服务官方）+ SVB（社会保险银行官方）+ PME/PGB 养老金基金官方**（本轮升级）+ XPAT（实务）+ Wikipedia（交叉，仅日志档）
> **核心结论先行：NL = registered 主导型——RP 与婚姻几乎全同（含法定继承权=2，强于 FR PACS），而 ordinary cohabitation 是另一个世界（无继承、无自动财产）——两 scope 严重分离。**

---

## 〇、scope 分离判定：ordinary cohabitation ≠ registered partnership（NL 答案：几乎完全不同）

| scope | 结构 | 与婚姻的差距 |
|---|---|---|
| **registered（1998 起，异性+同性）** | ~(2, 2, 2, 2, 1) | 与婚姻几乎全同：共同财产、**法定继承权**、税务/养老金同——主要例外在子女（RP 出生只与生母建立亲子）|
| **ordinary（samenwonen，未登记）** | ~(0-1, 0-1, 0, 1, 2) | 另一世界：无共同财产（除非共同购）、**无继承权**、samenlevingscontract 公证契约仅有限福利 |

**回答测试问题**：NL 的 RP 与 ordinary **不是趋同而是严重分离**——NL 属于 **registered 主导型**（ordinary 弱）。且 NL RP 的 L3=2（法定继承）显著强于 FR PACS 的 L3=1（无继承）——**registered 路径内部也不齐**，进一步支持五维+scope 分格。

## 一、NL 逐维核验表

### L1 伴侣身份承认

- **registered**：value=2。Geregistreerd partnerschap 1998-01-01 生效（Book 1 Civil Code），异性+同性皆可（设计给同性，异性亦用——1999-2001 约 1/3 为异性）。source：DSP 1999 + INED。effective：1998-01-01。confidence：高
- **ordinary**：value=0-1。无登记同居身份；samenlevingscontract（同居契约，公证）非身份但法院尊重其安排。source：INED + Wikipedia。confidence：高

### L2 财产/分割权

- **registered**：value=2。无契约时**默认共同财产制**（与婚姻同，Art. 93-94 Book 1）；2018-01-01 起婚前财产私有化（婚姻与 RP 同步改法）。source：INED + XPAT。effective：1998（共同财产）→2018（婚前私有改）。confidence：高
- **ordinary**：value=0-1。**无共同财产制**（同居不自动产生，INED 明确 No）；共同购买可得共有；契约可约定。source：INED（"Cohabitants do not have community of property by virtue of cohabiting"）。confidence：高

### L3 继承/遗属权

- **registered**：value=**2**。RP 是**法定继承人**（Art. 10 Book 4 Civil Code；INED 2015 Yes，1998 起）——继承/继承税与婚姻同（DSP：rules same as marriage）。source：INED + DSP。effective：1998-01-01。confidence：高。**note：这是 NL 与 FR（PACS L3=1）的关键差异——NL RP 有法定继承**
- **ordinary**：value=0。同居者无继承权（INED 2015 No；非婚伴侣死亡不是 heir）；samenlevingscontract 不能创设继承，须遗嘱。source：INED + Wikipedia。confidence：高

### L4 税收/社保

- **ordinary**：value=1。**接口为"条件性/登记驱动"，非自动配偶式待遇**（官方逐项核）：
  - **AOW（基础养老金）**：未婚同居者若满足共同分担 household 费用 / 有共同（认领或亲生）子女 / 有同居协议 / 过去结过婚或注册伴侣 → 按"与另一成人同住"档领取（**低于独居档**——这是 household 合并处理，非配偶式补贴）（source：SVB 官方 AOW 规则页）
  - **partner pension（补充养老金遗属金）**：同居者**须自行向基金登记**（婚姻/RP 自动，同居不自动）方获遗属养老金；登记后自动成为 fiscal partners 可联合报税（source：PME/PGB 官方）
  - **fiscal partnership**：条件可得（共同子女/注册同居/公证同居协议/登记等），非自动
  - source：SVB + PME/PGB（官方一手，替换 Wikipedia/XPAT）。confidence：高（现状规则）；**note：AOW 同居规则与 fiscal partner 认定规则的历史引入年份未逐条核（medium）——年度分段待补**
- **registered**：value=2。税务/养老金与婚姻同（DSP：rules in principle same；遗属养老金可能略低于配偶——minor gap）。source：DSP。effective：1998 起渐进趋同（2001 前后修正）。confidence：中高

### L5 亲子/家庭法

- **ordinary**：value=2（维持）。**官方源升级完成**：荷兰非婚生亲权框架完整——
  - 非婚父/co-mother 经 **erkenning（承认）** 成为法律父母：需母亲同意（子 16+ 除外）、子 12+ 需书面同意等（source：sdg.government.nl 官方，引 BW Art. 1:203）
  - **亲权（ouderlijk gezag）**：婚姻/注册伴侣父母**自动联合亲权**；非婚父母 2023-01-01 后承认子女的**自动联合亲权**（2023 立法修正，废除法院申请程序）；2023-01-01 前承认的需申请（表单或法院程序）；母亲出生即自动（单独）亲权（source：Rechtspraak 官方英文页，逐条列出例外情形）
  - **归因拆分（FR 教训应用）**：L5=2 是荷兰**总体亲子法对儿童的普遍保障**（erkenning 制 + 亲权可及），非"同居关系本身提供的接口"——同居状态与亲子接口无直接因果；非婚父须 erkenning（需同意）而婚内自动，属"部分权利需额外确认，不与婚姻自动效力完全等同"（与 SE L5 注释同口径）
  - effective：1970s-2010s 渐进（erkenning 制）→ **2023-01-01（自动联合亲权——窗口外 >2021 事件，主回归不触发，记分段待扩展点）**。confidence：**高**（Rechtspraak + sdg.government.nl 一手，替换待核）
- **registered**：value=1。**RP 出生只与生母建立亲子**（不自动双亲——与婚姻的关键差异）；可经认领/共同监护申请/收养建立。source：DSP（明确）。confidence：高

## 二、NL vs 前三国：构型空间第四个成员

| 国家 | 构型 | ordinary scope | registered scope |
|---|---|---|---|
| SE | automatic | (2,2,1,2,2) 自动保护 | —（无独立 RP 供异性）|
| FR | route-split | (0-1,0-1,0,0,2) 弱 | PACS (2,1-2,1,2,1) |
| DK | gradual | (0-1,0,1,1-2,2) 渐进低-中 | —（1989 RP 同性专属）|
| **NL** | **registered 主导** | (0-1,0-1,0,1,2) 弱 | **RP (2,2,2,2,1) 近婚姻全同** |

**关键对照**：NL RP 的 L3=2（法定继承）vs FR PACS 的 L3=1（无继承）——证明**"registered"不是同质范畴**，制度接口分维必须在 scope 内部继续细化。这对 A_j×w_j 的含义：即使同是 registered 路线，w_L3 的取值差异（1 vs 2）会真实改变 A×w 的效应。

## 三、NL 年度状态与待核项

- **registered scope 起始**：1998-01-01（明确事件——L1/L2/L3 同时 0→X）；2018 财产改法影响 L2 分段（若按默认制严格编码）
- **L4_ordinary 历史分段待核**：AOW 同居档/fiscal partner 认定规则的引入年份（现状规则官方已核 high，历史时间线 medium）
- **L5 窗口外事件已记**：2023-01-01 非婚父母自动联合亲权（主窗口 1975-2021 不触发；若扩展窗口需在表 B 加跃迁）
- **待核**：①L4_ordinary 历史时间线（AOW 同居规则引入年）；②samenlevingscontract 法律地位精确范围（是否入 L1/L2 的 0-1）；③第二编码员（Coder-B 独立填表）

---

> 落盘目录：`D:\Contents\Research\Reports\2026-09-02_EGS应用落地假设集\`
> 模板：同 SE/FR/DK 标准模板
> 状态：NL 初核完成（单编码员 frozen）；L5/L4 待官方源核；待 Coder-B + κ
