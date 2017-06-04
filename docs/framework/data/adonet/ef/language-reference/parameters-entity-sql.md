---
title: "Параметры (Entity SQL) | Microsoft Docs"
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
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Параметры (Entity SQL)
Параметры \- это переменные, определенные вне [!INCLUDE[esql](../../../../../../includes/esql-md.md)] обычно через привязку API, используемую базовым языком.  Каждый параметр имеет имя и тип.  Имена параметров определены в выражениях запросов с символом \(@\) в качестве префикса. Этим они отличаются от имен свойств или других имен, определенных в запросе.  
  
 API\-привязки базового языка предоставляет API для параметров привязки.  
  
## Пример  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Общие сведения о языке Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)