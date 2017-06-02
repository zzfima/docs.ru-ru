---
title: "(Остаток от деления) (Entity SQL) | Microsoft Docs"
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
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# (Остаток от деления) (Entity SQL)
Возвращает остаток от деления значения одного выражения на другое.  
  
## Синтаксис  
  
```  
  
dividend  
%  
divisor  
  
```  
  
## Аргументы  
 `dividend`  
 Делимое числовое выражение.`dividend` \- любое допустимое выражение с любым числовым типом данных.  
  
 `divisor`  
 Числовое выражение, на которое делится делимое.`divisor` \- любое допустимое выражение с любым числовым типом данных.  
  
## Типы результата  
 Edm.Int32  
  
## Пример  
 В следующем запросе Entity SQL используется арифметический оператор % для получения остатка от деления одного выражения на другое. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Как выполнить запрос, возвращающий результаты типа StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)