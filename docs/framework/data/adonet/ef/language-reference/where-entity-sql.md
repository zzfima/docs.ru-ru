---
title: "WHERE (Entity SQL) | Microsoft Docs"
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
  - "ESQL"
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# WHERE (Entity SQL)
Предложение WHERE применяется непосредственно после предложения [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md).  
  
## Синтаксис  
  
```  
[ WHERE expression ]  
```  
  
## Аргументы  
 `expression`  
 Тип Boolean.  
  
## Заметки  
 Предложение WHERE имеет такую же семантику, которая описана для [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].  Она ограничивает набор объектов, полученный выражением запроса, выбирая из исходной коллекции только те элементы, которые соответствуют условию.  
  
```  
select c from cs as c where e  
```  
  
 Выражение `e` должно иметь тип Boolean.  
  
 Предложение WHERE применяется непосредственно после предложения FROM, до выполнения любого группирования, упорядочения или проекции.  Все имена элементов, определенные в предложении FROM, доступны в выражении предложения WHERE.  
  
## См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Выражения запросов](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)