---
title: Составление вложенных запросов Entity SQL
ms.date: 03/30/2017
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
ms.openlocfilehash: 0ab92c1e41c89f141c3cbd37be3e1e18e64d9666
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833913"
---
# <a name="composing-nested-entity-sql-queries"></a>Составление вложенных запросов Entity SQL
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] - это богатый функциональный язык. Стандартный блок [!INCLUDE[esql](../../../../../../includes/esql-md.md)] является выражением. В отличие от обычного SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не ограничивается табличным результирующим набором: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает составление сложных выражений, которые могут иметь литералы, параметры или вложенные выражения. Значение в выражении может быть параметризовано или состоять из другого выражения.  
  
## <a name="nested-expressions"></a>Вложенные выражения  
 Вложенное выражение можно разместить в любом месте, где допустим тип возвращаемого им значения. Пример:  
  
```sql  
-- Returns a hierarchical collection of three elements at top-level.   
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 Вложенный запрос можно разместить в предложении проекции. Пример:  
  
```sql  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)   
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)   
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] вложенные запросы всегда должны быть заключены в скобки.  
  
```sql  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 В следующем примере показывается, как правильно вкладывать выражения [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [Как Закажите объединение двух запросов @ no__t-0.  
  
## <a name="nested-queries-in-projection"></a>Вложенные запросы в проекции  
 Вложенные запросы в предложении проекции могут быть переведены в запросы декартового произведения на сервере. На некоторых внутренних серверах, в том числе на серверах SLQ Server, это может привести к чрезмерному разрастанию таблицы TempDB, что может отрицательно сказаться на производительности.  
  
 Ниже приводится пример подобного запроса:  
  
```sql  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a>Упорядочение вложенных запросов  
 Платформа Entity Framework позволяет разместить вложенное выражение в любом месте запроса. Поскольку Entity SQL обеспечивает большую гибкость в написании запросов, можно создавать запросы, содержащие упорядочивание вложенных запросов. Однако порядок во вложенном запросе не сохраняется.  
  
```sql  
-- The following query will order the results by last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```sql  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="see-also"></a>См. также

- [Общие сведения об Entity SQL](entity-sql-overview.md)
