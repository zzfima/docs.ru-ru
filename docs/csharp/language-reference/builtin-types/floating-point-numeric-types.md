---
title: Числовые типы с плавающей запятой — справочник по C#
description: 'Дополнительные сведения о встроенных типах C# с плавающей запятой: float, double и decimal'
ms.date: 02/10/2020
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
ms.openlocfilehash: 95b7f266654bbbcdcd0f81e3aa11cfc94af9f0e5
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215243"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="ebe6d-103">Числовые типы с плавающей запятой (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ebe6d-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="ebe6d-104">*Числовые типы с плавающей запятой* представляют действительные числа.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-104">The *floating-point numeric types* represent real numbers.</span></span> <span data-ttu-id="ebe6d-105">Все числовые типы с плавающей запятой являются [типами значений](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="ebe6d-105">All floating-point numeric types are [value types](value-types.md).</span></span> <span data-ttu-id="ebe6d-106">Они также представляют собой [простые типы](value-types.md#built-in-value-types) и могут быть инициализированы [литералами](#real-literals).</span><span class="sxs-lookup"><span data-stu-id="ebe6d-106">They are also [simple types](value-types.md#built-in-value-types) and can be initialized with [literals](#real-literals).</span></span> <span data-ttu-id="ebe6d-107">Все числовые типы с плавающей запятой поддерживают [арифметические](../operators/arithmetic-operators.md) операторы, а также операторы [сравнения](../operators/comparison-operators.md) и [равенства](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="ebe6d-107">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="ebe6d-108">Характеристики типов с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="ebe6d-108">Characteristics of the floating-point types</span></span>

<span data-ttu-id="ebe6d-109">C# поддерживает следующие предварительно определенные типы с плавающей запятой:</span><span class="sxs-lookup"><span data-stu-id="ebe6d-109">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="ebe6d-110">Ключевое слово или тип C#</span><span class="sxs-lookup"><span data-stu-id="ebe6d-110">C# type/keyword</span></span>|<span data-ttu-id="ebe6d-111">Приблизительный диапазон значений</span><span class="sxs-lookup"><span data-stu-id="ebe6d-111">Approximate range</span></span>|<span data-ttu-id="ebe6d-112">Точность</span><span class="sxs-lookup"><span data-stu-id="ebe6d-112">Precision</span></span>|<span data-ttu-id="ebe6d-113">Размер</span><span class="sxs-lookup"><span data-stu-id="ebe6d-113">Size</span></span>|<span data-ttu-id="ebe6d-114">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="ebe6d-114">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="ebe6d-115">От ±1,5 x 10<sup>−45</sup> до ±3,4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="ebe6d-115">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="ebe6d-116">6–9 цифр</span><span class="sxs-lookup"><span data-stu-id="ebe6d-116">~6-9 digits</span></span>|<span data-ttu-id="ebe6d-117">4 байта</span><span class="sxs-lookup"><span data-stu-id="ebe6d-117">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="ebe6d-118">от ±5,0 × 10<sup>−324</sup> до ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="ebe6d-118">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="ebe6d-119">15–17 цифр</span><span class="sxs-lookup"><span data-stu-id="ebe6d-119">~15-17 digits</span></span>|<span data-ttu-id="ebe6d-120">8 байт</span><span class="sxs-lookup"><span data-stu-id="ebe6d-120">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="ebe6d-121">от ±1,0 x 10<sup>-28</sup> до ±7,9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="ebe6d-121">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="ebe6d-122">28-29 знаков</span><span class="sxs-lookup"><span data-stu-id="ebe6d-122">28-29 digits</span></span>|<span data-ttu-id="ebe6d-123">16 байт</span><span class="sxs-lookup"><span data-stu-id="ebe6d-123">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="ebe6d-124">В приведенной выше таблице каждый тип ключевого слова C# из крайнего левого столбца является псевдонимом для соответствующего типа .NET.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-124">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="ebe6d-125">Они взаимозаменяемые.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-125">They are interchangeable.</span></span> <span data-ttu-id="ebe6d-126">Например, следующие объявления объявляют переменные одного типа:</span><span class="sxs-lookup"><span data-stu-id="ebe6d-126">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="ebe6d-127">По умолчанию все типы с плавающей запятой имеют значение `0`.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-127">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="ebe6d-128">Все типы с плавающей запятой имеют константы `MinValue` и `MaxValue` с минимальным и максимальными итоговыми значениями этого типа.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-128">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="ebe6d-129">Типы `float` и `double` также предоставляют константы, обозначающие бесконечные и нечисловые значения.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-129">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="ebe6d-130">Например, тип `double` предоставляет следующие константы: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> и <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-130">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="ebe6d-131">Так как тип `decimal` характеризуется более высокой точностью и меньшим диапазоном, чем `float` и `double`, он подходит для финансовых расчетов.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-131">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="ebe6d-132">В одном и том же выражении можно сочетать и [целочисленные](integral-numeric-types.md) типы, и типы `float` и `double`.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-132">You can mix [integral](integral-numeric-types.md) types and the `float` and `double` types in an expression.</span></span> <span data-ttu-id="ebe6d-133">В этом случае целочисленные типы неявно преобразуются в один из типов с плавающей запятой. При необходимости тип `float` неявно преобразуется в `double`.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-133">In this case, integral types are implicitly converted to one of the floating-point types and, if necessary, the `float` type is implicitly converted to `double`.</span></span> <span data-ttu-id="ebe6d-134">Выражение вычисляется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-134">The expression is evaluated as follows:</span></span>

- <span data-ttu-id="ebe6d-135">Если в выражении есть тип `double`, оно оценивается как `double` или [`bool`](bool.md) в реляционных сравнениях или сравнениях на равенство.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-135">If there is `double` type in the expression, the expression evaluates to `double`, or to [`bool`](bool.md) in relational and equality comparisons.</span></span>
- <span data-ttu-id="ebe6d-136">Если в выражении нет типа `double`, оно оценивается как `float` или `bool` в реляционных сравнениях или сравнениях на равенство.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-136">If there is no `double` type in the expression, the expression evaluates to `float`, or to `bool` in relational and equality comparisons.</span></span>

<span data-ttu-id="ebe6d-137">Можно также смешивать целочисленные типы и тип `decimal` в выражении.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-137">You can also mix integral types and the `decimal` type in an expression.</span></span> <span data-ttu-id="ebe6d-138">В этом случае целочисленные типы неявно преобразуются в тип `decimal`, а выражение вычисляется как `decimal` или `bool` в реляционных сравнениях и сравнениях на равенство.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-138">In this case, integral types are implicitly converted to the `decimal` type and the expression evaluates to `decimal`, or to `bool` in relational and equality comparisons.</span></span>

<span data-ttu-id="ebe6d-139">Тип `decimal` нельзя смешивать с типами `float` и `double` в выражении.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-139">You cannot mix the `decimal` type with the `float` and `double` types in an expression.</span></span> <span data-ttu-id="ebe6d-140">В этом случае, если требуется выполнить арифметические операции или операции сравнения или равенства, необходимо явно преобразовать операнды из типа или в тип `decimal`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ebe6d-140">In this case, if you want to perform arithmetic, comparison, or equality operations, you must explicitly convert the operands either from or to the `decimal` type, as the following example shows:</span></span>

```csharp-interactive
double a = 1.0;
decimal b = 2.1m;
Console.WriteLine(a + (double)b);
Console.WriteLine((decimal)a + b);
```

<span data-ttu-id="ebe6d-141">Можно использовать [строки стандартных числовых форматов](../../../standard/base-types/standard-numeric-format-strings.md) или [строки пользовательских числовых форматов](../../../standard/base-types/custom-numeric-format-strings.md) для форматирования значения с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-141">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="real-literals"></a><span data-ttu-id="ebe6d-142">Вещественные литералы</span><span class="sxs-lookup"><span data-stu-id="ebe6d-142">Real literals</span></span>

<span data-ttu-id="ebe6d-143">Тип реального литерала определяется его суффиксом следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ebe6d-143">The type of a real literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="ebe6d-144">Литерал без суффикса или с суффиксом `d` или `D` имеет тип `double`.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-144">The literal without suffix or with the `d` or `D` suffix is of type `double`</span></span>
- <span data-ttu-id="ebe6d-145">Литерал с суффиксом `f` или `F` имеет тип `float`.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-145">The literal with the `f` or `F` suffix is of type `float`</span></span>
- <span data-ttu-id="ebe6d-146">Литерал с суффиксом `m` или `M` имеет тип `decimal`.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-146">The literal with the `m` or `M` suffix is of type `decimal`</span></span>

<span data-ttu-id="ebe6d-147">В приведенном ниже коде показан пример каждого из них.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-147">The following code demonstrates an example of each:</span></span>

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

<span data-ttu-id="ebe6d-148">В предыдущем примере также показано использование `_` в качестве *цифрового разделителя*, который поддерживается, начиная с версии C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-148">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="ebe6d-149">Цифровой разделитель можно использовать со всеми видами числовых литералов.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-149">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="ebe6d-150">Можно также использовать экспоненциальное представление, то есть указать экспоненту вещественного литерала, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ebe6d-150">You also can use scientific notation, that is, specify an exponent part of a real literal, as the following example shows:</span></span>

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a><span data-ttu-id="ebe6d-151">Преобразования</span><span class="sxs-lookup"><span data-stu-id="ebe6d-151">Conversions</span></span>

<span data-ttu-id="ebe6d-152">Существует только одно неявное преобразование между числовыми типами с плавающей запятой: из `float` в `double`.</span><span class="sxs-lookup"><span data-stu-id="ebe6d-152">There is only one implicit conversion between floating-point numeric types: from `float` to `double`.</span></span> <span data-ttu-id="ebe6d-153">Однако можно преобразовать любой тип с плавающей запятой в любой другой тип с плавающей запятой с помощью[явного приведения](../operators/type-testing-and-cast.md#cast-operator-).</span><span class="sxs-lookup"><span data-stu-id="ebe6d-153">However, you can convert any floating-point type to any other floating-point type with the [explicit cast](../operators/type-testing-and-cast.md#cast-operator-).</span></span> <span data-ttu-id="ebe6d-154">Для получения дополнительной информации см. статью [Встроенные числовые преобразования](numeric-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="ebe6d-154">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ebe6d-155">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ebe6d-155">C# language specification</span></span>

<span data-ttu-id="ebe6d-156">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="ebe6d-156">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="ebe6d-157">Типы с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="ebe6d-157">Floating-point types</span></span>](~/_csharplang/spec/types.md#floating-point-types)
- <span data-ttu-id="ebe6d-158">Тип [decimal](~/_csharplang/spec/types.md#the-decimal-type)</span><span class="sxs-lookup"><span data-stu-id="ebe6d-158">[The decimal type](~/_csharplang/spec/types.md#the-decimal-type)</span></span>
- [<span data-ttu-id="ebe6d-159">Вещественные литералы</span><span class="sxs-lookup"><span data-stu-id="ebe6d-159">Real literals</span></span>](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a><span data-ttu-id="ebe6d-160">См. также</span><span class="sxs-lookup"><span data-stu-id="ebe6d-160">See also</span></span>

- [<span data-ttu-id="ebe6d-161">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ebe6d-161">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ebe6d-162">Типы значений</span><span class="sxs-lookup"><span data-stu-id="ebe6d-162">Value types</span></span>](value-types.md)
- [<span data-ttu-id="ebe6d-163">Целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="ebe6d-163">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="ebe6d-164">Строки стандартных числовых форматов</span><span class="sxs-lookup"><span data-stu-id="ebe6d-164">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="ebe6d-165">Числовые значения в .NET</span><span class="sxs-lookup"><span data-stu-id="ebe6d-165">Numerics in .NET</span></span>](../../../standard/numerics.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
