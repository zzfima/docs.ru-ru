---
title: Удаление дубликатов элементов из последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b224a84-bad5-4843-adcc-14e784d280f5
ms.openlocfilehash: 9b8e19ac76869c33d01a59ee3aad104a7ddbb8f7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782213"
---
# <a name="eliminate-duplicate-elements-from-a-sequence"></a><span data-ttu-id="86dea-102">Удаление дубликатов элементов из последовательности</span><span class="sxs-lookup"><span data-stu-id="86dea-102">Eliminate Duplicate Elements from a Sequence</span></span>
<span data-ttu-id="86dea-103">Чтобы исключить элементы-дубликаты из последовательности, воспользуйтесь оператором <xref:System.Linq.Queryable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="86dea-103">Use the <xref:System.Linq.Queryable.Distinct%2A> operator to eliminate duplicate elements from a sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86dea-104">Пример</span><span class="sxs-lookup"><span data-stu-id="86dea-104">Example</span></span>  
 <span data-ttu-id="86dea-105">В следующем примере для выбора последовательности уникальных городов, в которых находятся клиенты, используется метод <xref:System.Linq.Queryable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="86dea-105">The following example uses <xref:System.Linq.Queryable.Distinct%2A> to select a sequence of the unique cities that have customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#36](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#36)]
 [!code-vb[DLinqQueryExamples#36](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#36)]  
  
## <a name="see-also"></a><span data-ttu-id="86dea-106">См. также</span><span class="sxs-lookup"><span data-stu-id="86dea-106">See also</span></span>

- [<span data-ttu-id="86dea-107">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="86dea-107">Query Examples</span></span>](query-examples.md)
