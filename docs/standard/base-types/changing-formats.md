---
title: "Пример регулярного выражения. Изменение форматов даты"
description: "Пример регулярного выражения. Изменение форматов даты"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 3e196697-981c-4c1d-93dd-c3b236ef36dd
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 8b333db10f7dc9d0e4701899b7af46f45f60aa8e

---

# <a name="regular-expression-example-changing-date-formats"></a>Пример регулярного выражения. Изменение форматов даты

В следующем примере кода метод [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) используется для замены дат в формате *mm/dd/yy* на даты в формате *dd-mm-yy*.

## <a name="example"></a>Пример

```csharp
static string MDYToDMY(string input) 
{
   try {
      return Regex.Replace(input, 
            "\\b(?<month>\\d{1,2})/(?<day>\\d{1,2})/(?<year>\\d{2,4})\\b",
            "${day}-${month}-${year}", RegexOptions.None,
            TimeSpan.FromMilliseconds(150));
   }         
   catch (RegexMatchTimeoutException) {
      return input;
   }
}
```

```vb
Function MDYToDMY(input As String) As String
   Try
      Return Regex.Replace(input, _
             "\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b", _
             "${day}-${month}-${year}", RegexOptions.None,
             TimeSpan.FromMilliseconds(150))
    Catch e As RegexMatchTimeoutException
       Return input
    End Try         
End Function
```

В следующем коде показано, как можно вызывать метод `MDYToDMY` в приложении. 

```csharp
using System;
using System.Globalization;
using System.Text.RegularExpressions;

public class Class1
{
   public static void Main()
   {
      string dateString = DateTime.Today.ToString("d", 
                                        DateTimeFormatInfo.InvariantInfo);
      string resultString = MDYToDMY(dateString);
      Console.WriteLine("Converted {0} to {1}.", dateString, resultString);
   }

   static string MDYToDMY(string input) 
   {
      try {
         return Regex.Replace(input, 
               "\\b(?<month>\\d{1,2})/(?<day>\\d{1,2})/(?<year>\\d{2,4})\\b",
               "${day}-${month}-${year}", RegexOptions.None,
               TimeSpan.FromMilliseconds(150));
      }         
      catch (RegexMatchTimeoutException) {
         return input;
      }
   }

}
// The example displays the following output to the console if run on 8/21/2007:
//      Converted 08/21/2007 to 21-08-2007.
```

```vb
Imports System.Globalization
Imports System.Text.RegularExpressions

Module DateFormatReplacement
   Public Sub Main()
      Dim dateString As String = Date.Today.ToString("d", _
                                           DateTimeFormatInfo.InvariantInfo)
      Dim resultString As String = MDYToDMY(dateString)
      Console.WriteLine("Converted {0} to {1}.", dateString, resultString)
   End Sub

    Function MDYToDMY(input As String) As String
       Try
          Return Regex.Replace(input, _
                 "\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b", _
                 "${day}-${month}-${year}", RegexOptions.None,
                 TimeSpan.FromMilliseconds(150))
        Catch e As RegexMatchTimeoutException
           Return input
        End Try         
    End Function
End Module
' The example displays the following output to the console if run on 8/21/2007:
'      Converted 08/21/2007 to 21-08-2007.
```

## <a name="comments"></a>Комментарии

Возможные интерпретации шаблона регулярного выражения `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` показаны в следующей таблице.

Шаблон | Описание
------- | ----------- 
`\b` | Совпадение должно начинаться на границе слова.
`(?<month>\d{1,2})` | Совпадение с одной или двумя десятичными цифрами. Это записанная группа `month`.
`/` | Совпадение с косой чертой.
`(?<day>\d{1,2})` | Совпадение с одной или двумя десятичными цифрами. Это записанная группа `day`.
`/` | Совпадение с косой чертой.
`(?<year>\d{2,4})` | Совпадение с двумя-четырьмя десятичными цифрами. Это записанная группа `year`.
`\b` | Совпадение должно заканчиваться на границе слова.
 
Шаблон `${day}-${month}-${year}` определяет строку замены, как показано в следующей таблице.

Шаблон | Описание
------- | ----------- 
`$(day)` | Добавляет строку, которая записана захватываемой группой `day`.
`-` | Добавляет символ дефиса.
`$(month)` | Добавляет строку, которая записана захватываемой группой `month`.
`-` | Добавляет символ дефиса.
`$(year)` | Добавляет строку, которая записана захватываемой группой `year`.
 
## <a name="see-also"></a>См. также

[Регулярные выражения .NET](regular-expressions.md)

[Примеры регулярных выражений](regex-examples.md)



<!--HONumber=Nov16_HO1-->


