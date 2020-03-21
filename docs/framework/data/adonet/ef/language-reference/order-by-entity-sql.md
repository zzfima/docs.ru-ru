---
title: ORDER BY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c0b61572-ecee-41eb-9d7f-74132ec8a26c
ms.openlocfilehash: 1233971b172079aa48227d0ec520068afbdf0952
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150073"
---
# <a name="order-by-entity-sql"></a>ORDER BY (Entity SQL)
Указывает порядок сортировки для объектов, возвращаемых инструкцией SELECT.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
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
  
## <a name="remarks"></a>Remarks  
 Предложение ORDER BY логически применяется к результату предложения SELECT. Предложение ORDER BY может ссылаться на элементы списка выбора по их псевдонимам. Предложение ORDER BY может также ссылаться на другие переменные, находящиеся в области видимости. Однако если предложение SELECT указано с модификатором DISTINCT, то предложение ORDER BY может ссылаться только на псевдонимы из предложения SELECT.  
  
 `SELECT c AS c1 FROM cs AS c ORDER BY c1.e1, c.e2`  
  
 Выражения в предложении ORDER BY должны иметь сравнимый тип, поскольку для упорядочивания производится сравнение элементов (меньше, больше и т. д.). Такими типами обычно являются скалярные примитивы - числа, строки и даты. Типы RowType для сравнимых типов также являются сравнимыми для упорядочивания.  
  
 Если код проходит по упорядоченному набору, отличному от проекции верхнего уровня, то сохранение порядка в выходных данных не гарантируется.  

В следующем примере заказ гарантированно сохраняется:

```sql  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  

В следующем запросе заказ вложенного запроса игнорируется:  

```sql  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
 Получить упорядоченный результат выполнения операции UNION, UNION ALL, EXCEPT или INTERSECT можно следующим образом.  
  
```sql  
SELECT ...  
FROM ( UNION/EXCEPT/INTERSECT operation )  
ORDER BY ...  
```  
  
## <a name="restricted-keywords"></a>Служебные ключевые слова  
 Следующие ключевые слова при использовании в предложении `ORDER BY` необходимо заключать в кавычки.  
  
- CROSS  
  
- FULL  
  
- KEY  
  
- LEFT  
  
- ORDER  
  
- OUTER  
  
- RIGHT  
  
- ROW  
  
- Значение  
  
## <a name="ordering-nested-queries"></a>Упорядочение вложенных запросов  
 Платформа Entity Framework позволяет разместить вложенное выражение в любом месте запроса. Порядок вложенного запроса не сохраняется.  

Следующий запрос закажет результаты по фамилии:  

```sql  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  

В следующем запросе заказ вложенного запроса игнорируется:  

```sql  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="example"></a>Пример  
 В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор ORDER BY задает порядок сортировки для объектов, возвращаемых инструкцией SELECT. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#ORDERBY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#orderby)]  
  
## <a name="see-also"></a>См. также раздел

- [Выражения запросов](query-expressions-entity-sql.md)
- [Справочник по Entity SQL](entity-sql-reference.md)
- [Пропустить](skip-entity-sql.md)
- [Предел](limit-entity-sql.md)
- [Вверх](top-entity-sql.md)
