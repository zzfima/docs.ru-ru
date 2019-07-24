---
title: Справочник по C#. Целочисленные типы
description: Сведения о диапазоне значений, размере занимаемой памяти и способах использования каждого из целочисленных типов.
ms.date: 06/25/2019
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
ms.openlocfilehash: dfb1298abaff0cfe8eae7536f94511a30012a4a9
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68236075"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="8bfb4-103">Целочисленные типы (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8bfb4-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="8bfb4-104">**Целочисленные типы** — это подмножество **простых типов**. Они могут инициализироваться [*литералами*](#integral-literals).</span><span class="sxs-lookup"><span data-stu-id="8bfb4-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integral-literals).</span></span> <span data-ttu-id="8bfb4-105">Кроме того, все целочисленные типы являются типами значений.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-105">All integral types are also value types.</span></span> <span data-ttu-id="8bfb4-106">Все целочисленные типы поддерживают [арифметические](../operators/arithmetic-operators.md) операторы, [побитовые логические](../operators/bitwise-and-shift-operators.md) операторы, операторы [сравнения и равенства](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="8bfb4-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="8bfb4-107">Характеристики целочисленных типов</span><span class="sxs-lookup"><span data-stu-id="8bfb4-107">Characteristics of the integral types</span></span>

<span data-ttu-id="8bfb4-108">C# поддерживает следующие предварительно определенные целочисленные типы:</span><span class="sxs-lookup"><span data-stu-id="8bfb4-108">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="8bfb4-109">Ключевое слово или тип C#</span><span class="sxs-lookup"><span data-stu-id="8bfb4-109">C# type/keyword</span></span>|<span data-ttu-id="8bfb4-110">Диапазон</span><span class="sxs-lookup"><span data-stu-id="8bfb4-110">Range</span></span>|<span data-ttu-id="8bfb4-111">Размер</span><span class="sxs-lookup"><span data-stu-id="8bfb4-111">Size</span></span>|<span data-ttu-id="8bfb4-112">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="8bfb4-112">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="8bfb4-113">От -128 до 127</span><span class="sxs-lookup"><span data-stu-id="8bfb4-113">-128 to 127</span></span>|<span data-ttu-id="8bfb4-114">8-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="8bfb4-114">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="8bfb4-115">От 0 до 255</span><span class="sxs-lookup"><span data-stu-id="8bfb4-115">0 to 255</span></span>|<span data-ttu-id="8bfb4-116">8-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="8bfb4-116">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="8bfb4-117">От -32 768 до 32 767</span><span class="sxs-lookup"><span data-stu-id="8bfb4-117">-32,768 to 32,767</span></span>|<span data-ttu-id="8bfb4-118">16-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="8bfb4-118">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="8bfb4-119">От 0 до 65 535</span><span class="sxs-lookup"><span data-stu-id="8bfb4-119">0 to 65,535</span></span>|<span data-ttu-id="8bfb4-120">16-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="8bfb4-120">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="8bfb4-121">От -2 147 483 648 до 2 147 483 647</span><span class="sxs-lookup"><span data-stu-id="8bfb4-121">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="8bfb4-122">32-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="8bfb4-122">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="8bfb4-123">От 0 до 4 294 967 295</span><span class="sxs-lookup"><span data-stu-id="8bfb4-123">0 to 4,294,967,295</span></span>|<span data-ttu-id="8bfb4-124">32-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="8bfb4-124">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="8bfb4-125">От -9 223 372 036 854 775 808 до 9 223 372 036 854 775 807</span><span class="sxs-lookup"><span data-stu-id="8bfb4-125">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="8bfb4-126">64-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="8bfb4-126">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="8bfb4-127">От 0 до 18 446 744 073 709 551 615</span><span class="sxs-lookup"><span data-stu-id="8bfb4-127">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="8bfb4-128">64-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="8bfb4-128">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="8bfb4-129">В приведенной выше таблице каждый тип ключевого слова C# из крайнего левого столбца является псевдонимом для соответствующего типа .NET.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-129">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="8bfb4-130">Они взаимозаменяемые.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-130">They are interchangeable.</span></span> <span data-ttu-id="8bfb4-131">Например, следующие объявления объявляют переменные одного типа:</span><span class="sxs-lookup"><span data-stu-id="8bfb4-131">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="8bfb4-132">По умолчанию все целочисленные типы имеют значение `0`.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-132">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="8bfb4-133">Все целочисленные типы имеют константы `MinValue` и `MaxValue` с минимальным и максимальными итоговыми значениями этого типа.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-133">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="8bfb4-134">Используйте структуру <xref:System.Numerics.BigInteger?displayProperty=nameWithType>, чтобы представить целое число со знаком без верхней и нижней границ.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-134">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integral-literals"></a><span data-ttu-id="8bfb4-135">Целочисленные литералы</span><span class="sxs-lookup"><span data-stu-id="8bfb4-135">Integral literals</span></span>

<span data-ttu-id="8bfb4-136">Целочисленные литералы можно задать как *десятичные*, *шестнадцатеричные* или *двоичные литералы*.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-136">Integral literals can be specified as *decimal literals*, *hexadecimal literals*, or *binary literals*.</span></span> <span data-ttu-id="8bfb4-137">Ниже приведены примеры каждого из них:</span><span class="sxs-lookup"><span data-stu-id="8bfb4-137">An example of each is shown below:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="8bfb4-138">Десятичные литералы не требуют префикса.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-138">Decimal literals don't require any prefix.</span></span> <span data-ttu-id="8bfb4-139">Префикс `x` или `X` означает, что это *шестнадцатеричный литерал*.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-139">The `x` or `X` prefix signifies a *hexadecimal literal*.</span></span> <span data-ttu-id="8bfb4-140">Префикс `b` или `B` означает, что это *двоичный литерал*.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-140">The `b` or `B` prefix signifies a *binary literal*.</span></span> <span data-ttu-id="8bfb4-141">Объявление `binaryLiteral` демонстрирует использование символа `_` в качестве *разделителя разрядов*.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-141">The declaration of `binaryLiteral` demonstrates the use of `_` as a *digit separator*.</span></span> <span data-ttu-id="8bfb4-142">Разделитель разрядов можно использовать с любыми числовыми литералами.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-142">The digit separator can be used with all numeric literals.</span></span> <span data-ttu-id="8bfb4-143">Двоичные литералы и разделитель разрядов `_` поддерживаются начиная с C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-143">Binary literals and the digit separator `_` are supported starting with C# 7.0.</span></span>

### <a name="literal-suffixes"></a><span data-ttu-id="8bfb4-144">Суффиксы литералов</span><span class="sxs-lookup"><span data-stu-id="8bfb4-144">Literal suffixes</span></span>

<span data-ttu-id="8bfb4-145">Суффикс `l` или `L` указывает, что целочисленный литерал должен иметь тип `long`.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-145">The `l` or `L` suffix specifies that the integral literal should be of the `long` type.</span></span> <span data-ttu-id="8bfb4-146">Суффикс `ul` или `UL` указывает тип `ulong`.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-146">The `ul` or `UL` suffix specifies the `ulong` type.</span></span> <span data-ttu-id="8bfb4-147">Если суффикс `L` используется с литералом, значение которого больше 9 223 372 036 854 775 807 (максимальное значение типа `long`), литерал преобразуется в тип `ulong`.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-147">If the `L` suffix is used on a literal that is greater than 9,223,372,036,854,775,807 (the maximum value of `long`), the value is converted to the `ulong` type.</span></span> <span data-ttu-id="8bfb4-148">Если значение, представленное целочисленным литералом, превышает <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, происходит ошибка компиляции [CS1021](../../misc/cs1021.md).</span><span class="sxs-lookup"><span data-stu-id="8bfb4-148">If the value represented by an integral literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span> 

> [!NOTE]
> <span data-ttu-id="8bfb4-149">Строчную букву "l" можно использовать в качестве суффикса.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-149">You can use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="8bfb4-150">Однако при этом выдается предупреждение компилятора, так как букву "l" легко перепутать с цифрой "1".</span><span class="sxs-lookup"><span data-stu-id="8bfb4-150">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="8bfb4-151">Для ясности используйте "L".</span><span class="sxs-lookup"><span data-stu-id="8bfb4-151">Use "L" for clarity.</span></span>

### <a name="type-of-an-integral-literal"></a><span data-ttu-id="8bfb4-152">Тип целочисленного литерала</span><span class="sxs-lookup"><span data-stu-id="8bfb4-152">Type of an integral literal</span></span>

<span data-ttu-id="8bfb4-153">Если целочисленный литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение:</span><span class="sxs-lookup"><span data-stu-id="8bfb4-153">If an integral literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. `int`
1. `uint`
1. `long`
1. `ulong`

<span data-ttu-id="8bfb4-154">Целочисленный литерал можно преобразовать в тип с меньшим диапазоном, чем у типа по умолчанию, путем присвоения или приведения:</span><span class="sxs-lookup"><span data-stu-id="8bfb4-154">You can convert an integral literal to a type with a smaller range than the default using either an assignment or a cast:</span></span>

```csharp
byte byteVariable = 42; // type is byte
var signedByte = (sbyte)42; // type is sbyte.
```

<span data-ttu-id="8bfb4-155">Целочисленный литерал можно преобразовать в тип с большим диапазоном, чем у типа по умолчанию, путем присвоения, приведения или добавления суффикса:</span><span class="sxs-lookup"><span data-stu-id="8bfb4-155">You can convert an integral literal to a type with a larger range than the default using either assignment, a cast, or a suffix on the literal:</span></span>

```csharp
var unsignedLong = 42UL;
var longVariable = 42L;
ulong anotherUnsignedLong = 42;
var anotherLong = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="8bfb4-156">Преобразования</span><span class="sxs-lookup"><span data-stu-id="8bfb4-156">Conversions</span></span>

<span data-ttu-id="8bfb4-157">Между любыми двумя целочисленными типами, один из которых поддерживает любые значения другого, существует неявное преобразование (которое называется *расширяющим*).</span><span class="sxs-lookup"><span data-stu-id="8bfb4-157">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="8bfb4-158">Например, существует неявное преобразование из `int` в `long`, так как диапазон значений типа `int` является строгим подмножеством значений `long`.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-158">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="8bfb4-159">Целочисленный тип без знака меньшего размера может неявно преобразовываться в целочисленный тип со знаком большего размера.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-159">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="8bfb4-160">Кроме того, существуют неявные преобразования любых целочисленных типов в любые типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-160">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="8bfb4-161">Неявных преобразований целочисленных типов со знаком в целочисленные типы без знака нет.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-161">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="8bfb4-162">Если неявное преобразование между двумя целочисленными типами не определено, необходимо использовать явное приведение.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-162">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="8bfb4-163">Это называется *сужающим преобразованием*.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-163">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="8bfb4-164">Явное приведение требуется по той причине, что преобразование может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="8bfb4-164">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="see-also"></a><span data-ttu-id="8bfb4-165">См. также</span><span class="sxs-lookup"><span data-stu-id="8bfb4-165">See also</span></span>

- [<span data-ttu-id="8bfb4-166">Спецификация языка C# — целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="8bfb4-166">C# language specification - Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="8bfb4-167">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="8bfb4-167">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8bfb4-168">Типы с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8bfb4-168">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="8bfb4-169">Таблица значений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8bfb4-169">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="8bfb4-170">Таблица форматирования числовых результатов</span><span class="sxs-lookup"><span data-stu-id="8bfb4-170">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="8bfb4-171">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="8bfb4-171">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="8bfb4-172">Числовые значения в .NET</span><span class="sxs-lookup"><span data-stu-id="8bfb4-172">Numerics in .NET</span></span>](../../../standard/numerics.md)
