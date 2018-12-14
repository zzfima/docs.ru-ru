---
title: Ключевое слово uint (справочник по C#)
ms.date: 03/14/2017
f1_keywords:
- uint
- uint_CSharpKeyword
helpviewer_keywords:
- uint keyword [C#]
ms.openlocfilehash: 86cbb216bd960251ebd78916fae7865aa10aa5fc
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149696"
---
# <a name="uint-c-reference"></a><span data-ttu-id="610cc-102">uint (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="610cc-102">uint (C# Reference)</span></span>

<span data-ttu-id="610cc-103">Ключевое слово `uint` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="610cc-103">The `uint` keyword signifies an integral type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="610cc-104">Тип</span><span class="sxs-lookup"><span data-stu-id="610cc-104">Type</span></span>|<span data-ttu-id="610cc-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="610cc-105">Range</span></span>|<span data-ttu-id="610cc-106">Размер</span><span class="sxs-lookup"><span data-stu-id="610cc-106">Size</span></span>|<span data-ttu-id="610cc-107">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="610cc-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`uint`|<span data-ttu-id="610cc-108">От 0 до 4 294 967 295</span><span class="sxs-lookup"><span data-stu-id="610cc-108">0 to 4,294,967,295</span></span>|<span data-ttu-id="610cc-109">32-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="610cc-109">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|

<span data-ttu-id="610cc-110">**Примечание.** Тип `uint` не совместим с CLS.</span><span class="sxs-lookup"><span data-stu-id="610cc-110">**Note** The `uint` type is not CLS-compliant.</span></span> <span data-ttu-id="610cc-111">По возможности используйте `int`.</span><span class="sxs-lookup"><span data-stu-id="610cc-111">Use `int` whenever possible.</span></span>

## <a name="literals"></a><span data-ttu-id="610cc-112">Литералы</span><span class="sxs-lookup"><span data-stu-id="610cc-112">Literals</span></span>

<span data-ttu-id="610cc-113">Переменную `uint` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7.0) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="610cc-113">You can declare and initialize a `uint` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="610cc-114">Если целочисленный литерал выходит за пределы диапазона `uint` (то есть если он меньше <xref:System.UInt32.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="610cc-114">If the integer literal is outside the range of `uint` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="610cc-115">В следующем примере целые числа, равные 3 000 000 000 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `uint`.</span><span class="sxs-lookup"><span data-stu-id="610cc-115">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `uint` values.</span></span>

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]

> [!NOTE]
> <span data-ttu-id="610cc-116">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="610cc-116">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="610cc-117">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="610cc-117">Decimal literals have no prefix.</span></span>

<span data-ttu-id="610cc-118">Начиная с C# 7.0 было добавлено несколько возможностей для повышения удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="610cc-118">Starting with C# 7.0, a couple of features have been added to enhance readability:</span></span>

- <span data-ttu-id="610cc-119">В C# 7.0 поддерживается использование символа подчеркивания (`_`) в качестве разделителя цифр.</span><span class="sxs-lookup"><span data-stu-id="610cc-119">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="610cc-120">В C# 7.2 поддерживается использование `_` (после префикса) в качестве разделителя для двоичного или шестнадцатеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="610cc-120">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="610cc-121">Десятичный литерал не может начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="610cc-121">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="610cc-122">Ниже приведено несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="610cc-122">Some examples are shown below.</span></span>

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]

<span data-ttu-id="610cc-123">Целочисленные литералы могут также содержать суффикс, обозначающий тип.</span><span class="sxs-lookup"><span data-stu-id="610cc-123">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="610cc-124">Суффикс `U` или "u" обозначает либо `uint`, либо `ulong` в зависимости от числового значения литерала.</span><span class="sxs-lookup"><span data-stu-id="610cc-124">The suffix `U` or 'u' denotes either a `uint` or a `ulong`, depending on the numeric value of the literal.</span></span> <span data-ttu-id="610cc-125">В следующем примере суффикс `u` используется для обозначения целого числа без знака обоих типов.</span><span class="sxs-lookup"><span data-stu-id="610cc-125">The following example uses the `u` suffix to denote an unsigned integer of both types.</span></span> <span data-ttu-id="610cc-126">Обратите внимание, что первый литерал имеет тип `uint`, поскольку его значение меньше <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, а второй имеет тип `ulong`, поскольку его значение больше <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="610cc-126">Note that the first literal is a `uint` because its value is less than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, while the second is a `ulong` because its value is greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>

[!code-csharp[usuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]

<span data-ttu-id="610cc-127">Если целочисленный литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение:</span><span class="sxs-lookup"><span data-stu-id="610cc-127">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. [<span data-ttu-id="610cc-128">int</span><span class="sxs-lookup"><span data-stu-id="610cc-128">int</span></span>](int.md)
2. `uint`
3. [<span data-ttu-id="610cc-129">long</span><span class="sxs-lookup"><span data-stu-id="610cc-129">long</span></span>](long.md)
4. [<span data-ttu-id="610cc-130">ulong</span><span class="sxs-lookup"><span data-stu-id="610cc-130">ulong</span></span>](ulong.md)

## <a name="conversions"></a><span data-ttu-id="610cc-131">Преобразования</span><span class="sxs-lookup"><span data-stu-id="610cc-131">Conversions</span></span>

<span data-ttu-id="610cc-132">Существует предопределенное неявное преобразование типа `uint` в тип [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md) или [decimal](decimal.md).</span><span class="sxs-lookup"><span data-stu-id="610cc-132">There is a predefined implicit conversion from `uint` to [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md), or [decimal](decimal.md).</span></span> <span data-ttu-id="610cc-133">Например:</span><span class="sxs-lookup"><span data-stu-id="610cc-133">For example:</span></span>

```csharp
float myFloat = 4294967290;   // OK: implicit conversion to float
```

<span data-ttu-id="610cc-134">Существует предопределенное неявное преобразование типа [byte](byte.md), [ushort](ushort.md) или [char](char.md) в тип `uint`.</span><span class="sxs-lookup"><span data-stu-id="610cc-134">There is a predefined implicit conversion from [byte](byte.md), [ushort](ushort.md), or [char](char.md) to `uint`.</span></span> <span data-ttu-id="610cc-135">В противном случае необходимо использовать приведение.</span><span class="sxs-lookup"><span data-stu-id="610cc-135">Otherwise you must use a cast.</span></span> <span data-ttu-id="610cc-136">Например, следующий оператор назначения вызывает ошибку компиляции без приведения:</span><span class="sxs-lookup"><span data-stu-id="610cc-136">For example, the following assignment statement will produce a compilation error without a cast:</span></span>

```csharp
long aLong = 22;
// Error -- no implicit conversion from long:
uint uInt1 = aLong;
// OK -- explicit conversion:
uint uInt2 = (uint)aLong;
```

<span data-ttu-id="610cc-137">Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `uint` не существует.</span><span class="sxs-lookup"><span data-stu-id="610cc-137">Notice also that there is no implicit conversion from floating-point types to `uint`.</span></span> <span data-ttu-id="610cc-138">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="610cc-138">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
// Error -- no implicit conversion from double:
uint x = 3.0;
// OK -- explicit conversion:
uint y = (uint)3.0;
```

<span data-ttu-id="610cc-139">Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](float.md) и [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="610cc-139">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](float.md) and [double](double.md).</span></span>

<span data-ttu-id="610cc-140">Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="610cc-140">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="610cc-141">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="610cc-141">C# language specification</span></span>

<span data-ttu-id="610cc-142">Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="610cc-142">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="610cc-143">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="610cc-143">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="610cc-144">См. также</span><span class="sxs-lookup"><span data-stu-id="610cc-144">See also</span></span>

- <xref:System.UInt32>
- [<span data-ttu-id="610cc-145">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="610cc-145">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="610cc-146">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="610cc-146">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="610cc-147">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="610cc-147">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="610cc-148">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="610cc-148">Integral Types Table</span></span>](integral-types-table.md)
- [<span data-ttu-id="610cc-149">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="610cc-149">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="610cc-150">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="610cc-150">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="610cc-151">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="610cc-151">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)