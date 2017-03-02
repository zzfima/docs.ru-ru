---
title: "Объектная модель регулярных выражений"
description: "Объектная модель регулярных выражений"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: a1e611ec-c6a2-48c6-9c52-0ed845787621
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 4e8744c6c7a42c3803bf9716a3ae271b7284be3d
ms.lasthandoff: 03/02/2017

---

# <a name="the-regular-expression-object-model"></a>Объектная модель регулярных выражений

В этом разделе описывается объектная модель, используемая при работе с регулярными выражениями в .NET. Он содержит следующие подразделы:

* [Механизм регулярных выражений](#the-regular-expression-engine)

* [Объекты MatchCollection и Match](#the-matchcollection-and-match-objects)

* [Коллекция Group](#the-group-collection)

* [Захватываемая группа](#the-captured-group)

* [Коллекция Capture](#the-capture-collection)

* [Отдельный захват](#the-individual-capture)

## <a name="the-regular-expression-engine"></a>Механизм регулярных выражений

Механизм регулярных выражений в .NET представлен классом [Regex](xref:System.Text.RegularExpressions.Regex). Механизм отвечает за синтаксический анализ и компиляцию регулярного выражение, а также выполнение операций, которые сопоставляют шаблон регулярного выражения с входной строкой. Данный механизм — центральный компонент объектной модели регулярных выражений .NET.

Вы можете использовать механизм регулярных выражений одним из двух способов:

* Вызывая статичные методы класса [Regex](xref:System.Text.RegularExpressions.Regex). Параметры метода включают в себя входную строку и шаблон регулярного выражения. Механизм регулярных выражений кэширует регулярные выражения, которые используются в вызовах статичных методов, чтобы повторные вызовы статичных методов регулярных выражений, применяющие одно и то же регулярное выражение, выполнялись относительно быстро.

* Создавая экземпляр объекта [Regex](xref:System.Text.RegularExpressions.Regex), передавая регулярное выражение конструктору класса. В этом случае объект [Regex](xref:System.Text.RegularExpressions.Regex) не изменяется (доступен только для чтения) и представляет механизм регулярных выражений, который тесно связана с одним регулярным выражением. Так как регулярные выражения, используемые экземплярами Regex, не кэшируются, не следует создавать экземпляр объекта [Regex](xref:System.Text.RegularExpressions.Regex) несколько раз с одним и тем же регулярным выражением.

Вы можете вызывать методы класса [Regex](xref:System.Text.RegularExpressions.Regex), чтобы выполнить следующие операции: 

* определить, соответствует ли строка шаблону регулярного выражения;

* извлечь одно сопоставление или первое сопоставление;

* извлечь все сопоставления;

* заменить сопоставленную подстроку;

* разделить одну строку на массив строк.

Эти операции описаны в следующих разделах.

### <a name="matching-a-regular-expression-pattern"></a>Сопоставление с шаблоном регулярного выражения

Метод [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) возвращает значение `false`, если строка соответствует шаблону; в противном случае возвращается значение `true`. Метод [IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) часто используется для проверки входной строки. Например, следующий код проверяет, содержит ли строка допустимый номер социального страхования для США.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] values = { "111-22-3333", "111-2-3333"};
      string pattern = @"^\d{3}-\d{2}-\d{4}$";
      foreach (string value in values) {
         if (Regex.IsMatch(value, pattern))
            Console.WriteLine("{0} is a valid SSN.", value);
         else   
            Console.WriteLine("{0}: Invalid", value);
      }
   }
}
// The example displays the following output:
//       111-22-3333 is a valid SSN.
//       111-2-3333: Invalid
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim values() As String = { "111-22-3333", "111-2-3333"}
      Dim pattern As String = "^\d{3}-\d{2}-\d{4}$"
      For Each value As String In values
         If Regex.IsMatch(value, pattern) Then
            Console.WriteLine("{0} is a valid SSN.", value)
         Else   
            Console.WriteLine("{0}: Invalid", value)
         End If   
      Next
   End Sub
End Module
' The example displays the following output:
'       111-22-3333 is a valid SSN.
'       111-2-3333: Invalid
```

Возможные интерпретации шаблона регулярного выражения `^\d{3}-\d{2}-\d{4}$` показаны в следующей таблице.

Шаблон | Описание
------- | ----------- 
`^` | Выделение начала входной строки.
`\d{3}` | Совпадение с тремя десятичными цифрами.
`-` | Выделение дефиса.
`\d{2}` | Совпадение с двумя десятичными цифрами.
`-` | Выделение дефиса.
`\d{4}` | Выделяются&4; десятичные цифры.
`$` | Соответствует концу входной строки.
 
### <a name="extracting-a-single-match-or-the-first-match"></a>Извлечение одного соответствия или первого соответствия

Метод [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) возвращает объект [Match](xref:System.Text.RegularExpressions.Match), который содержит сведения о первой подстроке, соответствующей шаблону регулярного выражения. Если свойство `Match.Success` возвращает значение `true` (найдено соответствие), вы можете получить информацию о последующих соответствиях, вызвав метод [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch). Этот метод можно вызывать, пока свойство `Match.Success` не вернет значение `false`. Например, следующий код использует метод [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String)) для поиска первого вхождения повторяющегося слова в строке. Затем вызывается метод [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch) для поиска других вхождений. В примере демонстрируется просмотр свойства `Match.Success` после каждого вызова метода, чтобы определить, было ли текущее сопоставление успешным и следует ли вызывать метод [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch).

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is a a farm that that raises dairy cattle."; 
      string pattern = @"\b(\w+)\W+(\1)\b";
      Match match = Regex.Match(input, pattern);
      while (match.Success)
      {
         Console.WriteLine("Duplicate '{0}' found at position {1}.",  
                           match.Groups[1].Value, match.Groups[2].Index);
         match = match.NextMatch();
      }                       
   }
}
// The example displays the following output:
//       Duplicate 'a' found at position 10.
//       Duplicate 'that' found at position 22.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is a a farm that that raises dairy cattle." 
      Dim pattern As String = "\b(\w+)\W+(\1)\b"
      Dim match As Match = Regex.Match(input, pattern)
      Do While match.Success
         Console.WriteLine("Duplicate '{0}' found at position {1}.", _ 
                           match.Groups(1).Value, match.Groups(2).Index)
         match = match.NextMatch()
      Loop                       
   End Sub
End Module
' The example displays the following output:
'       Duplicate 'a' found at position 10.
'       Duplicate 'that' found at position 22.
```

Возможные интерпретации шаблона регулярного выражения `\b(\w+)\W+(\1)\b` показаны в следующей таблице.

Шаблон | Описание
------- | ----------- 
`\b` | Сопоставление начинается на границе слова.
`(\w+)` | Совпадение с одним или несколькими символами слова. Это первая группа записи.
`\W+` | Совпадение с одним или большим числом несловообразующих символов.
`(\1)` | Выделение первой захватываемой строки. Это вторая группа записи. 
`\b` | Сопоставление заканчивается на границе слова.
 
### <a name="extracting-all-matches"></a>Извлечение всех соответствий

Метод [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) возвращает объект [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection), содержащий сведения о всех сопоставлениях, найденных механизмом регулярных выражений во входной строке. Например, предыдущий пример можно изменить, чтобы вызывать метод [Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) вместо методов [Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) и [NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch).

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is a a farm that that raises dairy cattle."; 
      string pattern = @"\b(\w+)\W+(\1)\b";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Duplicate '{0}' found at position {1}.",  
                           match.Groups[1].Value, match.Groups[2].Index);
   }
}
// The example displays the following output:
//       Duplicate 'a' found at position 10.
//       Duplicate 'that' found at position 22.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is a a farm that that raises dairy cattle." 
      Dim pattern As String = "\b(\w+)\W+(\1)\b"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Duplicate '{0}' found at position {1}.", _ 
                           match.Groups(1).Value, match.Groups(2).Index)
      Next                       
   End Sub
End Module
' The example displays the following output:
'       Duplicate 'a' found at position 10.
'       Duplicate 'that' found at position 22.
```

### <a name="replacing-a-matched-substring"></a>Замена найденной подстроки

Метод [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) заменяет каждую подстроку, соответствующую шаблону регулярного выражения, на указанную строку или шаблон регулярного выражения и возвращает всю замененную входную строку. Например, следующий код добавляет обозначение денежной единицы США перед десятичным числом в строке.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b\d+\.\d{2}\b";
      string replacement = "$$$&"; 
      string input = "Total Cost: 103.64";
      Console.WriteLine(Regex.Replace(input, pattern, replacement));     
   }
}
// The example displays the following output:
//       Total Cost: $103.64
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b\d+\.\d{2}\b"
      Dim replacement As String = "$$$&" 
      Dim input As String = "Total Cost: 103.64"
      Console.WriteLine(Regex.Replace(input, pattern, replacement))     
   End Sub
End Module
' The example displays the following output:
'       Total Cost: $103.64
```

Возможные интерпретации шаблона регулярного выражения `\b\d+\.\d{2}\b` показаны в следующей таблице.

Шаблон | Описание
------- | ----------- 
`\b` | Совпадение должно начинаться на границе слова.
`\d+` | Совпадение с одной или несколькими десятичными цифрами.
`\.` | Сопоставляется точка.
`\d{2}` | Совпадение с двумя десятичными цифрами.
`\b` | Совпадение должно заканчиваться на границе слова.
 
Шаблон замены `$$$&` интерпретируется, как показано в следующей таблице.

Шаблон | Строка замены
------- | ------------------ 
`$$` | Символ доллара (**$**).
`$&` | Вся сопоставленная подстрока.
 
### <a name="splitting-a-single-string-into-an-array-of-strings"></a>Разделение одной строки на массив строк

Метод [Regex.Split](xref:System.Text.RegularExpressions.Regex.Split(System.String)) разделяет входную строку в позициях, заданных соответствием регулярного выражения. Например, следующий код помещает элементы нумерованного списка в массив строк.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "1. Eggs 2. Bread 3. Milk 4. Coffee 5. Tea";
      string pattern = @"\b\d{1,2}\.\s";
      foreach (string item in Regex.Split(input, pattern))
      {
         if (! String.IsNullOrEmpty(item))
            Console.WriteLine(item);
      }      
   }
}
// The example displays the following output:
//       Eggs
//       Bread
//       Milk
//       Coffee
//       Tea
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "1. Eggs 2. Bread 3. Milk 4. Coffee 5. Tea"
      Dim pattern As String = "\b\d{1,2}\.\s"
      For Each item As String In Regex.Split(input, pattern)
         If Not String.IsNullOrEmpty(item) Then
            Console.WriteLine(item)
         End If
      Next      
   End Sub
End Module
' The example displays the following output:
'       Eggs
'       Bread
'       Milk
'       Coffee
'       Tea
```

Возможные интерпретации шаблона регулярного выражения `\b\d{1,2}\.\s` показаны в следующей таблице.

Шаблон | Описание
------- | -----------
`\b` | Совпадение должно начинаться на границе слова.
`\d{1,2}` | Совпадение с одной или двумя десятичными цифрами.
`\.` | Сопоставляется точка.
`\s` | Соответствует пробелу.
 
## <a name="the-matchcollection-and-match-objects"></a>Объекты MatchCollection и Match

Методы [Regex](xref:System.Text.RegularExpressions.Regex) возвращают два объекта, входящие в объектную модель регулярного выражения: объект [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) и объект [Match](xref:System.Text.RegularExpressions.Match). 

### <a name="the-match-collection"></a>Коллекция Match

Метод [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) возвращает объект [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection), содержащий объекты [Match](xref:System.Text.RegularExpressions.Match), которые представляют все сопоставления, найденные механизмом регулярных выражений, в том порядке, в котором они присутствуют во входной строке. Если соответствий нет, метод возвращает объект [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection), содержащий объект [Match](xref:System.Text.RegularExpressions.Match) без членов. Свойство [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) `Item` позволяет получить доступ к отдельным членам коллекции по индексу (от нуля до значения свойства [MatchCollection.Count](xref:System.Text.RegularExpressions.MatchCollection.Count) минус&1;). Item — это индексатор коллекции (для C#) и свойство по умолчанию (для Visual Basic).

По умолчанию вызов метода [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) использует отложенные вычисления для заполнения объекта [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection). Доступ к свойствам, которым требуется полностью заполненная коллекция, например свойства [MatchCollection.Count](xref:System.Text.RegularExpressions.MatchCollection.Count) и `Item`, может быть связан с дополнительными затратами. Поэтому мы рекомендуем обращаться к коллекции, используя объект [IEnumerator](xref:System.Collections.IEnumerator), возвращаемый методом [MatchCollection.GetEnumerator](xref:System.Text.RegularExpressions.MatchCollection.GetEnumerator). Отдельные языки предоставляют конструкции, такие как `foreach` в C# и For Each в Visual Basic, которые создают оболочку для интерфейса IEnumerator](xref:System.Collections.IEnumerator) коллекции.

В следующем примере используется метод [Regex.Matches(String)](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) для заполнения объекта [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) всеми соответствиями, найденными во входной строке. Пример перечисляет коллекцию, копирует соответствия в массив строк и записывает позиции символов в целочисленный массив.

```csharp
using System;
using System.Collections.Generic;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
       MatchCollection matches;
       List<string> results = new List<string>();
       List<int> matchposition = new List<int>();

       // Create a new Regex object and define the regular expression.
       Regex r = new Regex("abc");
       // Use the Matches method to find all matches in the input string.
       matches = r.Matches("123abc4abcd");
       // Enumerate the collection to retrieve all matches and positions.
       foreach (Match match in matches)
       {
          // Add the match string to the string array.
           results.Add(match.Value);
           // Record the character position where the match was found.
           matchposition.Add(match.Index);
       }
       // List the results.
       for (int ctr = 0; ctr < results.Count; ctr++)
         Console.WriteLine("'{0}' found at position {1}.", 
                           results[ctr], matchposition[ctr]);  
   }
}
// The example displays the following output:
//       'abc' found at position 3.
//       'abc' found at position 7.
```

```vb
Imports System.Collections.Generic
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
       Dim matches As MatchCollection
       Dim results As New List(Of String)
       Dim matchposition As New List(Of Integer)

       ' Create a new Regex object and define the regular expression.
       Dim r As New Regex("abc")
       ' Use the Matches method to find all matches in the input string.
       matches = r.Matches("123abc4abcd")
       ' Enumerate the collection to retrieve all matches and positions.
       For Each match As Match In matches
          ' Add the match string to the string array.
           results.Add(match.Value)
           ' Record the character position where the match was found.
           matchposition.Add(match.Index)
       Next
       ' List the results.
       For ctr As Integer = 0 To results.Count - 1
         Console.WriteLine("'{0}' found at position {1}.", _
                           results(ctr), matchposition(ctr))  
       Next
   End Sub
End Module
' The example displays the following output:
'       'abc' found at position 3.
'       'abc' found at position 7.
```

### <a name="the-match"></a>Класс Match

Класс [Match](xref:System.Text.RegularExpressions.Match) представляет результат одного сопоставления регулярного выражения. Доступ к объектам [Match](xref:System.Text.RegularExpressions.Match) можно получить двумя указанными далее способами.

* Извлекая их из объекта [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection), который возвращается методом Matches. Для извлечения отдельных объектов [Match](xref:System.Text.RegularExpressions.Match) выполните итерацию коллекции, воспользовавшись конструкцией `foreach` (в C#) или `For Each...Next` (в Visual Basic), либо используйте свойство [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) `Item` для извлечения конкретного объекта [Match](xref:System.Text.RegularExpressions.Match) по индексу или по имени. Вы также можете получить отдельные объекты [Match](xref:System.Text.RegularExpressions.Match) из коллекции, циклически проходя по коллекции по индексу (от нуля до числа объектов в коллекции минус&1;). Однако этот метод не использует отложенные вычисления, так как он обращается к свойству [MatchCollection.Count](xref:System.Text.RegularExpressions.MatchCollection.Count). 

  Следующий пример извлекает отдельные объекты [Match](xref:System.Text.RegularExpressions.Match) из объекта [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection), циклически перебирая коллекцию с помощью конструкции `foreach`. Регулярное выражение просто сопоставляет строку "abc" во входной строке.

  ```csharp
  using System;
  using System.Text.RegularExpressions;

  public class Example
  {
     public static void Main()
     {
        string pattern = "abc";
        string input = "abc123abc456abc789";
        foreach (Match match in Regex.Matches(input, pattern))
           Console.WriteLine("{0} found at position {1}.", 
                             match.Value, match.Index);
     }
  }
  // The example displays the following output:
  //       abc found at position 0.
  //       abc found at position 6.
  //       abc found at position 12.
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Public Sub Main()
        Dim pattern As String = "abc"
        Dim input As String = "abc123abc456abc789"
        For Each match As Match In Regex.Matches(input, pattern)
           Console.WriteLine("{0} found at position {1}.", _
                             match.Value, match.Index)
        Next                     
     End Sub
  End Module
  ' The example displays the following output:
  '       abc found at position 0.
  '       abc found at position 6.
  '       abc found at position 12.
  ```

* Вызывая метод [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)), который возвращает объект [Match](xref:System.Text.RegularExpressions.Match), представляющий первое соответствие в строке или ее части. Вы можете определить, найдено ли соответствие, получив значение свойства `Match.Success`. Чтобы извлечь объекты [Match](xref:System.Text.RegularExpressions.Match), представляющие последующие соответствия, вызывайте метод [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch), пока свойство `Success` полученного объекта [Match](xref:System.Text.RegularExpressions.Match) не будет иметь значение `false`. 

  В следующем примере используются методы [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String)) и [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch) для сопоставления строки "abc" во входной строке.

  ```csharp
  using System;
  using System.Text.RegularExpressions;

  public class Example
  {
     public static void Main()
     {
        string pattern = "abc";
        string input = "abc123abc456abc789";
        Match match = Regex.Match(input, pattern);
        while (match.Success)
        {
           Console.WriteLine("{0} found at position {1}.", 
                             match.Value, match.Index);
           match = match.NextMatch();                  
        }                     
     }
  }
  // The example displays the following output:
  //       abc found at position 0.
  //       abc found at position 6.
  //       abc found at position 12.
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Public Sub Main()
        Dim pattern As String = "abc"
        Dim input As String = "abc123abc456abc789"
        Dim match As Match = Regex.Match(input, pattern)
        Do While match.Success
           Console.WriteLine("{0} found at position {1}.", _
                             match.Value, match.Index)
           match = match.NextMatch()                  
        Loop                     
     End Sub
  End Module
  ' The example displays the following output:
  '       abc found at position 0.
  '       abc found at position 6.
  '       abc found at position 12.
  ```

Два свойства класса [Match](xref:System.Text.RegularExpressions.Match) возвращают объекты коллекции:

* Свойство [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) возвращает объект [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection), который содержит сведения о подстроках, соответствующих захватываемым группам в шаблоне регулярного выражения. 

* Свойство `Match.Captures` возвращает объект [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) с ограниченным применением. Коллекция не заполняется для объекта [Match](xref:System.Text.RegularExpressions.Match), свойство `Success` которого имеет значение `false`. В противном случае она содержит один объект [Capture](xref:System.Text.RegularExpressions.Capture), содержащий такие же данные, что и объект [Match](xref:System.Text.RegularExpressions.Match). 

Дополнительные сведения об этих объектах см. в разделах [Коллекция Group](#the-group-collection) и [Коллекция Capture](#the-capture-collection) далее в этой статье.

Два дополнительных свойства класса [Match](xref:System.Text.RegularExpressions.Match) предоставляют сведения о соответствии. Свойство `Match.Value` возвращает подстроку из входной строки, соответствующую шаблону регулярного выражения. Свойства `Match.Index` возвращает начальную позицию сопоставленной подстроки во входной строке с основанием ноль.

Класс [Match](xref:System.Text.RegularExpressions.Match) также содержит два метода сопоставления шаблона:

* Метод [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch) ищет совпадение после соответствия, представленного текущим объектом [Match](xref:System.Text.RegularExpressions.Match), и возвращает объект [Match](xref:System.Text.RegularExpressions.Match), представляющий соответствие.

* Метод [Match.Result](xref:System.Text.RegularExpressions.Match.NextMatch) выполняет указанную замену в сопоставленной строке и возвращает результат. 


В следующем примере метод [Match.Result](xref:System.Text.RegularExpressions.Match.NextMatch) используется для добавления символа **$** и пробела перед каждым числом из двух дробных разрядов. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b\d+(,\d{3})*\.\d{2}\b";
      string input = "16.32\n194.03\n1,903,672.08"; 

      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Result("$$ $&"));
   }
}
// The example displays the following output:
//       $ 16.32
//       $ 194.03
//       $ 1,903,672.08
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b\d+(,\d{3})*\.\d{2}\b"
      Dim input As String = "16.32" + vbCrLf + "194.03" + vbCrLf + "1,903,672.08" 

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Result("$$ $&"))
      Next
   End Sub
End Module
' The example displays the following output:
'       $ 16.32
'       $ 194.03
'       $ 1,903,672.08
```

Шаблон регулярного выражения `\b\d+(,\d{3})*\.\d{2}\b` определяется, как показано в следующей таблице.

Шаблон | Описание
------- | -----------
`\b` | Совпадение должно начинаться на границе слова.
`\d+` | Совпадение с одной или несколькими десятичными цифрами.
`(,\d{3})*` | Совпадение с нулем или несколькими вхождениями запятой, за которыми следуют три десятичные цифры.
`\.` | Совпадение с символом десятичной точки.
\d{2} | Совпадение с двумя десятичными цифрами.
`\b` | Совпадение должно заканчиваться на границе слова.
 
Шаблон замены **$$ $&** указывает, что сопоставленную подстроку следует заменить на символ доллара (**$**) (шаблон `$$`), пробел и значение соответствия (шаблон `$&`).

## <a name="the-group-collection"></a>Коллекция Group

Свойство [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) возвращает объект [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection), содержащий объекты [Group](xref:System.Text.RegularExpressions.Group), которые представляют захватываемые группы в одном соответствии. Первый объект [Group](xref:System.Text.RegularExpressions.Group) в коллекции (объект с нулевым индексом) представляет все сопоставление. Каждый последующий объект представляет результаты одной захватываемой группы. 

Вы можете извлечь отдельные объекты [Group](xref:System.Text.RegularExpressions.Group) из коллекции, используя свойство [GroupCollection.Item](xref:System.Text.RegularExpressions.GroupCollection.Item(System.Int32)). Неименованные группы можно извлечь по их номеру в коллекции, а именованные группы — по имени или номеру. Неименованные выделения идут в коллекции первыми и индексируются слева направо в том порядке, в котором они указаны в шаблоне регулярного выражения. Именованные выделения индексируются после неименованных слева направо в том порядке, в котором они указаны в шаблоне регулярного выражения. Чтобы определить, какие нумерованные группы доступны в коллекции, возвращаемой для определенного метода сопоставления регулярного выражения, вызовите метод [Regex.GetGroupNumbers](xref:System.Text.RegularExpressions.Regex.GetGroupNumbers) экземпляра. Чтобы определить, какие именованные группы доступны в коллекции, вызовите метод [Regex.GetGroupNames](xref:System.Text.RegularExpressions.Regex.GetGroupNames) экземпляра. Оба метода полезны в процедурах общего назначения, которые анализируют соответствия, найденные любым регулярным выражением. 

Свойство [GroupCollection.Item](xref:System.Text.RegularExpressions.GroupCollection.Item(System.Int32)) — это индексатор коллекции для C# и свойство объекта по умолчанию для Visual Basic. Это значит, что доступ к отдельным объектам [Group](xref:System.Text.RegularExpressions.Group) можно получить по индексу (или, для именованных групп, по имени) следующим образом: 

```csharp
Group group = match.Groups[ctr];
```

```vb
Dim group As Group = match.Groups(ctr)
```

В следующем примере определяется регулярное выражение, которое использует конструкции группировки для выделения месяца, дня и года из даты. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\w+)\s(\d{1,2}),\s(\d{4})\b";
      string input = "Born: July 28, 1989";
      Match match = Regex.Match(input, pattern);
      if (match.Success)
         for (int ctr = 0; ctr <  match.Groups.Count; ctr++)
            Console.WriteLine("Group {0}: {1}", ctr, match.Groups[ctr].Value);
    }
}
// The example displays the following output:
//       Group 0: July 28, 1989
//       Group 1: July
//       Group 2: 28
//       Group 3: 1989
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\w+)\s(\d{1,2}),\s(\d{4})\b"
      Dim input As String = "Born: July 28, 1989"
      Dim match As Match = Regex.Match(input, pattern)
      If match.Success Then
         For ctr As Integer = 0 To match.Groups.Count - 1
            Console.WriteLine("Group {0}: {1}", ctr, match.Groups(ctr).Value)
         Next      
      End If   
   End Sub
End Module
' The example displays the following output:
'       Group 0: July 28, 1989
'       Group 1: July
'       Group 2: 28
'       Group 3: 1989
```

Шаблон регулярного выражения `\b(\w+)\s(\d{1,2}),\s(\d{4})\b` определяется, как показано в следующей таблице.

Шаблон | Описание
------- | -----------
`\b` | Совпадение должно начинаться на границе слова.
`(\w+)` | Совпадение с одним или несколькими символами слова. Это первая группа записи.
`\s` | Соответствует пробелу.
`(\d{1,2})` | Совпадение с одной или двумя десятичными цифрами. Это вторая группа записи.
`,` | Сопоставление запятой.
`\s` | Соответствует пробелу.
`(\d{4})` | Выделяются&4; десятичные цифры. Это третья группа записи.
`\b` | Сопоставление заканчивается на границе слова.
 
## <a name="the-captured-group"></a>Захватываемая группа

Класс [Group](xref:System.Text.RegularExpressions.Group) представляет результат одной захватываемой группы. Объекты [Group](xref:System.Text.RegularExpressions.Group), представляющие захватываемые группы, заданные в регулярном выражении, возвращаются свойством [Item](xref:System.Text.RegularExpressions.GroupCollection.Item(System.Int32)) объекта [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection), который возвращается свойством [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups). Свойство [Item](xref:System.Text.RegularExpressions.GroupCollection.Item(System.Int32)) — это индексатор (для C#) и свойство по умолчанию (для Visual Basic) класса [Group](xref:System.Text.RegularExpressions.Group). Вы можете извлечь отдельные члены, циклически перебирая коллекцию с помощью конструкции `foreach`. Пример см. в предыдущем разделе.

В следующем примере вложенные конструкции группировки используются для записи подстрок в группы. Шаблон регулярного выражения `(a(b))c` сопоставляет строку "abc". Он назначает подстроку "ab" первой захватываемой группе, а подстроку "b" — второй захватываемой группе.

```csharp
List<int> matchposition = new List<int>();
List<string> results = new List<string>();
// Define substrings abc, ab, b.
Regex r = new Regex("(a(b))c"); 
Match m = r.Match("abdabc");
for (int i = 0; m.Groups[i].Value != ""; i++) 
{
   // Add groups to string array.
   results.Add(m.Groups[i].Value); 
   // Record character position.
   matchposition.Add(m.Groups[i].Index); 
}

// Display the capture groups.
for (int ctr = 0; ctr < results.Count; ctr++)
   Console.WriteLine("{0} at position {1}", 
                     results[ctr], matchposition[ctr]);
// The example displays the following output:
//       abc at position 3
//       ab at position 3
//       b at position 4
```

```vb
Dim matchposition As New List(Of Integer)
 Dim results As New List(Of String)
 ' Define substrings abc, ab, b.
 Dim r As New Regex("(a(b))c") 
 Dim m As Match = r.Match("abdabc")
 Dim i As Integer = 0
 While Not (m.Groups(i).Value = "")    
    ' Add groups to string array.
    results.Add(m.Groups(i).Value)     
    ' Record character position. 
    matchposition.Add(m.Groups(i).Index) 
     i += 1
 End While

 ' Display the capture groups.
 For ctr As Integer = 0 to results.Count - 1
    Console.WriteLine("{0} at position {1}", _ 
                      results(ctr), matchposition(ctr))
 Next                     
' The example displays the following output:
'       abc at position 3
'       ab at position 3
'       b at position 4
```

В следующем примере именованные конструкции группировки используются для выделения подстрок из строки, содержащей данные в формате "DATANAME:VALUE", которые регулярное выражение разделяет в позиции двоеточия (:).

```csharp
Regex r = new Regex("^(?<name>\\w+):(?<value>\\w+)");
Match m = r.Match("Section1:119900");
Console.WriteLine(m.Groups["name"].Value);
Console.WriteLine(m.Groups["value"].Value);
// The example displays the following output:
//       Section1
//       119900
```

```vb
Dim r As New Regex("^(?<name>\w+):(?<value>\w+)")
Dim m As Match = r.Match("Section1:119900")
Console.WriteLine(m.Groups("name").Value)
Console.WriteLine(m.Groups("value").Value)
' The example displays the following output:
'       Section1
'       119900
```

Шаблон регулярного выражения `^(?<name>\w+):(?<value>\w+)` определяется, как показано в следующей таблице.

Шаблон | Описание
------- | -----------
`^` | Начало совпадения в начале входной строки.
`(?<name>\w+)` | Совпадение с одним или несколькими символами слова. Имя захватываемой группы — name.
`:` | Сопоставление двоеточия.
`(?<value>\w+)` | Совпадение с одним или несколькими символами слова. Имя захватываемой группы — value.
 
Свойства класса [Group](xref:System.Text.RegularExpressions.Group) предоставляют сведения о захватываемой группе: свойство `Group.Value` содержит выделенную подстроку, свойство `Group.Index` указывает начальную позицию захватываемой группы во входном тексте, свойство `Group.Length` содержит длину выделенного текста, а свойство `Group.Success` указывает, соответствует ли подстрока шаблону, заданному захватываемой группой.

При применении квантификаторов к группе (дополнительные сведения см. в статье [Квантификаторы в регулярных выражениях](quantifiers.md)) поведение "один захват на захватываемую группу" изменяется двумя способами:

* Если квантификатор __*__ или __*?__ (который указывает ноль или больше соответствий) применен к группе, во входной строке может отсутствовать соответствие захватываемой группе. Если выделенного текста нет, свойства объекта [Group](xref:System.Text.RegularExpressions.Group) задаются, как показано в следующей таблице.

  Свойство объекта Group | Значение
  -------------- | ----- 
  `Success` | `false`
  `Value` | [String.Empty](xref:System.String.Empty) 
  `Length` | 0
 
  Ниже приведен пример. В шаблоне регулярного выражения `aaa(bbb)*ccc` первая захватываемая группа (подстрока "bbb") может быть сопоставлена ноль или больше раз. Так как входная строка "aaaccc" соответствует шаблону, захватываемая группа не имеет соответствия.

  ```csharp
  using System;
  using System.Text.RegularExpressions;

  public class Example
  {
     public static void Main()
     {
        string pattern = "aaa(bbb)*ccc";
        string input = "aaaccc";
        Match match = Regex.Match(input, pattern);
        Console.WriteLine("Match value: {0}", match.Value);
        if (match.Groups[1].Success)
           Console.WriteLine("Group 1 value: {0}", match.Groups[1].Value);
        else
           Console.WriteLine("The first capturing group has no match.");
     }
  }
  // The example displays the following output:
  //       Match value: aaaccc
  //       The first capturing group has no match.
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Public Sub Main()
        Dim pattern As String = "aaa(bbb)*ccc"
        Dim input As String = "aaaccc"
        Dim match As Match = Regex.Match(input, pattern)
        Console.WriteLine("Match value: {0}", match.Value)
        If match.Groups(1).Success Then
           Console.WriteLine("Group 1 value: {0}", match.Groups(1).Value)
        Else
           Console.WriteLine("The first capturing group has no match.")
       End If   
     End Sub
  End Module
  ' The example displays the following output:
  '       Match value: aaaccc
  '       The first capturing group has no match.
  ```

* Квантификаторы могут сопоставлять множество вхождений шаблона, заданного захватываемой группой. В этом случае свойства `Value` и `Length` объекта [Group](xref:System.Text.RegularExpressions.Group) содержат сведения только о последней выделенной подстроке. Например, следующее регулярное выражение сопоставляет предложение, заканчивающееся на точку. Оно использует две конструкции группировки: первая выделяет отдельные слова вместе с пробелом, вторая выделяет отдельные слова. Как видно из результата выполнения примера, хотя регулярное выражение успешно выделяет все предложение, вторая захватываемая группа выделяет только последнее слово.

  ```csharp
  using System;
  using System.Text.RegularExpressions;

  public class Example
  {
     public static void Main()
     {
        string pattern = @"\b((\w+)\s?)+\.";
        string input = "This is a sentence. This is another sentence.";
        Match match = Regex.Match(input, pattern);
        if (match.Success)
        {
           Console.WriteLine("Match: " + match.Value);
           Console.WriteLine("Group 2: " + match.Groups[2].Value);
        }   
     }
  }
  // The example displays the following output:
  //       Match: This is a sentence.
  //       Group 2: sentence
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Public Sub Main()
        Dim pattern As String = "\b((\w+)\s?)+\."
        Dim input As String = "This is a sentence. This is another sentence."
        Dim match As Match = Regex.Match(input, pattern)
        If match.Success Then
           Console.WriteLine("Match: " + match.Value)
           Console.WriteLine("Group 2: " + match.Groups(2).Value)
        End If   
     End Sub
  End Module
  ' The example displays the following output:
  '       Match: This is a sentence.
  '       Group 2: sentence
  ```

## <a name="the-capture-collection"></a>Коллекция Capture

Объект [Group](xref:System.Text.RegularExpressions.Group) содержит сведения только о последнем выделении. Однако весь набор выделений, созданный захватываемой группой, по-прежнему доступен из объекта [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection), возвращаемого свойством [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures). Каждый член коллекции — это объект [Capture](xref:System.Text.RegularExpressions.Capture), представляющий выделение этой захватываемой группы в порядке захвата (и, следовательно, в порядке сопоставления выделенных строк слева направо во входной строке). Вы можете извлечь отдельные объекты [Capture](xref:System.Text.RegularExpressions.Capture) из коллекции одним из двух способов: 

* циклически перебирая коллекцию с помощью конструкции `foreach` (для C#) или `For Each` (для Visual Basic);

* используя свойство [CaptureCollection.Item](xref:System.Text.RegularExpressions.CaptureCollection.Item(System.Int32)) для извлечения определенного объекта по индексу. Свойство [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) — это свойство по умолчанию (для Visual Basic) или индексатор (для C#).


Если квантификатор не применен к захватываемой группе, объект [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) содержит один объект [Capture](xref:System.Text.RegularExpressions.Capture), который не представляет особого интереса, так как содержит сведения о том же соответствии, что и объект [Group](xref:System.Text.RegularExpressions.Group). Если к захватываемой группе применен квантификатор, объект [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) содержит все выделения захватываемой группы, а последний член коллекции представляет то же выделение, что и объект [Group](xref:System.Text.RegularExpressions.Group). 

Например, если использовать шаблон регулярного выражения `((a(b))c)+` (где квантификатор `+` указывает одно или несколько соответствий) для выделения соответствий из строки "abcabcabc", объект [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) для каждого объекта [Group](xref:System.Text.RegularExpressions.Group) содержит три члена.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "((a(b))c)+";
      string input = "abcabcabc";

      Match match = Regex.Match(input, pattern);
      if (match.Success)
      {
         Console.WriteLine("Match: '{0}' at position {1}",  
                           match.Value, match.Index);
         GroupCollection groups = match.Groups;
         for (int ctr = 0; ctr < groups.Count; ctr++) {
            Console.WriteLine("   Group {0}: '{1}' at position {2}", 
                              ctr, groups[ctr].Value, groups[ctr].Index);
            CaptureCollection captures = groups[ctr].Captures;
            for (int ctr2 = 0; ctr2 < captures.Count; ctr2++) {
               Console.WriteLine("      Capture {0}: '{1}' at position {2}", 
                                 ctr2, captures[ctr2].Value, captures[ctr2].Index);
            }                     
         }
      }
   }
}
// The example displays the following output:
//       Match: 'abcabcabc' at position 0
//          Group 0: 'abcabcabc' at position 0
//             Capture 0: 'abcabcabc' at position 0
//          Group 1: 'abc' at position 6
//             Capture 0: 'abc' at position 0
//             Capture 1: 'abc' at position 3
//             Capture 2: 'abc' at position 6
//          Group 2: 'ab' at position 6
//             Capture 0: 'ab' at position 0
//             Capture 1: 'ab' at position 3
//             Capture 2: 'ab' at position 6
//          Group 3: 'b' at position 7
//             Capture 0: 'b' at position 1
//             Capture 1: 'b' at position 4
//             Capture 2: 'b' at position 7
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "((a(b))c)+"
      Dim input As STring = "abcabcabc"

      Dim match As Match = Regex.Match(input, pattern)
      If match.Success Then
         Console.WriteLine("Match: '{0}' at position {1}", _ 
                           match.Value, match.Index)
         Dim groups As GroupCollection = match.Groups
         For ctr As Integer = 0 To groups.Count - 1
            Console.WriteLine("   Group {0}: '{1}' at position {2}", _
                              ctr, groups(ctr).Value, groups(ctr).Index)
            Dim captures As CaptureCollection = groups(ctr).Captures
            For ctr2 As Integer = 0 To captures.Count - 1
               Console.WriteLine("      Capture {0}: '{1}' at position {2}", _
                                 ctr2, captures(ctr2).Value, captures(ctr2).Index)
            Next
         Next
      End If
   End Sub
End Module
' The example dosplays the following output:
'       Match: 'abcabcabc' at position 0
'          Group 0: 'abcabcabc' at position 0
'             Capture 0: 'abcabcabc' at position 0
'          Group 1: 'abc' at position 6
'             Capture 0: 'abc' at position 0
'             Capture 1: 'abc' at position 3
'             Capture 2: 'abc' at position 6
'          Group 2: 'ab' at position 6
'             Capture 0: 'ab' at position 0
'             Capture 1: 'ab' at position 3
'             Capture 2: 'ab' at position 6
'          Group 3: 'b' at position 7
'             Capture 0: 'b' at position 1
'             Capture 1: 'b' at position 4
'             Capture 2: 'b' at position 7
```

Следующий пример использует регулярное выражение `(Abc)+` для поиска одного или нескольких последовательных вхождений строки "Abc" в строке "XYZAbcAbcAbcXYZAbcAb". Этот пример демонстрирует использование свойства [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) для получения нескольких групп выделенных подстрок.

```csharp
{
   int counter;
   Match m;
   CaptureCollection cc;
   GroupCollection gc;

   // Look for groupings of "Abc".
   Regex r = new Regex("(Abc)+"); 
   // Define the string to search.
   m = r.Match("XYZAbcAbcAbcXYZAbcAb"); 
   gc = m.Groups;

   // Display the number of groups.
   Console.WriteLine("Captured groups = " + gc.Count.ToString());

   // Loop through each group.
   for (int i=0; i < gc.Count; i++) 
   {
      cc = gc[i].Captures;
      counter = cc.Count;

      // Display the number of captures in this group.
      Console.WriteLine("Captures count = " + counter.ToString());

      // Loop through each capture in the group.
      for (int ii = 0; ii < counter; ii++) 
      {
         // Display the capture and its position.
         Console.WriteLine(cc[ii] + "   Starts at character " + 
              cc[ii].Index);
      }
   }
}
// The example displays the following output:
//       Captured groups = 2
//       Captures count = 1
//       AbcAbcAbc   Starts at character 3
//       Captures count = 3
//       Abc   Starts at character 3
//       Abc   Starts at character 6
//       Abc   Starts at character 9  
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "((a(b))c)+"
      Dim input As STring = "abcabcabc"

      Dim match As Match = Regex.Match(input, pattern)
      If match.Success Then
         Console.WriteLine("Match: '{0}' at position {1}", _ 
                           match.Value, match.Index)
         Dim groups As GroupCollection = match.Groups
         For ctr As Integer = 0 To groups.Count - 1
            Console.WriteLine("   Group {0}: '{1}' at position {2}", _
                              ctr, groups(ctr).Value, groups(ctr).Index)
            Dim captures As CaptureCollection = groups(ctr).Captures
            For ctr2 As Integer = 0 To captures.Count - 1
               Console.WriteLine("      Capture {0}: '{1}' at position {2}", _
                                 ctr2, captures(ctr2).Value, captures(ctr2).Index)
            Next
         Next
      End If
   End Sub
End Module
' The example displays the following output:
'       Match: 'abcabcabc' at position 0
'          Group 0: 'abcabcabc' at position 0
'             Capture 0: 'abcabcabc' at position 0
'          Group 1: 'abc' at position 6
'             Capture 0: 'abc' at position 0
'             Capture 1: 'abc' at position 3
'             Capture 2: 'abc' at position 6
'          Group 2: 'ab' at position 6
'             Capture 0: 'ab' at position 0
'             Capture 1: 'ab' at position 3
'             Capture 2: 'ab' at position 6
'          Group 3: 'b' at position 7
'             Capture 0: 'b' at position 1
'             Capture 1: 'b' at position 4
'             Capture 2: 'b' at position 7
```

## <a name="the-individual-capture"></a>Отдельный захват

Класс [Capture](xref:System.Text.RegularExpressions.Capture) содержит результаты одного выделения части выражения. Свойство [Capture.Value](xref:System.Text.RegularExpressions.Capture.Value) содержит сопоставленный текст, а свойство [Capture.Index](xref:System.Text.RegularExpressions.Capture.Index) указывает начальную позицию сопоставленной подстроки во входной строке с основанием ноль. 

Следующий пример ищет во входной строке температуру выбранных городов. Запятая (",") используется для разделения города и температуры, а точка с запятой (";") — для разделения данных каждого города. Вся входная строка представляет одно соответствие. В шаблоне регулярного выражения `((\w+(\s\w+)*),(\d+);)+`, который используется для анализа строки, название города назначается второй захватываемой группе, а температура — четвертой захватываемой группе.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "Miami,78;Chicago,62;New York,67;San Francisco,59;Seattle,58;"; 
      string pattern = @"((\w+(\s\w+)*),(\d+);)+";
      Match match = Regex.Match(input, pattern);
      if (match.Success)
      {
         Console.WriteLine("Current temperatures:");
         for (int ctr = 0; ctr < match.Groups[2].Captures.Count; ctr++)
            Console.WriteLine("{0,-20} {1,3}", match.Groups[2].Captures[ctr].Value, 
                              match.Groups[4].Captures[ctr].Value);
      }
   }
}
// The example displays the following output:
//       Current temperatures:
//       Miami                 78
//       Chicago               62
//       New York              67
//       San Francisco         59
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "Miami,78;Chicago,62;New York,67;San Francisco,59;Seattle,58;" 
      Dim pattern As String = "((\w+(\s\w+)*),(\d+);)+"
      Dim match As Match = Regex.Match(input, pattern)
      If match.Success Then
         Console.WriteLine("Current temperatures:")
         For ctr As Integer = 0 To match.Groups(2).Captures.Count - 1
            Console.WriteLine("{0,-20} {1,3}", match.Groups(2).Captures(ctr).Value, _
                              match.Groups(4).Captures(ctr).Value)
         Next
      End If
   End Sub
End Module
' The example displays the following output:
'       Current temperatures:
'       Miami                 78
'       Chicago               62
'       New York              67
'       San Francisco         59
```

Определение регулярного выражения показано в следующей таблице.

Шаблон | Описание
------- | -----------
`\w+` | Совпадение с одним или несколькими символами слова.
`(\s\w+)*` | Сопоставляется ноль или несколько экземпляров пробела, за которыми следует один или несколько словообразующих символов. Этот шаблон выделяет названия городов из нескольких слов. Это третья группа записи.
`(\w+(\s\w+)*)` | Сопоставляется один или несколько словообразующих символов, за которыми следует ноль или несколько пробелов и один или несколько словообразующих символов. Это вторая группа записи.
`,` | Сопоставление запятой.
`(\d+)` | Сопоставление с одной или несколькими цифрами. Это четвертая группа записи.
`;` | Сопоставление точки с запятой.
`((\w+(\s\w+)*),(\d+);)+` | Шаблона из слова, за которым следуют другие слова, запятая, одна или несколько цифр и точка запятая сопоставляется один или более раз. Это первая группа записи. 
 
## <a name="see-also"></a>См. также

[System.Text.RegularExpressions](xref:System.Text.RegularExpressions)

[Регулярные выражения .NET](regular-expressions.md)

[Элементы языка регулярных выражений — краткий справочник](quick-ref.md)


