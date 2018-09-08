---
title: Математические канонические функции
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 0fc9f4942c3f76f139ab7e4400005f0bfe80204e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44204686"
---
# <a name="math-canonical-functions"></a><span data-ttu-id="10949-102">Математические канонические функции</span><span class="sxs-lookup"><span data-stu-id="10949-102">Math Canonical Functions</span></span>

<span data-ttu-id="10949-103">Язык Entity SQL включает в себя следующие математические канонические функции:</span><span class="sxs-lookup"><span data-stu-id="10949-103">Entity SQL includes the following math canonical functions:</span></span>
  
## <a name="absvalue"></a><span data-ttu-id="10949-104">Abs(значение)</span><span class="sxs-lookup"><span data-stu-id="10949-104">Abs(value)</span></span>

<span data-ttu-id="10949-105">Возвращает абсолютное значение `value`.</span><span class="sxs-lookup"><span data-stu-id="10949-105">Returns the absolute value of `value`.</span></span>

<span data-ttu-id="10949-106">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="10949-106">**Arguments**</span></span>

<span data-ttu-id="10949-107">`Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, И `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="10949-107">An `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="10949-108">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="10949-108">**Return Value**</span></span>

<span data-ttu-id="10949-109">Тип параметра `value`.</span><span class="sxs-lookup"><span data-stu-id="10949-109">The type of `value`.</span></span>

<span data-ttu-id="10949-110">**Пример**</span><span class="sxs-lookup"><span data-stu-id="10949-110">**Example**</span></span>

`Abs(-2)`

## <a name="ceilingvalue"></a><span data-ttu-id="10949-111">Ceiling(value)</span><span class="sxs-lookup"><span data-stu-id="10949-111">Ceiling(value)</span></span>

<span data-ttu-id="10949-112">Возвращает наименьшее целое число, которое не меньше значения `value`.</span><span class="sxs-lookup"><span data-stu-id="10949-112">Returns the smallest integer that is not less than `value`.</span></span>

<span data-ttu-id="10949-113">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="10949-113">**Arguments**</span></span>

<span data-ttu-id="10949-114">Объект `Single`, `Double`, и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="10949-114">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="10949-115">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="10949-115">**Return Value**</span></span>

<span data-ttu-id="10949-116">Тип параметра `value`.</span><span class="sxs-lookup"><span data-stu-id="10949-116">The type of `value`.</span></span>

<span data-ttu-id="10949-117">**Пример**</span><span class="sxs-lookup"><span data-stu-id="10949-117">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a><span data-ttu-id="10949-118">Floor(value)</span><span class="sxs-lookup"><span data-stu-id="10949-118">Floor(value)</span></span>

<span data-ttu-id="10949-119">Возвращает наибольшее целое число, которое не больше значения `value`.</span><span class="sxs-lookup"><span data-stu-id="10949-119">Returns the largest integer that is not greater than `value`.</span></span>

<span data-ttu-id="10949-120">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="10949-120">**Arguments**</span></span>

<span data-ttu-id="10949-121">Объект `Single`, `Double`, и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="10949-121">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="10949-122">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="10949-122">**Return Value**</span></span>

<span data-ttu-id="10949-123">Тип параметра `value`.</span><span class="sxs-lookup"><span data-stu-id="10949-123">The type of `value`.</span></span>

<span data-ttu-id="10949-124">**Пример**</span><span class="sxs-lookup"><span data-stu-id="10949-124">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a><span data-ttu-id="10949-125">Power(значение, показатель степени)</span><span class="sxs-lookup"><span data-stu-id="10949-125">Power(value, exponent)</span></span>

<span data-ttu-id="10949-126">Возвращает результат для заданного значения `value` по заданному показателю `exponent`.</span><span class="sxs-lookup"><span data-stu-id="10949-126">Returns the result of the specified `value` to the specified `exponent`.</span></span>

<span data-ttu-id="10949-127">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="10949-127">**Arguments**</span></span>

|  |  |
|--|--|
|`value` | <span data-ttu-id="10949-128">`Int32, Int64, Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="10949-128">An `Int32, Int64, Double`, or `Decimal`.</span></span> |
|`exponent` | <span data-ttu-id="10949-129">`Int64`, `Double`, Или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="10949-129">An `Int64`, `Double`, or `Decimal`.</span></span> |

<span data-ttu-id="10949-130">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="10949-130">**Return Value**</span></span>

<span data-ttu-id="10949-131">Тип параметра `value`.</span><span class="sxs-lookup"><span data-stu-id="10949-131">The type of `value`.</span></span>

<span data-ttu-id="10949-132">**Пример**</span><span class="sxs-lookup"><span data-stu-id="10949-132">**Example**</span></span>

`Power(748.58,2)`

## <a name="roundvalue"></a><span data-ttu-id="10949-133">Round(value)</span><span class="sxs-lookup"><span data-stu-id="10949-133">Round(value)</span></span>

<span data-ttu-id="10949-134">Возвращает целую часть `value`, округленную до ближайшего целого значения.</span><span class="sxs-lookup"><span data-stu-id="10949-134">Returns the integer portion of `value`, rounded to the nearest integer.</span></span>

<span data-ttu-id="10949-135">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="10949-135">**Arguments**</span></span>

<span data-ttu-id="10949-136">Объект `Single`, `Double`, и `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="10949-136">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="10949-137">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="10949-137">**Return Value**</span></span>

<span data-ttu-id="10949-138">Тип параметра `value`.</span><span class="sxs-lookup"><span data-stu-id="10949-138">The type of `value`.</span></span>

<span data-ttu-id="10949-139">**Пример**</span><span class="sxs-lookup"><span data-stu-id="10949-139">**Example**</span></span>

`Round(748.58)`

## <a name="roundvalue-digits"></a><span data-ttu-id="10949-140">Round(значение, количество знаков)</span><span class="sxs-lookup"><span data-stu-id="10949-140">Round(value, digits)</span></span>

<span data-ttu-id="10949-141">Возвращает значение `value`, округленное до ближайшего указанного знака `digits`.</span><span class="sxs-lookup"><span data-stu-id="10949-141">Returns the `value`, rounded to the nearest specified `digits`.</span></span>

<span data-ttu-id="10949-142">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="10949-142">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="10949-143">`Double` или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="10949-143">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="10949-144">`Int16` или `Int32`.</span><span class="sxs-lookup"><span data-stu-id="10949-144">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="10949-145">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="10949-145">**Return Value**</span></span>

<span data-ttu-id="10949-146">Тип параметра `value`.</span><span class="sxs-lookup"><span data-stu-id="10949-146">The type of `value`.</span></span>

<span data-ttu-id="10949-147">**Пример**</span><span class="sxs-lookup"><span data-stu-id="10949-147">**Example**</span></span>

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a><span data-ttu-id="10949-148">Truncate(значение, количество знаков)</span><span class="sxs-lookup"><span data-stu-id="10949-148">Truncate(value, digits)</span></span>

<span data-ttu-id="10949-149">Возвращает значение `value`, усеченное до ближайшего указанного знака `digits`.</span><span class="sxs-lookup"><span data-stu-id="10949-149">Returns the `value`, truncated to the nearest specified `digits`.</span></span>

<span data-ttu-id="10949-150">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="10949-150">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="10949-151">`Double` или `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="10949-151">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="10949-152">`Int16` или `Int32`.</span><span class="sxs-lookup"><span data-stu-id="10949-152">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="10949-153">**Возвращаемое значение**</span><span class="sxs-lookup"><span data-stu-id="10949-153">**Return Value**</span></span>

<span data-ttu-id="10949-154">Тип параметра `value`.</span><span class="sxs-lookup"><span data-stu-id="10949-154">The type of `value`.</span></span>

<span data-ttu-id="10949-155">**Пример**</span><span class="sxs-lookup"><span data-stu-id="10949-155">**Example**</span></span>

`Truncate(748.58,1)`  
  
 <span data-ttu-id="10949-156">Эти функции возвращают `null` при получении на входе `null`.</span><span class="sxs-lookup"><span data-stu-id="10949-156">These functions will return `null` if given `null` input.</span></span>  
  
 <span data-ttu-id="10949-157">Эквивалентную функциональность предоставляет управляемый поставщик клиента Microsoft SQL.</span><span class="sxs-lookup"><span data-stu-id="10949-157">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="10949-158">Дополнительные сведения см. в разделе [функции SqlClient для Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="10949-158">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10949-159">См. также</span><span class="sxs-lookup"><span data-stu-id="10949-159">See Also</span></span>  
 [<span data-ttu-id="10949-160">Канонические функции</span><span class="sxs-lookup"><span data-stu-id="10949-160">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
