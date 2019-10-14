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
- size of floating-point types [C#]
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: 17ae154780679dd1f42f43f1ec345cdc722815d3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002195"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="14bdc-103">Числовые типы с плавающей запятой (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="14bdc-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="14bdc-104">**Типы с плавающей запятой** — это подмножество **простых типов**. Они могут инициализироваться [*литералами*](#floating-point-literals).</span><span class="sxs-lookup"><span data-stu-id="14bdc-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#floating-point-literals).</span></span> <span data-ttu-id="14bdc-105">Все типы с плавающей запятой также являются типами значений.</span><span class="sxs-lookup"><span data-stu-id="14bdc-105">All floating-point types are also value types.</span></span> <span data-ttu-id="14bdc-106">Все числовые типы с плавающей запятой поддерживают [арифметические](../operators/arithmetic-operators.md) операторы, а также операторы [сравнения и равенства](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="14bdc-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="14bdc-107">Характеристики типов с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="14bdc-107">Characteristics of the floating-point types</span></span>

<span data-ttu-id="14bdc-108">C# поддерживает следующие предварительно определенные типы с плавающей запятой:</span><span class="sxs-lookup"><span data-stu-id="14bdc-108">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="14bdc-109">Ключевое слово или тип C#</span><span class="sxs-lookup"><span data-stu-id="14bdc-109">C# type/keyword</span></span>|<span data-ttu-id="14bdc-110">Приблизительный диапазон значений</span><span class="sxs-lookup"><span data-stu-id="14bdc-110">Approximate range</span></span>|<span data-ttu-id="14bdc-111">Точность</span><span class="sxs-lookup"><span data-stu-id="14bdc-111">Precision</span></span>|<span data-ttu-id="14bdc-112">Размер</span><span class="sxs-lookup"><span data-stu-id="14bdc-112">Size</span></span>|<span data-ttu-id="14bdc-113">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="14bdc-113">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="14bdc-114">От ±1,5 x 10<sup>−45</sup> до ±3,4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="14bdc-114">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="14bdc-115">6–9 цифр</span><span class="sxs-lookup"><span data-stu-id="14bdc-115">~6-9 digits</span></span>|<span data-ttu-id="14bdc-116">4 байта</span><span class="sxs-lookup"><span data-stu-id="14bdc-116">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="14bdc-117">от ±5,0 × 10<sup>−324</sup> до ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="14bdc-117">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="14bdc-118">15–17 цифр</span><span class="sxs-lookup"><span data-stu-id="14bdc-118">~15-17 digits</span></span>|<span data-ttu-id="14bdc-119">8 байт</span><span class="sxs-lookup"><span data-stu-id="14bdc-119">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="14bdc-120">от ±1,0 x 10<sup>-28</sup> до ±7,9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="14bdc-120">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="14bdc-121">28-29 знаков</span><span class="sxs-lookup"><span data-stu-id="14bdc-121">28-29 digits</span></span>|<span data-ttu-id="14bdc-122">16 байт</span><span class="sxs-lookup"><span data-stu-id="14bdc-122">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="14bdc-123">В приведенной выше таблице каждый тип ключевого слова C# из крайнего левого столбца является псевдонимом для соответствующего типа .NET.</span><span class="sxs-lookup"><span data-stu-id="14bdc-123">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="14bdc-124">Они взаимозаменяемые.</span><span class="sxs-lookup"><span data-stu-id="14bdc-124">They are interchangeable.</span></span> <span data-ttu-id="14bdc-125">Например, следующие объявления объявляют переменные одного типа:</span><span class="sxs-lookup"><span data-stu-id="14bdc-125">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="14bdc-126">По умолчанию все типы с плавающей запятой имеют значение `0`.</span><span class="sxs-lookup"><span data-stu-id="14bdc-126">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="14bdc-127">Все типы с плавающей запятой имеют константы `MinValue` и `MaxValue` с минимальным и максимальными итоговыми значениями этого типа.</span><span class="sxs-lookup"><span data-stu-id="14bdc-127">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="14bdc-128">Типы `float` и `double` также предоставляют константы, обозначающие бесконечные и нечисловые значения.</span><span class="sxs-lookup"><span data-stu-id="14bdc-128">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="14bdc-129">Например, тип `double` предоставляет следующие константы: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> и <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="14bdc-129">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="14bdc-130">Так как тип `decimal` характеризуется более высокой точностью и меньшим диапазоном, чем `float` и `double`, он подходит для финансовых расчетов.</span><span class="sxs-lookup"><span data-stu-id="14bdc-130">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="14bdc-131">В одном и том же выражении можно сочетать и [целочисленные типы](integral-numeric-types.md), и типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="14bdc-131">You can mix [integral](integral-numeric-types.md) types and floating-point types in an expression.</span></span> <span data-ttu-id="14bdc-132">В этом случае целочисленные типы преобразуются в типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="14bdc-132">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="14bdc-133">Выражение вычисляется по следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="14bdc-133">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="14bdc-134">Если одним из типов с плавающей запятой является `double`, то выражение оценивается как `double` или [bool](../keywords/bool.md) в реляционных сравнениях или сравнениях на равенство.</span><span class="sxs-lookup"><span data-stu-id="14bdc-134">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>
- <span data-ttu-id="14bdc-135">Если в выражении нет типа `double`, оно оценивается как `float` или [bool](../keywords/bool.md) в реляционных сравнениях или сравнениях на равенство.</span><span class="sxs-lookup"><span data-stu-id="14bdc-135">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>

<span data-ttu-id="14bdc-136">Выражение с плавающей запятой может содержать следующие наборы значений:</span><span class="sxs-lookup"><span data-stu-id="14bdc-136">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="14bdc-137">Положительный и отрицательный ноль</span><span class="sxs-lookup"><span data-stu-id="14bdc-137">Positive and negative zero</span></span>
- <span data-ttu-id="14bdc-138">Положительная и отрицательная бесконечность</span><span class="sxs-lookup"><span data-stu-id="14bdc-138">Positive and negative infinity</span></span>
- <span data-ttu-id="14bdc-139">Нечисловое значение (NaN)</span><span class="sxs-lookup"><span data-stu-id="14bdc-139">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="14bdc-140">Конечный набор ненулевых значений</span><span class="sxs-lookup"><span data-stu-id="14bdc-140">The finite set of nonzero values</span></span>

<span data-ttu-id="14bdc-141">Дополнительные сведения об этих значениях см. в документе "Стандарт IEEE для двоичной арифметики с плавающей запятой" на веб-сайте [IEEE](https://www.ieee.org).</span><span class="sxs-lookup"><span data-stu-id="14bdc-141">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="14bdc-142">Можно использовать [строки стандартных числовых форматов](../../../standard/base-types/standard-numeric-format-strings.md) или [строки пользовательских числовых форматов](../../../standard/base-types/custom-numeric-format-strings.md) для форматирования значения с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="14bdc-142">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="floating-point-literals"></a><span data-ttu-id="14bdc-143">Литералы с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="14bdc-143">Floating-point literals</span></span>

<span data-ttu-id="14bdc-144">По умолчанию числовой литерал с плавающей запятой в правой части оператора присваивания обрабатывается как `double`.</span><span class="sxs-lookup"><span data-stu-id="14bdc-144">By default, a floating-point numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="14bdc-145">Суффиксы можно использовать для преобразования литерала с плавающей запятой или целочисленного литерала в определенный тип:</span><span class="sxs-lookup"><span data-stu-id="14bdc-145">You can use suffixes to convert a floating-point or integral literal to a specific type:</span></span>

- <span data-ttu-id="14bdc-146">Суффикс `d` или `D` преобразует литерал в `double`.</span><span class="sxs-lookup"><span data-stu-id="14bdc-146">The `d` or `D` suffix converts a literal to a `double`.</span></span>
- <span data-ttu-id="14bdc-147">Суффикс `f` или `F` преобразует литерал в `float`.</span><span class="sxs-lookup"><span data-stu-id="14bdc-147">The `f` or `F` suffix converts a literal to a `float`.</span></span>
- <span data-ttu-id="14bdc-148">Суффикс `m` или `M` преобразует литерал в `decimal`.</span><span class="sxs-lookup"><span data-stu-id="14bdc-148">The `m` or `M` suffix converts a literal to a `decimal`.</span></span>

<span data-ttu-id="14bdc-149">В следующем примере показан каждый суффикс:</span><span class="sxs-lookup"><span data-stu-id="14bdc-149">The following examples show each suffix:</span></span>

```csharp
double d = 3D;
d = 4d;
float f = 3.5F;
f = 5.4f;
decimal myMoney = 300.5m;
myMoney = 400.75M;
```

## <a name="conversions"></a><span data-ttu-id="14bdc-150">Преобразования</span><span class="sxs-lookup"><span data-stu-id="14bdc-150">Conversions</span></span>

<span data-ttu-id="14bdc-151">Существует неявное преобразование (называемое *расширяющим преобразованием*) из `float` в `double`, так как диапазон значений `float` является строгим подмножеством объекта `double` и при преобразовании из `float` в `double` не теряется точность.</span><span class="sxs-lookup"><span data-stu-id="14bdc-151">There's an implicit conversion (called a *widening conversion*) from `float` to `double` because the range of `float` values is a proper subset of `double` and there is no loss of precision from `float` to `double`.</span></span>

<span data-ttu-id="14bdc-152">Если неявное преобразование между двумя типами с плавающей запятой не определено, необходимо использовать явное приведение.</span><span class="sxs-lookup"><span data-stu-id="14bdc-152">You must use an explicit cast to convert one floating-point type to another floating-point type when an implicit conversion isn't defined from the source type to the destination type.</span></span> <span data-ttu-id="14bdc-153">Это называется *сужающим преобразованием*.</span><span class="sxs-lookup"><span data-stu-id="14bdc-153">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="14bdc-154">Явное приведение требуется по той причине, что преобразование может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="14bdc-154">The explicit case is required because the conversion can result in data loss.</span></span> <span data-ttu-id="14bdc-155">Не существует неявного преобразования между другими типами с плавающей запятой и типом `decimal`, так как тип `decimal` имеет большую точность, чем `float` или `double`.</span><span class="sxs-lookup"><span data-stu-id="14bdc-155">There's no implicit conversion between other floating-point types and the `decimal` type because the `decimal` type has greater precision than either `float` or `double`.</span></span>

<span data-ttu-id="14bdc-156">Дополнительные сведения о неявных числовых преобразованиях см. в разделе [Таблица неявных числовых преобразований](../keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="14bdc-156">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="14bdc-157">Дополнительные сведения о явных числовых преобразованиях см. в разделе [Таблица явных числовых преобразований](../keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="14bdc-157">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="14bdc-158">См. также</span><span class="sxs-lookup"><span data-stu-id="14bdc-158">See also</span></span>

- [<span data-ttu-id="14bdc-159">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="14bdc-159">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="14bdc-160">Целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="14bdc-160">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="14bdc-161">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="14bdc-161">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="14bdc-162">Числовые значения в .NET</span><span class="sxs-lookup"><span data-stu-id="14bdc-162">Numerics in .NET</span></span>](../../../standard/numerics.md)
- [<span data-ttu-id="14bdc-163">Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="14bdc-163">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="14bdc-164">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="14bdc-164">Implicit Numeric Conversions Table</span></span>](../keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="14bdc-165">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="14bdc-165">Explicit Numeric Conversions Table</span></span>](../keywords/explicit-numeric-conversions-table.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [<span data-ttu-id="14bdc-166">Таблица форматирования числовых результатов</span><span class="sxs-lookup"><span data-stu-id="14bdc-166">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="14bdc-167">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="14bdc-167">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
