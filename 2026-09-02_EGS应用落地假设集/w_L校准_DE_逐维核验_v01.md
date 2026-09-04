# 六国校准：DE（德国）L1-L5 逐维法律核验（第五例 · 否定式/分散式制度压力测试）

> 日期：2026-09-02
> 定位：六国校准第五个样本——测试 **"无统一同居法 ≠ 无任何制度接口；分散式、判例式、否定式制度能否被稳定编码"**（用户定序 DE 🔜 作为最后一个大型压力测试）
> 编码单元规格：每格 {value, source, effective date, scope, confidence}
> 状态：单编码员初核（frozen single-coder case，按版本纪律待 Coder-B）
> 来源：Chambers Global 2026 Private Wealth（权威比较指南）+ Amt24 Sachsen（德国官方服务门户，引联邦司法部《Gemeinsam leben》手册）+ IAJ-UIM 2006 德国报告（国际法官协会）+ Damsté（荷兰德国法专家，逐项清单）+ Kapelle et al. SER 2025（德法同居财富溢价学术对照表，含制度比较）
> **核心结论先行：DE = 否定式构型——宪法保护的婚姻特权（GG Art.6.1）+ 逐领域"积极不立法/拒绝扩展"，ordinary cohabitation 接口接近全零；唯 L5 因 1998 儿童权利改革升至 2（归因儿童，非同居接口）。这是六国构型空间的最低接口端，且"零"是政策产物而非数据缺失——否定式制度同样可稳定编码。**

---

## 〇、DE 测试问题：分散式/判例式/否定式制度能不能稳定编码？

**SE 是"自动进入"、FR 是"registered/ordinary 双轨"、DK 是"多法条渐进拼接"、NL 是"registered 主导"——DE 攻击的是第五种形态**：

> 法律体系长期**积极维持婚姻特殊地位**（GG Art.6.1 对婚姻与家庭的特别保护，写进宪法），同时只在个别领域产生零散接口，且大量以"否定义务"（Bedarfsgemeinschaft 福利互助义务）而非"赋予权利"的形式存在。

**关键先验修正（v0.1 时对德国"分散式"的猜测被本轮证据替换为"否定式"）**：不是"有一些零散接口需要找"，而是"绝大多数领域被主动立法排除，接口接近全零"。这与 DK（渐进给接口）在机制上根本不同——**DE 的零是宪法/立法积极维持的状态，DK 的"历史 uncertain"是数据缺失**。编码上必须区分这两种"零"：
- **DE 型零（high confidence 持续零态）**：有明确宪法依据（GG Art.6.1）+ 立法史持续拒绝 + 法院维持——"零"本身是可靠的编码值
- **DK 型零（medium/low 历史 uncertain）**：可能只是没查到事件——不可当"已知恒定零"

**registered 路线的处理**：2001-08-01 LPartG（Lebenspartnerschaftsgesetz，注册生活伴侣）曾部分对齐配偶（§5 权利义务、§10 死亡后果、税务等同）——但**同性专属**，红线排除（不构成异性普通同居接口）；2017-10-01 同性婚姻合法后 LPartG 仅存续于未转换的旧伙伴。**德国历史上从未存在可供异性普通同居者使用的 registered 路线**——这是与 NL/FR 的结构性差异（他们至少给了一条登记路径，DE 连这条都没有，直接跳进婚姻）。

## 一、DE 逐维核验表（scope：ordinary cohabitation，nichteheliche Lebensgemeinschaft）

### L1 伴侣身份承认：value=0

- **source**：Chambers 2026（"mere cohabitation of a romantic couple does not give rise to any particular legal or tax consequences or rights"）+ Amt24（"unlike marriage or a registered civil partnership, the term is not defined by law"）+ IAJ 2006（宪法对婚姻家庭的特别保护阻止同等对待）
- **effective date**：全程无（1975-2021 恒定）——nichteheliche Lebensgemeinschaft 无法律定义、无登记制；术语首见于社会救助语境（Bedarfsgemeinschaft，属福利行政概念非身份）
- **scope**：ordinary cohabitation
- **confidence**：**高**（对"零"的高置信——否定式制度的稳定零态，宪法依据 GG Art.6.1）
- **note**：无任何全国性同居身份/登记；伴侣协议（Partnerschaftsvertrag）是合同法工具，非身份制度

### L2 财产/分割权：value=0

- **source**：Damsté（逐项："keine Verteilung von Zugewinn"无增益补偿、"keine Versorgungsausgleich"无养老金均衡、"kein Recht auf gemeinsame Nutzung von Wohnung und Hausrat"无共同住宅/动产使用权）+ IAJ 2006（"The couple is regarded in the same way as unrelated people. Each partner is entitled to the property he has had...as well as to those objects he/she acquires during the cohabitation"）+ Chambers 2026（"does not establish any matrimonial property law"）
- **effective date**：全程无。分手时无扶养/资本主张（IAJ："There are no claims to payment of maintenance or a capital sum between partners of cohabitation after breaking up"）——唯一例外：有共同子女时照护方对另一方有抚养请求权（§1615l BGB 类，属亲子法衍生非伴侣财产接口）
- **scope**：ordinary cohabitation
- **confidence**：**高**（多源一致，宪法依据明确）
- **note**：无 Zugewinnausgleich（婚姻增益补偿）→ 同居者财产完全分离，契约除外——比 FR concubinage 更彻底（FR 至少共同购买可形成共有，DE 是"视同无关人"）

### L3 继承/遗属权：value=0（§563 BGB 租约承继为边界 0-1）

- **source**：Chambers 2026（"does not...establish any...inheritance law position, such as entitlement to a compulsory share of an estate [Pflichtteil]"）+ Amt24（"your partner has no legal claim to the estate. The simplest form of protection...is a will...joint wills are reserved for married couples and same-sex couples [LPartG]"——**同居者连共同遗嘱都不能立，须各自立遗嘱**）+ Damsté（"kein gesetzliches Erbrecht"无法定继承、"keine Hinterbliebenenrenten"无遗属养老金）
- **effective date**：全程无继承法接口。**边界项**：§563 BGB——承租人死亡后共同居住的伴侣依法律加入租赁关系（Amt24 确认"becomes party to the agreement by operation of law"）——但这是**租赁合同承继**（契约关系延续，非遗产权益），与 DK Estates Act §111a 的"遗属对共同住宅的优先接管权益"不同
- **scope**：ordinary cohabitation
- **confidence**：**高**
- **note**：继承税无配偶档优惠（Chambers/Kapelle：视同无关人）。无遗嘱时同居者分文不得；遗嘱是唯一通道且被共同遗嘱规则压缩

### L4 税收/社保：value=0-1（逐项拆解——用户红线重点）

**三大"看似高实则零"逐项拆**（DE 最容易在此维度被高估，逐项核）：
- **联合报税**：0。无 Ehegattensplitting（配偶拆分课税）——同居者按个人独立课税（Amt24："The legislator assesses the income of spouses as joint income"仅限配偶；Kapelle 表：cohabitants "No benefits / Treatment similar to unmarried persons"）
- **法定医保家庭保险（Familienversicherung）**：0。同居伴侣不得纳入对方法定医保（Damsté："keine Aufnahme in die Familienversicherung der gesetzlichen Krankenversicherung"）——配偶/子女/2017 后 Lebenspartner 才可
- **法定养老险遗属金（Hinterbliebenenrente）**：0。同居者无遗属年金（Damsté 明确）；公务员遗属金亦无

**真正的零散接口（均为"条件性/义务侧/子女导向"，非自动权利）**：
- **2005 SGB II Bedarfsgemeinschaft**：福利法将同居者认定为"需要共同体"——相互供养义务（一方有收入则另一方福利减少/丧失）。Amt24 确认此术语语境。**这是义务不是权利**，但它是同居被官方承认进入制度计算的少数领域之一（Kapelle：marital status matters less 的领域——welfare 中已婚与同居同等供养义务）
- **Betreuungsunterhalt（照护抚养）**：照护共同未成年子女的非婚父母一方，分手后有抚养请求权（Amt24："A new provision...care maintenance for non-married persons who care for a joint child...up to three years"）——子女导向、条件性，属亲子法衍生接口（§1615l BGB 谱系）
- **Elterngeld/公共育儿支持**：与婚姻状态无关，仅以父母身份为条件（Kapelle）——归因"父母"非"同居"

- **value**：0-1。0 侧：三大税收/社保核心接口全零；1 侧：Bedarfsgemeinschaft（2005+，义务侧承认）+ 照护抚养（条件性）构成极弱正接口。**倾向主回归用 0**（"接口"语义是权利赋予，DE 的正接口几乎全在义务侧/子女侧），0-1 区间保留供敏感性
- **source**：Damsté + Amt24 + Kapelle SER 2025 + Chambers 2026。**effective**：2005（SGB II Bedarfsgemeinschaft 明确事件，使 L4 从 0 走向 0-1 的候选触发点）；照护抚养条款历史年份未单列（medium）
- **scope**：ordinary cohabitation
- **confidence**：高（现状规则多源核）；**note：SGB II 2005 为精确事件年，照护抚养条款精确引入年份待核（medium）**

### L5 亲子/家庭法：value=2（1998-07-01 后）｜1975-1997 为 1

- **source**：1998-07-01 **Kindschaftsrechtsreform（儿童权利改革）** 全面生效——废除婚生/非婚生区分，非婚生儿童法律地位与婚生儿童几乎完全平等（Amt24 现行体系 + 学界共识；SER/Kapelle 2025 确认亲子政策与婚姻状态脱钩）。亲权结构：婚生父母自动共同亲权；非婚生母出生即**单独**亲权；父须经 **Sorgeerklärung（亲权声明，双方同意，经 Jugendamt/公证）** 获共同亲权；2013-01-22 BVerfG 判决后父可在母拒绝时经家庭法院获共同亲权（符合儿童最佳利益且不与母权利冲突时）——2013 后父方路径大幅扩展
- **归因拆分（FR 教训正式应用）**：L5=2 是**儿童作为独立法律主体获得的普遍权利**（1998 Kindschaftsrechtsreform 是儿童权利立法，非"同居关系立法"）——非婚同居本身在 L5 上不提供任何接口（监护权与婚否/承认/法院令相关，与同居状态无关）。**因此 DE 的 L5=2 与 FR 的 L5=2 同源**：都是"国家普遍亲子法对非婚生儿童的保护"，不是 route 提供的接口。若按"route 提供接口"的严格语义，L5 应降权处理或在分析中单列归因
- **effective**：1998-07-01（明确事件，DE 少数可用离散跃迁）→ 2013（BVerfG 共同监护扩展，值不变 2）；1975-1997 段=1（战后渐进消除歧视——1969 Nichtehelichengesetz 等改善，但 1998 前仍非完全平等）
- **scope**：ordinary cohabitation（非婚生育家庭）
- **confidence**：高（1998 事件知名且有官方手册佐证）；**note：1975-1997 段的精确状态=1 是估计（medium），1969 起渐进改善但未平等**

## 二、DE 年度状态建议（供表 B 更新）

| 维度 | 1975-1997 | 1998 | 2005 | 2013 | 事件 |
|---|---|---|---|---|---|
| L1 身份 | **0** | 0 | 0 | 0 | 恒定零（宪法否定式）|
| L2 财产 | **0** | 0 | 0 | 0 | 恒定零（视同无关人）|
| L3 继承 | **0** | 0 | 0 | 0 | 恒定零（遗嘱唯一且共同遗嘱不可用）|
| L4 税收社保 | **0** | 0 | **0-1** | 0-1 | 2005 SGB II Bedarfsgemeinschaft（义务侧）|
| L5 亲子 | **1** | **2** | 2 | 2 | 1998-07-01 Kindschaftsrechtsreform |

- **编码类型**：L1/L2/L3 = 高置信恒定零（否定式制度，非历史 uncertain——零是政策产物）；L4 = 单事件弱跃迁（2005，medium）；L5 = 明确离散跃迁（1998，high）+ 2013 扩展（值不变）
- **state_confidence**：L1/L2/L3 high（对零）；L4 2005 前 high、后 medium；L5 1998 后 high、前 medium

## 三、DE vs 前四国：构型空间第五个成员

| 国家 | 构型 | ordinary scope | registered scope |
|---|---|---|---|
| SE | automatic | (2,2,1,2,2) 自动保护 | — |
| FR | route-split | (0-1,0-1,0,0,2) 弱 | PACS (2,1-2,1,2,1) |
| DK | gradual | (0-1,0,1,1-2,2) 渐进 | — |
| NL | registered 主导 | (0-1,0-1,0,1,2) 弱 | RP (2,2,2,2,1) |
| **DE** | **negative（否定式）** | **(0, 0, 0, 0-1, 2)** 全零+儿童权利 | **—（德国历史无异性可用的 registered 路线）** |

**DE 的三个方法学产出（比分数重要）**：
1. **"零"的两种语义被钉死**：DE 型零（宪法维持的否定式零，high confidence 可编码）≠ DK 型 uncertain（数据缺失，标 medium/low）。编码手册需加此区分——否则恒 0 会被误判为"数据没查到"
2. **否定式制度可稳定编码**：分散式/判例式/否定式不是障碍——恰恰相反，DE 的逐项拆解异常干净（每领域都查到明确的"无"及依据：Chambers/Damsté/IAJ 三源并列）。**"尺子能测出接近全零的形状"本身就是测量体系有效性的证据**
3. **L5 归因拆分第二次落地**：DE L5=2 与 FR L5=2 同源（儿童普遍权利），证明 L5 维度在跨国的"route 贡献"上可能是**独立的归因通道**——若 M1 要测"route 提供接口"，L5 需加权或单独分析（待六国齐后看 L5 与其他维的共变，即用户设定情形 A/B/C）

## 四、待核项（时间线收口）

- ①照护抚养（§1615l 谱系）精确引入年份（L4 的 medium 项）
- ②1969 Nichtehelichengesetz 到 1998 改革间的非婚生权利状态精确分段（L5 前段 medium）
- ③SGB II 2005 前福利法对同居的处理（Bedarfsgemeinschaft 前身）
- ④第二编码员（Coder-B 独立填表，κ 阶段）
- ⑤（窗口外）2017-10-01 同性婚姻——LPartG 衰亡，不影响异性普通同居接口

---

> 落盘目录：`D:\Contents\Research\Reports\2026-09-02_EGS应用落地假设集\`
> 模板：同 SE/FR/DK/NL 标准模板
> 状态：DE 初核完成（单编码员）；结构可标 provisional frozen（恒零维 high 置信），L4/L5 历史时间线待收口
