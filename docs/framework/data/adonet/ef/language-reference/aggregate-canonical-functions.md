---
title: Статистические канонические функции
ms.date: 03/30/2017
ms.assetid: 3bcff826-ca90-41b3-a791-04d6ff0e5085
ms.openlocfilehash: e4772176130fc72a22645462921c90dd5b7967b2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506642"
---
# <a name="aggregate-canonical-functions"></a>Статистические канонические функции

Статистические выражения - выражения, которые уменьшают количество входных значений, например, до одного значения. Статистические выражения обычно используются совместно с предложением группирования GROUP BY выражения SELECT, а на область их использования накладываются ограничения.

## <a name="aggegate-entity-sql-canonical-functions"></a>Канонические функции Aggegate Entity SQL

Ниже приведены статистические канонические функции Entity SQL.

### <a name="avgexpression"></a>Avg(expression)

Возвращает среднее для значений, отличных от NULL.

**Аргументы**

`Int32`, `Int64`, `Double`, И `Decimal`.

**Возвращаемое значение**

Тип `expression`, или `null` Если все входные значения имеют `null` значения.

**Пример**

[!code-csharp[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)] 
[!code-sql[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)]

### <a name="bigcountexpression"></a>BigCount(expression)

Возвращает объем данных, подвергаемых статистической обработке, включая значения NULL и повторяющиеся значения.

**Аргументы**

Любой тип.

**Возвращаемое значение**

Объект `Int64`.

**Пример**

[!code-csharp[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_bigcount)] 
[!code-sql[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_bigcount)]

### <a name="countexpression"></a>Count(expression) 

Возвращает объем данных, подвергаемых статистической обработке, включая значения NULL и повторяющиеся значения.

**Аргументы**

Любой тип.

**Возвращаемое значение**

Объект `Int32`.

**Пример**

[!code-csharp[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_count)]
[!code-sql[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_count)]

### <a name="maxexpression"></a>Max(expression)

Возвращает максимум для значений, отличных от NULL.

**Аргументы**

Значения типа `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.

**Возвращаемое значение**

Тип `expression`, или `null` Если все входные значения имеют `null` значения.

**Пример**

[!code-csharp[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_max)]
[!code-sql[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_max)]

### <a name="minexpression"></a>Min(expression)

Возвращает минимум для значений, отличных от NULL.

**Аргументы**

Значения типа `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.

**Возвращаемое значение**

Тип `expression`, или `null` Если все входные значения имеют `null` значения.

**Пример**

[!code-csharp[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_min)]
[!code-sql[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_min)]

### <a name="stdevexpression"></a>StDev(expression)

Возвращает стандартное отклонение для значений, отличных от NULL.

**Аргументы**

Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.

**Возвращаемое значение**

Объект `Double`. Возвращает `Null`, если все входные значения представляют собой значения `null`.

**Пример**

[!code-csharp[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdev)]
[!code-sql[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdev)]

### <a name="stdevpexpression"></a>StDevP(expression)

Возвращает стандартное отклонение для заполнения по всем значениям.

**Аргументы**

Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.

**Возвращаемое значение**

Объект `Double`, или `null` Если все входные значения имеют `null` значения.

**Пример**

[!code-csharp[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdevp)]
[!code-sql[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdevp)]

### <a name="sumexpression"></a>Sum(expression)

Возвращает сумму для значений, отличных от NULL.

**Аргументы**

Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.

**Возвращаемое значение**

Объект `Double`, или `null` Если все входные значения имеют `null` значения.

**Пример**

[!code-csharp[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_sum)]
[!code-sql[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_sum)]

### <a name="varexpression"></a>Var(expression)

Возвращает дисперсию всех значений, отличных от NULL.

**Аргументы**

Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.

**Возвращаемое значение**

Объект `Double`, или `null` Если все входные значения имеют `null` значения.

**Пример**

[!code-csharp[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_var)]
[!code-sql[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_var)]

### <a name="varpexpression"></a>VarP(expression)

Возвращает дисперсию для заполнения по всем значениям, отличным от NULL.

**Аргументы**

Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.

**Возвращаемое значение**

Объект `Double`, или `null` Если все входные значения имеют `null` значения.

**Пример**

[!code-csharp[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_varp)]
[!code-sql[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_varp)] 

Эквивалентную функциональность предоставляет управляемый поставщик клиента Microsoft SQL. Дополнительные сведения см. в разделе [функции SqlClient для Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).

## <a name="collection-based-aggregates"></a>Статистические функции на основе коллекции

Статистические функции на основе коллекций (функции коллекций) работают с коллекциями и возвращают значение. Например если ORDERS-коллекция всех заказов, можно рассчитать самую раннюю дату отгрузки со следующим выражением:

```sql
min(select value o.ShipDate from LOB.Orders as o)
```

Выражения внутри статистических функций на основе коллекций вычисляются в текущей внешней области разрешения имен.

## <a name="group-based-aggregates"></a>Статистические функции на основе группы

Статистические функции на основе групп вычисляются для группы, определенной предложением GROUP BY. Для каждой группы результата выполняется отдельное статистическое вычисление с использованием элементов каждой группы в качестве входных значений. Если в выражении SELECT используется предложение группирования, в проекции или предложении сортировки могут употребляться только имена выражений группирования, статистические функции или константные выражения.

В следующем примере вычисляется средняя величина заказа для каждого продукта.

```sql
select p, avg(ol.Quantity) from LOB.OrderLines as ol 
  group by ol.Product as p
```

Это может быть статистическое выражение на основе групп без явного предложения группирования в выражении SELECT. В этом случае все элементы обрабатываются как одна группа. Это эквивалентно группированию на основе константы. Например, выражение:

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol
```

Оно эквивалентно следующему выражению:

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol group by 1
```

Выражения внутри статистической функции на основе групп вычисляются в области разрешения имен, видимой для выражения предложения WHERE.

Как и в [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], статистические функции на основе группы можно также указать все или модификатор DISTINCT. Если задан модификатор DISTINCT, то перед вычислением статистической функции из входного набора исключаются повторяющиеся значения. Если задан модификатор ALL (или не указан никакой модификатор), то исключение повторяющихся значений не выполняется.  

## <a name="see-also"></a>См. также

[Канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
