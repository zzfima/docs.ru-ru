---
title: "|| (ИЛИ) (Entity SQL) | Microsoft Docs"
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
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# || (ИЛИ) (Entity SQL)
Объединяет два выражения типа `Boolean`.  
  
## Синтаксис  
  
```  
  
          boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## Аргументы  
 `boolean_expression`  
 Любое допустимое выражение, возвращающее значение типа `Boolean`.  
  
## Возвращаемое значение  
 `true`, если любое из условий есть `true`; в противном случае `false`.  
  
## Заметки  
 OR \- это логический оператор [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Он используется только для объединения двух условий. Если в инструкции используется более одного логического оператора, операторы OR вычисляются после операторов AND. Однако порядок выполнения можно изменить с помощью скобок.  
  
 Двойная вертикальная черта \(&#124;&#124;\) имеет ту же функциональность, что и оператор OR.  
  
 В следующей таблице указаны возможные входные значения и возвращаемые типы.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|TRUE|TRUE|TRUE|  
|`FALSE`|TRUE|FALSE|NULL|  
|`NULL`|TRUE|NULL|NULL|  
  
## Пример  
 Следующий запрос Entity SQL использует оператор OR, чтобы объединить два выражения типа `Boolean`. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Как выполнить запрос, возвращающий результаты типа StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)