---
title: Практическое руководство. Как фильтровать данные на уровне DataContext
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
ms.openlocfilehash: 343cffa9b1c034068e5abcc652e936f89ee6a992
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903010"
---
# <a name="how-to-filter-at-the-datacontext-level"></a><span data-ttu-id="de706-102">Практическое руководство. Как фильтровать данные на уровне DataContext</span><span class="sxs-lookup"><span data-stu-id="de706-102">How to: Filter at the DataContext Level</span></span>
<span data-ttu-id="de706-103">Фильтрацию `EntitySets` можно выполнить на уровне `DataContext`.</span><span class="sxs-lookup"><span data-stu-id="de706-103">You can filter `EntitySets` at the `DataContext` level.</span></span> <span data-ttu-id="de706-104">Подобные фильтры применяются ко всем запросам, осуществленным с помощью экземпляра <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="de706-104">Such filters apply to all queries done with that <xref:System.Data.Linq.DataContext> instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de706-105">Пример</span><span class="sxs-lookup"><span data-stu-id="de706-105">Example</span></span>  
 <span data-ttu-id="de706-106">В следующем примере <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> используется для фильтрации предварительно загруженных заказов для клиентов по `ShippedDate`.</span><span class="sxs-lookup"><span data-stu-id="de706-106">In the following example, <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> is used to filter the pre-loaded orders for customers by `ShippedDate`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="de706-107">См. также</span><span class="sxs-lookup"><span data-stu-id="de706-107">See also</span></span>

- [<span data-ttu-id="de706-108">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="de706-108">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
