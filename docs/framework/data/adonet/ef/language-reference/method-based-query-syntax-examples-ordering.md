---
title: "Примеры синтаксиса запросов на основе методов: упорядочение | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 5d21b178-d731-471a-8534-1f8184a2ef06
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Примеры синтаксиса запросов на основе методов: упорядочение
Примеры в этом разделе демонстрируют, как использовать метод <xref:System.Linq.Enumerable.ThenBy%2A>, чтобы выполнить запрос к [модели AdventureWorks Sales](http://msdn.microsoft.com/ru-ru/f16cd988-673f-4376-b034-129ca93c7832) с помощью синтаксиса запросов на основе методов.  Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.  
  
 В примерах, приведенных в этом разделе, используются следующие инструкции `using`\/`Imports`:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## ThenBy  
  
### Пример  
 В следующем примере, в синтаксисе запросов на основе методов, используются методы <xref:System.Linq.Queryable.OrderBy%2A> и <xref:System.Linq.Queryable.ThenBy%2A>, чтобы вернуть список контактов, отсортированный сначала по фамилии, а затем по имени.  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby_mq)]
 [!code-vb[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby_mq)]  
  
## ThenByDescending  
  
### Пример  
 В следующем примере используются методы <xref:System.Linq.Queryable.OrderBy%2A> и <xref:System.Linq.Queryable.ThenByDescending%2A>, чтобы вначале выполнить сортировку по стоимости, а затем сортировку по убыванию по названию продуктов.  
  
 [!code-csharp[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescending_mq)]
 [!code-vb[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescending_mq)]  
  
## См. также  
 [Запросы в LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)