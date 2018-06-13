---
title: Практическое руководство. Управление порядком в запросе PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to control ordering
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89e0abf711730326b6391184a2e3a1b55b303957
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580215"
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a><span data-ttu-id="3823a-102">Практическое руководство. Управление порядком в запросе PLINQ</span><span class="sxs-lookup"><span data-stu-id="3823a-102">How to: Control Ordering in a PLINQ Query</span></span>
<span data-ttu-id="3823a-103">В этих примерах показано, как управлять правилами упорядочения в запросе PLINQ с помощью метода расширения <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>.</span><span class="sxs-lookup"><span data-stu-id="3823a-103">These examples show how to control the ordering in a PLINQ query by using the <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> extension method.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="3823a-104">Эти примеры предназначены в основном для демонстрации использования, и могут выполняться быстрее или не быстрее аналогичных последовательных запросов LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="3823a-104">These examples are primarily intended to demonstrate usage, and may or may not run faster than the equivalent sequential LINQ to Objects queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3823a-105">Пример</span><span class="sxs-lookup"><span data-stu-id="3823a-105">Example</span></span>  
 <span data-ttu-id="3823a-106">В следующем примере сохраняется порядок исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="3823a-106">The following example preserves the ordering of the source sequence.</span></span> <span data-ttu-id="3823a-107">Иногда это необходимо. Например, некоторым операторам запроса нужна упорядоченная исходная последовательность для предоставления правильных результатов.</span><span class="sxs-lookup"><span data-stu-id="3823a-107">This is sometimes necessary; for example some query operators require an ordered source sequence to produce correct results.</span></span>  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="3823a-108">Пример</span><span class="sxs-lookup"><span data-stu-id="3823a-108">Example</span></span>  
 <span data-ttu-id="3823a-109">В следующем примере показано несколько операторов запроса, для которых может ожидаться упорядоченная исходная последовательность.</span><span class="sxs-lookup"><span data-stu-id="3823a-109">The following example shows some query operators whose source sequence is probably expected to be ordered.</span></span> <span data-ttu-id="3823a-110">Эти операторы могут работать и с неупорядоченными последовательностями, но иногда возвращают непредвиденные результаты.</span><span class="sxs-lookup"><span data-stu-id="3823a-110">These operators will work on unordered sequences, but they might produce unexpected results.</span></span>  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 <span data-ttu-id="3823a-111">Чтобы запустить этот метод, вставьте его в класс PLINQDataSample из проекта [Пример данных PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) и нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="3823a-111">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3823a-112">Пример</span><span class="sxs-lookup"><span data-stu-id="3823a-112">Example</span></span>  
 <span data-ttu-id="3823a-113">В следующем примере сохраняется порядок последовательности в первой части запроса, затем отменяется упорядочение, чтобы повысить производительность предложения join, и снова применяется упорядочение для конечной результирующей последовательности.</span><span class="sxs-lookup"><span data-stu-id="3823a-113">The following example shows how to preserve ordering for the first part of a query, then remove the ordering to increase the performance of a join clause, and then reapply ordering to the final result sequence.</span></span>  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 <span data-ttu-id="3823a-114">Чтобы запустить этот метод, вставьте его в класс PLINQDataSample из проекта [Пример данных PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) и нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="3823a-114">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3823a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3823a-115">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="3823a-116">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="3823a-116">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
