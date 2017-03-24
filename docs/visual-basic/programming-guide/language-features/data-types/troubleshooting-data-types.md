---
title: "Устранение неполадок типы данных (Visual Basic) | Документы Microsoft"
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
- Char data type, converting
- Decimal data type, conversions
- data types [Visual Basic], troubleshooting
- literals, default types
- type characters, literal
- Mod operator [Visual Basic], in floating-point operations
- troubleshooting Visual Basic, data types
- troubleshooting data types
- floating-point numbers, precision
- Boolean data type, converting
- literal types
- literal type characters
- floating-point numbers, imprecision
- String data type, converting
- floating-point numbers, comparison
- floating-point numbers
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
caps.latest.revision: 29
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
ms.openlocfilehash: cfb8fc77d3e0d85ef795a94fc95ab61a8f68ff39
ms.lasthandoff: 03/13/2017

---
# <a name="troubleshooting-data-types-visual-basic"></a>Устранение неполадок, связанных с типами данных (Visual Basic)
На этой странице перечислены некоторые общие проблемы, которые могут возникнуть при выполнении операций над встроенными типами данных.  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a>Выражения с плавающей запятой не сравниваются в равенстве  
 При работе с числами с плавающей запятой ([одного типа данных](../../../../visual-basic/language-reference/data-types/single-data-type.md) и [тип данных Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)), помните, что они хранятся в виде двоичных дробей. Это означает, что они не содержат точное представление любого числа, которое не является двоичной дробью (формы k / (2 ^ n) где k, а n — целые числа). Например 0,5 (= 1/2) и 0.3125 (= 5/16) могут храниться как точные значения, в то время как 0,2 (= 1/5) и 0,3 (= 3/10) могут быть только аппроксимацией.  
  
 Из-за этого неточности, нельзя полагаться на точные результаты при работе с значения с плавающей запятой. В частности два значения, равные теоретически может иметь несколько различных представлений.  
  
| Для сравнения чисел с плавающей запятой | 
|---| 
|1.  Вычислите абсолютное значение их разницы, с помощью <xref:System.Math.Abs%2A>метод <xref:System.Math>класса в <xref:System>имен.</xref:System> </xref:System.Math> </xref:System.Math.Abs%2A><br />2.  Определите допустимую максимальную разницу, таким образом, что можно будет равно практической точки зрения, если их различие не больше двух величин.<br />3.  Сравните абсолютное значение разницы с допустимой разницей.|  
  
 В следующем примере показано неправильное и правильное сравнение двух `Double` значения.  
  
 [!code-vb[VbVbalrDataTypes&#10;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 В предыдущем примере используется <xref:System.Double.ToString%2A>метод <xref:System.Double>структуры, чтобы можно было указать точность лучше, чем `CStr` использует ключевое слово.</xref:System.Double> </xref:System.Double.ToString%2A> Значение по умолчанию — 15 цифр, но формат «G17» расширяет его до 17 знаков.  
  
## <a name="mod-operator-does-not-return-accurate-result"></a>Оператор Mod не возвращает точный результат  
 Из-за неточности числа с плавающей запятой хранения [оператор Mod](../../../../visual-basic/language-reference/operators/mod-operator.md) может возвращать непредвиденный результат, когда по крайней мере один из операндов с плавающей запятой.  
  
 [Тип данных Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) не использует представление с плавающей запятой. Количество номеров, которые не являются точными в `Single` и `Double` являются точными в `Decimal` (например, 0,2 и 0,3). Хотя вычисления происходят медленнее `Decimal` чем в с плавающей запятой, может иметь смысл снизить производительность ради большей точности.  
  
|Чтобы найти целочисленный остаток чисел с плавающей запятой|  
|---|  
|1.  Объявите переменные как `Decimal`.<br />2.  Используйте знак типа литерала `D` для приведения литералов в `Decimal`, если их значения слишком велики для `Long` тип данных.|  
  
 В следующем примере показано возможная неточность операндов с плавающей запятой.  
  
 [!code-vb[VbVbalrDataTypes&11;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 В предыдущем примере используется <xref:System.Double.ToString%2A>метод <xref:System.Double>структуры, чтобы можно было указать точность лучше, чем `CStr` использует ключевое слово.</xref:System.Double> </xref:System.Double.ToString%2A> Значение по умолчанию — 15 цифр, но формат «G17» расширяет его до 17 знаков.  
  
 Поскольку `zeroPointTwo` — `Double`, его значение 0,2 является периодической бесконечной двоичной дробью, хранится в виде значения 0,20000000000000001. Деление на 2,0 этого количества дает 9,9999999999999995 с остатком 0,19999999999999991.  
  
 В выражении для `decimalRemainder`, знак типа литерала `D` приводит оба операнда для `Decimal`, и 0,2 имеет точное представление. Поэтому `Mod` оператор дает ожидаемый остаток 0,0.  
  
 Обратите внимание, что недостаточно для объявления `decimalRemainder` как `Decimal`. Необходимо также привести литералы в `Decimal`, или они используют `Double` по умолчанию и `decimalRemainder` получает тоже самое неточное значение как `doubleRemainder`.  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>Тип Boolean не выполняет преобразование в числовой тип точно  
 [Тип данных Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) значения не хранятся в виде чисел, и хранимые значения не предназначены для быть эквивалентными числам. Для обеспечения совместимости с более ранними версиями [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] содержит ключевые слова преобразований ([функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`и так далее) для преобразования между `Boolean` и числовых типов. Однако других языках эти преобразования иногда выполняются по-разному, как и [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] методы.  
  
 Никогда не следует писать код, который основывается на эквивалентных числовых значениях для `True` и `False`. Когда это возможно, следует ограничить использование `Boolean` переменные с логическими значениями, для которых они предназначены. Если необходимо смешать `Boolean` и числовые значения, убедитесь в том, что вы понимаете метод преобразования, который выбран.  
  
### <a name="conversion-in-visual-basic"></a>Преобразование в Visual Basic  
 При использовании `CType` или `CBool` ключевые слова преобразований для преобразования числовых типов данных для `Boolean`, 0 становится `False` и все остальные значения становятся `True`. При преобразовании `Boolean` значения в числовые типы с помощью зарезервированных слов преобразования `False` становится 0 и `True` становится 1.  
  
### <a name="conversion-in-the-framework"></a>Преобразование в Framework  
 <xref:System.Convert.ToInt32%2A>Метод <xref:System.Convert>класса в <xref:System>имен преобразует `True` до +&1;.</xref:System> </xref:System.Convert> </xref:System.Convert.ToInt32%2A>  
  
 Если необходимо преобразовать `Boolean` значение числового типа данных, будьте внимательны о том, какой метод преобразования можно использовать.  
  
## <a name="character-literal-generates-compiler-error"></a>Символьная константа создает ошибку компилятора  
 В случае отсутствия любого типа знаков [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] предполагает стандартные типы данных для литералов. Тип по умолчанию для литерала знаков, заключен в кавычки (`" "`), является `String`.  
  
 `String` Тип данных не расширяется до [тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md). Это означает, что если вы хотите назначить литерал к `Char` переменных, необходимо либо сделать сужающее преобразование или приведения литерала к `Char` типа.  

|Для создания литерала для присвоения переменной или константе Char|
|---|  
|1.  Объявите переменную или константу как `Char`.<br />2.  Заключите значение символа в кавычки (`" "`).<br />3.  После закрытия двойных кавычек с знак типа литерала `C` для приведения литерала к `Char`. Это необходимо, если переключатель проверки типа ([оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) является `On`, и желательно в любом случае.|  
  
 В следующем примере демонстрируется успешные и неудачные попытки назначения литерала `Char` переменной.  
  
 [!code-vb[VbVbalrDataTypes&#12;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]  
  
 Всегда существует риск при использовании сужающего преобразования, так как они могут завершиться ошибкой во время выполнения. Например, преобразование из `String` для `Char` может завершиться ошибкой, если `String` значение содержит более одного символа. Поэтому в программировании лучше использовать `C` знак типа.  
  
## <a name="string-conversion-fails-at-run-time"></a>Не удается преобразовать строку во время выполнения  
 [Строковый тип данных](../../../../visual-basic/language-reference/data-types/string-data-type.md) участвует в очень мало расширяющие преобразования. `String`расширяется только до себя и `Object`и только `Char` и `Char()` ( `Char` массива) расширяются до `String`. Это вызвано `String` переменных и констант может содержать значения, которые не могут содержать другие типы данных.  
  
 Если переключатель проверки типа ([оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) является `On`, компилятор запрещает все неявные сужающие преобразования. Это включает те включающие `String`. Код по-прежнему можно использовать ключевые слова преобразований например `CStr` и [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md), которые направляют [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] попытки преобразования.  
  
> [!NOTE]
>  Ошибка сужающего преобразования отбрасывается при преобразовании из элементов в `For Each…Next` коллекцию для переменной цикла. Дополнительные сведения и примеры см. в разделе «Сужающие преобразования» [For Each... Следующий оператор](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="narrowing-conversion-protection"></a>Защита сужающего преобразования  
 Недостатком сужающих преобразований является то, что они могут завершиться ошибкой во время выполнения. Например если `String` переменная содержит ничего, кроме «True» или «False», он не может быть преобразован `Boolean`. Если она содержит знаки препинания, не удается преобразование в любой числовой тип. Если известно, что ваш `String` переменная всегда содержит значения, которые может принимать конечный тип, преобразование не рекомендуется.  
  
 Если необходимо преобразовать из `String` в другой тип данных, самой безопасной процедурой является заключить попытку преобразования в [Try... CATCH... Оператор Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Это позволяет вам работать с ошибкой во время выполнения.  
  
### <a name="character-arrays"></a>Массив знаков  
 Один `Char` и массив `Char` элементов расширяемы до `String`. Тем не менее `String` не расширяется до `Char()`. Чтобы преобразовать `String` значение `Char` массива, можно использовать <xref:System.String.ToCharArray%2A>метод <xref:System.String?displayProperty=fullName>класса.</xref:System.String?displayProperty=fullName> </xref:System.String.ToCharArray%2A>  
  
### <a name="meaningless-values"></a>Не имеющие смысла значения  
 Как правило `String` значения не имеют смысла в других типах данных, и преобразование высокой искусственный и опасным. Когда это возможно, следует ограничить использование `String` переменные последовательности символов, для которых они предназначены. Никогда не следует писать код, который основывается на эквивалентных значения других типов.  
  
## <a name="see-also"></a>См. также  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Знаки типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Эффективное использование типов данных](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
