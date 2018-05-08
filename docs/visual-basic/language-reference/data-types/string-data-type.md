---
title: Тип данных String (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.String
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings [Visual Basic], string data type
- literals [Visual Basic], string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals [Visual Basic]
- data types [Visual Basic], assigning
- String literals [Visual Basic]
- identifier type characters [Visual Basic], $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
ms.openlocfilehash: 894638bbe50dad2cae1f74a2f7b7fe006f029d1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="string-data-type-visual-basic"></a>Тип данных String (Visual Basic)
Содержит последовательности точек неподписанный код 16-разрядное (2-байтовые) этого диапазона, в диапазоне от 0 до 65535. Каждый *кодовой*, или код символа, представляет один знак Юникода. Строка может содержать от нуля до двух миллиардов (2 ^ 31) знаков Юникода.  
  
## <a name="remarks"></a>Примечания  
 Используйте `String` тип данных для хранения нескольких символов, одновременно снижая издержки управления массивом `Char()`, массив `Char` элементов.  
  
 Значение по умолчанию `String` — `Nothing` (ссылка null). Обратите внимание, что это не то же, что пустая строка (значение `""`).  
  
## <a name="unicode-characters"></a>Символы Юникода  
 Первые 128 кодовых точек (от 0 до 127) Юникода соответствуют буквы и символы на стандартной клавиатуре США. Эти первые 128 кодовых точек являются такие же, как определяет набор символов ASCII. 128 кодовых точек (от 128 до 255) представляют специальные символы, такие как буквы латинского алфавита, диакритические знаки, символы валют и дроби. Юникод использует остальные кодовые точки (от 256 до 65535) для широкого набора символов. Сюда входят международные текстовые знаки, диакритические знаки и математические и технические символы.  
  
 Можно использовать методы, такие как <xref:System.Char.IsDigit%2A> и <xref:System.Char.IsPunctuation%2A> на отдельный символ в `String` переменную для определения ее классификации Юникода.  
  
## <a name="format-requirements"></a>Требования к формату  
 Необходимо заключить `String` литерал в кавычках (`" "`). Если необходимо включить знак кавычек, как один из символов в строке, используется два смежных кавычки (`""`). Это показано в следующем примере.  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 Обратите внимание, что парные кавычки, знак кавычки в строке зависят от кавычки в начале и конце `String` литерала.  
  
## <a name="string-manipulations"></a>Со строками  
 После того как строка, `String` переменных, эта строка является *неизменяемый*, это означает, что вы не может изменить его длину или содержимое. При изменении строки каким-либо образом Visual Basic создает новую строку и закрывает предыдущую. `String` Переменная указывает новую строку.  
  
 Можно управлять содержимым `String` переменной с помощью различных строковых функций. В следующем примере демонстрируется <xref:Microsoft.VisualBasic.Strings.Left%2A> функции  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 Строка, созданная другим компонентом может быть заполняются начальные или конечные пробелы. Получив такой строки, можно использовать <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, и <xref:Microsoft.VisualBasic.Strings.RTrim%2A> функции для удаления этих пробелов.  
  
 Дополнительные сведения о со строками в разделе [строки](../../../visual-basic/programming-guide/language-features/strings/index.md).  
  
## <a name="programming-tips"></a>Советы по программированию  
  
-   **Отрицательные числа.** Помните, что символы удерживаемые `String` без знака и не может представлять отрицательные значения. В любом случае не следует использовать `String` для хранения числовых значений.  
  
-   **Вопросы взаимодействия.** При взаимодействии с компонентами, которые не написаны для платформы .NET Framework, например, автоматизация или COM-объекты, помните, что строка символов быть другой размер (8 бит) в других средах. Если вы передаете 8-битовых символов строкового аргумента такому компоненту, объявите его как `Byte()`, массив `Byte` элементов, а не `String` в новом коде Visual Basic.  
  
-   **Символы типов.** Добавление знак типа идентификатора `$` к любому идентификатору производится принудительное для `String` тип данных. `String` не имеет типа литерала символа. Однако компилятор обрабатывает литералы, заключенные в кавычки (`" "`) как `String`.  
  
-   **Тип Framework.** Соответствующий тип в .NET Framework — <xref:System.String?displayProperty=nameWithType> класса.  
  
## <a name="see-also"></a>См. также  
 <xref:System.String?displayProperty=nameWithType>  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Тип данных Char](../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
