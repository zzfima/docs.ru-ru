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
ms.openlocfilehash: bfc48d4fed127b288353f0295f2de1ca33e0a8fe
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971210"
---
# <a name="security-changes-in-the-net-framework"></a><span data-ttu-id="2ce68-102">Изменения системы безопасности в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2ce68-102">Security Changes in the .NET Framework</span></span>
<span data-ttu-id="2ce68-103">Самым важным изменением безопасности в .NET Framework 4,5 является строгое именование.</span><span class="sxs-lookup"><span data-stu-id="2ce68-103">The most important change to security in the .NET Framework 4.5 is in strong naming.</span></span> <span data-ttu-id="2ce68-104">Описание этих изменений см. в разделе [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) .</span><span class="sxs-lookup"><span data-stu-id="2ce68-104">See [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) for a description of those changes.</span></span>  
  
 <span data-ttu-id="2ce68-105">В NET Framework предусмотрена двухуровневая модель безопасности для управляемых приложений.</span><span class="sxs-lookup"><span data-stu-id="2ce68-105">The .NET Framework provides a two-tier security model for managed applications.</span></span> <span data-ttu-id="2ce68-106">Приложения[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] работают в контейнере безопасности Windows, ограничивающем доступ к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="2ce68-106">[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps run in a Windows security container that limits access to resources.</span></span> <span data-ttu-id="2ce68-107">Внутри этого контейнера управляемые приложения работают с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="2ce68-107">Within that container, managed applications run fully trusted.</span></span> <span data-ttu-id="2ce68-108">С точки зрения управления доступом для кода разработчик ничего не может сделать для повышения прав доступа.</span><span class="sxs-lookup"><span data-stu-id="2ce68-108">From a code access security (CAS) perspective, there is nothing a developer can do to elevate privileges.</span></span> <span data-ttu-id="2ce68-109">Сведения о привилегиях, предоставляемых операционной системой Windows, см. в разделе [Объявления характеристик приложения (приложения Магазина Windows)](https://go.microsoft.com/fwlink/?LinkId=230436) в Центре разработки для Windows.</span><span class="sxs-lookup"><span data-stu-id="2ce68-109">For information about the privileges granted by Windows, see [App capability declarations (Windows Store apps)](https://go.microsoft.com/fwlink/?LinkId=230436) in the Windows Dev Center.</span></span> <span data-ttu-id="2ce68-110">Сведения о создании приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] см. в разделе [Создание первого приложения для Магазина Windows на C# или Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).</span><span class="sxs-lookup"><span data-stu-id="2ce68-110">For information about creating a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, see [Create your first Windows Store app using C# or Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).</span></span>
