---
title: Возврат разности наборов между двумя последовательностями
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 282ec36a2ad489e77db9fb5b338d3189c3001f03
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609035"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="3fa32-102">Возврат разности наборов между двумя последовательностями</span><span class="sxs-lookup"><span data-stu-id="3fa32-102">Return the Set Difference Between Two Sequences</span></span>
<span data-ttu-id="3fa32-103">Оператор <xref:System.Linq.Queryable.Except%2A> используется для возвращения разности наборов между двумя последовательностями.</span><span class="sxs-lookup"><span data-stu-id="3fa32-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fa32-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3fa32-104">Example</span></span>  
 <span data-ttu-id="3fa32-105">В данном примере для возвращения последовательности всех стран, где живут <xref:System.Linq.Queryable.Except%2A>, но не `Customers`, используется `Employees`.</span><span class="sxs-lookup"><span data-stu-id="3fa32-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="3fa32-106">В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] оператор <xref:System.Linq.Queryable.Except%2A> правильно определен только в наборах.</span><span class="sxs-lookup"><span data-stu-id="3fa32-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="3fa32-107">Семантика для мультинаборов не определена.</span><span class="sxs-lookup"><span data-stu-id="3fa32-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fa32-108">См. также</span><span class="sxs-lookup"><span data-stu-id="3fa32-108">See also</span></span>
- [<span data-ttu-id="3fa32-109">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="3fa32-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="3fa32-110">Преобразование стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="3fa32-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
