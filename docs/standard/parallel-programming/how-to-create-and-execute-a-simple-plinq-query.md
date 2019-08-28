---
title: Практическое руководство. Создание и выполнение простого запроса PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 472304dff23e92620dd461e8bc43c3093431ddc4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962519"
---
# <a name="how-to-create-and-execute-a-simple-plinq-query"></a><span data-ttu-id="55e0a-102">Практическое руководство. Создание и выполнение простого запроса PLINQ</span><span class="sxs-lookup"><span data-stu-id="55e0a-102">How to: Create and Execute a Simple PLINQ Query</span></span>
<span data-ttu-id="55e0a-103">В следующем примере показано, как создать простой параллельный запрос LINQ (PLINQ) с помощью метода расширения <xref:System.Linq.ParallelEnumerable.AsParallel%2A> исходной последовательности, а также выполнить запрос с помощью метода <xref:System.Linq.ParallelEnumerable.ForAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="55e0a-103">The following example shows how to create a simple Parallel LINQ query by using the <xref:System.Linq.ParallelEnumerable.AsParallel%2A> extension method on the source sequence, and executing the query by using the <xref:System.Linq.ParallelEnumerable.ForAll%2A> method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55e0a-104">В этой документации для определения делегатов в PLINQ используются лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="55e0a-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="55e0a-105">Если вы не знакомы с лямбда-выражениями в C# или Visual Basic, см. раздел [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="55e0a-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="55e0a-106">Пример</span><span class="sxs-lookup"><span data-stu-id="55e0a-106">Example</span></span>  
 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 <span data-ttu-id="55e0a-107">В данном примере показан базовый шаблон для создания и выполнения любого параллельного запроса LINQ в случае, когда порядок последовательности результатов не имеет значения; неупорядоченные запросы обычно выполняются быстрее упорядоченных.</span><span class="sxs-lookup"><span data-stu-id="55e0a-107">This example demonstrates the basic pattern for creating and executing any Parallel LINQ query when the ordering of the result sequence is not important; unordered queries are generally faster than ordered queries.</span></span> <span data-ttu-id="55e0a-108">Запрос делит источник на задачи, выполняемые асинхронно в нескольких потоках.</span><span class="sxs-lookup"><span data-stu-id="55e0a-108">The query partitions the source into tasks that are executed asynchronously on multiple threads.</span></span> <span data-ttu-id="55e0a-109">Порядок выполнения каждой из задач зависит не только от объема работы по обработке элементов в разделе, но и от внешних факторов, например, от планирования каждого из потоков операционной системой.</span><span class="sxs-lookup"><span data-stu-id="55e0a-109">The order in which each task completes depends not only on the amount of work involved to process the elements in the partition, but also on external factors such as how the operating system schedules each thread.</span></span> <span data-ttu-id="55e0a-110">Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="55e0a-110">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="55e0a-111">См. дополнительные сведения об [ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="55e0a-111">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span> <span data-ttu-id="55e0a-112">Дополнительные сведения о сохранении порядка элементов в запросе см. в статье [Практическое руководство. Управление порядком в запросе PLINQ](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md).</span><span class="sxs-lookup"><span data-stu-id="55e0a-112">For more information about how to preserve the ordering of elements in a query, see [How to: Control Ordering in a PLINQ Query](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e0a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="55e0a-113">See also</span></span>

- [<span data-ttu-id="55e0a-114">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="55e0a-114">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
