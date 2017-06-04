---
title: "Как загружать результаты, разбитые на страницы (службы WCF Data Services) | Microsoft Docs"
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
  - "Службы WCF Data Services, отложенное содержимое"
  - "Службы WCF Data Services, загрузка данных"
ms.assetid: bb786ea4-f3ef-4ad3-9a41-3a0b7feb6a1f
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Как загружать результаты, разбитые на страницы (службы WCF Data Services)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют службе данных ограничить количество сущностей, возвращаемых в отдельном канале ответа.  Если это происходит, последняя запись в канале содержит ссылку на следующую страницу данных.  URI для следующей страницы данных получен путем вызова метода <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A> объекта <xref:System.Data.Services.Client.QueryOperationResponse%601>, возвращенного при выполнении <xref:System.Data.Services.Client.DataServiceQuery%601>. Затем для загрузки следующей страницы результатов используется URI, представленный этим объектом.  Для получения дополнительной информации см. [Загрузка отложенного содержимого](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных.  Эта служба и клиентские классы данных создаются после выполнения действий, описанных в разделе [Краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Пример  
 Этот пример использует цикл `do…while` для загрузки сущностей `Customers` из разбитых на страницы результатов службы данных.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getcustomerspaged)]
 [!code-vb[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getcustomerspaged)]  
  
## Пример  
 Этот пример возвращает связанные сущности `Orders` вместе с каждой сущностью `Customers` и использует цикл `do…while` для загрузки страниц сущностей `Customers`, а также вложенный цикл `while` для загрузки страниц связанных сущностей `Orders` из службы данных.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getcustomerspagednested)]
 [!code-vb[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getcustomerspagednested)]  
  
## См. также  
 [Загрузка отложенного содержимого](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)   
 [Как загрузить связанные сущности](../../../../docs/framework/data/wcf/how-to-load-related-entities-wcf-data-services.md)