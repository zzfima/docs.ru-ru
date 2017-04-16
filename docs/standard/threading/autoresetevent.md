---
title: "AutoResetEvent | Microsoft Docs"
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
  - "threading [.NET Framework], AutoResetEvent class"
  - "AutoResetEvent class"
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# AutoResetEvent
Класс <xref:System.Threading.AutoResetEvent> представляет событие локального дескриптора ожидания, которое сбрасывается автоматически при получении сигнала после освобождения отдельного ожидающего потока.  Этот класс представляет специальное использование базового класса <xref:System.Threading.EventWaitHandle>.  Использование и функциональные возможности автоматического сброса событий см. в основной документации [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).  
  
 Объект <xref:System.Threading.AutoResetEvent> сбрасывается автоматически в несигнальное состояние после того, как освобождается одиночный ожидающий поток.  Если ни один поток не является ждущим, состояние объекта события остается сигнальным.  Объект <xref:System.Threading.AutoResetEvent> соответствует вызову Win32 `CreateEvent`, указывающему значение `false` в качестве аргумента параметра `bManualReset`.  
  
 Пример, использующий <xref:System.Threading.AutoResetEvent> см. в разделе [Monitor](../Topic/Monitors.md).  
  
## См. также  
 <xref:System.Threading.ManualResetEvent>   
 <xref:System.Threading.Monitor>   
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)   
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)   
 [Wait Handles](../Topic/Wait%20Handles.md)