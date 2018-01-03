---
title: "Практическое руководство. Добавление параметров запроса к запросу службы данных (службы данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- querying the data service [WCF Data Services]
- WCF Data Services, querying
- WCF Data Services, accessing data
ms.assetid: e4258526-557e-4e96-91e1-2175400c7c8f
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 55ed062ce2b4464618dfdb8184be65847195280d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-query-options-to-a-data-service-query-wcf-data-services"></a>Практическое руководство. Добавление параметров запроса к запросу службы данных (службы данных WCF)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют выполнять запросы к службе данных из клиентского приложения на основе .NET Framework с использованием сформированных клиентских классов службы данных. Самый легкий способ сделать это — составить выражение запроса LINQ, включающее необходимые параметры запроса. Также можно вызвать ряд методов запросов LINQ для составления эквивалентного запроса. Наконец, с помощью метода <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> можно добавить в запрос параметры запросов. В каждом из этих случаев URI, формируемый клиентом, включает запрошенный набор сущностей и выбранные параметры запросов. Дополнительные сведения см. в разделе [запросы к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и клиентские классы данных создаются после выполнения [краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует создание выражения запроса LINQ, возвращающего только заказы с ценой доставки, превышающей 30 долларов, упорядоченные по дате поставки в убывающем порядке.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsLinq](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptionslinq)]
 [!code-vb[Astoria Northwind Client#AddQueryOptionsLinq](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptionslinq)]  
  
## <a name="example"></a>Пример  
 Следующий пример показывает, как создать запрос LINQ, эквивалентный предыдущему запросу с использованием методов запросов LINQ.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqExpression](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptionslinqexpression)]
 [!code-vb[Astoria Northwind Client#AddQueryOptionsLinqExpression](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptionslinqexpression)]  
  
## <a name="example"></a>Пример  
 В следующем примере показывается, как можно использовать метод <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> для создания запроса <xref:System.Data.Services.Client.DataServiceQuery%601>, эквивалентного запросам в предыдущих примерах.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptions)]
 [!code-vb[Astoria Northwind Client#AddQueryOptions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptions)]  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует использование параметра запросов `$orderby` для одновременной фильтрации и упорядочения возвращаемых объектов Orders по свойству Freight.  
  
 [!code-csharp[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#orderwithfilter)]
 [!code-vb[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#orderwithfilter)]  
  
## <a name="see-also"></a>См. также  
 [Выполнение запросов к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
 [Практическое руководство. Проекция результатов запроса](../../../../docs/framework/data/wcf/how-to-project-query-results-wcf-data-services.md)
