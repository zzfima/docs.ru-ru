---
title: "Практическое руководство. Отмена задачи и ее дочерних элементов"
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
helpviewer_keywords: tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 374068694a3aa9724905964717dc5e77c09fc0ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-task-and-its-children"></a><span data-ttu-id="c3040-102">Практическое руководство. Отмена задачи и ее дочерних элементов</span><span class="sxs-lookup"><span data-stu-id="c3040-102">How to: Cancel a Task and Its Children</span></span>
<span data-ttu-id="c3040-103">Этих примерах показано, как выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="c3040-103">These examples show how to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="c3040-104">Создание и запуск задаче с возможностью отмены.</span><span class="sxs-lookup"><span data-stu-id="c3040-104">Create and start a cancelable task.</span></span>  
  
2.  <span data-ttu-id="c3040-105">Передача токена отмены пользовательскому делегату и при необходимости экземпляру задачи.</span><span class="sxs-lookup"><span data-stu-id="c3040-105">Pass a cancellation token to your user delegate and optionally to the task instance.</span></span>  
  
3.  <span data-ttu-id="c3040-106">Обратите внимание и ответить на запрос отмены в пользовательском делегате.</span><span class="sxs-lookup"><span data-stu-id="c3040-106">Notice and respond to the cancellation request in your user delegate.</span></span>  
  
4.  <span data-ttu-id="c3040-107">При необходимости Обратите внимание, в вызывающем потоке, выполнение задачи было отменено.</span><span class="sxs-lookup"><span data-stu-id="c3040-107">Optionally notice on the calling thread that the task was canceled.</span></span>  
  
 <span data-ttu-id="c3040-108">Вызывающий поток не завершает задачу принудительно; он только сообщает о запросе отмены.</span><span class="sxs-lookup"><span data-stu-id="c3040-108">The calling thread does not forcibly end the task; it only signals that cancellation is requested.</span></span> <span data-ttu-id="c3040-109">Если задача уже выполняется, именно пользовательский делегат рассмотрение запроса и реагировать соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="c3040-109">If the task is already running, it is up to the user delegate to notice the request and respond appropriately.</span></span> <span data-ttu-id="c3040-110">При поступлении запроса отмены до запуска задачи пользовательский делегат никогда не выполняется, и объект задачи переходит в состояние Canceled.</span><span class="sxs-lookup"><span data-stu-id="c3040-110">If cancellation is requested before the task runs, then the user delegate is never executed and the task object transitions into the Canceled state.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3040-111">Пример</span><span class="sxs-lookup"><span data-stu-id="c3040-111">Example</span></span>  
 <span data-ttu-id="c3040-112">В этом примере показано, как завершить <xref:System.Threading.Tasks.Task> и его дочерних элементов в ответ на запрос отмены.</span><span class="sxs-lookup"><span data-stu-id="c3040-112">This example shows how to terminate a <xref:System.Threading.Tasks.Task> and its children in response to a cancellation request.</span></span> <span data-ttu-id="c3040-113">Здесь также показано, что при завершении пользовательского делегата путем создания исключения <xref:System.Threading.Tasks.TaskCanceledException> вызывающий поток может дополнительно использовать метод <xref:System.Threading.Tasks.Task.Wait%2A> или метод <xref:System.Threading.Tasks.Task.WaitAll%2A> для ожидания завершения задач.</span><span class="sxs-lookup"><span data-stu-id="c3040-113">It also shows that when a user delegate terminates by throwing a <xref:System.Threading.Tasks.TaskCanceledException>, the calling thread can optionally use the <xref:System.Threading.Tasks.Task.Wait%2A> method or <xref:System.Threading.Tasks.Task.WaitAll%2A> method to wait for the tasks to finish.</span></span> <span data-ttu-id="c3040-114">В этом случае необходимо использовать блок `try/catch` для обработки исключений в вызывающем потоке.</span><span class="sxs-lookup"><span data-stu-id="c3040-114">In this case, you must use a `try/catch` block to handle the exceptions on the calling thread.</span></span>  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 <span data-ttu-id="c3040-115"><xref:System.Threading.Tasks.Task?displayProperty=nameWithType> Класс полностью интегрирован с моделью отмены, который основан на <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> и <xref:System.Threading.CancellationToken?displayProperty=nameWithType> типов.</span><span class="sxs-lookup"><span data-stu-id="c3040-115">The <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> class is fully integrated with the cancellation model that is based on the <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> and <xref:System.Threading.CancellationToken?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="c3040-116">Дополнительные сведения см. в разделе [Отмена в управляемых потоках](../../../docs/standard/threading/cancellation-in-managed-threads.md) и [отмены задачи](../../../docs/standard/parallel-programming/task-cancellation.md).</span><span class="sxs-lookup"><span data-stu-id="c3040-116">For more information, see [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md) and [Task Cancellation](../../../docs/standard/parallel-programming/task-cancellation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3040-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c3040-117">See Also</span></span>  
 <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>  
 <xref:System.Threading.CancellationToken?displayProperty=nameWithType>  
 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>  
 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>  
 [<span data-ttu-id="c3040-118">Асинхронное программирование на основе задач</span><span class="sxs-lookup"><span data-stu-id="c3040-118">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)  
 [<span data-ttu-id="c3040-119">Присоединенные и отсоединенные дочерние задачи</span><span class="sxs-lookup"><span data-stu-id="c3040-119">Attached and Detached Child Tasks</span></span>](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md)  
 [<span data-ttu-id="c3040-120">Лямбда-выражения в PLINQ и TPL</span><span class="sxs-lookup"><span data-stu-id="c3040-120">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
