---
title: "Как определить количество сущностей, возвращенных запросом (службы WCF Data Services) | Microsoft Docs"
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
  - "Службы WCF Data Services, число строк"
ms.assetid: 03d41a82-df95-40ac-8439-a6c327d37ba8
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Как определить количество сущностей, возвращенных запросом (службы WCF Data Services)
В [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] можно определить число сущностей в наборе сущностей, заданном в URI запроса.  Это число можно включить в результат запроса или представить как целое значение.  Для получения дополнительной информации см. [Запросы к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных.  Эта служба и клиентские классы данных создаются после выполнения действий, описанных в разделе [Краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Пример  
 В этом примере запрос выполняется после вызова метода <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A>.  Свойство <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A> возвращает число сущностей в наборе сущностей `Customers`.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#countallcustomers)]
 [!code-vb[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#countallcustomers)]  
  
## Пример  
 В данном примере метод <xref:System.Linq.Enumerable.Count%2A> вызывается для возвращения только целого значения числа сущностей в наборе сущностей `Customers`.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#countallcustomersvalueonly)]
 [!code-vb[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#countallcustomersvalueonly)]  
  
## См. также  
 [Запросы к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)