---
title: Возврат пересечения наборов двух последовательностей.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 3458ebf8f5708496eef6246fa55cf528e8a32bc4
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380058"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="bd318-102">Возврат пересечения наборов двух последовательностей.</span><span class="sxs-lookup"><span data-stu-id="bd318-102">Return the Set Intersection of Two Sequences</span></span>
<span data-ttu-id="bd318-103">Для возвращения пересечения наборов двух последовательностей используется оператор <xref:System.Linq.Queryable.Intersect%2A>.</span><span class="sxs-lookup"><span data-stu-id="bd318-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd318-104">Пример</span><span class="sxs-lookup"><span data-stu-id="bd318-104">Example</span></span>  
 <span data-ttu-id="bd318-105">В этом примере используется <xref:System.Linq.Queryable.Intersect%2A> для возвращения последовательности всех стран и регионов, где `Customers` и `Employees` live.</span><span class="sxs-lookup"><span data-stu-id="bd318-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries/regions in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="bd318-106">В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] оператор <xref:System.Linq.Queryable.Intersect%2A> правильно определен только в наборах.</span><span class="sxs-lookup"><span data-stu-id="bd318-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="bd318-107">Семантика для мультинаборов не определена.</span><span class="sxs-lookup"><span data-stu-id="bd318-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd318-108">См. также</span><span class="sxs-lookup"><span data-stu-id="bd318-108">See also</span></span>

- [<span data-ttu-id="bd318-109">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="bd318-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="bd318-110">Преобразование стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="bd318-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
