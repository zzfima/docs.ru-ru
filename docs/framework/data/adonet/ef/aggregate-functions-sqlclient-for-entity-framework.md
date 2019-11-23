---
title: Статистические функции (SqlClient для Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 3dbd4c0a24a5fc41153ea16747325e824669b0e5
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700047"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a>Статистические функции (SqlClient для Entity Framework)
Поставщик данных .NET Framework для SQL Server (SqlClient) предоставляет агрегатные функции. Агрегатные функции выполняют вычисления на наборе входных значений и возвращают значение. Эти функции находятся в пространстве имен SqlServer, которое доступно при использовании SqlClient. Свойство пространства имен поставщика позволяет платформе Entity Framework узнать, какой префикс используется поставщиком для конкретных конструкций, таких как типы или функции.  
  
 Ниже приведены агрегатные функции SqlClient.  

## <a name="avgexpression"></a>AVG (выражение)

Возвращает среднее значение для значений в коллекции. Значения NULL не учитываются.

**аргументы**

`Int32`, `Int64`, `Double`и `Decimal`.

**Возвращаемое значение**

Тип параметра `expression`.

**Пример**

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a>CHECKSUM_AGG (коллекция)
 
 Возвращает контрольную сумму значений в коллекции. Значения NULL не учитываются.
 
 **аргументы**
 
 Коллекция (`Int32`).
 
 **Возвращаемое значение**
 
 `Int32`.
 
 **Пример**
 
[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a>COUNT (выражение)

Возвращает число элементов в коллекции в виде `Int32`.

**аргументы**

Коллекция\<T >, где T — один из следующих типов:

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid` (не возвращается в SQL Server 2000)|

**Возвращаемое значение**

`Int32`.

**Пример**

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]
 
## <a name="count_bigexpression"></a>COUNT_BIG (выражение)
 
Возвращает число элементов в коллекции в виде `bigint`.
 
 **аргументы**
 
 Коллекция (T), где T — один из следующих типов:
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid` (не возвращается в SQL Server 2000)|

**Возвращаемое значение**

`Int64`.

**Пример**

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a>MAX (выражение)

Возвращает максимальное значение, содержащееся в коллекции.

**аргументы**

Коллекция (T), где T — один из следующих типов: 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**Возвращаемое значение**

Тип параметра `expression`.

**Пример**

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a>MIN (выражение)

Возвращает минимальное значение в коллекции.

**аргументы**

Коллекция (T), где T — один из следующих типов: 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**Возвращаемое значение**

Тип параметра `expression`.

**Пример**

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a>STDEV (выражение)

Возвращает статистическое стандартное отклонение всех значений в указанном выражении.

**аргументы**

Коллекция (`Double`).

**Возвращаемое значение**

Объект `Double`.

**Пример**

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a>STDEVP (выражение)

Возвращает статистическое стандартное отклонение совокупности всех значений в указанном выражении.

**аргументы**

Коллекция (`Double`).

**Возвращаемое значение**

Объект `Double`.

**Пример**

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a>SUM (выражение)

Возвращает сумму всех значений в коллекции.

**аргументы**

Коллекция (T), в которой T является одним из следующих типов: `Int32`, `Int64`, `Double`, `Decimal`.

**Возвращаемое значение**

Тип параметра `expression`.

**Пример**

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a>VAR (выражение)

Возвращает статистическую дисперсию всех значений в указанном выражении.

**аргументы**

Коллекция (`Double`).

**Возвращаемое значение**

Объект `Double`.

**Пример**

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a>VARP (выражение)

Возвращает статистическую дисперсию совокупности всех значений в указанном выражении.

**аргументы**

Коллекция (`Double`).

**Возвращаемое значение**

Объект `Double`.

**Пример**

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a>См. также:

- [Агрегатные функции (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [Язык Entity SQL](./language-reference/entity-sql-language.md)
- [Статистические канонические функции](./language-reference/aggregate-canonical-functions.md)
