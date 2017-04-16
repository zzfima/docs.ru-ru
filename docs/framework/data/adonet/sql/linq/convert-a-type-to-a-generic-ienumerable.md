---
title: "Преобразование последовательности в общий интерфейс IEnumerable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Преобразование последовательности в общий интерфейс IEnumerable
Для возвращения аргумента с типом универсальный `IEnumerable` используется <xref:System.Linq.Enumerable.AsEnumerable%2A>.  
  
## Пример  
 В этом примере [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] \(с помощью заданного по умолчанию универсального `Query`\) предпримет попытку преобразовать запрос в SQL и выполнить его на сервере.  Однако предложение `where` ссылается на пользовательский метод на стороне клиента \(`isValidProduct`\), который не может быть преобразован в SQL.  
  
 Решением является задание клиентской универсальной реализации <xref:System.Collections.Generic.IEnumerable%601> предложения `where` для замены универсального <xref:System.Linq.IQueryable%601>.  Для этого следует вызвать оператор <xref:System.Linq.Enumerable.AsEnumerable%2A>.  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## См. также  
 [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)