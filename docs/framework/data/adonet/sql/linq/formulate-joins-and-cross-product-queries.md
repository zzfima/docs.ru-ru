---
title: "Формирование соединений и запросов с перекрестными произведениями | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Формирование соединений и запросов с перекрестными произведениями
В следующем примере показано, как объединить результаты из нескольких таблиц.  
  
## Пример  
 В следующем примере для выбора всех заказов клиентов из Лондона используются переходы по внешним ключам в предложении `From` языка [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(предложении `from` языка C\#\).  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## Пример  
 В следующем примере для фильтрации отсутствующих на складе продуктов `Products`, поставщики \(`Supplier`\) которых находятся в США, используются переходы по внешним ключам в предложении `Where` языка [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(предложении `where` языка C\#\).  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## Пример  
 В следующем примере для фильтрации сотрудников, расположенных в Сиэтле, и получения списка закрепленных за ними регионов, используются переходы по внешним ключам в предложении `From` языка [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(предложении `from` языка C\#\).  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## Пример  
 В следующем примере для фильтрации пар сотрудников, в которых один сотрудник сообщает о другом и оба сотрудника находятся в одном городе \(`City`\), используются переходы по внешним ключам в предложении `Select` языка [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(предложении `select` языка C\#\).  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## Пример  
 В следующем примере, реализованном на языке [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)], выполняется поиск всех клиентов и заказов, проверяется соответствие заказов клиентам и для каждого клиента в списке указывается контактное лицо.  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## Пример  
 В следующем пример явно соединяются две таблицы и проецируются результаты из обеих таблиц.  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## Пример  
 В следующем пример явно соединяются три таблицы и проецируются результаты из каждой таблицы.  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## Пример  
 В следующем примере показано, как реализовать оператор `LEFT OUTER JOIN` с помощью метода `DefaultIfEmpty()`.  Если для сотрудника \(`Employee`\) не имеется заказов \(`Order`\), метод `DefaultIfEmpty()` возвращает значение NULL.  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## Пример  
 В следующем примере проецируется выражение `let`, полученное в результате соединения.  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## Пример  
 В следующем примере показан оператор `join` с композитным ключом.  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## Пример  
 В следующем примере показано, как создать оператор `join`, в котором одна сторона может принимать значение NULL, а другая сторона не может.  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## См. также  
 [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)