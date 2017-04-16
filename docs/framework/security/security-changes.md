---
title: "Изменения системы безопасности в .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "атрибут, разрешающий вызовы с неполным доверием"
  - ".NET Framework 4, изменения системы безопасности"
  - "безопасность платформы .NET Framework"
  - "прозрачный для системы безопасности код"
  - "критичный в плане безопасности код"
  - "управление доступом для кода, изменения"
ms.assetid: 5e87881c-9c13-4b52-8ad1-e34bb46e8aaa
caps.latest.revision: 52
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 52
---
# Изменения системы безопасности в .NET Framework
Самое важное изменение в отношении безопасности в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] — это строгое именование. Описание этих изменений см. в разделе [Усовершенствованное строгое именование](../../../docs/framework/app-domains/enhanced-strong-naming.md).  
  
 В NET Framework предусмотрена двухуровневая модель безопасности для управляемых приложений. Приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] работают в контейнере безопасности Windows, ограничивающем доступ к ресурсам. Внутри этого контейнера управляемые приложения работают с полным доверием. С точки зрения управления доступом для кода разработчик ничего не может сделать для повышения прав доступа. Сведения о привилегиях, предоставляемых операционной системой Windows, см. в разделе [Объявления характеристик приложения \(приложения Магазина Windows\)](http://go.microsoft.com/fwlink/?LinkId=230436) в Центре разработки для Windows. Сведения о создании приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] см. в разделе [Создание первого приложения для Магазина Windows на C\# или Visual Basic](http://go.microsoft.com/fwlink/?LinkId=230461).