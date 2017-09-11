---
title: "Таблица явных числовых преобразований (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#], explicit numeric
- numeric conversions [C#], explicit
- explicit numeric conversion [C#]
- numeric data types [C#]
- types [C#], explicit numeric conversions
- type conversion [C#], explicit numeric
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
caps.latest.revision: 14
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
ms.openlocfilehash: 0315810522be319a6bb565c99e1c8f7d1ba4701b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="explicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="d83b0-102">Таблица явных числовых преобразований (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d83b0-102">Explicit Numeric Conversions Table (C# Reference)</span></span>
<span data-ttu-id="d83b0-103">Явное числовое преобразование используется для преобразования любого числового типа в любой другой числовой тип, для которого отсутствует неявное преобразование, с использованием выражения приведения.</span><span class="sxs-lookup"><span data-stu-id="d83b0-103">Explicit numeric conversion is used to convert any numeric type to any other numeric type, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="d83b0-104">Эти преобразования показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d83b0-104">The following table shows these conversions.</span></span>  
  
 <span data-ttu-id="d83b0-105">Дополнительные сведения о преобразованиях см. в разделе [Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="d83b0-105">For more information about conversions, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
|<span data-ttu-id="d83b0-106">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="d83b0-106">From</span></span>|<span data-ttu-id="d83b0-107">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="d83b0-107">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="d83b0-108">sbyte</span><span class="sxs-lookup"><span data-stu-id="d83b0-108">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="d83b0-109">`byte`, `ushort`, `uint`, `ulong` или `char`</span><span class="sxs-lookup"><span data-stu-id="d83b0-109">`byte`, `ushort`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="d83b0-110">byte</span><span class="sxs-lookup"><span data-stu-id="d83b0-110">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="d83b0-111">`Sbyte` или `char`</span><span class="sxs-lookup"><span data-stu-id="d83b0-111">`Sbyte` or `char`</span></span>|  
|[<span data-ttu-id="d83b0-112">short</span><span class="sxs-lookup"><span data-stu-id="d83b0-112">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="d83b0-113">`sbyte`, `byte`, `ushort`, `uint`, `ulong` или `char`</span><span class="sxs-lookup"><span data-stu-id="d83b0-113">`sbyte`, `byte`, `ushort`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="d83b0-114">ushort</span><span class="sxs-lookup"><span data-stu-id="d83b0-114">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="d83b0-115">`sbyte`, `byte`, `short` или `char`</span><span class="sxs-lookup"><span data-stu-id="d83b0-115">`sbyte`, `byte`, `short`, or `char`</span></span>|  
|[<span data-ttu-id="d83b0-116">int</span><span class="sxs-lookup"><span data-stu-id="d83b0-116">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="d83b0-117">`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` или `char`</span><span class="sxs-lookup"><span data-stu-id="d83b0-117">`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong`,or `char`</span></span>|  
|[<span data-ttu-id="d83b0-118">uint</span><span class="sxs-lookup"><span data-stu-id="d83b0-118">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="d83b0-119">`sbyte`, `byte`, `short`, `ushort`, `int` или `char`</span><span class="sxs-lookup"><span data-stu-id="d83b0-119">`sbyte`, `byte`, `short`, `ushort`, `int`, or `char`</span></span>|  
|[<span data-ttu-id="d83b0-120">long</span><span class="sxs-lookup"><span data-stu-id="d83b0-120">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="d83b0-121">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` или `char`</span><span class="sxs-lookup"><span data-stu-id="d83b0-121">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="d83b0-122">ulong</span><span class="sxs-lookup"><span data-stu-id="d83b0-122">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="d83b0-123">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` или `char`</span><span class="sxs-lookup"><span data-stu-id="d83b0-123">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, or `char`</span></span>|  
|[<span data-ttu-id="d83b0-124">char</span><span class="sxs-lookup"><span data-stu-id="d83b0-124">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="d83b0-125">`sbyte`, `byte`или `short`</span><span class="sxs-lookup"><span data-stu-id="d83b0-125">`sbyte`, `byte`, or `short`</span></span>|  
|[<span data-ttu-id="d83b0-126">float</span><span class="sxs-lookup"><span data-stu-id="d83b0-126">float</span></span>](../../../csharp/language-reference/keywords/float.md)|<span data-ttu-id="d83b0-127">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="d83b0-127">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`,or `decimal`</span></span>|  
|[<span data-ttu-id="d83b0-128">double</span><span class="sxs-lookup"><span data-stu-id="d83b0-128">double</span></span>](../../../csharp/language-reference/keywords/double.md)|<span data-ttu-id="d83b0-129">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="d83b0-129">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`,or `decimal`</span></span>|  
|[<span data-ttu-id="d83b0-130">decimal</span><span class="sxs-lookup"><span data-stu-id="d83b0-130">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|<span data-ttu-id="d83b0-131">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` или `double`</span><span class="sxs-lookup"><span data-stu-id="d83b0-131">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, or `double`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d83b0-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="d83b0-132">Remarks</span></span>  
  
-   <span data-ttu-id="d83b0-133">Явное числовое преобразование может привести к потере точности или возникновению исключения.</span><span class="sxs-lookup"><span data-stu-id="d83b0-133">The explicit numeric conversion may cause loss of precision or result in throwing exceptions.</span></span>  
  
-   <span data-ttu-id="d83b0-134">При преобразовании значения `decimal` в целочисленный тип оно округляется в сторону нуля до ближайшего целого значения.</span><span class="sxs-lookup"><span data-stu-id="d83b0-134">When you convert a `decimal` value to an integral type, this value is rounded towards zero to the nearest integral value.</span></span> <span data-ttu-id="d83b0-135">Если итоговое целое значение находится вне диапазона целевого типа, возникает исключение <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="d83b0-135">If the resulting integral value is outside the range of the destination type, an <xref:System.OverflowException> is thrown.</span></span>  
  
-   <span data-ttu-id="d83b0-136">При преобразовании значения `double` или `float` в целочисленный тип это значение усекается.</span><span class="sxs-lookup"><span data-stu-id="d83b0-136">When you convert from a `double` or `float` value to an integral type, the value is truncated.</span></span> <span data-ttu-id="d83b0-137">Если полученное целое значение выходит за пределы диапазона целевого значения, результат будет зависеть от контекста проверки переполнения.</span><span class="sxs-lookup"><span data-stu-id="d83b0-137">If the resulting integral value is outside the range of the destination value, the result depends on the overflow checking context.</span></span> <span data-ttu-id="d83b0-138">В проверенном контексте возникает исключение `OverflowException`, а в непроверенном контексте результатом будет неопределенное значение целевого типа.</span><span class="sxs-lookup"><span data-stu-id="d83b0-138">In a checked context, an `OverflowException` is thrown, while in an unchecked context, the result is an unspecified value of the destination type.</span></span>  
  
-   <span data-ttu-id="d83b0-139">При преобразовании из `double` в `float` значение `double` округляется до ближайшего значения `float`.</span><span class="sxs-lookup"><span data-stu-id="d83b0-139">When you convert `double` to `float`, the `double` value is rounded to the nearest `float` value.</span></span> <span data-ttu-id="d83b0-140">Если значение `double` слишком мало или слишком велико для целевого типа, результатом будет ноль или бесконечность соответственно.</span><span class="sxs-lookup"><span data-stu-id="d83b0-140">If the `double` value is too small or too large to fit into the destination type, the result will be zero or infinity.</span></span>  
  
-   <span data-ttu-id="d83b0-141">При преобразовании из `float` или `double` в `decimal` исходное значение преобразуется в представление `decimal` и при необходимости округляется до ближайшего числа после 28-го десятичного разряда.</span><span class="sxs-lookup"><span data-stu-id="d83b0-141">When you convert `float` or `double` to `decimal`, the source value is converted to `decimal` representation and rounded to the nearest number after the 28th decimal place if required.</span></span> <span data-ttu-id="d83b0-142">В зависимости от исходного значения возможны следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="d83b0-142">Depending on the value of the source value, one of the following results may occur:</span></span>  
  
    -   <span data-ttu-id="d83b0-143">Если исходное значение слишком мало для представления в виде `decimal`, результатом будет ноль.</span><span class="sxs-lookup"><span data-stu-id="d83b0-143">If the source value is too small to be represented as a `decimal`, the result becomes zero.</span></span>  
  
    -   <span data-ttu-id="d83b0-144">Если исходное значение не является числом (NaN), равно бесконечности или слишком велико для представления в виде `decimal`, возникает исключение `OverflowException`.</span><span class="sxs-lookup"><span data-stu-id="d83b0-144">If the source value is NaN (not a number), infinity, or too large to be represented as a `decimal`, an `OverflowException` is thrown.</span></span>  
  
-   <span data-ttu-id="d83b0-145">При преобразовании из `decimal` в `float` или `double` значение `decimal` округляется до ближайшего значения `double` или `float`.</span><span class="sxs-lookup"><span data-stu-id="d83b0-145">When you convert `decimal` to `float` or `double`, the `decimal` value is rounded to the nearest `double` or `float` value.</span></span>  
  
 <span data-ttu-id="d83b0-146">Дополнительные сведения о явных преобразованиях см. в спецификации языка C#.</span><span class="sxs-lookup"><span data-stu-id="d83b0-146">For more information on explicit conversion, see Explicit in the C# Language Specification.</span></span> <span data-ttu-id="d83b0-147">Дополнительные сведения о доступе к спецификации см. в разделе [Спецификация языка C#](../../../csharp/language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="d83b0-147">For more information on how to access the spec, see [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d83b0-148">См. также</span><span class="sxs-lookup"><span data-stu-id="d83b0-148">See Also</span></span>  
 <span data-ttu-id="d83b0-149">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d83b0-149">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d83b0-150">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d83b0-150">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d83b0-151">[Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="d83b0-151">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span></span>  
 <span data-ttu-id="d83b0-152">[Оператор ()](../../../csharp/language-reference/operators/invocation-operator.md) </span><span class="sxs-lookup"><span data-stu-id="d83b0-152">[() Operator](../../../csharp/language-reference/operators/invocation-operator.md) </span></span>  
 <span data-ttu-id="d83b0-153">[Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="d83b0-153">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="d83b0-154">[Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="d83b0-154">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 [<span data-ttu-id="d83b0-155">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="d83b0-155">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)

