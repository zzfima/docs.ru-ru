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
ms.openlocfilehash: 1e42fca7800a76cab10fd60058e34d31ae8b8830
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907326"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>Преобразование значений между строковыми и другими типами (Visual Basic)
Можно преобразовать числовые, `Boolean`, или значение для даты и времени `String`. Также можно преобразовать в обратном направлении — из строкового значения в числовой, `Boolean`, или `Date` — интерпретацией содержимое строки как допустимое значение целевого типа данных. Если это невозможно, возникает ошибка времени выполнения.  
  
 Преобразования сужающие преобразования для все эти назначения, в любом направлении. Следует использовать ключевые слова преобразования типов (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, и `CType`). <xref:Microsoft.VisualBasic.Strings.Format%2A> И <xref:Microsoft.VisualBasic.Conversion.Val%2A> предоставляют дополнительные возможности управления преобразованиями строк и чисел.  
  
 Если вы определили, класса или структуры, можно определить операторы преобразования типов между `String` и тип класса или структуры. Дополнительные сведения см. в разделе [Как Определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="conversion-of-numbers-to-strings"></a>Преобразование чисел в строки  
 Можно использовать `Format` функцию для преобразования числа в форматированную строку, которая может включать не только соответствующие цифры, но также символы форматирования, например знак валюты (например, `$`), тысячи разделители или *разделителей символы* (такие как `,`) и десятичные разделители (такие как `.`). `Format` автоматически использует соответствующие символы согласно **региональные параметры** , заданные в Windows **панели управления**.  
  
 Обратите внимание, что объединение (`&`) оператор может преобразовать число в строку неявным образом, как показано в следующем примере.  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>Преобразования строк в числа  
 Можно использовать `Val` функцию для явного преобразования знаков в строке в число. `Val` Считывает строку, пока встретится символ, отличный от цифр, места, табуляции, перевода строки или период. Последовательности «& O» и «& H» изменяют основание системы счисления и завершают считывание. Пока не будет остановлено считывание, `Val` преобразует все соответствующие символы в числовое значение. Например, следующая инструкция возвращает значение `141.825`.  
  
 `Val("   14   1.825 miles")`  
  
 Когда Visual Basic строка преобразуется в числовое значение, он использует **региональные параметры** , заданные в Windows **панели управления** для интерпретации разрядов разделитель, десятичного разделителя и символ валюты. Это означает, что преобразование может быть выполнена успешно при выполнении одного параметра, но не другого. Например `"$14.20"` приемлемо для языкового стандарта Английский (США), но не в любой французского языка.  
  
## <a name="see-also"></a>См. также

- [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Практическое руководство. Преобразование объекта к другому типу в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [Преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Знакомство с международными приложениями на платформе .NET Framework](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
