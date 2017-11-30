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
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a><span data-ttu-id="070f5-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="070f5-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>
<span data-ttu-id="070f5-103">Дескрипторы ожидания событий позволяют потокам синхронизировать действия, обмениваясь сигналами и ожидая сигналов друг друга.</span><span class="sxs-lookup"><span data-stu-id="070f5-103">Event wait handles allow threads to synchronize activities by signaling each other and by waiting on each other's signals.</span></span> <span data-ttu-id="070f5-104">Такие события синхронизации основаны на дескрипторах ожидания Win32 и делятся на два типа: те, которые автоматически сбрасываются при получении сигнала, и те, которые нужно сбрасывать вручную.</span><span class="sxs-lookup"><span data-stu-id="070f5-104">These synchronization events are based on Win32 wait handles and can be divided into two types: those that reset automatically when signaled and those that are reset manually.</span></span>  
  
 <span data-ttu-id="070f5-105">Дескрипторы ожидания событий полезны во множестве сценариев как синхронизации <xref:System.Threading.Monitor> класса.</span><span class="sxs-lookup"><span data-stu-id="070f5-105">Event wait handles are useful in many of the same synchronization scenarios as the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="070f5-106">Дескрипторы ожидания событий часто проще, чем <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> и <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> методов и они обеспечивают больший контроль над сигнализации.</span><span class="sxs-lookup"><span data-stu-id="070f5-106">Event wait handles are often easier to use than the <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> and <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> methods, and they offer more control over signaling.</span></span> <span data-ttu-id="070f5-107">Именованные дескрипторы ожидания событий можно также использовать для синхронизации действий между различными доменами приложений и процессами, в то время как мониторы являются локальными для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="070f5-107">Named event wait handles can also be used to synchronize activities across application domains and processes, whereas monitors are local to an application domain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="070f5-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="070f5-108">In This Section</span></span>  
 [<span data-ttu-id="070f5-109">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="070f5-109">EventWaitHandle</span></span>](../../../docs/standard/threading/eventwaithandle.md)  
 <span data-ttu-id="070f5-110"><xref:System.Threading.EventWaitHandle> Класс может представлять любой автоматический или ручной сброс события и локальные или именованные системные события.</span><span class="sxs-lookup"><span data-stu-id="070f5-110">The <xref:System.Threading.EventWaitHandle> class can represent either automatic or manual reset events and either local events or named system events.</span></span>  
  
 [<span data-ttu-id="070f5-111">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="070f5-111">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
 <span data-ttu-id="070f5-112"><xref:System.Threading.AutoResetEvent> Класс является производным от <xref:System.Threading.EventWaitHandle> и представляет локальное событие, которое сбрасывается автоматически.</span><span class="sxs-lookup"><span data-stu-id="070f5-112">The <xref:System.Threading.AutoResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that resets automatically.</span></span>  
  
 [<span data-ttu-id="070f5-113">ManualResetEvent and ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="070f5-113">ManualResetEvent and ManualResetEventSlim</span></span>](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 <span data-ttu-id="070f5-114"><xref:System.Threading.ManualResetEvent> Класс является производным от <xref:System.Threading.EventWaitHandle> и представляет локальное событие, которое необходимо сбросить вручную.</span><span class="sxs-lookup"><span data-stu-id="070f5-114">The <xref:System.Threading.ManualResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that must be reset manually.</span></span> <span data-ttu-id="070f5-115"><xref:System.Threading.ManualResetEventSlim> Класс — это упрощенный, более высокую версию, которая может использоваться для событий в одном процессе.</span><span class="sxs-lookup"><span data-stu-id="070f5-115">The <xref:System.Threading.ManualResetEventSlim> class is a lightweight, faster version that can be used for events within the same process.</span></span>  
  
 [<span data-ttu-id="070f5-116">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="070f5-116">CountdownEvent</span></span>](../../../docs/standard/threading/countdownevent.md)  
 <span data-ttu-id="070f5-117"><xref:System.Threading.CountdownEvent> Класс предоставляет упрощенный способ реализации шаблонов параллельного выполнения ветвления и соединения в коде, использующем дескрипторы ожидания.</span><span class="sxs-lookup"><span data-stu-id="070f5-117">The <xref:System.Threading.CountdownEvent> class provides a simplified way to implement fork/join parallelism patterns in code that uses wait handles.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="070f5-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="070f5-118">Related Sections</span></span>  
 [<span data-ttu-id="070f5-119">Дескрипторы ожидания</span><span class="sxs-lookup"><span data-stu-id="070f5-119">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 <span data-ttu-id="070f5-120"><xref:System.Threading.WaitHandle> Класс является базовым классом для <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, и <xref:System.Threading.Mutex> классы.</span><span class="sxs-lookup"><span data-stu-id="070f5-120">The <xref:System.Threading.WaitHandle> class is the base class for the <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, and <xref:System.Threading.Mutex> classes.</span></span> <span data-ttu-id="070f5-121">Он содержит статические методы, такие как <xref:System.Threading.WaitHandle.SignalAndWait%2A> и <xref:System.Threading.WaitHandle.WaitAll%2A> , могут быть полезны при работе со всеми типами дескрипторов ожидания.</span><span class="sxs-lookup"><span data-stu-id="070f5-121">It contains static methods such as <xref:System.Threading.WaitHandle.SignalAndWait%2A> and <xref:System.Threading.WaitHandle.WaitAll%2A> that are useful when working with all types of wait handles.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="070f5-122">См. также</span><span class="sxs-lookup"><span data-stu-id="070f5-122">See Also</span></span>  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [<span data-ttu-id="070f5-123">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="070f5-123">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="070f5-124">Основы управляемых потоков</span><span class="sxs-lookup"><span data-stu-id="070f5-124">Managed Threading Basics</span></span>](../../../docs/standard/threading/managed-threading-basics.md)
