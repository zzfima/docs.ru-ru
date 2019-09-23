---
title: Возврат объединения наборов двух последовательностей.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 058856243b2a8daaecd653a9b5999013de5407a8
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182523"
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="88d1b-102">Возврат объединения наборов двух последовательностей.</span><span class="sxs-lookup"><span data-stu-id="88d1b-102">Return the Set Union of Two Sequences</span></span>
<span data-ttu-id="88d1b-103">Оператор <xref:System.Linq.Queryable.Union%2A> используется для возвращения объединения наборов двух последовательностей.</span><span class="sxs-lookup"><span data-stu-id="88d1b-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88d1b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="88d1b-104">Example</span></span>  
 <span data-ttu-id="88d1b-105">В этом примере <xref:System.Linq.Queryable.Union%2A> используется для возврата последовательности всех стран или регионов, в которых есть `Customers` или `Employees`.</span><span class="sxs-lookup"><span data-stu-id="88d1b-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries/regions in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="88d1b-106">В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]оператор определяется для множества наборов как неупорядоченное объединение множества наборов ( [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) фактически результат предложения в SQL). <xref:System.Linq.Queryable.Union%2A></span><span class="sxs-lookup"><span data-stu-id="88d1b-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) clause in SQL).</span></span>

<span data-ttu-id="88d1b-107">Дополнительные сведения и примеры см. в <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>разделе.</span><span class="sxs-lookup"><span data-stu-id="88d1b-107">For more info and examples, see <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="88d1b-108">См. также</span><span class="sxs-lookup"><span data-stu-id="88d1b-108">See also</span></span>

- [<span data-ttu-id="88d1b-109">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="88d1b-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="88d1b-110">Преобразование стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="88d1b-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
