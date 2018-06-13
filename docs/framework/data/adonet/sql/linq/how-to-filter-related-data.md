---
title: Практическое руководство. Фильтрация связанных данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
ms.openlocfilehash: b40de7201610c58b9b8e86045afe5869d958bdf6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360839"
---
# <a name="how-to-filter-related-data"></a><span data-ttu-id="8092e-102">Практическое руководство. Фильтрация связанных данных</span><span class="sxs-lookup"><span data-stu-id="8092e-102">How to: Filter Related Data</span></span>
<span data-ttu-id="8092e-103">Чтобы указать вложенные запросы для ограничения объема извлекаемых данных, используется метод <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="8092e-103">Use the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method to specify sub-queries to limit the amount of retrieved data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8092e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8092e-104">Example</span></span>  
 <span data-ttu-id="8092e-105">В следующем примере метод <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> ограничивает количество извлеченных заказов (`Orders`) заказами, которые сегодня не были доставлены.</span><span class="sxs-lookup"><span data-stu-id="8092e-105">In the following example, the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method limits the `Orders` retrieved to those that have not been shipped today.</span></span> <span data-ttu-id="8092e-106">Если не использовать этот подход, будут извлечены все заказы (`Orders`) даже в том случае, когда необходим только вложенный набор.</span><span class="sxs-lookup"><span data-stu-id="8092e-106">Without this approach, all `Orders` would have been retrieved even though only a subset is desired.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8092e-107">См. также</span><span class="sxs-lookup"><span data-stu-id="8092e-107">See Also</span></span>  
 [<span data-ttu-id="8092e-108">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="8092e-108">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
