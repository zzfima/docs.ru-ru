---
title: Тип данных Char
ms.date: 07/20/2015
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
ms.openlocfilehash: 1ed5b19a307d094fc1d5a6bb0251c57052dc9bc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344047"
---
# <a name="char-data-type-visual-basic"></a>Тип данных Char (Visual Basic)

Содержит 16-разрядные (2-байтовые) кодовые точки без знака в диапазоне от 0 до 65535. Каждая кодовая *точка*, или код символа, представляет один символ Юникода.

## <a name="remarks"></a>Примечания

Используйте тип данных `Char`, если необходимо удерживать только один символ и не требуется издержки `String`. В некоторых случаях для хранения нескольких символов можно использовать `Char()`, массив элементов `Char`.

Значением по умолчанию для `Char` является символ с кодовой точкой 0.

## <a name="unicode-characters"></a>Символы Юникода

Первая 128 кодовых позиций (0 – 127) Юникода соответствует буквам и символам стандартной клавиатуры США. Первые 128 кодовые точки те же, что и кодировка ASCII. Вторая 128 кодовых позиций (128 – 255) представляет специальные символы, такие как буквы латинского алфавита, диакритические знаки, символы валют и дроби. В Юникоде используются оставшиеся кодовые точки (256-65535) для широкого спектра символов, включая международные текстовые символы, диакритические знаки, математические и технические символы.

Для определения своей классификации Юникода можно использовать методы, такие как <xref:System.Char.IsDigit%2A> и <xref:System.Char.IsPunctuation%2A> в переменной `Char`.

## <a name="type-conversions"></a>Преобразования типов

Visual Basic не преобразует непосредственно между `Char` и числовыми типами. Для преобразования `Char` значения в `Integer`, представляющее его кодовую точку, можно использовать функцию <xref:Microsoft.VisualBasic.Strings.Asc%2A> или <xref:Microsoft.VisualBasic.Strings.AscW%2A>. Для преобразования `Integer` значения в `Char` с этой кодовой точкой можно использовать функцию <xref:Microsoft.VisualBasic.Strings.Chr%2A> или <xref:Microsoft.VisualBasic.Strings.ChrW%2A>.

Если параметр проверки типов ( [оператор Option строго](../../../visual-basic/language-reference/statements/option-strict-statement.md)) включен, необходимо добавить символ типа литерала в односимвольный строковый литерал, чтобы он определялся как тип данных `Char`. Это показано в следующем примере. Первое Присваивание переменной `charVar` приводит к ошибке компилятора [BC30512](../../misc/bc30512.md) , так как `Option Strict` находится в on. Второй компилируется успешно, так как символ типа литерала `c` идентифицирует литерал как `Char` значение.

```vb
Option Strict On

Module CharType
    Public Sub Main()
        Dim charVar As Char

        ' This statement generates compiler error BC30512 because Option Strict is On.  
        charVar = "Z"  

        ' The following statement succeeds because it specifies a Char literal.  
        charVar = "Z"c
    End Sub
End Module
```

## <a name="programming-tips"></a>Советы по программированию

- **Отрицательные числа.** `Char` является неподписанным типом и не может представлять отрицательное значение. В любом случае не следует использовать `Char` для хранения числовых значений.

- **Вопросы взаимодействия.** Если вы используете компоненты, не написанные для .NET Framework, например автоматизацию или COM-объекты, помните, что в других средах символьные типы имеют разную ширину данных (8 бит). При передаче 8-разрядного аргумента в такой компонент объявите его как `Byte` вместо `Char` в новом коде Visual Basic.

- **Расширяющие.** Тип данных `Char` расширяется до `String`. Это означает, что вы можете преобразовать `Char` в `String` и не встретит <xref:System.OverflowException?displayProperty=nameWithType>.

- **Символы типа.** Присоединение символьного типа литерала `C` к строковому литералу с одним символом принуждает его к `Char` типу данных. `Char` не имеет символа типа идентификатора.

- **Тип платформы.** В .NET Framework данный тип соответствует структуре <xref:System.Char?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Тип данных String](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
