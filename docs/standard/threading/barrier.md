---
title: Барьер (.NET Framework)
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, Barrier
ms.assetid: 613a8bc7-6a28-4795-bd6c-1abd9050478f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 385e370f205851630f809b285a93c2609220efeb
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44212403"
---
# <a name="barrier-net-framework"></a><span data-ttu-id="1b03f-102">Барьер (.NET Framework)</span><span class="sxs-lookup"><span data-stu-id="1b03f-102">Barrier (.NET Framework)</span></span>
<span data-ttu-id="1b03f-103">*Барьер* — это определяемый пользователем примитив синхронизации, позволяющий нескольким потокам (которые называются *участниками*) параллельно осуществлять поэтапную работу с алгоритмом.</span><span class="sxs-lookup"><span data-stu-id="1b03f-103">A *barrier* is a user-defined synchronization primitive that enables multiple threads (known as *participants*) to work concurrently on an algorithm in phases.</span></span> <span data-ttu-id="1b03f-104">Каждый участник выполняется до достижения точки барьера в коде.</span><span class="sxs-lookup"><span data-stu-id="1b03f-104">Each participant executes until it reaches the barrier point in the code.</span></span> <span data-ttu-id="1b03f-105">Барьер означает окончание одного этапа работы.</span><span class="sxs-lookup"><span data-stu-id="1b03f-105">The barrier represents the end of one phase of work.</span></span> <span data-ttu-id="1b03f-106">Когда участник достигает барьера, он блокируется до тех пор, пока все участники не достигнут этого барьера.</span><span class="sxs-lookup"><span data-stu-id="1b03f-106">When a participant reaches the barrier, it blocks until all participants have reached the same barrier.</span></span> <span data-ttu-id="1b03f-107">Когда все участники достигли барьера, можно при необходимости можно вызвать действие следующего этапа.</span><span class="sxs-lookup"><span data-stu-id="1b03f-107">After all participants have reached the barrier, you can optionally invoke a post-phase action.</span></span> <span data-ttu-id="1b03f-108">Это действие следующего этапа может использоваться для выполнения действий одним потоком, пока все остальные потоки все еще остаются блокированными.</span><span class="sxs-lookup"><span data-stu-id="1b03f-108">This post-phase action can be used to perform actions by a single thread while all other threads are still blocked.</span></span> <span data-ttu-id="1b03f-109">После выполнения действия все участники разблокируются.</span><span class="sxs-lookup"><span data-stu-id="1b03f-109">After the action has been executed, the participants are all unblocked.</span></span>  
  
 <span data-ttu-id="1b03f-110">Во фрагменте кода ниже показан базовый шаблон барьера.</span><span class="sxs-lookup"><span data-stu-id="1b03f-110">The following code snippet shows a basic barrier pattern.</span></span>  
  
 [!code-csharp[CDS_Barrier#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#02)]
 [!code-vb[CDS_Barrier#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#02)]  
  
 <span data-ttu-id="1b03f-111">Дополнительные сведения см. в руководстве по [синхронизации параллельных операций с барьером](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).</span><span class="sxs-lookup"><span data-stu-id="1b03f-111">For a complete example, see [How to: Synchronize Concurrent Operations with a Barrier](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).</span></span>  
  
## <a name="adding-and-removing-participants"></a><span data-ttu-id="1b03f-112">Добавление и удаление участников</span><span class="sxs-lookup"><span data-stu-id="1b03f-112">Adding and Removing Participants</span></span>  
 <span data-ttu-id="1b03f-113">При создании <xref:System.Threading.Barrier> укажите число участников.</span><span class="sxs-lookup"><span data-stu-id="1b03f-113">When you create a <xref:System.Threading.Barrier>, specify the number of participants.</span></span> <span data-ttu-id="1b03f-114">Вы можете также динамически добавлять или удалять участников в любое время.</span><span class="sxs-lookup"><span data-stu-id="1b03f-114">You can also add or remove participants dynamically at any time.</span></span> <span data-ttu-id="1b03f-115">Например, если один участник решил свою часть задачи, можно сохранить результат, остановить выполнение этого потока и вызвать <xref:System.Threading.Barrier.RemoveParticipant%2A>, чтобы уменьшить число участников барьера.</span><span class="sxs-lookup"><span data-stu-id="1b03f-115">For example, if one participant solves its part of the problem, you can store the result, stop execution on that thread, and call <xref:System.Threading.Barrier.RemoveParticipant%2A> to decrement the number of participants in the barrier.</span></span> <span data-ttu-id="1b03f-116">При добавлении участника путем вызова <xref:System.Threading.Barrier.AddParticipant%2A> возвращаемое значение определяет номер текущего этапа, что может быть полезно для инициализации действий нового участника.</span><span class="sxs-lookup"><span data-stu-id="1b03f-116">When you add a participant by calling <xref:System.Threading.Barrier.AddParticipant%2A>, the return value specifies the current phase number, which may be useful in order to initialize the work of the new participant.</span></span>  
  
## <a name="broken-barriers"></a><span data-ttu-id="1b03f-117">Неисправные барьеры</span><span class="sxs-lookup"><span data-stu-id="1b03f-117">Broken Barriers</span></span>  
 <span data-ttu-id="1b03f-118">Если один из участников не достигает барьера, это может привести к возникновению взаимоблокировок.</span><span class="sxs-lookup"><span data-stu-id="1b03f-118">Deadlocks can occur if one participant fails to reach the barrier.</span></span> <span data-ttu-id="1b03f-119">Во избежание взаимных блокировок используйте перегрузки метода <xref:System.Threading.Barrier.SignalAndWait%2A>, чтобы задать время ожидания и токен отмены.</span><span class="sxs-lookup"><span data-stu-id="1b03f-119">To avoid these deadlocks, use the overloads of the <xref:System.Threading.Barrier.SignalAndWait%2A> method to specify a time-out period and a cancellation token.</span></span> <span data-ttu-id="1b03f-120">Эти перегрузки возвращают логическое значение, которое может проверить каждый участник перед переходом к следующему этапу.</span><span class="sxs-lookup"><span data-stu-id="1b03f-120">These overloads return a Boolean value that every participant can check before it continues to the next phase.</span></span>  
  
## <a name="post-phase-exceptions"></a><span data-ttu-id="1b03f-121">Исключения следующих этапов</span><span class="sxs-lookup"><span data-stu-id="1b03f-121">Post-Phase Exceptions</span></span>  
 <span data-ttu-id="1b03f-122">Если делегат следующего этапа создает исключение, оно инкапсулируется в объект <xref:System.Threading.BarrierPostPhaseException>, который затем передается всем участникам.</span><span class="sxs-lookup"><span data-stu-id="1b03f-122">If the post-phase delegate throws an exception, it is wrapped in a <xref:System.Threading.BarrierPostPhaseException> object which is then propagated to all participants.</span></span>  
  
## <a name="barrier-versus-continuewhenall"></a><span data-ttu-id="1b03f-123">Сравнение барьера и ContinueWhenAll</span><span class="sxs-lookup"><span data-stu-id="1b03f-123">Barrier Versus ContinueWhenAll</span></span>  
 <span data-ttu-id="1b03f-124">Барьеры особенно полезны, когда потоки выполняют несколько этапов циклически.</span><span class="sxs-lookup"><span data-stu-id="1b03f-124">Barriers are especially useful when the threads are performing multiple phases in loops.</span></span> <span data-ttu-id="1b03f-125">Если код требует выполнения только в один–два этапа, рассмотрите возможность использования объектов <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> с любым видом неявного объединения, в том числе:</span><span class="sxs-lookup"><span data-stu-id="1b03f-125">If your code requires only one or two phases of work, consider whether to use <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects with any kind of implicit join, including:</span></span>  
  
-   <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.Invoke%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.ForEach%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.For%2A>  
  
 <span data-ttu-id="1b03f-126">Подробнее см. в разделе [Создание цепочки задач с помощью задач продолжения](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="1b03f-126">For more information, see [Chaining Tasks by Using Continuation Tasks](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b03f-127">См. также</span><span class="sxs-lookup"><span data-stu-id="1b03f-127">See also</span></span>

- [<span data-ttu-id="1b03f-128">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="1b03f-128">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
- [<span data-ttu-id="1b03f-129">Практическое руководство. Синхронизация параллельных операций с барьером</span><span class="sxs-lookup"><span data-stu-id="1b03f-129">How to: Synchronize Concurrent Operations with a Barrier</span></span>](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md)
