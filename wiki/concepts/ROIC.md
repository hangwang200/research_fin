---
type: Concept
category: Financial
formula: "ROIC = NOPAT / Invested Capital  (a 口径); ROIC_b = OCF / Invested Capital"
tags:
  - "#Concept"
  - "#Financial"
  - "#Capital-Efficiency"
  - "#Quality-Investing"
last_updated: 2026-04-26
related:
  - "[[Templates/Company-Analysis-Playbook]]"
  - "[[Owner Earnings]]"
  - "[[Wide Moat]]"
  - "[[NOPAT]]"
  - "[[WACC]]"
  - "[[ROE]]"
  - "[[Tangible Net Worth]]"
  - "[[META]]"
  - "[[TCOM]]"
aliases:
  - 投入资本回报率
  - Return on Invested Capital
  - 资本回报率
---

# 🧮 ROIC · Return on Invested Capital（投入资本回报率）

> **一句话定义**：[[ROIC]] 衡量一家公司在每一元「真实投入资本」上能产出多少税后利润，是 [[Quality Investing]] 框架下判断「**生意好坏**」的最重要单一指标。

> 💬 [[Charlie Munger]]：「Over the long term, the stock will earn the same return as the underlying business.」 —— 长期股价回报 ≈ 公司 [[ROIC]]。

---

## 📐 公式（[[双口径]]）

### A 口径（标准 / 利润视角）
```
ROIC_a = NOPAT / Invested Capital
       = EBIT × (1 - 实际税率) / (净有息负债 + 股东权益 - 现金等价物)
```

### B 口径（现金视角）
```
ROIC_b = 经营性现金流（OCF）/ Invested Capital
```

> ⭐ [[Templates/Company-Analysis-Playbook]] §3 强制 **同时计算 A 和 B**。差异过大说明 [[Earnings Quality]] 有问题（NI 与 OCF 偏离）。

### 投入资本（[[Invested Capital]]）的精确定义

| 算法 | 公式 | 适用 |
|---|---|---|
| 标准法 | 总资产 - 流动负债（无息）- 现金 | 大多数行业 |
| 简化法 | 净有息负债 + 股东权益 - 超额现金 | 互联网 / 平台 |
| Damodaran 法 | BV(Equity) + BV(Debt) - Cash - Cross-holdings | 投资性资产多的公司（如 [[TCOM]]）|

---

## 🎯 为什么它最重要？

1. **判断「好生意」的唯一硬指标**：[[Wide Moat]] 公司的 ROIC 长期 > [[WACC]]，差生意 ROIC ≤ WACC（典型如航空业）
2. **比 [[ROE]] 更纯粹**：[[ROE]] 受 [[杠杆]] 影响，[[ROIC]] 剥离债务结构噪音
3. **预测 [[内在价值]] 的输入**：[[Mauboussin]] 在《[[Expectations Investing]]》中用 ROIC × Δ 投入资本 推导 [[价值创造]]
4. **检验 [[Capital Allocation]]**：管理层每留存 $1 是否能产生 > $1 的市值增长？看 ROIC 趋势

---

## 🚨 红线（[[Templates/Company-Analysis-Playbook]] §3）

| ROIC 区间 | 评级 | 行动建议 |
|---|---|---|
| ROIC > 25% | ⭐⭐⭐⭐⭐ Wide Moat | 长持，溢价合理（[[META]] 33%、[[Visa]]、[[Constellation Software]]）|
| ROIC 15-25% | ⭐⭐⭐⭐ Quality | 优秀，关注趋势（[[Apple]]、成熟期 [[Booking]]）|
| ROIC 10-15% | ⭐⭐⭐ Acceptable | 合格，需 [[Geo Discount]] / [[周期]] 折扣（[[TCOM]] 11%）|
| ROIC 5-10% | ⭐⭐ Marginal | 仅在深度低估时考虑 |
| ROIC < 5% 或 < WACC | ⭐ Value Trap | 长期 [[价值毁灭]]，避开 |

> ⚠ **趋势比绝对值更重要**：ROIC 持续 3 年下行 = [[Diworsification]] / [[Moat Erosion]] 信号

---

## 🏢 跨公司对比（Wiki 内案例）

| 公司 | ROIC_a (FY2025) | ROIC_b | 解读 |
|---|---|---|---|
| [[META]] | **33.4%** | **52.7%** | [[Wide Moat]] 数字广告 + 高 [[Network Effects]] + 低维持性 [[CapEx]]（注：成长性 CapEx 急升，未来 ROIC 可能压缩）|
| [[TCOM]] | ~11.2% | ~19.1% | [[Wide Moat]] 但被「持有 RMB 100B+ 现金 + 长期投资性资产」严重稀释；剥离非经营资产后真实 ROIC 估 ≈ 25-30% |
| [[Booking]]（参考）| ~30% | ~35% | 全球 OTA 标杆，[[META]] / [[TCOM]] 双重对照 |
| [[Berkshire Hathaway]]（参考）| ~10% | n/a | 持有大量股权投资稀释口径，看 look-through ROIC ≈ 15% |

---

## 🔗 与其他概念的关系

- **[[ROE]] vs [[ROIC]]**：[[杜邦分析]] 拆解 ROE = 净利率 × 周转率 × 杠杆；ROIC 剔除杠杆，更干净
- **[[ROIC]] vs [[WACC]]**：差额（[[ROIC Spread]]）= 价值创造速度
- **[[ROIC]] vs [[Owner Earnings]]**：B 口径分子用 OCF 也可换成 [[Owner Earnings]]（OCF - 维持性 [[CapEx]]）→ 更保守的 [[ROIIC]]（[[增量]]口径）
- **[[ROIC]] vs [[Wide Moat]]**：高 ROIC 是 [[Wide Moat]] 的**结果**，[[Network Effects]] / [[Switching Cost]] / [[Brand Power]] 是**原因**

---

## 📚 经典文献

- [[Aswath Damodaran]] —《[[Investment Valuation]]》(2012) Ch. 12 · [[NYU Stern]] 公开课
- [[Michael Mauboussin]] —《[[Expectations Investing]]》(2021)·《[[Calculating Return on Invested Capital]]》(Credit Suisse, 2014)
- [[Bruce Greenwald]] —《[[Value Investing: From Graham to Buffett and Beyond]]》
- [[Warren Buffett]] — Berkshire 1979/1992 致股东信，多次强调 [[Return on Equity]] 与 [[Retained Earnings]] 的复利

---

## ⚠️ 计算陷阱

1. **[[一次性损益]]** 必须剔除 → [[META]] FY2025 NOPAT 必须剔除 $25.5B 一次性税款；[[TCOM]] FY2025 必须剔除 RMB 19.9B 投资公允价值变动
2. **[[商誉]] 处理**：保留还是剔除？多数学派保留（已付出资本），但 [[Damodaran]] 建议「[[Goodwill Impairment]]」前后口径一致
3. **[[过剩现金]]**：科技公司持有大量现金会**人为降低** ROIC（如 [[TCOM]] / [[Apple]]），需用 [[Adjusted Invested Capital]]
4. **[[Operating Leases]]**：ASC 842 后已资本化，旧数据需手动调整
5. **[[Cross-holdings]]**：[[TCOM]] 持有 [[MakeMyTrip]] / [[Tongcheng]] 股权 RMB 47B，须从分母剔除

---

> **关联笔记**：[[Owner Earnings]] · [[Wide Moat]] · [[Tangible Net Worth]] · [[CapEx]] · [[NOPAT]] · [[WACC]] · [[ROE]] · [[杜邦分析]] · [[Templates/Company-Analysis-Playbook]]
