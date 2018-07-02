---
title: sbyte (справочник по C#)
ms.date: 03/14/2017
f1_keywords:
- sbyte_CSharpKeyword
- sbyte
helpviewer_keywords:
- sbyte keyword [C#]
ms.assetid: 1a9c7b48-73d1-4d33-b485-c4faf0a816bc
ms.openlocfilehash: 94968ed61fced9716112740613a4e3a86622e2e3
ms.sourcegitcommit: f9e38d31288fe5962e6be5b0cc286da633482873
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37028062"
---
# <a name="sbyte-c-reference"></a><span data-ttu-id="17db3-102">sbyte (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="17db3-102">sbyte (C# Reference)</span></span>

<span data-ttu-id="17db3-103">`sbyte` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="17db3-103">`sbyte` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="17db3-104">Тип</span><span class="sxs-lookup"><span data-stu-id="17db3-104">Type</span></span>|<span data-ttu-id="17db3-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="17db3-105">Range</span></span>|<span data-ttu-id="17db3-106">Размер</span><span class="sxs-lookup"><span data-stu-id="17db3-106">Size</span></span>|<span data-ttu-id="17db3-107">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="17db3-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`sbyte`|<span data-ttu-id="17db3-108">От -128 до 127</span><span class="sxs-lookup"><span data-stu-id="17db3-108">-128 to 127</span></span>|<span data-ttu-id="17db3-109">8-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="17db3-109">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="17db3-110">Литералы</span><span class="sxs-lookup"><span data-stu-id="17db3-110">Literals</span></span>  

<span data-ttu-id="17db3-111">Переменную `sbyte` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7.0) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="17db3-111">You can declare and initialize an `sbyte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> 

<span data-ttu-id="17db3-112">В следующем примере целые числа, равные -102 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, неявно преобразуются из типа [int](../../../csharp/language-reference/keywords/int.md) в значения `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="17db3-112">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are converted from [int](../../../csharp/language-reference/keywords/int.md) to `sbyte` values.</span></span>    
  
[!code-csharp[SByte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByte)]  

> [!NOTE] 
> <span data-ttu-id="17db3-113">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="17db3-113">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="17db3-114">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="17db3-114">Decimal literals have no prefix.</span></span>

<span data-ttu-id="17db3-115">Начиная с C# 7.0 было добавлено несколько возможностей для повышения удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="17db3-115">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="17db3-116">В C# 7.0 поддерживается использование символа подчеркивания (`_`) в качестве разделителя цифр.</span><span class="sxs-lookup"><span data-stu-id="17db3-116">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="17db3-117">В C# 7.2 поддерживается использование `_` (после префикса) в качестве разделителя для двоичного или шестнадцатеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="17db3-117">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="17db3-118">Десятичный литерал не может начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="17db3-118">A decimal literal isn't permitted to have a leading underscore.</span></span>

 <span data-ttu-id="17db3-119">Ниже приведено несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="17db3-119">Some examples are shown below.</span></span>

[!code-csharp[SByteSeparator](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByteS)]  

<span data-ttu-id="17db3-120">Если целочисленный литерал выходит за пределы диапазона `sbyte` (то есть, если он меньше <xref:System.SByte.MinValue?displayProperty=nameWithType> или больше <xref:System.SByte.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="17db3-120">If the integer literal is outside the range of `sbyte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="17db3-121">Если целочисленный литерал не имеет суффикса, его тип — первый из этих типов, в котором может быть представлено его значение: [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md).</span><span class="sxs-lookup"><span data-stu-id="17db3-121">When an integer literal has no suffix, its type is the first of these types in which its value can be represented: [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md).</span></span> <span data-ttu-id="17db3-122">Это означает, что в данном примере числовые литералы `0x9A` и `0b10011010` интерпретируются как 32-разрядные целые числа со знаком, имеющие значение 156, превышающее <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="17db3-122">This means that, in this example, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="17db3-123">В связи с этим необходимо использовать оператор приведения, а назначение должно происходить в контексте [unchecked](unchecked.md).</span><span class="sxs-lookup"><span data-stu-id="17db3-123">Because of this, the casting operator is needed, and the assignment must occur in an [unchecked](unchecked.md) context.</span></span> 

## <a name="compiler-overload-resolution"></a><span data-ttu-id="17db3-124">Разрешение перегрузки компилятора</span><span class="sxs-lookup"><span data-stu-id="17db3-124">Compiler overload resolution</span></span>

 <span data-ttu-id="17db3-125">При вызове перегруженных методов необходимо использовать приведение типов.</span><span class="sxs-lookup"><span data-stu-id="17db3-125">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="17db3-126">Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `sbyte` и [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="17db3-126">Consider, for example, the following overloaded methods that use `sbyte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(sbyte b) {}  
```  
  
 <span data-ttu-id="17db3-127">Использование приведения типа `sbyte` гарантирует вызов метода правильного типа, например:</span><span class="sxs-lookup"><span data-stu-id="17db3-127">Using the `sbyte` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp 
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the sbyte parameter:  
SampleMethod((sbyte)5);  
```  
  
## <a name="conversions"></a><span data-ttu-id="17db3-128">Преобразования</span><span class="sxs-lookup"><span data-stu-id="17db3-128">Conversions</span></span>  
 <span data-ttu-id="17db3-129">Существует предопределенное преобразование типа `sbyte` в типы [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="17db3-129">There is a predefined implicit conversion from `sbyte` to [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="17db3-130">Нельзя неявно преобразовать не являющиеся литералами числовые типы большего размера при хранении в тип `sbyte` (сведения о размере целочисленных типов при хранении см. в разделе [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)).</span><span class="sxs-lookup"><span data-stu-id="17db3-130">You cannot implicitly convert nonliteral numeric types of larger storage size to `sbyte` (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="17db3-131">Рассмотрим, например, следующие две переменные `x` и `y` типа `sbyte`:</span><span class="sxs-lookup"><span data-stu-id="17db3-131">Consider, for example, the following two `sbyte` variables `x` and `y`:</span></span>  
  
```csharp  
sbyte x = 10, y = 20;  
```  
  
 <span data-ttu-id="17db3-132">Следующая инструкция назначения приведет к ошибке компиляции, потому что арифметическое выражение, расположенное справа от оператора назначения, по умолчанию оценивается как имеющее тип [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="17db3-132">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to [int](../../../csharp/language-reference/keywords/int.md) by default.</span></span>  
  
```csharp  
sbyte z = x + y;   // Error: conversion from int to sbyte  
```  
  
 <span data-ttu-id="17db3-133">Для устранения этой проблемы нужно привести тип этого выражения, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="17db3-133">To fix this problem, cast the expression as in the following example:</span></span>  
  
```csharp  
sbyte z = (sbyte)(x + y);   // OK: explicit conversion  
```  
  
 <span data-ttu-id="17db3-134">Тем не менее можно использовать следующие инструкции, в которых переменная назначения имеет такой же или больший размер при хранении:</span><span class="sxs-lookup"><span data-stu-id="17db3-134">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
sbyte x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="17db3-135">Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `sbyte` не существует.</span><span class="sxs-lookup"><span data-stu-id="17db3-135">Notice also that there is no implicit conversion from floating-point types to `sbyte`.</span></span> <span data-ttu-id="17db3-136">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="17db3-136">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
sbyte x = 3.0;         // Error: no implicit conversion from double  
sbyte y = (sbyte)3.0;  // OK: explicit conversion  
```  
  
 <span data-ttu-id="17db3-137">Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="17db3-137">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="17db3-138">Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="17db3-138">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="17db3-139">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="17db3-139">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="17db3-140">См. также</span><span class="sxs-lookup"><span data-stu-id="17db3-140">See Also</span></span>  
 <xref:System.SByte>  
 [<span data-ttu-id="17db3-141">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="17db3-141">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="17db3-142">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="17db3-142">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="17db3-143">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="17db3-143">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="17db3-144">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="17db3-144">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="17db3-145">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="17db3-145">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="17db3-146">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="17db3-146">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="17db3-147">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="17db3-147">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
