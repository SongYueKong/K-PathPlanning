# 网站与资料获取清单

用于用户协助获取公开研究信息。优先级 P0 决定选题能否成立，P1 用于后续设计。每项无需一次提供全部内容；先提供最相关的摘要或数据说明即可。

## 优先信息

| 优先级 | 网站/入口 | 检索或查看内容 | 最有用的返回信息 |
|---|---|---|---|
| P0 | [Google Scholar](https://scholar.google.com/) 或 [Semantic Scholar](https://www.semanticscholar.org/) | `geographically correlated failures alternative paths`；`shared risk link group disjoint routing`；`backup route portfolio network reliability` | 最接近的 5–10 篇论文的完整题名、年份、DOI与摘要；有正文时重点为方法、风险模型及实验部分 |
| P0 | [USGS](https://www.usgs.gov/) 与 [ScienceBase](https://www.sciencebase.gov/catalog/)；相关论文的数据附件 | `Wenchuan postseismic landslide inventory`；`Gorkha post earthquake landslide inventory`；`landslide road blockage` | 数据集名称、引用/链接、覆盖范围、发生/观测时间、同震还是震后、数据类型、许可、是否可下载 |
| P0 | [JAG 期刊范围](https://www.sciencedirect.com/journal/international-journal-of-applied-earth-observation-and-geoinformation/about/aims-and-scope) 与其站内论文检索 | 范围文字已由用户提供；后续检索 `landslide road accessibility`、`disaster resilient routing` 等最接近主题 | 范围说明无须重复提供；优先补充最接近论文的正文或可获取链接 |
| P1 | [RFC 4202](https://www.rfc-editor.org/rfc/rfc4202.html) | Shared Risk Link Group 的定义 | 相关定义段落与参考文献；用于判断“同一风险影响多条边”的已有概念 |
| P1 | [NASA LHASA](https://github.com/nasa/LHASA)、[滑坡预警产品入口](https://maps.nccs.nasa.gov/download/landslides) | 产品说明、存档覆盖时间、分辨率和许可 | 对应历史时期是否有数据、产品的概率含义和验证方式；目前不需要大规模栅格下载 |
| P1 | [OpenTopography](https://portal.opentopography.org/datasets)；[Geofabrik 亚洲道路数据](https://download.geofabrik.de/asia.html) | 候选区域 DEM 与道路数据说明 | 产品名称、精度/分辨率、日期、历史版本可得性、许可；待区域确定后再下载 |
| P1 | [ISPRS Journal 期刊范围](https://www.sciencedirect.com/journal/isprs-journal-of-photogrammetry-and-remote-sensing/about/aims-and-scope) | 范围文字已由用户提供；后续关注空间共同风险建模与创新应用论文 | 范围说明无须重复提供；最相关的方法论文或可获取链接用于比较贡献 |

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

## 首次设置时的访问状态与环境草稿

- 已访问：NASA 与 NetworkX 的官方 GitHub 材料。
- 返回代理 `403 Forbidden`：Crossref、OpenAlex、USGS 目标页、JAG/ISPRS 范围页面。
- 其余网站是候选入口，尚未测试；不能写成已确认被阻断或已经可用。
- 已保存自定义域名增补草稿：`api.crossref.org`、`api.openalex.org`、`doi.org`、`www.sciencedirect.com`、`www.usgs.gov`、`www.rfc-editor.org`。保留既有包管理器网络预设，未添加凭据要求。
- 保存草稿不等于当前网络已开放。平台返回需要发布；如使用该途径，应在环境设置中审核并保存后发布，再检查实际访问。用户直接提供信息也能推动文献核查。

## 本轮复查更新（2026-10-08）

环境配置元数据现在显示 `unrestricted`。实际请求确认 Crossref、OpenAlex、RFC 与 NASA 可访问；USGS 程序页、搜索页和地表破坏清单库也可访问。旧 USGS 目标页返回 404，已找到[有效清单库入口](https://www.usgs.gov/data/open-repository-earthquake-triggered-ground-failure-inventories)。

JAG 与 ISPRS 的上述范围页面仍返回代理 `403 Forbidden`。因此用户协助优先级调整为这两个期刊页面，以及元数据检索仍未提供正文的最接近论文；不再需要因首次访问失败而代查所有文献API或 USGS。配置显示开放不代表每个网站必然可达，暂不再要求增加相同域名。

Crossref 并发查询曾出现 429 和一次 500；后续较低并发的定向检索成功。这属于本轮具体请求的限流/服务错误，不能归类为域名完全不可访问。

详细状态与证据见[复查报告](network_recheck.md)及[新增访问记录](../references/access_recheck_2026-10-08.json)。此前的草稿说明保留为历史记录。

## 用户补充后的更新（2026-10-08）

JAG 范围说明已通过聊天文字收到，ISPRS 范围说明已通过文本附件收到。两个材料均已保存并记录来源，见[期刊定位更新](journal_fit.md)。原先缺少范围文字的事项已解决；官网能否直接访问与收到用户材料分别记录，不需要重复索取范围说明。

本轮已通过 Crossref/OpenAlex 获取三篇 JAG 相关论文的元数据和摘要；一篇关于空间误差相关性的论文可从机构库下载 PDF。优先事项转为最接近方法的全文对比与实际数据可获取性核查。
