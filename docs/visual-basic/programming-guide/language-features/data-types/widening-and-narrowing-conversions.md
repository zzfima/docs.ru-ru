---
title: "Расширяющие и сужающие преобразования (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- widening conversions
- narrowing conversions
- conversions, type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- conversions, exceptions during conversion
- type conversion, exceptions during conversion
- conversions, data type
- conversions, narrowing
- type conversion, narrowing
- data type conversion, widening
- data type conversion, narrowing
- changing data types
- type conversion, widening
- data type conversion, exceptions during conversion
- conversions, widening
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c00db1c631e1cc71df856407e8646532a73c6d44
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="widening-and-narrowing-conversions-visual-basic"></a><span data-ttu-id="71666-102">Расширяющие и сужающие преобразования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71666-102">Widening and Narrowing Conversions (Visual Basic)</span></span>
<span data-ttu-id="71666-103">Важным аспектом при преобразовании типа является результатом преобразования в пределах диапазона целевого типа данных.</span><span class="sxs-lookup"><span data-stu-id="71666-103">An important consideration with a type conversion is whether the result of the conversion is within the range of the destination data type.</span></span>  
  
 <span data-ttu-id="71666-104">Объект *расширяющее преобразование* изменяет значение на тип данных, который позволяет выполнять любое возможное значение исходных данных.</span><span class="sxs-lookup"><span data-stu-id="71666-104">A *widening conversion* changes a value to a data type that can allow for any possible value of the original data.</span></span>  <span data-ttu-id="71666-105">Расширяющие преобразования сохраняют исходное значение, но могут изменить его представление.</span><span class="sxs-lookup"><span data-stu-id="71666-105">Widening conversions preserve the source value but can change its representation.</span></span> <span data-ttu-id="71666-106">Это происходит при преобразовании из целого типа в `Decimal`, или `Char` в `String`.</span><span class="sxs-lookup"><span data-stu-id="71666-106">This occurs if you convert from an integral type to `Decimal`, or from `Char` to `String`.</span></span>  
  
 <span data-ttu-id="71666-107">*Преобразование сужения* изменяет тип данных значения на тип, который не сможет содержать некоторые возможные значения.</span><span class="sxs-lookup"><span data-stu-id="71666-107">A *narrowing conversion* changes a value to a data type that might not be able to hold some of the possible values.</span></span> <span data-ttu-id="71666-108">Например, дробные значения округляются при преобразовании целочисленного типа и числового типа, при преобразовании в `Boolean` уменьшается либо `True` или `False`.</span><span class="sxs-lookup"><span data-stu-id="71666-108">For example, a fractional value is rounded when it is converted to an integral type, and a numeric type being converted to `Boolean` is reduced to either `True` or `False`.</span></span>  
  
## <a name="widening-conversions"></a><span data-ttu-id="71666-109">Расширяющие преобразования</span><span class="sxs-lookup"><span data-stu-id="71666-109">Widening Conversions</span></span>  
 <span data-ttu-id="71666-110">В следующей таблице показаны стандартные расширяющие преобразования.</span><span class="sxs-lookup"><span data-stu-id="71666-110">The following table shows the standard widening conversions.</span></span>  
  
|<span data-ttu-id="71666-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="71666-111">Data type</span></span>|<span data-ttu-id="71666-112">Расширяется до типов данных <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="71666-112">Widens to data types <sup>1</sup></span></span>|  
|---|---|  
|[<span data-ttu-id="71666-113">SByte</span><span class="sxs-lookup"><span data-stu-id="71666-113">SByte</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="71666-114">`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="71666-114">`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="71666-115">Byte</span><span class="sxs-lookup"><span data-stu-id="71666-115">Byte</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="71666-116">`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="71666-116">`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="71666-117">Короткий</span><span class="sxs-lookup"><span data-stu-id="71666-117">Short</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="71666-118">`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="71666-118">`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="71666-119">UShort</span><span class="sxs-lookup"><span data-stu-id="71666-119">UShort</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="71666-120">`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="71666-120">`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="71666-121">Целое число</span><span class="sxs-lookup"><span data-stu-id="71666-121">Integer</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="71666-122">`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="71666-122">`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="71666-123">UInteger</span><span class="sxs-lookup"><span data-stu-id="71666-123">UInteger</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="71666-124">`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="71666-124">`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="71666-125">Длинное</span><span class="sxs-lookup"><span data-stu-id="71666-125">Long</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="71666-126">`Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="71666-126">`Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="71666-127">ULong</span><span class="sxs-lookup"><span data-stu-id="71666-127">ULong</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="71666-128">`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="71666-128">`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="71666-129">Decimal</span><span class="sxs-lookup"><span data-stu-id="71666-129">Decimal</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="71666-130">`Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="71666-130">`Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="71666-131">Single</span><span class="sxs-lookup"><span data-stu-id="71666-131">Single</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="71666-132">`Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="71666-132">`Single`, `Double`</span></span>|  
|[<span data-ttu-id="71666-133">Double</span><span class="sxs-lookup"><span data-stu-id="71666-133">Double</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|<span data-ttu-id="71666-134">Какой-либо перечисляемый тип ([перечисления](../../../../visual-basic/language-reference/statements/enum-statement.md))</span><span class="sxs-lookup"><span data-stu-id="71666-134">Any enumerated type ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))</span></span>|<span data-ttu-id="71666-135">Его основного целочисленного типа и любой тип, до которого может быть расширен базовый тип.</span><span class="sxs-lookup"><span data-stu-id="71666-135">Its underlying integral type and any type to which the underlying type widens.</span></span>|  
|[<span data-ttu-id="71666-136">Char</span><span class="sxs-lookup"><span data-stu-id="71666-136">Char</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="71666-137">`Char`, `String`</span><span class="sxs-lookup"><span data-stu-id="71666-137">`Char`, `String`</span></span>|  
|<span data-ttu-id="71666-138">Массив `Char`</span><span class="sxs-lookup"><span data-stu-id="71666-138">`Char` array</span></span>|<span data-ttu-id="71666-139">`Char`Массив,`String`</span><span class="sxs-lookup"><span data-stu-id="71666-139">`Char` array, `String`</span></span>|  
|<span data-ttu-id="71666-140">Любой тип</span><span class="sxs-lookup"><span data-stu-id="71666-140">Any type</span></span>|[<span data-ttu-id="71666-141">Объект</span><span class="sxs-lookup"><span data-stu-id="71666-141">Object</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|<span data-ttu-id="71666-142">Любой производный тип</span><span class="sxs-lookup"><span data-stu-id="71666-142">Any derived type</span></span>|<span data-ttu-id="71666-143">Любой базовый тип, из которого получается <sup>3</sup>.</span><span class="sxs-lookup"><span data-stu-id="71666-143">Any base type from which it is derived <sup>3</sup>.</span></span>|  
|<span data-ttu-id="71666-144">Любой тип</span><span class="sxs-lookup"><span data-stu-id="71666-144">Any type</span></span>|<span data-ttu-id="71666-145">Любой интерфейс, который его реализует.</span><span class="sxs-lookup"><span data-stu-id="71666-145">Any interface it implements.</span></span>|  
|[<span data-ttu-id="71666-146">Nothing</span><span class="sxs-lookup"><span data-stu-id="71666-146">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)|<span data-ttu-id="71666-147">Тип данных или тип объекта.</span><span class="sxs-lookup"><span data-stu-id="71666-147">Any data type or object type.</span></span>|  
  
 <span data-ttu-id="71666-148"><sup>1</sup> по определению каждый тип данных может быть расширен до самого.</span><span class="sxs-lookup"><span data-stu-id="71666-148"><sup>1</sup> By definition, every data type widens to itself.</span></span>  
  
 <span data-ttu-id="71666-149"><sup>2</sup> преобразования из `Integer`, `UInteger`, `Long`, `ULong`, или `Decimal` для `Single` или `Double` может привести к потере точности, но никогда не потере величины.</span><span class="sxs-lookup"><span data-stu-id="71666-149"><sup>2</sup> Conversions from `Integer`, `UInteger`, `Long`, `ULong`, or `Decimal` to `Single` or `Double` might result in loss of precision, but never in loss of magnitude.</span></span> <span data-ttu-id="71666-150">В этом смысле они не создают потерю данных.</span><span class="sxs-lookup"><span data-stu-id="71666-150">In this sense they do not incur information loss.</span></span>  
  
 <span data-ttu-id="71666-151"><sup>3</sup> может показаться странным, что преобразование из производного типа в один из его базовых типов является расширяющим.</span><span class="sxs-lookup"><span data-stu-id="71666-151"><sup>3</sup> It might seem surprising that a conversion from a derived type to one of its base types is widening.</span></span> <span data-ttu-id="71666-152">Объясняется это тем, что производный тип содержит все члены базового типа, поэтому он определяется как экземпляр базового типа.</span><span class="sxs-lookup"><span data-stu-id="71666-152">The justification is that the derived type contains all the members of the base type, so it qualifies as an instance of the base type.</span></span> <span data-ttu-id="71666-153">В обратном направлении базовый тип не содержит все новых членов, определенных производным типом.</span><span class="sxs-lookup"><span data-stu-id="71666-153">In the opposite direction, the base type does not contain any new members defined by the derived type.</span></span>  
  
 <span data-ttu-id="71666-154">Расширяющие преобразования всегда успешны во время выполнения и никогда не приводят к потере данных.</span><span class="sxs-lookup"><span data-stu-id="71666-154">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="71666-155">Можно всегда выполнить их неявным образом, является ли [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) задает ключ для проверки типа `On` или `Off`.</span><span class="sxs-lookup"><span data-stu-id="71666-155">You can always perform them implicitly, whether the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) sets the type checking switch to `On` or to `Off`.</span></span>  
  
## <a name="narrowing-conversions"></a><span data-ttu-id="71666-156">Сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="71666-156">Narrowing Conversions</span></span>  
 <span data-ttu-id="71666-157">Стандартные сужающие преобразования включают следующие:</span><span class="sxs-lookup"><span data-stu-id="71666-157">The standard narrowing conversions include the following:</span></span>  
  
-   <span data-ttu-id="71666-158">Обратные направления расширяющих преобразований в предшествующей таблице (за исключением того, что каждый тип может быть расширен на себя)</span><span class="sxs-lookup"><span data-stu-id="71666-158">The reverse directions of the widening conversions in the preceding table (except that every type widens to itself)</span></span>  
  
-   <span data-ttu-id="71666-159">Преобразования в любом направлении между [логическое](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) и любым числовым типом.</span><span class="sxs-lookup"><span data-stu-id="71666-159">Conversions in either direction between [Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) and any numeric type</span></span>  
  
-   <span data-ttu-id="71666-160">Преобразования любого числового типа в любой перечисляемый тип (`Enum`)</span><span class="sxs-lookup"><span data-stu-id="71666-160">Conversions from any numeric type to any enumerated type (`Enum`)</span></span>  
  
-   <span data-ttu-id="71666-161">Преобразования в любом направлении между [строка](../../../../visual-basic/language-reference/data-types/string-data-type.md) и любым числовым типом `Boolean`, или [даты](../../../../visual-basic/language-reference/data-types/date-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="71666-161">Conversions in either direction between [String](../../../../visual-basic/language-reference/data-types/string-data-type.md) and any numeric type, `Boolean`, or [Date](../../../../visual-basic/language-reference/data-types/date-data-type.md)</span></span>  
  
-   <span data-ttu-id="71666-162">Преобразования из типа данных или объект типа в тип, производный от него</span><span class="sxs-lookup"><span data-stu-id="71666-162">Conversions from a data type or object type to a type derived from it</span></span>  
  
 <span data-ttu-id="71666-163">Сужающие преобразования не всегда успешны во время выполнения и может завершиться ошибкой или приводят к потере данных.</span><span class="sxs-lookup"><span data-stu-id="71666-163">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="71666-164">Ошибка возникает, если целевой тип данных не может получить преобразованное значение.</span><span class="sxs-lookup"><span data-stu-id="71666-164">An error occurs if the destination data type cannot receive the value being converted.</span></span> <span data-ttu-id="71666-165">Например числовое преобразование может привести к переполнению.</span><span class="sxs-lookup"><span data-stu-id="71666-165">For example, a numeric conversion can result in an overflow.</span></span> <span data-ttu-id="71666-166">Компилятор не дают возможность выполнения сужающего преобразования неявно, если не [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) задает ключ для проверки типа `Off`.</span><span class="sxs-lookup"><span data-stu-id="71666-166">The compiler does not allow you to perform narrowing conversions implicitly unless the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) sets the type checking switch to `Off`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71666-167">Ошибка сужающего преобразования отбрасывается при преобразовании из элементов в `For Each…Next` коллекцию для переменной цикла.</span><span class="sxs-lookup"><span data-stu-id="71666-167">The narrowing-conversion error is suppressed for conversions from the elements in a `For Each…Next` collection to the loop control variable.</span></span> <span data-ttu-id="71666-168">Дополнительные сведения и примеры см. в разделе «Сужающие преобразования» [For Each... Следующий оператор](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="71666-168">For more information and examples, see the "Narrowing Conversions" section in [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
### <a name="when-to-use-narrowing-conversions"></a><span data-ttu-id="71666-169">Когда следует использовать сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="71666-169">When to Use Narrowing Conversions</span></span>  
 <span data-ttu-id="71666-170">Сужающее преобразование использовать, когда известно, что исходное значение может быть преобразовано в конечный тип данных без ошибки и потери данных.</span><span class="sxs-lookup"><span data-stu-id="71666-170">You use a narrowing conversion when you know the source value can be converted to the destination data type without error or data loss.</span></span> <span data-ttu-id="71666-171">Например, если у вас есть `String` , вы знаете, содержит значение «True» или «False», можно использовать `CBool` ключевое слово для преобразования его в `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="71666-171">For example, if you have a `String` that you know contains either "True" or "False," you can use the `CBool` keyword to convert it to `Boolean`.</span></span>  
  
## <a name="exceptions-during-conversion"></a><span data-ttu-id="71666-172">Исключения при преобразовании</span><span class="sxs-lookup"><span data-stu-id="71666-172">Exceptions During Conversion</span></span>  
 <span data-ttu-id="71666-173">Поскольку расширяющие преобразования всегда выполнена успешно, они не создают исключений.</span><span class="sxs-lookup"><span data-stu-id="71666-173">Because widening conversions always succeed, they do not throw exceptions.</span></span> <span data-ttu-id="71666-174">Сужающие преобразования, если они не часто создают следующие исключения:</span><span class="sxs-lookup"><span data-stu-id="71666-174">Narrowing conversions, when they fail, most commonly throw the following exceptions:</span></span>  
  
-   <span data-ttu-id="71666-175"><xref:System.InvalidCastException>— Если не определено преобразование между двумя типами</xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="71666-175"><xref:System.InvalidCastException> — if no conversion is defined between the two types</span></span>  
  
-   <span data-ttu-id="71666-176"><xref:System.OverflowException>— (только для целых типов) если преобразованное значение слишком велико для целевого типа</xref:System.OverflowException></span><span class="sxs-lookup"><span data-stu-id="71666-176"><xref:System.OverflowException> — (integral types only) if the converted value is too large for the target type</span></span>  
  
 <span data-ttu-id="71666-177">Если класс или структура определяет [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) в качестве оператора преобразования в или из этого класса или структуры, которая `CType` можно вызывать любое исключение, которые она считает необходимыми.</span><span class="sxs-lookup"><span data-stu-id="71666-177">If a class or structure defines a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to serve as a conversion operator to or from that class or structure, that `CType` can throw any exception it deems appropriate.</span></span> <span data-ttu-id="71666-178">Кроме того, что `CType` может вызвать [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] функции или [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] методы, которые в свою очередь, могут вызвать ряд исключений.</span><span class="sxs-lookup"><span data-stu-id="71666-178">In addition, that `CType` might call [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] functions or [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] methods, which in turn could throw a variety of exceptions.</span></span>  
  
## <a name="changes-during-reference-type-conversions"></a><span data-ttu-id="71666-179">Изменения в ходе преобразования типа ссылки</span><span class="sxs-lookup"><span data-stu-id="71666-179">Changes During Reference Type Conversions</span></span>  
 <span data-ttu-id="71666-180">Преобразование из *ссылочный тип* копирует только указатель на значение.</span><span class="sxs-lookup"><span data-stu-id="71666-180">A conversion from a *reference type* copies only the pointer to the value.</span></span> <span data-ttu-id="71666-181">Само значение не копируются и не изменяется.</span><span class="sxs-lookup"><span data-stu-id="71666-181">The value itself is neither copied nor changed in any way.</span></span> <span data-ttu-id="71666-182">Единственное, что можно изменить является типом данных переменной, содержащей указатель.</span><span class="sxs-lookup"><span data-stu-id="71666-182">The only thing that can change is the data type of the variable holding the pointer.</span></span> <span data-ttu-id="71666-183">В следующем примере тип данных преобразуется из производного класса в его базовый класс, но объект, чтобы указывают обе переменные, не изменяется.</span><span class="sxs-lookup"><span data-stu-id="71666-183">In the following example, the data type is converted from the derived class to its base class, but the object that both variables now point to is unchanged.</span></span>  
  
```  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a><span data-ttu-id="71666-184">См. также</span><span class="sxs-lookup"><span data-stu-id="71666-184">See Also</span></span>  
 <span data-ttu-id="71666-185">[Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="71666-185">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="71666-186"> [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="71666-186"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="71666-187"> [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="71666-187"> [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="71666-188"> [Преобразование между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md) </span><span class="sxs-lookup"><span data-stu-id="71666-188"> [Conversions Between Strings and Other Types](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md) </span></span>  
<span data-ttu-id="71666-189"> [Практическое руководство: преобразование объекта к другому типу в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span><span class="sxs-lookup"><span data-stu-id="71666-189"> [How to: Convert an Object to Another Type in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span></span>  
<span data-ttu-id="71666-190"> [Преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="71666-190"> [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md) </span></span>  
<span data-ttu-id="71666-191"> [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="71666-191"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="71666-192"> [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)</span><span class="sxs-lookup"><span data-stu-id="71666-192"> [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)</span></span>
