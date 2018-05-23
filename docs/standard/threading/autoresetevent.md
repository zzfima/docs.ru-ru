---
title: AutoResetEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4ab06993eed4b39746875a6ef3ebfad5edbd2e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="autoresetevent"></a><span data-ttu-id="89b0d-102">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="89b0d-102">AutoResetEvent</span></span>
<span data-ttu-id="89b0d-103">Класс <xref:System.Threading.AutoResetEvent> предоставляет событие локального дескриптора ожидания, которое автоматически сбрасывается после создания, освободив один поток ожидания.</span><span class="sxs-lookup"><span data-stu-id="89b0d-103">The <xref:System.Threading.AutoResetEvent> class represents a local wait handle event that resets automatically when signaled, after releasing a single waiting thread.</span></span> <span data-ttu-id="89b0d-104">Этот класс представляет отдельный сценарий применения базового класса <xref:System.Threading.EventWaitHandle>.</span><span class="sxs-lookup"><span data-stu-id="89b0d-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle>.</span></span> <span data-ttu-id="89b0d-105">Основную документацию по использованию и функциональным возможностям событий автоматического сброса см. в разделе [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="89b0d-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of automatic reset events.</span></span>  
  
 <span data-ttu-id="89b0d-106">Освободив один поток в состоянии ожидания, система автоматически сбрасывает сигнальное состояние объекта <xref:System.Threading.AutoResetEvent>.</span><span class="sxs-lookup"><span data-stu-id="89b0d-106">An <xref:System.Threading.AutoResetEvent> object is automatically reset to non-signaled by the system after a single waiting thread has been released.</span></span> <span data-ttu-id="89b0d-107">Если ожидающих потоков нет, состояние объекта события остается сигнальным.</span><span class="sxs-lookup"><span data-stu-id="89b0d-107">If no threads are waiting, the event object's state remains signaled.</span></span> <span data-ttu-id="89b0d-108"><xref:System.Threading.AutoResetEvent> соответствует вызову Win32 `CreateEvent`, где указано значение `false` для аргумента `bManualReset`.</span><span class="sxs-lookup"><span data-stu-id="89b0d-108"><xref:System.Threading.AutoResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `false` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="89b0d-109">Пример использования <xref:System.Threading.AutoResetEvent> см. в описании [класса Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).</span><span class="sxs-lookup"><span data-stu-id="89b0d-109">For an example that uses <xref:System.Threading.AutoResetEvent>, see [Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89b0d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="89b0d-110">See Also</span></span>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="89b0d-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="89b0d-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [<span data-ttu-id="89b0d-112">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="89b0d-112">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="89b0d-113">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="89b0d-113">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="89b0d-114">Дескрипторы ожидания</span><span class="sxs-lookup"><span data-stu-id="89b0d-114">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
