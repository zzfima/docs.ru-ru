---
title: Устранение неполадок, связанных с типами данных
ms.date: 07/20/2015
helpviewer_keywords:
- Char data type [Visual Basic], converting
- Decimal data type [Visual Basic], conversions
- data types [Visual Basic], troubleshooting
- literals [Visual Basic], default types
- type characters [Visual Basic], literal
- Mod operator [Visual Basic], in floating-point operations
- troubleshooting Visual Basic, data types
- troubleshooting data types [Visual Basic]
- floating-point numbers [Visual Basic], precision
- Boolean data type [Visual Basic], converting
- literal types [Visual Basic]
- literal type characters [Visual Basic]
- floating-point numbers [Visual Basic], imprecision
- String data type [Visual Basic], converting
- floating-point numbers [Visual Basic], comparison
- floating-point numbers
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
ms.openlocfilehash: 63b2513e420320742bf7e25314743f08404f46a7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350517"
---
# <a name="troubleshooting-data-types-visual-basic"></a>Устранение неполадок, связанных с типами данных (Visual Basic)

На этой странице перечислены некоторые распространенные проблемы, которые могут возникнуть при выполнении операций с внутренними типами данных.

## <a name="floating-point-expressions-do-not-compare-as-equal"></a>Выражения с плавающей запятой не считаются равными

При работе с числами с плавающей запятой ([один тип данных](../../../../visual-basic/language-reference/data-types/single-data-type.md) и [тип данных Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)) помните, что они хранятся в виде двоичных дробей. Это означает, что они не могут содержать точное представление любого количества, которое не является двоичной дробью (в форме k/(2 ^ n), где k и n являются целыми числами). Например, 0,5 (= 1/2) и 0,3125 (= 5/16) могут храниться как точные значения, тогда как 0,2 (= 1/5) и 0,3 (= 3/10) могут быть только приближениями.

Из-за этого неточности нельзя полагаться на точные результаты при работе с значениями с плавающей запятой. В частности, два значения, которые теоретически равны, могут иметь несколько различных представлений.

| Сравнение количества с плавающей запятой |
|---|
|1. Вычислите абсолютное значение их разности с помощью метода <xref:System.Math.Abs%2A> класса <xref:System.Math> в пространстве имен <xref:System>.<br />2. Определите допустимое максимальное различие, чтобы можно было считать, что два количества равны для практических целей, если их отличие больше.<br />3. Сравните абсолютное значение разницы с приемлемой разницей.|

В следующем примере показаны неверное и правильное сравнение двух `Double` значений.

[!code-vb[VbVbalrDataTypes#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#10)]

В предыдущем примере используется метод <xref:System.Double.ToString%2A> структуры <xref:System.Double>, чтобы можно было указать лучшую точность, чем ключевое слово `CStr`. По умолчанию используется 15 цифр, но формат "G17" расширяет его до 17 цифр.

## <a name="mod-operator-does-not-return-accurate-result"></a>Оператор Mod не возвращает точный результат

Из-за неправильной точности хранилища с плавающей запятой [оператор Mod](../../../../visual-basic/language-reference/operators/mod-operator.md) может вернуть непредвиденный результат, если хотя бы один из операндов является плавающей запятой.

[Тип данных Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) не использует представление с плавающей запятой. Многие числа, неточные в `Single` и `Double`, являются точными в `Decimal` (например, 0,2 и 0,3). Несмотря на то, что арифметические операции выполняются медленнее, чем в `Decimal` с плавающей запятой, может возникнуть снижение производительности, чтобы добиться лучшей точности.

|Поиск целочисленного остатка количества с плавающей запятой|
|---|
|1. Объявите переменные как `Decimal`.<br />2. Используйте символ типа литерала `D` для принудительного `Decimal`литералов, если их значения слишком велики для `Long`ного типа данных.|

В следующем примере показана потенциальная неточность операндов с плавающей запятой.

[!code-vb[VbVbalrDataTypes#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#11)]

В предыдущем примере используется метод <xref:System.Double.ToString%2A> структуры <xref:System.Double>, чтобы можно было указать лучшую точность, чем ключевое слово `CStr`. По умолчанию используется 15 цифр, но формат "G17" расширяет его до 17 цифр.

Поскольку `zeroPointTwo` имеет `Double`, его значение для 0,2 является бесконечным повторением двоичной дроби с хранимым значением 0.20000000000000001. При делении 2,0 на это количество выдается 9.9999999999999995 с остатком от 0.19999999999999991.

В выражении для `decimalRemainder`символ типа литерала `D` принудительно применяет оба операнда к `Decimal`, а 0,2 имеет точное представление. Поэтому оператор `Mod` выдает ожидаемый остаток от 0,0.

Обратите внимание, что объявление `decimalRemainder` как `Decimal`не является достаточным. Необходимо также принудительно принудить литералы `Decimal`или использовать `Double` по умолчанию и `decimalRemainder` получают то же неточное значение, что и `doubleRemainder`.

## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>Логический тип не преобразуется в числовой тип точно

Значения [логических типов данных](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) не хранятся в виде чисел, а хранимые значения не должны быть эквивалентны числам. Для совместимости с более ранними версиями Visual Basic предоставляет ключевые слова преобразования ([Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`и т. д.) для преобразования между `Boolean` и числовыми типами. Однако другие языки иногда выполняют эти преобразования по-разному, так же как и методы .NET Framework.

Никогда не следует писать код, который использует эквивалентные числовые значения для `True` и `False`. Везде, где это возможно, следует ограничить использование переменных `Boolean` логическими значениями, для которых они предназначены. Если необходимо смешивать `Boolean` и числовые значения, убедитесь, что вы понимаете выбранный метод преобразования.

### <a name="conversion-in-visual-basic"></a>Преобразование в Visual Basic

При использовании ключевых слов преобразования `CType` или `CBool` для преобразования числовых типов данных в `Boolean`0 становится `False`, а все остальные значения становятся `True`. При преобразовании `Boolean` значений в числовые типы с помощью ключевых слов преобразования `False` преобразуется в 0, а `True` преобразуется в значение-1.

### <a name="conversion-in-the-framework"></a>Преобразование в платформе

Метод <xref:System.Convert.ToInt32%2A> класса <xref:System.Convert> в пространстве имен <xref:System> преобразует `True` в + 1.

Если необходимо преобразовать `Boolean` значение в числовой тип данных, будьте внимательны с тем, какой метод преобразования используется.

## <a name="character-literal-generates-compiler-error"></a>Символьный литерал создает ошибку компилятора

В отсутствие каких бы то ни было символов типа Visual Basic предполагает наличие типов данных по умолчанию для литералов. Тип по умолчанию для символьного литерала, заключенный в кавычки (`" "`), `String`.

Тип данных `String` не расширяется до [типа данных char](../../../../visual-basic/language-reference/data-types/char-data-type.md). Это означает, что если необходимо присвоить литерал переменной `Char`, необходимо либо выполнить сужение преобразования, либо выполнить принудительное преобразование литерала в тип `Char`.

|Создание литерала Char для присвоения переменной или константе|
|---|
|1. Объявите переменную или константу как `Char`.<br />2. заключите значение символа в кавычки (`" "`).<br />3. Используйте закрывающую двойную кавычку с символьным типом литерала `C`, чтобы присвоить литералу `Char`. Это необходимо, если параметр проверки типов ([оператор Option строго](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) имеет `On`и желательно в любом случае.|

В следующем примере показаны неудачные и успешные назначения литерала в переменную `Char`.

[!code-vb[VbVbalrDataTypes#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#12)]

При использовании сужающих преобразований всегда возникает риск, так как они могут завершиться ошибкой во время выполнения. Например, преобразование из `String` в `Char` может завершиться ошибкой, если значение `String` содержит более одного символа. Поэтому в программировании лучше использовать символ типа `C`.

## <a name="string-conversion-fails-at-run-time"></a>Сбой преобразования строки во время выполнения

[Строковый тип данных](../../../../visual-basic/language-reference/data-types/string-data-type.md) участвует в очень редких расширяющихся преобразованиях. `String` расширяется только на себя и `Object`, и только `Char` и `Char()` (массив `Char`) расширяются до `String`. Это обусловлено тем, что `String` переменные и константы могут содержать значения, которые не могут содержать другие типы данных.

Если параметр проверки типов ([оператор Option строго](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) имеет `On`, компилятор запрещает все неявные сужающие преобразования. Сюда входят те, которые включают `String`. Код по-прежнему может использовать ключевые слова преобразования, такие как `CStr` и [CType](../../../../visual-basic/language-reference/functions/ctype-function.md), которые направляют .NET Framework для попыток преобразования.

> [!NOTE]
> Ошибка сужения преобразования подавляется для преобразований из элементов коллекции `For Each…Next` в переменную управления циклом. Дополнительные сведения и примеры см. в подразделе «сужающие преобразования» раздела [For Each... Следующий оператор](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).

### <a name="narrowing-conversion-protection"></a>Сужение защиты от преобразования

Недостаток сужающих преобразований заключается в том, что они могут привести к сбою во время выполнения. Например, если переменная `String` содержит любые значения, отличные от "true" или "false", ее нельзя преобразовать в `Boolean`. Если он содержит знаки препинания, преобразование в любой числовой тип завершается ошибкой. Если вы не уверены, что переменная `String` всегда содержит значения, которые тип назначения может принять, не следует пытаться выполнить преобразование.

Если необходимо выполнить преобразование из `String` в другой тип данных, наиболее надежной процедурой является заключить попытку преобразования в [try... Перехватить... Оператор finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Это позволяет справиться с ошибкой во время выполнения.

### <a name="character-arrays"></a>Массивы символов

Один `Char` и массив `Char`ных элементов расширяются до `String`. Однако `String` не расширяется для `Char()`. Чтобы преобразовать `String` значение в массив `Char`, можно использовать метод <xref:System.String.ToCharArray%2A> класса <xref:System.String?displayProperty=nameWithType>.

### <a name="meaningless-values"></a>Бессмысленные значения

В общем случае `String` значения не имеют смысла в других типах данных, а преобразование является очень искусственным и опасным. Всякий раз, когда это возможно, следует ограничить использование переменных `String` в последовательности символов, для которых они предназначены. Никогда не следует писать код, основанный на эквивалентных значениях других типов.

## <a name="see-also"></a>См. также

- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Знаки типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Эффективное использование типов данных](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
