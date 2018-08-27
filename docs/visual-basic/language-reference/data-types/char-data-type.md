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
ms.openlocfilehash: 09b0162068bc068bd77612816626897ec4a151d9
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42911971"
---
# <a name="char-data-type-visual-basic"></a>Тип данных Char (Visual Basic)
Содержит число без знака 16-разрядное (2-байтовые) кодовые в диапазоне от 0 до 65535. Каждый *кодовую точку*, или код символа, представляющего отдельный символ Юникода.  
  
## <a name="remarks"></a>Примечания  
 Используйте `Char` тип данных, если вам нужно хранить только один символ и не обязательно затраты на `String`. В некоторых случаях можно использовать `Char()`, массив `Char` элементов, для хранения нескольких символов.  
  
 Значение по умолчанию `Char` — это символ, с помощью кодовых позиций 0.  
  
## <a name="unicode-characters"></a>Символы Юникода  
 Первые 128 кодовых точек (от 0 до 127) Юникода соответствуют буквы и символы на стандартной клавиатуре США. Эти первые 128 кодовых точек являются те же определяет набор символов ASCII. 128 кодовых точек (128-255) представляют специальные символы, такие как буквы латинского алфавита, диакритические знаки, символы валют и дроби. Юникод использует остальные кодовые точки (от 256 до 65535) для широкого набора символов, включая международные текстовые знаки, математические и технические символы и диакритические знаки.  
  
 Можно использовать методы, такие как <xref:System.Char.IsDigit%2A> и <xref:System.Char.IsPunctuation%2A> на `Char` переменной, можно определить ее классификации Юникода.  
  
## <a name="type-conversions"></a>Преобразования типов  
 Visual Basic не выполняет преобразование между непосредственно `Char` числовые типы. Можно использовать <xref:Microsoft.VisualBasic.Strings.Asc%2A> или <xref:Microsoft.VisualBasic.Strings.AscW%2A> функцию для преобразования `Char` значение `Integer` , представляющий его кодовая точка. Можно использовать <xref:Microsoft.VisualBasic.Strings.Chr%2A> или <xref:Microsoft.VisualBasic.Strings.ChrW%2A> функцию для преобразования `Integer` значение `Char` с кодовой точки.  
  
 Если переключатель проверки типа ([оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)) имеет значение on, необходимо добавить знак типа литерала для строкового литерала в целях идентификации как `Char` тип данных. Это показано в следующем примере.  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## <a name="programming-tips"></a>Советы по программированию  
  
-   **Отрицательные числа.** `Char` является типом без знака и не может представлять отрицательное значение. В любом случае не следует использовать `Char` для хранения числовых значений.  
  
-   **Вопросы взаимодействия.** Если возможность взаимодействовать с компонентами, которые не написаны для платформы .NET Framework, например, автоматизация или COM-объекты, следует помните, что символьные типы имеют другой размер (8 бит) в других средах. Если при передаче 8-разрядного аргумента такому компоненту, объявите его как `Byte` вместо `Char` в новом коде Visual Basic.  
  
-   **Расширяющие.** `Char` Тип данных можно расширить до `String`. Это означает, что вы можете преобразовать `Char` для `String` и не столкнетесь с <xref:System.OverflowException?displayProperty=nameWithType> ошибки.  
  
-   **Символы типа.** Добавляется знак типа литерала `C` в строку односимвольный литерал приводит к принудительному `Char` тип данных. `Char` не имеет тип символа идентификатора.  
  
-   **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Char?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Char?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [Типы данных](../../../visual-basic/language-reference/data-types/index.md)  
 [Тип данных String](../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
