---
description: 计算精选的社交项目数。
title: 社交计数器
exl-id: def7fba4-1c2e-4c7b-84f7-f9ede592d675
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 11%

---

# 社交计数器{#social-counter}

计算精选的社交项目数。 有关可用端点的完整列表，请参阅Livefyre [API参考](https://api.livefyre.com/docs)部分。

Social计数器API会返回给定集合中一段时间内间隔的匹配管理规则计数。

>[!NOTE]
>
>此API仅对Twitter主题标签可用。

社交计数器API:

* 资源
* 规则类型
* 响应

## 资源 {#section_p2s_2hc_11b}

```
GET https://{networkName}.bootstrap.fyre.co/api/v3.0/stats.collections.curate/{query}.json
```

* **networkName：您** 的Livefyre提供了网络名称。例如：`labs.fyre.co`中的&#x200B;*labs*。
* **查询:** 所有站点的url安全基本64编码哈希、文章ID、应获取计数信息的规则类型表（预编码）

   ```
   {site ID}:{article ID};{rule-type},  {article ID};{rule-type}|{site ID}:{article ID};{rule-type}
   ```

   >[!NOTE]
   >查询仅限10个站点、文章ID和规则类型示例。 （上一个示例将包含3个示例。）

* **from** `(optional)` 指定图形的相对或绝对时间段；from指定开始，如果省略，则默认为24小时前。
* **untl指定** `(optional)` 图形的相对或绝对时间段；until指定开始，如果省略，则默认为当前时间（现在）。

### 相对时间

| 缩写 | 单位 |
|---|---|
| s | 秒 |
| min（分钟） | 分钟 |
| h | 小时 |
| d | 天数 |
| w | 周 |
| 蒙 | 30天（月） |
| y | 365天（年） |

示例：

```
https://labs-t402.bootstrap.fyre.co/api/v3.0/stats.collections.curate/MTIzNDU2OnNvbWUtYXJ0aWNsZS1pZDsy.json&from=-7d&until=-6d
```

## 绝对时间{#section_xqr_jgc_11b}

格式：HH:MM_YYYYMMDD

| 缩写 | 含义 |
|---|---|
| HH | 小时（24小时时钟格式） |
| MM | 分钟 |
| YYYY | 4位数年份 |
| MM | 月 |
| DD | 日 |

示例：

```
https://labs-t402.bootstrap.fyre.co/api/v3.0/stats.collections.curate/MTIzNDU2OnNvbWUtYXJ0aWNsZS1pZDsy.json&from=04:00_20130709 
```

## 规则类型{#section_v53_xqb_11b}

| 值 | 类型 |
|---|---|
| 2 | Twitter |

示例：

要获取站点`123456`和文章ID `some-article-id`和规则类型`2`在最后一分钟的计数，例如：`123456:some-article-id;2:`

```
curl -XGET "https://labs-t402.bootstrap.fyre.co/api/v3.0/stats.collections.curate/MTIzNDU2OnNvbWUtYXJ0aWNsZS1pZDsy.json&from=-1min" 
```

示例响应：

```
{ 
    "status": "ok", 
    "code": 200, 
    "data": { 
        "123456": { 
            "some-article-id": { 
                "2": [ 
                    [ 
                        2, 
                        1374770460 
                    ], 
                    [ 
                        4, 
                        1374770470 
                    ], 
                    [ 
                        3, 
                        1374770480 
                    ], 
                    [ 
                        1, 
                        1374770490 
                    ], 
                    [ 
                        0, 
                        1374770500 
                    ], 
                    [ 
                        7, 
                        1374770510 
                    ] 
                ] 
            } 
        } 
    } 
}
```
