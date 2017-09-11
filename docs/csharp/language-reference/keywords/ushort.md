---
title: "ushort (справочник по C#)"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ushort
- ushort_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2b067a2ffd0fbffe06dc5c9f2a9910c9563eec4b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="ushort-c-reference"></a><span data-ttu-id="999d0-102">ushort (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="999d0-102">ushort (C# Reference)</span></span>

<span data-ttu-id="999d0-103">Ключевое слово `ushort` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="999d0-103">The `ushort` keyword indicates an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="999d0-104">Тип</span><span class="sxs-lookup"><span data-stu-id="999d0-104">Type</span></span>|<span data-ttu-id="999d0-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="999d0-105">Range</span></span>|<span data-ttu-id="999d0-106">Размер</span><span class="sxs-lookup"><span data-stu-id="999d0-106">Size</span></span>|<span data-ttu-id="999d0-107">Тип платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="999d0-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ushort`|<span data-ttu-id="999d0-108">От 0 до 65 535</span><span class="sxs-lookup"><span data-stu-id="999d0-108">0 to 65,535</span></span>|<span data-ttu-id="999d0-109">16-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="999d0-109">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="999d0-110">Литералы</span><span class="sxs-lookup"><span data-stu-id="999d0-110">Literals</span></span>  

<span data-ttu-id="999d0-111">Переменную `ushort` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="999d0-111">You can declare and initialize a `ushort` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="999d0-112">Если целочисленный литерал выходит за пределы диапазона `ushort` (то есть если он меньше <xref:System.UInt16.MinValue?displayProperty=fullName> или больше <xref:System.UInt16.MaxValue?displayProperty=fullName>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="999d0-112">If the integer literal is outside the range of `ushort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=fullName> or greater than <xref:System.UInt16.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span>

<span data-ttu-id="999d0-113">В следующем примере целые числа, равные 65 034 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, неявно преобразуются из типа [int](../../../csharp/language-reference/keywords/int.md) в значения `ushort`.</span><span class="sxs-lookup"><span data-stu-id="999d0-113">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `ushort` values.</span></span>    
  
<span data-ttu-id="999d0-114">[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]</span><span class="sxs-lookup"><span data-stu-id="999d0-114">[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="999d0-115">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="999d0-115">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="999d0-116">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="999d0-116">Decimal literals have no prefix.</span></span>

<span data-ttu-id="999d0-117">Начиная с версии C# 7, для повышения удобочитаемости в качестве разделителя разрядов можно также использовать символ подчеркивания (`_`), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="999d0-117">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="999d0-118">[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]</span><span class="sxs-lookup"><span data-stu-id="999d0-118">[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]</span></span>  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="999d0-119">Разрешение перегрузки компилятора</span><span class="sxs-lookup"><span data-stu-id="999d0-119">Compiler overload resolution</span></span>
  
 <span data-ttu-id="999d0-120">При вызове перегруженных методов необходимо использовать приведение типов.</span><span class="sxs-lookup"><span data-stu-id="999d0-120">A cast must be used when you call overloaded methods.</span></span> <span data-ttu-id="999d0-121">Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `ushort` и [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="999d0-121">Consider, for example, the following overloaded methods that use `ushort` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ushort s) {}  
```  
 
 <span data-ttu-id="999d0-122">Использование приведения типа `ushort` гарантирует вызов метода правильного типа, например:</span><span class="sxs-lookup"><span data-stu-id="999d0-122">Using the `ushort` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
// Calls the method with the int parameter:  
SampleMethod(5);  
// Calls the method with the ushort parameter:  
SampleMethod((ushort)5);    
```  
  
## <a name="conversions"></a><span data-ttu-id="999d0-123">Преобразования</span><span class="sxs-lookup"><span data-stu-id="999d0-123">Conversions</span></span>  
 <span data-ttu-id="999d0-124">Существует предопределенное преобразование типа `ushort` в типы [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="999d0-124">There is a predefined implicit conversion from `ushort` to [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="999d0-125">Существует предопределенное неявное преобразование типа [byte](../../../csharp/language-reference/keywords/byte.md) или [char](../../../csharp/language-reference/keywords/char.md) в тип `ushort`.</span><span class="sxs-lookup"><span data-stu-id="999d0-125">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md) or [char](../../../csharp/language-reference/keywords/char.md) to `ushort`.</span></span> <span data-ttu-id="999d0-126">В противном случае для выполнения явного преобразования следует использовать приведение.</span><span class="sxs-lookup"><span data-stu-id="999d0-126">Otherwise a cast must be used to perform an explicit conversion.</span></span> <span data-ttu-id="999d0-127">Рассмотрим, например, следующие две переменные `x` и `y` типа `ushort`:</span><span class="sxs-lookup"><span data-stu-id="999d0-127">Consider, for example, the following two `ushort` variables `x` and `y`:</span></span>  
  
```csharp 
ushort x = 5, y = 12;  
```  
  
 <span data-ttu-id="999d0-128">Следующая инструкция назначения приведет к ошибке компиляции, потому что арифметическое выражение, расположенное справа от оператора назначения, по умолчанию оценивается как имеющее тип `int`.</span><span class="sxs-lookup"><span data-stu-id="999d0-128">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to `int` by default.</span></span>  
  
```csharp  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 <span data-ttu-id="999d0-129">Для устранения этой проблемы используйте приведение:</span><span class="sxs-lookup"><span data-stu-id="999d0-129">To fix this problem, use a cast:</span></span>  
  
```csharp 
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 <span data-ttu-id="999d0-130">Тем не менее можно использовать следующие инструкции, в которых переменная назначения имеет такой же или больший размер при хранении:</span><span class="sxs-lookup"><span data-stu-id="999d0-130">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="999d0-131">Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `ushort` не существует.</span><span class="sxs-lookup"><span data-stu-id="999d0-131">Notice also that there is no implicit conversion from floating-point types to `ushort`.</span></span> <span data-ttu-id="999d0-132">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="999d0-132">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 <span data-ttu-id="999d0-133">Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="999d0-133">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="999d0-134">Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="999d0-134">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="999d0-135">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="999d0-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="999d0-136">См. также</span><span class="sxs-lookup"><span data-stu-id="999d0-136">See Also</span></span>  
 <span data-ttu-id="999d0-137"><xref:System.UInt16></span><span class="sxs-lookup"><span data-stu-id="999d0-137"><xref:System.UInt16></span></span>   
 <span data-ttu-id="999d0-138">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="999d0-138">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="999d0-139">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="999d0-139">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="999d0-140">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="999d0-140">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="999d0-141">[Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="999d0-141">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="999d0-142">[Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="999d0-142">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="999d0-143">[Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="999d0-143">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="999d0-144">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="999d0-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

