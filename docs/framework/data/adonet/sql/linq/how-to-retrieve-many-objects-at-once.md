---
title: Практическое руководство. Как получить несколько объектов одновременно
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: 48cdb47bec35b5315e03629d3a01657136bf7ed2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781687"
---
# <a name="how-to-retrieve-many-objects-at-once"></a><span data-ttu-id="31bf6-102">Практическое руководство. Как получить несколько объектов одновременно</span><span class="sxs-lookup"><span data-stu-id="31bf6-102">How to: Retrieve Many Objects At Once</span></span>
<span data-ttu-id="31bf6-103">Для извлечения нескольких объектов из одного запроса используется <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="31bf6-103">You can retrieve many objects in one query by using <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31bf6-104">Пример</span><span class="sxs-lookup"><span data-stu-id="31bf6-104">Example</span></span>  
 <span data-ttu-id="31bf6-105">В следующем коде для извлечения объекта <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> и `Customer` используется метод `Order`.</span><span class="sxs-lookup"><span data-stu-id="31bf6-105">The following code uses the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to retrieve both `Customer` and `Order` objects.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="31bf6-106">См. также</span><span class="sxs-lookup"><span data-stu-id="31bf6-106">See also</span></span>

- [<span data-ttu-id="31bf6-107">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="31bf6-107">Query Concepts</span></span>](query-concepts.md)
