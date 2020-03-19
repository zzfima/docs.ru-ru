---
title: Параметры регулярных выражений
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, options
- constructs, options
- .NET Framework regular expressions, options
- inline option constructs
- options parameter
ms.assetid: c82dc689-7e82-4767-a18d-cd24ce5f05e9
ms.openlocfilehash: a53d7517485d2a0b02b6f11928f478a7da3f9503
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73972104"
---
# <a name="regular-expression-options"></a>Параметры регулярных выражений

По умолчанию при сравнении входной строки с любыми литералами в шаблоне регулярного выражения учитывается регистр, пробел в шаблоне интерпретируется как литерал, а захватываемые группы в регулярном выражении именуются как явно, так и неявно. Вы можете изменить эти и некоторые другие аспекты поведения регулярного выражения по умолчанию с помощью параметров регулярного выражения. Эти параметры, которые представлены в следующей таблице, могут быть указаны как часть шаблона регулярного выражения или переданы конструктору класса <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> или статичному методу сопоставления шаблона как значение перечисления <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.

|Член RegexOptions|Встроенный символ|Действие|
|-------------------------|----------------------|------------|
|<xref:System.Text.RegularExpressions.RegexOptions.None>|Недоступно|Использовать поведение по умолчанию. Дополнительные сведения см. в разделе [Параметры по умолчанию](#default-options).|
|<xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase>|`i`|Использовать соответствие без учета регистра. Дополнительные сведения см. в разделе [Сопоставление без учета регистра](#case-insensitive-matching).|
|<xref:System.Text.RegularExpressions.RegexOptions.Multiline>|`m`|Использовать многострочный режим, где `^` и `$` соответствуют началу и концу строки текста (а не началу и концу входной строки). Дополнительные сведения см. в разделе [Многострочный режим](#multiline-mode).|
|<xref:System.Text.RegularExpressions.RegexOptions.Singleline>|`s`|Использовать однострочный режим, где точка (.) соответствует любому символу (а не каждому символу, кроме `\n`). Дополнительные сведения см. в статье [Однострочный режим](#single-line-mode).|
|<xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture>|`n`|Не захватывать неименованные группы. К допустимым захватам относятся только явно именованные или нумерованные группы в формате `(?<`*имя*`>` *часть выражения*`)`. Дополнительные сведения см. в разделе [Только явные захваты](#explicit-captures-only).|
|<xref:System.Text.RegularExpressions.RegexOptions.Compiled>|Недоступно|Скомпилировать регулярное выражение в сборку. Дополнительные сведения см. в разделе [Скомпилированные регулярные выражения](#compiled-regular-expressions).|
|<xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace>|`x`|Исключить неэкранированные пробелы из шаблона и включить комментарии после символа решетки (`#`). Дополнительные сведения см. в статье [Пропуск пробелов](#ignore-white-space).|
|<xref:System.Text.RegularExpressions.RegexOptions.RightToLeft>|Недоступно|Изменить направление поиска. Поиск идет справа налево, а не слева направо. Дополнительные сведения см. в разделе [Режим "справа налево"](#right-to-left-mode).|
|<xref:System.Text.RegularExpressions.RegexOptions.ECMAScript>|Недоступно|Включить поведение, совместимое с ECMAScript, для выражения. Дополнительные сведения см. в разделе [Поведение сопоставления ECMAScript](#ecmascript-matching-behavior).|
|<xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant>|Недоступно|Игнорировать различия региональных параметров в языке. Дополнительные сведения см. в разделе [Сравнение с использованием инвариантных региональных параметров](#comparison-using-the-invariant-culture).|

## <a name="specifying-the-options"></a>Указание параметров

Параметры регулярных выражений можно указать одним из трех способов:

- В параметре `options` конструктора класса <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> или статичного метода сопоставления шаблона (`Shared` в Visual Basic), например <xref:System.Text.RegularExpressions.Regex.%23ctor%28System.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> или <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType>. Параметр `options` — побитовое сложение (логическое ИЛИ) значений перечисления <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.

  Когда параметры передаются экземпляру <xref:System.Text.RegularExpressions.Regex> с помощью параметра `options` конструктора класса, они присваиваются свойству <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>. Однако свойство <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType> не отражает встроенные параметры в самом шаблоне регулярного выражения.

  Ниже приведен пример. В нем параметр `options` метода <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> используется для включения сопоставления без учета регистра и пропуска пробелов при определении слов, начинающихся с буквы "d".

  [!code-csharp[Conceptual.Regex.Language.Options#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/example1.cs#6)]
  [!code-vb[Conceptual.Regex.Language.Options#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/example1.vb#6)]

- Применяя встроенные параметры в шаблоне регулярного выражения с помощью синтаксиса `(?imnsx-imnsx)`. Параметр применяется к шаблону от точки, в которой определен параметр, и действует либо до конца шаблона, либо до точки, в которой другая конструкция отменяет параметр. Обратите внимание на то, что свойство <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType> экземпляра <xref:System.Text.RegularExpressions.Regex> не отражает этих встроенных параметров. Дополнительные сведения см. в разделе [Другие конструкции](../../../docs/standard/base-types/miscellaneous-constructs-in-regular-expressions.md).

  Ниже приведен пример. В нем встроенные параметры используются для включения сопоставления без учета регистра и пропуска пробелов при определении слов, начинающихся с буквы "d".

  [!code-csharp[Conceptual.Regex.Language.Options#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/example1.cs#7)]
  [!code-vb[Conceptual.Regex.Language.Options#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/example1.vb#7)]

- Применяя встроенные параметры в определенной конструкции группировки в шаблоне регулярного выражения с помощью синтаксиса `(?imnsx-imnsx:`*часть выражения*`)`. Если знак перед наборов параметров отсутствует, он включается. Если перед набором параметров есть знак минуса, набор отключается. (`?` — это фиксированная часть синтаксиса языковой конструкции, необходимая, если параметры включаются или отключаются.) Этот параметр применяется только к данной группе. Дополнительные сведения см. в разделе [Конструкции группировки](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).

  Ниже приведен пример. В нем встроенные параметры в конструкции группировки используются для включения сопоставления без учета регистра и пропуска пробелов при определении слов, начинающихся с буквы "d".

  [!code-csharp[Conceptual.Regex.Language.Options#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/example1.cs#8)]
  [!code-vb[Conceptual.Regex.Language.Options#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/example1.vb#8)]

Если параметры указываются в строке, знак минуса (`-`) перед параметром или набором параметров, отключает соответствующие параметры. Например, встроенная конструкция `(?ix-ms)` включает параметры <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> и <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> и отключает параметры <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> и <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType>. Все параметры регулярного выражения по умолчанию отключены.

> [!NOTE]
> Если параметры регулярного выражения, указанные в параметре `options` конструктора или вызове метода, конфликтуют со встроенными параметрами в шаблоне регулярного выражения, используются последние.

Следующие пять параметров регулярного выражения можно задавать одновременно в параметрах метода и в строке:

- <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType>

Следующие пять параметров регулярного выражения можно задавать в параметре `options`, но не в строке:

- <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.RightToLeft?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.ECMAScript?displayProperty=nameWithType>

## <a name="determining-the-options"></a>Определение параметров

Вы можете определить, какие параметры были предоставлены объекту <xref:System.Text.RegularExpressions.Regex> при создании его экземпляра, получив значение свойства <xref:System.Text.RegularExpressions.Regex.Options%2A?displayProperty=nameWithType> только для чтения. Это свойство, в частности, полезно для определения параметров, заданных для скомпилированного регулярного выражения, которое было создано методом <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType>.

Чтобы проверить наличие любого параметра, кроме <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType>, выполните операцию AND со значением свойства <xref:System.Text.RegularExpressions.Regex.Options%2A?displayProperty=nameWithType> и значением <xref:System.Text.RegularExpressions.RegexOptions>, которое вас интересует. Затем проверьте, равен ли результат значению <xref:System.Text.RegularExpressions.RegexOptions>. Следующий пример проверяет, задан ли параметр <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType>.

[!code-csharp[Conceptual.Regex.Language.Options#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/determine1.cs#19)]
[!code-vb[Conceptual.Regex.Language.Options#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/determine1.vb#19)]

Чтобы проверить наличие параметра <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType>, определите, равно ли значение свойства <xref:System.Text.RegularExpressions.Regex.Options%2A?displayProperty=nameWithType> значению <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType>, как показано в следующем примере.

[!code-csharp[Conceptual.Regex.Language.Options#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/determine1.cs#20)]
[!code-vb[Conceptual.Regex.Language.Options#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/determine1.vb#20)]

В следующих разделах перечислены параметры, поддерживаемые регулярными выражениями .NET.

## <a name="default-options"></a>Параметры по умолчанию

Параметр <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType> указывает, что ни один параметр не задан, а механизм регулярных выражений использует поведение по умолчанию. Это поведение характеризуется следующим образом.

- Шаблон интерпретируется как каноническое, а не регулярное выражение ECMAScript.

- Шаблон регулярного выражения сопоставляется во входной строке слева направо.

- При сравнениях учитывается регистр.

- Языковые элементы `^` и `$` сопоставляют начало и конец входной строки.

- Языковой элемент `.` соответствует каждому символу, кроме `\n`.

- Любой пробел в шаблоне регулярного выражения интерпретируется как пробел-литерал.

- При сравнении шаблона со входной строкой используются соглашения текущих региональных параметров.

- Захватываемые группы в шаблоне регулярного выражения являются неявными и явными.

> [!NOTE]
> Параметр <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType> не имеет эквивалента среди встроенных параметров. Если параметры регулярного выражения применяются в строке, поведение по умолчанию восстанавливается для каждого параметра, за счет отключения того или иного параметра. Например, `(?i)` включает сравнение без учета регистра, а `(?-i)` восстанавливает учет регистра при сравнении.

Так как параметр <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType> представляет поведение механизма регулярных выражений по умолчанию, он редко явно указывается в вызове метода. Вместо этого вызывает конструктор или статичный метод сопоставления шаблона без параметра `options`.

## <a name="case-insensitive-matching"></a>Сопоставление без учета регистра

Параметр <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase> или встроенный параметр `i` обеспечивает сопоставление без учета регистра. По умолчанию используются соглашения о регистре текущих региональных параметров.

Следующий пример определяет шаблон регулярного выражения, `\bthe\w*\b`, который сопоставляет все слова, начинающиеся со строки "the". Так как первый вызов метода <xref:System.Text.RegularExpressions.Regex.Match%2A> использует сравнение с учетом регистра по умолчанию, в выходных данных указывается, что строка "The" в начале предложения, не была сопоставлена. Она выделяется, если метод <xref:System.Text.RegularExpressions.Regex.Match%2A> вызывается с параметрами <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase>.

[!code-csharp[Conceptual.Regex.Language.Options#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/case1.cs#1)]
[!code-vb[Conceptual.Regex.Language.Options#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/case1.vb#1)]

Следующий пример изменяет шаблон регулярного выражения из предыдущего примера для использования встроенных параметров вместо параметра `options`, чтобы включить сравнение без учета регистра. Первый шаблон определяет параметр отключения учета регистра в конструкции группировки, которая применяется только к букве "t" в строке "the". Так как конструкция указана в начале шаблона, второй шаблон применяет параметр учета регистра ко всему регулярному выражению.

[!code-csharp[Conceptual.Regex.Language.Options#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/case2.cs#2)]
[!code-vb[Conceptual.Regex.Language.Options#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/case2.vb#2)]

## <a name="multiline-mode"></a>Многострочный режим

Параметр <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> или встроенный параметр `m` позволяет механизму регулярных выражений обрабатывать входную строку, которая состоит из нескольких строк. Он изменяет интерпретацию языковых элементов `^` и `$`, чтобы они сопоставляли начало и конец строки текста, а не начало и строки входной строки.

По умолчанию `$` сопоставляет конец входной строки. Если указать параметр <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>, он сопоставляет символ новой строки (`\n`) или конец входной строки. Однако он не сопоставляет комбинацию символов возврата каретки и перевода строки. Для их успешного сопоставления используйте часть выражения `\r?$` вместо `$`.

Следующий пример извлекает имена и баллы игроков в боулинг и добавляет их в коллекцию <xref:System.Collections.Generic.SortedList%602>, где они сортируются по убыванию. Метод <xref:System.Text.RegularExpressions.Regex.Matches%2A> вызывается два раза. В первом вызове метода используется регулярное выражение `^(\w+)\s(\d+)$`, параметры не заданы. Как видно в результатах, совпадения не найдены, так как механизм регулярных выражений не может сопоставить входной шаблон с началом и концом входной строки. Во втором вызове метода регулярное выражение меняется на `^(\w+)\s(\d+)\r?$` и задаются параметры <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>. Как видно в результатах, имена и баллы успешно сопоставляются, а баллы отображаются по убыванию.

[!code-csharp[Conceptual.Regex.Language.Options#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/multiline1.cs#3)]
[!code-vb[Conceptual.Regex.Language.Options#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/multiline1.vb#3)]

Шаблон регулярного выражения `^(\w+)\s(\d+)\r*$` определяется, как показано в следующей таблице.

|Шаблон|Описание|
|-------------|-----------------|
|`^`|Начало с первого символа строки.|
|`(\w+)`|Совпадение с одним или несколькими символами слова. Это первая группа записи.|
|`\s`|Соответствует пробелу.|
|`(\d+)`|Совпадение с одной или несколькими десятичными цифрами. Это вторая группа записи.|
|`\r?`|Сопоставление нуля или одного символа возврата каретки.|
|`$`|Окончание в конце строки.|

Следующий пример аналогичен предыдущему, но он использует встроенный параметр `(?m)` для включения многострочного режима.

[!code-csharp[Conceptual.Regex.Language.Options#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/multiline2.cs#4)]
[!code-vb[Conceptual.Regex.Language.Options#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/multiline2.vb#4)]

## <a name="single-line-mode"></a>Однострочный режим

Параметр <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> или встроенный параметр `s` позволяет механизму регулярных выражений обрабатывать входную строку так, будто она состоит из одной строки. Для этого поведение языкового элемента `.` меняется так, чтобы он сопоставлял каждый символ, а не каждый символ, кроме символа новой строки `\n` или \u000A.

В следующем примере показано, как поведение языкового элемента `.` меняется при использовании параметра <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType>. Регулярное выражение `^.+` начинается с начала строки и соответствует любому знаку. По умолчанию соответствие заканчивается в конце первой строки; шаблон регулярного выражения соответствует символу возврата каретки, `\r` или \u000D, но не соответствует `\n`. Поскольку параметр <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> интерпретирует всю входную строку как единую строку, он сопоставляет каждый символ в строке ввода, включая `\n`.

[!code-csharp[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any2.cs#5)]
[!code-vb[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any2.vb#5)]

Следующий пример аналогичен предыдущему, но он использует встроенный параметр `(?s)` для включения однострочного режима.

[!code-csharp[Conceptual.Regex.Language.Options#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/singleline1.cs#5)]
[!code-vb[Conceptual.Regex.Language.Options#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/singleline1.vb#5)]

## <a name="explicit-captures-only"></a>Только явные захваты

По умолчанию захватываемые группы определяются с помощью круглых скобок в шаблоне регулярного выражения. Именованным группам назначается имя или номер с помощью параметра языка `(?<`*имя*`>`*часть выражения*`)`. Неименованные группы доступны по индексу. В объекте <xref:System.Text.RegularExpressions.GroupCollection> неименованные группы идут перед именованными.

Конструкции группировки часто используются только для применения квантификаторов к нескольким языковым элементам, а захваченные подстроки не представляют интереса. Например, если следующее регулярное выражение,

`\b\(?((\w+),?\s?)+[\.!?]\)?`

, предназначено только для извлечения предложений, которые оканчиваются на точку, восклицательный или вопросительный знак из документа, только полученное предложение (в объекте <xref:System.Text.RegularExpressions.Match>) представляет интерес, а отдельные слова в коллекции — нет.

Захватываемые группы, которые не используются в последствии, могут потреблять много ресурсов, так как механизм регулярных выражений должны заполнить объекты <xref:System.Text.RegularExpressions.GroupCollection> и <xref:System.Text.RegularExpressions.CaptureCollection> коллекции. В качестве альтернативы можно использовать параметр <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType> или встроенный параметр `n`, чтобы указать, что допустимыми захватами являются только явно именованные или нумерованные группы, обозначенными конструкцией `(?<`*имя*`>` *часть выражения*`)`.

Следующий пример отображает сведения о сопоставлениях, возвращаемых шаблоном регулярного выражения `\b\(?((\w+),?\s?)+[\.!?]\)?`, если метод <xref:System.Text.RegularExpressions.Regex.Match%2A> вызывается с параметром <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType> или без него. Как видно в результатах выполнения первого вызова метода, механизм регулярных выражений полностью заполняет объекты коллекции <xref:System.Text.RegularExpressions.GroupCollection> и <xref:System.Text.RegularExpressions.CaptureCollection> данными о выделенных подстроках. Так как второй метод вызывается с параметром `options`, для которого задано значение <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType>, он не записывает информацию о группах.

[!code-csharp[Conceptual.Regex.Language.Options#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/explicit1.cs#9)]
[!code-vb[Conceptual.Regex.Language.Options#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/explicit1.vb#9)]

Шаблон регулярного выражения `\b\(?((?>\w+),?\s?)+[\.!?]\)?` определяется так, как показано в следующей таблице.

|Шаблон|Описание|
|-------------|-----------------|
|`\b`|Начало на границе слова.|
|`\(?`|Сопоставляется ноль или один экземпляр открывающих круглых скобок ("(").|
|`(?>\w+),?`|Сопоставляется один или несколько словообразующих символов, за которыми следует ноль или одна запятая. При сопоставлении словообразующих символов обратный поиск не применяется.|
|`\s?`|Совпадение с нулем или одним символом пробела.|
|`((\w+),?\s?)+`|Один или несколько раз выделяет комбинацию из одного или нескольких символов, нуля или одной запятой, нуля или одного пробела.|
|`[\.!?]\)?`|Сопоставляются любые из трех знаков пунктуации, за которыми следует ноль или одна закрывающая круглая скобка (")").|

Вы также можете использовать встроенный элемент `(?n)`, чтобы отключить автоматическое выделение. Следующий пример изменяет предыдущий шаблон регулярного выражения, чтобы использовать встроенный элемент `(?n)` вместо параметра <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType>.

[!code-csharp[Conceptual.Regex.Language.Options#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/explicit2.cs#10)]
[!code-vb[Conceptual.Regex.Language.Options#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/explicit2.vb#10)]

Наконец, вы можете использовать встроенный элемент группы `(?n:)`, чтобы отключить автоматическое выделение для отдельных групп. Следующий пример изменяет предыдущий шаблон, чтобы отключить неименованные выделения во внешней группе, `((?>\w+),?\s?)`. Обратите внимание, что при этом подавляются неименованные выделения и во внутренней группе.

[!code-csharp[Conceptual.Regex.Language.Options#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/explicit3.cs#11)]
[!code-vb[Conceptual.Regex.Language.Options#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/explicit3.vb#11)]

## <a name="compiled-regular-expressions"></a>Скомпилированные регулярные выражения

По умолчанию регулярные выражения в .NET интерпретируются. Когда создается экземпляр объекта <xref:System.Text.RegularExpressions.Regex> или вызывается статичный метод <xref:System.Text.RegularExpressions.Regex>, шаблон регулярного выражения преобразуется в набор настраиваемых кодов операций, а интерпретатор использует их для выполнения регулярного выражения. С этим связан компромисс: затраты на инициализацию механизма регулярных выражений уменьшаются за счет производительности во время выполнения.

Вместо интерпретируемых регулярных выражений можно использовать скомпилированные регулярные выражения, указав параметр <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>. В этом случае при передаче шаблона механизму регулярных выражений он разбивается на набор кодов операций и преобразуется в инструкции MSIL, которые можно передать напрямую среде CLR. Скомпилированные регулярные выражения повышают производительность во время выполнения, но за счет более длительной инициализации.

> [!NOTE]
> Чтобы скомпилировать регулярное выражение, необходимо передать значение <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> параметру `options` конструктора класса <xref:System.Text.RegularExpressions.Regex> или статичного метода сопоставления шаблона. Этот параметр не может быть указан как встроенный.

Вы можете использовать скомпилированные регулярные выражения в вызовах статичных регулярных выражений и регулярных выражений экземпляров. В статичных регулярных выражениях параметр <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> передается в параметр `options` метода сопоставления шаблона регулярного выражения. В регулярных выражениях экземпляра он передается в параметр `options` конструктора класса <xref:System.Text.RegularExpressions.Regex>. В обоих случаях это повышает производительность.

Однако такой рост производительности возможен только в следующих условиях:

- Объект <xref:System.Text.RegularExpressions.Regex>, представляющий определенное регулярное выражение, используется в нескольких вызовах методов сопоставления шаблона регулярного выражения.

- Объект <xref:System.Text.RegularExpressions.Regex> не может выходить за область применения, поэтому его можно использовать повторно.

- Статичное регулярное выражение используется в нескольких вызовах методов сопоставления шаблона регулярного выражения. (Рост производительности возможен, так как регулярные выражения, используемые в вызовах статичных методов, кэшируются механизмом регулярных выражений.)

> [!NOTE]
> Параметр <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> не связан с методом <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType>, который создает специальную сборку с предварительно определенными скомпилированными регулярными выражениями.

## <a name="ignore-white-space"></a>Пропуск пробелов

По умолчанию пробел в шаблоне регулярного выражения учитывается. Он заставляет механизм регулярных выражений сопоставлять символ пробела во входной строке. Поэтому регулярные выражения "`\b\w+\s`" и "`\b\w+`" практически аналогичны. Кроме того, если в шаблоне регулярного выражения найден символ решетки (#), он интерпретируется как литерал, который необходимо сопоставить.

Параметр <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> или встроенный параметр `x` меняет такое поведение следующим образом:

- Неэкранированный пробел в шаблоне регулярного выражения игнорируется. Чтобы включить пробелы в шаблон регулярного выражения, их необходимо экранировать (например, как `\s` или "`\`").

- Символ решетки (#) интерпретируется как начало комментария, а не литерал. Весь текст в шаблоне регулярного выражения с символа # до конца строки интерпретируется как комментарий.

Но в следующих случаях пробелы в регулярном выражении не игнорируются, даже если указан параметр <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType>.

- Пробел в классе символов всегда интерпретируется как литерал. Например, шаблон регулярного выражения `[ .,;:]` сопоставляет любой отдельный символ пробела, точки, запятой, точки с запятой и двоеточия.

- Пробел не допускается в квантификаторах, окруженных квадратными скобками, таких как `{`*n*`}`, `{`*n*`,}` и `{`*n*`,`*m*`}`. Например, шаблон регулярного выражения `\d{1, 3}` не сопоставляет последовательности цифр из одной до трех цифр, так как он содержит пробел.

- Пробел не допускается в последовательности символов, предоставляющей языковой элемент. Пример:

  - Языковой элемент `(?:`*subexpression*`)` представляет незахватываемую группу, а часть `(?:` элемента не может включать пробелы. Шаблон `(? :`*часть выражения*`)` вызывает исключение <xref:System.ArgumentException> во время выполнения, так как механизм регулярных выражений не может проанализировать шаблон, а шаблону `( ?:`*часть выражения*`)` не удается сопоставить *часть выражения*.

  - Языковой элемент `\p{`*name*`}`, представляющий категорию Юникода или именованный блок, не может содержать пробелы в части `\p{` элемента. Если все-таки добавить пробел, элемент вызовет исключение <xref:System.ArgumentException> во время выполнения.

Включение этого параметра позволяет упростить регулярные выражения, синтаксический анализ и понимание которых зачастую вызывают затруднения. Это улучшает читаемость и позволяет документировать регулярное выражение.

В этом примере определяется следующий шаблон регулярного выражения:

`\b \(? ( (?>\w+) ,?\s? )+  [\.!?] \)? # Matches an entire sentence.`

Этот шаблон похож на тот, что был определен в разделе [Только явные захваты](#explicit-captures-only), но он использует параметр <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> для пропуска пробелов в шаблоне.

[!code-csharp[Conceptual.Regex.Language.Options#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/whitespace1.cs#12)]
[!code-vb[Conceptual.Regex.Language.Options#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/whitespace1.vb#12)]

Следующий пример использует встроенный параметр `(?x)` для пропуска пробелов.

[!code-csharp[Conceptual.Regex.Language.Options#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/whitespace2.cs#13)]
[!code-vb[Conceptual.Regex.Language.Options#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/whitespace2.vb#13)]

## <a name="right-to-left-mode"></a>Режим "справа налево"

По умолчанию механизм регулярных выражений выполняет поиска слева направо. Направление поиска можно изменить с помощью параметра <xref:System.Text.RegularExpressions.RegexOptions.RightToLeft?displayProperty=nameWithType>. Поиск автоматически будет начинаться с последнего символа строки. Для методов сопоставления шаблона с параметром начальной позиции, таких как <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.Int32%29?displayProperty=nameWithType>, начальная позиция — это индекс самого правого символа, с которого начинается поиск.

> [!NOTE]
> Чтобы включить режим "справа налево", необходимо передать значение <xref:System.Text.RegularExpressions.RegexOptions.RightToLeft?displayProperty=nameWithType> параметру `options` конструктора класса <xref:System.Text.RegularExpressions.Regex> или статичного метода сопоставления шаблона. Этот параметр не может быть указан как встроенный.

Параметр <xref:System.Text.RegularExpressions.RegexOptions.RightToLeft?displayProperty=nameWithType> меняет только направление поиска, а не интерпретирует шаблон регулярного выражения справа налево. Например, регулярное выражение `\bb\w+\s` сопоставляет слова, которые начинаются с буквы "b" и за которыми следует пробел. В следующем примере входная строка состоит из трех слов, которые содержат одну или несколько букв "b". Первое слово начинается с "b", второе заканчивается на "b", а в третьем буква "b" находится в середине слова. Как видно из результата примера, только первое слово соответствует шаблону регулярного выражения.

[!code-csharp[Conceptual.Regex.Language.Options#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/righttoleft1.cs#17)]
[!code-vb[Conceptual.Regex.Language.Options#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/righttoleft1.vb#17)]

Кроме того, обратите внимание, что утверждение просмотра вперед (фрагмент языка `(?=`*subexpression*`)`) и утверждение просмотра назад (элемент языка `(?<=`*subexpression*`)`) не изменяют направление поиска. Утверждения просмотра вперед выполняют поиск вправо, а утверждения просмотра назад — влево. Например, регулярное выражение `(?<=\d{1,2}\s)\w+,?\s\d{4}` использует утверждения просмотра назад для проверки наличия даты, перед которой идет название месяца. Затем регулярное выражение сопоставляет месяц и год. Сведения об утверждениях просмотра вперед и назад см. в статье [Конструкции группировки в регулярных выражениях](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).

[!code-csharp[Conceptual.Regex.Language.Options#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/righttoleft2.cs#18)]
[!code-vb[Conceptual.Regex.Language.Options#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/righttoleft2.vb#18)]

Шаблон регулярного выражения определяется, как показано в следующей таблице.

|Шаблон|Описание|
|-------------|-----------------|
|`(?<=\d{1,2}\s)`|Слева от начала сопоставления должна идти одна или две десятичных цифры, за которыми следует пробел.|
|`\w+`|Совпадение с одним или несколькими символами слова.|
|`,?`|Выделяется ноль или один символ запятой.|
|`\s`|Соответствует пробелу.|
|`\d{4}`|Выделяются 4 десятичные цифры.|

## <a name="ecmascript-matching-behavior"></a>Поведение сопоставления ECMAScript

По умолчанию механизм регулярных выражений использует каноническое поведение при сопоставлении шаблона регулярного выражения с входным текстом. Но вы можете использовать поведение сопоставления ECMAScript, указав параметр <xref:System.Text.RegularExpressions.RegexOptions.ECMAScript?displayProperty=nameWithType>.

> [!NOTE]
> Чтобы включить поведение ECMAScript, необходимо передать значение <xref:System.Text.RegularExpressions.RegexOptions.ECMAScript?displayProperty=nameWithType> параметру `options` конструктора класса <xref:System.Text.RegularExpressions.Regex> или статичного метода сопоставления шаблона. Этот параметр не может быть указан как встроенный.

Параметр <xref:System.Text.RegularExpressions.RegexOptions.ECMAScript?displayProperty=nameWithType> может использоваться только вместе с параметрами <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> и <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>. При использовании других параметров в регулярном выражении возникает исключение <xref:System.ArgumentOutOfRangeException>.

Поведение регулярных выражений ECMAScript и канонических регулярных выражений отличается в трех аспектах: синтаксис класса символов, ссылающиеся на себя захватываемые группы и интерпретация восьмеричных значений и обратных ссылок.

- Синтаксис класса символов. Так как канонические регулярные выражения поддерживают Юникод, а ECMAScript — нет, синтаксис классов символов в ECMAScript более ограничен, а некоторые языковые элементы класса символов обладают другим значением. Например, ECMAScript не поддерживает такие языковые элементы, как категория Юникода или элементы блока `\p` и `\P`. Аналогичным образом, элемент `\w`, который сопоставляет словообразующее слово, эквивалентен классу символов `[a-zA-Z_0-9]` при использовании ECMAScript и `[\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]` при использовании канонического поведения. Дополнительные сведения см. в разделе [Классы символов](../../../docs/standard/base-types/character-classes-in-regular-expressions.md).

  Следующий пример иллюстрирует разницу между каноническим сопоставлением шаблона и ECMAScript. В нем определяется регулярное выражение, `\b(\w+\s*)+`, сопоставляющее слова, за которыми следуют пробелы. Входные данные состоят из двух строк, одна из которых использует латиницу, а другая — кириллицу. Как видно из результата, при вызове метода <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType>, использующего сопоставление ECMAScript, не удается сопоставить слова на кириллице, а при вызове метода, использующего каноническое сопоставление — удается.

  [!code-csharp[Conceptual.Regex.Language.Options#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/ecmascript1.cs#16)]
  [!code-vb[Conceptual.Regex.Language.Options#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/ecmascript1.vb#16)]

- Ссылающиеся на себя захватываемые группы Класс захвата регулярного выражения с обратной ссылкой на себя необходимо обновлять после каждой итерации выделения. Как показано в следующем примере, это позволяет регулярному выражению `((a+)(\1) ?)+` сопоставить входную строку " aa aaaa aaaaaa " при использовании ECMAScript, но не канонического сопоставления.

  [!code-csharp[Conceptual.Regex.Language.Options#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/ecmascript2.cs#21)]
  [!code-vb[Conceptual.Regex.Language.Options#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/ecmascript2.vb#21)]

  Определение регулярного выражения показано в следующей таблице.

  |Шаблон|Описание|
  |-------------|-----------------|
  |(a+)|Буква "a" выделяется один или несколько раз. Это вторая группа записи.|
  |(\1)|Сопоставление подстроки, выделенной первой захватываемой группой. Это третья группа записи.|
  |?|Выделяется ноль или один символ пробела.|
  |((a+)(\1) ?)+|Один или несколько раз выделяется шаблон из одной или нескольких букв "a", за которыми следует строка, сопоставляющая первую захватываемую группу, за которой следует ноль или один символ пробела. Это первая группа записи.|

- Разрешение неоднозначности между восьмеричными Escape-символами и обратными ссылками. В следующей таблице представлены общие сведения об отличиях интерпретации восьмеричных чисел и обратных ссылок при использовании канонических регулярных выражений и ECMAScript.

  |Регулярное выражение|Каноническое поведение|Поведение ECMAScript|
  |------------------------|------------------------|-------------------------|
  |`\0` с последующими 0-2 восьмеричными цифрами|Интерпретируется как восьмеричное число. Например, `\044` всегда интерпретируется как восьмеричное значение и означает "$".|Такое же поведение.|
  |`\` с последующей цифрой от 1 до 9, за которой нет дополнительных десятичных цифр.|Интерпретируется как обратная ссылка. Например, `\9` всегда означает обратную ссылку на 9, даже если девятая захватываемая группа не существует. Если захватываемая группа не существует, анализатор регулярных выражений вызывает исключение <xref:System.ArgumentException>.|Если захватываемая группа из одной десятичной цифры существует, значение интерпретируется как обратная ссылка на эту цифру. В противном случае оно интерпретируется как литерал.|
  |`\` с последующей цифрой от 1 до 9, за которой следуют дополнительные десятичные цифры.|Цифры интерпретируются как десятичное значение. Если эта захватываемая группа существует, выражение интерпретируется как обратная ссылка.<br /><br /> В противном случае интерпретируются первые восьмеричные цифры до восьмеричного числа 377, т. е. учитываются только младшие 8 разрядов значения. Оставшиеся цифры интерпретируются как литералы. Например, выражение `\3000`, если захватываемая группа 300 существует, интерпретируется как обратная ссылка на 300. В противном случае оно интерпретируется как восьмеричное число 300, за которым следует 0.|Выражение интерпретируется как обратная ссылка, для этого как можно больше цифр преобразуется в десятичное значение, которые могут указывать на выделение. Если цифры не могут быть преобразованы, выражение интерпретируется как восьмеричное число с использованием первых восьмеричных разрядов до восьмеричного числа 377. Оставшиеся восьмеричные цифры интерпретируются как литералы.|

## <a name="comparison-using-the-invariant-culture"></a>Сравнение с использованием инвариантных региональных параметров

По умолчанию, когда механизм регулярных выражений выполняет сравнения без учета регистра, соглашения о регистре текущих региональных параметров используются для определения эквивалентных прописных и строчных символов.

Однако это недопустимо для некоторых типов сравнения, например при сравнении введенных пользователем данных с именами системных ресурсов, таких как пароли, файлы и URL-адреса. В следующем примере показана подобная ситуация. Этот код предназначен для блокировки доступа к любым ресурсам, URL-адрес которых начинается с **FILE://** . Регулярное выражение пытается выполнить сопоставление без учета регистра, используя регулярное выражение `$FILE://`. Но текущие региональные параметры заданы как tr-TR (Турецкий-Турция), и "I" — не является прописным эквивалентом "i". В результате вызов метода <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> возвращает `false`, и предоставляется доступ к файлу.

[!code-csharp[Conceptual.Regex.Language.Options#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/culture1.cs#14)]
[!code-vb[Conceptual.Regex.Language.Options#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/culture1.vb#14)]

> [!NOTE]
> Подробнее о сравнении строк с учетом регистра и использовании инвариантных региональных параметров см. в разделе [Рекомендации по использованию строк в .NET](../../../docs/standard/base-types/best-practices-strings.md).

Вместо использования сравнений без учета регистра текущих региональных параметров, можно указать параметр <xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant?displayProperty=nameWithType>, чтобы игнорировать региональные отличия в языке и использовать соглашения инвариантных региональных параметров.

> [!NOTE]
> Чтобы включить сравнение с использованием инвариантных региональных параметров, необходимо передать значение <xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant?displayProperty=nameWithType> параметру `options` конструктора класса <xref:System.Text.RegularExpressions.Regex> или статичного метода сопоставления шаблона. Этот параметр не может быть указан как встроенный.

Следующий пример идентичен предыдущему, но в нем статичный метод <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> вызывается с параметрами, содержащими <xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant?displayProperty=nameWithType>. Даже если в качестве региональных параметров выбрано "Турецкий (Турция)", механизм регулярных выражений сможет успешно сопоставить строки "FILE" и "file" и заблокировать доступ к файлу.

[!code-csharp[Conceptual.Regex.Language.Options#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/culture1.cs#15)]
[!code-vb[Conceptual.Regex.Language.Options#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/culture1.vb#15)]

## <a name="see-also"></a>См. также

- [Элементы языка регулярных выражений — краткий справочник](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
