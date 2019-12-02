---
title: Числовые типы с плавающей запятой — справочник по C#
description: Общие сведения о встроенных типах с плавающей запятой в C#
ms.date: 10/22/2019
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
ms.openlocfilehash: 23aa33c6887db48a12f995efc5e1e2220d30216c
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552282"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="83229-103">Числовые типы с плавающей запятой (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="83229-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="83229-104">**Типы с плавающей запятой** — это подмножество **простых типов**. Они могут инициализироваться [*литералами*](#real-literals).</span><span class="sxs-lookup"><span data-stu-id="83229-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#real-literals).</span></span> <span data-ttu-id="83229-105">Все типы с плавающей запятой также являются типами значений.</span><span class="sxs-lookup"><span data-stu-id="83229-105">All floating-point types are also value types.</span></span> <span data-ttu-id="83229-106">Все числовые типы с плавающей запятой поддерживают [арифметические](../operators/arithmetic-operators.md) операторы, а также операторы [сравнения](../operators/comparison-operators.md) и [равенства](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="83229-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="83229-107">Характеристики типов с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="83229-107">Characteristics of the floating-point types</span></span>

<span data-ttu-id="83229-108">C# поддерживает следующие предварительно определенные типы с плавающей запятой:</span><span class="sxs-lookup"><span data-stu-id="83229-108">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="83229-109">Ключевое слово или тип C#</span><span class="sxs-lookup"><span data-stu-id="83229-109">C# type/keyword</span></span>|<span data-ttu-id="83229-110">Приблизительный диапазон значений</span><span class="sxs-lookup"><span data-stu-id="83229-110">Approximate range</span></span>|<span data-ttu-id="83229-111">Точность</span><span class="sxs-lookup"><span data-stu-id="83229-111">Precision</span></span>|<span data-ttu-id="83229-112">Размер</span><span class="sxs-lookup"><span data-stu-id="83229-112">Size</span></span>|<span data-ttu-id="83229-113">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="83229-113">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="83229-114">От ±1,5 x 10<sup>−45</sup> до ±3,4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="83229-114">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="83229-115">6–9 цифр</span><span class="sxs-lookup"><span data-stu-id="83229-115">~6-9 digits</span></span>|<span data-ttu-id="83229-116">4 байта</span><span class="sxs-lookup"><span data-stu-id="83229-116">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="83229-117">от ±5,0 × 10<sup>−324</sup> до ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="83229-117">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="83229-118">15–17 цифр</span><span class="sxs-lookup"><span data-stu-id="83229-118">~15-17 digits</span></span>|<span data-ttu-id="83229-119">8 байт</span><span class="sxs-lookup"><span data-stu-id="83229-119">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="83229-120">от ±1,0 x 10<sup>-28</sup> до ±7,9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="83229-120">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="83229-121">28-29 знаков</span><span class="sxs-lookup"><span data-stu-id="83229-121">28-29 digits</span></span>|<span data-ttu-id="83229-122">16 байт</span><span class="sxs-lookup"><span data-stu-id="83229-122">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="83229-123">В приведенной выше таблице каждый тип ключевого слова C# из крайнего левого столбца является псевдонимом для соответствующего типа .NET.</span><span class="sxs-lookup"><span data-stu-id="83229-123">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="83229-124">Они взаимозаменяемые.</span><span class="sxs-lookup"><span data-stu-id="83229-124">They are interchangeable.</span></span> <span data-ttu-id="83229-125">Например, следующие объявления объявляют переменные одного типа:</span><span class="sxs-lookup"><span data-stu-id="83229-125">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="83229-126">По умолчанию все типы с плавающей запятой имеют значение `0`.</span><span class="sxs-lookup"><span data-stu-id="83229-126">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="83229-127">Все типы с плавающей запятой имеют константы `MinValue` и `MaxValue` с минимальным и максимальными итоговыми значениями этого типа.</span><span class="sxs-lookup"><span data-stu-id="83229-127">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="83229-128">Типы `float` и `double` также предоставляют константы, обозначающие бесконечные и нечисловые значения.</span><span class="sxs-lookup"><span data-stu-id="83229-128">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="83229-129">Например, тип `double` предоставляет следующие константы: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> и <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="83229-129">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="83229-130">Так как тип `decimal` характеризуется более высокой точностью и меньшим диапазоном, чем `float` и `double`, он подходит для финансовых расчетов.</span><span class="sxs-lookup"><span data-stu-id="83229-130">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="83229-131">В одном и том же выражении можно сочетать и [целочисленные типы](integral-numeric-types.md), и типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="83229-131">You can mix [integral](integral-numeric-types.md) types and floating-point types in an expression.</span></span> <span data-ttu-id="83229-132">В этом случае целочисленные типы преобразуются в типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="83229-132">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="83229-133">Выражение вычисляется по следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="83229-133">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="83229-134">Если одним из типов с плавающей запятой является `double`, выражение оценивается как `double` или [bool](bool.md) в реляционных сравнениях или сравнениях на равенство.</span><span class="sxs-lookup"><span data-stu-id="83229-134">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](bool.md) in relational and equality comparisons.</span></span>
- <span data-ttu-id="83229-135">Если в выражении нет типа `double`, оно оценивается как `float` или [bool](bool.md) в реляционных сравнениях или сравнениях на равенство.</span><span class="sxs-lookup"><span data-stu-id="83229-135">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](bool.md) in relational and equality comparisons.</span></span>

<span data-ttu-id="83229-136">Выражение с плавающей запятой может содержать следующие наборы значений:</span><span class="sxs-lookup"><span data-stu-id="83229-136">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="83229-137">Положительный и отрицательный ноль</span><span class="sxs-lookup"><span data-stu-id="83229-137">Positive and negative zero</span></span>
- <span data-ttu-id="83229-138">Положительная и отрицательная бесконечность</span><span class="sxs-lookup"><span data-stu-id="83229-138">Positive and negative infinity</span></span>
- <span data-ttu-id="83229-139">Нечисловое значение (NaN)</span><span class="sxs-lookup"><span data-stu-id="83229-139">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="83229-140">Конечный набор ненулевых значений</span><span class="sxs-lookup"><span data-stu-id="83229-140">The finite set of nonzero values</span></span>

<span data-ttu-id="83229-141">Дополнительные сведения об этих значениях см. в документе "Стандарт IEEE для двоичной арифметики с плавающей запятой" на веб-сайте [IEEE](https://www.ieee.org).</span><span class="sxs-lookup"><span data-stu-id="83229-141">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="83229-142">Можно использовать [строки стандартных числовых форматов](../../../standard/base-types/standard-numeric-format-strings.md) или [строки пользовательских числовых форматов](../../../standard/base-types/custom-numeric-format-strings.md) для форматирования значения с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="83229-142">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="real-literals"></a><span data-ttu-id="83229-143">Вещественные литералы</span><span class="sxs-lookup"><span data-stu-id="83229-143">Real literals</span></span>

<span data-ttu-id="83229-144">Тип реального литерала определяется его суффиксом следующим образом:</span><span class="sxs-lookup"><span data-stu-id="83229-144">The type of a real literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="83229-145">Литерал без суффикса или с суффиксом `d` или `D` имеет тип `double`.</span><span class="sxs-lookup"><span data-stu-id="83229-145">The literal without suffix or with the `d` or `D` suffix is of type `double`</span></span>
- <span data-ttu-id="83229-146">Литерал с суффиксом `f` или `F` имеет тип `float`.</span><span class="sxs-lookup"><span data-stu-id="83229-146">The literal with the `f` or `F` suffix is of type `float`</span></span>
- <span data-ttu-id="83229-147">Литерал с суффиксом `m` или `M` имеет тип `decimal`.</span><span class="sxs-lookup"><span data-stu-id="83229-147">The literal with the `m` or `M` suffix is of type `decimal`</span></span>

<span data-ttu-id="83229-148">В приведенном ниже коде показан пример каждого из них.</span><span class="sxs-lookup"><span data-stu-id="83229-148">The following code demonstrates an example of each:</span></span>

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

<span data-ttu-id="83229-149">В предыдущем примере также показано использование `_` в качестве *цифрового разделителя*, который поддерживается, начиная с версии C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="83229-149">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="83229-150">Цифровой разделитель можно использовать со всеми видами числовых литералов.</span><span class="sxs-lookup"><span data-stu-id="83229-150">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="83229-151">Можно также использовать экспоненциальное представление, то есть указать экспоненту вещественного литерала, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="83229-151">You also can use scientific notation, that is, specify an exponent part of a real literal, as the following example shows:</span></span>

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a><span data-ttu-id="83229-152">Преобразования</span><span class="sxs-lookup"><span data-stu-id="83229-152">Conversions</span></span>

<span data-ttu-id="83229-153">Существует только одно неявное преобразование между числовыми типами с плавающей запятой: из `float` в `double`.</span><span class="sxs-lookup"><span data-stu-id="83229-153">There is only one implicit conversion between floating-point numeric types: from `float` to `double`.</span></span> <span data-ttu-id="83229-154">Однако можно преобразовать любой тип с плавающей запятой в любой другой тип с плавающей запятой с помощью[явного приведения](../operators/type-testing-and-cast.md#cast-operator-).</span><span class="sxs-lookup"><span data-stu-id="83229-154">However, you can convert any floating-point type to any other floating-point type with the [explicit cast](../operators/type-testing-and-cast.md#cast-operator-).</span></span> <span data-ttu-id="83229-155">Для получения дополнительной информации см. статью [Встроенные числовые преобразования](numeric-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="83229-155">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="83229-156">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="83229-156">C# language specification</span></span>

<span data-ttu-id="83229-157">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="83229-157">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="83229-158">Типы с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="83229-158">Floating-point types</span></span>](~/_csharplang/spec/types.md#floating-point-types)
- <span data-ttu-id="83229-159">Тип [decimal](~/_csharplang/spec/types.md#the-decimal-type)</span><span class="sxs-lookup"><span data-stu-id="83229-159">[The decimal type](~/_csharplang/spec/types.md#the-decimal-type)</span></span>
- [<span data-ttu-id="83229-160">Вещественные литералы</span><span class="sxs-lookup"><span data-stu-id="83229-160">Real literals</span></span>](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a><span data-ttu-id="83229-161">См. также</span><span class="sxs-lookup"><span data-stu-id="83229-161">See also</span></span>

- [<span data-ttu-id="83229-162">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="83229-162">C# reference</span></span>](../index.md)
- [<span data-ttu-id="83229-163">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="83229-163">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="83229-164">Целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="83229-164">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="83229-165">Таблица форматирования числовых результатов</span><span class="sxs-lookup"><span data-stu-id="83229-165">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="83229-166">Строки стандартных числовых форматов</span><span class="sxs-lookup"><span data-stu-id="83229-166">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="83229-167">Числовые значения в .NET</span><span class="sxs-lookup"><span data-stu-id="83229-167">Numerics in .NET</span></span>](../../../standard/numerics.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
