---
type: Schema
title: LLM Wiki 工作规范 · 结构与流程定义
tags:
  - "#Schema"
  - "#Convention"
  - "#LLM-Wiki"
last_updated: 2026-04-26
related:
  - "[[.cursorrules]]"
  - "[[purpose.md]]"
  - "[[wiki/index.md]]"
  - "[[Templates/Company-Analysis-Playbook]]"
aliases:
  - 工作规范
  - Wiki Schema
---

# 🧬 Schema · LLM Wiki 工作规范

> [[Schema]] 回答 **"How does the wiki work?"** —— 规范结构、约定、操作流程。
> [[Purpose]] 回答 **"Why does it exist?"** —— 见 [[purpose.md]]。
> 两个文件**必须配合阅读**。LLM 在每次会话开始时应先读 schema.md，确认操作规范；再读 purpose.md，确认方向。

---

## 1. 三层架构（[[Karpathy]] 原始设计）

```
┌─────────────────────────────────────────────┐
│ Layer 1: Raw Sources（原始资料 · 不可变）       │  raw/
│   原始 PDF / 网页剪藏 / 财报 / 论文            │
│   LLM 只读，永不修改                           │
└────────────────────┬────────────────────────┘
                     │ Ingest
                     ▼
┌─────────────────────────────────────────────┐
│ Layer 2: Wiki（衍生页面 · LLM 完全拥有）        │  wiki/
│   实体 / 概念 / 摘要 / 综合 / 对比 / 索引       │
│   LLM 创建、更新、维护交叉引用                 │
└────────────────────┬────────────────────────┘
                     │ Governs
                     ▲
┌─────────────────────────────────────────────┐
│ Layer 3: Schema（规则 · 人机共维护）            │  根目录
│   .cursorrules / schema.md / Templates/      │
│   定义 Wiki 怎么运作；演化最慢                  │
└─────────────────────────────────────────────┘
```

---

## 2. 目录结构（[[Directory Layout]]）

```
hang_docs/                                # Vault 根目录
├── .cursorrules                          # ⚙ Cursor / Claude Code 强制规则
├── schema.md                             # ⚙ 本文件 · Wiki 工作规范
├── purpose.md                            # ⚙ 北极星 · 投资论点 · 评估框架
├── README.md                             # ⚙ 简短说明
│
├── raw/                                  # 📥 不可变原始资料（LLM 只读）
│   ├── sources/                          # 网页剪藏 / 财报 / 研报
│   └── assets/                           # 图片 / 截图 / 附件
│
├── wiki/                                 # 📚 LLM 维护的衍生页面
│   ├── index.md                          # 内容目录 + LLM 导航入口
│   ├── log.md                            # Append-Only 时间线日志
│   ├── overview.md                       # 全局摘要（每次重大 ingest 后重写）
│   ├── entities/                         # 实体页
│   │   ├── companies/                    # 上市公司分析
│   │   └── people/                       # 创始人 / CEO / 投资大师
│   ├── concepts/                         # 财务/估值/商业模式/AI 等概念
│   ├── sources/                          # raw/sources/ 的 LLM 摘要页
│   ├── synthesis/                        # 跨源综合分析
│   ├── comparisons/                      # 横向对比（多家公司/多种方案）
│   └── queries/                          # 优秀回答归档
│
├── Templates/                            # 🛠️ 方法论 Skill（人机共维护）
│   ├── Company-Analysis-Playbook.md      # SOP / 方法论
│   └── Company-Analysis-Template.md      # 填空模板
│
└── .obsidian/                            # 🔧 Obsidian 配置
```

---

## 3. 页面类型（[[Page Types]]）与 YAML Frontmatter

每种页面类型有标准化的 YAML frontmatter。LLM 创建新页面时**必须**遵循：

### 3.1 Company（公司）
```yaml
---
ticker: <TICKER>
type: Company
exchange: NASDAQ | NYSE | HKEX | SSE | SZSE
industry: <行业>
currency: USD | RMB | HKD
fy_end: 12-31
tags: ["#Company", "#<Industry-Tag>"]
last_updated: YYYY-MM-DD
related: ["[[Templates/Company-Analysis-Playbook]]"]
---
```
**位置**：`wiki/entities/companies/<TICKER>.md`
**模板**：[[Templates/Company-Analysis-Template]]

### 3.2 Person（人物）
```yaml
---
type: Person
role: Founder | CEO | Investor | Researcher
affiliation: ["[[<Company>]]"]
tags: ["#Person"]
last_updated: YYYY-MM-DD
---
```
**位置**：`wiki/entities/people/<Name>.md`

### 3.3 Concept（概念）
```yaml
---
type: Concept
category: Financial | Valuation | Business-Model | Macro | AI
formula: <公式（如 ROE = NI / Equity）>
tags: ["#Concept"]
last_updated: YYYY-MM-DD
---
```
**位置**：`wiki/concepts/<Name>.md`

### 3.4 Source Summary（源摘要）
```yaml
---
type: Source-Summary
source_path: "[[raw/sources/<filename>]]"
source_type: ClippedArticle | AnnualReport | ResearchReport | News
date_published: YYYY-MM-DD
date_summarized: YYYY-MM-DD
tags: ["#SourceSummary"]
related_entities: ["[[<Entity1>]]", "[[<Entity2>]]"]
---
```
**位置**：`wiki/sources/<short-title>.md`
**作用**：每个 raw source 在 ingest 后都生成一份 LLM 摘要页，用于回溯和搜索。

### 3.5 Synthesis（综合分析）
```yaml
---
type: Synthesis
sources: ["[[<Page1>]]", "[[<Page2>]]"]
question: "<核心问题>"
tags: ["#Synthesis"]
last_updated: YYYY-MM-DD
---
```
**位置**：`wiki/synthesis/<Title>.md`

### 3.6 Comparison（对比）
```yaml
---
type: Comparison
entities: ["[[<Entity1>]]", "[[<Entity2>]]", "[[<Entity3>]]"]
dimension: ROIC | Moat | Valuation | etc.
tags: ["#Comparison"]
last_updated: YYYY-MM-DD
---
```
**位置**：`wiki/comparisons/<Title>.md`

### 3.7 Query Archive（优秀回答归档）
```yaml
---
type: Query
question: "<原始问题>"
date_asked: YYYY-MM-DD
references: ["[[<Page>]]"]
tags: ["#Query"]
---
```
**位置**：`wiki/queries/<short-title>.md`

---

## 4. 三大操作（[[Operations]]）

### 4.1 [[Ingest]] · 投喂新源
1. 将原始资料放入 `raw/sources/`（不可变）
2. LLM 阅读 → 抽取关键 entity / concept
3. 在 `wiki/sources/` 创建摘要页（type: Source-Summary）
4. 创建 / 更新 `wiki/entities/`、`wiki/concepts/` 等相关页
5. **更新 [[wiki/index.md]]** —— 在对应类目追加新条目
6. **追加 [[wiki/log.md]]** —— `## [YYYY-MM-DD] ingest | <Title>`
7. 如触发重大变化，**重写 [[wiki/overview.md]]**

### 4.2 [[Query]] · 回答提问
1. 先读 [[wiki/index.md]]（content catalog 优先于全文搜索）
2. 根据 index 定位相关页面 → 深读
3. 综合多页生成答案，引用 `[[wikilinks]]` 注明来源
4. 优秀回答 → [[Save to Wiki]] → 归档到 `wiki/queries/`
5. 若发现新洞见 → 触发 [[Synthesis]] 流程

### 4.3 [[Lint]] · 健康检查（每月）
- 列出所有 [[Orphan Page]]（无入站链接）
- 列出 `last_updated` > 90 天的 [[wiki/entities/companies/]] 页面
- 列出高频被引用但仍是 [[红链]] 的概念
- 找出页面间 [[矛盾]]（同一指标在不同页给出不同结论）
- 跑 [[Anti-Goals]] 检查（[[purpose.md]] §5）—— 是否有页面违反「不做什么」

---

## 5. 命名约定（[[Naming Conventions]]）

| 类型 | 格式 | 示例 |
|---|---|---|
| 公司 | `<TICKER>.md` | `META.md` / `TCOM.md` |
| 人物 | `<Full Name>.md` | `Mark Zuckerberg.md` |
| 概念（英文）| `<Concept Name>.md` | `ROIC.md` / `Owner Earnings.md` |
| 概念（中文）| `<中文名>.md` | `毛利率.md` |
| 源摘要 | `<source-slug>.md` | `meta-q4-2025-earnings.md` |
| 综合分析 | `<标题>.md` | `数字广告三巨头 ROIC 对比.md` |
| 对比 | `<X vs Y>.md` | `META vs GOOGL.md` |

**WikiLink 偏好**：使用最短路径（如 `[[META]]` 而非 `[[wiki/entities/companies/META]]`），让 Obsidian 自动解析。仅当存在重名歧义时使用全路径。

---

## 6. 数据可信度分级（[[Source Hierarchy]]）

详见 [[Templates/Company-Analysis-Playbook]] §0.2。所有数字必须标注一/二/三/四级源。

| 等级 | 来源 | 引用格式 |
|---|---|---|
| 一级 | 公司财报（10-K、20-F、8-K、年报） | `[^src1]` 标注 SEC URL |
| 二级 | 卖方研报（[[摩根士丹利]] / [[高盛]] / [[国证]] 等）| 注明券商 + 报告标题 + 日期 |
| 三级 | 数据聚合器（[[Bloomberg]] / [[Wind]] / [[Yahoo Finance]]）| 注明平台 + 抓取日 |
| 四级 | 媒体报道 | 仅作交叉验证 |

---

## 7. WikiLink 强制规则（[[.cursorrules]] §1）

- ✅ 所有公司、人物、技术、概念、指标必须 `[[wikilink]]`
- ✅ 链向不存在的文件也要链（[[红链]] 是 [[Wiki]] 的待办清单）
- ✅ 中英文混合时优先英文 ticker（`[[META]]`），别名用 `|` 分隔（`[[META|脸书]]`）
- ❌ 不要为太通用的词创建 wikilink（如 `[[公司]]`、`[[业务]]`）

---

## 8. 与外部工具的协议

| 工具 | 用途 | 配置文件 |
|---|---|---|
| [[Obsidian]] | Wiki 浏览器 + 编辑器 + 图谱视图 | `.obsidian/` |
| [[Cursor]] / [[Claude Code]] | LLM Agent 工作环境 | `.cursorrules` |
| [[Dataview]]（Obsidian 插件）| 动态查询 frontmatter | 内嵌于 [[wiki/index.md]] |
| [[Obsidian Web Clipper]] | 网页 → Markdown | 输出到 `raw/sources/` |
| [[Git]] | 版本控制 | `.git/` |

---

## 9. 演化与版本

本 schema 是 [[Living Document]]。当 Wiki 规模扩张或工作流变化时，可以修订本文件。

| 版本 | 日期 | 修订 |
|---|---|---|
| v1.0 | 2026-04-26 | 初版创立 —— Karpathy 三层 + nashsu 子目录融合 |

---

> _本文件 + [[purpose.md]] + [[.cursorrules]] 共同构成 LLM 的「**工作宪法**」_
