---
title: SELECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 9a33bd0d-ded1-41e7-ba3c-305502755e3b
ms.openlocfilehash: 3d3564c37d8971d3261cb47acb774bd1b9f92192
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249215"
---
# <a name="select-entity-sql"></a>SELECT (Entity SQL)
Указывает элементы, возвращаемые запросом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
SELECT [ ALL | DISTINCT ] [ topSubclause ] aliasedExpr   
      [{ , aliasedExpr }] FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause ]  
or  
SELECT VALUE [ ALL | DISTINCT ] [ topSubclause ] expr FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause  
```  
  
## <a name="arguments"></a>Аргументы  
 ALL  
 Указывает на то, что в результирующем наборе могут появляться повторяющиеся элементы. ALL является значением по умолчанию.  
  
 DISTINCT  
 Указывает, что в результирующем наборе возвращаются только уникальные результаты.  
  
 VALUE  
 Позволяет указать только один элемент и не добавляет оболочку строк.  
  
 `topSubclause`  
 Любое допустимое выражение, указывающее число первых результатов, возвращаемых запросом, в формате `top(expr)`.  
  
 Параметр LIMIT оператора [ORDER BY](order-by-entity-sql.md) также позволяет выбрать первые n элементов в результирующем наборе.  
  
 `aliasedExpr`  
 Выражение в следующем формате.  
  
 `expr`как `identifier` &#124;`expr`  
  
 `expr`  
 Литерал или выражение.  
  
## <a name="remarks"></a>Примечания  
 Предложение SELECT вычисляется после вычисления предложений [from](from-entity-sql.md), [Group By](group-by-entity-sql.md)и [HAVING](having-entity-sql.md) . В предложении SELECT могут быть указаны только те элементы, которые в настоящий момент находящиеся в области (из предложения FROM, из внешних областей). Если указано предложение GROUP BY, то предложение SELECT может ссылаться только на псевдонимы для ключей GROUP BY. Обращение к элементам предложения FROM допустимо только в агрегатных функциях.  
  
 Список, содержащий одно или более выражений запросов, следующих за ключевым словом SELECT, называется списком выбора, или более формально - проекцией. Наиболее распространенная форма проекции - единственное выражение запроса. Если выбрать элемент `member1` из коллекции `collection1`, то будет подготовлена новая коллекция всех значений `member1` для каждого объекта в `collection1`, как показано в следующем примере.  
  
```  
SELECT collection1.member1 FROM collection1  
```  
  
 Например, если `customers` является коллекцией типа `Customer` со свойством `Name` типа `string`, то выбор `Name` из `customers` даст коллекцию строк, как показано в следующем примере.  
  
```  
SELECT customers.Name FROM customers AS c  
```  
  
 Можно также воспользоваться синтаксисом JOIN (FULL, INNER, LEFT, OUTER, ON и RIGHT). ON требуется для внутренних соединений и недопустим для перекрестных соединений.  
  
## <a name="row-and-value-select-clauses"></a>Предложения выбора строк и значений  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает два варианта предложения SELECT. Первый из них - выбор строк, указывается ключевым словом SELECT и может быть использован для указания одного или нескольких проецируемых значений. Поскольку к возвращенным значениям неявным образом добавляется оболочка строк, то результатом выражения запроса всегда является мультимножество строк.  
  
 Для каждого выражения запроса в выборе строки должен быть указан псевдоним. Если псевдоним не указан, то[!INCLUDE[esql](../../../../../../includes/esql-md.md)] пытается создать его на основе правил создания псевдонимов.  
  
 Другой тип предложения SELECT, выбор значения, идентифицируется ключевым словом SELECT VALUE. Он позволяет указать только одно значение и не добавляет оболочку строк.  
  
 Выбор строк всегда можно выразить в терминах VALUE SELECT, как показано в следующем примере.  
  
```  
SELECT 1 AS a, "abc" AS b FROM C  
SELECT VALUE ROW(1 AS a, "abc" AS b) FROM C   
```  
  
## <a name="all-and-distinct-modifiers"></a>Модификаторы All и Distinct  
 В обоих вариантах предложения SELECT языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)] могут быть указаны модификаторы ALL и DISTINCT. Если задан модификатор DISTINCT, то повторяющиеся значения исключаются из коллекции, полученной в результате выполнения выражения запроса (до предложения SELECT включительно). Если задан модификатор ALL, то исключение повторяющихся значений не выполняется. ALL является модификатором по умолчанию.  
  
## <a name="differences-from-transact-sql"></a>Отличия от языка Transact-SQL  
 В отличие от Transact-SQL, язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не поддерживает использование аргумента «*» в предложении SELECT.  Вместо этого в языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] запросы могут проецировать целые записи, ссылаясь на псевдонимы коллекций из предложения FROM, как показано в следующем примере.  
  
```  
SELECT * FROM T1, T2  
```  
  
 Предыдущее выражение запроса Transact-SQL выражается [!INCLUDE[esql](../../../../../../includes/esql-md.md)] следующим образом.  
  
```  
SELECT a1, a2 FROM T1 AS a1, T2 AS a2  
```  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL оператор SELECT используется для задания элементов, возвращаемых запросом. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру, описанную в [разделе инструкции. Выполнение запроса, возвращающего Структуралтипе](../how-to-execute-a-query-that-returns-structuraltype-results.md)результаты.  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less)]  
  
## <a name="see-also"></a>См. также

- [Выражения запросов](query-expressions-entity-sql.md)
- [Справочник по Entity SQL](entity-sql-reference.md)
- [TOP](top-entity-sql.md)
