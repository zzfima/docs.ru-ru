---
title: "ManualResetEvent and ManualResetEventSlim | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "threading [.NET Framework], ManualResetEvent class"
  - "ManualResetEvent class, about ManualResetEvent class"
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# ManualResetEvent and ManualResetEventSlim
Класс <xref:System.Threading.ManualResetEvent?displayProperty=fullName> представляет событие локального дескриптора ожидания, которое должно быть сброшено вручную после получения сигнала.  Этот класс представляет специальное использование базового класса <xref:System.Threading.EventWaitHandle?displayProperty=fullName>.  Вопросы, связанные с использованием и функциональными возможностями ручного сброса событий см. в основной документации [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).  
  
 Объект <xref:System.Threading.ManualResetEvent> остается оповещаемым до вызова метода <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=fullName>.  Во время оповещения о состоянии объекта можно освободить любое число ожидающих потоков, или потоков, ожидающих событие после оповещения.  Объект <xref:System.Threading.ManualResetEvent> соответствует вызову Win32 `CreateEvent`, указывающему значение `true` в качестве аргумента параметра `bManualReset`.  
  
 В [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] можно использовать класс <xref:System.Threading.ManualResetEventSlim?displayProperty=fullName> для повышения производительности, если предполагается, что времена ожидания будут очень короткими, а событие не выходит за рамки процесса.  <xref:System.Threading.ManualResetEventSlim> использует цикличную работу в режиме занятости в течение короткого промежутка времени, пока происходит ожидание перехода событий в сигнальное состояние.  Если периоды ожидания короткие, цикличная работа может быть намного дешевле ожидания с использованием дескрипторов ожидания.  Однако, если событие не сигнализирует после определенного промежутка времени, <xref:System.Threading.ManualResetEventSlim> обращается к стандартному дескриптору ожидания события.  
  
## См. также  
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)   
 [Wait Handles](../Topic/Wait%20Handles.md)   
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)   
 [SpinWait](../../../docs/standard/threading/spinwait.md)   
 [Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)