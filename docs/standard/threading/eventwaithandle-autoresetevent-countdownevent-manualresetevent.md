---
title: "EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent | Microsoft Docs"
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
  - "wait handles"
  - "threading [.NET Framework], EventWaitHandle class"
  - "event wait handles [.NET Framework]"
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
Дескрипторы ожидания событий позволяют потокам синхронизировать действия, обмениваясь сигналами и ожидая сигналов друг от друга.  Такие события синхронизации основаны на дескрипторах ожидания Win32. Их можно разделить на два типа: события, сбрасываемые автоматически в момент передачи сигнала и сбрасываемые вручную.  
  
 Дескрипторы ожидания событий полезны во многих из сценариев синхронизации, где используется класс <xref:System.Threading.Monitor>.  Использовать дескрипторы ожидания событий часто проще, чем методы <xref:System.Threading.Monitor.Wait%2A?displayProperty=fullName> и <xref:System.Threading.Monitor.Pulse%2A?displayProperty=fullName>, и они дают более широкие возможности управления сигналами.  Именованные дескрипторы ожидания событий также можно использовать для синхронизации действий между различными доменами приложений и процессами, в то время как мониторы являются локальными для домена приложения.  
  
## В этом подразделе  
 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md)  
 Класс <xref:System.Threading.EventWaitHandle> может представлять локальные или именованные системные события с автоматическим или ручным сбросом.  
  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 Класс <xref:System.Threading.AutoResetEvent> является производным от класса <xref:System.Threading.EventWaitHandle> и представляет локальное событие с автоматическим сбросом.  
  
 [ManualResetEvent and ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 Класс <xref:System.Threading.ManualResetEvent> является производным от класса <xref:System.Threading.EventWaitHandle> и представляет локальное событие, которое необходимо сбрасывать вручную.  Класс <xref:System.Threading.ManualResetEventSlim> является упрощенной и более быстрой версией, которую можно использовать для событий в одном и том же процессе.  
  
 [CountdownEvent](../../../docs/standard/threading/countdownevent.md)  
 Класс <xref:System.Threading.CountdownEvent> предоставляет упрощенный способ реализации шаблонов параллельного выполнения разветвлений и соединений в коде, использующем дескрипторы ожидания.  
  
## Связанные подразделы  
 [Wait Handles](../Topic/Wait%20Handles.md)  
 Класс <xref:System.Threading.WaitHandle> является базовым для классов <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore> и <xref:System.Threading.Mutex>.  Он содержит статические методы, такие как <xref:System.Threading.WaitHandle.SignalAndWait%2A> и <xref:System.Threading.WaitHandle.WaitAll%2A>, которые полезны в работе с дескрипторами ожидания всех типов.  
  
## См. также  
 <xref:System.Threading.EventWaitHandle>   
 <xref:System.Threading.WaitHandle>   
 <xref:System.Threading.AutoResetEvent>   
 <xref:System.Threading.ManualResetEvent>   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)   
 [Managed Threading Basics](../../../docs/standard/threading/managed-threading-basics.md)