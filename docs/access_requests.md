# 网站与资料获取清单

用于用户协助获取公开研究信息。优先级 P0 决定选题能否成立，P1 用于后续设计。每项无需一次提供全部内容；先提供最相关的摘要或数据说明即可。

## 优先信息

| 优先级 | 网站/入口 | 检索或查看内容 | 最有用的返回信息 |
|---|---|---|---|
| P0 | [Google Scholar](https://scholar.google.com/) 或 [Semantic Scholar](https://www.semanticscholar.org/) | `geographically correlated failures alternative paths`；`shared risk link group disjoint routing`；`backup route portfolio network reliability` | 最接近的 5–10 篇论文的完整题名、年份、DOI与摘要；有正文时重点为方法、风险模型及实验部分 |
| P0 | [USGS](https://www.usgs.gov/) 与 [ScienceBase](https://www.sciencebase.gov/catalog/)；相关论文的数据附件 | `Wenchuan postseismic landslide inventory`；`Gorkha post earthquake landslide inventory`；`landslide road blockage` | 数据集名称、引用/链接、覆盖范围、发生/观测时间、同震还是震后、数据类型、许可、是否可下载 |
| P0 | [JAG 期刊范围](https://www.sciencedirect.com/journal/international-journal-of-applied-earth-observation-and-geoinformation/about/aims-and-scope) 与其站内论文检索 | 官方 aims and scope；`landslide road accessibility`、`disaster resilient routing` 等最接近主题 | 范围说明文字，以及最接近的 3–5 篇论文题名、年份、DOI、摘要；如果检索不到，也记录词组和结果 |
| P1 | [RFC 4202](https://www.rfc-editor.org/rfc/rfc4202.html) | Shared Risk Link Group 的定义 | 相关定义段落与参考文献；用于判断“同一风险影响多条边”的已有概念 |
| P1 | [NASA LHASA](https://github.com/nasa/LHASA)、[滑坡预警产品入口](https://maps.nccs.nasa.gov/download/landslides) | 产品说明、存档覆盖时间、分辨率和许可 | 对应历史时期是否有数据、产品的概率含义和验证方式；目前不需要大规模栅格下载 |
| P1 | [OpenTopography](https://portal.opentopography.org/datasets)；[Geofabrik 亚洲道路数据](https://download.geofabrik.de/asia.html) | 候选区域 DEM 与道路数据说明 | 产品名称、精度/分辨率、日期、历史版本可得性、许可；待区域确定后再下载 |
| P1 | [ISPRS Journal 期刊范围](https://www.sciencedirect.com/journal/isprs-journal-of-photogrammetry-and-remote-sensing/about/aims-and-scope) | 官方范围及灾害道路信息提取相关论文 | 范围文字、最相关的方法论文摘要，用于判断遥感/空间信息方法贡献需要达到的程度 |

从已有摘要继续做前向和后向引用追踪，比无差别收集大量一般救灾论文更有效。最重要的是共同失效路线组合与可用于独立验证的真实资料。

## 提供信息的简短格式

论文：

```
网站或数据库：
检索词及日期：
题名 / 作者 / 年份 / 期刊：
DOI 或稳定链接：
摘要：
如有正文：风险如何定义？选择几条路线？目标是什么？如何验证？
```

数据：

```
数据集名称 / 发布机构 / 稳定链接：
区域与日期：
同震还是震后；事件时间还是影像观测时间：
点、面、道路封闭表或栅格：
分辨率 / 定位精度：
许可与下载条件：
网页上的说明原文：
```

正文可按最相关章节分批提供；不能凭摘要认定细节已验证。若提供公开下载链接，随后仍需实际检查格式、时间信息及许可。

## 当前访问状态与环境草稿

- 已访问：NASA 与 NetworkX 的官方 GitHub 材料。
- 返回代理 `403 Forbidden`：Crossref、OpenAlex、USGS 目标页、JAG/ISPRS 范围页面。
- 其余网站是候选入口，尚未测试；不能写成已确认被阻断或已经可用。
- 已保存自定义域名增补草稿：`api.crossref.org`、`api.openalex.org`、`doi.org`、`www.sciencedirect.com`、`www.usgs.gov`、`www.rfc-editor.org`。保留既有包管理器网络预设，未添加凭据要求。
- 保存草稿不等于当前网络已开放。平台返回需要发布；如使用该途径，应在环境设置中审核并保存后发布，再检查实际访问。用户直接提供信息也能推动文献核查。
