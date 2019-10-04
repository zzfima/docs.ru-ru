---
title: GROUPPARTITION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
ms.openlocfilehash: 19df566c254a3f3202eb3554ab43ee0d7c944181
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833752"
---
# <a name="grouppartition-entity-sql"></a>GROUPPARTITION (Entity SQL)
Возвращает коллекцию значений аргумента, проекция которых получена из текущей секции группы, с которой связано статистическое выражение. Агрегат `GroupPartition` основан на группе и не имеет формы, основанной на коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Произвольное выражение [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .  
  
## <a name="remarks"></a>Примечания  
 Следующий запрос возвращает список продуктов и коллекцию количеств в строках заказа для каждого продукта:  
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
```  
  
 Следующие два запроса семантически эквивалентны.  
  
```sql  
SELECT p, Sum(GroupPartition(ol.Quantity)) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
SELET p, Sum(ol.Quantity) FROM LOB.OrderLines AS ol
  group by ol.Product as p  
```  
  
 Оператор `GROUPPARTITION` может использоваться вместе с определяемыми пользователем агрегатная функциями.  
  
Оператор`GROUPPARTITION` является специальным агрегатным оператором, который хранит ссылку на сгруппированный входной набор. Эта ссылка может использоваться в любом месте запроса, где в области находится предложение GROUP BY. Пример:
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 При обычной `GROUP BY` результаты группирования скрываются. Эти результаты можно использовать только в агрегатной функции. Чтобы можно было видеть результаты группирования, необходимо сопоставить результаты группирования и входной набор с использованием вложенного запроса. Следующие два запроса эквивалентны.  
  
```sql  
SELET p, (SELECT q FROM GroupPartition(ol.Quantity) AS q) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
SELECT p, (SELECT ol.Quantity AS q FROM LOB.OrderLines AS ol2 WHERE ol2.Product = p) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 Как показывает этот пример, применение статистического оператора GROUPPARTITION позволяет упростить получение ссылки на входной набор после группирования.  
  
 В операторе GROUPPARTITION на входе может указываться любое выражение [!INCLUDE[esql](../../../../../../includes/esql-md.md)] , если используется параметр `expression` .  
  
 Например, все следующие входные выражения для секции группы являются допустимыми:  
  
```sql  
SELECT groupkey, GroupPartition(b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(1) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(a + b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition({a + b}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition({42}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition(b > a) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать предложение GROUPPARTITION с предложением GROUP BY. Предложение GROUP BY группирует сущности `SalesOrderHeader` по их значениям `Contact`. Затем предложение GROUPPARTITION находит проекцию свойства `TotalDue` для каждой группы, что приводит к получению коллекции десятичных чисел.  
  
 [!code-sql[DP EntityServices Concepts#Collection_GroupPartition](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#collection_grouppartition)]
