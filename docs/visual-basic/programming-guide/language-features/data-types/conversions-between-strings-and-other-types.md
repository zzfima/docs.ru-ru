---
title: "Преобразование между строковыми и другими типами (Visual Basic) | Документы Microsoft"
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
- data type conversion, string
- conversions, type
- string conversion
- conversions, data type
- type conversion, string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
caps.latest.revision: 16
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
ms.openlocfilehash: 34eb32cb6e640d681db6853aaa164d84acca7e4f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a><span data-ttu-id="3715a-102">Преобразование значений между строковыми и другими типами (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3715a-102">Conversions Between Strings and Other Types (Visual Basic)</span></span>
<span data-ttu-id="3715a-103">Можно преобразовать числовые, `Boolean`, или значение даты и времени `String`.</span><span class="sxs-lookup"><span data-stu-id="3715a-103">You can convert a numeric, `Boolean`, or date/time value to a `String`.</span></span> <span data-ttu-id="3715a-104">Можно также преобразовать в обратном направлении — от строковых значений к числовым, `Boolean`, или `Date` — интерпретацией содержимого строки как значения, допустимого для конечного типа данных.</span><span class="sxs-lookup"><span data-stu-id="3715a-104">You can also convert in the reverse direction — from a string value to numeric, `Boolean`, or `Date` — provided the contents of the string can be interpreted as a valid value of the destination data type.</span></span> <span data-ttu-id="3715a-105">Если это невозможно, возникает ошибка времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="3715a-105">If they cannot, a run-time error occurs.</span></span>  
  
 <span data-ttu-id="3715a-106">Преобразования для всех этих присваиваний в любом направлении являются сужающими преобразованиями.</span><span class="sxs-lookup"><span data-stu-id="3715a-106">The conversions for all these assignments, in either direction, are narrowing conversions.</span></span> <span data-ttu-id="3715a-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span><span class="sxs-lookup"><span data-stu-id="3715a-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span></span> <span data-ttu-id="3715a-108"><xref:Microsoft.VisualBasic.Strings.Format%2A>И <xref:Microsoft.VisualBasic.Conversion.Val%2A>функции предоставляют дополнительные возможности управления преобразованиями строк и чисел.</xref:Microsoft.VisualBasic.Conversion.Val%2A> </xref:Microsoft.VisualBasic.Strings.Format%2A></span><span class="sxs-lookup"><span data-stu-id="3715a-108">The <xref:Microsoft.VisualBasic.Strings.Format%2A> and <xref:Microsoft.VisualBasic.Conversion.Val%2A> functions give you additional control over conversions between strings and numbers.</span></span>  
  
 <span data-ttu-id="3715a-109">Если определены класс или структура, можно определить операторы преобразования типов между `String` и тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="3715a-109">If you have defined a class or structure, you can define type conversion operators between `String` and the type of your class or structure.</span></span> <span data-ttu-id="3715a-110">Дополнительные сведения см. в разделе [Практическое руководство: определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="3715a-110">For more information, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="conversion-of-numbers-to-strings"></a><span data-ttu-id="3715a-111">Преобразование чисел в строки</span><span class="sxs-lookup"><span data-stu-id="3715a-111">Conversion of Numbers to Strings</span></span>  
 <span data-ttu-id="3715a-112">Можно использовать `Format` функции для преобразования числа в форматированную строку, которая может включать не только соответствующие цифры, но также символы форматирования, например знак валюты (например, `$`), тысяч разделители или *символы группировки цифр* (такие как `,`) и десятичный разделитель (такие как `.`).</span><span class="sxs-lookup"><span data-stu-id="3715a-112">You can use the `Format` function to convert a number to a formatted string, which can include not only the appropriate digits but also formatting symbols such as a currency sign (such as `$`), thousands separators or *digit grouping symbols* (such as `,`), and a decimal separator (such as `.`).</span></span> <span data-ttu-id="3715a-113">`Format`автоматически использует соответствующие символы согласно **язык и региональные стандарты** , заданные в Windows **панели управления**.</span><span class="sxs-lookup"><span data-stu-id="3715a-113">`Format` automatically uses the appropriate symbols according to the **Regional Options** settings specified in the Windows **Control Panel**.</span></span>  
  
 <span data-ttu-id="3715a-114">Обратите внимание, что объединение (`&`) оператор может преобразовать число в строку неявным образом, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3715a-114">Note that the concatenation (`&`) operator can convert a number to a string implicitly, as the following example shows.</span></span>  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a><span data-ttu-id="3715a-115">Преобразование строк в числа</span><span class="sxs-lookup"><span data-stu-id="3715a-115">Conversion of Strings to Numbers</span></span>  
 <span data-ttu-id="3715a-116">Можно использовать `Val` функции, чтобы явным образом преобразовать цифры в строке в число.</span><span class="sxs-lookup"><span data-stu-id="3715a-116">You can use the `Val` function to explicitly convert the digits in a string to a number.</span></span> <span data-ttu-id="3715a-117">`Val`анализирует строку, пока встретится знак, отличный от цифр, места, табуляции, перевода строки или период.</span><span class="sxs-lookup"><span data-stu-id="3715a-117">`Val` reads the string until it encounters a character other than a digit, space, tab, line feed, or period.</span></span> <span data-ttu-id="3715a-118">Последовательности «& O» и «& H» изменяют основание системы счисления и завершают считывание.</span><span class="sxs-lookup"><span data-stu-id="3715a-118">The sequences "&O" and "&H" alter the base of the number system and terminate the scanning.</span></span> <span data-ttu-id="3715a-119">Пока не будет остановлено считывание, `Val` преобразует все соответствующие знаки в числовые значения.</span><span class="sxs-lookup"><span data-stu-id="3715a-119">Until it stops reading, `Val` converts all appropriate characters to a numeric value.</span></span> <span data-ttu-id="3715a-120">Например, следующая инструкция возвращает значение `141.825`.</span><span class="sxs-lookup"><span data-stu-id="3715a-120">For example, the following statement returns the value `141.825`.</span></span>  
  
 `Val("   14   1.825 miles")`  
  
 <span data-ttu-id="3715a-121">При [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] преобразует строки в числовое значение, он использует **язык и региональные стандарты** , заданные в Windows **панели управления** интерпретировать тысяч разделителя, десятичный разделитель и обозначение денежной единицы.</span><span class="sxs-lookup"><span data-stu-id="3715a-121">When [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] converts a string to a numeric value, it uses the **Regional Options** settings specified in the Windows **Control Panel** to interpret the thousands separator, decimal separator, and currency symbol.</span></span> <span data-ttu-id="3715a-122">Это означает, что преобразование может быть выполнена успешно в один параметр, но не другого.</span><span class="sxs-lookup"><span data-stu-id="3715a-122">This means that a conversion might succeed under one setting but not another.</span></span> <span data-ttu-id="3715a-123">Например `"$14.20"` допустимо в языковой стандарт английский (США), но не в любой французского языка.</span><span class="sxs-lookup"><span data-stu-id="3715a-123">For example, `"$14.20"` is acceptable in the English (United States) locale but not in any French locale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3715a-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3715a-124">See Also</span></span>  
 <span data-ttu-id="3715a-125">[Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="3715a-125">[Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="3715a-126"> [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="3715a-126"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span></span>  
<span data-ttu-id="3715a-127"> [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="3715a-127"> [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="3715a-128"> [Практическое руководство: преобразование объекта к другому типу в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span><span class="sxs-lookup"><span data-stu-id="3715a-128"> [How to: Convert an Object to Another Type in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span></span>  
<span data-ttu-id="3715a-129"> [Преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="3715a-129"> [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md) </span></span>  
<span data-ttu-id="3715a-130"> [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="3715a-130"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="3715a-131"> [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="3715a-131"> [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="3715a-132"> [Знакомство с международными приложениями на платформе .NET Framework](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)</span><span class="sxs-lookup"><span data-stu-id="3715a-132"> [Introduction to International Applications Based on the .NET Framework](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)</span></span>
