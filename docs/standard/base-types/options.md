---
title: "Параметры регулярных выражений"
description: "Параметры регулярных выражений"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 2db2c3e6-953e-4913-8168-d707c437f2df
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: a2a9fe356a0b2e9cf9415714bc01b77ea86229fc

---

# <a name="regular-expression-options"></a>Параметры регулярных выражений

По умолчанию при сравнении входной строки с любыми литералами в шаблоне регулярного выражения учитывается регистр, пробел в шаблоне интерпретируется как литерал, а захватываемые группы в регулярном выражении именуются как явно, так и неявно. Вы можете изменить эти и некоторые другие аспекты поведения регулярного выражения по умолчанию с помощью параметров регулярного выражения. Эти параметры, которые представлены в следующей таблице, могут быть указаны как часть шаблона регулярного выражения или переданы конструктору класса [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) или статичному методу сопоставления шаблона как значение перечисления [System.Text.RegularExpressions.RegexOptions](xref:System.Text.RegularExpressions.RegexOptions). 

Член RegexOptions | Встроенный символ | Действие
------------------- | ---------------- | ------ 
[None](xref:System.Text.RegularExpressions.RegexOptions.None) | Недоступно | Использовать поведение по умолчанию. Дополнительные сведения см. в статье [Параметры по умолчанию](#default-options).
[IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase) | **i** | Использовать соответствие без учета регистра. Дополнительные сведения см. в статье [Сопоставление без учета регистра](#case-insensitive-matching).
[Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline) | **m** | Использовать многострочный режим, где **^** и **$** соответствуют началу и концу строки текста (а не началу и концу входной строки). Дополнительные сведения см. в статье [Многострочный режим](#multiline-mode).
[Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline) | **s** | Использовать однострочный режим, где точка (**.**) соответствует любому символу (а не каждому символу, кроме **\n**). Дополнительные сведения см. в статье [Однострочный режим](#single-line-mode).
[ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) | **n** | Не захватывать неименованные группы. Единственные допустимые захваты — это явно именованные или нумерованные группы в формате **(?<**_name_**>** _subexpression_**)**. Дополнительные сведения см. в статье [Только явные захваты](#explicit-captures-only).
[Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) | Недоступно | Скомпилировать регулярное выражение в сборку. Дополнительные сведения см. в статье [Скомпилированные регулярные выражения](#compiled-regular-expressions).
[IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace) | **x** | Исключить неэкранированные пробелы из шаблона и включить комментарии после символа решетки (**#**). Дополнительные сведения см. в статье [Пропуск пробелов](#ignore-white-space).
[RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft) | Недоступно | Изменить направление поиска. Поиск идет справа налево, а не слева направо. Дополнительные сведения см. в статье [Режим "справа налево"](#right-to-left-mode).
[ECMAScript](xref:System.Text.RegularExpressions.RegexOptions.ECMAScript) | Недоступно | Включить поведение, совместимое с ECMAScript, для выражения. Дополнительные сведения см. в статье [Поведение сопоставления ECMAScript](#ecmascript-matching-behavior).
[CultureInvariant](xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant) | Недоступно | Игнорировать различия региональных параметров в языке. Дополнительные сведения см. в статье [Сравнение с использованием инвариантных региональных параметров](#comparison-using-the-invariant-culture).
 
## <a name="specifying-the-options"></a>Указание параметров

Параметры регулярных выражений можно указать одним из трех способов:

* В параметре *options* конструктора класса [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex), такого как [Regex.Regex(String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.%23ctor(System.String,System.Text.RegularExpressions.RegexOptions)), или статического метода сопоставления шаблона (Shared в Visual Basic), такого как [Regex.Match(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions)). Параметр *options* — побитовое сочетание OR значений перечисления [System.Text.RegularExpressions.RegexOptions](xref:System.Text.RegularExpressions.RegexOptions). 

  Когда параметры передаются экземпляру [Regex](xref:System.Text.RegularExpressions.Regex) с помощью параметра *options* конструктора класса, они присваиваются свойству [System.Text.RegularExpressions.RegexOptions](xref:System.Text.RegularExpressions.RegexOptions). Однако свойство [System.Text.RegularExpressions.RegexOptions](xref:System.Text.RegularExpressions.RegexOptions) не отражает встроенные параметры в самом шаблоне регулярного выражения. 

  Ниже приведен пример. В нем параметр *options* метода [Regex.Match(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) используется для включения сопоставления без учета регистра и пропуска пробелов при определении слов, начинающихся с буквы "d".

  ```csharp
  string pattern = @"d \w+ \s";
  string input = "Dogs are decidedly good pets.";
  RegexOptions options = RegexOptions.IgnoreCase | RegexOptions.IgnorePatternWhitespace;
  
  foreach (Match match in Regex.Matches(input, pattern, options))
     Console.WriteLine("'{0}// found at index {1}.", match.Value, match.Index);
  // The example displays the following output:
  //    'Dogs // found at index 0.
  //    'decidedly // found at index 9.      
  ```

  ```vb
  Dim pattern As String = "d \w+ \s"
  Dim input As String = "Dogs are decidedly good pets."
  Dim options As RegexOptions = RegexOptions.IgnoreCase Or RegexOptions.IgnorePatternWhitespace

  For Each match As Match In Regex.Matches(input, pattern, options)
     Console.WriteLine("'{0}' found at index {1}.", match.Value, match.Index)
  Next
  ' The example displays the following output:
  '    'Dogs ' found at index 0.
  '    'decidedly ' found at index 9.  
  ```

* Применяя встроенные параметры в шаблоне регулярного выражения с помощью синтаксиса **(?imnsx-imnsx)**. Параметр применяется к шаблону от точки, в которой определен параметр, и действует либо до конца шаблона, либо до точки, в которой другая конструкция отменяет параметр. Обратите внимание, что свойство [System.Text.RegularExpressions.RegexOptions](xref:System.Text.RegularExpressions.RegexOptions) экземпляра [Regex](xref:System.Text.RegularExpressions.Regex) не отражает этих встроенных параметров. Дополнительные сведения см. в статье [Другие конструкции в регулярных выражениях](miscellaneous.md).

  Ниже приведен пример. В нем встроенные параметры используются для включения сопоставления без учета регистра и пропуска пробелов при определении слов, начинающихся с буквы "d".

  ```csharp
  string pattern = @"(?ix) d \w+ \s";
  string input = "Dogs are decidedly good pets.";
  
  foreach (Match match in Regex.Matches(input, pattern))
     Console.WriteLine("'{0}// found at index {1}.", match.Value, match.Index);
  // The example displays the following output:
  //    'Dogs // found at index 0.
  //    'decidedly // found at index 9.      
  ```

  ```vb
  Dim pattern As String = "\b(?ix) d \w+ \s"
  Dim input As String = "Dogs are decidedly good pets."

  For Each match As Match In Regex.Matches(input, pattern)
     Console.WriteLine("'{0}' found at index {1}.", match.Value, match.Index)
  Next
  ' The example displays the following output:
  '    'Dogs ' found at index 0.
  '    'decidedly ' found at index 9.  
  ```

* Применяя встроенные параметры в определенной конструкции группировки в шаблоне регулярного выражения с помощью синтаксиса **(?imnsx-imnsx:**_subexpression_**)**. Если знак перед наборов параметров отсутствует, он включается. Если перед набором параметров есть знак минуса, набор отключается. (**?** — это фиксированная часть синтаксиса языковой конструкции, необходимая, если параметры включаются или отключаются.) Этот параметр применяется только к данной группе. Дополнительные сведения см. в статье [Конструкции группировки в регулярных выражениях](grouping.md).

  Ниже приведен пример. В нем встроенные параметры в конструкции группировки используются для включения сопоставления без учета регистра и пропуска пробелов при определении слов, начинающихся с буквы "d".

  ```csharp
  string pattern = @"\b(?ix: d \w+)\s";
  string input = "Dogs are decidedly good pets.";
  
  foreach (Match match in Regex.Matches(input, pattern))
     Console.WriteLine("'{0}// found at index {1}.", match.Value, match.Index);
  // The example displays the following output:
  //    'Dogs // found at index 0.
  //    'decidedly // found at index 9.      
  ```

  ```vb
  Dim pattern As String = "\b(?ix: d \w+)\s"
  Dim input As String = "Dogs are decidedly good pets."

  For Each match As Match In Regex.Matches(input, pattern)
     Console.WriteLine("'{0}' found at index {1}.", match.Value, match.Index)
  Next
  ' The example displays the following output:
  '    'Dogs ' found at index 0.
  '    'decidedly ' found at index 9. 
  ```


Если параметры указываются в строке, знак минуса (-) перед параметром или набором параметров отключает соответствующие параметры. Например, встроенная конструкция **(? ix-ms)** включает параметры [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase) и [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace) и отключает параметры [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline) и [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline). Все параметры регулярного выражения по умолчанию отключены.

> [!NOTE]
> Если параметры регулярного выражения, указанные в параметре options конструктора или вызове метода, конфликтуют со встроенными параметрами в шаблоне регулярного выражения, используются последние.
 

Следующие пять параметров регулярного выражения можно задавать одновременно в параметре *options* и в строке:

* [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase)

* [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline)

* [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline)

* [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture)

* [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace)

Следующие пять параметров регулярного выражения можно задавать в параметре *options*, но не в строке:

* [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None)

* [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled)

* [RegexOptions.RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft)

* [RegexOptions.CultureInvariant](xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant)

* [RegexOptions.ECMAScript](xref:System.Text.RegularExpressions.RegexOptions.ECMAScript)

## <a name="determining-the-options"></a>Определение параметров

Вы можете определить, какие параметры были предоставлены объекту [Regex](xref:System.Text.RegularExpressions.Regex) при создании его экземпляра, получив значение свойства [Regex.Options](xref:System.Text.RegularExpressions.Regex.Options) только для чтения.

Чтобы проверить наличие любого параметра, кроме [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None), выполните операцию AND со значением свойства [Regex.Options](xref:System.Text.RegularExpressions.Regex.Options) и значением [RegexOptions](xref:System.Text.RegularExpressions.RegexOptions), которое вас интересует. Затем проверьте, равен ли результат значению [RegexOptions](xref:System.Text.RegularExpressions.RegexOptions). Следующий пример проверяет, задан ли параметр [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase). 

```csharp
if ((rgx.Options & RegexOptions.IgnoreCase) == RegexOptions.IgnoreCase)
   Console.WriteLine("Case-insensitive pattern comparison.");
else
   Console.WriteLine("Case-sensitive pattern comparison.");
```

```vb
If (rgx.Options And RegexOptions.IgnoreCase) = RegexOptions.IgnoreCase Then
   Console.WriteLine("Case-insensitive pattern comparison.")
Else
   Console.WriteLine("Case-sensitive pattern comparison.")
End If 
```

Чтобы проверить наличие параметра [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None), определите, равно ли значение свойства [RegexOptions](xref:System.Text.RegularExpressions.RegexOptions) значению [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None), как показано в следующем примере. 

```csharp
if (rgx.Options == RegexOptions.None)
   Console.WriteLine("No options have been set.");
```

```vb
If rgx.Options = RegexOptions.None Then
   Console.WriteLine("No options have been set.")
End If
```

В следующих разделах перечислены параметры, поддерживаемые регулярными выражениями платформы .NET. 

## <a name="default-options"></a>Параметры по умолчанию

Параметр [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None) указывает, что ни один параметр не задан, а механизм регулярных выражений использует поведение по умолчанию. Это поведение характеризуется следующим образом.

* Шаблон интерпретируется как каноническое, а не регулярное выражение ECMAScript.

* Шаблон регулярного выражения сопоставляется во входной строке слева направо.

* При сравнениях учитывается регистр.

* Языковые элементы **^** и **$** сосуществуют началу и концу входной строки.

* Языковой элемент **.** соответствует каждому символу, кроме **\n**.

* Любой пробел в шаблоне регулярного выражения интерпретируется как пробел-литерал.

* При сравнении шаблона со входной строкой используются соглашения текущих региональных параметров. 

* Захватываемые группы в шаблоне регулярного выражения являются неявными и явными. 

> [!NOTE]
> Параметр [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None) не имеет эквивалента среди встроенных параметров. Если параметры регулярного выражения применяются в строке, поведение по умолчанию восстанавливается для каждого параметра, за счет отключения того или иного параметра. Например, `(?i)` включает сравнение без учета регистра, а `(?-i)` восстанавливает учет регистра при сравнении.
 
Так как параметр [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None) представляет поведение механизма регулярных выражений по умолчанию, он редко явно указывается в вызове метода. Вместо этого вызывается конструктор или статичный метод сопоставления шаблона без параметра options.

## <a name="case-insensitive-matching"></a>Сопоставление без учета регистра

Параметр [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase) или встроенный параметр **i** обеспечивает сопоставление без учета регистра. По умолчанию используются соглашения о регистре текущих региональных параметров.

Следующий пример определяет шаблон регулярного выражения, `\bthe\w*\b`, который сопоставляет все слова, начинающиеся со строки "the". Так как первый вызов метода Match использует сравнение с учетом регистра по умолчанию, в выходных данных указывается, что строка "The" в начале предложения не была сопоставлена. Она выделяется, если метод [Match](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) вызывается с параметром options, имеющим значение [IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase). 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\bthe\w*\b";
      string input = "The man then told them about that event.";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index);

      Console.WriteLine();
      foreach (Match match in Regex.Matches(input, pattern, 
                                            RegexOptions.IgnoreCase))
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index);
   }
}
// The example displays the following output:
//       Found then at index 8.
//       Found them at index 18.
//       
//       Found The at index 0.
//       Found then at index 8.
//       Found them at index 18.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\bthe\w*\b"
      Dim input As String = "The man then told them about that event."
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index)
      Next
      Console.WriteLine()
      For Each match As Match In Regex.Matches(input, pattern, _
                                               RegexOptions.IgnoreCase)
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index)
      Next
   End Sub
End Module
' The example displays the following output:
'       Found then at index 8.
'       Found them at index 18.
'       
'       Found The at index 0.
'       Found then at index 8.
'       Found them at index 18.
```

В следующем примере показано изменение шаблона регулярного выражения из предыдущего примера для использования встроенных параметров вместо параметра *options*, чтобы включить сравнение без учета регистра. Первый шаблон определяет параметр отключения учета регистра в конструкции группировки, которая применяется только к букве "t" в строке "the". Так как конструкция указана в начале шаблона, второй шаблон применяет параметр учета регистра ко всему регулярному выражению.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(?i:t)he\w*\b";
      string input = "The man then told them about that event.";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index);

      Console.WriteLine();
      pattern = @"(?i)\bthe\w*\b";
      foreach (Match match in Regex.Matches(input, pattern, 
                                            RegexOptions.IgnoreCase))
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index);
   }
}
// The example displays the following output:
//       Found The at index 0.
//       Found then at index 8.
//       Found them at index 18.
//       
//       Found The at index 0.
//       Found then at index 8.
//       Found them at index 18.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(?i:t)he\w*\b"
      Dim input As String = "The man then told them about that event."
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index)
      Next
      Console.WriteLine()
      pattern = "(?i)\bthe\w*\b"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index)
      Next
   End Sub
End Module
' The example displays the following output:
'       Found The at index 0.
'       Found then at index 8.
'       Found them at index 18.
'       
'       Found The at index 0.
'       Found then at index 8.
'       Found them at index 18.
```

## <a name="multiline-mode"></a>Многострочный режим

Параметр [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline) или встроенный параметр **m** позволяет механизму регулярных выражений обрабатывать входную строку, которая состоит из нескольких строк. Он изменяет интерпретацию языковых элементов **^** и **$**, чтобы они сопоставляли начало и конец строки текста, а не начало и строки входной строки. 

По умолчанию **$** сопоставляет конец входной строки. Если указать параметр [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline), он сопоставляет символ новой строки (**(\n)**) или конец входной строки. Однако он не сопоставляет комбинацию символов возврата каретки и перевода строки. Для их успешного сопоставления используйте часть выражения **\r?$** вместо **$**. 

В следующем примере извлекаются имена и баллы игроков в боулинг и добавляются в коллекцию [SortedList&lt;TKey, TValue&gt;](xref:System.Collections.Generic.SortedList%602), где они сортируются по убыванию. Метод [Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) вызывается два раза. В первом вызове метода используется регулярное выражение `^(\w+)\s(\d+)$`, параметры не заданы. Как видно в результатах, совпадения не найдены, так как механизм регулярных выражений не может сопоставить входной шаблон с началом и концом входной строки. Во втором вызове метода регулярное выражение меняется на `^(\w+)\s(\d+)\r?$` и задаются параметры [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline). Как видно в результатах, имена и баллы успешно сопоставляются, а баллы отображаются по убыванию.

```csharp
using System;
using System.Collections.Generic;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      SortedList<int, string> scores = new SortedList<int, string>(new DescendingComparer<int>());

      string input = "Joe 164\n" + 
                     "Sam 208\n" + 
                     "Allison 211\n" + 
                     "Gwen 171\n"; 
      string pattern = @"^(\w+)\s(\d+)$";
      bool matched = false;

      Console.WriteLine("Without Multiline option:");
      foreach (Match match in Regex.Matches(input, pattern))
      {
         scores.Add(Int32.Parse(match.Groups[2].Value), (string) match.Groups[1].Value);
         matched = true;
      }
      if (! matched)
         Console.WriteLine("   No matches.");
      Console.WriteLine();

      // Redefine pattern to handle multiple lines.
      pattern = @"^(\w+)\s(\d+)\r*$";
      Console.WriteLine("With multiline option:");
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.Multiline))
         scores.Add(Int32.Parse(match.Groups[2].Value), (string) match.Groups[1].Value);

      // List scores in descending order. 
      foreach (KeyValuePair<int, string> score in scores)
         Console.WriteLine("{0}: {1}", score.Value, score.Key);
   }
}

public class DescendingComparer<T> : IComparer<T>
{
   public int Compare(T x, T y)
   {
      return Comparer<T>.Default.Compare(x, y) * -1;       
   }
}
// The example displays the following output:
//   Without Multiline option:
//      No matches.
//   
//   With multiline option:
//   Allison: 211
//   Sam: 208
//   Gwen: 171
//   Joe: 164
```

```vb
Imports System.Collections.Generic
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim scores As New SortedList(Of Integer, String)(New DescendingComparer(Of Integer)())

      Dim input As String = "Joe 164" + vbCrLf + _
                            "Sam 208" + vbCrLf + _
                            "Allison 211" + vbCrLf + _
                            "Gwen 171" + vbCrLf
      Dim pattern As String = "^(\w+)\s(\d+)$"
      Dim matched As Boolean = False

      Console.WriteLine("Without Multiline option:")
      For Each match As Match In Regex.Matches(input, pattern)
         scores.Add(CInt(match.Groups(2).Value), match.Groups(1).Value)
         matched = True
      Next
      If Not matched Then Console.WriteLine("   No matches.")
      Console.WriteLine()

      ' Redefine pattern to handle multiple lines.
      pattern = "^(\w+)\s(\d+)\r*$"
      Console.WriteLine("With multiline option:")
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.Multiline)
         scores.Add(CInt(match.Groups(2).Value), match.Groups(1).Value)
      Next
      ' List scores in descending order. 
      For Each score As KeyValuePair(Of Integer, String) In scores
         Console.WriteLine("{0}: {1}", score.Value, score.Key)
      Next
   End Sub
End Module

Public Class DescendingComparer(Of T) : Implements IComparer(Of T)
   Public Function Compare(x As T, y As T) As Integer _
          Implements IComparer(Of T).Compare
      Return Comparer(Of T).Default.Compare(x, y) * -1       
   End Function
End Class
' The example displays the following output:
'    Without Multiline option:
'       No matches.
'    
'    With multiline option:
'    Allison: 211
'    Sam: 208
'    Gwen: 171
'    Joe: 164
```

Шаблон регулярного выражения `^(\w+)\s(\d+)\r*$` определяется, как показано в следующей таблице.

Шаблон | Описание
------- | ----------- 
`^` | Начало с первого символа строки.
`(\w+)` | Совпадение с одним или несколькими символами слова. Это первая группа записи.
`\s` | Соответствует пробелу.
`(\d+)` | Совпадение с одной или несколькими десятичными цифрами. Это вторая группа записи.
`\r?` | Сопоставление нуля или одного символа возврата каретки.
`$` | Окончание в конце строки.
 
Следующий пример аналогичен предыдущему, но он использует встроенный параметр **(?m)** для включения многострочного режима.

```csharp
using System;
using System.Collections.Generic;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      SortedList<int, string> scores = new SortedList<int, string>(new DescendingComparer<int>());

      string input = "Joe 164\n" +  
                     "Sam 208\n" +  
                     "Allison 211\n" +  
                     "Gwen 171\n"; 
      string pattern = @"(?m)^(\w+)\s(\d+)\r*$";

      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.Multiline))
         scores.Add(Convert.ToInt32(match.Groups[2].Value), match.Groups[1].Value);

      // List scores in descending order. 
      foreach (KeyValuePair<int, string> score in scores)
         Console.WriteLine("{0}: {1}", score.Value, score.Key);
   }
}

public class DescendingComparer<T> : IComparer<T>
{
   public int Compare(T x, T y) 
   {
      return Comparer<T>.Default.Compare(x, y) * -1;       
   }
}
// The example displays the following output:
//    Allison: 211
//    Sam: 208
//    Gwen: 171
//    Joe: 164
```

```vb
Imports System.Collections.Generic
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim scores As New SortedList(Of Integer, String)(New DescendingComparer(Of Integer)())

      Dim input As String = "Joe 164" + vbCrLf + _
                            "Sam 208" + vbCrLf + _
                            "Allison 211" + vbCrLf + _
                            "Gwen 171" + vbCrLf
      Dim pattern As String = "(?m)^(\w+)\s(\d+)\r*$"

      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.Multiline)
         scores.Add(CInt(match.Groups(2).Value), match.Groups(1).Value)
      Next
      ' List scores in descending order. 
      For Each score As KeyValuePair(Of Integer, String) In scores
         Console.WriteLine("{0}: {1}", score.Value, score.Key)
      Next
   End Sub
End Module

Public Class DescendingComparer(Of T) : Implements IComparer(Of T)
   Public Function Compare(x As T, y As T) As Integer _
          Implements IComparer(Of T).Compare
      Return Comparer(Of T).Default.Compare(x, y) * -1       
   End Function
End Class
' The example displays the following output:
'    Allison: 211
'    Sam: 208
'    Gwen: 171
'    Joe: 164
```

## <a name="single-line-mode"></a>Однострочный режим

Параметр [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline) или встроенный параметр s позволяет механизму регулярных выражений обрабатывать входную строку так, будто она состоит из одной строки. Для этого поведение языкового элемента **.** меняется так, чтобы он сопоставлял каждый символ, а не каждый символ кроме символа новой строки **\n** или \u000A.

В следующем примере показано различное поведение языкового элемента "." при использовании параметра [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline). Регулярное выражение `^.+` начинается с начала строки и соответствует любому знаку. По умолчанию соответствие заканчивается в конце первой строки; шаблон регулярного выражения соответствует символу возврата каретки **\r** или \u000D, но не соответствует **\n**. Поскольку параметр [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline) интерпретирует всю входную строку как единую строку, он сопоставляет каждый символ в строке ввода, включая **\n**.

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

Следующий пример аналогичен предыдущему, но он использует встроенный параметр **(?s)** для включения однострочного режима. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {      
      string pattern = "(?s)^.+";
      string input = "This is one line and" + Environment.NewLine + "this is the second.";

      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(Regex.Escape(match.Value));
   }
}
// The example displays the following output:
//       This\ is\ one\ line\ and\r\nthis\ is\ the\ second\.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(?s)^.+"
      Dim input As String = "This is one line and" + vbCrLf + "this is the second."

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(Regex.Escape(match.Value))
      Next
   End Sub
End Module
' The example displays the following output:
'       This\ is\ one\ line\ and\r\nthis\ is\ the\ second\.
```

## <a name="explicit-captures-only"></a>Только явные захваты

По умолчанию захватываемые группы определяются с помощью круглых скобок в шаблоне регулярного выражения. Именованным группам назначается имя или номер с помощью параметра **(?<**_name_**>** _subexpression_**)**, а именованные группы доступны по индексу. В объекте [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) неименованные группы идут перед именованными. 

Конструкции группировки часто используются только для применения квантификаторов к нескольким языковым элементам, а захваченные подстроки не представляют интереса. Например, если следующее регулярное выражение,

```
\b\(?((\w+),?\s?)+[\.!?]\)?
```

предназначено только для извлечения предложений, которые оканчиваются на точку, восклицательный или вопросительный знак из документа, и только полученное предложение (в объекте [Match](xref:System.Text.RegularExpressions.Match)) представляет интерес, а отдельные слова в коллекции — нет. 

Захватываемые группы, которые не используются в последствии, могут потреблять много ресурсов, так как механизм регулярных выражений должен заполнить объекты [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) и [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) коллекции. В качестве альтернативы можно использовать параметр [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) или встроенный параметр **n**, чтобы указать, что только допустимые выделения являются явно именованными или нумерованными группами, обозначенными конструкцией **(?<**_name_**>** _subexpression_**)**. 

Следующий пример отображает сведения о сопоставлениях, возвращаемых шаблоном регулярного выражения `\b\(?((\w+),?\s?)+[\.!?]\)?`, если метод [Match](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.Int32)) вызывается с параметром [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) или без него. Как видно в результатах выполнения первого вызова метода, механизм регулярных выражений полностью заполняет объекты коллекции [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) и [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) данными о захваченных подстроках. Так как второй метод вызывается с параметром options, для которого задано значение [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture), он не записывает информацию о группах.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is the first sentence. Is it the beginning " + 
                     "of a literary masterpiece? I think not. Instead, " + 
                     "it is a nonsensical paragraph.";
      string pattern = @"\b\(?((?>\w+),?\s?)+[\.!?]\)?";
      Console.WriteLine("With implicit captures:");
      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine("The match: {0}", match.Value);
         int groupCtr = 0;
         foreach (Group group in match.Groups)
         {
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value);
            groupCtr++;
            int captureCtr = 0;
            foreach (Capture capture in group.Captures)
            {
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value);
               captureCtr++;
            }
         }
      }
      Console.WriteLine();
      Console.WriteLine("With explicit captures only:");
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.ExplicitCapture))
      {
         Console.WriteLine("The match: {0}", match.Value);
         int groupCtr = 0;
         foreach (Group group in match.Groups)
         {
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value);
            groupCtr++;
            int captureCtr = 0;
            foreach (Capture capture in group.Captures)
            {
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value);
               captureCtr++;
            }
         }
      }
   }
}
// The example displays the following output:
//    With implicit captures:
//    The match: This is the first sentence.
//       Group 0: This is the first sentence.
//          Capture 0: This is the first sentence.
//       Group 1: sentence
//          Capture 0: This
//          Capture 1: is
//          Capture 2: the
//          Capture 3: first
//          Capture 4: sentence
//       Group 2: sentence
//          Capture 0: This
//          Capture 1: is
//          Capture 2: the
//          Capture 3: first
//          Capture 4: sentence
//    The match: Is it the beginning of a literary masterpiece?
//       Group 0: Is it the beginning of a literary masterpiece?
//          Capture 0: Is it the beginning of a literary masterpiece?
//       Group 1: masterpiece
//          Capture 0: Is
//          Capture 1: it
//          Capture 2: the
//          Capture 3: beginning
//          Capture 4: of
//          Capture 5: a
//          Capture 6: literary
//          Capture 7: masterpiece
//       Group 2: masterpiece
//          Capture 0: Is
//          Capture 1: it
//          Capture 2: the
//          Capture 3: beginning
//          Capture 4: of
//          Capture 5: a
//          Capture 6: literary
//          Capture 7: masterpiece
//    The match: I think not.
//       Group 0: I think not.
//          Capture 0: I think not.
//       Group 1: not
//          Capture 0: I
//          Capture 1: think
//          Capture 2: not
//       Group 2: not
//          Capture 0: I
//          Capture 1: think
//          Capture 2: not
//    The match: Instead, it is a nonsensical paragraph.
//       Group 0: Instead, it is a nonsensical paragraph.
//          Capture 0: Instead, it is a nonsensical paragraph.
//       Group 1: paragraph
//          Capture 0: Instead,
//          Capture 1: it
//          Capture 2: is
//          Capture 3: a
//          Capture 4: nonsensical
//          Capture 5: paragraph
//       Group 2: paragraph
//          Capture 0: Instead
//          Capture 1: it
//          Capture 2: is
//          Capture 3: a
//          Capture 4: nonsensical
//          Capture 5: paragraph
//    
//    With explicit captures only:
//    The match: This is the first sentence.
//       Group 0: This is the first sentence.
//          Capture 0: This is the first sentence.
//    The match: Is it the beginning of a literary masterpiece?
//       Group 0: Is it the beginning of a literary masterpiece?
//          Capture 0: Is it the beginning of a literary masterpiece?
//    The match: I think not.
//       Group 0: I think not.
//          Capture 0: I think not.
//    The match: Instead, it is a nonsensical paragraph.
//       Group 0: Instead, it is a nonsensical paragraph.
//          Capture 0: Instead, it is a nonsensical paragraph.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is the first sentence. Is it the beginning " + _
                            "of a literary masterpiece? I think not. Instead, " + _
                            "it is a nonsensical paragraph."
      Dim pattern As String = "\b\(?((?>\w+),?\s?)+[\.!?]\)?"
      Console.WriteLine("With implicit captures:")
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("The match: {0}", match.Value)
         Dim groupCtr As Integer = 0
         For Each group As Group In match.Groups
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value)
            groupCtr += 1
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value)
               captureCtr += 1
            Next
         Next
      Next
      Console.WriteLine()
      Console.WriteLine("With explicit captures only:")
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.ExplicitCapture)
         Console.WriteLine("The match: {0}", match.Value)
         Dim groupCtr As Integer = 0
         For Each group As Group In match.Groups
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value)
            groupCtr += 1
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value)
               captureCtr += 1
            Next
         Next
      Next
   End Sub
End Module
' The example displays the following output:
'    With implicit captures:
'    The match: This is the first sentence.
'       Group 0: This is the first sentence.
'          Capture 0: This is the first sentence.
'       Group 1: sentence
'          Capture 0: This
'          Capture 1: is
'          Capture 2: the
'          Capture 3: first
'          Capture 4: sentence
'       Group 2: sentence
'          Capture 0: This
'          Capture 1: is
'          Capture 2: the
'          Capture 3: first
'          Capture 4: sentence
'    The match: Is it the beginning of a literary masterpiece?
'       Group 0: Is it the beginning of a literary masterpiece?
'          Capture 0: Is it the beginning of a literary masterpiece?
'       Group 1: masterpiece
'          Capture 0: Is
'          Capture 1: it
'          Capture 2: the
'          Capture 3: beginning
'          Capture 4: of
'          Capture 5: a
'          Capture 6: literary
'          Capture 7: masterpiece
'       Group 2: masterpiece
'          Capture 0: Is
'          Capture 1: it
'          Capture 2: the
'          Capture 3: beginning
'          Capture 4: of
'          Capture 5: a
'          Capture 6: literary
'          Capture 7: masterpiece
'    The match: I think not.
'       Group 0: I think not.
'          Capture 0: I think not.
'       Group 1: not
'          Capture 0: I
'          Capture 1: think
'          Capture 2: not
'       Group 2: not
'          Capture 0: I
'          Capture 1: think
'          Capture 2: not
'    The match: Instead, it is a nonsensical paragraph.
'       Group 0: Instead, it is a nonsensical paragraph.
'          Capture 0: Instead, it is a nonsensical paragraph.
'       Group 1: paragraph
'          Capture 0: Instead,
'          Capture 1: it
'          Capture 2: is
'          Capture 3: a
'          Capture 4: nonsensical
'          Capture 5: paragraph
'       Group 2: paragraph
'          Capture 0: Instead
'          Capture 1: it
'          Capture 2: is
'          Capture 3: a
'          Capture 4: nonsensical
'          Capture 5: paragraph
'    
'    With explicit captures only:
'    The match: This is the first sentence.
'       Group 0: This is the first sentence.
'          Capture 0: This is the first sentence.
'    The match: Is it the beginning of a literary masterpiece?
'       Group 0: Is it the beginning of a literary masterpiece?
'          Capture 0: Is it the beginning of a literary masterpiece?
'    The match: I think not.
'       Group 0: I think not.
'          Capture 0: I think not.
'    The match: Instead, it is a nonsensical paragraph.
'       Group 0: Instead, it is a nonsensical paragraph.
'          Capture 0: Instead, it is a nonsensical paragraph.
```

Шаблон регулярного выражения `\b\(?((?>\w+),?\s?)+[\.!?]\)?` определяется, как показано в следующей таблице.

Шаблон | Описание
------- | ----------- 
`\b` | Начало на границе слова.
`\(?` | Сопоставляется ноль или один экземпляр открывающих круглых скобок ("(").
`(?>\w+),?` | Сопоставляется один или несколько словообразующих символов, за которыми следует ноль или одна запятая. При сопоставлении словообразующих символов обратный поиск не применяется.
`\s?` | Совпадение с нулем или одним символом пробела.
`((\w+),?\s?)+` | Один или несколько раз выделяет комбинацию из одного или нескольких символов, нуля или одной запятой, нуля или одного пробела.
`[\.!?]\)?` | Сопоставляются любые из трех знаков пунктуации, за которыми следует ноль или одна закрывающая круглая скобка (")").
 
Вы также можете использовать встроенный элемент **(?n)**, чтобы отключить автоматическое выделение. Следующий пример изменяет предыдущий шаблон регулярного выражения, чтобы использовать встроенный элемент **(?n)** вместо параметра [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture).

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is the first sentence. Is it the beginning " + 
                     "of a literary masterpiece? I think not. Instead, " + 
                     "it is a nonsensical paragraph.";
      string pattern = @"(?n)\b\(?((?>\w+),?\s?)+[\.!?]\)?";

      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine("The match: {0}", match.Value);
         int groupCtr = 0;
         foreach (Group group in match.Groups)
         {
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value);
            groupCtr++;
            int captureCtr = 0;
            foreach (Capture capture in group.Captures)
            {
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value);
               captureCtr++;
            }
         }
      }
   }
}
// The example displays the following output:
//       The match: This is the first sentence.
//          Group 0: This is the first sentence.
//             Capture 0: This is the first sentence.
//       The match: Is it the beginning of a literary masterpiece?
//          Group 0: Is it the beginning of a literary masterpiece?
//             Capture 0: Is it the beginning of a literary masterpiece?
//       The match: I think not.
//          Group 0: I think not.
//             Capture 0: I think not.
//       The match: Instead, it is a nonsensical paragraph.
//          Group 0: Instead, it is a nonsensical paragraph.
//             Capture 0: Instead, it is a nonsensical paragraph.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is the first sentence. Is it the beginning " + _
                            "of a literary masterpiece? I think not. Instead, " + _
                            "it is a nonsensical paragraph."
      Dim pattern As String = "(?n)\b\(?((?>\w+),?\s?)+[\.!?]\)?"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("The match: {0}", match.Value)
         Dim groupCtr As Integer = 0
         For Each group As Group In match.Groups
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value)
            groupCtr += 1
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value)
               captureCtr += 1
            Next
         Next
      Next
   End Sub
End Module
' The example displays the following output:
'       The match: This is the first sentence.
'          Group 0: This is the first sentence.
'             Capture 0: This is the first sentence.
'       The match: Is it the beginning of a literary masterpiece?
'          Group 0: Is it the beginning of a literary masterpiece?
'             Capture 0: Is it the beginning of a literary masterpiece?
'       The match: I think not.
'          Group 0: I think not.
'             Capture 0: I think not.
'       The match: Instead, it is a nonsensical paragraph.
'          Group 0: Instead, it is a nonsensical paragraph.
'             Capture 0: Instead, it is a nonsensical paragraph.
```

Наконец, вы можете использовать встроенный элемент группы **(?n:)**, чтобы отключить автоматическое выделение для отдельных групп. Следующий пример изменяет предыдущий шаблон, чтобы отключить неименованные выделения во внешней группе, `((?>\w+),?\s?)`. Обратите внимание, что при этом подавляются неименованные выделения и во внутренней группе.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is the first sentence. Is it the beginning " + 
                     "of a literary masterpiece? I think not. Instead, " + 
                     "it is a nonsensical paragraph.";
      string pattern = @"\b\(?(?n:(?>\w+),?\s?)+[\.!?]\)?";

      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine("The match: {0}", match.Value);
         int groupCtr = 0;
         foreach (Group group in match.Groups)
         {
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value);
            groupCtr++;
            int captureCtr = 0;
            foreach (Capture capture in group.Captures)
            {
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value);
               captureCtr++;
            }
         }
      }
   }
}
// The example displays the following output:
//       The match: This is the first sentence.
//          Group 0: This is the first sentence.
//             Capture 0: This is the first sentence.
//       The match: Is it the beginning of a literary masterpiece?
//          Group 0: Is it the beginning of a literary masterpiece?
//             Capture 0: Is it the beginning of a literary masterpiece?
//       The match: I think not.
//          Group 0: I think not.
//             Capture 0: I think not.
//       The match: Instead, it is a nonsensical paragraph.
//          Group 0: Instead, it is a nonsensical paragraph.
//             Capture 0: Instead, it is a nonsensical paragraph.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is the first sentence. Is it the beginning " + _
                            "of a literary masterpiece? I think not. Instead, " + _
                            "it is a nonsensical paragraph."
      Dim pattern As String = "\b\(?(?n:(?>\w+),?\s?)+[\.!?]\)?"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("The match: {0}", match.Value)
         Dim groupCtr As Integer = 0
         For Each group As Group In match.Groups
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value)
            groupCtr += 1
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value)
               captureCtr += 1
            Next
         Next
      Next
   End Sub
End Module
' The example displays the following output:
'       The match: This is the first sentence.
'          Group 0: This is the first sentence.
'             Capture 0: This is the first sentence.
'       The match: Is it the beginning of a literary masterpiece?
'          Group 0: Is it the beginning of a literary masterpiece?
'             Capture 0: Is it the beginning of a literary masterpiece?
'       The match: I think not.
'          Group 0: I think not.
'             Capture 0: I think not.
'       The match: Instead, it is a nonsensical paragraph.
'          Group 0: Instead, it is a nonsensical paragraph.
'             Capture 0: Instead, it is a nonsensical paragraph.
```

## <a name="compiled-regular-expressions"></a>Скомпилированные регулярные выражения

По умолчанию регулярные выражения в .NET интерпретируются. Когда создается экземпляр объекта [Regex](xref:System.Text.RegularExpressions.Regex) или вызывается статичный метод [Regex](xref:System.Text.RegularExpressions.Regex), шаблон регулярного выражения преобразуется в набор настраиваемых кодов операций, а интерпретатор использует их для выполнения регулярного выражения. С этим связан компромисс: затраты на инициализацию механизма регулярных выражений уменьшаются за счет производительности во время выполнения.

Вместо интерпретируемых регулярных выражений можно использовать скомпилированные регулярные выражения, указав параметр [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled). В этом случае при передаче шаблона механизму регулярных выражений он разбивается на набор кодов операций и преобразуется в инструкции MSIL, которые можно передать напрямую среде CLR. Скомпилированные регулярные выражения повышают производительность во время выполнения, но за счет более длительной инициализации.

> [!NOTE]
> Чтобы скомпилировать регулярное выражение, необходимо передать значение [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) параметру options конструктора класса [Regex](xref:System.Text.RegularExpressions.Regex) или статичного метода сопоставления шаблона. Этот параметр не может быть указан как встроенный. 
 

Вы можете использовать скомпилированные регулярные выражения в вызовах статичных регулярных выражений и регулярных выражений экземпляров. В статичных регулярных выражениях параметр [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) передается в параметр options метода сопоставления шаблона регулярного выражения. В регулярных выражениях экземпляра он передается в параметр options конструктора класса [Regex](xref:System.Text.RegularExpressions.Regex). В обоих случаях это повышает производительность. 

Однако такой рост производительности возможен только в следующих условиях:

* Объект [Regex](xref:System.Text.RegularExpressions.Regex), представляющий определенное регулярное выражение, используется в нескольких вызовах методов сопоставления шаблона регулярного выражения.

* Объект [Regex](xref:System.Text.RegularExpressions.Regex) не может выходить за область применения, поэтому его можно использовать повторно.

* Статичное регулярное выражение используется в нескольких вызовах методов сопоставления шаблона регулярного выражения. (Рост производительности возможен, так как регулярные выражения, используемые в вызовах статичных методов, кэшируются механизмом регулярных выражений.) 

## <a name="ignore-white-space"></a>Пропуск пробелов

По умолчанию пробел в шаблоне регулярного выражения учитывается. Он заставляет механизм регулярных выражений сопоставлять символ пробела во входной строке. Из-за этого регулярные выражения `"\b\w+\s"` и `"\b\w+ "` практически аналогичны. Кроме того, если в шаблоне регулярного выражения найден символ решетки (**#**), он интерпретируется как литерал, который необходимо сопоставить.

Параметр [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace) или встроенный параметр **x** меняет такое поведение по умолчанию следующим образом.

* Неэкранированный пробел в шаблоне регулярного выражения игнорируется. Чтобы включить пробелы в шаблон регулярного выражения, их необходимо экранировать (например, как **\s** или "**\** ").

* Символ решетки (**#**) интерпретируется как начало комментария, а не литерал. Весь текст в шаблоне регулярного выражения с символа **#** до конца строки интерпретируется как комментарий.

Однако в следующих случаях пробелы в регулярном выражении не игнорируются, даже если указан параметр [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace). 

* Пробел в классе символов всегда интерпретируется как литерал. Например, шаблон регулярного выражения `[ .,;:]` сопоставляет любой отдельный символ пробела, точки, запятой, точки с запятой и двоеточия. 

* Пробел не допускается в квантификаторах, окруженных квадратными скобками, например в **{**_n_**}**, **{**_n_**,}** и **{**_n_**,**_m_**}**. Например, шаблон регулярного выражения **\d{1. 3}** не сопоставляет последовательности цифр из одной до трех цифр, так как он содержит пробел. 

* Пробел не допускается в последовательности символов, предоставляющей языковой элемент. Пример: 

    * Языковой элемент **(?:**_subexpression_**)** представляет незахватываемую группу, а часть **(?:** не может содержать пробелы. Шаблон **(? :**_subexpression_**)** вызывает исключение [ArgumentException](xref:System.ArgumentException) во время выполнения, так как механизм регулярных выражений не может проанализировать шаблон, а шаблону **(? :**_subexpression_**)** не удается сопоставить *subexpression*.

    * Языковой элемент **\p{**_name_**}**, представляющий категорию Юникода или именованный блок, не может содержать пробелы в части **\p{**. Если все-таки добавить пробел, элемент вызовет исключение [ArgumentException](xref:System.ArgumentException) во время выполнения. 

Включение этого параметра позволяет упростить регулярные выражения, синтаксический анализ и понимание которых зачастую вызывают затруднения. Это улучшает читаемость и позволяет документировать регулярное выражение. 

В этом примере определяется следующий шаблон регулярного выражения:

`\b \(? ( (?>\w+) ,?\s? )+ [\.!?] \)? # Matches an entire sentence`.

Этот шаблон похож на тот, что был определен в разделе [Только явные захваты](#explicit-captures-only), но в нем используется параметр [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace) для пропуска пробелов в шаблоне.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is the first sentence. Is it the beginning " + 
                     "of a literary masterpiece? I think not. Instead, " + 
                     "it is a nonsensical paragraph.";
      string pattern = @"\b\(?((?>\w+),?\s?)+[\.!?]\)?";

      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnorePatternWhitespace))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       This is the first sentence.
//       Is it the beginning of a literary masterpiece?
//       I think not.
//       Instead, it is a nonsensical paragraph.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is the first sentence. Is it the beginning " + _
                            "of a literary masterpiece? I think not. Instead, " + _
                            "it is a nonsensical paragraph."
      Dim pattern As String = "\b \(? ( (?>\w+) ,?\s? )+  [\.!?] \)? # Matches an entire sentence."

      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnorePatternWhitespace)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       This is the first sentence.
'       Is it the beginning of a literary masterpiece?
'       I think not.
'       Instead, it is a nonsensical paragraph.
```

Следующий пример использует встроенный параметр **(?x)** для пропуска пробелов.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is the first sentence. Is it the beginning " + 
                     "of a literary masterpiece? I think not. Instead, " + 
                     "it is a nonsensical paragraph.";
      string pattern = @"(?x)\b \(? ( (?>\w+) ,?\s? )+  [\.!?] \)? # Matches an entire sentence.";

      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       This is the first sentence.
//       Is it the beginning of a literary masterpiece?
//       I think not.
//       Instead, it is a nonsensical paragraph.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is the first sentence. Is it the beginning " + _
                            "of a literary masterpiece? I think not. Instead, " + _
                            "it is a nonsensical paragraph."
      Dim pattern As String = "(?x)\b \(? ( (?>\w+) ,?\s? )+  [\.!?] \)? # Matches an entire sentence."

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       This is the first sentence.
'       Is it the beginning of a literary masterpiece?
'       I think not.
'       Instead, it is a nonsensical paragraph.
```

## <a name="right-to-left-mode"></a>Режим "справа налево"

По умолчанию механизм регулярных выражений выполняет поиска слева направо. Направление поиска можно изменить с помощью параметра [RegexOptions.RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft). Поиск автоматически будет начинаться с последнего символа строки. Для методов сопоставления шаблона с параметром начальной позиции, таких как [Regex.Match(String, Int32)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.Int32)), начальная позиция — это индекс самого правого символа, с которого начинается поиск. 

> [!NOTE]
> Чтобы включить режим "справа налево", необходимо передать значение [RegexOptions.RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft) параметру options конструктора класса [Regex](xref:System.Text.RegularExpressions.Regex) или статичного метода сопоставления шаблона. Этот параметр не может быть указан как встроенный. 
 

Параметр [RegexOptions.RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft) меняет только направление поиска, а не интерпретирует шаблон регулярного выражения справа налево. Например, регулярное выражение `\bb\w+\s` сопоставляет слова, которые начинаются с буквы "b" и за которыми следует пробел. В следующем примере входная строка состоит из трех слов, которые содержат одну или несколько букв "b". Первое слово начинается с "b", второе заканчивается на "b", а в третьем буква "b" находится в середине слова. Как видно из результата примера, только первое слово соответствует шаблону регулярного выражения. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\bb\w+\s";
      string input = "builder rob rabble";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.RightToLeft))
         Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);     
   }
}
// The example displays the following output:
//       'builder ' found at position 0.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\bb\w+\s"
      Dim input As String = "builder rob rabble"
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.RightToLeft)
         Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)     
      Next
   End Sub
End Module
' The example displays the following output:
'       'builder ' found at position 0.
```

Кроме того, обратите внимание, что утверждение просмотра вперед (языковой элемент **(?**=_subexpression_**)**) и утверждение просмотра назад (языковой элемент **(?<**=_subexpression_**)**) не меняют направление поиска. Утверждения просмотра вперед выполняют поиск вправо, а утверждения просмотра назад — влево. Например, регулярное выражение `(?<=\d{1,2}\s)\w+,?\s\d{4}` использует утверждения просмотра назад для проверки наличия даты, перед которой идет название месяца. Затем регулярное выражение сопоставляет месяц и год. Информацию об утверждениях поиска вперед и назад см. в статье [Конструкции группировки в регулярных выражениях](grouping.md).

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "1 May 1917", "June 16, 2003" };
      string pattern = @"(?<=\d{1,2}\s)\w+,?\s\d{4}";

      foreach (string input in inputs)
      {
         Match match = Regex.Match(input, pattern, RegexOptions.RightToLeft);
         if (match.Success)
            Console.WriteLine("The date occurs in {0}.", match.Value);
         else
            Console.WriteLine("{0} does not match.", input);
      }
   }
}
// The example displays the following output:
//       The date occurs in May 1917.
//       June 16, 2003 does not match.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "1 May 1917", "June 16, 2003" }
      Dim pattern As String = "(?<=\d{1,2}\s)\w+,?\s\d{4}"

      For Each input As String In inputs
         Dim match As Match = Regex.Match(input, pattern, RegexOptions.RightToLeft)
         If match.Success Then
            Console.WriteLine("The date occurs in {0}.", match.Value)
         Else
            Console.WriteLine("{0} does not match.", input)
         End If
      Next
   End Sub
End Module
' The example displays the following output:
'       The date occurs in May 1917.
'       June 16, 2003 does not match.
```

Шаблон регулярного выражения определяется, как показано в следующей таблице.

Шаблон | Описание
------- | ----------- 
`(?<=\d{1,2}\s)` | Слева от начала сопоставления должна идти одна или две десятичных цифры, за которыми следует пробел.
`\w+` | Совпадение с одним или несколькими символами слова.
`,?` | Выделяется ноль или один символ запятой.
`\s` | Соответствует пробелу.
`\d{4}` | Выделяются 4 десятичные цифры.
 
## <a name="ecmascript-matching-behavior"></a>Поведение сопоставления ECMAScript

По умолчанию механизм регулярных выражений использует каноническое поведение при сопоставлении шаблона регулярного выражения с входным текстом. Но вы можете использовать поведение сопоставления ECMAScript, указав параметр [RegexOptions.ECMAScript](xref:System.Text.RegularExpressions.RegexOptions.ECMAScript). 

> [!NOTE]
> Чтобы включить поведение ECMAScript, необходимо передать значение [RegexOptions.ECMAScript](xref:System.Text.RegularExpressions.RegexOptions.ECMAScript) параметру options конструктора класса [Regex](xref:System.Text.RegularExpressions.Regex) или статичного метода сопоставления шаблона. Этот параметр не может быть указан как встроенный. 
 
Параметр [RegexOptions.ECMAScript](xref:System.Text.RegularExpressions.RegexOptions.ECMAScript) можно использоваться только вместе с параметрами [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase) и [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline). При использовании других параметров в регулярном выражении возникает исключение [ArgumentOutOfRangeException](xref:System.ArgumentOutOfRangeException).

Поведение регулярных выражений ECMAScript и канонических регулярных выражений отличается в трех аспектах: синтаксис класса символов, ссылающиеся на себя захватываемые группы и интерпретация восьмеричных значений и обратных ссылок. 

* Синтаксис класса символов. Так как канонические регулярные выражения поддерживают Юникод, а ECMAScript — нет, синтаксис классов символов в ECMAScript более ограничен, а некоторые языковые элементы класса символов обладают другим значением. Например, ECMAScript не поддерживает такие языковые элементы, как категория Юникода или элементы блока *\p* и **\P**. Аналогичным образом элемент **\w**, который сопоставляет словообразующее слово, эквивалентен классу символов **[a–zA–Z_0–9]** при использовании ECMAScript и **[\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]** при использовании канонического поведения. Дополнительные сведения см. в статье [Классы символов в регулярных выражениях](classes.md).

  Следующий пример иллюстрирует разницу между каноническим сопоставлением шаблона и ECMAScript. В нем определяется регулярное выражение, `\b(\w+\s*)+`, сопоставляющее слова, за которыми следуют пробелы. Входные данные состоят из двух строк, одна из которых использует латиницу, а другая — кириллицу. Как видно из результата, при вызове метода [Regex.IsMatch(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)), использующего сопоставление ECMAScript, не удается сопоставить слова на кириллице, а при вызове метода, использующего каноническое сопоставление — удается. 

  ```csharp
  using System;
  using System.Text.RegularExpressions;
  
  public class Example
  {
     public static void Main()
     {
        string[] values = { "целый мир", "the whole world" };
        string pattern = @"\b(\w+\s*)+";
        foreach (var value in values)
        {
           Console.Write("Canonical matching: ");
           if (Regex.IsMatch(value, pattern))
              Console.WriteLine("'{0}' matches the pattern.", value);
           else
              Console.WriteLine("{0} does not match the pattern.", value);
  
           Console.Write("ECMAScript matching: ");
           if (Regex.IsMatch(value, pattern, RegexOptions.ECMAScript))
              Console.WriteLine("'{0}' matches the pattern.", value);
           else
              Console.WriteLine("{0} does not match the pattern.", value);
           Console.WriteLine();
        }
     }
  }
  // The example displays the following output:
  //       Canonical matching: 'целый мир' matches the pattern.
  //       ECMAScript matching: целый мир does not match the pattern.
  //       
  //       Canonical matching: 'the whole world' matches the pattern.
  //       ECMAScript matching: 'the whole world' matches the pattern.
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Public Sub Main()
        Dim values() As String = { "целый мир", "the whole world" }
        Dim pattern As String = "\b(\w+\s*)+"
        For Each value In values
           Console.Write("Canonical matching: ")
           If Regex.IsMatch(value, pattern)
              Console.WriteLine("'{0}' matches the pattern.", value)
           Else
              Console.WriteLine("{0} does not match the pattern.", value)
           End If

           Console.Write("ECMAScript matching: ")
           If Regex.IsMatch(value, pattern, RegexOptions.ECMAScript)
              Console.WriteLine("'{0}' matches the pattern.", value)
           Else
              Console.WriteLine("{0} does not match the pattern.", value)
           End If
           Console.WriteLine()
        Next
     End Sub
  End Module
  ' The example displays the following output:
  '       Canonical matching: 'целый мир' matches the pattern.
  '       ECMAScript matching: целый мир does not match the pattern.
  '       
  '       Canonical matching: 'the whole world' matches the pattern.
  '       ECMAScript matching: 'the whole world' matches the pattern.
  ```

* Ссылающиеся на себя захватываемые группы Класс захвата регулярного выражения с обратной ссылкой на себя необходимо обновлять после каждой итерации выделения. Как показано в следующем примере, это позволяет регулярному выражению `((a+)(\1) ?)+` сопоставить входную строку " aa aaaa aaaaaa " при использовании ECMAScript, но не канонического сопоставления. 

  ```csharp
  using System;
  using System.Text.RegularExpressions;

  public class Example
  {
     static string pattern;
  
     public static void Main()
     {
        string input = "aa aaaa aaaaaa "; 
        pattern = @"((a+)(\1) ?)+";
  
        // Match input using canonical matching.
        AnalyzeMatch(Regex.Match(input, pattern));

        // Match input using ECMAScript.
        AnalyzeMatch(Regex.Match(input, pattern, RegexOptions.ECMAScript));
     }   

     private static void AnalyzeMatch(Match m)
     {
        if (m.Success)
        {
           Console.WriteLine("'{0}' matches {1} at position {2}.",  
                             pattern, m.Value, m.Index);
           int grpCtr = 0;
           foreach (Group grp in m.Groups)
           {
              Console.WriteLine("   {0}: '{1}'", grpCtr, grp.Value);
              grpCtr++;
              int capCtr = 0;
              foreach (Capture cap in grp.Captures)
              {
                 Console.WriteLine("      {0}: '{1}'", capCtr, cap.Value);
                 capCtr++;
              }
           }
        }
        else
        {
           Console.WriteLine("No match found.");
        }   
        Console.WriteLine();
     }
  }
  // The example displays the following output:
  //    No match found.
  //    
  //    '((a+)(\1) ?)+' matches aa aaaa aaaaaa  at position 0.
  //       0: 'aa aaaa aaaaaa '
  //          0: 'aa aaaa aaaaaa '
  //       1: 'aaaaaa '
  //          0: 'aa '
  //          1: 'aaaa '
  //          2: 'aaaaaa '
  //       2: 'aa'
  //          0: 'aa'
  //          1: 'aa'
  //          2: 'aa'
  //       3: 'aaaa '
  //          0: ''
  //          1: 'aa '
  //          2: 'aaaa '
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Dim pattern As String

     Public Sub Main()
        Dim input As String = "aa aaaa aaaaaa " 
        pattern = "((a+)(\1) ?)+"
  
        ' Match input using canonical matching.
        AnalyzeMatch(Regex.Match(input, pattern))

        ' Match input using ECMAScript.
        AnalyzeMatch(Regex.Match(input, pattern, RegexOptions.ECMAScript))
     End Sub   

     Private Sub AnalyzeMatch(m As Match)
        If m.Success
           Console.WriteLine("'{0}' matches {1} at position {2}.", _ 
                             pattern, m.Value, m.Index)
           Dim grpCtr As Integer = 0
           For Each grp As Group In m.Groups
              Console.WriteLine("   {0}: '{1}'", grpCtr, grp.Value)
              grpCtr += 1
              Dim capCtr As Integer = 0
              For Each cap As Capture In grp.Captures
                 Console.WriteLine("      {0}: '{1}'", capCtr, cap.Value)
                 capCtr += 1
              Next
           Next
        Else
           Console.WriteLine("No match found.")
        End If   
        Console.WriteLine()
     End Sub
  End Module
  ' The example displays the following output:
  '    No match found.
  '    
  '    '((a+)(\1) ?)+' matches aa aaaa aaaaaa  at position 0.
  '       0: 'aa aaaa aaaaaa '
  '          0: 'aa aaaa aaaaaa '
  '       1: 'aaaaaa '
  '          0: 'aa '
  '          1: 'aaaa '  
  '          2: 'aaaaaa '
  '       2: 'aa'
  '          0: 'aa'
  '          1: 'aa'
  '          2: 'aa'
  '       3: 'aaaa '
  '          0: ''
  '          1: 'aa '
  '          2: 'aaaa '
  ``

  The regular expression is defined as shown in the following table.

Pattern | Description
------- | ----------- 
`(a+)` | Match the letter "a" one or more times. This is the second capturing group.
`(\1)` | Match the substring captured by the first capturing group. This is the third capturing group.
`?` | Match zero or one space characters.
`((a+)(\1) ?)+` | Match the pattern of one or more "a" characters followed by a string that matches the first capturing group followed by zero or one space characters one or more times. This is the first capturing group.
  
* Resolution of ambiguities between octal escapes and backreferences. The following table summarizes the differences in octal versus backreference interpretation by canonical and ECMAScript regular expressions.

Regular expression | Canonical behavior | ECMAScript behavior
------------------ | ------------------ | ------------------- 
`\0` followed by 0 to 2 octal digits | Interpret as an octal. For example, `\044` is always interpreted as an octal value and means "**$**". | Same behavior.
**\** followed by a digit from 1 to 9, followed by no additional decimal digits | Interpret as a backreference. For example, \9 always means backreference 9, even if a ninth capturing group does not exist. If the capturing group does not exist, the regular expression parser throws an [ArgumentException](xref:System.ArgumentException). | If a single decimal digit capturing group exists, backreference to that digit. Otherwise, interpret the value as a literal.
**\** followed by a digit from 1 to 9, followed by additional decimal digits | Interpret the digits as a decimal value. If that capturing group exists, interpret the expression as a backreference. Otherwise, interpret the leading octal digits up to octal 377; that is, consider only the low 8 bits of the value. Interpret the remaining digits as literals. For example, in the expression `\3000`, if capturing group 300 exists, interpret as backreference 300; if capturing group 300 does not exist, interpret as octal 300 followed by 0. | Interpret as a backreference by converting as many digits as possible to a decimal value that can refer to a capture. If no digits can be converted, interpret as an octal by using the leading octal digits up to octal 377; interpret the remaining digits as literals.
 
## Comparison using the invariant culture

By default, when the regular expression engine performs case-insensitive comparisons, it uses the casing conventions of the current culture to determine equivalent uppercase and lowercase characters. 

However, this behavior is undesirable for some types of comparisons, particularly when comparing user input to the names of system resources, such as passwords, files, or URLs. The following example illustrates such as scenario. The code is intended to block access to any resource whose URL is prefaced with **FILE://**. The regular expression attempts a case-insensitive match with the string by using the regular expression `$FILE://`. However, when the current system culture is tr-TR (Turkish-Turkey), "I" is not the uppercase equivalent of "i". As a result, the call to the [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) method returns `false`, and access to the file is allowed. 

```csharp
CultureInfo defaultCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("tr-TR");

string input = "file://c:/Documents.MyReport.doc";
string pattern = "FILE://";

Console.WriteLine("Culture-sensitive matching ({0} culture)...", 
                  Thread.CurrentThread.CurrentCulture.Name);
if (Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase))
   Console.WriteLine("URLs that access files are not allowed.");      
else
   Console.WriteLine("Access to {0} is allowed.", input);

Thread.CurrentThread.CurrentCulture = defaultCulture;
// The example displays the following output:
//       Culture-sensitive matching (tr-TR culture)...
//       Access to file://c:/Documents.MyReport.doc is allowed.
```

```vb
Dim defaultCulture As CultureInfo = Thread.CurrentThread.CurrentCulture
Thread.CurrentThread.CurrentCulture = New CultureInfo("tr-TR")

Dim input As String = "file://c:/Documents.MyReport.doc"
Dim pattern As String = "$FILE://"

Console.WriteLine("Culture-sensitive matching ({0} culture)...", _
                  Thread.CurrentThread.CurrentCulture.Name)
If Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase) Then
   Console.WriteLine("URLs that access files are not allowed.")      
Else
   Console.WriteLine("Access to {0} is allowed.", input)
End If

Thread.CurrentThread.CurrentCulture = defaultCulture
' The example displays the following output:
'       Culture-sensitive matching (tr-TR culture)...
'       Access to file://c:/Documents.MyReport.doc is allowed.
```

> [!NOTE]
>   Подробнее о сравнении строк с учетом регистра и использовании инвариантных региональных параметров см. в разделе [Рекомендации по использованию строк в .NET](best-practices.md).
 
Вместо использования сравнений без учета регистра текущих региональных параметров можно указать параметр [RegexOptions.CultureInvariant](xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant), чтобы игнорировать региональные отличия в языке и использовать соглашения инвариантных региональных параметров.

> [!NOTE]
> Чтобы включить сравнение с использованием инвариантных региональных параметров, необходимо передать значение [RegexOptions.CultureInvariant](xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant) параметру options конструктора класса [Regex](xref:System.Text.RegularExpressions.Regex) или статичного метода сопоставления шаблона. Этот параметр не может быть указан как встроенный. 
 
Следующий пример идентичен предыдущему, но в нем статичный метод [Regex.IsMatch(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) вызывается с параметрами, содержащими [RegexOptions.CultureInvariant](xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant). Даже если в качестве региональных параметров выбрано "Турецкий (Турция)", механизм регулярных выражений сможет успешно сопоставить строки "FILE" и "file" и заблокировать доступ к файлу. 

```csharp
CultureInfo defaultCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("tr-TR");

string input = "file://c:/Documents.MyReport.doc";
string pattern = "FILE://";

Console.WriteLine("Culture-insensitive matching...");
if (Regex.IsMatch(input, pattern, 
                  RegexOptions.IgnoreCase | RegexOptions.CultureInvariant)) 
   Console.WriteLine("URLs that access files are not allowed.");
else
   Console.WriteLine("Access to {0} is allowed.", input);

Thread.CurrentThread.CurrentCulture = defaultCulture;
// The example displays the following output:
//       Culture-insensitive matching...
//       URLs that access files are not allowed.
```

```vb
Dim defaultCulture As CultureInfo = Thread.CurrentThread.CurrentCulture
Thread.CurrentThread.CurrentCulture = New CultureInfo("tr-TR")

Dim input As String = "file://c:/Documents.MyReport.doc"
Dim pattern As String = "$FILE://"

Console.WriteLine("Culture-insensitive matching...")
If Regex.IsMatch(input, pattern, _
               RegexOptions.IgnoreCase Or RegexOptions.CultureInvariant) Then
   Console.WriteLine("URLs that access files are not allowed.")      
Else
   Console.WriteLine("Access to {0} is allowed.", input)
End If
Thread.CurrentThread.CurrentCulture = defaultCulture
' The example displays the following output:
'        Culture-insensitive matching...
'        URLs that access files are not allowed.
```

## <a name="see-also"></a>См. также

[Элементы языка регулярных выражений — краткий справочник](quick-ref.md)




<!--HONumber=Nov16_HO3-->


