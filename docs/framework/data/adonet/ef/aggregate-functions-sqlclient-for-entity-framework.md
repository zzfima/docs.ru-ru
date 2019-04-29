---
title: Статистические функции (SqlClient для Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: f2f2b557cd9f126ddd513a0f42d3ac95114c3822
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606785"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="9d6be-102">Статистические функции (SqlClient для Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="9d6be-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="9d6be-103">Поставщик данных .NET Framework для SQL Server (SqlClient) предоставляет агрегатные функции.</span><span class="sxs-lookup"><span data-stu-id="9d6be-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="9d6be-104">Агрегатные функции выполняют вычисления на наборе входных значений и возвращают значение.</span><span class="sxs-lookup"><span data-stu-id="9d6be-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="9d6be-105">Эти функции находятся в пространстве имен SqlServer, которое доступно при использовании SqlClient.</span><span class="sxs-lookup"><span data-stu-id="9d6be-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="9d6be-106">Свойство пространства имен поставщика позволяет платформе Entity Framework узнать, какой префикс используется поставщиком для конкретных конструкций, таких как типы или функции.</span><span class="sxs-lookup"><span data-stu-id="9d6be-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="9d6be-107">Ниже приведены агрегатные функции SqlClient.</span><span class="sxs-lookup"><span data-stu-id="9d6be-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="9d6be-108">AVG(Expression)</span><span class="sxs-lookup"><span data-stu-id="9d6be-108">AVG(expression)</span></span>

<span data-ttu-id="9d6be-109">Возвращает среднее значение для значений в коллекции.</span><span class="sxs-lookup"><span data-stu-id="9d6be-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="9d6be-110">Значения NULL не учитываются.</span><span class="sxs-lookup"><span data-stu-id="9d6be-110">Null values are ignored.</span></span>

<span data-ttu-id="9d6be-111">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="9d6be-111">**Arguments**</span></span>

<span data-ttu-id="9d6be-112">`Int32`, `Int64`, `Double`, И `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="9d6be-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="9d6be-113">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="9d6be-113">**Return Value**</span></span>

<span data-ttu-id="9d6be-114">Тип параметра `expression`.</span><span class="sxs-lookup"><span data-stu-id="9d6be-114">The type of `expression`.</span></span>

<span data-ttu-id="9d6be-115">**Пример**</span><span class="sxs-lookup"><span data-stu-id="9d6be-115">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksumaggcollection"></a><span data-ttu-id="9d6be-116">CHECKSUM_AGG(Collection)</span><span class="sxs-lookup"><span data-stu-id="9d6be-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="9d6be-117">Возвращает контрольную сумму значений в коллекции.</span><span class="sxs-lookup"><span data-stu-id="9d6be-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="9d6be-118">Значения NULL не учитываются.</span><span class="sxs-lookup"><span data-stu-id="9d6be-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="9d6be-119">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="9d6be-119">**Arguments**</span></span>
 
 <span data-ttu-id="9d6be-120">Коллекция (`Int32`).</span><span class="sxs-lookup"><span data-stu-id="9d6be-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="9d6be-121">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="9d6be-121">**Return Value**</span></span>
 
 <span data-ttu-id="9d6be-122">Объект `Int32`.</span><span class="sxs-lookup"><span data-stu-id="9d6be-122">An `Int32`.</span></span>
 
 <span data-ttu-id="9d6be-123">**Пример**</span><span class="sxs-lookup"><span data-stu-id="9d6be-123">**Example**</span></span>
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="9d6be-124">Count(Expression)</span><span class="sxs-lookup"><span data-stu-id="9d6be-124">COUNT(expression)</span></span>

<span data-ttu-id="9d6be-125">Возвращает число элементов в коллекции в виде `Int32`.</span><span class="sxs-lookup"><span data-stu-id="9d6be-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="9d6be-126">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="9d6be-126">**Arguments**</span></span>

<span data-ttu-id="9d6be-127">Коллекция\<T >, где T — один из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="9d6be-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="9d6be-128">`Guid` (не возвращаемое в SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="9d6be-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="9d6be-129">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="9d6be-129">**Return Value**</span></span>

<span data-ttu-id="9d6be-130">Объект `Int32`.</span><span class="sxs-lookup"><span data-stu-id="9d6be-130">An `Int32`.</span></span>

<span data-ttu-id="9d6be-131">**Пример**</span><span class="sxs-lookup"><span data-stu-id="9d6be-131">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
<span data-ttu-id="9d6be-132">[! код sql[SQLSERVER_COUNT # понятия EntityServices точки Распространения](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span><span class="sxs-lookup"><span data-stu-id="9d6be-132">[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span></span>
 
## <a name="countbigexpression"></a><span data-ttu-id="9d6be-133">COUNT_BIG(Expression)</span><span class="sxs-lookup"><span data-stu-id="9d6be-133">COUNT_BIG(expression)</span></span>
 
 <span data-ttu-id="9d6be-134">Возвращает число элементов в коллекции в виде `bigint`.</span><span class="sxs-lookup"><span data-stu-id="9d6be-134">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="9d6be-135">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="9d6be-135">**Arguments**</span></span>
 
 <span data-ttu-id="9d6be-136">Collection(T), где T — один из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="9d6be-136">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="9d6be-137">`Guid` (не возвращаемое в SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="9d6be-137">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="9d6be-138">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="9d6be-138">**Return Value**</span></span>

<span data-ttu-id="9d6be-139">Объект `Int64`.</span><span class="sxs-lookup"><span data-stu-id="9d6be-139">An `Int64`.</span></span>

<span data-ttu-id="9d6be-140">**Пример**</span><span class="sxs-lookup"><span data-stu-id="9d6be-140">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="9d6be-141">MAX(Expression)</span><span class="sxs-lookup"><span data-stu-id="9d6be-141">MAX(expression)</span></span>

<span data-ttu-id="9d6be-142">Возвращает максимальное значение, содержащееся в коллекции.</span><span class="sxs-lookup"><span data-stu-id="9d6be-142">Returns the maximum value the collection.</span></span>

<span data-ttu-id="9d6be-143">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="9d6be-143">**Arguments**</span></span>

<span data-ttu-id="9d6be-144">Collection(T), где T — один из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="9d6be-144">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="9d6be-145">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="9d6be-145">**Return Value**</span></span>

<span data-ttu-id="9d6be-146">Тип параметра `expression`.</span><span class="sxs-lookup"><span data-stu-id="9d6be-146">The type of `expression`.</span></span>

<span data-ttu-id="9d6be-147">**Пример**</span><span class="sxs-lookup"><span data-stu-id="9d6be-147">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="9d6be-148">Min(Expression)</span><span class="sxs-lookup"><span data-stu-id="9d6be-148">MIN(expression)</span></span>

<span data-ttu-id="9d6be-149">Возвращает минимальное значение в коллекции.</span><span class="sxs-lookup"><span data-stu-id="9d6be-149">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="9d6be-150">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="9d6be-150">**Arguments**</span></span>

<span data-ttu-id="9d6be-151">Collection(T), где T — один из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="9d6be-151">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="9d6be-152">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="9d6be-152">**Return Value**</span></span>

<span data-ttu-id="9d6be-153">Тип параметра `expression`.</span><span class="sxs-lookup"><span data-stu-id="9d6be-153">The type of `expression`.</span></span>

<span data-ttu-id="9d6be-154">**Пример**</span><span class="sxs-lookup"><span data-stu-id="9d6be-154">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="9d6be-155">StDev(Expression)</span><span class="sxs-lookup"><span data-stu-id="9d6be-155">STDEV(expression)</span></span>

<span data-ttu-id="9d6be-156">Возвращает статистическое стандартное отклонение всех значений в указанном выражении.</span><span class="sxs-lookup"><span data-stu-id="9d6be-156">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="9d6be-157">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="9d6be-157">**Arguments**</span></span>

<span data-ttu-id="9d6be-158">Коллекция (`Double`).</span><span class="sxs-lookup"><span data-stu-id="9d6be-158">A Collection(`Double`).</span></span>

<span data-ttu-id="9d6be-159">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="9d6be-159">**Return Value**</span></span>

<span data-ttu-id="9d6be-160">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="9d6be-160">A `Double`.</span></span>

<span data-ttu-id="9d6be-161">**Пример**</span><span class="sxs-lookup"><span data-stu-id="9d6be-161">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="9d6be-162">STDEVP(Expression)</span><span class="sxs-lookup"><span data-stu-id="9d6be-162">STDEVP(expression)</span></span>

<span data-ttu-id="9d6be-163">Возвращает статистическое стандартное отклонение совокупности всех значений в указанном выражении.</span><span class="sxs-lookup"><span data-stu-id="9d6be-163">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="9d6be-164">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="9d6be-164">**Arguments**</span></span>

<span data-ttu-id="9d6be-165">Коллекция (`Double`).</span><span class="sxs-lookup"><span data-stu-id="9d6be-165">A Collection(`Double`).</span></span>

<span data-ttu-id="9d6be-166">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="9d6be-166">**Return Value**</span></span>

<span data-ttu-id="9d6be-167">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="9d6be-167">A `Double`.</span></span>

<span data-ttu-id="9d6be-168">**Пример**</span><span class="sxs-lookup"><span data-stu-id="9d6be-168">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="9d6be-169">SUM(Expression)</span><span class="sxs-lookup"><span data-stu-id="9d6be-169">SUM(expression)</span></span>

<span data-ttu-id="9d6be-170">Возвращает сумму всех значений в коллекции.</span><span class="sxs-lookup"><span data-stu-id="9d6be-170">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="9d6be-171">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="9d6be-171">**Arguments**</span></span>

<span data-ttu-id="9d6be-172">Collection(T), где T — один из следующих типов: `Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="9d6be-172">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="9d6be-173">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="9d6be-173">**Return Value**</span></span>

<span data-ttu-id="9d6be-174">Тип параметра `expression`.</span><span class="sxs-lookup"><span data-stu-id="9d6be-174">The type of `expression`.</span></span>

<span data-ttu-id="9d6be-175">**Пример**</span><span class="sxs-lookup"><span data-stu-id="9d6be-175">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="9d6be-176">VAR(Expression)</span><span class="sxs-lookup"><span data-stu-id="9d6be-176">VAR(expression)</span></span>

<span data-ttu-id="9d6be-177">Возвращает статистическую дисперсию всех значений в указанном выражении.</span><span class="sxs-lookup"><span data-stu-id="9d6be-177">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="9d6be-178">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="9d6be-178">**Arguments**</span></span>

<span data-ttu-id="9d6be-179">Коллекция (`Double`).</span><span class="sxs-lookup"><span data-stu-id="9d6be-179">A Collection(`Double`).</span></span>

<span data-ttu-id="9d6be-180">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="9d6be-180">**Return Value**</span></span>

<span data-ttu-id="9d6be-181">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="9d6be-181">A `Double`.</span></span>

<span data-ttu-id="9d6be-182">**Пример**</span><span class="sxs-lookup"><span data-stu-id="9d6be-182">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="9d6be-183">VARP(Expression)</span><span class="sxs-lookup"><span data-stu-id="9d6be-183">VARP(expression)</span></span>

<span data-ttu-id="9d6be-184">Возвращает статистическую дисперсию совокупности всех значений в указанном выражении.</span><span class="sxs-lookup"><span data-stu-id="9d6be-184">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="9d6be-185">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="9d6be-185">**Arguments**</span></span>

<span data-ttu-id="9d6be-186">Коллекция (`Double`).</span><span class="sxs-lookup"><span data-stu-id="9d6be-186">A Collection(`Double`).</span></span>

<span data-ttu-id="9d6be-187">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="9d6be-187">**Return Value**</span></span>

<span data-ttu-id="9d6be-188">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="9d6be-188">A `Double`.</span></span>

<span data-ttu-id="9d6be-189">**Пример**</span><span class="sxs-lookup"><span data-stu-id="9d6be-189">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="9d6be-190">См. также</span><span class="sxs-lookup"><span data-stu-id="9d6be-190">See also</span></span>

<span data-ttu-id="9d6be-191">Дополнительные сведения об агрегатных функциях, поддерживаемых SqlClient, см. в документации к версии SQL Server, указанной в манифесте поставщика SqlClient.</span><span class="sxs-lookup"><span data-stu-id="9d6be-191">For more information about the aggregate functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>

- <span data-ttu-id="9d6be-192">**SQL Server 2005:** [Агрегатные функции (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="9d6be-192">**SQL Server 2005:** [Aggregate Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span></span>
- <span data-ttu-id="9d6be-193">**SQL Server 2008 и более поздних версий:** [Агрегатные функции (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="9d6be-193">**SQL Server 2008 and later:** [Aggregate Functions (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span></span>

- [<span data-ttu-id="9d6be-194">Язык Entity SQL</span><span class="sxs-lookup"><span data-stu-id="9d6be-194">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [<span data-ttu-id="9d6be-195">Статистические канонические функции</span><span class="sxs-lookup"><span data-stu-id="9d6be-195">Aggregate Canonical Functions</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)
