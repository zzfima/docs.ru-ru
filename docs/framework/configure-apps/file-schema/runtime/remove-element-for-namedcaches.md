---
title: "Элемент &lt;remove&gt; для &lt;namedCaches&gt; | Microsoft Docs"
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
  - "<remove> - элемент для namedCaches"
  - "remove - элемент для namedCaches"
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Элемент &lt;remove&gt; для &lt;namedCaches&gt;
Удаляет запись именованного кэша из коллекции `namedCaches` для кэша памяти.  
  
## Синтаксис  
  
```  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## Тип  
 `None`  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 `None`  
  
### Дочерние элементы  
 `None`  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<namedCaches\>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Содержит коллекцию параметров конфигурации для именованных экземпляров <xref:System.Runtime.Caching.MemoryCache>.|  
  
## Заметки  
 Элемент `remove` удаляет запись `namedCache` из коллекции именованных кэшей для кэша памяти.  
  
## См. также  
 [Элемент \<namedCaches\> \(параметры кэша\)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)