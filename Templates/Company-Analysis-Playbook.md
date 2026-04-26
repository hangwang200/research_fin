---
type: Skill
tags:
  - "#Skill"
  - "#Playbook"
  - "#Company-Analysis"
  - "#Value-Investing"
  - "#Due-Diligence"
last_updated: 2026-04-26
aliases:
  - 公司分析方法论
  - Company Due Diligence Playbook
---

# Company Analysis Playbook (商业模式分析方法论)

> **用途**：在 [[LLM Wiki]] 中对任意上市公司进行「商业模式 + 财务质量 + 估值」三位一体的尽调。
> **配套模板**：[[Templates/Company-Analysis-Template]] —— 新建公司笔记时直接复制这个文件，再按本 Playbook 填充。
> **角色定位**：以 [[Professional Business Researcher]] + [[Value Investor]] 的视角执行，遵循 [[Charlie Munger]] 的「[[Multidisciplinary Mental Models]]」与 [[Warren Buffett]] 的「[[Owner Earnings]]」框架。

---

## 0. Operating Rules（执行规则）

### 0.1 WikiLink Enforcement
- 所有「公司、人物、技术栈、宏观概念、竞争对手、产业链节点、财务指标」**必须**包裹为 `[[WikiLinks]]`，即使目标文件尚未创建。
- 示例：分析 [[TCOM]] 时必须链出 [[Booking Holdings]]、[[Expedia]]、[[Meituan]]、[[Tongcheng Travel]]、[[OTA]]、[[GMV]]、[[Take Rate]] 等。

### 0.2 数据可信度分级（Source Hierarchy）
按可信度从高到低引用：
1. **一级**：公司 [[10-K]]/ [[20-F]] / [[Annual Report]] / [[SEC Filing]] / [[HKEX 公告]] / 官网财报
2. **二级**：卖方研报（[[摩根士丹利]]、[[高盛]]、[[国证国际]]、[[中金公司]] 等）
3. **三级**：彭博 / Wind / 同花顺 / [[Moomoo]] / [[Yahoo Finance]] 聚合数据 / 巨潮(http://www.cninfo.com.cn) / 雪球
4. **四级**：新闻稿、媒体报道（仅作交叉验证）

> ⚠️ **每一个数字必须用脚注或行内括号标注来源**，格式：`(Source: 2024 Annual Report, p.XX)` 或 `[^src1]`。

### 0.3 Section 3 & 4 强制执行步骤
对「企业财务分析」与「企业股价表现」两节，必须严格执行：
1. **Step 1 - 列数据**：使用最近 **3 个完整财年** 数据 + 最新一期季报（TTM）。
2. **Step 2 - 双重核对**：每一行数字必须给出来源，并交叉对比至少 2 个数据源（财报 vs 研报 vs 第三方）。
3. **Step 3 - 趋势预测**：基于历史数据 + 卖方共识，给出 [[Bull Case]] / [[Base Case]] / [[Bear Case]] 三档预测，标注关键假设。

### 0.4 输出格式约束
- 所有表格使用标准 Markdown 表格语法（兼容 [[Obsidian]] 和 [[Dataview]] 查询）。
- 财务指标统一货币单位（人民币¥ 或美元$），并在文件顶部 YAML 中声明 `currency: RMB|USD`。
- 数字保留至**百万**级（millions），百分比保留一位小数。
- 趋势词汇统一用：`↗ 上升 / → 持平 / ↘ 下降 / ⚠ 异常`。

---

## 1. Section-by-Section 执行指南

### Section 1 · 企业概况
| 字段 | 取数路径 | WikiLink 提示 |
|---|---|---|
| 公司全称 | 招股书 / 年报封面 / [[SEC EDGAR]] | 法律实体名 |
| 企业文化 | 官网「关于我们」+ 创始人访谈 + 招股书使命愿景 | 链出 [[Founder Name]]、[[Mission Statement]] |
| 核心产品 | 年报「Business」章节 + 产品官网 | 列出每个产品 + 链出 [[Pricing Power]] 判断 |
| 市场分析 | [[Frost & Sullivan]] / [[iResearch]] / [[QuestMobile]] / [[Statista]] 报告 | 区分 [[TAM]] / [[SAM]] / [[SOM]]，并链出货币 |
| 股权架构 | 年报 Item 6 / 招股书「主要股东」 | 链出每位 [[Founder]] / [[Institutional Investor]] |

**Checklist**：
- [ ] 法律实体（含开曼/VIE 架构说明 → [[VIE Structure]]）
- [ ] 使命愿景对价值观的影响（举例说明，不能是套话）
- [ ] 核心产品 → 是否有 [[Pricing Power]]？证据是？
- [ ] 市场体量数字（人民币 or 美元 + 数据源 + 年份）
- [ ] 股权架构性质：[[合伙人制]] / [[创始人控股]] / [[国资背景]] / [[家族企业]] / [[Dual-class Share]]

---

### Section 2 · 行业分析
**Checklist**：
- [ ] 行业归属（[[消费]] / [[制造业]] / [[服务业]] / [[科技]] / [[医疗]] / [[能源]]）
- [ ] 竞争格局（[[百舸争流]] / [[一超多强]] / [[巨头垄断]] / [[寡头竞争]]）
- [ ] 5 年市场规模 [[CAGR]] + 行业天花板（含数据源）
- [ ] **同行对比表**（最近 2-3 年）：

| Metric | Target Co. | 国内对手 1 | 国内对手 2 | 国际对手 |
|---|---|---|---|---|
| 营收（最近年） | | | | |
| 营收 [[YoY]] | | | | |
| [[市场份额]] | | | | |
| 产品竞争力（Top 3 优势） | | | | |
| [[ROE]] | | | | |
| [[毛利率]] | | | | |

- [ ] [[产业链位置]]：上游 / 中部 / 下游 → 画 [[Smiling Curve]] 判断附加值
- [ ] 上下游议价能力（[[Porter Five Forces]] 简化版）：
    - 主要供应商 Top 5（是否集中？[[供应商集中度]]），是否能处理上游涨价风险
    - 主要客户 Top 5（若 ToB；是否有 [[提价权]]？）

---

### Section 3 · 企业财务分析【强制 3 步法】

**核心数据表（必填）**：

| 指标（百万 ¥/$） | FY-2 | FY-1 | FY-0 | TTM | Trend | 来源 |
|---|---|---|---|---|---|---|
| 营业收入 | | | | | | |
| [[毛利率]] (%) | | | | | | |
| [[经营性现金流]] | | | | | | |
| 净利润 | | | | | | |
| 净现金流（现金净增加额） | | | | | | |
| 应收账款 | | | | | | |
| 应付账款 | | | | | | |
| **应收/应付** 比 | | | | | | |
| 总负债（剔除 [[合同负债]] / [[预收款]]） | | | | | | |
| 有形资产净值（[[Tangible Net Worth]] = 净资产 - [[商誉]] - [[无形资产]]） | | | | | | |
| **总负债 / 有形净值** (<50% ✅) | | | | | | |
| 流动资产 | | | | | | |
| 流动负债 | | | | | | |
| **[[流动比率]]** (>1 ✅) | | | | | | |
| [[ROE]] (%) | | | | | | |
| └─ 净利率 | | | | | | |
| └─ [[资产周转率]] | | | | | | |
| └─ [[权益乘数]]（杠杆） | | | | | | |
| **[[ROIC]]_a** = [[NOPAT]] / 投入资本 | | | | | | |
| **[[ROIC]]_b** = 经营现金流净额 / 投入资本 | | | | | | |
| 净类现金资产（现金 + 短投 - 有息负债） | | | | | | |
| (市值 - 净类现金资产) / [[ROIC]] | | | | | | |
| 财务费用利息支出 | | | | | | |
| **利息支出 / 营收** (<10% ✅) | | | | | | |

**Checklist 对应红线**：
- [ ] 营业收入近 3 年是否稳定/增长？给出 [[CAGR]]。
- [ ] 毛利率 + 经营现金流是否同步提升？（背离需特别说明）
- [ ] 净利润与现金流净额是否方向一致？（[[利润现金流偏离]] 是造假信号）
- [ ] 应收账款 < 应付账款 × 2？
- [ ] 总负债（剔除合同负债、预付款）/ 有形净值 < 50%？
- [ ] 流动比率 > 1？
- [ ] ROE 横向对比同行（高 / 中 / 低判断 + [[杜邦分析]] 拆解原因）
- [ ] ROIC 趋势（必须做 [[ROIC]]_a 和 _b 两个口径）
- [ ] (市值 - 净类现金资产) / ROIC 估算「真实商业模式赚钱倍数」
- [ ] 利息支出占营收 < 10%？

> ⚠️ **关键指标总结表**（最重要，必填）：

| 维度 | 数值 | 评级 | 备注 |
|---|---|---|---|
| 1. 真实负债（含表外） | | 高/中/低 | |
| 2. 扣除商誉的净资产 | | | |
| 3. 真实净现金流（[[Owner Earnings]]） | | | |
| 4. 真实利润（剔除一次性收益） | | | |
| 5. 开销合理性（[[销售费用]] / [[研发费用]] / [[管理费用]] vs 同行） | | | |

---

### Section 4 · 股东研究
**Checklist**：
- [ ] 前十大股东占比是否 > 40%？（注意区分 [[流通股]] vs 全部股本）
- [ ] 第一大股东是否 > 34%？过去 2 年是否有 [[减持]] 记录？
- [ ] [[分红融资比]]（累计分红 / 累计融资）是否 ≥ 50%？
- [ ] 是否有定期 [[股票回购]] 计划？规模？
- [ ] 过去 2 年 [[股利支付率]]（[[Payout Ratio]]）：5-30% 为健康区间
- [ ] 过去 2 年是否有 [[增发]] / [[Dilution]] 记录？

**股东结构表**：

| 股东 | 持股 % | 类型 | 近 2 年变动 |
|---|---|---|---|
| | | [[创始人]] / [[机构]] / [[国资]] / [[战略投资人]] | |

---

### Section 5 · 企业股价表现【强制 3 步法】

> ⚠️ 注意：用户原模板中此节标号也是「4」，本 Playbook 修正为「5」以避免冲突。

**Checklist**：
- [ ] **市值分级**：
    - 大盘：> $100B
    - 中盘：$10B – $100B
    - 小盘：$2B – $10B
    - 微盘：< $2B
- [ ] **估值带**（绘制近 5 年分位数）：
    - [[PE]] (TTM / Forward)
    - [[PS]]
    - [[PB]]
    - [[EV/EBITDA]]
    - [[PEG]]
- [ ] **内在价值估算**（[[DCF]] 或 [[相对估值法]]）：

| 情景 | WACC | 永续增长 | 内在价值 / 股 | vs 现价 |
|---|---|---|---|---|
| Bull | | | | |
| Base | | | | |
| Bear | | | | |

- [ ] **筹码分布**（[[Cost Distribution]]）：
    - 当前 [[获利比例]] %
    - 短期（< 60 日）获利盘 % → 是否构成 [[抛压]]
    - 主要套牢区间

---

## 2. 复用方式

### 在 Obsidian 中新建公司笔记
1. 复制 [[Templates/Company-Analysis-Template]] 到 `wiki/entities/companies/<Ticker>.md`
2. 填充 YAML 中的 `ticker`、`currency`、`fy_end`
3. 按 Section 1 → 5 顺序填充，每节末尾写一段 **Mini Conclusion**
4. 文件末尾用 [[Dataview]] 关联同行：

````dataview
TABLE ticker, last_updated, file.tags
FROM "wiki/entities/companies"
WHERE contains(industry, this.industry)
SORT last_updated DESC
````

### 与 [[Cursor]] / LLM 协作
将本文件作为 **System Context** 注入，提示词示例：

> 「以专业商业调研员视角，根据 [[Templates/Company-Analysis-Playbook]] 分析（XXXX 公司），按 Section 1-5 顺序填充 [[Templates/Company-Analysis-Template]]，对 Section 3 & 5 严格执行 3 步法（列数据 → 标来源 → 给预测）。」

---

## 3. 反作弊清单（Red Flags Quick Scan）

执行完上述分析后，必须回答以下问题（任意一个 Yes 都需特别说明）：

- [ ] [[商誉]] / 总资产 > 30%？
- [ ] 经营现金流连续 2 年 < 净利润？（[[Earnings Quality]] 异常）
- [ ] [[应收账款周转率]] 同比下滑 > 20%？
- [ ] [[存货]] 增速显著快于营收？
- [ ] 大股东 / 高管 12 个月内净 [[减持]]？
- [ ] [[审计师]] 变更或出具非标准意见？
- [ ] [[关联交易]] 占比 > 营收 10%？
- [ ] 频繁 [[并购]] 但 [[ROIC]] 持续下行（[[Diworsification]]）？

---

## 4. 引用与延伸阅读

- [[Howard Marks]] — 《[[The Most Important Thing]]》
- [[Pat Dorsey]] — 《[[The Five Rules for Successful Stock Investing]]》
- [[Aswath Damodaran]] — [[NYU Stern Valuation Course]]
- [[Michael Mauboussin]] — 《[[Expectations Investing]]》
- [[Phil Fisher]] — 《[[Common Stocks and Uncommon Profits]]》「Scuttlebutt 调研法」

---

## 5. 修订记录

| 版本 | 日期 | 修订内容 |
|---|---|---|
| v1.0 | 2026-04-26 | 基于用户原始 checklist 整理为 Playbook，补充数据可信度分级、Red Flags、ROIC 双口径 |
