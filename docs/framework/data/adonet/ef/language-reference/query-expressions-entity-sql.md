---
title: "Выражения запросов (язык Entity SQL) | Microsoft Docs"
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
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Выражения запросов (язык Entity SQL)
Выражение запроса объединяет в едином синтаксисе множество разных операторов запросов.  В языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] предусмотрены различные типы выражений, в том числе: [литералы](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md), [параметры](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md), [переменные](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md), операторы, [функции](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md), операторы работы с наборами и т. д.  Для получения дополнительной информации см. [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md).  
  
## Предложения  
 Выражение запроса состоит из предложений, которые последовательно применяют операции к набору объектов.  Они основаны на тех же предложениях, которые можно найти в стандартной инструкции SELECT языка SQL: [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md), [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [WHERE](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md) и [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md).  
  
## Область  
 Имена, определенные в предложении FROM, появляются в области FROM в порядке перечисления, слева направо.  В списке JOIN выражения могут ссылаться на имена, которые определены в списке ранее.  Открытые свойства элементов, указанные в предложении FROM, не добавляются в область FROM. На них всегда следует ссылаться через имя с псевдонимом.  Но обычно все части выражения выбора находятся в области FROM.  
  
## См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)