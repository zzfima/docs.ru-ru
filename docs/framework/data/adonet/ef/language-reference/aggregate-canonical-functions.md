---
title: Статистические канонические функции
ms.date: 03/30/2017
ms.assetid: 3bcff826-ca90-41b3-a791-04d6ff0e5085
ms.openlocfilehash: 3f4bb84c45e503fc0018e7869f3b41ddab4581a6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251356"
---
# <a name="aggregate-canonical-functions"></a><span data-ttu-id="ed364-102">Статистические канонические функции</span><span class="sxs-lookup"><span data-stu-id="ed364-102">Aggregate Canonical Functions</span></span>

<span data-ttu-id="ed364-103">Статистические выражения - выражения, которые уменьшают количество входных значений, например, до одного значения.</span><span class="sxs-lookup"><span data-stu-id="ed364-103">Aggregates are expressions that reduce a series of input values into, for example, a single value.</span></span> <span data-ttu-id="ed364-104">Статистические выражения обычно используются совместно с предложением группирования GROUP BY выражения SELECT, а на область их использования накладываются ограничения.</span><span class="sxs-lookup"><span data-stu-id="ed364-104">Aggregates are normally used in conjunction with the GROUP BY clause of the SELECT expression, and there are constraints on where they can be used.</span></span>

## <a name="aggregate-entity-sql-canonical-functions"></a><span data-ttu-id="ed364-105">Агрегатные Entity SQL канонические функции</span><span class="sxs-lookup"><span data-stu-id="ed364-105">Aggregate Entity SQL canonical functions</span></span>

<span data-ttu-id="ed364-106">Ниже приведены агрегатные Entity SQL канонических функциях.</span><span class="sxs-lookup"><span data-stu-id="ed364-106">The following are the aggregate Entity SQL canonical functions.</span></span>

### <a name="avgexpression"></a><span data-ttu-id="ed364-107">Avg(expression)</span><span class="sxs-lookup"><span data-stu-id="ed364-107">Avg(expression)</span></span>

<span data-ttu-id="ed364-108">Возвращает среднее для значений, отличных от NULL.</span><span class="sxs-lookup"><span data-stu-id="ed364-108">Returns the average of the non-null values.</span></span>

<span data-ttu-id="ed364-109">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="ed364-109">**Arguments**</span></span>

<span data-ttu-id="ed364-110">`Int32` ,`Int64`, И .`Decimal` `Double`</span><span class="sxs-lookup"><span data-stu-id="ed364-110">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="ed364-111">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="ed364-111">**Return Value**</span></span>

<span data-ttu-id="ed364-112">Тип `expression` `null` или `null` значение, если все входные значения являются значениями.</span><span class="sxs-lookup"><span data-stu-id="ed364-112">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="ed364-113">**Пример**</span><span class="sxs-lookup"><span data-stu-id="ed364-113">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)]
[!code-sql[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)]

### <a name="bigcountexpression"></a><span data-ttu-id="ed364-114">BigCount(expression)</span><span class="sxs-lookup"><span data-stu-id="ed364-114">BigCount(expression)</span></span>

<span data-ttu-id="ed364-115">Возвращает объем данных, подвергаемых статистической обработке, включая значения NULL и повторяющиеся значения.</span><span class="sxs-lookup"><span data-stu-id="ed364-115">Returns the size of the aggregate including null and duplicate values.</span></span>

<span data-ttu-id="ed364-116">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="ed364-116">**Arguments**</span></span>

<span data-ttu-id="ed364-117">Любой тип.</span><span class="sxs-lookup"><span data-stu-id="ed364-117">Any type.</span></span>

<span data-ttu-id="ed364-118">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="ed364-118">**Return Value**</span></span>

<span data-ttu-id="ed364-119">Объект `Int64`.</span><span class="sxs-lookup"><span data-stu-id="ed364-119">An `Int64`.</span></span>

<span data-ttu-id="ed364-120">**Пример**</span><span class="sxs-lookup"><span data-stu-id="ed364-120">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_bigcount)]
[!code-sql[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_bigcount)]

### <a name="countexpression"></a><span data-ttu-id="ed364-121">Count(expression)</span><span class="sxs-lookup"><span data-stu-id="ed364-121">Count(expression)</span></span>

<span data-ttu-id="ed364-122">Возвращает объем данных, подвергаемых статистической обработке, включая значения NULL и повторяющиеся значения.</span><span class="sxs-lookup"><span data-stu-id="ed364-122">Returns the size of the aggregate including null and duplicate values.</span></span>

<span data-ttu-id="ed364-123">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="ed364-123">**Arguments**</span></span>

<span data-ttu-id="ed364-124">Любой тип.</span><span class="sxs-lookup"><span data-stu-id="ed364-124">Any type.</span></span>

<span data-ttu-id="ed364-125">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="ed364-125">**Return Value**</span></span>

<span data-ttu-id="ed364-126">Объект `Int32`.</span><span class="sxs-lookup"><span data-stu-id="ed364-126">An `Int32`.</span></span>

<span data-ttu-id="ed364-127">**Пример**</span><span class="sxs-lookup"><span data-stu-id="ed364-127">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_count)]
[!code-sql[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_count)]

### <a name="maxexpression"></a><span data-ttu-id="ed364-128">Max(expression)</span><span class="sxs-lookup"><span data-stu-id="ed364-128">Max(expression)</span></span>

<span data-ttu-id="ed364-129">Возвращает максимум для значений, отличных от NULL.</span><span class="sxs-lookup"><span data-stu-id="ed364-129">Returns the maximum of the non-null values.</span></span>

<span data-ttu-id="ed364-130">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="ed364-130">**Arguments**</span></span>

<span data-ttu-id="ed364-131">Значения типа `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span><span class="sxs-lookup"><span data-stu-id="ed364-131">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span></span>

<span data-ttu-id="ed364-132">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="ed364-132">**Return Value**</span></span>

<span data-ttu-id="ed364-133">Тип `expression` `null` или `null` значение, если все входные значения являются значениями.</span><span class="sxs-lookup"><span data-stu-id="ed364-133">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="ed364-134">**Пример**</span><span class="sxs-lookup"><span data-stu-id="ed364-134">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_max)]
[!code-sql[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_max)]

### <a name="minexpression"></a><span data-ttu-id="ed364-135">Min(expression)</span><span class="sxs-lookup"><span data-stu-id="ed364-135">Min(expression)</span></span>

<span data-ttu-id="ed364-136">Возвращает минимум для значений, отличных от NULL.</span><span class="sxs-lookup"><span data-stu-id="ed364-136">Returns the minimum of the non-null values.</span></span>

<span data-ttu-id="ed364-137">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="ed364-137">**Arguments**</span></span>

<span data-ttu-id="ed364-138">Значения типа `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span><span class="sxs-lookup"><span data-stu-id="ed364-138">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span></span>

<span data-ttu-id="ed364-139">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="ed364-139">**Return Value**</span></span>

<span data-ttu-id="ed364-140">Тип `expression` `null` или `null` значение, если все входные значения являются значениями.</span><span class="sxs-lookup"><span data-stu-id="ed364-140">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="ed364-141">**Пример**</span><span class="sxs-lookup"><span data-stu-id="ed364-141">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_min)]
[!code-sql[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_min)]

### <a name="stdevexpression"></a><span data-ttu-id="ed364-142">StDev(expression)</span><span class="sxs-lookup"><span data-stu-id="ed364-142">StDev(expression)</span></span>

<span data-ttu-id="ed364-143">Возвращает стандартное отклонение для значений, отличных от NULL.</span><span class="sxs-lookup"><span data-stu-id="ed364-143">Returns the standard deviation of the non-null values.</span></span>

<span data-ttu-id="ed364-144">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="ed364-144">**Arguments**</span></span>

<span data-ttu-id="ed364-145">Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ed364-145">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="ed364-146">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="ed364-146">**Return Value**</span></span>

<span data-ttu-id="ed364-147">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="ed364-147">A `Double`.</span></span> <span data-ttu-id="ed364-148">Возвращает `Null`, если все входные значения представляют собой значения `null`.</span><span class="sxs-lookup"><span data-stu-id="ed364-148">`Null`, if all input values are `null` values.</span></span>

<span data-ttu-id="ed364-149">**Пример**</span><span class="sxs-lookup"><span data-stu-id="ed364-149">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdev)]
[!code-sql[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdev)]

### <a name="stdevpexpression"></a><span data-ttu-id="ed364-150">StDevP(expression)</span><span class="sxs-lookup"><span data-stu-id="ed364-150">StDevP(expression)</span></span>

<span data-ttu-id="ed364-151">Возвращает стандартное отклонение для заполнения по всем значениям.</span><span class="sxs-lookup"><span data-stu-id="ed364-151">Returns the standard deviation for the population of all values.</span></span>

<span data-ttu-id="ed364-152">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="ed364-152">**Arguments**</span></span>

<span data-ttu-id="ed364-153">Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ed364-153">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="ed364-154">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="ed364-154">**Return Value**</span></span>

<span data-ttu-id="ed364-155">А `Double` `null` или `null` , если все входные значения являются значениями.</span><span class="sxs-lookup"><span data-stu-id="ed364-155">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="ed364-156">**Пример**</span><span class="sxs-lookup"><span data-stu-id="ed364-156">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdevp)]
[!code-sql[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdevp)]

### <a name="sumexpression"></a><span data-ttu-id="ed364-157">Sum(expression)</span><span class="sxs-lookup"><span data-stu-id="ed364-157">Sum(expression)</span></span>

<span data-ttu-id="ed364-158">Возвращает сумму для значений, отличных от NULL.</span><span class="sxs-lookup"><span data-stu-id="ed364-158">Returns the sum of the non-null values.</span></span>

<span data-ttu-id="ed364-159">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="ed364-159">**Arguments**</span></span>

<span data-ttu-id="ed364-160">Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ed364-160">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="ed364-161">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="ed364-161">**Return Value**</span></span>

<span data-ttu-id="ed364-162">А `Double` `null` или `null` , если все входные значения являются значениями.</span><span class="sxs-lookup"><span data-stu-id="ed364-162">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="ed364-163">**Пример**</span><span class="sxs-lookup"><span data-stu-id="ed364-163">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_sum)]
[!code-sql[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_sum)]

### <a name="varexpression"></a><span data-ttu-id="ed364-164">Var(expression)</span><span class="sxs-lookup"><span data-stu-id="ed364-164">Var(expression)</span></span>

<span data-ttu-id="ed364-165">Возвращает дисперсию всех значений, отличных от NULL.</span><span class="sxs-lookup"><span data-stu-id="ed364-165">Returns the variance of all non-null values.</span></span>

<span data-ttu-id="ed364-166">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="ed364-166">**Arguments**</span></span>

<span data-ttu-id="ed364-167">Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ed364-167">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="ed364-168">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="ed364-168">**Return Value**</span></span>

<span data-ttu-id="ed364-169">А `Double` `null` или `null` , если все входные значения являются значениями.</span><span class="sxs-lookup"><span data-stu-id="ed364-169">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="ed364-170">**Пример**</span><span class="sxs-lookup"><span data-stu-id="ed364-170">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_var)]
[!code-sql[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_var)]

### <a name="varpexpression"></a><span data-ttu-id="ed364-171">VarP(expression)</span><span class="sxs-lookup"><span data-stu-id="ed364-171">VarP(expression)</span></span>

<span data-ttu-id="ed364-172">Возвращает дисперсию для заполнения по всем значениям, отличным от NULL.</span><span class="sxs-lookup"><span data-stu-id="ed364-172">Returns the variance for the population of all non-null values.</span></span>

<span data-ttu-id="ed364-173">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="ed364-173">**Arguments**</span></span>

<span data-ttu-id="ed364-174">Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ed364-174">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="ed364-175">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="ed364-175">**Return Value**</span></span>

<span data-ttu-id="ed364-176">А `Double` `null` или `null` , если все входные значения являются значениями.</span><span class="sxs-lookup"><span data-stu-id="ed364-176">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="ed364-177">**Пример**</span><span class="sxs-lookup"><span data-stu-id="ed364-177">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_varp)]
[!code-sql[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_varp)]

<span data-ttu-id="ed364-178">Эквивалентную функциональность предоставляет управляемый поставщик клиента Microsoft SQL.</span><span class="sxs-lookup"><span data-stu-id="ed364-178">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="ed364-179">Дополнительные сведения см. в разделе [SqlClient для функций Entity Framework](../sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="ed364-179">For more information, see [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).</span></span>

## <a name="collection-based-aggregates"></a><span data-ttu-id="ed364-180">Статистические выражения на основе коллекций</span><span class="sxs-lookup"><span data-stu-id="ed364-180">Collection-based aggregates</span></span>

<span data-ttu-id="ed364-181">Статистические функции на основе коллекций (функции коллекций) работают с коллекциями и возвращают значение.</span><span class="sxs-lookup"><span data-stu-id="ed364-181">Collection-based aggregates (collection functions) operate on collections and return a value.</span></span> <span data-ttu-id="ed364-182">Например, если ORDERs является коллекцией всех заказов, можно вычислить самую раннюю дату отгрузки с помощью следующего выражения:</span><span class="sxs-lookup"><span data-stu-id="ed364-182">For example if ORDERS is a collection of all orders, you can calculate the earliest ship date with the following expression:</span></span>

```sql
min(select value o.ShipDate from LOB.Orders as o)
```

<span data-ttu-id="ed364-183">Выражения внутри статистических функций на основе коллекций вычисляются в текущей внешней области разрешения имен.</span><span class="sxs-lookup"><span data-stu-id="ed364-183">Expressions inside collection-based aggregates are evaluated within the current ambient name-resolution scope.</span></span>

## <a name="group-based-aggregates"></a><span data-ttu-id="ed364-184">Статистические выражения на основе групп</span><span class="sxs-lookup"><span data-stu-id="ed364-184">Group-based aggregates</span></span>

<span data-ttu-id="ed364-185">Статистические функции на основе групп вычисляются для группы, определенной предложением GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="ed364-185">Group-based aggregates are calculated over a group as defined by the GROUP BY clause.</span></span> <span data-ttu-id="ed364-186">Для каждой группы результата выполняется отдельное статистическое вычисление с использованием элементов каждой группы в качестве входных значений.</span><span class="sxs-lookup"><span data-stu-id="ed364-186">For each group in the result, a separate aggregate is calculated by using the elements in each group as input to the aggregate calculation.</span></span> <span data-ttu-id="ed364-187">Если в выражении SELECT используется предложение группирования, в проекции или предложении сортировки могут употребляться только имена выражений группирования, статистические функции или константные выражения.</span><span class="sxs-lookup"><span data-stu-id="ed364-187">When a group-by clause is used in a select expression, only grouping expression names, aggregates, or constant expressions can be present in the projection or order-by clause.</span></span>

<span data-ttu-id="ed364-188">В следующем примере вычисляется средняя величина заказа для каждого продукта.</span><span class="sxs-lookup"><span data-stu-id="ed364-188">The following example calculates the average quantity ordered for each product:</span></span>

```sql
select p, avg(ol.Quantity) from LOB.OrderLines as ol
  group by ol.Product as p
```

<span data-ttu-id="ed364-189">Можно использовать статистическое выражение на основе групп без явного предложения GROUP-BY в выражении SELECT.</span><span class="sxs-lookup"><span data-stu-id="ed364-189">It's possible to have a group-based aggregate without an explicit group-by clause in the SELECT expression.</span></span> <span data-ttu-id="ed364-190">В этом случае все элементы рассматриваются как одна группа.</span><span class="sxs-lookup"><span data-stu-id="ed364-190">In this case, all elements are treated as a single group.</span></span> <span data-ttu-id="ed364-191">Это эквивалентно указанию группирования на основе константы.</span><span class="sxs-lookup"><span data-stu-id="ed364-191">This is equivalent of specifying a grouping based on a constant.</span></span> <span data-ttu-id="ed364-192">Например, выражение:</span><span class="sxs-lookup"><span data-stu-id="ed364-192">Take, for example, the following expression:</span></span>

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol
```

<span data-ttu-id="ed364-193">Оно эквивалентно следующему выражению:</span><span class="sxs-lookup"><span data-stu-id="ed364-193">This is equivalent to the following:</span></span>

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol group by 1
```

<span data-ttu-id="ed364-194">Выражения внутри статистической функции на основе групп вычисляются в области разрешения имен, видимой для выражения предложения WHERE.</span><span class="sxs-lookup"><span data-stu-id="ed364-194">Expressions inside the group-based aggregate are evaluated within the name-resolution scope that would be visible to the WHERE clause expression.</span></span>

<span data-ttu-id="ed364-195">Как и в Transact-SQL, статистические выражения на основе групп могут также задавать модификатор ALL или DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="ed364-195">As in Transact-SQL, group-based aggregates can also specify an ALL or DISTINCT modifier.</span></span> <span data-ttu-id="ed364-196">Если задан модификатор DISTINCT, то перед вычислением статистической функции из входного набора исключаются повторяющиеся значения.</span><span class="sxs-lookup"><span data-stu-id="ed364-196">If the DISTINCT modifier is specified, duplicates are eliminated from the aggregate input collection, before the aggregate is computed.</span></span> <span data-ttu-id="ed364-197">Если задан модификатор ALL (или не указан никакой модификатор), то исключение повторяющихся значений не выполняется.</span><span class="sxs-lookup"><span data-stu-id="ed364-197">If the ALL modifier is specified (or if no modifier is specified), no duplicate elimination is performed.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed364-198">См. также</span><span class="sxs-lookup"><span data-stu-id="ed364-198">See also</span></span>

- [<span data-ttu-id="ed364-199">Канонические функции</span><span class="sxs-lookup"><span data-stu-id="ed364-199">Canonical Functions</span></span>](canonical-functions.md)
