---
title: Символы типов (Visual Basic)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31dc703598fa6d92b3f312b2b5f0bf5fadab9c04
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42911826"
---
# <a name="type-characters-visual-basic"></a>Введите символы (Visual Basic)

В дополнение к определению типов данных в операторе объявления, можно задать тип данных некоторых элементов программирования с *символ типа*. Символ типа должно следовать сразу за элементом без каких-либо промежуточного знака.

Символ типа не является частью имени элемента. Ссылка на элемент с символом типа может не символ типа.

## <a name="identifier-type-characters"></a>Символы типа идентификатора

Visual Basic предоставляет набор *символы типа идентификатора* можно использовать в объявлении для указания типа данных переменной или константы. В следующей таблице показаны допустимые символы типа идентификатора с примерами их использования.
  
|Знак типа идентификатора|Тип данных|Пример|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 Символов типа идентификатора не существует для `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, или `UShort` типов данных или других составные типы данных, таких как массивы или структуры.

В некоторых случаях можно добавить `$` символов для функции Visual Basic, например `Left$` вместо `Left`, чтобы получить возвращаемое значение типа `String`.

Во всех случаях знак типа идентификатора должно следовать сразу за имя идентификатора.

## <a name="literal-type-characters"></a>Символы типа литерала

Объект *литерала* является текстовым представлением отдельного значения типа данных.  

### <a name="default-literal-types"></a>Типы литералов по умолчанию

Форма литерала, как оно отображается в коде, обычно определяет его тип данных. Ниже приведены эти типы по умолчанию.  
  
|Текстовая форма литерала|Тип данных по умолчанию|Пример|  
|-----------------------------|-----------------------|-------------|  
|Числовые без дробной части|`Integer`|`2147483647`|  
|Числовые без дробной части, слишком велик для `Integer`|`Long`|`2147483648`|  
|Числовые дробной части|`Double`|`1.2`|  
|Заключенный в двойные кавычки|`String`|`"A"`|  
|Заключенные в решетки|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a>Принудительно типы литералов

Visual Basic предоставляет набор *символы типа литерала*, указывает, что можно использовать для принудительного присвоения литералу типом данных, отличный от его формы. Для этого добавляется знак в конец литерала. В следующей таблице показаны допустимые символы типа литерала с примерами их использования.
  
|Знак типа литерала|Тип данных|Пример|  
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

Никакие символы типа литерала существует для `Boolean`, `Byte`, `Date`, `Object`, `SByte`, или `String` типы данных, или для любых типов составных данных, таких как массивы или структуры.

Литералы также можно использовать символы типа идентификатора (`%`, `&`, `@`, `!`, `#`, `$`), как и переменные, константы и выражения. Тем не менее, символы типа литерала (`S`, `I`, `L`, `D`, `F`, `R`, `C`) может использоваться только с литералами.

Во всех случаях знак типа литерала должно следовать сразу за литеральное значение.

## <a name="hexadecimal-binary-and-octal-literals"></a>Шестнадцатеричные, двоичные и восьмеричные литералы

Как правило, компилятор интерпретирует целочисленным литералом в системе счисления десятичным (основание 10). Можно также определить целочисленный литерал, как число шестнадцатеричным (основание 16) с `&H` префиксом, как число двоичного файла (по основанию 2) с `&B` префикс и в качестве восьмеричным (основание 8) числом с `&O` префикс. Цифры, указанные префикс должен соответствовать типу в системе счисления. Это показано в следующей таблице.  
  
|Основание системы счисления|Префикс|Допустимые числовые значения|Пример|
|-----------------|------------|------------------------|-------------|
|16 (основание 16)|`&H`|0-9 или A-F|`&HFFFF`|
|Двоичный файл (по основанию 2)|`&B`|0—1|`&B01111100`|
|8 (основание 8)|`&O`|0-7|`&O77`|

Начиная с Visual Basic 2017, можно использовать символ подчеркивания (`_`) как разделитель групп, чтобы повысить удобочитаемость используется целочисленный литерал. В следующем примере используется `_` символ для группировки двоичный литерал в 8-разрядное групп:

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

Вы можете следовать префикса литерала знак типа литерала. Это показано в следующем примере.

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

В предыдущем примере `counter` имеет десятичное значение от -32768, и `flags` имеет десятичное значение + 32768.

Начиная с Visual Basic 15.5, можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и двоичное, шестнадцатеричное или восьмеричное цифры. Пример:

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a>См. также

 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)
