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
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="b0995-102">Статистические функции (SqlClient для Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="b0995-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="b0995-103">Поставщик данных .NET Framework для SQL Server (SqlClient) предоставляет агрегатные функции.</span><span class="sxs-lookup"><span data-stu-id="b0995-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="b0995-104">Агрегатные функции выполняют вычисления на наборе входных значений и возвращают значение.</span><span class="sxs-lookup"><span data-stu-id="b0995-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="b0995-105">Эти функции находятся в пространстве имен SqlServer, которое доступно при использовании SqlClient.</span><span class="sxs-lookup"><span data-stu-id="b0995-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="b0995-106">Свойство пространства имен поставщика позволяет платформе Entity Framework узнать, какой префикс используется поставщиком для конкретных конструкций, таких как типы или функции.</span><span class="sxs-lookup"><span data-stu-id="b0995-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="b0995-107">Ниже приведены агрегатные функции SqlClient.</span><span class="sxs-lookup"><span data-stu-id="b0995-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="b0995-108">AVG (выражение)</span><span class="sxs-lookup"><span data-stu-id="b0995-108">AVG(expression)</span></span>

<span data-ttu-id="b0995-109">Возвращает среднее значение для значений в коллекции.</span><span class="sxs-lookup"><span data-stu-id="b0995-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="b0995-110">Значения NULL не учитываются.</span><span class="sxs-lookup"><span data-stu-id="b0995-110">Null values are ignored.</span></span>

<span data-ttu-id="b0995-111">**аргументы**</span><span class="sxs-lookup"><span data-stu-id="b0995-111">**Arguments**</span></span>

<span data-ttu-id="b0995-112">`Int32`, `Int64`, `Double`и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="b0995-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="b0995-113">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="b0995-113">**Return Value**</span></span>

<span data-ttu-id="b0995-114">Тип параметра `expression`.</span><span class="sxs-lookup"><span data-stu-id="b0995-114">The type of `expression`.</span></span>

<span data-ttu-id="b0995-115">**Пример**</span><span class="sxs-lookup"><span data-stu-id="b0995-115">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="b0995-116">CHECKSUM_AGG (коллекция)</span><span class="sxs-lookup"><span data-stu-id="b0995-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="b0995-117">Возвращает контрольную сумму значений в коллекции.</span><span class="sxs-lookup"><span data-stu-id="b0995-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="b0995-118">Значения NULL не учитываются.</span><span class="sxs-lookup"><span data-stu-id="b0995-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="b0995-119">**аргументы**</span><span class="sxs-lookup"><span data-stu-id="b0995-119">**Arguments**</span></span>
 
 <span data-ttu-id="b0995-120">Коллекция (`Int32`).</span><span class="sxs-lookup"><span data-stu-id="b0995-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="b0995-121">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="b0995-121">**Return Value**</span></span>
 
 <span data-ttu-id="b0995-122">`Int32`.</span><span class="sxs-lookup"><span data-stu-id="b0995-122">An `Int32`.</span></span>
 
 <span data-ttu-id="b0995-123">**Пример**</span><span class="sxs-lookup"><span data-stu-id="b0995-123">**Example**</span></span>
 
[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="b0995-124">COUNT (выражение)</span><span class="sxs-lookup"><span data-stu-id="b0995-124">COUNT(expression)</span></span>

<span data-ttu-id="b0995-125">Возвращает число элементов в коллекции в виде `Int32`.</span><span class="sxs-lookup"><span data-stu-id="b0995-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="b0995-126">**аргументы**</span><span class="sxs-lookup"><span data-stu-id="b0995-126">**Arguments**</span></span>

<span data-ttu-id="b0995-127">Коллекция\<T >, где T — один из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="b0995-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="b0995-128">`Guid` (не возвращается в SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="b0995-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="b0995-129">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="b0995-129">**Return Value**</span></span>

<span data-ttu-id="b0995-130">`Int32`.</span><span class="sxs-lookup"><span data-stu-id="b0995-130">An `Int32`.</span></span>

<span data-ttu-id="b0995-131">**Пример**</span><span class="sxs-lookup"><span data-stu-id="b0995-131">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]
 
## <a name="count_bigexpression"></a><span data-ttu-id="b0995-132">COUNT_BIG (выражение)</span><span class="sxs-lookup"><span data-stu-id="b0995-132">COUNT_BIG(expression)</span></span>
 
<span data-ttu-id="b0995-133">Возвращает число элементов в коллекции в виде `bigint`.</span><span class="sxs-lookup"><span data-stu-id="b0995-133">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="b0995-134">**аргументы**</span><span class="sxs-lookup"><span data-stu-id="b0995-134">**Arguments**</span></span>
 
 <span data-ttu-id="b0995-135">Коллекция (T), где T — один из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="b0995-135">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="b0995-136">`Guid` (не возвращается в SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="b0995-136">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="b0995-137">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="b0995-137">**Return Value**</span></span>

<span data-ttu-id="b0995-138">`Int64`.</span><span class="sxs-lookup"><span data-stu-id="b0995-138">An `Int64`.</span></span>

<span data-ttu-id="b0995-139">**Пример**</span><span class="sxs-lookup"><span data-stu-id="b0995-139">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="b0995-140">MAX (выражение)</span><span class="sxs-lookup"><span data-stu-id="b0995-140">MAX(expression)</span></span>

<span data-ttu-id="b0995-141">Возвращает максимальное значение, содержащееся в коллекции.</span><span class="sxs-lookup"><span data-stu-id="b0995-141">Returns the maximum value the collection.</span></span>

<span data-ttu-id="b0995-142">**аргументы**</span><span class="sxs-lookup"><span data-stu-id="b0995-142">**Arguments**</span></span>

<span data-ttu-id="b0995-143">Коллекция (T), где T — один из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="b0995-143">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="b0995-144">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="b0995-144">**Return Value**</span></span>

<span data-ttu-id="b0995-145">Тип параметра `expression`.</span><span class="sxs-lookup"><span data-stu-id="b0995-145">The type of `expression`.</span></span>

<span data-ttu-id="b0995-146">**Пример**</span><span class="sxs-lookup"><span data-stu-id="b0995-146">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="b0995-147">MIN (выражение)</span><span class="sxs-lookup"><span data-stu-id="b0995-147">MIN(expression)</span></span>

<span data-ttu-id="b0995-148">Возвращает минимальное значение в коллекции.</span><span class="sxs-lookup"><span data-stu-id="b0995-148">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="b0995-149">**аргументы**</span><span class="sxs-lookup"><span data-stu-id="b0995-149">**Arguments**</span></span>

<span data-ttu-id="b0995-150">Коллекция (T), где T — один из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="b0995-150">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="b0995-151">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="b0995-151">**Return Value**</span></span>

<span data-ttu-id="b0995-152">Тип параметра `expression`.</span><span class="sxs-lookup"><span data-stu-id="b0995-152">The type of `expression`.</span></span>

<span data-ttu-id="b0995-153">**Пример**</span><span class="sxs-lookup"><span data-stu-id="b0995-153">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="b0995-154">STDEV (выражение)</span><span class="sxs-lookup"><span data-stu-id="b0995-154">STDEV(expression)</span></span>

<span data-ttu-id="b0995-155">Возвращает статистическое стандартное отклонение всех значений в указанном выражении.</span><span class="sxs-lookup"><span data-stu-id="b0995-155">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="b0995-156">**аргументы**</span><span class="sxs-lookup"><span data-stu-id="b0995-156">**Arguments**</span></span>

<span data-ttu-id="b0995-157">Коллекция (`Double`).</span><span class="sxs-lookup"><span data-stu-id="b0995-157">A Collection(`Double`).</span></span>

<span data-ttu-id="b0995-158">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="b0995-158">**Return Value**</span></span>

<span data-ttu-id="b0995-159">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="b0995-159">A `Double`.</span></span>

<span data-ttu-id="b0995-160">**Пример**</span><span class="sxs-lookup"><span data-stu-id="b0995-160">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="b0995-161">STDEVP (выражение)</span><span class="sxs-lookup"><span data-stu-id="b0995-161">STDEVP(expression)</span></span>

<span data-ttu-id="b0995-162">Возвращает статистическое стандартное отклонение совокупности всех значений в указанном выражении.</span><span class="sxs-lookup"><span data-stu-id="b0995-162">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="b0995-163">**аргументы**</span><span class="sxs-lookup"><span data-stu-id="b0995-163">**Arguments**</span></span>

<span data-ttu-id="b0995-164">Коллекция (`Double`).</span><span class="sxs-lookup"><span data-stu-id="b0995-164">A Collection(`Double`).</span></span>

<span data-ttu-id="b0995-165">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="b0995-165">**Return Value**</span></span>

<span data-ttu-id="b0995-166">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="b0995-166">A `Double`.</span></span>

<span data-ttu-id="b0995-167">**Пример**</span><span class="sxs-lookup"><span data-stu-id="b0995-167">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="b0995-168">SUM (выражение)</span><span class="sxs-lookup"><span data-stu-id="b0995-168">SUM(expression)</span></span>

<span data-ttu-id="b0995-169">Возвращает сумму всех значений в коллекции.</span><span class="sxs-lookup"><span data-stu-id="b0995-169">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="b0995-170">**аргументы**</span><span class="sxs-lookup"><span data-stu-id="b0995-170">**Arguments**</span></span>

<span data-ttu-id="b0995-171">Коллекция (T), в которой T является одним из следующих типов: `Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="b0995-171">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="b0995-172">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="b0995-172">**Return Value**</span></span>

<span data-ttu-id="b0995-173">Тип параметра `expression`.</span><span class="sxs-lookup"><span data-stu-id="b0995-173">The type of `expression`.</span></span>

<span data-ttu-id="b0995-174">**Пример**</span><span class="sxs-lookup"><span data-stu-id="b0995-174">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="b0995-175">VAR (выражение)</span><span class="sxs-lookup"><span data-stu-id="b0995-175">VAR(expression)</span></span>

<span data-ttu-id="b0995-176">Возвращает статистическую дисперсию всех значений в указанном выражении.</span><span class="sxs-lookup"><span data-stu-id="b0995-176">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="b0995-177">**аргументы**</span><span class="sxs-lookup"><span data-stu-id="b0995-177">**Arguments**</span></span>

<span data-ttu-id="b0995-178">Коллекция (`Double`).</span><span class="sxs-lookup"><span data-stu-id="b0995-178">A Collection(`Double`).</span></span>

<span data-ttu-id="b0995-179">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="b0995-179">**Return Value**</span></span>

<span data-ttu-id="b0995-180">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="b0995-180">A `Double`.</span></span>

<span data-ttu-id="b0995-181">**Пример**</span><span class="sxs-lookup"><span data-stu-id="b0995-181">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="b0995-182">VARP (выражение)</span><span class="sxs-lookup"><span data-stu-id="b0995-182">VARP(expression)</span></span>

<span data-ttu-id="b0995-183">Возвращает статистическую дисперсию совокупности всех значений в указанном выражении.</span><span class="sxs-lookup"><span data-stu-id="b0995-183">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="b0995-184">**аргументы**</span><span class="sxs-lookup"><span data-stu-id="b0995-184">**Arguments**</span></span>

<span data-ttu-id="b0995-185">Коллекция (`Double`).</span><span class="sxs-lookup"><span data-stu-id="b0995-185">A Collection(`Double`).</span></span>

<span data-ttu-id="b0995-186">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="b0995-186">**Return Value**</span></span>

<span data-ttu-id="b0995-187">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="b0995-187">A `Double`.</span></span>

<span data-ttu-id="b0995-188">**Пример**</span><span class="sxs-lookup"><span data-stu-id="b0995-188">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="b0995-189">См. также:</span><span class="sxs-lookup"><span data-stu-id="b0995-189">See also</span></span>

- [<span data-ttu-id="b0995-190">Агрегатные функции (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b0995-190">Aggregate Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [<span data-ttu-id="b0995-191">Язык Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b0995-191">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="b0995-192">Статистические канонические функции</span><span class="sxs-lookup"><span data-stu-id="b0995-192">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
