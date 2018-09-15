---
title: Математические канонические функции
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 0fc9f4942c3f76f139ab7e4400005f0bfe80204e
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2018
ms.locfileid: "45653191"
---
# <a name="math-canonical-functions"></a><span data-ttu-id="e662f-102">Математические канонические функции</span><span class="sxs-lookup"><span data-stu-id="e662f-102">Math Canonical Functions</span></span>

<span data-ttu-id="e662f-103">Язык Entity SQL включает в себя следующие математические канонические функции:</span><span class="sxs-lookup"><span data-stu-id="e662f-103">Entity SQL includes the following math canonical functions:</span></span>
  
## <a name="absvalue"></a><span data-ttu-id="e662f-104">Abs(значение)</span><span class="sxs-lookup"><span data-stu-id="e662f-104">Abs(value)</span></span>

<span data-ttu-id="e662f-105">Возвращает абсолютное значение `value`.</span><span class="sxs-lookup"><span data-stu-id="e662f-105">Returns the absolute value of `value`.</span></span>

<span data-ttu-id="e662f-106">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="e662f-106">**Arguments**</span></span>

<span data-ttu-id="e662f-107">`Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, И `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="e662f-107">An `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="e662f-108">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="e662f-108">**Return Value**</span></span>

<span data-ttu-id="e662f-109">Тип параметра `value`.</span><span class="sxs-lookup"><span data-stu-id="e662f-109">The type of `value`.</span></span>

<span data-ttu-id="e662f-110">**Пример**</span><span class="sxs-lookup"><span data-stu-id="e662f-110">**Example**</span></span>

`Abs(-2)`

## <a name="ceilingvalue"></a><span data-ttu-id="e662f-111">Ceiling(value)</span><span class="sxs-lookup"><span data-stu-id="e662f-111">Ceiling(value)</span></span>

<span data-ttu-id="e662f-112">Возвращает наименьшее целое число, которое не меньше значения `value`.</span><span class="sxs-lookup"><span data-stu-id="e662f-112">Returns the smallest integer that is not less than `value`.</span></span>

<span data-ttu-id="e662f-113">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="e662f-113">**Arguments**</span></span>

<span data-ttu-id="e662f-114">Объект `Single`, `Double`, и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="e662f-114">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="e662f-115">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="e662f-115">**Return Value**</span></span>

<span data-ttu-id="e662f-116">Тип параметра `value`.</span><span class="sxs-lookup"><span data-stu-id="e662f-116">The type of `value`.</span></span>

<span data-ttu-id="e662f-117">**Пример**</span><span class="sxs-lookup"><span data-stu-id="e662f-117">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a><span data-ttu-id="e662f-118">Floor(value)</span><span class="sxs-lookup"><span data-stu-id="e662f-118">Floor(value)</span></span>

<span data-ttu-id="e662f-119">Возвращает наибольшее целое число, которое не больше значения `value`.</span><span class="sxs-lookup"><span data-stu-id="e662f-119">Returns the largest integer that is not greater than `value`.</span></span>

<span data-ttu-id="e662f-120">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="e662f-120">**Arguments**</span></span>

<span data-ttu-id="e662f-121">Объект `Single`, `Double`, и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="e662f-121">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="e662f-122">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="e662f-122">**Return Value**</span></span>

<span data-ttu-id="e662f-123">Тип параметра `value`.</span><span class="sxs-lookup"><span data-stu-id="e662f-123">The type of `value`.</span></span>

<span data-ttu-id="e662f-124">**Пример**</span><span class="sxs-lookup"><span data-stu-id="e662f-124">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a><span data-ttu-id="e662f-125">Power(значение, показатель степени)</span><span class="sxs-lookup"><span data-stu-id="e662f-125">Power(value, exponent)</span></span>

<span data-ttu-id="e662f-126">Возвращает результат для заданного значения `value` по заданному показателю `exponent`.</span><span class="sxs-lookup"><span data-stu-id="e662f-126">Returns the result of the specified `value` to the specified `exponent`.</span></span>

<span data-ttu-id="e662f-127">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="e662f-127">**Arguments**</span></span>

|  |  |
|--|--|
|`value` | <span data-ttu-id="e662f-128">`Int32, Int64, Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="e662f-128">An `Int32, Int64, Double`, or `Decimal`.</span></span> |
|`exponent` | <span data-ttu-id="e662f-129">`Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="e662f-129">An `Int64`, `Double`, or `Decimal`.</span></span> |

<span data-ttu-id="e662f-130">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="e662f-130">**Return Value**</span></span>

<span data-ttu-id="e662f-131">Тип параметра `value`.</span><span class="sxs-lookup"><span data-stu-id="e662f-131">The type of `value`.</span></span>

<span data-ttu-id="e662f-132">**Пример**</span><span class="sxs-lookup"><span data-stu-id="e662f-132">**Example**</span></span>

`Power(748.58,2)`

## <a name="roundvalue"></a><span data-ttu-id="e662f-133">Round(value)</span><span class="sxs-lookup"><span data-stu-id="e662f-133">Round(value)</span></span>

<span data-ttu-id="e662f-134">Возвращает целую часть `value`, округленную до ближайшего целого значения.</span><span class="sxs-lookup"><span data-stu-id="e662f-134">Returns the integer portion of `value`, rounded to the nearest integer.</span></span>

<span data-ttu-id="e662f-135">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="e662f-135">**Arguments**</span></span>

<span data-ttu-id="e662f-136">Объект `Single`, `Double`, и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="e662f-136">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="e662f-137">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="e662f-137">**Return Value**</span></span>

<span data-ttu-id="e662f-138">Тип параметра `value`.</span><span class="sxs-lookup"><span data-stu-id="e662f-138">The type of `value`.</span></span>

<span data-ttu-id="e662f-139">**Пример**</span><span class="sxs-lookup"><span data-stu-id="e662f-139">**Example**</span></span>

`Round(748.58)`

## <a name="roundvalue-digits"></a><span data-ttu-id="e662f-140">Round(значение, количество знаков)</span><span class="sxs-lookup"><span data-stu-id="e662f-140">Round(value, digits)</span></span>

<span data-ttu-id="e662f-141">Возвращает значение `value`, округленное до ближайшего указанного знака `digits`.</span><span class="sxs-lookup"><span data-stu-id="e662f-141">Returns the `value`, rounded to the nearest specified `digits`.</span></span>

<span data-ttu-id="e662f-142">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="e662f-142">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="e662f-143">`Double` или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="e662f-143">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="e662f-144">`Int16` или `Int32`.</span><span class="sxs-lookup"><span data-stu-id="e662f-144">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="e662f-145">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="e662f-145">**Return Value**</span></span>

<span data-ttu-id="e662f-146">Тип параметра `value`.</span><span class="sxs-lookup"><span data-stu-id="e662f-146">The type of `value`.</span></span>

<span data-ttu-id="e662f-147">**Пример**</span><span class="sxs-lookup"><span data-stu-id="e662f-147">**Example**</span></span>

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a><span data-ttu-id="e662f-148">Truncate(значение, количество знаков)</span><span class="sxs-lookup"><span data-stu-id="e662f-148">Truncate(value, digits)</span></span>

<span data-ttu-id="e662f-149">Возвращает значение `value`, усеченное до ближайшего указанного знака `digits`.</span><span class="sxs-lookup"><span data-stu-id="e662f-149">Returns the `value`, truncated to the nearest specified `digits`.</span></span>

<span data-ttu-id="e662f-150">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="e662f-150">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="e662f-151">`Double` или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="e662f-151">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="e662f-152">`Int16` или `Int32`.</span><span class="sxs-lookup"><span data-stu-id="e662f-152">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="e662f-153">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="e662f-153">**Return Value**</span></span>

<span data-ttu-id="e662f-154">Тип параметра `value`.</span><span class="sxs-lookup"><span data-stu-id="e662f-154">The type of `value`.</span></span>

<span data-ttu-id="e662f-155">**Пример**</span><span class="sxs-lookup"><span data-stu-id="e662f-155">**Example**</span></span>

`Truncate(748.58,1)`  
  
 <span data-ttu-id="e662f-156">Эти функции возвращают `null` при получении на входе `null`.</span><span class="sxs-lookup"><span data-stu-id="e662f-156">These functions will return `null` if given `null` input.</span></span>  
  
 <span data-ttu-id="e662f-157">Эквивалентную функциональность предоставляет управляемый поставщик клиента Microsoft SQL.</span><span class="sxs-lookup"><span data-stu-id="e662f-157">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="e662f-158">Дополнительные сведения см. в разделе [функции SqlClient для Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="e662f-158">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e662f-159">См. также</span><span class="sxs-lookup"><span data-stu-id="e662f-159">See Also</span></span>  
 [<span data-ttu-id="e662f-160">Канонические функции</span><span class="sxs-lookup"><span data-stu-id="e662f-160">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
