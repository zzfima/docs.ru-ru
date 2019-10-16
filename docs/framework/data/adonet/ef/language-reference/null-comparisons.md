---
title: Сравнения NULL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ef88af8c-8dfe-4556-8b56-81df960a900b
ms.openlocfilehash: 8eca2ee1afec5662e40d4f43347c469bd538c066
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319498"
---
# <a name="null-comparisons"></a>Сравнения NULL
Значение `null` в источнике данных указывает на то, что это значение неизвестно. В LINQ to Entitiesных запросах можно проверить значения NULL, чтобы определенные вычисления или сравнения выполнялись только для строк, которые имеют допустимые или не имеющие значения NULL данные. Впрочем, null-семантика среды CLR может отличаться от null-семантики источника данных. В большинстве баз данных для выполнения сравнений со значением Null используется трехзначная логика. Это значит, что сравнение со значением NULL не вычисляется как `true` или `false`, оно вычисляется как `unknown`. Часто речь идет о реализациях Null ANSI, но так бывает не всегда.  
  
 По умолчанию в SQL Server сравнение «Null равняется Null» возвращает значение Null. В следующем примере строки, в которых `ShipDate` имеет значение null, исключаются из результирующего набора, а инструкция Transact-SQL возвращает 0 строк.  
  
```sql  
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
 *Селектор ключа* — это функция, используемая в стандартных операторах запросов для извлечения ключа из элемента. В функции селектора элемента может быть выполнено сравнение выражения с константой. Null-семантика CLR проявляется в тех случаях, когда выражение сравнивается с константой, имеющей значение Null, или когда сравниваются две константы со значениями Null. Null-семантика хранилищ проявляется в тех случаях, когда сравниваются два столбца источника данных со значениями Null. Селекторы ключей входят в состав многих используемых в запросах стандартных операторов группирования и упорядочивания, например <xref:System.Linq.Queryable.GroupBy%2A>, и применяются для выделения ключей, по которым будет осуществляться упорядочение или группирование результатов запроса.  
  
## <a name="null-property-on-a-null-object"></a>Свойство Null объекта Null  
 В Entity Framework свойства объекта null имеют значение null. При попытке обратиться к свойству объекта Null в среде CLR пользователь получает исключение <xref:System.NullReferenceException>. Когда в LINQ-запросе задействовано свойство объекта Null, может быть получен несогласованный результат.  
  
 Так, в следующем примере приведение к типу `NewProduct` осуществляется на уровне дерева команд. В результате может получиться так, что свойство `Introduced` будет иметь значение Null. Если определенные в базе данных сравнения со значением Null таковы, что сравнение с <xref:System.DateTime> дает значение True, то соответствующая строка будет включена.  
  
 [!code-csharp[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#castresultsisnull)]
 [!code-vb[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#castresultsisnull)]  
  
## <a name="passing-null-collections-to-aggregate-functions"></a>Передача коллекций значений NULL в статистические функции  
 В LINQ to Entities при передаче коллекции, которая поддерживает `IQueryable`, в агрегатную функцию, статистические операции выполняются в базе данных. Могут возникнуть различия в результатах запроса, который был выполнен в памяти, и запроса, выполненного в базе данных. Если в запросе в памяти нет совпадений, запрос возвращает ноль. В базе данных тот же самый запрос возвращает `null`. Если в агрегатную функцию LINQ передается значение `null`, возникнет исключение. Чтобы принимать возможные значения `null`, приведите типы и свойства типов, получающих результаты запроса, в типы, допускающие значение null.  
  
## <a name="see-also"></a>См. также

- [Выражения в запросах LINQ to Entities](expressions-in-linq-to-entities-queries.md)
