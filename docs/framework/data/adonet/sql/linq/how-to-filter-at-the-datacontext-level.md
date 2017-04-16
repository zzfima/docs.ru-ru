---
title: "Как отфильтровать данные на уровне DataContext | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как отфильтровать данные на уровне DataContext
Фильтрацию `EntitySets` можно выполнить на уровне `DataContext`.  Подобные фильтры применяются ко всем запросам, осуществленным с помощью экземпляра <xref:System.Data.Linq.DataContext>.  
  
## Пример  
 В следующем примере <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=fullName> используется для фильтрации предварительно загруженных заказов для клиентов по `ShippedDate`.  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## См. также  
 [Основные понятия о запросах](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)