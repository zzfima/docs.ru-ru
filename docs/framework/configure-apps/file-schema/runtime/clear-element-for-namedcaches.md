---
title: "Элемент &lt;clear&gt; для &lt;namedCaches&gt; | Microsoft Docs"
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
  - "<clear> - элемент для <namedCaches>"
  - "clear - элемент для <namedCaches>"
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Элемент &lt;clear&gt; для &lt;namedCaches&gt;
Очищает все записи `namedCache` в коллекции `namedCaches` для кэша памяти.  
  
## Синтаксис  
  
```  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## Тип  
 `Type`  
  
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
 Элемент `clear` очищает все записи `namedCache` в коллекции именованных кэшей для кэша памяти.  Элемент `clear` можно использовать перед использованием элемента `add`, чтобы добавить новую запись именованного кэша, чтобы убедиться, что в коллекции отсутствуют другие именованные кэши.  
  
## См. также  
 [Элемент \<namedCaches\> \(параметры кэша\)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)