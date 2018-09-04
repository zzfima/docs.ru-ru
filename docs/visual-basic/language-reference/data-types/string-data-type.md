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
ms.openlocfilehash: 54f7dcd7de28e8aaa5376bb4ddd67fd53518511e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43661558"
---
# <a name="string-data-type-visual-basic"></a>Тип данных String (Visual Basic)
Содержит последовательности точек неподписанный код 16-разрядное (2-байтовое) этого диапазона, в диапазоне от 0 до 65535. Каждый *кодовую точку*, или код символа, представляющего отдельный символ Юникода. Строки могут содержать от 0 до двух миллиардов (2 ^ 31) символов Юникода.  
  
## <a name="remarks"></a>Примечания  
 Используйте `String` тип данных для хранения нескольких знаков, без издержек на управление массива `Char()`, массив `Char` элементов.  
  
 Значение по умолчанию `String` является `Nothing` (ссылкой на null). Обратите внимание, что это не так же, как пустая строка (значение `""`).  
  
## <a name="unicode-characters"></a>Символы Юникода  
 Первые 128 кодовых точек (от 0 до 127) Юникода соответствуют буквы и символы на стандартной клавиатуре США. Эти первые 128 кодовых точек являются те же определяет набор символов ASCII. 128 кодовых точек (128-255) представляют специальные символы, такие как буквы латинского алфавита, диакритические знаки, символы валют и дроби. Юникод использует остальные кодовые точки (от 256 до 65535) для широкого набора символов. Сюда входят международные текстовые знаки, математические и технические символы и диакритические знаки.  
  
 Можно использовать методы, такие как <xref:System.Char.IsDigit%2A> и <xref:System.Char.IsPunctuation%2A> на отдельный символ в `String` переменной, можно определить ее классификации Юникода.  
  
## <a name="format-requirements"></a>Требования к формату  
 Необходимо заключить `String` литерал в кавычках (`" "`). Если необходимо включить знак кавычек, среди символов в строке, используется двух последовательных кавычек (`""`). Это показано в следующем примере.  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 Обратите внимание, что парные кавычки, которые представляют кавычки в строке не зависят от кавычек в начале и конце `String` литерала.  
  
## <a name="string-manipulations"></a>Операции со строками  
 После того как строка, `String` переменной, эта строка является *неизменяемый*, который означает, что нельзя изменить его длину или содержимое. При изменении строки любым способом, Visual Basic создает новую строку и закрывает предыдущую. `String` Переменная затем указывает на новую строку.  
  
 Можно управлять содержимым `String` переменной с помощью различных строковых функций. В следующем примере показано <xref:Microsoft.VisualBasic.Strings.Left%2A> функции  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 Строка, созданная другим компонентом может быть дополняются начальные или конечные пробелы. Если вы получаете такие строки, можно использовать <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, и <xref:Microsoft.VisualBasic.Strings.RTrim%2A> функции для удаления этих пробелов.  
  
 Дополнительные сведения об операции со строками, см. в разделе [строки](../../../visual-basic/programming-guide/language-features/strings/index.md).  
  
## <a name="programming-tips"></a>Советы по программированию  
  
-   **Отрицательные числа.** Помните, что символы удерживаемые `String` не подписаны и не может представлять отрицательные значения. В любом случае не следует использовать `String` для хранения числовых значений.  
  
-   **Вопросы взаимодействия.** При взаимодействии с компонентами, которые не написаны для платформы .NET Framework, например, автоматизация или COM-объекты, помните, что символы строки имеют другой размер (8 бит) в других средах. Если вы передаете 8-разрядных символов строкового аргумента такому компоненту, объявите ее в качестве `Byte()`, массив `Byte` элементов, вместо `String` в новом коде Visual Basic.  
  
-   **Символы типа.** Добавление знак типа идентификатора `$` к любому идентификатору производится принудительное для `String` тип данных. `String` не имеет тип литерала символа. Однако компилятор обрабатывает литералы, заключенные в кавычки (`" "`) как `String`.  
  
-   **Тип Framework.** Соответствующий тип в .NET Framework — <xref:System.String?displayProperty=nameWithType> класса.  
  
## <a name="see-also"></a>См. также  
 <xref:System.String?displayProperty=nameWithType>  
 [Типы данных](../../../visual-basic/language-reference/data-types/index.md)  
 [Тип данных Char](../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
