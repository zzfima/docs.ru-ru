---
title: "ulong (справочник по C#)"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ulong_CSharpKeyword
- ulong
dev_langs:
- CSharp
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
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
ms.openlocfilehash: c2da253e4da7a5d6cfa71116e4fcba7816441e92
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="ulong-c-reference"></a><span data-ttu-id="941a9-102">ulong (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="941a9-102">ulong (C# Reference)</span></span>

<span data-ttu-id="941a9-103">Ключевое слово `ulong` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="941a9-103">The `ulong` keyword denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="941a9-104">Тип</span><span class="sxs-lookup"><span data-stu-id="941a9-104">Type</span></span>|<span data-ttu-id="941a9-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="941a9-105">Range</span></span>|<span data-ttu-id="941a9-106">Размер</span><span class="sxs-lookup"><span data-stu-id="941a9-106">Size</span></span>|<span data-ttu-id="941a9-107">Тип платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="941a9-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ulong`|<span data-ttu-id="941a9-108">От 0 до 18 446 744 073 709 551 615</span><span class="sxs-lookup"><span data-stu-id="941a9-108">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="941a9-109">64-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="941a9-109">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="941a9-110">Литералы</span><span class="sxs-lookup"><span data-stu-id="941a9-110">Literals</span></span>  

<span data-ttu-id="941a9-111">Переменную `ulong` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="941a9-111">You can declare and initialize a `ulong` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="941a9-112">Если целочисленный литерал выходит за пределы диапазона `ulong` (то есть если он меньше <xref:System.UInt64.MinValue?displayProperty=fullName> или больше <xref:System.UInt64.MaxValue?displayProperty=fullName>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="941a9-112">If the integer literal is outside the range of `ulong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=fullName> or greater than <xref:System.UInt64.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span> 

<span data-ttu-id="941a9-113">В следующем примере целые числа, равные 7 934 076 125 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `ulong`.</span><span class="sxs-lookup"><span data-stu-id="941a9-113">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ulong` values.</span></span>  
  
<span data-ttu-id="941a9-114">[!code-cs[ulong](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]</span><span class="sxs-lookup"><span data-stu-id="941a9-114">[!code-cs[ulong](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="941a9-115">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="941a9-115">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="941a9-116">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="941a9-116">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="941a9-117">Начиная с версии C# 7, для повышения удобочитаемости в качестве разделителя разрядов можно также использовать символ подчеркивания (`_`), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="941a9-117">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="941a9-118">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span><span class="sxs-lookup"><span data-stu-id="941a9-118">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span></span>  
 
 <span data-ttu-id="941a9-119">Целочисленные литералы могут также содержать суффикс, обозначающий тип.</span><span class="sxs-lookup"><span data-stu-id="941a9-119">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="941a9-120">Суффикс `UL` или `ul` однозначно идентифицирует числовой литерал как значение `ulong`.</span><span class="sxs-lookup"><span data-stu-id="941a9-120">The suffix `UL` or `ul` unambiguously identifies a numeric literal as a `ulong` value.</span></span> <span data-ttu-id="941a9-121">Суффикс `L` обозначает `ulong`, если значение литерала превышает <xref:System.Int64.MaxValue?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="941a9-121">The `L` suffix denotes a `ulong` if the literal value exceeds <xref:System.Int64.MaxValue?displayProperty=fullName>.</span></span> <span data-ttu-id="941a9-122">Суффикс `U` или `u` обозначает `ulong`, если значение литерала превышает <xref:System.UInt32.MaxValue?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="941a9-122">And the `U` or `u` suffix denotes a `ulong` if the literal value exceeds <xref:System.UInt32.MaxValue?displayProperty=fullName>.</span></span> <span data-ttu-id="941a9-123">В следующем примере суффикс `ul` используется для обозначения длинного целого числа:</span><span class="sxs-lookup"><span data-stu-id="941a9-123">The following example uses the `ul` suffix to denote a long integer:</span></span>
 
<span data-ttu-id="941a9-124">[!code-cs[ulsuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="941a9-124">[!code-cs[ulsuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]</span></span>

<span data-ttu-id="941a9-125">Если целочисленный литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение:</span><span class="sxs-lookup"><span data-stu-id="941a9-125">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="941a9-126">int</span><span class="sxs-lookup"><span data-stu-id="941a9-126">int</span></span>](int.md)
2. [<span data-ttu-id="941a9-127">uint</span><span class="sxs-lookup"><span data-stu-id="941a9-127">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="941a9-128">long</span><span class="sxs-lookup"><span data-stu-id="941a9-128">long</span></span>](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a><span data-ttu-id="941a9-129">Разрешение перегрузки компилятора</span><span class="sxs-lookup"><span data-stu-id="941a9-129">Compiler overload resolution</span></span>
  
 <span data-ttu-id="941a9-130">Обычно суффикс используется для вызова перегруженных методов.</span><span class="sxs-lookup"><span data-stu-id="941a9-130">A common use of the suffix is with calling overloaded methods.</span></span> <span data-ttu-id="941a9-131">Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `ulong` и [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="941a9-131">Consider, for example, the following overloaded methods that use `ulong` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ulong l) {}  
```  
  
 <span data-ttu-id="941a9-132">Использование суффикса с параметром `ulong` гарантирует вызов метода правильного типа, например:</span><span class="sxs-lookup"><span data-stu-id="941a9-132">Using a suffix with the `ulong` parameter guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5UL);  // Calling the method with the ulong parameter  
```  
  
## <a name="conversions"></a><span data-ttu-id="941a9-133">Преобразования</span><span class="sxs-lookup"><span data-stu-id="941a9-133">Conversions</span></span>  
 <span data-ttu-id="941a9-134">Существует предопределенное неявное преобразование типа `ulong` в тип [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="941a9-134">There is a predefined implicit conversion from `ulong` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="941a9-135">Неявного преобразования типа `ulong` в любой целочисленный тип не существует.</span><span class="sxs-lookup"><span data-stu-id="941a9-135">There is no implicit conversion from `ulong` to any integral type.</span></span> <span data-ttu-id="941a9-136">Например, следующий оператор вызывает ошибку компиляции без явного приведения:</span><span class="sxs-lookup"><span data-stu-id="941a9-136">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
long long1 = 8UL;   // Error: no implicit conversion from ulong  
```  
  
 <span data-ttu-id="941a9-137">Существует предопределенное неявное преобразование типа [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md) или [char](../../../csharp/language-reference/keywords/char.md) в тип `ulong`.</span><span class="sxs-lookup"><span data-stu-id="941a9-137">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `ulong`.</span></span>  
  
 <span data-ttu-id="941a9-138">Кроме того, неявного преобразования типов с плавающей запятой в тип `ulong` не существует.</span><span class="sxs-lookup"><span data-stu-id="941a9-138">Also, there is no implicit conversion from floating-point types to `ulong`.</span></span> <span data-ttu-id="941a9-139">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="941a9-139">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ulong x = 3.0;  
// OK -- explicit conversion:  
ulong y = (ulong)3.0;    
```  
  
 <span data-ttu-id="941a9-140">Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="941a9-140">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="941a9-141">Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="941a9-141">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="941a9-142">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="941a9-142">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="941a9-143">См. также</span><span class="sxs-lookup"><span data-stu-id="941a9-143">See Also</span></span>  
 <span data-ttu-id="941a9-144"><xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="941a9-144"><xref:System.UInt64></span></span>   
 <span data-ttu-id="941a9-145">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="941a9-145">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="941a9-146">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="941a9-146">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="941a9-147">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="941a9-147">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="941a9-148">[Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="941a9-148">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="941a9-149">[Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="941a9-149">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="941a9-150">[Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="941a9-150">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="941a9-151">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="941a9-151">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

