# ResearchFin

```
以专业商业调研员视角，根据 [[Templates/Company-Analysis-Playbook]]
分析META, 按 Section 1-5 顺序填充
[[Templates/Company-Analysis-Template]]，对 Section 3 & 5
严格执行 3 步法（列数据 → 标来源 → 给预测）。
```

相关仓库

这里为您对您提供的四个量化投资与开发相关的 GitHub 项目进行了详细的 README 风格总结。您可以根据需要直接将其整合进您的 Obsidian 知识库、项目文档或总 README 中：

---

# 量化投资项目集锦与技术栈总结

本文档汇总了您当前管理的 4 个核心量化投资、数据同步及系统开发开源项目，涵盖数据基础设施、Python 量化学习笔记、国家级ETF/指数跟踪以及多因子选股实战系统。

---

## 1. 📂 QuantClass 数据增量同步工具 (`quantclass-sync`)

* **项目地址**：[Astro-Han/quantclass-sync](https://github.com/Astro-Han/quantclass-sync)
* **核心定位**：面向 QuantClass（邢不行量化课）数据源的自动化增量同步与管理工具（支持 macOS，提供 CLI 与 GUI）。
* **核心功能**：
* **双模操作**：既支持通过 `QuantClass Sync.command` 的图形界面（基于 `pywebview`）进行直观管理，也支持命令行（CLI）快速同步。
* **增量补全**：自动识别本地数据缺口，几天没运行也能一键将股票及币圈数据安全补齐。
* **数据健康与质量审计**：内置 `audit` 命令检查数据质量并支持一键修复（`--fix`），提供 `--dry-run` 模拟运行机制。
* **重要迁移提示**：因官方数据 API 即将停用，项目已全面适配并推荐过渡至 QuantClass 官方客户端进行日常数据维护。



---

## 2. 📂 Python 量化投资与 GitHub 学习笔记 (`Python_Stock_Github`)

* **项目地址**：[gavin30/Python_Stock_Github](https://github.com/gavin30/Python_Stock_Github)
* **核心定位**：个人在量化投资探索期与 GitHub 工程化管理阶段的学习笔记与代码归档。
* **核心内容**：
* **工程沉淀**：记录了从零开始使用 GitHub、模块化封装 Python 代码（如解决爬虫跨文件导入问题）的心得与思考。
* **数据获取与处理**：探索了基于预测者网站的历史财务数据导入、网易财经新闻 Scrapy 爬虫抓取，以及利用 Pandas 和 Jieba 进行文本分析的基础工作流。
* **量化链路思考**：梳理了从选股策略、择时策略、信号传递到自动化交易系统（Windows 端）的整体架构思路，并尝试加入舆情分析与财务数据交叉验证的思考。



---

## 3. 📂 ETF 与国家队资金跟踪 (`etf-national-tracker`)

* **项目地址**：[kitaki-Ciallo/etf-national-tracker](https://github.com/kitaki-Ciallo/etf-national-tracker)
* **核心定位**：专注于跟踪国家队资金流向、宽基 ETF 动态及大资金动向的监控分析工具。
* **核心功能**：
* **资金监控**：捕获重要宽基 ETF（如沪深300ETF、中证500ETF等）的成交量异动与份额变化，推演国家队护盘或调仓行为。
* **市场情绪透视**：通过对特定资金标的的量化指标监测，辅助判断大盘关键支撑位与宏观流动性周期。



---

## 4. 📂 多因子选股与量化分析系统 (`quantitative_analysis`)

* **项目地址**：[henrylin99/quantitative_analysis](https://github.com/henrylin99/quantitative_analysis)
* **核心定位**：功能完备的多因子选股与量化分析系统原型（v4.0 采用 React 前端 + Flask API 架构，存储采用 Parquet + SQLite，**零外部中间件依赖**，克隆即用）。
* **核心功能**：
* **🤖 AI 智能工作台**：支持自然语言查数据、构建宽表、计算因子、因子组合回测及训练 ML 模型（流式对话，附带只读 SQL 安全约束）。
* **📊 实时行情与多因子库**：内置国泰君安 Alpha191 因子库及自定义白名单表达式引擎；集成通达信分钟数据接入与实时行情、技术指标计算。
* **🔬 研究工具链与回测验证**：提供 IC 衰减、分位组合回测、特征去冗余、模型对比、模拟盘（Paper Trading）及策略参数网格寻优（Walk-Forward OOS 验证）。
* **⏰ 盘后自动化调度**：18:30 调度链完成数据链路编排、事件归档、情绪极值预警及多渠道（企业微信/钉钉/Server酱/Webhook）推送。



---