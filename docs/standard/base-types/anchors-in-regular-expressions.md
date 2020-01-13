---
title: Привязки в регулярных выражениях .NET
description: Узнайте, как использовать привязки в шаблонах регулярных выражений.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- atomic zero-width assertions
- regular expressions, anchors
- regular expressions, atomic zero-width assertions
- anchors, in regular expressions
- metacharacters, atomic zero-width assertions
- metacharacters, anchors
- .NET Framework regular expressions, anchors
- .NET Framework regular expressions, atomic zero-width assertions
ms.assetid: 336391f6-2614-499b-8b1b-07a6837108a7
ms.openlocfilehash: 319aa76754adc852528f35448d9906d4e903693b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711549"
---
# <a name="anchors-in-regular-expressions"></a>Привязки в регулярных выражениях
Привязки (или атомарные утверждения нулевой ширины) указывают положение в строке, где должно быть найдено соответствие. При использовании привязки в выражении поиска обработчик регулярных выражений не проходит по строке и не потребляет символы; он ищет соответствия только в заданном местоположении. Например, `^` указывает, что соответствие должно начаться в начале строки. Таким образом, регулярное выражение `^http:` находит соответствие для http, только если этот элемент находится в начале строки. В таблице ниже перечислены привязки, поддерживаемые регулярными выражениями в .NET.  
  
|Привязка|Описание|  
|------------|-----------------|  
|`^`|По умолчанию соответствие должно обнаруживаться в начале строки. В многострочном режиме соответствие должно обнаруживаться в начале линии. Дополнительные сведения см. в разделе [Начало строки](#start-of-string-or-line-).|  
|`$`|По умолчанию соответствие должно обнаруживаться в конце строки или перед символом `\n` в конце строки. В многострочном режиме соответствие должно обнаруживаться в конце линии или перед символом `\n` в конце линии. Дополнительные сведения см. в разделе [Конец строки](#end-of-string-or-line-).|  
|`\A`|Соответствие должно находиться только в начале строки (многострочность не поддерживается). Дополнительные сведения см. в разделе [Только начало строки](#start-of-string-only-a).|  
|`\Z`|Соответствие должно находиться в конце строки или до символа `\n` в конце строки. Дополнительные сведения см. в разделе [Конец строки или до конца символа новой строки](#end-of-string-or-before-ending-newline-z).|  
|`\z`|Соответствие должно находиться исключительно в конце строки. Дополнительные сведения см. в разделе [Только конец строки](#end-of-string-only-z).|  
|`\G`|Соответствие должно начинаться в точке, где завершилось предыдущее соответствие. Дополнительные сведения см. в разделе [Непрерывные совпадения](#contiguous-matches-g).|  
|`\b`|Соответствие должно находиться на границе слова. Дополнительные сведения см. в разделе [Граница слова](#word-boundary-b).|  
|`\B`|Соответствие не должно находиться на границе слова. Дополнительные сведения см. в разделе [Не на границе слова](#non-word-boundary-b).|  

## <a name="start-of-string-or-line-"></a>Начало строки: ^  
 По умолчанию привязка `^` указывает, что следующий шаблон должен начинаться на месте первого символа строки. Если используется символ `^` с параметром <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> (см. руководство по [параметрам регулярных выражений](../../../docs/standard/base-types/regular-expression-options.md)), в начале каждой строки следует обеспечить соответствие.  
  
 В следующем примере используется привязка `^` в регулярном выражении, которое извлекает сведения о годах, в течение которых существовали некоторые профессиональные бейсбольные команды. В примере вызывается две перегрузки метода <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> .  
  
- При вызове перегрузки <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%29> удается найти только первую подстроку в строке ввода, которая соответствует шаблону регулярного выражения.  
  
- Вызов перегрузки <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29> с параметром `options` , имеющим значение <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> , позволяет найти все пять подстрок.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/startofstring1.cs#1)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/startofstring1.vb#1)]  
  
 Шаблон регулярного выражения `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+` определяется, как показано в следующей таблице.  
  
|Шаблон|Описание|  
|-------------|-----------------|  
|`^`|Соответствие должно начинаться в начале входной строки (или в начале строки, если метод вызывается с параметром <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> ).|  
|`((\w+(\s?)){2,}`|Сопоставление одного или нескольких символов слов, за которыми следует ноль или один пробел, хотя бы два раза. Это первая группа записи. Это выражение также определяет вторую и третью группу записи: вторая состоит из записанного слова, а третья — из записанных пробелов.|  
|`,\s`|Сопоставление запятой, за которой следует пробел.|  
|`(\w+\s\w+)`|Сопоставление одного или более символов слов, за которыми следует пробел и один или более символов слов. Это четвертая группа записи.|  
|`,`|Сопоставление запятой.|  
|`\s\d{4}`|Сопоставление пробела, за которым следуют четыре десятичные цифры.|  
|<code>(-(\d{4}&#124;present))?</code>|Сопоставление нулевого или единичного вхождения дефиса, за которым следуют четыре десятичные цифры или строка present. Это шестая группа записи. Она также включает седьмую группу записи.|  
|`,?`|Сопоставление нулевого или единичного вхождения запятой.|  
|<code>(\s\d{4}(-(\d{4}&#124;present))?,?)+</code>|Сопоставление одного или нескольких вхождений следующих символов: пробела, четырех десятичных цифр, нулевого или единичного вхождения дефиса, за которым следуют четыре десятичные цифры или строка present, нуля или одной запятой. Это пятая группа записи.| 

## <a name="end-of-string-or-line-"></a>Конец строки: $  
 Привязка `$` указывает, что предыдущий шаблон должен находиться в конце входной строки или перед символом `\n` в конце входной строки.  
  
 Если используется символ `$` с параметром <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> , соответствие также может иметь место в конце строки. Обратите внимание, что `$` соответствует `\n` , но не соответствует `\r\n` (комбинации символов возврата и перевода строки каретки или CR/LF). Чтобы сопоставить комбинацию символов CR/LF, включите `\r?$` в шаблон регулярного выражения.  
  
 В следующем примере добавляется привязка `$` к шаблону регулярного выражения, используемого в примере из раздела [Начало строки](#start-of-string-or-line-) . При использовании с исходной входной строкой, которая включает пять строк текста, методу <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%29?displayProperty=nameWithType> не удается найти соответствие, потому что конец первой строки не соответствует шаблону `$` . Если исходная входная строка разбивается на массив строк, методу <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%29?displayProperty=nameWithType> удается найти соответствие для каждой из пяти строк. Если метод <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> вызывается с параметром `options` , для которого задано значение <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>, соответствия не найдены, потому что шаблон регулярного выражения не учитывает элемент возврата каретки (\u+000D). Однако изменение шаблона регулярного выражения (замена `$` последовательностью `\r?$`) приведет к тому, что вызов метода <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> с параметром `options` , равным <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> , позволит снова найти пять соответствий.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/endofstring1.cs#2)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/endofstring1.vb#2)]     

## <a name="start-of-string-only-a"></a>Только начало строки: \A  
 Привязка `\A` указывает, что соответствие должно находиться в начале входной строки. Она идентична привязке `^` с той разницей, что `\A` игнорирует параметр <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> . Следовательно, можно найти соответствие только для начала первой строки в многострочной входной строке.  
  
 Следующий пример похож на примеры для привязок `^` и `$` . В нем привязка `\A` используется в регулярном выражении, которое извлекает сведения о годах, в течение которых существовали некоторые профессиональные бейсбольные команды. Входная строка включает пять строк. При вызове метода <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> удается найти только первую подстроку во входной строке, которая соответствует шаблону регулярного выражения. Как показано в примере, параметр <xref:System.Text.RegularExpressions.RegexOptions.Multiline> не оказывает никакого влияния.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/startofstring2.cs#3)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/startofstring2.vb#3)]     

## <a name="end-of-string-or-before-ending-newline-z"></a>Конец строки или до конца символа новой строки: \Z  
 Привязка `\Z` указывает, что соответствие должно находиться в конце входной строки или перед символом `\n` в конце входной строки. Она идентична привязке `$` с той разницей, что `\Z` игнорирует параметр <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> . Таким образом, в многострочной строке она может соответствовать только концу последней строки или последней строке до символа `\n`.  
  
 Обратите внимание, что `\Z` соответствует `\n` но не соответствует `\r\n` (комбинации символов CR/LF). Для нахождения соответствия CR/LF включите `\r?\Z` в шаблон регулярного выражения.  
  
 В следующем примере используется привязка `\Z` в регулярном выражении, которая похожа на использованную в примере из раздела [Начало строки](#start-of-string-or-line-) и которая извлекает информацию о годах, в течение которых существовали некоторые профессиональные бейсбольные команды. Часть выражения `\r?\Z` в регулярном выражении `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\Z` соответствует концу строки, а также соответствует строке, которая заканчивается на `\n` или `\r\n`. В результате каждый элемент в массиве соответствует шаблону регулярного выражения.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/endofstring2.cs#4)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/endofstring2.vb#4)]     

## <a name="end-of-string-only-z"></a>Только начало строки: \z  
 Привязка `\z` указывает, что соответствие должно находиться в конце входной строки. Как и языковой элемент `$` , `\z` игнорирует параметр <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> . В отличие от языкового элемента `\Z``\z` не сопоставляет символ `\n` в конце строки. Таким образом, соответствие может находиться только в последней строке входной строки.  
  
 В следующем примере используется привязка `\z` в регулярном выражении, которая похожа на использованную в примере из предыдущего раздела с той разницей, что она извлекает информацию о годах, в течение которых существовали некоторые профессиональные бейсбольные команды. В примере предпринимается попытка сопоставить каждый из пяти элементов в массиве строк шаблону регулярного выражения `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\z`. Две строки оканчиваются символом возврата каретки и перевода строки, одна заканчивается символом перевода строки, и еще две — ни символом возврата каретки, ни символом перевода строки. Как показывают выходные данные, шаблону соответствуют только строки без символа возврата каретки и перевода строки.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/endofstring3.cs#5)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/endofstring3.vb#5)]    

## <a name="contiguous-matches-g"></a>Непрерывные совпадения: \G  
 Привязка `\G` указывает, что соответствие должно находиться в точке окончания предыдущего соответствия. При использовании этой привязки с методом <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> или <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> гарантируется непрерывность всех совпадений.  
  
 В следующем примере регулярное выражение используется для извлечения имен видов грызунов из строки с разделителями запятыми.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/contiguous1.cs#6)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/contiguous1.vb#6)]  
  
 Возможные интерпретации регулярного выражения `\G(\w+\s?\w*),?` показаны в следующей таблице.  
  
|Шаблон|Описание|  
|-------------|-----------------|  
|`\G`|Начать сопоставление там, где закончилось последнее соответствие.|  
|`\w+`|Совпадение с одним или несколькими символами слова.|  
|`\s?`|Совпадение с нулем или одним пробелом.|  
|`\w*`|Совпадение с нулем или большим числом буквенных символов.|  
|`(\w+\s?\w*)`|Сопоставление одного или более символов слов, за которыми ноль или один пробел, а затем ноль или более символов слов. Это первая группа записи.|  
|`,?`|Сопоставление нулевому или единичному вхождению литерального символа запятой.|     

## <a name="word-boundary-b"></a>Граница слова: \b  
 Привязка `\b` указывает, что соответствие должно находиться на границе между символом слова (языковым элементом `\w` ) и несловесным символом (языковым элементом `\W` ). Символы слов — это буквенно-цифровые символы и подчеркивания; несловесные символы — это все остальные символы. (См. дополнительные сведения см. о [классах символов](../../../docs/standard/base-types/character-classes-in-regular-expressions.md).) Соответствие может также находиться на границе слова в начале или конце строки.  
  
 Привязку `\b` часто используют, чтобы убедиться, что часть выражения соответствует всему слову, а не просто окончанию или началу слова. Регулярное выражение `\bare\w*\b` в следующем примере демонстрируется использование этой привязки. Она соответствует любому слову, которое начинается с подстроки are. Выходные данные в этом примере также показывают, что `\b` соответствует началу и концу входной строки.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/word1.cs#7)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/word1.vb#7)]  
  
 Возможные интерпретации шаблона регулярного выражения показаны в следующей таблице.  
  
|Шаблон|Описание|  
|-------------|-----------------|  
|`\b`|Совпадение должно начинаться на границе слова.|  
|`are`|Совпадение с подстрокой are.|  
|`\w*`|Совпадение с нулем или большим числом буквенных символов.|  
|`\b`|Совпадение должно заканчиваться на границе слова.|  

## <a name="non-word-boundary-b"></a>Не на границе слова: \B  
 Привязка `\B` указывает, что соответствие не должно находиться на границе слова. Это противоположность привязки `\b` .  
  
 В следующем примере привязка `\B` используется для обнаружения вхождений в слове подстроки qu. Шаблон регулярного выражения `\Bqu\w+` соответствует подстроке, которая начинается с qu, которое не находится в начале слова и продолжается до конца слова.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/nonword1.cs#8)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/nonword1.vb#8)]  
  
 Возможные интерпретации шаблона регулярного выражения показаны в следующей таблице.  
  
|Шаблон|Описание|  
|-------------|-----------------|  
|`\B`|Совпадение не должно начинаться на границе слова.|  
|`qu`|Совпадение с подстрокой qu.|  
|`\w+`|Совпадение с одним или несколькими символами слова.|  
  
## <a name="see-also"></a>См. также

- [Элементы языка регулярных выражений — краткий справочник](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
- [Параметры регулярных выражений](../../../docs/standard/base-types/regular-expression-options.md)
