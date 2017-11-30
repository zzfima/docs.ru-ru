---
title: "Практическое руководство. Задание режима выполнения в PLINQ"
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
helpviewer_keywords: PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 745ceae9832582c7b66a56075d128f9cf1c8ff69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a><span data-ttu-id="62bde-102">Практическое руководство. Задание режима выполнения в PLINQ</span><span class="sxs-lookup"><span data-stu-id="62bde-102">How to: Specify the Execution Mode in PLINQ</span></span>
<span data-ttu-id="62bde-103">В этом примере показано, как для принудительного пропуска его эвристику по умолчанию и параллелизации запроса независимо от формы запроса PLINQ.</span><span class="sxs-lookup"><span data-stu-id="62bde-103">This example shows how to force PLINQ to bypass its default heuristics and parallelize a query regardless of the query's shape.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="62bde-104">Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="62bde-104">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="62bde-105">Дополнительные сведения об увеличении скорости см. в разделе [понимание ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="62bde-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="62bde-106">Пример</span><span class="sxs-lookup"><span data-stu-id="62bde-106">Example</span></span>  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 <span data-ttu-id="62bde-107">PLINQ предназначен для использования возможностей параллелизации.</span><span class="sxs-lookup"><span data-stu-id="62bde-107">PLINQ is designed to exploit opportunities for parallelization.</span></span> <span data-ttu-id="62bde-108">Однако не все запросы выигрывать от параллельной обработки.</span><span class="sxs-lookup"><span data-stu-id="62bde-108">However, not all queries benefit from parallel execution.</span></span> <span data-ttu-id="62bde-109">Например если запрос содержит отдельный пользовательский делегат, который выполняет мало работы, запрос обычно выполняется быстрее последовательно.</span><span class="sxs-lookup"><span data-stu-id="62bde-109">For example, when a query contains a single user delegate that does very little work, the query will usually run faster sequentially.</span></span> <span data-ttu-id="62bde-110">Это потому, что нагрузка, вызванная выполнения параллелизации требуется дороже, чем ускорение работы, которая получается.</span><span class="sxs-lookup"><span data-stu-id="62bde-110">This is because the overhead involved in enabling parallelizing execution is more expensive than the speedup that is obtained.</span></span> <span data-ttu-id="62bde-111">Таким образом PLINQ не выполнять автоматическую параллелизацию каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="62bde-111">Therefore, PLINQ does not automatically parallelize every query.</span></span> <span data-ttu-id="62bde-112">Во-первых, он проверяет в форме запроса и различные операторы, входящих в него.</span><span class="sxs-lookup"><span data-stu-id="62bde-112">It first examines the shape of the query and the various operators that comprise it.</span></span> <span data-ttu-id="62bde-113">На основании этого анализа PLINQ в режиме выполнения по умолчанию может потребоваться выполнить некоторые или все запрос последовательно.</span><span class="sxs-lookup"><span data-stu-id="62bde-113">Based on this analysis, PLINQ in the default execution mode may decide to execute some or all of the query sequentially.</span></span> <span data-ttu-id="62bde-114">Однако в некоторых случаях может быть известно больше о запросе, чем PLINQ способен определить на основе анализа.</span><span class="sxs-lookup"><span data-stu-id="62bde-114">However, in some cases you may know more about your query than PLINQ is able to determine from its analysis.</span></span> <span data-ttu-id="62bde-115">Например вы знаете, что делегат является весьма затратным, и что запрос будет определенно выигрыш от параллелизации.</span><span class="sxs-lookup"><span data-stu-id="62bde-115">For example, you may know that a delegate is very expensive, and that the query will definitely benefit from parallelization.</span></span> <span data-ttu-id="62bde-116">В таких случаях можно использовать <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> метод и укажите <xref:System.Linq.ParallelExecutionMode.ForceParallelism> значение для указания PLINQ всегда выполнял запрос параллельно.</span><span class="sxs-lookup"><span data-stu-id="62bde-116">In such cases, you can use the <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> method and specify the <xref:System.Linq.ParallelExecutionMode.ForceParallelism> value to instruct PLINQ to always run the query as parallel.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="62bde-117">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="62bde-117">Compiling the Code</span></span>  
 <span data-ttu-id="62bde-118">Скопируйте и вставьте этот код в [пример данных PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) и вызовите метод из `Main`.</span><span class="sxs-lookup"><span data-stu-id="62bde-118">Cut and paste this code into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) and call the method from `Main`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62bde-119">См. также</span><span class="sxs-lookup"><span data-stu-id="62bde-119">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>  
 [<span data-ttu-id="62bde-120">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="62bde-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
