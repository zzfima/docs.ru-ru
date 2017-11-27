---
title: "Сравнения NULL"
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
ms.assetid: ef88af8c-8dfe-4556-8b56-81df960a900b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: fefbd3894063c0298a7ad5110ed6867408869107
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="null-comparisons"></a>Сравнения NULL
Значение `null` в источнике данных указывает на то, что это значение неизвестно. В запросах [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] можно реализовать проверку наличия значений NULL так, чтобы определенные вычисления или сравнения выполнялись только для строк с допустимыми данными, не содержащими значений NULL. Впрочем, null-семантика среды CLR может отличаться от null-семантики источника данных. В большинстве баз данных для выполнения сравнений со значением Null используется трехзначная логика. То есть сравнения со значением null не вычисляется `true` или `false`, результат вычисления равен `unknown`. Часто речь идет о реализациях Null ANSI, но так бывает не всегда.  
  
 По умолчанию в SQL Server сравнение «Null равняется Null» возвращает значение Null. В следующем примере строки, где параметр `ShipDate` имеет значение NULL, исключаются из результирующего набора, и инструкция [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] возвращает 0 строк.  
  
```  
-- Find order details and orders with no ship date.  
SELECT h.SalesOrderID  
FROM Sales.SalesOrderHeader h  
JOIN Sales.SalesOrderDetail o ON o.SalesOrderID = h.SalesOrderID  
WHERE h.ShipDate IS Null  
```  
  
 Это совсем не похоже на Null-семантику среды CRL, где сравнение «Null равняется Null» возвращает значение True.  
  
 Следующий запрос LINQ выражается в среде CLR, но выполняется в источнике данных. Гарантии того, что семантика CLR будет действительна для среды источника данных, не существует, поэтому предполагаемое поведение непредсказуемо.  
  
 [!code-csharp[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#joinonnull)]
 [!code-vb[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#joinonnull)]  
  
## <a name="key-selectors"></a>Селекторы ключей  
 Объект *селектора ключа* -функция, используемая в стандартных операторах запросов, извлекающая ключ из элемента. В функции селектора элемента может быть выполнено сравнение выражения с константой. Null-семантика CLR проявляется в тех случаях, когда выражение сравнивается с константой, имеющей значение Null, или когда сравниваются две константы со значениями Null. Null-семантика хранилищ проявляется в тех случаях, когда сравниваются два столбца источника данных со значениями Null. Селекторы ключей входят в состав многих используемых в запросах стандартных операторов группирования и упорядочивания, например <xref:System.Linq.Queryable.GroupBy%2A>, и применяются для выделения ключей, по которым будет осуществляться упорядочение или группирование результатов запроса.  
  
## <a name="null-property-on-a-null-object"></a>Свойство Null объекта Null  
 В [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] свойства объекта Null имеют значения Null. При попытке обратиться к свойству объекта Null в среде CLR пользователь получает исключение <xref:System.NullReferenceException>. Когда в LINQ-запросе задействовано свойство объекта Null, может быть получен несогласованный результат.  
  
 Так, в следующем примере приведение к типу `NewProduct` осуществляется на уровне дерева команд. В результате может получиться так, что свойство `Introduced` будет иметь значение Null. Если определенные в базе данных сравнения со значением Null таковы, что сравнение с <xref:System.DateTime> дает значение True, то соответствующая строка будет включена.  
  
 [!code-csharp[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#castresultsisnull)]
 [!code-vb[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#castresultsisnull)]  
  
## <a name="passing-null-collections-to-aggregate-functions"></a>Передача коллекций значений NULL в статистические функции  
 В [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]при передаче коллекции, которая поддерживает `IQueryable` агрегатной функции, статистические операции выполняются в базе данных. Возможны различия в результатах запроса, который был выполнен в оперативной памяти и запрос, который был выполнен в базе данных. С помощью запроса в памяти если совпадений нет, запрос возвращает ноль. В базе данных тот же самый запрос возвращает `null`. Если `null` агрегатные функции LINQ передается значение, будет вызвано исключение. Чтобы принимать возможные `null` значения, приводите типы и свойства типов, которые получают результаты запроса в типы, допускающие значение NULL.  
  
## <a name="see-also"></a>См. также  
 [Выражения в запросах LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
