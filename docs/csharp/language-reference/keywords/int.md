---
title: int. Справочник по C#
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- int_CSharpKeyword
- int
helpviewer_keywords:
- int keyword [C#]
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
ms.openlocfilehash: b1a621b7cce61ecd2c26c72adbdc3aa56749c914
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54615654"
---
# <a name="int-c-reference"></a><span data-ttu-id="f46a8-102">int (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f46a8-102">int (C# Reference)</span></span>

<span data-ttu-id="f46a8-103">`int` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f46a8-103">`int` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="f46a8-104">Тип</span><span class="sxs-lookup"><span data-stu-id="f46a8-104">Type</span></span>|<span data-ttu-id="f46a8-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="f46a8-105">Range</span></span>|<span data-ttu-id="f46a8-106">Размер</span><span class="sxs-lookup"><span data-stu-id="f46a8-106">Size</span></span>|<span data-ttu-id="f46a8-107">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="f46a8-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`int`|<span data-ttu-id="f46a8-108">От -2 147 483 648 до 2 147 483 647</span><span class="sxs-lookup"><span data-stu-id="f46a8-108">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="f46a8-109">32-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="f46a8-109">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="f46a8-110">Литералы</span><span class="sxs-lookup"><span data-stu-id="f46a8-110">Literals</span></span>  
 
<span data-ttu-id="f46a8-111">Переменную `int` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7.0) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="f46a8-111">You can declare and initialize an `int` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="f46a8-112">Если целочисленный литерал выходит за пределы диапазона `int` (то есть если он меньше <xref:System.Int32.MinValue?displayProperty=nameWithType> или больше <xref:System.Int32.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="f46a8-112">If the integer literal is outside the range of `int` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="f46a8-113">В следующем примере целые числа, равные 90 946 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `int`.</span><span class="sxs-lookup"><span data-stu-id="f46a8-113">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `int` values.</span></span>  
  
[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]  

> [!NOTE] 
> <span data-ttu-id="f46a8-114">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="f46a8-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="f46a8-115">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="f46a8-115">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="f46a8-116">Начиная с C# 7.0 было добавлено несколько возможностей для повышения удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="f46a8-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="f46a8-117">В C# 7.0 поддерживается использование символа подчеркивания (`_`) в качестве разделителя цифр.</span><span class="sxs-lookup"><span data-stu-id="f46a8-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="f46a8-118">В C# 7.2 поддерживается использование `_` (после префикса) в качестве разделителя для двоичного или шестнадцатеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="f46a8-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="f46a8-119">Десятичный литерал не может начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="f46a8-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="f46a8-120">Ниже приведено несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="f46a8-120">Some examples are shown below.</span></span>

[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]  
 
 <span data-ttu-id="f46a8-121">Целочисленные литералы могут содержать суффикс, обозначающий тип, несмотря на то, что для обозначения типа `int` суффикс не предусмотрен.</span><span class="sxs-lookup"><span data-stu-id="f46a8-121">Integer literals can also include a suffix that denotes the type, although there is no suffix that denotes the `int` type.</span></span> <span data-ttu-id="f46a8-122">Если целочисленный литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение:</span><span class="sxs-lookup"><span data-stu-id="f46a8-122">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. `int`
2. [<span data-ttu-id="f46a8-123">uint</span><span class="sxs-lookup"><span data-stu-id="f46a8-123">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="f46a8-124">long</span><span class="sxs-lookup"><span data-stu-id="f46a8-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="f46a8-125">ulong</span><span class="sxs-lookup"><span data-stu-id="f46a8-125">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
 
<span data-ttu-id="f46a8-126">В этих примерах литерал 90946 имеет тип `int`.</span><span class="sxs-lookup"><span data-stu-id="f46a8-126">In these examples, the literal 90946 is of type `int`.</span></span>
  
## <a name="conversions"></a><span data-ttu-id="f46a8-127">Преобразования</span><span class="sxs-lookup"><span data-stu-id="f46a8-127">Conversions</span></span>  
 <span data-ttu-id="f46a8-128">Существует предопределенное неявное преобразование типа `int` в тип [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="f46a8-128">There is a predefined implicit conversion from `int` to [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="f46a8-129">Например:</span><span class="sxs-lookup"><span data-stu-id="f46a8-129">For example:</span></span>  
  
```csharp  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 <span data-ttu-id="f46a8-130">Существует предопределенное неявное преобразование типа [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) или [char](../../../csharp/language-reference/keywords/char.md) в `int`.</span><span class="sxs-lookup"><span data-stu-id="f46a8-130">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `int`.</span></span> <span data-ttu-id="f46a8-131">Например, следующий оператор назначения вызывает ошибку компиляции без приведения:</span><span class="sxs-lookup"><span data-stu-id="f46a8-131">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 <span data-ttu-id="f46a8-132">Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `int` не существует.</span><span class="sxs-lookup"><span data-stu-id="f46a8-132">Notice also that there is no implicit conversion from floating-point types to `int`.</span></span> <span data-ttu-id="f46a8-133">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="f46a8-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 <span data-ttu-id="f46a8-134">Дополнительные сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="f46a8-134">For more information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f46a8-135">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f46a8-135">C# Language Specification</span></span>  

<span data-ttu-id="f46a8-136">Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="f46a8-136">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="f46a8-137">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="f46a8-137">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f46a8-138">См. также</span><span class="sxs-lookup"><span data-stu-id="f46a8-138">See also</span></span>

- <xref:System.Int32>
- [<span data-ttu-id="f46a8-139">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f46a8-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="f46a8-140">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f46a8-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f46a8-141">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f46a8-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="f46a8-142">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="f46a8-142">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)
- [<span data-ttu-id="f46a8-143">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="f46a8-143">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="f46a8-144">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="f46a8-144">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="f46a8-145">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="f46a8-145">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
