---
title: "Квантификаторы в регулярных выражениях"
description: "Квантификаторы в регулярных выражениях"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 8e5124c4-20b5-4c57-ab68-301d1d7311c4
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: cd47cc351fb926bcf444bdcbd12f3cd61d9fb327
ms.lasthandoff: 03/02/2017

---

# <a name="quantifiers-in-regular-expressions"></a>Квантификаторы в регулярных выражениях

Квантификаторы определяют количество экземпляров символа, группы или класса символов, которое должно присутствовать во входных данных, чтобы было зафиксировано совпадение. В приведенной ниже таблице перечислены квантификаторы, поддерживаемые платформой .NET.

Жадный квантификатор | Ленивый квантификатор | Описание
----------------- | --------------- | ----------- 
**\*** | **\*?** | Совпадение ноль или несколько раз.
**+** | **+?** | Совпадение один или несколько раз.
**?** | **??** | Совпадение ноль или один раз.
**{**_n_**}** | **{**_n_**}?** | Совпадение ровно n раз.
**{**_n_**,}** | **{**_n_**,}?** | Совпадение как минимум n раз.
**{**_n_**,**_m_**}** | **{**_n_**,**_m_**}?** | Совпадение от n до m раз.
 
Количества *n* и *m* являются целочисленными константами. Обычно квантификаторы "жадные" — они заставляют обработчик регулярных выражений выделить максимально возможное число вхождений определенного шаблона. Добавление символа `?` в квантификатор делает его отложенным (или ленивым). Это приводит к тому, что обработчик регулярных выражений пытается сопоставить так мало вхождений, как это возможно. Полное описание различий между "жадными" и "ленивыми" квантификаторами см. в разделе [Жадные и ленивые квантификаторы](#greedy-and-lazy-quantifiers) далее в этой статье.

> [!IMPORTANT]
> Вложенные квантификаторы (например, шаблон регулярного выражения `(a*)*`) могут увеличить количество сравнений, которые должен выполнять обработчик регулярных выражений, как экспоненциальная функция количества символов во входной строке. Дополнительные сведения об этом поведении и способах его обхода см. в статье [Поиск с возвратом в регулярных выражениях](backtracking.md).

## <a name="regular-expression-quantifiers"></a>Квантификаторы регулярных выражений

В следующих разделах перечислены квантификаторы, поддерживаемые регулярными выражениями платформы .NET. 

> [!NOTE]
> Если в шаблоне регулярных выражений встречаются символы \*, +,?, {, и }, обработчик регулярных выражений интерпретирует их как квантификаторы или как часть конструкций квантификаторов, только если они не включаются в [класс символов](classes.md). Чтобы они интерпретировались как символы-литералы за пределами класса символов, необходимо ставить перед ними escape-символ — обратную косую черту. Например, строка `\*` в шаблоне регулярного выражения интерпретируется как литеральный символ звездочки ("*").

### <a name="match-zero-or-more-times-"></a>Совпадение нуль или более раз: \*

Квалификатор \* выделяет предыдущий элемент, повторяющийся ноль или более раз. Это свойство эквивалентно квантификатору **{0},**. **\*** — "жадный" квантификатор, "ленивым" эквивалентом которого является квантификатор **\*?**.

В следующем примере показано, как использовать это регулярное выражение. Пять из девяти чисел в исходной строке соответствуют заданному шаблону, четыре числа (`95`, `929`, `9129` и `9919`) — нет.

```csharp
string pattern = @"\b91*9*\b";   
string input = "99 95 919 929 9119 9219 999 9919 91119";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

// The example displays the following output:   
//       '99' found at position 0.
//       '919' found at position 6.
//       '9119' found at position 14.
//       '999' found at position 24.
//       '91119' found at position 33.
```

```vb
Dim pattern As String = "\b91*9*\b"   
Dim input As String = "99 95 919 929 9119 9219 999 9919 91119"
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next     
' The example displays the following output:   
'       '99' found at position 0.
'       '919' found at position 6.
'       '9119' found at position 14.
'       '999' found at position 24.
'       '91119' found at position 33.
```

Шаблон регулярного выражения определяется, как показано в следующей таблице.

Шаблон | Описание
------- | ----------- 
`\b` | Начало на границе слова.
`91*` | Совпадение с символом "9", за которыми следует ноль или более символов "1".
`9*` | Выделить ноль или больше символов "9".
`\b` | Конец на границе слова.
 
### <a name="match-one-or-more-times-"></a>Совпадение один или более раз: +

Квантификатор **+** сопоставляет предыдущий элемент один или более раз. Он аналогичен параметру **{1,}**. **+** — жадный квантификатор, ленивым эквивалентом которого является квантификатор **+?**.

Например, с помощью регулярного выражения `\ban+\w*?\b` осуществляется сопоставление целых слов, начинающихся с буквы `a`, за которой следует одна или несколько букв `n`. В следующем примере показано, как использовать это регулярное выражение. Регулярное выражение соответствует словам `an`, `annual`, `announcement` и `antique` и не соответствует словам `autumn` и `all`.

```csharp
string pattern = @"\ban+\w*?\b";

string input = "Autumn is a great time for an annual announcement to all antique collectors.";
foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

// The example displays the following output:   
//       'an' found at position 27.
//       'annual' found at position 30.
//       'announcement' found at position 37.
//       'antique' found at position 57.      
```

```vb
Dim pattern As String = "\ban+\w*?\b"

Dim input As String = "Autumn is a great time for an annual announcement to all antique collectors."
For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next   
' The example displays the following output:   
'       'an' found at position 27.
'       'annual' found at position 30.
'       'announcement' found at position 37.
'       'antique' found at position 57. 
```

Шаблон регулярного выражения определяется, как показано в следующей таблице.

Шаблон | Описание
------- | ----------- 
`\b` | Начало на границе слова.
`an+` | Совпадение с "a"с последующим одним или несколькими символами "n". 
`\w*?` | Совпадение со словообразующим символом ноль или несколько раз (по возможности минимальное количество раз).
`\b` | Конец на границе слова.
 
### <a name="match-zero-or-one-time-"></a>Совпадение нуль или один раз: ?

Квантификатор **?** сопоставляет предыдущий элемент ноль или один раз. Он аналогичен параметру **{0,1}**. **?** — жадный квантификатор, ленивым эквивалентом которого является квантификатор **??**.

Например, с помощью регулярного выражения `\ban?\b` осуществляется сопоставление целых слов, начинающихся с буквы `a`, за которой следует одна буква `n` или не следует ни одной такой буквы. Иными словами, предпринимается попытка найти слова `a` и `an`. В следующем примере показано, как использовать это регулярное выражение.

```csharp
string pattern = @"\ban?\b";
string input = "An amiable animal with a large snount and an animated nose.";
foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

// The example displays the following output:   
//        'An' found at position 0.
//        'a' found at position 23.
//        'an' found at position 42.
```

```vb
Dim pattern As String = "\ban?\b"
Dim input As String = "An amiable animal with a large snount and an animated nose."
For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next  
' The example displays the following output:   
'       'An' found at position 0.
'       'a' found at position 23.
'       'an' found at position 42.
```

Шаблон регулярного выражения определяется, как показано в следующей таблице.

Шаблон | Описание
------- | ----------- 
`\b` | Начало на границе слова.
`an?` | Совпадение с "a"с последующими символами "n" (при их наличии). 
`\b` | Конец на границе слова.
 
### <a name="match-exactly-n-times-n"></a>Совпадение ровно n раз: {n}

Квантификатор **{**_n_**}** сопоставляет предыдущий элемент ровно *n* раз, где *n* — любое целое число. **{**_n_**}** — жадный квантификатор, ленивым эквивалентом которого является квантификатор **{**_n_**}?**.

Например, с помощью регулярного выражения `\b\d+\,\d{3}\b` осуществляется поиск границы слова, за которой следует один или более десятичных знаков, еще три десятичных знака и граница слова. В следующем примере показано, как использовать это регулярное выражение. 

```csharp
string pattern = @"\b\d+\,\d{3}\b";
string input = "Sales totaled 103,524 million in January, " + 
                      "106,971 million in February, but only " + 
                      "943 million in March.";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:   
//        '103,524' found at position 14.
//        '106,971' found at position 45.
```

```vb
Dim pattern As String = "\b\d+\,\d{3}\b"
Dim input As String = "Sales totaled 103,524 million in January, " + _
                      "106,971 million in February, but only " + _
                      "943 million in March."
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next     
' The example displays the following output:   
'       '103,524' found at position 14.
'       '106,971' found at position 45.
```

Шаблон регулярного выражения определяется, как показано в следующей таблице.

Шаблон | Описание
------- | ----------- 
`\b` | Начало на границе слова.
`\d+` | Совпадение с одной или несколькими десятичными цифрами. 
`\,` | Совпадение с символом запятой.
`\d{3}` | Совпадение с тремя десятичными цифрами.
`\b` | Конец на границе слова.
 
### <a name="match-at-least-n-times-n"></a>Совпадение как минимум n раз: {n,}

Квантификатор **{**_n_**,}** сопоставляет предыдущий элемент как минимум *n* раз, где *n* — любое целое число. **{**_n_**,}** — жадный квантификатор, ленивым эквивалентом которого является квантификатор **{**_n_**}?**.

Например, с помощью регулярного выражения `\b\d{2,}\b\D+` осуществляется поиск границы слова, за которой следует по крайней мере два десятичных знака, граница слова и знак, не являющийся числом. В следующем примере показано, как использовать это регулярное выражение. Регулярное выражение не соответствует фразе "7 days", так как она содержит всего один десятичный знак, но соответствует фразам "10 weeks and 300 years".

```csharp
string pattern = @"\b\d{2,}\b\D+";   
string input = "7 days, 10 weeks, 300 years";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        '10 weeks, ' found at position 8.
// 
``` 

```vb
Dim pattern As String = "\b\d{2,}\b\D+"  
 Dim input As String = "7 days, 10 weeks, 300 years"
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next 
' The example displays the following output:
'       '10 weeks, ' found at position 8.
'       '300 years' found at position 18.
      '300 years' found at position 18.
```

Шаблон регулярного выражения определяется, как показано в следующей таблице.

Шаблон | Описание
------- | ----------- 
`\b` | Начало на границе слова.
`\d{2,}` | Совпадение как минимум с двумя десятичными цифрами. 
`\b` | Соответствует границе слова.
`\D+` | Совпадение как минимум с одной цифрой, не являющейся десятичной.
 
### <a name="match-between-n-and-m-times-nm"></a>Совпадение от n до m раз: {n,m}

Квантификатор **{**_n_**,**_m_**}** сопоставляет предыдущий элемент минимум *n* раз, но не больше *m* раз, где *n* и *m* — целые числа. **{**_n_**,**_m_**}** — жадный квантификатор, ленивым эквивалентом которого является квантификатор **{**_n_**,**_m_**}?**.

В следующем примере с помощью регулярного выражения `(00\s){2,4}` осуществляется поиск от двух до четырех вхождений двух нулей, за которыми следует пробел. Обратите внимание, что в конце входной строки имеются пять вхождений этого фрагмента при максимуме в четыре вхождения. Однако только начало этой части строки (до пробела и пятой пары нулей) соответствует шаблону регулярного выражения.

```csharp
string pattern = @"(00\s){2,4}";
string input = "0x00 FF 00 00 18 17 FF 00 00 00 21 00 00 00 00 00";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        '00 00 ' found at position 8.
//        '00 00 00 ' found at position 23.
//        '00 00 00 00 ' found at position 35.
```

```vb
Dim pattern As String = "(00\s){2,4}"
Dim input As String = "0x00 FF 00 00 18 17 FF 00 00 00 21 00 00 00 00 00"
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next 
' The example displays the following output:
'       '00 00 ' found at position 8.
'       '00 00 00 ' found at position 23.
'       '00 00 00 00 ' found at position 35.
```

### <a name="match-zero-or-more-times-lazy-match-"></a>Совпадение нуль или более раз ("ленивое" совпадение): \*?

Квантификатор **\*?** совпадает с предыдущим элементом ноль или более раз, но как можно меньшее число раз. Это ленивый квантификатор, являющийся аналогом жадного квантификатора **\***.

В следующем примере регулярное выражение `\b\w*?oo\w*?\b` сопоставляет все слова, которые содержат строку `oo`. 

```csharp
 string pattern = @"\b\w*?oo\w*?\b";
 string input = "woof root root rob oof woo woe";
 foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
    Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

 //  The example displays the following output:
//        'woof' found at position 0.
//        'root' found at position 5.
//        'root' found at position 10.
//        'oof' found at position 19.
//        'woo' found at position 23.
```

```vb
Dim pattern As String = "\b\w*?oo\w*?\b"
 Dim input As String = "woof root root rob oof woo woe"
 For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
    Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
 Next 
 ' The example displays the following output:
'       'woof' found at position 0.
'       'root' found at position 5.
'       'root' found at position 10.
'       'oof' found at position 19.
'       'woo' found at position 23.
```

Шаблон регулярного выражения определяется, как показано в следующей таблице.

Шаблон | Описание
------- | ----------- 
`\b` | Начало на границе слова.
`\w*?` | Совпадение с нулем или минимально возможным числом словообразующих символов. 
`oo` | Совпадение со строкой "oo".
`\w*?` | Совпадение с нулем или минимально возможным числом словообразующих символов.
`\b` | Конец на границе слова.
 
### <a name="match-one-or-more-times-lazy-match-"></a>Совпадение один или более раз ("ленивое" совпадение): +?

Квантификатор **+?** совпадает с предыдущим элементом один или более раз, но как можно меньшее число раз. Это ленивый квантификатор, являющийся аналогом жадного квантификатора **+**.

Например, регулярное выражение `\b\w+?\b` соответствует одному или нескольким символам, разделенным границами слов. В следующем примере показано, как использовать это регулярное выражение.

```csharp
string pattern = @"\b\w+?\b";
string input = "Aa Bb Cc Dd Ee Ff";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        'Aa' found at position 0.
//        'Bb' found at position 3.
//        'Cc' found at position 6.
//        'Dd' found at position 9.
//        'Ee' found at position 12.
//        'Ff' found at position 15.
```

```vb
Dim pattern As String = "\b\w+?\b"
 Dim input As String = "Aa Bb Cc Dd Ee Ff"
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next 
' The example displays the following output:
'       'Aa' found at position 0.
'       'Bb' found at position 3.
'       'Cc' found at position 6.
'       'Dd' found at position 9.
'       'Ee' found at position 12.
'       'Ff' found at position 15.
```

### <a name="match-zero-or-one-time-lazy-match-"></a>Совпадение нуль или один раз ("ленивое" совпадение): ??

Квантификатор **??** совпадает с предыдущим элементом ноль или один раз, но как можно меньшее число раз. Это ленивый квантификатор, являющийся аналогом жадного квантификатора **?**.

Например, регулярное выражение `^\s*(System.)??Console.Write(Line)??\(??` пытается сопоставить строки "Console.Write" или "Console.WriteLine". Строка может также включать "System." перед "Console", за ней может следовать открывающая скобка. Искомый текст должен находиться в начале строки, хотя перед ним может стоять пробел. В следующем примере показано, как использовать это регулярное выражение.

```csharp
string pattern = @"^\s*(System.)??Console.Write(Line)??\(??";
string input = "System.Console.WriteLine(\"Hello!\")\n" + 
                      "Console.Write(\"Hello!\")\n" + 
                      "Console.WriteLine(\"Hello!\")\n" + 
                      "Console.ReadLine()\n" + 
                      "   Console.WriteLine";
foreach (Match match in Regex.Matches(input, pattern, 
                                      RegexOptions.IgnorePatternWhitespace | 
                                      RegexOptions.IgnoreCase | 
                                      RegexOptions.Multiline))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        'System.Console.Write' found at position 0.
//        'Console.Write' found at position 36.
//        'Console.Write' found at position 61.
//        '   Console.Write' found at position 110.
```

```vb
Dim pattern As String = "^\s*(System.)??Console.Write(Line)??\(??"
Dim input As String = "System.Console.WriteLine(""Hello!"")" + vbCrLf + _
                      "Console.Write(""Hello!"")" + vbCrLf + _
                      "Console.WriteLine(""Hello!"")" + vbCrLf + _
                      "Console.ReadLine()" + vbCrLf + _
                      "   Console.WriteLine"
For Each match As Match In Regex.Matches(input, pattern, _
                                         RegexOptions.IgnorePatternWhitespace Or RegexOptions.IgnoreCase Or RegexOptions.MultiLine)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next 
' The example displays the following output:
'       'System.Console.Write' found at position 0.
'       'Console.Write' found at position 36.
'       'Console.Write' found at position 61.
'       '   Console.Write' found at position 110.
```

Шаблон регулярного выражения определяется, как показано в следующей таблице.

Шаблон | Описание
------- | ----------- 
`^` | Соответствует концу входной строки.
`\s*` | Соответствует нулю или нескольким символам пробела.
`(System.)??` | Совпадение с нулевым или единичным вхождением строки "System.".
`Console.Write` | Совпадение со строкой "Console.Write".
`(Line)??` | Совпадение с нулевым или единичным вхождением строки "Line".
`\(??` | Совпадение с нулем или одним экземпляром открывающих круглых скобок.
 
### <a name="match-exactly-n-times-lazy-match-n"></a>Совпадение ровно n раз ("ленивое" совпадение): {n}?

Квантификатор **{**_n_**}?** сопоставляет предыдущий элемент ровно *n* раз, где *n* — любое целое число. Это ленивый квантификатор, являющийся аналогом жадного квантификатора **{**_n_**}+**.

В следующем примере регулярное выражение `\b(\w{3,}?\.){2}?\w{3,}?\b` используется для определения адреса веб-сайта. Обратите внимание, что есть совпадение с "www.microsoft.com" и "msdn.microsoft.com", но нет совпадения с "mywebsite" или "mycompany.com".

```csharp
string pattern = @"\b(\w{3,}?\.){2}?\w{3,}?\b";
string input = "www.microsoft.com msdn.microsoft.com mywebsite mycompany.com";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        'www.microsoft.com' found at position 0.
//        'msdn.microsoft.com' found at position 18.
```

```vb
Dim pattern As String = "\b(\w{3,}?\.){2}?\w{3,}?\b"
 Dim input As String = "www.microsoft.com msdn.microsoft.com mywebsite mycompany.com"
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next     
' The example displays the following output:
'       'www.microsoft.com' found at position 0.
'       'msdn.microsoft.com' found at position 18.
```

Шаблон регулярного выражения определяется, как показано в следующей таблице.

Шаблон | Описание
------- | -----------
`\b` | Начало на границе слова.
`(\w{3,}?\.)` | Совпадение с минимум тремя словообразующими символами как можно меньшее количество раз, зак которыми следует символ точки. Это первая группа записи.
`(\w{3,}?\.){2}?` | Совпадение с шаблоном в первой группе два раза, но как можно меньшее количество раз.
`\b` | Сопоставление заканчивается на границе слова.
 
### <a name="match-at-least-n-times-lazy-match-n"></a>Совпадение как минимум n раз ("ленивое" совпадение): {n,}?

Квантификатор **{**_n_**,}?** сопоставляет предыдущий элемент как минимум *n* раз (где *n* — любое целое число), но как можно меньшее количество раз. Это ленивый квантификатор, являющийся аналогом жадного квантификатора **{**_n_**,}**.

См. пример использования квантификатора **{**_n_**}?** в предыдущем разделе. В регулярном выражении из этого примера квантификатор **{**_n_**,}** используется для поиска строки, состоящей по крайней мере из трех символов, после которых стоит точка.

### <a name="match-between-n-and-m-times-lazy-match-nm"></a>Совпадение от n до m раз ("ленивое" совпадение): {n,m}?

Квантификатор **{**_n_**,**_m_**}?** сопоставляет предыдущий элемент от *n* до *m* раз (где *n* и *m* — целые числа), но как можно меньшее количество раз. Это ленивый квантификатор, являющийся аналогом жадного квантификатора **{**_n_**,**_m_**}**.

В следующем примере регулярное выражение `\b[A-Z](\w*\s+){1,10}?[.!?]` сопоставляет фразы, содержащие от одного до десяти слов. Ему соответствуют все предложения в исходной строке кроме одного, длина которого составляет 18 слов.

```csharp
string pattern = @"\b[A-Z](\w*?\s*?){1,10}[.!?]";
string input = "Hi. I am writing a short note. Its purpose is " + 
                      "to test a regular expression that attempts to find " + 
                      "sentences with ten or fewer words. Most sentences " + 
                      "in this note are short.";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        'Hi.' found at position 0.
//        'I am writing a short note.' found at position 4.
//        'Most sentences in this note are short.' found at position 132.
```

```vb
Dim pattern As String = "\b[A-Z](\w*\s?){1,10}?[.!?]"
Dim input As String = "Hi. I am writing a short note. Its purpose is " + _
                      "to test a regular expression that attempts to find " + _
                      "sentences with ten or fewer words. Most sentences " + _
                      "in this note are short."
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next 
' The example displays the following output:
'       'Hi.' found at position 0.
'       'I am writing a short note.' found at position 4.
'       'Most sentences in this note are short.' found at position 132.
```

Шаблон регулярного выражения определяется, как показано в следующей таблице.

Шаблон | Описание
------- | -----------
`\b` | Начало на границе слова.
`[A-Z]` | Совпадение с любым символом верхнего регистра от А до Z.
`(\w*\s+)` | Совпадение с нулем или несколькими словообразующими символами, за которыми следует один или несколько символов пробела. Это первая захватываемая группа.
`{1,10}?` | Совпадение с предыдущим шаблоном от 1 до 10 раз, но как можно меньшее количество раз.
`[.!?]` | Совпадение с любым из знаков препинания ".", "!" или "?".
 
## <a name="greedy-and-lazy-quantifiers"></a>"Жадные" и "ленивые" квантификаторы

У некоторых квантификаторов есть две версии. 

* Жадная версия. 

  Жадный квантификатор пытается найти максимально возможное число соответствий элемента. 


* •Нежадная (ленивая) версия. 

 При использовании нежадных идентификаторов предпринимается попытка найти минимально возможное число соответствий элемента. Чтобы превратить жадный квантификатор в ленивый, достаточно добавить **?**.

Представьте простое регулярное выражение, позволяющее находить последние четыре цифры в числовой строке, например в номере кредитной карты. Версия регулярного выражения с жадным квантификатором **\*** будет иметь вид `\b.*([0-9]{4})\b`. Однако если строка содержит два числа, то с помощью такого регулярного выражения будут найдены только последние четыре цифры второго числа, как показано в следующем примере.

```csharp
string greedyPattern = @"\b.*([0-9]{4})\b";
string input1 = "1112223333 3992991999";
foreach (Match match in Regex.Matches(input1, greedyPattern))
   Console.WriteLine("Account ending in ******{0}.", match.Groups[1].Value);

// The example displays the following output:
//       Account ending in ******1999.
```

```vb
Dim greedyPattern As String = "\b.*([0-9]{4})\b"
Dim input1 As String = "1112223333 3992991999"
For Each match As Match In Regex.Matches(input1, greedypattern)
   Console.WriteLine("Account ending in ******{0}.", match.Groups(1).Value)
Next
' The example displays the following output:
'       Account ending in ******1999.
```

Регулярное выражение не совпадает с первым числом, поскольку при использовании квантификатора **\*** предпринимается попытка найти максимально возможное число совпадений с предыдущим элементом во всей строке, и поэтому совпадение находится только в конце строки.

Это не то, что нам нужно. Вместо этого можно использовать **\*?**. для извлечения цифр из обоих чисел, как показано в следующем примере.

```csharp
string lazyPattern = @"\b.*?([0-9]{4})\b";
string input2 = "1112223333 3992991999";
foreach (Match match in Regex.Matches(input2, lazyPattern))
   Console.WriteLine("Account ending in ******{0}.", match.Groups[1].Value);

// The example displays the following output:
//       Account ending in ******3333.
//       Account ending in ******1999.
```

```vb
Dim lazyPattern As String = "\b.*?([0-9]{4})\b"
Dim input2 As String = "1112223333 3992991999"
For Each match As Match In Regex.Matches(input2, lazypattern)
   Console.WriteLine("Account ending in ******{0}.", match.Groups(1).Value)
Next     
' The example displays the following output:
'       Account ending in ******3333.
'       Account ending in ******1999.
```

В большинстве случаев регулярные выражения с жадными и ленивыми квантификаторами возвращают одни и те же результаты. Результаты обычно различаются, если в регулярных выражениях используется подстановочный метасимвол (**.**), который соответствует любому символу. 

## <a name="quantifiers-and-empty-matches"></a>Квантификаторы и пустые соответствия

Квантификаторы **\***, **+** и **{**_n_**,**_m_**}** и их ленивые аналоги никогда не повторяются после пустого соответствия, если найдено минимальное количество записей. Это правило препятствует вхождению квантификаторов в бесконечные циклы при пустых соответствиях частей выражений, если максимальное количество возможных фиксаций группы бесконечно или приближено к бесконечному.

Например, в следующем коде показан результат вызова метода [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) с шаблоном регулярного выражения `(a?)*,`, который соответствует нулю или одному символу "a" ноль или более раз. Обратите внимание, что отдельная захватываемая группы записывает каждое вхождение "a" и [String.Empty](xref:System.String.Empty), но второго пустого совпадения нет, потому что первое пустое совпадение предписывает квантификатору прекратить повторение.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "(a?)*";
      string input = "aaabbb";
      Match match = Regex.Match(input, pattern);
      Console.WriteLine("Match: '{0}' at index {1}", 
                        match.Value, match.Index);
      if (match.Groups.Count > 1) {
         GroupCollection groups = match.Groups;
         for (int grpCtr = 1; grpCtr <= groups.Count - 1; grpCtr++) {
            Console.WriteLine("   Group {0}: '{1}' at index {2}", 
                              grpCtr, 
                              groups[grpCtr].Value,
                              groups[grpCtr].Index);
            int captureCtr = 0;
            foreach (Capture capture in groups[grpCtr].Captures) {
               captureCtr++;
               Console.WriteLine("      Capture {0}: '{1}' at index {2}", 
                                 captureCtr, capture.Value, capture.Index);
            }
         } 
      }   
   }
}
// The example displays the following output:
//       Match: 'aaa' at index 0
//          Group 1: '' at index 3
//             Capture 1: 'a' at index 0
//             Capture 2: 'a' at index 1
//             Capture 3: 'a' at index 2
//             Capture 4: '' at index 3
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(a?)*"
      Dim input As String = "aaabbb"
      Dim match As Match = Regex.Match(input, pattern)
      Console.WriteLine("Match: '{0}' at index {1}", 
                        match.Value, match.Index)
      If match.Groups.Count > 1 Then
         Dim groups As GroupCollection = match.Groups
         For grpCtr As Integer = 1 To groups.Count - 1
            Console.WriteLine("   Group {0}: '{1}' at index {2}", 
                              grpCtr, 
                              groups(grpCtr).Value,
                              groups(grpCtr).Index)
            Dim captureCtr As Integer = 0
            For Each capture As Capture In groups(grpCtr).Captures
               captureCtr += 1
               Console.WriteLine("      Capture {0}: '{1}' at index {2}", 
                                 captureCtr, capture.Value, capture.Index)
            Next
         Next 
      End If   
   End Sub
End Module
' The example displays the following output:
'       Match: 'aaa' at index 0
'          Group 1: '' at index 3
'             Capture 1: 'a' at index 0
'             Capture 2: 'a' at index 1
'             Capture 3: 'a' at index 2
'             Capture 4: '' at index 3
```

Чтобы увидеть практическое различие между захватываемой группой, определяющей минимальное и максимальное количество записей, и группой, определяющей фиксированное количество записей, воспользуйтесь шаблонами регулярных выражений `(a\1|(?(1)\1)){0,2}` и `(a\1|(?(1)\1)){2}`. Оба регулярных выражения состоят из одной захватываемой группы, которая определяется, как показано в следующей таблице. 

Шаблон | Описание
------- | -----------
`(a\1` | Сопоставление "a" вместе со значением первой захваченной группы...
`&#124;(?(1)` | … или проверка того, была ли определена первая захваченная группа. (Обратите внимание, что конструкция **(?(1)** не определяет захватываемую группу.)
`\1))` | Если первая захваченная группа существует, следует сопоставить ее значение. Если группа отсутствует, она будет соответствовать [String.Empty](xref:System.String.Empty). 
 
Первое регулярное выражение пытается сопоставить этот шаблон от нуля до двух раз. Второй — ровно два раза. Поскольку первый шаблон достигает своего минимального количества записей при первой записи значения [String.Empty](xref:System.String.Empty), он не повторяет попытку сопоставить `a\1;`. Квантификатор `{0,2}` допускает только пустые соответствия в последней итерации. Напротив, второе регулярное выражение соответствует "а", потому что оно вычисляет `a\1` второй раз. Минимальное число итераций (2) предписывает обработчику выполнять повтор после пустого соответствия.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern, input;

      pattern = @"(a\1|(?(1)\1)){0,2}";
      input = "aaabbb"; 

      Console.WriteLine("Regex pattern: {0}", pattern);
      Match match = Regex.Match(input, pattern);
      Console.WriteLine("Match: '{0}' at position {1}.", 
                        match.Value, match.Index);
      if (match.Groups.Count > 1) {
         for (int groupCtr = 1; groupCtr <= match.Groups.Count - 1; groupCtr++)
         {
            Group group = match.Groups[groupCtr];         
            Console.WriteLine("   Group: {0}: '{1}' at position {2}.", 
                              groupCtr, group.Value, group.Index);
            int captureCtr = 0;
            foreach (Capture capture in group.Captures) {
               captureCtr++;
               Console.WriteLine("      Capture: {0}: '{1}' at position {2}.", 
                                 captureCtr, capture.Value, capture.Index);
            }   
         }
      }
      Console.WriteLine();

      pattern = @"(a\1|(?(1)\1)){2}";
      Console.WriteLine("Regex pattern: {0}", pattern);
      match = Regex.Match(input, pattern);
         Console.WriteLine("Matched '{0}' at position {1}.", 
                           match.Value, match.Index);
      if (match.Groups.Count > 1) {
         for (int groupCtr = 1; groupCtr <= match.Groups.Count - 1; groupCtr++)
         {
            Group group = match.Groups[groupCtr];         
            Console.WriteLine("   Group: {0}: '{1}' at position {2}.", 
                              groupCtr, group.Value, group.Index);
            int captureCtr = 0;
            foreach (Capture capture in group.Captures) {
               captureCtr++;
               Console.WriteLine("      Capture: {0}: '{1}' at position {2}.", 
                                 captureCtr, capture.Value, capture.Index);
            }   
         }
      }
   }
}
// The example displays the following output:
//       Regex pattern: (a\1|(?(1)\1)){0,2}
//       Match: '' at position 0.
//          Group: 1: '' at position 0.
//             Capture: 1: '' at position 0.
//       
//       Regex pattern: (a\1|(?(1)\1)){2}
//       Matched 'a' at position 0.
//          Group: 1: 'a' at position 0.
//             Capture: 1: '' at position 0.
//             Capture: 2: 'a' at position 0.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern, input As String

      pattern = "(a\1|(?(1)\1)){0,2}"
      input = "aaabbb" 

      Console.WriteLine("Regex pattern: {0}", pattern)
      Dim match As Match = Regex.Match(input, pattern)
      Console.WriteLine("Match: '{0}' at position {1}.", 
                        match.Value, match.Index)
      If match.Groups.Count > 1 Then
         For groupCtr As Integer = 1 To match.Groups.Count - 1
            Dim group As Group = match.Groups(groupCtr)         
            Console.WriteLine("   Group: {0}: '{1}' at position {2}.", 
                              groupCtr, group.Value, group.Index)
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               captureCtr += 1
               Console.WriteLine("      Capture: {0}: '{1}' at position {2}.", 
                                 captureCtr, capture.Value, capture.Index)
            Next   
         Next
      End If
      Console.WriteLine()

      pattern = "(a\1|(?(1)\1)){2}"
      Console.WriteLine("Regex pattern: {0}", pattern)
      match = Regex.Match(input, pattern)
         Console.WriteLine("Matched '{0}' at position {1}.", 
                           match.Value, match.Index)
      If match.Groups.Count > 1 Then
         For groupCtr As Integer = 1 To match.Groups.Count - 1
            Dim group As Group = match.Groups(groupCtr)         
            Console.WriteLine("   Group: {0}: '{1}' at position {2}.", 
                              groupCtr, group.Value, group.Index)
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               captureCtr += 1
               Console.WriteLine("      Capture: {0}: '{1}' at position {2}.", 
                                 captureCtr, capture.Value, capture.Index)
            Next   
         Next
      End If
   End Sub
End Module
' The example displays the following output:
'       Regex pattern: (a\1|(?(1)\1)){0,2}
'       Match: '' at position 0.
'          Group: 1: '' at position 0.
'             Capture: 1: '' at position 0.
'       
'       Regex pattern: (a\1|(?(1)\1)){2}
'       Matched 'a' at position 0.
'          Group: 1: 'a' at position 0.
'             Capture: 1: '' at position 0.
'             Capture: 2: 'a' at position 0.
```

## <a name="see-also"></a>См. также

[Элементы языка регулярных выражений — краткий справочник](quick-ref.md)

[Поиск с возвратом в регулярных выражениях](backtracking.md)


