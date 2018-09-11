---
title: Математические функции
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: e6c58d781d7138f8295f2d0a2f0db110ad4b1dd6
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2018
ms.locfileid: "44365648"
---
# <a name="mathematical-functions"></a><span data-ttu-id="6b2ed-102">Математические функции</span><span class="sxs-lookup"><span data-stu-id="6b2ed-102">Mathematical Functions</span></span>

<span data-ttu-id="6b2ed-103">Поставщик данных для SQL Server платформы .NET Framework (SqlClient) предоставляет математические функции, производящие вычисления на входящих значениях, предоставляемых в качестве аргументов, и возвращающие результат в виде числовых значений.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="6b2ed-104">Эти функции находятся в пространстве имен SqlServer, которое доступно при использовании SqlClient.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="6b2ed-105">Свойство пространства имен поставщика позволяет платформе Entity Framework узнать, какой префикс используется поставщиком для конкретных конструкций, таких как типы или функции. В следующей таблице описаны математические функции SqlClient.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="6b2ed-106">ABS(Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-106">ABS(expression)</span></span>

<span data-ttu-id="6b2ed-107">Возвращает абсолютное значение.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-107">Performs the absolute value function.</span></span>

<span data-ttu-id="6b2ed-108">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-108">**Arguments**</span></span>

<span data-ttu-id="6b2ed-109">`expression`: значение типа `Int32`, `Int64`, `Double` или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-109">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="6b2ed-110">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-110">**Return Value**</span></span>

<span data-ttu-id="6b2ed-111">Абсолютное значение заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-111">The absolute value of the specified expression.</span></span>

<span data-ttu-id="6b2ed-112">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-112">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="6b2ed-113">ACOS(Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-113">ACOS(expression)</span></span>

<span data-ttu-id="6b2ed-114">Возвращает значение арккосинуса указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-114">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="6b2ed-115">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-115">**Arguments**</span></span>

<span data-ttu-id="6b2ed-116">`expression`: Тип `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-116">`expression`: A `Double`.</span></span>

<span data-ttu-id="6b2ed-117">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-117">**Return Value**</span></span>

<span data-ttu-id="6b2ed-118">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-118">A `Double`.</span></span>

<span data-ttu-id="6b2ed-119">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-119">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="6b2ed-120">ASIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-120">ASIN(expression)</span></span>

<span data-ttu-id="6b2ed-121">Возвращает значение арксинуса указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-121">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="6b2ed-122">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-122">**Arguments**</span></span>

<span data-ttu-id="6b2ed-123">`expression`: Тип `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-123">`expression`: A `Double`.</span></span>

<span data-ttu-id="6b2ed-124">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-124">**Return Value**</span></span>

<span data-ttu-id="6b2ed-125">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-125">A `Double`.</span></span>

<span data-ttu-id="6b2ed-126">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-126">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="6b2ed-127">ATAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-127">ATAN(expression)</span></span>

<span data-ttu-id="6b2ed-128">Возвращает значение арктангенса указанного числового выражения.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-128">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="6b2ed-129">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-129">**Arguments**</span></span>

<span data-ttu-id="6b2ed-130">`expression`: Тип `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-130">`expression`: A `Double`.</span></span>

<span data-ttu-id="6b2ed-131">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-131">**Return Value**</span></span>

<span data-ttu-id="6b2ed-132">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-132">A `Double`.</span></span>

<span data-ttu-id="6b2ed-133">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-133">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="6b2ed-134">ATN2(Expression, Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-134">ATN2(expression, expression)</span></span>

<span data-ttu-id="6b2ed-135">Возвращает угол в радианах, тангенс которого находится в диапазоне между двумя заданными числовыми выражениями.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-135">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="6b2ed-136">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-136">**Arguments**</span></span>

<span data-ttu-id="6b2ed-137">`expression`: Тип `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-137">`expression`: A `Double`.</span></span>

<span data-ttu-id="6b2ed-138">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-138">**Return Value**</span></span>

<span data-ttu-id="6b2ed-139">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-139">A `Double`.</span></span>

<span data-ttu-id="6b2ed-140">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-140">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="6b2ed-141">CEILING(Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-141">CEILING(expression)</span></span>

<span data-ttu-id="6b2ed-142">Преобразует указанное выражение в наименьшее целое число, большее или равное данному выражению.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-142">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="6b2ed-143">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-143">**Arguments**</span></span>

<span data-ttu-id="6b2ed-144">`expression`: значение типа `Int32`, `Int64`, `Double` или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-144">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="6b2ed-145">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-145">**Return Value**</span></span>

<span data-ttu-id="6b2ed-146">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-146">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="6b2ed-147">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-147">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="6b2ed-148">COS(Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-148">COS(expression)</span></span>

<span data-ttu-id="6b2ed-149">Вычисляет тригонометрический косинус указанного угла в радианах.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-149">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="6b2ed-150">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-150">**Arguments**</span></span> 

<span data-ttu-id="6b2ed-151">`expression`: Тип `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-151">`expression`: A `Double`.</span></span> 

<span data-ttu-id="6b2ed-152">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-152">**Return Value**</span></span> 

<span data-ttu-id="6b2ed-153">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-153">A `Double`.</span></span> 

<span data-ttu-id="6b2ed-154">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-154">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="6b2ed-155">COT(Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-155">COT(expression)</span></span>

<span data-ttu-id="6b2ed-156">Вычисляет тригонометрический котангенс указанного угла в радианах.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-156">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="6b2ed-157">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-157">**Arguments**</span></span> 

<span data-ttu-id="6b2ed-158">`expression`: Тип `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-158">`expression`: A `Double`.</span></span> 

<span data-ttu-id="6b2ed-159">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-159">**Return Value**</span></span> 

<span data-ttu-id="6b2ed-160">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-160">A `Double`.</span></span> 

<span data-ttu-id="6b2ed-161">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-161">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="6b2ed-162">DEGREES(RADIANS)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-162">DEGREES(radians)</span></span>

<span data-ttu-id="6b2ed-163">Возвращает соответствующее значение угла в градусах.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-163">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="6b2ed-164">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-164">**Arguments**</span></span> 

<span data-ttu-id="6b2ed-165">`expression`: значение типа `Int32`, `Int64`, `Double` или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-165">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="6b2ed-166">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-166">**Return Value**</span></span> 

<span data-ttu-id="6b2ed-167">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-167">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="6b2ed-168">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-168">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="6b2ed-169">EXP(Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-169">EXP(expression)</span></span>

<span data-ttu-id="6b2ed-170">Вычисляет экспоненту заданного числового выражения.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-170">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="6b2ed-171">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-171">**Arguments**</span></span> 

<span data-ttu-id="6b2ed-172">`expression`: Тип `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-172">`expression`: A `Double`.</span></span> 

<span data-ttu-id="6b2ed-173">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-173">**Return Value**</span></span> 

<span data-ttu-id="6b2ed-174">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-174">A `Double`.</span></span> 

<span data-ttu-id="6b2ed-175">**Пример** `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="6b2ed-175">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="6b2ed-176">FLOOR(Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-176">FLOOR(expression)</span></span>

<span data-ttu-id="6b2ed-177">Преобразует указанное выражение в наибольшее целое число, меньшее или равное данному выражению.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-177">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="6b2ed-178">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-178">**Arguments**</span></span> 

<span data-ttu-id="6b2ed-179">`expression`: Тип `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-179">`expression`: A `Double`.</span></span> 

<span data-ttu-id="6b2ed-180">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-180">**Return Value**</span></span> 

<span data-ttu-id="6b2ed-181">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-181">A `Double`.</span></span> 

<span data-ttu-id="6b2ed-182">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-182">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="6b2ed-183">LOG(Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-183">LOG(expression)</span></span>

<span data-ttu-id="6b2ed-184">Вычисляет натуральный логарифм заданного выражения типа `float`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-184">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="6b2ed-185">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-185">**Arguments**</span></span> 

<span data-ttu-id="6b2ed-186">`expression`: Тип `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-186">`expression`: A `Double`.</span></span> 

<span data-ttu-id="6b2ed-187">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-187">**Return Value**</span></span> 

<span data-ttu-id="6b2ed-188">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-188">A `Double`.</span></span> 

<span data-ttu-id="6b2ed-189">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-189">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="6b2ed-190">LOG10(Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-190">LOG10(expression)</span></span>

<span data-ttu-id="6b2ed-191">Возвращает десятичный логарифм указанного выражения типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-191">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="6b2ed-192">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-192">**Arguments**</span></span> 

<span data-ttu-id="6b2ed-193">`expression`: Тип `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-193">`expression`: A `Double`.</span></span> 

<span data-ttu-id="6b2ed-194">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-194">**Return Value**</span></span> 

<span data-ttu-id="6b2ed-195">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-195">A `Double`.</span></span> 

<span data-ttu-id="6b2ed-196">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-196">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="6b2ed-197">ПИ()</span><span class="sxs-lookup"><span data-stu-id="6b2ed-197">PI()</span></span>

<span data-ttu-id="6b2ed-198">Возвращает константу «пи» в виде значения типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-198">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="6b2ed-199">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-199">**Return Value**</span></span> 

<span data-ttu-id="6b2ed-200">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-200">A `Double`.</span></span> 

<span data-ttu-id="6b2ed-201">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-201">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a><span data-ttu-id="6b2ed-202">POWER (numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-202">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="6b2ed-203">Вычисляет значение указанного выражения, возведенного в заданную степень.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-203">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="6b2ed-204">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-204">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="6b2ed-205">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-205">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="6b2ed-206">Объект `Double` , представляющее степень, в которую возводится `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-206">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="6b2ed-207">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-207">**Return Value**</span></span> 

<span data-ttu-id="6b2ed-208">Значение заданного выражения `numeric_expression` в указанной степени `power_expression`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-208">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="6b2ed-209">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-209">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="6b2ed-210">RADIANS(Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-210">RADIANS(expression)</span></span>

<span data-ttu-id="6b2ed-211">Преобразовывает градусы в радианы.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-211">Converts degrees to radians.</span></span> 

<span data-ttu-id="6b2ed-212">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-212">**Arguments**</span></span> 

<span data-ttu-id="6b2ed-213">`expression`: значение типа `Int32`, `Int64`, `Double` или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-213">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="6b2ed-214">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-214">**Return Value**</span></span> 

<span data-ttu-id="6b2ed-215">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-215">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="6b2ed-216">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-216">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="6b2ed-217">RAND([seed])</span><span class="sxs-lookup"><span data-stu-id="6b2ed-217">RAND([seed])</span></span>

<span data-ttu-id="6b2ed-218">Возвращает случайное значение от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-218">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="6b2ed-219">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-219">**Arguments**</span></span> 

<span data-ttu-id="6b2ed-220">Начальное значение, что `Int32`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-220">The seed value as an `Int32`.</span></span> <span data-ttu-id="6b2ed-221">Если начальное значение не задано, то компонент SQL Server Database Engine присваивает случайно выбранное начальное значение.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-221">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="6b2ed-222">Для указанного начального значения возвращаемый результат всегда будет один и тот же.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-222">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="6b2ed-223">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-223">**Return Value**</span></span> 

<span data-ttu-id="6b2ed-224">Случайное значение типа `Double` от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-224">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="6b2ed-225">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-225">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a><span data-ttu-id="6b2ed-226">Round(Numeric_Expression, length[,Function])</span><span class="sxs-lookup"><span data-stu-id="6b2ed-226">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="6b2ed-227">Возвращает числовое выражение, округленное до указанной длины или точности.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-227">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="6b2ed-228">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-228">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="6b2ed-229">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-229">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="6b2ed-230">Значение типа `Int32`, указывающее точность, до которой должно быть округлено значение аргумента `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-230">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="6b2ed-231">Если аргумент `length` является положительным числом, значение `numeric_expression` округляется до числа десятичных разрядов, указанных аргументом `length`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-231">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="6b2ed-232">Если аргумент `length` является отрицательным числом, значение `numeric_expression` округляется слева от десятичной запятой, как указано аргументом `length`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-232">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="6b2ed-233">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-233">Optional.</span></span> <span data-ttu-id="6b2ed-234">`Int32` , Представляющий тип выполняемой операции.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-234">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="6b2ed-235">Если функция указан или имеет значение 0 (по умолчанию), `numeric_expression` округляется.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-235">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="6b2ed-236">Если значение, отличное от указано значение 0, `numeric_expression` усекается.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-236">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="6b2ed-237">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-237">**Return Value**</span></span> 

<span data-ttu-id="6b2ed-238">Значение заданного выражения `numeric_expression` в указанной степени `power_expression`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-238">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="6b2ed-239">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-239">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="6b2ed-240">Sign(Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-240">SIGN(expression)</span></span> 

<span data-ttu-id="6b2ed-241">Возвращает положительный знак (+1), ноль (0) или отрицательный знак (-1) указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-241">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="6b2ed-242">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-242">**Arguments**</span></span> 

<span data-ttu-id="6b2ed-243">`expression`: `Int32`, `Int64`, `Double` или `Decimal`</span><span class="sxs-lookup"><span data-stu-id="6b2ed-243">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="6b2ed-244">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-244">**Return Value**</span></span> 

<span data-ttu-id="6b2ed-245">`Int32`, `Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-245">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="6b2ed-246">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-246">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="6b2ed-247">SIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-247">SIN(expression)</span></span>

<span data-ttu-id="6b2ed-248">Вычисляет тригонометрический синус заданного угла в радианах и возвращает выражение типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-248">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="6b2ed-249">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-249">**Arguments**</span></span> 

<span data-ttu-id="6b2ed-250">`expression`: Тип `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-250">`expression`: A `Double`.</span></span> 

<span data-ttu-id="6b2ed-251">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-251">**Return Value**</span></span> 

<span data-ttu-id="6b2ed-252">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-252">A `Double`.</span></span> 

<span data-ttu-id="6b2ed-253">**Пример** `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="6b2ed-253">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="6b2ed-254">SQRT(Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-254">SQRT(expression)</span></span>

<span data-ttu-id="6b2ed-255">Возвращает квадратный корень указанного выражения.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-255">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="6b2ed-256">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-256">**Arguments**</span></span> 

<span data-ttu-id="6b2ed-257">`expression`: Тип `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-257">`expression`: A `Double`.</span></span> 

<span data-ttu-id="6b2ed-258">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-258">**Return Value**</span></span> 

<span data-ttu-id="6b2ed-259">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-259">A `Double`.</span></span> 

<span data-ttu-id="6b2ed-260">**Пример** `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="6b2ed-260">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="6b2ed-261">Square(Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-261">SQUARE(expression)</span></span>

<span data-ttu-id="6b2ed-262">Возвращает значение указанного выражения в квадрате.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-262">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="6b2ed-263">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-263">**Arguments**</span></span> 

<span data-ttu-id="6b2ed-264">`expression`: Тип `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-264">`expression`: A `Double`.</span></span> 

<span data-ttu-id="6b2ed-265">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-265">**Return Value**</span></span> 

<span data-ttu-id="6b2ed-266">Объект `Double`.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-266">A `Double`.</span></span> 

<span data-ttu-id="6b2ed-267">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-267">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="6b2ed-268">TAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-268">TAN(expression)</span></span>

<span data-ttu-id="6b2ed-269">Вычисляет тангенс заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-269">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="6b2ed-270">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-270">**Arguments**</span></span> 

<span data-ttu-id="6b2ed-271">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="6b2ed-271">`expression`: `Double`</span></span> 

<span data-ttu-id="6b2ed-272">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-272">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="6b2ed-273">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6b2ed-273">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="6b2ed-274">См. также</span><span class="sxs-lookup"><span data-stu-id="6b2ed-274">See also</span></span>

<span data-ttu-id="6b2ed-275">Дополнительные сведения о математических функциях, поддерживаемых SqlClient, см. в документации к версии SQL Server, указанной в манифесте поставщика SqlClient.</span><span class="sxs-lookup"><span data-stu-id="6b2ed-275">For more information about the mathematical functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>  
  
<span data-ttu-id="6b2ed-276">**SQL Server 2005:** [математические функции (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="6b2ed-276">**SQL Server 2005:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span></span>  
<span data-ttu-id="6b2ed-277">**SQL Server 2008:** [математические функции (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="6b2ed-277">**SQL Server 2008:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span></span>  
<span data-ttu-id="6b2ed-278">**SQL Server 2012 и более поздних версий:** [математические функции (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span><span class="sxs-lookup"><span data-stu-id="6b2ed-278">**SQL Server 2012 and later:** [Mathematical Functions (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span></span>   

 [<span data-ttu-id="6b2ed-279">Функции SqlClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="6b2ed-279">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
