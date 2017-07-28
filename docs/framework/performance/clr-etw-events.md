---
title: "CLR ETW Events | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CLR ETW events"
  - "ETW, common language runtime"
  - "ETW, CLR events"
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
caps.latest.revision: 45
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 45
---
# CLR ETW Events
В подразделах этого раздела представлено описание событий трассировки событий Windows.  У каждого события имеется связанное ключевое слово и уровень, описание которых представлено в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).  В CLR существуют два поставщика для событий.  
  
-   Поставщик среды выполнения вызывает события в зависимости от включенных ключевых слов \(категорий событий\).  GUID поставщика времени выполнения среды CLR — e13c0d23\-ccbc\-4e12\-931b\-d9cc2eee27e4.  
  
-   Поставщик очистки со специализированными вариантами использования.  GUID поставщика очистки среды CLR — a669021c\-c450\-4609\-a035\-5af59af4df18.  
  
 Дополнительные сведения о поставщиках см. в разделе [CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md).  
  
## В этом подразделе  
 [Runtime Information Events](../../../docs/framework/performance/runtime-information-etw-events.md)  
 Сбор сведений о среде выполнения, включая SKU, номер версии, способ активации среды выполнения, параметры командной строки, с которыми она запущена, GUID \(при наличии\) и другие соответствующие данные.  
  
 [Exception Thrown\_V1 Event](../../../docs/framework/performance/exception-thrown-v1-etw-event.md)  
 Сбор сведений о возникающих исключениях.  
  
 [Contention Events](../../../docs/framework/performance/contention-etw-events.md)  
 Сбор сведений о конфликте блокировок monitor или блокировок машинного кода, используемых средой выполнения.  
  
 [Thread Pool Events](../../../docs/framework/performance/thread-pool-etw-events.md)  
 Сбор сведений о пулах рабочих потоков и пулах потоков ввода\-вывода.  
  
 [Loader Events](../../../docs/framework/performance/loader-etw-events.md)  
 Сбор сведений о загрузке и выгрузке доменов приложений, сборок и модулей.  
  
 [Method Events](../../../docs/framework/performance/method-etw-events.md)  
 Сбор сведений о методах среды CLR для разрешения символов.  
  
 [Garbage Collection Events](../../../docs/framework/performance/garbage-collection-etw-events.md)  
 Сбор сведений, относящихся к сборке мусора, для упрощения диагностики и отладки.  
  
 [JIT Tracing Events](../../../docs/framework/performance/jit-tracing-etw-events.md)  
 Сбор сведений о встраивании кода JIT и вызовах метода с префиксом tail.  
  
 [Interop Events](../../../docs/framework/performance/interop-etw-events.md)  
 Сбор сведений о создании ловушек и кэшировании MSIL.  
  
 [ARM Events](../../../docs/framework/performance/application-domain-resource-monitoring-arm-etw-events.md)  
 Сбор подробных диагностических сведений о состоянии домена приложения.  
  
 [Security Events](../../../docs/framework/performance/security-etw-events.md)  
 Сбор сведений о строгом имени и проверке Authenticode.  
  
 [Stack Event](../../../docs/framework/performance/stack-etw-event.md)  
 Сбор сведений, используемых с другими событиями для создания трассировок стека после вызова события.  
  
## См. также  
 [Улучшение производительности в ходе отладки и трассировки событий Windows](http://go.microsoft.com/fwlink/?LinkId=179696)   
 [Блог производительности Windows](http://go.microsoft.com/fwlink/?LinkId=179509)   
 [Controlling .NET Framework Logging](../../../docs/framework/performance/controlling-logging.md)   
 [CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md)   
 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)   
 [ETW Events in the Common Language Runtime](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)