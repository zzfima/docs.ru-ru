---
title: "Подстановки в регулярных выражениях"
description: "Подстановки в регулярных выражениях"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 0fded615-1021-4468-a644-b491814305c6
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 3e02d18d6566c67c7fff7003671f340f97b0dfce

---

# <a name="substitutions-in-regular-expressions"></a>Подстановки в регулярных выражениях

Подстановки — это языковые элементы, которые распознаются только в шаблонах замены. Они используют шаблон регулярного выражения для определения всего текста или его части, предназначенной для замены совпадающего текста во входной строке. Шаблон замены может включать одну или несколько подстановок вместе с литеральными символами. Для перегруженных версий метода [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions)) с параметром *replacement* и для метода [Match.Result](xref:System.Text.RegularExpressions.Match.Result(System.String)) предоставляются шаблоны замены. Эти методы заменяют совпавший шаблон шаблоном, определенным параметром *replacement*.

Платформа .NET определяет элементы подстановки, перечисленные в следующей таблице.

Подстановка | Описание
------------ | ----------- 
**$**_number_ | Включает в строку замены последнюю подстроку, соответствующую захватываемой группе, которая идентифицируется как *number*, где *number* — десятичное значение. Дополнительные сведения см. в разделе [Подстановка нумерованной группы](#substituting-a-numbered-group).
**${**_name_**}** | Включает в строку замены последнюю подстроку, соответствующую именованной группе, обозначаемой как **(?<**_name_**>)**. Дополнительные сведения см. в разделе [Подстановка именованной группы](#substituting-a-named-group).
**$$** | Включает один литерал "$" в строку замены. Дополнительные сведения см. в разделе [Подстановка символа "$"](#substituting-a--character).
**$&** | Включает копию всего соответствия в строку замены. Дополнительные сведения см. в разделе [Подстановка всего соответствия](#substituting-the-entire-match).
**$`** | Включает весь текст входной строки до соответствия в строку замены. Дополнительные сведения см. в разделе [Подстановка текста до соответствия](#substituting-the-text-before-the-match).
**$'** | Включает весь текст входной строки после соответствия в строку замены. Дополнительные сведения см. в разделе [Подстановка текста после соответствия](#substituting-the-text-after-the-match). 
**$+** | Включает последнюю записанную группу в строку замены. Дополнительные сведения см. в разделе [Подстановка последней захваченной группы](#substituting-the-last-captured-group).
**$_** | Включает всю входную строку в строку замены. Дополнительные сведения см. в разделе [Подстановка всей входной строки](#substituting-the-entire-input-string).
 
## <a name="substitution-elements-and-replacement-patterns"></a>Элементы подстановки и шаблоны замены

В шаблонах замены распознается только одна специальная конструкция: подстановки. Ни один из остальных элементов языка регулярных выражений, включая escape-символы и точку (**.**), которая соответствует любому знаку, не поддерживается. Аналогичным образом, подставляемые элементы языка распознаются только в шаблонах замены и никогда не являются допустимыми в шаблоны регулярных выражений. 

Единственный знак, который может встречаться в шаблоне регулярного выражения либо в подстановке, — это знак **$**, хотя он в разных случаях имеет разное значение. В шаблоне регулярного выражения **$** является привязкой, совпадающей с концом строки. В шаблоне замены **$** указывает начало подстановки. 

> [!NOTE]
> Для получения возможностей, подобных шаблону замены в регулярном выражении, используйте обратную ссылку. Дополнительные сведения об обратных ссылках см. в разделе [Конструкции обратных ссылок](backreference.md).
 
## <a name="substituting-a-numbered-group"></a>Подстановка нумерованной группы

Языковой элемент **$**_number_ включает последнюю подстроку, сопоставленную по захватываемой группе number в строке замены, где *number* — это индекс захватываемой группы. Например, шаблон замены `$1` указывает, что совпадающая подстрока будет заменена первой группой записи. Дополнительные сведения о нумерованных захватываемых группах см. в разделе [Конструкции группировки в регулярных выражениях](grouping.md).

Все цифры, указанные после **$**, интерпретируются как относящиеся к группе number. Если это не соответствует вашим намерениям, можно вместо этого подставить именованную группу. Например, можно использовать строку замены **${1}1** вместо **$11**, чтобы определить строку замены как значение первой захваченной группы вместе с номером "1". Дополнительные сведения см. в разделе [Подстановка именованной группы](#substituting-a-named-group). 

Захватываемые группы, которым явно не назначены имена с помощью синтаксиса **(?<**_name-**>)**, нумеруются слева направо, начиная с единицы. Именованные группы также нумеруются слева направо, начиная с номера, превышающего индекс последней неименованной группы. Например, в регулярном выражении `(\w)(?<digit>\d)` индекс именованной группы `digit` — 2.

Если *number* не соответствует допустимой захватываемой группе, определенной в шаблоне регулярного выражения, **$**_number_ интерпретируется как последовательность литеральных символов, используемая для замены каждого соответствия.

В следующем примере подстановка **$**_number_ используется для удаления символа валюты из десятичного значения. Она удаляет символы денежной единицы, найденные в начале или конце денежного значения, и распознает два наиболее распространенных десятичных разделителя ("." и ","). 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\p{Sc}*(\s?\d+[.,]?\d*)\p{Sc}*";
      string replacement = "$1";
      string input = "$16.32 12.19 £16.29 €18.29  €18,29";
      string result = Regex.Replace(input, pattern, replacement);
      Console.WriteLine(result);
   }
}
// The example displays the following output:
//       16.32 12.19 16.29 18.29  18,29
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\p{Sc}*(\s?\d+[.,]?\d*)\p{Sc}*"
      Dim replacement As String = "$1"
      Dim input As String = "$16.32 12.19 £16.29 €18.29  €18,29"
      Dim result As String = Regex.Replace(input, pattern, replacement)
      Console.WriteLine(result)
   End Sub
End Module
' The example displays the following output:
'       16.32 12.19 16.29 18.29  18,29
```

Шаблон регулярного выражения `\p{Sc}*(\s?\d+[.,]?\d*)\p{Sc}*` определяется, как показано в следующей таблице.

Шаблон | Описание
------- | -----------
`\p{Sc}*` | Совпадение с нулем или более символами денежной единицы.
`\s?` | Совпадение с нулем или одним символом пробела.
`\d+` | Совпадение с одной или несколькими десятичными цифрами.
`[.,]?` | Совпадение с нулем или одной точкой либо запятой.
`\d*` | Соответствует нулю или нескольким десятичным числам.
`(\s?\d+[.,]?\d*)` | Совпадение с пробелом, за которым следует одна или несколько десятичных цифр, после которых идет ноль или одна точка либо запятая, а за ними — ноль или более десятичных цифр. Это первая группа записи. Так как шаблон замены имеет вид `$1`, вызов метода [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions)) заменяет всю совпадающую подстроку данной захватываемой группой. 
 
## <a name="substituting-a-named-group"></a>Подстановка именованной группы

Языковой элемент **${**_name_**}** замещает последнюю подстроку, сопоставленную по захватываемой группе *name*, где *name* — это имя захватываемой группы, определенной в языковом элементе **(?<**_name_**>)**. Дополнительные сведения об именованных захватываемых группах см. в разделе [Конструкции группировки в регулярных выражениях](grouping.md).

Если *name* не соответствует допустимой именованной захватываемой группе, определенной в регулярном выражении, и состоит из цифр, то **${**_name_**}** интерпретируется как нумерованная группа. 

Если *name* не соответствует ни допустимой именованной захватываемой группе, ни допустимой нумерованной захватываемой группе, определенной в шаблоне регулярного выражения, **${**_name_**}** интерпретируется как последовательность литеральных символов, используемая для замены каждого соответствия.

В следующем примере подстановка **${**_name_**}** используется для удаления символа валюты из десятичного значения. Она удаляет символы денежной единицы, найденные в начале или конце денежного значения, и распознает два наиболее распространенных десятичных разделителя ("." и ",").

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\p{Sc}*(?<amount>\s?\d+[.,]?\d*)\p{Sc}*";
      string replacement = "${amount}";
      string input = "$16.32 12.19 £16.29 €18.29  €18,29";
      string result = Regex.Replace(input, pattern, replacement);
      Console.WriteLine(result);
   }
}
// The example displays the following output:
//       16.32 12.19 16.29 18.29  18,29
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\p{Sc}*(?<amount>\s?\d+[.,]?\d*)\p{Sc}*"
      Dim replacement As String = "${amount}"
      Dim input As String = "$16.32 12.19 £16.29 €18.29  €18,29"
      Dim result As String = Regex.Replace(input, pattern, replacement)
      Console.WriteLine(result)
   End Sub
End Module
' The example displays the following output:
'       16.32 12.19 16.29 18.29  18,29
```

Шаблон регулярного выражения `\p{Sc}*(?<amount>\s?\d[.,]?\d*)\p{Sc}*` определяется, как показано в следующей таблице. 

Шаблон | Описание
------- | -----------
`\p{Sc}*` | Совпадение с нулем или более символами денежной единицы.
`\s?` | Совпадение с нулем или одним символом пробела.
`\d+` | Совпадение с одной или несколькими десятичными цифрами.
`[.,]?` | Совпадение с нулем или одной точкой либо запятой.
`\d*` | Соответствует нулю или нескольким десятичным числам.
`(?<amount>\s?\d[.,]?\d*)` | Совпадение с пробелом, за которым следует одна или несколько десятичных цифр, после которых идет ноль или одна точка либо запятая, а за ними — ноль или более десятичных цифр. Это захватываемая группа с именем amount. Так как шаблон замены имеет вид `${amount}`, вызов метода [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions)) заменяет всю совпадающую подстроку данной захватываемой группой. 
 
## <a name="substituting-a-character"></a>Подстановка символа "$"

Подстановка **$$** вставляет символ литерала "$"в строку замены. 

В следующем примере объект [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) используется для определения символа валюты для текущего языка и региональных параметров и его размещения в строке валюты. Затем он динамически создает как шаблон регулярного выражения, так и шаблон замены. Если пример выполняется на компьютере, где в качестве языка и региональных параметров задано значение «Английский — США» (en-US), будет создан шаблон регулярного выражения `\b(\d+)(\.(\d+))?` и шаблон замены `$$ $1$2`. Шаблон замены замещает совпавший текст символом валюты и пробелом после первой и второй записанной группы.

```csharp
using System;
using System.Globalization;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      // Define array of decimal values.
      string[] values= { "16.35", "19.72", "1234", "0.99"};
      // Determine whether currency precedes (True) or follows (False) number.
      bool precedes = NumberFormatInfo.CurrentInfo.CurrencyPositivePattern % 2 == 0;
      // Get decimal separator.
      string cSeparator = NumberFormatInfo.CurrentInfo.CurrencyDecimalSeparator;
      // Get currency symbol.
      string symbol = NumberFormatInfo.CurrentInfo.CurrencySymbol;
      // If symbol is a "$", add an extra "$".
      if (symbol == "$") symbol = "$$";

      // Define regular expression pattern and replacement string.
      string pattern = @"\b(\d+)(" + cSeparator + @"(\d+))?"; 
      string replacement = "$1$2";
      replacement = precedes ? symbol + " " + replacement : replacement + " " + symbol;
      foreach (string value in values)
         Console.WriteLine("{0} --> {1}", value, Regex.Replace(value, pattern, replacement));
   }
}
// The example displays the following output:
//       16.35 --> $ 16.35
//       19.72 --> $ 19.72
//       1234 --> $ 1234
//       0.99 --> $ 0.99
```

```vb
Imports System.Globalization
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      ' Define array of decimal values.
      Dim values() As String = { "16.35", "19.72", "1234", "0.99"}
      ' Determine whether currency precedes (True) or follows (False) number.
      Dim precedes As Boolean = (NumberFormatInfo.CurrentInfo.CurrencyPositivePattern Mod 2 = 0)
      ' Get decimal separator.
      Dim cSeparator As String = NumberFormatInfo.CurrentInfo.CurrencyDecimalSeparator
      ' Get currency symbol.
      Dim symbol As String = NumberFormatInfo.CurrentInfo.CurrencySymbol
      ' If symbol is a "$", add an extra "$".
      If symbol = "$" Then symbol = "$$"

      ' Define regular expression pattern and replacement string.
      Dim pattern As String = "\b(\d+)(" + cSeparator + "(\d+))?" 
      Dim replacement As String = "$1$2"
      replacement = If(precedes, symbol + " " + replacement, replacement + " " + symbol)
      For Each value In values
         Console.WriteLine("{0} --> {1}", value, Regex.Replace(value, pattern, replacement))
      Next
   End Sub
End Module
' The example displays the following output:
'       16.35 --> $ 16.35
'       19.72 --> $ 19.72
'       1234 --> $ 1234
'       0.99 --> $ 0.99
```

Шаблон регулярного выражения `\b(\d+)(\.(\d+))?` определяется, как показано в следующей таблице.

Шаблон | Описание
------- | -----------
`\b` | Начало соответствия в начале границы слова.
`(\d+)` | Совпадение с одной или несколькими десятичными цифрами. Это первая группа записи.
`\.` | Совпадение с точкой (десятичным разделителем).
`(\d+)` | Совпадение с одной или несколькими десятичными цифрами. Это третья группа записи.
`(\.(\d+))?` | Совпадение с нулем или одним вхождением точки, за которой следует одна или несколько десятичных цифр. Это вторая группа записи.
 
## <a name="substituting-the-entire-match"></a>Подстановка всего совпадения

Подстановка **$&** включает все соответствие в строку замены. Часто она используется для добавления подстроки в начало или в конец совпадающей строки. Например, шаблон замены `($&)` добавляет скобки в начало и в конец каждого соответствия. Если нет соответствия, подстановка **$&** не оказывает влияния.

В следующем примере используется подстановка **$&** для добавления кавычек в начало и конец названий книг, хранящихся в строковом массиве.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"^(\w+\s?)+$";
      string[] titles = { "A Tale of Two Cities", 
                          "The Hound of the Baskervilles", 
                          "The Protestant Ethic and the Spirit of Capitalism", 
                          "The Origin of Species" };
      string replacement = "\"$&\"";
      foreach (string title in titles)
         Console.WriteLine(Regex.Replace(title, pattern, replacement));
   }
}
// The example displays the following output:
//       "A Tale of Two Cities"
//       "The Hound of the Baskervilles"
//       "The Protestant Ethic and the Spirit of Capitalism"
//       "The Origin of Species"
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^(\w+\s?)+$"
      Dim titles() As String = { "A Tale of Two Cities", _
                                 "The Hound of the Baskervilles", _
                                 "The Protestant Ethic and the Spirit of Capitalism", _
                                 "The Origin of Species" }
      Dim replacement As String = """$&"""
      For Each title As String In titles
         Console.WriteLine(Regex.Replace(title, pattern, replacement))
      Next  
   End Sub
End Module
' The example displays the following output:
'       "A Tale of Two Cities"
'       "The Hound of the Baskervilles"
'       "The Protestant Ethic and the Spirit of Capitalism"
'       "The Origin of Species"
```

Шаблон регулярного выражения `^(\w+\s?)+$` определяется, как показано в следующей таблице.

Шаблон | Описание
------- | -----------
`^` | Начало соответствия в начале входной строки.
`(\w+\s?)+` | Выделяет один или несколько раз шаблон из одного или нескольких словообразующих символов, за которыми следует ноль или один символ пробела. 
`$` | Соответствует концу входной строки.

Шаблон замены `"$&"` добавляет литеральные кавычки в начало и в конец каждого соответствия.

## <a name="substituting-the-text-before-the-match"></a>Подстановка текста до соответствия

Подстановка **$`** substitution replaces the matched string with the entire input string before the match. That is, it duplicates the input string up to the match while removing the matched text. Any text that follows the matched text is unchanged in the result string. If there are multiple matches in an input string, the replacement text is derived from the original input string, rather than from the string in which text has been replaced by earlier matches. (The example provides an illustration.) If there is no match, the **$`** не оказывает никакого влияния.

В следующем примере шаблон регулярного выражения `\d+` используется для сопоставления последовательности из одной или нескольких цифр десятичного числа во входной строке. Строка замены **$`** заменяет эти цифры текстом, который предшествует совпадению. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "aa1bb2cc3dd4ee5";
      string pattern = @"\d+";
      string substitution = "$`";
      Console.WriteLine("Matches:");
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);

      Console.WriteLine("Input string:  {0}", input);
      Console.WriteLine("Output string: " + 
                        Regex.Replace(input, pattern, substitution));
   }
}
// The example displays the following output:
//    Matches:
//       1 at position 2
//       2 at position 5
//       3 at position 8
//       4 at position 11
//       5 at position 14
//    Input string:  aa1bb2cc3dd4ee5
//    Output string: aaaabbaa1bbccaa1bb2ccddaa1bb2cc3ddeeaa1bb2cc3dd4ee
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "aa1bb2cc3dd4ee5"
      Dim pattern As String = "\d+"
      Dim substitution As String = "$`"
      Console.WriteLine("Matches:")
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
      Console.WriteLine("Input string:  {0}", input)
      Console.WriteLine("Output string: " + _
                        Regex.Replace(input, pattern, substitution))
   End Sub
End Module
' The example displays the following output:
'    Matches:
'       1 at position 2
'       2 at position 5
'       3 at position 8
'       4 at position 11
'       5 at position 14
'    Input string:  aa1bb2cc3dd4ee5
'    Output string: aaaabbaa1bbccaa1bb2ccddaa1bb2cc3ddeeaa1bb2cc3dd4ee
```

В этом примере входная строка `"aa1bb2cc3dd4ee5"` содержит пять совпадений. В следующей таблице показано, как подстановка $ вызывает замену обработчиком регулярных выражений каждого соответствия во входной строке. Вставленный текст отображается в столбце результатов строкового типа полужирным шрифтом.

Соответствие | Положение | Строка до соответствия | Результирующая строка
----- | -------- | ------------------- | -------------
1 | 2 | aa | aa**aa**bb2cc3dd4ee5
2 | 5 | aa1bb | aaaabb**aa1bb**cc3dd4ee5
3 | 8 | aa1bb2cc | aaaabbaa1bbcc**aa1bb2cc**dd4ee5
4 | 11 | aa1bb2cc3dd | aaaabbaa1bbccaa1bb2ccdd**aa1bb2cc3dd**ee5
5 | 14 | aa1bb2cc3dd4ee | aaaabbaa1bbccaa1bb2ccddaa1bb2cc3ddee **aa1bb2cc3dd4ee**
 
## <a name="substituting-the-text-after-the-match"></a>Подстановка текста после соответствия

Подстановка **$'** заменяет совпадающую строку всей входной строкой после соответствия. То есть входная строка после соответствия дублируется с удалением совпадающего текста. Любой текст, который предшествует совпадающему тексту, не изменяется в результирующей строке. Если нет соответствия, подстановка **$'** не оказывает влияния.

В следующем примере шаблон регулярного выражения `\d+` используется для сопоставления последовательности из одной или нескольких цифр десятичного числа во входной строке. Строка замены **$'** заменяет эти цифры текстом, который следует за соответствием. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "aa1bb2cc3dd4ee5";
      string pattern = @"\d+";
      string substitution = "$'";
      Console.WriteLine("Matches:");
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);
      Console.WriteLine("Input string:  {0}", input);
      Console.WriteLine("Output string: " + 
                        Regex.Replace(input, pattern, substitution));
   }
}
// The example displays the following output:
//    Matches:
//       1 at position 2
//       2 at position 5
//       3 at position 8
//       4 at position 11
//       5 at position 14
//    Input string:  aa1bb2cc3dd4ee5
//    Output string: aaaabbaa1bbccaa1bb2ccddaa1bb2cc3ddeeaa1bb2cc3dd4ee
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "aa1bb2cc3dd4ee5"
      Dim pattern As String = "\d+"
      Dim substitution As String = "$'"
      Console.WriteLine("Matches:")
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
      Console.WriteLine("Input string:  {0}", input)
      Console.WriteLine("Output string: " + _
                        Regex.Replace(input, pattern, substitution))
   End Sub
End Module
' The example displays the following output:
'    Matches:
'       1 at position 2
'       2 at position 5
'       3 at position 8
'       4 at position 11
'       5 at position 14
'    Input string:  aa1bb2cc3dd4ee5
'    Output string: aaaabbaa1bbccaa1bb2ccddaa1bb2cc3ddeeaa1bb2cc3dd4ee
```

В этом примере входная строка `"aa1bb2cc3dd4ee5"` содержит пять совпадений. В следующей таблице показано, как подстановка **$'** вызывает замену обработчиком регулярных выражений каждого соответствия во входной строке. Вставленный текст отображается в столбце результатов строкового типа полужирным шрифтом.

Соответствие | Положение | Строка до соответствия | Результирующая строка
----- | -------- | ------------------- | -------------
1 | 2 | bb2cc3dd4ee5 | aa**bb2cc3dd4ee5**bb2cc3dd4ee5
2 | 5 | cc3dd4ee5 | aabb2cc3dd4ee5bb**cc3dd4ee5**cc3dd4ee5
3 | 8 | dd4ee5 | aabb2cc3dd4ee5bbcc3dd4ee5cc**dd4ee5**dd4ee5
4 | 11 | ee5 | aabb2cc3dd4ee5bbcc3dd4ee5ccdd4ee5dd**ee5**ee5
5 | 14 | [String.Empty](xref:System.String.Empty) | aabb2cc3dd4ee5bbcc3dd4ee5ccdd4ee5ddee5ee
 
## <a name="substituting-the-last-captured-group"></a>Подстановка последней захваченной группы

Подстановка **$+** заменяет совпадающую строку всей последней захваченной группой. Если захваченные группы отсутствуют или значение последней захваченной группы равно [String.Empty](xref:System.String.Empty), подстановка **$+** не оказывает влияния.

В следующем примере в строке определяются повторяющиеся слова и используется подстановка **$+** для их замены одним вхождением слова. Параметр [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase) позволяет убедиться, что слова, отличающиеся регистром, но идентичные во всем остальном, считаются дубликатами.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\w+)\s\1\b";
      string substitution = "$+";
      string input = "The the dog jumped over the fence fence.";
      Console.WriteLine(Regex.Replace(input, pattern, substitution, 
                        RegexOptions.IgnoreCase));
   }
}
// The example displays the following output:
//      The dog jumped over the fence.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\w+)\s\1\b"
      Dim substitution As String = "$+"
      Dim input As String = "The the dog jumped over the fence fence."
      Console.WriteLine(Regex.Replace(input, pattern, substitution, _
                                      RegexOptions.IgnoreCase))
   End Sub
End Module
' The example displays the following output:
'      The dog jumped over the fence.
```

Шаблон регулярного выражения `\b(\w+)\s\1\b` определяется, как показано в следующей таблице.

Шаблон | Описание
------- | ----------- 
`\b` | Совпадение должно начинаться на границе слова.
`(\w+)` | Совпадение с одним или несколькими символами слова. Это первая группа записи.
`\s` | Соответствует пробелу.
`\1` | Соответствует первой группе записи.
`\b` | Совпадение должно заканчиваться на границе слова.
 
## <a name="substituting-the-entire-input-string"></a>Подстановка всей входной строки

Подстановка **$_** заменяет совпадающую строку всей входной строкой. То есть совпадающий текст удаляется и заменяется всей строкой, включая совпадающий текст.

В следующем примере сопоставляется одна или несколько цифр десятичного числа во входной строке. При этом используется подстановка **$_** для их замены входной строкой.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "ABC123DEF456";
      string pattern = @"\d+";
      string substitution = "$_";
      Console.WriteLine("Original string:          {0}", input);
      Console.WriteLine("String with substitution: {0}", 
                        Regex.Replace(input, pattern, substitution));      
   }
}
// The example displays the following output:
//       Original string:          ABC123DEF456
//       String with substitution: ABCABC123DEF456DEFABC123DEF456
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "ABC123DEF456"
      Dim pattern As String = "\d+"
      Dim substitution As String = "$_"
      Console.WriteLine("Original string:          {0}", input)
      Console.WriteLine("String with substitution: {0}", _
                        Regex.Replace(input, pattern, substitution))      
   End Sub
End Module
' The example displays the following output:
'       Original string:          ABC123DEF456
'       String with substitution: ABCABC123DEF456DEFABC123DEF456
```

В этом примере входная строка `"ABC123DEF456"` содержит два совпадения. В следующей таблице показано, как подстановка **$_** вызывает замену обработчиком регулярных выражений каждого соответствия во входной строке. Вставленный текст отображается в столбце результатов строкового типа полужирным шрифтом.

Соответствие | Положение | Строка до соответствия | Результирующая строка
----- | -------- | ------------------- | -------------
1 | 3 | 123 | ABC**ABC123DEF456**DEF456
2 | 5 | 456 | ABCABC123DEF456DEF**ABC123DEF456**
 
## <a name="see-also"></a>См. также

[Элементы языка регулярных выражений — краткий справочник](quick-ref.md)




<!--HONumber=Nov16_HO1-->


