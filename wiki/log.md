---
type: Log
title: Wiki 时间线日志
tags:
  - "#Log"
  - "#AppendOnly"
  - "#LLM-Wiki"
last_updated: 2026-04-26
format: "## [YYYY-MM-DD] action | Title  -- 见 Karpathy llm-wiki.md"
related:
  - "[[index.md]]"
  - "[[purpose.md]]"
aliases:
  - 日志
  - Activity Log
---

# 📅 Log · Wiki 时间线日志

> **格式约定**（[[Karpathy]] 原始规范）：每条日志必须以一致前缀开头，方便 grep 解析：
> ```bash
> grep "^## \[" log.md | tail -10        # 最近 10 条
> grep "^## \[2026-04" log.md             # 4 月所有活动
> grep "ingest" log.md                     # 所有 ingest 记录
> grep "lint" log.md                       # 所有 lint 记录
> ```
>
> **Action 类型**（首字母小写，便于 grep）：
> - `setup` — Wiki 基础设施搭建
> - `ingest` — 投喂新源（公司、研报、文章）
> - `query` — 用户提问 → LLM 回答（值得记录的）
> - `synthesis` — 跨源综合分析
> - `lint` — 健康检查
> - `revise` — 重大修订（重写既有页）
> - `archive` — 归档优秀回答
> - `decision` — 实际投资决策记录

---

## 📊 Quick Stats

| 维度 | 数值 |
|---|---|
| 总条目数 | 7 |
| Setup 条目 | 6 |
| Ingest 条目 | 1 |
| 距上次活动 | 0 天 |

---

## 🗂️ Activity Log（倒序，最新在上）

## [2026-04-26] setup | 目录重构为 [[LLM Wiki Standard]] 格式
- **What**：将 vault 目录结构重组为 [[Karpathy]] 三层 + [[nashsu/llm_wiki]] 子目录的标准布局
- **Why**：让 LLM Agent 一眼识别 [[raw/]] (不可变) vs [[wiki/]] (LLM 维护) 的边界；为后续大规模 ingest 留足扩展空间
- **变更明细**：
    - 🆕 新增 `raw/sources/` · `raw/assets/` · `wiki/entities/companies/` · `wiki/entities/people/` · `wiki/concepts/` · `wiki/sources/` · `wiki/synthesis/` · `wiki/comparisons/` · `wiki/queries/` 9 个标准目录
    - 🆕 新增治理文件 `schema.md`（Wiki 工作规范）+ `wiki/overview.md`（全局摘要）
    - 🔁 `Companies/META.md` → `wiki/entities/companies/META.md`
    - 🔁 `Clippings/opencode-...md` → `raw/sources/opencode-...md`
    - 🔁 `index.md` → `wiki/index.md`，`log.md` → `wiki/log.md`
    - 🔁 `purpose.md` 保留根目录（[[Karpathy]] 规范）
    - ❌ 删除空目录 `Companies/` · `Clippings/`
    - 📝 全量更新 [[Dataview]] `FROM "..."` 路径（9 处）
    - 📝 修正 `[[Companies/X]]` / `[[Clippings/X]]` / `[[Concepts/X]]` / `[[People/X]]` / `[[Macro/X]]` 等显式路径 WikiLinks 为最短路径或新路径
    - 📝 修正 `Templates/*` 中对 `Companies/` 的引用 → `wiki/entities/companies/`
    - 📝 修正 `.obsidian/workspace.json` 中的陈旧文件引用
    - 📝 重写 `README.md`（修复 BOM 乱码 + 增加三层架构说明）
- **Files Touched**：~14
- **Status**：✅
- **影响**：从此 LLM 应严格按 [[schema.md]] §2 的目录约定创建新页
- **Next**：基于新结构 ingest 第二家公司（[[TCOM]] 或 [[GOOGL]]）

## [2026-04-26] setup | log.md 创立
- **What**：本文件创立 —— [[Karpathy]] llm-wiki 模式中的「时间维度」核心文件
- **Why**：让 [[Wiki]] 演化轨迹可追溯，方便 [[Lint]] 时排查近期改动
- **Files**：`log.md`（新增）
- **Status**：✅
- **Next**：每次 Ingest / Lint / Revise 都必须追加新条目

## [2026-04-26] setup | purpose.md 创立
- **What**：定义 [[Wiki]] 的「为什么」—— [[北极星]] 问题、三大研究战场、决策框架、4 个 Living Theses、反目标、Human-LLM 契约
- **Why**：避免 [[LLM]] 在 Ingest / Query 时跑偏；每次操作前先读 purpose 校准方向
- **Files**：`purpose.md`（新增）
- **Status**：✅
- **影响范围**：未来所有 [[wiki/entities/companies/]] / [[wiki/concepts/]] / [[wiki/synthesis/]] 必须服务于此 Purpose
- **Next**：[[Lint]] 时核查每个公司分析是否能回答 [[Charlie Munger]] 三连问

## [2026-04-26] setup | index.md 创立
- **What**：按 [[Karpathy]] 原始规范创建主索引 —— 内容目录 + LLM 导航入口
- **Why**：[[LLM]] 在 Query 时**先读 index** 而非全文搜索，提升导航效率
- **Files**：`index.md`（新增）
- **Sections**：Companies / Concepts / Macro / People / Strategy / Templates / Clippings / Synthesis / Comparisons / Queries
- **Status**：✅
- **特性**：每个分类都嵌入 [[Dataview]] 查询，新文件自动出现
- **Next**：每次 Ingest 必须更新 index.md 对应类目

## [2026-04-26] ingest | META | Q4 2025 + Full Year 2025 财报
- **Source**：
    - [[Meta 8-K]] FY2025 (filed 2026-01-28) [^src1]
    - [[Meta 10-K]] FY2025 [^src2]
    - [[WARC]] Global Ad Trends 2025[^src3]
    - [[eMarketer]] 2026 Forecast[^src4]
    - [[Yahoo Finance]] / [[StockAnalysis.com]] / [[Capital.com]] 估值快照
- **Output**：[[META]]（`wiki/entities/companies/META.md` · 541 行，9 个一级章节，14 个引用脚注）
- **Key Findings**：
    - FY2025 营收 $200.97B (+22% YoY)，但 GAAP 净利 -3% 是会计假象（$25.5B 一次性税款）
    - **真实利润 +27%**（剔除税款影响后）
    - **CapEx 警报**：FY2026 指引 $115-135B，三年涨 2.6 倍
    - **ROIC 极优**：ROIC_a 33.4% / ROIC_b 52.7%
    - **估值合理偏便宜**：Forward PE 17.7x、PEG 0.79、SOTP 隐含 +19% 上行
    - **决策**：Buy on Dip / Hold（核心仓 5-10%）
- **Status**：✅
- **Pages Touched**：1（[[META]]）— Wiki 启动期，未来同主题 ingest 会触及更多页
- **Red Lines Triggered**：
    - 总负债/TNW 87% > 50% ⚠（科技巨头特殊解读，非真实风险）
    - 应收/应付 2.22x > 2x ⚠（广告业 Net 30-60 正常）
- **Next [[Catalyst]]**：2026-04-29 Q1 2026 Earnings

## [2026-04-26] setup | wiki/entities/companies/META.md 模板填充
- **What**：用 [[Templates/Company-Analysis-Template]] 框架第一次完整填充
- **Why**：验证 [[Templates/Company-Analysis-Playbook]] 方法论的可执行性
- **Validation**：
    - ✅ Section 3 & 5 严格执行 3 步法（数据 → 来源 → Bull/Base/Bear）
    - ✅ WikiLink 使用 200+ 处
    - ✅ 数据可信度分级（一/二/三级源）9 个脚注
    - ✅ Red Flags 8 项全检
    - ✅ Charlie Munger 三连问全答
- **Status**：✅ Playbook 方法论可投入生产

## [2026-04-26] setup | Templates/ 方法论双文件创立
- **What**：建立可复用的「公司分析 Playbook + 填空 Template」体系
- **Files**：
    - `Templates/Company-Analysis-Playbook.md`（249 行，方法论 SOP）
    - `Templates/Company-Analysis-Template.md`（300 行，填空模板）
- **Design Choice**：拆为两个文件 —— Playbook 是 [[Skill]] 不重复填充，Template 每家公司复制一份
- **关键升级 vs 用户原始 prompt**：
    1. 数据可信度分级（一/二/三/四级源）
    2. Section 3 & 5 三步法固化（数据 → 来源 → Bull/Base/Bear）
    3. ROIC 双口径（NOPAT / OCF）
    4. 关键指标总结表 5 项（负债/扣商誉净资产/真实净现金流/真实利润/开销合理性）
    5. Red Flags 8 项快扫
    6. Charlie Munger 三连问决策收敛
    7. 修正了原编号 bug（原版有两个 Section 4）
- **Status**：✅
- **Next**：随实战迭代 Playbook，每季度版本号 +0.1

---

## 📜 早期历史（Pre-Log Era · 2026-04-25 之前）

> 此前的活动未记录到 log.md。仅保留摘要：
- 2026-04-25：Obsidian Vault 初始化（[[.obsidian/]] 配置）
- 2026-04-25：[[Clippings]] 目录开始接收 [[Obsidian Web Clipper]] 内容（首篇：[[opencode-ai 终端 AI 编码代理]]）
- 2026-04-26 早期：[[.cursorrules]] 创立，定义 LLM 强制规则（[[WikiLink Enforcement]] + [[YAML Frontmatter]]）

---

## 🔧 维护规则（Append-Only Discipline）

1. **只追加，不修改**：本文件 [[Append-Only]]，错误条目通过新增 `revise` 条目修正，不覆盖历史
2. **每次操作必须记录**：[[Ingest]] / [[Lint]] / [[Synthesis]] / [[Decision]] 都必须留痕
3. **格式严格统一**：`## [YYYY-MM-DD] action | Title` —— 否则 grep 解析失败
4. **每条至少包含**：What / Why / Files / Status；建议加 Next Steps
5. **重大决策**（投资动作）使用 `decision` action，并在 [[purpose.md]] §8 同步演化记录

---

## 🎯 待办（Backlog · 不属于历史，仅供参考）

> 这部分会在执行后转为正式 log 条目，然后从 backlog 移除。

- [ ] `ingest | TCOM | 携程 2025 全年财报`（已研究但未生成最终页面）
- [ ] `setup | overview.md`（[[Karpathy]] 模式中的全局摘要文件）
- [ ] `setup | wiki/concepts/ROE.md` + `wiki/concepts/ROIC.md` + `wiki/concepts/Owner Earnings.md`（核心红链）
- [ ] `synthesis | 数字广告三巨头对比 - META vs GOOGL vs AMZN`（需先 ingest GOOGL + AMZN）
- [ ] `lint | 首次健康检查`（在 Companies 数 ≥ 5 后触发）
- [ ] `setup | wiki/entities/people/Mark Zuckerberg.md`（META 分析中已大量引用，应建专页）

---

## 🔍 常用 Grep 命令速查

```bash
# 进入 vault
cd /mnt/c/Users/HW/Desktop/Hang_doc/docs/hang_docs

# 最近 10 条活动
grep "^## \[" log.md | tail -10

# 某月所有活动
grep "^## \[2026-04" log.md

# 所有 ingest 记录
grep "^## \[.*\] ingest" log.md

# 所有 decision 记录（实际投资动作）
grep "^## \[.*\] decision" log.md

# 涉及某公司的所有活动
grep -i "META\|TCOM" log.md | grep "^##"

# 统计每种 action 出现次数
grep -oP "^## \[.*?\] \K\w+" log.md | sort | uniq -c | sort -rn
```

---

> _Append-only 文件 · 禁止修改历史条目 · 每次 Wiki 活动必须留痕_
