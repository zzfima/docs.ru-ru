---
title: short (справочник по C#)
ms.date: 03/14/2017
f1_keywords:
- short
- short_CSharpKeyword
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
ms.openlocfilehash: d3b374c01c78a63e8341023b65dc3e57542ec1fd
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "50184157"
---
# <a name="short-c-reference"></a><span data-ttu-id="b2457-102">short (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b2457-102">short (C# Reference)</span></span>

<span data-ttu-id="b2457-103">Ключевое слово `short` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведены в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="b2457-103">`short` denotes an integral data type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="b2457-104">Тип</span><span class="sxs-lookup"><span data-stu-id="b2457-104">Type</span></span>|<span data-ttu-id="b2457-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="b2457-105">Range</span></span>|<span data-ttu-id="b2457-106">Размер</span><span class="sxs-lookup"><span data-stu-id="b2457-106">Size</span></span>|<span data-ttu-id="b2457-107">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="b2457-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`short`|<span data-ttu-id="b2457-108">От -32 768 до 32 767</span><span class="sxs-lookup"><span data-stu-id="b2457-108">-32,768 to 32,767</span></span>|<span data-ttu-id="b2457-109">16-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="b2457-109">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="b2457-110">Литералы</span><span class="sxs-lookup"><span data-stu-id="b2457-110">Literals</span></span>

<span data-ttu-id="b2457-111">Переменную `short` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7.0) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="b2457-111">You can declare and initialize a `short` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="b2457-112">Если целочисленный литерал выходит за пределы диапазона `short` (то есть если он меньше <xref:System.Int16.MinValue?displayProperty=nameWithType> или больше <xref:System.Int16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="b2457-112">If the integer literal is outside the range of `short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="b2457-113">В следующем примере целые числа, равные 1034 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, неявно преобразуются из типа [int](int.md) в значения `short`.</span><span class="sxs-lookup"><span data-stu-id="b2457-113">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](int.md) to `short` values.</span></span>

[!code-csharp[Short](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]

> [!NOTE]
> <span data-ttu-id="b2457-114">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="b2457-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="b2457-115">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="b2457-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="b2457-116">Начиная с C# 7.0 было добавлено несколько возможностей для повышения удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="b2457-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span>

- <span data-ttu-id="b2457-117">В C# 7.0 поддерживается использование символа подчеркивания (`_`) в качестве разделителя цифр.</span><span class="sxs-lookup"><span data-stu-id="b2457-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="b2457-118">В C# 7.2 поддерживается использование `_` (после префикса) в качестве разделителя для двоичного или шестнадцатеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="b2457-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="b2457-119">Десятичный литерал не может начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="b2457-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="b2457-120">Ниже приведено несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="b2457-120">Some examples are shown below.</span></span>

[!code-csharp[Short](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]

## <a name="compiler-overload-resolution"></a><span data-ttu-id="b2457-121">Разрешение перегрузки компилятора</span><span class="sxs-lookup"><span data-stu-id="b2457-121">Compiler overload resolution</span></span>

<span data-ttu-id="b2457-122">При вызове перегруженных методов необходимо использовать приведение типов.</span><span class="sxs-lookup"><span data-stu-id="b2457-122">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="b2457-123">Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `short` и [int](int.md):</span><span class="sxs-lookup"><span data-stu-id="b2457-123">Consider, for example, the following overloaded methods that use `short` and [int](int.md) parameters:</span></span>

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(short s) {}
```

<span data-ttu-id="b2457-124">Использование приведения типа `short` гарантирует вызов метода правильного типа, например:</span><span class="sxs-lookup"><span data-stu-id="b2457-124">Using the `short` cast guarantees that the correct type is called, for example:</span></span>

```csharp
SampleMethod(5);         // Calling the method with the int parameter
SampleMethod((short)5);  // Calling the method with the short parameter
```

## <a name="conversions"></a><span data-ttu-id="b2457-125">Преобразования</span><span class="sxs-lookup"><span data-stu-id="b2457-125">Conversions</span></span>

<span data-ttu-id="b2457-126">Существует предопределенное неявное преобразование типа `short` в тип [int](int.md), [long](long.md), [float](float.md), [double](double.md) или [decimal](decimal.md).</span><span class="sxs-lookup"><span data-stu-id="b2457-126">There is a predefined implicit conversion from `short` to [int](int.md), [long](long.md), [float](float.md), [double](double.md), or [decimal](decimal.md).</span></span>

<span data-ttu-id="b2457-127">Нельзя неявно преобразовать не являющиеся литералами числовые типы большего размера при хранении в тип `short` (сведения о размере целочисленных типов при хранении см. в разделе [Таблица целых типов](integral-types-table.md)).</span><span class="sxs-lookup"><span data-stu-id="b2457-127">You cannot implicitly convert nonliteral numeric types of larger storage size to `short` (see [Integral Types Table](integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="b2457-128">Рассмотрим, например, следующие две переменные `x` и `y` типа `short`:</span><span class="sxs-lookup"><span data-stu-id="b2457-128">Consider, for example, the following two `short` variables `x` and `y`:</span></span>

```csharp
short x = 5, y = 12;
```

<span data-ttu-id="b2457-129">Приведенный ниже оператор присваивания приведет к ошибке компиляции, потому что арифметическое выражение, расположенное справа от оператора присваивания, по умолчанию оценивается как имеющее тип [int](int.md).</span><span class="sxs-lookup"><span data-stu-id="b2457-129">The following assignment statement produces a compilation error because the arithmetic expression on the right-hand side of the assignment operator evaluates to [int](int.md) by default.</span></span>

```csharp
short z  = x + y;        // Compiler error CS0266: no conversion from int to short
```

<span data-ttu-id="b2457-130">Для устранения этой проблемы используйте приведение:</span><span class="sxs-lookup"><span data-stu-id="b2457-130">To fix this problem, use a cast:</span></span>

```csharp
short z  = (short)(x + y);   // Explicit conversion
```

<span data-ttu-id="b2457-131">Также можно использовать следующие инструкции, в которых переменная назначения имеет такой же или больший размер при хранении:</span><span class="sxs-lookup"><span data-stu-id="b2457-131">It is also possible to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>

```csharp
int m = x + y;
long n = x + y;
```

<span data-ttu-id="b2457-132">Неявного преобразования типов с плавающей запятой в тип `short` не существует.</span><span class="sxs-lookup"><span data-stu-id="b2457-132">There is no implicit conversion from floating-point types to `short`.</span></span> <span data-ttu-id="b2457-133">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="b2457-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
short x = 3.0;          // Error: no implicit conversion from double
short y = (short)3.0;   // OK: explicit conversion
```

<span data-ttu-id="b2457-134">Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](float.md) и [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="b2457-134">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](float.md) and [double](double.md).</span></span>

<span data-ttu-id="b2457-135">Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="b2457-135">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b2457-136">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b2457-136">C# language specification</span></span>

<span data-ttu-id="b2457-137">Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="b2457-137">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="b2457-138">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="b2457-138">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2457-139">См. также</span><span class="sxs-lookup"><span data-stu-id="b2457-139">See also</span></span>

- <xref:System.Int16>
- [<span data-ttu-id="b2457-140">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b2457-140">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b2457-141">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b2457-141">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b2457-142">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="b2457-142">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b2457-143">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="b2457-143">Integral Types Table</span></span>](integral-types-table.md)
- [<span data-ttu-id="b2457-144">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="b2457-144">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="b2457-145">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="b2457-145">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="b2457-146">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="b2457-146">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)