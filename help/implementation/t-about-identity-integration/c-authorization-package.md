---
description: 安装身份验证包以启用用户身份验证，以便用户能够与您的应用程序交互。
title: 身份验证包
exl-id: 639032ee-ed7d-4cb0-83ba-f11d3dc607b6
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 1%

---

# 身份验证包{#authentication-package}

安装身份验证包以启用用户身份验证，以便用户能够与您的应用程序交互。

Livefyre应用程序使用全局身份验证包将用户与应用程序操作关联。 身份验证包可通过`Livefyre.require`使用。

要在您的页面上启用身份验证，请首先将`Livefyre.js`添加到您的网页或网站模板的`<head>`元素。

```
<script src="//cdn.livefyre.com/Livefyre.js"></script>
```

使用Livefyre.require启用身份验证与使用要求调用其他包类似。 需要身份验证的集成代码如下所示：

```
Livefyre.require(['auth'], function (auth) {  
// Perform action... 
});
```

## 方法 {#section_ojx_1lz_fz}

使用`Livefyre.require`将身份验证模块包含在上面之后，身份验证模块将显示以下方法，您可以调用这些方法来通知页面上的其他应用程序有关身份验证相关事件的信息。

| 方法 | 描述 |
|--- |--- |
| `.login(callback)` | 触发注册的AuthDelegate实现的登录流。 通常，只有启用身份验证的应用程序才会调用此项，而不是主机页面本身。 |
| `.logout(callback)` | 通知身份验证最终用户已通过某些外部方式注销，并且所有依赖应用程序应清除其身份验证状态，直到下次登录。 这将清除由Auth维护的内部会话。 |
| `.authenticate(credentials)` | 通知身份验证用户已通过某些外部方式的身份验证，并且已为最终用户购买了Livefyre身份验证令牌。 如果您使用Livefyre令牌设置了Cookie，或者用户有令牌并希望显式登录用户，则使用此选项。 例如：<br>`auth.authenticate({&nbsp;livefyre:&nbsp;`<br>`'<insert&nbsp;lftoken&nbsp;string&nbsp;for&nbsp;newly&nbsp;logged-in&nbsp;user>'&nbsp;});` |
| `.delegate(authDelegate)` | 将身份验证的实施详细信息（例如，您的自定义身份验证流）委派给您定义的对象。 必须由主机页调用，才能启用Livefyre应用程序的交互功能。 |
