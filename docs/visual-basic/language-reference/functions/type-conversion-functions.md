---
title: Функции преобразования типов (Visual Basic)
ms.date: 10/24/2018
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
ms.openlocfilehash: 56dad921b2900061dbe2db0d8f1faaf759641f87
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148139"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="17078-102">Функции преобразования типов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17078-102">Type Conversion Functions (Visual Basic)</span></span>
<span data-ttu-id="17078-103">Эти функции являются компилируется путем подстановки, это означает, что код преобразования является частью кода, который вычисляет выражение.</span><span class="sxs-lookup"><span data-stu-id="17078-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="17078-104">Иногда отсутствует вызов процедуры для выполнения преобразований, что улучшает производительность.</span><span class="sxs-lookup"><span data-stu-id="17078-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="17078-105">Каждая функция преобразует выражение к определенному типу данных.</span><span class="sxs-lookup"><span data-stu-id="17078-105">Each function coerces an expression to a specific data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17078-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="17078-106">Syntax</span></span>  
  
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
  
## <a name="part"></a><span data-ttu-id="17078-107">Отделение</span><span class="sxs-lookup"><span data-stu-id="17078-107">Part</span></span>  
 `expression`  
 <span data-ttu-id="17078-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="17078-108">Required.</span></span> <span data-ttu-id="17078-109">Любое выражение типа источника данных.</span><span class="sxs-lookup"><span data-stu-id="17078-109">Any expression of the source data type.</span></span>  
  
## <a name="return-value-data-type"></a><span data-ttu-id="17078-110">Тип данных возвращаемого значения</span><span class="sxs-lookup"><span data-stu-id="17078-110">Return Value Data Type</span></span>  
 <span data-ttu-id="17078-111">Имя функции определяет тип данных значения, которое возвращается, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="17078-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>  
  
|<span data-ttu-id="17078-112">Имя функции</span><span class="sxs-lookup"><span data-stu-id="17078-112">Function name</span></span>|<span data-ttu-id="17078-113">Тип возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="17078-113">Return data type</span></span>|<span data-ttu-id="17078-114">Диапазон `expression` аргумент</span><span class="sxs-lookup"><span data-stu-id="17078-114">Range for `expression` argument</span></span>|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[<span data-ttu-id="17078-115">Логический тип данных</span><span class="sxs-lookup"><span data-stu-id="17078-115">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="17078-116">Любое допустимое `Char` или `String` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="17078-116">Any valid `Char` or `String` or numeric expression.</span></span>|  
|`CByte`|[<span data-ttu-id="17078-117">Тип данных Byte</span><span class="sxs-lookup"><span data-stu-id="17078-117">Byte Data Type</span></span>](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte.MinValue?displayProperty=nameWithType> <span data-ttu-id="17078-118">(0) через <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (без знака); дробная часть округляется.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="17078-118">(0) through <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="17078-119">Начиная с 15.8 Visual Basic, Visual Basic оптимизирует производительность вычислений с плавающей запятой, для преобразования байтов с помощью `CByte` функции; см. в разделе ["Примечания"](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="17078-119">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to byte conversion with the `CByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="17078-120">См. в разделе [пример CInt](#cint-example) приведен пример.</span><span class="sxs-lookup"><span data-stu-id="17078-120">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CChar`|[<span data-ttu-id="17078-121">Тип данных Char</span><span class="sxs-lookup"><span data-stu-id="17078-121">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="17078-122">Любое допустимое `Char` или `String` выражение; только первый символ `String` преобразуется; значение может быть от 0 до 65535 (без знака).</span><span class="sxs-lookup"><span data-stu-id="17078-122">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|  
|`CDate`|[<span data-ttu-id="17078-123">Тип данных Date</span><span class="sxs-lookup"><span data-stu-id="17078-123">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="17078-124">Любое допустимое представление даты и времени.</span><span class="sxs-lookup"><span data-stu-id="17078-124">Any valid representation of a date and time.</span></span>|  
|`CDbl`|[<span data-ttu-id="17078-125">Тип данных Double</span><span class="sxs-lookup"><span data-stu-id="17078-125">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="17078-126">-1, 79769313486231570E + 308 до - 4, 94065645841246544E-324 для отрицательных значений; 4.94065645841246544E-324 до 1, 79769313486231570E + 308 для положительных значений.</span><span class="sxs-lookup"><span data-stu-id="17078-126">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|  
|`CDec`|[<span data-ttu-id="17078-127">Тип данных Decimal</span><span class="sxs-lookup"><span data-stu-id="17078-127">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="17078-128">+/-79228162514264337593543950335 для целых чисел то есть числа без десятичных разрядов.</span><span class="sxs-lookup"><span data-stu-id="17078-128">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="17078-129">Для чисел с 28 десятичных разрядов диапазон — от +/-7,9228162514264337593543950335.</span><span class="sxs-lookup"><span data-stu-id="17078-129">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="17078-130">Наименьшее возможное число ненулевое значение — 0,0000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="17078-130">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|  
|`CInt`|[<span data-ttu-id="17078-131">Тип данных Integer</span><span class="sxs-lookup"><span data-stu-id="17078-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32.MinValue?displayProperty=nameWithType> <span data-ttu-id="17078-132">(-2147483648) через <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2 147 483 647); дробная часть округляется.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="17078-132">(-2,147,483,648) through <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2,147,483,647); fractional parts are rounded.<sup>1</sup></span></span> <br/><br/><span data-ttu-id="17078-133">Начиная с 15.8 Visual Basic, Visual Basic оптимизирует производительность вычислений с плавающей запятой в целое число, преобразование с `CInt` функции; см. в разделе ["Примечания"](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="17078-133">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to integer conversion with the `CInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="17078-134">См. в разделе [пример CInt](#cint-example) приведен пример.</span><span class="sxs-lookup"><span data-stu-id="17078-134">See the [CInt Example](#cint-example) section for an example.</span></span> |  
|`CLng`|[<span data-ttu-id="17078-135">Тип данных Long</span><span class="sxs-lookup"><span data-stu-id="17078-135">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)|<xref:System.Int64.MinValue?displayProperty=nameWithType> <span data-ttu-id="17078-136">(-9223372036854775808) через <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9223372036854775807); дробная часть округляется.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="17078-136">(-9,223,372,036,854,775,808) through <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9,223,372,036,854,775,807); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="17078-137">Начиная с 15.8 Visual Basic, Visual Basic оптимизирует производительность вычислений с плавающей запятой, для преобразования 64-разрядное целое число, с помощью `CLng` функции; см. в разделе ["Примечания"](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="17078-137">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 64-bit integer conversion with the `CLng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="17078-138">См. в разделе [пример CInt](#cint-example) приведен пример.</span><span class="sxs-lookup"><span data-stu-id="17078-138">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CObj`|[<span data-ttu-id="17078-139">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="17078-139">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="17078-140">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="17078-140">Any valid expression.</span></span>|  
|`CSByte`|[<span data-ttu-id="17078-141">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="17078-141">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte.MinValue?displayProperty=nameWithType> <span data-ttu-id="17078-142">(от -128) через <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); дробная часть округляется.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="17078-142">(-128) through <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="17078-143">Начиная с 15.8 Visual Basic, Visual Basic оптимизирует производительность вычислений с плавающей запятой, для преобразования байт со знаком с `CSByte` функции; см. в разделе ["Примечания"](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="17078-143">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to signed byte conversion with the `CSByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="17078-144">См. в разделе [пример CInt](#cint-example) приведен пример.</span><span class="sxs-lookup"><span data-stu-id="17078-144">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CShort`|[<span data-ttu-id="17078-145">Тип данных Short</span><span class="sxs-lookup"><span data-stu-id="17078-145">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)|<xref:System.Int16.MinValue?displayProperty=nameWithType> <span data-ttu-id="17078-146">(-32 768) до <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32 767); дробная часть округляется.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="17078-146">(-32,768) through <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32,767); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="17078-147">Начиная с 15.8 Visual Basic, Visual Basic оптимизирует производительность вычислений с плавающей запятой, для преобразования 16-разрядное целое число, с помощью `CShort` функции; см. в разделе ["Примечания"](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="17078-147">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 16-bit integer conversion with the `CShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="17078-148">См. в разделе [пример CInt](#cint-example) приведен пример.</span><span class="sxs-lookup"><span data-stu-id="17078-148">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CSng`|[<span data-ttu-id="17078-149">Тип данных Single</span><span class="sxs-lookup"><span data-stu-id="17078-149">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="17078-150">-3, 402823E + 38 до - 1, 401298E-45 для отрицательных значений; 1, 401298E-45 до 3, 402823E + 38 для положительных значений.</span><span class="sxs-lookup"><span data-stu-id="17078-150">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|  
|`CStr`|[<span data-ttu-id="17078-151">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="17078-151">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="17078-152">Возвращает для `CStr` зависят от `expression` аргумент.</span><span class="sxs-lookup"><span data-stu-id="17078-152">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="17078-153">См. в разделе [возвращаемые значения функции CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="17078-153">See [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>|  
|`CUInt`|[<span data-ttu-id="17078-154">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="17078-154">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32.MinValue?displayProperty=nameWithType> <span data-ttu-id="17078-155">(0) через <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4 294 967 295) (без знака); дробная часть округляется.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="17078-155">(0) through <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4,294,967,295) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="17078-156">Начиная с 15.8 Visual Basic, Visual Basic оптимизирует производительность вычислений с плавающей запятой в целое число без знака преобразования с помощью `CUInt` функции; см. в разделе ["Примечания"](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="17078-156">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned integer conversion with the `CUInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="17078-157">См. в разделе [пример CInt](#cint-example) приведен пример.</span><span class="sxs-lookup"><span data-stu-id="17078-157">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CULng`|[<span data-ttu-id="17078-158">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="17078-158">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64.MinValue?displayProperty=nameWithType> <span data-ttu-id="17078-159">(0) через <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18446744073709551615) (без знака); дробная часть округляется.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="17078-159">(0) through <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18,446,744,073,709,551,615) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="17078-160">Начиная с 15.8 Visual Basic, Visual Basic оптимизирует производительность вычислений с плавающей запятой в длинное целое без знака преобразования с помощью `CULng` функции; см. в разделе ["Примечания"](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="17078-160">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned long integer conversion with the `CULng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="17078-161">См. в разделе [пример CInt](#cint-example) приведен пример.</span><span class="sxs-lookup"><span data-stu-id="17078-161">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CUShort`|[<span data-ttu-id="17078-162">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="17078-162">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16.MinValue?displayProperty=nameWithType> <span data-ttu-id="17078-163">(0) через <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65 535) (без знака); дробная часть округляется.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="17078-163">(0) through <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65,535) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="17078-164">Начиная с 15.8 Visual Basic, Visual Basic оптимизирует производительность вычислений с плавающей запятой, для преобразования 16-разрядных целых беззнаковых с `CUShort` функции; см. в разделе ["Примечания"](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="17078-164">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned 16-bit integer conversion with the `CUShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="17078-165">См. в разделе [пример CInt](#cint-example) приведен пример.</span><span class="sxs-lookup"><span data-stu-id="17078-165">See the [CInt Example](#cint-example) section for an example.</span></span>|  
  
 <span data-ttu-id="17078-166"><sup>1</sup> дробных частей может быть причиной специальный тип округления вызываемой *банковское округление*.</span><span class="sxs-lookup"><span data-stu-id="17078-166"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="17078-167">Дополнительные сведения см. в подразделе «Примечания».</span><span class="sxs-lookup"><span data-stu-id="17078-167">See "Remarks" for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17078-168">Примечания</span><span class="sxs-lookup"><span data-stu-id="17078-168">Remarks</span></span>  
 <span data-ttu-id="17078-169">Как правило, следует использовать функции преобразования типов Visual Basic предпочтительнее, чем методы платформы .NET Framework например `ToString()`, либо на <xref:System.Convert> класса или для отдельного типа структуры или класса.</span><span class="sxs-lookup"><span data-stu-id="17078-169">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="17078-170">Функции языка Visual Basic предназначены для оптимального взаимодействия с кодом Visual Basic, и они смогут исходный код короче и удобнее для чтения.</span><span class="sxs-lookup"><span data-stu-id="17078-170">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="17078-171">Кроме того, методы преобразования платформы .NET Framework не всегда производят те же результаты, что функции языка Visual Basic, например, при преобразовании `Boolean` для `Integer`.</span><span class="sxs-lookup"><span data-stu-id="17078-171">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="17078-172">Дополнительные сведения см. в разделе [Устранение неполадок типы данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="17078-172">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  

<span data-ttu-id="17078-173">Начиная с Visual Basic 15.8, производительность плавающей-запятой в целочисленные преобразования оптимизирован при передаче <xref:System.Single> или <xref:System.Double> значение, возвращаемое следующими методами для одной из функций преобразования целого числа (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span><span class="sxs-lookup"><span data-stu-id="17078-173">Starting with Visual Basic 15.8, the performance of floating-point-to-integer conversion is optimized when you pass the <xref:System.Single> or <xref:System.Double> value returned by the following methods to one of the integer conversion functions (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

<span data-ttu-id="17078-174">Эта оптимизация позволяет коду, который выполняет большое количество преобразования целых чисел будет выполняться в два раза быстрее.</span><span class="sxs-lookup"><span data-stu-id="17078-174">This optimization allows code that does a large number of integer conversions to run up to twice as fast.</span></span> <span data-ttu-id="17078-175">В следующем примере показано эти оптимизированного плавающей-запятой в целочисленные преобразования:</span><span class="sxs-lookup"><span data-stu-id="17078-175">The following example illustrates these optimized floating-point-to-integer conversions:</span></span>

```vb
Dim s As Single = 173.7619
Dim d As Double = s 

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a><span data-ttu-id="17078-176">Поведение</span><span class="sxs-lookup"><span data-stu-id="17078-176">Behavior</span></span>  
  
-   **<span data-ttu-id="17078-177">Приведение типа.</span><span class="sxs-lookup"><span data-stu-id="17078-177">Coercion.</span></span>** <span data-ttu-id="17078-178">Как правило функции преобразования типов данных можно использовать для присвоения результат операции для определенного типа данных, а не тип данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="17078-178">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="17078-179">Например, использовать `CDec` для принудительного десятичному в случаях, где одиночной точности, двойной точности или целочисленные арифметические операции обычно занимает место.</span><span class="sxs-lookup"><span data-stu-id="17078-179">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>  
  
-   **<span data-ttu-id="17078-180">Сбой преобразования.</span><span class="sxs-lookup"><span data-stu-id="17078-180">Failed Conversions.</span></span>** <span data-ttu-id="17078-181">Если `expression` , передаваемое функции находится вне диапазона типа данных, на которое он будет преобразован, <xref:System.OverflowException> происходит.</span><span class="sxs-lookup"><span data-stu-id="17078-181">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>  
  
-   **<span data-ttu-id="17078-182">Дробные части.</span><span class="sxs-lookup"><span data-stu-id="17078-182">Fractional Parts.</span></span>** <span data-ttu-id="17078-183">При преобразовании нецелочисленное значение в целочисленный тип, функции преобразования целых чисел (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, и `CUShort`) Удаление Дробная часть и округляет значение до ближайшего целого.</span><span class="sxs-lookup"><span data-stu-id="17078-183">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>  
  
     <span data-ttu-id="17078-184">Если дробная часть равна точно 0,5, функции преобразования целых чисел округляет его для ближайшего четного целого.</span><span class="sxs-lookup"><span data-stu-id="17078-184">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="17078-185">Например 0,5 округляется до 0, а 1,5 и 2,5 округляются до 2.</span><span class="sxs-lookup"><span data-stu-id="17078-185">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="17078-186">Это иногда называется *банковское округление*, и предназначен для компенсации сдвигов, которые могут накапливаться при объединении таких чисел.</span><span class="sxs-lookup"><span data-stu-id="17078-186">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>  
  
     `CInt` <span data-ttu-id="17078-187">и `CLng` отличаются от <xref:Microsoft.VisualBasic.Conversion.Int%2A> и <xref:Microsoft.VisualBasic.Conversion.Fix%2A> функций, которые усечение, а не округление, дробная часть числа.</span><span class="sxs-lookup"><span data-stu-id="17078-187">and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="17078-188">Кроме того `Fix` и `Int` всегда возвращает значение одного типа данных при передаче в.</span><span class="sxs-lookup"><span data-stu-id="17078-188">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>  
  
-   **<span data-ttu-id="17078-189">Преобразования даты и времени.</span><span class="sxs-lookup"><span data-stu-id="17078-189">Date/Time Conversions.</span></span>** <span data-ttu-id="17078-190">Используйте <xref:Microsoft.VisualBasic.Information.IsDate%2A> функцию, чтобы определить, если значение можно преобразовать в дату и время.</span><span class="sxs-lookup"><span data-stu-id="17078-190">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> `CDate` <span data-ttu-id="17078-191">распознает литералы даты и времени, но не числовые значения.</span><span class="sxs-lookup"><span data-stu-id="17078-191">recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="17078-192">Для преобразования в Visual Basic 6.0 `Date` значение `Date` значение в Visual Basic 2005 или более поздних версий, можно использовать <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="17078-192">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>  
  
-   **<span data-ttu-id="17078-193">Нейтральный значений даты и времени.</span><span class="sxs-lookup"><span data-stu-id="17078-193">Neutral Date/Time Values.</span></span>** <span data-ttu-id="17078-194">[Тип данных Date](../../../visual-basic/language-reference/data-types/date-data-type.md) всегда содержит сведения о дате и времени.</span><span class="sxs-lookup"><span data-stu-id="17078-194">The [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="17078-195">В целях преобразования типов Visual Basic рассматривает 1/1/0001 (1 января 1 года) быть *нейтральным значением* для даты и 00:00:00 (полночь) могла быть нейтральным значением времени.</span><span class="sxs-lookup"><span data-stu-id="17078-195">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="17078-196">При преобразовании `Date` значение в строку `CStr` не включает нейтральные значения в результирующую строку.</span><span class="sxs-lookup"><span data-stu-id="17078-196">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="17078-197">Например, при преобразовании `#January 1, 0001 9:30:00#` в строку, результат равен «9:30:00 AM»; дата отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="17078-197">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="17078-198">Тем не менее, сведения о дате по-прежнему присутствует в исходном `Date` значение и могут быть извлечены с помощью функции например <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> функции.</span><span class="sxs-lookup"><span data-stu-id="17078-198">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>  
  
-   **<span data-ttu-id="17078-199">Учет языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="17078-199">Culture Sensitivity.</span></span>** <span data-ttu-id="17078-200">Функции преобразования типов, нежели строки выполняют преобразование, на основе текущих настроек языка и региональных параметров для приложения.</span><span class="sxs-lookup"><span data-stu-id="17078-200">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="17078-201">Например `CDate` распознает форматы даты в соответствии с настройкой языкового стандарта системы.</span><span class="sxs-lookup"><span data-stu-id="17078-201">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="17078-202">Необходимо указать день, месяц и год в правильном порядке для языка, или дата может интерпретироваться неправильно.</span><span class="sxs-lookup"><span data-stu-id="17078-202">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="17078-203">Длинный формат даты не распознается, если он содержит строку day of week, такие как «Среда».</span><span class="sxs-lookup"><span data-stu-id="17078-203">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>  
  
     <span data-ttu-id="17078-204">Если вам нужно преобразовать в или из строкового представления значения в формате, отличном от, указанного параметром языкового стандарта, нельзя использовать функции преобразования типов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="17078-204">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="17078-205">Чтобы сделать это, используйте `ToString(IFormatProvider)` и `Parse(String, IFormatProvider)` методы типа это значение.</span><span class="sxs-lookup"><span data-stu-id="17078-205">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="17078-206">Например, использовать <xref:System.Double.Parse%2A?displayProperty=nameWithType> при преобразовании строки в `Double`и использовать <xref:System.Double.ToString%2A?displayProperty=nameWithType> при преобразовании значения типа `Double` в строку.</span><span class="sxs-lookup"><span data-stu-id="17078-206">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>  
  
## <a name="ctype-function"></a><span data-ttu-id="17078-207">CType Function</span><span class="sxs-lookup"><span data-stu-id="17078-207">CType Function</span></span>  
 <span data-ttu-id="17078-208">[Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md) принимает второй аргумент — `typename`и приводит это `expression` для `typename`, где `typename` может быть любой тип данных, структуры, класса или интерфейса, для которого существует допустимое преобразование.</span><span class="sxs-lookup"><span data-stu-id="17078-208">The [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>  
  
 <span data-ttu-id="17078-209">Сравнение `CType` с других ключевых слов преобразования типов, см. в разделе [оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) и [оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="17078-209">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
## <a name="cbool-example"></a><span data-ttu-id="17078-210">Пример использования функции CBool</span><span class="sxs-lookup"><span data-stu-id="17078-210">CBool Example</span></span>  
 <span data-ttu-id="17078-211">В следующем примере используется `CBool` функцию для преобразования выражений для `Boolean` значения.</span><span class="sxs-lookup"><span data-stu-id="17078-211">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="17078-212">Если выражение имеет ненулевое значение, `CBool` возвращает `True`; в противном случае он возвращает `False`.</span><span class="sxs-lookup"><span data-stu-id="17078-212">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]  
  
## <a name="cbyte-example"></a><span data-ttu-id="17078-213">Пример использования функции CByte</span><span class="sxs-lookup"><span data-stu-id="17078-213">CByte Example</span></span>  
 <span data-ttu-id="17078-214">В следующем примере используется `CByte` функцию для преобразования выражения `Byte`.</span><span class="sxs-lookup"><span data-stu-id="17078-214">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]  
  
## <a name="cchar-example"></a><span data-ttu-id="17078-215">Пример использования функции CChar</span><span class="sxs-lookup"><span data-stu-id="17078-215">CChar Example</span></span>  
 <span data-ttu-id="17078-216">В следующем примере используется `CChar` функцию для преобразования первый символ `String` выражение `Char` типа.</span><span class="sxs-lookup"><span data-stu-id="17078-216">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]  
  
 <span data-ttu-id="17078-217">Входной аргумент для `CChar` должен иметь тип данных `Char` или `String`.</span><span class="sxs-lookup"><span data-stu-id="17078-217">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="17078-218">Нельзя использовать `CChar` для преобразования числа в символ, так как `CChar` не может принимать числового типа данных.</span><span class="sxs-lookup"><span data-stu-id="17078-218">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="17078-219">В следующем примере получается число, представляющее кодовую точку (код символа) и преобразует его в соответствующий символ.</span><span class="sxs-lookup"><span data-stu-id="17078-219">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="17078-220">Она использует <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> функции для получения строки из цифр, `CInt` для преобразования строки в тип `Integer`, и `ChrW` для преобразования числа к типу `Char`.</span><span class="sxs-lookup"><span data-stu-id="17078-220">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]  
  
## <a name="cdate-example"></a><span data-ttu-id="17078-221">Пример CDate</span><span class="sxs-lookup"><span data-stu-id="17078-221">CDate Example</span></span>  
 <span data-ttu-id="17078-222">В следующем примере используется `CDate` функции преобразования строк для `Date` значения.</span><span class="sxs-lookup"><span data-stu-id="17078-222">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="17078-223">В общем случае не рекомендуется жестко запрограммированного значения даты и времени, как строки (как показано в этом примере).</span><span class="sxs-lookup"><span data-stu-id="17078-223">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="17078-224">Используйте литералы даты и времени, например #Feb 12, 1969 # и # 4:45:23 PM #, вместо этого.</span><span class="sxs-lookup"><span data-stu-id="17078-224">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>  
  
 [!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]  
  
## <a name="cdbl-example"></a><span data-ttu-id="17078-225">Пример использования функции CDbl</span><span class="sxs-lookup"><span data-stu-id="17078-225">CDbl Example</span></span>  
 [!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]  
  
## <a name="cdec-example"></a><span data-ttu-id="17078-226">Пример CDec</span><span class="sxs-lookup"><span data-stu-id="17078-226">CDec Example</span></span>  
 <span data-ttu-id="17078-227">В следующем примере используется `CDec` функция для преобразования числовых значений для `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="17078-227">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]  
  
## <a name="cint-example"></a><span data-ttu-id="17078-228">Пример CInt</span><span class="sxs-lookup"><span data-stu-id="17078-228">CInt Example</span></span>  
 <span data-ttu-id="17078-229">В следующем примере используется `CInt` функция для преобразования значения `Integer`.</span><span class="sxs-lookup"><span data-stu-id="17078-229">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]  

## <a name="clng-example"></a><span data-ttu-id="17078-230">Пример использования функции CLng</span><span class="sxs-lookup"><span data-stu-id="17078-230">CLng Example</span></span>
 <span data-ttu-id="17078-231">В следующем примере используется `CLng` функцию для преобразования значения `Long`.</span><span class="sxs-lookup"><span data-stu-id="17078-231">The following example uses the `CLng` function to convert values to `Long`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]  
  
## <a name="cobj-example"></a><span data-ttu-id="17078-232">Пример CObj</span><span class="sxs-lookup"><span data-stu-id="17078-232">CObj Example</span></span>  
 <span data-ttu-id="17078-233">В следующем примере используется `CObj` функция для преобразования числовых значений для `Object`.</span><span class="sxs-lookup"><span data-stu-id="17078-233">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="17078-234">`Object` Переменная содержит только указатель размером 4 байта, которое указывает `Double` присвоено значение.</span><span class="sxs-lookup"><span data-stu-id="17078-234">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>  
  
 [!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]  
  
## <a name="csbyte-example"></a><span data-ttu-id="17078-235">Пример использования функции CSByte</span><span class="sxs-lookup"><span data-stu-id="17078-235">CSByte Example</span></span>  
 <span data-ttu-id="17078-236">В следующем примере используется `CSByte` функция для преобразования числовых значений для `SByte`.</span><span class="sxs-lookup"><span data-stu-id="17078-236">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]  
  
## <a name="cshort-example"></a><span data-ttu-id="17078-237">Пример использования функции CShort</span><span class="sxs-lookup"><span data-stu-id="17078-237">CShort Example</span></span>  
 <span data-ttu-id="17078-238">В следующем примере используется `CShort` функция для преобразования числовых значений для `Short`.</span><span class="sxs-lookup"><span data-stu-id="17078-238">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]  
  
## <a name="csng-example"></a><span data-ttu-id="17078-239">Пример использования функции CSng</span><span class="sxs-lookup"><span data-stu-id="17078-239">CSng Example</span></span>  
 <span data-ttu-id="17078-240">В следующем примере используется `CSng` функцию для преобразования значения `Single`.</span><span class="sxs-lookup"><span data-stu-id="17078-240">The following example uses the `CSng` function to convert values to `Single`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]  
  
## <a name="cstr-example"></a><span data-ttu-id="17078-241">Пример использования функции CStr</span><span class="sxs-lookup"><span data-stu-id="17078-241">CStr Example</span></span>  
 <span data-ttu-id="17078-242">В следующем примере используется `CStr` функция для преобразования числовых значений для `String`.</span><span class="sxs-lookup"><span data-stu-id="17078-242">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]  
  
 <span data-ttu-id="17078-243">В следующем примере используется `CStr` функцию для преобразования `Date` значения `String` значения.</span><span class="sxs-lookup"><span data-stu-id="17078-243">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>  
  
 [!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]  
  
 `CStr` <span data-ttu-id="17078-244">всегда выводит `Date` значение в стандартном кратком формате для текущего языкового стандарта, например, «6/15/2003 4:35:47 PM».</span><span class="sxs-lookup"><span data-stu-id="17078-244">always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="17078-245">Тем не менее `CStr` подавляет *нейтральные значения* из 1/1/0001 для даты и 00:00:00 для времени.</span><span class="sxs-lookup"><span data-stu-id="17078-245">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>  
  
 <span data-ttu-id="17078-246">Дополнительные сведения о значениях, возвращаемых `CStr`, см. в разделе [возвращаемые значения функции CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="17078-246">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>  
  
## <a name="cuint-example"></a><span data-ttu-id="17078-247">Пример использования функции CUInt</span><span class="sxs-lookup"><span data-stu-id="17078-247">CUInt Example</span></span>  
 <span data-ttu-id="17078-248">В следующем примере используется `CUInt` функция для преобразования числовых значений для `UInteger`.</span><span class="sxs-lookup"><span data-stu-id="17078-248">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]  
  
## <a name="culng-example"></a><span data-ttu-id="17078-249">Пример использования функции CULng</span><span class="sxs-lookup"><span data-stu-id="17078-249">CULng Example</span></span>  
 <span data-ttu-id="17078-250">В следующем примере используется `CULng` функция для преобразования числовых значений для `ULong`.</span><span class="sxs-lookup"><span data-stu-id="17078-250">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]  
  
## <a name="cushort-example"></a><span data-ttu-id="17078-251">Пример использования функции CShort</span><span class="sxs-lookup"><span data-stu-id="17078-251">CUShort Example</span></span>  
 <span data-ttu-id="17078-252">В следующем примере используется `CUShort` функция для преобразования числовых значений для `UShort`.</span><span class="sxs-lookup"><span data-stu-id="17078-252">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]  
  
## <a name="see-also"></a><span data-ttu-id="17078-253">См. также</span><span class="sxs-lookup"><span data-stu-id="17078-253">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- <xref:Microsoft.VisualBasic.Strings.Format%2A>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:Microsoft.VisualBasic.Conversion.Oct%2A>
- <xref:Microsoft.VisualBasic.Conversion.Str%2A>
- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="17078-254">Функции преобразования</span><span class="sxs-lookup"><span data-stu-id="17078-254">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [<span data-ttu-id="17078-255">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="17078-255">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
