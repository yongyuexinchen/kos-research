# SillyTavern（酒馆）生态产品应用调研

> 日期：2026-08-16
> 目的：摸清"酒馆"SillyTavern 生态目前的产品/应用形态，为永月（本地优先 AI 伴侣）产品化提供对标。
> 数据源：GitHub API 实时抓取（2026-08-16，直连可达），README 实际读取，星数/活跃度为抓取时点。
> 数据分级：开源代码库= S 级（代码即事实）；README 描述=B 级；未验证声称=D 级。

## 一、结论速览

酒馆生态已从"单一前端"演进为 **六层产品矩阵**：

1. **前端本体层**：SillyTavern（32k⭐，事实标准）＋ TavernAI（鼻祖）＋ RisuAI（竞品）
2. **衍生重写层**：TauriTavern（Tauri/Rust 原生重写，2026 最大变量，支持桌面+移动全平台）
3. **插件应用层**：记忆增强（最大刚需，3 个独立记忆插件）、角色生成、RPG 玩法、思考链
4. **内容标准层**：Character Card V2 规范 + Chub.ai 平台 + 配套工具链
5. **伴侣整合层**（★对永月最关键）：Artemis（本地 AI 女友全栈）、Project AIRI（47.9k⭐ Neuro-sama 再造）、Soul-of-Waifu、fount（酒馆作者下一代）
6. **配套服务层**：TTS（Kokoro 5.3k⭐）、启动器、安卓壳、后端 API 全家桶

**核心判断：酒馆本身是"引擎"，价值正在向上层整合产品迁移——这正是永月的生态位。**

## 二、逐层产品明细

### 第 1 层：前端本体

| 项目 | 星数 | 状态 | 说明 |
|------|------|------|------|
| SillyTavern/SillyTavern | 32,177 | 活跃 2026-07 | 事实标准，"LLM Frontend for Power Users"，AGPL-3.0 |
| TavernAI/TavernAI-v1 | 2,700 | 活跃 2026-06 | 鼻祖（2021），已边缘化 |
| kwaroran/Risuai | 1,608 | 活跃 2026-08 | 独立前端竞品，更友好 |
| PocketRisu | 264 | 活跃 2026-07 | RisuAI 自托管 fork |

### 第 2 层：衍生重写 / 客户端（★2026 热点）

| 项目 | 星数 | 说明 |
|------|------|------|
| **Darkatse/TauriTavern** | 1,272 | **SillyTavern 用 Tauri/Rust 原生重写**，桌面+移动全平台（Win/macOS/Linux/Android/iOS），中文社区主导，2026-08-16 仍在推，canary 持续发布。酒馆用户想要"原生应用"体验的答案 |
| SillyTavern/SillyTavern-Launcher | 554 | 官方启动器 |
| al01cn/sillyTavern-launcher | 186 | 图形化启动器（已归档） |
| leigegehaha/sillytavernlauncher | 19 | 中文酒馆启动器（Tauri v2，暗黑奇幻风，DeepSeek 特供版） |
| Aegis-plus/SillyTavern-Android | 44 | 安卓 WebView 壳 |

### 第 3 层：插件应用层（酒馆的功能化应用）

| 插件 | 星数 | 功能 |
|------|------|------|
| **muyoou/st-memory-enhancement** | 1,417 | **长期记忆增强**（中文作者），酒馆最大痛点=记忆 |
| SpicyMarinara/rpg-companion | 304 | RPG 扩展：角色/任务/背包/游戏状态追踪 |
| bmen25124/SillyTavern-Character-Creator | 171 | LLM 自动创建角色卡 |
| cierru/st-stepped-thinking | 168 | 角色先思考再回复 |
| SenriYuki/SillyTavern-Horae | 165 | 记忆增强插件 |
| Lodactio/Extension-Summaryception | 136 | 记忆总结插件 |
| bmen25124/SillyTavern-WorldInfo-Recommender | 125 | 世界书智能推荐 |
| SillyTavern/SillyTavern-Extras | 689 | 官方扩展 API，**已标记 OBSOLETE（废弃）** |

记忆类插件 3 个并存且都有活跃维护 → **记忆是酒馆用户第一痛点，且现有方案都只是"摘要式"，无真正长期记忆产品**。

### 第 4 层：内容标准 + 平台（角色卡生态）

| 项目 | 星数 | 说明 |
|------|------|------|
| malfoyslastname/character-card-spec-v2 | 183 | 角色卡 V2 规范，事实标准 |
| Chub.ai（平台，非开源） | - | 最大角色卡分享平台，配套工具：Chub-Ripper（本地下载备份）、chub-ai-gems（质量发现引擎）、chub-charlink-scraper |
| lenML/CCEditor | 36 | 在线角色卡编辑器 |
| altkriz/aimaker | 8 | 客户端建卡工具（兼容 Chub/Janitor） |

### 第 5 层：伴侣整合产品（★对永月最重要的对标层）

| 项目 | 星数 | 定位 | 技术栈 | 与永月的关系 |
|------|------|------|--------|--------------|
| **moeru-ai/airi（Project AIRI）** | **47,938** | "重新造 Neuro-sama"——AI waifu 灵魂容器，数字生命 | 实时语音聊天、Live2D、Minecraft 集成、VTuber | 最火的数字生命叙事，MIT。证明"独立人格/灵魂"叙事有巨大需求 |
| **momori777/Artemis** | 268 | 中文：100% 本地 AI 女友后宫 | OpenClaw + QQ/Telegram Bot + llama.cpp + GPT-SoVITS + ComfyUI 画图 + Live2D + 桌宠 + **酒馆角色卡导入**，8G 显存可跑，N 卡脚本 + AMD 分支 | **离永月最近的现实对标**——本地、离线、多模态、角色卡生态复用。但定位是"女友后宫"，永月=独立人格 |
| **steve02081504/fount** | 720 | "Not a chatbot. A presence you keep."——可编程 agent 运行时平台 | 角色 + agent 能力融合，可嵌入 IDE/浏览器/终端/Discord | 酒馆社区大佬（ST-script 作者）的下一代方向：**角色向 agent 演进**。README 明确把自己与 OpenClaw/character.ai/SillyTavern 对比 |
| jofizcd/Soul-of-Waifu | 1,207 | 桌面 AI 伴侣 | Live2D/VRM 模型、角色扮演 | 桌面伴侣形态 |
| Synthintel0/MyGirlGPT | 430 | 本地 AI 女友（2024，较老） | 本地 LLM | 早期形态 |
| Playa-0v0/Cyrene-Agent | 393 | AI 桌面伴侣 | 沉浸聊天+长期记忆 | 记忆型伴侣 |

### 第 6 层：配套服务

- **TTS 语音**：remsky/Kokoro-FastAPI（5,333⭐，OpenAI 兼容 TTS 包装）、daswer123/xtts-api-server（597⭐）——酒馆要"出声"的标配
- **后端模型**：酒馆是 OpenAI 兼容 API 前端 → 可接 OpenRouter/OpenAI/Claude/DeepSeek/KoboldCPP/Ollama 全家桶
- **超级整合包**：heshengtao/super-agent-party（2,587⭐，自托管全能 AI 伴侣 = neuro sama + openclaw）

## 三、对永月的启示（产品层面）

1. **生态位确认**：酒馆生态的价值正在从"前端引擎"向"整合伴侣产品"迁移（Artemis/AIRI/fount 均非纯前端）。永月做"独立人格 + 知识体系驱动"的本地伴侣，**不与酒馆前端竞争，与整合层竞争**——该层尚无"独立人格"定位的产品，差异化成立。

2. **记忆是共识痛点，但全是摘要式**：三个记忆插件都只做"总结压缩"，没有真正的长期记忆架构（向量/结构化）。永月"记忆框架"是差异化核心，方向已验证。

3. **可复用生态而非重建**：Character Card V2 规范 + Chub.ai 内容库 + 酒馆角色卡导入（Artemis 已验证可行）→ 永月可借力内容生态，把精力花在人格/记忆/知识层。

4. **形态启示**：TauriTavern 证明用户要原生桌面体验；AIRI 证明"数字生命"叙事能引爆（47.9k⭐）；fount 证明角色→agent 演进是社区方向——永月的"AI 伴侣 + agent 能力"组合是对的。

5. **许可纪律**：SillyTavern/TauriTavern 均为 AGPL-3.0（传染性），airi 是 MIT（可借鉴）。永月若复用代码注意 AGPL 陷阱；只参考不抄可规避。

## 四、信息源

| 项目 | 来源 | 抓取时间 |
|------|------|----------|
| GitHub 搜索/仓库数据 | api.github.com（直连） | 2026-08-16 |
| README 内容 | api.github.com/repos/*/readme | 2026-08-16 |
| AI 伴侣赛道背景 | ai-agent-industry-research 技能快照（2026-08-15） | 复用 |
| Chub.ai 平台信息 | GitHub 配套工具 repo 描述推断 | 2026-08-16 |
