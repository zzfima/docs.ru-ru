---
title: "Классы ManualResetEvent и ManualResetEventSlim"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f663dd17b063f77e2f9ce6bd4bbd0f8859ba4116
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="manualresetevent-and-manualreseteventslim"></a><span data-ttu-id="39a99-102">Классы ManualResetEvent и ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="39a99-102">ManualResetEvent and ManualResetEventSlim</span></span>
<span data-ttu-id="39a99-103"><xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> Класс представляет событие дескриптора ожидания, которое необходимо сбросить вручную после получения сигнала.</span><span class="sxs-lookup"><span data-stu-id="39a99-103">The <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class represents a local wait handle event that must be reset manually after it is signaled.</span></span> <span data-ttu-id="39a99-104">Этот класс представляет специальное использование базового класса, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="39a99-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span></span> <span data-ttu-id="39a99-105">Основную документацию по использованию и функциональным возможностям событий ручного сброса см. в разделе [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="39a99-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of manual reset events.</span></span>  
  
 <span data-ttu-id="39a99-106">Объект <xref:System.Threading.ManualResetEvent> объект получает сигнал до его <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="39a99-106">A <xref:System.Threading.ManualResetEvent> object remains signaled until its <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="39a99-107">Пока сообщается состояние объекта, любое количество ожидающих потоков или потоков, ожидающих события после сигнала, может освободиться.</span><span class="sxs-lookup"><span data-stu-id="39a99-107">Any number of waiting threads, or threads that wait on the event after it has been signaled, can be released while the object's state is signaled.</span></span> <span data-ttu-id="39a99-108"><xref:System.Threading.ManualResetEvent>соответствует Win32 `CreateEvent` вызвать, указав `true` для `bManualReset` аргумент.</span><span class="sxs-lookup"><span data-stu-id="39a99-108"><xref:System.Threading.ManualResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `true` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="39a99-109">В [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], можно использовать <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> класса для повышения производительности, когда предполагается, что времена ожидания будут очень короткими, а события не пересекает границы процессов.</span><span class="sxs-lookup"><span data-stu-id="39a99-109">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use the <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> class for better performance when wait times are expected to be very short, and when the event does not cross a process boundary.</span></span> <span data-ttu-id="39a99-110"><xref:System.Threading.ManualResetEventSlim> использует цикличную работу в режиме занятости в течение короткого промежутка времени, пока ожидает перехода события в сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="39a99-110"><xref:System.Threading.ManualResetEventSlim> uses busy spinning for a short time while it waits for the event to become signaled.</span></span> <span data-ttu-id="39a99-111">Если периоды ожидания короткие, цикличность может стоить гораздо дешевле, чем ожидание с использованием соответствующих дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="39a99-111">When wait times are short, spinning can be much less expensive than waiting by using wait handles.</span></span> <span data-ttu-id="39a99-112">Тем не менее, если событие не сигнализирует за определенный период времени, <xref:System.Threading.ManualResetEventSlim> обращается к стандартному дескриптору ожидания события.</span><span class="sxs-lookup"><span data-stu-id="39a99-112">However, if the event does not become signaled within a certain period of time, <xref:System.Threading.ManualResetEventSlim> resorts to a regular event handle wait.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a99-113">См. также</span><span class="sxs-lookup"><span data-stu-id="39a99-113">See Also</span></span>  
 [<span data-ttu-id="39a99-114">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="39a99-114">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="39a99-115">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="39a99-115">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="39a99-116">Дескрипторы ожидания</span><span class="sxs-lookup"><span data-stu-id="39a99-116">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 [<span data-ttu-id="39a99-117">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="39a99-117">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
 [<span data-ttu-id="39a99-118">SpinWait</span><span class="sxs-lookup"><span data-stu-id="39a99-118">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 [<span data-ttu-id="39a99-119">Классы Semaphore и SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="39a99-119">Semaphore and SemaphoreSlim</span></span>](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
