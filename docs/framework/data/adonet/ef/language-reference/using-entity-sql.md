---
title: "USING (Entity SQL) | Microsoft Docs"
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
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# USING (Entity SQL)
Задает пространства имен, используемые в выражении запроса.  
  
## Синтаксис  
  
```  
USING [ alias = ] namespace  
```  
  
## Аргументы  
 `alias`  
 Задает более короткий псевдоним, с помощью которого можно уточнить применяемое пространство имен.  
  
 `namespace`  
 Любое допустимое пространство имен.  
  
## Пример  
 В следующем запросе Entity SQL используется оператор USING для задания пространства имен, используемого в выражении запроса.  Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Следуйте инструкциям в разделе [Как выполнить запрос, возвращающий типы\-примитивы](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery`:  
  
```  
using SqlServer; RAND()  
```  
  
## См. также  
 [Пространства имен](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)   
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)