---
title: Статистические канонические функции
ms.date: 03/30/2017
ms.assetid: 3bcff826-ca90-41b3-a791-04d6ff0e5085
ms.openlocfilehash: 04b7d9c20373a465c073d55a090f1c2fd7fc6e07
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761939"
---
# <a name="aggregate-canonical-functions"></a>Статистические канонические функции

Статистические выражения - выражения, которые уменьшают количество входных значений, например, до одного значения. Статистические выражения обычно используются совместно с предложением группирования GROUP BY выражения SELECT, а на область их использования накладываются ограничения.

В следующей таблице приведены канонические статистические функции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)].

| Функция | Описание |
| -------- | ----------- |
| `Avg(expression)` | Возвращает среднее для значений, отличных от NULL.<br><br>**Аргументы**<br><br>`Int32`, `Int64`, `Double`, И `Decimal`.<br><br>**Возвращаемое значение**<br><br>Тип параметра `expression`. Возвращает `Null`, если все входные значения представляют собой значения `null`.<br><br>**Пример**[!code-csharp[DP EntityServices Concepts#EDM_AVG](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)] [!code-sql[DP EntityServices Concepts#EDM_AVG](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)] |
| `BigCount(expression)` | Возвращает объем данных, подвергаемых статистической обработке, включая значения NULL и повторяющиеся значения.<br><br>**Аргументы**<br><br>Любой тип.<br><br>**Возвращаемое значение**<br><br>Объект `Int64`.<br><br>**Пример**[!code-csharp[DP EntityServices Concepts#EDM_BIGCOUNT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_bigcount)] [!code-sql[DP EntityServices Concepts#EDM_BIGCOUNT](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_bigcount)] |
| `Count(expression)` | Возвращает объем данных, подвергаемых статистической обработке, включая значения NULL и повторяющиеся значения.<br><br>**Аргументы**<br><br>Любой тип.<br><br>**Возвращаемое значение**<br><br>Объект `Int32`.<br><br>**Пример**[!code-csharp[DP EntityServices Concepts#EDM_COUNT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_count)] [!code-sql[DP EntityServices Concepts#EDM_COUNT](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_count)] |
| `Max(expression)` | Возвращает максимум для значений, отличных от NULL.<br><br>**Аргументы**<br><br>Значения типа `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.<br><br>**Возвращаемое значение**<br><br>Тип параметра `expression`. Возвращает `Null`, если все входные значения представляют собой значения `null`.<br><br>**Пример**[!code-csharp[DP EntityServices Concepts#EDM_MAX](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_max)] [!code-sql[DP EntityServices Concepts#EDM_MAX](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_max)] |
| `Min(expression)` | Возвращает минимум для значений, отличных от NULL.<br><br>**Аргументы**<br><br>Значения типа `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.<br><br>**Возвращаемое значение**<br><br>Тип параметра `expression`. Возвращает `Null`, если все входные значения представляют собой значения `null`.<br><br>**Пример**[!code-csharp[DP EntityServices Concepts#EDM_MIN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_min)] [!code-sql[DP EntityServices Concepts#EDM_MIN](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_min)] |
| `StDev(expression)` | Возвращает стандартное отклонение для значений, отличных от NULL.<br><br>**Аргументы**<br><br>Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.<br><br>**Возвращаемое значение**<br><br>Объект `Double`. Возвращает `Null`, если все входные значения представляют собой значения `null`.<br><br>**Пример**[!code-csharp[DP EntityServices Concepts#EDM_STDEV](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdev)] [!code-sql[DP EntityServices Concepts#EDM_STDEV](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdev)] |
| `StDevP(expression)` | Возвращает стандартное отклонение для заполнения по всем значениям.<br><br>**Аргументы**<br><br>Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.<br><br>**Возвращаемое значение**<br><br>Объект `Double`. Возвращает `Null`, если все входные значения представляют собой значения `null`.<br><br>**Пример**[!code-csharp[DP EntityServices Concepts#EDM_STDEVP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdevp)] [!code-sql[DP EntityServices Concepts#EDM_STDEVP](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdevp)] |
| `Sum(expression)` | Возвращает сумму для значений, отличных от NULL.<br><br>**Аргументы**<br><br>Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.<br><br>**Возвращаемое значение**<br><br>Объект `Double`. Возвращает `Null`, если все входные значения представляют собой значения `null`.<br><br>**Пример**[!code-csharp[DP EntityServices Concepts#EDM_SUM](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_sum)] [!code-sql[DP EntityServices Concepts#EDM_SUM](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_sum)] |
| `Var(expression)` | Возвращает дисперсию всех значений, отличных от NULL.<br><br>**Аргументы**<br><br>Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.<br><br>**Возвращаемое значение**<br><br>Объект `Double`. Возвращает `Null`, если все входные значения представляют собой значения `null`.<br><br>**Пример**[!code-csharp[DP EntityServices Concepts#EDM_VAR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_var)] [!code-sql[DP EntityServices Concepts#EDM_VAR](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_var)] |
| `VarP(expression)` | Возвращает дисперсию для заполнения по всем значениям, отличным от NULL.<br><br>**Аргументы**<br><br>Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.<br><br>**Возвращаемое значение**<br><br>Объект `Double`. Возвращает `Null`, если все входные значения представляют собой значения `null`.<br><br>**Пример**[!code-csharp[DP EntityServices Concepts#EDM_VARP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_varp)] [!code-sql[DP EntityServices Concepts#EDM_VARP](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_varp)] |

Эквивалентную функциональность предоставляет управляемый поставщик клиента Microsoft SQL. Дополнительные сведения см. в разделе [функции SqlClient для Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).

## <a name="collection-based-aggregates"></a>Статистические функции на основе коллекций

Статистические функции на основе коллекций (функции коллекций) работают с коллекциями и возвращают значение. Например, если ORDERS-коллекция всех заказов, можно рассчитать самую раннюю дату отгрузки с использованием следующего выражения:

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

Это могут быть статистическое выражение на базе групп без явного предложения группирования в выражении SELECT. В этом случае все элементы обрабатываются как одна группа. Это эквивалентно группированию на основе константы. Например, выражение:

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol
```

Оно эквивалентно следующему выражению:

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol group by 1
```

Выражения внутри статистической функции на основе групп вычисляются в области разрешения имен, видимой для выражения предложения WHERE.

Как и в [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], статистические функции на основе группы можно также указать ALL или модификатор DISTINCT. Если задан модификатор DISTINCT, то перед вычислением статистической функции из входного набора исключаются повторяющиеся значения. Если задан модификатор ALL (или не указан никакой модификатор), то исключение повторяющихся значений не выполняется.  

## <a name="see-also"></a>См. также

[Канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
