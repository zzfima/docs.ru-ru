---
title: Справочник по C#. Целочисленные типы
description: Сведения о диапазоне значений, размере занимаемой памяти и способах использования каждого из целочисленных типов.
ms.date: 10/22/2019
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
ms.openlocfilehash: 394a809a9a2f45f4aee652d0eca892f62f0f2e54
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093205"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="81a8a-103">Целочисленные типы (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="81a8a-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="81a8a-104">*Целочисленные типы* представляют целые числа.</span><span class="sxs-lookup"><span data-stu-id="81a8a-104">The *integral numeric types* represent integer numbers.</span></span> <span data-ttu-id="81a8a-105">Все целочисленные типы являются [типами значений](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="81a8a-105">All integral numeric types are [value types](value-types.md).</span></span> <span data-ttu-id="81a8a-106">Они также представляют собой [простые типы](value-types.md#built-in-value-types) и могут быть инициализированы [литералами](#integer-literals).</span><span class="sxs-lookup"><span data-stu-id="81a8a-106">They are also [simple types](value-types.md#built-in-value-types) and can be initialized with [literals](#integer-literals).</span></span> <span data-ttu-id="81a8a-107">Все целочисленные типы поддерживают [арифметические](../operators/arithmetic-operators.md) операторы, [побитовые логические](../operators/bitwise-and-shift-operators.md) операторы, операторы [сравнения](../operators/comparison-operators.md) и [равенства](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="81a8a-107">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="81a8a-108">Характеристики целочисленных типов</span><span class="sxs-lookup"><span data-stu-id="81a8a-108">Characteristics of the integral types</span></span>

<span data-ttu-id="81a8a-109">C# поддерживает следующие предварительно определенные целочисленные типы:</span><span class="sxs-lookup"><span data-stu-id="81a8a-109">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="81a8a-110">Ключевое слово или тип C#</span><span class="sxs-lookup"><span data-stu-id="81a8a-110">C# type/keyword</span></span>|<span data-ttu-id="81a8a-111">Диапазон</span><span class="sxs-lookup"><span data-stu-id="81a8a-111">Range</span></span>|<span data-ttu-id="81a8a-112">Размер</span><span class="sxs-lookup"><span data-stu-id="81a8a-112">Size</span></span>|<span data-ttu-id="81a8a-113">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="81a8a-113">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="81a8a-114">От -128 до 127</span><span class="sxs-lookup"><span data-stu-id="81a8a-114">-128 to 127</span></span>|<span data-ttu-id="81a8a-115">8-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="81a8a-115">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="81a8a-116">От 0 до 255</span><span class="sxs-lookup"><span data-stu-id="81a8a-116">0 to 255</span></span>|<span data-ttu-id="81a8a-117">8-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="81a8a-117">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="81a8a-118">От -32 768 до 32 767</span><span class="sxs-lookup"><span data-stu-id="81a8a-118">-32,768 to 32,767</span></span>|<span data-ttu-id="81a8a-119">16-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="81a8a-119">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="81a8a-120">От 0 до 65 535</span><span class="sxs-lookup"><span data-stu-id="81a8a-120">0 to 65,535</span></span>|<span data-ttu-id="81a8a-121">16-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="81a8a-121">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="81a8a-122">От -2 147 483 648 до 2 147 483 647</span><span class="sxs-lookup"><span data-stu-id="81a8a-122">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="81a8a-123">32-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="81a8a-123">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="81a8a-124">От 0 до 4 294 967 295</span><span class="sxs-lookup"><span data-stu-id="81a8a-124">0 to 4,294,967,295</span></span>|<span data-ttu-id="81a8a-125">32-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="81a8a-125">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="81a8a-126">От -9 223 372 036 854 775 808 до 9 223 372 036 854 775 807</span><span class="sxs-lookup"><span data-stu-id="81a8a-126">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="81a8a-127">64-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="81a8a-127">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="81a8a-128">От 0 до 18 446 744 073 709 551 615</span><span class="sxs-lookup"><span data-stu-id="81a8a-128">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="81a8a-129">64-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="81a8a-129">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="81a8a-130">В приведенной выше таблице каждый тип ключевого слова C# из крайнего левого столбца является псевдонимом для соответствующего типа .NET.</span><span class="sxs-lookup"><span data-stu-id="81a8a-130">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="81a8a-131">Они взаимозаменяемые.</span><span class="sxs-lookup"><span data-stu-id="81a8a-131">They are interchangeable.</span></span> <span data-ttu-id="81a8a-132">Например, следующие объявления объявляют переменные одного типа:</span><span class="sxs-lookup"><span data-stu-id="81a8a-132">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="81a8a-133">По умолчанию все целочисленные типы имеют значение `0`.</span><span class="sxs-lookup"><span data-stu-id="81a8a-133">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="81a8a-134">Все целочисленные типы имеют константы `MinValue` и `MaxValue` с минимальным и максимальными итоговыми значениями этого типа.</span><span class="sxs-lookup"><span data-stu-id="81a8a-134">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="81a8a-135">Используйте структуру <xref:System.Numerics.BigInteger?displayProperty=nameWithType>, чтобы представить целое число со знаком без верхней и нижней границ.</span><span class="sxs-lookup"><span data-stu-id="81a8a-135">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="81a8a-136">Целочисленные литералы</span><span class="sxs-lookup"><span data-stu-id="81a8a-136">Integer literals</span></span>

<span data-ttu-id="81a8a-137">Целочисленные литералы могут быть:</span><span class="sxs-lookup"><span data-stu-id="81a8a-137">Integer literals can be</span></span>

- <span data-ttu-id="81a8a-138">*десятичным числом*: без префикса;</span><span class="sxs-lookup"><span data-stu-id="81a8a-138">*decimal*: without any prefix</span></span>
- <span data-ttu-id="81a8a-139">*шестнадцатеричным числом*: с префиксом `0x` или `0X`;</span><span class="sxs-lookup"><span data-stu-id="81a8a-139">*hexadecimal*: with the `0x` or `0X` prefix</span></span>
- <span data-ttu-id="81a8a-140">*двоичными*: с префиксом `0b` или `0B` (доступно в C# 7.0 и более поздних версиях).</span><span class="sxs-lookup"><span data-stu-id="81a8a-140">*binary*: with the `0b` or `0B` prefix (available in C# 7.0 and later)</span></span>

<span data-ttu-id="81a8a-141">В приведенном ниже коде показан пример каждого из них.</span><span class="sxs-lookup"><span data-stu-id="81a8a-141">The following code demonstrates an example of each:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="81a8a-142">В предыдущем примере также показано использование `_` в качестве *цифрового разделителя*, который поддерживается, начиная с версии C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="81a8a-142">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="81a8a-143">Цифровой разделитель можно использовать со всеми видами числовых литералов.</span><span class="sxs-lookup"><span data-stu-id="81a8a-143">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="81a8a-144">Тип целочисленного литерала определяется его суффиксом следующим образом:</span><span class="sxs-lookup"><span data-stu-id="81a8a-144">The type of an integer literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="81a8a-145">Если литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение: `int`, `uint`, `long`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="81a8a-145">If the literal has no suffix, its type is the first of the following types in which its value can be represented: `int`, `uint`, `long`, `ulong`.</span></span>
- <span data-ttu-id="81a8a-146">Если у литерала есть суффикс `U` или `u`, его типом будет первый из следующих типов, в котором может быть представлено его значение: `uint`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="81a8a-146">If the literal is suffixed by `U` or `u`, its type is the first of the following types in which its value can be represented: `uint`, `ulong`.</span></span>
- <span data-ttu-id="81a8a-147">Если у литерала есть суффикс `L` или `l`, его типом будет первый из следующих типов, в котором может быть представлено его значение: `long`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="81a8a-147">If the literal is suffixed by `L` or `l`, its type is the first of the following types in which its value can be represented: `long`, `ulong`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="81a8a-148">Строчную букву `l` можно использовать в качестве суффикса.</span><span class="sxs-lookup"><span data-stu-id="81a8a-148">You can use the lowercase letter `l` as a suffix.</span></span> <span data-ttu-id="81a8a-149">Однако при этом выдается предупреждение компилятора, так как букву `l` можно перепутать с цифрой `1`.</span><span class="sxs-lookup"><span data-stu-id="81a8a-149">However, this generates a compiler warning because the letter `l` can be confused with the digit `1`.</span></span> <span data-ttu-id="81a8a-150">Для ясности используйте `L`.</span><span class="sxs-lookup"><span data-stu-id="81a8a-150">Use `L` for clarity.</span></span>

- <span data-ttu-id="81a8a-151">Если у литерала есть суффикс `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU` или `lu`, его тип — `ulong`.</span><span class="sxs-lookup"><span data-stu-id="81a8a-151">If the literal is suffixed by `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`, or `lu`, its type is `ulong`.</span></span>

<span data-ttu-id="81a8a-152">Если значение, представленное целочисленным литералом, превышает <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, происходит ошибка компиляции [CS1021](../../misc/cs1021.md).</span><span class="sxs-lookup"><span data-stu-id="81a8a-152">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="81a8a-153">Если определенный тип целочисленного литерала — `int`, а значение, представленное литералом, находится в диапазоне целевого типа, значение можно неявно преобразовать в `sbyte`, `byte`, `short`, `ushort`, `uint` или `ulong`:</span><span class="sxs-lookup"><span data-stu-id="81a8a-153">If the determined type of an integer literal is `int` and the value represented by the literal is within the range of the destination type, the value can be implicitly converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`:</span></span>

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

<span data-ttu-id="81a8a-154">Как показано в предыдущем примере, если значение литерала выходит за пределы диапазона целевого типа, возникает ошибка компилятора [CS0031](../../misc/cs0031.md).</span><span class="sxs-lookup"><span data-stu-id="81a8a-154">As the preceding example shows, if the literal's value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

<span data-ttu-id="81a8a-155">Можно также использовать приведение для преобразования значения, представленного целочисленным литералом, в тип, отличный от определенного типа литерала.</span><span class="sxs-lookup"><span data-stu-id="81a8a-155">You also can use a cast to convert the value represented by an integer literal to the type other than the determined type of the literal:</span></span>

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="81a8a-156">Преобразования</span><span class="sxs-lookup"><span data-stu-id="81a8a-156">Conversions</span></span>

<span data-ttu-id="81a8a-157">Любой целочисленный тип можно преобразовать в любой другой целочисленный тип.</span><span class="sxs-lookup"><span data-stu-id="81a8a-157">You can convert any integral numeric type to any other integral numeric type.</span></span> <span data-ttu-id="81a8a-158">Если целевой тип может хранить все значения исходного типа, преобразование является неявным.</span><span class="sxs-lookup"><span data-stu-id="81a8a-158">If the destination type can store all values of the source type, the conversion is implicit.</span></span> <span data-ttu-id="81a8a-159">В противном случае используйте [оператор приведения `()`](../operators/type-testing-and-cast.md#cast-operator-) для вызова явного преобразования.</span><span class="sxs-lookup"><span data-stu-id="81a8a-159">Otherwise, you need to use the [cast operator `()`](../operators/type-testing-and-cast.md#cast-operator-) to invoke an explicit conversion.</span></span> <span data-ttu-id="81a8a-160">Для получения дополнительной информации см. статью [Встроенные числовые преобразования](numeric-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="81a8a-160">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="81a8a-161">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="81a8a-161">C# language specification</span></span>

<span data-ttu-id="81a8a-162">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="81a8a-162">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="81a8a-163">Целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="81a8a-163">Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="81a8a-164">Целочисленные литералы</span><span class="sxs-lookup"><span data-stu-id="81a8a-164">Integer literals</span></span>](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a><span data-ttu-id="81a8a-165">См. также</span><span class="sxs-lookup"><span data-stu-id="81a8a-165">See also</span></span>

- [<span data-ttu-id="81a8a-166">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="81a8a-166">C# reference</span></span>](../index.md)
- [<span data-ttu-id="81a8a-167">Типы значений</span><span class="sxs-lookup"><span data-stu-id="81a8a-167">Value types</span></span>](value-types.md)
- [<span data-ttu-id="81a8a-168">Типы с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="81a8a-168">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="81a8a-169">Строки стандартных числовых форматов</span><span class="sxs-lookup"><span data-stu-id="81a8a-169">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="81a8a-170">Числовые значения в .NET</span><span class="sxs-lookup"><span data-stu-id="81a8a-170">Numerics in .NET</span></span>](../../../standard/numerics.md)
