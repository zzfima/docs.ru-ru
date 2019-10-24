---
title: Справочник по C#. Целочисленные типы
description: Сведения о диапазоне значений, размере занимаемой памяти и способах использования каждого из целочисленных типов.
ms.date: 10/18/2019
f1_keywords:
- byte
- byte_CSharpKeyword
- sbyte_CSharpKeyword
- sbyte
- short
- short_CSharpKeyword
- ushort
- ushort_CSharpKeyword
- int_CSharpKeyword
- int
- uint
- uint_CSharpKeyword
- long_CSharpKeyword
- long
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
- byte keyword [C#]
- sbyte keyword [C#]
- short keyword [C#]
- ushort keyword [C#]
- int keyword [C#]
- uint keyword [C#]
- long keyword [C#]
- ulong keyword [C#]
ms.openlocfilehash: 3d4f3164d67a000123417619f3be6be455d5ab87
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72579196"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="e8f64-103">Целочисленные типы (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e8f64-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="e8f64-104">**Целочисленные типы** — это подмножество **простых типов**. Они могут инициализироваться [*литералами*](#integer-literals).</span><span class="sxs-lookup"><span data-stu-id="e8f64-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integer-literals).</span></span> <span data-ttu-id="e8f64-105">Кроме того, все целочисленные типы являются типами значений.</span><span class="sxs-lookup"><span data-stu-id="e8f64-105">All integral types are also value types.</span></span> <span data-ttu-id="e8f64-106">Все целочисленные типы поддерживают [арифметические](../operators/arithmetic-operators.md) операторы, [побитовые логические](../operators/bitwise-and-shift-operators.md) операторы, операторы [сравнения](../operators/comparison-operators.md) и [равенства](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="e8f64-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="e8f64-107">Характеристики целочисленных типов</span><span class="sxs-lookup"><span data-stu-id="e8f64-107">Characteristics of the integral types</span></span>

<span data-ttu-id="e8f64-108">C# поддерживает следующие предварительно определенные целочисленные типы:</span><span class="sxs-lookup"><span data-stu-id="e8f64-108">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="e8f64-109">Ключевое слово или тип C#</span><span class="sxs-lookup"><span data-stu-id="e8f64-109">C# type/keyword</span></span>|<span data-ttu-id="e8f64-110">Диапазон</span><span class="sxs-lookup"><span data-stu-id="e8f64-110">Range</span></span>|<span data-ttu-id="e8f64-111">Размер</span><span class="sxs-lookup"><span data-stu-id="e8f64-111">Size</span></span>|<span data-ttu-id="e8f64-112">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="e8f64-112">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="e8f64-113">От -128 до 127</span><span class="sxs-lookup"><span data-stu-id="e8f64-113">-128 to 127</span></span>|<span data-ttu-id="e8f64-114">8-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="e8f64-114">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="e8f64-115">От 0 до 255</span><span class="sxs-lookup"><span data-stu-id="e8f64-115">0 to 255</span></span>|<span data-ttu-id="e8f64-116">8-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="e8f64-116">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="e8f64-117">От -32 768 до 32 767</span><span class="sxs-lookup"><span data-stu-id="e8f64-117">-32,768 to 32,767</span></span>|<span data-ttu-id="e8f64-118">16-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="e8f64-118">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="e8f64-119">От 0 до 65 535</span><span class="sxs-lookup"><span data-stu-id="e8f64-119">0 to 65,535</span></span>|<span data-ttu-id="e8f64-120">16-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="e8f64-120">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="e8f64-121">От -2 147 483 648 до 2 147 483 647</span><span class="sxs-lookup"><span data-stu-id="e8f64-121">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="e8f64-122">32-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="e8f64-122">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="e8f64-123">От 0 до 4 294 967 295</span><span class="sxs-lookup"><span data-stu-id="e8f64-123">0 to 4,294,967,295</span></span>|<span data-ttu-id="e8f64-124">32-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="e8f64-124">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="e8f64-125">От -9 223 372 036 854 775 808 до 9 223 372 036 854 775 807</span><span class="sxs-lookup"><span data-stu-id="e8f64-125">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="e8f64-126">64-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="e8f64-126">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="e8f64-127">От 0 до 18 446 744 073 709 551 615</span><span class="sxs-lookup"><span data-stu-id="e8f64-127">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="e8f64-128">64-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="e8f64-128">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="e8f64-129">В приведенной выше таблице каждый тип ключевого слова C# из крайнего левого столбца является псевдонимом для соответствующего типа .NET.</span><span class="sxs-lookup"><span data-stu-id="e8f64-129">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="e8f64-130">Они взаимозаменяемые.</span><span class="sxs-lookup"><span data-stu-id="e8f64-130">They are interchangeable.</span></span> <span data-ttu-id="e8f64-131">Например, следующие объявления объявляют переменные одного типа:</span><span class="sxs-lookup"><span data-stu-id="e8f64-131">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="e8f64-132">По умолчанию все целочисленные типы имеют значение `0`.</span><span class="sxs-lookup"><span data-stu-id="e8f64-132">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="e8f64-133">Все целочисленные типы имеют константы `MinValue` и `MaxValue` с минимальным и максимальными итоговыми значениями этого типа.</span><span class="sxs-lookup"><span data-stu-id="e8f64-133">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="e8f64-134">Используйте структуру <xref:System.Numerics.BigInteger?displayProperty=nameWithType>, чтобы представить целое число со знаком без верхней и нижней границ.</span><span class="sxs-lookup"><span data-stu-id="e8f64-134">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="e8f64-135">Целочисленные литералы</span><span class="sxs-lookup"><span data-stu-id="e8f64-135">Integer literals</span></span>

<span data-ttu-id="e8f64-136">Целочисленные литералы могут быть:</span><span class="sxs-lookup"><span data-stu-id="e8f64-136">Integer literals can be</span></span>

- <span data-ttu-id="e8f64-137">*десятичным числом*: без префикса;</span><span class="sxs-lookup"><span data-stu-id="e8f64-137">*decimal*: without any prefix</span></span>
- <span data-ttu-id="e8f64-138">*шестнадцатеричным числом*: с префиксом `0x` или `0X`;</span><span class="sxs-lookup"><span data-stu-id="e8f64-138">*hexadecimal*: with the `0x` or `0X` prefix</span></span>
- <span data-ttu-id="e8f64-139">*двоичными*: с префиксом `0b` или `0B` (доступно в C# 7.0 и более поздних версиях).</span><span class="sxs-lookup"><span data-stu-id="e8f64-139">*binary*: with the `0b` or `0B` prefix (available in C# 7.0 and later)</span></span>

<span data-ttu-id="e8f64-140">В приведенном ниже коде показан пример каждого из них.</span><span class="sxs-lookup"><span data-stu-id="e8f64-140">The following code demonstrates an example of each:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="e8f64-141">В предыдущем примере также показано использование `_` в качестве *цифрового разделителя*, который поддерживается, начиная с версии C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="e8f64-141">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="e8f64-142">Цифровой разделитель можно использовать со всеми видами числовых литералов.</span><span class="sxs-lookup"><span data-stu-id="e8f64-142">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="e8f64-143">Тип целочисленного литерала определяется его суффиксом следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e8f64-143">The type of an integer literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="e8f64-144">Если литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение: `int`, `uint`, `long`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="e8f64-144">If the literal has no suffix, its type is the first of the following types in which its value can be represented: `int`, `uint`, `long`, `ulong`.</span></span>
- <span data-ttu-id="e8f64-145">Если у литерала есть суффикс `U` или `u`, его типом будет первый из следующих типов, в котором может быть представлено его значение: `uint`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="e8f64-145">If the literal is suffixed by `U` or `u`, its type is the first of the following types in which its value can be represented: `uint`, `ulong`.</span></span>
- <span data-ttu-id="e8f64-146">Если у литерала есть суффикс `L` или `l`, его типом будет первый из следующих типов, в котором может быть представлено его значение: `long`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="e8f64-146">If the literal is suffixed by `L` or `l`, its type is the first of the following types in which its value can be represented: `long`, `ulong`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e8f64-147">Строчную букву `l` можно использовать в качестве суффикса.</span><span class="sxs-lookup"><span data-stu-id="e8f64-147">You can use the lowercase letter `l` as a suffix.</span></span> <span data-ttu-id="e8f64-148">Однако при этом выдается предупреждение компилятора, так как букву `l` можно перепутать с цифрой `1`.</span><span class="sxs-lookup"><span data-stu-id="e8f64-148">However, this generates a compiler warning because the letter `l` can be confused with the digit `1`.</span></span> <span data-ttu-id="e8f64-149">Для ясности используйте `L`.</span><span class="sxs-lookup"><span data-stu-id="e8f64-149">Use `L` for clarity.</span></span>

- <span data-ttu-id="e8f64-150">Если у литерала есть суффикс `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU` или `lu`, его тип — `ulong`.</span><span class="sxs-lookup"><span data-stu-id="e8f64-150">If the literal is suffixed by `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`, or `lu`, its type is `ulong`.</span></span>

<span data-ttu-id="e8f64-151">Если значение, представленное целочисленным литералом, превышает <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, происходит ошибка компиляции [CS1021](../../misc/cs1021.md).</span><span class="sxs-lookup"><span data-stu-id="e8f64-151">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="e8f64-152">Значение, представленное целочисленным литералом, можно неявно преобразовать в тип с меньшим диапазоном, чем определенный тип литерала.</span><span class="sxs-lookup"><span data-stu-id="e8f64-152">The value represented by an integer literal can be implicitly converted to a type with a smaller range than the determined type of the literal.</span></span> <span data-ttu-id="e8f64-153">Это возможно, если значение находится в диапазоне целевого типа.</span><span class="sxs-lookup"><span data-stu-id="e8f64-153">That's possible when the value is within the range of the destination type:</span></span>

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

<span data-ttu-id="e8f64-154">Как показано в предыдущем примере, если значение литерала выходит за пределы диапазона целевого типа, возникает ошибка компилятора [CS0031](../../misc/cs0031.md).</span><span class="sxs-lookup"><span data-stu-id="e8f64-154">As the preceding example shows, if the literal's value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

<span data-ttu-id="e8f64-155">Можно также использовать приведение для преобразования значения, представленного целочисленным литералом, в тип, отличный от определенного типа литерала.</span><span class="sxs-lookup"><span data-stu-id="e8f64-155">You also can use a cast to convert the value represented by an integer literal to the type other than the determined type of the literal:</span></span>

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="e8f64-156">Преобразования</span><span class="sxs-lookup"><span data-stu-id="e8f64-156">Conversions</span></span>

<span data-ttu-id="e8f64-157">Между любыми двумя целочисленными типами, один из которых поддерживает любые значения другого, существует неявное преобразование (которое называется *расширяющим*).</span><span class="sxs-lookup"><span data-stu-id="e8f64-157">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="e8f64-158">Например, существует неявное преобразование из `int` в `long`, так как диапазон значений типа `int` является строгим подмножеством значений `long`.</span><span class="sxs-lookup"><span data-stu-id="e8f64-158">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="e8f64-159">Целочисленный тип без знака меньшего размера может неявно преобразовываться в целочисленный тип со знаком большего размера.</span><span class="sxs-lookup"><span data-stu-id="e8f64-159">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="e8f64-160">Кроме того, существуют неявные преобразования любых целочисленных типов в любые типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="e8f64-160">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="e8f64-161">Неявных преобразований целочисленных типов со знаком в целочисленные типы без знака нет.</span><span class="sxs-lookup"><span data-stu-id="e8f64-161">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="e8f64-162">Если неявное преобразование между двумя целочисленными типами не определено, необходимо использовать явное приведение.</span><span class="sxs-lookup"><span data-stu-id="e8f64-162">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="e8f64-163">Это называется *сужающим преобразованием*.</span><span class="sxs-lookup"><span data-stu-id="e8f64-163">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="e8f64-164">Явное приведение требуется по той причине, что преобразование может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="e8f64-164">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e8f64-165">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e8f64-165">C# language specification</span></span>

<span data-ttu-id="e8f64-166">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="e8f64-166">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="e8f64-167">Целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="e8f64-167">Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="e8f64-168">Целочисленные литералы</span><span class="sxs-lookup"><span data-stu-id="e8f64-168">Integer literals</span></span>](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a><span data-ttu-id="e8f64-169">См. также</span><span class="sxs-lookup"><span data-stu-id="e8f64-169">See also</span></span>

- [<span data-ttu-id="e8f64-170">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e8f64-170">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e8f64-171">Типы с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="e8f64-171">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="e8f64-172">Таблица значений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e8f64-172">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="e8f64-173">Таблица форматирования числовых результатов</span><span class="sxs-lookup"><span data-stu-id="e8f64-173">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="e8f64-174">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="e8f64-174">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="e8f64-175">Числовые значения в .NET</span><span class="sxs-lookup"><span data-stu-id="e8f64-175">Numerics in .NET</span></span>](../../../standard/numerics.md)
