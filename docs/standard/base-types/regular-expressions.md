---
title: Регулярные выражения в .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pattern-matching with regular expressions, about pattern-matching
- substrings
- searching with regular expressions, about regular expressions
- pattern-matching with regular expressions
- searching with regular expressions
- parsing text with regular expressions
- regular expressions [.NET Framework], about regular expressions
- regular expressions [.NET Framework]
- .NET Framework regular expressions, about
- characters [.NET Framework], regular expressions
- parsing text with regular expressions, overview
- .NET Framework regular expressions
- strings [.NET Framework], regular expressions
ms.assetid: 521b3f6d-f869-42e1-93e5-158c54a6895d
ms.openlocfilehash: ac034ff37b0b39f41d6f58381286706f9a9ac602
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121706"
---
# <a name="net-regular-expressions"></a>Регулярные выражения в .NET
Регулярные выражения предоставляют мощный, гибкий и эффективный способ обработки текста. Комплексная нотация сопоставления шаблонов регулярных выражений позволяет быстро анализировать большие объемы текста для поиска определенных шаблонов символов, проверять текст на соответствие предопределенному шаблону (например, адресу электронной почты), извлекать, изменять, заменять и удалять текстовые подстроки, а также добавлять извлеченные строки в коллекцию для создания отчета. Для многих приложений, которые работают со строками или анализируют большие блоки текста, регулярные выражения — незаменимый инструмент.  
  
## <a name="how-regular-expressions-work"></a>Принцип работы регулярных выражений  
 Главный компонент обработки текста с помощью регулярных выражений — это механизм регулярных выражений, представленный в .NET объектом <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>. Как минимум, для обработки текста с использованием в регулярных выражений механизму регулярных выражений необходимо предоставить два следующих элемента:  
  
- Шаблон регулярного выражения для определения текста.  
  
     В .NET шаблоны регулярных выражений определяются специальным синтаксисом или языком, который совместим с регулярными выражениями Perl 5 и добавляет дополнительные возможности, например сопоставление справа налево. Дополнительные сведения см. в разделе [Элементы языка регулярных выражений. Краткий справочник](regular-expression-language-quick-reference.md).  
  
- Текст, который будет проанализирован на соответствие шаблону регулярного выражения.  
  
 Методы класса <xref:System.Text.RegularExpressions.Regex> позволяют выполнять следующие операции:  
  
- Определить, входит ли шаблон регулярного выражения во входной текст, с помощью метода <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType>. Пример использования метода <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> для проверки текста см. в разделе [Руководство. Проверка строк на соответствие формату электронной почты](how-to-verify-that-strings-are-in-valid-email-format.md).  
  
- Получить один или все экземпляры текста, соответствующего шаблону регулярного выражения с помощью метода <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType> или <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType>. Первый метод возвращает объект <xref:System.Text.RegularExpressions.Match?displayProperty=nameWithType>, который предоставляет сведения о соответствующем тексте. Второй метод возвращает объект <xref:System.Text.RegularExpressions.MatchCollection>, содержащий один объект <xref:System.Text.RegularExpressions.Match?displayProperty=nameWithType> для каждого соответствия, обнаруженного в обработанном тексте.  
  
- Заменить текст, соответствующий шаблону регулярного выражения, с помощью метода <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType>. Примеры использования метода <xref:System.Text.RegularExpressions.Regex.Replace%2A> для изменения форматов даты и удаления недопустимых символов из строки см. в разделах [Руководство. Исключение недопустимых символов из строки](how-to-strip-invalid-characters-from-a-string.md) и [Руководство. Изменение форматов даты](regular-expression-example-changing-date-formats.md).  
  
 Обзор объектной модели регулярных выражений см. в разделе [Объектная модель регулярных выражений](the-regular-expression-object-model.md).  
  
 Дополнительные сведения о языке регулярных выражений см. в [кратком справочнике по элементам языка регулярных выражений](regular-expression-language-quick-reference.md) или в одной из следующих брошюр, который вы можете скачать и распечатать:  
  
 [Краткий справочник в формате Word (DOCX)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.docx);  
 [Краткий справочник в формате PDF (PDF)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.pdf).  
  
## <a name="regular-expression-examples"></a>Примеры регулярных выражений  
 Класс <xref:System.String> содержит ряд методов для поиска и замены строк, которые можно использовать для поиска строковых литералов в длинных строках. Регулярные выражения максимально полезны, если требуется найти одну из нескольких подстрок в длинной строке или определить шаблоны в строке, как показано в следующих примерах.  
  
### <a name="example-1-replacing-substrings"></a>Пример 1: Замена подстрок  
 Предположим, что список рассылки содержит имена, в которые иногда входит обращение (Mr., Mrs., Miss или Ms.) в дополнение к имени и фамилии. Если вы не хотите включать обращения при создании этикеток для конвертов из списка, с помощью регулярного выражения их можно удалить, как показано в следующем примере.  
  
 [!code-csharp[Conceptual.Regex#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex/cs/example1.cs#2)]
 [!code-vb[Conceptual.Regex#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex/vb/example1.vb#2)]  
  
 Шаблон регулярного выражения `(Mr\.? |Mrs\.? |Miss |Ms\.? )` сопоставляет все вхождения строк "Mr", "Mr.", "Mrs", "Mrs.", "Miss", "Ms" или "Ms.". После вызова метода <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> сопоставленная строка заменяется на <xref:System.String.Empty?displayProperty=nameWithType>; другими словами, она удаляется из исходной строки.  
  
### <a name="example-2-identifying-duplicated-words"></a>Пример 2: Поиск повторяющихся слов  
 Случайный повтор слов — это распространенная ошибка при написании текстов. Регулярное выражение можно использовать для определения повторяющихся слов, как показано в следующем примере.  
  
 [!code-csharp[Conceptual.Regex#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex/cs/example2.cs#3)]
 [!code-vb[Conceptual.Regex#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex/vb/example2.vb#3)]  
  
 Шаблон регулярного выражения `\b(\w+?)\s\1\b` интерпретируется следующим образом:  
  
|||  
|-|-|  
|`\b`|Начало на границе слова.|  
|(\w+?)|Соответствует одному или нескольким символам слова (как можно меньшему количеству). Вместе они формируют группу, к которой можно обращаться как к `\1`.|  
|`\s`|Соответствует пробелу.|  
|`\1`|Сопоставление подстроки, равной группе с именем `\1`.|  
|`\b`|Соответствует границе слова.|  
  
 Метод <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> вызывается с параметрами регулярного выражения <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType>. Поэтому операция сопоставления учитывает регистр, а пример указывает, что подстрока "This this" является повтором.  
  
 Обратите внимание, что входная строка содержит подстроку "this? This". Но из-за знака пунктуации она не считается повторением.  
  
### <a name="example-3-dynamically-building-a-culture-sensitive-regular-expression"></a>Пример 3. Динамическое создание регулярного выражения с учетом языка и региональных параметров  
 Следующий пример демонстрирует преимущества использования регулярных выражений с гибкими возможностями глобализации .NET. В примере объект <xref:System.Globalization.NumberFormatInfo> применяется для определения формата денежных значений в текущих региональных стандартах системы. Затем эти данные используются для динамического создания регулярного выражения, которое извлекает денежные значения из текста. Для каждого совпадения извлекается подгруппа, содержащая только числовые строки, которая преобразуется в значение <xref:System.Decimal>, после чего рассчитывается промежуточный итог.  
  
 [!code-csharp[Conceptual.Regex#1](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex/cs/example.cs#1)]
 [!code-vb[Conceptual.Regex#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex/vb/example.vb#1)]  
  
 На компьютере с региональными параметрами "English - United States (en-US)" пример динамически создает регулярное выражение `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`. Шаблон регулярного выражения интерпретируется следующим образом:  
  
|||  
|-|-|  
|`\$`|Выполняется поиск одного вхождения символа доллара (`$`) во входной строке. Строка шаблона регулярного выражения содержит обратную косую черту, что говорит о том, что символ доллара интерпретируется буквально, а не как привязка регулярного выражения. (Отдельный символ `$` указывает, что механизм регулярных выражений должен начинать сопоставление с конца строки.) Чтобы правильно обработать текущий символ валюты, в примере вызывается метод <xref:System.Text.RegularExpressions.Regex.Escape%2A?displayProperty=nameWithType>, который экранирует символ.|  
|`\s*`|Поиск нуля или нескольких вхождений пробела.|  
|`[-+]?`|Поиск нуля или нескольких вхождений знака плюс или минус.|  
|`([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`|Внешние круглые скобки вокруг этого выражения делают его захватываемой группой или частью выражения. Если найдено соответствие, сведения об этой части строки можно получить из второго объекта <xref:System.Text.RegularExpressions.Group> в объекте <xref:System.Text.RegularExpressions.GroupCollection>, который возвращается свойством <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>. (Первый элемент в коллекции представляет все сопоставление.)|  
|`[0-9]{0,3}`|Поиск 0-3 вхождений десятичных цифр (0-9).|  
|`(,[0-9]{3})*`|Поиск нуля или нескольких вхождений разделителя группы, за которыми следуют три десятичные цифры.|  
|`\.`|Поиск одного вхождения десятичного разделителя.|  
|`[0-9]+`|Поиск одной или нескольких десятичных цифр.|  
|`(\.[0-9]+)?`|Поиск нуля или одного вхождения десятичного разделителя, за которым следует по крайней мере одна десятичная цифра.|  
  
 Если каждый из этих подшаблонов найден во входной строке, сопоставление является успешным, а объект <xref:System.Text.RegularExpressions.Match> с информацией о сопоставлении добавляется в объект <xref:System.Text.RegularExpressions.MatchCollection>.  
  
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Элементы языка регулярных выражений — краткий справочник](regular-expression-language-quick-reference.md)|Сведения о наборе символов, операторов и конструкций, которые можно использовать для определения регулярных выражений.|  
|[Объектная модель регулярных выражений](the-regular-expression-object-model.md)|Сведения об использовании классов регулярных выражений и примеры кода.|  
|[Подробные сведения о поведении регулярных выражений](details-of-regular-expression-behavior.md)|Сведения о возможностях и поведении регулярных выражений платформы .NET.|  
|[Примеры регулярных выражений](regular-expression-examples.md)|Примеры кода, демонстрирующие типичное применение регулярных выражений.|  
  
## <a name="reference"></a>Справочник  
 <xref:System.Text.RegularExpressions?displayProperty=nameWithType>  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>  
 [Краткий справочник по регулярным выражениям (скачать в формате Word)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.docx)  
 [Регулярные выражения — краткий справочник (загрузить в формате PDF)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.pdf)
