---
title: Изменения системы безопасности в .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- Allow Partially Trusted Callers attribute
- .NET Framework 4, security changes
- .NET Framework security
- security-transparent code
- security-critical code
- code access security, changes
ms.assetid: 5e87881c-9c13-4b52-8ad1-e34bb46e8aaa
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c62a469b3e31283e5790c747092a8fe504ef8c2a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670162"
---
# <a name="security-changes-in-the-net-framework"></a><span data-ttu-id="663bb-102">Изменения системы безопасности в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="663bb-102">Security Changes in the .NET Framework</span></span>
<span data-ttu-id="663bb-103">Самое важное изменение в отношении безопасности в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] — это строгое именование.</span><span class="sxs-lookup"><span data-stu-id="663bb-103">The most important change to security in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] is in strong naming.</span></span> <span data-ttu-id="663bb-104">Описание этих изменений см. в разделе [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) .</span><span class="sxs-lookup"><span data-stu-id="663bb-104">See [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) for a description of those changes.</span></span>  
  
 <span data-ttu-id="663bb-105">В NET Framework предусмотрена двухуровневая модель безопасности для управляемых приложений.</span><span class="sxs-lookup"><span data-stu-id="663bb-105">The .NET Framework provides a two-tier security model for managed applications.</span></span> <span data-ttu-id="663bb-106">Приложения[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] работают в контейнере безопасности Windows, ограничивающем доступ к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="663bb-106">[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps run in a Windows security container that limits access to resources.</span></span> <span data-ttu-id="663bb-107">Внутри этого контейнера управляемые приложения работают с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="663bb-107">Within that container, managed applications run fully trusted.</span></span> <span data-ttu-id="663bb-108">С точки зрения управления доступом для кода разработчик ничего не может сделать для повышения прав доступа.</span><span class="sxs-lookup"><span data-stu-id="663bb-108">From a code access security (CAS) perspective, there is nothing a developer can do to elevate privileges.</span></span> <span data-ttu-id="663bb-109">Сведения о привилегиях, предоставляемых операционной системой Windows, см. в разделе [Объявления характеристик приложения (приложения Магазина Windows)](https://go.microsoft.com/fwlink/?LinkId=230436) в Центре разработки для Windows.</span><span class="sxs-lookup"><span data-stu-id="663bb-109">For information about the privileges granted by Windows, see [App capability declarations (Windows Store apps)](https://go.microsoft.com/fwlink/?LinkId=230436) in the Windows Dev Center.</span></span> <span data-ttu-id="663bb-110">Сведения о создании приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] см. в разделе [Создание первого приложения для Магазина Windows на C# или Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).</span><span class="sxs-lookup"><span data-stu-id="663bb-110">For information about creating a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, see [Create your first Windows Store app using C# or Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).</span></span>
