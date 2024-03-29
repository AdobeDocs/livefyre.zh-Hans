---
description: 使用“审核”选项卡为传入内容设置预审核规则，包括亵渎列表、标志规则和禁止的IP地址。
title: 设置审核
exl-id: 09fc44c4-7ee1-47fd-ae68-885532a6f03f
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '1276'
ht-degree: 0%

---

# 设置审核{#setting-up-moderation}

使用“审核”选项卡为传入内容设置预审核规则，包括亵渎列表、标志规则和禁止的IP地址。

## 仲裁的工作原理{#section_kyf_gvc_t1b}

您可以通过以下方式审核内容：

* 根据您在发布内容之前设置的规则自动预审内容以过滤掉不想要的内容。
* 使用库中的ModQ或应用程序内容，手动删除或批准使用自动预审核标记的内容。
* 确定那些通过禁止特定Livefyre用户、社交用户或IP地址反复发布冒犯性内容以阻止其发布的网站访客。
* 确定允许列出用户或关闭特定流、站点或网络的过滤器始终可以显示的人物和内容。

您可以通过以下方式自动预审内容：

* 设置规则以自动标记某些类型的内容：

   * 为使用&#x200B;**[!UICONTROL Settings > Moderation > Rules]**&#x200B;的站点访客标志标记的内容设置标志规则
   * 使用&#x200B;**[!UICONTROL Settings > Moderation > Rules]**&#x200B;设置SAFE规则
   * 禁止使用&#x200B;**[!UICONTROL Settings > Streams]**&#x200B;的特定Twitter用户
   * 禁止使用&#x200B;**[!UICONTROL Settings > Bans]**&#x200B;的IP地址
   * 按请求按国家/地区代码禁止IP区域。 禁止的内容将标记为垃圾信息。

* 在&#x200B;**[!UICONTROL Settings > Moderation > Rules]**&#x200B;下的“网络”或“站点”的“亵渎”列表中创建一列表字，以便您认为这些字是亵渎的。
* 通过使用或关闭特定流、站点或网络的过滤器，允许列出用户（始终允许这些用户显示内容）。

在设置了亵渎列表、SAFE过滤器和规则后，您可以选择是否在流中预审核内容并应用SAFE过滤器。 有关详细信息，请参阅[所有流规则的流规则选项](/help/using/c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)。

Livefyre将内容标记为&#x200B;**[!UICONTROL Approved]**、**[!UICONTROL Pending]**、**[!UICONTROL Junk]**&#x200B;等。 根据内容的来源、发布位置以及您在系统中设置的规则。 下表详细描述了Livefyre采取的操作，具体取决于这些因素。

## 审核的工作原理

| 内容来自： | 将内容发送到： | 批准状态 |
|--- |--- |--- |
| 库 | 应用程序 | 已批准的内容 |
| 社交搜索 | 应用程序 | 已批准的内容 |
| 流规则 | 应用程序 | 内容是否被SAFE过滤器标记为“垃圾邮件”？<br><ul><li>否 — 流到应用程序审核工作流</li><li>是 — 内容被丢弃</li></ul> |
| 库 | 文件夹 | 无状态（在文件夹中，未发布，未丢弃） |
| 社交搜索 | 文件夹 | 无状态（在文件夹中，未发布，未丢弃） |
| 流规则 | 文件夹 | 内容是否被SAFE过滤器标记为“垃圾邮件”？<br><ul><li>否 — 无状态（在文件夹中，未发布，未丢弃）</li><li>是 — 内容被丢弃</li></ul> |
| 应用程序帖子 | 应用程序 | 内容是否被SAFE过滤器标记为“垃圾邮件”？<br><ul><li>否 — 应用程序后审核工作流</li><li>是 — 内容被丢弃</li></ul> |

## 流到应用程序审核工作流{#section_z5z_w4d_t1b}

![](assets/stream_to_app_workflow.png)

在将流中的内容发布到应用程序之前，Livefyre会执行以下检查以确定如何处理内容：

1. 如果SAFE将内容标记为垃圾或丢弃，则Livefyre会丢弃该内容。
1. 如果SAFE未将内容标记为垃圾邮件，Livefyre将检查是否打开预审核。
1. 如果启用了预审核，Livefyre会将内容标记为“待定”。
1. 如果设置了ModQ规则，则Livefyre会将内容发送到ModQ。
1. 如果未打开预审，Livefyre将检查SAFE是否标记了该内容。
1. 如果SAFE标记了内容，则Livefyre将批准该内容并将内容发布到App。
1. 如果SAFE标记内容，而您未设置SAFE规则，则Livefyre会批准该内容并将内容发布到App。
1. 如果SAFE标记内容并您设置了SAFE规则，则Livefyre会检查您是否为流设置了SAFE规则。
1. 如果您为流设置SAFE规则，Livefyre将批准内容并将内容发布到App。 如果您未为流设置SAFE规则，Livefyre将使用审核SAFE规则来确定如何处理内容（发送到ModQ、垃圾桶等）。

## 应用程序后审核工作流{#section_fwn_w4d_t1b}

![](assets/post_to_app_workflow.png)

在将App帖子中的内容发布到App之前，Livefyre会执行以下检查以确定如何处理内容：

1. 如果SAFE过滤器将内容标记为drop，则Livefyre将删除内容。
1. 如果SAFE未将内容标记为“drop”，Livefyre将检查是否打开预审核。 如果启用了预审核，Livefyre会将内容标记为“待定”。 如果您设置了ModQ规则，则Livefyre会将内容作为待处理内容发送到ModQ。 否则，内容将在库中的应用程序内容中保持挂起状态。
1. 如果未打开预审，Livefyre将检查SAFE是否标记了该内容。 否则，Livefyre将批准内容并将内容发布到应用程序。
1. 如果SAFE标记内容，而您设置了SAFE规则，Livefyre将使用SAFE规则确定如何处理内容（发送到ModQ、垃圾桶等）。 如果SAFE标记内容，而您未设置SAFE规则，则Livefyre会批准该内容并将内容发布到App。

## 批量过滤器{#section_lyk_ktx_vy}

“批量过滤”功能可以在短时间内在所有Livefyre网络中查找发布的重复内容。 如果检测到此内容，则将其标记为“批量”，然后在默认情况下进行丢弃。 批量内容可能由用户生成（如“触及！”） 在流行的足球比赛期间，多次在聊天中发布)，大多数都来自垃圾邮件活动。 此过滤器与语言无关，可与任何语言一起使用。 要自定义批量过滤器，必须联系Livefyre支持。

## 规则 {#section_gqz_ksk_f1b}

使用“规则”部分可根据SAFE和用户应用的标志创建预审核规则。 此面板优惠了两种规则：

* **[!UICONTROL Flag Rules:]** 指定应对由用户标记的注释执行的定义次数的操作。
* **[!UICONTROL SAFE Rules:]***将SAFE标志与对标记内容采取的操作结合起来。

要创建标志规则，请选择标志（冒犯、关闭主题、反对或垃圾信息），输入必须将其应用于某个内容的次数，然后选择要执行的操作。 您可以为每个标志选项（“冒犯”、“关闭主题”、“反对”或“垃圾邮件”）设置一个标志规则。

您可以在网络、站点和流级别创建规则。 站点级规则将继承网络规则，除非您以不同方式配置站点规则。 流规则将继承站点规则，除非您以不同方式配置它们。

可用操作：

* **[!UICONTROL Trash it:]***将标记的注释发送到垃圾桶。
* **[!UICONTROL Bozo it:]** 隐藏所有用户（其作者除外）的已标记注释，该注释仍对其可见。
* **[!UICONTROL Pending:]** 将内容设置为“待定”。如果在&#x200B;**[!UICONTROL Settings > ModQ]**&#x200B;下将“预审核”设置为ON，则它将位于ModQ中。 否则，它将仅在应用程序内容中。

>[!NOTE]
>
>Livefyre建议您为五个用户标记为“垃圾邮件”或“冒犯性”的Bozo注释创建规则。

## 审核Recommendations {#section_ec3_vr3_2cb}

您可以使用审核推荐来帮助您确定如何审核Livefyre应用程序中网站访客发布的内容。 审核建议指示器会根据您之前对类似内容执行的操作，建议何时可能丢弃某条内容。 要使用审核Recommendations:

1. 联系您的Adobe Livefyre支持专业人员，打开“协调Recommendations”功能。
1. 在“网络设置”中设置审核推荐。

   使用&#x200B;**[!UICONTROL Network Settings]**&#x200B;下的&#x200B;**[!UICONTROL Livefyre Recommends Trash]**&#x200B;设置设置审核推荐。

   ![](assets/image_mod_reco_trash.png)

1. 设置SAFE规则，告诉Livefyre如何处理审核推荐识别为可能被丢弃的内容的内容。 有关如何为&#x200B;**[!UICONTROL Livefyre Recommends Trash]**&#x200B;选项设置SAFE规则的详细信息，请参阅[审核](/help/using/c-features-livefyre/c-about-moderation/c-moderation.md#c_moderation)。

   ![](assets/modreco4.png)

1. 使用ModQ或App Content中的&#x200B;**[!UICONTROL Moderation Recommendation Indicator]**&#x200B;筛选审核推荐所标识的可能被传输的内容。

   在ModQ中，指示符如下所示： ![](assets/mod_reco1.png)

   有关如何使用审核Recommendations在ModQ中审核内容的详细信息，请参阅[ModQ](/help/using/c-features-livefyre/c-about-moderation/c-modq.md#c_modq)。

   在应用程序内容中，审核推荐如下所示： ![](assets/modreco3.png)

   有关如何在应用程序内容中使用审核Recommendations的详细信息，请参阅[使用应用程序内容审核内容](/help/using/c-features-livefyre/c-about-moderation/c-moderate-content-using-app-content.md#c_moderate_content_using_app_content)。
