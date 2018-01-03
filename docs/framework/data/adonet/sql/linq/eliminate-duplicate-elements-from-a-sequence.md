---
title: "Удаление дубликатов элементов из последовательности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 2b224a84-bad5-4843-adcc-14e784d280f5
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 844b9cc43755041ebccae63f477b4f1b21bd69c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="eliminate-duplicate-elements-from-a-sequence"></a><span data-ttu-id="cf18b-102">Удаление дубликатов элементов из последовательности</span><span class="sxs-lookup"><span data-stu-id="cf18b-102">Eliminate Duplicate Elements from a Sequence</span></span>
<span data-ttu-id="cf18b-103">Чтобы исключить элементы-дубликаты из последовательности, воспользуйтесь оператором <xref:System.Linq.Queryable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf18b-103">Use the <xref:System.Linq.Queryable.Distinct%2A> operator to eliminate duplicate elements from a sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf18b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="cf18b-104">Example</span></span>  
 <span data-ttu-id="cf18b-105">В следующем примере для выбора последовательности уникальных городов, в которых находятся клиенты, используется метод <xref:System.Linq.Queryable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf18b-105">The following example uses <xref:System.Linq.Queryable.Distinct%2A> to select a sequence of the unique cities that have customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#36](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#36)]
 [!code-vb[DLinqQueryExamples#36](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#36)]  
  
## <a name="see-also"></a><span data-ttu-id="cf18b-106">См. также</span><span class="sxs-lookup"><span data-stu-id="cf18b-106">See Also</span></span>  
 [<span data-ttu-id="cf18b-107">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="cf18b-107">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
