---
title: Тип данных Char (Visual Basic)
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
ms.openlocfilehash: ca40e6c8dcba3da29bdb68b29c91c852e477f8f7
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512790"
---
# <a name="char-data-type-visual-basic"></a>Тип данных Char (Visual Basic)

Содержит 16-разрядные (2-байтовые) кодовые точки без знака в диапазоне от 0 до 65535. Каждая кодовая *точка*, или код символа, представляет один символ Юникода.

## <a name="remarks"></a>Примечания

Используйте тип `String`данных, если необходимо хранить только один символ и не требуется дополнительная нагрузка. `Char` В некоторых случаях для хранения нескольких `Char()`символов можно использовать `Char` массив элементов.

Значение по умолчанию `Char` — символ с кодовой точкой 0.

## <a name="unicode-characters"></a>Символы Юникода

Первая 128 кодовых позиций (0 – 127) Юникода соответствует буквам и символам стандартной клавиатуры США. Первые 128 кодовые точки те же, что и кодировка ASCII. Вторая 128 кодовых позиций (128 – 255) представляет специальные символы, такие как буквы латинского алфавита, диакритические знаки, символы валют и дроби. В Юникоде используются оставшиеся кодовые точки (256-65535) для широкого спектра символов, включая международные текстовые символы, диакритические знаки, математические и технические символы.

Для определения своей классификации в <xref:System.Char.IsDigit%2A> Юникоде <xref:System.Char.IsPunctuation%2A> можно использовать `Char` методы, такие как и, для переменной.

## <a name="type-conversions"></a>Преобразования типов

Visual Basic не выполняет прямое преобразование между `Char` и числовыми типами. Можно использовать <xref:Microsoft.VisualBasic.Strings.Asc%2A> функцию или <xref:Microsoft.VisualBasic.Strings.AscW%2A> `Char` для`Integer` преобразования значения в, представляющего ее кодовую точку. <xref:Microsoft.VisualBasic.Strings.Chr%2A> <xref:Microsoft.VisualBasic.Strings.ChrW%2A> Для преобразования`Integer` значения в ,котороеимеетэтукодовуюточку,можноиспользоватьфункциюили.`Char`

Если включен параметр проверки типов ([оператор Option строго](../../../visual-basic/language-reference/statements/option-strict-statement.md)), необходимо добавить символ типа литерала в односимвольный строковый литерал, чтобы его можно было обозначить `Char` как тип данных. Это показано в следующем примере.

```vb
Option Strict On
Dim charVar As Char
' The following statement attempts to convert a String literal to Char.
' Because Option Strict is On, it generates a compiler error.
charVar = "Z"
' The following statement succeeds because it specifies a Char literal.
charVar = "Z"C
```

## <a name="programming-tips"></a>Советы по программированию

- **Отрицательные числа.** `Char`является неподписанным типом и не может представлять отрицательное значение. В любом случае не следует использовать `Char` для хранения числовых значений.

- **Вопросы взаимодействия.** Если вы используете компоненты, не написанные для .NET Framework, например автоматизацию или COM-объекты, помните, что в других средах символьные типы имеют разную ширину данных (8 бит). При передаче 8-разрядного аргумента в такой компонент объявите его как `Byte` `Char` вместо в новом коде Visual Basic.

- **Расширяющие.** Тип данных расширяется до `String`. `Char` Это означает, что вы `Char` можете `String` преобразовать в <xref:System.OverflowException?displayProperty=nameWithType> и не получит ошибку.

- **Символы типа.** Добавление символа `C` типа литерала к строковому литералу с одним символом приводит к тому `Char` , что он применяет его к типу данных. `Char`не имеет символа типа идентификатора.

- **Тип платформы.** В .NET Framework данный тип соответствует структуре <xref:System.Char?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Тип данных String](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
