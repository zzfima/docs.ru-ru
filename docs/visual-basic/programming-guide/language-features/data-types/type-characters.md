---
title: "Введите символы (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals
- F literal type character
- '& identifier type character'
- type characters
- octal literals
- literals, hexadecimal
- '&O prefix for octal values'
- literals, default types
- defaults, literal types
- C literal type character
- type characters, literal
- $ identifier type character
- L literal type character
- UI literal type characters
- default literal types
- D literal type character
- literals, octal
- S literal type character
- '! identifier type character'
- US literal type characters
- '% identifier type character'
- data types [Visual Basic], type characters
- characters, identifier type
- type characters, identifier
- '# identifier type character'
- identifier type characters
- literal type characters
- I literal type character
- R literal type character
- '@ identifier type character'
- UL literal type characters
- literal types, default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 6e112e7d221ef8e7a660094306bbb242c988e843
ms.lasthandoff: 03/13/2017

---
# <a name="type-characters-visual-basic"></a>Символы типов (Visual Basic)
В дополнение к определению типов данных в операторе объявления, можно задать тип данных некоторых элементов программирования с *символ типа*. Знак типа следует непосредственно за элементом без каких-либо промежуточного знака.  
  
 Знак типа не является частью имени элемента. Ссылка на элемент с символом типа может не знак типа.  
  
## <a name="identifier-type-characters"></a>Символы типа идентификатора  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]предоставляет набор *символы типа идентификатора*, который можно использовать в объявлении для задания типа данных переменной или константы. В следующей таблице показаны допустимые символы типа идентификатора с примерами их использования.  
  
|Знак типа идентификатора|Тип данных|Пример|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 Символов типа идентификатора не существует для `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, или `UShort` типы данных, или для любых составных типов данных, таких как массивы и структуры.  
  
 В некоторых случаях можно добавить `$` символ [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] функции, например `Left$` вместо `Left`, чтобы получить возвращаемое значение типа `String`.  
  
 Во всех случаях знак типа идентификатора должен следовать непосредственно за имя идентификатора.  
  
## <a name="literal-type-characters"></a>Символы типа литерала  
 Объект *литерала* является текстовым представлением отдельного значения типа данных.  
  
### <a name="default-literal-types"></a>Типы литералов по умолчанию  
 Форма литерала, как он отображается в коде, обычно определяет его тип данных. Ниже приведены эти типы по умолчанию.  
  
|Текстовая форма литерала|Тип данных по умолчанию|Пример|  
|-----------------------------|-----------------------|-------------|  
|Числовые без дробной части|`Integer`|`2147483647`|  
|Числовые без дробной части, слишком велик для`Integer`|`Long`|`2147483648`|  
|Числовые дробной части|`Double`|`1.2`|  
|Заключено в двойные кавычки|`String`|`"A"`|  
|Заключенные в решетки|`Date`|`#5/17/1993 9:32 AM#`|  
  
### <a name="forced-literal-types"></a>Принудительные типы литерала  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]предоставляет набор *символы типа литерала*, указывает, что можно использовать для принудительного присвоения литералу тип данных, отличный от его формы. Это делается путем добавления символа в конец литерала. В следующей таблице показаны допустимые символы типа литерала с примерами их использования.  
  
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
  
 Символы типа литерала существуют для `Boolean`, `Byte`, `Date`, `Object`, `SByte`, или `String` типы данных, или для любых составных типов данных, таких как массивы и структуры.  
  
 Литералы также могут использовать символы типа идентификатора (`%`, `&`, `@`, `!`, `#`, `$`), как и переменные, константы и выражения. Однако, символы типа литерала (`S`, `I`, `L`, `D`, `F`, `R`, `C`) можно использовать только с литералами.  
  
 Во всех случаях знак типа литерала должен следовать непосредственно за литеральное значение.  
  
## <a name="hexadecimal-and-octal-literals"></a>Шестнадцатеричные и восьмеричные литералы  
 Компилятор обычно construes целочисленным литералом в системе счисления десятичным (основание 10). Можно принудительно целое литерала шестнадцатеричным (основание 16) с `&H` префикс и заставить его быть восьмеричным (основание 8) с `&O` префикс. Цифры, располагающиеся за префиксом, должны соответствовать системе счисления. Это показано в следующей таблице.  
  
|Основание системы счисления|Префикс|Допустимые числовые значения|Пример|  
|-----------------|------------|------------------------|-------------|  
|16 (основание 16)|`&H`|0-9 или A-F|`&HFFFF`|  
|8 (основание 8)|`&O`|0-7|`&O77`|  
  
 Вы можете следовать после префикса литерала знак типа литерала. Это показано в следующем примере.  
  
```  
Dim counter As Short = &H8000S  
Dim flags As UShort = &H8000US  
```  
  
 В предыдущем примере `counter` имеет десятичное значение-32768 и `flags` имеет десятичное значение +&32768;.  
  
## <a name="see-also"></a>См. также  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Устранение неполадок типы данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
