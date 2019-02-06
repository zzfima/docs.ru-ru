---
title: Математические функции
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: b6f248382f069df59a55e85e9a764b0df700fb26
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759383"
---
# <a name="mathematical-functions"></a><span data-ttu-id="2c7c5-102">Математические функции</span><span class="sxs-lookup"><span data-stu-id="2c7c5-102">Mathematical Functions</span></span>

<span data-ttu-id="2c7c5-103">Поставщик данных для SQL Server платформы .NET Framework (SqlClient) предоставляет математические функции, производящие вычисления на входящих значениях, предоставляемых в качестве аргументов, и возвращающие результат в виде числовых значений.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="2c7c5-104">Эти функции находятся в пространстве имен SqlServer, которое доступно при использовании SqlClient.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="2c7c5-105">Свойство пространства имен поставщика позволяет платформе Entity Framework узнать, какой префикс используется поставщиком для конкретных конструкций, таких как типы или функции.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="2c7c5-106">В следующей таблице описаны математические функции SqlClient.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="2c7c5-107">ABS(Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-107">ABS(expression)</span></span>

<span data-ttu-id="2c7c5-108">Возвращает абсолютное значение.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-108">Performs the absolute value function.</span></span>

<span data-ttu-id="2c7c5-109">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-109">**Arguments**</span></span>

<span data-ttu-id="2c7c5-110">`expression`: `Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="2c7c5-111">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-111">**Return Value**</span></span>

<span data-ttu-id="2c7c5-112">Абсолютное значение заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="2c7c5-113">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="2c7c5-114">ACOS(Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-114">ACOS(expression)</span></span>

<span data-ttu-id="2c7c5-115">Возвращает значение арккосинуса указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="2c7c5-116">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-116">**Arguments**</span></span>

<span data-ttu-id="2c7c5-117">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="2c7c5-118">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-118">**Return Value**</span></span>

<span data-ttu-id="2c7c5-119">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-119">A `Double`.</span></span>

<span data-ttu-id="2c7c5-120">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="2c7c5-121">ASIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-121">ASIN(expression)</span></span>

<span data-ttu-id="2c7c5-122">Возвращает значение арксинуса указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="2c7c5-123">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-123">**Arguments**</span></span>

<span data-ttu-id="2c7c5-124">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="2c7c5-125">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-125">**Return Value**</span></span>

<span data-ttu-id="2c7c5-126">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-126">A `Double`.</span></span>

<span data-ttu-id="2c7c5-127">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="2c7c5-128">ATAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-128">ATAN(expression)</span></span>

<span data-ttu-id="2c7c5-129">Возвращает значение арктангенса указанного числового выражения.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="2c7c5-130">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-130">**Arguments**</span></span>

<span data-ttu-id="2c7c5-131">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="2c7c5-132">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-132">**Return Value**</span></span>

<span data-ttu-id="2c7c5-133">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-133">A `Double`.</span></span>

<span data-ttu-id="2c7c5-134">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="2c7c5-135">ATN2(Expression, Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="2c7c5-136">Возвращает угол в радианах, тангенс которого находится в диапазоне между двумя заданными числовыми выражениями.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="2c7c5-137">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-137">**Arguments**</span></span>

<span data-ttu-id="2c7c5-138">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="2c7c5-139">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-139">**Return Value**</span></span>

<span data-ttu-id="2c7c5-140">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-140">A `Double`.</span></span>

<span data-ttu-id="2c7c5-141">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="2c7c5-142">CEILING(Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-142">CEILING(expression)</span></span>

<span data-ttu-id="2c7c5-143">Преобразует указанное выражение в наименьшее целое число, большее или равное данному выражению.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="2c7c5-144">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-144">**Arguments**</span></span>

<span data-ttu-id="2c7c5-145">`expression`: `Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="2c7c5-146">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-146">**Return Value**</span></span>

<span data-ttu-id="2c7c5-147">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="2c7c5-148">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-148">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="2c7c5-149">COS(Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-149">COS(expression)</span></span>

<span data-ttu-id="2c7c5-150">Вычисляет тригонометрический косинус указанного угла в радианах.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="2c7c5-151">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-151">**Arguments**</span></span> 

<span data-ttu-id="2c7c5-152">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-152">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2c7c5-153">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-153">**Return Value**</span></span> 

<span data-ttu-id="2c7c5-154">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-154">A `Double`.</span></span> 

<span data-ttu-id="2c7c5-155">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-155">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="2c7c5-156">COT(Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-156">COT(expression)</span></span>

<span data-ttu-id="2c7c5-157">Вычисляет тригонометрический котангенс указанного угла в радианах.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="2c7c5-158">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-158">**Arguments**</span></span> 

<span data-ttu-id="2c7c5-159">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-159">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2c7c5-160">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-160">**Return Value**</span></span> 

<span data-ttu-id="2c7c5-161">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-161">A `Double`.</span></span> 

<span data-ttu-id="2c7c5-162">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-162">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="2c7c5-163">DEGREES(RADIANS)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-163">DEGREES(radians)</span></span>

<span data-ttu-id="2c7c5-164">Возвращает соответствующее значение угла в градусах.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-164">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="2c7c5-165">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-165">**Arguments**</span></span> 

<span data-ttu-id="2c7c5-166">`expression`: `Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="2c7c5-167">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-167">**Return Value**</span></span> 

<span data-ttu-id="2c7c5-168">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="2c7c5-169">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-169">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="2c7c5-170">EXP(Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-170">EXP(expression)</span></span>

<span data-ttu-id="2c7c5-171">Вычисляет экспоненту заданного числового выражения.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-171">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="2c7c5-172">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-172">**Arguments**</span></span> 

<span data-ttu-id="2c7c5-173">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-173">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2c7c5-174">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-174">**Return Value**</span></span> 

<span data-ttu-id="2c7c5-175">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-175">A `Double`.</span></span> 

<span data-ttu-id="2c7c5-176">**Пример** `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="2c7c5-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="2c7c5-177">FLOOR(Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-177">FLOOR(expression)</span></span>

<span data-ttu-id="2c7c5-178">Преобразует указанное выражение в наибольшее целое число, меньшее или равное данному выражению.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-178">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="2c7c5-179">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-179">**Arguments**</span></span> 

<span data-ttu-id="2c7c5-180">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-180">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2c7c5-181">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-181">**Return Value**</span></span> 

<span data-ttu-id="2c7c5-182">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-182">A `Double`.</span></span> 

<span data-ttu-id="2c7c5-183">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-183">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="2c7c5-184">LOG(Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-184">LOG(expression)</span></span>

<span data-ttu-id="2c7c5-185">Вычисляет натуральный логарифм заданного выражения типа `float`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-185">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="2c7c5-186">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-186">**Arguments**</span></span> 

<span data-ttu-id="2c7c5-187">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-187">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2c7c5-188">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-188">**Return Value**</span></span> 

<span data-ttu-id="2c7c5-189">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-189">A `Double`.</span></span> 

<span data-ttu-id="2c7c5-190">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-190">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="2c7c5-191">LOG10(Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-191">LOG10(expression)</span></span>

<span data-ttu-id="2c7c5-192">Возвращает десятичный логарифм указанного выражения типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="2c7c5-193">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-193">**Arguments**</span></span> 

<span data-ttu-id="2c7c5-194">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-194">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2c7c5-195">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-195">**Return Value**</span></span> 

<span data-ttu-id="2c7c5-196">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-196">A `Double`.</span></span> 

<span data-ttu-id="2c7c5-197">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-197">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="2c7c5-198">ПИ()</span><span class="sxs-lookup"><span data-stu-id="2c7c5-198">PI()</span></span>

<span data-ttu-id="2c7c5-199">Возвращает константу «пи» в виде значения типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-199">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="2c7c5-200">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-200">**Return Value**</span></span> 

<span data-ttu-id="2c7c5-201">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-201">A `Double`.</span></span> 

<span data-ttu-id="2c7c5-202">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-202">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a><span data-ttu-id="2c7c5-203">POWER (numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="2c7c5-204">Вычисляет значение указанного выражения, возведенного в заданную степень.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="2c7c5-205">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-205">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="2c7c5-206">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="2c7c5-207">Объект `Double` , представляющее степень, в которую возводится `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="2c7c5-208">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-208">**Return Value**</span></span> 

<span data-ttu-id="2c7c5-209">Значение заданного выражения `numeric_expression` в указанной степени `power_expression`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="2c7c5-210">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-210">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="2c7c5-211">RADIANS(Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-211">RADIANS(expression)</span></span>

<span data-ttu-id="2c7c5-212">Преобразовывает градусы в радианы.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-212">Converts degrees to radians.</span></span> 

<span data-ttu-id="2c7c5-213">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-213">**Arguments**</span></span> 

<span data-ttu-id="2c7c5-214">`expression`: `Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="2c7c5-215">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-215">**Return Value**</span></span> 

<span data-ttu-id="2c7c5-216">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="2c7c5-217">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-217">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="2c7c5-218">RAND([seed])</span><span class="sxs-lookup"><span data-stu-id="2c7c5-218">RAND([seed])</span></span>

<span data-ttu-id="2c7c5-219">Возвращает случайное значение от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-219">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="2c7c5-220">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-220">**Arguments**</span></span> 

<span data-ttu-id="2c7c5-221">Начальное значение, что `Int32`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="2c7c5-222">Если начальное значение не задано, то компонент SQL Server Database Engine присваивает случайно выбранное начальное значение.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="2c7c5-223">Для указанного начального значения возвращаемый результат всегда будет один и тот же.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="2c7c5-224">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-224">**Return Value**</span></span> 

<span data-ttu-id="2c7c5-225">Случайное значение типа `Double` от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-225">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="2c7c5-226">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-226">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a><span data-ttu-id="2c7c5-227">Round(Numeric_Expression, length[,Function])</span><span class="sxs-lookup"><span data-stu-id="2c7c5-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="2c7c5-228">Возвращает числовое выражение, округленное до указанной длины или точности.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-228">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="2c7c5-229">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-229">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="2c7c5-230">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="2c7c5-231">Значение типа `Int32`, указывающее точность, до которой должно быть округлено значение аргумента `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="2c7c5-232">Если аргумент `length` является положительным числом, значение `numeric_expression` округляется до числа десятичных разрядов, указанных аргументом `length`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="2c7c5-233">Если аргумент `length` является отрицательным числом, значение `numeric_expression` округляется слева от десятичной запятой, как указано аргументом `length`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="2c7c5-234">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-234">Optional.</span></span> <span data-ttu-id="2c7c5-235">`Int32` , Представляющий тип выполняемой операции.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="2c7c5-236">Если функция указан или имеет значение 0 (по умолчанию), `numeric_expression` округляется.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="2c7c5-237">Если значение, отличное от указано значение 0, `numeric_expression` усекается.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="2c7c5-238">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-238">**Return Value**</span></span> 

<span data-ttu-id="2c7c5-239">Значение заданного выражения `numeric_expression` в указанной степени `power_expression`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="2c7c5-240">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-240">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="2c7c5-241">Sign(Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-241">SIGN(expression)</span></span> 

<span data-ttu-id="2c7c5-242">Возвращает положительный знак (+1), ноль (0) или отрицательный знак (-1) указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="2c7c5-243">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-243">**Arguments**</span></span> 

<span data-ttu-id="2c7c5-244">`expression`: `Int32`, `Int64`, `Double` или `Decimal`</span><span class="sxs-lookup"><span data-stu-id="2c7c5-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="2c7c5-245">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-245">**Return Value**</span></span> 

<span data-ttu-id="2c7c5-246">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="2c7c5-247">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-247">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="2c7c5-248">SIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-248">SIN(expression)</span></span>

<span data-ttu-id="2c7c5-249">Вычисляет тригонометрический синус заданного угла в радианах и возвращает выражение типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="2c7c5-250">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-250">**Arguments**</span></span> 

<span data-ttu-id="2c7c5-251">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-251">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2c7c5-252">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-252">**Return Value**</span></span> 

<span data-ttu-id="2c7c5-253">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-253">A `Double`.</span></span> 

<span data-ttu-id="2c7c5-254">**Пример** `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="2c7c5-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="2c7c5-255">SQRT(Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-255">SQRT(expression)</span></span>

<span data-ttu-id="2c7c5-256">Возвращает квадратный корень указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-256">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="2c7c5-257">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-257">**Arguments**</span></span> 

<span data-ttu-id="2c7c5-258">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-258">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2c7c5-259">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-259">**Return Value**</span></span> 

<span data-ttu-id="2c7c5-260">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-260">A `Double`.</span></span> 

<span data-ttu-id="2c7c5-261">**Пример** `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="2c7c5-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="2c7c5-262">Square(Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-262">SQUARE(expression)</span></span>

<span data-ttu-id="2c7c5-263">Возвращает значение указанного выражения в квадрате.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-263">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="2c7c5-264">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-264">**Arguments**</span></span> 

<span data-ttu-id="2c7c5-265">`expression`: ОБЪЕКТ `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-265">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2c7c5-266">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-266">**Return Value**</span></span> 

<span data-ttu-id="2c7c5-267">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-267">A `Double`.</span></span> 

<span data-ttu-id="2c7c5-268">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-268">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="2c7c5-269">TAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-269">TAN(expression)</span></span>

<span data-ttu-id="2c7c5-270">Вычисляет тангенс заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="2c7c5-271">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-271">**Arguments**</span></span> 

<span data-ttu-id="2c7c5-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="2c7c5-272">`expression`: `Double`</span></span> 

<span data-ttu-id="2c7c5-273">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-273">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="2c7c5-274">**Пример**</span><span class="sxs-lookup"><span data-stu-id="2c7c5-274">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="2c7c5-275">См. также</span><span class="sxs-lookup"><span data-stu-id="2c7c5-275">See also</span></span>

<span data-ttu-id="2c7c5-276">Дополнительные сведения о математических функциях, поддерживаемых SqlClient, см. в документации к версии SQL Server, указанной в манифесте поставщика SqlClient.</span><span class="sxs-lookup"><span data-stu-id="2c7c5-276">For more information about the mathematical functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>

- <span data-ttu-id="2c7c5-277">**SQL Server 2005:** [Математические функции (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="2c7c5-277">**SQL Server 2005:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span></span>
- <span data-ttu-id="2c7c5-278">**SQL Server 2008** [Математические функции (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="2c7c5-278">**SQL Server 2008:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span></span>
- <span data-ttu-id="2c7c5-279">**SQL Server 2012 и более поздних версий:** [Математические функции (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span><span class="sxs-lookup"><span data-stu-id="2c7c5-279">**SQL Server 2012 and later:** [Mathematical Functions (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span></span>

- [<span data-ttu-id="2c7c5-280">Функции SqlClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="2c7c5-280">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
