---
title: Удаление дубликатов элементов из последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b224a84-bad5-4843-adcc-14e784d280f5
ms.openlocfilehash: 3dbb5be65823b456e5b573f7cbbad8d172022425
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="eliminate-duplicate-elements-from-a-sequence"></a><span data-ttu-id="80af7-102">Удаление дубликатов элементов из последовательности</span><span class="sxs-lookup"><span data-stu-id="80af7-102">Eliminate Duplicate Elements from a Sequence</span></span>
<span data-ttu-id="80af7-103">Чтобы исключить элементы-дубликаты из последовательности, воспользуйтесь оператором <xref:System.Linq.Queryable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="80af7-103">Use the <xref:System.Linq.Queryable.Distinct%2A> operator to eliminate duplicate elements from a sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80af7-104">Пример</span><span class="sxs-lookup"><span data-stu-id="80af7-104">Example</span></span>  
 <span data-ttu-id="80af7-105">В следующем примере для выбора последовательности уникальных городов, в которых находятся клиенты, используется метод <xref:System.Linq.Queryable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="80af7-105">The following example uses <xref:System.Linq.Queryable.Distinct%2A> to select a sequence of the unique cities that have customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#36](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#36)]
 [!code-vb[DLinqQueryExamples#36](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#36)]  
  
## <a name="see-also"></a><span data-ttu-id="80af7-106">См. также</span><span class="sxs-lookup"><span data-stu-id="80af7-106">See Also</span></span>  
 [<span data-ttu-id="80af7-107">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="80af7-107">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
