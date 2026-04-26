---
type: Index
title: LLM Wiki — 主索引
purpose: 财务分析与 AI Infra 研究的中央目录
tags:
  - "#Index"
  - "#Hub"
  - "#Navigation"
  - "#LLM-Wiki"
last_updated: 2026-04-26
maintainer: 自维护（LLM 每次 ingest 后更新）
total_pages: 16
total_companies: 2
total_concepts: 7
total_clippings: 1
related:
  - "[[Templates/Company-Analysis-Playbook]]"
  - "[[purpose.md]]"
  - "[[schema.md]]"
  - "[[log.md]]"
  - "[[overview.md]]"
aliases:
  - 主页
  - Home
  - MOC
---

# 📖 LLM Wiki · 主索引

> 这是一个 [[Karpathy]] 式的 [[LLM Wiki]] —— 一个由 LLM 持续维护、自我累积的金融研究知识图谱。
> **角色分工**：[[人类]] 负责选源、提问、判断；[[LLM]] 负责摘要、交叉引用、归档、维护。

---

## 🎯 Wiki 用途（[[Purpose]]）

本 Wiki 聚焦三大领域，所有分析必须为「[[决策]]」服务，而非堆砌信息：

| 领域 | 关键问题 | 输出形式 |
|---|---|---|
| 💰 [[Value Investing]] / [[商业模式分析]] | 这是不是一门好生意？ | 公司分析页（[[wiki/entities/companies/]]） |
| 🤖 [[AI Infrastructure]] | 谁在 [[CapEx]] 战中真正赚钱？ | 概念页（[[wiki/concepts/]]） + 同行对比 |
| 🌍 [[Macro]] / [[Geopolitics]] | 哪些宏观变量在重塑产业？ | 宏观页（[[wiki/concepts/]] · `category: Macro`） |

**评估标准**（[[Charlie Munger]] 三连问）：
1. 这是不是一门好生意？（[[Economic Moat]]）
2. 价格是否合理？（[[Intrinsic Value]]）
3. 管理层是否值得托付？（[[Capital Allocation]]）

---

## 🤖 LLM 操作手册（[[Schema]]）

LLM 在 [[Ingest]] / [[Query]] / [[Lint]] 时**必须**遵循：

### 0. 强制规则（来自 [[.cursorrules]]）
- ✅ 所有实体必须 [[WikiLink]] 化，即使目标文件不存在
- ✅ 所有新建文档必须有 [[YAML Frontmatter]]（含 `type`、`tags`、`last_updated`）
- ✅ 公司分析必须遵循 [[Templates/Company-Analysis-Playbook]] 的方法论
- ✅ Section 3 & 5 强制执行 3 步法（列数据 → 标来源 → Bull/Base/Bear 预测）

### 1. [[Ingest]] 工作流
当用户投喂新源（[[Clippings]]、研报、新闻）时：
1. 阅读源 → 抽取关键 [[Entity]]（公司、人物、技术）和 [[Concept]]（理论、指标）
2. 在相应目录创建 / 更新对应页面
3. **更新本 index.md**（在对应分类下追加新条目）
4. **追加 [[log.md]]** 一条 ingest 记录

### 2. [[Query]] 工作流
回答问题时：
1. 先读 **本 index.md**（content catalog 优先于全文搜索）
2. 根据 index 定位相关页面 → 深读
3. 综合多页生成回答 + 引用 [[wikilink]]
4. 优秀的回答应当 [[Save to Wiki]]，归档到 `wiki/queries/` 或 `wiki/synthesis/`

### 3. [[Lint]] 工作流（健康检查，每月运行）
- 寻找页面间 [[矛盾]]
- 寻找 [[Orphan Page]]（无入站链接）
- 寻找应有专页但仍是 [[红链]] 的概念
- 检查所有 [[wiki/entities/companies/]] 页面 `last_updated` > 90 天的需要刷新

---

## 🗂️ 目录结构（[[LLM Wiki Standard]]）

```
hang_docs/
├── .cursorrules            # ⚙ LLM 强制规则（执行层）
├── schema.md               # ⚙ Wiki 工作规范（结构 / 命名 / 流程）
├── purpose.md              # ⚙ 北极星 + 投资论点 + 评估框架
├── README.md               # ⚙ 简要说明
│
├── raw/                    # 📥 原始资料（LLM 只读）
│   ├── sources/            #   网页剪藏 / 财报 / 研报
│   └── assets/             #   图片附件
│
├── wiki/                   # 📚 LLM 维护的衍生页面
│   ├── index.md            #   本文件 · 内容目录 + 导航
│   ├── log.md              #   Append-Only 日志
│   ├── overview.md         #   全局摘要（自动重写）
│   ├── entities/
│   │   ├── companies/      #   上市公司分析
│   │   └── people/         #   创始人 / CEO / 投资大师
│   ├── concepts/           #   财务 / 估值 / 商业模式 / AI 概念
│   ├── sources/            #   raw/sources/ 的 LLM 摘要页
│   ├── synthesis/          #   跨源综合分析
│   ├── comparisons/        #   横向对比
│   └── queries/            #   优秀回答归档
│
├── Templates/              # 🛠️ 方法论 Skill（人机共维护）
└── .obsidian/              # 🔧 Obsidian 配置
```

> **三层架构**（[[Karpathy]] 设计）：[[raw/]] = 不可变原始资料 · [[wiki/]] = LLM 衍生 · 根目录治理文件 = Schema。
> 详见 [[schema.md]]。

---

## 📁 内容目录（按类型组织）

### 🏢 Companies · 公司分析
> 模板：[[Templates/Company-Analysis-Template]] | 方法论：[[Templates/Company-Analysis-Playbook]]

| 公司 | 行业 | Ticker | 评级 | 上次更新 |
|---|---|---|---|---|
| [[META\|Meta Platforms]] | [[Digital Advertising]] / [[AI Infrastructure]] | [[META]] | Buy on Dip | 2026-04-26 |
| [[TCOM\|Trip.com Group]] | [[Online Travel]] / [[China Consumer]] | [[TCOM]] | Buy on Dip | 2026-04-26 |

```dataview
TABLE WITHOUT ID
  file.link AS "公司",
  industry AS "行业",
  ticker AS "Ticker",
  last_updated AS "更新日期"
FROM "wiki/entities/companies"
WHERE type = "Company"
SORT last_updated DESC
```

**Watchlist（待补全）**：[[GOOGL]] · [[AAPL]] · [[NVDA]] · [[TSLA]] · [[AMZN]] · [[MSFT]] · [[Pinduoduo]] · [[BABA]] · [[BIDU]] · [[Booking Holdings\|BKNG]] · [[Tongcheng Travel\|0780.HK]] · [[Meituan\|3690.HK]]

---

### 💡 Concepts · 概念与指标
> 财务、估值、技术、商业模式相关的可复用概念页

**📊 财务指标**（已建 · 7 个核心 Concept · 2026-04-26）：

| 概念 | 类别 | 公式 / 一句话 | 重点案例 |
|---|---|---|---|
| [[ROIC]] | Financial | NOPAT / Invested Capital · 双口径必算 | [[META]] 33% · [[TCOM]] 11% |
| [[Owner Earnings]] | Financial | OCF - Maintenance CapEx · Buffett 1986 | [[META]] / [[TCOM]] 双向校准 |
| [[Wide Moat]] | Business-Model | 5 大护城河来源 · Pat Dorsey | [[META]] 🟢 · [[TCOM]] 🟡 |
| [[Tangible Net Worth]] | Financial | 股东权益 - 商誉 - 无形资产 | 总负债/TNW 红线 |
| [[CapEx]] | Financial | Maintenance + Growth · AI Hyperscaler 周期 | [[META]] 三年 2.6x |
| [[流动比率]] | Financial | 流动资产 / 流动负债 · 短期偿债 | 阈值 > 1.0 |
| [[应收应付比]] | Financial | AR / AP · Pricing Power 间接证据 | [[TCOM]] 0.30x ⭐⭐⭐ |

**📈 估值方法**（待建）：
- [[DCF]] · [[PE]] · [[PS]] · [[PB]] · [[PEG]] · [[EV/EBITDA]] · [[Sum-of-the-Parts]]

**🏗️ 商业模式**（待建）：
- [[Network Effects]] · [[Pricing Power]] · [[Switching Cost]] · [[Brand Power]] · [[Scale Economics]] · [[Efficient Scale]]
- [[Smiling Curve]] · [[Two-Sided Network]] · [[Platform Economics]]
- [[Take Rate]] · [[CAC]] · [[LTV]] · [[ARPU]] · [[Churn Rate]]

**🔍 财务质量**（待建）：
- [[NOPAT]] · [[FCF]] · [[ROE]] · [[杜邦分析]] · [[毛利率]] · [[Earnings Quality]] · [[Cash Conversion Cycle]]
- [[Maintenance CapEx]] · [[Working Capital]] · [[Quick Ratio]] · [[DSO]] · [[DPO]]

**🤖 AI 基础设施**（待建）：
- [[AI Infrastructure]] · [[Hyperscaler]] · [[CapEx Cycle]] · [[GPU]] · [[HBM]] · [[Foundation Model]]

```dataview
TABLE WITHOUT ID
  file.link AS "概念",
  tags AS "标签",
  last_updated AS "更新日期"
FROM "wiki/concepts"
WHERE type = "Concept"
SORT file.link ASC
```

---

### 🌍 Macro · 宏观与行业
> 行业概览、产业链、宏观经济、地缘政治

**行业概览**（待建）：
- [[Digital Advertising Industry Overview]] · [[AI Infrastructure CapEx Cycle]] · [[Online Travel Industry]]
- [[Semiconductor Supply Chain]] · [[China Consumer Tech]]

**宏观主题**（待建）：
- [[Fed Rate Cycle]] · [[USD Strength]] · [[China Stimulus]] · [[US-China Tech War]] · [[Tariffs 2026]]

```dataview
TABLE WITHOUT ID
  file.link AS "主题",
  type AS "类型",
  last_updated AS "更新日期"
FROM "wiki/concepts" WHERE category = "Macro"
SORT last_updated DESC
```

---

### 👥 People · 关键人物
> 创始人、CEO、思想家、投资大师

**待建索引**：
- 投资大师：[[Charlie Munger]] · [[Warren Buffett]] · [[Howard Marks]] · [[Phil Fisher]] · [[Aswath Damodaran]] · [[Michael Mauboussin]]
- 科技创始人：[[Mark Zuckerberg]] · [[Sam Altman]] · [[Jensen Huang]] · [[Elon Musk]] · [[梁建章]] · [[张一鸣]]

```dataview
TABLE WITHOUT ID
  file.link AS "人物",
  type AS "类型",
  last_updated AS "更新日期"
FROM "wiki/entities/people"
SORT file.link ASC
```

---

### 🧠 Strategy · 投资策略与心智模型
> 框架、方法论、心智模型

**待建**：
- [[Value Investing]] · [[Quality Investing]] · [[Growth at Reasonable Price]]
- [[Mental Models]] · [[Multidisciplinary Mental Models]] · [[Inversion Thinking]] · [[Circle of Competence]]
- [[Margin of Safety]] · [[Mr. Market]] · [[Owner Earnings]] · [[Look-through Earnings]]

---

### 🛠️ Templates · 方法论 / Skill / Playbook
> 可复用的分析框架，[[人类]] 与 [[LLM]] 协作的 SOP

| 文件 | 用途 | 上次更新 |
|---|---|---|
| [[Templates/Company-Analysis-Playbook]] | 商业模式分析方法论（数据可信度分级、3 步法、Red Flags、Munger 三连问） | 2026-04-26 |
| [[Templates/Company-Analysis-Template]] | 填空式公司分析模板（Section 1-9） | 2026-04-26 |

```dataview
TABLE WITHOUT ID
  file.link AS "模板",
  type AS "类型",
  last_updated AS "更新日期"
FROM "Templates"
SORT last_updated DESC
```

---

### 📰 Clippings · 网页剪藏（[[Raw Sources]]）
> 来自 [[Obsidian Web Clipper]] 的不可变原始资料；LLM **只读**

| 标题 | 主题 | 剪藏日期 |
|---|---|---|
| [[opencode-aiopencode A powerful AI coding agent. Built for the terminal\|opencode 终端 AI 编码代理]] | [[AI Coding Agent]] / [[Developer Tools]] | 2026-04 |

```dataview
TABLE WITHOUT ID
  file.link AS "剪藏",
  file.cday AS "剪藏日"
FROM "raw/sources"
SORT file.cday DESC
LIMIT 20
```

---

### 🧪 Synthesis · 跨源综合分析
> 从多个源头综合而来的原创分析（不属于任何单一公司或概念）

**待建示例**：
- [[2026 数字广告三巨头之争 - Google vs Meta vs Amazon]]
- [[AI CapEx 黑洞 - 谁在赚 GPU 周期的钱]]
- [[中概股回归 - 港股 vs A 股双重上市浪潮]]

```dataview
TABLE WITHOUT ID
  file.link AS "综合分析",
  tags AS "标签",
  last_updated AS "更新日期"
FROM "wiki/synthesis"
SORT last_updated DESC
```

---

### 🔁 Comparisons · 横向对比
> 多家公司 / 多个标的 / 多种方案的并排对比

**待建示例**：
- [[META vs GOOGL - 数字广告 ROIC 对比]]
- [[TCOM vs Booking - 全球 OTA 商业模式]]
- [[NVDA vs AMD vs MTIA - AI 算力供应链]]

```dataview
TABLE WITHOUT ID
  file.link AS "对比",
  tags AS "标签",
  last_updated AS "更新日期"
FROM "wiki/comparisons"
SORT last_updated DESC
```

---

### ❓ Queries · 优秀回答归档
> 来自 LLM Chat 的高质量回答，已 [[Save to Wiki]] 形成永久资产

**待建**

```dataview
TABLE WITHOUT ID
  file.link AS "回答",
  tags AS "标签",
  file.cday AS "归档日"
FROM "wiki/queries"
SORT file.cday DESC
```

---

## 📊 Wiki 元数据（Health Stats）

```dataview
TABLE WITHOUT ID
  length(rows) AS "页数"
FROM "" 
WHERE type
GROUP BY type
SORT length(rows) DESC
```

| 维度 | 数值 | 目标 |
|---|---|---|
| 总页数 | 16（含治理层） | 100+ |
| 公司分析 | 2 ([[META]] · [[TCOM]]) | 20-30 |
| 概念页 | 7（[[ROIC]] · [[Owner Earnings]] · [[Wide Moat]] · [[Tangible Net Worth]] · [[CapEx]] · [[流动比率]] · [[应收应付比]]）| 50+ |
| 网页剪藏 | 1 | 持续 |
| 治理 / 元 | 5（[[purpose]] / [[schema]] / [[index]] / [[log]] / [[overview]]） | 5（已齐）|
| [[Orphan Page]] 数 | 待 [[Lint]] | < 5% |
| 平均出站链接数 | 待统计 | > 8 |

---

## 🔗 关联文件 / 维护流程

| 文件 | 路径 | 角色 | 状态 |
|---|---|---|---|
| [[index.md]] | `wiki/index.md` | 本文件 · 内容目录 + LLM 导航入口 | ✅ |
| [[purpose.md]] | `purpose.md` | Wiki 的「为什么存在」 + 北极星 + 投资论点 | ✅ |
| [[schema.md]] | `schema.md` | Wiki 的工作规范（结构 / YAML / 操作 / 命名）| ✅ |
| [[log.md]] | `wiki/log.md` | 时间线日志（[[Append-Only]]，每次 ingest / lint 的记录）| ✅ |
| [[overview.md]] | `wiki/overview.md` | 全局摘要（重大 ingest 后自动重写）| ✅ |
| [[.cursorrules]] | `.cursorrules` | Cursor / Claude Code 的强制规则（[[schema.md]] 的执行层）| ✅ |

---

## 🚀 接下来想做什么？

请用以下 prompt 模板指挥 LLM：

### 🆕 新建公司分析
````
以专业商业调研员视角，根据 [[Templates/Company-Analysis-Playbook]] 分析 (XXXX)，
按 Section 1-5 顺序填充 [[Templates/Company-Analysis-Template]]，
对 Section 3 & 5 严格执行 3 步法（列数据 → 标来源 → Bull/Base/Bear 预测）。
完成后追加到 [[index.md]] 的 Companies 表格。
````

### 🔄 [[Lint]] / 健康检查
````
对当前 Wiki 执行一次 Lint：
1. 列出所有 [[Orphan Page]]（无入站链接）
2. 列出所有 last_updated > 90 天的 [[wiki/entities/companies/]] 页面
3. 列出 index.md 中提到但尚未创建的 [[红链]]，按出现频次排序前 10
4. 找出公司分析中可能矛盾的论点（如同一指标在两份分析里给出不同评级）
````

### 🌐 [[Deep Research]]
````
针对 [[<X>]] 这个红链概念，调用网络搜索补全（目标：`wiki/concepts/<X>.md`）：
1. 至少 2 个一级数据源（年报 / 论文 / 官方文档）
2. 至少 1 个二级数据源（卖方研报 / 权威媒体）
3. 写成符合 [[.cursorrules]] / [[schema.md]] 规范的概念页 → 保存到 `wiki/concepts/`
4. 更新 [[index.md]]
````

### 📝 [[Synthesis]] / 跨源综合
````
基于 [[META]] + [[GOOGL]] + [[AMZN]]，
写一篇《数字广告三巨头 ROIC 对比与 AI CapEx 周期分析》，
保存到 `wiki/synthesis/`，并更新 [[index.md]]。
````

---

## 📅 维护节奏建议

| 频率 | 动作 |
|---|---|
| 每次 [[Ingest]] | LLM 自动更新本 index.md 对应类目 + [[log.md]] |
| 每周 | 复习 [[Watchlist]]，决定是否触发 [[财报跟踪]] |
| 每月 | 跑一次 [[Lint]] + 检查 [[Orphan Page]] |
| 每季度 | 复盘所有 [[wiki/entities/companies/]] 评级，更新 [[Mini Conclusion]] |
| 每年 | 重写 [[overview.md]]，回顾投资决策准确率 |

---

## 📚 参考与致谢

- [[Andrej Karpathy]] — 原始 [[llm-wiki.md]] 设计模式
- [[Vannevar Bush]] — [[Memex]] (1945)，知识库的先驱概念
- [[nashsu/llm_wiki]] — 完整的 Tauri 桌面实现，本 Wiki 借鉴其结构
- [[Charlie Munger]] — 《[[Poor Charlie's Almanack]]》，[[多元思维模型]]
- [[Aswath Damodaran]] — [[NYU Stern]] 估值课程

---

> _最后更新：2026-04-26 · 由 [[LLM]] 自维护 · 人类审阅_
