---
type: Concept
category: Financial
formula: "TNW = 股东权益 - 商誉 - 无形资产"
tags:
  - "#Concept"
  - "#Financial"
  - "#Balance-Sheet"
  - "#Risk"
last_updated: 2026-04-26
related:
  - "[[Templates/Company-Analysis-Playbook]]"
  - "[[商誉]]"
  - "[[无形资产]]"
  - "[[Book Value]]"
  - "[[流动比率]]"
  - "[[ROIC]]"
  - "[[META]]"
  - "[[TCOM]]"
aliases:
  - 有形资产净值
  - 有形净值
  - TNW
  - Tangible Book Value
  - 有形账面价值
---

# 🏗️ Tangible Net Worth · 有形资产净值（TNW）

> **一句话定义**：[[Tangible Net Worth]] = 把「不会变现但会减值」的 [[商誉]] / [[无形资产]] 全部剥离后的**真实股东净资产**，是债权人和价值投资者衡量「**最坏情况下还剩多少**」的保守指标。

> 💬 [[Benjamin Graham]]：「The investor should have a definite price level above which he will not buy stocks, no matter how attractive the company appears.」 —— [[NCAV]] / [[TNW]] 是这个 Anchor。

---

## 📐 公式

```
Tangible Net Worth (TNW)
  = Total Stockholders' Equity 
  - Goodwill（商誉）
  - Intangible Assets（无形资产，如品牌、专利、客户关系、商标）
  - 其他不可变现项目（如开发支出、长期递延所得税资产）
```

> ⚠ **保守版本**还会减去：[[递延所得税资产]] / [[长期股权投资]] / [[投资性房地产]] / 部分跨境的「[[受限现金]]」

### [[Templates/Company-Analysis-Playbook]] §3 简化版
```
TNW = 净资产 - 商誉 - 无形资产
```

---

## 🎯 为什么它最重要？

1. **真实清算价值**：[[商誉]] 在企业出问题时**首先减记**（[[Goodwill Impairment]]）。Boeing、GE、Bayer 都有过百亿级别的减记
2. **债权人视角**：银行授信看 TNW，不看账面权益
3. **检测「[[价值毁灭式并购]]」**：一家公司如果 [[商誉]]/总资产 > 30%，几乎肯定靠并购堆估值
4. **[[杠杆]] 健康度的分母**：[[总负债]]/TNW 比 [[总负债]]/[[股东权益]] 更严苛

---

## 🚨 红线（[[Templates/Company-Analysis-Playbook]] §3）

| 指标 | 健康 | 警告 | 危险 |
|---|---|---|---|
| **总负债 / TNW** | < 50% ✅ | 50-100% ⚠ | > 100% 🚨 |
| **商誉 / 总资产** | < 10% | 10-30% | > 30% 🚨 |
| **TNW 增长**（5Y）| 正增长 | 持平 | 持续下降 |

---

## 🏢 跨公司对比（Wiki 内案例）

| 公司 | 股东权益 | 商誉 + 无形 | TNW | 总负债 | 总负债/TNW | 解读 |
|---|---|---|---|---|---|---|
| [[META]] FY2025 | $185B | $24B | **$161B** | $86B | **53%** | 单看比例略警告，但 [[META]] 现金 $76B 完全覆盖，且商誉来自 IG/WhatsApp 收购至今仍创造现金 → **形式问题非实质问题** |
| [[TCOM]] FY2024 | RMB 142B | RMB 26B | **RMB 116B** | RMB 99B | **86%** | 大部分负债是 [[递延收入]]/[[预收账款]]（无息），剔除后真实负债 < RMB 30B，TNW Coverage 极强 |
| [[Berkshire]]（参考）| ~$640B | ~$80B | ~$560B | ~$400B | ~71% | 保险公司天然高杠杆，但 [[Float]] 是负债成本 |
| [[航空业]]（典型负面）| 多为负 | 占比中等 | 接近 0 或负 | 高 | > 200% | 长期 [[价值毁灭]] 行业 |

---

## ⚠️ 行业差异（不能一刀切）

| 行业 | TNW 通常水平 | 解读 |
|---|---|---|
| **[[平台型]]** / [[SaaS]] | 中（科技公司大量商誉来自并购）| 50-100% 总负债/TNW 可接受 |
| **[[消费品]]** | 高（品牌价值合理）| 商誉占比可达 30%+，看 [[ROIC]] 验证 |
| **[[制造业]]** | 高（厂房设备）| 总负债/TNW < 50% 应严格遵守 |
| **[[银行 / 保险]]** | 不适用（[[杠杆]] 商业模式）| 用 [[Tier 1]] / [[Solvency Ratio]] 替代 |
| **[[铁路 / 公用事业]]** | 高（实物资产）| 高杠杆可接受（稳定现金流）|

---

## 🧮 [[Tangible Book Value Per Share]]（TBVPS）

```
TBVPS = TNW / 总流通股
```

- [[价值投资]] 经典安全边际：**P/TBV < 1.5x** 视为「[[NCAV Stock]]」候选
- [[Benjamin Graham]] [[Net-Net]] 策略要求 **股价 < 2/3 × NCAV**
- 现代科技公司多数 [[P/TBV]] > 5x（[[META]] ~3.7x、[[TCOM]] 2.35x），需结合 [[ROIC]] 综合判断

---

## 🔗 与其他概念的关系

- **[[Book Value]]**（账面价值）：含商誉，是 TNW 的「上界」
- **[[NCAV]]**（[[Net Current Asset Value]]）：[[Graham]] 更保守版本 = 流动资产 - 总负债
- **[[ROIC]]**：分母可用 TNW 替换 [[Invested Capital]]（更保守）
- **[[流动比率]]**：流动资产/流动负债 是「短期偿债」，TNW 是「长期偿债」
- **[[Goodwill Impairment Risk]]**：当 [[市值]] < TNW + 已分配商誉时高度警惕

---

## 📚 经典文献

- [[Benjamin Graham]] —《[[Security Analysis]]》(1934) · TNW 作为「**安全边际**」之一
- [[Benjamin Graham]] —《[[The Intelligent Investor]]》Ch. 14 · [[防御型投资者]] 标准
- [[Aswath Damodaran]] —《[[The Dark Side of Valuation]]》(2009) · 商誉处理章节
- [[Howard Marks]] —《[[The Most Important Thing]]》Ch. 11 · [[Risk]] 与「**真实**」净值

---

## ⚠️ 实战陷阱

1. **[[商誉]] 不是错**，错的是「不创造现金的商誉」。[[META]] 收购 Instagram $1B 至今商誉仍为 $1B，但每年贡献数百亿广告收入 → 商誉**远低估**真实价值
2. **[[品牌无形资产]]** 多数未上账：[[Coca-Cola]] 账面无形资产仅 $20B，真实品牌价值 $90B+（[[Interbrand]] 估值）
3. **[[受限现金]] / [[VIE 结构]] 资产**应进一步剔除：[[TCOM]] / [[BABA]] 等中概股的 [[VIE]] 资产理论上对美股股东不可处置
4. **[[Operating Lease]] 资本化**（ASC 842 / IFRS 16）：把租赁资产计入资产+负债，会**人为降低** TNW

---

> **关联笔记**：[[商誉]] · [[无形资产]] · [[Book Value]] · [[ROIC]] · [[流动比率]] · [[NCAV]] · [[Benjamin Graham]] · [[Templates/Company-Analysis-Playbook]] · [[META]] · [[TCOM]]
