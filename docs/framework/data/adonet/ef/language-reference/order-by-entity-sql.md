---
title: ORDER BY (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0b61572-ecee-41eb-9d7f-74132ec8a26c
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4321c5fd3f173b209d99e096ec0ebf8788437c3d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="order-by-entity-sql"></a>ORDER BY (Entity SQL)
Указывает порядок сортировки для объектов, возвращаемых инструкцией SELECT.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ ORDER BY   
   {  
      order_by_expression [SKIP n] [LIMIT n]  
      [ COLLATE collation_name ]  
      [ ASC | DESC ]  
   }  
   [ ,…n ]   
]  
```  
  
## <a name="arguments"></a>Аргументы  
 `order_by_expression`  
 Любое допустимое выражение запроса, задающее свойство, по которому выполняется сортировка. Может быть указано несколько выражений сортировки. Последовательность выражений сортировки в предложении ORDER BY определяет порядок сортировки результирующего набора.  
  
 COLLATE {collation_name}  
 Указывает, что операция ORDER BY должна выполняться в соответствии с параметрами сортировки, заданными в аргументе `collation_name`. COLLATE применяется только для строковых выражений.  
  
 ASC  
 Указывает, что значения в указанном свойстве должны быть отсортированы в порядке возрастания, от меньшего к большему. Это значение по умолчанию.  
  
 DESC  
 Указывает, что значения в указанном свойстве должны быть отсортированы в порядке убывания, от большего к меньшему.  
  
 LIMIT `n`  
 Будут выбраны только первые `n` элементов.  
  
 SKIP `n`  
 Пропускает первые `n` элементов.  
  
## <a name="remarks"></a>Примечания  
 Предложение ORDER BY логически применяется к результату предложения SELECT. Предложение ORDER BY может ссылаться на элементы списка выбора по их псевдонимам. Предложение ORDER BY может также ссылаться на другие переменные, находящиеся в области видимости. Однако если предложение SELECT указано с модификатором DISTINCT, то предложение ORDER BY может ссылаться только на псевдонимы из предложения SELECT.  
  
 `SELECT c AS c1 FROM cs AS c ORDER BY c1.e1, c.e2`  
  
 Выражения в предложении ORDER BY должны иметь сравнимый тип, поскольку для упорядочивания производится сравнение элементов (меньше, больше и т. д.). Такими типами обычно являются скалярные примитивы - числа, строки и даты. Типы RowType для сравнимых типов также являются сравнимыми для упорядочивания.  
  
 Если код проходит по упорядоченному набору, отличному от проекции верхнего уровня, то сохранение порядка в выходных данных не гарантируется.  
  
```  
-- In the following sample, order is guaranteed to be preserved:  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
 Получить упорядоченный результат выполнения операции UNION, UNION ALL, EXCEPT или INTERSECT можно следующим образом.  
  
```  
SELECT ...  
FROM ( UNION/EXCEPT/INTERSECT operation )  
ORDER BY ...  
```  
  
## <a name="restricted-keywords"></a>Служебные ключевые слова  
 Следующие ключевые слова при использовании в предложении `ORDER BY` необходимо заключать в кавычки.  
  
-   CROSS  
  
-   FULL  
  
-   KEY  
  
-   LEFT  
  
-   ORDER  
  
-   OUTER  
  
-   RIGHT  
  
-   ROW  
  
-   VALUE  
  
## <a name="ordering-nested-queries"></a>Упорядочение вложенных запросов  
 Платформа Entity Framework позволяет разместить вложенное выражение в любом месте запроса. Порядок вложенного запроса не сохраняется.  
  
```  
-- The following query will order the results by the last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="example"></a>Пример  
 В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор ORDER BY задает порядок сортировки для объектов, возвращаемых инструкцией SELECT. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#ORDERBY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#orderby)]  
  
## <a name="see-also"></a>См. также  
 [Выражения запросов](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
 [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
 [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
