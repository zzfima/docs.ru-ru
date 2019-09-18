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
ms.openlocfilehash: f4cf91924e762495df6787a187e4295b69f2cd96
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045375"
---
# <a name="security-changes-in-the-net-framework"></a>Изменения системы безопасности в .NET Framework

Самым важным изменением безопасности в .NET Framework 4,5 является строгое именование. Описание этих изменений см. в разделе [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) .  
  
В NET Framework предусмотрена двухуровневая модель безопасности для управляемых приложений. Приложения[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] работают в контейнере безопасности Windows, ограничивающем доступ к ресурсам. Внутри этого контейнера управляемые приложения работают с полным доверием. С точки зрения управления доступом для кода разработчик ничего не может сделать для повышения прав доступа. Сведения о привилегиях, предоставляемых операционной системой Windows, см. в разделе [Объявления характеристик приложения (приложения Магазина Windows)](https://go.microsoft.com/fwlink/?LinkId=230436) в Центре разработки для Windows. Сведения о создании приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] см. в разделе [Создание первого приложения для Магазина Windows на C# или Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).
