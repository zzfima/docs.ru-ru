---
title: "uint (справочник по C#)"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- uint
- uint_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- uint keyword [C#]
ms.assetid: e93e42c6-ec72-4b0b-89df-2fd8d36f7a7b
caps.latest.revision: 18
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
ms.openlocfilehash: 4342c08ab536f45a2e3b5fa6fe94839436600a4a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="uint-c-reference"></a><span data-ttu-id="c63cb-102">uint (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c63cb-102">uint (C# Reference)</span></span>

<span data-ttu-id="c63cb-103">Ключевое слово `uint` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="c63cb-103">The `uint` keyword signifies an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="c63cb-104">Тип</span><span class="sxs-lookup"><span data-stu-id="c63cb-104">Type</span></span>|<span data-ttu-id="c63cb-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="c63cb-105">Range</span></span>|<span data-ttu-id="c63cb-106">Размер</span><span class="sxs-lookup"><span data-stu-id="c63cb-106">Size</span></span>|<span data-ttu-id="c63cb-107">Тип платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c63cb-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`uint`|<span data-ttu-id="c63cb-108">От 0 до 4 294 967 295</span><span class="sxs-lookup"><span data-stu-id="c63cb-108">0 to 4,294,967,295</span></span>|<span data-ttu-id="c63cb-109">32-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="c63cb-109">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=fullName>|  
  
 <span data-ttu-id="c63cb-110">**Примечание.** Тип `uint` не совместим с CLS.</span><span class="sxs-lookup"><span data-stu-id="c63cb-110">**Note** The `uint` type is not CLS-compliant.</span></span> <span data-ttu-id="c63cb-111">По возможности используйте `int`.</span><span class="sxs-lookup"><span data-stu-id="c63cb-111">Use `int` whenever possible.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="c63cb-112">Литералы</span><span class="sxs-lookup"><span data-stu-id="c63cb-112">Literals</span></span>  

<span data-ttu-id="c63cb-113">Переменную `uint` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="c63cb-113">You can declare and initialize a `uint` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="c63cb-114">Если целочисленный литерал выходит за пределы диапазона `uint` (то есть если он меньше <xref:System.UInt32.MinValue?displayProperty=fullName> или больше <xref:System.UInt32.MaxValue?displayProperty=fullName>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="c63cb-114">If the integer literal is outside the range of `uint` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=fullName> or greater than <xref:System.UInt32.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span>

<span data-ttu-id="c63cb-115">В следующем примере целые числа, равные 3 000 000 000 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `uint`.</span><span class="sxs-lookup"><span data-stu-id="c63cb-115">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `uint` values.</span></span>  
  
<span data-ttu-id="c63cb-116">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]</span><span class="sxs-lookup"><span data-stu-id="c63cb-116">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="c63cb-117">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="c63cb-117">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="c63cb-118">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="c63cb-118">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="c63cb-119">Начиная с версии C# 7, для повышения удобочитаемости в качестве разделителя разрядов можно также использовать символ подчеркивания (`_`), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c63cb-119">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="c63cb-120">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]</span><span class="sxs-lookup"><span data-stu-id="c63cb-120">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]</span></span>  
 
 <span data-ttu-id="c63cb-121">Целочисленные литералы могут также содержать суффикс, обозначающий тип.</span><span class="sxs-lookup"><span data-stu-id="c63cb-121">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="c63cb-122">Суффикс `U` или "u" обозначает либо `uint`, либо `ulong` в зависимости от числового значения литерала.</span><span class="sxs-lookup"><span data-stu-id="c63cb-122">The suffix `U` or 'u' denotes either a `uint` or a `ulong`, depending on the numeric value of the literal.</span></span> <span data-ttu-id="c63cb-123">В следующем примере суффикс `u` используется для обозначения целого числа без знака обоих типов.</span><span class="sxs-lookup"><span data-stu-id="c63cb-123">The following example uses the `u` suffix to denote an unsigned integer of both types.</span></span> <span data-ttu-id="c63cb-124">Обратите внимание, что первый литерал имеет тип `uint`, поскольку его значение меньше <xref:System.UInt32.MaxValue?displayProperty=fullName>, а второй имеет тип `ulong`, поскольку его значение больше <xref:System.UInt32.MaxValue?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="c63cb-124">Note that the first literal is a `uint` because its value is less than <xref:System.UInt32.MaxValue?displayProperty=fullName>, while the second is a `ulong` because its value is greater than <xref:System.UInt32.MaxValue?displayProperty=fullName>.</span></span>

<span data-ttu-id="c63cb-125">[!code-cs[usuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c63cb-125">[!code-cs[usuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]</span></span>  
 
<span data-ttu-id="c63cb-126">Если целочисленный литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение:</span><span class="sxs-lookup"><span data-stu-id="c63cb-126">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="c63cb-127">int</span><span class="sxs-lookup"><span data-stu-id="c63cb-127">int</span></span>](int.md)
2. `uint`
3. [<span data-ttu-id="c63cb-128">long</span><span class="sxs-lookup"><span data-stu-id="c63cb-128">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="c63cb-129">ulong</span><span class="sxs-lookup"><span data-stu-id="c63cb-129">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
  
## <a name="conversions"></a><span data-ttu-id="c63cb-130">Преобразования</span><span class="sxs-lookup"><span data-stu-id="c63cb-130">Conversions</span></span>  
 <span data-ttu-id="c63cb-131">Существует предопределенное неявное преобразование типа `uint` в тип [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="c63cb-131">There is a predefined implicit conversion from `uint` to [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="c63cb-132">Пример:</span><span class="sxs-lookup"><span data-stu-id="c63cb-132">For example:</span></span>  
  
```csharp  
float myFloat = 4294967290;   // OK: implicit conversion to float  
```  
  
 <span data-ttu-id="c63cb-133">Существует предопределенное неявное преобразование типа [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) или [char](../../../csharp/language-reference/keywords/char.md) в тип `uint`.</span><span class="sxs-lookup"><span data-stu-id="c63cb-133">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `uint`.</span></span> <span data-ttu-id="c63cb-134">В противном случае необходимо использовать приведение.</span><span class="sxs-lookup"><span data-stu-id="c63cb-134">Otherwise you must use a cast.</span></span> <span data-ttu-id="c63cb-135">Например, следующий оператор назначения вызывает ошибку компиляции без приведения:</span><span class="sxs-lookup"><span data-stu-id="c63cb-135">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
// Error -- no implicit conversion from long:  
uint uInt1 = aLong;   
// OK -- explicit conversion:  
uint uInt2 = (uint)aLong;  
```  
  
 <span data-ttu-id="c63cb-136">Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `uint` не существует.</span><span class="sxs-lookup"><span data-stu-id="c63cb-136">Notice also that there is no implicit conversion from floating-point types to `uint`.</span></span> <span data-ttu-id="c63cb-137">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="c63cb-137">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
uint x = 3.0;  
// OK -- explicit conversion:  
uint y = (uint)3.0;   
```  
  
 <span data-ttu-id="c63cb-138">Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="c63cb-138">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="c63cb-139">Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="c63cb-139">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c63cb-140">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c63cb-140">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c63cb-141">См. также</span><span class="sxs-lookup"><span data-stu-id="c63cb-141">See Also</span></span>  
 <span data-ttu-id="c63cb-142"><xref:System.UInt32></span><span class="sxs-lookup"><span data-stu-id="c63cb-142"><xref:System.UInt32></span></span>   
 <span data-ttu-id="c63cb-143">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c63cb-143">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c63cb-144">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c63cb-144">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c63cb-145">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="c63cb-145">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="c63cb-146">[Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="c63cb-146">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="c63cb-147">[Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="c63cb-147">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="c63cb-148">[Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="c63cb-148">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="c63cb-149">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="c63cb-149">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

