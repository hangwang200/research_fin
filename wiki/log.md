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
| 总条目数 | 9 |
| Setup 条目 | 7 |
| Ingest 条目 | 2 |
| 距上次活动 | 0 天 |

---

## 🗂️ Activity Log（倒序，最新在上）

## [2026-04-26] setup | wiki/concepts/ × 7 | 核心 Concept 页批量建立
- **Trigger**：用户指令「建核心 Concepts [[ROIC]] / [[Owner Earnings 真实净现金流]] / [[Wide Moat]] / [[有形资产净值]] / [[CapEx]] / [[流动比例]] / [[应收/应付比]]」
- **Output**：7 个 Concept 页，全部位于 `wiki/concepts/`
    - [[ROIC]] (`ROIC.md`, 122 行) — 双口径（NOPAT vs OCF）+ Damodaran/Mauboussin 文献 + 跨公司红线
    - [[Owner Earnings]] (`Owner Earnings.md`, 148 行) — Buffett 1986 框架 + META/TCOM 双向校准案例
    - [[Wide Moat]] (`Wide Moat.md`, 144 行) — Pat Dorsey 5 大护城河 + 7 Powers 扩展 + Moat Erosion 警告
    - [[Tangible Net Worth]] (`Tangible Net Worth.md`, 137 行) — Graham 安全边际 + 总负债/TNW 红线
    - [[CapEx]] (`CapEx.md`, 159 行) — Maintenance vs Growth + AI Hyperscaler 周期（4 大 Hyperscaler FY2026 合计 ~$500B）
    - [[流动比率]] (`流动比率.md`, 147 行 · 别名：流动比例 / Current Ratio) — 行业差异化阈值 + Window Dressing 警告
    - [[应收应付比]] (`应收应付比.md`, 177 行 · 别名：AR/AP Ratio / 应收/应付比) — Pricing Power 间接证据 + Schilit 造假信号 + TCOM 0.30x 极致案例
- **Methodology Anchors**（每页都包含）：
    - YAML frontmatter（type: Concept · category · formula · aliases · related）
    - 公式定义 + 计算口径
    - [[Templates/Company-Analysis-Playbook]] §3 红线锚定
    - 跨公司案例（[[META]] FY2025 + [[TCOM]] FY2024-FY2025 实测数据）
    - 经典文献引用（Buffett / Graham / Munger / Dorsey / Damodaran / Mauboussin / Greenwald / Helmer / Schilit）
    - 实战陷阱（Window Dressing / 一次性损益 / VIE / Operating Lease 等）
- **Cross-Reference 密度**：~580 个 [[WikiLink]]（含红链），平均 83 条/页
- **Status**：✅
- **Pages Touched**：10（7 个新建 + [[wiki/index.md]] + [[wiki/log.md]] + [[wiki/overview.md]]）
- **Index 更新**：
    - `total_pages: 9 → 16` · `total_concepts: 0 → 7`
    - 「💡 Concepts」章节从「待建」升级为表格化清单
    - Health Stats 同步
- **Living Thesis 影响**：所有 7 个概念页都强化了 [[purpose.md]] §4 [[投资三大主题]]：
    - 🟢 [[ROIC]] / [[Wide Moat]] / [[Owner Earnings]] → 直接服务于 [[Quality Investing]] 主题
    - 🟢 [[CapEx]] → 直接服务于 [[AI Infrastructure]] 主题（详细 Hyperscaler 周期分析）
    - 🟢 [[Tangible Net Worth]] / [[流动比率]] / [[应收应付比]] → 服务于 [[Risk Management]] 子框架
- **Knowledge Gap 推进**：[[wiki/overview.md]] 中「待建概念页」第一优先级清单 7 项全部完成
- **Next Concepts Pipeline**（按优先级）：
    1. [[Network Effects]] / [[Switching Cost]] / [[Pricing Power]]（[[Wide Moat]] 5 大来源的细分）
    2. [[FCF]] / [[NOPAT]] / [[杜邦分析]]（[[ROIC]] / [[Owner Earnings]] 的依赖）
    3. [[DCF]] / [[PEG]] / [[EV/EBITDA]]（估值方法集）
    4. [[Maintenance CapEx]] / [[Greenwald Maintenance CapEx Formula]]（[[CapEx]] 深化）

---

## [2026-04-26] ingest | TCOM | 携程 2025 全年财报 + Q4 2025 + SAMR 反垄断调查
- **Source**（详见 [[TCOM]] §9 引用文献）：
    - [[Trip.com Group 6-K]] FY2025 Q4 + Full Year Press Release (filed 2026-02-25)
    - [[SEC EX-99.1]] FY2025 Q4 数据表
    - [[Trip.com Group 20-F FY2024]] (filed 2025-04)
    - [[Trip.com Group]] H1 2025 + $5B Buyback 授权 (2025-08)
    - [[Tiger Brokers]] / [[BoCom Int'l]] 行业份额估算
    - [[Mordor Intelligence]] 《China Online Travel Market 2025-2031》
    - [[Sohu]] / [[行业研究]] 2025 中国 OTA 报告
    - [[Yahoo Finance]] / [[StockAnalysis]] / [[ValueInvesting.io]] 估值快照
    - [[China Daily]] / [[SCMP]] / [[Trivium China]] [[SAMR]] 调查报道
    - [[White Sky Hospitality]] OTA 佣金率对比
- **Output**：[[TCOM]]（`wiki/entities/companies/TCOM.md` · ~280 行 · 9 个一级章节 · 12 个引用脚注）
- **Key Findings**：
    - **会计幻觉警报**：FY2025 GAAP NI RMB 33.4B (+95% YoY) 中 RMB 19.9B 是一次性投资公允价值变动；**核心经营净利润 ≈ RMB 16B (-12% YoY)**
    - **垄断地位**：[[Trip.com Alliance]]（Ctrip+Qunar+Tongcheng）= 70% 中国 OTA GMV；TCOM 单家 56%；出境游 48.3%
    - **现金堡垒**：净类现金 RMB 85.7B / ~$12.3B（占市值 38%）；新 $5B 多年期 [[Buyback]] 授权（占市值 ~15%）
    - **国际化提速**：FY2025 国际 [[OTA]] [[Bookings]] +60% YoY；服务 [[Inbound Travelers]] ~2,000 万；国际收入占比 ~40%
    - **估值低分位**：Forward PE 12-14x（5Y < 25 分位）/ EV/EBITDA 4.69-13x / PB 1.32x（< 10 分位）
    - **核心风险**：[[SAMR]] 反垄断调查 (2026-01-14) 涉及 [[最低价]] / [[二选一]] / [[算法控价] / [[商家强制独家]]；潜在罚款 ≤10% 营收 ≈ RMB 5.3B 上限
    - **治理变动**：[[Min Fan]] / [[Qi Ji]] 共同创始人 2026-02-25 退出董事会；[[James Liang]] 持续掌舵
    - **决策**：Buy on Dip / Hold（核心仓 3-5%）；Base [[DCF]] 内在价值 $58-71 vs 现价 $48-49 (+20-47% 上行)
- **Status**：✅
- **Pages Touched**：1（[[TCOM]]）
- **Red Lines Triggered**：
    - 总负债/TNW 86% > 50% ⚠（主要为 [[递延收入]] / [[预收账款]]，非真实债务）
    - GAAP OCF/NI 0.66x ⚠（穿透到核心 NI 后回到 1.4x ✅）
    - S&M 同比 +25% > 营收 +17% ⚠（国际扩张期可接受，需观察是否常态化）
- **Living Thesis 验证**：🟢 [[中国消费 / 旅游业被错杀]]（[[purpose.md]] §4 Thesis #2）从 🔴 升级 → 🟡 partial（仅 1 例，需补 [[Pinduoduo]] / [[BABA]] 验证扩展性）
- **Next [[Catalyst]]**：
    - 2026-05-19 [[Q1 2026 Earnings]] —— 核心营业利润 YoY 是关键（需 ≥ +5%）
    - [[SAMR]] 调查结果披露（罚款金额 / 整改要求）
    - 国际 OTA Bookings 增速能否维持 ≥ +40%

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

- [x] ~~`ingest | TCOM | 携程 2025 全年财报`~~ ✅ 2026-04-26 完成
- [x] ~~`setup | overview.md`~~ ✅ 2026-04-26 完成
- [ ] `setup | wiki/concepts/ROIC.md` + `wiki/concepts/Owner Earnings.md` + `wiki/concepts/Wide Moat.md`（核心红链 · 在 [[META]] 与 [[TCOM]] 中均高频出现）
- [ ] `setup | wiki/concepts/SAMR Anti-Monopoly Investigation.md`（[[TCOM]] 分析中关键风险，独立成页便于跨公司复用）
- [ ] `setup | wiki/concepts/VIE Structure.md`（中概股共性结构）
- [ ] `synthesis | 全球 OTA 对比 - TCOM vs Booking vs Expedia`（[[TCOM]] 已 ingest，需 [[BKNG]] / [[EXPE]] 补全）
- [ ] `synthesis | 数字广告三巨头对比 - META vs GOOGL vs AMZN`（需先 ingest GOOGL + AMZN）
- [ ] `lint | 首次健康检查`（在 Companies 数 ≥ 5 后触发）
- [ ] `setup | wiki/entities/people/Mark Zuckerberg.md`（META 分析中已大量引用，应建专页）
- [ ] `setup | wiki/entities/people/James Liang.md`（[[TCOM]] 创始人 + 人口经济学家，独特视角）

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
