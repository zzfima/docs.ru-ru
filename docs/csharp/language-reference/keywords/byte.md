---
title: byte. Справочник по C#
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- byte
- byte_CSharpKeyword
helpviewer_keywords:
- byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
ms.openlocfilehash: 94ecc19294d82038e5406a05f8e1281d47e43081
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185913"
---
# <a name="byte-c-reference"></a><span data-ttu-id="7829a-102">byte (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="7829a-102">byte (C# Reference)</span></span>

<span data-ttu-id="7829a-103">Ключевое слово `byte` обозначает целочисленный тип данных, в котором хранятся значения, описанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="7829a-103">`byte` denotes an integral type that stores values as indicated in the following table.</span></span>

|<span data-ttu-id="7829a-104">Тип</span><span class="sxs-lookup"><span data-stu-id="7829a-104">Type</span></span>|<span data-ttu-id="7829a-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="7829a-105">Range</span></span>|<span data-ttu-id="7829a-106">Размер</span><span class="sxs-lookup"><span data-stu-id="7829a-106">Size</span></span>|<span data-ttu-id="7829a-107">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="7829a-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`byte`|<span data-ttu-id="7829a-108">От 0 до 255</span><span class="sxs-lookup"><span data-stu-id="7829a-108">0 to 255</span></span>|<span data-ttu-id="7829a-109">8-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="7829a-109">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="7829a-110">Литералы</span><span class="sxs-lookup"><span data-stu-id="7829a-110">Literals</span></span>

<span data-ttu-id="7829a-111">Переменную `byte` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7.0) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="7829a-111">You can declare and initialize a `byte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="7829a-112">Если целочисленный литерал выходит за пределы диапазона `byte` (то есть если он меньше <xref:System.Byte.MinValue?displayProperty=nameWithType> или больше <xref:System.Byte.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="7829a-112">If the integer literal is outside the range of `byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="7829a-113">В следующем примере целые числа, равные 201 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, неявно преобразуются из типа [int](../../../csharp/language-reference/keywords/int.md) в значения `byte`.</span><span class="sxs-lookup"><span data-stu-id="7829a-113">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `byte` values.</span></span>

[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]

> [!NOTE]
> <span data-ttu-id="7829a-114">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="7829a-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="7829a-115">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="7829a-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="7829a-116">Начиная с C# 7.0 было добавлено несколько возможностей для повышения удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="7829a-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span>
- <span data-ttu-id="7829a-117">В C# 7.0 поддерживается использование символа подчеркивания (`_`) в качестве разделителя цифр.</span><span class="sxs-lookup"><span data-stu-id="7829a-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="7829a-118">В C# 7.2 поддерживается использование `_` (после префикса) в качестве разделителя для двоичного или шестнадцатеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="7829a-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="7829a-119">Десятичный литерал не может начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="7829a-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="7829a-120">Ниже приведено несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="7829a-120">Some examples are shown below.</span></span>

[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]

## <a name="conversions"></a><span data-ttu-id="7829a-121">Преобразования</span><span class="sxs-lookup"><span data-stu-id="7829a-121">Conversions</span></span>

<span data-ttu-id="7829a-122">Существует предопределенное неявное преобразование типа `byte` в типы [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="7829a-122">There is a predefined implicit conversion from `byte` to [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>

<span data-ttu-id="7829a-123">Невозможно неявным образом преобразовать не являющиеся литералами числовые типы большего размера при хранении в тип `byte`.</span><span class="sxs-lookup"><span data-stu-id="7829a-123">You cannot implicitly convert non-literal numeric types of larger storage size to `byte`.</span></span> <span data-ttu-id="7829a-124">Дополнительные сведения о размере целочисленных типов при хранении см. в разделе [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="7829a-124">For more information on the storage sizes of integral types, see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md).</span></span> <span data-ttu-id="7829a-125">Рассмотрим, например, следующие две переменные `x` и `y` типа `byte`:</span><span class="sxs-lookup"><span data-stu-id="7829a-125">Consider, for example, the following two `byte` variables `x` and `y`:</span></span>

```csharp
byte x = 10, y = 20;
```

<span data-ttu-id="7829a-126">Следующий оператор присваивания приведет к ошибке компиляции, потому что арифметическое выражение, расположенное справа от оператора присваивания, по умолчанию оценивается как имеющее тип `int`.</span><span class="sxs-lookup"><span data-stu-id="7829a-126">The following assignment statement will produce a compilation error, because the arithmetic expression on the right-hand side of the assignment operator evaluates to `int` by default.</span></span>

```csharp
// Error: conversion from int to byte:
byte z = x + y;
```

<span data-ttu-id="7829a-127">Для устранения этой проблемы используйте приведение:</span><span class="sxs-lookup"><span data-stu-id="7829a-127">To fix this problem, use a cast:</span></span>

```csharp
// OK: explicit conversion:
byte z = (byte)(x + y);
```

<span data-ttu-id="7829a-128">Однако можно использовать следующие операторы, в которых переменная назначения имеет такой же или больший размер при хранении:</span><span class="sxs-lookup"><span data-stu-id="7829a-128">It is possible though, to use the following statements where the destination variable has the same storage size or a larger storage size:</span></span>

```csharp
int x = 10, y = 20;
int m = x + y;
long n = x + y;
```

<span data-ttu-id="7829a-129">Кроме того, неявного преобразования типов с плавающей запятой в тип `byte` не существует.</span><span class="sxs-lookup"><span data-stu-id="7829a-129">Also, there is no implicit conversion from floating-point types to `byte`.</span></span> <span data-ttu-id="7829a-130">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="7829a-130">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
// Error: no implicit conversion from double:
byte x = 3.0;
// OK: explicit conversion:
byte y = (byte)3.0;
```

<span data-ttu-id="7829a-131">При вызове перегруженных методов необходимо использовать приведение типов.</span><span class="sxs-lookup"><span data-stu-id="7829a-131">When calling overloaded methods, a cast must be used.</span></span> <span data-ttu-id="7829a-132">Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `byte` и [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="7829a-132">Consider, for example, the following overloaded methods that use `byte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(byte b) {}
```

<span data-ttu-id="7829a-133">Использование приведения типа `byte` гарантирует вызов метода правильного типа, например:</span><span class="sxs-lookup"><span data-stu-id="7829a-133">Using the `byte` cast guarantees that the correct type is called, for example:</span></span>

```csharp
// Calling the method with the int parameter:
SampleMethod(5);
// Calling the method with the byte parameter:
SampleMethod((byte)5);
```

<span data-ttu-id="7829a-134">Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="7829a-134">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>

<span data-ttu-id="7829a-135">Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="7829a-135">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7829a-136">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7829a-136">C# Language Specification</span></span>

<span data-ttu-id="7829a-137">Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="7829a-137">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="7829a-138">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="7829a-138">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="7829a-139">См. также</span><span class="sxs-lookup"><span data-stu-id="7829a-139">See also</span></span>

- <xref:System.Byte>
- [<span data-ttu-id="7829a-140">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="7829a-140">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="7829a-141">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7829a-141">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="7829a-142">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="7829a-142">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="7829a-143">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="7829a-143">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)
- [<span data-ttu-id="7829a-144">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="7829a-144">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="7829a-145">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="7829a-145">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="7829a-146">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="7829a-146">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
