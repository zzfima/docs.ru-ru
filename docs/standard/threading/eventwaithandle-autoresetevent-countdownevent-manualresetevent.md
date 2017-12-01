---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c0bcb27ed9c8981665a50c129dfbd824c9612f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a>EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
Дескрипторы ожидания событий позволяют потокам синхронизировать действия, обмениваясь сигналами и ожидая сигналов друг друга. Такие события синхронизации основаны на дескрипторах ожидания Win32 и делятся на два типа: те, которые автоматически сбрасываются при получении сигнала, и те, которые нужно сбрасывать вручную.  
  
 Дескрипторы ожидания событий полезны во множестве сценариев как синхронизации <xref:System.Threading.Monitor> класса. Дескрипторы ожидания событий часто проще, чем <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> и <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> методов и они обеспечивают больший контроль над сигнализации. Именованные дескрипторы ожидания событий можно также использовать для синхронизации действий между различными доменами приложений и процессами, в то время как мониторы являются локальными для домена приложения.  
  
## <a name="in-this-section"></a>Содержание  
 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md)  
 <xref:System.Threading.EventWaitHandle> Класс может представлять любой автоматический или ручной сброс события и локальные или именованные системные события.  
  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 <xref:System.Threading.AutoResetEvent> Класс является производным от <xref:System.Threading.EventWaitHandle> и представляет локальное событие, которое сбрасывается автоматически.  
  
 [ManualResetEvent and ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 <xref:System.Threading.ManualResetEvent> Класс является производным от <xref:System.Threading.EventWaitHandle> и представляет локальное событие, которое необходимо сбросить вручную. <xref:System.Threading.ManualResetEventSlim> Класс — это упрощенный, более высокую версию, которая может использоваться для событий в одном процессе.  
  
 [CountdownEvent](../../../docs/standard/threading/countdownevent.md)  
 <xref:System.Threading.CountdownEvent> Класс предоставляет упрощенный способ реализации шаблонов параллельного выполнения ветвления и соединения в коде, использующем дескрипторы ожидания.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Дескрипторы ожидания](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 <xref:System.Threading.WaitHandle> Класс является базовым классом для <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, и <xref:System.Threading.Mutex> классы. Он содержит статические методы, такие как <xref:System.Threading.WaitHandle.SignalAndWait%2A> и <xref:System.Threading.WaitHandle.WaitAll%2A> , могут быть полезны при работе со всеми типами дескрипторов ожидания.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Основы управляемых потоков](../../../docs/standard/threading/managed-threading-basics.md)
