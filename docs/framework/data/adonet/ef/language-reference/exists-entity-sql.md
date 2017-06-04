---
title: "EXISTS (Entity SQL) | Microsoft Docs"
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
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# EXISTS (Entity SQL)
Определяет, является ли коллекция пустой.  
  
## Синтаксис  
  
```  
  
[NOT] EXISTS (expression)  
```  
  
## Аргументы  
 `expression`  
 Любое допустимое выражение, возвращающее коллекцию.  
  
 NOT  
 Указывает, что результат оператора EXISTS должен быть инвертирован.  
  
## Возвращаемое значение  
 Значение `true`, если коллекция не пуста; в противном случае \- значение `false`.  
  
## Заметки  
 EXISTS \- это один из операторов работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо. Сведения о порядке выполнения операторов работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] см. в статье [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).  
  
## Пример  
 В следующем запросе Entity SQL оператор EXISTS используется, чтобы определить, пуста ли коллекция. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Как выполнить запрос, возвращающий результаты типа StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#EXISTS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#exists)]  
  
## См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)