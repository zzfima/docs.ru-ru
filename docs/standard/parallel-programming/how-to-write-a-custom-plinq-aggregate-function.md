---
title: "Практическое руководство. Написание пользовательской агрегатной функции PLINQ"
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
helpviewer_keywords: PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8b098f21e29d0d59cd99ddbb64af6246d9953a3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a><span data-ttu-id="ca7f2-102">Практическое руководство. Написание пользовательской агрегатной функции PLINQ</span><span class="sxs-lookup"><span data-stu-id="ca7f2-102">How to: Write a Custom PLINQ Aggregate Function</span></span>
<span data-ttu-id="ca7f2-103">В этом примере показано, как использовать <xref:System.Linq.ParallelEnumerable.Aggregate%2A> метод для применения пользовательской функции агрегирования к исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="ca7f2-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.Aggregate%2A> method to apply a custom aggregation function to a source sequence.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="ca7f2-104">Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="ca7f2-104">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="ca7f2-105">Дополнительные сведения об увеличении скорости см. в разделе [понимание ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="ca7f2-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca7f2-106">Пример</span><span class="sxs-lookup"><span data-stu-id="ca7f2-106">Example</span></span>  
 <span data-ttu-id="ca7f2-107">В следующем примере вычисляется стандартное отклонение последовательности целых чисел.</span><span class="sxs-lookup"><span data-stu-id="ca7f2-107">The following example calculates the standard deviation of a sequence of integers.</span></span>  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 <span data-ttu-id="ca7f2-108">В этом примере используется перегрузка стандартного оператора запроса Aggregate, уникального для PLINQ.</span><span class="sxs-lookup"><span data-stu-id="ca7f2-108">This example uses an overload of the Aggregate standard query operator that is unique to PLINQ.</span></span> <span data-ttu-id="ca7f2-109">Эта перегрузка принимает дополнительный <xref:System.Func%603?displayProperty=nameWithType> третьего входного параметра.</span><span class="sxs-lookup"><span data-stu-id="ca7f2-109">This overload takes an extra <xref:System.Func%603?displayProperty=nameWithType> as the third input parameter.</span></span> <span data-ttu-id="ca7f2-110">Этот делегат объединяет результаты из всех потоков перед выполнением окончательного расчета к статистическим результатам.</span><span class="sxs-lookup"><span data-stu-id="ca7f2-110">This delegate combines the results from all threads before it performs the final calculation on the aggregated results.</span></span> <span data-ttu-id="ca7f2-111">В этом примере складываются суммы из всех потоков.</span><span class="sxs-lookup"><span data-stu-id="ca7f2-111">In this example we add together the sums from all the threads.</span></span>  
  
 <span data-ttu-id="ca7f2-112">Обратите внимание, что, если тело лямбда-выражения состоит из одного выражения, возвращаемое значение <xref:System.Func%602?displayProperty=nameWithType> делегат является значение выражения.</span><span class="sxs-lookup"><span data-stu-id="ca7f2-112">Note that when a lambda expression body consists of a single expression, the return value of the <xref:System.Func%602?displayProperty=nameWithType> delegate is the value of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca7f2-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ca7f2-113">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="ca7f2-114">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="ca7f2-114">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
