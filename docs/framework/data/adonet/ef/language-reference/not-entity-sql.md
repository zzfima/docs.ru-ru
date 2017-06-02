---
title: "! (NOT) (язык Entity SQL) | Microsoft Docs"
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
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# ! (NOT) (язык Entity SQL)
Изменяет значение выражения типа `Boolean` на обратное.  
  
## Синтаксис  
  
```  
  
NOT boolean_expression  
or  
! boolean_expression  
```  
  
## Аргументы  
 `boolean_expression`  
 Любое допустимое выражение, возвращающее значение типа Boolean.  
  
## Заметки  
 Восклицательный знак \(\!\) имеет ту же функциональность, что и оператор NOT.  
  
## Пример  
 Следующий запрос Entity SQL использует оператор NOT, чтобы изменить на обратное выражение типа `Boolean`. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Как выполнить запрос, возвращающий результаты типа StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not)]  
  
## См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)