---
title: Практическое руководство. Как получить несколько объектов одновременно
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: dd53c2fd16a82ce0f69a33e0b7d7ffef7815b91b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220530"
---
# <a name="how-to-retrieve-many-objects-at-once"></a><span data-ttu-id="e68c4-102">Практическое руководство. Как получить несколько объектов одновременно</span><span class="sxs-lookup"><span data-stu-id="e68c4-102">How to: Retrieve Many Objects At Once</span></span>
<span data-ttu-id="e68c4-103">Для извлечения нескольких объектов из одного запроса используется <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="e68c4-103">You can retrieve many objects in one query by using <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e68c4-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e68c4-104">Example</span></span>  
 <span data-ttu-id="e68c4-105">В следующем коде для извлечения объекта <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> и `Customer` используется метод `Order`.</span><span class="sxs-lookup"><span data-stu-id="e68c4-105">The following code uses the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to retrieve both `Customer` and `Order` objects.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="e68c4-106">См. также</span><span class="sxs-lookup"><span data-stu-id="e68c4-106">See also</span></span>

- [<span data-ttu-id="e68c4-107">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="e68c4-107">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
