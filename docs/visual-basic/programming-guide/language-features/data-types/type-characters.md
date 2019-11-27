---
title: Символы типов
ms.date: 01/31/2018
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals [Visual Basic]
- F literal type character [Visual Basic]
- '& identifier type character'
- type characters [Visual Basic]
- octal literals [Visual Basic]
- literals [Visual Basic], hexadecimal
- '&O prefix for octal values'
- literals [Visual Basic], default types
- defaults, literal types
- C literal type character [Visual Basic]
- type characters [Visual Basic], literal
- $ identifier type character
- L literal type character [Visual Basic]
- UI literal type characters [Visual Basic]
- default literal types [Visual Basic]
- D literal type character [Visual Basic]
- literals [Visual Basic], octal
- S literal type character [Visual Basic]
- '! identifier type character'
- US literal type characters [Visual Basic]
- '% identifier type character'
- data types [Visual Basic], type characters
- characters [Visual Basic], identifier type
- type characters [Visual Basic], identifier
- '# identifier type character'
- identifier type characters [Visual Basic]
- literal type characters [Visual Basic]
- I literal type character [Visual Basic]
- R literal type character [Visual Basic]
- '@ identifier type character'
- UL literal type characters [Visual Basic]
- literal types [Visual Basic], default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
ms.openlocfilehash: 628461c8136946dd902c0a52048eee7c516c52cd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352929"
---
# <a name="type-characters-visual-basic"></a>Символы типов (Visual Basic)

Помимо указания типа данных в операторе объявления, можно принудительно указать тип данных некоторых программных элементов с помощью *символа типа*. Символ типа должен следовать непосредственно за элементом, не имеющим промежуточных символов любого вида.

Символ типа не является частью имени элемента. На элемент, определенный с помощью символа типа, можно ссылаться без символа типа.

## <a name="identifier-type-characters"></a>Символы типа идентификатора

Visual Basic предоставляет набор *символов типа идентификатора* , которые можно использовать в объявлении для указания типа данных переменной или константы. В следующей таблице приведены доступные символы типа идентификатора с примерами использования.
  
|Символ типа идентификатора|Тип данных|Пример|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 Не существует символов типа идентификатора для `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`или `ULong`типов данных, а также для любых составных типов данных, таких как массивы или структуры.`UShort`

В некоторых случаях можно добавить `$`ный символ в функцию Visual Basic, например `Left$` вместо `Left`, чтобы получить возвращаемое значение типа `String`.

Во всех случаях символ типа идентификатора должен следовать непосредственно за именем идентификатора.

## <a name="literal-type-characters"></a>Символы типа литерала

*Литерал* — это текстовое представление конкретного значения типа данных.  

### <a name="default-literal-types"></a>Типы литералов по умолчанию

Форма литерала в том виде, в котором она отображается в коде, обычно определяет его тип данных. В следующей таблице показаны эти типы по умолчанию.  
  
|Текстовая форма литерала|Тип данных по умолчанию|Пример|  
|-----------------------------|-----------------------|-------------|  
|Numeric, без дробной части|`Integer`|`2147483647`|  
|Numeric, без дробной части, слишком велика для `Integer`|`Long`|`2147483648`|  
|Числовая, дробная часть|`Double`|`1.2`|  
|Заключено в двойные кавычки|`String`|`"A"`|  
|Заключено в знаки решетки|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a>Принудительные типы литералов

Visual Basic предоставляет набор *символов типа литерала*, который можно использовать для принудительного применения литерала к типу данных, отличному от того, который указывает его форма. Это можно сделать, добавив символ в конец литерала. В следующей таблице показаны доступные символы типа литерала с примерами использования.
  
|Символ типа литерала|Тип данных|Пример|  
|----------------------------|---------------|-------------|  
|`S`|`Short`|`I = 347S`|
|`I`|`Integer`|`J = 347I`|
|`L`|`Long`|`K = 347L`|
|`D`|`Decimal`|`X = 347D`|
|`F`|`Single`|`Y = 347F`|
|`R`|`Double`|`Z = 347R`|
|`US`|`UShort`|`L = 347US`|
|`UI`|`UInteger`|`M = 347UI`|
|`UL`|`ULong`|`N = 347UL`|
|`C`|`Char`|`Q = "."C`|

Для типов данных `Boolean`, `Byte`, `Date`, `Object`, `SByte`или `String` не существует символов типа литерала или для любых составных типов данных, таких как массивы или структуры.

Литералы также могут использовать символы типа идентификатора (`%`, `&`, `@`, `!`, `#`, `$`), как это могут быть переменные, константы и выражения. Однако символы типа литерала (`S`, `I`, `L`, `D`, `F`, `R`, `C`) можно использовать только с литералами.

Во всех случаях символ типа литерала должен следовать непосредственно за литеральным значением.

## <a name="hexadecimal-binary-and-octal-literals"></a>Шестнадцатеричные, двоичные и восьмеричные литералы

Компилятор обычно интерпретирует целочисленный литерал в десятичной системе счисления (с основанием 10). Можно также определить целочисленный литерал как шестнадцатеричное (с основанием 16) значением префикса `&H`, в виде двоичного номера (основание 2) с префиксом `&B`, а также как восьмеричное (основание 8) число с префиксом `&O`. Цифры, которые следуют за префиксом, должны соответствовать системе счисления. Это показано в следующей таблице.  
  
|Базовый номер|Префикс|Допустимые разрядные значения|Пример|
|-----------------|------------|------------------------|-------------|
|16 (основание 16)|`&H`|0-9 и A-F|`&HFFFF`|
|Двоичный (основание 2)|`&B`|0—1|`&B01111100`|
|8 (основание 8)|`&O`|0-7|`&O77`|

Начиная с Visual Basic 2017 можно использовать символ подчеркивания (`_`) в качестве разделителя групп, чтобы повысить удобочитаемость целочисленного литерала. В следующем примере используется символ `_` для группирования двоичного литерала в 8-разрядные группы:

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

Можно следовать предопределенному литералу с символом типа литерала. Это показано в следующем примере.

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

В предыдущем примере `counter` имеет десятичное значение-32768, а `flags` имеет десятичное значение + 32768.

Начиная с Visual Basic 15,5 можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и шестнадцатеричными, двоичными или восьмеричными цифрами. Пример.

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a>См. также

- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)
