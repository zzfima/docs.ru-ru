---
title: Преобразование значений между строковыми и другими типами (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
ms.openlocfilehash: 40a28d664bc6ed3d094ccc7c342d6411fe88fd7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650573"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>Преобразование значений между строковыми и другими типами (Visual Basic)
Можно преобразовать числовые, `Boolean`, или значение даты и времени `String`. Также можно преобразовать в обратном направлении — от строковых значений к числовым, `Boolean`, или `Date` — интерпретацией содержимое строки как допустимое значение целевого типа данных. Если это невозможно, возникает ошибка времени выполнения.  
  
 Преобразования сужающие преобразования для всех этих присваиваний в любом направлении. Следует использовать ключевых слов преобразования типов (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, и `CType`). <xref:Microsoft.VisualBasic.Strings.Format%2A> И <xref:Microsoft.VisualBasic.Conversion.Val%2A> предоставляют дополнительные возможности управления преобразованиями строк и чисел.  
  
 Если вы определили класс или структура, можно определить операторы преобразования типов между `String` и тип класса или структуры. Дополнительные сведения см. в разделе [как: определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="conversion-of-numbers-to-strings"></a>Преобразование чисел в строки  
 Можно использовать `Format` функции для преобразования числа в форматированную строку, которая может включать не только соответствующие цифры, а также символы форматирования, например знак валюты (например, `$`), тысячи разделители или *группировки символы* (такие как `,`) и десятичный разделитель (такие как `.`). `Format` автоматически использует соответствующие символы согласно **язык и региональные стандарты** , заданные в Windows **панели управления**.  
  
 Обратите внимание, что объединение (`&`) оператор может преобразовать число в строку неявным образом, как показано в следующем примере.  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>Преобразование строк в числа  
 Можно использовать `Val` для явного преобразования знаков в строке в число. `Val` анализирует строку, пока встретится знак, отличный от цифры, пробел, вкладки, перевода строки или точки. Последовательности «& O» и «& H» изменяют основание системы счисления и завершают считывание. Пока не будет остановлено считывание, `Val` преобразует все соответствующие знаки в числовые значения. Например, следующая инструкция возвращает значение `141.825`.  
  
 `Val("   14   1.825 miles")`  
  
 Когда Visual Basic строка преобразуется в числовое значение, он использует **язык и региональные стандарты** , заданные в Windows **панели управления** для интерпретации разрядов разделитель, десятичного разделителя и символ валюты. Это означает, что преобразование может завершиться успешно в разделе один параметр, но не другого. Например `"$14.20"` допустима в языковом стандарте английского языка (США), но не в любой французского языка.  
  
## <a name="see-also"></a>См. также  
 [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Как: преобразование объекта к другому типу в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [Преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Знакомство с международными приложениями на платформе .NET Framework](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
