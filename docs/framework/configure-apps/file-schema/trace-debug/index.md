---
title: "Схема параметров трассировки и отладки | Microsoft Docs"
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
  - "схема конфигурации [платформа .NET Framework], параметры трассировки и отладки"
  - "разделы конфигурации [платформа .NET Framework]"
  - "параметры конфигурации [платформа .NET Framework], отладка"
  - "параметры конфигурации [платформа .NET Framework], трассировка"
  - "элементы [платформа .NET Framework], параметры трассировки и отладки"
  - "параметры конфигурации схемы"
  - "прослушиватели трассировки, схема параметров трассировки и отладки"
  - "трассировка [платформа .NET Framework], схема параметров трассировки и отладки"
ms.assetid: 277ca5f6-e1c4-41b6-a47f-3a67ce5b94ac
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Схема параметров трассировки и отладки
Параметры трассировки и отладки задают прослушиватели трассировки, предназначенные для сбора, хранения и маршрутизации сообщений, а также уровень, на котором установлен переключатель трассировки.  
  
 В следующей таблице описывается назначение каждого элемента трассировки и отладки.  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|Добавляет прослушиватель в коллекцию `Listeners`.|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-sharedlisteners.md)|Добавляет прослушиватель в коллекцию `sharedListeners`.|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|Задает уровень, на котором устанавливается переключатель трассировки.|  
|[\<assert\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|Указывает, следует ли отображать сообщение при вызове метода <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>, а также задает имя файла для записи сообщений.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|Очистка коллекции `Listeners` для источника трассировки.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|Очищает коллекцию `Listeners` для трассировки.|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|Добавляет фильтр в прослушиватель в коллекции `Listeners` для трассировки.|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|Добавляет фильтр в прослушиватель в коллекции `sharedListeners`.|  
|[\<listeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|Задает прослушиватели для коллекции `Listeners` для источника трассировки.|  
|[\<listeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|Задает прослушиватели для коллекции `Listeners` для трассировки.|  
|[\<performanceCounters\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|Размер глобальной памяти, совместно используемой счетчиками производительности.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|Удаляет прослушиватель из коллекции `Listeners` для трассировки.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|Удаляет прослушиватель из коллекции `Listeners` для источника трассировки.|  
|[\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки.|  
|[\<sources\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|Элемент, содержащий источники трассировки, инициирующие трассировочные сообщения.|  
|[\<source\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|Источник трассировки, инициирующий сообщения трассировки.|  
|[\<switches\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|Содержит переключатели трассировки и уровень, на котором установлены эти переключатели.|  
|[\<system.diagnostics\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/system-diagnostics-element.md)|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором устанавливается переключатель трассировки.|  
|[\<trace\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|Содержит прослушиватели, собирающие, хранящие и маршрутизирующие сообщения трассировки.|  
  
## См. также  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.Debug>   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)