---
title: "Схема веб-параметров | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
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
  - "система конфигурации ASP.NET, схема веб-параметров"
  - "файлы конфигурации [ASP.NET]"
  - "схема конфигурации [платформа .NET Framework], веб-параметры"
  - "схема веб-параметров"
  - "веб-параметры, схема [ASP.NET]"
  - "Web.config - файл конфигурации [ASP.NET]"
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# Схема веб-параметров
Веб\-параметры задают ЦП и параметры ASP.NET уровня выполнения, которые применяются к поведению на уровне всего процесса, управляемому уровнем размещения ASP.NET.  Эти параметры отличаются от параметров приложения доменного типа, задаваемых в файле Web.config приложения ASP.NET.  
  
 Веб\-параметры содержатся в файлах Aspnet.config, находящихся в установочных папках версий платформы .NET Framework.  Например, файл Aspnet.config для [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] находится в следующей папке:  
  
 `C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
 Веб\-параметры не используются ни в каких других файлах конфигурации, таких как файл machine.config, корневой файл Web.config или файлы Web.config уровня приложения.  
  
 [Элемент \<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [Элемент \<system.web\> \(Веб\-параметры\)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)  
  
 [Элемент \<applicationPool\> \(Веб\-параметры\)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<system.web\>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|Содержит сведения, используемые уровнем размещения ASP.NET.|  
|[\<applicationPool\>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Задает ЦП и параметры ASP.NET уровня выполнения, которые применяются к поведению на уровне всего процесса, управляемому уровнем размещения ASP.NET.|  
  
## См. также  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)