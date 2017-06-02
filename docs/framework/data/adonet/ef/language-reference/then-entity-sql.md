---
title: "THEN (Entity SQL) | Microsoft Docs"
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
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# THEN (Entity SQL)
Результат предложения WHEN, если оно оценивается как значение `true`.  
  
## Синтаксис  
  
```  
  
WHEN when_expression THEN then_expression  
```  
  
## Аргументы  
 `when_expression`  
 Любое допустимое выражение типа Boolean.  
  
 `then_expression`  
 Любое допустимое выражение запроса, возвращающее коллекцию.  
  
## Заметки  
 Если аргумент `when_expression` оценивается как значение `true`, результатом является соответствующее значение `then-expression`. Если не выполнено ни одно из условий предложения WHEN, оценивается выражение `else-expression`. Однако, если выражение `else-expression` отсутствует, результат равен NULL.  
  
 Пример см. в разделе [CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md).  
  
## Пример  
 В следующем запросе Entity SQL с помощью выражения CASE оценивается набор выражений типа `Boolean`. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Как выполнить запрос, возвращающий типы\-примитивы](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## См. также  
 [CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)   
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)