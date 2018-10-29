---
title: Классы ManualResetEvent и ManualResetEventSlim
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c85d0c5c291743c6daac549e15d479fcf332235c
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452827"
---
# <a name="manualresetevent-and-manualreseteventslim"></a><span data-ttu-id="906e2-102">Классы ManualResetEvent и ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="906e2-102">ManualResetEvent and ManualResetEventSlim</span></span>
<span data-ttu-id="906e2-103">Класс <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> представляет событие локального дескриптора ожидания, которое необходимо сбросить вручную после создания сигнала.</span><span class="sxs-lookup"><span data-stu-id="906e2-103">The <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class represents a local wait handle event that must be reset manually after it is signaled.</span></span> <span data-ttu-id="906e2-104">Этот класс представляет отдельный сценарий применения базового класса <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="906e2-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span></span> <span data-ttu-id="906e2-105">Основную документацию по использованию и функциональным возможностям событий ручного сброса см. в разделе [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="906e2-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of manual reset events.</span></span>  
  
 <span data-ttu-id="906e2-106">Объект <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> сохраняет активный статус, пока не будет вызван его метод <xref:System.Threading.ManualResetEvent>.</span><span class="sxs-lookup"><span data-stu-id="906e2-106">A <xref:System.Threading.ManualResetEvent> object remains signaled until its <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="906e2-107">Пока сообщается состояние объекта, любое количество ожидающих потоков или потоков, ожидающих события после сигнала, может освободиться.</span><span class="sxs-lookup"><span data-stu-id="906e2-107">Any number of waiting threads, or threads that wait on the event after it has been signaled, can be released while the object's state is signaled.</span></span>
  
 <span data-ttu-id="906e2-108">В [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] вы можете использовать класс <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, чтобы повысить производительность, если периоды ожидания будут очень короткими, а событие не выходит за рамки процесса.</span><span class="sxs-lookup"><span data-stu-id="906e2-108">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use the <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> class for better performance when wait times are expected to be very short, and when the event does not cross a process boundary.</span></span> <span data-ttu-id="906e2-109"><xref:System.Threading.ManualResetEventSlim> использует цикличную работу в режиме занятости в течение короткого промежутка времени, пока ожидает перехода события в сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="906e2-109"><xref:System.Threading.ManualResetEventSlim> uses busy spinning for a short time while it waits for the event to become signaled.</span></span> <span data-ttu-id="906e2-110">Если периоды ожидания короткие, цикличность может стоить гораздо дешевле, чем ожидание с использованием соответствующих дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="906e2-110">When wait times are short, spinning can be much less expensive than waiting by using wait handles.</span></span> <span data-ttu-id="906e2-111">Однако, если состояние события не изменяется в течение заданного периода времени, <xref:System.Threading.ManualResetEventSlim> применяет обычный дескриптор ожидания событий.</span><span class="sxs-lookup"><span data-stu-id="906e2-111">However, if the event does not become signaled within a certain period of time, <xref:System.Threading.ManualResetEventSlim> resorts to a regular event handle wait.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="906e2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="906e2-112">See also</span></span>

- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- [<span data-ttu-id="906e2-113">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="906e2-113">AutoResetEvent</span></span>](autoresetevent.md)  
- [<span data-ttu-id="906e2-114">SpinWait</span><span class="sxs-lookup"><span data-stu-id="906e2-114">SpinWait</span></span>](spinwait.md)  
- [<span data-ttu-id="906e2-115">Классы Semaphore и SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="906e2-115">Semaphore and SemaphoreSlim</span></span>](semaphore-and-semaphoreslim.md)
- [<span data-ttu-id="906e2-116">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="906e2-116">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
- [<span data-ttu-id="906e2-117">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="906e2-117">Threading objects and features</span></span>](threading-objects-and-features.md)  
- [<span data-ttu-id="906e2-118">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="906e2-118">Threading</span></span>](index.md)  
