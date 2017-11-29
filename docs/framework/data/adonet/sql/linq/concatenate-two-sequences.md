---
title: "Сцепление двух последовательностей"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e7230e1f53f58f37dacbb1f22fbad1593768e01e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="concatenate-two-sequences"></a><span data-ttu-id="6604d-102">Сцепление двух последовательностей</span><span class="sxs-lookup"><span data-stu-id="6604d-102">Concatenate Two Sequences</span></span>
<span data-ttu-id="6604d-103">Для объединения двух последовательностей используется оператор <xref:System.Linq.Queryable.Concat%2A>.</span><span class="sxs-lookup"><span data-stu-id="6604d-103">Use the <xref:System.Linq.Queryable.Concat%2A> operator to concatenate two sequences.</span></span>  
  
 <span data-ttu-id="6604d-104">Оператор <xref:System.Linq.Queryable.Concat%2A> определен для упорядоченных множественных наборов, в которых порядок получателя и аргумента совпадают.</span><span class="sxs-lookup"><span data-stu-id="6604d-104">The <xref:System.Linq.Queryable.Concat%2A> operator is defined for ordered multisets where the orders of the receiver and the argument are the same.</span></span>  
  
 <span data-ttu-id="6604d-105">В SQL упорядочивание является последним шагом перед получением результатов.</span><span class="sxs-lookup"><span data-stu-id="6604d-105">Ordering in SQL is the final step before results are produced.</span></span> <span data-ttu-id="6604d-106">Поэтому оператор <xref:System.Linq.Queryable.Concat%2A> реализован с помощью `UNION ALL` и не сохраняет порядок своих аргументов.</span><span class="sxs-lookup"><span data-stu-id="6604d-106">For this reason, the <xref:System.Linq.Queryable.Concat%2A> operator is implemented by using `UNION ALL` and does not preserve the order of its arguments.</span></span> <span data-ttu-id="6604d-107">Для обеспечения правильного порядка в результатах требуется их явное упорядочение.</span><span class="sxs-lookup"><span data-stu-id="6604d-107">To make sure ordering is correct in the results, make sure to explicitly order the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6604d-108">Пример</span><span class="sxs-lookup"><span data-stu-id="6604d-108">Example</span></span>  
 <span data-ttu-id="6604d-109">В данном примере для возвращения последовательности всех номеров телефонов и факсов <xref:System.Linq.Queryable.Concat%2A> и `Customer` используется `Employee`.</span><span class="sxs-lookup"><span data-stu-id="6604d-109">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` telephone and fax numbers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a><span data-ttu-id="6604d-110">Пример</span><span class="sxs-lookup"><span data-stu-id="6604d-110">Example</span></span>  
 <span data-ttu-id="6604d-111">В данном примере для возвращения последовательности всех сопоставлений имен и номеров телефонов <xref:System.Linq.Queryable.Concat%2A> и `Customer` используется `Employee`.</span><span class="sxs-lookup"><span data-stu-id="6604d-111">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` name and telephone number mappings.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a><span data-ttu-id="6604d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="6604d-112">See Also</span></span>  
 [<span data-ttu-id="6604d-113">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="6604d-113">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="6604d-114">Трансляция стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="6604d-114">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
