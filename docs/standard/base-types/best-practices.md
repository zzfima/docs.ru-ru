---
title: "Рекомендации по использованию регулярных выражений"
description: "Рекомендации по использованию регулярных выражений"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 096fd614-91bf-4296-be24-12f62b062294
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 00c7228c5cb906f41df5e60a318721008ecf0bb7

---

# <a name="best-practices-for-regular-expressions"></a>Рекомендации по использованию регулярных выражений

Обработчик регулярных выражений в .NET — мощное средство, обрабатывающее текст на основе совпадения шаблонов, а не сравнивающее непосредственно текст. В большинстве случаев сопоставление шаблонов выполняется быстро и эффективно. Однако в некоторых случаях обработчик регулярных выражений может работать очень медленно. В крайних случаях он даже может перестать отвечать, обрабатывая относительно небольшой объем входной информации в течение часов или даже дней. 

В этом разделе приведены некоторые рекомендации для разработчиков по обеспечению оптимальной производительности регулярных выражений. Он содержит следующие подразделы:

* [Учет источника входных данных](#consider-the-input-source)

* [Правильное создание объектов](#handle-object-instantiation-appropriately)

* [Грамотное использование поиска с возвратом](#take-charge-of-backtracking)

* [Использование значений времени ожидания](#use-time-out-values)

* [Захват только в случае необходимости](#capture-only-when-necessary)

* [Связанные статьи](#related-topics)

## <a name="consider-the-input-source"></a>Учет источника входных данных

Регулярные выражения могут принимать два типа входных данных: определенные и произвольные. Определенные входные данные — это текст, происходящий из известного надежного источника в заранее определенном формате. Произвольные входные данные — это текст, происходящий из ненадежного источника, например от пользователя в Интернете, который может не соответствовать заданному или ожидаемому формату.

Шаблоны регулярных выражений обычно ориентированы на подходящие входные данные. Это значит, что разработчик анализирует текст, который требуется найти, и составляет шаблон регулярного выражения. Затем разработчик определяет, требуется ли корректировка шаблона или его уточнение, тестируя его с различными подходящими входными данными. Когда шаблон соответствует всем возможным подходящим вариантам входных данных, считается, что он готов и его можно включить в выпускаемое приложение. В результате этих действий шаблон регулярного выражения готов для сопоставления с определенными входными данными. Но он не готов для сопоставления с произвольными входными данными.

Для сопоставления с произвольными входными данными шаблон регулярного выражения должен уметь обрабатывать три вида текста:

• Текст, соответствующий шаблону регулярного выражения.

• Текст, не соответствующий шаблону регулярного выражения.

• Текст, почти соответствующий шаблону регулярного выражения.

Последний вид текста представляет особую проблему для регулярных выражений, написанных для обработки определенных входных данных. Если в регулярном выражении также широко используется [поиск с возвратом](backtracking.md), обработчик регулярных выражений может неожиданно долго (в некоторых случаях часы или дни) обрабатывать, казалось бы, безобидный текст. 

> [!WARNING]
> В следующем примере используется регулярное выражение, которое подвержено избыточному использованию поиска с возвратом и может отклонить допустимые адреса электронной почты. Использовать его для проверки электронной почты не следует. Если требуется регулярное выражение, проверяющее адреса электронной почты, обратитесь к статье [Практическое руководство. Проверка строк на соответствие формату электронной почты](verify-format.md). 


Например, рассмотрим очень часто используемое и при этом очень проблематичное регулярное выражение для проверки псевдонима адреса электронной почты. Регулярное выражение `^[0-9A-Z]([-.\w]*[0-9A-Z])*$` предназначено для обработки допустимого адреса электронной почты и состоит из алфавитно-цифрового символа, за которым следует ноль или более знаков, которые могут представлять собой алфавитно-цифровые символы, точки или дефисы. Регулярное выражение должно оканчиваться алфавитно-цифровым символом. Однако, как показывает следующий пример, несмотря на то что это регулярное выражение хорошо обрабатывает подходящие входные данные, оно очень неэффективно при обработке почти подходящих входных данных.

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      Stopwatch sw;    
      string[] addresses = { "AAAAAAAAAAA@contoso.com", 
                             "AAAAAAAAAAaaaaaaaaaa!@contoso.com" };
      // The following regular expression should not actually be used to 
      // validate an email address.
      string pattern = @"^[0-9A-Z]([-.\w]*[0-9A-Z])*$";
      string input; 

      foreach (var address in addresses) {
         string mailBox = address.Substring(0, address.IndexOf("@"));       
         int index = 0;
         for (int ctr = mailBox.Length - 1; ctr >= 0; ctr--) {
            index++;

            input = mailBox.Substring(ctr, index); 
            sw = Stopwatch.StartNew();
            Match m = Regex.Match(input, pattern, RegexOptions.IgnoreCase);
            sw.Stop();
            if (m.Success)
               Console.WriteLine("{0,2}. Matched '{1,25}' in {2}", 
                                 index, m.Value, sw.Elapsed);
            else                     
               Console.WriteLine("{0,2}. Failed  '{1,25}' in {2}", 
                                 index, input, sw.Elapsed);
         }
         Console.WriteLine();
      }
   }
}

// The example displays output similar to the following:
//     1. Matched '                        A' in 00:00:00.0007122
//     2. Matched '                       AA' in 00:00:00.0000282
//     3. Matched '                      AAA' in 00:00:00.0000042
//     4. Matched '                     AAAA' in 00:00:00.0000038
//     5. Matched '                    AAAAA' in 00:00:00.0000042
//     6. Matched '                   AAAAAA' in 00:00:00.0000042
//     7. Matched '                  AAAAAAA' in 00:00:00.0000042
//     8. Matched '                 AAAAAAAA' in 00:00:00.0000087
//     9. Matched '                AAAAAAAAA' in 00:00:00.0000045
//    10. Matched '               AAAAAAAAAA' in 00:00:00.0000045
//    11. Matched '              AAAAAAAAAAA' in 00:00:00.0000045
//    
//     1. Failed  '                        !' in 00:00:00.0000447
//     2. Failed  '                       a!' in 00:00:00.0000071
//     3. Failed  '                      aa!' in 00:00:00.0000071
//     4. Failed  '                     aaa!' in 00:00:00.0000061
//     5. Failed  '                    aaaa!' in 00:00:00.0000081
//     6. Failed  '                   aaaaa!' in 00:00:00.0000126
//     7. Failed  '                  aaaaaa!' in 00:00:00.0000359
//     8. Failed  '                 aaaaaaa!' in 00:00:00.0000414
//     9. Failed  '                aaaaaaaa!' in 00:00:00.0000758
//    10. Failed  '               aaaaaaaaa!' in 00:00:00.0001462
//    11. Failed  '              aaaaaaaaaa!' in 00:00:00.0002885
//    12. Failed  '             Aaaaaaaaaaa!' in 00:00:00.0005780
//    13. Failed  '            AAaaaaaaaaaa!' in 00:00:00.0011628
//    14. Failed  '           AAAaaaaaaaaaa!' in 00:00:00.0022851
//    15. Failed  '          AAAAaaaaaaaaaa!' in 00:00:00.0045864
//    16. Failed  '         AAAAAaaaaaaaaaa!' in 00:00:00.0093168
//    17. Failed  '        AAAAAAaaaaaaaaaa!' in 00:00:00.0185993
//    18. Failed  '       AAAAAAAaaaaaaaaaa!' in 00:00:00.0366723
//    19. Failed  '      AAAAAAAAaaaaaaaaaa!' in 00:00:00.1370108
//    20. Failed  '     AAAAAAAAAaaaaaaaaaa!' in 00:00:00.1553966
//    21. Failed  '    AAAAAAAAAAaaaaaaaaaa!' in 00:00:00.3223372
```

```vb
Imports System.Diagnostics
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim sw As Stopwatch    
      Dim addresses() As String = { "AAAAAAAAAAA@contoso.com", 
                                 "AAAAAAAAAAaaaaaaaaaa!@contoso.com" }
      ' The following regular expression should not actually be used to 
      ' validate an email address.
      Dim pattern As String = "^[0-9A-Z]([-.\w]*[0-9A-Z])*$"
      Dim input As String 

      For Each address In addresses
         Dim mailBox As String = address.Substring(0, address.IndexOf("@"))       
         Dim index As Integer = 0
         For ctr As Integer = mailBox.Length - 1 To 0 Step -1
            index += 1
            input = mailBox.Substring(ctr, index) 
            sw = Stopwatch.StartNew()
            Dim m As Match = Regex.Match(input, pattern, RegexOptions.IgnoreCase)
            sw.Stop()
            if m.Success Then
               Console.WriteLine("{0,2}. Matched '{1,25}' in {2}", 
                                 index, m.Value, sw.Elapsed)
            Else                     
               Console.WriteLine("{0,2}. Failed  '{1,25}' in {2}", 
                                 index, input, sw.Elapsed)
            End If                  
         Next
         Console.WriteLine()
      Next
   End Sub
End Module
' The example displays output similar to the following:
'     1. Matched '                        A' in 00:00:00.0007122
'     2. Matched '                       AA' in 00:00:00.0000282
'     3. Matched '                      AAA' in 00:00:00.0000042
'     4. Matched '                     AAAA' in 00:00:00.0000038
'     5. Matched '                    AAAAA' in 00:00:00.0000042
'     6. Matched '                   AAAAAA' in 00:00:00.0000042
'     7. Matched '                  AAAAAAA' in 00:00:00.0000042
'     8. Matched '                 AAAAAAAA' in 00:00:00.0000087
'     9. Matched '                AAAAAAAAA' in 00:00:00.0000045
'    10. Matched '               AAAAAAAAAA' in 00:00:00.0000045
'    11. Matched '              AAAAAAAAAAA' in 00:00:00.0000045
'    
'     1. Failed  '                        !' in 00:00:00.0000447
'     2. Failed  '                       a!' in 00:00:00.0000071
'     3. Failed  '                      aa!' in 00:00:00.0000071
'     4. Failed  '                     aaa!' in 00:00:00.0000061
'     5. Failed  '                    aaaa!' in 00:00:00.0000081
'     6. Failed  '                   aaaaa!' in 00:00:00.0000126
'     7. Failed  '                  aaaaaa!' in 00:00:00.0000359
'     8. Failed  '                 aaaaaaa!' in 00:00:00.0000414
'     9. Failed  '                aaaaaaaa!' in 00:00:00.0000758
'    10. Failed  '               aaaaaaaaa!' in 00:00:00.0001462
'    11. Failed  '              aaaaaaaaaa!' in 00:00:00.0002885
'    12. Failed  '             Aaaaaaaaaaa!' in 00:00:00.0005780
'    13. Failed  '            AAaaaaaaaaaa!' in 00:00:00.0011628
'    14. Failed  '           AAAaaaaaaaaaa!' in 00:00:00.0022851
'    15. Failed  '          AAAAaaaaaaaaaa!' in 00:00:00.0045864
'    16. Failed  '         AAAAAaaaaaaaaaa!' in 00:00:00.0093168
'    17. Failed  '        AAAAAAaaaaaaaaaa!' in 00:00:00.0185993
'    18. Failed  '       AAAAAAAaaaaaaaaaa!' in 00:00:00.0366723
'    19. Failed  '      AAAAAAAAaaaaaaaaaa!' in 00:00:00.1370108
'    20. Failed  '     AAAAAAAAAaaaaaaaaaa!' in 00:00:00.1553966
'    21. Failed  '    AAAAAAAAAAaaaaaaaaaa!' in 00:00:00.3223372
```

Как видно по выводу примера, обработчик регулярных выражений обрабатывает подходящие псевдонимы электронной почты различной длины практически за одинаковое время. С другой стороны, если почти подходящий адрес электронной почты содержит более 5 символов, время обработки удваивается для каждого дополнительного символа в строке. Это значит, что почти подходящая строка из 28 символов будет обрабатываться более часа, а на обработку почти подходящей строки из 33 символов уйдет около дня. 

Поскольку это регулярное выражение ориентировано только на формат подходящих входных данных, оно плохо работает со входными данными, не соответствующими шаблону. А это может привести к тому, что произвольные входные данные, почти соответствующие шаблону регулярного выражения, могут существенно снизить производительность.

Чтобы устранить эту проблему, можно выполнить одно из следующих действий.

* При создании шаблона необходимо учитывать, как поиск с возвратом может повлиять на производительность обработчика регулярных выражений, особенно если регулярное выражение должно обрабатывать произвольные входные данные. Дополнительные сведения см. в разделе [Грамотное использование поиска с возвратом](#take-charge-of-backtracking).

* Следует тщательно протестировать регулярное выражение с использованием неподходящих и почти подходящих входных данных. Для генерации произвольных входных данных для конкретного регулярного выражения можно использовать [Rex](http://research.microsoft.com/en-us/projects/rex/) — средство исследования регулярных выражений, разработанное группой Microsoft Research.

## <a name="handle-object-instantiation-appropriately"></a>Правильное создание объектов

Сердцем объектной модели регулярных выражений .NET является класс [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex), представляющий обработчик регулярных выражений. Часто производительность регулярного выражения зависит именно от того, как используется обработчик [Regex](xref:System.Text.RegularExpressions.Regex). Определение регулярного выражения предполагает установление тесной взаимозависимости между обработчиком регулярных выражений и шаблоном регулярного выражения. Процесс установления этой взаимозависимости является затратным, независимо от того, происходит ли создание объекта [Regex](xref:System.Text.RegularExpressions.Regex) путем передачи его конструктору шаблона регулярного выражения или вызов статического метода путем передачи ему шаблона регулярного выражения и входной строки.

Можно установить связь между обработчиком регулярных выражений и конкретным шаблоном регулярного выражения, а затем использовать обработчик для поиска совпадения в тексте несколькими способами.

* Можно вызвать статический метод поиска совпадения с шаблоном, такой как [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String)). При этом не требуется создание объекта регулярного выражения.

* Можно создать экземпляр объекта [Regex](xref:System.Text.RegularExpressions.Regex) и вызвать метод поиска совпадения с шаблоном этого экземпляра для интерпретированного регулярного выражения. Это метод по умолчанию для привязки обработчика регулярных выражений к шаблону регулярного выражения. Он дает результат, когда объект [Regex](xref:System.Text.RegularExpressions.Regex) создается без аргумента options, который включает флаг [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled).

* Можно создать экземпляр объекта [Regex](xref:System.Text.RegularExpressions.Regex) и вызвать метод поиска совпадения с шаблоном этого экземпляра для скомпилированного регулярного выражения. Объекты регулярных выражений представляют скомпилированные шаблоны, когда объект [Regex](xref:System.Text.RegularExpressions.Regex) создается с аргументом options с флагом [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled).

> [!IMPORTANT]
> Способ вызова метода (статический, интерпретированный, скомпилированный) влияет на производительность, если одно регулярное выражение используется многократно при вызове методов или если приложение активно использует объекты регулярных выражений.
 
### <a name="static-regular-expressions"></a>Статические регулярные выражения

Статические методы регулярных выражений рекомендуется использовать как альтернативу многократному созданию объектов регулярных выражений с одним регулярным выражением. В отличие от шаблонов регулярных выражений, используемых объектами регулярных выражений, коды операций или скомпилированный MSIL-код шаблонов, используемых при вызове методов экземпляра, кэшируются внутренне обработчиком регулярных выражений. 

Например, можно вызывать метод для проверки ввода пользователя. В этом примере метод с именем `IsValidCurrency` проверяет, что пользователь ввел обозначение денежной единицы и еще по крайней мере один десятичный знак. Очень неэффективная реализация метода `IsValidCurrency` показана в следующем примере. Обратите внимание, что при каждом вызове метода заново создается объект [Regex](xref:System.Text.RegularExpressions.Regex) с одним и тем же шаблоном. А это значит, что шаблон регулярного выражения перекомпилируется при каждом вызове метода.

```csharp
using System;
using System.Text.RegularExpressions;

public class RegexLib
{
   public static bool IsValidCurrency(string currencyValue)
   {
      string pattern = @"\p{Sc}+\s*\d+";
      Regex currencyRegex = new Regex(pattern);
      return currencyRegex.IsMatch(currencyValue);
   }
}
```

```vb
Public Sub OKButton_Click(sender As Object, e As EventArgs) _ 
           Handles OKButton.Click

   If Not String.IsNullOrEmpty(sourceCurrency.Text) Then
      If RegexLib.IsValidCurrency(sourceCurrency.Text) Then
         PerformConversion()
      Else
         status.Text = "The source currency value is invalid."
      End If          
   End If
End Sub
```

Этот неэффективный код следует заменить вызовом статического метода [Regex.IsMatch(String, String)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String)). Исчезнет необходимость заново создавать объект [Regex](xref:System.Text.RegularExpressions.Regex) при каждом вызове метода поиска совпадения с шаблоном, обработчик регулярных выражений сможет извлекать скомпилированную версию регулярного выражения из кэша.

```csharp
using System;
using System.Text.RegularExpressions;

public class RegexLib
{
   public static bool IsValidCurrency(string currencyValue)
   {
      string pattern = @"\p{Sc}+\s*\d+";
      return Regex.IsMatch(currencyValue, pattern); 
   }
}
```

```vb
Imports System.Text.RegularExpressions

Public Module RegexLib
   Public Function IsValidCurrency(currencyValue As String) As Boolean
      Dim pattern As String = "\p{Sc}+\s*\d+"
      Return Regex.IsMatch(currencyValue, pattern)
   End Function
End Module
```

По умолчанию кэшируется 15 последних использованных шаблонов статических регулярных выражений. Для приложений, которым требуется большее число кэшированных статических регулярных выражений, размер кэша можно задать с помощью свойства [Regex.CacheSize](xref:System.Text.RegularExpressions.Regex.CacheSize).

Регулярное выражение `\p{Sc}+\s*\d+`, используемое в этом примере, проверяет, что входная строка состоит из обозначения валюты и по меньшей мере одного десятичного знака. Шаблон определяется, как показано в следующей таблице.

Шаблон | Описание
------- | -----------
`\p{Sc}+` | Совпадение с одним или несколькими символами Unicode Symbol, Currency (символ валюты в Юникоде).
`\s*` | Соответствует нулю или нескольким символам пробела.
`\d+` | Совпадение с одной или несколькими десятичными цифрами.
 
### <a name="interpreted-vs-compiled-regular-expressions"></a>Интерпретированные и скомпилированные регулярные выражения

Шаблоны регулярных выражений, не привязанные к обработчику регулярных выражений указанием параметра [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled), интерпретируются. При создании объекта регулярного выражения обработчик регулярных выражений преобразует регулярное выражение в набор кодов операций. При вызове метода экземпляра коды операций преобразуются в MSIL-код и выполняются JIT-компилятором. Аналогично, при вызове статического метода регулярного выражения, если не удается найти регулярное выражение в кэше, обработчик регулярных выражений преобразует регулярное выражение в набор кодов операций и хранит их в кэше. Затем эти коды операций преобразуются в MSIL-код, чтобы JIT-компилятор мог выполнить их. Интерпретированные регулярные выражения снижают время запуска ценой более медленного выполнения. Поэтому их лучше всего использовать, когда регулярное выражение используется с небольшим числом вызовов методов или если точное число вызовов методов регулярных выражений неизвестно, но предполагается, что оно будет небольшим. По мере увеличения числа вызовов методов выгоду по производительности от быстрого запуска перевешивает низкая скорость выполнения.

Шаблоны регулярных выражений, привязанные к обработчику регулярных выражений указанием параметра [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled), компилируются. Это значит, что при создании объекта регулярного выражения или при вызове статического метода регулярного выражения, если не удается найти регулярное выражение в кэше, обработчик регулярных выражений преобразует регулярное выражение в промежуточный набор кодов операций, который затем преобразуется в MSIL-код. Когда вызывается метод, JIT-компилятор выполняет MSIL-код. В отличие от интерпретированных регулярных выражений, скомпилированные регулярные выражения увеличивают время запуска, но позволяют выполнять отдельные методы поиска совпадения с шаблоном быстрее. В результате выгода по производительности от скомпилированных регулярных выражений увеличивается пропорционально числу вызовов методов регулярных выражений.

Подводя итог, мы рекомендуем использовать интерпретированные регулярные выражения, когда методы регулярного выражения с конкретным регулярным выражением вызываются относительно редко. Скомпилированные регулярные выражения следует использовать, когда методы регулярного выражения с конкретным регулярным выражением вызываются относительно часто. Точное пороговое значение, начиная с которого низкая скорость выполнения интерпретированных регулярных выражений перевешивает выгоду от быстрого запуска, или пороговое значение, при котором медленный запуск скомпилированных регулярных выражений перевешивает выгоду от быстрого выполнения, трудно указать. Оно зависит от нескольких факторов, в том числе от сложности регулярного выражения и конкретных обрабатываемых данных. Чтобы определить, что позволит добиться лучшей производительности — интерпретированные или скомпилированные регулярные выражения, — можно использовать класс [Stopwatch](xref:System.Diagnostics.Stopwatch), чтобы сравнить время выполнения в обоих случаях.

В следующем примере сравнивается производительность скомпилированных и интерпретированных регулярных выражений при чтении первых десяти предложений, а также при чтении всех предложений текста книги "Финансист" Теодора Драйзера. Как показывает вывод примера, если требуется выполнить только 10 вызовов методов поиска совпадения, интерпретированное регулярное выражение дает более высокую производительность. Однако скомпилированное регулярное выражение обеспечивает более высокую производительность при большом числе вызовов (в данном случае 13 000). 

```csharp
using System;
using System.Diagnostics;
using System.IO;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]";
      Stopwatch sw;
      Match match;
      int ctr;

      StreamReader inFile = new StreamReader(@".\Dreiser_TheFinancier.txt");
      string input = inFile.ReadToEnd();
      inFile.Close();

      // Read first ten sentences with interpreted regex.
      Console.WriteLine("10 Sentences with Interpreted Regex:");
      sw = Stopwatch.StartNew();
      Regex int10 = new Regex(pattern, RegexOptions.Singleline);
      match = int10.Match(input);
      for (ctr = 0; ctr <= 9; ctr++) {
         if (match.Success)
            // Do nothing with the match except get the next match.
            match = match.NextMatch();
         else
            break;
      }
      sw.Stop();
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed);

      // Read first ten sentences with compiled regex.
      Console.WriteLine("10 Sentences with Compiled Regex:");
      sw = Stopwatch.StartNew();
      Regex comp10 = new Regex(pattern, 
                   RegexOptions.Singleline | RegexOptions.Compiled);
      match = comp10.Match(input);
      for (ctr = 0; ctr <= 9; ctr++) {
         if (match.Success)
            // Do nothing with the match except get the next match.
            match = match.NextMatch();
         else
            break;
      }
      sw.Stop();
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed);

      // Read all sentences with interpreted regex.
      Console.WriteLine("All Sentences with Interpreted Regex:");
      sw = Stopwatch.StartNew();
      Regex intAll = new Regex(pattern, RegexOptions.Singleline);
      match = intAll.Match(input);
      int matches = 0;
      while (match.Success) {
         matches++;
         // Do nothing with the match except get the next match.
         match = match.NextMatch();
      }
      sw.Stop();
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed);

      // Read all sentnces with compiled regex.
      Console.WriteLine("All Sentences with Compiled Regex:");
      sw = Stopwatch.StartNew();
      Regex compAll = new Regex(pattern, 
                      RegexOptions.Singleline | RegexOptions.Compiled);
      match = compAll.Match(input);
      matches = 0;
      while (match.Success) {
         matches++;
         // Do nothing with the match except get the next match.
         match = match.NextMatch();
      }
      sw.Stop();
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed);      
   }
}
// The example displays the following output:
//       10 Sentences with Interpreted Regex:
//          10 matches in 00:00:00.0047491
//       10 Sentences with Compiled Regex:
//          10 matches in 00:00:00.0141872
//       All Sentences with Interpreted Regex:
//          13,443 matches in 00:00:01.1929928
//       All Sentences with Compiled Regex:
//          13,443 matches in 00:00:00.7635869
//       
//       >compare1
//       10 Sentences with Interpreted Regex:
//          10 matches in 00:00:00.0046914
//       10 Sentences with Compiled Regex:
//          10 matches in 00:00:00.0143727
//       All Sentences with Interpreted Regex:
//          13,443 matches in 00:00:01.1514100
//       All Sentences with Compiled Regex:
//          13,443 matches in 00:00:00.7432921
```

```vb
Imports System.Diagnostics
Imports System.IO
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]"
      Dim sw As Stopwatch
      Dim match As Match
      Dim ctr As Integer

      Dim inFile As New StreamReader(".\Dreiser_TheFinancier.txt")
      Dim input As String = inFile.ReadToEnd()
      inFile.Close()

      ' Read first ten sentences with interpreted regex.
      Console.WriteLine("10 Sentences with Interpreted Regex:")
      sw = Stopwatch.StartNew()
      Dim int10 As New Regex(pattern, RegexOptions.SingleLine)
      match = int10.Match(input)
      For ctr = 0 To 9
         If match.Success Then
            ' Do nothing with the match except get the next match.
            match = match.NextMatch()
         Else
            Exit For
         End If
      Next
      sw.Stop()
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed)

      ' Read first ten sentences with compiled regex.
      Console.WriteLine("10 Sentences with Compiled Regex:")
      sw = Stopwatch.StartNew()
      Dim comp10 As New Regex(pattern, 
                   RegexOptions.SingleLine Or RegexOptions.Compiled)
      match = comp10.Match(input)
      For ctr = 0 To 9
         If match.Success Then
            ' Do nothing with the match except get the next match.
            match = match.NextMatch()
         Else
            Exit For
         End If
      Next
      sw.Stop()
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed)

      ' Read all sentences with interpreted regex.
      Console.WriteLine("All Sentences with Interpreted Regex:")
      sw = Stopwatch.StartNew()
      Dim intAll As New Regex(pattern, RegexOptions.SingleLine)
      match = intAll.Match(input)
      Dim matches As Integer = 0
      Do While match.Success
         matches += 1
         ' Do nothing with the match except get the next match.
         match = match.NextMatch()
      Loop
      sw.Stop()
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed)

      ' Read all sentnces with compiled regex.
      Console.WriteLine("All Sentences with Compiled Regex:")
      sw = Stopwatch.StartNew()
      Dim compAll As New Regex(pattern, 
                     RegexOptions.SingleLine Or RegexOptions.Compiled)
      match = compAll.Match(input)
      matches = 0
      Do While match.Success
         matches += 1
         ' Do nothing with the match except get the next match.
         match = match.NextMatch()
      Loop
      sw.Stop()
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed)      
   End Sub
End Module
' The example displays output like the following:
'       10 Sentences with Interpreted Regex:
'          10 matches in 00:00:00.0047491
'       10 Sentences with Compiled Regex:
'          10 matches in 00:00:00.0141872
'       All Sentences with Interpreted Regex:
'          13,443 matches in 00:00:01.1929928
'       All Sentences with Compiled Regex:
'          13,443 matches in 00:00:00.7635869
'       
'       >compare1
'       10 Sentences with Interpreted Regex:
'          10 matches in 00:00:00.0046914
'       10 Sentences with Compiled Regex:
'          10 matches in 00:00:00.0143727
'       All Sentences with Interpreted Regex:
'          13,443 matches in 00:00:01.1514100
'       All Sentences with Compiled Regex:
'          13,443 matches in 00:00:00.7432921
```

Используемый в примере шаблон регулярного выражения `\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]` определяется, как показано в следующей таблице.

Шаблон | Описание
------- | -----------
`\b` | Совпадение должно начинаться на границе слова.
`\w+` | Совпадение с одним или несколькими символами слова.
(\r?\n)|,?\s) | Соответствует нулю или одному возврату каретки и последующему символу новой строки; или нулю или одной запятой с последующим пробелом.
(\w+((\r?\n)|,?\s))* | Совпадение с одним или несколькими символами слова, за которыми следует ноль или один возврат каретки и символ новой строки, или ноль или одна запятая с последующим пробелом.
`\w+` | Совпадение с одним или несколькими символами слова.
`[.?:;!]` | Совпадение с точкой, вопросительным знаком, двоеточием, точкой с запятой или восклицательным знаком.
 
## <a name="take-charge-of-backtracking"></a>Грамотное использование поиска с возвратом

Обычно обработчик регулярных выражений двигается по входной строке линейным образом, сравнивая ее с шаблоном регулярного выражения. Однако когда в шаблоне регулярного выражения используются неопределенные квантификаторы, такие как __*__, **+** и **?**, обработчик регулярных выражений может отбрасывать частичное совпадение и возвращаться к ранее сохраненному состоянию, чтобы искать совпадение с шаблоном целиком. Этот процесс известен как поиск с возвратом.

> [!NOTE]
> Дополнительные сведения о поиске с возвратом см. в статьях [Подробные сведения о поведении регулярных выражений](regex-behavior.md) и [Поиск с возвратом в регулярных выражениях](backtracking.md).
 
Поддержка поиска с возвратом обеспечивает мощность и гибкость регулярных выражений. При этом ответственность за управление работой обработчика регулярных выражений лежит на разработчике регулярных выражений. Поскольку разработчики часто не отдают себе отчет в этой ответственности, неправильное или излишнее использование поиска с возвратом часто становится причиной снижения производительности регулярных выражений. В самом неблагоприятном случае время обработки может удваиваться при каждом добавлении символа во входную строку. Чрезмерно используя поиск с возвратом, очень легко создать программный аналог бесконечной петли, если входные данные почти совпадают с шаблоном регулярного выражения. Обработчик регулярных выражений может в течение часов или даже дней обрабатывать относительно короткую входную строку.

Часто приложения имеют сниженную производительность из-за использования поиска с возвратом, хотя поиск с возвратом не очень важен для обнаружения совпадения. Например, регулярное выражение `\b\p{Lu}\w*\b` совпадает со всеми словами, начинающимися с символа верхнего регистра, как показано в следующей таблице.

Шаблон | Описание
------- | -----------
`\b` | Совпадение должно начинаться на границе слова.
`\p{Lu}` | Совпадение с символом верхнего регистра.
`\w*` | Совпадение с нулем или большим числом буквенных символов.
`\b` | Совпадение должно заканчиваться на границе слова.
 
Поскольку граница слова не является символом слова (или подмножеством символов слова), нет шанса, что регулярное выражение перейдет границу слова, сопоставляя символы слова. Это значит, что для этого регулярного выражения поиск с возвратом не принесет никакой пользы, а только снизит производительность, поскольку обработчик регулярных выражений вынужден сохранять свое состояние для каждого возможного совпадения.

Если вы понимаете, что нет необходимости использовать поиск с возвратом, его можно отключить с помощью языкового элемента **(?>**_subexpression_**)**. В следующем примере производится анализ входной строки с использованием двух регулярных выражений. Функционирование первого регулярного выражения, `\b\p{Lu}\w*\b`, основано на поиске с возвратом. Второе регулярное выражение, `\b\p{Lu}(?>\w*)\b`, отключает поиск с возвратом. Как видно по выводу, выражения дают одинаковый результат.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This this word Sentence name Capital";
      string pattern = @"\b\p{Lu}\w*\b";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);

      Console.WriteLine();

      pattern = @"\b\p{Lu}(?>\w*)\b";   
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       This
//       Sentence
//       Capital
//       
//       This
//       Sentence
//       Capital
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This this word Sentence name Capital"
      Dim pattern As String = "\b\p{Lu}\w*\b"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
      Console.WriteLine()

      pattern = "\b\p{Lu}(?>\w*)\b"   
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       This
'       Sentence
'       Capital
'       
'       This
'       Sentence
'       Capital
```

Часто поиск с возвратом очень важен для поиска во входной строке совпадения с шаблоном регулярного выражения. Тем не менее избыточное использование поиска с возвратом может сильно снизить производительность и создать впечатление, что приложение перестало отвечать. Например, так происходит, когда используются вложенные квантификаторы и текст, совпадающий со внешней частью выражения, является подмножеством текста, совпадающего со внутренней частью выражения. 

> [!WARNING]
> Помимо того, что следует избегать избыточного использования поиска с возвратом, необходимо использовать возможность времени ожидания, чтобы убедиться, что избыточный поиск с возвратом не слишком сильно снижает производительность регулярного выражения. Дополнительные сведения см. в разделе [Использование значений времени ожидания](#use-time-out-values).
 
Например, шаблон регулярного выражения `^[0-9A-Z]([-.\w]*[0-9A-Z])*\$$` должен искать номер части, состоящий из по крайней мере одного алфавитно-цифрового символа. Дополнительные символы могут включать в себя алфавитно-цифровые символы, дефис, подчеркивание или точку, но последний символ должен быть алфавитно-цифровым. Знак доллара завершает номер части. В некоторых случаях этот шаблон регулярного выражения может привести к очень низкой производительности, поскольку в нем используются вложенные квантификаторы и часть выражения `[0-9A-Z]` является подмножеством части выражения `[-.\w]*`.

В таких случаях можно оптимизировать производительность, удалив вложенные квантификаторы и заменив внешнюю часть выражения утверждением просмотра вперед или назад нулевой ширины. Утверждения просмотра вперед и назад являются "якорями". Они не перемещают указатель во входной строке, а выполняют поиск впереди или позади, проверяя, выполняется ли заданное условие. Например, регулярное выражение для поиска номера части можно записать следующим образом: `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$`. Этот шаблон регулярного выражения определяется, как показано в следующей таблице.

Шаблон | Описание
------- | -----------
`^` | Начало совпадения в начале входной строки.
`[0-9A-Z]` | Совпадение с алфавитно-цифровым символом. Номер части должен состоять по меньшей мере из этого символа.
`[-.\w]*` | Совпадение с нулем или большим числом вхождений любого символа слова, дефиса или точки.
`\$] | Совпадение со знаком доллара.
`(?<=[0-9A-Z])` | Посмотреть перед конечным знаком доллара, чтобы проверить, что предыдущий символ — это алфавитно-цифровой символ.
`$`: совпадение должно заканчиваться в конце входной строки.
 
В приведенном ниже примере демонстрируется использование этого регулярного выражения для поиска совпадений в массиве потенциальных номеров частей.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$";
      string[] partNos = { "A1C$", "A4", "A4$", "A1603D$", "A1603D#" };

      foreach (var input in partNos) {
         Match match = Regex.Match(input, pattern);
         if (match.Success)
            Console.WriteLine(match.Value);
         else
            Console.WriteLine("Match not found.");
      }      
   }
}
// The example displays the following output:
//       A1C$
//       Match not found.
//       A4$
//       A1603D$
//       Match not found.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$"
      Dim partNos() As String = { "A1C$", "A4", "A4$", "A1603D$", 
                                  "A1603D#" }

      For Each input As String In partNos
         Dim match As Match = Regex.Match(input, pattern)
         If match.Success Then
            Console.WriteLine(match.Value)
         Else
            Console.WriteLine("Match not found.")
         End If
      Next      
   End Sub
End Module
' The example displays the following output:
'       A1C$
'       Match not found.
'       A4$
'       A1603D$
'       Match not found.
```

Язык регулярных выражений в .NET включает следующие языковые элементы, которые можно использовать для исключения вложенных квантификаторов. Дополнительные сведения см. в статье [Конструкции группировки в регулярных выражениях](grouping.md).

Элемент языка | Описание
---------------- | ----------- 
**(?**=_subexpression_**)** | Положительный просмотр вперед нулевой ширины. Поиск перед текущей позицией с целью проверить, совпадает ли параметр *subexpression* со входной строкой.
**(?!**_subexpression_**)** | Отрицательный просмотр вперед нулевой ширины. Поиск перед текущей позицией с целью проверить, что параметр *subexpression* не совпадает со входной строкой.
**(?<**=_subexpression_**)** | Положительный просмотр назад нулевой ширины. Поиск за текущей позицией с целью проверить, что параметр *subexpression* совпадает со входной строкой.
**(?<!**_subexpression_**)** | Отрицательный просмотр назад нулевой ширины. Поиск за текущей позицией с целью проверить, что параметр *subexpression* не совпадает со входной строкой.
 
## <a name="use-timeout-values"></a>Использование значений времени ожидания

Если регулярные выражения обрабатывают входные данные, которые почти совпадают с шаблоном регулярного выражения, зачастую они могут использовать избыточный поиск с возвратом, что сильно влияет на их производительность. Помимо того, что следует тщательно обдумывать использование поиска с возвратом и тестировать регулярное выражение на почти совпадающих входных данных, необходимо всегда устанавливать значение времени ожидания для минимизации влияния на производительность избыточного поиска с возвратом, если он все же используется.

Интервал времени ожидания регулярного выражения определяет период времени, в течение которого обработчик регулярных выражений выполняет поиск одного совпадения, после чего время ожидания истекает. По умолчанию интервал времени ожидания равен [Regex.InfiniteMatchTimeout](xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout), что означает, что регулярное выражение имеет неограниченное время ожидания. Можно переопределить это значение и задать интервал времени ожидания следующим образом: 

* предоставив значение времени ожидания при создании экземпляра объекта [Regex](xref:System.Text.RegularExpressions.Regex) путем вызова конструктора [Regex(String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.%23ctor(System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan));

* путем вызова статического метода поиска совпадения с шаблоном, такого как [Regex.Match(String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) или [Regex.Replace(String, String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)), который имеет параметр *matchTimeout*.

Если определен интервал времени ожидания и по истечении этого интервала совпадение не найдено, метод регулярного выражения вызывает исключение [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException). В обработчике исключений можно принять решение о том, повторить ли поиск совпадения с более длинным интервалом времени ожидания, отказаться от попытки поиска совпадения и предположить, что совпадение не найдено, или же отказаться от попытки поиска совпадения и зарегистрировать сведения об исключении в журнале для анализа в дальнейшем.

В следующем примере определяется метод `GetWordData`, который создает регулярное выражение с интервалом времени ожидания 350 миллисекунд, чтобы вычислить количество слов и среднее количество символов в слове в текстовом документе. Если время ожидания для операции поиска совпадения истекает, интервал времени ожидания увеличивается на 350 миллисекунд, и объект [Regex](xref:System.Text.RegularExpressions.Regex) создается заново. Если новый интервал времени ожидания превышает 1 секунду, метод передает исключение вызывающему объекту.

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      RegexUtilities util = new RegexUtilities();
      string title = "Doyle - The Hound of the Baskervilles.txt";
      try {
         var info = util.GetWordData(title);
         Console.WriteLine("Words:               {0:N0}", info.Item1);
         Console.WriteLine("Average Word Length: {0:N2} characters", info.Item2); 
      }
      catch (IOException e) {
         Console.WriteLine("IOException reading file '{0}'", title);
         Console.WriteLine(e.Message);
      }
      catch (RegexMatchTimeoutException e) {
         Console.WriteLine("The operation timed out after {0:N0} milliseconds", 
                           e.MatchTimeout.TotalMilliseconds);
      }
   }
}

public class RegexUtilities
{
   public Tuple<int, double> GetWordData(string filename)
   { 
      const int MAX_TIMEOUT = 1000;   // Maximum timeout interval in milliseconds.
      const int INCREMENT = 350;      // Milliseconds increment of timeout.

      List<string> exclusions = new List<string>( new string[] { "a", "an", "the" });
      int[] wordLengths = new int[29];        // Allocate an array of more than ample size.
      string input = null;
      StreamReader sr = null;
      try { 
         sr = new StreamReader(filename);
         input = sr.ReadToEnd();
      }
      catch (FileNotFoundException e) {
         string msg = String.Format("Unable to find the file '{0}'", filename);
         throw new IOException(msg, e);
      }
      catch (IOException e) {
         throw new IOException(e.Message, e);
      }
      finally {
         if (sr != null) sr.Close(); 
      }

      int timeoutInterval = INCREMENT;
      bool init = false;
      Regex rgx = null;
      Match m = null;
      int indexPos = 0;  
      do {
         try {
            if (! init) {
               rgx = new Regex(@"\b\w+\b", RegexOptions.None, 
                               TimeSpan.FromMilliseconds(timeoutInterval));
               m = rgx.Match(input, indexPos);
               init = true;
            }
            else { 
               m = m.NextMatch();
            }
            if (m.Success) {    
               if ( !exclusions.Contains(m.Value.ToLower()))
                  wordLengths[m.Value.Length]++;

               indexPos += m.Length + 1;   
            }
         }
         catch (RegexMatchTimeoutException e) {
            if (e.MatchTimeout.TotalMilliseconds < MAX_TIMEOUT) {
               timeoutInterval += INCREMENT;
               init = false;
            }
            else {
               // Rethrow the exception.
               throw; 
            }   
         }          
      } while (m.Success);

      // If regex completed successfully, calculate number of words and average length.
      int nWords = 0; 
      long totalLength = 0;

      for (int ctr = wordLengths.GetLowerBound(0); ctr <= wordLengths.GetUpperBound(0); ctr++) {
         nWords += wordLengths[ctr];
         totalLength += ctr * wordLengths[ctr];
      }
      return new Tuple<int, double>(nWords, totalLength/nWords);
   }
}
```

```vb
Imports System.Collections.Generic
Imports System.IO
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim util As New RegexUtilities()
      Dim title As String = "Doyle - The Hound of the Baskervilles.txt"
      Try
         Dim info = util.GetWordData(title)
         Console.WriteLine("Words:               {0:N0}", info.Item1)
         Console.WriteLine("Average Word Length: {0:N2} characters", info.Item2) 
      Catch e As IOException
         Console.WriteLine("IOException reading file '{0}'", title)
         Console.WriteLine(e.Message)
      Catch e As RegexMatchTimeoutException
         Console.WriteLine("The operation timed out after {0:N0} milliseconds", 
                           e.MatchTimeout.TotalMilliseconds)
      End Try
   End Sub
End Module

Public Class RegexUtilities
   Public Function GetWordData(filename As String) As Tuple(Of Integer, Double) 
      Const MAX_TIMEOUT As Integer = 1000  ' Maximum timeout interval in milliseconds.
      Const INCREMENT As Integer = 350     ' Milliseconds increment of timeout.

      Dim exclusions As New List(Of String)({"a", "an", "the" })
      Dim wordLengths(30) As Integer        ' Allocate an array of more than ample size.
      Dim input As String = Nothing
      Dim sr As StreamReader = Nothing
      Try 
         sr = New StreamReader(filename)
         input = sr.ReadToEnd()
      Catch e As FileNotFoundException
         Dim msg As String = String.Format("Unable to find the file '{0}'", filename)
         Throw New IOException(msg, e)
      Catch e As IOException
         Throw New IOException(e.Message, e)
      Finally
         If sr IsNot Nothing Then sr.Close() 
      End Try

      Dim timeoutInterval As Integer = INCREMENT
      Dim init As Boolean = False
      Dim rgx As Regex = Nothing
      Dim m As Match = Nothing
      Dim indexPos As Integer = 0  
      Do
         Try
            If Not init Then
               rgx = New Regex("\b\w+\b", RegexOptions.None, 
                               TimeSpan.FromMilliseconds(timeoutInterval))
               m = rgx.Match(input, indexPos)
               init = True
            Else 
               m = m.NextMatch()
            End If
            If m.Success Then    
               If Not exclusions.Contains(m.Value.ToLower()) Then
                  wordLengths(m.Value.Length) += 1
               End If
               indexPos += m.Length + 1   
            End If
         Catch e As RegexMatchTimeoutException
            If e.MatchTimeout.TotalMilliseconds < MAX_TIMEOUT Then
               timeoutInterval += INCREMENT
               init = False
            Else
               ' Rethrow the exception.
               Throw 
            End If   
         End Try          
      Loop While m.Success

      ' If regex completed successfully, calculate number of words and average length.
      Dim nWords As Integer
      Dim totalLength As Long

      For ctr As Integer = wordLengths.GetLowerBound(0) To wordLengths.GetUpperBound(0)
         nWords += wordLengths(ctr)
         totalLength += ctr * wordLengths(ctr)
      Next
      Return New Tuple(Of Integer, Double)(nWords, totalLength/nWords)
   End Function
End Class
```

## <a name="capture-only-when-necessary"></a>Захват только в случае необходимости

Регулярные выражения в .NET поддерживают ряд конструкций группирования, позволяющих группировать шаблон регулярного выражения в виде одной или более частей. Наиболее часто в языке регулярных выражений .NET используются конструкции группирования **(**_subexpression_**)**, которая определяет нумерованную группу записи, и **(?<*_name_**>**_subexpression_**)**, которая определяет именованную группу записи. Конструкции группирования крайне важны для создания обратных ссылок и для определения части выражения, к которой должен применяться квантификатор. 

Однако использование этих языковых элементов имеет последствия. Объект [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection), возвращаемый свойством [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups), заполняется наиболее новыми неименованными или именованными захваченными объектами, и если одна конструкция группирования захватила несколько подстрок из входной строки, они заполняют объект [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection), возвращаемый свойством [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) определенной группы захвата с несколькими объектами [Capture](xref:System.Text.RegularExpressions.Capture).

Часто конструкции группирования используются в регулярном выражении только для того, чтобы к нему можно было применить квантификаторы, и группы, захваченные этими частями выражения затем не используются. Например, регулярное выражение `\b(\w+[;,]?\s?)+[.?!]` предназначено для записи всего предложения. В следующей таблице описаны языковые элементы этого шаблона регулярных выражений и их влияние на коллекции [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) и [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) объекта [Match](xref:System.Text.RegularExpressions.Match).

Шаблон | Описание
------- | -----------
`\b` | Совпадение должно начинаться на границе слова.
`\w+` | Совпадение с одним или несколькими символами слова.
`[;,]?` | Совпадение с нулем или одной запятой или точкой с запятой.
`\s?` | Совпадение с нулем или одним символом пробела.
`(\w+[;,]?\s?)+` | Совпадение с одним или большим числом символов слова; затем, необязательно, запятой или точкой с запятой; затем, необязательно, пробелом. Здесь определена первая группа захвата, которая необходима, чтобы набор нескольких символов слова (то есть слово) и необязательно следующий за ним знак препинания повторялись, пока регулярное выражение не достигнет конца предложения.
`[.?!]` | Совпадение с точкой, вопросительным знаком или восклицательным знаком.
 
Как показано в следующем примере, когда совпадение найдено, объекты [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) и [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) заполняются захваченными объектами из совпадения. В этом случае используется группа записи `(\w+[;,]?\s?)`, чтобы к ней можно было применить квантификатор **+**, который позволяет шаблону регулярного выражения сопоставить каждое слово в предложении. В противном случае было бы найдено совпадение только с последним словом предложения.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is one sentence. This is another.";
      string pattern = @"\b(\w+[;,]?\s?)+[.?!]";

      foreach (Match match in Regex.Matches(input, pattern)) {
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index);
         int grpCtr = 0;
         foreach (Group grp in match.Groups) {
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index);
            int capCtr = 0;
            foreach (Capture cap in grp.Captures) {
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index);
               capCtr++;
            }
            grpCtr++;
         }          
         Console.WriteLine();        
      }
   }
}
// The example displays the following output:
//       Match: 'This is one sentence.' at index 0.
//          Group 0: 'This is one sentence.' at index 0.
//             Capture 0: 'This is one sentence.' at 0.
//          Group 1: 'sentence' at index 12.
//             Capture 0: 'This ' at 0.
//             Capture 1: 'is ' at 5.
//             Capture 2: 'one ' at 8.
//             Capture 3: 'sentence' at 12.
//       
//       Match: 'This is another.' at index 22.
//          Group 0: 'This is another.' at index 22.
//             Capture 0: 'This is another.' at 22.
//          Group 1: 'another' at index 30.
//             Capture 0: 'This ' at 22.
//             Capture 1: 'is ' at 27.
//             Capture 2: 'another' at 30.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is one sentence. This is another."
      Dim pattern As String = "\b(\w+[;,]?\s?)+[.?!]"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index)
         Dim grpCtr As Integer = 0
         For Each grp As Group In match.Groups
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index)
            Dim capCtr As Integer = 0
            For Each cap As Capture In grp.Captures
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index)
               capCtr += 1
            Next
            grpCtr += 1
         Next          
         Console.WriteLine()        
      Next    
   End Sub
End Module
' The example displays the following output:
'       Match: 'This is one sentence.' at index 0.
'          Group 0: 'This is one sentence.' at index 0.
'             Capture 0: 'This is one sentence.' at 0.
'          Group 1: 'sentence' at index 12.
'             Capture 0: 'This ' at 0.
'             Capture 1: 'is ' at 5.
'             Capture 2: 'one ' at 8.
'             Capture 3: 'sentence' at 12.
'       
'       Match: 'This is another.' at index 22.
'          Group 0: 'This is another.' at index 22.
'             Capture 0: 'This is another.' at 22.
'          Group 1: 'another' at index 30.
'             Capture 0: 'This ' at 22.
'             Capture 1: 'is ' at 27.
'             Capture 2: 'another' at 30.
```

Если части выражения используются только для применения к ним квантификаторов и захваченный текст не нужен, следует отменить захваты групп. Например, языковой элемент **(?:**_subexpression_**)** не позволяет группе, к которой он применен, захватывать совпавшие подстроки. В следующем примере шаблон регулярного выражения из предыдущего примера изменен на `\b(?:\w+[;,]?\s?)+[.?!]`. Как показывает вывод, обработчик регулярных выражений не заполняет коллекции [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) и [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection).

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is one sentence. This is another.";
      string pattern = @"\b(?:\w+[;,]?\s?)+[.?!]";

      foreach (Match match in Regex.Matches(input, pattern)) {
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index);
         int grpCtr = 0;
         foreach (Group grp in match.Groups) {
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index);
            int capCtr = 0;
            foreach (Capture cap in grp.Captures) {
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index);
               capCtr++;
            }
            grpCtr++;
         }          
         Console.WriteLine();        
      }
   }
}
// The example displays the following output:
//       Match: 'This is one sentence.' at index 0.
//          Group 0: 'This is one sentence.' at index 0.
//             Capture 0: 'This is one sentence.' at 0.
//       
//       Match: 'This is another.' at index 22.
//          Group 0: 'This is another.' at index 22.
//             Capture 0: 'This is another.' at 22.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is one sentence. This is another."
      Dim pattern As String = "\b(?:\w+[;,]?\s?)+[.?!]"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index)
         Dim grpCtr As Integer = 0
         For Each grp As Group In match.Groups
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index)
            Dim capCtr As Integer = 0
            For Each cap As Capture In grp.Captures
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index)
               capCtr += 1
            Next
            grpCtr += 1
         Next          
         Console.WriteLine()        
      Next    
   End Sub
End Module
' The example displays the following output:
'       Match: 'This is one sentence.' at index 0.
'          Group 0: 'This is one sentence.' at index 0.
'             Capture 0: 'This is one sentence.' at 0.
'       
'       Match: 'This is another.' at index 22.
'          Group 0: 'This is another.' at index 22.
'             Capture 0: 'This is another.' at 22.
```

Отключить захват можно одним из следующих способов:

* Использовать языковой элемент **(?:**_subexpression_**)**. Этот элемент отключает захват совпавших подстрок в группе, к которой он применен. Во вложенных группах захват подстрок не отключается.

* Использовать параметр [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture). Он отключает все неименованные и неявные захваты для шаблона регулярных выражений. При использовании этого параметра могут захватываться только подстроки, совпадающие с именованными группами, определенными с помощью языкового элемента **(?<**_name_**>**_subexpression_**)**. Флаг [ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) можно передать в параметр options конструктора класса [Regex](xref:System.Text.RegularExpressions.Regex) или в параметр options статического метода поиска совпадения [Regex](xref:System.Text.RegularExpressions.Regex).

* Использовать параметр **n** в языковом элементе **(?imnsx)**. Этот параметр отключает все неименованные или неявные захваты, начиная с того места, на котором находится этот элемент в шаблоне регулярного выражения. Захват отключается либо до конца шаблона, либо пока захват для неименованных и неявных объектов не будет включен параметром **(-n)**. Дополнительные сведения см. в статье [Другие конструкции в регулярных выражениях](miscellaneous.md).

* Использовать параметр **n** в языковом элементе **(?imnsx:**_subexpression_**)**. Этот параметр отключает все неименованные и неявные захваты в части выражения *subexpression*. Захваты для всех вложенных неименованных и неявных групп также отключаются.

## <a name="related-topics"></a>См. также

Заголовок | Описание
----- | ----------- 
[Подробные сведения о поведении регулярных выражений](regex-behavior.md) | Описание реализации обработчика регулярных выражений в .NET. В этом разделе основное внимание уделено гибкости регулярных выражений; кроме того, рассказывается об ответственности разработчика за эффективную и надежную работу обработчика регулярных выражений.
[Поиск с возвратом в регулярных выражениях](backtracking.md) | Описание поиска с возвратом и того, как он влияет на производительность регулярных выражений. Описание языковых элементов, которые можно использовать вместо поиска с возвратом.
[Элементы языка регулярных выражений — краткий справочник](quick-ref.md) | Описание элементов языка регулярных выражений в .NET и ссылки на подробную документацию для каждого языкового элемента.
 




<!--HONumber=Nov16_HO1-->


