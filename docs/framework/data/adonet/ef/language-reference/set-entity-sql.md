---
title: "SET (Entity SQL) | Microsoft Docs"
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
  - "ESQL"
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# SET (Entity SQL)
Выражение SET используется для преобразования коллекции объектов в набор путем получения новой коллекции, из которой удалены все повторяющиеся элементы.  
  
## Синтаксис  
  
```  
  
SET (expression)  
```  
  
## Аргументы  
 `expression`  
 Любое допустимое выражение запроса, возвращающее коллекцию.  
  
## Заметки  
 Выражение набора `SET(c)` логически эквивалентно следующей инструкции SELECT:  
  
```  
SELECT VALUE DISTINCT c FROM c  
```  
  
 Оператор `SET` \- это один из операторов работы с наборами в [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо. Сведения о порядке выполнения операторов работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] см. в разделе [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).  
  
## Пример  
 В следующем запросе Entity SQL используется выражение SET для преобразования коллекции объектов в набор. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Как выполнить запрос, возвращающий типы\-примитивы](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#SET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#set)]  
  
## См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)