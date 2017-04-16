---
title: "Удаление повторяющихся элементов из последовательности | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2b224a84-bad5-4843-adcc-14e784d280f5
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Удаление повторяющихся элементов из последовательности
Чтобы исключить элементы\-дубликаты из последовательности, воспользуйтесь оператором <xref:System.Linq.Queryable.Distinct%2A>.  
  
## Пример  
 В следующем примере для выбора последовательности уникальных городов, в которых находятся клиенты, используется метод <xref:System.Linq.Queryable.Distinct%2A>.  
  
 [!code-csharp[DLinqQueryExamples#36](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#36)]
 [!code-vb[DLinqQueryExamples#36](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#36)]  
  
## См. также  
 [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)