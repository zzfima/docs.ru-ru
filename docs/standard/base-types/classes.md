---
title: "Классы символов в регулярных выражениях"
description: "Классы символов в регулярных выражениях"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c7a9305f-7144-4fe8-80e8-a727bf7d223f
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: ae677af2590636fd144d8978a3500c37f9d33615
ms.lasthandoff: 03/03/2017

---

# <a name="character-classes-in-regular-expressions"></a>Классы символов в регулярных выражениях

Класс символов определяет набор символов, любой из которых может присутствовать во входной строке для успешного сопоставления. Язык регулярных выражений в .NET поддерживает следующие классы символов:

* Положительные группы символов. Входная строка должна содержать символ из указанного набора. Дополнительные сведения см. в разделе [Положительная группа символов](#positive-character-group--).

* Отрицательные группы символов. Входная строка не должна содержать символ из указанного набора. Дополнительные сведения см. в разделе [Отрицательная группа символов](#negative-character-group-).

* Любой символ. NATVIS-файл (точка) в регулярных выражениях является подстановочным знаком, который соответствует всем символам, кроме **\n**. Дополнительные сведения см. в разделе [Любой символ](#any-character-). 

* Общая категория Юникода или именованный блок. Входная строка должна содержать символ из определенной категории Юникода или непрерывного диапазона символов Юникода. Дополнительные сведения см. в разделе [Категория Юникода или блок Юникода](#unicode-category-or-unicode-block-p).

* Отрицательная общая категория Юникода или именованный блок. Входная строка не должна содержать символ из определенной категории Юникода или непрерывного диапазона символов Юникода. Дополнительные сведения см. в разделе [Отрицательная категория Юникода или блок Юникода](#negative-unicode-category-or-unicode-block-p).

* Словообразующий символ. Входная строка может содержать символ, относящийся к любой категории Юникода, соответствующей символам в словах. Дополнительные сведения см. в разделе [Словообразующий символ](#word-character-w).

* Несловообразующий символ. Входная строка может содержать символ, относящийся к любой категории Юникода, не соответствующей словообразующим символам. Дополнительные сведения см. в разделе [Несловообразующий символ](#non-word-character-w).

* Символ пробела. Входная строка может содержать любой разделитель Юникода, а также любой из множества управляющих символов. Дополнительные сведения см. в разделе [Символ пробела](#white-space-character-s).

* Символ, не являющийся пробелом. Входная строка может содержать любой символ, кроме пробела. Дополнительные сведения см. в разделе [Символ, не являющийся пробелом](#non-white-space-character-s).

* Десятичная цифра. Входная строка может содержать любой набор знаков, классифицируемых как десятичные цифры Юникода. Дополнительные сведения см. в разделе [Десятичная цифра](#decimal-digit-character-d).

* Недесятичная цифра. Входная строка может содержать любой символ, кроме десятичных цифр Юникода. Дополнительные сведения см. в разделе [Недесятичная цифра](#non-digit-character-d).


Платформа .NET поддерживает выражения вычитания в классах знаков, которые позволяют в результате исключения одного класса знаков из другого класса знаков определить набор знаков. Дополнительные сведения см. в разделе [Вычитание класса знаков](#character-class-subtraction).

## <a name="positive-character-group--"></a>Положительная группа символов: [ ]

Положительная группа символов задает список символов, один из которых должен присутствовать во входной строке для успешного сопоставления. Символы можно задать по отдельности или в виде диапазона. 

Синтаксис для указания списка отдельных символов выглядит следующим образом: 

[*character*_*group*]

Здесь *character_group* — это список отдельных символов, которые могут присутствовать во входной строке для успешного сопоставления. *character*_*group* может включать в себя любое сочетание литеральных символов, [escape-символов](escapes.md) или классов символов. 

Синтаксис для указания диапазона символов выглядит следующим образом:

```
[firstCharacter-lastCharacter]
```

Здесь *firstCharacter* — это символ, с которого начинается диапазон, а *lastCharacter* — символ, которым он заканчивается. Диапазон символов — это непрерывная последовательность знаков, которая задается указанием первого и последнего знака в последовательности и дефиса между ними. Два знака являются смежными, если они имеют соседние кодовые точки в Юникоде.

В следующей таблице перечислены некоторые распространенные шаблоны регулярных выражений, содержащие классы положительных символов.

Шаблон | Описание
------- | ----------- 
`[aeiou]` | Соответствует всем гласным.
`[\p{P}\d]` | Соответствует всем знакам препинания и десятичным цифрам.
`[\s\p{P}]` | Соответствует всем символам пробела и знакам препинания.
 
В следующем примере определена положительная группа знаков, которая содержит символы "a" и "e", таким образом, чтобы входная строка содержала слова grey или gray и еще одно слово.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"gr[ae]y\s\S+?[\s\p{P}]";
      string input = "The gray wolf jumped over the grey wall.";
      MatchCollection matches = Regex.Matches(input, pattern);
      foreach (Match match in matches)
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       gray wolf
//       grey wall.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "gr[ae]y\s\S+?[\s\p{P}]"
      Dim input As String = "The gray wolf jumped over the grey wall."
      Dim matches As MatchCollection = Regex.Matches(input, pattern)
      For Each match As Match In matches
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       gray wolf
'       grey wall.
```

Регулярное выражение `gr[ae]y\s\S+?[\s|\p{P}]` определяется следующим образом:

Шаблон | Описание
------- | ----------- 
`gr` | Соответствует буквенным символам "gr".
`[ae]` | Соответствует букве "a" или "e".
`y\s` | Соответствует буквенному символу "y", за которым следует пробел.
`\S+?` | Соответствует одному или нескольким символам, отличным от пробела.
`[\s\p{P}]` | Соответствует символу пробела или знаку препинания.
 
В следующем примере выделяются слова, начинающиеся с любой прописной буквы. Вложенное выражение `[A-Z]` представляет диапазон прописных букв от A до Z. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b[A-Z]\w*\b";
      string input = "A city Albany Zulu maritime Marseilles";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       A
//       Albany
//       Zulu
//       Marseilles
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b[A-Z]\w*\b"
      Dim input As String = "A city Albany Zulu maritime Marseilles"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
```

Определение регулярного выражения `\b[A-Z]\w*\b` показано в таблице ниже.

Шаблон | Описание
------- | ----------- 
`\b` | Начало на границе слова.
`[A-Z]` | Соответствует любому символу верхнего регистра от А до Z.
`\w*` | Совпадение с нулем или большим числом буквенных символов.
`\b` | Соответствует границе слова.

## <a name="negative-character-group-"></a>Отрицательная группа символов: [^]

Отрицательная группа символов задает список символов, которые не должны присутствовать во входной строке для успешного сопоставления. Символы можно задать по отдельности или в виде диапазона. 

Синтаксис для указания списка отдельных символов выглядит следующим образом:

[^*character*_*group*]

Здесь *character_group* — это список отдельных символов, которые не могут присутствовать во входной строке для успешного сопоставления. *character*_*group* может включать в себя любое сочетание литеральных символов, [escape-символов](escapes.md) или классов символов. 

Синтаксис для указания диапазона символов выглядит следующим образом:

[^*firstCharacter-lastCharacter*]

Здесь *firstCharacter* — это символ, с которого начинается диапазон, а *lastCharacter* — символ, которым он заканчивается. Диапазон символов — это непрерывная последовательность знаков, которая задается указанием первого и последнего знака в последовательности и дефиса между ними. Два знака являются смежными, если они имеют соседние кодовые точки в Юникоде.

Два или более диапазона знаков могут быть объединены. Например, чтобы задать диапазон десятичных цифр от "0" до "9", диапазон строчных букв от "a" до "f" и диапазон прописных букв от "A" до "F" используйте строку `[0-9a-fA-F]`.

Начальный символ (^) отрицательной группы символов является обязательным и указывает на то, что группа символов является отрицательной, а не положительной.

> [!IMPORTANT]
> Отрицательная группа символов в больших шаблонах регулярных выражений не является утверждением нулевой ширины. То есть после оценки отрицательной группы символов обработчик регулярных выражений перемещает один символ во входную строку.

В следующей таблице перечислены некоторые распространенные шаблоны регулярных выражений, содержащие отрицательные группы символов.

Шаблон | Описание
------- | ----------- 
`[^aeiou]` | Соответствует всем символам, кроме гласных.
`[^\p{P}\d]` | Соответствует всем символам, кроме знаков препинания и десятичных цифр.
 
Следующий пример соответствует любому слову, начинающемуся с символов "th", за которыми нет символа "o". 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\bth[^o]\w+\b";
      string input = "thought thing though them through thus thorough this";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       thing
//       them
//       through
//       thus
//       this
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\bth[^o]\w+\b"
      Dim input As String = "thought thing though them through thus " + _
                            "thorough this"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       thing
'       them
'       through
'       thus
'       this
```

Определение регулярного выражения `\bth[^o]\w+\b` показано в таблице ниже.

Шаблон | Описание
------- | ----------- 
`\b` | Начало на границе слова.
`th` | Соответствует буквенным символам "th".
`[^o]` | Соответствует любому символу, отличающемуся от "o".
`\w+` | Совпадение с одним или несколькими символами слова.
`\b` | Конец на границе слова.

## <a name="any-character-"></a>Любой символ: .

Символ точки (.) соответствует любому символу, кроме **\n** (символ перевода строки **\u000A**), с использованием следующих двух квалификаторов:

* Если шаблон регулярного выражения изменяется параметром [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline) или если часть этого шаблона, содержащая класс символов ".", изменяется параметром **s**, то "." соответствует любому символу. Дополнительные сведения см. в статье [Параметры регулярных выражений](options.md).

  В следующем примере показано различное поведение класса символов "." по умолчанию и с параметром [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline). Регулярное выражение `^.+` начинается с начала строки и соответствует любому знаку. По умолчанию соответствие заканчивается в конце первой строки; шаблон регулярного выражения соответствует символу возврата каретки **\r** или **\u000D**, но не соответствует **\n**. Поскольку параметр [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline) интерпретирует всю входную строку как единую строку, он сопоставляет каждый символ в строке ввода, включая **\n**.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "^.+";
      string input = "This is one line and" + Environment.NewLine + "this is the second.";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(Regex.Escape(match.Value));

      Console.WriteLine();
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.Singleline))
         Console.WriteLine(Regex.Escape(match.Value));
   }
}
// The example displays the following output:
//       This\ is\ one\ line\ and\r
//       
//       This\ is\ one\ line\ and\r\nthis\ is\ the\ second\.
```

```vb
Imports System.Text.RegularExpressions

Module Example
    Public Sub Main()
        Dim pattern As String = "^.+"
        Dim input As String = "This is one line and" + vbCrLf + "this is the second."
        For Each match As Match In Regex.Matches(input, pattern)
           Console.WriteLine(Regex.Escape(match.Value))
        Next
        Console.WriteLine()
        For Each match As Match In Regex.Matches(input, pattern, RegexOptions.SingleLine)
           Console.WriteLine(Regex.Escape(match.Value))
        Next
     End Sub
  End Module
  ' The example displays the following output:
  '       This\ is\ one\ line\ and\r
  '       
  '       This\ is\ one\ line\ and\r\nthis\ is\ the\ second\.
```

  > [!NOTE]
  > Так как класс символов "." соответствует любому символу, кроме **\n**, он также соответствует **\r** (символ возврата каретки **\u000D**).
 
* Точка в положительной или отрицательной группе символов рассматривается как литеральный символ точки, а не как класс символов. Дополнительные сведения см. в разделах [Положительная группа символов](#positive-character-group--) и [Отрицательная группа символов](#negative-character-group-) ранее в этой статье. В следующем примере представлено определение регулярного выражения, содержащее символ точки (**.**) как класс символов и как член положительной группы символов. Регулярное выражение `\b.*[.?!;:](\s|\z)` начинается на границе слова, выделяет все символы, пока не встретится один из четырех знаков препинания (включая точку), после чего выделяет символ пробела или конца строки.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b.*[.?!;:](\s|\z)";
      string input = "this. what: is? go, thing.";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       this. what: is? go, thing.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As STring = "\b.*[.?!;:](\s|\z)"
      Dim input As String = "this. what: is? go, thing."
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next   
   End Sub
End Module
' The example displays the following output:
'       this. what: is? go, thing.
```

  > [!NOTE]
  > Так как элемент языка "." соответствует любому символу, он часто используется с отложенным квантификатором, если шаблон регулярного выражения пытается несколько раз найти соответствие любому символу. Дополнительные сведения см. в статье [Квантификаторы в регулярных выражениях](quantifiers.md). 
 
## <a name="unicode-category-or-unicode-block-p"></a>Категория Юникода или блок Юникода: \p{}

В стандарте Юникода каждому символу присваивается общая категория. Например, определенный символ может быть прописной буквой (категория **Lu**), десятичной цифрой (категория **Nd**), математическим символом (категория **Sm**) или разделителем абзацев (категория **Zl**). Определенные наборы символов стандарта Юникод также занимают некоторый диапазон или блок последовательных кодовых точек. Например, базовая латинская кодировка находится в диапазоне от **\u0000** до **\u007F**, а арабская кодировка — в диапазоне от **\u0600** до **\u06FF**. 

Конструкция регулярного выражения

**\p{**_name_**}**

соответствует любым символам, которые относятся к общей категории Юникода или именованному блоку, где name — сокращенное название категории или имя блока. Список сокращений категорий см. в разделе [Поддерживаемые общие категории Юникода](#supported-unicode-general-categories) далее в этой статье. Список именованных блоков см. в разделе [Поддерживаемые именованные блоки](#supported-named-blocks) далее в этой статье. 

В примере ниже конструкция **\p{**_name_**}** используется для выделения общей категории Юникода (в данном случае **Pd** или Punctuation,Dash, т. е. категории знаков препинания и тире) и именованного блока (**IsGreek** и **IsBasicLatin**).

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+";
      string input = "?ata ?a??a??? - The Gospel of Matthew";

      Console.WriteLine(Regex.IsMatch(input, pattern));        // Displays True.
   }
}
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+"
      Dim input As String = "Κατα Μαθθαίον - The Gospel of Matthew"

      Console.WriteLine(Regex.IsMatch(input, pattern))         ' Displays True.
   End Sub
End Module
```

Определение регулярного выражения `\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+` показано в таблице ниже.

Шаблон | Описание
------- | ----------- 
`\b` | Начало на границе слова.
`\p{IsGreek}+` | Соответствует одному или нескольким греческим символам.
`(\s)?` | Совпадение с нулем или одним символом пробела.
`(\p{IsGreek}+(\s)?)+` | Выделяет один или несколько раз шаблон из одного или нескольких греческих символов, за которыми следует ноль или один символ пробела. 
`\p{Pd}` | Соответствует знакам препинания и тире.
`\s` | Соответствует пробелу.
`\p{IsBasicLatin}+` | Соответствует одному или нескольким базовым латинским символам.
`(\s)?` | Совпадение с нулем или одним символом пробела.
`(\p{IsBasicLatin}+(\s)?)+` | Выделяет один или несколько раз шаблон из одного или нескольких базовых латинских символов, за которыми следует ноль или один символ пробела.

## <a name="negative-unicode-category-or-unicode-block-p"></a>Отрицательная категория Юникода или блок Юникода: \P{}

В стандарте Юникода каждому символу присваивается общая категория. Например, определенный символ может быть прописной буквой (категория **Lu**), десятичной цифрой (категория **Nd**), математическим символом (категория **Sm**) или разделителем абзацев (категория **Zl**). Определенные наборы символов стандарта Юникод также занимают некоторый диапазон или блок последовательных кодовых точек. Например, базовая латинская кодировка находится в диапазоне от **\u0000** до **\u007F**, а арабская кодировка — в диапазоне от **\u0600** до **\u06FF**. 

Конструкция регулярного выражения

**\P{**_name_**}**

соответствует любым символам, которые относятся к общей категории Юникода или именованному блоку, где name — сокращенное название категории или имя блока. Список сокращений категорий см. в разделе [Поддерживаемые общие категории Юникода](#supported-unicode-general-categories) далее в этой статье. Список именованных блоков см. в разделе [Поддерживаемые именованные блоки](#supported-named-blocks) далее в этой статье.

В примере ниже конструкция **\P{**_name_**}** используется для удаления любых символов валют (в данном случае **Sc** или Symbol, Currency, т. е. категории символов и валют) из числовых строк.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(\P{Sc})+";

      string[] values = { "$164,091.78", "£1,073,142.68", "73¢", "€120" };
      foreach (string value in values)
         Console.WriteLine(Regex.Match(value, pattern).Value);
   }
}
// The example displays the following output:
//       164,091.78
//       1,073,142.68
//       73
//       120
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(\P{Sc})+"

      Dim values() As String = { "$164,091.78", "£1,073,142.68", "73¢", "€120"}
      For Each value As String In values
         Console.WriteLine(Regex.Match(value, pattern).Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       164,091.78
'       1,073,142.68
'       73
'       120
```

Шаблон регулярного выражения `(\P{Sc})+` выделяет один или несколько символов, которые не являются символами валют. Это позволяет удалить любой символ валюты из строки результата.

## <a name="word-character-w"></a>Словообразующий символ: \w

**\w** соответствует любому словообразующему символу. Словообразующий символ входит во все категории Юникода, перечисленные в следующей таблице. 

Категория | Описание
-------- | ----------- 
Ll | Буква: строчные буквы
Lu | Буква: прописные буквы
Lt | Буква: заглавный регистр
Lo | Буква: другие
Lm | Буква: модификатор
Mn | Метка: не занимающая место
Nd | Число: десятичная цифра
Pc | Пунктуация, соединитель. Эта категория включает десять символов, наиболее часто используемым из которых является знак подчеркивания (_), u+005F.
 
Если задано поведение, совместимое с ECMAScript, то параметр **\w** эквивалентен `[a-zA-Z_0-9]`. Информацию о регулярных выражениях ECMAScript см. в разделе [Поведение сопоставления ECMAScript](options.md#ecmascript-matching-behavior) статьи [Параметры регулярных выражений](options.md). 

> [!NOTE]
> Так как элемент языка \w соответствует любому словообразующему символу, он часто используется с отложенным квантификатором, если шаблон регулярного выражения пытается несколько раз найти соответствие любому словообразующему символу, за которым следует определенный словообразующий символ. Дополнительные сведения см. в статье [Квантификаторы в регулярных выражениях](quantifiers.md).

В следующем примере элемент языка **\w** используется для выделения повторяющихся символов в слове. В примере определяется шаблон регулярного выражения **(\w)\1**, который можно интерпретировать следующим образом.

Элемент | Описание
------- | -----------
(\w) | Соответствует словообразующему символу. Это первая группа записи.
\1 | Соответствует значению первой записи. 
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(\w)\1";
      string[] words = { "trellis", "seer", "latter", "summer", 
                         "hoarse", "lesser", "aardvark", "stunned" };
      foreach (string word in words)
      {
         Match match = Regex.Match(word, pattern);
         if (match.Success)
            Console.WriteLine("'{0}' found in '{1}' at position {2}.", 
                              match.Value, word, match.Index);
         else
            Console.WriteLine("No double characters in '{0}'.", word);
      }                                                  
   }
}
// The example displays the following output:
//       'll' found in 'trellis' at position 3.
//       'ee' found in 'seer' at position 1.
//       'tt' found in 'latter' at position 2.
//       'mm' found in 'summer' at position 2.
//       No double characters in 'hoarse'.
//       'ss' found in 'lesser' at position 2.
//       'aa' found in 'aardvark' at position 0.
//       'nn' found in 'stunned' at position 3.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(\w)\1"
      Dim words() As String = { "trellis", "seer", "latter", "summer", _
                                "hoarse", "lesser", "aardvark", "stunned" }
      For Each word As String In words
         Dim match As Match = Regex.Match(word, pattern)
         If match.Success Then
            Console.WriteLine("'{0}' found in '{1}' at position {2}.", _
                              match.Value, word, match.Index)
         Else
            Console.WriteLine("No double characters in '{0}'.", word)
         End If
      Next                                                  
   End Sub
End Module
' The example displays the following output:
'       'll' found in 'trellis' at position 3.
'       'ee' found in 'seer' at position 1.
'       'tt' found in 'latter' at position 2.
'       'mm' found in 'summer' at position 2.
'       No double characters in 'hoarse'.
'       'ss' found in 'lesser' at position 2.
'       'aa' found in 'aardvark' at position 0.
'       'nn' found in 'stunned' at position 3.
```

## <a name="non-word-character-w"></a>Несловообразующий символ: \W

**\W** соответствует любому несловообразующему символу. Элемент языка **\W** эквивалентен следующему классу символов:

```
[^\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]
```

Другими словами, он соответствует любому символу, за исключением символов в категории Юникода, перечисленных в следующей таблице.

Категория | Описание
-------- | -----------
Ll | Буква: строчные буквы
Lu | Буква: прописные буквы
Lt | Буква: заглавный регистр
Lo | Буква: другие
Lm | Буква: модификатор
Mn | Метка: не занимающая место
Nd | Число: десятичная цифра
Pc | Пунктуация, соединитель. Эта категория включает десять символов, наиболее часто используемым из которых является знак подчеркивания (_), u+005F.
 
Если задано поведение, совместимое с ECMAScript, то параметр **\W** эквивалентен `[^a-zA-Z_0-9]`. Информацию о регулярных выражениях ECMAScript см. в разделе [Поведение сопоставления ECMAScript](options.md#ecmascript-matching-behavior) статьи [Параметры регулярных выражений](options.md). 

> [!NOTE]
> Так как элемент языка \w соответствует любому словообразующему символу, он часто используется с отложенным квантификатором, если шаблон регулярного выражения пытается несколько раз найти соответствие любому словообразующему символу, за которым следует определенный словообразующий символ. Дополнительные сведения см. в статье [Квантификаторы в регулярных выражениях](quantifiers.md). 

В следующем примере показан класс символов **\W**. Он определяет шаблон регулярного выражения `\b(\w+)(\W){1,2}`, выделяющий слово, за которым следует один или два несловообразующих символа, например пробелы или знаки препинания. Возможные интерпретации регулярного выражения показаны в следующей таблице.

Элемент | Описание
------- | ----------- 
\b | Совпадение должно начинаться на границе слова.
(\w+) | Совпадение с одним или несколькими символами слова. Это первая группа записи.
(\W){1,2} | Выделяет несловообразующий символ один или два раза. Это вторая группа записи.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\w+)(\W){1,2}";
      string input = "The old, grey mare slowly walked across the narrow, green pasture.";
      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine(match.Value);
         Console.Write("   Non-word character(s):");
         CaptureCollection captures = match.Groups[2].Captures;
         for (int ctr = 0; ctr < captures.Count; ctr++)
             Console.Write(@"'{0}' (\u{1}){2}", captures[ctr].Value, 
                           Convert.ToUInt16(captures[ctr].Value[0]).ToString("X4"), 
                           ctr < captures.Count - 1 ? ", " : "");
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The
//          Non-word character(s):' ' (\u0020)
//       old,
//          Non-word character(s):',' (\u002C), ' ' (\u0020)
//       grey
//          Non-word character(s):' ' (\u0020)
//       mare
//          Non-word character(s):' ' (\u0020)
//       slowly
//          Non-word character(s):' ' (\u0020)
//       walked
//          Non-word character(s):' ' (\u0020)
//       across
//          Non-word character(s):' ' (\u0020)
//       the
//          Non-word character(s):' ' (\u0020)
//       narrow,
//          Non-word character(s):',' (\u002C), ' ' (\u0020)
//       green
//          Non-word character(s):' ' (\u0020)
//       pasture.
//          Non-word character(s):'.' (\u002E)
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\w+)(\W){1,2}"
      Dim input As String = "The old, grey mare slowly walked across the narrow, green pasture."
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
         Console.Write("   Non-word character(s):")
         Dim captures As CaptureCollection = match.Groups(2).Captures
         For ctr As Integer = 0 To captures.Count - 1
             Console.Write("'{0}' (\u{1}){2}", captures(ctr).Value, _
                           Convert.ToUInt16(captures(ctr).Value.Chars(0)).ToString("X4"), _
                           If(ctr < captures.Count - 1, ", ", ""))
         Next
         Console.WriteLine()
      Next
   End Sub
End Module
' The example displays the following output:
'       The
'          Non-word character(s):' ' (\u0020)
'       old,
'          Non-word character(s):',' (\u002C), ' ' (\u0020)
'       grey
'          Non-word character(s):' ' (\u0020)
'       mare
'          Non-word character(s):' ' (\u0020)
'       slowly
'          Non-word character(s):' ' (\u0020)
'       walked
'          Non-word character(s):' ' (\u0020)
'       across
'          Non-word character(s):' ' (\u0020)
'       the
'          Non-word character(s):' ' (\u0020)
'       narrow,
'          Non-word character(s):',' (\u002C), ' ' (\u0020)
'       green
'          Non-word character(s):' ' (\u0020)
'       pasture.
'          Non-word character(s):'.' (\u002E)
```

Поскольку объект `Group` для второй группы записи содержит только один захваченный несловообразующий символ, в примере извлекаются все захваченные несловообразующие символы из объекта `CaptureCollection`, который возвращается свойством `Group.Captures`.

## <a name="white-space-character-s"></a>Символ пробела: \s

**\s** соответствует любому символу пробела. Это эквивалентно управляющим последовательностям и категориям Юникода, перечисленным в следующей таблице. 

Категория | Описание
-------- | ----------- 
**\f** | Символ перевода страницы, \u000C.
**\n** | Символ новой строки, \u000A.
**\r** | Символ возврата каретки, \u000D.
**\t** | Символ табуляции, \u0009.
**\v** | Символ вертикальной табуляции, \u000B.
**\x85** | Многоточие или символ NEXT LINE (NEL) (…), \u0085.
**\p{Z}** | Соответствует любому разделительному символу.
 

Если задано поведение, совместимое с ECMAScript, то параметр **\s** эквивалентен `[ \f\n\r\t\v]`.  Информацию о регулярных выражениях ECMAScript см. в разделе [Поведение сопоставления ECMAScript](options.md#ecmascript-matching-behavior) статьи [Параметры регулярных выражений](options.md). 

В примере ниже показан класс символов \s. Он определяет шаблон регулярного выражения `\b\w+(e)?s(\s|$)`, выделяющий слово, заканчивающееся на "s" или "es", за которым следует знак пробела или конец входной строки. Возможные интерпретации регулярного выражения показаны в следующей таблице.

Элемент | Описание
------- | -----------
\b | Совпадение должно начинаться на границе слова.
\w+ | Совпадение с одним или несколькими символами слова. 
(e)? | Выделяет "e" ноль или один раз.
s | Выделяет "s".
(\s|$) | Совпадает с символом пробела или концом входной строки.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b\w+(e)?s(\s|$)";
      string input = "matches stores stops leave leaves";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       matches
//       stores
//       stops
//       leaves
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b\w+(e)?s(\s|$)"
      Dim input As String = "matches stores stops leave leaves"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)      
      Next
   End Sub
End Module
' The example displays the following output:
'       matches
'       stores
'       stops
'       leaves
```

## <a name="non-white-space-character-s"></a>Символ, не являющийся пробелом: \S

**\S** соответствует любому символу, не являющемуся пробелом. Он эквивалентен шаблону регулярного выражения `[^\f\n\r\t\v\x85\p{Z}]` или противоположному шаблону, эквивалентному **\s**, выделяющему символы пробела. Дополнительные сведения см. в подразделе "Символ пробела: \s".

Если задано поведение, совместимое с ECMAScript, то параметр **\S** эквивалентен `[^ \f\n\r\t\v]`. Информацию о регулярных выражениях ECMAScript см. в разделе [Поведение сопоставления ECMAScript](options.md#ecmascript-matching-behavior) статьи [Параметры регулярных выражений](options.md).

В следующем примере показан элемент языка **\S**. Шаблон регулярного выражения \b(\S+)\s? выделяет строки, разделенные символами пробела. Второй элемент в объекте GroupCollection содержит совпадающую строку. Возможные интерпретации регулярного выражения показаны в следующей таблице.

Элемент | Описание
------- | ----------- 
`\b` | Совпадение должно начинаться на границе слова.
`(\S+)` | Соответствует одному или нескольким символам, которые не являются пробелами. Это первая группа записи.
`\s?` | Совпадение с нулем или одним символом пробела. 
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\S+)\s?";
      string input = "This is the first sentence of the first paragraph. " + 
                            "This is the second sentence.\n" + 
                            "This is the only sentence of the second paragraph.";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Groups[1]);
   }
}
// The example displays the following output:
//    This
//    is
//    the
//    first
//    sentence
//    of
//    the
//    first
//    paragraph.
//    This
//    is
//    the
//    second
//    sentence.
//    This
//    is
//    the
//    only
//    sentence
//    of
//    the
//    second
//    paragraph.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\S+)\s?"
      Dim input As String = "This is the first sentence of the first paragraph. " + _
                            "This is the second sentence." + vbCrLf + _
                            "This is the only sentence of the second paragraph."
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Groups(1))
      Next
   End Sub
End Module
' The example displays the following output:
'    This
'    is
'    the
'    first
'    sentence
'    of
'    the
'    first
'    paragraph.
'    This
'    is
'    the
'    second
'    sentence.
'    This
'    is
'    the
'    only
'    sentence
'    of
'    the
'    second
'    paragraph.
```

## <a name="decimal-digit-character-d"></a>Десятичная цифра: \d

**\d** соответствует любой десятичной цифре. Он эквивалентен шаблону регулярного выражения `\\p{Nd}`, который включает стандартные десятичные цифры 0–9, а также десятичные цифры из некоторых других наборов символов.

Если задано поведение, совместимое с ECMAScript, то параметр **\d** эквивалентен `[0-9]`. Информацию о регулярных выражениях ECMAScript см. в разделе [Поведение сопоставления ECMAScript](options.md#ecmascript-matching-behavior) статьи [Параметры регулярных выражений](options.md).

В следующем примере показан элемент языка **\d**. Проверяет, представляет ли входная строка допустимый телефонный номер в США и Канаде. Шаблон регулярного выражения `^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$` определяется, как показано в следующей таблице.

Элемент | Описание
------- | ----------- 
`^` | Начало совпадения в начале входной строки.
`\(?` | Выделяет ноль или один символ "(". 
`\d{3}` | Совпадение с тремя десятичными цифрами. 
`\)?` | Выделяет ноль или один символ ")".
`[\s-]` | Выделяет дефис или пробел.
`(\(?\d{3}\)?[\s-])?` | Выделяет несколько раз необязательные открывающие скобки с последующими тремя десятичными цифрами, необязательную закрывающую скобку, а также знак пробела или дефис (если они есть). Это первая группа записи.
`\d{3}-\d{4}` | Выделяет три десятичных цифры, следующий за ними дефис и еще четыре десятичные цифры.
`$` | Соответствует концу входной строки.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$";
      string[] inputs = { "111 111-1111", "222-2222", "222 333-444", 
                          "(212) 111-1111", "111-AB1-1111", 
                          "212-111-1111", "01 999-9999" };

      foreach (string input in inputs)
      {
         if (Regex.IsMatch(input, pattern)) 
            Console.WriteLine(input + ": matched");
         else
            Console.WriteLine(input + ": match failed");
      }
   }
}
// The example displays the following output:
//       111 111-1111: matched
//       222-2222: matched
//       222 333-444: match failed
//       (212) 111-1111: matched
//       111-AB1-1111: match failed
//       212-111-1111: matched
//       01 999-9999: match failed
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$"
      Dim inputs() As String = { "111 111-1111", "222-2222", "222 333-444", _
                                 "(212) 111-1111", "111-AB1-1111", _
                                 "212-111-1111", "01 999-9999" }

      For Each input As String In inputs
         If Regex.IsMatch(input, pattern) Then 
            Console.WriteLine(input + ": matched")
         Else
            Console.WriteLine(input + ": match failed")
         End If   
      Next
   End Sub
End Module
' The example displays the following output:
'       111 111-1111: matched
'       222-2222: matched
'       222 333-444: match failed
'       (212) 111-1111: matched
'       111-AB1-1111: match failed
'       212-111-1111: matched
'       01 999-9999: match failed
```

## <a name="non-digit-character-d"></a>Символ, не являющийся цифрой: \D

**\D** соответствует любому символу, не являющемуся цифрой. Он эквивалентен шаблону регулярного выражения `\P{Nd}`.

Если задано поведение, совместимое с ECMAScript, то параметр **\D** эквивалентен `[^0-9]`. Информацию о регулярных выражениях ECMAScript см. в разделе [Поведение сопоставления ECMAScript](options.md#ecmascript-matching-behavior) статьи [Параметры регулярных выражений](options.md).

В следующем примере показан элемент языка **\D**. Он проверяет, включает ли строка (например, номер продукта) соответствующее сочетание десятичных и недесятичных символов. Шаблон регулярного выражения `^\D\d{1,5}\D*$` определяется, как показано в следующей таблице.

Элемент | Описание
------- | ----------- 
`^` | Начало совпадения в начале входной строки.
`\D` | Выделяет любой символ, не являющийся цифрой. 
`\d{1,5}` | Выделяет от одной до пяти десятичных цифр. 
`\D*` | Выделяет нуль, одну или несколько недесятичных цифр. 
`$` | Соответствует концу входной строки.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"^\D\d{1,5}\D*$"; 
      string[] inputs = { "A1039C", "AA0001", "C18A", "Y938518" }; 

      foreach (string input in inputs)
      {
         if (Regex.IsMatch(input, pattern))
            Console.WriteLine(input + ": matched");
         else
            Console.WriteLine(input + ": match failed");
      }
   }
}
// The example displays the following output:
//       A1039C: matched
//       AA0001: match failed
//       C18A: matched
//       Y938518: match failed
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^\D\d{1,5}\D*$" 
      Dim inputs() As String = { "A1039C", "AA0001", "C18A", "Y938518" } 

      For Each input As String In inputs
         If Regex.IsMatch(input, pattern) Then
            Console.WriteLine(input + ": matched")
         Else
            Console.WriteLine(input + ": match failed")
         End If   
      Next
   End Sub
End Module
' The example displays the following output:
```

## <a name="supported-unicode-general-categories"></a>Поддерживаемые общие категории Юникода

В Юникоде определяются общие категории, приведенные в следующей таблице. Дополнительные сведения см. в подразделах "Формат файлов UCD" и "Значения общих категорий" в разделе [База данных символов Юникода](http://www.unicode.org/reports/tr44/).

Категория | Описание
-------- | -----------
**Lu** | Буква: прописные буквы
**Ll** | Буква: строчные буквы
**Lt** | Буква: заглавный регистр
**Lm** | Буква: модификатор
**Lo** | Буква: другие
**L** | Все буквенные символы. Сюда входят символы **Lu**, **Ll**, **Lt**, **Lm** и **Lo**.
**Mn** | Метка: не занимающая место
**Mc** | Метка: комбинированная
**Me** | Метка: вложенная
**M** | Все диакритические знаки. Сюда входят категории **Mn**, **Mc** и **Me**.
**Nd** | Число: десятичная цифра
**Nl** | Число: буква
**No** | Число: другое
**N** | Все числа. Сюда входят категории **Nd**, **Nl** и **No**.
**Pc** | Пунктуация: соединитель
**Pd** | Пунктуация: тире
**Ps** | Пунктуация: открывающий знак пунктуации
**Pe** | Пунктуация: закрывающий знак пунктуации
**Pi** | Пунктуация: открывающая кавычка (в зависимости от использования поведение может быть аналогичным Ps или Pe)
**Pf** | Пунктуация: закрывающая кавычка (в зависимости от использования поведение может быть аналогичным Ps или Pe)
**Po** | Пунктуация: другие знаки пунктуации
**P** | Все знаки препинания. Сюда входят категории **Pc**, **Pd**, **Ps**, **Pe**, **Pi**, **Pf** и **Po**.
**Sm** | Символ: математический
**Sc** | Символ денежной единицы
**Sk** | Символ: модификатор
**So** | Символ: другие
**S** | Все символы. Сюда входят категории **Sm**, **Sc**, **Sk** и **So**.
**Zs** | Разделитель: пробел
**Zl** | Разделитель: строка
**Zp** | Разделитель: абзац
**Z** | Все знаки разделения. Сюда входят категории **Zs**, **Zl** и **Zp**.
**Cc** | Другое: управляющий символ
**Cf** | Другое: формат
**Cs** | Другое: заменяющий символ
**Co** | Другое: индивидуальное использование
**Cn** | Другое: неназначенные символы (ни один символ не имеет этого свойства)
**C** | Все управляющие символы. Сюда входят категории **Cc**, **Cf**, **Cs**, **Co** и **Cn**.
 
##<a name="supported-named-blocks"></a>Поддерживаемые именованные блоки

Платформа .NET предоставляет именованные блоки, перечисленные в следующей таблице. Набор поддерживаемых именованных блоков составлен на основе Юникода версии 4.0 и Perl версии 5.6.

Диапазон кодовых точек | Имя блока
---------------- | ---------- 
0000 - 007F | **IsBasicLatin**
0080 - 00FF | **IsLatin-1Supplement**
0100 - 017F | **IsLatinExtended-A**
0180 - 024F | **IsLatinExtended-B**
0250 - 02AF | **IsIPAExtensions**
02B0 - 02FF | **IsSpacingModifierLetters**
0300 - 036F | **IsCombiningDiacriticalMarks**
0370 - 03FF | **IsGreek** -или- **IsGreekandCoptic**
0400 - 04FF | **IsCyrillic**
0500 - 052F | **IsCyrillicSupplement**
0530 - 058F | **IsArmenian**
0590 - 05FF | **IsHebrew**
0600 - 06FF | **IsArabic**
0700 - 074F | **IsSyriac**
0780 - 07BF | **IsThaana**
0900 - 097F | **IsDevanagari**
0980 - 09FF | **IsBengali**
0A00 - 0A7F | **IsGurmukhi**
0A80 - 0AFF | **IsGujarati**
0B00 - 0B7F | **IsOriya**
0B80 - 0BFF | **IsTamil**
0C00 - 0C7F | **IsTelugu**
0C80 - 0CFF | **IsKannada**
0D00 - 0D7F | **IsMalayalam**
0D80 - 0DFF | **IsSinhala**
0E00 - 0E7F | **IsThai**
0E80 - 0EFF | **IsLao**
0F00 - 0FFF | **IsTibetan**
1000 - 109F | **IsMyanmar**
10A0 - 10FF | **IsGeorgian**
1100 - 11FF | **IsHangulJamo**
1200 - 137F | **IsEthiopic**
13A0 - 13FF | **IsCherokee**
1400 - 167F | **IsUnifiedCanadianAboriginalSyllabics**
1680 - 169F | **IsOgham**
16A0 - 16FF | **IsRunic**
1700 - 171F | **IsTagalog**
1720 - 173F | **IsHanunoo**
1740 - 175F | **IsBuhid**
1760 - 177F | **IsTagbanwa**
1780 - 17FF | **IsKhmer**
1800 - 18AF | **IsMongolian**
1900 - 194F | **IsLimbu**
1950 - 197F | **IsTaiLe**
19E0 - 19FF | **IsKhmerSymbols**
1D00 - 1D7F | **IsPhoneticExtensions**
1E00 - 1EFF | **IsLatinExtendedAdditional**
1F00 - 1FFF | **IsGreekExtended**
2000 - 206F | **IsGeneralPunctuation**
2070 - 209F | **IsSuperscriptsandSubscripts**
20A0 - 20CF | **IsCurrencySymbols**
20D0 - 20FF | **IsCombiningDiacriticalMarksforSymbols** -или- **IsCombiningMarksforSymbols**
2100 - 214F | **IsLetterlikeSymbols**
2150 - 218F | **IsNumberForms**
2190 - 21FF | **IsArrows**
2200 - 22FF | **IsMathematicalOperators**
2300 - 23FF | **IsMiscellaneousTechnical**
2400 - 243F | **IsControlPictures**
2440 - 245F | **IsOpticalCharacterRecognition**
2460 - 24FF | **IsEnclosedAlphanumerics**
2500 - 257F | **IsBoxDrawing**
2580 - 259F | **IsBlockElements**
25A0 - 25FF | **IsGeometricShapes**
2600 - 26FF | **IsMiscellaneousSymbols**
2700 - 27BF | **IsDingbats**
27C0 - 27EF | **IsMiscellaneousMathematicalSymbols-A**
27F0 - 27FF | **IsSupplementalArrows-A**
2800 - 28FF | **IsBraillePatterns**
2900 - 297F | **IsSupplementalArrows-B**
2980 - 29FF | **IsMiscellaneousMathematicalSymbols-B**
2A00 - 2AFF | **IsSupplementalMathematicalOperators**
2B00 - 2BFF | **IsMiscellaneousSymbolsandArrows**
2E80 - 2EFF | **IsCJKRadicalsSupplement**
2F00 - 2FDF | **IsKangxiRadicals**
2FF0 - 2FFF | **IsIdeographicDescriptionCharacters**
3000 - 303F | **IsCJKSymbolsandPunctuation**
3040 - 309F | **IsHiragana**
30A0 - 30FF | **IsKatakana**
3100 - 312F | **IsBopomofo**
3130 - 318F | **IsHangulCompatibilityJamo**
3190 - 319F | **IsKanbun**
31A0 - 31BF | **IsBopomofoExtended**
31F0 - 31FF | **IsKatakanaPhoneticExtensions**
3200 - 32FF | **IsEnclosedCJKLettersandMonths**
3300 - 33FF | **IsCJKCompatibility**
3400 - 4DBF | **IsCJKUnifiedIdeographsExtensionA**
4DC0 - 4DFF | **IsYijingHexagramSymbols**
4E00 - 9FFF | **IsCJKUnifiedIdeographs**
A000 - A48F | **IsYiSyllables**
A490 - A4CF | **IsYiRadicals**
AC00 - D7AF | **IsHangulSyllables**
D800 - DB7F | **IsHighSurrogates**
DB80 - DBFF | **IsHighPrivateUseSurrogates**
DC00 - DFFF | **IsLowSurrogates**
E000 - F8FF | **IsPrivateUse** или **IsPrivateUseArea**
F900 - FAFF | **IsCJKCompatibilityIdeographs**
FB00 - FB4F | **IsAlphabeticPresentationForms** 
FB50 - FDFF | **IsArabicPresentationForms-A** 
FE00 - FE0F | **IsVariationSelectors** 
FE20 - FE2F | **IsCombiningHalfMarks** 
FE30 - FE4F | **IsCJKCompatibilityForms** 
FE50 - FE6F | **IsSmallFormVariants**
FE70 - FEFF | **IsArabicPresentationForms-B** 
FF00 - FFEF | **IsHalfwidthandFullwidthForms** 
FFF0 - FFFF | **IsSpecials**
 
<a name="character-class-subtraction"></a>
## <a name="character-class-subtraction-basegroup---excludedgroup"></a>Вычитание класса символов: [базовая_группа - [исключенная_группа]]

Класс знаков определяет набор знаков. Результатом вычитания класса знаков является набор знаков, полученный в результате исключения одного класса знаков из другого класса знаков. 

Выражение вычитания класса знаков имеет следующий вид:

__[__*base*_*group*-__[__*excluded*_*group*__]]--

Квадратные скобки (**[]**) и дефис (-) являются обязательными. *base_group* представляет собой положительную или отрицательную группу символов. Компонент *excluded_group* — это другая положительная или отрицательная группа символов или другое выражение вычитания класса символов (то есть можно осуществлять вложение выражений вычитания класса символов). 

Например, предположим, что имеется базовая группа, состоящая из диапазона знаков от "а" до "z". Чтобы задать набор знаков, состоящий из базовой группы за исключением знака "m", используйте команду `[a-z-[m]]`. Чтобы задать набор знаков, состоящий из базовой группы за исключением знаков "d", "j", и "p", используйте команду `[a-z-[djp]]`. Чтобы определить набор знаков, состоящий из базовой группы за исключением диапазона знаков от "m" до "p", используйте команду `[a-z-[m-p]]`. 

Рассмотрим вложенное выражение вычитания классов знаков `[a-z-[d-w-[m-o]]]`. Вычисление выражения начинается из самого внутреннего диапазона знаков. Сначала диапазон знаков от "m" до "o" вычитается из диапазона знаков от "d" до "w", в результате чего остается набор знаков от "d" до "i" и от "p" до "w". Затем этот набор вычитается из диапазона знаков от "a" до "z", вследствие чего получается набор знаков `[abcmnoxyz]`.

При вычитании класса знаков можно использовать любой класс знаков. Чтобы задать набор знаков, состоящий из всех знаков Юникода от "\u0000" до "\uFFFF", за исключением пробела (**\s**), знаков препинания в общей категории (**\p{P}**), знаков в именованном блоке **IsGreek** (**\p{IsGreek}**) и управляющего символа Юникода NEXT LINE (\x85), используйте `[\u0000-\uFFFF-[\s\p{P}\p{IsGreek}\x85]]`.

Выберите классы знаков для выражения вычитания класса знаков, которое возвратит полезные результаты. Избегайте выражений, в результате которых возвращается пустой набор знаков, который ничему не соответствует, и выражений, эквивалентных исходной базовой группе. Например, пустой набор является результатом выражения `[\p{IsBasicLatin}-[\x00-\x7F]]`, которое вычитает все символы диапазона **IsBasicLatin** из общей категории **IsBasicLatin**. Аналогично, результатом выражения `[a-z-[0-9]]` является исходная базовая группа. Это происходит из-за того, что базовая группа, которая является диапазоном букв от "a" до "z", не содержит знаков исключаемой группы, которая является диапазоном десятичных цифр от "0" до "9". 

В следующем примере определяется регулярное выражение `^[0-9-[2468]]+$`, которое выделяет ноль и нечетные цифры во входной строке. Возможные интерпретации регулярного выражения показаны в следующей таблице.

Элемент | Описание
------- | ----------- 
`^` | Соответствие должно обнаруживаться в начале входной строки.
`[0-9-[2468]]+` | Соответствует одному или нескольким вхождениям любого символа от 0 до 9, за исключением 2, 4, 6 и 8. Другими словами, выделяется одно или несколько вхождений нуля или нечетной цифры.
`$` | Совпадение должно заканчиваться в конце входной строки.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "123", "13579753", "3557798", "335599901" };
      string pattern = @"^[0-9-[2468]]+$";

      foreach (string input in inputs)
      {
         Match match = Regex.Match(input, pattern);
         if (match.Success) 
            Console.WriteLine(match.Value);
      }      
   }
}
// The example displays the following output:
//       13579753
//       335599901
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "123", "13579753", "3557798", "335599901" }
      Dim pattern As String = "^[0-9-[2468]]+$"

      For Each input As String In inputs
         Dim match As Match = Regex.Match(input, pattern)
         If match.Success Then Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       13579753
'       335599901
```

## <a name="see-also"></a>См. также

[Параметры регулярных выражений](options.md)
