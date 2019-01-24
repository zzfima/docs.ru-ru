---
title: Удаление дубликатов элементов из последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b224a84-bad5-4843-adcc-14e784d280f5
ms.openlocfilehash: 604307bd179136c9c2b685faa5164f9b5ecabaf9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738174"
---
# <a name="eliminate-duplicate-elements-from-a-sequence"></a><span data-ttu-id="81ab8-102">Удаление дубликатов элементов из последовательности</span><span class="sxs-lookup"><span data-stu-id="81ab8-102">Eliminate Duplicate Elements from a Sequence</span></span>
<span data-ttu-id="81ab8-103">Чтобы исключить элементы-дубликаты из последовательности, воспользуйтесь оператором <xref:System.Linq.Queryable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="81ab8-103">Use the <xref:System.Linq.Queryable.Distinct%2A> operator to eliminate duplicate elements from a sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81ab8-104">Пример</span><span class="sxs-lookup"><span data-stu-id="81ab8-104">Example</span></span>  
 <span data-ttu-id="81ab8-105">В следующем примере для выбора последовательности уникальных городов, в которых находятся клиенты, используется метод <xref:System.Linq.Queryable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="81ab8-105">The following example uses <xref:System.Linq.Queryable.Distinct%2A> to select a sequence of the unique cities that have customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#36](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#36)]
 [!code-vb[DLinqQueryExamples#36](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#36)]  
  
## <a name="see-also"></a><span data-ttu-id="81ab8-106">См. также</span><span class="sxs-lookup"><span data-stu-id="81ab8-106">See also</span></span>
- [<span data-ttu-id="81ab8-107">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="81ab8-107">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
