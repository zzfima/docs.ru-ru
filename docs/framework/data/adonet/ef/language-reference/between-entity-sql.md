---
title: "BETWEEN (Entity SQL) | Microsoft Docs"
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
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# BETWEEN (Entity SQL)
Определяет, находится ли значение выражения в указанном диапазоне. Выражение [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN имеет ту же функциональность, что и выражение Transact\-SQL BETWEEN.  
  
## Синтаксис  
  
```  
  
expression [ NOT ] BETWEEN begin_expression AND end_expression  
```  
  
## Аргументы  
 `expression`  
 Любое допустимое выражение для проверки на принадлежность диапазону в пределах от `begin_expression` до `end_expression`. Аргумент `expression` должен быть того же типа данных, что и аргументы `begin_expression` и `end_expression`.  
  
 `begin_expression`  
 Любое допустимое выражение. Аргумент `begin_expression` должен быть того же типа данных, что и аргументы `expression` и `end_expression`. Значение `begin_expression` должно быть меньше `end_expression`, иначе возвращаемое значение будет инвертировано.  
  
 `end_expression`  
 Любое допустимое выражение. Аргумент `end_expression` должен быть того же типа данных, что и аргументы `expression` и `begin_expression`.  
  
 NOT  
 Указывает, что результат оператора BETWEEN должен быть инвертирован.  
  
 AND  
 Играет роль местозаполнителя и указывает на то, что значение выражения `expression` должно находиться в пределах заданных значений аргументов `begin_expression` и `end_expression`.  
  
## Возвращаемое значение  
 Значение `true`, если аргумент `expression` находится в диапазоне между `begin_expression` и `end_expression`; в противном случае \- значение `false`. Возвращает `null`, если `expression` равно `null` или если `begin_expression` или `end_expression` равно `null`.  
  
## Заметки  
 Чтобы указать диапазон, исключая границы, вместо оператора BETWEEN используйте операторы "больше" \(\>\) и "меньше" \(\<\).  
  
## Пример  
 В следующем запросе Entity SQL оператор BETWEEN определяет, входит ли значение выражения в указанный диапазон. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Как выполнить запрос, возвращающий результаты типа StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)