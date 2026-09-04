# 27 国 E 型事件盘点：识别资产地图（Event Registry + Event Matrix 完成）

> 日期：2026-09-02
> 定位：六国方法学成果扩展为 27 国可计算面板的中间里程碑——21 国 E 型事件盘点 + 识别资产地图
> 方法：六组并行子代理（北欧/西欧/南欧/东欧×2/UK-TR-IE）只盘三类事件（E_route/E_cohab/E_child），四项质量门（event date+effective date+scope+pre/post evidence）；东欧组套 R7（政治断裂≠制度事件）
> 数据：`data_obsbridge/event_registry_27countries.csv`（81 行：六国 26 + 21 国 54 事件）+ `data_obsbridge/event_matrix_27countries.csv`（47 route 行）

---

## 〇、盘点规模

- 21 国盘点回填 **54 条核心事件**（21 国 × 平均 2.6 条）
- Matrix：47 route 行（27 国中 20 国普通同居单行 + 7 国 registered 双行 + ES 区级行）
- **识别资产计数**：24/27 国有至少 1 个 E 类维度标注；105 个 country×route×dimension 级 E 标注（含 E_w 弱/E_ss 同性专属/E_p 部分/E_r 区级变体）

## 一、子代理盘点的重要修正（防"伪事件"入库）

| 国家 | 修正 | 意义 |
|---|---|---|
| **EL** | 异性可用注册路线锚点是 **2008**（L.3719，初为异性）→ 2015 才全性别化 | 不是 2015 创建；2008 就是异性路线事件 |
| **IT** | 2016 L.76 一法双产出：unioni civili（同性专属 registered）+ **convivenze di fatto 同居框架**（全性别 E_cohab）| 意大利普通同居 2016 年才首次全国制度化 |
| **LV** | 废除婚生/非婚生区分的真事件是 **2003-01-01**（2002 修法），不是 1993（恢复战前民法典仍含两分）| R7 关键：1993"恢复战前法"≠现代平等，若当 E_child 重置即编码错误 |
| **UK** | 异性开放 CP 是 **2019-12-02**（非 2018）；FLRA 1987 御准 1987-05-15 | 精确日期修正 |
| **HU** | 同居制度化最早最密：1978 定义（社会主义）→ 1996 全性别（宪院驱动）→ 2014 民法典编 | 东欧同居制度化的异类 |
| **SK** | 三类全无 E——2005 家庭法是"重编"非接口变化（学者确认父权三推定未变）| 结构性 G/S 国家的极端案例 |
| **PL** | E_child 1950（窗口前完成）→ 窗口 1975+ 零事件 | 社会主义早期完成 = 无时间识别资产 |

## 二、识别资产地理分布（三型地图）

**E 型（时间识别资产）——按机制分组**：

| 机制 | 国家·事件 | 时间识别用途 |
|---|---|---|
| **普通同居制度化**（E_cohab）| NO L2 1991/L3 2008、FI L2·L3 2011、PT L1 1999/2001、IT L1 2016、HU L1 1996·L2 2014、AT L3 弱 2017 + 六国 SE/SI | DID 核心：同居接口从 0 到正值的立法时刻 |
| **registered route 创建**（E_route）| 异性可用：LU 2004、BE 2000、EE 2016、LV 2024、EL 2008(+NL/FR PACS/SI 六国)；同性专属：NO 1993/IS 1996/FI 2002/AT 2010/CZ 2006/UK 2005/HU 2009/IE 2011/CH 2007/IT 2016 | route 存在性跳跃（t<创建 NA）+ 部分 2019-2024 异性开放（AT/UK）|
| **C_child 改革**（E_child）| 北欧 NO 1982/IS 1992/FI 1976-84、南欧 PT 1978/ES 1981/EL 1983/IT 2013、东欧 EE 1995·2010/HU 2014/CZ 2014/LV 2003/LT 2001、UK 1987/IE 1987、TR 2002 + 六国 | 普遍权利过程：1970s-2010s 各国儿童法完成年错开 |

**S 型（横截面/对照）**：DE 全维恒 0、PL 同居/registered 结构性零、CH/IS/UK 同居无配偶权（common law 迷思）、TR 同居零、SK 全 S/G

**G 型（无时间识别）**：SE-L4/DK-L3·L4/NL ordinary-L4/SI-L4（六国，渐进税社保）+ 多数国家的 L4 维度（部门法渐进无单一事件）

## 三、统计口径校准（用户要求）

- **N_event（维度级）= 105**（country×route×dimension 的 E 标注，最小单位不是国家）
- **N_country ≥1 E 事件 = 24/27**；但**普通同居路线 L1-L4 有真 E 的国家只有 9 个**（SE/SI/NO/FI/PT/IT/HU/AT 弱/六国中 FR 弱）——普通同居的制度化事件在欧洲是稀缺品
- 无任何 E 类资产的国家：**SK、PL、LU-ordinary**（C_child 层面 LU 也未完成）——这三国只能进横截面

## 四、对 P0 设计的直接含义

1. **事件型 DID 子样本**（Sample_E）：普通同居 E_cohab 事件集中在中北欧（NO 1991/FI 2011/PT 1999/IT 2016/HU 1996/SI 1976）+ registered 开放事件（AT 2019/UK 2019/EL 2008）——这些是 A×w 时间识别的主引擎
2. **Sample_E+S**：全 27 国横截面（2021 窗口）+ 事件国对照
3. **G 型 NA 段不进时间回归**；L4 维多数国家只有横截面可用——**L1-L3 是时间识别的可用维度，L4 基本只能横截面**
4. 无 E 资产三国（SK/PL/LU ordinary）作 S 型对照——事后筛选诱惑已被"保留全 27 国 registry + 预定义样本"规则堵住

## 五、残余待收口（诚实边界）

- 生效日未核：PT 135/99、CZ 2025 法案编号、UK FLRA 生效年、IE Status of Children 生效年、NO 1915（窗口外）、SK 2005 分类（重编 vs 接口）
- LT 2025 司法路径为 partial（无立法）；EE 2016-2023 实施法真空
- 区级（ES 17 区）与次国家层面未全面编码（记 E_note）
- C_child 东欧"名义平等早于转型"与"实际接口改革在 1995-2014"的区分已按 R7 处理（平等原则 S 型基线 + 接口改革 E 型）

## 六、下一步

1. 残余时间线收口（上表 6 项，逐项核）
2. **engine 机械展开** 27 国 (country, route, year, L1-L4, C_child) panel——Event Registry 事件表 → 状态表
3. **三对齐数据桥**：A(country,route,year) 需按 route 拆（多数国家 A 只有 non-marital 总量 = 混合载体，按 Route-Consistency Axiom 用 w_effective 或敏感性双 scope）
4. P0 设计定稿：Sample_E 事件 DID + Sample_E+S 横截面

---
> 落盘目录：`D:\Contents\Research\Reports\2026-09-02_EGS应用落地假设集\`
> 数据：event_registry_27countries.csv（81 行）+ event_matrix_27countries.csv（47 route 行）
> 状态：27 国 E 型事件盘点完成——识别资产地图就绪，进入 panel 机械展开阶段
