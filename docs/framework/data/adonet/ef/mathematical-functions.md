---
title: Математические функции
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 4512aaa2eeb3e715a1d6f7a8655912eb15162124
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149769"
---
# <a name="mathematical-functions"></a>Математические функции

Поставщик данных для SQL Server платформы .NET Framework (SqlClient) предоставляет математические функции, производящие вычисления на входящих значениях, предоставляемых в качестве аргументов, и возвращающие результат в виде числовых значений. Эти функции находятся в пространстве имен SqlServer, которое доступно при использовании SqlClient. Свойство пространства имен поставщика позволяет платформе Entity Framework узнать, какой префикс используется поставщиком для конкретных конструкций, таких как типы или функции. В следующей таблице описаны математические функции SqlClient.  
  
## <a name="absexpression"></a>АБС (выражение)

Возвращает абсолютное значение.

**Аргументы**

`expression`: значение типа `Int32`, `Int64`, `Double` или `Decimal`.

**Значение возврата**

Абсолютное значение заданного выражения.

**Пример**

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a>ACOS (выражение)

Возвращает значение арккосинуса указанного выражения.

**Аргументы**

`expression` — значение в формате `Double`.

**Значение возврата**

`Double`.

**Пример**

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a>ASIN (выражение)

Возвращает значение арксинуса указанного выражения.

**Аргументы**

`expression` — значение в формате `Double`.

**Значение возврата**

`Double`.

**Пример**

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a>АТАН (ВЫРАЖЕНИЕ)

Возвращает значение арктангенса указанного числового выражения.

**Аргументы**

`expression` — значение в формате `Double`.

**Значение возврата**

`Double`.

**Пример**

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a>ATN2 (выражение, выражение)

Возвращает угол в радианах, тангенс которого находится в диапазоне между двумя заданными числовыми выражениями.

**Аргументы**

`expression` — значение в формате `Double`.

**Значение возврата**

`Double`.

**Пример**

`SqlServer.ATN2(9, 8)`

## <a name="ceilingexpression"></a>CEILING (выражение)

Преобразует указанное выражение в наименьшее целое число, большее или равное данному выражению.

**Аргументы**

`expression`: значение типа `Int32`, `Int64`, `Double` или `Decimal`.

**Значение возврата**

An `Int32` `Int64`, `Double`, `Decimal`или .

**Пример**

[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a>COS (выражение)

Вычисляет тригонометрический косинус указанного угла в радианах.

**Аргументы**

`expression` — значение в формате `Double`.

**Значение возврата**

`Double`.

**Пример**

`SqlServer.COS(45)`

## <a name="cotexpression"></a>КОТ (выражение)

Вычисляет тригонометрический котангенс указанного угла в радианах.

**Аргументы**

`expression` — значение в формате `Double`.

**Значение возврата**

`Double`.

**Пример**

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a>DEGREES (радианы)

Возвращает соответствующее значение угла в градусах.

**Аргументы**

`expression`: значение типа `Int32`, `Int64`, `Double` или `Decimal`.

**Значение возврата**

An `Int32` `Int64`, `Double`, `Decimal`или .

**Пример**

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a>EXP (выражение)

Вычисляет экспоненту заданного числового выражения.

**Аргументы**

`expression` — значение в формате `Double`.

**Значение возврата**

`Double`.

**Пример**`SqlServer.EXP(1)`

## <a name="floorexpression"></a>FLOOR (выражение)

Преобразует указанное выражение в наибольшее целое число, меньшее или равное данному выражению.

**Аргументы**

`expression` — значение в формате `Double`.

**Значение возврата**

`Double`.

**Пример**

[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a>LOG (выражение)

Вычисляет натуральный логарифм заданного выражения типа `float`.

**Аргументы**

`expression` — значение в формате `Double`.

**Значение возврата**

`Double`.

**Пример**

`SqlServer.LOG(100)`

## <a name="log10expression"></a>LOG10 (выражение)

Возвращает десятичный логарифм указанного выражения типа `Double`.

**Аргументы**

`expression` — значение в формате `Double`.

**Значение возврата**

`Double`.

**Пример**

`SqlServer.LOG10(100)`

## <a name="pi"></a>PI()

Возвращает константу «пи» в виде значения типа `Double`.

**Значение возврата**

`Double`.

**Пример**

`SqlServer.PI()`

## <a name="powernumeric_expression-power_expression"></a>POWER (numeric_expression, power_expression)

Вычисляет значение указанного выражения, возведенного в заданную степень.

**Аргументы**

|  |  |
|--|--|
|`numeric_expression`| An `Int32` `Int64`, `Double`, `Decimal`или .|
|`power_expression`| A, `Double` который представляет собой власть, к которой поднять `numeric_expression`.|

**Значение возврата**

Значение заданного выражения `numeric_expression` в указанной степени `power_expression`.

**Пример**

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a>РАДИАНС (выражение)

Преобразует градусы в радианы.

**Аргументы**

`expression`: значение типа `Int32`, `Int64`, `Double` или `Decimal`.

**Значение возврата**

An `Int32` `Int64`, `Double`, `Decimal`или .

**Пример**

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a>RAND («семя»)

Возвращает случайное значение от 0 до 1.

**Аргументы**

Значение семян как `Int32`. Если начальное значение не задано, то компонент SQL Server Database Engine присваивает случайно выбранное начальное значение. Для указанного начального значения возвращаемый результат всегда будет один и тот же.

**Значение возврата**

Случайное значение типа `Double` от 0 до 1.

**Пример**

`SqlServer.RAND()`
  
## <a name="roundnumeric_expression-lengthfunction"></a>ROUND (numeric_expression, длина, функция)

Возвращает числовое выражение, округленное до указанной длины или точности.

**Аргументы**

|  |  |
|--|--|
|`numeric_expression`| An `Int32` `Int64`, `Double`, `Decimal`или .
|`length`| Значение типа `Int32`, указывающее точность, до которой должно быть округлено значение аргумента `numeric_expression`. Если аргумент `length` является положительным числом, значение `numeric_expression` округляется до числа десятичных разрядов, указанных аргументом `length`. Если аргумент `length` является отрицательным числом, значение `numeric_expression` округляется слева от десятичной запятой, как указано аргументом `length`.|
|`function` | Необязательный параметр. Тип `Int32` операции представляет собой тип операции. Когда функция опущена или имеет значение 0 `numeric_expression` (по умолчанию), округляется. Когда значение, не превышающее 0, усечено. `numeric_expression` |

**Значение возврата**

Значение заданного выражения `numeric_expression` в указанной степени `power_expression`.

**Пример**

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a>SIGN (выражение)

Возвращает положительное (+1), нулевое (0) или отрицательное (-1) значение, обозначающее знак заданного выражения.

**Аргументы**

`expression`: `Int32`, `Int64`, `Double` или `Decimal`

**Значение возврата**

An `Int32` `Int64`, `Double`, `Decimal`или .

**Пример**

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a>SIN (выражение)

Вычисляет тригонометрический синус заданного угла в радианах и возвращает выражение типа `Double`.

**Аргументы**

`expression` — значение в формате `Double`.

**Значение возврата**

`Double`.

**Пример**`SqlServer.SIN(20)`

## <a name="sqrtexpression"></a>СЗРТ (выражение)

Возвращает квадратный корень указанного выражения.

**Аргументы**

`expression` — значение в формате `Double`.

**Значение возврата**

`Double`.

**Пример**`SqlServer.SQRT(3600)`

## <a name="squareexpression"></a>СКВАРЕ (выражение)

Возвращает значение указанного выражения в квадрате.

**Аргументы**

`expression` — значение в формате `Double`.

**Значение возврата**

`Double`.

**Пример**

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a>TAN (выражение)

Вычисляет тангенс заданного выражения.

**Аргументы**

`expression`: `Double`

**Значение возврата**

`Double`

**Пример**

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a>См. также раздел

- [Математические функции (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql)
- [Функции SqlClient для Entity Framework](sqlclient-for-ef-functions.md)
