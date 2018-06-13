---
title: Сцепление двух последовательностей
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
ms.openlocfilehash: c0a6dde667c4f858d8177dc80a726619f463f3a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354057"
---
# <a name="concatenate-two-sequences"></a><span data-ttu-id="9503a-102">Сцепление двух последовательностей</span><span class="sxs-lookup"><span data-stu-id="9503a-102">Concatenate Two Sequences</span></span>
<span data-ttu-id="9503a-103">Для объединения двух последовательностей используется оператор <xref:System.Linq.Queryable.Concat%2A>.</span><span class="sxs-lookup"><span data-stu-id="9503a-103">Use the <xref:System.Linq.Queryable.Concat%2A> operator to concatenate two sequences.</span></span>  
  
 <span data-ttu-id="9503a-104">Оператор <xref:System.Linq.Queryable.Concat%2A> определен для упорядоченных множественных наборов, в которых порядок получателя и аргумента совпадают.</span><span class="sxs-lookup"><span data-stu-id="9503a-104">The <xref:System.Linq.Queryable.Concat%2A> operator is defined for ordered multisets where the orders of the receiver and the argument are the same.</span></span>  
  
 <span data-ttu-id="9503a-105">В SQL упорядочивание является последним шагом перед получением результатов.</span><span class="sxs-lookup"><span data-stu-id="9503a-105">Ordering in SQL is the final step before results are produced.</span></span> <span data-ttu-id="9503a-106">Поэтому оператор <xref:System.Linq.Queryable.Concat%2A> реализован с помощью `UNION ALL` и не сохраняет порядок своих аргументов.</span><span class="sxs-lookup"><span data-stu-id="9503a-106">For this reason, the <xref:System.Linq.Queryable.Concat%2A> operator is implemented by using `UNION ALL` and does not preserve the order of its arguments.</span></span> <span data-ttu-id="9503a-107">Для обеспечения правильного порядка в результатах требуется их явное упорядочение.</span><span class="sxs-lookup"><span data-stu-id="9503a-107">To make sure ordering is correct in the results, make sure to explicitly order the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9503a-108">Пример</span><span class="sxs-lookup"><span data-stu-id="9503a-108">Example</span></span>  
 <span data-ttu-id="9503a-109">В данном примере для возвращения последовательности всех номеров телефонов и факсов <xref:System.Linq.Queryable.Concat%2A> и `Customer` используется `Employee`.</span><span class="sxs-lookup"><span data-stu-id="9503a-109">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` telephone and fax numbers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a><span data-ttu-id="9503a-110">Пример</span><span class="sxs-lookup"><span data-stu-id="9503a-110">Example</span></span>  
 <span data-ttu-id="9503a-111">В данном примере для возвращения последовательности всех сопоставлений имен и номеров телефонов <xref:System.Linq.Queryable.Concat%2A> и `Customer` используется `Employee`.</span><span class="sxs-lookup"><span data-stu-id="9503a-111">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` name and telephone number mappings.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a><span data-ttu-id="9503a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9503a-112">See Also</span></span>  
 [<span data-ttu-id="9503a-113">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="9503a-113">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="9503a-114">Преобразование стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="9503a-114">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
