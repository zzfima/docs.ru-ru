---
title: Математические канонические функции
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: f575785bb198251ef50ba3563e736946253c9526
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760640"
---
# <a name="math-canonical-functions"></a>Математические канонические функции

Язык Entity SQL включает в себя следующие математические канонические функции:
  
## <a name="absvalue"></a>Abs(значение)

Возвращает абсолютное значение `value`.

**Аргументы**

`Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, И `Decimal`.

**Возвращаемое значение**

Тип параметра `value`.

**Пример**

`Abs(-2)`

## <a name="ceilingvalue"></a>Ceiling(value)

Возвращает наименьшее целое число, которое не меньше значения `value`.

**Аргументы**

Объект `Single`, `Double`, и `Decimal`.

**Возвращаемое значение**

Тип параметра `value`.

**Пример**

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a>Floor(value)

Возвращает наибольшее целое число, которое не больше значения `value`.

**Аргументы**

Объект `Single`, `Double`, и `Decimal`.

**Возвращаемое значение**

Тип параметра `value`.

**Пример**

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a>Power(значение, показатель степени)

Возвращает результат для заданного значения `value` по заданному показателю `exponent`.

**Аргументы**

|  |  |
|--|--|
|`value` | `Int32, Int64, Double`, Или `Decimal`. |
|`exponent` | `Int64`, `Double`, Или `Decimal`. |

**Возвращаемое значение**

Тип параметра `value`.

**Пример**

`Power(748.58,2)`

## <a name="roundvalue"></a>Round(value)

Возвращает целую часть `value`, округленную до ближайшего целого значения.

**Аргументы**

Объект `Single`, `Double`, и `Decimal`.

**Возвращаемое значение**

Тип параметра `value`.

**Пример**

`Round(748.58)`

## <a name="roundvalue-digits"></a>Round(значение, количество знаков)

Возвращает значение `value`, округленное до ближайшего указанного знака `digits`.

**Аргументы**

|  |  |
|--|--|
|`value`|`Double` или `Decimal`.|
|`digits`|`Int16` или `Int32`.|

**Возвращаемое значение**

Тип параметра `value`.

**Пример**

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a>Truncate(значение, количество знаков)

Возвращает значение `value`, усеченное до ближайшего указанного знака `digits`.

**Аргументы**

|  |  |
|--|--|
|`value`|`Double` или `Decimal`.|
|`digits`|`Int16` или `Int32`.|

**Возвращаемое значение**

Тип параметра `value`.

**Пример**

`Truncate(748.58,1)`  
  
 Эти функции возвращают `null` при получении на входе `null`.  
  
 Эквивалентную функциональность предоставляет управляемый поставщик клиента Microsoft SQL. Дополнительные сведения см. в разделе [функции SqlClient для Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## <a name="see-also"></a>См. также

- [Канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
