---
title: "Другие конструкции в регулярных выражениях"
description: "Другие конструкции в регулярных выражениях"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 478901dc-db6c-4d90-9d3b-f5cfdca2cbf5
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 477332f4009790727686aa3d91e35509e3766903

---

# <a name="miscellaneous-constructs-in-regular-expressions"></a>Другие конструкции в регулярных выражениях


Регулярные выражения в .NET поддерживают три различные языковые конструкции. Одна позволяет включать или отключать определенные параметры соответствия в середине шаблона регулярного выражения. Оставшиеся две позволяют включать комментарии в регулярное выражение.

## <a name="inline-options"></a>Встроенные параметры

С помощью синтаксиса можно задать или отключить конкретные параметры сопоставления шаблонов для части регулярного выражения.

```
(?imnsx-imnsx)
```

Параметры, которые нужно включить, указываются после вопросительного знака, а параметры, которые требуется отключить, перечисляются после знака минус. В таблице ниже представлено описание каждого из этих параметров. Дополнительные сведения о каждом параметре см. в статье [Параметры регулярных выражений](options.md).

Параметр | Описание
------ | ----------- 
**i** | Сопоставление без учета регистра.
**m** | Многострочный режим.
**n** | Только явные захваты. (Скобки не действуют как захватываемые группы.)
**s** | Однострочный режим.
**x** | Игнорировать не преобразованные в escape-последовательность пробелы и разрешить комментарии в режиме x. 
 
Любое изменение параметров регулярных выражений, заданное конструкцией **(? imnsx-imnsx)**, остается в силе до конца содержащей группы.

> [!NOTE]
> Конструкция группировки **(?imnsx-imnsx**:_subexpression_**)** предоставляет для части выражения одинаковые функциональные возможности. Дополнительные сведения см. в статье [Конструкции группировки в регулярных выражениях](grouping.md).
 
В следующем примере параметры **i**, **n** и **x** используются для отключения чувствительности к регистру и включения явных захватов, а также для пропуска пробелов в шаблоне в середине регулярного выражения. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern; 
      string input = "double dare double Double a Drooling dog The Dreaded Deep";

      pattern = @"\b(D\w+)\s(d\w+)\b";
      // Match pattern using default options.
      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine(match.Value);
         if (match.Groups.Count > 1)
            for (int ctr = 1; ctr < match.Groups.Count; ctr++) 
               Console.WriteLine("   Group {0}: {1}", ctr, match.Groups[ctr].Value);
      }
      Console.WriteLine();

      // Change regular expression pattern to include options.
      pattern = @"\b(D\w+)(?ixn) \s (d\w+) \b";
      // Match new pattern with options. 
      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine(match.Value);
         if (match.Groups.Count > 1)
            for (int ctr = 1; ctr < match.Groups.Count; ctr++) 
               Console.WriteLine("   Group {0}: '{1}'", ctr, match.Groups[ctr].Value);
      }
   }
}
// The example displays the following output:
//       Drooling dog
//          Group 1: Drooling
//          Group 2: dog
//       
//       Drooling dog
//          Group 1: 'Drooling'
//       Dreaded Deep
//          Group 1: 'Dreaded'
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String 
      Dim input As String = "double dare double Double a Drooling dog The Dreaded Deep"

      pattern = "\b(D\w+)\s(d\w+)\b"
      ' Match pattern using default options.
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
         If match.Groups.Count > 1 Then
            For ctr As Integer = 1 To match.Groups.Count - 1 
               Console.WriteLine("   Group {0}: {1}", ctr, match.Groups(ctr).Value)
            Next
         End If
      Next
      Console.WriteLine()

      ' Change regular expression pattern to include options.
      pattern = "\b(D\w+)(?ixn) \s (d\w+) \b"
      ' Match new pattern with options. 
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
         If match.Groups.Count > 1 Then
            For ctr As Integer = 1 To match.Groups.Count - 1 
               Console.WriteLine("   Group {0}: '{1}'", ctr, match.Groups(ctr).Value)
            Next
         End If
      Next
   End Sub
End Module
' The example displays the following output:
'       Drooling dog
'          Group 1: Drooling
'          Group 2: dog
'       
'       Drooling dog
'          Group 1: 'Drooling'
'       Dreaded Deep
'          Group 1: 'Dreaded'
```

В примере определяются два регулярных выражения. Первое `\b(D\w+)\s(d\w+)\b` выделяет два последовательных слова, начинающихся с прописной буквы "D" и строчной буквы "d". Во втором регулярном выражении `\b(D\w+)(?ixn) \s (d\w+) \b` используются встроенные параметры для изменения этого шаблона, как описано в следующей таблице. Сравнение результатов подтверждает влияние конструкции `(?ixn)`.

Шаблон | Описание
------- | ----------- 
`\b` | Начало на границе слова.
`(D\w+)` | Совпадение с прописной буквой "D", за которой следует один или более словообразующих символов. Это первая захватываемая группа.
`(?ixn)` | С этого момента рекомендуется делать сравнения без учета регистра, делать только явные захваты и игнорировать пробелы в шаблоне регулярного выражения.
`\s` | Соответствует пробелу.
`(d\w+)` | Совпадение с прописной или строчной буквой "d", за которой следует один или более словообразующих символов. Эта группа не захватывается, так как был включен параметр (явный захват).
`\b` | Соответствует границе слова.
 
## <a name="inline-comment"></a>Встроенный комментарий

Конструкция **(?#** _comment_**)** позволяет включать встроенные комментарии в регулярное выражение. Обработчик регулярных выражений не использует какую-либо часть комментария при сопоставлении шаблонов, хотя комментарий включается в строку, которая возвращается методом [Regex.ToString](xref:System.Text.RegularExpressions.Regex.Unescape(System.String)). Примечание заканчивается первой закрывающей скобкой.

В следующем примере повторяется первый шаблон регулярного выражения из примера, указанного в предыдущем разделе. В регулярное выражение добавляются два встроенных комментария, чтобы указать, учитывается ли в сравнении регистр. Шаблон регулярного выражения `\b((?# case-sensitive comparison)D\w+)\s((?#case-insensitive comparison)d\w+)\b` определяется, как показано ниже.

Шаблон | Описание
------- | ----------- 
`\b` | Начало на границе слова.
`(?# case-sensitive comparison)` | Комментарий. Не влияет на алгоритм соответствия шаблону.
`(D\w+)` | Совпадение с прописной буквой "D", за которой следует один или более словообразующих символов. Это первая группа записи.
`\s` | Соответствует пробелу.
`(?ixn)` |С этого момента рекомендуется делать сравнения с учетом регистра, делать только явные захваты и игнорировать пробелы в шаблоне регулярного выражения.
`(?#case-insensitive comparison)` | Комментарий. Не влияет на алгоритм соответствия шаблону. 
`(d\w+)` | Совпадение с прописной или строчной буквой "d", за которой следует один или более словообразующих символов. Это вторая захватываемая группа.
`\b` | Соответствует границе слова.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b((?# case sensitive comparison)D\w+)\s(?ixn)((?#case insensitive comparison)d\w+)\b";
      Regex rgx = new Regex(pattern);
      string input = "double dare double Double a Drooling dog The Dreaded Deep";

      Console.WriteLine("Pattern: " + pattern.ToString());
      // Match pattern using default options.
      foreach (Match match in rgx.Matches(input))
      {
         Console.WriteLine(match.Value);
         if (match.Groups.Count > 1)
         {
            for (int ctr = 1; ctr <match.Groups.Count; ctr++) 
               Console.WriteLine("   Group {0}: {1}", ctr, match.Groups[ctr].Value);
         }
      }
   }
}
// The example displays the following output:
//    Pattern: \b((?# case sensitive comparison)D\w+)\s(?ixn)((?#case insensitive comp
//    arison)d\w+)\b
//    Drooling dog
//       Group 1: Drooling
//    Dreaded Deep
//       Group 1: Dreaded
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b((?# case sensitive comparison)D\w+)\s(?ixn)((?#case insensitive comparison)d\w+)\b"
      Dim rgx As New Regex(pattern)
      Dim input As String = "double dare double Double a Drooling dog The Dreaded Deep"

      Console.WriteLine("Pattern: " + pattern.ToString())
      ' Match pattern using default options.
      For Each match As Match In rgx.Matches(input)
         Console.WriteLine(match.Value)
         If match.Groups.Count > 1 Then
            For ctr As Integer = 1 To match.Groups.Count - 1 
               Console.WriteLine("   Group {0}: {1}", ctr, match.Groups(ctr).Value)
            Next
         End If
      Next
   End Sub
End Module
' The example displays the following output:
'    Pattern: \b((?# case sensitive comparison)D\w+)\s(?ixn)((?#case insensitive comp
'    arison)d\w+)\b
'    Drooling dog
'       Group 1: Drooling
'    Dreaded Deep
'       Group 1: Dreaded
```

## <a name="endofline-comment"></a>Комментарий в конце строки

Символ решетки (**#**) помечает комментарий режима x, который начинается символом #, не преобразованным в escape-последовательность, в конце шаблона регулярного выражения, и продолжается до конца строки. Для использования этой конструкции следует включить параметр **x** (во встроенных параметрах) или передать значение [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace) в параметр *option* при создании объекта [Regex](xref:System.Text.RegularExpressions.Regex) или вызове статического метода [Regex](xref:System.Text.RegularExpressions.Regex). 

В следующем примере показана конструкция комментария в конце строки. Она определяет, является ли строка составного форматирования строкой, которая содержит по крайней мере один элемент формата. В следующей таблице описаны конструкции в шаблоне регулярного выражения. 

`\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item`. 

Шаблон | Описание
------- | ----------- 
`\{` | Совпадение с открывающей скобкой.
`\d+` | Совпадение с одной или несколькими десятичными цифрами.
`(,-*\d+)*` | Совпадение с нулем или одним вхождением точки, за которой следует необязательный знак минус, за которым идет одна или несколько десятичных цифр.
`(\:\w{1,4}?)*` | Совпадение с нулем или одним вхождением двоеточия, за которым следует от одного до четырех символов пробела (но как можно меньшее количество).
`(?#case insensitive comparison)` | Встроенный комментарий. Не влияет на алгоритм соответствия шаблону.
`\}` | Совпадение с закрывающей фигурной скобкой.
`(?x)` | Включить параметр для пропуска пробелов, чтобы распознавался комментарий в конце строки.
`# Looks for a composite format item.` | Комментарий в конце строки.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item.";
      string input = "{0,-3:F}";
      Console.WriteLine("'{0}':", input);
      if (Regex.IsMatch(input, pattern))
         Console.WriteLine("   contains a composite format item.");
      else
         Console.WriteLine("   does not contain a composite format item.");
   }
}
// The example displays the following output:
//       '{0,-3:F}':
//          contains a composite format item.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item."
      Dim input As String = "{0,-3:F}"
      Console.WriteLine("'{0}':", input)
      If Regex.IsMatch(input, pattern) Then
         Console.WriteLine("   contains a composite format item.")
      Else
         Console.WriteLine("   does not contain a composite format item.")
      End If
   End Sub
End Module
' The example displays the following output:
'       '{0,-3:F}':
'          contains a composite format item.
```

Обратите внимание, что вместо указания конструкции `(?x)` в регулярном выражении комментарий также можно распознать путем вызова метода [Regex.IsMatch(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) и передачи ему значения перечисления [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace).

## <a name="see-also"></a>См. также

[Элементы языка регулярных выражений — краткий справочник](quick-ref.md)




<!--HONumber=Nov16_HO1-->


