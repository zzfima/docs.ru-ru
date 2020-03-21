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
# <a name="mathematical-functions"></a><span data-ttu-id="8ed21-102">Математические функции</span><span class="sxs-lookup"><span data-stu-id="8ed21-102">Mathematical Functions</span></span>

<span data-ttu-id="8ed21-103">Поставщик данных для SQL Server платформы .NET Framework (SqlClient) предоставляет математические функции, производящие вычисления на входящих значениях, предоставляемых в качестве аргументов, и возвращающие результат в виде числовых значений.</span><span class="sxs-lookup"><span data-stu-id="8ed21-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="8ed21-104">Эти функции находятся в пространстве имен SqlServer, которое доступно при использовании SqlClient.</span><span class="sxs-lookup"><span data-stu-id="8ed21-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="8ed21-105">Свойство пространства имен поставщика позволяет платформе Entity Framework узнать, какой префикс используется поставщиком для конкретных конструкций, таких как типы или функции.</span><span class="sxs-lookup"><span data-stu-id="8ed21-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="8ed21-106">В следующей таблице описаны математические функции SqlClient.</span><span class="sxs-lookup"><span data-stu-id="8ed21-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="8ed21-107">АБС (выражение)</span><span class="sxs-lookup"><span data-stu-id="8ed21-107">ABS(expression)</span></span>

<span data-ttu-id="8ed21-108">Возвращает абсолютное значение.</span><span class="sxs-lookup"><span data-stu-id="8ed21-108">Performs the absolute value function.</span></span>

<span data-ttu-id="8ed21-109">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-109">**Arguments**</span></span>

<span data-ttu-id="8ed21-110">`expression`: значение типа `Int32`, `Int64`, `Double` или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="8ed21-111">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-111">**Return Value**</span></span>

<span data-ttu-id="8ed21-112">Абсолютное значение заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="8ed21-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="8ed21-113">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="8ed21-114">ACOS (выражение)</span><span class="sxs-lookup"><span data-stu-id="8ed21-114">ACOS(expression)</span></span>

<span data-ttu-id="8ed21-115">Возвращает значение арккосинуса указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="8ed21-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="8ed21-116">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-116">**Arguments**</span></span>

<span data-ttu-id="8ed21-117">`expression` — значение в формате `Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="8ed21-118">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-118">**Return Value**</span></span>

<span data-ttu-id="8ed21-119">`Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-119">A `Double`.</span></span>

<span data-ttu-id="8ed21-120">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="8ed21-121">ASIN (выражение)</span><span class="sxs-lookup"><span data-stu-id="8ed21-121">ASIN(expression)</span></span>

<span data-ttu-id="8ed21-122">Возвращает значение арксинуса указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="8ed21-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="8ed21-123">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-123">**Arguments**</span></span>

<span data-ttu-id="8ed21-124">`expression` — значение в формате `Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="8ed21-125">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-125">**Return Value**</span></span>

<span data-ttu-id="8ed21-126">`Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-126">A `Double`.</span></span>

<span data-ttu-id="8ed21-127">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="8ed21-128">АТАН (ВЫРАЖЕНИЕ)</span><span class="sxs-lookup"><span data-stu-id="8ed21-128">ATAN(expression)</span></span>

<span data-ttu-id="8ed21-129">Возвращает значение арктангенса указанного числового выражения.</span><span class="sxs-lookup"><span data-stu-id="8ed21-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="8ed21-130">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-130">**Arguments**</span></span>

<span data-ttu-id="8ed21-131">`expression` — значение в формате `Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="8ed21-132">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-132">**Return Value**</span></span>

<span data-ttu-id="8ed21-133">`Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-133">A `Double`.</span></span>

<span data-ttu-id="8ed21-134">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="8ed21-135">ATN2 (выражение, выражение)</span><span class="sxs-lookup"><span data-stu-id="8ed21-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="8ed21-136">Возвращает угол в радианах, тангенс которого находится в диапазоне между двумя заданными числовыми выражениями.</span><span class="sxs-lookup"><span data-stu-id="8ed21-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="8ed21-137">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-137">**Arguments**</span></span>

<span data-ttu-id="8ed21-138">`expression` — значение в формате `Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="8ed21-139">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-139">**Return Value**</span></span>

<span data-ttu-id="8ed21-140">`Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-140">A `Double`.</span></span>

<span data-ttu-id="8ed21-141">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`

## <a name="ceilingexpression"></a><span data-ttu-id="8ed21-142">CEILING (выражение)</span><span class="sxs-lookup"><span data-stu-id="8ed21-142">CEILING(expression)</span></span>

<span data-ttu-id="8ed21-143">Преобразует указанное выражение в наименьшее целое число, большее или равное данному выражению.</span><span class="sxs-lookup"><span data-stu-id="8ed21-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="8ed21-144">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-144">**Arguments**</span></span>

<span data-ttu-id="8ed21-145">`expression`: значение типа `Int32`, `Int64`, `Double` или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="8ed21-146">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-146">**Return Value**</span></span>

<span data-ttu-id="8ed21-147">An `Int32` `Int64`, `Double`, `Decimal`или .</span><span class="sxs-lookup"><span data-stu-id="8ed21-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="8ed21-148">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-148">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="8ed21-149">COS (выражение)</span><span class="sxs-lookup"><span data-stu-id="8ed21-149">COS(expression)</span></span>

<span data-ttu-id="8ed21-150">Вычисляет тригонометрический косинус указанного угла в радианах.</span><span class="sxs-lookup"><span data-stu-id="8ed21-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span>

<span data-ttu-id="8ed21-151">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-151">**Arguments**</span></span>

<span data-ttu-id="8ed21-152">`expression` — значение в формате `Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-152">`expression`: A `Double`.</span></span>

<span data-ttu-id="8ed21-153">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-153">**Return Value**</span></span>

<span data-ttu-id="8ed21-154">`Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-154">A `Double`.</span></span>

<span data-ttu-id="8ed21-155">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-155">**Example**</span></span>

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="8ed21-156">КОТ (выражение)</span><span class="sxs-lookup"><span data-stu-id="8ed21-156">COT(expression)</span></span>

<span data-ttu-id="8ed21-157">Вычисляет тригонометрический котангенс указанного угла в радианах.</span><span class="sxs-lookup"><span data-stu-id="8ed21-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span>

<span data-ttu-id="8ed21-158">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-158">**Arguments**</span></span>

<span data-ttu-id="8ed21-159">`expression` — значение в формате `Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-159">`expression`: A `Double`.</span></span>

<span data-ttu-id="8ed21-160">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-160">**Return Value**</span></span>

<span data-ttu-id="8ed21-161">`Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-161">A `Double`.</span></span>

<span data-ttu-id="8ed21-162">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-162">**Example**</span></span>

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="8ed21-163">DEGREES (радианы)</span><span class="sxs-lookup"><span data-stu-id="8ed21-163">DEGREES(radians)</span></span>

<span data-ttu-id="8ed21-164">Возвращает соответствующее значение угла в градусах.</span><span class="sxs-lookup"><span data-stu-id="8ed21-164">Returns the corresponding angle in degrees.</span></span>

<span data-ttu-id="8ed21-165">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-165">**Arguments**</span></span>

<span data-ttu-id="8ed21-166">`expression`: значение типа `Int32`, `Int64`, `Double` или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="8ed21-167">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-167">**Return Value**</span></span>

<span data-ttu-id="8ed21-168">An `Int32` `Int64`, `Double`, `Decimal`или .</span><span class="sxs-lookup"><span data-stu-id="8ed21-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="8ed21-169">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-169">**Example**</span></span>

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="8ed21-170">EXP (выражение)</span><span class="sxs-lookup"><span data-stu-id="8ed21-170">EXP(expression)</span></span>

<span data-ttu-id="8ed21-171">Вычисляет экспоненту заданного числового выражения.</span><span class="sxs-lookup"><span data-stu-id="8ed21-171">Calculates the exponential value of a specified numeric expression.</span></span>

<span data-ttu-id="8ed21-172">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-172">**Arguments**</span></span>

<span data-ttu-id="8ed21-173">`expression` — значение в формате `Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-173">`expression`: A `Double`.</span></span>

<span data-ttu-id="8ed21-174">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-174">**Return Value**</span></span>

<span data-ttu-id="8ed21-175">`Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-175">A `Double`.</span></span>

<span data-ttu-id="8ed21-176">**Пример**`SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="8ed21-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="8ed21-177">FLOOR (выражение)</span><span class="sxs-lookup"><span data-stu-id="8ed21-177">FLOOR(expression)</span></span>

<span data-ttu-id="8ed21-178">Преобразует указанное выражение в наибольшее целое число, меньшее или равное данному выражению.</span><span class="sxs-lookup"><span data-stu-id="8ed21-178">Converts the specified expression to the largest integer less than or equal to it.</span></span>

<span data-ttu-id="8ed21-179">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-179">**Arguments**</span></span>

<span data-ttu-id="8ed21-180">`expression` — значение в формате `Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-180">`expression`: A `Double`.</span></span>

<span data-ttu-id="8ed21-181">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-181">**Return Value**</span></span>

<span data-ttu-id="8ed21-182">`Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-182">A `Double`.</span></span>

<span data-ttu-id="8ed21-183">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-183">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="8ed21-184">LOG (выражение)</span><span class="sxs-lookup"><span data-stu-id="8ed21-184">LOG(expression)</span></span>

<span data-ttu-id="8ed21-185">Вычисляет натуральный логарифм заданного выражения типа `float`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-185">Calculates the natural logarithm of the specified `float` expression.</span></span>

<span data-ttu-id="8ed21-186">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-186">**Arguments**</span></span>

<span data-ttu-id="8ed21-187">`expression` — значение в формате `Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-187">`expression`: A `Double`.</span></span>

<span data-ttu-id="8ed21-188">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-188">**Return Value**</span></span>

<span data-ttu-id="8ed21-189">`Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-189">A `Double`.</span></span>

<span data-ttu-id="8ed21-190">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-190">**Example**</span></span>

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="8ed21-191">LOG10 (выражение)</span><span class="sxs-lookup"><span data-stu-id="8ed21-191">LOG10(expression)</span></span>

<span data-ttu-id="8ed21-192">Возвращает десятичный логарифм указанного выражения типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span>

<span data-ttu-id="8ed21-193">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-193">**Arguments**</span></span>

<span data-ttu-id="8ed21-194">`expression` — значение в формате `Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-194">`expression`: A `Double`.</span></span>

<span data-ttu-id="8ed21-195">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-195">**Return Value**</span></span>

<span data-ttu-id="8ed21-196">`Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-196">A `Double`.</span></span>

<span data-ttu-id="8ed21-197">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-197">**Example**</span></span>

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="8ed21-198">PI()</span><span class="sxs-lookup"><span data-stu-id="8ed21-198">PI()</span></span>

<span data-ttu-id="8ed21-199">Возвращает константу «пи» в виде значения типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-199">Returns the constant value of pi as a `Double`.</span></span>

<span data-ttu-id="8ed21-200">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-200">**Return Value**</span></span>

<span data-ttu-id="8ed21-201">`Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-201">A `Double`.</span></span>

<span data-ttu-id="8ed21-202">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-202">**Example**</span></span>

`SqlServer.PI()`

## <a name="powernumeric_expression-power_expression"></a><span data-ttu-id="8ed21-203">POWER (numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="8ed21-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="8ed21-204">Вычисляет значение указанного выражения, возведенного в заданную степень.</span><span class="sxs-lookup"><span data-stu-id="8ed21-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="8ed21-205">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-205">**Arguments**</span></span>

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="8ed21-206">An `Int32` `Int64`, `Double`, `Decimal`или .</span><span class="sxs-lookup"><span data-stu-id="8ed21-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="8ed21-207">A, `Double` который представляет собой власть, к которой поднять `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>|

<span data-ttu-id="8ed21-208">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-208">**Return Value**</span></span>

<span data-ttu-id="8ed21-209">Значение заданного выражения `numeric_expression` в указанной степени `power_expression`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="8ed21-210">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-210">**Example**</span></span>

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="8ed21-211">РАДИАНС (выражение)</span><span class="sxs-lookup"><span data-stu-id="8ed21-211">RADIANS(expression)</span></span>

<span data-ttu-id="8ed21-212">Преобразует градусы в радианы.</span><span class="sxs-lookup"><span data-stu-id="8ed21-212">Converts degrees to radians.</span></span>

<span data-ttu-id="8ed21-213">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-213">**Arguments**</span></span>

<span data-ttu-id="8ed21-214">`expression`: значение типа `Int32`, `Int64`, `Double` или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="8ed21-215">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-215">**Return Value**</span></span>

<span data-ttu-id="8ed21-216">An `Int32` `Int64`, `Double`, `Decimal`или .</span><span class="sxs-lookup"><span data-stu-id="8ed21-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="8ed21-217">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-217">**Example**</span></span>

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="8ed21-218">RAND («семя»)</span><span class="sxs-lookup"><span data-stu-id="8ed21-218">RAND([seed])</span></span>

<span data-ttu-id="8ed21-219">Возвращает случайное значение от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="8ed21-219">Returns a random value from 0 through 1.</span></span>

<span data-ttu-id="8ed21-220">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-220">**Arguments**</span></span>

<span data-ttu-id="8ed21-221">Значение семян как `Int32`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="8ed21-222">Если начальное значение не задано, то компонент SQL Server Database Engine присваивает случайно выбранное начальное значение.</span><span class="sxs-lookup"><span data-stu-id="8ed21-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="8ed21-223">Для указанного начального значения возвращаемый результат всегда будет один и тот же.</span><span class="sxs-lookup"><span data-stu-id="8ed21-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="8ed21-224">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-224">**Return Value**</span></span>

<span data-ttu-id="8ed21-225">Случайное значение типа `Double` от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="8ed21-225">A random `Double` value from 0 through 1.</span></span>

<span data-ttu-id="8ed21-226">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-226">**Example**</span></span>

`SqlServer.RAND()`
  
## <a name="roundnumeric_expression-lengthfunction"></a><span data-ttu-id="8ed21-227">ROUND (numeric_expression, длина, функция)</span><span class="sxs-lookup"><span data-stu-id="8ed21-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="8ed21-228">Возвращает числовое выражение, округленное до указанной длины или точности.</span><span class="sxs-lookup"><span data-stu-id="8ed21-228">Returns a numeric expression, rounded to the specified length or precision.</span></span>

<span data-ttu-id="8ed21-229">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-229">**Arguments**</span></span>

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="8ed21-230">An `Int32` `Int64`, `Double`, `Decimal`или .</span><span class="sxs-lookup"><span data-stu-id="8ed21-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>
|`length`| <span data-ttu-id="8ed21-231">Значение типа `Int32`, указывающее точность, до которой должно быть округлено значение аргумента `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="8ed21-232">Если аргумент `length` является положительным числом, значение `numeric_expression` округляется до числа десятичных разрядов, указанных аргументом `length`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="8ed21-233">Если аргумент `length` является отрицательным числом, значение `numeric_expression` округляется слева от десятичной запятой, как указано аргументом `length`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="8ed21-234">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8ed21-234">Optional.</span></span> <span data-ttu-id="8ed21-235">Тип `Int32` операции представляет собой тип операции.</span><span class="sxs-lookup"><span data-stu-id="8ed21-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="8ed21-236">Когда функция опущена или имеет значение 0 `numeric_expression` (по умолчанию), округляется.</span><span class="sxs-lookup"><span data-stu-id="8ed21-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="8ed21-237">Когда значение, не превышающее 0, усечено. `numeric_expression`</span><span class="sxs-lookup"><span data-stu-id="8ed21-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="8ed21-238">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-238">**Return Value**</span></span>

<span data-ttu-id="8ed21-239">Значение заданного выражения `numeric_expression` в указанной степени `power_expression`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="8ed21-240">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-240">**Example**</span></span>

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="8ed21-241">SIGN (выражение)</span><span class="sxs-lookup"><span data-stu-id="8ed21-241">SIGN(expression)</span></span>

<span data-ttu-id="8ed21-242">Возвращает положительное (+1), нулевое (0) или отрицательное (-1) значение, обозначающее знак заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="8ed21-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span>

<span data-ttu-id="8ed21-243">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-243">**Arguments**</span></span>

<span data-ttu-id="8ed21-244">`expression`: `Int32`, `Int64`, `Double` или `Decimal`</span><span class="sxs-lookup"><span data-stu-id="8ed21-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span>

<span data-ttu-id="8ed21-245">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-245">**Return Value**</span></span>

<span data-ttu-id="8ed21-246">An `Int32` `Int64`, `Double`, `Decimal`или .</span><span class="sxs-lookup"><span data-stu-id="8ed21-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="8ed21-247">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-247">**Example**</span></span>

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="8ed21-248">SIN (выражение)</span><span class="sxs-lookup"><span data-stu-id="8ed21-248">SIN(expression)</span></span>

<span data-ttu-id="8ed21-249">Вычисляет тригонометрический синус заданного угла в радианах и возвращает выражение типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span>

<span data-ttu-id="8ed21-250">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-250">**Arguments**</span></span>

<span data-ttu-id="8ed21-251">`expression` — значение в формате `Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-251">`expression`: A `Double`.</span></span>

<span data-ttu-id="8ed21-252">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-252">**Return Value**</span></span>

<span data-ttu-id="8ed21-253">`Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-253">A `Double`.</span></span>

<span data-ttu-id="8ed21-254">**Пример**`SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="8ed21-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="8ed21-255">СЗРТ (выражение)</span><span class="sxs-lookup"><span data-stu-id="8ed21-255">SQRT(expression)</span></span>

<span data-ttu-id="8ed21-256">Возвращает квадратный корень указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="8ed21-256">Returns the square root of the specified expression.</span></span>

<span data-ttu-id="8ed21-257">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-257">**Arguments**</span></span>

<span data-ttu-id="8ed21-258">`expression` — значение в формате `Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-258">`expression`: A `Double`.</span></span>

<span data-ttu-id="8ed21-259">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-259">**Return Value**</span></span>

<span data-ttu-id="8ed21-260">`Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-260">A `Double`.</span></span>

<span data-ttu-id="8ed21-261">**Пример**`SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="8ed21-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="8ed21-262">СКВАРЕ (выражение)</span><span class="sxs-lookup"><span data-stu-id="8ed21-262">SQUARE(expression)</span></span>

<span data-ttu-id="8ed21-263">Возвращает значение указанного выражения в квадрате.</span><span class="sxs-lookup"><span data-stu-id="8ed21-263">Returns the square of the specified expression.</span></span>

<span data-ttu-id="8ed21-264">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-264">**Arguments**</span></span>

<span data-ttu-id="8ed21-265">`expression` — значение в формате `Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-265">`expression`: A `Double`.</span></span>

<span data-ttu-id="8ed21-266">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-266">**Return Value**</span></span>

<span data-ttu-id="8ed21-267">`Double`.</span><span class="sxs-lookup"><span data-stu-id="8ed21-267">A `Double`.</span></span>

<span data-ttu-id="8ed21-268">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-268">**Example**</span></span>

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="8ed21-269">TAN (выражение)</span><span class="sxs-lookup"><span data-stu-id="8ed21-269">TAN(expression)</span></span>

<span data-ttu-id="8ed21-270">Вычисляет тангенс заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="8ed21-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="8ed21-271">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="8ed21-271">**Arguments**</span></span>

<span data-ttu-id="8ed21-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="8ed21-272">`expression`: `Double`</span></span>

<span data-ttu-id="8ed21-273">**Значение возврата**</span><span class="sxs-lookup"><span data-stu-id="8ed21-273">**Return Value**</span></span>

`Double`

<span data-ttu-id="8ed21-274">**Пример**</span><span class="sxs-lookup"><span data-stu-id="8ed21-274">**Example**</span></span>

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="8ed21-275">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8ed21-275">See also</span></span>

- [<span data-ttu-id="8ed21-276">Математические функции (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8ed21-276">Mathematical Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/mathematical-functions-transact-sql)
- [<span data-ttu-id="8ed21-277">Функции SqlClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="8ed21-277">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
