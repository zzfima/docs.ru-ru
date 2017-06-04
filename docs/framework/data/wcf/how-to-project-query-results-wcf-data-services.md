---
title: "Как проецировать результаты запроса (службы WCF Data Services) | Microsoft Docs"
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
  - "проекция [службы WCF Data Services]"
  - "проекция запроса [службы WCF Data Services]"
  - "Службы WCF Data Services, проекция"
  - "Службы WCF Data Services, запрос"
ms.assetid: 474ac625-8770-43ba-8320-d3315ea9530f
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Как проецировать результаты запроса (службы WCF Data Services)
Проекция представляет собой механизм уменьшения объема возвращаемых запросом данных путем указания того, что в ответе возвращаются только определенные свойства сущности.  Можно выполнить проекции результатов запроса [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], используя либо параметр запроса `$select`, либо предложение [select](../Topic/select%20clause%20\(C%23%20Reference\).md) \([Select](../Topic/Select%20Clause%20\(Visual%20Basic\).md) в Visual Basic\) в запросе LINQ.  Дополнительные сведения см. в разделе [Запросы к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных.  Эта служба и клиентские классы данных создаются после выполнения действий, описанных в разделе [Краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Пример  
 В следующем примере показан запрос LINQ, проецирующий сущности Customers в новый тип CustomerAddress, который содержит только зависящие от адреса свойства плюс свойство\- идентификатор.  Этот класс `CustomerAddress` определен на клиенте и помечается с помощью атрибута, таким образом библиотека клиентов может распознать его как тип сущности.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddress)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddress)]  
  
## Пример  
 В следующем примере показан запрос LINQ, который проецирует возвращаемые сущности Customer в новый тип CustomerAddressNonEntity, который содержит только зависящие от адреса свойства и не содержит свойство\-идентификатор.  Этот класс `CustomerAddressNonEntity` определен на клиенте и не помечается с помощью атрибута как тип сущности.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddressnonentity)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddressnonentity)]  
  
## Пример  
 В следующем примере показаны определения типов `CustomerAddress` `CustomerAddressNonEntity`, которые используются в предыдущих примерах.  
  
 [!code-csharp[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customeraddress.cs#customeraddressdefinition)]
 [!code-vb[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customeraddress.vb#customeraddressdefinition)]