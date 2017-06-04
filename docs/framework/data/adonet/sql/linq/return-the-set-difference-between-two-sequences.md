---
title: "Возвращение различий в наборах двух последовательностей | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Возвращение различий в наборах двух последовательностей
Оператор <xref:System.Linq.Queryable.Except%2A> используется для возвращения разности наборов между двумя последовательностями.  
  
## Пример  
 В данном примере для возвращения последовательности всех стран, где живут `Customers`, но не `Employees`, используется <xref:System.Linq.Queryable.Except%2A>.  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] оператор <xref:System.Linq.Queryable.Except%2A> правильно определен только в наборах.  Семантика для мультинаборов не определена.  
  
## См. также  
 [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)   
 [Преобразование стандартных операторов запросов](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)