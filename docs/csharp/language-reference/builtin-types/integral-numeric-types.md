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
ms.openlocfilehash: 0a1ed01d9e6cb86ea177e8b947627f9dc02eedae
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744217"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="55541-103">Целочисленные типы (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="55541-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="55541-104">**Целочисленные типы** — это подмножество **простых типов**. Они могут инициализироваться [*литералами*](#integral-literals).</span><span class="sxs-lookup"><span data-stu-id="55541-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integral-literals).</span></span> <span data-ttu-id="55541-105">Кроме того, все целочисленные типы являются типами значений.</span><span class="sxs-lookup"><span data-stu-id="55541-105">All integral types are also value types.</span></span>

<span data-ttu-id="55541-106">Все целочисленные типы поддерживают [арифметические](../operators/arithmetic-operators.md) операторы, [побитовые логические](../operators/bitwise-and-shift-operators.md) операторы, операторы [сравнения и равенства](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="55541-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="sizes-and-ranges"></a><span data-ttu-id="55541-107">Размеры и диапазоны</span><span class="sxs-lookup"><span data-stu-id="55541-107">Sizes and ranges</span></span>

<span data-ttu-id="55541-108">В таблице ниже приводятся сведения о размерах и диапазонах для целочисленных типов.</span><span class="sxs-lookup"><span data-stu-id="55541-108">The following table shows the sizes and ranges of the integral types:</span></span>

|<span data-ttu-id="55541-109">Тип</span><span class="sxs-lookup"><span data-stu-id="55541-109">Type</span></span>|<span data-ttu-id="55541-110">Диапазон</span><span class="sxs-lookup"><span data-stu-id="55541-110">Range</span></span>|<span data-ttu-id="55541-111">Размер</span><span class="sxs-lookup"><span data-stu-id="55541-111">Size</span></span>|  
|----------|-----------|----------|  
|`sbyte`|<span data-ttu-id="55541-112">От -128 до 127</span><span class="sxs-lookup"><span data-stu-id="55541-112">-128 to 127</span></span>|<span data-ttu-id="55541-113">8-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="55541-113">Signed 8-bit integer</span></span>|  
|`byte`|<span data-ttu-id="55541-114">От 0 до 255</span><span class="sxs-lookup"><span data-stu-id="55541-114">0 to 255</span></span>|<span data-ttu-id="55541-115">8-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="55541-115">Unsigned 8-bit integer</span></span>|  
|`short`|<span data-ttu-id="55541-116">От -32 768 до 32 767</span><span class="sxs-lookup"><span data-stu-id="55541-116">-32,768 to 32,767</span></span>|<span data-ttu-id="55541-117">16-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="55541-117">Signed 16-bit integer</span></span>|  
|`ushort`|<span data-ttu-id="55541-118">От 0 до 65 535</span><span class="sxs-lookup"><span data-stu-id="55541-118">0 to 65,535</span></span>|<span data-ttu-id="55541-119">16-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="55541-119">Unsigned 16-bit integer</span></span>|  
|`int`|<span data-ttu-id="55541-120">От -2 147 483 648 до 2 147 483 647</span><span class="sxs-lookup"><span data-stu-id="55541-120">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="55541-121">32-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="55541-121">Signed 32-bit integer</span></span>|  
|`uint`|<span data-ttu-id="55541-122">От 0 до 4 294 967 295</span><span class="sxs-lookup"><span data-stu-id="55541-122">0 to 4,294,967,295</span></span>|<span data-ttu-id="55541-123">32-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="55541-123">Unsigned 32-bit integer</span></span>|  
|`long`|<span data-ttu-id="55541-124">От -9 223 372 036 854 775 808 до 9 223 372 036 854 775 807</span><span class="sxs-lookup"><span data-stu-id="55541-124">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="55541-125">64-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="55541-125">Signed 64-bit integer</span></span>|  
|`ulong`|<span data-ttu-id="55541-126">От 0 до 18 446 744 073 709 551 615</span><span class="sxs-lookup"><span data-stu-id="55541-126">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="55541-127">64-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="55541-127">Unsigned 64-bit integer</span></span>|  

<span data-ttu-id="55541-128">Значение по умолчанию для всех целочисленных типов — `0`.</span><span class="sxs-lookup"><span data-stu-id="55541-128">The default value for all integral types is `0`.</span></span> <span data-ttu-id="55541-129">Каждый целочисленный тип имеет константы `MinValue` и `MaxValue` с минимальным и максимальным значениями этого типа.</span><span class="sxs-lookup"><span data-stu-id="55541-129">Each of the integral types has constants named `MinValue` and `MaxValue` for the minimum and maximum value for that type.</span></span>

<span data-ttu-id="55541-130">Используйте структуру <xref:System.Numerics.BigInteger?displayProperty=nameWithType>, чтобы представить целое число со знаком без верхней и нижней границ.</span><span class="sxs-lookup"><span data-stu-id="55541-130">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integral-literals"></a><span data-ttu-id="55541-131">Целочисленные литералы</span><span class="sxs-lookup"><span data-stu-id="55541-131">Integral literals</span></span>

<span data-ttu-id="55541-132">Целочисленные литералы можно задать как *десятичные*, *шестнадцатеричные* или *двоичные литералы*.</span><span class="sxs-lookup"><span data-stu-id="55541-132">Integral literals can be specified as *decimal literals*, *hexadecimal literals*, or *binary literals*.</span></span> <span data-ttu-id="55541-133">Ниже приведены примеры каждого из них:</span><span class="sxs-lookup"><span data-stu-id="55541-133">An example of each is shown below:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="55541-134">Десятичные литералы не требуют префикса.</span><span class="sxs-lookup"><span data-stu-id="55541-134">Decimal literals don't require any prefix.</span></span> <span data-ttu-id="55541-135">Префикс `x` или `X` означает, что это *шестнадцатеричный литерал*.</span><span class="sxs-lookup"><span data-stu-id="55541-135">The `x` or `X` prefix signifies a *hexadecimal literal*.</span></span> <span data-ttu-id="55541-136">Префикс `b` или `B` означает, что это *двоичный литерал*.</span><span class="sxs-lookup"><span data-stu-id="55541-136">The `b` or `B` prefix signifies a *binary literal*.</span></span> <span data-ttu-id="55541-137">Объявление `binaryLiteral` демонстрирует использование символа `_` в качестве *разделителя разрядов*.</span><span class="sxs-lookup"><span data-stu-id="55541-137">The declaration of `binaryLiteral` demonstrates the use of `_` as a *digit separator*.</span></span> <span data-ttu-id="55541-138">Разделитель разрядов можно использовать с любыми числовыми литералами.</span><span class="sxs-lookup"><span data-stu-id="55541-138">The digit separator can be used with all numeric literals.</span></span> <span data-ttu-id="55541-139">Двоичные литералы и разделитель разрядов `_` поддерживаются начиная с C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="55541-139">Binary literals and the digit separator `_` are supported starting with C# 7.0.</span></span>

### <a name="literal-suffixes"></a><span data-ttu-id="55541-140">Суффиксы литералов</span><span class="sxs-lookup"><span data-stu-id="55541-140">Literal suffixes</span></span> 

<span data-ttu-id="55541-141">Суффикс `l` или `L` указывает, что целочисленный литерал должен иметь тип `long`.</span><span class="sxs-lookup"><span data-stu-id="55541-141">The `l` or `L` suffix specifies that the integral literal should be of the `long` type.</span></span> <span data-ttu-id="55541-142">Суффикс `ul` или `UL` указывает тип `ulong`.</span><span class="sxs-lookup"><span data-stu-id="55541-142">The `ul` or `UL` suffix specifies the `ulong` type.</span></span> <span data-ttu-id="55541-143">Если суффикс `L` используется с литералом, значение которого больше 9 223 372 036 854 775 807 (максимальное значение типа `long`), литерал преобразуется в тип `ulong`.</span><span class="sxs-lookup"><span data-stu-id="55541-143">If the `L` suffix is used on a literal that is greater than 9,223,372,036,854,775,807 (the maximum value of `long`), the value is converted to the `ulong` type.</span></span> <span data-ttu-id="55541-144">Если значение, представленное целочисленным литералом, превышает <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, происходит ошибка компиляции [CS1021](../../misc/cs1021.md).</span><span class="sxs-lookup"><span data-stu-id="55541-144">If the value represented by an integral literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span> 

> [!NOTE]
> <span data-ttu-id="55541-145">Строчную букву "l" можно использовать в качестве суффикса.</span><span class="sxs-lookup"><span data-stu-id="55541-145">You can use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="55541-146">Однако при этом выдается предупреждение компилятора, так как букву "l" легко перепутать с цифрой "1".</span><span class="sxs-lookup"><span data-stu-id="55541-146">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="55541-147">Для ясности используйте "L".</span><span class="sxs-lookup"><span data-stu-id="55541-147">Use "L" for clarity.</span></span>

### <a name="type-of-an-integral-literal"></a><span data-ttu-id="55541-148">Тип целочисленного литерала</span><span class="sxs-lookup"><span data-stu-id="55541-148">Type of an integral literal</span></span>

<span data-ttu-id="55541-149">Если целочисленный литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение:</span><span class="sxs-lookup"><span data-stu-id="55541-149">If an integral literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. `int`
1. `uint`
1. `long`
1. `ulong`

<span data-ttu-id="55541-150">Целочисленный литерал можно преобразовать в тип с меньшим диапазоном, чем у типа по умолчанию, путем присвоения или приведения:</span><span class="sxs-lookup"><span data-stu-id="55541-150">You can convert an integral literal to a type with a smaller range than the default using either an assignment or a cast:</span></span>

```csharp
byte byteVariable = 42; // type is byte
var signedByte = (sbyte)42; // type is sbyte.
```

<span data-ttu-id="55541-151">Целочисленный литерал можно преобразовать в тип с большим диапазоном, чем у типа по умолчанию, путем присвоения, приведения или добавления суффикса:</span><span class="sxs-lookup"><span data-stu-id="55541-151">You can convert an integral literal to a type with a larger range than the default using either assignment, a cast, or a suffix on the literal:</span></span>

```csharp
var unsignedLong = 42UL;
var longVariable = 42L;
ulong anotherUnsignedLong = 42;
var anotherLong = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="55541-152">Преобразования</span><span class="sxs-lookup"><span data-stu-id="55541-152">Conversions</span></span>

<span data-ttu-id="55541-153">Между любыми двумя целочисленными типами, один из которых поддерживает любые значения другого, существует неявное преобразование (которое называется *расширяющим*).</span><span class="sxs-lookup"><span data-stu-id="55541-153">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="55541-154">Например, существует неявное преобразование из `int` в `long`, так как диапазон значений типа `int` является строгим подмножеством значений `long`.</span><span class="sxs-lookup"><span data-stu-id="55541-154">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="55541-155">Целочисленный тип без знака меньшего размера может неявно преобразовываться в целочисленный тип со знаком большего размера.</span><span class="sxs-lookup"><span data-stu-id="55541-155">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="55541-156">Кроме того, существуют неявные преобразования любых целочисленных типов в любые типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="55541-156">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="55541-157">Неявных преобразований целочисленных типов со знаком в целочисленные типы без знака нет.</span><span class="sxs-lookup"><span data-stu-id="55541-157">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="55541-158">Если неявное преобразование между двумя целочисленными типами не определено, необходимо использовать явное приведение.</span><span class="sxs-lookup"><span data-stu-id="55541-158">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="55541-159">Это называется *сужающим преобразованием*.</span><span class="sxs-lookup"><span data-stu-id="55541-159">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="55541-160">Явное приведение требуется по той причине, что преобразование может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="55541-160">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="see-also"></a><span data-ttu-id="55541-161">См. также</span><span class="sxs-lookup"><span data-stu-id="55541-161">See also</span></span>

- [<span data-ttu-id="55541-162">Спецификация языка C# — целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="55541-162">C# language specification - Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="55541-163">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="55541-163">C# reference</span></span>](../index.md)
- [<span data-ttu-id="55541-164">Типы с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="55541-164">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="55541-165">Таблица значений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="55541-165">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="55541-166">Таблица форматирования числовых результатов</span><span class="sxs-lookup"><span data-stu-id="55541-166">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="55541-167">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="55541-167">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="55541-168">Числовые значения в .NET</span><span class="sxs-lookup"><span data-stu-id="55541-168">Numerics in .NET</span></span>](../../../standard/numerics.md)
- <xref:System.Byte?displayProperty=nameWithType>
- <xref:System.SByte?displayProperty=nameWithType>
- <xref:System.Int16?displayProperty=nameWithType>
- <xref:System.UInt16?displayProperty=nameWithType>
- <xref:System.Int32?displayProperty=nameWithType>
- <xref:System.UInt32?displayProperty=nameWithType>
- <xref:System.Int64?displayProperty=nameWithType>
- <xref:System.UInt64?displayProperty=nameWithType>
