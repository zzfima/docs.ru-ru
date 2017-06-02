---
title: "REF (Entity SQL) | Microsoft Docs"
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
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# REF (Entity SQL)
Возвращает ссылку на экземпляр сущности.  
  
## Синтаксис  
  
```  
  
REF( expression )   
```  
  
## Аргументы  
 `expression`  
 Любое допустимое выражение, результатом которого является экземпляр типа сущности.  
  
## Возвращаемое значение  
 Ссылка на указанный экземпляр сущности.  
  
## Заметки  
 Ссылка на сущность состоит из ключа сущности и имени набора сущности. На одном и том же типе сущности могут быть основаны разные наборы сущностей, поэтому какой\-то конкретный ключ сущности может появляться в нескольких наборах сущностей. Но ссылка на сущность всегда является уникальной. Если входное выражение представляет сохраняемую сущность, то будет возвращена ссылка на эту сущность. Если входное выражение не является сохраняемой сущностью, то возвращается ссылка null.  
  
 Если оператор извлечения свойства \(.\) используется для доступа к свойству сущности, то ссылка автоматически разыменовывается.  
  
## Пример  
 В следующем запросе Entity SQL используется оператор REF в целях получения ссылки для входного аргумента сущности. Тот же запрос разыменовывает ссылку, так как используется оператор извлечения свойства \(.\) для доступа к свойству сущности Product. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Как выполнить запрос, возвращающий типы\-примитивы](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#REF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref)]  
  
## См. также  
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)   
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)   
 [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)   
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Определения типов](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)