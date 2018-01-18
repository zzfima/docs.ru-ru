---
title: "Практическое руководство. Фильтрация связанных данных"
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
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 27c09badda5675158ca5c50481472db142eca32e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-filter-related-data"></a><span data-ttu-id="2876f-102">Практическое руководство. Фильтрация связанных данных</span><span class="sxs-lookup"><span data-stu-id="2876f-102">How to: Filter Related Data</span></span>
<span data-ttu-id="2876f-103">Чтобы указать вложенные запросы для ограничения объема извлекаемых данных, используется метод <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="2876f-103">Use the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method to specify sub-queries to limit the amount of retrieved data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2876f-104">Пример</span><span class="sxs-lookup"><span data-stu-id="2876f-104">Example</span></span>  
 <span data-ttu-id="2876f-105">В следующем примере метод <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> ограничивает количество извлеченных заказов (`Orders`) заказами, которые сегодня не были доставлены.</span><span class="sxs-lookup"><span data-stu-id="2876f-105">In the following example, the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method limits the `Orders` retrieved to those that have not been shipped today.</span></span> <span data-ttu-id="2876f-106">Если не использовать этот подход, будут извлечены все заказы (`Orders`) даже в том случае, когда необходим только вложенный набор.</span><span class="sxs-lookup"><span data-stu-id="2876f-106">Without this approach, all `Orders` would have been retrieved even though only a subset is desired.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2876f-107">См. также</span><span class="sxs-lookup"><span data-stu-id="2876f-107">See Also</span></span>  
 [<span data-ttu-id="2876f-108">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="2876f-108">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
