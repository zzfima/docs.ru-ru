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
ms.openlocfilehash: af2869e5ca3b41778c094b7a78a9493e74868811
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204507"
---
# <a name="security-changes-in-the-net-framework"></a>Изменения системы безопасности в .NET Framework

Самым важным изменением безопасности в .NET Framework 4,5 является строгое именование. Описание этих изменений см. в разделе [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) .  
  
В NET Framework предусмотрена двухуровневая модель безопасности для управляемых приложений. Приложения Магазина Windows 8. x выполняются в контейнере безопасности Windows, который ограничивает доступ к ресурсам. Внутри этого контейнера управляемые приложения работают с полным доверием. С точки зрения управления доступом для кода разработчик ничего не может сделать для повышения прав доступа. Сведения о привилегиях, предоставляемых операционной системой Windows, см. в разделе [Объявления характеристик приложения (приложения Магазина Windows)](https://go.microsoft.com/fwlink/?LinkId=230436) в Центре разработки для Windows. Сведения о создании приложения для Магазина Windows 8. x см. в статье [Создание первого приложения для Магазина Windows C# с помощью или Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).
