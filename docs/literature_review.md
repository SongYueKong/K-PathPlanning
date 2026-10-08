# 文献核查框架与已核实材料

日期：2026-10-08。**这是检索方案与有限材料记录，不是完成的系统综述。** 本轮已获取部分相关论文的元数据/摘要及 RFC 原文；当前没有读取最接近路线共同失效研究的论文正文，因此不能认定拟研究问题具有新颖性。

## 1. 已获得的可靠信息

已通过官方 GitHub 读取两个来源，并固定到提交版本。完整访问证据及内容校验值见 [verification_log.json](../references/verification_log.json)。

| 来源 | 固定版本 | 已核实内容 | 不能据此声称 |
|---|---|---|---|
| NetworkX shortest_simple_paths 源码与文档 | `6da4704cbf32ba6f50f6d9c46cc0a071e3a87985` | 基于 Yen 算法生成按成本排序的简单路径；不直接支持 MultiGraph/MultiDiGraph；文档列出 Yen 1971 文献 | 已阅读 Yen 原文，或该算法适合全部原始道路图而无需转换 |
| NASA LHASA 官方 README | `b8036f7ad4ae27d3faa333c809ecb1de7b218d4a` | LHASA 2 使用机器学习估计约 1 km、每日尺度的降雨诱发滑坡发生概率；包含道路暴露分析与数据入口 | 产品能直接刻画震后道路阻断，或约 1 km 结果可解析具体窄路口 |

固定来源：

- [NetworkX 文档所在源码](https://github.com/networkx/networkx/blob/6da4704cbf32ba6f50f6d9c46cc0a071e3a87985/networkx/algorithms/simple_paths.py)
- [NASA LHASA README](https://github.com/nasa/LHASA/blob/b8036f7ad4ae27d3faa333c809ecb1de7b218d4a/README.md)

## 2. 从官方材料取得的论文线索

下列元数据仅得到上述官方材料的二手支持。论文原文、出版商元数据和结果尚未核验；DOI 是材料提供的入口，不应直接转为“已读文献”。

| 论文线索 | 材料提供的信息 | 关联用途 | 核查状态 |
|---|---|---|---|
| Jin Y. Yen, 1971, *Finding the K Shortest Loopless Paths in a Network* | Management Science, 17(11), 712–716 | K 最短路径基线 | 题名、年卷页由 NetworkX 文档支持；原文未读 |
| Kirschbaum & Stanley, 2018, *Satellite-Based Assessment of Rainfall-Triggered Landslide Hazard for Situational Awareness* | Earth's Future, 6(3), 505–523；[10.1002/2017EF000715](https://doi.org/10.1002/2017EF000715) | 滑坡风险与情景信息来源 | NASA README 引用；原文与 DOI 元数据未核查 |
| Stanley & Kirschbaum, 2017, *A heuristic approach to global landslide susceptibility mapping* | Natural Hazards；[10.1007/s11069-017-2757-y](https://doi.org/10.1007/s11069-017-2757-y) | 易发性与概率的区分、模型因素 | NASA README 引用；原文未读 |
| Emberson, Kirschbaum & Stanley, 2020, *New global characterisation of landslide exposure* | NHESS, 20(12), 3413–3424；[10.5194/nhess-20-3413-2020](https://doi.org/10.5194/nhess-20-3413-2020) | 道路暴露与空间尺度的已有工作 | NASA README 引用；原文未读 |
| Khan et al., 2022, *Global Landslide Forecasting System for Hazard Assessment and Situational Awareness* | Frontiers in Earth Science, 10 | LHASA 系统介绍 | NASA README 的 DOI 显示文字为 `10.3389/feart.2022.878996`，链接目标却为 `10.3389/feart.2022.878`；须核查后使用 |

已发现的 DOI 文本与链接不一致说明，即使官方软件说明也需要逐条核对，不能自动导入引用库。

## 3. 最重要的待检索研究簇

| 研究簇 | 必须回答的问题 | 与本选题可能重叠的部分 |
|---|---|---|
| K shortest / alternative / diverse paths | 是否优化路线集合？多样性如何定义？ | 路径生成与路线组合的一般框架 |
| Edge/node-disjoint paths | 不相交约束、成本、不可行性如何处理？ | 避免共享道路及必经设施 |
| Shared risk link groups / risk-disjoint routing | 风险组是否允许重叠？同时毁坏多组如何处理？ | “不同边受到同一风险”的核心思想可能已有成熟研究 |
| Geographically / spatially correlated network failures | 灾害区域的形状、尺度、概率和联合失效如何表示？ | 空间共同失效与幸存路线组合 |
| Reliable / stochastic / robust route portfolios | 是否直接最大化至少一条路线可用？ | 本方案的目标函数和不确定性处理 |
| Disaster logistics / resilient road accessibility | 使用什么真实灾害标签和路网？ | 场景、评价指标及业务解释 |
| Landslide road exposure / runout mapping | 灾害范围怎样影响路段、何时代表真实阻断？ | 地理空间风险建模可能的贡献及误差边界 |

特别需要比较共享风险组方法与地理相关失效研究。如果这些工作已采用空间风险分组与至少一条路线幸存目标，本方案必须找到更具体的数据、机理或验证贡献。

## 4. 检索词与范围

建议在 Google Scholar、Web of Science、Scopus 或 Semantic Scholar 分别检索以下词组，再做前向与后向引用追踪；这些是检索词，不是假定所有平台共用的查询语法。

```
shared risk link group disjoint routing
geographically correlated failures alternative paths
spatially correlated failures reliable routing
backup route portfolio network reliability
disaster resilient alternative routes landslide
landslide road exposure accessibility
postseismic rainfall landslide road blockage
```

先独立检索网络可靠性与灾害路网两条线，避免所有检索都要求同时包含 landslide，漏掉最接近的算法工作。检索截至 2026-10-08，经典理论不设置下限年份。近年工作另行筛选，并核查实际出版状态。

建议先筛出最接近的 5–10 篇，再扩展；数量只是工作目标，不是现有阅读量。记录检索平台、日期、原始词组、筛选理由和可访问程度。

## 5. 经典方法的待核查线索

以下来自通用方法知识，当前未通过在线来源核实，不作为已验证参考文献：

- Suurballe, *Disjoint paths in a network*（1974）：核查不相交最短路径问题与本基线的适用条件。
- Nemhauser、Wolsey、Fisher，关于单调次模集合函数最大化近似的经典工作（1978）：核查精确题名与定理条件。
- [RFC 4202](https://www.rfc-editor.org/rfc/rfc4202.html)：本轮已读取原文第 2.3 节，核实 shared risk link group 的定义；见下方更新。它是术语/标准来源，不能代替学术现状检索。

数学方案使用的是已知最大覆盖结构，不把它包装成新理论。

## 6. 逐篇提取模板

每篇优先文献记录：

| 字段 | 内容要求 |
|---|---|
| 完整引用与访问层级 | 作者、题名、年份、期刊、DOI；元数据/摘要/正文分别标记 |
| 问题与输出 | 单路径或路径组合；固定 K 或自适应；备用或同时运输 |
| 风险表示 | 独立边、共享风险组、灾害区域、空间随机场、真实事件 |
| 优化目标与约束 | 可靠性、共同阻断、长度、时间、容量、不相交 |
| 地理空间信息 | DEM、遥感、道路几何、风险范围与空间尺度 |
| 求解与保证 | 候选范围、精确/近似/启发式；保证依赖的条件 |
| 验证 | 真实或合成；事件/区域划分；时间泄漏；强对照 |
| 最接近的重叠 | 本方案已经被该文完成的部分 |
| 可成立的差异 | 有证据支持的差异；未查到不等于未有人研究 |

## 7. 文献核查的完成标准

最接近的共同失效路线组合论文必须至少有可靠摘要，关键主张要读取正文；明确风险分组、空间区域失效和路线组合目标的已有工作后，才决定贡献表述。仅有 K 最短路径及滑坡预警文献不足以完成这一阶段。

## 8. 网络复查后的新增线索

新增记录见 [access_recheck_2026-10-08.json](../references/access_recheck_2026-10-08.json)。元数据、摘要与正文的访问层级分别记录，尚未开展完整引用追踪。

| 文献/标准 | 已核查层级 | 实际支持的信息与下一步 |
|---|---|---|
| Neumayer & Modiano, 2010, *Network Reliability With Geographically Correlated Failures*；[DOI](https://doi.org/10.1109/infcom.2010.5461984) | Crossref 元数据、OpenAlex 提供的摘要 | 摘要说明随机地理灾害、随机线切与二端可靠性，地理几何影响网络存活；需读取正文，比较其可靠性分析与本方案路线组合选择的差异 |
| Vass et al., 2026, *Availability-Aware Routing in Presence of Geographically Correlated Failures*；[DOI](https://doi.org/10.1109/infocom59046.2026.11571439) | Crossref 与 OpenAlex 元数据；未取得摘要或正文 | 题名高度接近，列为优先阅读全文的对象；不能仅凭题名断言目标、路线数量或方法已经相同 |
| Datta & Somani, 2008, *Graph transformation approaches for diverse routing in shared risk resource group (SRRG) failures*；[DOI](https://doi.org/10.1016/j.comnet.2008.04.017) | Crossref 与 OpenAlex 元数据；未取得摘要或正文 | 共享风险组路线规划的重要对照线索，须核查其约束、算法及风险模型 |
| Kincey et al., 2022, *Modelling post-earthquake cascading hazards: Changing patterns of landslide runout following the 2015 Gorkha earthquake, Nepal*；[DOI](https://doi.org/10.1002/esp.5501) | Crossref 元数据与摘要，DataCite 的机构存储记录 | 摘要明确使用多时相震后滑坡清单比较滑坡运动范围，并覆盖震后 4.5 年；这是数据与机理线索，不代表原始数据已取得，也不能直接支撑 24 小时道路风险预测 |
| RFC 4202，第 2.3 节 | 官方原文 | 明确定义共享资源失效可影响一组链路，一条链路可属于多个风险组，并建议多样路线避免共同链路与共同 SRLG；共同风险分离的基本概念已有明确先例 |

本轮结论是：共同风险与地理相关失效属于已有研究范畴。后续贡献应核查滑坡影响范围、道路脆弱性和独立灾害验证的具体差异，而非先宣称首次考虑共同失效。

Crossref 原始搜索包含无关结果和服务错误；未筛选结果只作为检索记录，不作为相关文献清单。上述 2026 文献元数据在两个检索服务中一致，但方法与结果仍未核实。

## 9. 用户提供期刊范围后的定向核查

两刊范围材料已归档，JAG限定检索与三篇相关论文的摘要核查已开展。题名、DOI、访问层级及对本方案的具体影响见[期刊定位更新](journal_fit.md)与[检索记录](../references/jag_related_search_2026-10-08.json)。

新增重点是空间信息怎样可靠地支持共同灾害暴露，以及空间相关制图误差如何传播到决策。不能只以出现 landslide 或 uncertainty 的题名判定最接近方法，也不能据这些摘要认定新颖性已经成立。
