---
title: "Регулярные выражения в .NET"
description: "Регулярные выражения в .NET"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: d1a640cf-09ca-48f7-800c-a627a6d549c9
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 1fc1edd64c330fe579f389750432665ed982976e

---

# <a name="regular-expressions-in-net"></a>Регулярные выражения в .NET

Регулярные выражения предоставляют мощный, гибкий и эффективный способ обработки текста. Комплексная нотация сопоставления шаблонов регулярных выражений позволяет быстро анализировать большие объемы текста для поиска определенных шаблонов символов, проверять текст на соответствие предопределенному шаблону (например, адресу электронной почты, извлекать, изменять, заменять и удалять текстовые подстроки, а также добавлять извлеченные строки в коллекцию для создания отчета. Для многих приложений, которые работают со строками или анализируют большие блоки текста, регулярные выражения — незаменимый инструмент.

## <a name="how-regular-expressions-work"></a>Принцип работы регулярных выражений

Главный компонент обработки текста с помощью регулярных выражений — это механизм регулярных выражений, представленный в платформе .NET объектом [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex). Как минимум, для обработки текста с использованием в регулярных выражений механизму регулярных выражений необходимо предоставить два следующих элемента:

* Шаблон регулярного выражения для определения текста. 
  
  В .NET шаблоны регулярных выражений определяются специальным синтаксисом или языком, который совместим с регулярными выражениями Perl 5 и добавляет дополнительные возможности, например сопоставление справа налево. Дополнительные сведения см. в разделе [Элементы языка регулярных выражений. Краткий справочник](quick-ref.md).
  
* Текст, который будет проанализирован на соответствие шаблону регулярного выражения.

Методы класса [Regex](xref:System.Text.RegularExpressions.Regex) позволяют выполнять перечисленные далее операции.

* Определить, входит ли шаблон регулярного выражения во входной текст, с помощью метода [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)). Пример, в котором для проверки текста используется метод [IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)), см. в разделе [Практическое руководство. Проверка соответствия формата строк формату электронной почты](verify-format.md).

* Получить один или все экземпляры текста, соответствующего шаблону регулярного выражения, с помощью метода [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) или [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)). Первый метод возвращает объект [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match), который предоставляет сведения о соответствующем тексте. Второй метод возвращает объект [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection), содержащий один объект [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) для каждого соответствия, обнаруженного в обработанном тексте. 

* Заменить текст, соответствующий шаблону регулярного выражения, с помощью метода [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)). Примеры использования метода [Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) для изменения форматов даты и удаления недопустимых символов из строки см. в разделах [Практическое руководство. Исключение недопустимых символов из строки](strip-characters.md) и [Пример регулярного выражения. Изменение форматов даты](changing-formats.md).

Обзор объектной модели регулярных выражений см. в разделе [Объектная модель регулярных выражений](object-model.md).

Дополнительные сведения о языке регулярных выражений см. в разделе [Элементы языка регулярных выражений. Краткий справочник](quick-ref.md).

## <a name="regular-expression-examples"></a>Примеры регулярных выражений

Класс [String](xref:System.String) содержит ряд методов для поиска и замены строк, которые можно использовать для поиска строковых литералов в длинных строках. Регулярные выражения максимально полезны, если требуется найти одну из нескольких подстрок в длинной строке или определить шаблоны в строке, как показано в следующих примерах. 

### <a name="example-1-replacing-substrings"></a>Пример 1. Замена подстрок

Предположим, что список рассылки содержит имена, в которые иногда входит обращение (Mr., Mrs., Miss или Ms.) в дополнение к имени и фамилии. Если вы не хотите включать обращения при создании этикеток для конвертов из списка, с помощью регулярного выражения их можно удалить, как показано в следующем примере.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "(Mr\\.? |Mrs\\.? |Miss |Ms\\.? )";
      string[] names = { "Mr. Henry Hunt", "Ms. Sara Samuels", 
                         "Abraham Adams", "Ms. Nicole Norris" };
      foreach (string name in names)
         Console.WriteLine(Regex.Replace(name, pattern, String.Empty));
   }
}
// The example displays the following output:
//    Henry Hunt
//    Sara Samuels
//    Abraham Adams
//    Nicole Norris
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(Mr\.? |Mrs\.? |Miss |Ms\.? )"
      Dim names() As String = { "Mr. Henry Hunt", "Ms. Sara Samuels", _
                                "Abraham Adams", "Ms. Nicole Norris" }
      For Each name As String In names
         Console.WriteLine(Regex.Replace(name, pattern, String.Empty))
      Next                                
   End Sub
End Module
' The example displays the following output:
'    Henry Hunt
'    Sara Samuels
'    Abraham Adams
'    Nicole Norris
```

Шаблон регулярного выражения `(Mr\.? |Mrs\.? |Miss |Ms\.? )` сопоставляет все вхождения строк "Mr", "Mr.", "Mrs", "Mrs.", "Miss", "Ms" или "Ms.". После вызова метода [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) сопоставленная строка заменяется на [String.Empty](xref:System.String.Empty). Другими словами, она удаляется из исходной строки.

### <a name="example-2-identifying-duplicated-words"></a>Пример 2. Поиск повторяющихся слов

Случайный повтор слов — это распространенная ошибка при написании текстов. Регулярное выражение можно использовать для определения повторяющихся слов, как показано в следующем примере.

```csharp
using System;
using System.Text.RegularExpressions;

public class Class1
{
   public static void Main()
   {
      string pattern = @"\b(\w+?)\s\1\b";
      string input = "This this is a nice day. What about this? This tastes good. I saw a a dog.";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
         Console.WriteLine("{0} (duplicates '{1}') at position {2}", 
                           match.Value, match.Groups[1].Value, match.Index);
   }
}
// The example displays the following output:
//       This this (duplicates 'This)' at position 0
//       a a (duplicates 'a)' at position 66
```

```vb
Imports System.Text.RegularExpressions

Module modMain
   Public Sub Main()
      Dim pattern As String = "\b(\w+?)\s\1\b"
      Dim input As String = "This this is a nice day. What about this? This tastes good. I saw a a dog."
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
         Console.WriteLine("{0} (duplicates '{1}') at position {2}", _
                           match.Value, match.Groups(1).Value, match.Index)
      Next
   End Sub
End Module
' The example displays the following output:
'       This this (duplicates 'This)' at position 0
'       a a (duplicates 'a)' at position 66
```

Шаблон регулярного выражения `\b(\w+?)\s\1\b` интерпретируется следующим образом:

Синтаксис | Значение
------ | -------
`\b` | Начало на границе слова.
`(\w+?)` | Соответствует одному или нескольким символам слова (как можно меньшему количеству). Вместе они формируют группу, к которой можно обращаться как к `\1`.
`\s` | Соответствует пробелу.
`\1` | Сопоставление подстроки, равной группе с именем `\1`.
`\b` | Соответствует границе слова.

Метод [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) вызывается с параметрами регулярного выражения [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase). Поэтому операция сопоставления учитывает регистр, а пример указывает, что подстрока "This this" является повтором.

Обратите внимание, что входная строка содержит подстроку "this? This". Но из-за знака пунктуации она не считается повторением.

### <a name="example-3-dynamically-building-a-culturesensitive-regular-expression"></a>Пример 3. Динамическое создание регулярного выражения с учетом языка и региональных параметров

Следующий пример демонстрирует преимущества использования регулярных выражений с гибкими возможностями глобализации .NET. В примере объект [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) применяется для определения формата денежных значений в текущем языке и региональных параметрах системы. Затем эти данные используются для динамического создания регулярного выражения, которое извлекает денежные значения из текста. Для каждого совпадения извлекается подгруппа, содержащая только числовые строки, которая преобразуется в значение [Decimal](xref:System.Decimal), после чего рассчитывается промежуточный итог. 

```csharp
using System;
using System.Collections.Generic;
using System.Globalization;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      // Define text to be parsed.
      string input = "Office expenses on 2/13/2008:\n" + 
                     "Paper (500 sheets)                      $3.95\n" + 
                     "Pencils (box of 10)                     $1.00\n" + 
                     "Pens (box of 10)                        $4.49\n" + 
                     "Erasers                                 $2.19\n" + 
                     "Ink jet printer                        $69.95\n\n" + 
                     "Total Expenses                        $ 81.58\n"; 

      // Get current culture's NumberFormatInfo object.
      NumberFormatInfo nfi = CultureInfo.CurrentCulture.NumberFormat;
      // Assign needed property values to variables.
      string currencySymbol = nfi.CurrencySymbol;
      bool symbolPrecedesIfPositive = nfi.CurrencyPositivePattern % 2 == 0;
      string groupSeparator = nfi.CurrencyGroupSeparator;
      string decimalSeparator = nfi.CurrencyDecimalSeparator;

      // Form regular expression pattern.
      string pattern = Regex.Escape( symbolPrecedesIfPositive ? currencySymbol : "") + 
                       @"\s*[-+]?" + "([0-9]{0,3}(" + groupSeparator + "[0-9]{3})*(" + 
                       Regex.Escape(decimalSeparator) + "[0-9]+)?)" + 
                       (! symbolPrecedesIfPositive ? currencySymbol : ""); 
      Console.WriteLine( "The regular expression pattern is:");
      Console.WriteLine("   " + pattern);      

      // Get text that matches regular expression pattern.
      MatchCollection matches = Regex.Matches(input, pattern, 
                                              RegexOptions.IgnorePatternWhitespace);               
      Console.WriteLine("Found {0} matches.", matches.Count); 

      // Get numeric string, convert it to a value, and add it to List object.
      List<decimal> expenses = new List<Decimal>();

      foreach (Match match in matches)
         expenses.Add(Decimal.Parse(match.Groups[1].Value));      

      // Determine whether total is present and if present, whether it is correct.
      decimal total = 0;
      foreach (decimal value in expenses)
         total += value;

      if (total / 2 == expenses[expenses.Count - 1]) 
         Console.WriteLine("The expenses total {0:C2}.", expenses[expenses.Count - 1]);
      else
         Console.WriteLine("The expenses total {0:C2}.", total);
   }  
}
// The example displays the following output:
//       The regular expression pattern is:
//          \$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)
//       Found 6 matches.
//       The expenses total $81.58.
```

```vb
Imports System.Collections.Generic
Imports System.Globalization
Imports System.Text.RegularExpressions

Public Module Example
   Public Sub Main()
      ' Define text to be parsed.
      Dim input As String = "Office expenses on 2/13/2008:" + vbCrLf + _
                            "Paper (500 sheets)                      $3.95" + vbCrLf + _
                            "Pencils (box of 10)                     $1.00" + vbCrLf + _
                            "Pens (box of 10)                        $4.49" + vbCrLf + _
                            "Erasers                                 $2.19" + vbCrLf + _
                            "Ink jet printer                        $69.95" + vbCrLf + vbCrLf + _
                            "Total Expenses                        $ 81.58" + vbCrLf
      ' Get current culture's NumberFormatInfo object.
      Dim nfi As NumberFormatInfo = CultureInfo.CurrentCulture.NumberFormat
      ' Assign needed property values to variables.
      Dim currencySymbol As String = nfi.CurrencySymbol
      Dim symbolPrecedesIfPositive As Boolean = CBool(nfi.CurrencyPositivePattern Mod 2 = 0)
      Dim groupSeparator As String = nfi.CurrencyGroupSeparator
      Dim decimalSeparator As String = nfi.CurrencyDecimalSeparator

      ' Form regular expression pattern.
      Dim pattern As String = Regex.Escape(CStr(IIf(symbolPrecedesIfPositive, currencySymbol, ""))) + _
                              "\s*[-+]?" + "([0-9]{0,3}(" + groupSeparator + "[0-9]{3})*(" + _
                              Regex.Escape(decimalSeparator) + "[0-9]+)?)" + _
                              CStr(IIf(Not symbolPrecedesIfPositive, currencySymbol, "")) 
      Console.WriteLine("The regular expression pattern is: ")
      Console.WriteLine("   " + pattern)      

      ' Get text that matches regular expression pattern.
      Dim matches As MatchCollection = Regex.Matches(input, pattern, RegexOptions.IgnorePatternWhitespace)               
      Console.WriteLine("Found {0} matches. ", matches.Count)

      ' Get numeric string, convert it to a value, and add it to List object.
      Dim expenses As New List(Of Decimal)

      For Each match As Match In matches
         expenses.Add(Decimal.Parse(match.Groups.Item(1).Value))      
      Next

      ' Determine whether total is present and if present, whether it is correct.
      Dim total As Decimal
      For Each value As Decimal In expenses
         total += value
      Next

      If total / 2 = expenses(expenses.Count - 1) Then
         Console.WriteLine("The expenses total {0:C2}.", expenses(expenses.Count - 1))
      Else
         Console.WriteLine("The expenses total {0:C2}.", total)
      End If   
   End Sub
End Module
' The example displays the following output:
'       The regular expression pattern is:
'          \$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)
'       Found 6 matches.
'       The expenses total $81.58.
```

На компьютере с региональными параметрами "English - United States (en-US)" пример динамически создает регулярное выражение `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`. Шаблон регулярного выражения интерпретируется следующим образом:

Синтаксис | Значение
------ | -------
`\$` | Выполняется поиск одного вхождения символа доллара ($) во входной строке. Строка шаблона регулярного выражения содержит обратную косую черту, что говорит о том, что символ доллара интерпретируется буквально, а не как привязка регулярного выражения. (Отдельный символ $ указывает, что механизм регулярных выражений должен начинать сопоставление с конца строки.) Чтобы правильно обработать текущий символ валюты, в примере вызывается метод [Escape](xref:System.Text.RegularExpressions.Regex.Escape(System.String)), который экранирует символ.
`\s*` | Поиск нуля или нескольких вхождений пробела.
`[-+]?` | Поиск нуля или нескольких вхождений знака плюс или минус.
`([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)` | Внешние круглые скобки вокруг этого выражения делают его захватываемой группой или частью выражения. Если найдено соответствие, сведения об этой части строки можно получить из второго объекта [Group](xref:System.Text.RegularExpressions.Group) в объекте [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection), который возвращается свойством [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups). (Первый элемент в коллекции представляет все сопоставление.)
`[0-9]{0,3}` | Поиск 0-3 вхождений десятичных цифр (0-9).
`(,[0-9]{3})*` | Поиск нуля или нескольких вхождений разделителя группы, за которыми следуют три десятичные цифры.
`\.` | Поиск одного вхождения десятичного разделителя.
`[0-9]+` | Поиск одной или нескольких десятичных цифр.
`(\.[0-9]+)?` | Поиск нуля или одного вхождения десятичного разделителя, за которым следует по крайней мере одна десятичная цифра.

## <a name="related-topics"></a>Связанные разделы

Заголовок | Описание
----- | -----------
[Элементы языка регулярных выражений — краткий справочник](quick-ref.md) | Сведения о наборе символов, операторов и конструкций, которые можно использовать для определения регулярных выражений.
[Объектная модель регулярных выражений](object-model.md) | Сведения об использовании классов регулярных выражений и примеры кода.
[Подробные сведения о поведении регулярных выражений](regex-behavior.md) | Сведения о возможностях и поведении регулярных выражений платформы .NET.
[Примеры регулярных выражений](regex-examples.md) | Примеры кода, демонстрирующие типичное применение регулярных выражений.


## <a name="reference"></a>Ссылка

[System.Text.RegularExpressions](xref:System.Text.RegularExpressions)

[System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex)




<!--HONumber=Nov16_HO3-->


