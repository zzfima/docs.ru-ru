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
ms.openlocfilehash: 543853f581436a5fb7e5c897012b99bef20dc289
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582953"
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a><span data-ttu-id="c3a30-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="c3a30-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>
<span data-ttu-id="c3a30-103">Дескрипторы ожидания событий позволяют потокам синхронизировать действия, обмениваясь сигналами и ожидая сигналов друг друга.</span><span class="sxs-lookup"><span data-stu-id="c3a30-103">Event wait handles allow threads to synchronize activities by signaling each other and by waiting on each other's signals.</span></span> <span data-ttu-id="c3a30-104">Такие события синхронизации основаны на дескрипторах ожидания Win32 и делятся на два типа: те, которые автоматически сбрасываются при получении сигнала, и те, которые нужно сбрасывать вручную.</span><span class="sxs-lookup"><span data-stu-id="c3a30-104">These synchronization events are based on Win32 wait handles and can be divided into two types: those that reset automatically when signaled and those that are reset manually.</span></span>  
  
 <span data-ttu-id="c3a30-105">Дескрипторы ожидания событий часто бывают полезны в тех же сценариях синхронизации, где используется класс <xref:System.Threading.Monitor>.</span><span class="sxs-lookup"><span data-stu-id="c3a30-105">Event wait handles are useful in many of the same synchronization scenarios as the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="c3a30-106">Дескрипторы ожидания событий часто проще использовать, чем методы <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> и <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType>, и они дают больше контроля над передачей сигналов.</span><span class="sxs-lookup"><span data-stu-id="c3a30-106">Event wait handles are often easier to use than the <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> and <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> methods, and they offer more control over signaling.</span></span> <span data-ttu-id="c3a30-107">Именованные дескрипторы ожидания событий можно также использовать для синхронизации действий между различными доменами приложений и процессами, в то время как мониторы являются локальными для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c3a30-107">Named event wait handles can also be used to synchronize activities across application domains and processes, whereas monitors are local to an application domain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c3a30-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c3a30-108">In This Section</span></span>  
 [<span data-ttu-id="c3a30-109">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="c3a30-109">EventWaitHandle</span></span>](../../../docs/standard/threading/eventwaithandle.md)  
 <span data-ttu-id="c3a30-110">Класс <xref:System.Threading.EventWaitHandle> может представлять локальные или именованные системные события с автоматическим или ручным сбросом.</span><span class="sxs-lookup"><span data-stu-id="c3a30-110">The <xref:System.Threading.EventWaitHandle> class can represent either automatic or manual reset events and either local events or named system events.</span></span>  
  
 [<span data-ttu-id="c3a30-111">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="c3a30-111">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
 <span data-ttu-id="c3a30-112">Класс <xref:System.Threading.AutoResetEvent> является производным от <xref:System.Threading.EventWaitHandle> и представляет локальное событие с автоматическим сбросом.</span><span class="sxs-lookup"><span data-stu-id="c3a30-112">The <xref:System.Threading.AutoResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that resets automatically.</span></span>  
  
 [<span data-ttu-id="c3a30-113">ManualResetEvent and ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="c3a30-113">ManualResetEvent and ManualResetEventSlim</span></span>](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 <span data-ttu-id="c3a30-114">Класс <xref:System.Threading.ManualResetEvent> является производным от <xref:System.Threading.EventWaitHandle> и представляет локальное событие со сбросом вручную.</span><span class="sxs-lookup"><span data-stu-id="c3a30-114">The <xref:System.Threading.ManualResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that must be reset manually.</span></span> <span data-ttu-id="c3a30-115">Класс <xref:System.Threading.ManualResetEventSlim> является упрощенной и более быстрой версией, которую можно использовать для событий в одном процессе.</span><span class="sxs-lookup"><span data-stu-id="c3a30-115">The <xref:System.Threading.ManualResetEventSlim> class is a lightweight, faster version that can be used for events within the same process.</span></span>  
  
 [<span data-ttu-id="c3a30-116">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="c3a30-116">CountdownEvent</span></span>](../../../docs/standard/threading/countdownevent.md)  
 <span data-ttu-id="c3a30-117">Класс <xref:System.Threading.CountdownEvent> предоставляет упрощенный способ реализации шаблонов параллельного выполнения ветвлений и соединений в коде, где используются дескрипторы ожидания.</span><span class="sxs-lookup"><span data-stu-id="c3a30-117">The <xref:System.Threading.CountdownEvent> class provides a simplified way to implement fork/join parallelism patterns in code that uses wait handles.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c3a30-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c3a30-118">Related Sections</span></span>  
 [<span data-ttu-id="c3a30-119">Дескрипторы ожидания</span><span class="sxs-lookup"><span data-stu-id="c3a30-119">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 <span data-ttu-id="c3a30-120">Класс <xref:System.Threading.WaitHandle> является базовым для классов <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore> и <xref:System.Threading.Mutex>.</span><span class="sxs-lookup"><span data-stu-id="c3a30-120">The <xref:System.Threading.WaitHandle> class is the base class for the <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, and <xref:System.Threading.Mutex> classes.</span></span> <span data-ttu-id="c3a30-121">Он содержит статические методы, например <xref:System.Threading.WaitHandle.SignalAndWait%2A> и <xref:System.Threading.WaitHandle.WaitAll%2A>, которые помогают в работе со всеми типами дескрипторов ожидания.</span><span class="sxs-lookup"><span data-stu-id="c3a30-121">It contains static methods such as <xref:System.Threading.WaitHandle.SignalAndWait%2A> and <xref:System.Threading.WaitHandle.WaitAll%2A> that are useful when working with all types of wait handles.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3a30-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c3a30-122">See Also</span></span>  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [<span data-ttu-id="c3a30-123">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="c3a30-123">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="c3a30-124">Основы управляемых потоков</span><span class="sxs-lookup"><span data-stu-id="c3a30-124">Managed Threading Basics</span></span>](../../../docs/standard/threading/managed-threading-basics.md)
