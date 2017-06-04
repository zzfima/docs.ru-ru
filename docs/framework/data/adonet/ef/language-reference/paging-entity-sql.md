---
title: "Разбивка на страницы (Entity SQL) | Microsoft Docs"
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
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Разбивка на страницы (Entity SQL)
Физическое разбиение на страницы выполняется с помощью вложенных предложений [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) и [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) в предложении [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md).  Для детерминированного физического разбиения на страницы необходимо использовать предложения SKIP и LIMIT.  Если нужно ограничить лишь число строк в результате недетерминированным методом, следует использовать предложение [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md).  Предложения TOP и SKIP\/LIMIT являются взаимоисключающими.  
  
## Общие сведения о предложении TOP  
 Предложение SELECT может иметь необязательное вложенное предложение TOP, которое следует за необязательным модификатором ALL\/DISTINCT.  Предложение TOP указывает, что в результатах запроса возвращается только набор первых строк.  Дополнительные сведения см. в разделе [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md).  
  
## Общие сведения о предложениях SKIP и LIMIT  
 Предложения SKIP и LIMIT являются частью предложения ORDER BY.  Если в предложении ORDER BY имеется вложенное предложение SKIP, результаты будут отсортированы в соответствии со спецификацией сортировки, а результирующий набор будет включать строку или строки, начиная со строки, следующей непосредственно за значением выражения SKIP.  Например, SKIP 5 пропустит первые пять строк и возвратит все, начиная с шестой.  Если в предложении ORDER BY имеется подчиненное выражение LIMIT, результаты запроса будут отсортированы в соответствии со спецификацией сортировки, а количество строк в наборе будет ограничено выражением LIMIT.  Например, LIMIT 5 ограничит результирующий набор пятью экземплярами строк.  Предложения SKIP и LIMIT необязательно использовать вместе: в предложение ORDER BY можно включить только SKIP или только LIMIT.  Дополнительные сведения см. в следующих разделах:  
  
-   [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
  
-   [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
  
-   [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
  
## См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Общие сведения о языке Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)   
 [How to: Page Through Query Results](http://msdn.microsoft.com/ru-ru/ffc0f920-e7de-42e0-9b12-ef356421d030)