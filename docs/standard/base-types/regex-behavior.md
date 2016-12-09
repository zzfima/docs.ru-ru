---
title: "Подробные сведения о поведении регулярных выражений"
description: "Подробные сведения о поведении регулярных выражений"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 6f11047f-45a4-4caf-a259-18abe08cc0d2
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: fa0513a5b450742995bd86fca495ba9904e7361b

---

# <a name="details-of-regular-expression-behavior"></a>Подробные сведения о поведении регулярных выражений


Обработчик регулярных выражений .NET выполняет поиск с возвратом для регулярных выражений и является реализацией традиционной NFA-машины (недетерминированного конечного автомата), аналогично тем, которые используются в Perl, Python, Emacs и Tcl. Это отличает его от более быстрых, но и более ограниченных DFA-машин (детерминированный конечный автомат), предназначенных только для регулярных выражений и используемых в awk, egrep или lex. Это также отличает его от типовых, но более медленных POSIX NFA-машин. В следующем разделе представлено описание трех типов обработчиков регулярных выражений и объясняется причина реализации регулярных выражений в .NET с помощью обычной NFA-машины.

## <a name="benefits-of-the-nfa-engine"></a>Преимущества NFA-машины

Когда DFA-машины выполняют сопоставление шаблонов, порядок обработки определяется входной строкой. Машина начинает обработку с начала входной строки и продолжает последовательную обработку для определения соответствия следующего символа шаблону регулярного выражения. Их можно обнаружить как соответствия максимальной длины. Так как DFA-машины не проверяют один и тот же знак дважды, они не поддерживают поиск с возвратом. Но поскольку DFA-машина поддерживает только ограниченный режим работы, она не способна выполнять поиск соответствий по шаблону с обратными ссылками. Кроме того, она не создает явные выражения и не способна выделять части выражения.

В отличие от DFA-машин обычные NFA-машины выполняют поиск соответствий по шаблонам, и порядок обработки определяется шаблоном регулярных выражений. По мере обработки определенного элемента языка машина использует жадное сопоставление: она выполняет сопоставление как можно большей части входной строки. И кроме того, она сохраняет свое состояние после успешного поиска соответствия части выражения. Если поиск соответствия в конечном счете завершился с ошибкой, машина может вернуться в сохраненное состояние, поэтому она может попытаться найти дополнительные соответствия. Такой процесс оставления успешного соответствия части выражения, при котором последующие элементы языка также могут привести к соответствию, называется поиском с возвратом. NFA-машины используют поиск с возвратом, проверяя все возможные расширения регулярного выражения в определенном порядке и принимая первое соответствие. Поскольку обычная NFA-машина создает определенное расширение регулярного выражения для успешного сопоставления, она способна находить соответствия для частей выражений и обратных ссылок. Но так как обычная NFA-машина выполняет поиск с возвратом, она может анализировать одно и то же состояние несколько раз, если к нему ведут несколько разных путей. В результате в наихудшем случае работа может замедляться по экспоненте. Так как обычная NFA-машина принимает первое найденное соответствие, другие (возможно, более длинные) соответствия могут остаться необнаруженными.

POSIX NFA-машины похожи на обычные NFA-машины, за исключением того, что они продолжают поиск с возвратом до тех пор, пока не будет найдено наиболее длинное совпадение. В результате POSIX NFA-машина работает медленнее обычной NFA-машины, и при использовании POSIX NFA-машины, изменив порядок поиска с возвратом, невозможно задать предпочтение короткому совпадению вместо более длинного. 

Программисты предпочитают обычные NFA-машины, поскольку они превосходят по возможностям управления строковыми соответствиями обычные DFA-машины или POSIX NFA-машины. Несмотря на то, что в наихудшем случае быстродействие NFA-машин снижается, ими можно управлять так, что поиск соответствий будет проходить по линейному или полиномиальному времени. Добиться этого можно с помощью шаблонов, уменьшающих неоднозначности и ограничивающих количество возвратов. Другими словами, несмотря на то, что NFA-машины жертвуют производительностью в обмен на мощность и гибкость, в большинстве случаев они обеспечивают хорошую (или хотя бы приемлемую) производительность, если регулярное выражение грамотно написано и позволяет избежать ситуаций, при которых производительность поиска с возвратом снижается экспоненциально.

> [!NOTE]
> Сведения о том, как излишнее использование поиска с возвратом может повлиять на производительность и как избежать проблем, см. в разделе [Поиск с возвратом в регулярных выражениях](backtracking.md).
 
## <a name="net-framework-engine-capabilities"></a>Возможности обработчика .NET Framework

В обработчик регулярных выражений .NET были включены лучшие функции NFA-машины, а также полный набор структурных элементов, позволяющий программистам управлять процессом поиска с возвратом. Эти структуры можно использовать для ускорения поиска или для выбора предпочтительных расширений.

Ниже представлены другие возможности обработчика регулярных выражений .NET. 

### <a name="lazy-quantifiers"></a>Ленивые квантификаторы

Ленивые квантификаторы: **??**, __*?__, **+?**, **{**_n_**,**_m_**}?**. В первую очередь они указывают обработчику на необходимость ведения поиска минимального числа повторений. Обычные "жадные" квантификаторы, наоборот, пытаются сначала найти наибольшее число повторений. В следующем примере кода демонстрируется различие между двумя квантификаторами. Регулярное выражение соответствует предложению, оканчивающемуся на число, и захваченная группа должна извлечь это число. Регулярное выражение `.+(\d+)\.` содержит жадный квантификатор `.+`, под влиянием которого обработчик регулярных выражений захватывает только последнюю цифру числа. И наоборот, регулярное выражение `.+?(\d+)\.` содержит ленивый квантификатор `.+?`, под влиянием которого обработчик регулярных выражений захватывает все число.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string greedyPattern = @".+(\d+)\.";
      string lazyPattern = @".+?(\d+)\.";
      string input = "This sentence ends with the number 107325.";
      Match match;

      // Match using greedy quantifier .+.
      match = Regex.Match(input, greedyPattern);
      if (match.Success)
         Console.WriteLine("Number at end of sentence (greedy): {0}", 
                           match.Groups[1].Value);
      else
         Console.WriteLine("{0} finds no match.", greedyPattern);
       // Match using lazy quantifier .+?.
      match = Regex.Match(input, lazyPattern);
      if (match.Success)
         Console.WriteLine("Number at end of sentence (lazy): {0}", 
                           match.Groups[1].Value);
      else
         Console.WriteLine("{0} finds no match.", lazyPattern);
   }
}
// The example displays the following output:
//       Number at end of sentence (greedy): 5
//       Number at end of sentence (lazy): 107325
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim greedyPattern As String = ".+(\d+)\."
      Dim lazyPattern As String = ".+?(\d+)\."
      Dim input As String = "This sentence ends with the number 107325."
      Dim match As Match

      ' Match using greedy quantifier .+.
      match = Regex.Match(input, greedyPattern)
      If match.Success Then
         Console.WriteLine("Number at end of sentence (greedy): {0}", 
                           match.Groups(1).Value)
      Else
         Console.WriteLine("{0} finds no match.", greedyPattern)
      End If

      ' Match using lazy quantifier .+?.
      match = Regex.Match(input, lazyPattern)
      If match.Success Then
         Console.WriteLine("Number at end of sentence (lazy): {0}", 
                           match.Groups(1).Value)
      Else
         Console.WriteLine("{0} finds no match.", lazyPattern)
      End If
   End Sub
End Module
' The example displays the following output:
'       Number at end of sentence (greedy): 5
'       Number at end of sentence (lazy): 107325
```

Определение жадных и ленивых версий этого регулярного выражения представлено в следующей таблице.

Шаблон | Описание
------- | -----------
`.+` ("жадный" квантификатор) | Соответствие как минимум одному вхождению любого символа. Это дает обработчику регулярных выражений команду на сопоставление всей строки и выполнение поиска с возвратом, который требуется для сопоставления оставшейся части шаблона.
`.+?` ("ленивый" квантификатор) | Соответствие как минимум одному вхождению любого символа, но как можно меньшему количеству.
`(\d+)` | Соответствие как минимум одной цифре и назначение ее для первой захваченной группы.
`\.` | Сопоставляется точка.
 
Дополнительные сведения о "ленивых" квантификаторах см. в статье [Квантификаторы в регулярных выражениях](quantifiers.md).

### <a name="positive-lookahead"></a>Положительный поиск вперед

Положительный поиск: **(?**=_subexpression_**)**. Эта функция позволяет обработчику с поиском с возвратом возвращаться в начальное место в тексте после сопоставления части выражения. Эта функция полезна при осуществлении поиска с одной позиции с помощью нескольких шаблонов. Она также позволяет обработчику проверять существование части строки в конце соответствия, не включая при этом часть строки в сопоставленный текст. В следующем примере используется положительный поиск вперед для извлечения слов в предложении, после которых нет знаков препинания.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b[A-Z]+\b(?=\P{P})";
      string input = "If so, what comes next?";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       If
//       what
//       comes
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b[A-Z]+\b(?=\P{P})"
      Dim input As String = "If so, what comes next?"
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
         Console.WriteLine(match.Value)
      Next   
   End Sub
End Module
' The example displays the following output:
'       If
'       what
'       comes
```

Определение регулярного выражения `\b[A-Z]+\b(?=\P{P})` показано в таблице ниже.

Шаблон | Описание
------- | -----------
`\b` | Совпадение должно начинаться на границе слова.
`[A-Z]+` | Совпадение с любым символом один или более раз. Так как метод [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) вызывается с параметром [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase), сравнение не зависит от регистра символов. 
`\b` | Совпадение должно заканчиваться на границе слова.
`(?=\P{P})` | Поиск для определения, является ли следующий символ знаком препинания. Если не является, соответствие считается успешным.

Дополнительные сведения об утверждениях положительного поиска вперед см. в статье [Конструкции группировки в регулярных выражениях](grouping.md).

### <a name="negative-lookahead"></a>Отрицательный поиск вперед

Отрицательный поиск: **(?!**_subexpression_**)**. Сопоставление выражения выполняется только в том случае, когда не было обнаружено соответствия части выражения. Это существенно упрощает поиск, поскольку часто бывает проще описать выражения, не соответствующие правилу, чем само правило. Например, трудно написать выражение для поиска слов, которые не начинаются с "non". В следующем примере для их исключения используется отрицательный поиск.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(?!non)\w+\b";
      string input = "Nonsense is not always non-functional.";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       is
//       not
//       always
//       functional
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(?!non)\w+\b"
      Dim input As String = "Nonsense is not always non-functional."
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       is
'       not
'       always
'       functional
```

Шаблон регулярного выражения `\b(?!non)\w+\b` определяется, как показано в следующей таблице.

Шаблон | Описание
------- | -----------
`\b` | Совпадение должно начинаться на границе слова.
`(?!non)` | Поиск для определения, не начинается ли текущая строка с "non". Если начинается, соответствие считается неудачным.
`(\w+)` | Совпадение с одним или несколькими символами слова.
`\b` | Совпадение должно заканчиваться на границе слова.
 
Дополнительные сведения об утверждениях отрицательного поиска вперед см. в статье [Конструкции группировки в регулярных выражениях](grouping.md).

### <a name="conditional-evaluation"></a>Условная оценка

Условная оценка: **(?(**_expression_**)**_yes_&#124;_no_**)** and**(?(**_name_**)**_yes_&#124;_no_**)**, где *expression* — сопоставляемая часть выражения, *name* — имя захваченной группы, *yes* — сопоставляемая строка, если *expression* имеет соответствие или *name* является допустимой непустой захваченной группой, а *no* — сопоставляемая часть выражения, если *expression* не имеет соответствия или *name* не является допустимой непустой захваченной группой. Эта функция позволяет обработчику вести поиск с использованием нескольких альтернативных шаблонов в зависимости от результатов сопоставлений предыдущей части выражения или утверждения нулевой ширины. Это более действенный вид обратной ссылки, позволяющий, например, искать соответствия части выражения в зависимости от соответствия предыдущей части выражения. Регулярное выражение в следующем примере соответствует абзацам, предназначенным для общего и внутреннего использования. Абзацы, предназначенные только для внутреннего использования, начинаются с тега `<PRIVATE>`. Шаблон регулярного выражения `^(?<Pvt>\<PRIVATE\>\s)?(?(Pvt)((\w+\p{P}?\s)+)|((\w+\p{P}?\s)+))\r?$` использует условную оценку для назначения содержимого абзацев, предназначенных для общего и внутреннего использования, для отдельных захваченных групп. Поэтому эти абзацы можно обработать по-разному.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "<PRIVATE> This is not for public consumption." + Environment.NewLine + 
                     "But this is for public consumption." + Environment.NewLine + 
                     "<PRIVATE> Again, this is confidential.\n";  
      string pattern = @"^(?<Pvt>\<PRIVATE\>\s)?(?(Pvt)((\w+\p{P}?\s)+)|((\w+\p{P}?\s)+))\r?$";
      string publicDocument = null, privateDocument = null;

      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.Multiline))
      {
         if (match.Groups[1].Success) {
            privateDocument += match.Groups[1].Value + "\n";
         }
         else {
            publicDocument += match.Groups[3].Value + "\n";   
            privateDocument += match.Groups[3].Value + "\n";
         }  
      }

      Console.WriteLine("Private Document:");
      Console.WriteLine(privateDocument);
      Console.WriteLine("Public Document:");
      Console.WriteLine(publicDocument);
   }
}
// The example displays the following output:
//    Private Document:
//    This is not for public consumption.
//    But this is for public consumption.
//    Again, this is confidential.
//    
//    Public Document:
//    But this is for public consumption.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "<PRIVATE> This is not for public consumption." + vbCrLf + _
                            "But this is for public consumption." + vbCrLf + _
                            "<PRIVATE> Again, this is confidential." + vbCrLf
      Dim pattern As String = "^(?<Pvt>\<PRIVATE\>\s)?(?(Pvt)((\w+\p{P}?\s)+)|((\w+\p{P}?\s)+))\r?$"
      Dim publicDocument As String = Nothing
      Dim privateDocument As String = Nothing

      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.Multiline)
         If match.Groups(1).Success Then
            privateDocument += match.Groups(1).Value + vbCrLf
         Else
            publicDocument += match.Groups(3).Value + vbCrLf   
            privateDocument += match.Groups(3).Value + vbCrLf
         End If  
      Next

      Console.WriteLine("Private Document:")
      Console.WriteLine(privateDocument)
      Console.WriteLine("Public Document:")
      Console.WriteLine(publicDocument)
   End Sub
End Module
' The example displays the following output:
'    Private Document:
'    This is not for public consumption.
'    But this is for public consumption.
'    Again, this is confidential.
'    
'    Public Document:
'    But this is for public consumption.
```

Шаблон регулярного выражения определяется, как показано в следующей таблице.

Шаблон | Описание
------- | -----------
`^` | Начало совпадения в начале строки.
`(?<Pvt>\<PRIVATE\>\s)?` | Соответствует вхождениям в количестве 0 или 1 строки `<PRIVATE>` за которым следует символ пробела. Назначение соответствия для захваченной группы с именем.
`(?(Pvt)((\w+\p{P}?\s)+)` | Если захваченная группа `Pvt` существует, сопоставление одного или нескольких вхождений одного или нескольких вхождений символов слов, за которыми следует 0 или 1 пунктуационный разделитель с последующим любым пробелом. Назначение части строки первой захваченной группе.
`&#124;((\w+\p{P}?\s)+))` | Если захваченная группа `Pvt` не существует, сопоставление одного или нескольких вхождений одного или нескольких вхождений символов слов, за которыми следует 0 или 1 пунктуационный разделитель с последующим любым пробелом. Назначение части строки третьей захваченной группе.
`\r?$` | Соответствует концу строки.
 
Дополнительные сведения об условной оценке см. в статье [Конструкции изменения в регулярных выражениях](alternation.md).

### <a name="balancing-group-definitions"></a>Сбалансированные определения группы

Сбалансированные определения группы:**(?<**_name1-name2_**>** _subexpression_**)**. Эта функция позволяет обработчику регулярных выражений отслеживать вложенные конструкции, такие как скобки или открывающие и закрывающие круглые скобки. Пример см. в статье [Конструкции группировки в регулярных выражениях](grouping.md).

### <a name="nonbacktracking-subexpressions"></a>Невозвращающиеся части выражения

Невозвращающиеся ("жадные") части выражения: **(?>**_subexpression_**)**. Эта функция обеспечивает для подвыражения верность только первого соответствия, как будто выражение запускалось независимо от содержащего его выражения. Без этой конструкции поиск в большом выражении с использованием поиска с возвратом может изменить поведение части выражения. Например, регулярное выражение `(a+)\w` соответствует одному или нескольким символам "a" наряду с буквой, после которой идет последовательность символов "a", и назначает последовательность символов "a" для первой захваченной группы. Однако если последний символ входной строки также является символом "a", он соответствует элементу языка `\w` и не входит в захваченную группу.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "aaaaa", "aaaaab" };
      string backtrackingPattern = @"(a+)\w";
      Match match;

      foreach (string input in inputs) {
         Console.WriteLine("Input: {0}", input);
         match = Regex.Match(input, backtrackingPattern);
         Console.WriteLine("   Pattern: {0}", backtrackingPattern);
         if (match.Success) { 
            Console.WriteLine("      Match: {0}", match.Value);
            Console.WriteLine("      Group 1: {0}", match.Groups[1].Value);
         }
         else {
            Console.WriteLine("      Match failed.");
         }   
      }
      Console.WriteLine();            
   }
}
// The example displays the following output:
//       Input: aaaaa
//          Pattern: (a+)\w
//             Match: aaaaa
//             Group 1: aaaa
//       Input: aaaaab
//          Pattern: (a+)\w
//             Match: aaaaab
//             Group 1: aaaaa
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "aaaaa", "aaaaab" }
      Dim backtrackingPattern As String = "(a+)\w"
      Dim match As Match

      For Each input As String In inputs
         Console.WriteLine("Input: {0}", input)
         match = Regex.Match(input, backtrackingPattern)
         Console.WriteLine("   Pattern: {0}", backtrackingPattern)
         If match.Success Then 
            Console.WriteLine("      Match: {0}", match.Value)
            Console.WriteLine("      Group 1: {0}", match.Groups(1).Value)
         Else 
            Console.WriteLine("      Match failed.")
         End If   
      Next
      Console.WriteLine()            
   End Sub
End Module
' The example displays the following output:
'       Input: aaaaa
'          Pattern: (a+)\w
'             Match: aaaaa
'             Group 1: aaaa
'       Input: aaaaab
'          Pattern: (a+)\w
'             Match: aaaaab
'             Group 1: aaaaa
```

Регулярное выражение `((?>a+))\w` препятствует такому поведению. Поскольку все последовательные символы "a" имеют соответствия без поиска с возвратом, первая захваченная группа содержит все последовательные символы "a". Если после символов "a" не следует ни один символ, отличный от "a", соответствие считается неудачным.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "aaaaa", "aaaaab" };
      string nonbacktrackingPattern = @"((?>a+))\w";
      Match match;

      foreach (string input in inputs) {
         Console.WriteLine("Input: {0}", input);
         match = Regex.Match(input, nonbacktrackingPattern);
         Console.WriteLine("   Pattern: {0}", nonbacktrackingPattern);
         if (match.Success) { 
            Console.WriteLine("      Match: {0}", match.Value);
            Console.WriteLine("      Group 1: {0}", match.Groups[1].Value);
         }
         else {
            Console.WriteLine("      Match failed.");
         }   
      }
      Console.WriteLine();            
   }
}
// The example displays the following output:
//       Input: aaaaa
//          Pattern: ((?>a+))\w
//             Match failed.
//       Input: aaaaab
//          Pattern: ((?>a+))\w
//             Match: aaaaab
//             Group 1: aaaaa
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "aaaaa", "aaaaab" }
      Dim nonbacktrackingPattern As String = "((?>a+))\w"
      Dim match As Match

      For Each input As String In inputs
         Console.WriteLine("Input: {0}", input)
         match = Regex.Match(input, nonbacktrackingPattern)
         Console.WriteLine("   Pattern: {0}", nonbacktrackingPattern)
         If match.Success Then 
            Console.WriteLine("      Match: {0}", match.Value)
            Console.WriteLine("      Group 1: {0}", match.Groups(1).Value)
         Else 
            Console.WriteLine("      Match failed.")
         End If   
      Next
      Console.WriteLine()            
   End Sub
End Module
' The example displays the following output:
'       Input: aaaaa
'          Pattern: ((?>a+))\w
'             Match failed.
'       Input: aaaaab
'          Pattern: ((?>a+))\w
'             Match: aaaaab
'             Group 1: aaaaa
```

Дополнительные сведения о невозвращающихся частях выражений см. в статье [Конструкции группировки в регулярных выражениях](grouping.md).

### <a name="right-to-left-matching"></a>Поиск совпадений справа налево

Поиск совпадений справа налево, задаваемый путем передачи параметра [RegexOptions.RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft) конструктору класса [Regex](xref:System.Text.RegularExpressions.Regex) или методу сопоставления статических экземпляров. Эта функция полезна при поиске справа налево вместо обычного поиска слева направо, а также бывает более эффективно начинать поиск с правой части шаблона, а не с левой. Как показано в примере ниже, использование поиска соответствий справа налево может изменить поведение жадных квантификаторов. В примере выполняется два поисковых запроса предложения, оканчивающегося на число. При поиске слева направо с использованием жадного квантификатора `+` имеется соответствие одной из шести цифр в предложении, тогда как при поиске справа налево — всем шести цифрам. Описание шаблона регулярного выражения см. в примере с ленивыми квантификаторами ранее в этом разделе.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string greedyPattern = @".+(\d+)\.";
      string input = "This sentence ends with the number 107325.";
      Match match;

      // Match from left-to-right using lazy quantifier .+?.
      match = Regex.Match(input, greedyPattern);
      if (match.Success)
         Console.WriteLine("Number at end of sentence (left-to-right): {0}", 
                           match.Groups[1].Value);
      else
         Console.WriteLine("{0} finds no match.", greedyPattern);

      // Match from right-to-left using greedy quantifier .+.
      match = Regex.Match(input, greedyPattern, RegexOptions.RightToLeft);
      if (match.Success)
         Console.WriteLine("Number at end of sentence (right-to-left): {0}", 
                           match.Groups[1].Value);
      else
         Console.WriteLine("{0} finds no match.", greedyPattern);
   }
}
// The example displays the following output:
//       Number at end of sentence (left-to-right): 5
//       Number at end of sentence (right-to-left): 107325
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim greedyPattern As String = ".+(\d+)\."
      Dim input As String = "This sentence ends with the number 107325."
      Dim match As Match

      ' Match from left-to-right using lazy quantifier .+?.
      match = Regex.Match(input, greedyPattern)
      If match.Success Then
         Console.WriteLine("Number at end of sentence (left-to-right): {0}", 
                           match.Groups(1).Value)
      Else
         Console.WriteLine("{0} finds no match.", greedyPattern)
      End If

      ' Match from right-to-left using greedy quantifier .+.
      match = Regex.Match(input, greedyPattern, RegexOptions.RightToLeft)
      If match.Success Then
         Console.WriteLine("Number at end of sentence (right-to-left): {0}", 
                           match.Groups(1).Value)
      Else
         Console.WriteLine("{0} finds no match.", greedyPattern)
      End If
   End Sub
End Module
' The example displays the following output:
'       Number at end of sentence (left-to-right): 5
'       Number at end of sentence (right-to-left): 107325
```

Дополнительные сведения о поиске соответствий справа налево см. в статье [Параметры регулярных выражений](options.md).

### <a name="positive-and-negative-lookbehind"></a>Положительный и отрицательный поиск назад

Положительный и отрицательный поиск назад: **(?<**=_subexpression_**)** для положительного поиска назад и **(?<!**_subexpression_**)** для отрицательного поиска назад. Эта функция аналогична поиску вперед, рассмотренному ранее в этом разделе. Поскольку обработчик регулярных выражений позволяет выполнять поиск справа налево, к регулярным выражениям можно применять поиск назад без каких-либо ограничений. С помощью положительного и отрицательного поиска назад также можно избегать вложенных квантификаторов, когда вложенная часть выражения является супермножеством внешнего выражения. Регулярные выражения с такими вложенными квантификаторами часто являются причиной низкой производительности. В следующем примере выполняется проверка, начинается ли и оканчивается ли строка с буквы или цифры, а также является ли любой другой символ в строке символом большего подмножества. В результате формируется часть регулярного выражения, используемая для проверки адресов электронной почты. Дополнительные сведения см. в разделе [Практическое руководство. Проверка строк на соответствие формату электронной почты](verify-format.md).

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "jack.sprat", "dog#", "dog#1", "me.myself", 
                          "me.myself!" };
      string pattern = @"^[A-Z0-9]([-!#$%&'.*+/=?^`{}|~\w])*(?<=[A-Z0-9])$";
      foreach (string input in inputs) {
         if (Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase))
            Console.WriteLine("{0}: Valid", input);
         else
            Console.WriteLine("{0}: Invalid", input);
      }
   }
}
// The example displays the following output:
//       jack.sprat: Valid
//       dog#: Invalid
//       dog#1: Valid
//       me.myself: Valid
//       me.myself!: Invalid
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "jack.sprat", "dog#", "dog#1", "me.myself", 
                                 "me.myself!" }
      Dim pattern As String = "^[A-Z0-9]([-!#$%&'.*+/=?^`{}|~\w])*(?<=[A-Z0-9])$"
      For Each input As String In inputs
         If Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase) Then
            Console.WriteLine("{0}: Valid", input)
         Else
            Console.WriteLine("{0}: Invalid", input)
         End If   
      Next
   End Sub
End Module
' The example displays the following output:
'       jack.sprat: Valid
'       dog#: Invalid
'       dog#1: Valid
'       me.myself: Valid
'       me.myself!: Invalid
```

В таблице ниже представлено определение регулярного выражения `^[A-Z0-9]([-!#$%&'.*+/=?^`{}|~\w])*(?<=[A-Z0-9])$.

Шаблон | Описание
------- | ----------- 
`^` | Начало совпадения в начале строки.
`[A-Z0-9]` | Соответствие любому алфавитно-цифровому символу. (При сравнении регистр не учитывается.)
`([-!#$%&'.*+/=?^`{}&#124;~\w])*` | Соответствие 0 или нескольким вхождениям любого символа слова или любого следующего символа: -, !, #, $, %, &, ', ., *, +, /, =, ?, ^, `, {, }, &#124;, или ~.
`(?<=[A-Z0-9])` | Поиск назад предыдущего символа, который должен являться числом или буквенно-цифровым символом. (При сравнении регистр не учитывается.)
`$` | Совпадение должно заканчиваться в конце строки.
 
Дополнительные сведения о положительном и отрицательном поиске назад см. в статье [Конструкции группировки в регулярных выражениях](grouping.md).


## <a name="related-topics"></a>Связанные разделы

Заголовок | Описание
----- | ----------- 
[Поиск с возвратом](backtracking.md) | Сведения об использовании поиска с возвратом для поиска альтернативных соответствий.
[Компиляция и многократное использование](compilation.md) | Сведения о компиляции и многократном использовании регулярных выражений для повышения производительности.
[Потокобезопасность](thread-safety.md) | Сведения о потокобезопасности регулярных выражений и времени синхронизации доступа к объектам регулярных выражений.
[Регулярные выражения .NET](regular-expressions.md) | Общие сведения о регулярных выражениях в контексте языка программирования.
[Объектная модель регулярных выражений](object-model.md) | Сведения об использовании классов регулярных выражений и примеры кода.
[Примеры регулярных выражений](regex-examples.md) | Примеры кодов, иллюстрирующих использование регулярных выражений в обычных приложениях.
[Элементы языка регулярных выражений — краткий справочник](quick-ref.md) | Сведения о наборе символов, операторов и конструкций, которые можно использовать для определения регулярных выражений.
 
## <a name="reference"></a>Ссылка

[System.Text.RegularExpressions](xref:System.Text.RegularExpressions)




<!--HONumber=Nov16_HO3-->


