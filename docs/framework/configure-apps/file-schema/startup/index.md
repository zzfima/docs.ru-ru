---
title: "Схема параметров запуска | Microsoft Docs"
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
  - "схема конфигурации [платформа .NET Framework], параметры запуска"
  - "параметры запуска схемы"
  - "схема параметров запуска"
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Схема параметров запуска
Параметры запуска задают версию среды CLR, которая должна запускать приложение.  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<requiredRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|Указывает, что приложение поддерживает только версию 1.0 среды CLR.  Приложения, собранные с помощью среды выполнения версии 1.1, должны использовать элемент **\<supportedRuntime\>**.|  
|[\<supportedRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|Указывает, какие версии среды CLR поддерживает приложение.|  
|[\<начальные\>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|Содержит элементы **\<requiredRuntime\>** и **\<supportedRuntime\>**.|  
  
## См. также  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<PaveOver\> Specifying Which Runtime Version to Use](http://msdn.microsoft.com/ru-ru/c376208d-980d-42b4-865b-fbe0d9cc97c2)