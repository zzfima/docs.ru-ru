---
title: Устранение неполадок, связанных с типами данных (Visual Basic)
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
ms.openlocfilehash: c5ff9d097c0660956a9751a23511d8273766227c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655789"
---
# <a name="troubleshooting-data-types-visual-basic"></a>Устранение неполадок, связанных с типами данных (Visual Basic)
Этой странице перечислены некоторые общие проблемы, которые могут возникнуть при выполнении операций над встроенными типами данных.  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a>Выражения с плавающей запятой не считаются равными  
 При работе с числами с плавающей запятой ([одного типа данных](../../../../visual-basic/language-reference/data-types/single-data-type.md) и [тип данных Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)), помните, что они хранятся в виде двоичных дробей. Это означает, что они не содержат точное представление любого числа, которое не является двоичной дробью (формы k / (2 ^ n) где k и n являются целыми числами). Например 0,5 (= 1/2) и 0.3125 (= 5/16) могут храниться как точные значения, тогда как 0,2 (= 1/5) и 0,3 (= 3/10) могут быть только аппроксимацией.  
  
 По этой причине неточности, нельзя полагаться на точные результаты при работе с значения с плавающей запятой. В частности два значения, равные теоретически может иметь несколько различных представлений.  
  
| Для сравнения чисел с плавающей запятой | 
|---| 
|1.  Вычислите абсолютное значение их разницы с помощью <xref:System.Math.Abs%2A> метод <xref:System.Math> класса в <xref:System> пространства имен.<br />2.  Определите допустимую максимальную разницу, таким образом, можно рассмотреть два количества будет равно практической точки зрения, если их различие не больше.<br />3.  Сравните абсолютное значение разницы с допустимой разницей.|  
  
 В следующем примере показано неправильное и правильное сравнение двух `Double` значения.  
  
 [!code-vb[VbVbalrDataTypes#10](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 В предыдущем примере используется <xref:System.Double.ToString%2A> метод <xref:System.Double> структурировать таким образом, чтобы его можно указать точность лучше, чем `CStr` использует ключевое слово. Значение по умолчанию — 15 цифр, но формата «G17» расширяет его до 17 знаков.  
  
## <a name="mod-operator-does-not-return-accurate-result"></a>Оператор Mod не возвращает точный результат  
 Из-за неточности числа с плавающей запятой хранилища [оператор Mod](../../../../visual-basic/language-reference/operators/mod-operator.md) может возвращать непредвиденный результат, когда по крайней мере один из операндов с плавающей запятой.  
  
 [Тип данных Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) не использует представление с плавающей запятой. Многие числа, которые не являются точными в `Single` и `Double` являются точными в `Decimal` (например, 0,2 и 0,3). Хотя вычисления происходят медленнее `Decimal` чем в с плавающей запятой, может иметь смысл снизить производительность ради большей точности.  
  
|Чтобы найти целочисленный остаток чисел с плавающей запятой|  
|---|  
|1.  Объявите переменные как `Decimal`.<br />2.  Использовать знак типа литерала `D` для приведения литералов в `Decimal`, если их значения слишком велики для `Long` тип данных.|  
  
 В следующем примере показано возможная неточность операндов с плавающей запятой.  
  
 [!code-vb[VbVbalrDataTypes#11](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 В предыдущем примере используется <xref:System.Double.ToString%2A> метод <xref:System.Double> структурировать таким образом, чтобы его можно указать точность лучше, чем `CStr` использует ключевое слово. Значение по умолчанию — 15 цифр, но формата «G17» расширяет его до 17 знаков.  
  
 Поскольку `zeroPointTwo` — `Double`, его значение 0,2 является периодической бесконечной двоичной дробью, сохраненное значение 0,20000000000000001. Деление 2.0 на это количество дает 9,9999999999999995 с остатком 0,19999999999999991.  
  
 В выражении для `decimalRemainder`, знак типа литерала `D` приводит оба операнда для `Decimal`, и 0,2 имеет точное представление. Поэтому `Mod` оператор возвращает ожидаемый остаток 0,0.  
  
 Обратите внимание, что недостаточно для объявления `decimalRemainder` как `Decimal`. Также необходимо привести литералы в `Decimal`, или они используют `Double` по умолчанию и `decimalRemainder` получает же неточное значение как `doubleRemainder`.  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>Логический тип не выполняет преобразование в числовой тип точно  
 [Тип данных Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) значения не хранятся в виде чисел, и хранимые значения не должны быть эквивалентными числам. Для обеспечения совместимости с более ранними версиями Visual Basic предоставляет ключевые слова преобразований ([функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`и так далее) для преобразования между `Boolean` и числовых типов. Тем не менее, других языках эти преобразования иногда выполняются по-разному, как и [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] методы.  
  
 Никогда не следует писать код, который основывается на эквивалентных числовых значениях для `True` и `False`. Когда это возможно, следует ограничить использование `Boolean` переменные с логическими значениями, для которых они предназначены. Если требуется смешать `Boolean` и числовые значения, убедитесь в том, что вы понимаете метод преобразования, который выбран.  
  
### <a name="conversion-in-visual-basic"></a>Преобразование в Visual Basic  
 При использовании `CType` или `CBool` ключевые слова преобразований для преобразования числовых типов данных для `Boolean`, 0 становится `False` и все остальные значения становятся `True`. При преобразовании `Boolean` значения в числовые типы с помощью ключевых слов преобразования, `False` становится 0 и `True` становится 1.  
  
### <a name="conversion-in-the-framework"></a>Преобразование в Framework  
 <xref:System.Convert.ToInt32%2A> Метод <xref:System.Convert> класса в <xref:System> преобразует пространство имен `True` до + 1.  
  
 Если необходимо преобразовать `Boolean` значение числового типа данных, будьте внимательны о том, какой метод преобразования используются.  
  
## <a name="character-literal-generates-compiler-error"></a>Символьный литерал создает ошибку компилятора  
 В случае отсутствия любого типа знаков Visual Basic использует по умолчанию типы данных для литералов. Тип по умолчанию для литерала знаков, заключен в кавычки (`" "`) — является `String`.  
  
 `String` Тип данных не расширяется до [тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md). Это означает, что если вы хотите назначить литерал к `Char` переменных, необходимо сделать сужающего преобразования или приведения литерала к `Char` типа.  

|Для создания литерала, присваиваемое переменной или константы Char|
|---|  
|1.  Объявите переменную или константу как `Char`.<br />2.  Заключите значение символа в кавычки (`" "`).<br />3.  После закрытия двойных кавычек с знак типа литерала `C` для приведения литерала к `Char`. Это необходимо, если переключатель проверки типа ([оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) является `On`, и желательно в любом случае.|  
  
 В следующем примере демонстрируется успешные и неудачные попытки назначения литерала `Char` переменной.  
  
 [!code-vb[VbVbalrDataTypes#12](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]  
  
 Всегда есть риск при использовании сужающего преобразования, так как они могут завершиться ошибкой во время выполнения. Например, преобразование из `String` для `Char` может завершиться ошибкой, если `String` значение содержит более одного символа. Поэтому в программировании лучше использовать `C` тип символа.  
  
## <a name="string-conversion-fails-at-run-time"></a>Не удается преобразовать строку во время выполнения  
 [Строкового типа данных](../../../../visual-basic/language-reference/data-types/string-data-type.md) участвует в очень мало расширяющие преобразования. `String` расширяется только до себя и `Object`и только `Char` и `Char()` ( `Char` массива) расширяются до `String`. Это вызвано `String` переменными и константами, может содержать значения, которые не могут содержать другие типы данных.  
  
 Если переключатель проверки типа ([оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) является `On`, компилятор запрещает все неявные сужающие преобразования. Это включает те включающие `String`. Код по-прежнему можно использовать ключевые слова преобразований например `CStr` и [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md), которые направляют [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] предпринимается попытка преобразования.  
  
> [!NOTE]
>  Ошибка сужающего преобразования отбрасывается при преобразовании из элементов в `For Each…Next` коллекции для управляющей переменной цикла. Дополнительные сведения и примеры см. в подразделе «Сужающие преобразования» [For Each... Следующий оператор](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="narrowing-conversion-protection"></a>Защита сужающего преобразования  
 Сужающие преобразования недостатком является то, что они могут завершиться ошибкой во время выполнения. Например если `String` переменная содержит ничего, кроме «True» или «False», он не может быть преобразован `Boolean`. Если она содержит знаки препинания, не удалось выполнить преобразование любого числового типа. Если известно, что ваш `String` переменная всегда содержит значения, которые может принимать конечный тип, преобразование не рекомендуется.  
  
 Если необходимо преобразовать из `String` в другой тип данных безопасной процедурой является заключить попытку преобразования в [Try... CATCH... Оператор Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Это позволяет вам работать с ошибкой во время выполнения.  
  
### <a name="character-arrays"></a>Массив знаков  
 Один `Char` и массив `Char` элементов расширяемы до `String`. Тем не менее `String` не расширяется до `Char()`. Чтобы преобразовать `String` значение `Char` массива, можно использовать <xref:System.String.ToCharArray%2A> метод <xref:System.String?displayProperty=nameWithType> класса.  
  
### <a name="meaningless-values"></a>Не имеющие смысла значения  
 Как правило `String` значения не имеют смысла в другие типы данных, и преобразование высокой искусственный и опасно. Когда это возможно, следует ограничить использование `String` переменные для последовательности символов, для которых они предназначены. Никогда не следует писать код, который основывается на эквивалентных значения других типов.  
  
## <a name="see-also"></a>См. также  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Знаки типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Эффективное использование типов данных](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
