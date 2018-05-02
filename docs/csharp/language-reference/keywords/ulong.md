---
title: ulong (справочник по C#)
ms.date: 03/14/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 049d1cc4b30e16535f20cee8e0ad80e5c80b4a49
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="ulong-c-reference"></a><span data-ttu-id="ebccf-102">ulong (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ebccf-102">ulong (C# Reference)</span></span>

<span data-ttu-id="ebccf-103">Ключевое слово `ulong` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="ebccf-103">The `ulong` keyword denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="ebccf-104">Тип</span><span class="sxs-lookup"><span data-stu-id="ebccf-104">Type</span></span>|<span data-ttu-id="ebccf-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="ebccf-105">Range</span></span>|<span data-ttu-id="ebccf-106">Размер</span><span class="sxs-lookup"><span data-stu-id="ebccf-106">Size</span></span>|<span data-ttu-id="ebccf-107">Тип платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ebccf-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ulong`|<span data-ttu-id="ebccf-108">От 0 до 18 446 744 073 709 551 615</span><span class="sxs-lookup"><span data-stu-id="ebccf-108">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="ebccf-109">64-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="ebccf-109">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="ebccf-110">Литералы</span><span class="sxs-lookup"><span data-stu-id="ebccf-110">Literals</span></span>  

<span data-ttu-id="ebccf-111">Переменную `ulong` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7.0) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="ebccf-111">You can declare and initialize a `ulong` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="ebccf-112">Если целочисленный литерал выходит за пределы диапазона `ulong` (то есть если он меньше <xref:System.UInt64.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="ebccf-112">If the integer literal is outside the range of `ulong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="ebccf-113">В следующем примере целые числа, равные 7 934 076 125 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `ulong`.</span><span class="sxs-lookup"><span data-stu-id="ebccf-113">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ulong` values.</span></span>  
  
[!code-csharp[ulong](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]  

> [!NOTE] 
> <span data-ttu-id="ebccf-114">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="ebccf-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="ebccf-115">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="ebccf-115">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="ebccf-116">Начиная с C# 7.0 было добавлено несколько возможностей для повышения удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="ebccf-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="ebccf-117">В C# 7.0 поддерживается использование символа подчеркивания (`_`) в качестве разделителя цифр.</span><span class="sxs-lookup"><span data-stu-id="ebccf-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="ebccf-118">В C# 7.2 поддерживается использование `_` (после префикса) в качестве разделителя для двоичного или шестнадцатеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="ebccf-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="ebccf-119">Десятичный литерал не может начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="ebccf-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="ebccf-120">Ниже приведено несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="ebccf-120">Some examples are shown below.</span></span>

[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]  
 
 <span data-ttu-id="ebccf-121">Целочисленные литералы могут также содержать суффикс, обозначающий тип.</span><span class="sxs-lookup"><span data-stu-id="ebccf-121">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="ebccf-122">Суффикс `UL` или `ul` однозначно идентифицирует числовой литерал как значение `ulong`.</span><span class="sxs-lookup"><span data-stu-id="ebccf-122">The suffix `UL` or `ul` unambiguously identifies a numeric literal as a `ulong` value.</span></span> <span data-ttu-id="ebccf-123">Суффикс `L` обозначает `ulong`, если значение литерала превышает <xref:System.Int64.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ebccf-123">The `L` suffix denotes a `ulong` if the literal value exceeds <xref:System.Int64.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ebccf-124">Суффикс `U` или `u` обозначает `ulong`, если значение литерала превышает <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ebccf-124">And the `U` or `u` suffix denotes a `ulong` if the literal value exceeds <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ebccf-125">В следующем примере суффикс `ul` используется для обозначения длинного целого числа:</span><span class="sxs-lookup"><span data-stu-id="ebccf-125">The following example uses the `ul` suffix to denote a long integer:</span></span>
 
[!code-csharp[ulsuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]

<span data-ttu-id="ebccf-126">Если целочисленный литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение:</span><span class="sxs-lookup"><span data-stu-id="ebccf-126">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="ebccf-127">int</span><span class="sxs-lookup"><span data-stu-id="ebccf-127">int</span></span>](int.md)
2. [<span data-ttu-id="ebccf-128">uint</span><span class="sxs-lookup"><span data-stu-id="ebccf-128">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="ebccf-129">long</span><span class="sxs-lookup"><span data-stu-id="ebccf-129">long</span></span>](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a><span data-ttu-id="ebccf-130">Разрешение перегрузки компилятора</span><span class="sxs-lookup"><span data-stu-id="ebccf-130">Compiler overload resolution</span></span>
  
 <span data-ttu-id="ebccf-131">Обычно суффикс используется для вызова перегруженных методов.</span><span class="sxs-lookup"><span data-stu-id="ebccf-131">A common use of the suffix is with calling overloaded methods.</span></span> <span data-ttu-id="ebccf-132">Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `ulong` и [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="ebccf-132">Consider, for example, the following overloaded methods that use `ulong` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ulong l) {}  
```  
  
 <span data-ttu-id="ebccf-133">Использование суффикса с параметром `ulong` гарантирует вызов метода правильного типа, например:</span><span class="sxs-lookup"><span data-stu-id="ebccf-133">Using a suffix with the `ulong` parameter guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5UL);  // Calling the method with the ulong parameter  
```  
  
## <a name="conversions"></a><span data-ttu-id="ebccf-134">Преобразования</span><span class="sxs-lookup"><span data-stu-id="ebccf-134">Conversions</span></span>  
 <span data-ttu-id="ebccf-135">Существует предопределенное неявное преобразование типа `ulong` в тип [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="ebccf-135">There is a predefined implicit conversion from `ulong` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="ebccf-136">Неявного преобразования типа `ulong` в любой целочисленный тип не существует.</span><span class="sxs-lookup"><span data-stu-id="ebccf-136">There is no implicit conversion from `ulong` to any integral type.</span></span> <span data-ttu-id="ebccf-137">Например, следующий оператор вызывает ошибку компиляции без явного приведения:</span><span class="sxs-lookup"><span data-stu-id="ebccf-137">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
long long1 = 8UL;   // Error: no implicit conversion from ulong  
```  
  
 <span data-ttu-id="ebccf-138">Существует предопределенное неявное преобразование типа [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md) или [char](../../../csharp/language-reference/keywords/char.md) в тип `ulong`.</span><span class="sxs-lookup"><span data-stu-id="ebccf-138">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `ulong`.</span></span>  
  
 <span data-ttu-id="ebccf-139">Кроме того, неявного преобразования типов с плавающей запятой в тип `ulong` не существует.</span><span class="sxs-lookup"><span data-stu-id="ebccf-139">Also, there is no implicit conversion from floating-point types to `ulong`.</span></span> <span data-ttu-id="ebccf-140">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="ebccf-140">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ulong x = 3.0;  
// OK -- explicit conversion:  
ulong y = (ulong)3.0;    
```  
  
 <span data-ttu-id="ebccf-141">Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="ebccf-141">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="ebccf-142">Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="ebccf-142">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ebccf-143">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ebccf-143">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ebccf-144">См. также</span><span class="sxs-lookup"><span data-stu-id="ebccf-144">See Also</span></span>  
 <xref:System.UInt64>  
 [<span data-ttu-id="ebccf-145">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ebccf-145">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ebccf-146">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ebccf-146">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ebccf-147">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="ebccf-147">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="ebccf-148">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="ebccf-148">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="ebccf-149">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="ebccf-149">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="ebccf-150">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="ebccf-150">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="ebccf-151">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="ebccf-151">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
