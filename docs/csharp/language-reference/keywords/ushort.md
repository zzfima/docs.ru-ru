---
title: Справочник по C#. Ключевое слово ushort
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- ushort
- ushort_CSharpKeyword
helpviewer_keywords:
- ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
ms.openlocfilehash: 934e25576a8a24c176a54ec6af984459b513fe5a
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614466"
---
# <a name="ushort-c-reference"></a><span data-ttu-id="9abad-102">ushort (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9abad-102">ushort (C# Reference)</span></span>

<span data-ttu-id="9abad-103">Ключевое слово `ushort` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="9abad-103">The `ushort` keyword indicates an integral data type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="9abad-104">Тип</span><span class="sxs-lookup"><span data-stu-id="9abad-104">Type</span></span>|<span data-ttu-id="9abad-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="9abad-105">Range</span></span>|<span data-ttu-id="9abad-106">Размер</span><span class="sxs-lookup"><span data-stu-id="9abad-106">Size</span></span>|<span data-ttu-id="9abad-107">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="9abad-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`ushort`|<span data-ttu-id="9abad-108">От 0 до 65 535</span><span class="sxs-lookup"><span data-stu-id="9abad-108">0 to 65,535</span></span>|<span data-ttu-id="9abad-109">16-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="9abad-109">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="9abad-110">Литералы</span><span class="sxs-lookup"><span data-stu-id="9abad-110">Literals</span></span>

<span data-ttu-id="9abad-111">Переменную `ushort` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7.0) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="9abad-111">You can declare and initialize a `ushort` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="9abad-112">Если целочисленный литерал выходит за пределы диапазона `ushort` (то есть если он меньше <xref:System.UInt16.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="9abad-112">If the integer literal is outside the range of `ushort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="9abad-113">В следующем примере целые числа, равные 65 034 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, неявно преобразуются из типа [int](int.md) в значения `ushort`.</span><span class="sxs-lookup"><span data-stu-id="9abad-113">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](int.md) to `ushort` values.</span></span>

[!code-csharp[UShort](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]

> [!NOTE]
> <span data-ttu-id="9abad-114">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="9abad-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="9abad-115">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="9abad-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="9abad-116">Начиная с C# 7.0 было добавлено несколько возможностей для повышения удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="9abad-116">Starting with C# 7.0, a couple of features have been added to enhance readability:</span></span>

- <span data-ttu-id="9abad-117">В C# 7.0 поддерживается использование символа подчеркивания (`_`) в качестве разделителя цифр.</span><span class="sxs-lookup"><span data-stu-id="9abad-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="9abad-118">В C# 7.2 поддерживается использование `_` (после префикса) в качестве разделителя для двоичного или шестнадцатеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="9abad-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="9abad-119">Десятичный литерал не может начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="9abad-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="9abad-120">Ниже приведено несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="9abad-120">Some examples are shown below.</span></span>

[!code-csharp[UShort](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]

## <a name="compiler-overload-resolution"></a><span data-ttu-id="9abad-121">Разрешение перегрузки компилятора</span><span class="sxs-lookup"><span data-stu-id="9abad-121">Compiler overload resolution</span></span>

<span data-ttu-id="9abad-122">При вызове перегруженных методов необходимо использовать приведение типов.</span><span class="sxs-lookup"><span data-stu-id="9abad-122">A cast must be used when you call overloaded methods.</span></span> <span data-ttu-id="9abad-123">Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `ushort` и [int](int.md):</span><span class="sxs-lookup"><span data-stu-id="9abad-123">Consider, for example, the following overloaded methods that use `ushort` and [int](int.md) parameters:</span></span>

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(ushort s) {}
```

<span data-ttu-id="9abad-124">Использование приведения типа `ushort` гарантирует вызов метода правильного типа, например:</span><span class="sxs-lookup"><span data-stu-id="9abad-124">Using the `ushort` cast guarantees that the correct type is called, for example:</span></span>

```csharp
// Calls the method with the int parameter:
SampleMethod(5);
// Calls the method with the ushort parameter:
SampleMethod((ushort)5);
```

## <a name="conversions"></a><span data-ttu-id="9abad-125">Преобразования</span><span class="sxs-lookup"><span data-stu-id="9abad-125">Conversions</span></span>

<span data-ttu-id="9abad-126">Существует предопределенное преобразование типа `ushort` в типы [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md) или [decimal](decimal.md).</span><span class="sxs-lookup"><span data-stu-id="9abad-126">There is a predefined implicit conversion from `ushort` to [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md), or [decimal](decimal.md).</span></span>

<span data-ttu-id="9abad-127">Существует предопределенное неявное преобразование типа [byte](byte.md) или [char](char.md) в тип `ushort`.</span><span class="sxs-lookup"><span data-stu-id="9abad-127">There is a predefined implicit conversion from [byte](byte.md) or [char](char.md) to `ushort`.</span></span> <span data-ttu-id="9abad-128">В противном случае для выполнения явного преобразования следует использовать приведение.</span><span class="sxs-lookup"><span data-stu-id="9abad-128">Otherwise a cast must be used to perform an explicit conversion.</span></span> <span data-ttu-id="9abad-129">Рассмотрим, например, следующие две переменные `x` и `y` типа `ushort`:</span><span class="sxs-lookup"><span data-stu-id="9abad-129">Consider, for example, the following two `ushort` variables `x` and `y`:</span></span>

```csharp
ushort x = 5, y = 12;
```

<span data-ttu-id="9abad-130">Следующая инструкция назначения приведет к ошибке компиляции, потому что арифметическое выражение, расположенное справа от оператора назначения, по умолчанию оценивается как имеющее тип `int`.</span><span class="sxs-lookup"><span data-stu-id="9abad-130">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to `int` by default.</span></span>

```csharp
ushort z = x + y;   // Error: conversion from int to ushort
```

<span data-ttu-id="9abad-131">Для устранения этой проблемы используйте приведение:</span><span class="sxs-lookup"><span data-stu-id="9abad-131">To fix this problem, use a cast:</span></span>

```csharp
ushort z = (ushort)(x + y);   // OK: explicit conversion
```

<span data-ttu-id="9abad-132">Тем не менее можно использовать следующие инструкции, в которых переменная назначения имеет такой же или больший размер при хранении:</span><span class="sxs-lookup"><span data-stu-id="9abad-132">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>

```csharp
int m = x + y;
long n = x + y;
```

<span data-ttu-id="9abad-133">Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `ushort` не существует.</span><span class="sxs-lookup"><span data-stu-id="9abad-133">Notice also that there is no implicit conversion from floating-point types to `ushort`.</span></span> <span data-ttu-id="9abad-134">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="9abad-134">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
// Error -- no implicit conversion from double:
ushort x = 3.0;
// OK -- explicit conversion:
ushort y = (ushort)3.0;
```

<span data-ttu-id="9abad-135">Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](float.md) и [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="9abad-135">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](float.md) and [double](double.md).</span></span>

<span data-ttu-id="9abad-136">Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="9abad-136">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9abad-137">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="9abad-137">C# language specification</span></span>

<span data-ttu-id="9abad-138">Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="9abad-138">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="9abad-139">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="9abad-139">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="9abad-140">См. также</span><span class="sxs-lookup"><span data-stu-id="9abad-140">See also</span></span>

- <xref:System.UInt16>
- [<span data-ttu-id="9abad-141">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="9abad-141">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9abad-142">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9abad-142">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9abad-143">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="9abad-143">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="9abad-144">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="9abad-144">Integral Types Table</span></span>](integral-types-table.md)
- [<span data-ttu-id="9abad-145">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="9abad-145">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="9abad-146">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="9abad-146">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="9abad-147">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="9abad-147">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)
