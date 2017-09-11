---
title: "Явные и неявные преобразования (Visual Basic) | Документы Microsoft"
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
- conversions, type
- variables [Visual Basic], changing data type
- casting
- conversions, data type
- type conversion, implicit conversions
- CType function, conversions
- casting, data types
- data type conversion, explicit
- type conversion, explicit conversions
- data types [Visual Basic], casting
- conversions, implicit
- explicit data type conversions
- conversions
- changing data types
- conversions, explicit
- data type conversion, implicit
- implicit data type conversions
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
caps.latest.revision: 25
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
ms.openlocfilehash: 76f32fc4c8e26470c77e1415d96ed9035a4d9165
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="implicit-and-explicit-conversions-visual-basic"></a><span data-ttu-id="1172e-102">Явные и неявные преобразования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1172e-102">Implicit and Explicit Conversions (Visual Basic)</span></span>
<span data-ttu-id="1172e-103">*Неявное преобразование* не требуют специального синтаксиса в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="1172e-103">An *implicit conversion* does not require any special syntax in the source code.</span></span> <span data-ttu-id="1172e-104">В следующем примере [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] неявно преобразует значение `k` в значение с плавающей запятой одиночной точности, перед назначением их `q`.</span><span class="sxs-lookup"><span data-stu-id="1172e-104">In the following example, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] implicitly converts the value of `k` to a single-precision floating-point value before assigning it to `q`.</span></span>  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 <span data-ttu-id="1172e-105">*Явное преобразование* используется ключевое слово преобразования типа.</span><span class="sxs-lookup"><span data-stu-id="1172e-105">An *explicit conversion* uses a type conversion keyword.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="1172e-106">предоставляет несколько зарезервированных слов, которые приводят выражение в скобках для нужного типа данных.</span><span class="sxs-lookup"><span data-stu-id="1172e-106"> provides several such keywords, which coerce an expression in parentheses to the desired data type.</span></span> <span data-ttu-id="1172e-107">Эти ключевые слова действуют аналогично функциям, но компилятор создает встроенный код, поэтому выполнение будет несколько быстрее, чем при вызове функции.</span><span class="sxs-lookup"><span data-stu-id="1172e-107">These keywords act like functions, but the compiler generates the code inline, so execution is slightly faster than with a function call.</span></span>  
  
 <span data-ttu-id="1172e-108">В следующем расширении предыдущего примера `CInt` ключевое слово преобразует значение `q` обратно в целое перед его присвоением `k`.</span><span class="sxs-lookup"><span data-stu-id="1172e-108">In the following extension of the preceding example, the `CInt` keyword converts the value of `q` back to an integer before assigning it to `k`.</span></span>  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## <a name="conversion-keywords"></a><span data-ttu-id="1172e-109">Ключевые слова преобразований</span><span class="sxs-lookup"><span data-stu-id="1172e-109">Conversion Keywords</span></span>  
 <span data-ttu-id="1172e-110">В следующей таблице показаны допустимые зарезервированные слова преобразования.</span><span class="sxs-lookup"><span data-stu-id="1172e-110">The following table shows the available conversion keywords.</span></span>  
  
|<span data-ttu-id="1172e-111">Ключевое слово преобразования типа</span><span class="sxs-lookup"><span data-stu-id="1172e-111">Type conversion keyword</span></span>|<span data-ttu-id="1172e-112">Преобразует выражение в тип данных</span><span class="sxs-lookup"><span data-stu-id="1172e-112">Converts an expression to data type</span></span>|<span data-ttu-id="1172e-113">Допустимые типы данных преобразуемого выражения</span><span class="sxs-lookup"><span data-stu-id="1172e-113">Allowable data types of expression to be converted</span></span>|  
|---|---|---|  
|`CBool`|[<span data-ttu-id="1172e-114">Логический тип данных</span><span class="sxs-lookup"><span data-stu-id="1172e-114">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="1172e-115">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="1172e-115">Any numeric type (including `Byte`, `SByte`, and enumerated types), `String`, `Object`</span></span>|  
|`CByte`|[<span data-ttu-id="1172e-116">Тип данных Byte</span><span class="sxs-lookup"><span data-stu-id="1172e-116">Byte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="1172e-117">Любой числовой тип (включая `SByte` и типы перечисления), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="1172e-117">Any numeric type (including `SByte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CChar`|[<span data-ttu-id="1172e-118">Тип данных Char</span><span class="sxs-lookup"><span data-stu-id="1172e-118">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="1172e-119">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="1172e-119">`String`, `Object`</span></span>|  
|`CDate`|[<span data-ttu-id="1172e-120">Тип данных Date</span><span class="sxs-lookup"><span data-stu-id="1172e-120">Date Data Type</span></span>](../../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="1172e-121">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="1172e-121">`String`, `Object`</span></span>|  
|`CDbl`|[<span data-ttu-id="1172e-122">Тип данных Double</span><span class="sxs-lookup"><span data-stu-id="1172e-122">Double Data Type</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="1172e-123">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="1172e-123">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CDec`|[<span data-ttu-id="1172e-124">Тип данных Decimal</span><span class="sxs-lookup"><span data-stu-id="1172e-124">Decimal Data Type</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="1172e-125">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="1172e-125">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CInt`|[<span data-ttu-id="1172e-126">Тип данных Integer</span><span class="sxs-lookup"><span data-stu-id="1172e-126">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="1172e-127">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="1172e-127">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CLng`|[<span data-ttu-id="1172e-128">Тип данных Long</span><span class="sxs-lookup"><span data-stu-id="1172e-128">Long Data Type</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="1172e-129">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="1172e-129">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CObj`|[<span data-ttu-id="1172e-130">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="1172e-130">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="1172e-131">Любой тип</span><span class="sxs-lookup"><span data-stu-id="1172e-131">Any type</span></span>|  
|`CSByte`|[<span data-ttu-id="1172e-132">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="1172e-132">SByte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="1172e-133">Любой числовой тип (включая `Byte` и типы перечисления), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="1172e-133">Any numeric type (including `Byte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CShort`|[<span data-ttu-id="1172e-134">Тип данных Short</span><span class="sxs-lookup"><span data-stu-id="1172e-134">Short Data Type</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="1172e-135">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="1172e-135">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CSng`|[<span data-ttu-id="1172e-136">Тип данных Single</span><span class="sxs-lookup"><span data-stu-id="1172e-136">Single Data Type</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="1172e-137">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="1172e-137">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CStr`|[<span data-ttu-id="1172e-138">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="1172e-138">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="1172e-139">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `Char`, `Char` массива, `Date`,`Object`</span><span class="sxs-lookup"><span data-stu-id="1172e-139">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `Char`, `Char` array, `Date`, `Object`</span></span>|  
|`CType`|<span data-ttu-id="1172e-140">Тип, заданный после запятой (`,`)</span><span class="sxs-lookup"><span data-stu-id="1172e-140">Type specified following the comma (`,`)</span></span>|<span data-ttu-id="1172e-141">При преобразовании в *простой тип данных* (включая массив простейших типов), же типы, которые разрешены для соответствующих зарезервированных слов преобразования</span><span class="sxs-lookup"><span data-stu-id="1172e-141">When converting to an *elementary data type* (including an array of an elementary type), the same types as allowed for the corresponding conversion keyword</span></span><br /><br /> <span data-ttu-id="1172e-142">При преобразовании в *составного типа*, он реализует интерфейсы и классы, от которых они наследуются</span><span class="sxs-lookup"><span data-stu-id="1172e-142">When converting to a *composite data type*, the interfaces it implements and the classes from which it inherits</span></span><br /><br /> <span data-ttu-id="1172e-143">При преобразовании класса или структуры, в которой имеются перегруженные `CType`, класса или структуры</span><span class="sxs-lookup"><span data-stu-id="1172e-143">When converting to a class or structure on which you have overloaded `CType`, that class or structure</span></span>|  
|`CUInt`|[<span data-ttu-id="1172e-144">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="1172e-144">UInteger Data Type</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="1172e-145">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="1172e-145">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CULng`|[<span data-ttu-id="1172e-146">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="1172e-146">ULong Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="1172e-147">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="1172e-147">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CUShort`|[<span data-ttu-id="1172e-148">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="1172e-148">UShort Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="1172e-149">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="1172e-149">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
  
## <a name="the-ctype-function"></a><span data-ttu-id="1172e-150">Функция CType</span><span class="sxs-lookup"><span data-stu-id="1172e-150">The CType Function</span></span>  
 <span data-ttu-id="1172e-151">[Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) имеет два аргумента.</span><span class="sxs-lookup"><span data-stu-id="1172e-151">The [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) operates on two arguments.</span></span> <span data-ttu-id="1172e-152">Во-первых, преобразуемое выражение, а второй — класс тип или объект назначения данных.</span><span class="sxs-lookup"><span data-stu-id="1172e-152">The first is the expression to be converted, and the second is the destination data type or object class.</span></span> <span data-ttu-id="1172e-153">Обратите внимание, что первый аргумент должен быть выражением, а не тип.</span><span class="sxs-lookup"><span data-stu-id="1172e-153">Note that the first argument must be an expression, not a type.</span></span>  
  
 <span data-ttu-id="1172e-154">`CType`— *встроенная функция*, то есть скомпилированный код делает преобразование, часто без создания функции вызова.</span><span class="sxs-lookup"><span data-stu-id="1172e-154">`CType` is an *inline function*, meaning the compiled code makes the conversion, often without generating a function call.</span></span> <span data-ttu-id="1172e-155">Это повышает производительность.</span><span class="sxs-lookup"><span data-stu-id="1172e-155">This improves performance.</span></span>  
  
 <span data-ttu-id="1172e-156">Сравнение `CType` с другим типом зарезервированных слов преобразования, в разделе [оператор DirectCast](../../../../visual-basic/language-reference/operators/directcast-operator.md) и [оператор TryCast](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1172e-156">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
### <a name="elementary-types"></a><span data-ttu-id="1172e-157">Простые типы</span><span class="sxs-lookup"><span data-stu-id="1172e-157">Elementary Types</span></span>  
 <span data-ttu-id="1172e-158">В следующем примере показано использование функции `CType`.</span><span class="sxs-lookup"><span data-stu-id="1172e-158">The following example demonstrates the use of `CType`.</span></span>  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### <a name="composite-types"></a><span data-ttu-id="1172e-159">Составные типы</span><span class="sxs-lookup"><span data-stu-id="1172e-159">Composite Types</span></span>  
 <span data-ttu-id="1172e-160">Можно использовать `CType` для преобразования значений в составной данных типов, а также простые типы.</span><span class="sxs-lookup"><span data-stu-id="1172e-160">You can use `CType` to convert values to composite data types as well as to elementary types.</span></span> <span data-ttu-id="1172e-161">Его также можно использовать для присвоения класса объекта типу одного из его интерфейсов, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1172e-161">You can also use it to coerce an object class to the type of one of its interfaces, as in the following example.</span></span>  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### <a name="array-types"></a><span data-ttu-id="1172e-162">Типы массивов</span><span class="sxs-lookup"><span data-stu-id="1172e-162">Array Types</span></span>  
 <span data-ttu-id="1172e-163">`CType`также можно преобразовать типы данных массивов, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1172e-163">`CType` can also convert array data types, as in the following example.</span></span>  
  
```  
Dim v() As classV  
Dim obArray() As Object  
' Assume some object array has been assigned to obArray.  
' Check for run-time type compatibility.  
If TypeOf obArray Is classV()  
    ' obArray can be converted to classV.  
    v = CType(obArray, classV())  
End If  
```  
  
 <span data-ttu-id="1172e-164">Дополнительные сведения и пример см. в разделе [преобразования массива](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="1172e-164">For more information and an example, see [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span></span>  
  
### <a name="types-defining-ctype"></a><span data-ttu-id="1172e-165">Типы, определение CType</span><span class="sxs-lookup"><span data-stu-id="1172e-165">Types Defining CType</span></span>  
 <span data-ttu-id="1172e-166">Можно определить `CType` в классе или структуре, определенных вами.</span><span class="sxs-lookup"><span data-stu-id="1172e-166">You can define `CType` on a class or structure you have defined.</span></span> <span data-ttu-id="1172e-167">Это дает возможность преобразования значений из типа класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="1172e-167">This allows you to convert values to and from the type of your class or structure.</span></span> <span data-ttu-id="1172e-168">Дополнительные сведения и пример см. в разделе [Практическое руководство: определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1172e-168">For more information and an example, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1172e-169">Значения, используемые с ключевым словом преобразования должен быть допустимым для целевого типа данных, или произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="1172e-169">Values used with a conversion keyword must be valid for the destination data type, or an error occurs.</span></span> <span data-ttu-id="1172e-170">Например, если при попытке преобразовать `Long` для `Integer`, значение `Long` должно быть в пределах допустимого диапазона для `Integer` тип данных.</span><span class="sxs-lookup"><span data-stu-id="1172e-170">For example, if you attempt to convert a `Long` to an `Integer`, the value of the `Long` must be within the valid range for the `Integer` data type.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="1172e-171">Указание `CType` для преобразования из одного типа класса в другой вызовет ошибку во время выполнения, если тип источника не является производным от конечного типа.</span><span class="sxs-lookup"><span data-stu-id="1172e-171">Specifying `CType` to convert from one class type to another fails at run time if the source type does not derive from the destination type.</span></span> <span data-ttu-id="1172e-172">Такой сбой вызовет исключение <xref:System.InvalidCastException>исключение.</xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="1172e-172">Such a failure throws an <xref:System.InvalidCastException> exception.</span></span>  
  
 <span data-ttu-id="1172e-173">Тем не менее если один из типов является структурой или определения класса, а определены `CType` для структуры или класса, преобразование может быть успешным, если оно удовлетворяет требованиям вашего `CType`.</span><span class="sxs-lookup"><span data-stu-id="1172e-173">However, if one of the types is a structure or class you have defined, and if you have defined `CType` on that structure or class, a conversion can succeed if it satisfies the requirements of your `CType`.</span></span> <span data-ttu-id="1172e-174">В разделе [Практическое руководство: определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1172e-174">See [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
 <span data-ttu-id="1172e-175">Выполнение явного преобразования называется также *приведение* выражение для данных типа или объект класса.</span><span class="sxs-lookup"><span data-stu-id="1172e-175">Performing an explicit conversion is also known as *casting* an expression to a given data type or object class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1172e-176">См. также</span><span class="sxs-lookup"><span data-stu-id="1172e-176">See Also</span></span>  
 <span data-ttu-id="1172e-177">[Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="1172e-177">[Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="1172e-178"> [Преобразование между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md) </span><span class="sxs-lookup"><span data-stu-id="1172e-178"> [Conversions Between Strings and Other Types](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md) </span></span>  
<span data-ttu-id="1172e-179"> [Практическое руководство: преобразование объекта к другому типу в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span><span class="sxs-lookup"><span data-stu-id="1172e-179"> [How to: Convert an Object to Another Type in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span></span>  
<span data-ttu-id="1172e-180"> [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span><span class="sxs-lookup"><span data-stu-id="1172e-180"> [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span></span>  
<span data-ttu-id="1172e-181"> [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="1172e-181"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="1172e-182"> [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="1172e-182"> [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="1172e-183"> [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="1172e-183"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)</span></span>
