---
title: "Практическое руководство. Проверка строк на соответствие формату электронной почты"
description: "Проверка строк на соответствие формату электронной почты"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 6d735520-4059-4754-b34c-d117299d36f1
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 077a09152ac23c986a751f42c893e1dcca858291
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-verify-that-strings-are-in-valid-email-format"></a>Практическое руководство. Проверка строк на соответствие формату электронной почты

В следующем примере регулярное выражение используется, чтобы проверить, имеет ли строка допустимый формат адреса электронной почты.

## <a name="example"></a>Пример

В примере определяется метод `IsValidEmail`, который возвращает значение `true`, если строка содержит допустимый адрес электронной почты, и значение `false`, если она его не содержит, но не выполняет никаких других действий. 

Чтобы проверить, что адрес электронной почты допустим, метод `IsValidEmail` вызывает метод [Regex.Replace(String, String, MatchEvaluator)](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.Text.RegularExpressions.MatchEvaluator)) с шаблоном регулярного выражения `(@)(.+)$` для выделения доменного имени из адреса электронной почты. Третий параметр — это делегат [MatchEvaluator](xref:System.Text.RegularExpressions.MatchEvaluator), представляющий метод, который обрабатывает и заменяет найденный текст. Шаблон регулярного выражения интерпретируется следующим образом. 

Шаблон | Описание
------- | ----------- 
`(@)` | Совпадение с символом @. Это первая группа записи.
`(.+)` | Совпадение с одним или несколькими вхождениями любого символа. Это вторая группа записи.
`$` | Совпадение должно заканчиваться в конце строки.
 
Доменное имя вместе с символом "@" передается методу `DomainMapper`, который использует класс [IdnMapping](xref:System.Globalization.IdnMapping) для преобразования символов Юникода, находящихся вне диапазона символов US-ASCII, в формат Punycode. Метод также устанавливает флаг `invalid` в значение `true`, если метод [IdnMapping.GetAscii](xref:System.Globalization.IdnMapping.GetAscii(System.String)) находит какие-либо недопустимые символы в доменном имени. Метод возвращает доменное имя в формате Punycode, которому предшествует символ "@", методу `IsValidEmail`. 

Метод `IsValidEmail` затем вызывает метод [Regex.IsMatch(String, String)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String)), чтобы убедиться, что адрес соответствует шаблону регулярного выражения. 

Обратите внимание, что метод `IsValidEmail` не выполняет аутентификацию для проверки действительности адреса электронной почты. Он просто проверяет, является ли его формат допустимым для адреса электронной почты. Кроме того, метод `IsValidEmail` не проверяет, является ли доменное имя верхнего уровня действительным доменным именем, присутствующим в [базе данных корневых зон IANA](https://www.iana.org/domains/root/db), что потребовало бы операции поиска. Вместо этого регулярное выражение просто проверяет, что доменное имя верхнего уровня состоит из алфавитно-цифровых символов ASCII в количестве от двух до двадцати четырех, при этом первый и последний символ — это буква или цифра, а остальные символы — это буква, цифра или дефис (-). 

```csharp
using System;
using System.Globalization;
using System.Text.RegularExpressions;

public class RegexUtilities
{
   bool invalid = false;

   public bool IsValidEmail(string strIn)
   {
       invalid = false;
       if (String.IsNullOrEmpty(strIn))
          return false;

       // Use IdnMapping class to convert Unicode domain names.
       try {
          strIn = Regex.Replace(strIn, @"(@)(.+)$", this.DomainMapper,
                                RegexOptions.None, TimeSpan.FromMilliseconds(200));
       }
       catch (RegexMatchTimeoutException) {
         return false;
       }

        if (invalid)
           return false;

       // Return true if strIn is in valid e-mail format.
       try {
          return Regex.IsMatch(strIn,
                @"^(?("")("".+?(?<!\\)""@)|(([0-9a-z]((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`\{\}\|~\w])*)(?<=[0-9a-z])@))" +
                @"(?(\[)(\[(\d{1,3}\.){3}\d{1,3}\])|(([0-9a-z][-\w]*[0-9a-z]*\.)+[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))$",
                RegexOptions.IgnoreCase, TimeSpan.FromMilliseconds(250));
       }
       catch (RegexMatchTimeoutException) {
          return false;
       }
   }

   private string DomainMapper(Match match)
   {
      // IdnMapping class with default property values.
      IdnMapping idn = new IdnMapping();

      string domainName = match.Groups[2].Value;
      try {
         domainName = idn.GetAscii(domainName);
      }
      catch (ArgumentException) {
         invalid = true;
      }
      return match.Groups[1].Value + domainName;
   }
}
```

```vb
Imports System.Globalization
Imports System.Text.RegularExpressions

Public Class RegexUtilities
   Dim invalid As Boolean = False

   public Function IsValidEmail(strIn As String) As Boolean
       invalid = False
       If String.IsNullOrEmpty(strIn) Then Return False

       ' Use IdnMapping class to convert Unicode domain names.
       Try
          strIn = Regex.Replace(strIn, "(@)(.+)$", AddressOf Me.DomainMapper, 
                                RegexOptions.None, TimeSpan.FromMilliseconds(200))
       Catch e As RegexMatchTimeoutException
          Return False
       End Try

       If invalid Then Return False

       ' Return true if strIn is in valid e-mail format.
       Try
          Return Regex.IsMatch(strIn,
                 "^(?("")("".+?(?<!\\)""@)|(([0-9a-z]((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`\{\}\|~\w])*)(?<=[0-9a-z])@))" +
                 "(?(\[)(\[(\d{1,3}\.){3}\d{1,3}\])|(([0-9a-z][-\w]*[0-9a-z]*\.)+[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))$",
                 RegexOptions.IgnoreCase, TimeSpan.FromMilliseconds(250))
       Catch e As RegexMatchTimeoutException
          Return False
       End Try  
   End Function

   Private Function DomainMapper(match As Match) As String
      ' IdnMapping class with default property values.
      Dim idn As New IdnMapping()

      Dim domainName As String = match.Groups(2).Value
      Try
         domainName = idn.GetAscii(domainName)
      Catch e As ArgumentException
         invalid = True      
      End Try      
      Return match.Groups(1).Value + domainName
   End Function
End Class
```

Возможные интерпретации шаблона регулярного выражения `^(?(")(".+?(?<!\\)"@)|(([0-9a-z]((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`\{ \} \|~ \w])*)(?<=[0-9a-z])@))(?\[)(\[(\d{1,3}\.){3}\d{1,3}\])|( ([0-9a-z] [-\w]*[0-9a-z] *\.) + [a-z0-9] [\-a-z0-9]{0,22}[a-z0-9]))$` в этом примере показаны в следующей таблице. Обратите внимание, что регулярное выражение компилируется с флагом [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase).

Шаблон | Описание
------- | ----------- 
`^` | Соответствие должно обнаруживаться в начале строки.
`(?(")` | Определение, является ли первый символ кавычкой. `(?(")` является началом конструкции изменения.
`(?("")("".+?(?<!\\)""@)` | Если первый символ является кавычкой, совпадение с открывающей кавычкой, после которой следует как минимум одно вхождение любого символа с последующей закрывающей кавычкой. Последней закрывающей кавычки не должен предшествовать символ обратной косой черты (`(\). (?<!`) — это начало утверждения отрицательного просмотра назад нулевой ширины. Строка должна заканчиваться знаком @.
`&#124;(([0-9a-z] | Если первый символ не является кавычкой, имеется соответствие любой буквы с A до Z (при сравнении учитывается регистр) или любой цифре от 0 до 9.
`(\.(?!\.))` | Если следующим символом является точка, имеется соответствие. Если этот символ не является точкой, выполняется поиск вперед к следующему символу и продолжается поиск соответствия. `(?!\.)` является утверждением отрицательного поиска вперед нулевой ширины, предотвращающим отображение двух последовательных точек в локальной части адреса электронной почты.
`&#124;[-!#\$%&'\*\+/=\?\^`\{\}\&#124;~\w] | Если следующий символ не является точкой, совпадение с любым символом слова или одним из следующих символов: -!#$%'*+=?^`{}&#124;~. 
`((\.(?!\.))&#124;[-!#\$%'\*\+/=\?\^`\{\}\&#124;~\w])* | Соответствие шаблону изменения (точка, после которой следует символ, отличный от точки, или одна цифра)&0; или несколько раз.
`@` | Совпадение с символом @.
`(?<=[0-9a-z])` | Продолжение поиска соответствия, если символ, предшествующий символу @, является буквой от A до Z, от a до z или цифрой от 0 до 9. Конструкция `(?<=[0-9a-z])` определяет утверждение положительного поиска вперед нулевой ширины.
`(?(\[)` | Проверка, является ли символ, следующий после символа @, открывающей круглой скобкой.
`(\[(\d{1,3}\.){3}\d{1,3}\])` | Если этот символ является открывающей круглой скобкой, имеется соответствие открытой круглой скобки, после которой идет IP-адрес (четыре группы из одной-трех цифр, разделенные точкой) и закрывающая круглая скобка.
`&#124;(([0-9a-z][-\w]*[0-9a-z]*\.)+` | Если символ, следующий за @, не является открывающей круглой скобкой, совпадение с одним буквенно-цифровым символом со значением A-Z, a-z или 0-9, за которым следует ноль или несколько вхождений символа слова или дефиса, за которыми следует ноль или один буквенно-цифровой символ со значением A-Z, a-z или 0-9 с последующей точкой. Этот шаблон может повторяться один или больше раз и после него должно идти доменное имя верхнего уровня. 
`[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))` | Доменное имя должно начинаться с буквы или цифры (a-z, A-Z и 0-9) и заканчиваться на букву или цифру. В него также может входить от 0 до 22 ASCII-символов, которые могут быть буквами, цифрами или дефисом. 
`$` | Совпадение должно заканчиваться в конце строки.
 
Можно вызвать методы `IsValidEmail` и `DomainMapper`, используя следующий код:

```csharp
public class Application
{
   public static void Main()
   {
      RegexUtilities util = new RegexUtilities();
      string[] emailAddresses = { "david.jones@proseware.com", "d.j@server1.proseware.com",
                                  "jones@ms1.proseware.com", "j.@server1.proseware.com",
                                  "j@proseware.com9", "js#internal@proseware.com",
                                  "j_9@[129.126.118.1]", "j..s@proseware.com",
                                  "js*@proseware.com", "js@proseware..com",
                                  "js@proseware.com9", "j.s@server1.proseware.com",
                                   "\"j\\\"s\\\"\"@proseware.com", "js@contoso.中国" };

      foreach (var emailAddress in emailAddresses) {
         if (util.IsValidEmail(emailAddress))
            Console.WriteLine("Valid: {0}", emailAddress);
         else
            Console.WriteLine("Invalid: {0}", emailAddress);
      }                                            
   }
}
// The example displays the following output:
//       Valid: david.jones@proseware.com
//       Valid: d.j@server1.proseware.com
//       Valid: jones@ms1.proseware.com
//       Invalid: j.@server1.proseware.com
//       Valid: j@proseware.com9
//       Valid: js#internal@proseware.com
//       Valid: j_9@[129.126.118.1]
//       Invalid: j..s@proseware.com
//       Invalid: js*@proseware.com
//       Invalid: js@proseware..com
//       Valid: js@proseware.com9
//       Valid: j.s@server1.proseware.com
//       Valid: "j\"s\""@proseware.com
//       Valid: js@contoso.ä¸­å›½
```

```vb
Public Class Application
   Public Shared Sub Main()
      Dim util As New RegexUtilities()
      Dim emailAddresses() As String = { "david.jones@proseware.com", "d.j@server1.proseware.com", _
                                         "jones@ms1.proseware.com", "j.@server1.proseware.com", _
                                         "j@proseware.com9", "js#internal@proseware.com", _
                                         "j_9@[129.126.118.1]", "j..s@proseware.com", _
                                         "js*@proseware.com", "js@proseware..com", _
                                         "js@proseware.com9", "j.s@server1.proseware.com",
                                         """j\""s\""""@proseware.com", "js@contoso.中国" }

      For Each emailAddress As String In emailAddresses
         If util.IsValidEmail(emailAddress) Then
            Console.WriteLine("Valid: {0}", emailAddress)
         Else
            Console.WriteLine("Invalid: {0}", emailAddress)
         End If      
      Next                                            
   End Sub
End Class
' The example displays the following output:
'       Valid: david.jones@proseware.com
'       Valid: d.j@server1.proseware.com
'       Valid: jones@ms1.proseware.com
'       Invalid: j.@server1.proseware.com
'       Valid: j@proseware.com9
'       Valid: js#internal@proseware.com
'       Valid: j_9@[129.126.118.1]
'       Invalid: j..s@proseware.com
'       Invalid: js*@proseware.com
'       Invalid: js@proseware..com
'       Valid: js@proseware.com9
'       Valid: j.s@server1.proseware.com
'       Valid: "j\"s\""@proseware.com
'       Valid: js@contoso.ä¸­å›½
```

## <a name="see-also"></a>См. также

[Регулярные выражения .NET](regular-expressions.md)

[Примеры регулярных выражений](regex-examples.md)

