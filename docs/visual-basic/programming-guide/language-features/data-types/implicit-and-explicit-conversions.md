---
title: Явные и неявные преобразования (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- variables [Visual Basic], changing data type
- casting
- conversions [Visual Basic], data type
- type conversion [Visual Basic], implicit conversions
- CType function [Visual Basic], conversions
- casting, data types
- data type conversion [Visual Basic], explicit
- type conversion [Visual Basic], explicit conversions
- data types [Visual Basic], casting
- conversions [Visual Basic], implicit
- explicit data type conversions [Visual Basic]
- conversions [Visual Basic]
- changing data types [Visual Basic]
- conversions [Visual Basic], explicit
- data type conversion [Visual Basic], implicit
- implicit data type conversions [Visual Basic]
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
ms.openlocfilehash: 09d96b304ba3bcf2a9de2812ce37ae69dba73a41
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44037244"
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a><span data-ttu-id="dce61-102">Явные и неявные преобразования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dce61-102">Implicit and Explicit Conversions (Visual Basic)</span></span>
<span data-ttu-id="dce61-103">*Неявное преобразование* не требует специального синтаксиса в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="dce61-103">An *implicit conversion* does not require any special syntax in the source code.</span></span> <span data-ttu-id="dce61-104">В следующем примере Visual Basic неявно преобразует значение `k` значение с плавающей запятой одиночной точности, перед назначением его `q`.</span><span class="sxs-lookup"><span data-stu-id="dce61-104">In the following example, Visual Basic implicitly converts the value of `k` to a single-precision floating-point value before assigning it to `q`.</span></span>  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 <span data-ttu-id="dce61-105">*Явное преобразование* используется ключевое слово преобразования типа.</span><span class="sxs-lookup"><span data-stu-id="dce61-105">An *explicit conversion* uses a type conversion keyword.</span></span> <span data-ttu-id="dce61-106">Visual Basic предоставляет несколько зарезервированных слов, которые приводят выражение в круглые скобки, чтобы в нужный тип данных.</span><span class="sxs-lookup"><span data-stu-id="dce61-106">Visual Basic provides several such keywords, which coerce an expression in parentheses to the desired data type.</span></span> <span data-ttu-id="dce61-107">Эти ключевые слова действуют аналогично функциям, но компилятор создает встроенный код, поэтому выполнение будет немного быстрее, чем при вызове функции.</span><span class="sxs-lookup"><span data-stu-id="dce61-107">These keywords act like functions, but the compiler generates the code inline, so execution is slightly faster than with a function call.</span></span>  
  
 <span data-ttu-id="dce61-108">В следующее расширение в предыдущем примере `CInt` ключевое слово преобразует значение `q` обратно в целое число перед назначением его `k`.</span><span class="sxs-lookup"><span data-stu-id="dce61-108">In the following extension of the preceding example, the `CInt` keyword converts the value of `q` back to an integer before assigning it to `k`.</span></span>  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## <a name="conversion-keywords"></a><span data-ttu-id="dce61-109">Ключевые слова преобразований</span><span class="sxs-lookup"><span data-stu-id="dce61-109">Conversion Keywords</span></span>  
 <span data-ttu-id="dce61-110">В следующей таблице показаны ключевые слова преобразований.</span><span class="sxs-lookup"><span data-stu-id="dce61-110">The following table shows the available conversion keywords.</span></span>  
  
|<span data-ttu-id="dce61-111">Ключевое слово преобразования типа</span><span class="sxs-lookup"><span data-stu-id="dce61-111">Type conversion keyword</span></span>|<span data-ttu-id="dce61-112">Преобразует выражение в тип данных</span><span class="sxs-lookup"><span data-stu-id="dce61-112">Converts an expression to data type</span></span>|<span data-ttu-id="dce61-113">Допустимые типы данных выражение для преобразования</span><span class="sxs-lookup"><span data-stu-id="dce61-113">Allowable data types of expression to be converted</span></span>|  
|---|---|---|  
|`CBool`|[<span data-ttu-id="dce61-114">Логический тип данных</span><span class="sxs-lookup"><span data-stu-id="dce61-114">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="dce61-115">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="dce61-115">Any numeric type (including `Byte`, `SByte`, and enumerated types), `String`, `Object`</span></span>|  
|`CByte`|[<span data-ttu-id="dce61-116">Тип данных Byte</span><span class="sxs-lookup"><span data-stu-id="dce61-116">Byte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="dce61-117">Любой числовой тип (включая `SByte` и типы перечисления), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="dce61-117">Any numeric type (including `SByte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CChar`|[<span data-ttu-id="dce61-118">Тип данных Char</span><span class="sxs-lookup"><span data-stu-id="dce61-118">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="dce61-119">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="dce61-119">`String`, `Object`</span></span>|  
|`CDate`|[<span data-ttu-id="dce61-120">Тип данных Date</span><span class="sxs-lookup"><span data-stu-id="dce61-120">Date Data Type</span></span>](../../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="dce61-121">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="dce61-121">`String`, `Object`</span></span>|  
|`CDbl`|[<span data-ttu-id="dce61-122">Тип данных Double</span><span class="sxs-lookup"><span data-stu-id="dce61-122">Double Data Type</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="dce61-123">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="dce61-123">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CDec`|[<span data-ttu-id="dce61-124">Тип данных Decimal</span><span class="sxs-lookup"><span data-stu-id="dce61-124">Decimal Data Type</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="dce61-125">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="dce61-125">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CInt`|[<span data-ttu-id="dce61-126">Тип данных Integer</span><span class="sxs-lookup"><span data-stu-id="dce61-126">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="dce61-127">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="dce61-127">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CLng`|[<span data-ttu-id="dce61-128">Тип данных Long</span><span class="sxs-lookup"><span data-stu-id="dce61-128">Long Data Type</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="dce61-129">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="dce61-129">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CObj`|[<span data-ttu-id="dce61-130">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="dce61-130">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="dce61-131">Любой тип</span><span class="sxs-lookup"><span data-stu-id="dce61-131">Any type</span></span>|  
|`CSByte`|[<span data-ttu-id="dce61-132">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="dce61-132">SByte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="dce61-133">Любой числовой тип (включая `Byte` и типы перечисления), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="dce61-133">Any numeric type (including `Byte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CShort`|[<span data-ttu-id="dce61-134">Тип данных Short</span><span class="sxs-lookup"><span data-stu-id="dce61-134">Short Data Type</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="dce61-135">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="dce61-135">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CSng`|[<span data-ttu-id="dce61-136">Тип данных Single</span><span class="sxs-lookup"><span data-stu-id="dce61-136">Single Data Type</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="dce61-137">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="dce61-137">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CStr`|[<span data-ttu-id="dce61-138">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="dce61-138">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="dce61-139">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `Char`, `Char` массива, `Date`, `Object`</span><span class="sxs-lookup"><span data-stu-id="dce61-139">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `Char`, `Char` array, `Date`, `Object`</span></span>|  
|`CType`|<span data-ttu-id="dce61-140">Тип, заданный после запятой (`,`)</span><span class="sxs-lookup"><span data-stu-id="dce61-140">Type specified following the comma (`,`)</span></span>|<span data-ttu-id="dce61-141">При преобразовании в *простой тип данных* типов (включая массив простейших типов), так же, как для соответствующих зарезервированных слов преобразования</span><span class="sxs-lookup"><span data-stu-id="dce61-141">When converting to an *elementary data type* (including an array of an elementary type), the same types as allowed for the corresponding conversion keyword</span></span><br /><br /> <span data-ttu-id="dce61-142">При преобразовании в *составной тип данных*, он реализует интерфейсы и классы, от которых он наследует</span><span class="sxs-lookup"><span data-stu-id="dce61-142">When converting to a *composite data type*, the interfaces it implements and the classes from which it inherits</span></span><br /><br /> <span data-ttu-id="dce61-143">При преобразовании в класс или структура, в которой имеются перегруженные `CType`, класса или структуры</span><span class="sxs-lookup"><span data-stu-id="dce61-143">When converting to a class or structure on which you have overloaded `CType`, that class or structure</span></span>|  
|`CUInt`|[<span data-ttu-id="dce61-144">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="dce61-144">UInteger Data Type</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="dce61-145">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="dce61-145">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CULng`|[<span data-ttu-id="dce61-146">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="dce61-146">ULong Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="dce61-147">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="dce61-147">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CUShort`|[<span data-ttu-id="dce61-148">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="dce61-148">UShort Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="dce61-149">Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="dce61-149">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
  
## <a name="the-ctype-function"></a><span data-ttu-id="dce61-150">Функция CType</span><span class="sxs-lookup"><span data-stu-id="dce61-150">The CType Function</span></span>  
 <span data-ttu-id="dce61-151">[Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) имеет два аргумента.</span><span class="sxs-lookup"><span data-stu-id="dce61-151">The [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) operates on two arguments.</span></span> <span data-ttu-id="dce61-152">Первый — это выражение для преобразования, а вторым – класс типа или объект назначения данных.</span><span class="sxs-lookup"><span data-stu-id="dce61-152">The first is the expression to be converted, and the second is the destination data type or object class.</span></span> <span data-ttu-id="dce61-153">Обратите внимание на то, что первый аргумент должен быть выражением, а не типом.</span><span class="sxs-lookup"><span data-stu-id="dce61-153">Note that the first argument must be an expression, not a type.</span></span>  
  
 <span data-ttu-id="dce61-154">`CType` — *встроенная функция*, то есть скомпилированный код делает преобразование, часто без формирования функцию вызвать.</span><span class="sxs-lookup"><span data-stu-id="dce61-154">`CType` is an *inline function*, meaning the compiled code makes the conversion, often without generating a function call.</span></span> <span data-ttu-id="dce61-155">Это повышает производительность.</span><span class="sxs-lookup"><span data-stu-id="dce61-155">This improves performance.</span></span>  
  
 <span data-ttu-id="dce61-156">Сравнение `CType` с других ключевых слов преобразования типов, см. в разделе [оператор DirectCast](../../../../visual-basic/language-reference/operators/directcast-operator.md) и [оператор TryCast](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="dce61-156">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
### <a name="elementary-types"></a><span data-ttu-id="dce61-157">Простые типы</span><span class="sxs-lookup"><span data-stu-id="dce61-157">Elementary Types</span></span>  
 <span data-ttu-id="dce61-158">В следующем примере показано использование функции `CType`.</span><span class="sxs-lookup"><span data-stu-id="dce61-158">The following example demonstrates the use of `CType`.</span></span>  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### <a name="composite-types"></a><span data-ttu-id="dce61-159">Составные типы</span><span class="sxs-lookup"><span data-stu-id="dce61-159">Composite Types</span></span>  
 <span data-ttu-id="dce61-160">Можно использовать `CType` для преобразования значений в составные типы данных также относительно простыми типами.</span><span class="sxs-lookup"><span data-stu-id="dce61-160">You can use `CType` to convert values to composite data types as well as to elementary types.</span></span> <span data-ttu-id="dce61-161">Можно также используется для присвоения объекту класса тип одного из интерфейсов, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="dce61-161">You can also use it to coerce an object class to the type of one of its interfaces, as in the following example.</span></span>  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### <a name="array-types"></a><span data-ttu-id="dce61-162">Типы массивов</span><span class="sxs-lookup"><span data-stu-id="dce61-162">Array Types</span></span>  
 <span data-ttu-id="dce61-163">`CType` также можно преобразовать типы данных массивов, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="dce61-163">`CType` can also convert array data types, as in the following example.</span></span>  
  
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
  
 <span data-ttu-id="dce61-164">Дополнительные сведения и пример см. в разделе [преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="dce61-164">For more information and an example, see [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span></span>  
  
### <a name="types-defining-ctype"></a><span data-ttu-id="dce61-165">Типы, определение CType</span><span class="sxs-lookup"><span data-stu-id="dce61-165">Types Defining CType</span></span>  
 <span data-ttu-id="dce61-166">Вы можете определить `CType` для класса или структуры, которые вы определили.</span><span class="sxs-lookup"><span data-stu-id="dce61-166">You can define `CType` on a class or structure you have defined.</span></span> <span data-ttu-id="dce61-167">Это позволяет преобразовывать значения из типа класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="dce61-167">This allows you to convert values to and from the type of your class or structure.</span></span> <span data-ttu-id="dce61-168">Дополнительные сведения и пример см. в разделе [как: определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="dce61-168">For more information and an example, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dce61-169">Значения, используемые с ключевым словом преобразование должно быть допустимым для целевого типа данных, или произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="dce61-169">Values used with a conversion keyword must be valid for the destination data type, or an error occurs.</span></span> <span data-ttu-id="dce61-170">Например, если при попытке преобразовать `Long` для `Integer`, значение `Long` должно быть в допустимом диапазоне для `Integer` тип данных.</span><span class="sxs-lookup"><span data-stu-id="dce61-170">For example, if you attempt to convert a `Long` to an `Integer`, the value of the `Long` must be within the valid range for the `Integer` data type.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="dce61-171">Указание `CType` для преобразования из одного типа класса в другой вызовет ошибку во время выполнения, если исходный тип не является производным от типа назначения.</span><span class="sxs-lookup"><span data-stu-id="dce61-171">Specifying `CType` to convert from one class type to another fails at run time if the source type does not derive from the destination type.</span></span> <span data-ttu-id="dce61-172">Такой сбой вызывает <xref:System.InvalidCastException> исключение.</span><span class="sxs-lookup"><span data-stu-id="dce61-172">Such a failure throws an <xref:System.InvalidCastException> exception.</span></span>  
  
 <span data-ttu-id="dce61-173">Тем не менее если один из типов структуры или класса, вы определили, а также если вы определили `CType` для структуры или класса, преобразование может быть успешным, если он удовлетворяет требованиям вашего `CType`.</span><span class="sxs-lookup"><span data-stu-id="dce61-173">However, if one of the types is a structure or class you have defined, and if you have defined `CType` on that structure or class, a conversion can succeed if it satisfies the requirements of your `CType`.</span></span> <span data-ttu-id="dce61-174">См. в разделе [как: определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="dce61-174">See [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
 <span data-ttu-id="dce61-175">Выполнение явного преобразования также называется *приведения* выражение к классу данных типа или объекта.</span><span class="sxs-lookup"><span data-stu-id="dce61-175">Performing an explicit conversion is also known as *casting* an expression to a given data type or object class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dce61-176">См. также</span><span class="sxs-lookup"><span data-stu-id="dce61-176">See Also</span></span>  
 [<span data-ttu-id="dce61-177">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dce61-177">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="dce61-178">Преобразования значений между строковыми и другими типами</span><span class="sxs-lookup"><span data-stu-id="dce61-178">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="dce61-179">Практическое: преобразование объекта в другой тип в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dce61-179">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [<span data-ttu-id="dce61-180">Структуры</span><span class="sxs-lookup"><span data-stu-id="dce61-180">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="dce61-181">Типы данных</span><span class="sxs-lookup"><span data-stu-id="dce61-181">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="dce61-182">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="dce61-182">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="dce61-183">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="dce61-183">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
