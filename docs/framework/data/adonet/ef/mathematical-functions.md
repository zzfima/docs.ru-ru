---
title: Математические функции
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 664d1a4f67ecced6713f83bf3dd11931c9b4dc18
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700003"
---
# <a name="mathematical-functions"></a><span data-ttu-id="584c6-102">Математические функции</span><span class="sxs-lookup"><span data-stu-id="584c6-102">Mathematical Functions</span></span>

<span data-ttu-id="584c6-103">Поставщик данных для SQL Server платформы .NET Framework (SqlClient) предоставляет математические функции, производящие вычисления на входящих значениях, предоставляемых в качестве аргументов, и возвращающие результат в виде числовых значений.</span><span class="sxs-lookup"><span data-stu-id="584c6-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="584c6-104">Эти функции находятся в пространстве имен SqlServer, которое доступно при использовании SqlClient.</span><span class="sxs-lookup"><span data-stu-id="584c6-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="584c6-105">Свойство пространства имен поставщика позволяет платформе Entity Framework узнать, какой префикс используется поставщиком для конкретных конструкций, таких как типы или функции.</span><span class="sxs-lookup"><span data-stu-id="584c6-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="584c6-106">В следующей таблице описаны математические функции SqlClient.</span><span class="sxs-lookup"><span data-stu-id="584c6-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="584c6-107">ABS (выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-107">ABS(expression)</span></span>

<span data-ttu-id="584c6-108">Возвращает абсолютное значение.</span><span class="sxs-lookup"><span data-stu-id="584c6-108">Performs the absolute value function.</span></span>

<span data-ttu-id="584c6-109">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-109">**Arguments**</span></span>

<span data-ttu-id="584c6-110">`expression`. `Int32` ,`Int64`, Или .`Decimal` `Double`</span><span class="sxs-lookup"><span data-stu-id="584c6-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="584c6-111">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-111">**Return Value**</span></span>

<span data-ttu-id="584c6-112">Абсолютное значение заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="584c6-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="584c6-113">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="584c6-114">ACOS (выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-114">ACOS(expression)</span></span>

<span data-ttu-id="584c6-115">Возвращает значение арккосинуса указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="584c6-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="584c6-116">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-116">**Arguments**</span></span>

<span data-ttu-id="584c6-117">`expression`. ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="584c6-118">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-118">**Return Value**</span></span>

<span data-ttu-id="584c6-119">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-119">A `Double`.</span></span>

<span data-ttu-id="584c6-120">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="584c6-121">ASIN (выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-121">ASIN(expression)</span></span>

<span data-ttu-id="584c6-122">Возвращает значение арксинуса указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="584c6-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="584c6-123">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-123">**Arguments**</span></span>

<span data-ttu-id="584c6-124">`expression`. ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="584c6-125">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-125">**Return Value**</span></span>

<span data-ttu-id="584c6-126">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-126">A `Double`.</span></span>

<span data-ttu-id="584c6-127">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="584c6-128">ATAN (выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-128">ATAN(expression)</span></span>

<span data-ttu-id="584c6-129">Возвращает значение арктангенса указанного числового выражения.</span><span class="sxs-lookup"><span data-stu-id="584c6-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="584c6-130">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-130">**Arguments**</span></span>

<span data-ttu-id="584c6-131">`expression`. ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="584c6-132">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-132">**Return Value**</span></span>

<span data-ttu-id="584c6-133">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-133">A `Double`.</span></span>

<span data-ttu-id="584c6-134">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="584c6-135">ATN2 (выражение, выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="584c6-136">Возвращает угол в радианах, тангенс которого находится в диапазоне между двумя заданными числовыми выражениями.</span><span class="sxs-lookup"><span data-stu-id="584c6-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="584c6-137">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-137">**Arguments**</span></span>

<span data-ttu-id="584c6-138">`expression`. ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="584c6-139">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-139">**Return Value**</span></span>

<span data-ttu-id="584c6-140">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-140">A `Double`.</span></span>

<span data-ttu-id="584c6-141">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="584c6-142">CEILING (выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-142">CEILING(expression)</span></span>

<span data-ttu-id="584c6-143">Преобразует указанное выражение в наименьшее целое число, большее или равное данному выражению.</span><span class="sxs-lookup"><span data-stu-id="584c6-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="584c6-144">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-144">**Arguments**</span></span>

<span data-ttu-id="584c6-145">`expression`. `Int32` ,`Int64`, Или .`Decimal` `Double`</span><span class="sxs-lookup"><span data-stu-id="584c6-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="584c6-146">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-146">**Return Value**</span></span>

<span data-ttu-id="584c6-147">`Int32` ,`Int64`, Или .`Decimal` `Double`</span><span class="sxs-lookup"><span data-stu-id="584c6-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="584c6-148">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-148">**Example**</span></span> 

[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="584c6-149">COS (выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-149">COS(expression)</span></span>

<span data-ttu-id="584c6-150">Вычисляет тригонометрический косинус указанного угла в радианах.</span><span class="sxs-lookup"><span data-stu-id="584c6-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="584c6-151">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-151">**Arguments**</span></span> 

<span data-ttu-id="584c6-152">`expression`. ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-152">`expression`: A `Double`.</span></span> 

<span data-ttu-id="584c6-153">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-153">**Return Value**</span></span> 

<span data-ttu-id="584c6-154">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-154">A `Double`.</span></span> 

<span data-ttu-id="584c6-155">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-155">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="584c6-156">COT (выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-156">COT(expression)</span></span>

<span data-ttu-id="584c6-157">Вычисляет тригонометрический котангенс указанного угла в радианах.</span><span class="sxs-lookup"><span data-stu-id="584c6-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="584c6-158">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-158">**Arguments**</span></span> 

<span data-ttu-id="584c6-159">`expression`. ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-159">`expression`: A `Double`.</span></span> 

<span data-ttu-id="584c6-160">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-160">**Return Value**</span></span> 

<span data-ttu-id="584c6-161">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-161">A `Double`.</span></span> 

<span data-ttu-id="584c6-162">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-162">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="584c6-163">ГРАДУСы (радианы)</span><span class="sxs-lookup"><span data-stu-id="584c6-163">DEGREES(radians)</span></span>

<span data-ttu-id="584c6-164">Возвращает соответствующее значение угла в градусах.</span><span class="sxs-lookup"><span data-stu-id="584c6-164">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="584c6-165">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-165">**Arguments**</span></span> 

<span data-ttu-id="584c6-166">`expression`. `Int32` ,`Int64`, Или .`Decimal` `Double`</span><span class="sxs-lookup"><span data-stu-id="584c6-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="584c6-167">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-167">**Return Value**</span></span> 

<span data-ttu-id="584c6-168">`Int32` ,`Int64`, Или .`Decimal` `Double`</span><span class="sxs-lookup"><span data-stu-id="584c6-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="584c6-169">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-169">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="584c6-170">EXP (выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-170">EXP(expression)</span></span>

<span data-ttu-id="584c6-171">Вычисляет экспоненту заданного числового выражения.</span><span class="sxs-lookup"><span data-stu-id="584c6-171">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="584c6-172">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-172">**Arguments**</span></span> 

<span data-ttu-id="584c6-173">`expression`. ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-173">`expression`: A `Double`.</span></span> 

<span data-ttu-id="584c6-174">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-174">**Return Value**</span></span> 

<span data-ttu-id="584c6-175">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-175">A `Double`.</span></span> 

<span data-ttu-id="584c6-176">**Пример**`SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="584c6-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="584c6-177">FLOOR (выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-177">FLOOR(expression)</span></span>

<span data-ttu-id="584c6-178">Преобразует указанное выражение в наибольшее целое число, меньшее или равное данному выражению.</span><span class="sxs-lookup"><span data-stu-id="584c6-178">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="584c6-179">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-179">**Arguments**</span></span> 

<span data-ttu-id="584c6-180">`expression`. ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-180">`expression`: A `Double`.</span></span> 

<span data-ttu-id="584c6-181">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-181">**Return Value**</span></span> 

<span data-ttu-id="584c6-182">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-182">A `Double`.</span></span> 

<span data-ttu-id="584c6-183">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-183">**Example**</span></span> 

[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="584c6-184">LOG (выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-184">LOG(expression)</span></span>

<span data-ttu-id="584c6-185">Вычисляет натуральный логарифм заданного выражения типа `float`.</span><span class="sxs-lookup"><span data-stu-id="584c6-185">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="584c6-186">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-186">**Arguments**</span></span> 

<span data-ttu-id="584c6-187">`expression`. ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-187">`expression`: A `Double`.</span></span> 

<span data-ttu-id="584c6-188">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-188">**Return Value**</span></span> 

<span data-ttu-id="584c6-189">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-189">A `Double`.</span></span> 

<span data-ttu-id="584c6-190">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-190">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="584c6-191">LOG10 (выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-191">LOG10(expression)</span></span>

<span data-ttu-id="584c6-192">Возвращает десятичный логарифм указанного выражения типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="584c6-193">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-193">**Arguments**</span></span> 

<span data-ttu-id="584c6-194">`expression`. ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-194">`expression`: A `Double`.</span></span> 

<span data-ttu-id="584c6-195">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-195">**Return Value**</span></span> 

<span data-ttu-id="584c6-196">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-196">A `Double`.</span></span> 

<span data-ttu-id="584c6-197">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-197">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="584c6-198">PI ()</span><span class="sxs-lookup"><span data-stu-id="584c6-198">PI()</span></span>

<span data-ttu-id="584c6-199">Возвращает константу «пи» в виде значения типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-199">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="584c6-200">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-200">**Return Value**</span></span> 

<span data-ttu-id="584c6-201">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-201">A `Double`.</span></span> 

<span data-ttu-id="584c6-202">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-202">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumeric_expression-power_expression"></a><span data-ttu-id="584c6-203">МОЩНОСТЬ (numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="584c6-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="584c6-204">Вычисляет значение указанного выражения, возведенного в заданную степень.</span><span class="sxs-lookup"><span data-stu-id="584c6-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="584c6-205">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-205">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="584c6-206">`Int32` ,`Int64`, Или .`Decimal` `Double`</span><span class="sxs-lookup"><span data-stu-id="584c6-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="584c6-207">Объект `Double` , представляющий степень, до которой `numeric_expression`вызывается.</span><span class="sxs-lookup"><span data-stu-id="584c6-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="584c6-208">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-208">**Return Value**</span></span> 

<span data-ttu-id="584c6-209">Значение заданного выражения `numeric_expression` в указанной степени `power_expression`.</span><span class="sxs-lookup"><span data-stu-id="584c6-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="584c6-210">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-210">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="584c6-211">РАДИАНы (выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-211">RADIANS(expression)</span></span>

<span data-ttu-id="584c6-212">Преобразовывает градусы в радианы.</span><span class="sxs-lookup"><span data-stu-id="584c6-212">Converts degrees to radians.</span></span> 

<span data-ttu-id="584c6-213">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-213">**Arguments**</span></span> 

<span data-ttu-id="584c6-214">`expression`. `Int32` ,`Int64`, Или .`Decimal` `Double`</span><span class="sxs-lookup"><span data-stu-id="584c6-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="584c6-215">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-215">**Return Value**</span></span> 

<span data-ttu-id="584c6-216">`Int32` ,`Int64`, Или .`Decimal` `Double`</span><span class="sxs-lookup"><span data-stu-id="584c6-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="584c6-217">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-217">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="584c6-218">RAND ([начальное значение])</span><span class="sxs-lookup"><span data-stu-id="584c6-218">RAND([seed])</span></span>

<span data-ttu-id="584c6-219">Возвращает случайное значение от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="584c6-219">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="584c6-220">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-220">**Arguments**</span></span> 

<span data-ttu-id="584c6-221">Начальное значение в виде `Int32`.</span><span class="sxs-lookup"><span data-stu-id="584c6-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="584c6-222">Если начальное значение не задано, то компонент SQL Server Database Engine присваивает случайно выбранное начальное значение.</span><span class="sxs-lookup"><span data-stu-id="584c6-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="584c6-223">Для указанного начального значения возвращаемый результат всегда будет один и тот же.</span><span class="sxs-lookup"><span data-stu-id="584c6-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="584c6-224">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-224">**Return Value**</span></span> 

<span data-ttu-id="584c6-225">Случайное значение типа `Double` от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="584c6-225">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="584c6-226">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-226">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumeric_expression-lengthfunction"></a><span data-ttu-id="584c6-227">ROUND (numeric_expression, длина [, функция])</span><span class="sxs-lookup"><span data-stu-id="584c6-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="584c6-228">Возвращает числовое выражение, округленное до указанной длины или точности.</span><span class="sxs-lookup"><span data-stu-id="584c6-228">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="584c6-229">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-229">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="584c6-230">`Int32` ,`Int64`, Или .`Decimal` `Double`</span><span class="sxs-lookup"><span data-stu-id="584c6-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="584c6-231">Значение типа `Int32`, указывающее точность, до которой должно быть округлено значение аргумента `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="584c6-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="584c6-232">Если аргумент `length` является положительным числом, значение `numeric_expression` округляется до числа десятичных разрядов, указанных аргументом `length`.</span><span class="sxs-lookup"><span data-stu-id="584c6-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="584c6-233">Если аргумент `length` является отрицательным числом, значение `numeric_expression` округляется слева от десятичной запятой, как указано аргументом `length`.</span><span class="sxs-lookup"><span data-stu-id="584c6-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="584c6-234">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="584c6-234">Optional.</span></span> <span data-ttu-id="584c6-235">Объект `Int32` , представляющий тип выполняемой операции.</span><span class="sxs-lookup"><span data-stu-id="584c6-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="584c6-236">Если функция опущена или имеет значение 0 (по умолчанию), `numeric_expression` то параметр округляется.</span><span class="sxs-lookup"><span data-stu-id="584c6-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="584c6-237">Если указано значение, отличное от 0, `numeric_expression` усекается.</span><span class="sxs-lookup"><span data-stu-id="584c6-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="584c6-238">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-238">**Return Value**</span></span> 

<span data-ttu-id="584c6-239">Значение заданного выражения `numeric_expression` в указанной степени `power_expression`.</span><span class="sxs-lookup"><span data-stu-id="584c6-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="584c6-240">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-240">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="584c6-241">SIGN (выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-241">SIGN(expression)</span></span> 

<span data-ttu-id="584c6-242">Возвращает положительный знак (+1), ноль (0) или отрицательный знак (-1) указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="584c6-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="584c6-243">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-243">**Arguments**</span></span> 

<span data-ttu-id="584c6-244">`expression`: `Int32`, `Int64`, `Double` или `Decimal`</span><span class="sxs-lookup"><span data-stu-id="584c6-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="584c6-245">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-245">**Return Value**</span></span> 

<span data-ttu-id="584c6-246">`Int32` ,`Int64`, Или .`Decimal` `Double`</span><span class="sxs-lookup"><span data-stu-id="584c6-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="584c6-247">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-247">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="584c6-248">SIN (выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-248">SIN(expression)</span></span>

<span data-ttu-id="584c6-249">Вычисляет тригонометрический синус заданного угла в радианах и возвращает выражение типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="584c6-250">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-250">**Arguments**</span></span> 

<span data-ttu-id="584c6-251">`expression`. ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-251">`expression`: A `Double`.</span></span> 

<span data-ttu-id="584c6-252">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-252">**Return Value**</span></span> 

<span data-ttu-id="584c6-253">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-253">A `Double`.</span></span> 

<span data-ttu-id="584c6-254">**Пример**`SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="584c6-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="584c6-255">SQRT (выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-255">SQRT(expression)</span></span>

<span data-ttu-id="584c6-256">Возвращает квадратный корень указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="584c6-256">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="584c6-257">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-257">**Arguments**</span></span> 

<span data-ttu-id="584c6-258">`expression`. ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-258">`expression`: A `Double`.</span></span> 

<span data-ttu-id="584c6-259">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-259">**Return Value**</span></span> 

<span data-ttu-id="584c6-260">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-260">A `Double`.</span></span> 

<span data-ttu-id="584c6-261">**Пример**`SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="584c6-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="584c6-262">SQUARE (выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-262">SQUARE(expression)</span></span>

<span data-ttu-id="584c6-263">Возвращает значение указанного выражения в квадрате.</span><span class="sxs-lookup"><span data-stu-id="584c6-263">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="584c6-264">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-264">**Arguments**</span></span> 

<span data-ttu-id="584c6-265">`expression`. ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-265">`expression`: A `Double`.</span></span> 

<span data-ttu-id="584c6-266">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-266">**Return Value**</span></span> 

<span data-ttu-id="584c6-267">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="584c6-267">A `Double`.</span></span> 

<span data-ttu-id="584c6-268">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-268">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="584c6-269">TAN (выражение)</span><span class="sxs-lookup"><span data-stu-id="584c6-269">TAN(expression)</span></span>

<span data-ttu-id="584c6-270">Вычисляет тангенс заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="584c6-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="584c6-271">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="584c6-271">**Arguments**</span></span> 

<span data-ttu-id="584c6-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="584c6-272">`expression`: `Double`</span></span> 

<span data-ttu-id="584c6-273">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="584c6-273">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="584c6-274">**Пример**</span><span class="sxs-lookup"><span data-stu-id="584c6-274">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="584c6-275">См. также</span><span class="sxs-lookup"><span data-stu-id="584c6-275">See also</span></span>

- [<span data-ttu-id="584c6-276">Математические функции (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="584c6-276">Mathematical Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/mathematical-functions-transact-sql)
- [<span data-ttu-id="584c6-277">Функции SqlClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="584c6-277">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
