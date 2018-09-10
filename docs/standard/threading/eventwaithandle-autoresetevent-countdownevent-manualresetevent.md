---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f61e614696e731a85a030e34aa4356137d9000d
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44260153"
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a>EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
Дескрипторы ожидания событий позволяют потокам синхронизировать действия, обмениваясь сигналами и ожидая сигналов друг друга. Такие события синхронизации основаны на дескрипторах ожидания Win32 и делятся на два типа: те, которые автоматически сбрасываются при получении сигнала, и те, которые нужно сбрасывать вручную.  
  
 Дескрипторы ожидания событий часто бывают полезны в тех же сценариях синхронизации, где используется класс <xref:System.Threading.Monitor>. Дескрипторы ожидания событий часто проще использовать, чем методы <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> и <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType>, и они дают больше контроля над передачей сигналов. Именованные дескрипторы ожидания событий можно также использовать для синхронизации действий между различными доменами приложений и процессами, в то время как мониторы являются локальными для домена приложения.  
  
## <a name="in-this-section"></a>В этом разделе  
 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md)  
 Класс <xref:System.Threading.EventWaitHandle> может представлять локальные или именованные системные события с автоматическим или ручным сбросом.  
  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 Класс <xref:System.Threading.AutoResetEvent> является производным от <xref:System.Threading.EventWaitHandle> и представляет локальное событие с автоматическим сбросом.  
  
 [ManualResetEvent and ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 Класс <xref:System.Threading.ManualResetEvent> является производным от <xref:System.Threading.EventWaitHandle> и представляет локальное событие со сбросом вручную. Класс <xref:System.Threading.ManualResetEventSlim> является упрощенной и более быстрой версией, которую можно использовать для событий в одном процессе.  
  
 [CountdownEvent](../../../docs/standard/threading/countdownevent.md)  
 Класс <xref:System.Threading.CountdownEvent> предоставляет упрощенный способ реализации шаблонов параллельного выполнения ветвлений и соединений в коде, где используются дескрипторы ожидания.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Дескрипторы ожидания](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 Класс <xref:System.Threading.WaitHandle> является базовым для классов <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore> и <xref:System.Threading.Mutex>. Он содержит статические методы, например <xref:System.Threading.WaitHandle.SignalAndWait%2A> и <xref:System.Threading.WaitHandle.WaitAll%2A>, которые помогают в работе со всеми типами дескрипторов ожидания.  
  
## <a name="see-also"></a>См. также

- <xref:System.Threading.EventWaitHandle>  
- <xref:System.Threading.WaitHandle>  
- <xref:System.Threading.AutoResetEvent>  
- <xref:System.Threading.ManualResetEvent>  
- [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)  
- [Основы управляемых потоков](../../../docs/standard/threading/managed-threading-basics.md)
