---
title: "Объединение двух последовательностей | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Объединение двух последовательностей
Для объединения двух последовательностей используется оператор <xref:System.Linq.Queryable.Concat%2A>.  
  
 Оператор <xref:System.Linq.Queryable.Concat%2A> определен для упорядоченных множественных наборов, в которых порядок получателя и аргумента совпадают.  
  
 В SQL упорядочивание является последним шагом перед получением результатов.  Поэтому оператор <xref:System.Linq.Queryable.Concat%2A> реализован с помощью `UNION ALL` и не сохраняет порядок своих аргументов.  Для обеспечения правильного порядка в результатах требуется их явное упорядочение.  
  
## Пример  
 В данном примере для возвращения последовательности всех номеров телефонов и факсов `Customer` и `Employee` используется <xref:System.Linq.Queryable.Concat%2A>.  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## Пример  
 В данном примере для возвращения последовательности всех сопоставлений имен и номеров телефонов `Customer` и `Employee` используется <xref:System.Linq.Queryable.Concat%2A>.  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## См. также  
 [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)   
 [Преобразование стандартных операторов запросов](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)