# registered route 21 国校准完成：生命周期三段语义 + 多 route 面板闭合

> 日期：2026-09-02
> 版本：panel27_routeyear_v13.csv（2209 行，**pending 归零**）
> 前置：v12（21 国 ordinary 2021 校准 + 4 项口径裁决）→ 本版补 registered/region 行
> 代码：`egs_data/backfill_reg21.py`（可复现）

## 一、校准范围与结果

五组并行子代理对 16 国 registered + ES region 做 2021 横截面 L1-L4 编码（v0.3.1 codebook + 4 项裁决），另主控修正 PT/LT 两处误建。

### 1.1 异性/双性向可用 registered（6 国，registered-route 分析主样本候选）

| 国家 | 创建 | 异性可用起 | L1-L4(2021) | 结构特征 |
|---|---|---|---|---|
| BE | 2000 cohabitation légale | 2000（双性向）| **(1,1,0,1)** | 轻义务实锤：无共产/无维持义务，L3 仅可击穿住宅用益权（裁决 1→0）|
| LU | 2004 partenariat | 2004（双性向）| **(1,1,0,2)** | **与 FR PACS 同构**：L4=婚姻级但 L3=0 无法定继承（e-Justice 卢方报告）|
| EL | 2008 σύμφωνο | 2008（异性）| **2008-14:(2,1,1,1) → 2015+:(2,2,2,2)** | 2015 L4356 全性别化同时给异性升权（减额 1/6→配偶同额）|
| EE | 2016 Kooseluseadus | 2016（双性向）| **(2,1,0,0)** | 实施真空：2016 生效但实施法 2021 未通过，继承 2024 才写入继承法 |
| AT | 2010 EP | 2019（VfGH 开放）| **(2,2,2,2)** | EP 2010 创设即≈婚姻；2019 开放不改数值 |
| UK | 2005 CP | 2019-12-02（E&W）| **(2,2,2,2)** | CP 2005 起四维=婚姻；2019 开放不改数值 |

### 1.2 同性专属 registered（8 国，单列记录，不进 ordinary-family 主样本）

| 国家 | 创建 | 2021 状态 | L1-L4(可用期) | 备注 |
|---|---|---|---|---|
| CH | 2007 PartG | 开放（2022-07 Ehe-für-alle 后停立，窗口内可用）| (2,2,2,2) | 财产/继承/税社保≈婚姻 |
| CZ | 2006 | 开放（2025 民法典平权窗口外）| **(2,0,2,0)** | 继承平权但财产/社保归零的错配 |
| HU | 2009 | 开放 | (2,2,2,2) | 最接近婚姻（除收养/ART/姓氏）|
| IT | 2016 unioni civili | 开放 | (2,2,2,2) | c.13 共产+c.20 配偶延伸 |
| NO | 1993 | **2009 关闭**（并入婚姻）| (2,2,2,2) → closed | LOV-2008-06-27-53 废止 |
| IS | 1996 | **2010 关闭** | (2,2,2,2) → closed | Act 65/2010 明示废止（最干净合并）|
| FI | 2002 | **2017 关闭** | (2,2,2,2) → closed | 法未废、存量 §8 保留效力=婚姻 |
| IE | 2011 | **2015 关闭**（法定停办）| (2,2,2,2) → closed | Marriage Act 2015 后零新登 |

### 1.3 主控修正

- **PT registered 47 行 → route_not_exist 全 NA**：葡萄牙无 registered 制度（2001 união de facto 属 ordinary、2010 直接同性婚姻）——engine/matrix 误建行修正
- **LT registered 47 行 → route_not_exist 全 NA**：2025 司法路径在窗口外
- **ES region 47 行 → 1998 前 NA / 1998+ regional_only**：区级 de facto 法 17 区+2 市差异过大无法聚合国家值（巴斯克上限 2,1,2,2 / 中位 2,0,0,1），**不进主样本**，敏感性备用

## 二、生命周期三段语义（本轮的元产出）

registered route 在 1975-2021 窗口内呈现**完整生命周期**，panel 现在能区分四个状态：

| 状态 | route_exists | 语义 | 例 |
|---|---|---|---|
| route_not_exist（含生效前过渡年）| 0 | 制度不存在或已立法未生效 | BE 1999/AT 2009/PT 全期 |
| 可用 | 1 | 制度开放、有数值 | BE 2000+/LU 2004+ |
| route_closed | 0 | 制度并入婚姻/法定停办，无新入口 | NO 2009+/IS 2010+/FI 2017+/IE 2015+ |
| regional_only | 0 | 载体是区非国家，排除主样本 | ES region 1998+ |

**立法通过年-生效年过渡**（AT 2009→2010、BE 1998→2000、UK 2004→2005 等 10 行）按生效语义归 route_not_exist——法案通过 ≠ 路线可用（R7 规则的法律时间延伸）。

## 三、结构性发现（比数值本身重要）

1. **"registered"的制度异质性被彻底钉死**：六国 registered 2021 值横跨 (1,1,0,1)/(1,1,0,2)/(2,1,0,0)/(2,0,2,0)/(2,2,2,2)——registered 从来不是一种制度，是登记制接口的谱系（与 v0.3.1"registered 内部不齐"结论互证）
2. **BE/LU 的"登记≠婚姻"是拉丁系 cohabitation légale/PACS 家族的共同特征**（L3=0 继承缺口），与 FR PACS 三例互证——**裁决 1（自动继承才计）在此类制度上制造了最大的国别差异**
3. **EE 实施真空是"纸面制度 vs 实际可及"的极端案例**（2016-2023 整部实施法缺位）——w 名义值与可及值分离的实证，呼应 SI 的 access friction 候选
4. **北欧三国 registered 全部并入性别中立婚姻**（2009/2010/2017）——registered 制度在窗口内的"完成使命后消失"，route_closed 状态首次出现
5. **CZ 错配 (2,0,2,0)**：注册伴侣有配偶顺位继承却无财产/社保——继承接口与财产接口在 registered 内再次解耦（与 ordinary 路的 L3-L2 解耦同构）
6. **IE 是唯一"两线皆无自动接口"国家**（registered 关闭 + ordinary 同居 L3=0）——registered 关闭后存量权利不再可及新进入者

## 四、panel v13 状态与 P0 含义

**value_status 分布（2209 行）**：crosssection_2021_flat 423（六国 pilot + registered 校准）/ crosssection_partial_G 752（21 国 ordinary）/ coded 66 + partial 263（六国 pilot 历史段）/ na_route_not_exist 644 / na_route_closed 37 / regional_only 24。**pending 0**。

**scope 分层对 P0 的含义**：
- **ordinary route**（27 国）= P0 主样本路线（A_j 的 j₁）
- **异性可用 registered**（BE/LU/EL/EE/AT/UK，共 6 国，个别晚开放）= registered 次级路线（j₂），可与 FR PACS/NL RP 合并构成 registered 类跨国产出；时间识别资产 = 创建/开放事件（EL 2008+2015、AT 2019、UK 2019、BE 2000、LU 2004、EE 2016）
- **同性专属 registered**（8 国）= 单列记录，不进普通家庭主样本（除非扩展 same-sex 研究问题）
- **PT/LT/ES-region** = 无国家 registered 资产（PT/LT 全 NA、ES 区级排除）
- route_closed 段（37 行）按 existence 对齐规则不进任何 A 数据窗口（NO/IS/FI/IE 的同性 registered 关闭后 A_same-sex 需另处理）

## 五、残余不确定项（诚实标注，不填假精确）

1. EL 2008-2014 段 L2 子代理给 0/1 区间，取 1（依协议/不当得利弱接口）——严格值需希腊语源复核
2. CZ L4 所得税口径冲突（HCCH 复函称视同配偶 vs Wikipedia 称无税优）——两口径下 L4 均 0（无联合申报制度），留档
3. BE L3 裁决 1 下计 0——若团队口径为"凡无遗嘱自动发生即计"则 BE 应为 1（裁决文档已注）
4. LU L3=0 依赖 e-Justice 卢方报告（与 Expatica 等消费级源冲突）——以专业源为准，正式论文需卢森堡官方法源复核
5. AT/CH C_child 已按裁决 2 收敛 2（不涉及本表）

## 六、下一步

registered 校准完成 → **三对齐 Data Bridge**（A 按 route 拆/ordinary 主样本 + registered 次级 + w_effective 混合载体处理 + Y merge）→ P0 Identification Audit v1（N_cross-section/N_E-event/N_route-matched 写死）→ dimension-specific P0（A_j×L_k 先跑）→ scalar robustness → event study。
