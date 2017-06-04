---
title: "Не поддерживаемые выражения (Entity SQL) | Microsoft Docs"
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
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Не поддерживаемые выражения (Entity SQL)
В этом разделе описываются выражения [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], не поддерживаемые в [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Дополнительные сведения см. в разделе [Отличия Entity SQL и Transact\-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).  
  
## Предикаты с кванторами  
 Язык [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] допускает присутствие следующих конструкций:  
  
```  
sal > all (select salary from employees)  
sal > any (select salary from employees)  
```  
  
 Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] такие конструкции не поддерживает.  Эквивалентные выражения могут быть написаны на языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] следующим образом:  
  
```  
not exists(select 0 from employees as e where sal > e.salary)  
exists(select 0 from employees as e where sal > e.salary)  
```  
  
## Оператор \*  
 В [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] поддерживается использование оператора \* в предложении SELECT, чтобы указать, что необходимо вернуть все столбцы.  В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] это не поддерживается.  
  
## См. также  
 [Общие сведения о языке Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)   
 [Отличия Entity SQL и Transact\-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)