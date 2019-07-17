---
title: Числовые типы с плавающей запятой — справочник по C#
description: Общие сведения о встроенных типах с плавающей запятой в C#
ms.date: 06/30/2019
f1_keywords:
- float
- float_CSharpKeyword
- double
- double_CSharpKeyword
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- floating-point numbers [C#]
- ranges of floating-point types [C#]
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: 738368abd9db75fbd97d1913324cab3b6e869c56
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67664194"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="f0984-103">Числовые типы с плавающей запятой (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f0984-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="f0984-104">**Типы с плавающей запятой** — это подмножество **простых типов**. Они могут инициализироваться [*литералами*](#floating-point-literals).</span><span class="sxs-lookup"><span data-stu-id="f0984-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#floating-point-literals).</span></span> <span data-ttu-id="f0984-105">Все типы с плавающей запятой также являются типами значений.</span><span class="sxs-lookup"><span data-stu-id="f0984-105">All floating-point types are also value types.</span></span> <span data-ttu-id="f0984-106">Все числовые типы с плавающей запятой поддерживают [арифметические](../operators/arithmetic-operators.md) операторы, операторы [сравнения и равенства](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="f0984-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md) [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

<span data-ttu-id="f0984-107">В приведенной ниже таблице представлен точный и приблизительный диапазон значений для типов с плавающей запятой:</span><span class="sxs-lookup"><span data-stu-id="f0984-107">The following table shows the precision and approximate ranges for the floating-point types:</span></span>
  
|<span data-ttu-id="f0984-108">Тип</span><span class="sxs-lookup"><span data-stu-id="f0984-108">Type</span></span>|<span data-ttu-id="f0984-109">Приблизительный диапазон значений</span><span class="sxs-lookup"><span data-stu-id="f0984-109">Approximate range</span></span>|<span data-ttu-id="f0984-110">Точность</span><span class="sxs-lookup"><span data-stu-id="f0984-110">Precision</span></span>|  
|----------|-----------------------|---------------|  
|`float`|<span data-ttu-id="f0984-111">От ±1,5 x 10<sup>−45</sup> до ±3,4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="f0984-111">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="f0984-112">6–9 цифр</span><span class="sxs-lookup"><span data-stu-id="f0984-112">~6-9 digits</span></span>|  
|`double`|<span data-ttu-id="f0984-113">от ±5,0 × 10<sup>−324</sup> до ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="f0984-113">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="f0984-114">15–17 цифр</span><span class="sxs-lookup"><span data-stu-id="f0984-114">~15-17 digits</span></span>|  
|`decimal`|<span data-ttu-id="f0984-115">от ±1,0 x 10<sup>-28</sup> до ±7,9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="f0984-115">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="f0984-116">28-29 знаков</span><span class="sxs-lookup"><span data-stu-id="f0984-116">28-29 digits</span></span>|  

<span data-ttu-id="f0984-117">По умолчанию типы с плавающей запятой имеют значение `0`.</span><span class="sxs-lookup"><span data-stu-id="f0984-117">The default value for all floating-point types is `0`.</span></span> <span data-ttu-id="f0984-118">Каждый тип с плавающей запятой имеет константы `MinValue` и `MaxValue` с минимальным и максимальным значениями этого типа.</span><span class="sxs-lookup"><span data-stu-id="f0984-118">Each of the floating-point types has constants named `MinValue` and `MaxValue` for the minimum and maximum value for that type.</span></span> <span data-ttu-id="f0984-119">Типы `float` и `double` имеют дополнительные константы для `PositiveInfinity`, `NegativeInfinity` и `NaN` (для параметров "Не число").</span><span class="sxs-lookup"><span data-stu-id="f0984-119">The `float` and `double` types have additional constants for `PositiveInfinity`, `NegativeInfinity`, and `NaN` (for "Not a Number").</span></span> <span data-ttu-id="f0984-120">Тип `decimal` включает в себя константы для `Zero`, `One` и `MinusOne`.</span><span class="sxs-lookup"><span data-stu-id="f0984-120">The `decimal` type includes constants for `Zero`, `One`, and `MinusOne`.</span></span>

<span data-ttu-id="f0984-121">Типа `decimal` имеет более высокую точность и меньший диапазон, чем `float` и `double`, благодаря чему этот тип подходит для финансовых расчетов.</span><span class="sxs-lookup"><span data-stu-id="f0984-121">The `decimal` type has more precision and a smaller range than both `float` and `double`, which makes it appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="f0984-122">В одном и том же выражении можно сочетать и целочисленные типы, и типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="f0984-122">You can mix integral types and floating-point types in an expression.</span></span> <span data-ttu-id="f0984-123">В этом случае целочисленные типы преобразуются в типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="f0984-123">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="f0984-124">Выражение вычисляется по следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="f0984-124">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="f0984-125">Если одним из типов с плавающей запятой является `double`, то выражение оценивается как `double` или [bool](../keywords/bool.md) в реляционных сравнениях или сравнениях на равенство.</span><span class="sxs-lookup"><span data-stu-id="f0984-125">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>
- <span data-ttu-id="f0984-126">Если в выражении нет типа `double`, оно оценивается как `float` или [bool](../keywords/bool.md) в реляционных сравнениях или сравнениях на равенство.</span><span class="sxs-lookup"><span data-stu-id="f0984-126">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>

<span data-ttu-id="f0984-127">Выражение с плавающей запятой может содержать следующие наборы значений:</span><span class="sxs-lookup"><span data-stu-id="f0984-127">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="f0984-128">Положительный и отрицательный ноль</span><span class="sxs-lookup"><span data-stu-id="f0984-128">Positive and negative zero</span></span>
- <span data-ttu-id="f0984-129">Положительная и отрицательная бесконечность</span><span class="sxs-lookup"><span data-stu-id="f0984-129">Positive and negative infinity</span></span>
- <span data-ttu-id="f0984-130">Нечисловое значение (NaN)</span><span class="sxs-lookup"><span data-stu-id="f0984-130">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="f0984-131">Конечный набор ненулевых значений</span><span class="sxs-lookup"><span data-stu-id="f0984-131">The finite set of nonzero values</span></span>

<span data-ttu-id="f0984-132">Дополнительные сведения об этих значениях см. в документе "Стандарт IEEE для двоичной арифметики с плавающей запятой" на веб-сайте [IEEE](https://www.ieee.org).</span><span class="sxs-lookup"><span data-stu-id="f0984-132">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="f0984-133">Можно использовать [строки стандартных числовых форматов](../../../standard/base-types/standard-numeric-format-strings.md) или [строки пользовательских числовых форматов](../../../standard/base-types/custom-numeric-format-strings.md) для форматирования значения с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="f0984-133">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="floating-point-literals"></a><span data-ttu-id="f0984-134">Литералы с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f0984-134">Floating-point literals</span></span>

<span data-ttu-id="f0984-135">По умолчанию числовой литерал с плавающей запятой в правой части оператора присваивания обрабатывается как `double`.</span><span class="sxs-lookup"><span data-stu-id="f0984-135">By default, a floating-point numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="f0984-136">Суффиксы можно использовать для преобразования литерала с плавающей запятой или целочисленного литерала в определенный тип:</span><span class="sxs-lookup"><span data-stu-id="f0984-136">You can use suffixes to convert a floating-point or integral literal to a specific type:</span></span>

- <span data-ttu-id="f0984-137">Суффикс `d` или `D` преобразует литерал в `double`.</span><span class="sxs-lookup"><span data-stu-id="f0984-137">The `d` or `D` suffix converts a literal to a `double`.</span></span>
- <span data-ttu-id="f0984-138">Суффикс `f` или `F` преобразует литерал в `float`.</span><span class="sxs-lookup"><span data-stu-id="f0984-138">The `f` or `F` suffix converts a literal to a `float`.</span></span>
- <span data-ttu-id="f0984-139">Суффикс `m` или `M` преобразует литерал в `decimal`.</span><span class="sxs-lookup"><span data-stu-id="f0984-139">The `m` or `M` suffix converts a literal to a `decimal`.</span></span>

<span data-ttu-id="f0984-140">В следующем примере показан каждый суффикс:</span><span class="sxs-lookup"><span data-stu-id="f0984-140">The following examples show each suffix:</span></span>

```csharp
double d = 3D;
d = 4d;
float f = 3.5F;
f = 5.4f;
decimal myMoney = 300.5m;
myMoney = 400.75M;
```

## <a name="conversions"></a><span data-ttu-id="f0984-141">Преобразования</span><span class="sxs-lookup"><span data-stu-id="f0984-141">Conversions</span></span>

<span data-ttu-id="f0984-142">Существует неявное преобразование (называемое *расширяющим преобразованием*) из `float` в `double`, так как диапазон значений `float` является строгим подмножеством объекта `double` и при преобразовании из `float` в `double` не теряется точность.</span><span class="sxs-lookup"><span data-stu-id="f0984-142">There's an implicit conversion (called a *widening conversion*) from `float` to `double` because the range of `float` values is a proper subset of `double` and there is no loss of precision from `float` to `double`.</span></span> 

<span data-ttu-id="f0984-143">Если неявное преобразование между двумя типами с плавающей запятой не определено, необходимо использовать явное приведение.</span><span class="sxs-lookup"><span data-stu-id="f0984-143">You must use an explicit cast to convert one floating-point type to another floating-point type when an implicit conversion isn't defined from the source type to the destination type.</span></span> <span data-ttu-id="f0984-144">Это называется *сужающим преобразованием*.</span><span class="sxs-lookup"><span data-stu-id="f0984-144">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="f0984-145">Явное приведение требуется по той причине, что преобразование может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="f0984-145">The explicit case is required because the conversion can result in data loss.</span></span> <span data-ttu-id="f0984-146">Не существует неявного преобразования между другими типами с плавающей запятой и типом `decimal`, так как тип `decimal` имеет большую точность, чем `float` или `double`.</span><span class="sxs-lookup"><span data-stu-id="f0984-146">There's no implicit conversion between other floating-point types and the `decimal` type because the `decimal` type has greater precision than either `float` or `double`.</span></span>

<span data-ttu-id="f0984-147">Дополнительные сведения о неявных числовых преобразованиях см. в разделе [Таблица неявных числовых преобразований](../keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="f0984-147">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="f0984-148">Дополнительные сведения о явных числовых преобразованиях см. в разделе [Таблица явных числовых преобразований](../keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="f0984-148">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0984-149">См. также</span><span class="sxs-lookup"><span data-stu-id="f0984-149">See also</span></span>

- [<span data-ttu-id="f0984-150">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f0984-150">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f0984-151">Целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="f0984-151">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="f0984-152">Таблица значений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f0984-152">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="f0984-153">Таблица форматирования числовых результатов</span><span class="sxs-lookup"><span data-stu-id="f0984-153">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="f0984-154">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="f0984-154">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="f0984-155">Числовые значения в .NET</span><span class="sxs-lookup"><span data-stu-id="f0984-155">Numerics in .NET</span></span>](../../../standard/numerics.md)
- [<span data-ttu-id="f0984-156">Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="f0984-156">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="f0984-157">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="f0984-157">Implicit Numeric Conversions Table</span></span>](../keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="f0984-158">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="f0984-158">Explicit Numeric Conversions Table</span></span>](../keywords/explicit-numeric-conversions-table.md)
- <xref:System.Single?displayProperty=nameWithType>
- <xref:System.Double?displayProperty=nameWithType>
- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [<span data-ttu-id="f0984-159">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="f0984-159">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
