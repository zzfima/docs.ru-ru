---
title: Статистические функции (SqlClient для Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 1fad25f2229b4fa810cf82a96dcb8c50a9de3070
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150653"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="5902d-102">Статистические функции (SqlClient для Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="5902d-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="5902d-103">Поставщик данных .NET Framework для SQL Server (SqlClient) предоставляет агрегатные функции.</span><span class="sxs-lookup"><span data-stu-id="5902d-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="5902d-104">Агрегатные функции выполняют вычисления на наборе входных значений и возвращают значение.</span><span class="sxs-lookup"><span data-stu-id="5902d-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="5902d-105">Эти функции находятся в пространстве имен SqlServer, которое доступно при использовании SqlClient.</span><span class="sxs-lookup"><span data-stu-id="5902d-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="5902d-106">Свойство пространства имен поставщика позволяет платформе Entity Framework узнать, какой префикс используется поставщиком для конкретных конструкций, таких как типы или функции.</span><span class="sxs-lookup"><span data-stu-id="5902d-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="5902d-107">Ниже приведены агрегированные функции SqlClient.</span><span class="sxs-lookup"><span data-stu-id="5902d-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="5902d-108">AVG (выражение)</span><span class="sxs-lookup"><span data-stu-id="5902d-108">AVG(expression)</span></span>

<span data-ttu-id="5902d-109">Возвращает среднее значение для значений в коллекции.</span><span class="sxs-lookup"><span data-stu-id="5902d-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="5902d-110">Значения NULL пропускаются.</span><span class="sxs-lookup"><span data-stu-id="5902d-110">Null values are ignored.</span></span>

<span data-ttu-id="5902d-111">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="5902d-111">**Arguments**</span></span>

<span data-ttu-id="5902d-112">Ан `Int32` `Int64`, `Double`, `Decimal`и .</span><span class="sxs-lookup"><span data-stu-id="5902d-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="5902d-113">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="5902d-113">**Return Value**</span></span>

<span data-ttu-id="5902d-114">Тип параметра `expression`.</span><span class="sxs-lookup"><span data-stu-id="5902d-114">The type of `expression`.</span></span>

<span data-ttu-id="5902d-115">**Пример**</span><span class="sxs-lookup"><span data-stu-id="5902d-115">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="5902d-116">CHECKSUM_AGG (сбор)</span><span class="sxs-lookup"><span data-stu-id="5902d-116">CHECKSUM_AGG(collection)</span></span>

 <span data-ttu-id="5902d-117">Возвращает контрольную сумму значений в коллекции.</span><span class="sxs-lookup"><span data-stu-id="5902d-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="5902d-118">Значения NULL пропускаются.</span><span class="sxs-lookup"><span data-stu-id="5902d-118">Null values are ignored.</span></span>

 <span data-ttu-id="5902d-119">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="5902d-119">**Arguments**</span></span>

 <span data-ttu-id="5902d-120">Коллекция ().`Int32`</span><span class="sxs-lookup"><span data-stu-id="5902d-120">A Collection(`Int32`).</span></span>

 <span data-ttu-id="5902d-121">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="5902d-121">**Return Value**</span></span>

 <span data-ttu-id="5902d-122">`Int32`.</span><span class="sxs-lookup"><span data-stu-id="5902d-122">An `Int32`.</span></span>

 <span data-ttu-id="5902d-123">**Пример**</span><span class="sxs-lookup"><span data-stu-id="5902d-123">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]

## <a name="countexpression"></a><span data-ttu-id="5902d-124">COUNT (выражение)</span><span class="sxs-lookup"><span data-stu-id="5902d-124">COUNT(expression)</span></span>

<span data-ttu-id="5902d-125">Возвращает число элементов в коллекции в виде `Int32`.</span><span class="sxs-lookup"><span data-stu-id="5902d-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="5902d-126">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="5902d-126">**Arguments**</span></span>

<span data-ttu-id="5902d-127">Коллекция\<T>, где T является одним из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="5902d-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="5902d-128">`Guid`(не возвращенв в сервере S'L 2000)</span><span class="sxs-lookup"><span data-stu-id="5902d-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="5902d-129">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="5902d-129">**Return Value**</span></span>

<span data-ttu-id="5902d-130">`Int32`.</span><span class="sxs-lookup"><span data-stu-id="5902d-130">An `Int32`.</span></span>

<span data-ttu-id="5902d-131">**Пример**</span><span class="sxs-lookup"><span data-stu-id="5902d-131">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]

## <a name="count_bigexpression"></a><span data-ttu-id="5902d-132">COUNT_BIG (выражение)</span><span class="sxs-lookup"><span data-stu-id="5902d-132">COUNT_BIG(expression)</span></span>

<span data-ttu-id="5902d-133">Возвращает число элементов в коллекции в виде `bigint`.</span><span class="sxs-lookup"><span data-stu-id="5902d-133">Returns the number of items in a collection as a `bigint`.</span></span>

 <span data-ttu-id="5902d-134">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="5902d-134">**Arguments**</span></span>

 <span data-ttu-id="5902d-135">Коллекция (T), где T является одним из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="5902d-135">A Collection(T), where T is one of the following types:</span></span>

 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="5902d-136">`Guid`(не возвращенв в сервере S'L 2000)</span><span class="sxs-lookup"><span data-stu-id="5902d-136">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="5902d-137">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="5902d-137">**Return Value**</span></span>

<span data-ttu-id="5902d-138">`Int64`.</span><span class="sxs-lookup"><span data-stu-id="5902d-138">An `Int64`.</span></span>

<span data-ttu-id="5902d-139">**Пример**</span><span class="sxs-lookup"><span data-stu-id="5902d-139">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="5902d-140">MAX (выражение)</span><span class="sxs-lookup"><span data-stu-id="5902d-140">MAX(expression)</span></span>

<span data-ttu-id="5902d-141">Возвращает максимальное значение, содержащееся в коллекции.</span><span class="sxs-lookup"><span data-stu-id="5902d-141">Returns the maximum value the collection.</span></span>

<span data-ttu-id="5902d-142">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="5902d-142">**Arguments**</span></span>

<span data-ttu-id="5902d-143">Коллекция (T), где T является одним из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="5902d-143">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="5902d-144">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="5902d-144">**Return Value**</span></span>

<span data-ttu-id="5902d-145">Тип параметра `expression`.</span><span class="sxs-lookup"><span data-stu-id="5902d-145">The type of `expression`.</span></span>

<span data-ttu-id="5902d-146">**Пример**</span><span class="sxs-lookup"><span data-stu-id="5902d-146">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="5902d-147">MIN (выражение)</span><span class="sxs-lookup"><span data-stu-id="5902d-147">MIN(expression)</span></span>

<span data-ttu-id="5902d-148">Возвращает минимальное значение в коллекции.</span><span class="sxs-lookup"><span data-stu-id="5902d-148">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="5902d-149">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="5902d-149">**Arguments**</span></span>

<span data-ttu-id="5902d-150">Коллекция (T), где T является одним из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="5902d-150">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="5902d-151">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="5902d-151">**Return Value**</span></span>

<span data-ttu-id="5902d-152">Тип параметра `expression`.</span><span class="sxs-lookup"><span data-stu-id="5902d-152">The type of `expression`.</span></span>

<span data-ttu-id="5902d-153">**Пример**</span><span class="sxs-lookup"><span data-stu-id="5902d-153">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="5902d-154">STDEV (выражение)</span><span class="sxs-lookup"><span data-stu-id="5902d-154">STDEV(expression)</span></span>

<span data-ttu-id="5902d-155">Возвращает статистическое стандартное отклонение всех значений в указанном выражении.</span><span class="sxs-lookup"><span data-stu-id="5902d-155">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="5902d-156">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="5902d-156">**Arguments**</span></span>

<span data-ttu-id="5902d-157">Коллекция ().`Double`</span><span class="sxs-lookup"><span data-stu-id="5902d-157">A Collection(`Double`).</span></span>

<span data-ttu-id="5902d-158">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="5902d-158">**Return Value**</span></span>

<span data-ttu-id="5902d-159">`Double`.</span><span class="sxs-lookup"><span data-stu-id="5902d-159">A `Double`.</span></span>

<span data-ttu-id="5902d-160">**Пример**</span><span class="sxs-lookup"><span data-stu-id="5902d-160">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="5902d-161">STDEVP (выражение)</span><span class="sxs-lookup"><span data-stu-id="5902d-161">STDEVP(expression)</span></span>

<span data-ttu-id="5902d-162">Возвращает статистическое стандартное отклонение совокупности всех значений в указанном выражении.</span><span class="sxs-lookup"><span data-stu-id="5902d-162">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="5902d-163">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="5902d-163">**Arguments**</span></span>

<span data-ttu-id="5902d-164">Коллекция ().`Double`</span><span class="sxs-lookup"><span data-stu-id="5902d-164">A Collection(`Double`).</span></span>

<span data-ttu-id="5902d-165">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="5902d-165">**Return Value**</span></span>

<span data-ttu-id="5902d-166">`Double`.</span><span class="sxs-lookup"><span data-stu-id="5902d-166">A `Double`.</span></span>

<span data-ttu-id="5902d-167">**Пример**</span><span class="sxs-lookup"><span data-stu-id="5902d-167">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="5902d-168">SUM (выражение)</span><span class="sxs-lookup"><span data-stu-id="5902d-168">SUM(expression)</span></span>

<span data-ttu-id="5902d-169">Возвращает сумму всех значений в коллекции.</span><span class="sxs-lookup"><span data-stu-id="5902d-169">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="5902d-170">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="5902d-170">**Arguments**</span></span>

<span data-ttu-id="5902d-171">Коллекция (T), где T является одним `Int32`из `Int64` `Double`следующих типов: , , `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="5902d-171">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="5902d-172">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="5902d-172">**Return Value**</span></span>

<span data-ttu-id="5902d-173">Тип параметра `expression`.</span><span class="sxs-lookup"><span data-stu-id="5902d-173">The type of `expression`.</span></span>

<span data-ttu-id="5902d-174">**Пример**</span><span class="sxs-lookup"><span data-stu-id="5902d-174">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="5902d-175">VAR (выражение)</span><span class="sxs-lookup"><span data-stu-id="5902d-175">VAR(expression)</span></span>

<span data-ttu-id="5902d-176">Возвращает статистическую дисперсию всех значений в указанном выражении.</span><span class="sxs-lookup"><span data-stu-id="5902d-176">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="5902d-177">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="5902d-177">**Arguments**</span></span>

<span data-ttu-id="5902d-178">Коллекция ().`Double`</span><span class="sxs-lookup"><span data-stu-id="5902d-178">A Collection(`Double`).</span></span>

<span data-ttu-id="5902d-179">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="5902d-179">**Return Value**</span></span>

<span data-ttu-id="5902d-180">`Double`.</span><span class="sxs-lookup"><span data-stu-id="5902d-180">A `Double`.</span></span>

<span data-ttu-id="5902d-181">**Пример**</span><span class="sxs-lookup"><span data-stu-id="5902d-181">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="5902d-182">VARP (выражение)</span><span class="sxs-lookup"><span data-stu-id="5902d-182">VARP(expression)</span></span>

<span data-ttu-id="5902d-183">Возвращает статистическую дисперсию для заполнения всех значений в указанном выражении.</span><span class="sxs-lookup"><span data-stu-id="5902d-183">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="5902d-184">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="5902d-184">**Arguments**</span></span>

<span data-ttu-id="5902d-185">Коллекция ().`Double`</span><span class="sxs-lookup"><span data-stu-id="5902d-185">A Collection(`Double`).</span></span>

<span data-ttu-id="5902d-186">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="5902d-186">**Return Value**</span></span>

<span data-ttu-id="5902d-187">`Double`.</span><span class="sxs-lookup"><span data-stu-id="5902d-187">A `Double`.</span></span>

<span data-ttu-id="5902d-188">**Пример**</span><span class="sxs-lookup"><span data-stu-id="5902d-188">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]
  
## <a name="see-also"></a><span data-ttu-id="5902d-189">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5902d-189">See also</span></span>

- [<span data-ttu-id="5902d-190">Агрегатные функции (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5902d-190">Aggregate Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [<span data-ttu-id="5902d-191">Язык Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5902d-191">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="5902d-192">Статистические канонические функции</span><span class="sxs-lookup"><span data-stu-id="5902d-192">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
