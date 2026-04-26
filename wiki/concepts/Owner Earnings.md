---
type: Concept
category: Financial
formula: "Owner Earnings = Net Income + D&A + Other Non-cash Charges - Maintenance CapEx ± Δ Working Capital"
tags:
  - "#Concept"
  - "#Financial"
  - "#Buffett"
  - "#Quality-of-Earnings"
  - "#Cash-Flow"
last_updated: 2026-04-26
related:
  - "[[Templates/Company-Analysis-Playbook]]"
  - "[[ROIC]]"
  - "[[CapEx]]"
  - "[[FCF]]"
  - "[[GAAP Net Income]]"
  - "[[Earnings Quality]]"
  - "[[Warren Buffett]]"
  - "[[Berkshire 1986 Letter]]"
  - "[[META]]"
  - "[[TCOM]]"
aliases:
  - 真实净现金流
  - Owner Earnings 真实净现金流
  - 所有者盈余
  - Buffett Owner Earnings
---

# 💰 Owner Earnings · 真实净现金流（Buffett 所有者盈余）

> **一句话定义**：[[Owner Earnings]] 是 [[Warren Buffett]] 在 [[Berkshire 1986 Letter]] 中提出的「**理论上股东可以从企业里安全提取的最大现金**」，比 [[GAAP Net Income]] 更接近**真实经济利润**。

> 💬 [[Buffett 1986]]：
> *"These represent (a) reported earnings plus (b) depreciation, depletion, amortization, and certain other non-cash charges... less (c) the average annual amount of capitalized expenditures for plant and equipment, etc. that the business requires to fully maintain its long-term competitive position and its unit volume."*

---

## 📐 公式

### Buffett 原始定义（1986）

```
Owner Earnings 
  = Reported Earnings (GAAP NI)
  + Depreciation, Depletion, Amortization (D&A)
  + Other Non-cash Charges (含 [[Stock-Based Compensation]] / [[递延税]])
  - Average Maintenance CapEx
  ± Δ Working Capital（可选，多数版本不含）
```

### 实战简化版（[[Templates/Company-Analysis-Playbook]] §3）

```
Owner Earnings ≈ 经营性现金流（OCF）- 维持性 CapEx
```

> ⚠ 关键变量：**[[Maintenance CapEx]]**（[[维持性]] vs [[Growth CapEx]]）—— [[GAAP]] 不区分，必须靠**判断**。
> 经验法则：**Maintenance CapEx ≈ D&A**（成熟稳态业务），但 AI [[Hyperscaler]] 时代这条法则失灵。

---

## 🎯 为什么它最重要？

### 「GAAP 净利润是会计学家的产物，[[Owner Earnings]] 是企业主的产物」—— Buffett

| 场景 | GAAP NI 错在哪？ | Owner Earnings 怎么救？ |
|---|---|---|
| 一次性损益 | 易被「[[特殊项目]]」扭曲 | 强制剥离非经常性 |
| [[折旧]] 不对应真实磨损 | 重资产 / 轻资产共用同一会计准则 | 用 Maintenance CapEx 替换 D&A |
| [[Stock-Based Compensation]] | 现金不出但稀释股东 | 算入 [[Real Cost]]（注意：本派与 Buffett 部分立场不同）|
| [[商誉减值]] | 账面虚增/虚减 | 已计入非现金调整 |
| [[Working Capital]] 操控 | 季末 [[应收]] / [[应付]] 美容 | 可以用平均值或剥离 |

---

## 🚨 双向校准（[[Wiki]] 内已确立的核心方法论）

> 同时见 [[wiki/overview.md]] §🎯 已确立观点 · #3

### 案例 A：[[META]] FY2025 — GAAP 低估真实利润 ❌
- 报表：GAAP NI -3% YoY ⚠
- 真相：包含 **$25.5B 一次性递延税款**（IRS 税务清算）
- [[Owner Earnings]] 调整后：**+27% YoY** ✅
- **结论**：股价跌出黄金坑，是 Buy-on-Dip 信号

### 案例 B：[[TCOM]] FY2025 — GAAP 高估真实利润 ❌
- 报表：GAAP NI **+95% YoY** 🚀
- 真相：包含 **RMB 19.9B 一次性投资公允价值变动**（持仓 [[MakeMyTrip]] / [[Tongcheng]] 市值重估）
- [[Owner Earnings]] 调整后：**-12% YoY** ⚠
- **结论**：「双倍幻觉」，市场看穿后 SAMR 利空 + 估值收缩双杀

> ⭐ 核心 Insight：**会计 noise 可以双向**。LLM 在 [[Ingest]] 公司财报时**永远先问**：这个 GAAP NI 包含什么一次性？

---

## 🔢 Owner Earnings 标准计算流程（5 步法）

| Step | 动作 | 数据源 |
|---|---|---|
| 1 | 拿 GAAP 归属股东净利润 | [[10-K]] / [[20-F]] / [[6-K]] 利润表 |
| 2 | 加回 D&A、SBC、商誉减值、其他非现金 | 现金流量表「经营活动」加项 |
| 3 | 加回/减去 [[一次性损益]]（税款 / 投资性收益 / 重组费用 / 法律和解） | MD&A 或 Non-GAAP 调节表 |
| 4 | 减去 [[Maintenance CapEx]]（≈ D&A 或更低，AI 公司需重估）| CapEx 拆解或自行估算 |
| 5 | 可选：调整 [[Working Capital]] 周期波动 | 资产负债表 |

---

## 🚨 红线 / 健康指标

| 指标 | 健康 | 警告 | 异常 |
|---|---|---|---|
| **OCF / NI 比率** | 1.0-1.5x | 0.7-1.0x | <0.7x 或 >2x |
| **Owner Earnings / GAAP NI** | 0.7-1.3x | 0.5-0.7 / 1.3-1.7 | < 0.5x 或 > 1.7x |
| **Owner Earnings 稳定性**（5Y CV）| < 30% | 30-50% | > 50% |

> [[Templates/Company-Analysis-Playbook]] §3 红线：**经营现金流连续 2 年 < 净利润 → [[Earnings Quality]] 警告**

---

## 🔗 与其他概念的关系

- **[[FCF]]**（自由现金流）：FCF = OCF - 总 [[CapEx]]（含成长性）；[[Owner Earnings]] 只减维持性 CapEx，因此 **Owner Earnings ≥ FCF**（成长期公司）
- **[[ROIC]] B 口径**：分子可用 [[Owner Earnings]] 替换 OCF，更保守
- **[[DCF]]**：内在价值 = Σ Owner Earnings / (1+WACC)^n + 终值（Buffett 的[[内在价值]]口径）
- **[[Look-through Earnings]]**：Buffett 把持仓公司未分配利润按比例并入，是 [[Owner Earnings]] 的扩展版本

---

## 📚 经典文献

- [[Warren Buffett]] —《[[Berkshire 1986 Letter]]》（首次提出，必读）
- [[Lawrence Cunningham]] —《[[The Essays of Warren Buffett]]》(2015) Chapter on "Owner Earnings"
- [[Bruce Greenwald]] —《[[Value Investing]]》Ch. 4
- [[Pat Dorsey]] —《[[The Five Rules for Successful Stock Investing]]》Ch. 5

---

## ⚠️ 实战陷阱

1. **Maintenance CapEx 估算难**：Buffett 自己也承认是「主观判断」；可参考 [[Bruce Greenwald]] 的 [[Maintenance CapEx Greenwald Formula]]
2. **[[Stock-Based Compensation]]** 是否减回？— Buffett 派坚决减，[[Munger]] 也曾说「[[SBC]] is real cost」；但部分学派不减（争议点）
3. **[[Working Capital]]** 周期性陷阱：零售业季节性大，年度 OE 需用平均值
4. **[[商誉减值]]** 是非现金，但反映过去并购错误，**不应忽略**（即使加回）

---

> **关联笔记**：[[ROIC]] · [[FCF]] · [[CapEx]] · [[Maintenance CapEx]] · [[Earnings Quality]] · [[Warren Buffett]] · [[Berkshire 1986 Letter]] · [[Templates/Company-Analysis-Playbook]] · [[META]] · [[TCOM]]
