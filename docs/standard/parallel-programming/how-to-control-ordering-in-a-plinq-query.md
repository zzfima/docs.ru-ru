---
title: "Практическое руководство. Управление порядком в запросе PLINQ"
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
helpviewer_keywords: PLINQ queries, how to control ordering
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9e29aa825a68154e32a34a23ca170258092b88a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a><span data-ttu-id="a7505-102">Практическое руководство. Управление порядком в запросе PLINQ</span><span class="sxs-lookup"><span data-stu-id="a7505-102">How to: Control Ordering in a PLINQ Query</span></span>
<span data-ttu-id="a7505-103">Эти примеры показывают, как управление порядком в запросе PLINQ с помощью <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> метода расширения.</span><span class="sxs-lookup"><span data-stu-id="a7505-103">These examples show how to control the ordering in a PLINQ query by using the <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> extension method.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="a7505-104">Эти примеры в основном предназначен для демонстрации использования и может выполняться быстрее, чем эквивалентный последовательный LINQ to Objects, запросы.</span><span class="sxs-lookup"><span data-stu-id="a7505-104">These examples are primarily intended to demonstrate usage, and may or may not run faster than the equivalent sequential LINQ to Objects queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7505-105">Пример</span><span class="sxs-lookup"><span data-stu-id="a7505-105">Example</span></span>  
 <span data-ttu-id="a7505-106">Следующий пример сохраняет порядок исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="a7505-106">The following example preserves the ordering of the source sequence.</span></span> <span data-ttu-id="a7505-107">Иногда это необходимо; Например, некоторые операторы запросов требуется упорядоченный исходной последовательности для получения правильных результатов.</span><span class="sxs-lookup"><span data-stu-id="a7505-107">This is sometimes necessary; for example some query operators require an ordered source sequence to produce correct results.</span></span>  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="a7505-108">Пример</span><span class="sxs-lookup"><span data-stu-id="a7505-108">Example</span></span>  
 <span data-ttu-id="a7505-109">В следующем примере некоторые операторы, исходная последовательность, возможно, ожидалось упорядоченный запроса.</span><span class="sxs-lookup"><span data-stu-id="a7505-109">The following example shows some query operators whose source sequence is probably expected to be ordered.</span></span> <span data-ttu-id="a7505-110">Эти операторы будут работать с неупорядоченными последовательностями, но они могут привести к непредвиденным результатам.</span><span class="sxs-lookup"><span data-stu-id="a7505-110">These operators will work on unordered sequences, but they might produce unexpected results.</span></span>  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 <span data-ttu-id="a7505-111">Чтобы запустить этот метод, вставьте его в класс PLINQDataSample в [пример данных PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) проекта и нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="a7505-111">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7505-112">Пример</span><span class="sxs-lookup"><span data-stu-id="a7505-112">Example</span></span>  
 <span data-ttu-id="a7505-113">Приведенный ниже показано, как сохранить порядок первой части запроса, а затем удалить его для повышения производительности предложения join и повторно применить упорядочение окончательный результат последовательности.</span><span class="sxs-lookup"><span data-stu-id="a7505-113">The following example shows how to preserve ordering for the first part of a query, then remove the ordering to increase the performance of a join clause, and then reapply ordering to the final result sequence.</span></span>  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 <span data-ttu-id="a7505-114">Чтобы запустить этот метод, вставьте его в класс PLINQDataSample в [пример данных PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) проекта и нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="a7505-114">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7505-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a7505-115">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="a7505-116">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="a7505-116">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
