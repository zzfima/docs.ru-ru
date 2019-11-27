---
title: Тип данных String
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
ms.openlocfilehash: c2c6f9632646c432abb7b6da8887253e526cc994
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343910"
---
# <a name="string-data-type-visual-basic"></a>Тип данных String (Visual Basic)

Содержит последовательности 16-разрядных (2-байтовых) кодовых точек без знака, которые находятся в диапазоне от 0 до 65535. Каждая кодовая *точка*, или код символа, представляет один символ Юникода. Строка может содержать от 0 до приблизительно 2 000 000 000 (2 ^ 31) символов Юникода.  
  
## <a name="remarks"></a>Заметки  

 Используйте `String` тип данных для хранения нескольких символов без дополнительных затрат на Управление массивом `Char()`, массива элементов `Char`.  
  
 Значение `String` по умолчанию — `Nothing` (пустая ссылка). Обратите внимание, что это не то же самое, что пустая строка (значение `""`).  
  
## <a name="unicode-characters"></a>Символы Юникода  

 Первая 128 кодовых позиций (0 – 127) Юникода соответствует буквам и символам стандартной клавиатуры США. Первые 128 кодовые точки те же, что и кодировка ASCII. Вторая 128 кодовых позиций (128 – 255) представляет специальные символы, такие как буквы латинского алфавита, диакритические знаки, символы валют и дроби. В Юникоде используются оставшиеся кодовые точки (256-65535) для широкого спектра символов. Это включает в себя международные текстовые символы, диакритические знаки, математические и технические символы.  
  
 Для определения своей классификации Юникода можно использовать такие методы, как <xref:System.Char.IsDigit%2A> и <xref:System.Char.IsPunctuation%2A> на отдельный символ в `String` переменной.  
  
## <a name="format-requirements"></a>Требования к формату  

 `String` литерал необходимо заключить в кавычки (`" "`). Если необходимо включить кавычки в качестве одного из символов в строке, используются две смежные кавычки (`""`). Это показано в следующем примере.  
  
```vb  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 Обратите внимание, что смежные кавычки, представляющие кавычки в строке, не зависят от кавычек, начинающихся и заканчивая литералом `String`.  
  
## <a name="string-manipulations"></a>Манипуляции со строками  

 После присвоения строки переменной `String` эта строка является *неизменяемой*, что означает, что изменить ее длину или содержимое нельзя. При изменении строки каким-либо образом Visual Basic создает новую строку и задействует предыдущую. Переменная `String` указывает на новую строку.  
  
 Вы можете манипулировать содержимым `String` переменной с помощью различных строковых функций. В следующем примере показана функция <xref:Microsoft.VisualBasic.Strings.Left%2A>  
  
```vb  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 Строка, созданная другим компонентом, может быть дополнена начальными или конечными пробелами. Если вы получаете такую строку, для удаления этих пробелов можно использовать функции <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>и <xref:Microsoft.VisualBasic.Strings.RTrim%2A>.  
  
 Дополнительные сведения об операциях со строками см. в разделе [строки](../../../visual-basic/programming-guide/language-features/strings/index.md).  
  
## <a name="programming-tips"></a>Советы по программированию  
  
- **Отрицательные числа.** Помните, что символы, удерживаемые `String`, не являются знаками и не могут представлять отрицательные значения. В любом случае не следует использовать `String` для хранения числовых значений.  
  
- **Вопросы взаимодействия.** Если вы взаимодействуете с компонентами, которые не написаны для .NET Framework, например автоматизации или COM-объекты, помните, что в других средах символы строки имеют разную ширину данных (8 бит). При передаче строкового аргумента из 8-разрядных символов в такой компонент объявите его как `Byte()`, массив `Byte`ных элементов, а не `String` в новом коде Visual Basic.  
  
- **Символы типа.** Добавление символа типа идентификатора `$` к любому идентификатору приводит к тому, что он применяет его к `String` типу данных. `String` не имеет символа типа литерала. Однако компилятор обрабатывает литералы, заключенные в кавычки (`" "`), как `String`.  
  
- **Тип платформы.** Соответствующий тип в .NET Framework является классом <xref:System.String?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

- <xref:System.String?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Тип данных Char](../../../visual-basic/language-reference/data-types/char-data-type.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
