---
title: "Как добавить параметры запроса к запросу службы данных (службы WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "запросы к службе данных [службы WCF Data Services]"
  - "Службы WCF Data Services, доступ к данным"
  - "Службы WCF Data Services, запрос"
ms.assetid: e4258526-557e-4e96-91e1-2175400c7c8f
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Как добавить параметры запроса к запросу службы данных (службы WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяет запрашивать службы данных из клиентского приложения на основе .NET Framework, используя сформированные классы клиентской службы данных. Проще всего этого добиться, составив выражение запроса LINQ, которое включает в себя параметры желаемого запроса.  Также можно вызвать ряд методов запросов LINQ для составления эквивалентного запроса.  Наконец, с помощью метода <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> можно добавить в запрос параметры запросов.  В каждом из этих случаев URI, формируемый клиентом, включает запрошенный набор сущностей и выбранные параметры запросов.  Для получения дополнительной информации см. [Запросы к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных.  Эта служба и клиентские классы данных создаются после выполнения действий, описанных в разделе [Краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Пример  
 Следующий пример иллюстрирует создание выражения запроса LINQ, возвращающего только заказы с ценой доставки, превышающей 30 долларов, упорядоченные по дате поставки в убывающем порядке.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsLinq](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptionslinq)]
 [!code-vb[Astoria Northwind Client#AddQueryOptionsLinq](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptionslinq)]  
  
## Пример  
 Следующий пример показывает, как создать запрос LINQ, эквивалентный предыдущему запросу с использованием методов запросов LINQ.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqExpression](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptionslinqexpression)]
 [!code-vb[Astoria Northwind Client#AddQueryOptionsLinqExpression](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptionslinqexpression)]  
  
## Пример  
 В следующем примере показывается, как можно использовать метод <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> для создания запроса <xref:System.Data.Services.Client.DataServiceQuery%601>, эквивалентного запросам в предыдущих примерах.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptions)]
 [!code-vb[Astoria Northwind Client#AddQueryOptions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptions)]  
  
## Пример  
 Следующий пример иллюстрирует использование параметра запросов `$orderby` для одновременной фильтрации и упорядочения возвращаемых объектов Orders по свойству Freight.  
  
 [!code-csharp[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#orderwithfilter)]
 [!code-vb[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#orderwithfilter)]  
  
## См. также  
 [Запросы к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)   
 [Как проецировать результаты запроса](../../../../docs/framework/data/wcf/how-to-project-query-results-wcf-data-services.md)