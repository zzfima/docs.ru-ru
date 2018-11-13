---
title: uint (справочник по C#)
ms.date: 03/14/2017
f1_keywords:
- uint
- uint_CSharpKeyword
helpviewer_keywords:
- uint keyword [C#]
ms.assetid: e93e42c6-ec72-4b0b-89df-2fd8d36f7a7b
ms.openlocfilehash: c8610d13a97e672773fdf80d013a159a58e7cfbf
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "50744341"
---
# <a name="uint-c-reference"></a><span data-ttu-id="70073-102">uint (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="70073-102">uint (C# Reference)</span></span>

<span data-ttu-id="70073-103">Ключевое слово `uint` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="70073-103">The `uint` keyword signifies an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="70073-104">Тип</span><span class="sxs-lookup"><span data-stu-id="70073-104">Type</span></span>|<span data-ttu-id="70073-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="70073-105">Range</span></span>|<span data-ttu-id="70073-106">Размер</span><span class="sxs-lookup"><span data-stu-id="70073-106">Size</span></span>|<span data-ttu-id="70073-107">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="70073-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`uint`|<span data-ttu-id="70073-108">От 0 до 4 294 967 295</span><span class="sxs-lookup"><span data-stu-id="70073-108">0 to 4,294,967,295</span></span>|<span data-ttu-id="70073-109">32-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="70073-109">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
  
 <span data-ttu-id="70073-110">**Примечание.** Тип `uint` не совместим с CLS.</span><span class="sxs-lookup"><span data-stu-id="70073-110">**Note** The `uint` type is not CLS-compliant.</span></span> <span data-ttu-id="70073-111">По возможности используйте `int`.</span><span class="sxs-lookup"><span data-stu-id="70073-111">Use `int` whenever possible.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="70073-112">Литералы</span><span class="sxs-lookup"><span data-stu-id="70073-112">Literals</span></span>  

<span data-ttu-id="70073-113">Переменную `uint` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7.0) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="70073-113">You can declare and initialize a `uint` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="70073-114">Если целочисленный литерал выходит за пределы диапазона `uint` (то есть если он меньше <xref:System.UInt32.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="70073-114">If the integer literal is outside the range of `uint` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="70073-115">В следующем примере целые числа, равные 3 000 000 000 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `uint`.</span><span class="sxs-lookup"><span data-stu-id="70073-115">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `uint` values.</span></span>  
  
[!code-csharp[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]  

> [!NOTE] 
> <span data-ttu-id="70073-116">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="70073-116">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="70073-117">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="70073-117">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="70073-118">Начиная с C# 7.0 было добавлено несколько возможностей для повышения удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="70073-118">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="70073-119">В C# 7.0 поддерживается использование символа подчеркивания (`_`) в качестве разделителя цифр.</span><span class="sxs-lookup"><span data-stu-id="70073-119">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="70073-120">В C# 7.2 поддерживается использование `_` (после префикса) в качестве разделителя для двоичного или шестнадцатеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="70073-120">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="70073-121">Десятичный литерал не может начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="70073-121">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="70073-122">Ниже приведено несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="70073-122">Some examples are shown below.</span></span>

[!code-csharp[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]  
 
 <span data-ttu-id="70073-123">Целочисленные литералы могут также содержать суффикс, обозначающий тип.</span><span class="sxs-lookup"><span data-stu-id="70073-123">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="70073-124">Суффикс `U` или "u" обозначает либо `uint`, либо `ulong` в зависимости от числового значения литерала.</span><span class="sxs-lookup"><span data-stu-id="70073-124">The suffix `U` or 'u' denotes either a `uint` or a `ulong`, depending on the numeric value of the literal.</span></span> <span data-ttu-id="70073-125">В следующем примере суффикс `u` используется для обозначения целого числа без знака обоих типов.</span><span class="sxs-lookup"><span data-stu-id="70073-125">The following example uses the `u` suffix to denote an unsigned integer of both types.</span></span> <span data-ttu-id="70073-126">Обратите внимание, что первый литерал имеет тип `uint`, поскольку его значение меньше <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, а второй имеет тип `ulong`, поскольку его значение больше <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="70073-126">Note that the first literal is a `uint` because its value is less than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, while the second is a `ulong` because its value is greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>

[!code-csharp[usuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]  
 
<span data-ttu-id="70073-127">Если целочисленный литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение:</span><span class="sxs-lookup"><span data-stu-id="70073-127">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="70073-128">int</span><span class="sxs-lookup"><span data-stu-id="70073-128">int</span></span>](int.md)
2. `uint`
3. [<span data-ttu-id="70073-129">long</span><span class="sxs-lookup"><span data-stu-id="70073-129">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="70073-130">ulong</span><span class="sxs-lookup"><span data-stu-id="70073-130">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
  
## <a name="conversions"></a><span data-ttu-id="70073-131">Преобразования</span><span class="sxs-lookup"><span data-stu-id="70073-131">Conversions</span></span>  
 <span data-ttu-id="70073-132">Существует предопределенное неявное преобразование типа `uint` в тип [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="70073-132">There is a predefined implicit conversion from `uint` to [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="70073-133">Пример:</span><span class="sxs-lookup"><span data-stu-id="70073-133">For example:</span></span>  
  
```csharp  
float myFloat = 4294967290;   // OK: implicit conversion to float  
```  
  
 <span data-ttu-id="70073-134">Существует предопределенное неявное преобразование типа [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) или [char](../../../csharp/language-reference/keywords/char.md) в тип `uint`.</span><span class="sxs-lookup"><span data-stu-id="70073-134">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `uint`.</span></span> <span data-ttu-id="70073-135">В противном случае необходимо использовать приведение.</span><span class="sxs-lookup"><span data-stu-id="70073-135">Otherwise you must use a cast.</span></span> <span data-ttu-id="70073-136">Например, следующий оператор назначения вызывает ошибку компиляции без приведения:</span><span class="sxs-lookup"><span data-stu-id="70073-136">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
// Error -- no implicit conversion from long:  
uint uInt1 = aLong;   
// OK -- explicit conversion:  
uint uInt2 = (uint)aLong;  
```  
  
 <span data-ttu-id="70073-137">Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `uint` не существует.</span><span class="sxs-lookup"><span data-stu-id="70073-137">Notice also that there is no implicit conversion from floating-point types to `uint`.</span></span> <span data-ttu-id="70073-138">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="70073-138">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
uint x = 3.0;  
// OK -- explicit conversion:  
uint y = (uint)3.0;   
```  
  
 <span data-ttu-id="70073-139">Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="70073-139">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="70073-140">Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="70073-140">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="70073-141">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="70073-141">C# Language Specification</span></span>  

<span data-ttu-id="70073-142">Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="70073-142">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="70073-143">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="70073-143">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="70073-144">См. также</span><span class="sxs-lookup"><span data-stu-id="70073-144">See Also</span></span>

- <xref:System.UInt32>  
- [<span data-ttu-id="70073-145">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="70073-145">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="70073-146">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="70073-146">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="70073-147">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="70073-147">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="70073-148">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="70073-148">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="70073-149">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="70073-149">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="70073-150">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="70073-150">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="70073-151">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="70073-151">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
