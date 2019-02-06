---
title: Статистические функции (SqlClient для Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: f2f2b557cd9f126ddd513a0f42d3ac95114c3822
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758707"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a>Статистические функции (SqlClient для Entity Framework)
Поставщик данных .NET Framework для SQL Server (SqlClient) предоставляет агрегатные функции. Агрегатные функции выполняют вычисления на наборе входных значений и возвращают значение. Эти функции находятся в пространстве имен SqlServer, которое доступно при использовании SqlClient. Свойство пространства имен поставщика позволяет платформе Entity Framework узнать, какой префикс используется поставщиком для конкретных конструкций, таких как типы или функции.  
  
 Ниже приведены агрегатные функции SqlClient.  

## <a name="avgexpression"></a>AVG(Expression)

Возвращает среднее значение для значений в коллекции. Значения NULL не учитываются.

**Аргументы**

`Int32`, `Int64`, `Double`, И `Decimal`.

**Возвращаемое значение**

Тип параметра `expression`.

**Пример**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksumaggcollection"></a>CHECKSUM_AGG(Collection)
 
 Возвращает контрольную сумму значений в коллекции. Значения NULL не учитываются.
 
 **Аргументы**
 
 Коллекция (`Int32`).
 
 **Возвращаемое значение**
 
 Объект `Int32`.
 
 **Пример**
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a>Count(Expression)

Возвращает число элементов в коллекции в виде `Int32`.

**Аргументы**

Коллекция\<T >, где T — один из следующих типов:

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid` (не возвращаемое в SQL Server 2000)|

**Возвращаемое значение**

Объект `Int32`.

**Пример**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
[! код sql[SQLSERVER_COUNT # понятия EntityServices точки Распространения](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)
 
## <a name="countbigexpression"></a>COUNT_BIG(Expression)
 
 Возвращает число элементов в коллекции в виде `bigint`.
 
 **Аргументы**
 
 Collection(T), где T — один из следующих типов:
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid` (не возвращаемое в SQL Server 2000)|

**Возвращаемое значение**

Объект `Int64`.

**Пример**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a>MAX(Expression)

Возвращает максимальное значение, содержащееся в коллекции.

**Аргументы**

Collection(T), где T — один из следующих типов: 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**Возвращаемое значение**

Тип параметра `expression`.

**Пример**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a>Min(Expression)

Возвращает минимальное значение в коллекции.

**Аргументы**

Collection(T), где T — один из следующих типов: 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**Возвращаемое значение**

Тип параметра `expression`.

**Пример**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a>StDev(Expression)

Возвращает статистическое стандартное отклонение всех значений в указанном выражении.

**Аргументы**

Коллекция (`Double`).

**Возвращаемое значение**

Объект `Double`.

**Пример**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a>STDEVP(Expression)

Возвращает статистическое стандартное отклонение совокупности всех значений в указанном выражении.

**Аргументы**

Коллекция (`Double`).

**Возвращаемое значение**

Объект `Double`.

**Пример**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a>SUM(Expression)

Возвращает сумму всех значений в коллекции.

**Аргументы**

Collection(T), где T — один из следующих типов: `Int32`, `Int64`, `Double`, `Decimal`.

**Возвращаемое значение**

Тип параметра `expression`.

**Пример**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a>VAR(Expression)

Возвращает статистическую дисперсию всех значений в указанном выражении.

**Аргументы**

Коллекция (`Double`).

**Возвращаемое значение**

Объект `Double`.

**Пример**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a>VARP(Expression)

Возвращает статистическую дисперсию совокупности всех значений в указанном выражении.

**Аргументы**

Коллекция (`Double`).

**Возвращаемое значение**

Объект `Double`.

**Пример**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a>См. также

Дополнительные сведения об агрегатных функциях, поддерживаемых SqlClient, см. в документации к версии SQL Server, указанной в манифесте поставщика SqlClient.

- **SQL Server 2005:** [Агрегатные функции (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))
- **SQL Server 2008 и более поздних версий:** [Агрегатные функции (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)

- [Язык Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [Статистические канонические функции](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)
