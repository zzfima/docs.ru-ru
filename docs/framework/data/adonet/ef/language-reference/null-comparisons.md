---
title: "Сравнения со значением Null | Microsoft Docs"
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
ms.assetid: ef88af8c-8dfe-4556-8b56-81df960a900b
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Сравнения со значением Null
Значение `null` в источнике данных указывает на то, что это значение неизвестно.  В запросах [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] можно реализовать проверку наличия значений NULL так, чтобы определенные вычисления или сравнения выполнялись только для строк с допустимыми данными, не содержащими значений NULL.  Впрочем, null\-семантика среды CLR может отличаться от null\-семантики источника данных.  В большинстве баз данных для выполнения сравнений со значением Null используется трехзначная логика.  Иначе говоря, результат сравнения со значением Null не дает ни `true`, ни `false`; в результате получается значение `unknown`.  Часто речь идет о реализациях Null ANSI, но так бывает не всегда.  
  
 По умолчанию в SQL Server сравнение «Null равняется Null» возвращает значение Null.  В следующем примере строки, где параметр `ShipDate` имеет значение NULL, исключаются из результирующего набора, и инструкция [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] возвращает 0 строк.  
  
```  
-- Find order details and orders with no ship date.  
SELECT h.SalesOrderID  
FROM Sales.SalesOrderHeader h  
JOIN Sales.SalesOrderDetail o ON o.SalesOrderID = h.SalesOrderID  
WHERE h.ShipDate IS Null  
```  
  
 Это совсем не похоже на Null\-семантику среды CRL, где сравнение «Null равняется Null» возвращает значение True.  
  
 Следующий запрос LINQ выражается в среде CLR, но выполняется в источнике данных.  Гарантии того, что семантика CLR будет действительна для среды источника данных, не существует, поэтому предполагаемое поведение непредсказуемо.  
  
 [!code-csharp[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#joinonnull)]
 [!code-vb[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#joinonnull)]  
  
## Селекторы ключей  
 *Селектор ключа* \- функция, используемая в стандартных операторах запросов для извлечения ключа из элемента.  В функции селектора элемента может быть выполнено сравнение выражения с константой.  Null\-семантика CLR проявляется в тех случаях, когда выражение сравнивается с константой, имеющей значение Null, или когда сравниваются две константы со значениями Null.  Null\-семантика хранилищ проявляется в тех случаях, когда сравниваются два столбца источника данных со значениями Null.  Селекторы ключей входят в состав многих используемых в запросах стандартных операторов группирования и упорядочивания, например <xref:System.Linq.Queryable.GroupBy%2A>, и применяются для выделения ключей, по которым будет осуществляться упорядочение или группирование результатов запроса.  
  
## Свойство Null объекта Null  
 В [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] свойства объекта Null имеют значения Null.  При попытке обратиться к свойству объекта Null в среде CLR пользователь получает исключение <xref:System.NullReferenceException>.  Когда в LINQ\-запросе задействовано свойство объекта Null, может быть получен несогласованный результат.  
  
 Так, в следующем примере приведение к типу `NewProduct` осуществляется на уровне дерева команд. В результате может получиться так, что свойство `Introduced` будет иметь значение Null.  Если определенные в базе данных сравнения со значением Null таковы, что сравнение с <xref:System.DateTime> дает значение True, то соответствующая строка будет включена.  
  
 [!code-csharp[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#castresultsisnull)]
 [!code-vb[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#castresultsisnull)]  
  
## Передача коллекций значений NULL в статистические функции  
 В языке [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)], если в агрегатную функцию передается коллекция, которая поддерживает интерфейс `IQueryable`, то статистические операции выполняются в базе данных.  Могут обнаруживаться различия в результатах запроса, который был выполнен в оперативной памяти, и запроса, который был выполнен в базе данных.  Что касается запроса в памяти, то если совпадения отсутствуют, запрос возвращает ноль.  В базе данных тот же самый запрос возвращает `null`.  Если агрегатные функции LINQ передается значение `null`, вызывается исключение.  Чтобы можно было принимать возможные значения `null`, приводите типы и свойства типов, которые получают результаты запроса, к типам, допускающим значения NULL.  
  
## См. также  
 [Выражения в запросах LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)