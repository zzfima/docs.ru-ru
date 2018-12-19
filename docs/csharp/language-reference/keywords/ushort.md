---
title: ushort. Справочник по C#
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- ushort
- ushort_CSharpKeyword
helpviewer_keywords:
- ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
ms.openlocfilehash: e70964802aa6d67cdf8ae46aff7f35a26fbf7ea4
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245159"
---
# <a name="ushort-c-reference"></a><span data-ttu-id="3884f-102">ushort (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="3884f-102">ushort (C# Reference)</span></span>

<span data-ttu-id="3884f-103">Ключевое слово `ushort` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="3884f-103">The `ushort` keyword indicates an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="3884f-104">Тип</span><span class="sxs-lookup"><span data-stu-id="3884f-104">Type</span></span>|<span data-ttu-id="3884f-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="3884f-105">Range</span></span>|<span data-ttu-id="3884f-106">Размер</span><span class="sxs-lookup"><span data-stu-id="3884f-106">Size</span></span>|<span data-ttu-id="3884f-107">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="3884f-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ushort`|<span data-ttu-id="3884f-108">От 0 до 65 535</span><span class="sxs-lookup"><span data-stu-id="3884f-108">0 to 65,535</span></span>|<span data-ttu-id="3884f-109">16-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="3884f-109">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="3884f-110">Литералы</span><span class="sxs-lookup"><span data-stu-id="3884f-110">Literals</span></span>  

<span data-ttu-id="3884f-111">Переменную `ushort` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7.0) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="3884f-111">You can declare and initialize a `ushort` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="3884f-112">Если целочисленный литерал выходит за пределы диапазона `ushort` (то есть если он меньше <xref:System.UInt16.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="3884f-112">If the integer literal is outside the range of `ushort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="3884f-113">В следующем примере целые числа, равные 65 034 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, неявно преобразуются из типа [int](../../../csharp/language-reference/keywords/int.md) в значения `ushort`.</span><span class="sxs-lookup"><span data-stu-id="3884f-113">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `ushort` values.</span></span>    
  
[!code-csharp[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]  

> [!NOTE] 
> <span data-ttu-id="3884f-114">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="3884f-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="3884f-115">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="3884f-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="3884f-116">Начиная с C# 7.0 было добавлено несколько возможностей для повышения удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="3884f-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="3884f-117">В C# 7.0 поддерживается использование символа подчеркивания (`_`) в качестве разделителя цифр.</span><span class="sxs-lookup"><span data-stu-id="3884f-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="3884f-118">В C# 7.2 поддерживается использование `_` (после префикса) в качестве разделителя для двоичного или шестнадцатеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="3884f-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="3884f-119">Десятичный литерал не может начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="3884f-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="3884f-120">Ниже приведено несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="3884f-120">Some examples are shown below.</span></span>

[!code-csharp[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="3884f-121">Разрешение перегрузки компилятора</span><span class="sxs-lookup"><span data-stu-id="3884f-121">Compiler overload resolution</span></span>
  
 <span data-ttu-id="3884f-122">При вызове перегруженных методов необходимо использовать приведение типов.</span><span class="sxs-lookup"><span data-stu-id="3884f-122">A cast must be used when you call overloaded methods.</span></span> <span data-ttu-id="3884f-123">Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `ushort` и [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="3884f-123">Consider, for example, the following overloaded methods that use `ushort` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ushort s) {}  
```  
 
 <span data-ttu-id="3884f-124">Использование приведения типа `ushort` гарантирует вызов метода правильного типа, например:</span><span class="sxs-lookup"><span data-stu-id="3884f-124">Using the `ushort` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
// Calls the method with the int parameter:  
SampleMethod(5);  
// Calls the method with the ushort parameter:  
SampleMethod((ushort)5);    
```  
  
## <a name="conversions"></a><span data-ttu-id="3884f-125">Преобразования</span><span class="sxs-lookup"><span data-stu-id="3884f-125">Conversions</span></span>  
 <span data-ttu-id="3884f-126">Существует предопределенное преобразование типа `ushort` в типы [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="3884f-126">There is a predefined implicit conversion from `ushort` to [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="3884f-127">Существует предопределенное неявное преобразование типа [byte](../../../csharp/language-reference/keywords/byte.md) или [char](../../../csharp/language-reference/keywords/char.md) в тип `ushort`.</span><span class="sxs-lookup"><span data-stu-id="3884f-127">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md) or [char](../../../csharp/language-reference/keywords/char.md) to `ushort`.</span></span> <span data-ttu-id="3884f-128">В противном случае для выполнения явного преобразования следует использовать приведение.</span><span class="sxs-lookup"><span data-stu-id="3884f-128">Otherwise a cast must be used to perform an explicit conversion.</span></span> <span data-ttu-id="3884f-129">Рассмотрим, например, следующие две переменные `x` и `y` типа `ushort`:</span><span class="sxs-lookup"><span data-stu-id="3884f-129">Consider, for example, the following two `ushort` variables `x` and `y`:</span></span>  
  
```csharp 
ushort x = 5, y = 12;  
```  
  
 <span data-ttu-id="3884f-130">Следующая инструкция назначения приведет к ошибке компиляции, потому что арифметическое выражение, расположенное справа от оператора назначения, по умолчанию оценивается как имеющее тип `int`.</span><span class="sxs-lookup"><span data-stu-id="3884f-130">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to `int` by default.</span></span>  
  
```csharp  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 <span data-ttu-id="3884f-131">Для устранения этой проблемы используйте приведение:</span><span class="sxs-lookup"><span data-stu-id="3884f-131">To fix this problem, use a cast:</span></span>  
  
```csharp 
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 <span data-ttu-id="3884f-132">Тем не менее можно использовать следующие инструкции, в которых переменная назначения имеет такой же или больший размер при хранении:</span><span class="sxs-lookup"><span data-stu-id="3884f-132">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="3884f-133">Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `ushort` не существует.</span><span class="sxs-lookup"><span data-stu-id="3884f-133">Notice also that there is no implicit conversion from floating-point types to `ushort`.</span></span> <span data-ttu-id="3884f-134">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="3884f-134">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 <span data-ttu-id="3884f-135">Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="3884f-135">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="3884f-136">Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="3884f-136">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3884f-137">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="3884f-137">C# Language Specification</span></span>  

<span data-ttu-id="3884f-138">Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="3884f-138">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="3884f-139">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="3884f-139">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3884f-140">См. также</span><span class="sxs-lookup"><span data-stu-id="3884f-140">See Also</span></span>

- <xref:System.UInt16>  
- [<span data-ttu-id="3884f-141">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="3884f-141">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="3884f-142">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3884f-142">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3884f-143">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="3884f-143">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="3884f-144">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="3884f-144">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="3884f-145">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="3884f-145">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="3884f-146">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="3884f-146">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="3884f-147">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="3884f-147">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
