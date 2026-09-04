# P0 Data Contract 与 Identification Audit v1

> 日期：2026-09-02
> 数据：`P0_master.csv`（2209 行 country-route-year，带 eligibility 与样本标签）
> 代码：`egs_data/build_p0_contract.py`（可复现）
> 定位：从"建库"到"检验"的桥——机械判定每行是否有资格进入 P0，并把每个识别来源的贡献写死

## 一、P0 Data Contract（Eligibility 规则）

每行 (country, route, year) 进入 P0 的最小条件：

```
j_A = j_w      ← A 端为国家级混合载体（见 §三），route 一致性由 w 侧 route 选择承担
t_A = t_w      ← A/Y 端 country-year 与 w 端 country-route-year 按 (country, year) join
route_exists   ← route_exists_t = 1（route_not_exist / route_closed / regional_only 全部排除）
A ≠ NA         ← A1（nmb_share 非婚生育比例）非空
w ≠ NA         ← L1-L4 至少一维有值（区间 0-1/1-2 视为有效）
Y ≠ NA         ← Y 主结果 F1MR 非空（备选 crudeMR）
```

**contract_ok = exists & A & Y & w**。审计结果：**1375/2209 行通过 contract（27 国、43 个 country-route 组合）**。

## 二、w 的时间语义：panel complete ≠ every cell equally identified

| w_time_signal | 含义 | contract_ok 行数 |
|---|---|---|
| **six_timeseries** | 六国 ordinary 历史分段（真实制度事件驱动的时间变异）| 256 |
| **registered_event** | registered route 有创建/开放/关闭生命周期事件 | 220 |
| **flat** | 21 国 ordinary——2021 校准值平铺全期，**无时间变异** | 899 |

**关键识别事实**：21 国 ordinary 的 L1-L3 是 2021 横截面校准值的 flat 回填（S 型恒值合法、E 型事件国的历史段未重建）——它们在 panel 里"有值"但**不贡献 w 的时间识别**，只能进横截面或作为"恒常 w"参与 A 变异识别。真正能识别"制度跃迁 → Y 变化"的只有六国 ordinary + registered 事件族（共 476 行）。

## 三、A 端路线问题（Route-Consistency 落地）

**A1（nmb_share 非婚生育比例）是国家级混合载体**（ordinary cohabitation + registered/PACS + 单亲 + 离异/丧偶生育），无法按 route 从现有数据拆分（Eurostat/OECD 无 route 内出生拆分）。

处理规范（沿用 P0 v0.2 §8 Route-Consistency Axiom）：
- **不默认 A_nonmarital = A_ordinary**
- 主规格：A_mixed × w_j（j=ordinary 或 registered 分别跑）——A 的 route 构成权重 s_j 未估计前，**A×w_j 系数是"混合 A 在 j 类接口下的调节效应"**，解释时须声明
- 敏感性：`P0_sensitivity_effective` 样本对 w_effective = Σ_j s_j·w_j 的两端假设（s 主导 ordinary vs 均衡）做界限——s_j 是路线构成权重，后续若找到各 route 生育占比数据（如 FR INSEE 的 PACS-内出生）可升级为主规格
- **w 侧已严格 route 化**：ordinary 主路线（27 国）与 registered 次路线（异性可用 6 国 + FR PACS/NL RP）分离，不存在 A_ordinary×w_PACS 混乘

## 四、三样本标签（P0_master 已生成）

| 样本 | 定义 | n | 用途 |
|---|---|---|---|
| **samp_B2021** | year=2021 & exists & A & **Y_F1MR** & w | 23（16 国）| P0-B 横截面主规格 |
| **samp_Aevent** | exists & A & Y_F1MR & w & w_time_signal ∈ {six_timeseries, registered_event} | 363（20 国）| P0-A 事件 DID/event-study |
| **samp_sens** | exists & A & (Y_F1MR 或 crudeMR) & w | 1375 | P0 敏感性（crudeMR 版/有效担保规格）|

## 五、P0 Identification Audit v1（识别来源 × 有效观察）

### 5.1 横截面（P0-B，2021，ordinary route）

| 规格 | n（国）| 说明 |
|---|---|---|
| Y = F1MR（主）| **16 国** | F1MR 滞后：AT 止 2019、BE/DE 止 2017、UK 止 2015、IE 止 2016、IS 止 2011、NO/SE 止 2020、EE 止 2018、TR 止 2020 |
| Y = crudeMR（备选）| **17 国** | 2021 crudeMR 亦缺 AT（Eurostat 延迟）|

**分维有效样本（P0-B 内 A_j × L_k）**：

| 维度 | F1MR 版 | crudeMR 版 | 含义 |
|---|---|---|---|
| A×L1 | 16 国 | 17 国 | 身份接口横截面可识别 |
| A×L2 | 16 国 | 17 国 | 财产接口可识别 |
| A×L3 | **15 国** | 16 国 | 继承接口可识别 |
| A×L4 | **3 国** | **4 国** | **税社保接口横截面基本不可识别**（L4 多为 G 型 NA：21 国仅 4 国有 L4 2021 值）|

**这是审计最重要的发现之一**：L4 在横截面几乎无识别力——税社保接口的渐进型（G）特征使它的观测集中在六国时间序列，横截面只剩 3-4 国。P0 第一轮若跑 A×L4 横截面，N=3 是无效估计，必须依赖时间样本或放弃该维度横截面。

### 5.2 事件样本（P0-A，时间识别）

- **n = 363 route-year，20 国**，其中：
  - 六国 ordinary 时间序列 170 行：SE 29y(1990-2020)/FR 22y(1998-2021)/DK 32y/NL 30y/DE 25y(止 2017)/SI 32y——**这是 w 真实制度事件驱动变异的唯一来源**
  - registered 事件族 193 行 / 16 个 country-route 组合（BE 2000/LU 2004/EL 2008+2015/EE 2016/AT 2019/UK 2019 + FR PACS 1999/NL RP 1998 + 同性专属关闭事件 NO 2009/IS 2010/FI 2017/IE 2015）
- 事件年窗口内的 A 变异 + w 分段 → 可做 event-study（A_{t-k}×w 前后斜率变化）
- **21 国 ordinary 全部不在 P0-A**（flat，无时间信号）——诚实声明：它们的 E 型事件年（NO 1991/FI 2011/PT 1999 等）虽在 Event Registry，但**事件前 w 值未重建**，不能伪造 DID 观察

### 5.3 敏感性样本（P0_sens）

- **n = 1375**（全 contract_ok 行）——crudeMR 版全样本/有效担保 w_effective 规格用

## 六、P0 估计规格建议（Data Contract 固化的结论）

1. **P0-B 横截面（2021）**：A×L1/L2/L3 三组可跑（15-17 国），**A×L4 横截面放弃**（N=3 无效）；Y 主 F1MR、备 crudeMR；C_child(2021) 全 2 无变异 → 横截面中只能作常量，无法估计（其价值在时间维）
2. **P0-A 事件（时间识别）**：六国 ordinary + registered 事件族（363 route-year/20 国）——这里 C_child(country,t) 有真实变异（E_child 事件 1→2），可估计其**平行过程**效应，与 w_R 分离
3. **分维先行**：A×L1、A×L2、A×L3（+A×L4 仅时间样本）分别跑，再跑 A×w_R 压缩版——L3 若显著稳定则支持"继承接口是关键担保"的理论解读
4. **C_child 作为平行过程**：进入所有时间模型，与 A×w_R 并列——检验"关系接口"与"普遍权利"两个过程是否机制分离（DE pilot 已预示 w_R≈0 恒值 + C_child 1→2 可分离估计）
5. 解释声明：A 为混合载体，A×w_j 系数为"混合 A 的 j 类调节效应"；route 构成权重 s_j 待后续升级

## 七、残余清单（写死的不确定性）

1. F1MR 滞后 11 国（2021 横截面主结果样本损失 ~40%）——备选 crudeMR 只补 1 国；时间样本不受影响（F1MR 1990s 起覆盖良好）
2. AT 2021 crudeMR 亦缺（Eurostat 未发布）
3. L4 横截面 3-4 国——21 国 L4 G 型 NA 的校准缺口直接吃掉该维横截面识别
4. A 端 route 构成权重 s_j 未估计（依赖 INSEE 等 route-内出生数据，后续可升级）
5. C_child 时间序列在 P0_master 中已随行携带（六国/21 国 E_child 事件已知），事件样本内可全用

> 一句话：**1375 行通过契约，但真正的时间识别资产是 363 行事件样本（六国+registered 生命周期），横截面识别资产是 15-17 国的 L1/L2/L3——L4 与 C_child 只在时间轴上活着。**
