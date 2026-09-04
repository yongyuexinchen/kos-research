# 六国校准：SE（瑞典）L1-L5 逐维法律核验（第一例）

> 日期：2026-09-02
> 定位：w_L 五维化校准集的第一个样本（用户定序：SE → L1-L5 逐维核验）
> 编码单元规格（用户定）：每格 {value, source, effective date, scope, confidence}
> scope 取值：ordinary cohabitation（未登记同居）/ registered partnership / marriage-equivalent
> **source 升级（2026-09-02）**：瑞典政府官方页面 Government.se《Cohabitee relationships》（2025-04-08 发布）逐条验证 + CFR-CDF 2003 国别报告历史佐证。
> ⚠️ 本表为单编码员初核（AI 检索），**正式 κ 需第二编码员独立填表**。
> **状态：SE = (2, 2, 1, 2, 2) 措辞修正后冻结（v01 终版）**

---

## 〇、措辞修正记录（用户 2026-09-02 定，防过头表述）

| 维度 | 原表述问题 | 修正后表述 |
|---|---|---|
| L1 | "法定民事状态"过强 | **普通同居关系自动进入明确的法定保护范围，无需注册**——sambolagen 定义 cohabitee 并规定其保护，**不是**婚姻/RP 式独立登记身份 |
| L5 | "非婚生父母亲权平等"过头 | 非婚父母及子女有**完整亲子法律关系框架**，但部分权利（另一方家长身份、共同监护）**需额外确认，不与婚姻自动效力完全等同**；收养可保留但不反推"所有亲子权利自动等同婚姻" |
| L4 | confidence 可升 high | 维持 **medium-high**——多法律领域集合判断（租赁/税法/社保），不像 L2 可单法钉死 |

---

## 一、核验结论先行

**瑞典是"普通同居本身获较强保护"型的极端案例——但结构与 v0.1 总分 3 暗示的"全维度高水平"不符：**

| 维度 | value | 一句话结论 | 与 v0.1 总分 3 的偏差 |
|---|---|---|---|
| L1 身份承认 | **2** | **普通同居关系自动进入明确的法定保护范围，无需注册**——sambolagen 定义适用的 cohabitee 并规定相应保护，但不是婚姻/RP 式独立登记身份 | 符合（表述已修订）|
| L2 财产/分割 | **2** | sambolag 明确成文法：分手可强制分割，**但只覆盖共同住宅+日用物**（samboegendom），不含车辆/储蓄/度假屋/婚前财产 | 部分（范围窄）|
| L3 继承/遗属 | **1** | **无默认继承权（须遗嘱）**；遗属仅在死者遗嘱给他人时可请求分割+获配偶法定额一半 | **明显高估**（总分 3 暗示全面）|
| L4 税收/社保 | **2** | 税务与社会保险**多项将同居者等同配偶**（CFR 2003 原话）| 符合 |
| L5 亲子/家庭法 | **2** | 非婚生父母亲权平等（1970s-80s 改革）；sambo 可收养伴侣子女 | 符合 |

**SE 结构 = (2, 2, 1, 2, 2)，不是 (3,3,3,3,3)。** 活案例成立：总分 3 把"财产强、继承弱"的制度结构压扁成全面高水平——L3 的实际缺口（同居伴侣无继承权）正是 M1 里"制度接口未开全"的精确含义。

## 二、SE 逐维核验表（编码单元规格）

### L1 伴侣身份承认：value=2

- **source**：Government.se《Cohabitee relationships》（2025-04-08，一手官方）：sambolagen 定义 cohabitee（永久同居+夫妻般关系+共同家庭，无性别限制）+ CFR-CDF 2003（SFS 2003:376 生效 2003-07-01 取代 1988 法）
- **effective date**：1987（首部同居法，异性）→ 1988（同性分法）→ **2003-07-01**（统一为 Cohabitees Act，性别中立）
- **scope**：ordinary cohabitation（**未登记即自动适用**——进入婚姻式同居关系即触发，非登记制）
- **confidence**：高（官方成文法 + 政府页面双源）
- **note**（措辞修正后）：**普通同居自动进入明确的法定保护范围，无需注册**——sambolagen 是"适用即保护"型，不是婚姻/RP 式登记身份

### L2 财产/分割权：value=2

- **source**：Sambolag 2003:376（samboegendom 定义）；CFR-CDF 2003（"joint home and joint household goods 均分"）；律师实务源 d-jur.se（范围细节）
- **effective date**：1987（首法）→ 2003（统一，范围明确化）
- **scope**：ordinary cohabitation
- **confidence**：高
- **note**：**范围窄**——仅"共同住宅+日用物"（为共同使用取得），**不含**车辆/度假屋/银行储蓄/个人账户/婚前财产；分手可要求强制分割（bodelning）；samboavtal 可排除

### L3 继承/遗属权：value=1（v0.1 高估的关键维度）

- **source**：Government.se（2025 官方黑体原话：**"Cohabitees do not inherit from each other unless they make a will specifying this"**）+ 遗属"lilla basbeloppsregeln"（Social Insurance Code 下遗属恒得两个价格基数，部分对应婚姻的 base amount rule）+ CFR-CDF 2003
- **effective date**：持续现状（无变革事件——1995 同性 RP / 2009 同性婚姻均不涉异性同居继承扩展）
- **scope**：ordinary cohabitation
- **confidence**：高（官方原文）
- **note**：**无默认继承权（须遗嘱）**；遗属保护有限：死亡时仅遗属可请求分割，且 Social Insurance Code 提供相当于两个价格基数的遗属补偿（对应婚姻 base amount rule 的部分，非全额）——微弱遗属待遇，非继承权

### L4 税收/社保：value=2（confidence 维持 medium-high）

- **source**：Government.se（2025 官方原话："rules in the **Tenancy Act, Sweden's tax acts, and the social security rules** that **equate cohabitees with spouses**, especially when cohabitees have children together"）
- **effective date**：渐进（多法条，无单一事件）；1987 后逐步
- **scope**：ordinary cohabitation
- **confidence**：medium-high（政府页面确认多领域等同，但为集合判断非单法可钉死——不升 high）
- **note**：租赁法/税法/社保规则把同居者等同配偶，**尤其共同育有子女时**；瑞典为个人课税制（无联合申报），等同体现在社保/租赁多项

### L5 亲子/家庭法：value=2（注释收紧，措辞修正后）

- **source**：Government.se《Cohabitee relationships·Children of cohabitees》+《About children》（2025 官方）：未婚父母**另一方家长身份必须专门建立**（acknowledgement/法院判决）；母亲出生即**单独监护**，联合监护经共同通知取得（常与亲权确认同时、出生 14 天内可通知）
- **effective date**：1970s-80s（非婚生亲子框架改革渐进）；sambo 收养伴侣子女为现代扩展
- **scope**：ordinary cohabitation（非婚生育家庭）
- **confidence**：中高（政府页面确认框架；具体历史时间线仍需 Föräldrabalken 条文核）
- **note**（措辞修正后）：非婚父母及子女有**完整亲子法律关系框架**，但部分权利（另一方家长身份、共同监护）**需额外确认，不与婚姻自动效力完全等同**——同居者可收养伴侣子女（条件满足时），但不反推"所有亲子权利自动等同婚姻"

## 三、关键审计发现

1. **SE 制度是"普通同居自动保护"型（无登记门槛），与 NL/FR 的"登记型"根本不同**——即便 NL/FR/SE 总分相近，scope 机制差异意味着对 G_eff 的含义不同（SE：同居即获保护；NL/FR：须登记）。支持五维之外还需 scope 字段的审计价值。
2. **L3 是 SE 的短板**：无继承权是"接口未开全"的实证——若瑞典家庭选择同居（非婚生育高、婚姻率低），"死亡后无继承保障"是制度接口的实际缺口，M1 的 w 不应把它记成全面。
3. **总分 3 → SE (2,2,1,2,2)**：如果 summary 用简单均值 = 9/10=1.8（若用 0-3 scale），与 FR 的 PACS (需逐维核) 可能撞分，但结构完全不同——正是"先存结构再压缩"的理由。
4. **1995 瑞典同性 RP / 2009 同性婚姻都不计入**：同性专属制度不构成普通同居接口（RP 已废止转婚姻，同性婚姻不影响异性同居接口）——编码红线在 SE 案例中自动执行。

## 四、SE 冻结声明（用户 2026-09-02 定稿）

$$
\boxed{SE = (2, 2, 1, 2, 2)}\quad\text{冻结}
$$

**它的核心价值不是向量本身，而是：**

$$
(2,2,1,2,2) \neq (3,3,3,3,3)
$$

v0.1 的总分 3 把**继承这一重要制度接口缺口隐藏掉了**（L3=1：同居无默认继承权须遗嘱）。同时官方材料证明 scope 差异是真实的制度机制差异：**瑞典普通同居自动触发 sambolagen（无需登记），与法国 PACS、荷兰 registered partnership 的登记制不是同一种制度路径**——scope 强制字段的必要性获一手来源确认。

**六国校准的真正目标（用户定）**：不是"六国各打一个 w 分数"，而是**看六国是否产生不同的 L1-L5 配置**——SE 给出第一种 (2,2,1,2,2)；若 FR/NL/DK/DE 各得不同结构，即获得**制度接口的经验构型空间**。届时是否压缩成单一 w_L 反而是次要问题。**六国完成前不因单个国家的"漂亮总分"锁死测量结构。**

## 五、版本纪律（frozen single-coder case，用户 2026-09-02 定）

SE-v01 已冻结为**单编码员初核表**。后续若第二编码员对 L3/L5 等提出不同值（如 L3=0、L5=1），**不直接修改本冻结表**。修订走独立流程：

```
SE-v01 frozen（本表）
↓  Coder-B independent（独立填表，不参照本表）
↓  disagreement table（两表差异清单）
↓  source adjudication（差异格回法律源仲裁）
↓  SE calibration record v02（仲裁后版本，保留 v01 供追溯）
```

否则 κ 无法追溯"原始编码 vs 仲裁后编码"之间发生了什么。

## 六、SE 年度状态建议（供表 B 更新，待 κ 后定稿）

| 年份 | L1 | L2 | L3 | L4 | L5 | 说明 |
|---|---|---|---|---|---|---|
| 1975-1986 | 0 | 0 | 0 | 0 | 1? | L5 亲权平等渐进起点待核；其余无成文接口 |
| 1987-2002 | 1 | 1 | 0 | 1 | 2 | 首部同居法（异性）；范围有限 |
| 2003-2021 | 2 | 2 | 1 | 2 | 2 | Sambolag 统一生效 |

**state_confidence**：2003+ = high（成文法）；1987-2002 = high（1987 首法）；1975-1986 = **low-medium**（判例/惯例待核——不可倒推，先标 uncertain）

## 五、待核项（进正式 κ 前）

1. L5 的亲权平等的**具体法律时间线**（Föräldrabalken 1976/1980s 条文）——中置信
2. 1987 前瑞典 sambo 是否已有判例性财产保护（影响 1975-1986 段 L2）
3. L4 社保"等同配偶"的具体法条清单（影响精确 effective date）
4. 第二编码员独立填表 → weighted κ

---

> 落盘目录：`D:\Contents\Research\Reports\2026-09-02_EGS应用落地假设集\`
> 模板：本文档为六国校准的标准模板——FR/DK/NL/DE/SI 按同一结构逐国核验
> 状态：SE 初核完成（单编码员）；正式 κ 待第二编码员
