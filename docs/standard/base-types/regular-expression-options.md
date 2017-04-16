---
title: "Параметры регулярных выражений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Параметры регулярных выражений"
  - "конструкции, параметры"
  - "Регулярные выражения .NET framework, параметры"
  - "конструкции подставляемых параметров"
  - "options - параметр"
ms.assetid: c82dc689-7e82-4767-a18d-cd24ce5f05e9
caps.latest.revision: 27
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 27
---
# Параметры регулярных выражений
<a name="Top"></a>По умолчанию сравнение входной строки с любыми литералами в шаблоне регулярного выражения чувствительно к регистру, пробелы в шаблоне регулярного выражения интерпретируется как литеральные знаки пустого пространства и группы захвата в регулярном выражении именуются как явно и неявно. Вы можете изменить эти и некоторые другие аспекты поведения регулярного выражения по умолчанию с помощью параметров регулярного выражения. Эти параметры, которые представлены в следующей таблице, могут быть указаны как часть шаблона регулярного выражения или переданы конструктору класса <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> или статичному методу сопоставления шаблона как значение перечисления <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.  
  
|Член RegexOptions|Встроенный символ|Действие|  
|-------------------------|----------------------|------------|  
|<xref:System.Text.RegularExpressions.RegexOptions>|Недоступно|Использовать поведение по умолчанию. Дополнительные сведения см. в разделе [Параметры по умолчанию](#Default).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|`i`|Использовать соответствие без учета регистра. Дополнительные сведения см. в разделе [Сопоставление без учета регистра](#Case).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|`m`|Использовать многострочный режим, где `^` и `$` соответствуют началу и концу строки текста (а не началу и концу входной строки). Дополнительные сведения см. в разделе [Многострочный режим](#Multiline).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|`s`|Использовать однострочный режим, где точка (.) соответствует любому символу (а не каждому символу, кроме `\n`). Дополнительные сведения см. в разделе [Однострочный режим](#Singleline).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|`n`|Не захватывать неименованные группы. Единственные допустимые записи являются явно именованные или пронумерованными группами в форме `(?<` *имя* `>` *часть выражения*`)`. Дополнительные сведения см. в разделе [Только явные захваты](#Explicit).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|Недоступно|Скомпилировать регулярное выражение в сборку. Дополнительные сведения см. в разделе [Скомпилированные регулярные выражения](#Compiled).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|`x`|Исключить неэкранированные пробелы из шаблона и включить комментарии после символа решетки (`#`). Дополнительные сведения см. в разделе [Игнорирование пробела](#Whitespace).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|Недоступно|Изменить направление поиска. Поиск идет справа налево, а не слева направо. Дополнительные сведения см. в разделе [Режим "справа налево"](#RightToLeft).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|Недоступно|Включить поведение, совместимое с ECMAScript, для выражения. Дополнительные сведения см. в разделе [Поведение сопоставления ECMAScript](#ECMAScript).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|Недоступно|Игнорировать различия региональных параметров в языке. Дополнительные сведения см. в разделе [Сравнение с использованием инвариантных региональных параметров](#Invariant).|  
  
## <a name="specifying-the-options"></a>Указание параметров  
 Параметры регулярных выражений можно указать одним из трех способов:  
  
-   В `options` параметр <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> конструктор класса или static (`Shared` в Visual Basic) метод поиска совпадения с шаблоном, такой как <xref:System.Text.RegularExpressions.Regex.%23ctor%28System.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=fullName> или <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=fullName>. `options` Параметр является побитовое сочетание OR <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> значений перечисления.  
  
     Когда параметры передаются в <xref:System.Text.RegularExpressions.Regex> экземпляр с помощью `options` параметра конструктора класса, назначенные <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> свойство. Однако свойство <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> не отражает встроенные параметры в самом шаблоне регулярного выражения.  
  
     Ниже приведен пример. Он использует `options` параметр <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=fullName> метод для включения сопоставления без учета регистра и пропуска пробелов при определении слов, начинающихся с буквы «d».  
  
     [!code-csharp[Conceptual.Regex.Language.Options#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/example1.cs#6)]
     [!code-vb[Conceptual.Regex.Language.Options#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/example1.vb#6)]  
  
-   Применяя встроенные параметры в шаблоне регулярного выражения с помощью синтаксиса `(?imnsx-imnsx)`. Параметр применяется к шаблону от точки, в которой определен параметр, и действует либо до конца шаблона, либо до точки, в которой другая конструкция отменяет параметр. Обратите внимание, что свойство <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> экземпляра <xref:System.Text.RegularExpressions.Regex> не отражает этих встроенных параметров. Дополнительные сведения см. в разделе [прочие конструкции](../../../docs/standard/base-types/miscellaneous-constructs-in-regular-expressions.md) раздела.  
  
     Ниже приведен пример. В нем встроенные параметры используются для включения сопоставления без учета регистра и пропуска пробелов при определении слов, начинающихся с буквы "d".  
  
     [!code-csharp[Conceptual.Regex.Language.Options#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/example1.cs#7)]
     [!code-vb[Conceptual.Regex.Language.Options#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/example1.vb#7)]  
  
-   Применяя встроенные параметры в определенной группе конструкции в шаблон регулярного выражения с помощью синтаксиса `(?imnsx-imnsx:` *часть выражения*`)`. Если знак перед наборов параметров отсутствует, он включается. Если перед набором параметров есть знак минуса, набор отключается. (`?` — это фиксированная часть синтаксиса языковой конструкции, необходимая, если параметры включаются или отключаются.) Этот параметр применяется только к данной группе. Дополнительные сведения см. в разделе [конструкции группировки](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
     Ниже приведен пример. В нем встроенные параметры в конструкции группировки используются для включения сопоставления без учета регистра и пропуска пробелов при определении слов, начинающихся с буквы "d".  
  
     [!code-csharp[Conceptual.Regex.Language.Options#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/example1.cs#8)]
     [!code-vb[Conceptual.Regex.Language.Options#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/example1.vb#8)]  
  
 Если параметры указываются в строке, знак минуса (`-`) перед параметром или набором параметров, отключает соответствующие параметры. Например, встроенная конструкция `(?ix-ms)` включает <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> и <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> и отключает <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> и <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> параметры. Все параметры регулярного выражения по умолчанию отключены.  
  
> [!NOTE]
>  Если параметры регулярного выражения, указанные в параметре `options` конструктора или вызове метода, конфликтуют со встроенными параметрами в шаблоне регулярного выражения, используются последние.  
  
 Следующие пять параметров регулярного выражения можно задавать одновременно в параметрах метода и в строке:  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
 Следующие пять параметров регулярного выражения можно задавать в параметре `options`, но не в строке:  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
## <a name="determining-the-options"></a>Определение параметров  
 Вы можете определить, какие параметры были предоставлены объекту <xref:System.Text.RegularExpressions.Regex> при создании его экземпляра, получив значение свойства <xref:System.Text.RegularExpressions.Regex.Options%2A?displayProperty=fullName> только для чтения. Это свойство особенно полезно для определения параметров, которые определены для скомпилированного регулярного выражения, созданные <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=fullName> метод.  
  
 Чтобы проверить наличие любого параметра, кроме <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>, выполните операцию AND со значением свойства <xref:System.Text.RegularExpressions.Regex.Options%2A?displayProperty=fullName> и значением <xref:System.Text.RegularExpressions.RegexOptions>, которое вас интересует. Затем проверьте, равен ли результат значению <xref:System.Text.RegularExpressions.RegexOptions>. Следующий пример проверяет, задан ли параметр <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/determine1.cs#19)]
 [!code-vb[Conceptual.Regex.Language.Options#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/determine1.vb#19)]  
  
 Для проверки <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>, определить, является ли значение <xref:System.Text.RegularExpressions.Regex.Options%2A?displayProperty=fullName> равно <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>, как показано в следующем примере.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/determine1.cs#20)]
 [!code-vb[Conceptual.Regex.Language.Options#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/determine1.vb#20)]  
  
 В следующих разделах перечислены параметры, поддерживаемые регулярными выражениями платформы .NET Framework.  
  
<a name="Default"></a>   
## <a name="default-options"></a>Параметры по умолчанию  
 Параметр <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> указывает, что ни один параметр не задан, а механизм регулярных выражений использует поведение по умолчанию. Это поведение характеризуется следующим образом.  
  
-   Шаблон интерпретируется как каноническое, а не регулярное выражение ECMAScript.  
  
-   Шаблон регулярного выражения сопоставляется во входной строке слева направо.  
  
-   При сравнениях учитывается регистр.  
  
-   Языковые элементы `^` и `$` сопоставляют начало и конец входной строки.  
  
-   Языковой элемент `.` соответствует каждому символу, кроме `\n`.  
  
-   Любой пробел в шаблоне регулярного выражения интерпретируется как пробел-литерал.  
  
-   При сравнении шаблона со входной строкой используются соглашения текущих региональных параметров.  
  
-   Захватываемые группы в шаблоне регулярного выражения являются неявными и явными.  
  
> [!NOTE]
>  Параметр <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> не имеет эквивалента среди встроенных параметров. Если параметры регулярного выражения применяются в строке, поведение по умолчанию восстанавливается для каждого параметра, за счет отключения того или иного параметра. Например, `(?i)` включает сравнение без учета регистра, а `(?-i)` восстанавливает учет регистра при сравнении.  
  
 Так как параметр <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> представляет поведение механизма регулярных выражений по умолчанию, он редко явно указывается в вызове метода. Вместо этого вызывает конструктор или статичный метод сопоставления шаблона без параметра `options`.  
  
 [К началу страницы](#Top)  
  
<a name="Case"></a>   
## <a name="case-insensitive-matching"></a>Сопоставление без учета регистра  
 <xref:System.Text.RegularExpressions.RegexOptions> параметр, или `i` встроенный параметр обеспечивает сопоставление без учета регистра. По умолчанию используются соглашения о регистре текущих региональных параметров.  
  
 Следующий пример определяет шаблон регулярного выражения, `\bthe\w*\b`, который сопоставляет все слова, начинающиеся со строки "the". Так как первый вызов <xref:System.Text.RegularExpressions.Regex.Match%2A> метод использует сравнение с учетом регистра по умолчанию, выходные данные показывают, что строка «» начинается предложения не соответствует указанному. Она выделяется, если метод <xref:System.Text.RegularExpressions.Regex.Match%2A> вызывается с параметром options, имеющим значение <xref:System.Text.RegularExpressions.RegexOptions>.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/case1.cs#1)]
 [!code-vb[Conceptual.Regex.Language.Options#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/case1.vb#1)]  
  
 Следующий пример изменяет шаблон регулярного выражения из предыдущего примера для использования встроенных параметров вместо параметра `options`, чтобы включить сравнение без учета регистра. Первый шаблон определяет параметр отключения учета регистра в конструкции группировки, которая применяется только к букве "t" в строке "the". Так как конструкция указана в начале шаблона, второй шаблон применяет параметр учета регистра ко всему регулярному выражению.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/case2.cs#2)]
 [!code-vb[Conceptual.Regex.Language.Options#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/case2.vb#2)]  
  
 [К началу страницы](#Top)  
  
<a name="Multiline"></a>   
## <a name="multiline-mode"></a>Многострочный режим  
 <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> параметр, или `m` встроенный параметр позволяет обработчику регулярных выражений обрабатывать входную строку, которая состоит из нескольких строк. Он изменяет интерпретацию языковых элементов `^` и `$`, чтобы они сопоставляли начало и конец строки текста, а не начало и строки входной строки.  
  
 По умолчанию `$` сопоставляет конец входной строки. При указании <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> параметр, она соответствует символу новой строки (`\n`) или в конце входной строки. Однако он не сопоставляет комбинацию символов возврата каретки и перевода строки. Для их успешного сопоставления используйте часть выражения `\r?$` вместо `$`.  
  
 Следующий пример извлекает имена и баллы игроков в Боулинг и добавляет их в <xref:System.Collections.Generic.SortedList%602> коллекции, отсортированных в порядке убывания.</TKey, TValue> Метод <xref:System.Text.RegularExpressions.Regex.Matches%2A> вызывается два раза. В первом вызове метода используется регулярное выражение `^(\w+)\s(\d+)$`, параметры не заданы. Как видно в результатах, совпадения не найдены, так как механизм регулярных выражений не может сопоставить входной шаблон с началом и концом входной строки. Во втором вызове метода регулярное выражение меняется на `^(\w+)\s(\d+)\r?$` и задаются параметры <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>. Как видно в результатах, имена и баллы успешно сопоставляются, а баллы отображаются по убыванию.  
  
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
  
 [К началу страницы](#Top)  
  
<a name="Singleline"></a>   
## <a name="single-line-mode"></a>Однострочный режим  
 <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> параметр, или `s` встроенный параметр заставляет механизм регулярных выражений обрабатывать входную строку так, будто она состоит из одной строки. Для этого поведение языкового элемента `.` меняется так, чтобы он сопоставлял каждый символ, а не каждый символ, кроме символа новой строки `\n` или \u000A.  
  
 В следующем примере показано как поведение `.` элемент языка меняется при использовании <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> параметр. Регулярное выражение `^.+` начинается с начала строки и соответствует любому знаку. По умолчанию соответствие заканчивается в конце первой строки; шаблон регулярного выражения соответствует символу возврата каретки, `\r` или \u000D, но не соответствует `\n`. Поскольку <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> параметр интерпретирует всю входную строку в виде одной строки, он сопоставляет каждый символ в строке ввода, включая `\n`.  
  
 [!code-csharp[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any2.cs#5)]
 [!code-vb[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any2.vb#5)]  
  
 Следующий пример аналогичен предыдущему, но он использует встроенный параметр `(?s)` для включения однострочного режима.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/singleline1.cs#5)]
 [!code-vb[Conceptual.Regex.Language.Options#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/singleline1.vb#5)]  
  
 [К началу страницы](#Top)  
  
<a name="Explicit"></a>   
## <a name="explicit-captures-only"></a>Только явные захваты  
 По умолчанию захватываемые группы определяются с помощью круглых скобок в шаблоне регулярного выражения. Именованные группы назначаются имя или номер с помощью `(?<` *имя*`>`*часть выражения* `)` параметром языка, тогда как неименованные группы доступны по индексу. В объекте <xref:System.Text.RegularExpressions.GroupCollection> неименованные группы идут перед именованными.  
  
 Конструкции группировки часто используются только для применения квантификаторов к нескольким языковым элементам, а захваченные подстроки не представляют интереса. Например, если следующее регулярное выражение,  
  
```  
\b\(?((\w+),?\s?)+[\.!?]\)?  
```  
  
 предназначено только для извлечения предложений, которые оканчиваются на точку, восклицательный или вопросительный знак из документа, и только полученное предложение (в объекте <xref:System.Text.RegularExpressions.Match>) представляет интерес, а отдельные слова в коллекции — нет.  
  
 Захватываемые группы, которые не используются в последствии, могут потреблять много ресурсов, так как механизм регулярных выражений должен заполнить объекты <xref:System.Text.RegularExpressions.GroupCollection> и <xref:System.Text.RegularExpressions.CaptureCollection> коллекции. В качестве альтернативы можно использовать <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> параметр или `n` встроенный параметр, чтобы указать, что единственные допустимые записи являются явно с именем или нумерованными группами, обозначенными `(?<` *имя* `>` *часть выражения* `)` построения.  
  
 Следующий пример отображает сведения о сопоставлениях, возвращаемых шаблоном регулярного выражения `\b\(?((\w+),?\s?)+[\.!?]\)?`, если метод <xref:System.Text.RegularExpressions.Regex.Match%2A> вызывается с параметром <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> или без него. Как видно в результатах выполнения первого вызова метода, механизм регулярных выражений полностью заполняет объекты коллекции <xref:System.Text.RegularExpressions.GroupCollection> и <xref:System.Text.RegularExpressions.CaptureCollection> данными о захваченных подстроках. Так как второй метод вызывается с `options` значение <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>, он не записывает сведения о группах.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/explicit1.cs#9)]
 [!code-vb[Conceptual.Regex.Language.Options#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/explicit1.vb#9)]  
  
 Шаблон регулярного выражения`\b\(?((?>\w+),?\s?)+[\.!?]\)?` определяется, как показано в следующей таблице.  
  
|Шаблон|Описание|  
|-------------|-----------------|  
|`\b`|Начало на границе слова.|  
|`\(?`|Сопоставляется ноль или один экземпляр открывающих круглых скобок ("(").|  
|`(?>\w+),?`|Сопоставляется один или несколько словообразующих символов, за которыми следует ноль или одна запятая. При сопоставлении словообразующих символов обратный поиск не применяется.|  
|`\s?`|Совпадение с нулем или одним символом пробела.|  
|`((\w+),?\s?)+`|Один или несколько раз выделяет комбинацию из одного или нескольких символов, нуля или одной запятой, нуля или одного пробела.|  
|`[\.!?]\)?`|Сопоставляются любые из трех знаков пунктуации, за которыми следует ноль или одна закрывающая круглая скобка (")").|  
  
 Вы также можете использовать встроенный элемент `(?n)`, чтобы отключить автоматическое выделение. Следующий пример изменяет предыдущий шаблон регулярного выражения для использования `(?n)` встроенного элемента вместо <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> параметр.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/explicit2.cs#10)]
 [!code-vb[Conceptual.Regex.Language.Options#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/explicit2.vb#10)]  
  
 Наконец, вы можете использовать встроенный элемент группы `(?n:)`, чтобы отключить автоматическое выделение для отдельных групп. Следующий пример изменяет предыдущий шаблон, чтобы отключить неименованные выделения во внешней группе, `((?>\w+),?\s?)`. Обратите внимание, что при этом подавляются неименованные выделения и во внутренней группе.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/explicit3.cs#11)]
 [!code-vb[Conceptual.Regex.Language.Options#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/explicit3.vb#11)]  
  
 [К началу страницы](#Top)  
  
<a name="Compiled"></a>   
## <a name="compiled-regular-expressions"></a>Скомпилированные регулярные выражения  
 По умолчанию регулярные выражения в .NET Framework интерпретируются. Когда создается экземпляр объекта <xref:System.Text.RegularExpressions.Regex> или вызывается статичный метод <xref:System.Text.RegularExpressions.Regex>, шаблон регулярного выражения преобразуется в набор настраиваемых кодов операций, а интерпретатор использует их для выполнения регулярного выражения. С этим связан компромисс: затраты на инициализацию механизма регулярных выражений уменьшаются за счет производительности во время выполнения.  
  
 Вместо интерпретируемых регулярных выражений можно использовать скомпилированные регулярные выражения, указав параметр <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>. В этом случае при передаче шаблона механизму регулярных выражений он разбивается на набор кодов операций и преобразуется в инструкции MSIL, которые можно передать напрямую среде CLR. Скомпилированные регулярные выражения повышают производительность во время выполнения, но за счет более длительной инициализации.  
  
> [!NOTE]
>  Скомпилировать регулярное выражение, необходимо передать <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> значение `options` параметр <xref:System.Text.RegularExpressions.Regex> класса конструктор или статический метод поиска совпадения с шаблоном. Этот параметр не может быть указан как встроенный.  
  
 Вы можете использовать скомпилированные регулярные выражения в вызовах статичных регулярных выражений и регулярных выражений экземпляров. В статических регулярных выражений <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> передается параметр `options` параметр метода поиска совпадения с шаблоном регулярного выражения. В регулярных выражениях экземпляра он передается в `options` параметр <xref:System.Text.RegularExpressions.Regex> конструктора класса. В обоих случаях это повышает производительность.  
  
 Однако такой рост производительности возможен только в следующих условиях:  
  
-   Объект <xref:System.Text.RegularExpressions.Regex>, представляющий определенное регулярное выражение, используется в нескольких вызовах методов сопоставления шаблона регулярного выражения.  
  
-   Объект <xref:System.Text.RegularExpressions.Regex> не может выходить за область применения, поэтому его можно использовать повторно.  
  
-   Статичное регулярное выражение используется в нескольких вызовах методов сопоставления шаблона регулярного выражения. (Рост производительности возможен, так как регулярные выражения, используемые в вызовах статичных методов, кэшируются механизмом регулярных выражений.)  
  
> [!NOTE]
>  <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> не связан с <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=fullName> метод, который создает специальную сборку, который содержит предопределенные скомпилированных регулярных выражений.  
  
 [К началу страницы](#Top)  
  
<a name="Whitespace"></a>   
## <a name="ignore-white-space"></a>Пропуск пробелов  
 По умолчанию пробел в шаблоне регулярного выражения учитывается. Он заставляет механизм регулярных выражений сопоставлять символ пробела во входной строке. По этой причине регулярное выражение «`\b\w+\s`«и»`\b\w+` » являются приблизительно равными регулярными выражениями. Кроме того, если в шаблоне регулярного выражения найден символ решетки (#), он интерпретируется как литерал, который необходимо сопоставить.  
  
 <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> параметр, или `x` встроенный параметр изменяет это поведение по умолчанию следующим образом:  
  
-   Неэкранированный пробел в шаблоне регулярного выражения игнорируется. Чтобы быть частью шаблона регулярного выражения, их необходимо экранировать пробельные символы (например, как `\s` или «`\` »).  
  
-   Символ решетки (#) интерпретируется как начало комментария, а не литерал. Весь текст в шаблоне регулярного выражения с символа # до конца строки интерпретируется как комментарий.  
  
 Однако в следующих случаях пробелы в регулярном выражении не игнорируются, даже если указан параметр <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.  
  
-   Пробел в классе символов всегда интерпретируется как литерал. Например, шаблон регулярного выражения `[ .,;:]` сопоставляет любой отдельный символ пробела, точки, запятой, точки с запятой и двоеточия.  
  
-   White space isn't allowed within a bracketed quantifier, such as `{`*n*`}`, `{`*n*`,}`, and `{`*n*`,`*m*`}`. Например, шаблон регулярного выражения `\d{1. 3}` не сопоставляет последовательности цифр из одной до трех цифр, так как он содержит пробел.  
  
-   Пробел не допускается в последовательности символов, предоставляющей языковой элемент. Например:  
  
    -   Элемент языка `(?:` *часть выражения* `)` представляет группу без сбора и `(?:` часть элемента не может содержать пробелы. Шаблон `(? :` *часть выражения* `)` вызывает <xref:System.ArgumentException> во время выполнения, поскольку обработчик регулярных выражений не может проанализировать шаблон и шаблон `( ?:` *часть выражения* `)` не соответствует *часть выражения*.  
  
    -   Элемент языка `\p{` *имя*`}`, представляющий категорию Юникода или именованный блок, не может содержать пробелы в `\p{` часть элемента. Если все-таки добавить пробел, элемент вызовет исключение <xref:System.ArgumentException> во время выполнения.  
  
 Включение этого параметра позволяет упростить регулярные выражения, синтаксический анализ и понимание которых зачастую вызывают затруднения. Это улучшает читаемость и позволяет документировать регулярное выражение.  
  
 В этом примере определяется следующий шаблон регулярного выражения:  
  
 `\b \(? ( (?>\w+) ,?\s? )+  [\.!?] \)? # Matches an entire sentence.`  
  
 Этот шаблон похож на тот, что был определен в разделе [Только явные захваты](#Explicit), но он использует параметр <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> для пропуска пробелов в шаблоне.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/whitespace1.cs#12)]
 [!code-vb[Conceptual.Regex.Language.Options#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/whitespace1.vb#12)]  
  
 Следующий пример использует встроенный параметр `(?x)` для пропуска пробелов.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/whitespace2.cs#13)]
 [!code-vb[Conceptual.Regex.Language.Options#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/whitespace2.vb#13)]  
  
 [К началу страницы](#Top)  
  
<a name="RightToLeft"></a>   
## <a name="right-to-left-mode"></a>Режим "справа налево"  
 По умолчанию механизм регулярных выражений выполняет поиска слева направо. Направление поиска можно изменить с помощью параметра <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>. Поиск автоматически будет начинаться с последнего символа строки. Для методов сопоставления шаблона с параметром начальной позиции, таких как <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.Int32%29?displayProperty=fullName>, начальная позиция — это индекс самого правого символа, с которого начинается поиск.  
  
> [!NOTE]
>  Режим справа налево шаблон доступен только путем предоставления <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> значение `options` параметр <xref:System.Text.RegularExpressions.Regex> класса конструктор или статический метод поиска совпадения с шаблоном. Этот параметр не может быть указан как встроенный.  
  
 Параметр <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> меняет только направление поиска, а не интерпретирует шаблон регулярного выражения справа налево. Например, регулярное выражение `\bb\w+\s` сопоставляет слова, которые начинаются с буквы "b" и за которыми следует пробел. В следующем примере входная строка состоит из трех слов, которые содержат одну или несколько букв "b". Первое слово начинается с "b", второе заканчивается на "b", а в третьем буква "b" находится в середине слова. Как видно из результата примера, только первое слово соответствует шаблону регулярного выражения.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/righttoleft1.cs#17)]
 [!code-vb[Conceptual.Regex.Language.Options#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/righttoleft1.vb#17)]  
  
 Также Обратите внимание, что утверждение просмотра вперед ( `(?=` *часть выражения* `)` элемент языка) и утверждение просмотра назад ( `(?<=` *часть выражения* `)` элемент языка) не меняют направление. Утверждения просмотра вперед выполняют поиск вправо, а утверждения просмотра назад — влево. Например, регулярное выражение `(?<=\d{1,2}\s)\w+,?\s\d{4}` использует утверждения просмотра назад для проверки наличия даты, перед которой идет название месяца. Затем регулярное выражение сопоставляет месяц и год. Сведения об утверждениях просмотра вперед и назад см. в разделе [конструкции группировки](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
 [!code-csharp[Conceptual.Regex.Language.Options#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/righttoleft2.cs#18)]
 [!code-vb[Conceptual.Regex.Language.Options#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/righttoleft2.vb#18)]  
  
 Шаблон регулярного выражения определяется, как показано в следующей таблице.  
  
|Шаблон|Описание|  
|-------------|-----------------|  
|`(?<=\d{1,2}\s)`|Слева от начала сопоставления должна идти одна или две десятичных цифры, за которыми следует пробел.|  
|`\w+`|Совпадение с одним или несколькими символами слова.|  
|`,?`|Выделяется ноль или один символ запятой.|  
|`\s`|Соответствует пробелу.|  
|`\d{4}`|Выделяются&4; десятичные цифры.|  
  
 [К началу страницы](#Top)  
  
<a name="ECMAScript"></a>   
## <a name="ecmascript-matching-behavior"></a>Поведение сопоставления ECMAScript  
 По умолчанию механизм регулярных выражений использует каноническое поведение при сопоставлении шаблона регулярного выражения с входным текстом. Но вы можете использовать поведение сопоставления ECMAScript, указав параметр <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.  
  
> [!NOTE]
>  Поведение, совместимое с ECMAScript доступна только путем предоставления <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> значение `options` параметр <xref:System.Text.RegularExpressions.Regex> класса конструктор или статический метод поиска совпадения с шаблоном. Этот параметр не может быть указан как встроенный.  
  
 Параметр <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> можно использоваться только вместе с параметрами <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> и <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>. При использовании других параметров в регулярном выражении возникает исключение <xref:System.ArgumentOutOfRangeException>.  
  
 Поведение регулярных выражений ECMAScript и канонических регулярных выражений отличается в трех аспектах: синтаксис класса символов, ссылающиеся на себя захватываемые группы и интерпретация восьмеричных значений и обратных ссылок.  
  
-   Синтаксис класса символов. Так как канонические регулярные выражения поддерживают Юникод, а ECMAScript — нет, синтаксис классов символов в ECMAScript более ограничен, а некоторые языковые элементы класса символов обладают другим значением. Например, ECMAScript не поддерживает такие языковые элементы, как категория Юникода или элементы блока `\p` и `\P`. Аналогичным образом, элемент `\w`, который сопоставляет словообразующее слово, эквивалентен классу символов `[a-zA-Z_0-9]` при использовании ECMAScript и `[\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]` при использовании канонического поведения. Дополнительные сведения см. в разделе [классы символов](../../../docs/standard/base-types/character-classes-in-regular-expressions.md).  
  
     Следующий пример иллюстрирует разницу между каноническим сопоставлением шаблона и ECMAScript. В нем определяется регулярное выражение, `\b(\w+\s*)+`, сопоставляющее слова, за которыми следуют пробелы. Входные данные состоят из двух строк, одна из которых использует латиницу, а другая — кириллицу. Как видно из результата, при вызове метода <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=fullName>, использующего сопоставление ECMAScript, не удается сопоставить слова на кириллице, а при вызове метода, использующего каноническое сопоставление — удается.  
  
     [!code-csharp[Conceptual.Regex.Language.Options#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/ecmascript1.cs#16)]
     [!code-vb[Conceptual.Regex.Language.Options#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/ecmascript1.vb#16)]  
  
-   Ссылающиеся на себя захватываемые группы Класс захвата регулярного выражения с обратной ссылкой на себя необходимо обновлять после каждой итерации выделения. Как показано в следующем примере, это позволяет регулярному выражению `((a+)(\1) ?)+` сопоставить входную строку " aa aaaa aaaaaa " при использовании ECMAScript, но не канонического сопоставления.  
  
     [!code-csharp[Conceptual.Regex.Language.Options#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/ecmascript2.cs#21)]
     [!code-vb[Conceptual.Regex.Language.Options#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/ecmascript2.vb#21)]  
  
     Определение регулярного выражения показано в следующей таблице.  
  
    |Шаблон|Описание|  
    |-------------|-----------------|  
    |(a+)|Буква "a" выделяется один или несколько раз. Это вторая группа записи.|  
    |(\1)|Сопоставление подстроки, выделенной первой захватываемой группой. Это третья группа записи.|  
    |?|Выделяется ноль или один символ пробела.|  
    |((a+)(\1) ?)+|Один или несколько раз выделяется шаблон из одной или нескольких букв "a", за которыми следует строка, сопоставляющая первую захватываемую группу, за которой следует ноль или один символ пробела. Это первая группа записи.|  
  
-   Разрешение неоднозначности между восьмеричными Escape-символами и обратными ссылками. В следующей таблице представлены общие сведения об отличиях интерпретации восьмеричных чисел и обратных ссылок при использовании канонических регулярных выражений и ECMAScript.  
  
    |Регулярное выражение|Каноническое поведение|Поведение ECMAScript|  
    |------------------------|------------------------|-------------------------|  
    |`\0` с последующими 0-2 восьмеричными цифрами|Интерпретируется как восьмеричное число. Например, `\044` всегда интерпретируется как восьмеричное значение и означает "$".|Такое же поведение.|  
    |`\` с последующей цифрой от 1 до 9, за которой нет дополнительных десятичных цифр.|Интерпретируется как обратная ссылка. Например, `\9` всегда означает обратную ссылку на 9, даже если девятая захватываемая группа не существует. Если группа записи не существует, анализатор регулярных выражений создает исключение <xref:System.ArgumentException>.|Если захватываемая группа из одной десятичной цифры существует, значение интерпретируется как обратная ссылка на эту цифру. В противном случае оно интерпретируется как литерал.|  
    |`\` с последующей цифрой от 1 до 9, за которой следуют дополнительные десятичные цифры.|Цифры интерпретируются как десятичное значение. Если эта захватываемая группа существует, выражение интерпретируется как обратная ссылка.<br /><br /> В противном случае интерпретируются первые восьмеричные цифры до восьмеричного числа 377, т. е. учитываются только младшие 8 разрядов значения. Оставшиеся цифры интерпретируются как литералы. Например, выражение `\3000`, если захватываемая группа 300 существует, интерпретируется как обратная ссылка на 300. В противном случае оно интерпретируется как восьмеричное число 300, за которым следует 0.|Выражение интерпретируется как обратная ссылка, для этого как можно больше цифр преобразуется в десятичное значение, которые могут указывать на выделение. Если цифры не могут быть преобразованы, выражение интерпретируется как восьмеричное число с использованием первых восьмеричных разрядов до восьмеричного числа 377. Оставшиеся восьмеричные цифры интерпретируются как литералы.|  
  
 [К началу страницы](#Top)  
  
<a name="Invariant"></a>   
## <a name="comparison-using-the-invariant-culture"></a>Сравнение с использованием инвариантных региональных параметров  
 По умолчанию, когда механизм регулярных выражений выполняет сравнения без учета регистра, соглашения о регистре текущих региональных параметров используются для определения эквивалентных прописных и строчных символов.  
  
 Однако это недопустимо для некоторых типов сравнения, например при сравнении введенных пользователем данных с именами системных ресурсов, таких как пароли, файлы и URL-адреса.  В следующем примере показана подобная ситуация. Код предназначен для блокировки доступа к любому ресурсу, URL-адрес, используемое **FILE://**. Регулярное выражение пытается выполнить сопоставление без учета регистра, используя регулярное выражение `$FILE://`. Но текущие региональные параметры заданы как tr-TR (Турецкий-Турция), и "I" — не является прописным эквивалентом "i". В результате вызова <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> возвращает метод `false`, и доступ к файлу.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/culture1.cs#14)]
 [!code-vb[Conceptual.Regex.Language.Options#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/culture1.vb#14)]  
  
> [!NOTE]
>  Подробнее о сравнении строк с учетом регистра и использовании инвариантных региональных параметров см. в разделе [Рекомендации по использованию строк в .NET](../../../docs/standard/base-types/best-practices-strings.md).  
  
 Вместо использования сравнений без учета регистра текущих региональных параметров можно указать параметр <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>, чтобы игнорировать региональные отличия в языке и использовать соглашения инвариантных региональных параметров.  
  
> [!NOTE]
>  Сравнение с использованием инвариантного языка и региональных параметров доступна только путем предоставления <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> значение `options` параметр <xref:System.Text.RegularExpressions.Regex> класса конструктор или статический метод поиска совпадения с шаблоном. Этот параметр не может быть указан как встроенный.  
  
 Следующий пример идентичен предыдущему, но в нем статичный метод <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=fullName> вызывается с параметрами, содержащими <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>. Даже если в качестве региональных параметров выбрано "Турецкий (Турция)", механизм регулярных выражений сможет успешно сопоставить строки "FILE" и "file" и заблокировать доступ к файлу.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/culture1.cs#15)]
 [!code-vb[Conceptual.Regex.Language.Options#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/culture1.vb#15)]  
  
## <a name="see-also"></a>См. также  
 [Элементы языка регулярных выражений — краткий справочник](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)