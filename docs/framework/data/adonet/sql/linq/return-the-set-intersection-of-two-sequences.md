---
title: Возврат пересечения наборов двух последовательностей.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 944d0b2efe1e74f901a493d1c3202d0f180d599d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792700"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="9f216-102">Возврат пересечения наборов двух последовательностей.</span><span class="sxs-lookup"><span data-stu-id="9f216-102">Return the Set Intersection of Two Sequences</span></span>
<span data-ttu-id="9f216-103">Для возвращения пересечения наборов двух последовательностей используется оператор <xref:System.Linq.Queryable.Intersect%2A>.</span><span class="sxs-lookup"><span data-stu-id="9f216-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f216-104">Пример</span><span class="sxs-lookup"><span data-stu-id="9f216-104">Example</span></span>  
 <span data-ttu-id="9f216-105">В этом примере <xref:System.Linq.Queryable.Intersect%2A> используется для возврата последовательности всех стран или регионов `Customers` , в которых и, `Employees` и в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="9f216-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries/regions in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="9f216-106">В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] оператор <xref:System.Linq.Queryable.Intersect%2A> правильно определен только в наборах.</span><span class="sxs-lookup"><span data-stu-id="9f216-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="9f216-107">Семантика для мультинаборов не определена.</span><span class="sxs-lookup"><span data-stu-id="9f216-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f216-108">См. также</span><span class="sxs-lookup"><span data-stu-id="9f216-108">See also</span></span>

- [<span data-ttu-id="9f216-109">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="9f216-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="9f216-110">Преобразование стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="9f216-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
