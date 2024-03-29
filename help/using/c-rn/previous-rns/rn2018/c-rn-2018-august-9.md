---
description: 2018年8月9日版本的发行说明。
title: 2018 年 8 月 9 日
exl-id: 7b2fb562-33bf-4c34-ab83-5fc34f5d1f4f
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 8%

---

# 2018 年 8 月 9 日{#august}

2018年8月9日版本的发行说明。

## 新增功能 {#section_syx_mdt_wcb}

**视频智能标** 签：用户现在可以看到50MB以下视频的智能标签。

## 问题 {#section_ehw_ndt_wcb}

此版本中解决了下表中的问题。

## 生产版本

| **问题类型** | **组件** | **发行说明** |
|---|---|---|
| 错误 | 应用程序内容 | 修复了管理员和内容管理者无法编辑应用程序内容中内容的问题。 |
| 增强功能 | 应用程序 | 社交网络已进行隐私更改，这意味着Facebook或Twitter不再支持社交提及。 |
| 增强功能 | 应用程序 | 社交网络已经改变了隐私。 已删除将内容自动发布到社交网络(Facebook、LinkedIn、Twitter)的“发布到”功能。 |
| 增强功能 | GDPR | 从“设置”>“隐私”下的请求详细信息页面删除了详细信息模式的切换。 在URL末尾添加/dbg仍可以访问详细信息模式切换。 |
| 错误 | 集成：AEM | 修复了在AEM中拖放Livefyre应用程序时似乎会创建多个应用程序的问题。 |
| 错误 | 库 | 修复了资源未在库中正确保存的问题。 |
| 错误 | Livefyre Identity | 修复了LF标识在登录时导致403个错误的问题。 |
| 错误 | 社交搜索 | 修复了用户无法使用社交搜索中的URL选项搜索公共Facebook帖子的问题。 |
| 增强功能 | 社交同步 | 社交网络已进行隐私更改，这意味着Facebook将不再支持Social Sync。 |
| 增强功能 | 流 | 现在，在删除应用程序时，您会删除与该应用程序关联的所有流。 |
| 增强功能 | Studio | 现在，客户能够将Livefyre事件分别发送到Adobe Analytics，而不是分批发送。 |
| 增强功能 | Studio | 用于社交网络的对话应用程序中显示的模态窗口现在将是来自社交网络的模态窗口，而不是Adobe Experience Manager Livefyre或其他品牌的模态窗口。 |

## UAT版本

在UAT版本发行版中解决了下表中的问题。

| **问题类型** | **组件** | **发行说明** |
|---|---|---|
| 错误 | GDPR | 修复了某些Instagram视频不显示退出消息的问题。 |
| 错误 | 库 | 修复了授予权限的卡手动显示错误权限请求状态的问题。 |
| 错误 | 库 | 修复了无法将资产保存到文件夹的问题。 |
| 错误 | 库/搜索 | 恢复了在Social Search中从Instagram搜索URL的功能。 |
| 错误 | ModQ | 修复了ModQ中“更多信息”菜单未在预期位置显示的问题。 |
| 错误 | Rights Management | 修复了页面滚动时ModQ中排序应处于固定位置的问题。 |
| 错误 | 流 | 修复了在暂存环境上查看流的问题。 |
| 增强功能 | 流 | 添加了“安全工作”(SFW)和“非安全工作”(NSFW)切换到“流”。 |
| 增强功能 | Studio | 为通过FileStack上传到Livefyre Studio Library的内容（“所有资产”中的上传功能）添加了智能标记功能。 |
