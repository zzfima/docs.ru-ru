---
title: Математические функции
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: e6c58d781d7138f8295f2d0a2f0db110ad4b1dd6
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44225247"
---
# <a name="mathematical-functions"></a>Математические функции

Поставщик данных для SQL Server платформы .NET Framework (SqlClient) предоставляет математические функции, производящие вычисления на входящих значениях, предоставляемых в качестве аргументов, и возвращающие результат в виде числовых значений. Эти функции находятся в пространстве имен SqlServer, которое доступно при использовании SqlClient. Свойство пространства имен поставщика позволяет платформе Entity Framework узнать, какой префикс используется поставщиком для конкретных конструкций, таких как типы или функции. В следующей таблице описаны математические функции SqlClient.  
  
## <a name="absexpression"></a>ABS(Expression)

Возвращает абсолютное значение.

**Аргументы**

`expression`: значение типа `Int32`, `Int64`, `Double` или `Decimal`.

**Возвращаемое значение**

Абсолютное значение заданного выражения.

**Пример**

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a>ACOS(Expression)

Возвращает значение арккосинуса указанного выражения.

**Аргументы**

`expression`: Тип `Double`.

**Возвращаемое значение**

Объект `Double`.

**Пример**

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a>ASIN(Expression)

Возвращает значение арксинуса указанного выражения.

**Аргументы**

`expression`: Тип `Double`.

**Возвращаемое значение**

Объект `Double`.

**Пример**

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a>ATAN(Expression)

Возвращает значение арктангенса указанного числового выражения.

**Аргументы**

`expression`: Тип `Double`.

**Возвращаемое значение**

Объект `Double`.

**Пример**

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a>ATN2(Expression, Expression)

Возвращает угол в радианах, тангенс которого находится в диапазоне между двумя заданными числовыми выражениями.

**Аргументы**

`expression`: Тип `Double`.

**Возвращаемое значение**

Объект `Double`.

**Пример**

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a>CEILING(Expression)

Преобразует указанное выражение в наименьшее целое число, большее или равное данному выражению.

**Аргументы**

`expression`: значение типа `Int32`, `Int64`, `Double` или `Decimal`.

**Возвращаемое значение**

`Int32`, `Int64`, `Double`, Или `Decimal`.

**Пример** 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a>COS(Expression)

Вычисляет тригонометрический косинус указанного угла в радианах. 

**Аргументы** 

`expression`: Тип `Double`. 

**Возвращаемое значение** 

Объект `Double`. 

**Пример** 

`SqlServer.COS(45)`

## <a name="cotexpression"></a>COT(Expression)

Вычисляет тригонометрический котангенс указанного угла в радианах. 

**Аргументы** 

`expression`: Тип `Double`. 

**Возвращаемое значение** 

Объект `Double`. 

**Пример** 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a>DEGREES(RADIANS)

Возвращает соответствующее значение угла в градусах. 

**Аргументы** 

`expression`: значение типа `Int32`, `Int64`, `Double` или `Decimal`. 

**Возвращаемое значение** 

`Int32`, `Int64`, `Double`, Или `Decimal`. 

**Пример** 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a>EXP(Expression)

Вычисляет экспоненту заданного числового выражения. 

**Аргументы** 

`expression`: Тип `Double`. 

**Возвращаемое значение** 

Объект `Double`. 

**Пример** `SqlServer.EXP(1)`

## <a name="floorexpression"></a>FLOOR(Expression)

Преобразует указанное выражение в наибольшее целое число, меньшее или равное данному выражению. 

**Аргументы** 

`expression`: Тип `Double`. 

**Возвращаемое значение** 

Объект `Double`. 

**Пример** 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a>LOG(Expression)

Вычисляет натуральный логарифм заданного выражения типа `float`. 

**Аргументы** 

`expression`: Тип `Double`. 

**Возвращаемое значение** 

Объект `Double`. 

**Пример** 

`SqlServer.LOG(100)`

## <a name="log10expression"></a>LOG10(Expression)

Возвращает десятичный логарифм указанного выражения типа `Double`. 

**Аргументы** 

`expression`: Тип `Double`. 

**Возвращаемое значение** 

Объект `Double`. 

**Пример** 

`SqlServer.LOG10(100)`

## <a name="pi"></a>ПИ()

Возвращает константу «пи» в виде значения типа `Double`. 

**Возвращаемое значение** 

Объект `Double`. 

**Пример** 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a>POWER (numeric_expression, power_expression)

Вычисляет значение указанного выражения, возведенного в заданную степень.

**Аргументы** 

|  |  |
|--|--|
|`numeric_expression`| `Int32`, `Int64`, `Double`, Или `Decimal`.|
|`power_expression`| Объект `Double` , представляющее степень, в которую возводится `numeric_expression`.| 

**Возвращаемое значение** 

Значение заданного выражения `numeric_expression` в указанной степени `power_expression`. 

**Пример** 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a>RADIANS(Expression)

Преобразовывает градусы в радианы. 

**Аргументы** 

`expression`: значение типа `Int32`, `Int64`, `Double` или `Decimal`. 

**Возвращаемое значение** 

`Int32`, `Int64`, `Double`, Или `Decimal`. 

**Пример** 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a>RAND([seed])

Возвращает случайное значение от 0 до 1. 

**Аргументы** 

Начальное значение, что `Int32`. Если начальное значение не задано, то компонент SQL Server Database Engine присваивает случайно выбранное начальное значение. Для указанного начального значения возвращаемый результат всегда будет один и тот же.

**Возвращаемое значение** 

Случайное значение типа `Double` от 0 до 1. 

**Пример** 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a>Round(Numeric_Expression, length[,Function])

Возвращает числовое выражение, округленное до указанной длины или точности. 

**Аргументы** 

|  |  |
|--|--|
|`numeric_expression`| `Int32`, `Int64`, `Double`, Или `Decimal`. 
|`length`| Значение типа `Int32`, указывающее точность, до которой должно быть округлено значение аргумента `numeric_expression`. Если аргумент `length` является положительным числом, значение `numeric_expression` округляется до числа десятичных разрядов, указанных аргументом `length`. Если аргумент `length` является отрицательным числом, значение `numeric_expression` округляется слева от десятичной запятой, как указано аргументом `length`.|
|`function` | Необязательный. `Int32` , Представляющий тип выполняемой операции. Если функция указан или имеет значение 0 (по умолчанию), `numeric_expression` округляется. Если значение, отличное от указано значение 0, `numeric_expression` усекается. |

**Возвращаемое значение** 

Значение заданного выражения `numeric_expression` в указанной степени `power_expression`.

**Пример** 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a>Sign(Expression) 

Возвращает положительный знак (+1), ноль (0) или отрицательный знак (-1) указанного выражения. 

**Аргументы** 

`expression`: `Int32`, `Int64`, `Double` или `Decimal` 

**Возвращаемое значение** 

`Int32`, `Int64`, `Double`, Или `Decimal`. 

**Пример** 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a>SIN(Expression)

Вычисляет тригонометрический синус заданного угла в радианах и возвращает выражение типа `Double`. 

**Аргументы** 

`expression`: Тип `Double`. 

**Возвращаемое значение** 

Объект `Double`. 

**Пример** `SqlServer.SIN(20)`

## <a name="sqrtexpression"></a>SQRT(Expression)

Возвращает квадратный корень указанного выражения. 

**Аргументы** 

`expression`: Тип `Double`. 

**Возвращаемое значение** 

Объект `Double`. 

**Пример** `SqlServer.SQRT(3600)`

## <a name="squareexpression"></a>Square(Expression)

Возвращает значение указанного выражения в квадрате. 

**Аргументы** 

`expression`: Тип `Double`. 

**Возвращаемое значение** 

Объект `Double`. 

**Пример** 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a>TAN(Expression)

Вычисляет тангенс заданного выражения.

**Аргументы** 

`expression`: `Double` 

**Возвращаемое значение** 

`Double` 

**Пример** 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a>См. также

Дополнительные сведения о математических функциях, поддерживаемых SqlClient, см. в документации к версии SQL Server, указанной в манифесте поставщика SqlClient.  
  
**SQL Server 2005:** [математические функции (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))  
**SQL Server 2008:** [математические функции (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))  
**SQL Server 2012 и более поздних версий:** [математические функции (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)   

 [Функции SqlClient для Entity Framework](sqlclient-for-ef-functions.md)
