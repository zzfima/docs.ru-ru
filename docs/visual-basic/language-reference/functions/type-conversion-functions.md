---
title: Функции преобразования типов (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
ms.openlocfilehash: c9222bdb31f4fd7c792d5a50c100067e29e9d537
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605086"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="73378-102">Функции преобразования типов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73378-102">Type Conversion Functions (Visual Basic)</span></span>
<span data-ttu-id="73378-103">Эти функции являются скомпилированных встроенный, это означает, что код преобразования является частью кода, вычисляет выражение.</span><span class="sxs-lookup"><span data-stu-id="73378-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="73378-104">Иногда отсутствует вызов процедуры для выполнения преобразований, что улучшает производительность.</span><span class="sxs-lookup"><span data-stu-id="73378-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="73378-105">Каждая функция преобразует выражение к определенному типу данных.</span><span class="sxs-lookup"><span data-stu-id="73378-105">Each function coerces an expression to a specific data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73378-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73378-106">Syntax</span></span>  
  
```  
CBool(expression)  
CByte(expression)  
CChar(expression)  
CDate(expression)  
CDbl(expression)  
CDec(expression)  
CInt(expression)  
CLng(expression)  
CObj(expression)  
CSByte(expression)  
CShort(expression)  
CSng(expression)  
CStr(expression)  
CUInt(expression)  
CULng(expression)  
CUShort(expression)  
```  
  
## <a name="part"></a><span data-ttu-id="73378-107">Отделение</span><span class="sxs-lookup"><span data-stu-id="73378-107">Part</span></span>  
 `expression`  
 <span data-ttu-id="73378-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="73378-108">Required.</span></span> <span data-ttu-id="73378-109">Любое выражение исходного типа данных.</span><span class="sxs-lookup"><span data-stu-id="73378-109">Any expression of the source data type.</span></span>  
  
## <a name="return-value-data-type"></a><span data-ttu-id="73378-110">Тип данных возвращаемого значения</span><span class="sxs-lookup"><span data-stu-id="73378-110">Return Value Data Type</span></span>  
 <span data-ttu-id="73378-111">Имя функции определяет тип данных значение, которое возвращается, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="73378-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>  
  
|<span data-ttu-id="73378-112">Имя функции</span><span class="sxs-lookup"><span data-stu-id="73378-112">Function name</span></span>|<span data-ttu-id="73378-113">Тип возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="73378-113">Return data type</span></span>|<span data-ttu-id="73378-114">Диапазон `expression` аргумент</span><span class="sxs-lookup"><span data-stu-id="73378-114">Range for `expression` argument</span></span>|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[<span data-ttu-id="73378-115">Логический тип данных</span><span class="sxs-lookup"><span data-stu-id="73378-115">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="73378-116">Любое допустимое `Char` или `String` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="73378-116">Any valid `Char` or `String` or numeric expression.</span></span>|  
|`CByte`|[<span data-ttu-id="73378-117">Тип данных Byte</span><span class="sxs-lookup"><span data-stu-id="73378-117">Byte Data Type</span></span>](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="73378-118">от 0 до 255 (без знака); Дробная часть округляется. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="73378-118">0 through 255 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CChar`|[<span data-ttu-id="73378-119">Тип данных Char</span><span class="sxs-lookup"><span data-stu-id="73378-119">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="73378-120">Любое допустимое `Char` или `String` выражения; только первый символ `String` преобразуется; значение может быть от 0 до 65535 (без знака).</span><span class="sxs-lookup"><span data-stu-id="73378-120">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|  
|`CDate`|[<span data-ttu-id="73378-121">Тип данных Date</span><span class="sxs-lookup"><span data-stu-id="73378-121">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="73378-122">Любое допустимое представление даты и времени.</span><span class="sxs-lookup"><span data-stu-id="73378-122">Any valid representation of a date and time.</span></span>|  
|`CDbl`|[<span data-ttu-id="73378-123">Тип данных Double</span><span class="sxs-lookup"><span data-stu-id="73378-123">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="73378-124">-1, 79769313486231570E + 308 до - 4, 94065645841246544E-324 для отрицательных значений; 4.94065645841246544E-324 до 1, 79769313486231570E + 308 для положительных значений.</span><span class="sxs-lookup"><span data-stu-id="73378-124">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|  
|`CDec`|[<span data-ttu-id="73378-125">Тип данных Decimal</span><span class="sxs-lookup"><span data-stu-id="73378-125">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="73378-126">+/-79228162514264337593543950335 для целых чисел, то есть числа без десятичных разрядов.</span><span class="sxs-lookup"><span data-stu-id="73378-126">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="73378-127">Для чисел с 28 десятичных разрядов диапазон — от +/-7,9228162514264337593543950335.</span><span class="sxs-lookup"><span data-stu-id="73378-127">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="73378-128">Наименьшее возможное ненулевое число это 0.0000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="73378-128">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|  
|`CInt`|[<span data-ttu-id="73378-129">Тип данных Integer</span><span class="sxs-lookup"><span data-stu-id="73378-129">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="73378-130">от -2147483648 до 2 147 483 647; Дробная часть округляется. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="73378-130">-2,147,483,648 through 2,147,483,647; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CLng`|[<span data-ttu-id="73378-131">Тип данных Long</span><span class="sxs-lookup"><span data-stu-id="73378-131">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="73378-132">-9223372036854775808 до 9223372036854775807; Дробная часть округляется. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="73378-132">-9,223,372,036,854,775,808 through 9,223,372,036,854,775,807; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CObj`|[<span data-ttu-id="73378-133">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="73378-133">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="73378-134">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="73378-134">Any valid expression.</span></span>|  
|`CSByte`|[<span data-ttu-id="73378-135">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="73378-135">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="73378-136">от -128 до 127; Дробная часть округляется. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="73378-136">-128 through 127; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CShort`|[<span data-ttu-id="73378-137">Тип данных Short</span><span class="sxs-lookup"><span data-stu-id="73378-137">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="73378-138">-32 768 до 32 767; Дробная часть округляется. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="73378-138">-32,768 through 32,767; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CSng`|[<span data-ttu-id="73378-139">Тип данных Single</span><span class="sxs-lookup"><span data-stu-id="73378-139">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="73378-140">-3, 402823E + 38 до - 1, 401298E-45 для отрицательных значений; 1, 401298E-45 до 3, 402823E + 38 для положительных значений.</span><span class="sxs-lookup"><span data-stu-id="73378-140">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|  
|`CStr`|[<span data-ttu-id="73378-141">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="73378-141">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="73378-142">Возвращает для `CStr` зависят от `expression` аргумент.</span><span class="sxs-lookup"><span data-stu-id="73378-142">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="73378-143">В разделе [возвращаемые значения функции CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="73378-143">See [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>|  
|`CUInt`|[<span data-ttu-id="73378-144">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="73378-144">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="73378-145">от 0 до 4 294 967 295 (без знака); Дробная часть округляется. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="73378-145">0 through 4,294,967,295 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CULng`|[<span data-ttu-id="73378-146">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="73378-146">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="73378-147">от 0 до 18446744073709551615 (без знака); Дробная часть округляется. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="73378-147">0 through 18,446,744,073,709,551,615 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CUShort`|[<span data-ttu-id="73378-148">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="73378-148">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="73378-149">от 0 до 65 535 (без знака); Дробная часть округляется. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="73378-149">0 through 65,535 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
  
 <span data-ttu-id="73378-150"><sup>1</sup> дробных частей может быть причиной специальный тип округления вызываемой *банковское округление*.</span><span class="sxs-lookup"><span data-stu-id="73378-150"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="73378-151">Дополнительные сведения в разделе «Примечания».</span><span class="sxs-lookup"><span data-stu-id="73378-151">See "Remarks" for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73378-152">Примечания</span><span class="sxs-lookup"><span data-stu-id="73378-152">Remarks</span></span>  
 <span data-ttu-id="73378-153">Как правило, следует использовать функции преобразования типов Visual Basic предпочтительнее, чем методы платформы .NET Framework например `ToString()`, либо на <xref:System.Convert> класса или класса или структуры отдельного типа.</span><span class="sxs-lookup"><span data-stu-id="73378-153">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="73378-154">Функции языка Visual Basic предназначены для оптимального взаимодействия с Visual Basic, и они позволят исходный код короче и удобнее для чтения.</span><span class="sxs-lookup"><span data-stu-id="73378-154">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="73378-155">Кроме того, методы преобразования .NET Framework не всегда производят те же результаты, как функции Visual Basic, например, при преобразовании `Boolean` для `Integer`.</span><span class="sxs-lookup"><span data-stu-id="73378-155">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="73378-156">Дополнительные сведения см. в разделе [Устранение неполадок типы данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="73378-156">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="73378-157">Поведение</span><span class="sxs-lookup"><span data-stu-id="73378-157">Behavior</span></span>  
  
-   <span data-ttu-id="73378-158">**Приведение типа.**</span><span class="sxs-lookup"><span data-stu-id="73378-158">**Coercion.**</span></span> <span data-ttu-id="73378-159">Как правило функции преобразования типов данных можно использовать для присвоения результат операции имеет определенный тип данных, а не тип данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="73378-159">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="73378-160">Например, использовать `CDec` для принудительного десятичному в случаях, где одиночной точности, двойной точности или целочисленные арифметические операции обычно происходящим.</span><span class="sxs-lookup"><span data-stu-id="73378-160">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>  
  
-   <span data-ttu-id="73378-161">**Сбой преобразования.**</span><span class="sxs-lookup"><span data-stu-id="73378-161">**Failed Conversions.**</span></span> <span data-ttu-id="73378-162">Если `expression` передан функции находится вне диапазона типа данных, на который он преобразуется, <xref:System.OverflowException> происходит.</span><span class="sxs-lookup"><span data-stu-id="73378-162">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>  
  
-   <span data-ttu-id="73378-163">**Дробная часть.**</span><span class="sxs-lookup"><span data-stu-id="73378-163">**Fractional Parts.**</span></span> <span data-ttu-id="73378-164">При преобразовании нецелочисленное значение целочисленного типа, функции преобразования целых чисел (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, и `CUShort`) Удаление Дробная часть и округляют значение до ближайшего целого числа.</span><span class="sxs-lookup"><span data-stu-id="73378-164">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>  
  
     <span data-ttu-id="73378-165">Если дробная часть равна точно 0,5, функции преобразования целых чисел округления для ближайшего четного целого.</span><span class="sxs-lookup"><span data-stu-id="73378-165">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="73378-166">Например 0,5 округляется до 0, а 1,5 и 2,5 округляются до 2.</span><span class="sxs-lookup"><span data-stu-id="73378-166">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="73378-167">Это иногда называется *банковское округление*, и его целью является компенсация сдвигов, которые могут накапливаться при сложении многих таких чисел.</span><span class="sxs-lookup"><span data-stu-id="73378-167">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>  
  
     <span data-ttu-id="73378-168">`CInt` и `CLng` отличаются от <xref:Microsoft.VisualBasic.Conversion.Int%2A> и <xref:Microsoft.VisualBasic.Conversion.Fix%2A> функций, которые усечение, а не округляют дробную часть числа.</span><span class="sxs-lookup"><span data-stu-id="73378-168">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="73378-169">Кроме того `Fix` и `Int` всегда возвращают значение того же типа данных при передаче в.</span><span class="sxs-lookup"><span data-stu-id="73378-169">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>  
  
-   <span data-ttu-id="73378-170">**Дата и время преобразования.**</span><span class="sxs-lookup"><span data-stu-id="73378-170">**Date/Time Conversions.**</span></span> <span data-ttu-id="73378-171">Используйте <xref:Microsoft.VisualBasic.Information.IsDate%2A> функцию, чтобы определить, если значение можно преобразовать в дату и время.</span><span class="sxs-lookup"><span data-stu-id="73378-171">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="73378-172">`CDate` распознает литералы даты и времени, но не числовые значения.</span><span class="sxs-lookup"><span data-stu-id="73378-172">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="73378-173">Для преобразования Visual Basic 6.0 `Date` значение `Date` в языке Visual Basic 2005 или более поздней версии, можно использовать <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> метода.</span><span class="sxs-lookup"><span data-stu-id="73378-173">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="73378-174">**Нейтральные значения даты и времени.**</span><span class="sxs-lookup"><span data-stu-id="73378-174">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="73378-175">[Тип данных Date](../../../visual-basic/language-reference/data-types/date-data-type.md) всегда содержит сведения о дате и времени.</span><span class="sxs-lookup"><span data-stu-id="73378-175">The [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="73378-176">В целях преобразования типов Visual Basic рассматривает 1/1/0001 (1 января 1 года) быть *нейтральным значением* для даты и 00:00:00 (полночь) будет нейтральным значением времени.</span><span class="sxs-lookup"><span data-stu-id="73378-176">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="73378-177">Если вы преобразуете `Date` значения в строку `CStr` включает нейтральные значения в результирующую строку.</span><span class="sxs-lookup"><span data-stu-id="73378-177">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="73378-178">Например, если вы преобразуете `#January 1, 0001 9:30:00#` в строку, результат будет «9:30:00 AM»; дата отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="73378-178">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="73378-179">Тем не менее, сведения о дате по-прежнему присутствует в исходной коллекции `Date` значение и может быть восстановлен с помощью функции например <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> функции.</span><span class="sxs-lookup"><span data-stu-id="73378-179">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>  
  
-   <span data-ttu-id="73378-180">**Восприимчивость языка и региональных параметров.**</span><span class="sxs-lookup"><span data-stu-id="73378-180">**Culture Sensitivity.**</span></span> <span data-ttu-id="73378-181">Функции преобразования типов, включающие строки преобразований на основе текущих параметров языка и региональных параметров для приложения.</span><span class="sxs-lookup"><span data-stu-id="73378-181">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="73378-182">Например `CDate` распознает форматы даты согласно региональным параметрам системы.</span><span class="sxs-lookup"><span data-stu-id="73378-182">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="73378-183">Необходимо указать день, месяц и год в правильном порядке для языка или дата может интерпретироваться неправильно.</span><span class="sxs-lookup"><span data-stu-id="73378-183">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="73378-184">Длинный формат даты не распознается, если он содержит строки день недели, например «Среда».</span><span class="sxs-lookup"><span data-stu-id="73378-184">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>  
  
     <span data-ttu-id="73378-185">Если требуется преобразовать в или из строкового представления значения в формате, отличном от того, задаваемого языка, нельзя использовать функции преобразования типов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="73378-185">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="73378-186">Чтобы сделать это, используйте `ToString(IFormatProvider)` и `Parse(String, IFormatProvider)` методы типа этого значения.</span><span class="sxs-lookup"><span data-stu-id="73378-186">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="73378-187">Например, использовать <xref:System.Double.Parse%2A?displayProperty=nameWithType> при преобразовании строки в `Double`и использовать <xref:System.Double.ToString%2A?displayProperty=nameWithType> при преобразовании значения типа `Double` в строку.</span><span class="sxs-lookup"><span data-stu-id="73378-187">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>  
  
## <a name="ctype-function"></a><span data-ttu-id="73378-188">CType Function</span><span class="sxs-lookup"><span data-stu-id="73378-188">CType Function</span></span>  
 <span data-ttu-id="73378-189">[Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md) получает в качестве второго аргумента `typename`и приводит `expression` для `typename`, где `typename` может быть любой тип данных, структуры, класса или интерфейса, для которого существует допустимое преобразование.</span><span class="sxs-lookup"><span data-stu-id="73378-189">The [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>  
  
 <span data-ttu-id="73378-190">Сравнение `CType` с других ключевых слов преобразования типов, в разделе [оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) и [оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="73378-190">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
## <a name="cbool-example"></a><span data-ttu-id="73378-191">Пример использования функции CBool</span><span class="sxs-lookup"><span data-stu-id="73378-191">CBool Example</span></span>  
 <span data-ttu-id="73378-192">В следующем примере используется `CBool` функцию для преобразования выражений для `Boolean` значения.</span><span class="sxs-lookup"><span data-stu-id="73378-192">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="73378-193">Если результатом выражения является ненулевое значение `CBool` возвращает `True`; в противном случае возвращается значение `False`.</span><span class="sxs-lookup"><span data-stu-id="73378-193">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#1](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_1.vb)]  
  
## <a name="cbyte-example"></a><span data-ttu-id="73378-194">Пример использования функции CByte</span><span class="sxs-lookup"><span data-stu-id="73378-194">CByte Example</span></span>  
 <span data-ttu-id="73378-195">В следующем примере используется `CByte` функцию для преобразования выражения `Byte`.</span><span class="sxs-lookup"><span data-stu-id="73378-195">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#2](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_2.vb)]  
  
## <a name="cchar-example"></a><span data-ttu-id="73378-196">Пример использования функции CChar</span><span class="sxs-lookup"><span data-stu-id="73378-196">CChar Example</span></span>  
 <span data-ttu-id="73378-197">В следующем примере используется `CChar` функцию для преобразования первого символа `String` выражение `Char` типа.</span><span class="sxs-lookup"><span data-stu-id="73378-197">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#3](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_3.vb)]  
  
 <span data-ttu-id="73378-198">Входной аргумент для `CChar` должен иметь тип данных `Char` или `String`.</span><span class="sxs-lookup"><span data-stu-id="73378-198">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="73378-199">Нельзя использовать `CChar` для преобразования числа в символ, поскольку `CChar` не может принимать числового типа данных.</span><span class="sxs-lookup"><span data-stu-id="73378-199">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="73378-200">В следующем примере получается число, представляющее кодовую точку (код знака) и преобразует его в соответствующий символ.</span><span class="sxs-lookup"><span data-stu-id="73378-200">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="73378-201">Она использует <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> функции для получения строки из цифр, `CInt` для преобразования строки в тип `Integer`, и `ChrW` для преобразования числа к типу `Char`.</span><span class="sxs-lookup"><span data-stu-id="73378-201">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#4](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_4.vb)]  
  
## <a name="cdate-example"></a><span data-ttu-id="73378-202">Пример использования функции CDate</span><span class="sxs-lookup"><span data-stu-id="73378-202">CDate Example</span></span>  
 <span data-ttu-id="73378-203">В следующем примере используется `CDate` функцию для преобразования строк для `Date` значения.</span><span class="sxs-lookup"><span data-stu-id="73378-203">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="73378-204">В общем случае не рекомендуется жестко запрограммированные значения даты и время в виде строк (как показано в следующем примере).</span><span class="sxs-lookup"><span data-stu-id="73378-204">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="73378-205">Используйте литералы даты и времени, например #Feb 12, 1969 # и # 4:45:23 PM #, вместо этого.</span><span class="sxs-lookup"><span data-stu-id="73378-205">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>  
  
 [!code-vb[VbVbalrFunctions#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_5.vb)]  
  
## <a name="cdbl-example"></a><span data-ttu-id="73378-206">Пример использования функции CDbl</span><span class="sxs-lookup"><span data-stu-id="73378-206">CDbl Example</span></span>  
 [!code-vb[VbVbalrFunctions#6](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_6.vb)]  
  
## <a name="cdec-example"></a><span data-ttu-id="73378-207">Пример использования функции CDec</span><span class="sxs-lookup"><span data-stu-id="73378-207">CDec Example</span></span>  
 <span data-ttu-id="73378-208">В следующем примере используется `CDec` функцию для преобразования числовых значений для `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="73378-208">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#7](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_7.vb)]  
  
## <a name="cint-example"></a><span data-ttu-id="73378-209">Пример использования функции CInt</span><span class="sxs-lookup"><span data-stu-id="73378-209">CInt Example</span></span>  
 <span data-ttu-id="73378-210">В следующем примере используется `CInt` функции, чтобы преобразовать значение в `Integer`.</span><span class="sxs-lookup"><span data-stu-id="73378-210">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_8.vb)]  
  
## <a name="clng-example"></a><span data-ttu-id="73378-211">Пример использования функции CLng</span><span class="sxs-lookup"><span data-stu-id="73378-211">CLng Example</span></span>  
 <span data-ttu-id="73378-212">В следующем примере используется `CLng` функцию для преобразования значения `Long`.</span><span class="sxs-lookup"><span data-stu-id="73378-212">The following example uses the `CLng` function to convert values to `Long`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#9](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_9.vb)]  
  
## <a name="cobj-example"></a><span data-ttu-id="73378-213">Пример использования функции CObj</span><span class="sxs-lookup"><span data-stu-id="73378-213">CObj Example</span></span>  
 <span data-ttu-id="73378-214">В следующем примере используется `CObj` функцию для преобразования числовых значений для `Object`.</span><span class="sxs-lookup"><span data-stu-id="73378-214">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="73378-215">`Object` Переменная содержит только 4 байтовый указатель, указывающая на `Double` присвоенного значения.</span><span class="sxs-lookup"><span data-stu-id="73378-215">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>  
  
 [!code-vb[VbVbalrFunctions#10](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_10.vb)]  
  
## <a name="csbyte-example"></a><span data-ttu-id="73378-216">Пример использования функции CSByte</span><span class="sxs-lookup"><span data-stu-id="73378-216">CSByte Example</span></span>  
 <span data-ttu-id="73378-217">В следующем примере используется `CSByte` функцию для преобразования числовых значений для `SByte`.</span><span class="sxs-lookup"><span data-stu-id="73378-217">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#11](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_11.vb)]  
  
## <a name="cshort-example"></a><span data-ttu-id="73378-218">Пример использования функции CShort</span><span class="sxs-lookup"><span data-stu-id="73378-218">CShort Example</span></span>  
 <span data-ttu-id="73378-219">В следующем примере используется `CShort` функцию для преобразования числовых значений для `Short`.</span><span class="sxs-lookup"><span data-stu-id="73378-219">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#12](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_12.vb)]  
  
## <a name="csng-example"></a><span data-ttu-id="73378-220">Пример использования функции CSng</span><span class="sxs-lookup"><span data-stu-id="73378-220">CSng Example</span></span>  
 <span data-ttu-id="73378-221">В следующем примере используется `CSng` функцию для преобразования значения `Single`.</span><span class="sxs-lookup"><span data-stu-id="73378-221">The following example uses the `CSng` function to convert values to `Single`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#13](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_13.vb)]  
  
## <a name="cstr-example"></a><span data-ttu-id="73378-222">Пример использования функции CStr</span><span class="sxs-lookup"><span data-stu-id="73378-222">CStr Example</span></span>  
 <span data-ttu-id="73378-223">В следующем примере используется `CStr` функцию для преобразования числовых значений для `String`.</span><span class="sxs-lookup"><span data-stu-id="73378-223">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#14](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_14.vb)]  
  
 <span data-ttu-id="73378-224">В следующем примере используется `CStr` функцию для преобразования `Date` значения `String` значения.</span><span class="sxs-lookup"><span data-stu-id="73378-224">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>  
  
 [!code-vb[VbVbalrFunctions#15](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_15.vb)]  
  
 <span data-ttu-id="73378-225">`CStr` всегда выводит `Date` значение в стандартном кратком формате для текущего языкового стандарта, например, «6/15/2003 4:35:47 PM».</span><span class="sxs-lookup"><span data-stu-id="73378-225">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="73378-226">Тем не менее `CStr` подавляет *нейтральные значения* из 1/1/0001 00:00:00, время и даты.</span><span class="sxs-lookup"><span data-stu-id="73378-226">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>  
  
 <span data-ttu-id="73378-227">Дополнительные сведения по значениям, возвращаемым методом `CStr`, в разделе [возвращаемые значения функции CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="73378-227">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>  
  
## <a name="cuint-example"></a><span data-ttu-id="73378-228">Пример использования функции CUInt</span><span class="sxs-lookup"><span data-stu-id="73378-228">CUInt Example</span></span>  
 <span data-ttu-id="73378-229">В следующем примере используется `CUInt` функцию для преобразования числовых значений для `UInteger`.</span><span class="sxs-lookup"><span data-stu-id="73378-229">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#16](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_16.vb)]  
  
## <a name="culng-example"></a><span data-ttu-id="73378-230">Пример использования функции CULng</span><span class="sxs-lookup"><span data-stu-id="73378-230">CULng Example</span></span>  
 <span data-ttu-id="73378-231">В следующем примере используется `CULng` функцию для преобразования числовых значений для `ULong`.</span><span class="sxs-lookup"><span data-stu-id="73378-231">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_17.vb)]  
  
## <a name="cushort-example"></a><span data-ttu-id="73378-232">Пример CUShort</span><span class="sxs-lookup"><span data-stu-id="73378-232">CUShort Example</span></span>  
 <span data-ttu-id="73378-233">В следующем примере используется `CUShort` функцию для преобразования числовых значений для `UShort`.</span><span class="sxs-lookup"><span data-stu-id="73378-233">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#18](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_18.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="73378-234">См. также</span><span class="sxs-lookup"><span data-stu-id="73378-234">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 <xref:Microsoft.VisualBasic.Strings.Format%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Oct%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Str%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [<span data-ttu-id="73378-235">Функции преобразования</span><span class="sxs-lookup"><span data-stu-id="73378-235">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [<span data-ttu-id="73378-236">Преобразования типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="73378-236">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
