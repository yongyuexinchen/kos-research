# 六国校准：FR（法国）L1-L5 逐维法律核验（第二例）

> 日期：2026-09-02
> 定位：六国校准第二个样本——与 SE 形成第一组结构对照（SE automatic vs FR registered）
> 编码单元规格：每格 {value, source, effective date, scope, confidence}
> 状态：**calibration structure frozen**（FR ✅）；L5 source 已升级 Legifrance+政府 CRC 报告（百度源移除）；ordinary scope final coding = 0-1
> 来源：Notaires de France（官方）、ONCP 法国公证人协会、英国高等法院 2024 专家报告、Fremeaux & Leturcq EJPop 2022（A 级学术）、Legifrance（ordonnance 2005-759）、法国政府 UN CRC 报告、INSEE
> ⚠️ 单编码员初核（frozen single-coder case，按 SE 版本纪律待 Coder-B）

---

## 〇、核验结论先行——FR 必须 scope 分格 + route-consistent measurement（计量识别红线）

**法国的法律接口集中在 PACS（registered pathway），普通未登记同居（concubinage）的正式制度接口非常有限（非零：共同购买不动产可共有、部分债务/住房事项有法律后果）。**

| scope | 结构 | 一句话 |
|---|---|---|
| **registered（PACS）** | ~(2, 1-2, 1, 2, 1) | 登记路径：共同申报/社保等同、住房遗属一年、**无自动继承但继承税豁免** |
| **ordinary cohabitation（concubinage）** | ~(0-1, 0-1, 0, 0, 2) | **正式接口非常有限**：各自独立、继承税 60%、无共同申报；共同购买不动产可共有、部分债务/住房有法律后果（非完全无效果）|

### 核心发现 1：route scope mismatch（正式升级为数据规范，见 P0 v0.2 第九节）

法国现实中大量伴侣进入 union libre（未登记同居）而非 PACS——INSEE：2011 年约 720 万人在 union libre vs PACS 伴侣约 140 万；2011-2014 平均每年约 54.6 万新 union libre（超婚姻+PACS）。因此：

$$
A_{\mathrm{observed}} \neq A_{\mathrm{route\ covered\ by}\ w}
$$

若用 A=非婚生育比例 × w=PACS 制度化，实际在估计 **A_mostly ordinary × w_mostly registered**——不干净的 M1 乘法。**A_j 与 w_j 必须属于同一替代路线**（route-consistent measurement）：FR 应拆两个 treatment——A_cohab↔w_cohab 与 A_PACS↔w_PACS，不得 A_nonmarital↔w_PACS 直乘。这使"RP≠ordinary cohabitation"从编码红线升级为**计量识别红线**。

### 核心发现 2：L2(t) 是 event→state 的完美案例（2007 regime change）

PACS 财产默认制在 2007 前后不同：t<2007 默认 indivision（共同）；t≥2007 默认 séparation des biens（分离），可选 indivision。**L2(t)=f(2007 regime change)**——FR 不是单一分数，年度 w 面板在此有真实法律事件基础（支持 event→state 做法）。

### 核心发现 3：FR calibration 完成（成果=三个结构发现，不是"FR=2"）

FR 初核的产出记录为：①ordinary/registered scope split；②route-consistent A×w requirement；③1999（PACS 创设）/2007（财产制切换）法律事件造成的状态分段。

## 一、FR 逐维核验表

### L1 伴侣身份承认

- **registered（PACS）**：value=2。PACS 是 1999-11-15 法创设的登记契约（2000-01 生效；市镇厅/公证人登记），异性+同性，明确法律身份。source：Notaires de France（"contract...allows them to plan their life together"）+ EJPop 2022。effective：1999（法）/2000（生效）/2007（财产默认改分离制）。confidence：高。scope：registered partnership
- **ordinary cohabitation（concubinage）**：value=0-1。未形成独立登记身份，普通同居的**正式制度接口非常有限**；部分财产、共同购买和其他特定事项仍产生法律效果（如共同购不动产可共有、部分债务/住房事项）——非"完全无效果"。source：Notaires de France（vie maritale/concubinage 页）+ EJPop 2022。effective：n/a（无统一登记制度）。confidence：高。scope：ordinary cohabitation

### L2 财产/分割权

- **registered（PACS）**：value=1-2。PACS 2007 起默认**分别财产制**（1999-2006 曾默认共同取得制），可契约选共同（indivision）；分手无补偿（PACS 无离婚补偿/扶养——专家报告："no financial claims...upon dissolution"）。source：Notaires + ONCP + 专家报告。effective：2007（默认改分离）。confidence：高。**note：法国 PACS 财产接口弱于瑞典 sambo 的强制分割——分手各留各的，仅共同购部分平分**
- **ordinary cohabitation**：value=0。无分割机制，除非共同购买并登记共有。source：EJPop（"No asset sharing, unless bought together"）。confidence：高

### L3 继承/遗属权

- **registered（PACS）**：value=1。Notaires 原话："**the partners are not heirs of each other**...must make a will"；遗属仅：租赁转移 + 死亡后可在共有住宅免费居住一年（死者单独所有时）；**有遗嘱时免继承税**（vs 同居者 60% 税率视同陌生人）。source：Notaires + 专家报告。effective：1999-2000。confidence：高
- **ordinary cohabitation**：value=0。同居者无继承权且**继承税 60%**（法律视同陌生人）；仅遗嘱可救济。source：专家报告（"cohabitees pay inheritance tax at 60% as they are considered as strangers"）。confidence：高

### L4 税收/社保

- **registered（PACS）**：value=2。PACS 注册即**共同申报**（与已婚相同，EJPop 表）；社保等同已婚（专家报告："social security cover equivalent to those enjoyed by married couples"）。source：EJPop + 专家报告。effective：1999 起（共同申报 2005 后简化）。confidence：高
- **ordinary cohabitation**：value=0。无共同申报。source：EJPop 表（Income taxation: Separate for cohabitation）。confidence：高

### L5 亲子/家庭法

- **两个 scope 都高**：value=2。法国非婚生亲权已完全平等：**loi n°2002-305 du 4 mars 2002（autorité parentale）确立 coparentalité 原则**（民法 310-1："Tous les enfants dont la filiation est légalement établie ont les mêmes droits..."）；**ordonnance n°2005-759 du 4 juillet 2005 portant réforme de la filiation（生效 2006-07-01）废除 légitime/naturelle 区别**——PACS/同居所生子女均非婚生但权利与婚生同。**注意**：PACS 本身不影响亲子（PACS 伴侣无共同收养权）——L5 高是法国**总体非婚生亲权平等**的功劳。source：**Legifrance（ordonnance 2005-759）+ 法国政府 UN CRC 报告（diplomatie.gouv.fr 2007）+ 2002-305 法**（官方一手，百度源已弃）。effective：2002（coparentalité 原则）→ 2006-07-01（filiation 全面改革生效）。confidence：**高**（官方源升级完成）。scope：both（ordinary cohabitation 家庭受益于总体亲权平等）

## 二、FR vs SE：第一组结构对照（六国校准最重要的对照）

| | SE（ordinary 自动型）| FR（registered 型）|
|---|---|---|
| 法律接口触发 | 同居**自动**进入 sambolagen 保护 | 接口集中在 **PACS 登记**；concubinage 正式接口非常有限（共同购不动产可共有等零星效果）|
| ordinary cohabitation scope | (2,2,1,2,2) 自动保护 | (0-1,0-1,0,0,2) 接口非常有限 |
| L3 继承 | 1（无继承+遗属两价格基数）| registered 1（无继承+住房一年+继承税豁免）；ordinary 0（60% 税）|
| 实际家庭形态与 w 载体 | sambo 家庭即受保护（载体匹配）| **载体错配**：大量家庭走 union libre（INSEE 2011：约 720 万 union libre vs PACS 伴侣约 140 万），PACS 覆盖有限（2016 年法国大都会居住在 couple 中人群约 7% 为 PACS）|

**含义**：法国的"高制度化"（PACS）与实际替代家庭形态（未登记同居为主）**脱节**——对 A×w 回归，FR 的 w 若按 PACS 计会高估替代家庭实际获得的接口。**识别含义**：A×w 检验需要 A 的构成与 w 的 scope 匹配（A 分 PACS-内 vs concubinage-内生育），否则 FR 观测点贡献的 β₃ 信息会系统偏误。此限制记录为 FR 样本的识别注意事项。

## 三、FR 初核结构与待核项

**FR 建议（scope 分格后，ordinary cohabitation 为 w_L 主对象——与 SE 可比）**：

| scope | L1 | L2 | L3 | L4 | L5 |
|---|---|---|---|---|---|
| ordinary cohabitation | 0 | 0 | 0 | 0 | 2 |
| registered（PACS）| 2 | 1-2 | 1 | 2 | 1 |

**待核**：①filiation 2005 改革精确条款（L5 confidence 升级）；②PACS 财产默认制 2007 变更对 L2 的年度分段；③1999-2006 PACS 共同取得制默认期是否短暂影响 L2（实际大部分 PACS 是 2007 后）；④第二编码员。

---

> 落盘目录：`D:\Contents\Research\Reports\2026-09-02_EGS应用落地假设集\`
> 模板：同 SE 标准模板
> 状态：FR 初核完成（单编码员 frozen）；待 Coder-B + κ
