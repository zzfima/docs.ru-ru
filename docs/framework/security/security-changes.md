---
title: "Изменения системы безопасности в .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Allow Partially Trusted Callers attribute
- .NET Framework 4, security changes
- .NET Framework security
- security-transparent code
- security-critical code
- code access security, changes
ms.assetid: 5e87881c-9c13-4b52-8ad1-e34bb46e8aaa
caps.latest.revision: 52
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b2ee4194f6e6788d99222badeb88e2702247904e
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="security-changes-in-the-net-framework"></a>Изменения системы безопасности в .NET Framework
Самое важное изменение в отношении безопасности в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] — это строгое именование. Описание этих изменений см. в разделе [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) .  
  
 В NET Framework предусмотрена двухуровневая модель безопасности для управляемых приложений. Приложения[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] работают в контейнере безопасности Windows, ограничивающем доступ к ресурсам. Внутри этого контейнера управляемые приложения работают с полным доверием. С точки зрения управления доступом для кода разработчик ничего не может сделать для повышения прав доступа. Сведения о привилегиях, предоставляемых операционной системой Windows, см. в разделе [Объявления характеристик приложения (приложения Магазина Windows)](http://go.microsoft.com/fwlink/?LinkId=230436) в Центре разработки для Windows. Сведения о создании приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] см. в разделе [Создание первого приложения для Магазина Windows на C# или Visual Basic](http://go.microsoft.com/fwlink/?LinkId=230461).

