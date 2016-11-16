---
title: "Привязки в регулярных выражениях"
description: "Привязки в регулярных выражениях"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 96dff1be-3005-4ba5-af1b-323182a26085
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: b2162a90d5cb6f3472a9d323a3e46e137c9edf82

---

# <a name="anchors-in-regular-expressions"></a>Привязки в регулярных выражениях

Привязки (или атомарные утверждения нулевой ширины) указывают положение в строке, где должно быть найдено соответствие. При использовании привязки в выражении поиска обработчик регулярных выражений не проходит по строке и не потребляет символы; он ищет соответствия только в заданном местоположении. Например, **^** указывает, что соответствие должно начаться в начале строки. Таким образом, регулярное выражение `^http:` находит соответствие для http, только если этот элемент находится в начале строки. В таблице ниже перечислены привязки, поддерживаемые регулярными выражениями в .NET. 

Привязка | Описание
------ | ----------- 
**^** | Соответствие должно находиться в начале строки.
**$** | Соответствие должно находиться в конце строки или до символа \n в конце строки.
**\A** | Соответствие должно находиться только в начале строки (многострочность не поддерживается).
**\Z** | Соответствие должно находиться в конце строки или до символа \n в конце строки.
**\z** | Соответствие должно находиться исключительно в конце строки. 
**\G** | Соответствие должно начинаться в точке, где завершилось предыдущее соответствие.
**\b** | Соответствие должно находиться на границе слова.
**\B** | Соответствие не должно находиться на границе слова.
 
## <a name="start-of-string-or-line-"></a>Начало строки: ^

Привязка **^** указывает, что следующий шаблон должен начинаться на месте первого символа строки. Если используется символ **^** с параметром [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline) (см. статью [Параметры регулярных выражений](options.md)), соответствие должно находиться в начале каждой строки.

В следующем примере используется привязка **^** в регулярном выражении, которое извлекает сведения о годах, в течение которых существовали некоторые профессиональные бейсбольные команды. В примере вызывается две перегрузки метода `Regex.Matches`. 

* При вызове перегрузки [Matches(String, String)](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String)) удается найти только первую подстроку во входной строке, которая соответствует шаблону регулярного выражения. 

* Вызов перегрузки [Matches(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) с параметром options, имеющим значение [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline), позволяет найти все пять подстрок.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      int startPos = 0, endPos = 70;
      string input = "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957\n" +
                     "Chicago Cubs, National League, 1903-present\n" + 
                     "Detroit Tigers, American League, 1901-present\n" + 
                     "New York Giants, National League, 1885-1957\n" +  
                     "Washington Senators, American League, 1901-1960\n";   
      string pattern = @"^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+";
      Match match;

      if (input.Substring(startPos, endPos).Contains(",")) {
         match = Regex.Match(input, pattern);
         while (match.Success) {
            Console.Write("The {0} played in the {1} in", 
                              match.Groups[1].Value, match.Groups[4].Value);
            foreach (Capture capture in match.Groups[5].Captures)
               Console.Write(capture.Value);

            Console.WriteLine(".");
            startPos = match.Index + match.Length;
            endPos = startPos + 70 <= input.Length ? 70 : input.Length - startPos;
            if (! input.Substring(startPos, endPos).Contains(",")) break;
            match = match.NextMatch();
         }
         Console.WriteLine();
      }

      if (input.Substring(startPos, endPos).Contains(",")) {
         match = Regex.Match(input, pattern, RegexOptions.Multiline);
         while (match.Success) {
            Console.Write("The {0} played in the {1} in", 
                              match.Groups[1].Value, match.Groups[4].Value);
            foreach (Capture capture in match.Groups[5].Captures)
               Console.Write(capture.Value);

            Console.WriteLine(".");
            startPos = match.Index + match.Length;
            endPos = startPos + 70 <= input.Length ? 70 : input.Length - startPos;
            if (! input.Substring(startPos, endPos).Contains(",")) break;
            match = match.NextMatch();
         }
         Console.WriteLine();
      }
   }
}
// The example displays the following output:
//    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
//    
//    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
//    The Chicago Cubs played in the National League in 1903-present.
//    The Detroit Tigers played in the American League in 1901-present.
//    The New York Giants played in the National League in 1885-1957.
//    The Washington Senators played in the American League in 1901-1960.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim startPos As Integer = 0
      Dim endPos As Integer = 70
      Dim input As String = "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957" + vbCrLf + _
                            "Chicago Cubs, National League, 1903-present" + vbCrLf + _
                            "Detroit Tigers, American League, 1901-present" + vbCrLf + _
                            "New York Giants, National League, 1885-1957" + vbCrLf + _
                            "Washington Senators, American League, 1901-1960" + vbCrLf  

      Dim pattern As String = "^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+"
      Dim match As Match

      ' Provide minimal validation in the event the input is invalid.
      If input.Substring(startPos, endPos).Contains(",") Then
         match = Regex.Match(input, pattern)
         Do While match.Success
            Console.Write("The {0} played in the {1} in", _
                              match.Groups(1).Value, match.Groups(4).Value)
            For Each capture As Capture In match.Groups(5).Captures
               Console.Write(capture.Value)
            Next
            Console.WriteLine(".")
            startPos = match.Index + match.Length 
            endPos = CInt(IIf(startPos + 70 <= input.Length, 70, input.Length - startPos))
            If Not input.Substring(startPos, endPos).Contains(",") Then Exit Do
            match = match.NextMatch()            
         Loop
         Console.WriteLine()                               
      End If      

      startPos = 0
      endPos = 70
      If input.Substring(startPos, endPos).Contains(",") Then
         match = Regex.Match(input, pattern, RegexOptions.Multiline)
         Do While match.Success
            Console.Write("The {0} played in the {1} in", _
                              match.Groups(1).Value, match.Groups(4).Value)
            For Each capture As Capture In match.Groups(5).Captures
               Console.Write(capture.Value)
            Next
            Console.WriteLine(".")
            startPos = match.Index + match.Length 
            endPos = CInt(IIf(startPos + 70 <= input.Length, 70, input.Length - startPos))
            If Not input.Substring(startPos, endPos).Contains(",") Then Exit Do
            match = match.NextMatch()            
         Loop
         Console.WriteLine()                               
      End If      


'       For Each match As Match in Regex.Matches(input, pattern, RegexOptions.Multiline)
'          Console.Write("The {0} played in the {1} in", _
'                            match.Groups(1).Value, match.Groups(4).Value)
'          For Each capture As Capture In match.Groups(5).Captures
'             Console.Write(capture.Value)
'          Next
'          Console.WriteLine(".")
'       Next
   End Sub
End Module
' The example displays the following output:
'    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
'    
'    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
'    The Chicago Cubs played in the National League in 1903-present.
'    The Detroit Tigers played in the American League in 1901-present.
'    The New York Giants played in the National League in 1885-1957.
'    The Washington Senators played in the American League in 1901-1960.
```

Шаблон регулярного выражения `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+` определяется, как показано в следующей таблице.

Шаблон | Описание
------- | ----------- 
`^` | Соответствие должно начинаться в начале входной строки (или в начале строки, если метод вызывается с параметром `RegexOptions.Multiline`).
`((\w+(\s?)){2,}` | Сопоставление одного или нескольких символов слов, за которыми следует ноль или один пробел, два раза. Это первая группа записи. Это выражение также определяет вторую и третью группу записи: вторая состоит из записанного слова, а третья — из записанных пробелов. 
`,\s` | Сопоставление запятой, за которой следует пробел.
`(\w+\s\w+)` | Сопоставление одного или более символов слов, за которыми следует пробел и один или более символов слов. Это четвертая группа записи.
`,` | Сопоставление запятой.
`\s\d{4}` | Сопоставление пробела, за которым следуют четыре десятичные цифры.
`(-(\d{4}`&#124;`present))?` |  Сопоставление нулевого или единичного вхождения дефиса, за которым следуют четыре десятичные цифры или строка present. Это шестая группа записи. Она также включает седьмую группу записи. 
`,?` | Сопоставление нулевого или единичного вхождения запятой.
`(\s\d{4}(-(\d{4}`&#124;`present))?,?)+` | Сопоставление одного или нескольких вхождений следующих символов: пробела, четырех десятичных цифр, нулевого или единичного вхождения дефиса, за которым следуют четыре десятичные цифры или строка present, нуля или одной запятой. Это пятая группа записи.
 
## <a name="end-of-string-or-line-"></a>Конец строки: $

Привязка **$** указывает, что предыдущий шаблон должен находиться в конце входной строки или перед символом \n в конце входной строки. 

Если используется символ **$** с параметром [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline), соответствие также может иметь место в конце строки. Обратите внимание, что **$** соответствует **\n**, но не соответствует **\r\n** (комбинации символов возврата и перевода строки каретки или CR/LF). Чтобы сопоставить комбинацию символов CR/LF, включите **\r?$** в шаблон регулярного выражения.

В следующем примере показано добавление привязки **$** к шаблону регулярного выражения, используемого в примере из подраздела "Начало строки". При использовании с исходной входной строкой, которая включает пять строк текста, методу [Regex.Matches(String, String)](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String)) не удается найти соответствие, так как конец первой строки не соответствует шаблону **$**. Если исходная входная строка разбивается на массив строк, методу `Regex.Matches(String, String)` удается найти соответствие для каждой из пяти строк. Если метод [Regex.Matches(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) вызывается с параметром *options*, для которого задано значение `RegexOptions.Multiline`, соответствия не найдены, потому что шаблон регулярного выражения не учитывает элемент возврата каретки (\u+000D). Однако изменение шаблона регулярного выражения (замена **$** последовательностью **\r?$**) приведет к тому, что вызов метода `Regex.Matches(String, String, RegexOptions)` с параметром *options*, равным `RegexOptions.Multiline`, позволит снова найти пять соответствий.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      int startPos = 0, endPos = 70;
      string cr = Environment.NewLine;
      string input = "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957" + cr +
                     "Chicago Cubs, National League, 1903-present" + cr + 
                     "Detroit Tigers, American League, 1901-present" + cr + 
                     "New York Giants, National League, 1885-1957" + cr +  
                     "Washington Senators, American League, 1901-1960" + cr;   
      Match match;

      string basePattern = @"^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+";
      string pattern = basePattern + "$";
      Console.WriteLine("Attempting to match the entire input string:");
      if (input.Substring(startPos, endPos).Contains(",")) {
         match = Regex.Match(input, pattern);
         while (match.Success) {
            Console.Write("The {0} played in the {1} in", 
                              match.Groups[1].Value, match.Groups[4].Value);
            foreach (Capture capture in match.Groups[5].Captures)
               Console.Write(capture.Value);

            Console.WriteLine(".");
            startPos = match.Index + match.Length;
            endPos = startPos + 70 <= input.Length ? 70 : input.Length - startPos;
            if (! input.Substring(startPos, endPos).Contains(",")) break;
            match = match.NextMatch();
         }
         Console.WriteLine();
      }

      string[] teams = input.Split(new String[] { cr }, StringSplitOptions.RemoveEmptyEntries);
      Console.WriteLine("Attempting to match each element in a string array:");
      foreach (string team in teams)
      {
         if (team.Length > 70) continue;

         match = Regex.Match(team, pattern);
         if (match.Success)
         {
            Console.Write("The {0} played in the {1} in", 
                          match.Groups[1].Value, match.Groups[4].Value);
            foreach (Capture capture in match.Groups[5].Captures)
               Console.Write(capture.Value);
            Console.WriteLine(".");
         }
      }
      Console.WriteLine();

      startPos = 0;
      endPos = 70;
      Console.WriteLine("Attempting to match each line of an input string with '$':");
      if (input.Substring(startPos, endPos).Contains(",")) {
         match = Regex.Match(input, pattern, RegexOptions.Multiline);
         while (match.Success) {
            Console.Write("The {0} played in the {1} in", 
                              match.Groups[1].Value, match.Groups[4].Value);
            foreach (Capture capture in match.Groups[5].Captures)
               Console.Write(capture.Value);

            Console.WriteLine(".");
            startPos = match.Index + match.Length;
            endPos = startPos + 70 <= input.Length ? 70 : input.Length - startPos;
            if (! input.Substring(startPos, endPos).Contains(",")) break;
            match = match.NextMatch();
         }
         Console.WriteLine();
      }

      startPos = 0;
      endPos = 70;
      pattern = basePattern + "\r?$"; 
      Console.WriteLine(@"Attempting to match each line of an input string with '\r?$':");
      if (input.Substring(startPos, endPos).Contains(",")) {
         match = Regex.Match(input, pattern, RegexOptions.Multiline);
         while (match.Success) {
            Console.Write("The {0} played in the {1} in", 
                              match.Groups[1].Value, match.Groups[4].Value);
            foreach (Capture capture in match.Groups[5].Captures)
               Console.Write(capture.Value);

            Console.WriteLine(".");
            startPos = match.Index + match.Length;
            endPos = startPos + 70 <= input.Length ? 70 : input.Length - startPos;
            if (! input.Substring(startPos, endPos).Contains(",")) break;
            match = match.NextMatch();
         }
         Console.WriteLine();
      }
   }
}
// The example displays the following output:
//    Attempting to match the entire input string:
//    
//    Attempting to match each element in a string array:
//    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
//    The Chicago Cubs played in the National League in 1903-present.
//    The Detroit Tigers played in the American League in 1901-present.
//    The New York Giants played in the National League in 1885-1957.
//    The Washington Senators played in the American League in 1901-1960.
//    
//    Attempting to match each line of an input string with '$':
//    
//    Attempting to match each line of an input string with '\r+$':
//    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
//    The Chicago Cubs played in the National League in 1903-present.
//    The Detroit Tigers played in the American League in 1901-present.
//    The New York Giants played in the National League in 1885-1957.
//    The Washington Senators played in the American League in 1901-1960.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim startPos As Integer = 0
      Dim endPos As Integer = 70
      Dim input As String = "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957" + vbCrLf + _
                            "Chicago Cubs, National League, 1903-present" + vbCrLf + _
                            "Detroit Tigers, American League, 1901-present" + vbCrLf + _
                            "New York Giants, National League, 1885-1957" + vbCrLf + _
                            "Washington Senators, American League, 1901-1960" + vbCrLf  

      Dim basePattern As String = "^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+"
      Dim match As Match

      Dim pattern As String = basePattern + "$"
      Console.WriteLine("Attempting to match the entire input string:")
      ' Provide minimal validation in the event the input is invalid.
      If input.Substring(startPos, endPos).Contains(",") Then
         match = Regex.Match(input, pattern)
         Do While match.Success
            Console.Write("The {0} played in the {1} in", _
                              match.Groups(1).Value, match.Groups(4).Value)
            For Each capture As Capture In match.Groups(5).Captures
               Console.Write(capture.Value)
            Next
            Console.WriteLine(".")
            startPos = match.Index + match.Length 
            endPos = CInt(IIf(startPos + 70 <= input.Length, 70, input.Length - startPos))
            If Not input.Substring(startPos, endPos).Contains(",") Then Exit Do
            match = match.NextMatch()            
         Loop
         Console.WriteLine()                               
      End If      

      Dim teams() As String = input.Split(New String() { vbCrLf }, StringSplitOptions.RemoveEmptyEntries)
      Console.WriteLine("Attempting to match each element in a string array:")
      For Each team As String In teams
         If team.Length > 70 Then Continue For
         match = Regex.Match(team, pattern)
         If match.Success Then
            Console.Write("The {0} played in the {1} in", _
                           match.Groups(1).Value, match.Groups(4).Value)
            For Each capture As Capture In match.Groups(5).Captures
               Console.Write(capture.Value)
            Next
            Console.WriteLine(".")
         End If
      Next
      Console.WriteLine()

      startPos = 0
      endPos = 70
      Console.WriteLine("Attempting to match each line of an input string with '$':")
      ' Provide minimal validation in the event the input is invalid.
      If input.Substring(startPos, endPos).Contains(",") Then
         match = Regex.Match(input, pattern, RegexOptions.Multiline)
         Do While match.Success
            Console.Write("The {0} played in the {1} in", _
                              match.Groups(1).Value, match.Groups(4).Value)
            For Each capture As Capture In match.Groups(5).Captures
               Console.Write(capture.Value)
            Next
            Console.WriteLine(".")
            startPos = match.Index + match.Length 
            endPos = CInt(IIf(startPos + 70 <= input.Length, 70, input.Length - startPos))
            If Not input.Substring(startPos, endPos).Contains(",") Then Exit Do
            match = match.NextMatch()            
         Loop
         Console.WriteLine()                               
      End If      


      startPos = 0
      endPos = 70
      pattern = basePattern + "\r?$" 
      Console.WriteLine("Attempting to match each line of an input string with '\r?$':")
      ' Provide minimal validation in the event the input is invalid.
      If input.Substring(startPos, endPos).Contains(",") Then
         match = Regex.Match(input, pattern, RegexOptions.Multiline)
         Do While match.Success
            Console.Write("The {0} played in the {1} in", _
                              match.Groups(1).Value, match.Groups(4).Value)
            For Each capture As Capture In match.Groups(5).Captures
               Console.Write(capture.Value)
            Next
            Console.WriteLine(".")
            startPos = match.Index + match.Length 
            endPos = CInt(IIf(startPos + 70 <= input.Length, 70, input.Length - startPos))
            If Not input.Substring(startPos, endPos).Contains(",") Then Exit Do
            match = match.NextMatch()            
         Loop
         Console.WriteLine()                               
      End If      
   End Sub
End Module
' The example displays the following output:
'    Attempting to match the entire input string:
'    
'    Attempting to match each element in a string array:
'    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
'    The Chicago Cubs played in the National League in 1903-present.
'    The Detroit Tigers played in the American League in 1901-present.
'    The New York Giants played in the National League in 1885-1957.
'    The Washington Senators played in the American League in 1901-1960.
'    
'    Attempting to match each line of an input string with '$':
'    
'    Attempting to match each line of an input string with '\r+$':
'    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
'    The Chicago Cubs played in the National League in 1903-present.
'    The Detroit Tigers played in the American League in 1901-present.
'    The New York Giants played in the National League in 1885-1957.
'    The Washington Senators played in the American League in 1901-1960.
```

## <a name="start-of-string-only-a"></a>Только начало строки: \A

Привязка **\A** указывает, что соответствие должно находиться в начале входной строки. Она идентична привязке **^** с той разницей, что **\A** игнорирует параметр [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline). Следовательно, можно найти соответствие только для начала первой строки в многострочной входной строке.

Следующий пример похож на примеры для привязок **^** и **$**. В нем привязка **\A** используется в регулярном выражении, которое извлекает сведения о годах, в течение которых существовали некоторые профессиональные бейсбольные команды. Входная строка включает пять строк. При вызове метода [Regex.Matches(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) удается найти только первую подстроку во входной строке, которая соответствует шаблону регулярного выражения. Как показано в примере, параметр `Multiline` не оказывает никакого влияния.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      int startPos = 0, endPos = 70;
      string input = "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957\n" +
                     "Chicago Cubs, National League, 1903-present\n" + 
                     "Detroit Tigers, American League, 1901-present\n" + 
                     "New York Giants, National League, 1885-1957\n" +  
                     "Washington Senators, American League, 1901-1960\n";   

      string pattern = @"\A((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+";
      Match match;

      if (input.Substring(startPos, endPos).Contains(",")) {
         match = Regex.Match(input, pattern, RegexOptions.Multiline);
         while (match.Success) {
            Console.Write("The {0} played in the {1} in", 
                              match.Groups[1].Value, match.Groups[4].Value);
            foreach (Capture capture in match.Groups[5].Captures)
               Console.Write(capture.Value);

            Console.WriteLine(".");
            startPos = match.Index + match.Length;
            endPos = startPos + 70 <= input.Length ? 70 : input.Length - startPos;
            if (! input.Substring(startPos, endPos).Contains(",")) break;
            match = match.NextMatch();
         }
         Console.WriteLine();
      }
   }
}
// The example displays the following output:
//    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim startPos As Integer = 0
      Dim endPos As Integer = 70
      Dim input As String = "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957" + vbCrLf + _
                            "Chicago Cubs, National League, 1903-present" + vbCrLf + _
                            "Detroit Tigers, American League, 1901-present" + vbCrLf + _
                            "New York Giants, National League, 1885-1957" + vbCrLf + _
                            "Washington Senators, American League, 1901-1960" + vbCrLf  

      Dim pattern As String = "\A((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+"
      Dim match As Match

      ' Provide minimal validation in the event the input is invalid.
      If input.Substring(startPos, endPos).Contains(",") Then
         match = Regex.Match(input, pattern, RegexOptions.Multiline)
         Do While match.Success
            Console.Write("The {0} played in the {1} in", _
                              match.Groups(1).Value, match.Groups(4).Value)
            For Each capture As Capture In match.Groups(5).Captures
               Console.Write(capture.Value)
            Next
            Console.WriteLine(".")
            startPos = match.Index + match.Length 
            endPos = CInt(IIf(startPos + 70 <= input.Length, 70, input.Length - startPos))
            If Not input.Substring(startPos, endPos).Contains(",") Then Exit Do
            match = match.NextMatch()            
         Loop
         Console.WriteLine()                               
      End If      
   End Sub   
End Module
' The example displays the following output:
'    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
```

## <a name="end-of-string-or-before-ending-newline-z"></a>Конец строки или до конца символа новой строки: \Z

Привязка **\Z** указывает, что соответствие должно находиться в конце входной строки или перед символом **\n** в конце входной строки. Она идентична привязке **$** с той разницей, что **\Z** игнорирует параметр [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline). Таким образом, в многострочной строке она может соответствовать только концу последней строки или последней строке до символа **\n**.

Обратите внимание, что **\Z** соответствует **\n**, но не соответствует **\r\n** (комбинации символов CR/LF). Для нахождения соответствия CR/LF включите **\r?\Z** в шаблон регулярного выражения.

В следующем примере используется привязка **\Z** в регулярном выражении, которая похожа на использованную в примере из раздела "Начало строки" и которая извлекает информацию о годах, в течение которых существовали некоторые профессиональные бейсбольные команды. Часть выражения `\r?\Z` в регулярном выражении `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\Z` соответствует концу строки, а также соответствует строке, которая заканчивается на **\n** или **\r\n**. В результате каждый элемент в массиве соответствует шаблону регулярного выражения.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957",  
                          "Chicago Cubs, National League, 1903-present" + Environment.NewLine, 
                          "Detroit Tigers, American League, 1901-present" + Regex.Unescape(@"\n"), 
                          "New York Giants, National League, 1885-1957", 
                          "Washington Senators, American League, 1901-1960" + Environment.NewLine}; 
      string pattern = @"^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\Z";

      foreach (string input in inputs)
      {
         if (input.Length > 70 || ! input.Contains(",")) continue;

         Console.WriteLine(Regex.Escape(input));
         Match match = Regex.Match(input, pattern);
         if (match.Success)
            Console.WriteLine("   Match succeeded.");
         else
            Console.WriteLine("   Match failed.");
      }   
   }
}
// The example displays the following output:
//    Brooklyn\ Dodgers,\ National\ League,\ 1911,\ 1912,\ 1932-1957
//       Match succeeded.
//    Chicago\ Cubs,\ National\ League,\ 1903-present\r\n
//       Match succeeded.
//    Detroit\ Tigers,\ American\ League,\ 1901-present\n
//       Match succeeded.
//    New\ York\ Giants,\ National\ League,\ 1885-1957
//       Match succeeded.
//    Washington\ Senators,\ American\ League,\ 1901-1960\r\n
//       Match succeeded.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957",  _
                            "Chicago Cubs, National League, 1903-present" + vbCrLf, _
                            "Detroit Tigers, American League, 1901-present" + vbLf, _
                            "New York Giants, National League, 1885-1957", _
                            "Washington Senators, American League, 1901-1960" + vbCrLf }  
      Dim pattern As String = "^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\Z"

      For Each input As String In inputs
         If input.Length > 70 Or Not input.Contains(",") Then Continue For

         Console.WriteLine(Regex.Escape(input))
         Dim match As Match = Regex.Match(input, pattern)
         If match.Success Then
            Console.WriteLine("   Match succeeded.")
         Else
            Console.WriteLine("   Match failed.")
         End If
      Next   
   End Sub
End Module
' The example displays the following output:
'    Brooklyn\ Dodgers,\ National\ League,\ 1911,\ 1912,\ 1932-1957
'       Match succeeded.
'    Chicago\ Cubs,\ National\ League,\ 1903-present\r\n
'       Match succeeded.
'    Detroit\ Tigers,\ American\ League,\ 1901-present\n
'       Match succeeded.
'    New\ York\ Giants,\ National\ League,\ 1885-1957
'       Match succeeded.
'    Washington\ Senators,\ American\ League,\ 1901-1960\r\n
'       Match succeeded.
```

## <a name="end-of-string-only-z"></a>Только начало строки: \z

Привязка **\z** указывает, что соответствие должно находиться в конце входной строки. Как и языковой элемент **$**, **\z** игнорирует параметр [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline). В отличие от языкового элемента **\Z** **\z** не сопоставляет символ **\n** в конце строки. Таким образом, соответствие может находиться только в последней строке входной строки.

В следующем примере используется привязка **\z** в регулярном выражении, которая похожа на использованную в примере из предыдущего раздела с той разницей, что она извлекает информацию о годах, в течение которых существовали некоторые профессиональные бейсбольные команды. В примере предпринимается попытка сопоставить каждый из пяти элементов в массиве строк шаблону регулярного выражения `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\z`. Две строки оканчиваются символом возврата каретки и перевода строки, одна заканчивается символом перевода строки, и еще две — ни символом возврата каретки, ни символом перевода строки. Как показывают выходные данные, шаблону соответствуют только строки без символа возврата каретки и перевода строки. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957", 
                          "Chicago Cubs, National League, 1903-present" + Environment.NewLine,
                          "Detroit Tigers, American League, 1901-present\\r",
                          "New York Giants, National League, 1885-1957",
                          "Washington Senators, American League, 1901-1960" + Environment.NewLine };  
      string pattern = @"^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\z";

      foreach (string input in inputs)
      {
         if (input.Length > 70 || ! input.Contains(",")) continue;

         Console.WriteLine(Regex.Escape(input));
         Match match = Regex.Match(input, pattern);
         if (match.Success)
            Console.WriteLine("   Match succeeded.");
         else
            Console.WriteLine("   Match failed.");
      }   
   }
}
// The example displays the following output:
//    Brooklyn\ Dodgers,\ National\ League,\ 1911,\ 1912,\ 1932-1957
//       Match succeeded.
//    Chicago\ Cubs,\ National\ League,\ 1903-present\r\n
//       Match failed.
//    Detroit\ Tigers,\ American\ League,\ 1901-present\n
//       Match failed.
//    New\ York\ Giants,\ National\ League,\ 1885-1957
//       Match succeeded.
//    Washington\ Senators,\ American\ League,\ 1901-1960\r\n
//       Match failed.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957",  _
                            "Chicago Cubs, National League, 1903-present" + vbCrLf, _
                            "Detroit Tigers, American League, 1901-present" + vbLf, _
                            "New York Giants, National League, 1885-1957", _
                            "Washington Senators, American League, 1901-1960" + vbCrLf }  
      Dim pattern As String = "^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\z"

      For Each input As String In inputs
         If input.Length > 70 Or Not input.Contains(",") Then Continue For

         Console.WriteLine(Regex.Escape(input))
         Dim match As Match = Regex.Match(input, pattern)
         If match.Success Then
            Console.WriteLine("   Match succeeded.")
         Else
            Console.WriteLine("   Match failed.")
         End If
      Next   
   End Sub
End Module
' The example displays the following output:
'    Brooklyn\ Dodgers,\ National\ League,\ 1911,\ 1912,\ 1932-1957
'       Match succeeded.
'    Chicago\ Cubs,\ National\ League,\ 1903-present\r\n
'       Match failed.
'    Detroit\ Tigers,\ American\ League,\ 1901-present\n
'       Match failed.
'    New\ York\ Giants,\ National\ League,\ 1885-1957
'       Match succeeded.
'    Washington\ Senators,\ American\ League,\ 1901-1960\r\n
'       Match failed.
```

## <a name="contiguous-matches-g"></a>Непрерывные совпадения: \G

Привязка **\G** указывает, что соответствие должно находиться в точке окончания предыдущего соответствия. При использовании этой привязки с методом [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) или [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch) гарантируется непрерывность всех совпадений. 

В следующем примере регулярное выражение используется для извлечения имен видов грызунов из строки с разделителями запятыми. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "capybara,squirrel,chipmunk,porcupine,gopher," + 
                     "beaver,groundhog,hamster,guinea pig,gerbil," + 
                     "chinchilla,prairie dog,mouse,rat";
      string pattern = @"\G(\w+\s?\w*),?";
      Match match = Regex.Match(input, pattern);
      while (match.Success) 
      {
         Console.WriteLine(match.Groups[1].Value);
         match = match.NextMatch();
      } 
   }
}
// The example displays the following output:
//       capybara
//       squirrel
//       chipmunk
//       porcupine
//       gopher
//       beaver
//       groundhog
//       hamster
//       guinea pig
//       gerbil
//       chinchilla
//       prairie dog
//       mouse
//       rat
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "capybara,squirrel,chipmunk,porcupine,gopher," + _
                            "beaver,groundhog,hamster,guinea pig,gerbil," + _
                            "chinchilla,prairie dog,mouse,rat"
      Dim pattern As String = "\G(\w+\s?\w*),?"
      Dim match As Match = Regex.Match(input, pattern)
      Do While match.Success
         Console.WriteLine(match.Groups(1).Value)
         match = match.NextMatch()
      Loop 
   End Sub
End Module
' The example displays the following output:
'       capybara
'       squirrel
'       chipmunk
'       porcupine
'       gopher
'       beaver
'       groundhog
'       hamster
'       guinea pig
'       gerbil
'       chinchilla
'       prairie dog
'       mouse
'       rat
```

Возможные интерпретации регулярного выражения `\G(\w+\s?\w*),?` показаны в следующей таблице.

Шаблон | Описание
------- | ----------- 
`\G` | Начать сопоставление там, где закончилось последнее соответствие.
`\w+` | Совпадение с одним или несколькими символами слова.
`\s?` | Совпадение с нулем или одним пробелом.
`\w*` | Совпадение с нулем или большим числом буквенных символов.
`(\w+\s?\w*)` | Сопоставление одного или более символов слов, за которыми ноль или один пробел, а затем ноль или более символов слов. Это первая группа записи.
`,?` | Сопоставление нулевому или единичному вхождению литерального символа запятой.
 
## <a name="word-boundary-b"></a>Граница слова: \b

Привязка **\b** указывает, что соответствие должно находиться на границе между словообразующим символом (языковым элементом **\w**) и несловообразующим символом (языковым элементом **\W**). Символы слов — это буквенно-цифровые символы и подчеркивания; несловесные символы — это все остальные символы. (Дополнительные сведения см. в статье [Классы символов в регулярных выражениях](classes.md).) Соответствие может также находиться на границе слова в начале или конце строки.

Привязку **\b** часто используют, чтобы убедиться, что часть выражения соответствует всему слову, а не просто окончанию или началу слова. Регулярное выражение `\bare\w*\b` в следующем примере демонстрируется использование этой привязки. Она соответствует любому слову, которое начинается с подстроки are. Выходные данные в этом примере также показывают, что **\b** соответствует началу и концу входной строки. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "area bare arena mare";
      string pattern = @"\bare\w*\b";
      Console.WriteLine("Words that begin with 'are':");
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("'{0}' found at position {1}",
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       Words that begin with 'are':
//       'area' found at position 0
//       'arena' found at position 10
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "area bare arena mare"
      Dim pattern As String = "\bare\w*\b"
      Console.WriteLine("Words that begin with 'are':")
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("'{0}' found at position {1}", _
                           match.Value, match.Index)
      Next
   End Sub
End Module
' The example displays the following output:
'       Words that begin with 'are':
'       'area' found at position 0
'       'arena' found at position 10
```

Возможные интерпретации шаблона регулярного выражения показаны в следующей таблице.

Шаблон | Описание
------- | ----------- 
`\b` | Совпадение должно начинаться на границе слова.
`are` | Совпадение с подстрокой are.
`\w*` | Совпадение с нулем или большим числом буквенных символов.
`\b` | Совпадение должно заканчиваться на границе слова.
 
## <a name="nonword-boundary-b"></a>Не на границе слова: \B

Привязка **\B** указывает, что соответствие не должно находиться на границе слова. Это противоположность привязки **\b**.

В следующем примере привязка **\B** используется для обнаружения вхождений в слове подстроки qu. Шаблон регулярного выражения `\Bqu\w+` соответствует подстроке, которая начинается с qu, которое не находится в начале слова и продолжается до конца слова.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "equity queen equip acquaint quiet";
      string pattern = @"\Bqu\w+";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("'{0}' found at position {1}", 
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       'quity' found at position 1
//       'quip' found at position 14
//       'quaint' found at position 21
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "equity queen equip acquaint quiet"
      Dim pattern As String = "\Bqu\w+"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("'{0}' found at position {1}", _
                           match.Value, match.Index)
      Next
   End Sub
End Module
' The example displays the following output:
'       'quity' found at position 1
'       'quip' found at position 14
'       'quaint' found at position 21
```

Возможные интерпретации шаблона регулярного выражения показаны в следующей таблице.

Шаблон | Описание
------- | ----------- 
`\B` | Совпадение не должно начинаться на границе слова.
`qu` | Совпадение с подстрокой qu.
`\w+` | Совпадение с одним или несколькими символами слова.
 
## <a name="see-also"></a>См. также

[Элементы языка регулярных выражений — краткий справочник](quick-ref.md)

[Параметры регулярных выражений](options.md)
 



<!--HONumber=Nov16_HO1-->


