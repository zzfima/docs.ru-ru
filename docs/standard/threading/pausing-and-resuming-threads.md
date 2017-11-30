---
title: "Приостановка и возобновление потоков"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resuming threads
- threading [.NET Framework], pausing
- pausing threads
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b146987d2491f044e1f5794eba17d02d8f5e478c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="pausing-and-resuming-threads"></a><span data-ttu-id="47795-102">Приостановка и возобновление потоков</span><span class="sxs-lookup"><span data-stu-id="47795-102">Pausing and Resuming Threads</span></span>
<span data-ttu-id="47795-103">Наиболее распространенными способами синхронизации действий потоков являются блокировка и освобождение потоков или блокировка объектов или областей кода.</span><span class="sxs-lookup"><span data-stu-id="47795-103">The most common ways to synchronize the activities of threads are to block and release threads, or to lock objects or regions of code.</span></span> <span data-ttu-id="47795-104">Подробнее об этих механизмах фиксации и блокировки см. в разделе [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="47795-104">For more information on these locking and blocking mechanisms, see [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="47795-105">Также можно организовать перевод потоков в спящий режим.</span><span class="sxs-lookup"><span data-stu-id="47795-105">You can also have threads put themselves to sleep.</span></span> <span data-ttu-id="47795-106">Если потоки заблокированы или находятся в спящем режиме, можно использовать <xref:System.Threading.ThreadInterruptedException> для вывода потоков из состояния ожидания.</span><span class="sxs-lookup"><span data-stu-id="47795-106">When threads are blocked or sleeping, you can use a <xref:System.Threading.ThreadInterruptedException> to break them out of their wait states.</span></span>  
  
## <a name="the-threadsleep-method"></a><span data-ttu-id="47795-107">Метод Thread.Sleep</span><span class="sxs-lookup"><span data-stu-id="47795-107">The Thread.Sleep Method</span></span>  
 <span data-ttu-id="47795-108">Вызов <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> метод приводит к немедленной блокировке количество миллисекунд или интервал времени, который передается методу текущего потока и выдает оставшуюся часть своего интервала времени в другой поток.</span><span class="sxs-lookup"><span data-stu-id="47795-108">Calling the <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> method causes the current thread to immediately block for the number of milliseconds or the time interval you pass to the method, and yields the remainder of its time slice to another thread.</span></span> <span data-ttu-id="47795-109">По истечении этого интервала времени спящий поток возобновляет выполнение.</span><span class="sxs-lookup"><span data-stu-id="47795-109">Once that interval elapses, the sleeping thread resumes execution.</span></span>  
  
 <span data-ttu-id="47795-110">Поток не может вызвать метод <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> для другого потока.</span><span class="sxs-lookup"><span data-stu-id="47795-110">One thread cannot call <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> on another thread.</span></span>  <span data-ttu-id="47795-111"><xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>представляет статический метод, который всегда вызывает текущий поток в спящий режим.</span><span class="sxs-lookup"><span data-stu-id="47795-111"><xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is a static method that always causes the current thread to sleep.</span></span>  
  
 <span data-ttu-id="47795-112">Вызов <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> со значением <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType> вынуждает поток в спящий режим, пока будет прерван другим потоком, который вызывает <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> методом в потоке находится в спящем режиме или до его завершения путем вызова его <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="47795-112">Calling <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> with a value of <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType> causes a thread to sleep until it is interrupted by another thread that calls the  <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> method on the sleeping thread, or until it is terminated by a call to its <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method.</span></span>  <span data-ttu-id="47795-113">В следующем примере показаны оба метода прерывания спящего потока.</span><span class="sxs-lookup"><span data-stu-id="47795-113">The following example illustrates both methods of interrupting a sleeping thread.</span></span>  
  
 [!code-csharp[Conceptual.Threading.Resuming#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Threading.Resuming/cs/Sleep1.cs#1)]
 [!code-vb[Conceptual.Threading.Resuming#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Threading.Resuming/vb/Sleep1.vb#1)]  
  
## <a name="interrupting-threads"></a><span data-ttu-id="47795-114">Прерывание потоков</span><span class="sxs-lookup"><span data-stu-id="47795-114">Interrupting Threads</span></span>  
 <span data-ttu-id="47795-115">Можно прервать ожидающий поток путем вызова <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> метод для заблокированного потока для вызова <xref:System.Threading.ThreadInterruptedException>, которое выводит поток из вызова блокировки.</span><span class="sxs-lookup"><span data-stu-id="47795-115">You can interrupt a waiting thread by calling the <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> method on the blocked thread to throw a <xref:System.Threading.ThreadInterruptedException>, which breaks the thread out of the blocking call.</span></span> <span data-ttu-id="47795-116">Поток должен перехватить исключение <xref:System.Threading.ThreadInterruptedException> и выполнить соответствующие действия для продолжения работы.</span><span class="sxs-lookup"><span data-stu-id="47795-116">The thread should catch the <xref:System.Threading.ThreadInterruptedException> and do whatever is appropriate to continue working.</span></span> <span data-ttu-id="47795-117">Если поток пропускает исключение, среда выполнения перехватывает его и останавливает поток.</span><span class="sxs-lookup"><span data-stu-id="47795-117">If the thread ignores the exception, the runtime catches the exception and stops the thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47795-118">Если целевой поток не заблокирован при вызове метода <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>, поток не прерывается до блокировки.</span><span class="sxs-lookup"><span data-stu-id="47795-118">If the target thread is not blocked when <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> is called, the thread is not interrupted until it blocks.</span></span> <span data-ttu-id="47795-119">Если поток никогда не блокируется, он может завершиться, не будучи прерванным.</span><span class="sxs-lookup"><span data-stu-id="47795-119">If the thread never blocks, it could complete without ever being interrupted.</span></span>  
  
 <span data-ttu-id="47795-120">Если ожидание является управляемым, методы <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> и <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> незамедлительно выводят поток из спящего режима.</span><span class="sxs-lookup"><span data-stu-id="47795-120">If a wait is a managed wait, then <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> and <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> both wake the thread immediately.</span></span> <span data-ttu-id="47795-121">Если ожидание является неуправляемым (например, вызов Win32 неуправляемого [WaitForSingleObject](https://msdn.microsoft.com/library/windows/desktop/ms687032\(v=vs.85\).aspx) функции), ни <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> , ни <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> может занять управлять потоком до его возврата или входа в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="47795-121">If a wait is an unmanaged wait (for example, a platform invoke call to the Win32 [WaitForSingleObject](https://msdn.microsoft.com/library/windows/desktop/ms687032\(v=vs.85\).aspx) function), neither <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> nor <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> can take control of the thread until it returns to or calls into managed code.</span></span> <span data-ttu-id="47795-122">В управляемом коде это поведение выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="47795-122">In managed code, the behavior is as follows:</span></span>  
  
-   <span data-ttu-id="47795-123"><xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> выводит поток из состояния ожидания, в котором он может находиться, и приводит к созданию исключения <xref:System.Threading.ThreadInterruptedException> в целевом потоке.</span><span class="sxs-lookup"><span data-stu-id="47795-123"><xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> wakes a thread out of any wait it might be in and causes a <xref:System.Threading.ThreadInterruptedException> to be thrown in the destination thread.</span></span>  
  
-   <span data-ttu-id="47795-124"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>выводит поток из состояния ожидания, он может находиться в и вызывает <xref:System.Threading.ThreadAbortException> исключение в потоке.</span><span class="sxs-lookup"><span data-stu-id="47795-124"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> wakes a thread out of any wait it might be in and causes a <xref:System.Threading.ThreadAbortException> to be thrown on the thread.</span></span> <span data-ttu-id="47795-125">Подробнее см. в разделе [Уничтожение потоков](../../../docs/standard/threading/destroying-threads.md).</span><span class="sxs-lookup"><span data-stu-id="47795-125">For details, see [Destroying Threads](../../../docs/standard/threading/destroying-threads.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47795-126">См. также</span><span class="sxs-lookup"><span data-stu-id="47795-126">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadInterruptedException>  
 <xref:System.Threading.ThreadAbortException>  
 [<span data-ttu-id="47795-127">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="47795-127">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="47795-128">Использование потоков и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="47795-128">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)  
 [<span data-ttu-id="47795-129">Обзор примитивов синхронизации</span><span class="sxs-lookup"><span data-stu-id="47795-129">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)
