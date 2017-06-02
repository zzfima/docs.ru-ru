---
title: "Создание вложенных запросов Entity SQL | Microsoft Docs"
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
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Создание вложенных запросов Entity SQL
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] \- это богатый функциональный язык.  Блоком построения языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)] является выражение.  В отличие от обычного SQL [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не ограничен табличным результирующим набором: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает создание сложных выражений, в которых могут присутствовать литералы, параметры или вложенные выражения.  Значение в выражении может быть параметризованным или состоять из другого выражения.  
  
## Вложенные выражения  
 Вложенное выражение можно разместить в любом месте, где допустим тип возвращаемого им значения.  Например:  
  
```  
-- Returns a hierarchical collection of three elements at top-level.   
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 Вложенный запрос можно разместить в предложении проекции.  Например:  
  
```  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)   
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)   
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] вложенные запросы всегда должны быть заключены в скобки.  
  
```  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 В следующем примере показывается, как правильно вкладывать выражения [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:  [How to: Order the Union of Two Queries](http://msdn.microsoft.com/ru-ru/853c583a-eaba-4400-830d-be974e735313).  
  
## Вложенные запросы в проекции  
 Вложенные запросы в предложении проекции могут быть переведены в запросы декартового произведения на сервере.  На некоторых внутренних серверах, в том числе на серверах SLQ Server, это может привести к чрезмерному разрастанию таблицы TempDB, что может отрицательно сказаться на производительности.  
  
 Ниже приводится пример подобного запроса:  
  
```  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## Упорядочение вложенных запросов  
 Платформа Entity Framework позволяет разместить вложенное выражение в любом месте запроса.  Поскольку Entity SQL обеспечивает большую гибкость в написании запросов, можно создавать запросы, содержащие упорядочивание вложенных запросов.  Однако порядок во вложенном запросе не сохраняется.  
  
```  
-- The following query will order the results by last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## См. также  
 [Общие сведения о языке Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)