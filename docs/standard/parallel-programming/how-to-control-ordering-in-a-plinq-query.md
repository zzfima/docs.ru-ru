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
ms.openlocfilehash: 86011cff71fabed5e47e085f91b1759238638c9a
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588492"
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a><span data-ttu-id="63d8e-102">Практическое руководство. Управление порядком в запросе PLINQ</span><span class="sxs-lookup"><span data-stu-id="63d8e-102">How to: Control Ordering in a PLINQ Query</span></span>
<span data-ttu-id="63d8e-103">В этих примерах показано, как управлять правилами упорядочения в запросе PLINQ с помощью метода расширения <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>.</span><span class="sxs-lookup"><span data-stu-id="63d8e-103">These examples show how to control the ordering in a PLINQ query by using the <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> extension method.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="63d8e-104">Эти примеры предназначены в основном для демонстрации использования, и могут выполняться быстрее или не быстрее аналогичных последовательных запросов LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="63d8e-104">These examples are primarily intended to demonstrate usage, and may or may not run faster than the equivalent sequential LINQ to Objects queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63d8e-105">Пример</span><span class="sxs-lookup"><span data-stu-id="63d8e-105">Example</span></span>  
 <span data-ttu-id="63d8e-106">В следующем примере сохраняется порядок исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="63d8e-106">The following example preserves the ordering of the source sequence.</span></span> <span data-ttu-id="63d8e-107">Иногда это необходимо. Например, некоторым операторам запроса нужна упорядоченная исходная последовательность для предоставления правильных результатов.</span><span class="sxs-lookup"><span data-stu-id="63d8e-107">This is sometimes necessary; for example some query operators require an ordered source sequence to produce correct results.</span></span>  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="63d8e-108">Пример</span><span class="sxs-lookup"><span data-stu-id="63d8e-108">Example</span></span>  
 <span data-ttu-id="63d8e-109">В следующем примере показано несколько операторов запроса, для которых может ожидаться упорядоченная исходная последовательность.</span><span class="sxs-lookup"><span data-stu-id="63d8e-109">The following example shows some query operators whose source sequence is probably expected to be ordered.</span></span> <span data-ttu-id="63d8e-110">Эти операторы могут работать и с неупорядоченными последовательностями, но иногда возвращают непредвиденные результаты.</span><span class="sxs-lookup"><span data-stu-id="63d8e-110">These operators will work on unordered sequences, but they might produce unexpected results.</span></span>  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 <span data-ttu-id="63d8e-111">Чтобы запустить этот метод, вставьте его в класс PLINQDataSample из проекта [Пример данных PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) и нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="63d8e-111">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63d8e-112">Пример</span><span class="sxs-lookup"><span data-stu-id="63d8e-112">Example</span></span>  
 <span data-ttu-id="63d8e-113">В следующем примере сохраняется порядок последовательности в первой части запроса, затем отменяется упорядочение, чтобы повысить производительность предложения join, и снова применяется упорядочение для конечной результирующей последовательности.</span><span class="sxs-lookup"><span data-stu-id="63d8e-113">The following example shows how to preserve ordering for the first part of a query, then remove the ordering to increase the performance of a join clause, and then reapply ordering to the final result sequence.</span></span>  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 <span data-ttu-id="63d8e-114">Чтобы запустить этот метод, вставьте его в класс PLINQDataSample из проекта [Пример данных PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) и нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="63d8e-114">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d8e-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="63d8e-115">See also</span></span>

- <xref:System.Linq.ParallelEnumerable>
- [<span data-ttu-id="63d8e-116">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="63d8e-116">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
