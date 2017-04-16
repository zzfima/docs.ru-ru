---
title: "Примеры синтаксиса запросов на основе методов: операторы работы с элементами | Microsoft Docs"
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
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Примеры синтаксиса запросов на основе методов: операторы работы с элементами
Примеры в этом разделе демонстрируют, как использовать метод <xref:System.Linq.Enumerable.First%2A>, чтобы выполнить запрос к [модели AdventureWorks Sales](http://msdn.microsoft.com/ru-ru/f16cd988-673f-4376-b034-129ca93c7832) с помощью синтаксиса запросов на основе методов.  Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.  
  
 В примере в этом разделе используются следующие инструкции `using`\/`Imports`:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## First  
  
### Пример  
 В следующем примере метод <xref:System.Linq.Enumerable.First%2A> используется для нахождения первого адреса электронной почты, начинающегося со строки «caroline».  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## См. также  
 [Запросы в LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)