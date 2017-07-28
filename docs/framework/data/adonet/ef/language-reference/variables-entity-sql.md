---
title: "Переменные (Entity SQL) | Microsoft Docs"
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
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Переменные (Entity SQL)
## Переменная  
 Выражение переменной – это ссылка на именованное выражение, определенное в текущей области.  Ссылка на переменную должна представлять собой допустимый идентификатор [!INCLUDE[esql](../../../../../../includes/esql-md.md)], как это определено в [Идентификаторы](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).  
  
 В следующем примере показано применение переменной в выражении.  Символ `c` в предложении FROM является определением переменной.  Использование символа `c` в предложении SELECT представляет ссылку на переменную.  
  
```  
select c   
from LOB.customers as c  
```  
  
## См. также  
 [Идентификаторы](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)   
 [Параметры](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)   
 [Общие сведения о языке Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)