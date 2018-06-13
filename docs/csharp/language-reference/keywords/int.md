---
title: int (справочник по C#)
ms.date: 03/14/2017
f1_keywords:
- int_CSharpKeyword
- int
helpviewer_keywords:
- int keyword [C#]
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
ms.openlocfilehash: c7d9bb0ee3d59ef3e0cf56d26e73a925fcfb4206
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275295"
---
# <a name="int-c-reference"></a><span data-ttu-id="e0727-102">int (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e0727-102">int (C# Reference)</span></span>

<span data-ttu-id="e0727-103">`int` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="e0727-103">`int` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="e0727-104">Тип</span><span class="sxs-lookup"><span data-stu-id="e0727-104">Type</span></span>|<span data-ttu-id="e0727-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="e0727-105">Range</span></span>|<span data-ttu-id="e0727-106">Размер</span><span class="sxs-lookup"><span data-stu-id="e0727-106">Size</span></span>|<span data-ttu-id="e0727-107">Тип платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e0727-107">.NET Framework type</span></span>|<span data-ttu-id="e0727-108">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e0727-108">Default Value</span></span>|  
|----------|-----------|----------|-------------------------|-------------------|  
|`int`|<span data-ttu-id="e0727-109">От -2 147 483 648 до 2 147 483 647</span><span class="sxs-lookup"><span data-stu-id="e0727-109">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="e0727-110">32-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="e0727-110">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="e0727-111">0</span><span class="sxs-lookup"><span data-stu-id="e0727-111">0</span></span>|  
  
## <a name="literals"></a><span data-ttu-id="e0727-112">Литералы</span><span class="sxs-lookup"><span data-stu-id="e0727-112">Literals</span></span>  
 
<span data-ttu-id="e0727-113">Переменную `int` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7.0) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="e0727-113">You can declare and initialize an `int` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="e0727-114">Если целочисленный литерал выходит за пределы диапазона `int` (то есть если он меньше <xref:System.Int32.MinValue?displayProperty=nameWithType> или больше <xref:System.Int32.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="e0727-114">If the integer literal is outside the range of `int` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="e0727-115">В следующем примере целые числа, равные 90 946 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `int`.</span><span class="sxs-lookup"><span data-stu-id="e0727-115">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `int` values.</span></span>  
  
[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]  

> [!NOTE] 
> <span data-ttu-id="e0727-116">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="e0727-116">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="e0727-117">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="e0727-117">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="e0727-118">Начиная с C# 7.0 было добавлено несколько возможностей для повышения удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="e0727-118">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="e0727-119">В C# 7.0 поддерживается использование символа подчеркивания (`_`) в качестве разделителя цифр.</span><span class="sxs-lookup"><span data-stu-id="e0727-119">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="e0727-120">В C# 7.2 поддерживается использование `_` (после префикса) в качестве разделителя для двоичного или шестнадцатеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="e0727-120">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="e0727-121">Десятичный литерал не может начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="e0727-121">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="e0727-122">Ниже приведено несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="e0727-122">Some examples are shown below.</span></span>

[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]  
 
 <span data-ttu-id="e0727-123">Целочисленные литералы могут содержать суффикс, обозначающий тип, несмотря на то, что для обозначения типа `int` суффикс не предусмотрен.</span><span class="sxs-lookup"><span data-stu-id="e0727-123">Integer literals can also include a suffix that denotes the type, although there is no suffix that denotes the `int` type.</span></span> <span data-ttu-id="e0727-124">Если целочисленный литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение:</span><span class="sxs-lookup"><span data-stu-id="e0727-124">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. `int`
2. [<span data-ttu-id="e0727-125">uint</span><span class="sxs-lookup"><span data-stu-id="e0727-125">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="e0727-126">long</span><span class="sxs-lookup"><span data-stu-id="e0727-126">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="e0727-127">ulong</span><span class="sxs-lookup"><span data-stu-id="e0727-127">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
 
<span data-ttu-id="e0727-128">В этих примерах литерал 90946 имеет тип `int`.</span><span class="sxs-lookup"><span data-stu-id="e0727-128">In these examples, the literal 90946 is of type `int`.</span></span>
  
## <a name="conversions"></a><span data-ttu-id="e0727-129">Преобразования</span><span class="sxs-lookup"><span data-stu-id="e0727-129">Conversions</span></span>  
 <span data-ttu-id="e0727-130">Существует предопределенное неявное преобразование типа `int` в тип [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="e0727-130">There is a predefined implicit conversion from `int` to [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="e0727-131">Пример:</span><span class="sxs-lookup"><span data-stu-id="e0727-131">For example:</span></span>  
  
```csharp  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 <span data-ttu-id="e0727-132">Существует предопределенное неявное преобразование типа [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) или [char](../../../csharp/language-reference/keywords/char.md) в `int`.</span><span class="sxs-lookup"><span data-stu-id="e0727-132">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `int`.</span></span> <span data-ttu-id="e0727-133">Например, следующий оператор назначения вызывает ошибку компиляции без приведения:</span><span class="sxs-lookup"><span data-stu-id="e0727-133">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 <span data-ttu-id="e0727-134">Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `int` не существует.</span><span class="sxs-lookup"><span data-stu-id="e0727-134">Notice also that there is no implicit conversion from floating-point types to `int`.</span></span> <span data-ttu-id="e0727-135">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="e0727-135">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 <span data-ttu-id="e0727-136">Дополнительные сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="e0727-136">For more information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e0727-137">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e0727-137">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e0727-138">См. также</span><span class="sxs-lookup"><span data-stu-id="e0727-138">See Also</span></span>  
 <xref:System.Int32>  
 [<span data-ttu-id="e0727-139">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e0727-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e0727-140">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e0727-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e0727-141">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="e0727-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="e0727-142">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="e0727-142">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="e0727-143">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="e0727-143">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="e0727-144">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="e0727-144">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="e0727-145">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="e0727-145">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
