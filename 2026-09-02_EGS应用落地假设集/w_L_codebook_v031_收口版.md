# w_L codebook v0.3.1（正式收口版）— 时间重建规则固化

> 日期：2026-09-02
> 版本关系：v0.2（框架）→ v0.3（rule refinement：D1-D4/R5）→ **v0.3.1（收口：pilot1+2 已验证规则全部固化 + FR-L1 仲裁）**
> 状态：**正式收口**——本版本为历史面板建设（Step 2 full）与后续统计的现行编码手册；不再开放结构性规则修订（仅在新增国家暴露新 failure mode 时以 v0.3.2+ 增量修订）
> 修订驱动：Step 2 pilot1（SE/FR/DE）+ pilot2（DK/NL/SI）的 temporal failure mode 验证

---

## 〇、v0.3.1 变更一览（自 v0.3）

| 编号 | 变更 | 来源 |
|---|---|---|
| **R6** | **route 不存在 = NA ≠ 0** | pilot2 T5（NL RP 1998 前）|
| **R7** | **political event ≠ institutional event**（断裂必须被证明）| pilot2 T6（SI 1991）|
| **R8** | **E/S/G 三型分类法**（每维每段标注型别）| pilot1+2 元结论 |
| **R9** | **G 型不得前推**：时间变异标 NA + uncertain_flag；仅保留已知现代状态备注 | pilot1 SE-L4 / pilot2 DK |
| **D3+** | "增强条件 ≠ 触发门槛"判别词：接口以 X 为增强条件（无 X 仍有接口）→ 不受 D3 封顶；以 X 为触发门槛（无 X 无接口）→ 封顶 1 | Coder-B2 反馈 F1 |
| **A1** | **FR-L1 仲裁裁决**：法定定义 + ≥1 项可执行法律效果 → 记 1；纯定义无效果 → 记 0。FR concubinage（1999 定义 + 部分可执行效果）→ **1**（与 Coder-B2 一致，消除 A 的 0-1 区间）| B2 反馈 F2 |
| **R10** | **C_child 升格为独立时间状态过程** C_child(country, t)——非附带控制变量；与 w_R 平行建设、平行演进（关系接口演进 vs 普遍权利演进两个独立过程）| 用户 F3 + pilot1 T3/DE |
| **R11** | **数据桥接三对齐**：A_j 与 w_j 必须 route 对齐（j_A=j_w）+ time 对齐（t_A=t_w）+ existence 对齐（route exists_t=1，否则 NA 不顶 0）| 用户三条件 |
| **R12** | **panel 值域规范**：value ∈ {0,1,2,NA} + confidence + E/S/G 标签三列必存——统计时明确区分观察来源（法律跃迁/结构稳定/证据不足排除）| 用户 |

---

## 一、现行完整规则集（v0.3.1 编码手册）

### 1. 构念与索引
- w_R = f(L1 身份, L2 财产, L3 继承, L4 税/社保)——关系路线获得的制度接口（ordinary cohabitation scope）
- C_child = L5 独立编码（universal child rights），索引 (country, t)
- 全索引：w_R(country, route, dimension, year)；维度内每格 {value, source, effective date, scope, confidence, ESG_class}

### 2. value 判定规则
- 0：无制度接口（结构性零/宪法否定 zero）
- 1：有限/条件性/明确但窄（D2：clear but narrow → 1；D3：触发门槛型条件 → ≤1）
- 2：clarity + breadth（D2）；自动无条件广泛（D3 例外：增强条件非门槛 + 接近普遍覆盖）
- **区间 {0-1, 1-2} 仅在仲裁期可用**（v0.3.1 已收敛 FR-L1=1；新增国家若判区间须入仲裁流程）

### 3. 时间重建规则（v0.3.1 核心增量）
- **R6**：route 制度创建年之前一律 NA（0 表示"存在但不给"，NA 表示"不存在"）
- **R7**：政治事件不自动产生跃迁；仅真实法律事件（立法/宪法条款/宪法法院裁决直接改接口）编码跃迁；制度连续是默认
- **R8**：E 型（事件型——年度分段）、S 型（结构性恒定——全程可填，恒值即信息）、G 型（渐进无事件——时间变异 NA）
- **R9**：G 型不前推、不做平滑、不做粗锚
- **D3+**：判别"增强条件 vs 触发门槛"

### 4. 归因规则
- route-dependent 维（L1-L4）进 w_R；route-independent（C_child）单列——禁止混入 route score

### 5. scope 红线
- registered partnership ≠ ordinary cohabitation；同性专属不计；私人契约不计入接口值（R5）

### 6. 数据桥接（P0 前置）
- R11 三对齐 + R12 值域/标签规范

## 二、M_A(v0.3) → M_A(v0.3.1) 变更

| 格 | v0.3 | v0.3.1 | 规则 |
|---|---|---|---|
| FR-L1 | 0-1（区间）| **1** | A1 仲裁（定义+效果 → 1，与 B2 一致）|
| 其余 | 不变 | 不变 | — |

## 三、面板产物规范（Step 2 full 输出）

- 每观察：country, route, year, L1-L4（可 NA）, C_child, confidence (per dim), ESG_class (per dim), source_event
- 统计使用规则：E 型事件年提供时间识别；S 型恒值作横截面/对照；G 型 NA 段不进时间回归；全样本可用横截面（2021 窗口）
- 识别资产 = E 型立法事件（DID 式）；不是所有 w_R(t) 都需要时间变化

---

> 落盘目录：`D:\Contents\Research\Reports\2026-09-02_EGS应用落地假设集\`
> 前置：v0.3（rule refinement）、pilot1、pilot2
> 下一步：27 国 Event Registry（country/route/dimension/event... 事件表 → 机器展开 panel）
