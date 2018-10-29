---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.date: 09/14/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be9c858d7c76fdcc1b3e02485eb0b459f4e7555c
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583156"
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a><span data-ttu-id="78643-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="78643-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>

<span data-ttu-id="78643-103">Дескрипторы ожидания событий позволяют потокам синхронизировать действия, обмениваясь сигналами и ожидая сигналов друг друга.</span><span class="sxs-lookup"><span data-stu-id="78643-103">Event wait handles allow threads to synchronize activities by signaling each other and by waiting on each other's signals.</span></span> <span data-ttu-id="78643-104">Такие события синхронизации основаны на дескрипторах ожидания ОС и делятся на два типа — те, которые автоматически сбрасываются при получении сигнала, и те, которые нужно сбрасывать вручную.</span><span class="sxs-lookup"><span data-stu-id="78643-104">These synchronization events are based on operating system wait handles and can be divided into two types: those that reset automatically when signaled and those that are reset manually.</span></span>  
  
<span data-ttu-id="78643-105">Дескрипторы ожидания событий часто бывают полезны в тех же сценариях синхронизации, где используется класс <xref:System.Threading.Monitor>.</span><span class="sxs-lookup"><span data-stu-id="78643-105">Event wait handles are useful in many of the same synchronization scenarios as the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="78643-106">Дескрипторы ожидания событий часто проще использовать, чем методы <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> и <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType>, и они дают больше контроля над передачей сигналов.</span><span class="sxs-lookup"><span data-stu-id="78643-106">Event wait handles are often easier to use than the <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> and <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> methods, and they offer more control over signaling.</span></span> <span data-ttu-id="78643-107">Именованные дескрипторы ожидания событий можно также использовать для синхронизации действий между различными доменами приложений и процессами, в то время как мониторы являются локальными для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="78643-107">Named event wait handles can also be used to synchronize activities across application domains and processes, whereas monitors are local to an application domain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="78643-108">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="78643-108">In this section</span></span>

 [<span data-ttu-id="78643-109">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="78643-109">EventWaitHandle</span></span>](eventwaithandle.md)  
 <span data-ttu-id="78643-110">Класс <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> может представлять локальные или именованные системные события с автоматическим или ручным сбросом.</span><span class="sxs-lookup"><span data-stu-id="78643-110">The <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> class can represent either automatic or manual reset events and either local events or named system events.</span></span>  
  
 [<span data-ttu-id="78643-111">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="78643-111">AutoResetEvent</span></span>](autoresetevent.md)  
 <span data-ttu-id="78643-112">Класс <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType> является производным от <xref:System.Threading.EventWaitHandle> и представляет локальное событие с автоматическим сбросом.</span><span class="sxs-lookup"><span data-stu-id="78643-112">The <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that resets automatically.</span></span>  
  
 [<span data-ttu-id="78643-113">ManualResetEvent and ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="78643-113">ManualResetEvent and ManualResetEventSlim</span></span>](manualresetevent-and-manualreseteventslim.md)  
 <span data-ttu-id="78643-114">Класс <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> является производным от <xref:System.Threading.EventWaitHandle> и представляет локальное событие со сбросом вручную.</span><span class="sxs-lookup"><span data-stu-id="78643-114">The <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that must be reset manually.</span></span> <span data-ttu-id="78643-115">Класс <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> является упрощенной и более быстрой версией, которую можно использовать для событий в одном процессе.</span><span class="sxs-lookup"><span data-stu-id="78643-115">The <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> class is a lightweight, faster version that can be used for events within the same process.</span></span>  
  
 [<span data-ttu-id="78643-116">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="78643-116">CountdownEvent</span></span>](countdownevent.md)  
 <span data-ttu-id="78643-117">Класс <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> предоставляет упрощенный способ реализации шаблонов параллельного выполнения ветвлений и соединений в коде, где используются дескрипторы ожидания.</span><span class="sxs-lookup"><span data-stu-id="78643-117">The <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> class provides a simplified way to implement fork/join parallelism patterns in code that uses wait handles.</span></span>  

## <a name="see-also"></a><span data-ttu-id="78643-118">См. также</span><span class="sxs-lookup"><span data-stu-id="78643-118">See also</span></span>

- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.Threading.Barrier?displayProperty=nameWithType>
- [<span data-ttu-id="78643-119">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="78643-119">Threading objects and features</span></span>](threading-objects-and-features.md)
- [<span data-ttu-id="78643-120">Основы управляемых потоков</span><span class="sxs-lookup"><span data-stu-id="78643-120">Managed threading basics</span></span>](managed-threading-basics.md)
