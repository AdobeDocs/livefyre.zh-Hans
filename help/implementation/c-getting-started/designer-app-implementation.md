---
description: 将Bootstrap和流API与Livefyre应用程序结合使用。
title: 应用程序实施
uuid: null
exl-id: f1edef86-491d-4f8e-8ce5-f6e019d057ec
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# 应用程序实施{#appimplementation}

用例：作为客户，我希望使用Livefyre.js方法将Livefyre集成到我的第三方CMS中。

在自定义AEM组件或其他CMS（如WordPress、Sitecore或DemandWare）中实施Livefyre有三种方法：设计器应用程序实施、API、实施和第三方身份验证集成。

## 设计器应用程序实施{#designerapp}

什么：最简单、最快速的Livefyre应用程序集成方式。 您可以设计、配置和生成自定义的Javascript嵌入代码，在几分钟内将LiveFree应用程序集成到页面上。

操作方法：[创建、预览、发布和嵌入Livefyre应用程序](/help/using/c-about-apps/c-create-an-app.md)

示例：[https://codepen.io/dharafyre/pen/bvGrLo](https://codepen.io/dharafyre/pen/bvGrLo)

### Livefyre.js实施{#livefyrejsimp}

什么：[Livefyre.js](/help/implementation/c-livefyre.js.md)是为站点上的Apps和Auth提供支持的核心库。 它定义全局`window.Livefyre`对象和单个公共方法Livefyre.require，该方法可用于加载其他Livefyre JavaScript库，这些库有助于嵌入Livefyre应用程序并与第三方用户身份验证平台集成。

操作方法：

* [使用CollectionMeta令牌创建集合](/help/implementation/t-create-a-collectionmeta-token.md)

* 使用应用程序集成将应用程序集成到第三方CMS

示例：

* 评论应用程序：[https://codepen.io/dharafyre/pen/oYoJdP](https://codepen.io/dharafyre/pen/oYoJdP)

* 评论应用程序：[https://codepen.io/dharafyre/pen/GXgvvd](https://codepen.io/dharafyre/pen/GXgvvd)

* 媒体墙：[https://codepen.io/dharafyre/pen/dNMPvM](https://codepen.io/dharafyre/pen/dNMPvM)

* 有关使用SDK进行高级自定义的信息，请参阅StreamHub SDK。

## API实现{#apiimplementation}

要创建自定义体验和数据可视化，可以使用Bootstrap和流API使用Livefyre和社交数据从头开始创建Livefyre应用程序。

## 第三方身份验证集成{#thirdpartyauth}

有关需要身份验证的Livefyre应用程序，请参阅[Identity Integration](/help/implementation/t-about-identity-integration/t-about-identity-integration.md)以了解第三方身份验证平台。

## 客户示例{#customerexamples}

以下客户通过第三方CMS集成实施了Livefyre:

* [PGA巡回媒体墙](https://www.pgatour.com/social-hub.html)

* [超时](https://www.timeout.com/london/restaurants/forest-bar-kitchen#tab_panel_3)
