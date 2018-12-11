---
title: Математические функции
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 63f83532c399f77e268913da3198327345b9c2ee
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143679"
---
# <a name="mathematical-functions"></a><span data-ttu-id="96e4d-102">Математические функции</span><span class="sxs-lookup"><span data-stu-id="96e4d-102">Mathematical Functions</span></span>

<span data-ttu-id="96e4d-103">Поставщик данных для SQL Server платформы .NET Framework (SqlClient) предоставляет математические функции, производящие вычисления на входящих значениях, предоставляемых в качестве аргументов, и возвращающие результат в виде числовых значений.</span><span class="sxs-lookup"><span data-stu-id="96e4d-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="96e4d-104">Эти функции находятся в пространстве имен SqlServer, которое доступно при использовании SqlClient.</span><span class="sxs-lookup"><span data-stu-id="96e4d-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="96e4d-105">Свойство пространства имен поставщика позволяет платформе Entity Framework узнать, какой префикс используется поставщиком для конкретных конструкций, таких как типы или функции.</span><span class="sxs-lookup"><span data-stu-id="96e4d-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="96e4d-106">В следующей таблице описаны математические функции SqlClient.</span><span class="sxs-lookup"><span data-stu-id="96e4d-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="96e4d-107">ABS(Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-107">ABS(expression)</span></span>

<span data-ttu-id="96e4d-108">Возвращает абсолютное значение.</span><span class="sxs-lookup"><span data-stu-id="96e4d-108">Performs the absolute value function.</span></span>

<span data-ttu-id="96e4d-109">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-109">**Arguments**</span></span>

<span data-ttu-id="96e4d-110">`expression`: `Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="96e4d-111">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-111">**Return Value**</span></span>

<span data-ttu-id="96e4d-112">Абсолютное значение заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="96e4d-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="96e4d-113">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="96e4d-114">ACOS(Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-114">ACOS(expression)</span></span>

<span data-ttu-id="96e4d-115">Возвращает значение арккосинуса указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="96e4d-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="96e4d-116">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-116">**Arguments**</span></span>

<span data-ttu-id="96e4d-117">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="96e4d-118">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-118">**Return Value**</span></span>

<span data-ttu-id="96e4d-119">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-119">A `Double`.</span></span>

<span data-ttu-id="96e4d-120">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="96e4d-121">ASIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-121">ASIN(expression)</span></span>

<span data-ttu-id="96e4d-122">Возвращает значение арксинуса указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="96e4d-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="96e4d-123">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-123">**Arguments**</span></span>

<span data-ttu-id="96e4d-124">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="96e4d-125">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-125">**Return Value**</span></span>

<span data-ttu-id="96e4d-126">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-126">A `Double`.</span></span>

<span data-ttu-id="96e4d-127">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="96e4d-128">ATAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-128">ATAN(expression)</span></span>

<span data-ttu-id="96e4d-129">Возвращает значение арктангенса указанного числового выражения.</span><span class="sxs-lookup"><span data-stu-id="96e4d-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="96e4d-130">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-130">**Arguments**</span></span>

<span data-ttu-id="96e4d-131">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="96e4d-132">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-132">**Return Value**</span></span>

<span data-ttu-id="96e4d-133">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-133">A `Double`.</span></span>

<span data-ttu-id="96e4d-134">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="96e4d-135">ATN2(Expression, Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="96e4d-136">Возвращает угол в радианах, тангенс которого находится в диапазоне между двумя заданными числовыми выражениями.</span><span class="sxs-lookup"><span data-stu-id="96e4d-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="96e4d-137">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-137">**Arguments**</span></span>

<span data-ttu-id="96e4d-138">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="96e4d-139">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-139">**Return Value**</span></span>

<span data-ttu-id="96e4d-140">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-140">A `Double`.</span></span>

<span data-ttu-id="96e4d-141">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="96e4d-142">CEILING(Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-142">CEILING(expression)</span></span>

<span data-ttu-id="96e4d-143">Преобразует указанное выражение в наименьшее целое число, большее или равное данному выражению.</span><span class="sxs-lookup"><span data-stu-id="96e4d-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="96e4d-144">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-144">**Arguments**</span></span>

<span data-ttu-id="96e4d-145">`expression`: `Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="96e4d-146">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-146">**Return Value**</span></span>

<span data-ttu-id="96e4d-147">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="96e4d-148">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-148">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="96e4d-149">COS(Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-149">COS(expression)</span></span>

<span data-ttu-id="96e4d-150">Вычисляет тригонометрический косинус указанного угла в радианах.</span><span class="sxs-lookup"><span data-stu-id="96e4d-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="96e4d-151">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-151">**Arguments**</span></span> 

<span data-ttu-id="96e4d-152">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-152">`expression`: A `Double`.</span></span> 

<span data-ttu-id="96e4d-153">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-153">**Return Value**</span></span> 

<span data-ttu-id="96e4d-154">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-154">A `Double`.</span></span> 

<span data-ttu-id="96e4d-155">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-155">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="96e4d-156">COT(Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-156">COT(expression)</span></span>

<span data-ttu-id="96e4d-157">Вычисляет тригонометрический котангенс указанного угла в радианах.</span><span class="sxs-lookup"><span data-stu-id="96e4d-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="96e4d-158">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-158">**Arguments**</span></span> 

<span data-ttu-id="96e4d-159">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-159">`expression`: A `Double`.</span></span> 

<span data-ttu-id="96e4d-160">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-160">**Return Value**</span></span> 

<span data-ttu-id="96e4d-161">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-161">A `Double`.</span></span> 

<span data-ttu-id="96e4d-162">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-162">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="96e4d-163">DEGREES(RADIANS)</span><span class="sxs-lookup"><span data-stu-id="96e4d-163">DEGREES(radians)</span></span>

<span data-ttu-id="96e4d-164">Возвращает соответствующее значение угла в градусах.</span><span class="sxs-lookup"><span data-stu-id="96e4d-164">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="96e4d-165">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-165">**Arguments**</span></span> 

<span data-ttu-id="96e4d-166">`expression`: `Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="96e4d-167">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-167">**Return Value**</span></span> 

<span data-ttu-id="96e4d-168">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="96e4d-169">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-169">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="96e4d-170">EXP(Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-170">EXP(expression)</span></span>

<span data-ttu-id="96e4d-171">Вычисляет экспоненту заданного числового выражения.</span><span class="sxs-lookup"><span data-stu-id="96e4d-171">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="96e4d-172">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-172">**Arguments**</span></span> 

<span data-ttu-id="96e4d-173">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-173">`expression`: A `Double`.</span></span> 

<span data-ttu-id="96e4d-174">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-174">**Return Value**</span></span> 

<span data-ttu-id="96e4d-175">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-175">A `Double`.</span></span> 

<span data-ttu-id="96e4d-176">**Пример** `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="96e4d-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="96e4d-177">FLOOR(Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-177">FLOOR(expression)</span></span>

<span data-ttu-id="96e4d-178">Преобразует указанное выражение в наибольшее целое число, меньшее или равное данному выражению.</span><span class="sxs-lookup"><span data-stu-id="96e4d-178">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="96e4d-179">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-179">**Arguments**</span></span> 

<span data-ttu-id="96e4d-180">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-180">`expression`: A `Double`.</span></span> 

<span data-ttu-id="96e4d-181">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-181">**Return Value**</span></span> 

<span data-ttu-id="96e4d-182">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-182">A `Double`.</span></span> 

<span data-ttu-id="96e4d-183">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-183">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="96e4d-184">LOG(Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-184">LOG(expression)</span></span>

<span data-ttu-id="96e4d-185">Вычисляет натуральный логарифм заданного выражения типа `float`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-185">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="96e4d-186">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-186">**Arguments**</span></span> 

<span data-ttu-id="96e4d-187">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-187">`expression`: A `Double`.</span></span> 

<span data-ttu-id="96e4d-188">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-188">**Return Value**</span></span> 

<span data-ttu-id="96e4d-189">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-189">A `Double`.</span></span> 

<span data-ttu-id="96e4d-190">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-190">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="96e4d-191">LOG10(Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-191">LOG10(expression)</span></span>

<span data-ttu-id="96e4d-192">Возвращает десятичный логарифм указанного выражения типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="96e4d-193">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-193">**Arguments**</span></span> 

<span data-ttu-id="96e4d-194">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-194">`expression`: A `Double`.</span></span> 

<span data-ttu-id="96e4d-195">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-195">**Return Value**</span></span> 

<span data-ttu-id="96e4d-196">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-196">A `Double`.</span></span> 

<span data-ttu-id="96e4d-197">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-197">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="96e4d-198">ПИ()</span><span class="sxs-lookup"><span data-stu-id="96e4d-198">PI()</span></span>

<span data-ttu-id="96e4d-199">Возвращает константу «пи» в виде значения типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-199">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="96e4d-200">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-200">**Return Value**</span></span> 

<span data-ttu-id="96e4d-201">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-201">A `Double`.</span></span> 

<span data-ttu-id="96e4d-202">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-202">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a><span data-ttu-id="96e4d-203">POWER (numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="96e4d-204">Вычисляет значение указанного выражения, возведенного в заданную степень.</span><span class="sxs-lookup"><span data-stu-id="96e4d-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="96e4d-205">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-205">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="96e4d-206">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="96e4d-207">Объект `Double` , представляющее степень, в которую возводится `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="96e4d-208">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-208">**Return Value**</span></span> 

<span data-ttu-id="96e4d-209">Значение заданного выражения `numeric_expression` в указанной степени `power_expression`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="96e4d-210">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-210">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="96e4d-211">RADIANS(Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-211">RADIANS(expression)</span></span>

<span data-ttu-id="96e4d-212">Преобразовывает градусы в радианы.</span><span class="sxs-lookup"><span data-stu-id="96e4d-212">Converts degrees to radians.</span></span> 

<span data-ttu-id="96e4d-213">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-213">**Arguments**</span></span> 

<span data-ttu-id="96e4d-214">`expression`: `Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="96e4d-215">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-215">**Return Value**</span></span> 

<span data-ttu-id="96e4d-216">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="96e4d-217">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-217">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="96e4d-218">RAND([seed])</span><span class="sxs-lookup"><span data-stu-id="96e4d-218">RAND([seed])</span></span>

<span data-ttu-id="96e4d-219">Возвращает случайное значение от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="96e4d-219">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="96e4d-220">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-220">**Arguments**</span></span> 

<span data-ttu-id="96e4d-221">Начальное значение, что `Int32`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="96e4d-222">Если начальное значение не задано, то компонент SQL Server Database Engine присваивает случайно выбранное начальное значение.</span><span class="sxs-lookup"><span data-stu-id="96e4d-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="96e4d-223">Для указанного начального значения возвращаемый результат всегда будет один и тот же.</span><span class="sxs-lookup"><span data-stu-id="96e4d-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="96e4d-224">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-224">**Return Value**</span></span> 

<span data-ttu-id="96e4d-225">Случайное значение типа `Double` от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="96e4d-225">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="96e4d-226">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-226">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a><span data-ttu-id="96e4d-227">Round(Numeric_Expression, length[,Function])</span><span class="sxs-lookup"><span data-stu-id="96e4d-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="96e4d-228">Возвращает числовое выражение, округленное до указанной длины или точности.</span><span class="sxs-lookup"><span data-stu-id="96e4d-228">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="96e4d-229">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-229">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="96e4d-230">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="96e4d-231">Значение типа `Int32`, указывающее точность, до которой должно быть округлено значение аргумента `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="96e4d-232">Если аргумент `length` является положительным числом, значение `numeric_expression` округляется до числа десятичных разрядов, указанных аргументом `length`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="96e4d-233">Если аргумент `length` является отрицательным числом, значение `numeric_expression` округляется слева от десятичной запятой, как указано аргументом `length`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="96e4d-234">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="96e4d-234">Optional.</span></span> <span data-ttu-id="96e4d-235">`Int32` , Представляющий тип выполняемой операции.</span><span class="sxs-lookup"><span data-stu-id="96e4d-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="96e4d-236">Если функция указан или имеет значение 0 (по умолчанию), `numeric_expression` округляется.</span><span class="sxs-lookup"><span data-stu-id="96e4d-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="96e4d-237">Если значение, отличное от указано значение 0, `numeric_expression` усекается.</span><span class="sxs-lookup"><span data-stu-id="96e4d-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="96e4d-238">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-238">**Return Value**</span></span> 

<span data-ttu-id="96e4d-239">Значение заданного выражения `numeric_expression` в указанной степени `power_expression`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="96e4d-240">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-240">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="96e4d-241">Sign(Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-241">SIGN(expression)</span></span> 

<span data-ttu-id="96e4d-242">Возвращает положительный знак (+1), ноль (0) или отрицательный знак (-1) указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="96e4d-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="96e4d-243">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-243">**Arguments**</span></span> 

<span data-ttu-id="96e4d-244">`expression`: `Int32`, `Int64`, `Double` или `Decimal`</span><span class="sxs-lookup"><span data-stu-id="96e4d-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="96e4d-245">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-245">**Return Value**</span></span> 

<span data-ttu-id="96e4d-246">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="96e4d-247">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-247">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="96e4d-248">SIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-248">SIN(expression)</span></span>

<span data-ttu-id="96e4d-249">Вычисляет тригонометрический синус заданного угла в радианах и возвращает выражение типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="96e4d-250">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-250">**Arguments**</span></span> 

<span data-ttu-id="96e4d-251">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-251">`expression`: A `Double`.</span></span> 

<span data-ttu-id="96e4d-252">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-252">**Return Value**</span></span> 

<span data-ttu-id="96e4d-253">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-253">A `Double`.</span></span> 

<span data-ttu-id="96e4d-254">**Пример** `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="96e4d-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="96e4d-255">SQRT(Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-255">SQRT(expression)</span></span>

<span data-ttu-id="96e4d-256">Возвращает квадратный корень указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="96e4d-256">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="96e4d-257">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-257">**Arguments**</span></span> 

<span data-ttu-id="96e4d-258">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-258">`expression`: A `Double`.</span></span> 

<span data-ttu-id="96e4d-259">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-259">**Return Value**</span></span> 

<span data-ttu-id="96e4d-260">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-260">A `Double`.</span></span> 

<span data-ttu-id="96e4d-261">**Пример** `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="96e4d-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="96e4d-262">Square(Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-262">SQUARE(expression)</span></span>

<span data-ttu-id="96e4d-263">Возвращает значение указанного выражения в квадрате.</span><span class="sxs-lookup"><span data-stu-id="96e4d-263">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="96e4d-264">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-264">**Arguments**</span></span> 

<span data-ttu-id="96e4d-265">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-265">`expression`: A `Double`.</span></span> 

<span data-ttu-id="96e4d-266">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-266">**Return Value**</span></span> 

<span data-ttu-id="96e4d-267">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="96e4d-267">A `Double`.</span></span> 

<span data-ttu-id="96e4d-268">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-268">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="96e4d-269">TAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="96e4d-269">TAN(expression)</span></span>

<span data-ttu-id="96e4d-270">Вычисляет тангенс заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="96e4d-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="96e4d-271">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="96e4d-271">**Arguments**</span></span> 

<span data-ttu-id="96e4d-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="96e4d-272">`expression`: `Double`</span></span> 

<span data-ttu-id="96e4d-273">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="96e4d-273">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="96e4d-274">**Пример**</span><span class="sxs-lookup"><span data-stu-id="96e4d-274">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="96e4d-275">См. также</span><span class="sxs-lookup"><span data-stu-id="96e4d-275">See also</span></span>

<span data-ttu-id="96e4d-276">Дополнительные сведения о математических функциях, поддерживаемых SqlClient, см. в документации к версии SQL Server, указанной в манифесте поставщика SqlClient.</span><span class="sxs-lookup"><span data-stu-id="96e4d-276">For more information about the mathematical functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>  
  
<span data-ttu-id="96e4d-277">**SQL Server 2005:** [Математические функции (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="96e4d-277">**SQL Server 2005:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span></span>  
<span data-ttu-id="96e4d-278">**SQL Server 2008** [Математические функции (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="96e4d-278">**SQL Server 2008:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span></span>  
<span data-ttu-id="96e4d-279">**SQL Server 2012 и более поздних версий:** [Математические функции (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span><span class="sxs-lookup"><span data-stu-id="96e4d-279">**SQL Server 2012 and later:** [Mathematical Functions (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span></span>   

 [<span data-ttu-id="96e4d-280">Функции SqlClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="96e4d-280">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
