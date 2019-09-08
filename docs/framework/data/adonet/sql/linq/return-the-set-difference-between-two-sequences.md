---
title: Возврат разности наборов между двумя последовательностями
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 92513ed33e2afb785edbdd462ba7bc14923aa6b0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781144"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="0c655-102">Возврат разности наборов между двумя последовательностями</span><span class="sxs-lookup"><span data-stu-id="0c655-102">Return the Set Difference Between Two Sequences</span></span>
<span data-ttu-id="0c655-103">Оператор <xref:System.Linq.Queryable.Except%2A> используется для возвращения разности наборов между двумя последовательностями.</span><span class="sxs-lookup"><span data-stu-id="0c655-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c655-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0c655-104">Example</span></span>  
 <span data-ttu-id="0c655-105">В этом примере <xref:System.Linq.Queryable.Except%2A> используется для возврата последовательности всех стран или регионов, `Customers` в которых динамический, но не `Employees` в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="0c655-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries/regions in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="0c655-106">В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] оператор <xref:System.Linq.Queryable.Except%2A> правильно определен только в наборах.</span><span class="sxs-lookup"><span data-stu-id="0c655-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="0c655-107">Семантика для мультинаборов не определена.</span><span class="sxs-lookup"><span data-stu-id="0c655-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c655-108">См. также</span><span class="sxs-lookup"><span data-stu-id="0c655-108">See also</span></span>

- [<span data-ttu-id="0c655-109">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="0c655-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="0c655-110">Преобразование стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="0c655-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
