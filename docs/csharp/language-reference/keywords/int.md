---
title: "int (справочник по C#)"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- int_CSharpKeyword
- int
dev_langs:
- CSharp
helpviewer_keywords:
- int keyword [C#]
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
caps.latest.revision: 19
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
ms.sourcegitcommit: 935428cc9442a3e1d15eeb8942176c237bff4e22
ms.openlocfilehash: 6e87893bcd9800b61297e71b782028fec5116479
ms.contentlocale: ru-ru
ms.lasthandoff: 08/22/2017

---
# <a name="int-c-reference"></a><span data-ttu-id="6c24a-102">int (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6c24a-102">int (C# Reference)</span></span>

<span data-ttu-id="6c24a-103">`int` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="6c24a-103">`int` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="6c24a-104">Тип</span><span class="sxs-lookup"><span data-stu-id="6c24a-104">Type</span></span>|<span data-ttu-id="6c24a-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="6c24a-105">Range</span></span>|<span data-ttu-id="6c24a-106">Размер</span><span class="sxs-lookup"><span data-stu-id="6c24a-106">Size</span></span>|<span data-ttu-id="6c24a-107">Тип платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6c24a-107">.NET Framework type</span></span>|<span data-ttu-id="6c24a-108">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6c24a-108">Default Value</span></span>|  
|----------|-----------|----------|-------------------------|-------------------|  
|`int`|<span data-ttu-id="6c24a-109">От -2 147 483 648 до 2 147 483 647</span><span class="sxs-lookup"><span data-stu-id="6c24a-109">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="6c24a-110">32-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="6c24a-110">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=fullName>|<span data-ttu-id="6c24a-111">0</span><span class="sxs-lookup"><span data-stu-id="6c24a-111">0</span></span>|  
  
## <a name="literals"></a><span data-ttu-id="6c24a-112">Литералы</span><span class="sxs-lookup"><span data-stu-id="6c24a-112">Literals</span></span>  
 
<span data-ttu-id="6c24a-113">Переменную `int` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="6c24a-113">You can declare and initialize an `int` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="6c24a-114">Если целочисленный литерал выходит за пределы диапазона `int` (то есть если он меньше <xref:System.Int32.MinValue?displayProperty=fullName> или больше <xref:System.Int32.MaxValue?displayProperty=fullName>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="6c24a-114">If the integer literal is outside the range of `int` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=fullName> or greater than <xref:System.Int32.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span> 

<span data-ttu-id="6c24a-115">В следующем примере целые числа, равные 90 946 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `int`.</span><span class="sxs-lookup"><span data-stu-id="6c24a-115">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `int` values.</span></span>  
  
<span data-ttu-id="6c24a-116">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]</span><span class="sxs-lookup"><span data-stu-id="6c24a-116">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="6c24a-117">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="6c24a-117">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="6c24a-118">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="6c24a-118">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="6c24a-119">Начиная с версии C# 7, для повышения удобочитаемости в качестве разделителя разрядов можно также использовать символ подчеркивания (`_`), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6c24a-119">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="6c24a-120">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]</span><span class="sxs-lookup"><span data-stu-id="6c24a-120">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]</span></span>  
 
 <span data-ttu-id="6c24a-121">Целочисленные литералы могут содержать суффикс, обозначающий тип, несмотря на то, что для обозначения типа `int` суффикс не предусмотрен.</span><span class="sxs-lookup"><span data-stu-id="6c24a-121">Integer literals can also include a suffix that denotes the type, although there is no suffix that denotes the `int` type.</span></span> <span data-ttu-id="6c24a-122">Если целочисленный литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение:</span><span class="sxs-lookup"><span data-stu-id="6c24a-122">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. `int`
2. [<span data-ttu-id="6c24a-123">uint</span><span class="sxs-lookup"><span data-stu-id="6c24a-123">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="6c24a-124">long</span><span class="sxs-lookup"><span data-stu-id="6c24a-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="6c24a-125">ulong</span><span class="sxs-lookup"><span data-stu-id="6c24a-125">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
 
<span data-ttu-id="6c24a-126">В этих примерах литерал 90946 имеет тип `int`.</span><span class="sxs-lookup"><span data-stu-id="6c24a-126">In these examples, the literal 90946 is of type `int`.</span></span>
  
## <a name="conversions"></a><span data-ttu-id="6c24a-127">Преобразования</span><span class="sxs-lookup"><span data-stu-id="6c24a-127">Conversions</span></span>  
 <span data-ttu-id="6c24a-128">Существует предопределенное неявное преобразование типа `int` в тип [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="6c24a-128">There is a predefined implicit conversion from `int` to [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="6c24a-129">Пример:</span><span class="sxs-lookup"><span data-stu-id="6c24a-129">For example:</span></span>  
  
```csharp  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 <span data-ttu-id="6c24a-130">Существует предопределенное неявное преобразование типа [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) или [char](../../../csharp/language-reference/keywords/char.md) в `int`.</span><span class="sxs-lookup"><span data-stu-id="6c24a-130">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `int`.</span></span> <span data-ttu-id="6c24a-131">Например, следующий оператор назначения вызывает ошибку компиляции без приведения:</span><span class="sxs-lookup"><span data-stu-id="6c24a-131">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 <span data-ttu-id="6c24a-132">Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `int` не существует.</span><span class="sxs-lookup"><span data-stu-id="6c24a-132">Notice also that there is no implicit conversion from floating-point types to `int`.</span></span> <span data-ttu-id="6c24a-133">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="6c24a-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 <span data-ttu-id="6c24a-134">Дополнительные сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="6c24a-134">For more information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6c24a-135">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6c24a-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6c24a-136">См. также</span><span class="sxs-lookup"><span data-stu-id="6c24a-136">See Also</span></span>  
 <span data-ttu-id="6c24a-137"><xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="6c24a-137"><xref:System.Int32></span></span>   
 <span data-ttu-id="6c24a-138">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6c24a-138">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6c24a-139">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6c24a-139">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6c24a-140">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="6c24a-140">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="6c24a-141">[Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="6c24a-141">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="6c24a-142">[Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="6c24a-142">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="6c24a-143">[Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="6c24a-143">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="6c24a-144">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="6c24a-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

