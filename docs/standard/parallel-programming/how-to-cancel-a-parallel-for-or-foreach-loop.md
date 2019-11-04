---
title: Практическое руководство. Отмена цикла Parallel.For или Parallel.ForEach
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel foreach loop, how to cancel
- parallel for loops, how to cancel
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
ms.openlocfilehash: 67f1f91f235cc88deaa97d412f368819ae0a8cda
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134246"
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a><span data-ttu-id="8ede4-102">Практическое руководство. Отмена цикла Parallel.For или Parallel.ForEach</span><span class="sxs-lookup"><span data-stu-id="8ede4-102">How to: Cancel a Parallel.For or ForEach Loop</span></span>
<span data-ttu-id="8ede4-103">Метод <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> поддерживают отмену с применением маркеров отмены.</span><span class="sxs-lookup"><span data-stu-id="8ede4-103">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> methods support cancellation through the use of cancellation tokens.</span></span> <span data-ttu-id="8ede4-104">Дополнительные сведения о механизмах отмены в целом см. в [этой статье](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="8ede4-104">For more information about cancellation in general, see [Cancellation](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span> <span data-ttu-id="8ede4-105">В параллельном цикле <xref:System.Threading.CancellationToken> передается в методу через параметр <xref:System.Threading.Tasks.ParallelOptions>, и этот параллельный вызов заключен в блок try-catch.</span><span class="sxs-lookup"><span data-stu-id="8ede4-105">In a parallel loop, you supply the <xref:System.Threading.CancellationToken> to the method in the <xref:System.Threading.Tasks.ParallelOptions> parameter and then enclose the parallel call in a try-catch block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ede4-106">Пример</span><span class="sxs-lookup"><span data-stu-id="8ede4-106">Example</span></span>  
 <span data-ttu-id="8ede4-107">Следующий пример демонстрирует, как отменить вызов <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8ede4-107">The following example shows how to cancel a call to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8ede4-108">Этот же подход вы можете применить и к вызову <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8ede4-108">You can apply the same approach to a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> call.</span></span>  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 <span data-ttu-id="8ede4-109">Если маркер, сообщающий об отмене, совпадает с указанным в экземпляре <xref:System.Threading.Tasks.ParallelOptions>маркером, то параллельный цикл создаст для отмены одно исключение <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="8ede4-109">If the token that signals the cancellation is the same token that is specified in the <xref:System.Threading.Tasks.ParallelOptions> instance, then the parallel loop will throw a single <xref:System.OperationCanceledException> on cancellation.</span></span> <span data-ttu-id="8ede4-110">Если отмена вызвана другим маркером, цикл создаст исключение <xref:System.AggregateException> и вложит в него <xref:System.OperationCanceledException> в качестве значения InnerException.</span><span class="sxs-lookup"><span data-stu-id="8ede4-110">If some other token causes cancellation, the loop will throw an <xref:System.AggregateException> with an <xref:System.OperationCanceledException> as an InnerException.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ede4-111">См. также</span><span class="sxs-lookup"><span data-stu-id="8ede4-111">See also</span></span>

- [<span data-ttu-id="8ede4-112">Параллелизм данных</span><span class="sxs-lookup"><span data-stu-id="8ede4-112">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="8ede4-113">Лямбда-выражения в PLINQ и TPL</span><span class="sxs-lookup"><span data-stu-id="8ede4-113">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
