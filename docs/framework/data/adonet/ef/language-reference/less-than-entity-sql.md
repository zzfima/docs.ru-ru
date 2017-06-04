---
title: "&lt; (меньше) (Entity SQL) | Microsoft Docs"
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
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# &lt; (меньше) (Entity SQL)
Сравнивает два выражения, чтобы определить, является ли значение левого выражения меньшим, чем значение правого выражения.  
  
## Синтаксис  
  
```  
  
expression  
<  
expression  
  
```  
  
## Аргументы  
 `expression`  
 Любое допустимое выражение. Оба выражения должны иметь типы данных, допускающих неявное преобразование.  
  
## Типы результата  
 `true`, если значение левого выражения меньше, чем правого; в противном случае \- `false`.  
  
## Пример  
 В следующем запросе Entity SQL оператор \< используется для сравнения двух выражений, чтобы определить, является ли значение левого выражения меньшим, чем правого. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Как выполнить запрос, возвращающий результаты типа StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less)]  
  
## См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)