---
title: "DEREF (Entity SQL) | Microsoft Docs"
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
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# DEREF (Entity SQL)
Разыменовывает значение ссылки и выдает результат разыменования.  
  
## Синтаксис  
  
```  
  
SELECT DEREF ( o.expression) from Table as o;  
```  
  
## Аргументы  
 `expression`  
 Любое допустимое выражение запроса, возвращающее коллекцию.  
  
## Возвращаемое значение  
 Значение сущности, на которую указывает ссылка.  
  
## Заметки  
 Оператор DEREF разыменовывает значение ссылки и выдает результат разыменования. Например, если  `r`  является ссылкой типа ref\<T\>, то выражение  `Deref``(r)`  имеет тип  `T`  и возвращает сущность, на которую ссылается  `r`. Если ссылка имеет значение null или висячее значение \(т. е. цель ссылки не существует\), то результатом оператора DEREF будет значение null.  
  
## Пример  
 В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор DEREF используется для разыменования значения ссылки и возврата результата разыменования. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Как выполнить запрос, возвращающий типы\-примитивы](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Передайте методу ExecutePrimitiveTypeQuery следующий запрос в качестве аргумента.  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)   
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)   
 [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)   
 [Допускающие значения null структурированные типы](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)