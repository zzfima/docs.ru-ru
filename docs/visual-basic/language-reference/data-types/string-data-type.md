---
title: "Строковый тип данных (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.String
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings, string data type
- literals, string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals
- data types [Visual Basic], assigning
- String literals
- identifier type characters, $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
caps.latest.revision: 19
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9221a89a1fb46609b4b8550968e3a2bbe874772c
ms.lasthandoff: 03/13/2017

---
# <a name="string-data-type-visual-basic"></a>Тип данных String (Visual Basic)
Содержит этот диапазон последовательности без знака 16-разрядные (2-байтовые) кодовые точки в диапазоне от 0 до 65535. Каждый *кодовой*, или код знака, представляет один знак Юникода. Строка может содержать от нуля до двух миллиардов (2 ^ 31) знаков Юникода.  
  
## <a name="remarks"></a>Примечания  
 Используйте `String` тип данных для хранения нескольких символов без использования управления массива `Char()`, массив `Char` элементы.  
  
 Значение по умолчанию `String` — `Nothing` (пустая ссылка). Обратите внимание, что это не совпадает с пустой строкой (значение `""`).  
  
## <a name="unicode-characters"></a>Символы Юникода  
 Первые 128 кодовых точек (от 0 до 127) Юникода соответствуют буквам и символам стандартной американской клавиатуры. Эти первые 128 кодовых точек являются такими же, как определяет набор символов ASCII. 128 кодовых точек (128-255) представляют специальные символы, такие как буквы латинского алфавита, знаки ударения, символы валют и дроби. Юникод использует остальные кодовые точки (от&256; до&65535;) для широкого набора символов. Это включает в себя международные текстовые знаки, математические и технические символы и диакритические знаки.  
  
 Можно использовать методы, такие как <xref:System.Char.IsDigit%2A>и <xref:System.Char.IsPunctuation%2A>на отдельный символ в `String` переменную для определения ее классификации Юникода.</xref:System.Char.IsPunctuation%2A> </xref:System.Char.IsDigit%2A>  
  
## <a name="format-requirements"></a>Требования к формату  
 Необходимо заключить `String` литерал в кавычках (`" "`). Если необходимо включить кавычки как один из символов в строке, используется два смежных кавычки (`""`). Это показано в следующем примере.  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 Обратите внимание, что парные кавычки, которые представляют кавычки в строке не зависят от кавычки, которые начинают и завершают `String` литерала.  
  
## <a name="string-manipulations"></a>Операции со строками  
 После того как строка, `String` переменной, что строка является *неизменяемый*, означает, что нельзя изменить её длину или содержимое. При изменении строки каким-либо образом Visual Basic создает новую строку и закрывает предыдущую. `String` Переменная затем указывает на новую строку.  
  
 Можно управлять содержимым `String` переменной с помощью различных строковых функций. В следующем примере <xref:Microsoft.VisualBasic.Strings.Left%2A>функция</xref:Microsoft.VisualBasic.Strings.Left%2A>  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 Строка, созданная другим компонентом может быть заполняется начальные или конечные пробелы. Если вы получаете такие строки, можно использовать <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, и <xref:Microsoft.VisualBasic.Strings.RTrim%2A>функции для удаления этих пробелов.</xref:Microsoft.VisualBasic.Strings.RTrim%2A> </xref:Microsoft.VisualBasic.Strings.LTrim%2A> </xref:Microsoft.VisualBasic.Strings.Trim%2A>  
  
 Дополнительные сведения об операции со строками см. в разделе [строки](../../../visual-basic/programming-guide/language-features/strings/index.md).  
  
## <a name="programming-tips"></a>Советы по программированию  
  
-   **Отрицательные числа.** Помните, что символы удерживаемые `String` без знака и не может представлять отрицательные значения. В любом случае не следует использовать `String` для хранения числовых значений.  
  
-   **Вопросы взаимодействия.** При взаимодействии с компонентами, написанными не для платформы .NET Framework, например автоматизации или COM-объектов, помните, что символы строки имеют другой размер (8 бит) в других средах. Если такому компоненту передается строковый аргумент 8-разрядных символов, объявите ее в качестве `Byte()`, массив `Byte` элементов, а не `String` в новом коде Visual Basic.  
  
-   **Символы типов.** Добавление знак типа идентификатора `$` к любому идентификатору приводит к принудительному `String` тип данных. `String`не имеет буквенного символа. Однако компилятор обрабатывает литералы, заключенные в кавычки (`" "`) как `String`.  
  
-   **Тип Framework.** Соответствующий тип в .NET Framework является <xref:System.String?displayProperty=fullName>класс.</xref:System.String?displayProperty=fullName>  
  
## <a name="see-also"></a>См. также  
 <xref:System.String?displayProperty=fullName></xref:System.String?displayProperty=fullName>   
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Тип данных char](../../../visual-basic/language-reference/data-types/char-data-type.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Практическое руководство: вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

