---
title: uint (справочник по C#)
ms.date: 03/14/2017
f1_keywords:
- uint
- uint_CSharpKeyword
helpviewer_keywords:
- uint keyword [C#]
ms.assetid: e93e42c6-ec72-4b0b-89df-2fd8d36f7a7b
ms.openlocfilehash: fa0169ad92819cee36832d6c928202eb0dd6733e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288909"
---
# <a name="uint-c-reference"></a><span data-ttu-id="f61d4-102">uint (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f61d4-102">uint (C# Reference)</span></span>

<span data-ttu-id="f61d4-103">Ключевое слово `uint` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f61d4-103">The `uint` keyword signifies an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="f61d4-104">Тип</span><span class="sxs-lookup"><span data-stu-id="f61d4-104">Type</span></span>|<span data-ttu-id="f61d4-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="f61d4-105">Range</span></span>|<span data-ttu-id="f61d4-106">Размер</span><span class="sxs-lookup"><span data-stu-id="f61d4-106">Size</span></span>|<span data-ttu-id="f61d4-107">Тип платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f61d4-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`uint`|<span data-ttu-id="f61d4-108">От 0 до 4 294 967 295</span><span class="sxs-lookup"><span data-stu-id="f61d4-108">0 to 4,294,967,295</span></span>|<span data-ttu-id="f61d4-109">32-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="f61d4-109">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
  
 <span data-ttu-id="f61d4-110">**Примечание.** Тип `uint` не совместим с CLS.</span><span class="sxs-lookup"><span data-stu-id="f61d4-110">**Note** The `uint` type is not CLS-compliant.</span></span> <span data-ttu-id="f61d4-111">По возможности используйте `int`.</span><span class="sxs-lookup"><span data-stu-id="f61d4-111">Use `int` whenever possible.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="f61d4-112">Литералы</span><span class="sxs-lookup"><span data-stu-id="f61d4-112">Literals</span></span>  

<span data-ttu-id="f61d4-113">Переменную `uint` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7.0) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="f61d4-113">You can declare and initialize a `uint` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="f61d4-114">Если целочисленный литерал выходит за пределы диапазона `uint` (то есть если он меньше <xref:System.UInt32.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="f61d4-114">If the integer literal is outside the range of `uint` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="f61d4-115">В следующем примере целые числа, равные 3 000 000 000 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `uint`.</span><span class="sxs-lookup"><span data-stu-id="f61d4-115">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `uint` values.</span></span>  
  
[!code-csharp[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]  

> [!NOTE] 
> <span data-ttu-id="f61d4-116">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="f61d4-116">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="f61d4-117">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="f61d4-117">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="f61d4-118">Начиная с C# 7.0 было добавлено несколько возможностей для повышения удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="f61d4-118">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="f61d4-119">В C# 7.0 поддерживается использование символа подчеркивания (`_`) в качестве разделителя цифр.</span><span class="sxs-lookup"><span data-stu-id="f61d4-119">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="f61d4-120">В C# 7.2 поддерживается использование `_` (после префикса) в качестве разделителя для двоичного или шестнадцатеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="f61d4-120">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="f61d4-121">Десятичный литерал не может начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="f61d4-121">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="f61d4-122">Ниже приведено несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="f61d4-122">Some examples are shown below.</span></span>

[!code-csharp[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]  
 
 <span data-ttu-id="f61d4-123">Целочисленные литералы могут также содержать суффикс, обозначающий тип.</span><span class="sxs-lookup"><span data-stu-id="f61d4-123">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="f61d4-124">Суффикс `U` или "u" обозначает либо `uint`, либо `ulong` в зависимости от числового значения литерала.</span><span class="sxs-lookup"><span data-stu-id="f61d4-124">The suffix `U` or 'u' denotes either a `uint` or a `ulong`, depending on the numeric value of the literal.</span></span> <span data-ttu-id="f61d4-125">В следующем примере суффикс `u` используется для обозначения целого числа без знака обоих типов.</span><span class="sxs-lookup"><span data-stu-id="f61d4-125">The following example uses the `u` suffix to denote an unsigned integer of both types.</span></span> <span data-ttu-id="f61d4-126">Обратите внимание, что первый литерал имеет тип `uint`, поскольку его значение меньше <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, а второй имеет тип `ulong`, поскольку его значение больше <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f61d4-126">Note that the first literal is a `uint` because its value is less than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, while the second is a `ulong` because its value is greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>

[!code-csharp[usuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]  
 
<span data-ttu-id="f61d4-127">Если целочисленный литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение:</span><span class="sxs-lookup"><span data-stu-id="f61d4-127">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="f61d4-128">int</span><span class="sxs-lookup"><span data-stu-id="f61d4-128">int</span></span>](int.md)
2. `uint`
3. [<span data-ttu-id="f61d4-129">long</span><span class="sxs-lookup"><span data-stu-id="f61d4-129">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="f61d4-130">ulong</span><span class="sxs-lookup"><span data-stu-id="f61d4-130">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
  
## <a name="conversions"></a><span data-ttu-id="f61d4-131">Преобразования</span><span class="sxs-lookup"><span data-stu-id="f61d4-131">Conversions</span></span>  
 <span data-ttu-id="f61d4-132">Существует предопределенное неявное преобразование типа `uint` в тип [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="f61d4-132">There is a predefined implicit conversion from `uint` to [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="f61d4-133">Пример:</span><span class="sxs-lookup"><span data-stu-id="f61d4-133">For example:</span></span>  
  
```csharp  
float myFloat = 4294967290;   // OK: implicit conversion to float  
```  
  
 <span data-ttu-id="f61d4-134">Существует предопределенное неявное преобразование типа [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) или [char](../../../csharp/language-reference/keywords/char.md) в тип `uint`.</span><span class="sxs-lookup"><span data-stu-id="f61d4-134">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `uint`.</span></span> <span data-ttu-id="f61d4-135">В противном случае необходимо использовать приведение.</span><span class="sxs-lookup"><span data-stu-id="f61d4-135">Otherwise you must use a cast.</span></span> <span data-ttu-id="f61d4-136">Например, следующий оператор назначения вызывает ошибку компиляции без приведения:</span><span class="sxs-lookup"><span data-stu-id="f61d4-136">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
// Error -- no implicit conversion from long:  
uint uInt1 = aLong;   
// OK -- explicit conversion:  
uint uInt2 = (uint)aLong;  
```  
  
 <span data-ttu-id="f61d4-137">Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `uint` не существует.</span><span class="sxs-lookup"><span data-stu-id="f61d4-137">Notice also that there is no implicit conversion from floating-point types to `uint`.</span></span> <span data-ttu-id="f61d4-138">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="f61d4-138">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
uint x = 3.0;  
// OK -- explicit conversion:  
uint y = (uint)3.0;   
```  
  
 <span data-ttu-id="f61d4-139">Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="f61d4-139">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="f61d4-140">Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="f61d4-140">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f61d4-141">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f61d4-141">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f61d4-142">См. также</span><span class="sxs-lookup"><span data-stu-id="f61d4-142">See Also</span></span>  
 <xref:System.UInt32>  
 [<span data-ttu-id="f61d4-143">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f61d4-143">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f61d4-144">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f61d4-144">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f61d4-145">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f61d4-145">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f61d4-146">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="f61d4-146">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="f61d4-147">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="f61d4-147">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="f61d4-148">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="f61d4-148">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="f61d4-149">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="f61d4-149">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
