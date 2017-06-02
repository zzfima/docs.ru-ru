---
title: "MULTISET (Entity SQL) | Microsoft Docs"
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
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# MULTISET (Entity SQL)
Создает экземпляр мультинабора из списка значений. Все значения конструктора MULTISET должны принадлежать совместимому типу  `T`. Применение пустых конструкторов мультинаборов не допускается.  
  
## Синтаксис  
  
```  
  
MULTISET (expression [{, expression }] )  
or  
{ expression [{, expression }] }  
```  
  
## Аргументы  
 `expression`  
 Любой допустимый список значений.  
  
## Возвращаемое значение  
 Коллекция типа MULTISET\<T\>.  
  
## Заметки  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] предоставляет три типа конструкторов: конструкторы строк, конструкторы объектов и конструкторы мультинаборов \(или коллекций\). Для получения дополнительной информации см. [Сборка типов](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).  
  
 Конструктор мультинаборов создает экземпляр мультинабора из списка значений. Все значения конструктора MULTISET должны принадлежать совместимому типу.  
  
 Например, следующее выражение создает мультинабор целых чисел.  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
>  Вложенные литералы мультинаборов поддерживаются лишь в тех случаях, когда мультинабор\-упаковщик имеет лишь один элемент мультинабора, например `{{1, 2, 3}}`. Когда же мультинабор\-упаковщик имеет несколько элементов мультинабора \(например, `{{1, 2}, {3, 4}}`\), вложенные литералы мультинаборов не поддерживаются.  
  
## Пример  
 В следующем запросе Entity SQL оператор MULTISET используется для создания экземпляра мультинабора из списка значений. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Как выполнить запрос, возвращающий результаты типа StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTISET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiset)]  
  
## См. также  
 [Сборка типов](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)   
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)