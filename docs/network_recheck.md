# 网站复查与初步发现

复查日期：2026-10-08（Asia/Shanghai）。完整请求结果与文献线索见 [access_recheck_2026-10-08.json](../references/access_recheck_2026-10-08.json)。

## 1. 实际访问结果

环境配置元数据当前显示网络策略为 `unrestricted`。以下状态来自实际请求，不能仅凭配置推断网站是否可达。

| 来源 | 结果 | 已取得的内容 |
|---|---|---|
| Crossref API | HTTP 200 | 文献检索与定向题名查询；并发检索个别请求出现 429/500，后续低并发查询成功 |
| OpenAlex API | HTTP 200 | 论文元数据、部分摘要和开放获取位置线索 |
| USGS 有效入口 | HTTP 200 | Landslide Hazards 程序页、官方搜索及地震诱发地表破坏清单库说明 |
| DataCite API | HTTP 200 | Gorkha 相关文献机构存储与其他数据条目；结果仍需筛选 |
| RFC 4202 | HTTP 200 | 官方 HTML/TXT 原文，已核查第 2.3 节 |
| NASA LHASA README | HTTP 200 | 官方软件资料正常可访问 |
| JAG aims and scope | 代理连接 403 Forbidden | 未取得页面内容 |
| ISPRS aims and scope | 代理连接 403 Forbidden | 未取得页面内容 |

原 USGS 路径 `/programs/earthquake-hazards/science/earthquake-induced-landslides` 返回 HTTP 404。此前无法区分路径是否有效，本轮已确认需要更换链接，不能继续把它归类为整个 USGS 被阻断。

有效数据入口：[An Open Repository of Earthquake-Triggered Ground-Failure Inventories](https://www.usgs.gov/data/open-repository-earthquake-triggered-ground-failure-inventories)，数据发布 DOI 为 [10.5066/F7H70DB4](https://doi.org/10.5066/F7H70DB4)。官网说明其提供原始数字清单（如可得）及统一属性的集成数据库，并记录原作者报告的制图方法与完整性。当前只读取了网页说明，没有下载清单或确认具体地区、时间与许可是否满足本研究。

## 2. 对研究判断的影响

**共享风险分离的思想已有明确先例。** RFC 4202 第 2.3 节定义 SRLG：一组链路共享某个资源，该资源失效可影响整个组；同一链路可以属于多个组。原文还建议多样路线同时避免共同链路和共同 SRLG。不能将“避免多条路线经过同一风险”作为未经核查的首次创新。

**地理相关失效也有直接研究。** Neumayer & Modiano 的 2010 年论文摘要讨论随机地理灾害、线切及二端可靠性，强调网络几何对存活的影响。它提供基础背景，但摘要不足以判断路线组合选择是否已被解决。

**存在高度相关的新文献需要优先阅读全文。** 2026 年 *Availability-Aware Routing in Presence of Geographically Correlated Failures* 的题名、DOI及作者信息已由 Crossref/OpenAlex 核查，尚未取得摘要或正文。必须比较其方法与目标后再决定创新表述。

**Gorkha 有多时相震后研究线索。** Kincey et al. (2022)，[10.1002/esp.5501](https://doi.org/10.1002/esp.5501)，摘要使用多时相震后滑坡清单验证运动范围，并讨论震后 4.5 年的演化。这提高了继续核查该区域的价值，但并不证明原始清单公开可下载或可以支持 24 小时救援风险预测。若只有季节/多年分辨率，应明确调整时间尺度与应用主张。

本轮未下载任何研究论文全文或地理空间数据，未执行真实实验，未完成系统综述。

## 3. 后续获取重点

利用已恢复的 API 定向检索，并优先查 2026 年高度相关论文、共享风险组路线方法的正文及 Gorkha 多时相数据。对期刊范围页面，用户提供官方说明文字仍有帮助。无需因首次网络失败要求用户代查全部来源，也不再要求添加已经开放的同一域名。
