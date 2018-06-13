---
title: Возврат разности наборов между двумя последовательностями
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 80348961d2848e9664e6978789ceb2441ea2f89a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356222"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="ed9ae-102">Возврат разности наборов между двумя последовательностями</span><span class="sxs-lookup"><span data-stu-id="ed9ae-102">Return the Set Difference Between Two Sequences</span></span>
<span data-ttu-id="ed9ae-103">Оператор <xref:System.Linq.Queryable.Except%2A> используется для возвращения разности наборов между двумя последовательностями.</span><span class="sxs-lookup"><span data-stu-id="ed9ae-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed9ae-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ed9ae-104">Example</span></span>  
 <span data-ttu-id="ed9ae-105">В данном примере для возвращения последовательности всех стран, где живут <xref:System.Linq.Queryable.Except%2A>, но не `Customers`, используется `Employees`.</span><span class="sxs-lookup"><span data-stu-id="ed9ae-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="ed9ae-106">В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] оператор <xref:System.Linq.Queryable.Except%2A> правильно определен только в наборах.</span><span class="sxs-lookup"><span data-stu-id="ed9ae-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="ed9ae-107">Семантика для мультинаборов не определена.</span><span class="sxs-lookup"><span data-stu-id="ed9ae-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed9ae-108">См. также</span><span class="sxs-lookup"><span data-stu-id="ed9ae-108">See Also</span></span>  
 [<span data-ttu-id="ed9ae-109">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="ed9ae-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="ed9ae-110">Преобразование стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="ed9ae-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
