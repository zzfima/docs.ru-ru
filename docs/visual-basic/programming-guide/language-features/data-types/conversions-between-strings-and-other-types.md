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
ms.openlocfilehash: 06dabbb5d5dfbfb545f01afb157fd532ca0551df
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197334"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>Преобразование значений между строковыми и другими типами (Visual Basic)
Можно преобразовать числовое, `Boolean` или значение даты и времени в `String`. Можно также преобразовать в обратном направлении — от строкового значения к числовому, `Boolean` или `Date` — при условии, что содержимое строки может интерпретироваться как допустимое значение целевого типа данных. Если они не могут, возникает ошибка времени выполнения.  
  
 Преобразования для всех этих назначений в любом направлении представляют собой сужающие преобразования. Следует использовать ключевые слова для преобразования типов (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort` , 3 и 4). Функции <xref:Microsoft.VisualBasic.Strings.Format%2A> и <xref:Microsoft.VisualBasic.Conversion.Val%2A> обеспечивают дополнительный контроль над преобразованиями между строками и числами.  
  
 Если вы определили класс или структуру, можно определить операторы преобразования типов между `String` и типом класса или структуры. Дополнительные сведения см. в разделе [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="conversion-of-numbers-to-strings"></a>Преобразование чисел в строки  
 Функцию `Format` можно использовать для преобразования числа в отформатированную строку, которая может включать не только соответствующие цифры, но и символы форматирования, такие как знак валюты (например, `$`), разделители групп разрядов или *символы группирования цифр* (например, @no __t_3) и десятичный разделитель (например, `.`). `Format` автоматически использует соответствующие символы в соответствии с **региональными** параметрами, заданными на **панели управления**Windows.  
  
 Обратите внимание, что оператор конкатенации (`&`) может преобразовать число в строку неявным образом, как показано в следующем примере.  
  
```vb  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>Преобразование строк в числа  
 Функцию `Val` можно использовать для явного преобразования цифр в строке в число. `Val` считывает строку, пока не встретится символ, отличный от цифры, пробела, табуляции, перевода строки или точки. Последовательности "& O" и "& H" изменяют основание системы счисления и завершают сканирование. Пока не будет остановлено чтение, `Val` преобразует все соответствующие символы в числовое значение. Например, следующая инструкция возвращает значение `141.825`.  
  
 `Val("   14   1.825 miles")`  
  
 Когда Visual Basic преобразует строку в числовое значение, она использует **региональные параметры** , заданные на **панели управления** Windows, для интерпретации разделителя групп разрядов, десятичного разделителя и символа валюты. Это означает, что преобразование может быть выполнено в одном параметре, но не в другом. Например, `"$14.20"` допустимы в языковом стандарте English (США), но не на французском языке.  
  
## <a name="see-also"></a>См. также

- [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Как преобразовать объект в другой тип в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [Преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Разработка глобализованных и локализованных приложений](/visualstudio/ide/globalizing-and-localizing-applications)
