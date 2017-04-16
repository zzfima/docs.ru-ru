---
title: "GROUPPARTITION (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# GROUPPARTITION (Entity SQL)
Возвращает коллекцию значений аргумента, проекция которых получена из текущей секции группы, с которой связано статистическое выражение. Агрегат `GroupPartition` основан на группе и не имеет формы, основанной на коллекции.  
  
## Синтаксис  
  
```  
  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## Аргументы  
 `expression`  
 Произвольное выражение [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## Заметки  
 Следующий запрос возвращает список продуктов и коллекцию количеств в строках заказа для каждого продукта:  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 Следующие два запроса семантически эквивалентны.  
  
```  
select p, Sum(GroupPartition(ol.Quantity)) from LOB.OrderLines as ol  
  group by ol.Product as p  
select p, Sum(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 Оператор `GROUPPARTITION` может использоваться вместе с определяемыми пользователем агрегатная функциями.  
  
 Оператор `GROUPPARTITION` является специальным агрегатным оператором, который хранит ссылку на сгруппированный входной набор. Эта ссылка может использоваться в любом месте запроса, где в области находится предложение GROUP BY. Например:  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 При использовании обычного предложения GROUP BY результаты группирования скрыты. Эти результаты можно использовать только в агрегатной функции. Чтобы можно было видеть результаты группирования, необходимо сопоставить результаты группирования и входной набор с использованием вложенного запроса. Следующие два запроса эквивалентны.  
  
```  
select p, (select q from GroupPartition(ol.Quantity) as q) from LOB.OrderLines as ol group by ol.Product as p  
select p, (select ol.Quantity as q from LOB.OrderLines as ol2 where ol2.Product = p) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 Как показывает этот пример, применение статистического оператора GROUPPARTITION позволяет упростить получение ссылки на входной набор после группирования.  
  
 В операторе GROUPPARTITION на входе может указываться любое выражение [!INCLUDE[esql](../../../../../../includes/esql-md.md)], если используется параметр `expression`.  
  
 Например, все следующие входные выражения для секции группы являются допустимыми:  
  
```  
select groupkey, GroupPartition(b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(1) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(a + b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({a + b}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({42}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(b > a) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
```  
  
## Пример  
 В следующем примере показано, как использовать предложение GROUPPARTITION с предложением GROUP BY. Предложение GROUP BY группирует сущности `SalesOrderHeader` по их значениям `Contact`. Затем предложение GROUPPARTITION находит проекцию свойства `TotalDue` для каждой группы, что приводит к получению коллекции десятичных чисел.  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]