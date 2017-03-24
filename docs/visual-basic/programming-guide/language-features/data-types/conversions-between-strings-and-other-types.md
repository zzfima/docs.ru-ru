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
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2d0a5fc7327ecd6339b5021e1b4cb87cc54bd2bc
ms.lasthandoff: 03/13/2017

---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>Преобразование значений между строковыми и другими типами (Visual Basic)
Можно преобразовать числовые, `Boolean`, или значение даты и времени `String`. Можно также преобразовать в обратном направлении — от строковых значений к числовым, `Boolean`, или `Date` — интерпретацией содержимого строки как значения, допустимого для конечного типа данных. Если это невозможно, возникает ошибка времени выполнения.  
  
 Преобразования для всех этих присваиваний в любом направлении являются сужающими преобразованиями. You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`). <xref:Microsoft.VisualBasic.Strings.Format%2A>И <xref:Microsoft.VisualBasic.Conversion.Val%2A>функции предоставляют дополнительные возможности управления преобразованиями строк и чисел.</xref:Microsoft.VisualBasic.Conversion.Val%2A> </xref:Microsoft.VisualBasic.Strings.Format%2A>  
  
 Если определены класс или структура, можно определить операторы преобразования типов между `String` и тип класса или структуры. Дополнительные сведения см. в разделе [Практическое руководство: определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="conversion-of-numbers-to-strings"></a>Преобразование чисел в строки  
 Можно использовать `Format` функции для преобразования числа в форматированную строку, которая может включать не только соответствующие цифры, но также символы форматирования, например знак валюты (например, `$`), тысяч разделители или *символы группировки цифр* (такие как `,`) и десятичный разделитель (такие как `.`). `Format`автоматически использует соответствующие символы согласно **язык и региональные стандарты** , заданные в Windows **панели управления**.  
  
 Обратите внимание, что объединение (`&`) оператор может преобразовать число в строку неявным образом, как показано в следующем примере.  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>Преобразование строк в числа  
 Можно использовать `Val` функции, чтобы явным образом преобразовать цифры в строке в число. `Val`анализирует строку, пока встретится знак, отличный от цифр, места, табуляции, перевода строки или период. Последовательности «& O» и «& H» изменяют основание системы счисления и завершают считывание. Пока не будет остановлено считывание, `Val` преобразует все соответствующие знаки в числовые значения. Например, следующая инструкция возвращает значение `141.825`.  
  
 `Val("   14   1.825 miles")`  
  
 При [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] преобразует строки в числовое значение, он использует **язык и региональные стандарты** , заданные в Windows **панели управления** интерпретировать тысяч разделителя, десятичный разделитель и обозначение денежной единицы. Это означает, что преобразование может быть выполнена успешно в один параметр, но не другого. Например `"$14.20"` допустимо в языковой стандарт английский (США), но не в любой французского языка.  
  
## <a name="see-also"></a>См. также  
 [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Практическое руководство: преобразование объекта к другому типу в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Знакомство с международными приложениями на платформе .NET Framework](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
