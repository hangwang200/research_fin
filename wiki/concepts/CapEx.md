---
type: Concept
category: Financial
formula: "CapEx = Maintenance CapEx + Growth CapEx; FCF = OCF - 总 CapEx; Owner Earnings = OCF - Maintenance CapEx"
tags:
  - "#Concept"
  - "#Financial"
  - "#Cash-Flow"
  - "#AI-Infrastructure"
  - "#Hyperscaler"
last_updated: 2026-04-26
related:
  - "[[Templates/Company-Analysis-Playbook]]"
  - "[[Owner Earnings]]"
  - "[[FCF]]"
  - "[[ROIC]]"
  - "[[D&A]]"
  - "[[AI Infrastructure]]"
  - "[[Hyperscaler]]"
  - "[[META]]"
  - "[[TCOM]]"
aliases:
  - Capital Expenditures
  - 资本开支
  - 资本支出
---

# 🏗️ CapEx · Capital Expenditures（资本开支）

> **一句话定义**：[[CapEx]] 是企业为获取 / 升级长期固定资产（[[厂房]] / [[设备]] / [[数据中心]] / [[GPU]] 等）而付出的现金，是 [[Owner Earnings]] / [[FCF]] 计算的核心扣减项，也是 [[AI Hyperscaler]] 时代估值最关键的不确定性变量。

> 💬 [[Buffett 1986]]：「the average annual amount of capitalized expenditures for plant and equipment, etc. that the business **requires to fully maintain its long-term competitive position**」—— 维持性 CapEx 的经典定义。

---

## 📐 公式 / 拆分

### 第一层拆分：维持 vs 增长

```
Total CapEx 
  = [[Maintenance CapEx]]（维持当前业务规模 / 竞争力）
  + [[Growth CapEx]]（扩张产能 / 进入新市场）
```

### 第二层：与现金流公式的关系

```
[[FCF]]                = [[OCF]] - 总 CapEx
[[Owner Earnings]]     = [[OCF]] - Maintenance CapEx
[[CapEx Intensity]]    = CapEx / 营收 (%)
[[CapEx / D&A]]        = 重资产 vs 轻资产 信号
```

### 第三层：[[Greenwald Maintenance CapEx]] 估算法

[[Bruce Greenwald]] 在《[[Value Investing]]》中提出经验公式：
```
Maintenance CapEx 
  ≈ Gross PP&E × (营收 YoY) / 5  +  D&A
（假设 5 年资产更新周期）
```

> ⚠ AI [[Hyperscaler]] 时代该公式**部分失效** —— [[GPU]] 折旧周期实际只有 4-6 年，但报表 D&A 普遍按 5-6 年线性折旧，造成「**真实折旧 vs 账面 D&A 偏离**」。

---

## 🎯 为什么它最重要？

### 1. [[AI CapEx Cycle]] 是 2024-2030 最大的资本市场叙事

| 公司 | FY2024 CapEx | FY2025 CapEx | FY2026 CapEx Guidance | 三年涨幅 |
|---|---|---|---|---|
| **[[META]]** | $40B | ~$70B | **$115-135B** | **2.6x** 🚀🚀🚀 |
| [[GOOGL]]（参考）| $50B | ~$75B | $80-100B | 2x |
| [[MSFT]]（参考）| $44B | ~$80B | $95-110B | 2.4x |
| [[AMZN]]（参考）| $77B | ~$110B | $140-160B | 2x |
| **[[TCOM]]** | RMB ~3-4B（轻资产）| RMB ~4-5B（est.） | RMB ~5B | 1.5x |

> ⚠ **大数定律**：FY2026 全球 4 大 [[Hyperscaler]] 合计 [[AI CapEx]] 约 **$500B**，相当于全球 [[半导体]] 行业总收入的 80%、[[TSMC]] 全年收入的 5x。

### 2. [[CapEx Intensity]] 直接决定 ROIC

| 业态 | CapEx / 营收 | 典型 ROIC |
|---|---|---|
| 重资产 [[制造业]] | 5-10% | 8-15% |
| [[Hyperscaler]] AI 期 | 25-35% ⚠ | 急剧从 35% → 20% 压缩 |
| [[平台型]] [[轻资产]] | < 5% | 25-40% |
| [[SaaS]] | 1-3% | 30-50% |
| [[OTA]]（[[TCOM]]）| ~7% | 11-25% |

---

## 🏢 案例：[[META]] 三年 [[CapEx]] 翻 2.6 倍的 4 种解读

| # | 解读 | 概率 | 含义 |
|---|---|---|---|
| 1 | **AI 算力为护城河买单** | 50% | [[Wide Moat]] 加固，长期 ROIC 重新爬升 |
| 2 | **[[Diworsification]] 警告** | 25% | [[Reality Labs]] 累计亏损 $80B+，资金错配风险 |
| 3 | **[[行业军备竞赛]]** | 20% | 全行业一起打水漂，[[GPU]] 折旧周期早于回报周期 |
| 4 | **[[CapEx]] 实际无效** | 5% | 模型路线错误（如 [[Llama]] 失败），最坏情形 |

> [[Templates/Company-Analysis-Playbook]] §3 红线：[[CapEx]] 突然 +50% 必须给出明确回报路径论证。

---

## 🏢 案例：[[TCOM]] 为什么 [[CapEx]] 这么少？

- [[OTA]] 是 [[轻资产]] [[平台型]] 商业模式 —— 不持有酒店 / 飞机 / 客车
- [[CapEx]] 主要为：[[数据中心]]、办公装修、自有酒店收购（[[亚朵]] / [[华住]] 等少量战投）
- FY2024 总 CapEx 仅 RMB ~4B，与 RMB 19.6B [[OCF]] 相比 < 25% → [[FCF Conversion]] 极高
- 这是 TCOM 持有 RMB 100B+ 现金的根本原因

---

## 🚨 [[Maintenance CapEx]] 估算的 4 种方法

| 方法 | 公式 | 适用 |
|---|---|---|
| **简化法** | ≈ D&A | 成熟稳态 |
| **Greenwald 法** | Gross PP&E × Δ营收/5 + D&A | 制造业 |
| **行业平均法** | 行业 CapEx 中位数 × 营收 | 跨周期 |
| **管理层口径** | 公司在 MD&A / Earnings Call 自报 | 优先采用 |

> ⚠ [[META]] 2025 年 Earnings Call 首次披露 「**Growth CapEx ~80%、Maintenance ~20%**」，这是计算 [[Owner Earnings]] 的关键输入。

---

## 🔗 与其他概念的关系

- **[[Owner Earnings]]**：分母用维持性 CapEx，是更保守的 FCF
- **[[FCF]]**：用总 CapEx，会低估成长公司
- **[[ROIC]]**：CapEx 累计 ≈ [[Invested Capital]] 增长，但 ROIC 看的是「**新增 CapEx 是否产生新增 NOPAT**」（即 [[Marginal ROIC]] / [[ROIIC]]）
- **[[D&A]]**：[[CapEx]] - [[D&A]] = 资本投入净额；持续 > 0 = 扩张期，< 0 = 收缩期
- **[[AI Infrastructure]]** / [[Hyperscaler]]：FY2024-2030 主导叙事

---

## 📚 经典文献

- [[Bruce Greenwald]] —《[[Value Investing: From Graham to Buffett and Beyond]]》Ch. 4 · Maintenance CapEx 估算法
- [[Pat Dorsey]] —《[[The Five Rules]]》Ch. 5 · 区分 Maintenance vs Growth
- [[Aswath Damodaran]] —《[[Investment Valuation]]》Ch. 10
- [[Pat Gelsinger]] / [[Jensen Huang]] / [[Mark Zuckerberg]] 系列演讲 · [[AI CapEx]] 时代的产业逻辑
- [[Goldman Sachs]] / [[Morgan Stanley]] 季度 [[Hyperscaler CapEx Tracker]]

---

## ⚠️ 实战陷阱

1. **[[资本化软件开发支出]]**（[[ASC 350-40]]）：技术公司把研发支出资本化，会同时**增加 CapEx + 降低 OpEx**，扭曲 [[Operating Margin]] 与 [[CapEx Intensity]]
2. **[[GPU 折旧周期]]**：[[NVIDIA]] H100 实际可用 4-5 年，但多家 [[Hyperscaler]] 按 6 年折旧 → 真实 [[Owner Earnings]] 被高估
3. **[[Operating Lease]] 不是 CapEx**：但已变成 [[Right-of-Use Asset]]，需在 [[FCF]] 公式里手动加回（ASC 842 后）
4. **[[半导体设备]]**（[[ASML]]、[[AMAT]]）的 CapEx 高度周期性，5Y 平均更可靠
5. **[[研发支出]] vs [[CapEx]]**：[[META]] R&D $50B / CapEx $70B；[[TCOM]] R&D RMB 15B / CapEx RMB 4B —— **R&D 是另一种 CapEx**，[[Damodaran]] 主张资本化处理

---

> **关联笔记**：[[Owner Earnings]] · [[FCF]] · [[ROIC]] · [[D&A]] · [[Maintenance CapEx]] · [[Growth CapEx]] · [[AI Infrastructure]] · [[Hyperscaler]] · [[Templates/Company-Analysis-Playbook]] · [[META]] · [[TCOM]]
