---
title: "Примеры синтаксиса выражений запроса. Отношения навигации"
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
ms.assetid: 0d4a7f41-c758-4059-8f83-d2e9c2745593
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c029ce130e0bc8a6f959c6c27d863422794c22e5
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="query-expression-syntax-examples-navigating-relationships"></a>Примеры синтаксиса выражений запроса. Отношения навигации
Свойства навигации в модели [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] - это свойства быстрого доступа, используемые для нахождения сущностей в элементах ассоциации. Свойства навигации позволяют пользователю переходить от одной сущности к другой или от сущности к связанным сущностям в наборе ассоциаций. В этом разделе в синтаксисе выражений запросов представлены примеры того, как осуществляется навигация по связям с помощью свойств навигации в запросах [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  
  
 Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.  
  
 В примерах в этом разделе используются следующие `using` / `Imports` инструкции:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется метод <xref:System.Linq.Queryable.Select%2A> для возврата всех идентификаторов контактных лиц и итогового значения суммы заказов для каждого контактного лица с фамилией «Zhou». Свойство навигации `Contact.SalesOrderHeader` используется для получения коллекции объектов `SalesOrderHeader` для каждого контактного лица. Метод `Sum` использует свойство навигации `Contact.SalesOrderHeader` для получения суммы всех заказов для каждого контактного лица.  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2)]  
  
## <a name="example"></a>Пример  
 В следующем примере осуществляется возврат всех заказов контактных лиц с фамилией «Zhou». Свойство навигации `Contact.SalesOrderHeader` используется для получения коллекции объектов `SalesOrderHeader` для каждого контактного лица. Имя и заказы контактного лица возвращаются в анонимном типе.  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3)]  
  
## <a name="example"></a>Пример  
 В следующем примере используются свойства навигации объектов `SalesOrderHeader.Address` и `SalesOrderHeader.Contact` для возврата коллекции объектов `Address` и `Contact`, связанных с каждым заказом. Фамилия контактного лица, адрес, номер заказа на продажу и сумма заказа по каждому заказу в Сиэттле возвращаются в анонимном типе.  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships)]  
  
### <a name="example"></a>Пример  
 В следующем примере используется метод `Where` для нахождения заказов, сделанных после 1 декабря 2003 г. После этого с помощью свойства навигации `order.SalesOrderDetail` определяются подробности каждого заказа.  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a>См. также  
 [Запросы в LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
