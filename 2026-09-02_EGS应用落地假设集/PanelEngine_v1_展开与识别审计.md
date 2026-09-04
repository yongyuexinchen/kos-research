# 27 国 Panel Engine v1：展开 + Coverage Audit + P0 Identification Matrix

> 日期：2026-09-02
> 定位：从 Event Registry（人工/法律判断）到 (country, route, year) 面板的机械展开——验证引擎"可重复、无偷填、可追溯"
> 代码：`panel_engine_v1.py`（egs_data）+ `build_p0_matrix.py`
> 数据边界（诚实声明）：六国（SE/FR/DK/NL/DE/SI）L1-L4/C_child 有完整数值状态（pilot 人工 state rules 的具现）；**21 国 L1-L4 数值尚未做横截面校准**（matrix 只给 ESG 分类 + registry 给事件年）——数值列标 value_pending，不偷填。C_child 21 国同样待校准。

---

## 一、四层输出

### L1 原始事件表（source of truth，不动）
`event_registry_27countries.csv`（81 行：六国 26 + 21 国 54 事件）——本次引擎零修改。

### L2 route-year master
`panel27_routeyear_master.csv`（2209 行 = 47 route × 47 年全覆盖）
每行：country, route, year, L1-L4, C_child, na_reason, ESG_class, source_event, route_exists, uncertain_flag, value_status

### L3 Coverage Audit
`na_reason` 五类区分（用户要求的 NA 内部语义）：

| na_reason | 行数 | 含义 |
|---|---|---|
| **route_not_exist** | 517 | route 在制度上不存在（NL RP 1998 前等 registered 创建前）|
| **temporal_uncertain** | 968 | G 型：历史变化存在但无法定位（SE-L4/DK-L3·L4 六国渐进维）|
| **value_pending** | 1363 | 21 国数值未做横截面校准（E/S 型分类已知、数值待补）|
| out_of_scope / insufficient_evidence | 0 | 引擎未用到（预留）|

**G 型不偷填检查（核心 QA）**：DK-ordinary L3 47 年全 NA（=47 行全 NA，证明 G 型未被 engine 填成上一年值或 0）。SE-L4 1975-2002 全 NA、2003+ 有值（pilot 的 state 边界被原样传播）。

### L4 P0 Identification Matrix
`p0_identification_matrix.csv`（47 route 行）类型分布：

| 类型 | route 行 | 时间识别 | 建议用途 |
|---|---|---|---|
| **E_cohab_event** | 10 | ✅ | 普通同居制度化 DID（SE/SI/NO/FI/PT/IT/HU/AT 等 L1-L3）|
| **E_route_event** | 13 | ✅(registered) | registered 创建/扩展（EL 2008/AT·UK 2019 异性开放等）|
| E_route_ss | 4 | 仅 registered 同性 | registered 子样本 |
| S_control | 5 | ❌ | 横截面/对照（DE/PL/CH/IS/TR 等）|
| S_G_mix | 13 | ❌（G 维） | 横截面（多数国家 L4 维 G）|
| registered_none_or_S | 2 | ❌ | 无 registered 制度（PT/SK）|

**有时间识别能力的 route 行 = 23/47**。

## 二、追溯统计（为什么每行有值/没值）

- 理论上限：47 route × 47 年 = 2209 route-year（全展开，0 漏行）
- 六国数值就绪：约 66 行全数值 + 216 行部分（uncertain 段）
- 517 行 = route 未创建（制度不存在，非资料缺失）
- 968 行 = G 型时间不可定位（渐进税社保维为主）
- 1363 行 = 21 国数值待校准（分类已知）

**可追溯性达成**：任何一行都能回答"为什么没值"——NL 1997 RP = route_not_exist（制度尚不存在）；DK 2000 L3 = temporal_uncertain（丹麦语立法史缺失）；NO 1990 L2 = E 事件前状态（value_pending 待校准）。

## 三、P0 设计结论（Identification Matrix 的直接推论）

1. **P0 main 建议 = E + S mixed design**，不是纯 E：E_cohab 事件国 10 个 route 行提供时间识别，S_control 5 国 + S_G_mix 提供横截面与对照——27 国全样本横截面（2021 窗口）+ E 事件 DID 子样本并行
2. **E 事件时间识别维度集中在 L1-L3**（L4 多数国家 G 型只能横截面）
3. route_not_exist 段（517 行）不进回归（A 在 route 创建前也无意义）
4. value_pending 段（21 国）是下一轮横截面校准的工作量——完成前 21 国只能进"ESG 分类级"分析

## 四、引擎方法论验证

- **机械可重复**：2209 行由 81 事件 + 47 route 分类确定性生成，无随机性
- **无偷填**：G 型→NA 原样保持；E 型事件前段不自动填值（六国 pilot 已验证，21 国 value_pending 明确标注）
- **NA 语义区分**：route_not_exist vs temporal_uncertain vs value_pending 三类可分别统计与处理——用户要求的"制度不存在 ≠ 历史缺失 ≠ 数值未校准"已落地

## 五、下一步（按用户流水线）

1. **21 国横截面校准轮**（六国式逐维 2021 值 + state rules）——这是 panel 数值完整化的唯一缺口
2. C_child 21 国事件推导数值（多数有 E_child 事件：事件前 1/后 2 可填）
3. **三对齐数据桥**：A(country,route,year) route 拆分/w_effective + Y merge
4. P0 回归（Sample_E DID + Sample_E+S 横截面）

---
> 落盘目录：`D:\Contents\Research\Reports\2026-09-02_EGS应用落地假设集\data_obsbridge\`
> 产物：panel27_routeyear_master.csv（2209 行）+ p0_identification_matrix.csv（47 行）
> 状态：Panel Engine v1 跑通——EGS 测量层从"研究文档"进入"可计算数据基础设施"（21 国数值缺口已定位待校准）
