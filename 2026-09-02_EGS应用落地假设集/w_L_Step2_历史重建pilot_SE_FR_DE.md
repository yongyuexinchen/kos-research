# w_L Step 2：历史 reconstruction pilot（SE / FR / DE）— event→state 引擎首次运行

> 日期：2026-09-02
> 定位：从"2021 横截面可稳定编码"推进到"同一国家在不同时间点可稳定重建"（temporal reconstructability）——按用户定序，第一批 SE/FR/DE 三国（事件密度低→高、规则最清楚者先上），DK/NL/SI 第二批
> 规则：严格冻结 v0.3（`w_L_codebook_v03_rule_refinement.md`）：w_R=f(L1-L4)，C_child 单列；D2/D3/R5 生效；unknown 进 uncertain 不得当 0、不得前推
> 时间窗口：1975-2021（对齐已落地的 A1/Y panel_raw_YA）
> 引擎规范：L_k(t) = x_0 (t<t₁) → x₁ (t₁≤t<t₂) → ...——每次状态变化必须追溯到 legal event → effective date → scope → new state

---

## 〇、Pilot 的三个测试目标

| # | 测试 | 对应国家 |
|---|---|---|
| T1 | 单一强事件能否干净分段 | SE（2003 Cohabitees Act）|
| T2 | 路线分裂 + 制度事件能否在 route 维度展开 | FR（ordinary 恒低 vs PACS 1999 出现 + 2007 财产改）|
| T3 | 否定式长期稳定 + 普遍权利跃迁的分离 | DE（L1-L4 恒 0 vs C_child 1998/2013）|

**Pilot 的隐藏目标**：暴露**哪几维的时间线无法在现有证据下重建**（temporal uncertain）——这比"填出完整面板"更重要，因为 v0.3 规则明确禁止用 2021 值前推。

---

## 一、SE 瑞典（T1：单一强事件）

### 1.1 Event→State 引擎表（route：ordinary cohabitation / sambo）

| 维度 | 分段 | 事件 → 生效 → scope → 新值 | confidence |
|---|---|---|---|
| L1 身份 | 1975-1986: **0** | 无成文 sambo 法；判例萌芽（sambo 概念渐进 1980s 前）| medium-low（判例演进无精确节点）|
| | 1987-2002: **1** | 首部 sambo 法（1987/88，覆盖共同住宅财产）→ sambo 获得有限法定地位 | medium（CFR 转述年份）|
| | 2003-2021: **2** | Cohabitees Act（sambolag 2003:376）2003-07-01 生效 → 性别中立、同居自动适用、保护扩展 | high（Government.se + CFR）|
| L2 财产 | 1975-1986: **0** | 无 samboegendom 法定分割基础 | medium-low |
| | 1987-2021: **1** | 首部法起 samboegendom 分割；2003 统一后仍 narrow（仅共同住宅+日用物）→ v0.3 D2 判 1 恒定 | high（D2 锚例）|
| L3 继承 | 1975-1987: **0-1** | 无默认继承；遗属微补偿规则（lilla basbeloppsregeln）引入年份待核 | medium-low（uncertain）|
| | 1988-2021: **1** | 遗属微补偿（死者遗嘱给他人时遗属可请求分割共同住宅+配偶法定额一半）| medium（CFR 2003 确认现代状态；精确起点待核）|
| L4 税/社保 | 1975-2002: **NA（temporal uncertain）** | 部门法渐进等同无单一事件；现有证据无法重建精确分段 → **标 uncertain 不填、不前推** | — |
| | 2003-2021: **2** | Government.se 确认税/社保多项等同配偶（现代状态，非"2003 才立法"——起点仍未知）| high（现代）/ low（归因年份）|
| C_child | 1975-2021: **2** | 非婚生儿童平等 1970s 基本完成（北欧先锋）；本窗口内无跃迁 | medium-high（窗口前完成）|

### 1.2 SE Pilot 读数

- **T1 通过**：2003 是干净的单点（L1 0→1→2 的三段式在 SE 完美运行）
- **暴露的卡点**：L4 是**时间线不可重建维**（部门法渐进、无单一事件）——SE-L4(t) 只能给 2003+ 的"已知近期状态"，1975-2002 必须 NA。**这正是用户"不得前推"规则要防的**，也是 DK 渐进型问题的预演
- 小问题：L3 的 1988 起点与 L4 归因年份（2003 非立法年）都是 medium/low——时间线收口项 +2

## 二、FR 法国（T2：路线分裂 + 制度事件）

### 2.1 Event→State 引擎表

**route A：ordinary cohabitation（concubinage）**

| 维度 | 分段 | 事件 → 生效 → scope → 新值 | confidence |
|---|---|---|---|
| L1 身份 | 1975-1998: **0-1** | concubinage notoire 判例承认（无成文）；判例效果零散 | medium-low |
| | 1999-2021: **0-1** | 1999-11-15 法给 concubinage 法定定义（"稳定持续同居"）——但无实质保护权（v0.3 F2 仲裁候选：定义算不算接口）| medium |
| L2 财产 | 1975-2021: **0** | v0.3 R5：共同购不动产共有=普通物权非接口 | high（恒定零）|
| L3 继承 | 1975-2021: **0** | 无继承资格、遗赠 60% 税视同陌生人 | high（恒定零）|
| L4 税/社保 | 1975-2021: **0** | 无联合申报、无配偶式待遇 | high（恒定零）|
| C_child | 1975-2000: **1** | 1972 filiation 改革后非婚生母权确立，但继承等领域仍有差异 | medium |
| | 2001-2005: **1-2** | Mazurek ECHR 判决（2001-02-01）+ 2001-12-03 法：非婚生继承权修正 | medium（ECHR 日期）|
| | 2006-2021: **2** | ordonnance 2005-759（2006-07-01 生效）：全面取消婚生/非婚生区分 | high |

**route B：registered（PACS）——用户点名测试 1999→2007**

| 维度 | 分段 | 事件 → 生效 → scope → 新值 | confidence |
|---|---|---|---|
| L1 | 1975-1998: **不存在（route 未创建）** | PACS 1999 前无法定登记路线 | — |
| | 1999-2021: **2** | PACS 创设（1999-11-15 法）：登记制身份，异性+同性 | medium（生效年份）|
| L2 | 1999-2006: **2** | PACS 默认财产 indivision（共同制）| medium |
| | 2007-2021: **1** | 2007 改法：默认 séparation des biens（分离制），可选共同 → 自动共同接口消失 | high（Notaires 确认）|
| L3 | 1999-2021: **1** | PACS 无自动继承（须遗嘱）+ 住房遗属一年 + 继承税豁免 | high |
| C_child | （与 ordinary 同——儿童权利与国家 route 无关）| | |

### 2.2 FR Pilot 读数

- **T2 通过且产出最有信息量的结构**：FR 的 **route 分裂在时间轴上展开**——ordinary 46 年恒低 (0-1, 0, 0, 0)（1999 定义是唯一微调），PACS 是 1999 年凭空创建的独立制度（且 2007 财产默认制翻转）
- **关键方法学发现**：A 数据（非婚生育/同居规模）在 FR 主要是 ordinary route 的行为，而 w 若取 PACS 值是**时间上也在错配**（不是只有横截面 mismatch——1999 前 PACS 不存在、2007 财产制翻转只影响登记伴侣）——Route-Consistency Axiom 的**时间维度**显形
- C_child 是三国里唯一有三级跃迁的（1→1-2→2）：1972 母权 / 2001 继承 / 2006 全面——"普遍权利演进"的完整叙事

## 三、DE 德国（T3：否定式稳定 + 普遍权利跃迁分离）

### 3.1 Event→State 引擎表（route：ordinary cohabitation）

| 维度 | 分段 | 事件 → 生效 → scope → 新值 | confidence |
|---|---|---|---|
| L1 身份 | 1975-2021: **0** | 恒定零：宪法 GG Art.6.1 婚姻特权 + 无同居立法 + 无异性的 registered 路线 | **high（负零态时间稳定）** |
| L2 财产 | 1975-2021: **0** | 恒定零：无 Zugewinn / 视同无关人 | high |
| L3 继承 | 1975-2021: **0** | 恒定零：无法定继承 / 无遗属金 / 共同遗嘱不可用 | high |
| L4 税/社保 | 1975-2021: **0** | v0.3 R5 后恒定零：2005 SGB II Bedarfsgemeinschaft 为义务侧不计接口；照护抚养子女导向 | high |
| C_child | 1975-1997: **1** | 1969 Nichtehelichengesetz 后改善但未平等（继承等仍受限）| medium |
| | 1998-2021: **2** | 1998-07-01 Kindschaftsrechtsreform：废除婚生/非婚生区分，全面平等 | high |
| | （2013 BVerfG：父可诉共同监护——值不变，记录为扩展事件）| | |

### 3.2 DE Pilot 读数

- **T3 通过且是 pilot 最干净的一例**：L1-L4 恒 0 全程（high confidence 负零态 46 年时间稳定），而 C_child 1998 单点跃迁
- **"关系接口演进 vs 普遍权利演进"两过程分离的实证**：DE 的关系接口 46 年**零演进**（宪法维持），普遍权利 1 次大跃迁（1998 儿童立法）+ 1 次扩展（2013 监护）——若把两者压成一个 w_L 总分，这条分离完全不可见。用户 F3 判断的直接兑现
- DE 的 1998/2005/2013 三节点里，**只有 1998 落在 C_child**，2005（SGB II）被 R5 判为不计接口、2013 是 C_child 值内扩展——**三节点没有一个落在 w_R 上**，证明 DE 的路由接口与普遍权利几乎正交

---

## 四、Pilot 面板 CSV（`wR_pilot_SE_FR_DE.csv`）

生成规则：
- 键 = (country, route, year)，year ∈ 1975-2021
- L1-L4 存 v0.3 离散值；区间格存 "0-1"；**temporal uncertain 存 NA**（SE-L4 1975-2002）
- C_child 单列
- 文件：`data_obsbridge/wR_pilot_SE_FR_DE.csv`

## 五、Pilot 结论与卡点清单

**通过**：
- T1（SE 单强事件三段式）、T2（FR route 分裂时间展开 + PACS 2007 翻转）、T3（DE 负零态稳定 + 两过程分离）全部运行成功
- 引擎规则（event→effective date→scope→new state）可执行且无一处"用 2021 前推"

**Temporal reconstructability 卡点（如实记录，不填）**：
1. **SE-L4**（部门法渐进无事件）：1975-2002 标 NA——渐进型维度的历史重建是 pilot 暴露的最大方法学缺口（DK 第二批会放大）
2. **SE-L3 起点 / SE-L4 归因年份**：medium/low 待收口（时间线项）
3. **FR PACS 生效精确日**（1999-11-15 法 vs 部分条款 2000）：medium
4. **FR 1975-2000 C_child=1 的边界**：1972 改革后至 2001 间仍有差异，具体差异清单未核

**两过程分离的 pilot 级确认**：DE（w_R 恒 0 / C_child 1 次跃迁）与 FR（w_R-ordinary 恒低 / C_child 3 级跃迁）证明——**关系接口与普遍权利在时间上是独立过程**，分开建模比混合分数信息量大

## 六、下一步

1. 第二批 DK / NL / SI（渐进型多法条 / route 分裂+制度事件 / 跨政体连续性）——重点攻击 SE-L4 暴露的渐进型时间线缺口
2. 时间线收口项（SE-L3/L4、FR PACS 生效、C_child 边界）逐项核
3. 三国 pilot 通过后，将引擎推广到全 27 国 panel（2021 窗口值 + 事件年表）

---
> 落盘目录：`D:\Contents\Research\Reports\2026-09-02_EGS应用落地假设集\`
> 面板：`data_obsbridge/wR_pilot_SE_FR_DE.csv`
