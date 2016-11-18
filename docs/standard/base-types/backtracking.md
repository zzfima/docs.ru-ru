---
title: "Поиск с возвратом в регулярных выражениях"
description: "Поиск с возвратом в регулярных выражениях"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 8a3e6298-26b7-4c99-bd97-c9892f6c9418
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 649dfd6752f0589eb396b00e7d0b5184bb65d488

---

# <a name="backtracking-in-regular-expressions"></a>Поиск с возвратом в регулярных выражениях

Поиск с возвратом происходит, если шаблон регулярного выражения содержит переменные [квантификаторы](quantifiers.md) или [конструкции изменения](alternation.md), и обработчик регулярных выражений возвращается в предыдущее сохраненное состояние, чтобы продолжить поиск совпадения. В поиске с возвратом заключена сила регулярных выражений. Благодаря ему выражения могут быть мощными и гибкими, а также совпадать со сложными шаблонами. С другой стороны, эти возможности дорого обходятся. Часто именно поиск с возвратом существенно снижает производительность обработчика регулярных выражений. К счастью, разработчик может управлять работой обработчика регулярных выражений и тем, как он использует поиск с возвратом. В этом разделе описано, как функционирует поиск с возвратом, и как им можно управлять.

> [!NOTE]
> В целом при использовании NFA-машины (недетерминированного конечного автомата), такой как обработчик регулярных выражений .NET, ответственность за создание эффективных и быстро выполняемых регулярных выражений лежит на разработчике.
 
В этом разделе содержатся следующие подразделы.

* [Линейное сравнение без поиска с возвратом](#linear-comparison-without-backtracking)

* [Поиск с возвратом с необязательными квантификаторами и конструкциями чередования](#backtracking-with-optional-quantifiers-or-alternation-constructs)

* [Поиск с возвратом со вложенными необязательными квантификаторами](#backtracking-with-nested-optional-quantifiers)

* [Управление поиском с возвратом](#controlling-backtracking)

## <a name="linear-comparison-without-backtracking"></a>Линейное сравнение без поиска с возвратом

Если шаблон регулярного выражения не содержит переменных квантификаторов или конструкций изменения, обработчик регулярных выражений работает за линейное время. Это значит, что когда обработчик регулярных выражений находит совпадение с первым языковым элементом шаблона в тексте входной строки, он сопоставляет следующий языковой элемент шаблона со следующим символом или группой символов входной строки. Так продолжается, пока поиск совпадения не заканчивается успешно или неуспешно. В обоих случаях обработчик регулярных выражений продвигается вперед, обрабатывая по одному символу входной строки.

Ниже приведен пример. Регулярное выражение `e{2}\w\b` ищет следующую строку: два вхождения буквы «e», затем символ слова, затем граница слова.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "needing a reed";
      string pattern = @"e{2}\w\b";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("{0} found at position {1}", 
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       eed found at position 11
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "needing a reed"
      Dim pattern As String = "e{2}\w\b"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("{0} found at position {1}", _
                           match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       eed found at position 11
```

Несмотря на то что это регулярное выражение содержит квантификатор `{2}`, оно обрабатывается линейным образом. Обработчик регулярных выражений не выполняет поиск с возвратом, поскольку квантификатор `{2}` не является переменным квантификатором; он указывает конкретное, а не переменное число вхождений предшествующей части выражения. В результате обработчик регулярных выражений ищет совпадение с шаблоном во входной строке, как показано в следующей таблице.

Операция | Положение в шаблоне | Положение в строке | Результат
--------- | ------------------- | ------------------ | ------ 
1 | й | "needing a reed" (позиция 0) | Нет совпадения. 
2 | й | "eeding a reed" (позиция 1) | Возможное совпадение. 
3 | e{2} | "eding a reed" (позиция 2) | Возможное совпадение. 
4 | \w | "ding a reed" (позиция 3) | Возможное совпадение.
5 | \b | "ing a reed" (позиция 4) | Совпадение не подтвердилось. 
6 | й | "eding a reed" (позиция 2) | Возможное совпадение. 
7 | e{2} | "ding a reed" (позиция 3) | Совпадение не подтвердилось. 
8 | й | "ding a reed" (позиция 3) | Совпадение отсутствует. 
9 | й | "ing a reed" (позиция 4) | Нет совпадения.
10 | й | "ng a reed" (позиция 5) | Нет совпадения.
11 | й | "g a reed" (позиция 6) | Нет совпадения.
12 | й | " a reed" (позиция 7) | Нет совпадения.
13 | й | a reed (позиция 8) | Нет совпадения.
14 | й | " reed" (позиция 9) | Нет совпадения.
15 | й | reed (позиция 10) | Нет совпадения.
16 | й | "eed" (позиция 11) | Возможное совпадение.
17 | e{2} | "ed" (позиция 12) | Возможное совпадение.
18 | \w | "d" (позиция 13) | Возможное совпадение.
19 | \b | "" (позиция 14) | Совпадение.
 

Если в шаблоне регулярного выражения нет переменных квантификаторов или конструкций изменения, максимальное число сравнений, необходимое для поиска во входной строке совпадения с шаблоном регулярного выражения, примерно равно числу символов во входной строке. В этом случае обработчик регулярных выражений использует 19 сравнений, чтобы определить возможные совпадения в этой 13-значной строке. Другими словами, обработчик регулярных выражений работает почти за линейное время, если отсутствуют переменные квантификаторы или конструкции изменения.

## <a name="backtracking-with-optional-quantifiers-or-alternation-constructs"></a>Поиск с возвратом с необязательными квантификаторами и конструкциями чередования

Если регулярное выражение содержит переменные квантификаторы или конструкции изменения, оценка входной строки уже не может быть линейной. При использовании NFA-машины сопоставление шаблонов определяется языковыми элементами регулярного выражения, а не символами входной строки. Поэтому обработчик регулярных выражений пытается найти полное совпадение для переменных подвыражений или подвыражений выбора. При переходе к следующему языковому элементу подвыражения и нарушении совпадения обработчик регулярных выражений отбрасывает совпавшую часть и возвращается к ранее сохраненному состоянию; ему снова требуется найти во входной строке совпадение с регулярным выражением целиком. Процесс возвращения к ранее сохраненному состоянию для поиска совпадения называется "поиск с возвратом".

Например, рассмотрим шаблон регулярного выражения `.*(es)`, совпадающий с символами "es" и любыми предшествующими символам. Как показано в следующем примере, если взять входную строку "Essential services are provided by regular expressions.", совпадать с шаблоном будет вся строка до букв "es" в слове "expressions" включительно.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "Essential services are provided by regular expressions.";
      string pattern = ".*(es)"; 
      Match m = Regex.Match(input, pattern, RegexOptions.IgnoreCase);
      if (m.Success) {
         Console.WriteLine("'{0}' found at position {1}", 
                           m.Value, m.Index);
         Console.WriteLine("'es' found at position {0}", 
                           m.Groups[1].Index);      
      } 
   }
}
//    'Essential services are provided by regular expres' found at position 0
//    'es' found at position 47
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "Essential services are provided by regular expressions."
      Dim pattern As String = ".*(es)" 
      Dim m As Match = Regex.Match(input, pattern, RegexOptions.IgnoreCase)
      If m.Success Then
         Console.WriteLine("'{0}' found at position {1}", _
                           m.Value, m.Index)
         Console.WriteLine("'es' found at position {0}", _
                           m.Groups(1).Index)                  
      End If     
   End Sub
End Module
'    'Essential services are provided by regular expres' found at position 0
'    'es' found at position 47
```

В этом случае обработчик регулярных выражений использует поиск с возвратом следующим образом.

* Обработчик обнаруживает совпадение части выражения `.*` (что соответствует любому числу любых символов) со всей входной строкой.

* Затем обработчик ищет совпадение для символа "e" шаблона регулярного выражения. Однако во входной строке нет больше символов для поиска совпадения.

* Обработчик возвращается к месту последнего успешного совпадения, "Essential services are provided by regular expressions", и сравнивает символ "e" с точкой в конце предложения. Совпадение отсутствует.

* Обработчик продолжает возвращаться к предыдущим успешным совпадениям, отступая по одному символу, пока предположительно подходящей подстрокой не становится подстрока "Essential services are provided by regular expr". Затем обработчик сравнивает символ "e" шаблона со второй буквой "e" в слове "expressions" и обнаруживает совпадение.

* Затем он сравнивает символ "s" шаблона с символом "s" после символа "e" в строке (первая буква "s" в слове "expressions"). Совпадение успешно.

При использовании поиска с возвратом поиск совпадения шаблона регулярного выражения со входной строкой длиной 55 символов требует 67 операций сравнения. Интересно, что если шаблон регулярного выражения включает ленивый квантификатор `.*?(es),`, поиск совпадения потребует дополнительных операций сравнения. В этом случае вместо обратного поиска от конца строки до символа "r" в слове "expressions" обработчику регулярных выражений придется выполнить обратный поиск до начала строки в поисках "Es", что потребует 113 сравнений. Как правило, если в шаблоне регулярного выражения есть один переменный квантификатор или одна конструкция изменения, число сравнений, необходимых для поиска во входной строке совпадения с шаблоном регулярного выражения, более чем вдвое превышает число символов во входной строке.

## <a name="backtracking-with-nested-optional-quantifiers"></a>Поиск с возвратом со вложенными необязательными квантификаторами

Количество сравнений, необходимое для поиска во входной строке совпадения с шаблоном регулярного выражения, может увеличиваться экспоненциально, если шаблон включает большое количество конструкций изменения или вложенные конструкции изменения, или, что случается чаще, вложенные переменные квантификаторы. Например, шаблон регулярного выражения `^(a+)+$` должен совпадать со строкой, состоящей из одного и более символов "a". В примере показаны две входные строки одинаковой длины, только одна из которых совпадает с шаблоном. Класс [System.Diagnostics.Stopwatch](xref:System.Diagnostics.Stopwatch) используется для определения времени выполнения операции поиска совпадения. 

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "^(a+)+$";
      string[] inputs = { "aaaaaa", "aaaaa!" };
      Regex rgx = new Regex(pattern);
      Stopwatch sw;

      foreach (string input in inputs) {
         sw = Stopwatch.StartNew();   
         Match match = rgx.Match(input);
         sw.Stop();
         if (match.Success)
            Console.WriteLine("Matched {0} in {1}", match.Value, sw.Elapsed);
         else
            Console.WriteLine("No match found in {0}", sw.Elapsed);
      }
   }
}
```

```vb
Imports System.Diagnostics
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^(a+)+$"
      Dim inputs() As String = { "aaaaaa", "aaaaa!" }
      Dim rgx As New Regex(pattern)
      Dim sw As Stopwatch

      For Each input As String In inputs
         sw = Stopwatch.StartNew()   
         Dim match As Match = rgx.Match(input)
         sw.Stop()
         If match.Success Then
            Console.WriteLine("Matched {0} in {1}", match.Value, sw.Elapsed)
         Else
            Console.WriteLine("No match found in {0}", sw.Elapsed)
         End If      
      Next
   End Sub
End Module
```

Как показывают выходные данные примера, у обработчика регулярных выражений установление отсутствия совпадения с шаблоном занимает в два раза больше времени, чем нахождение совпадения. Неуспешное совпадение — худший сценарий. Обработчик регулярных выражений должен использовать регулярное выражение для проверки всех возможных путей в данных, чтобы заключить, что совпадения нет, а вложенные скобки сильно увеличивают количество таких путей. Чтобы установить, что вторая строка не совпадает с шаблоном, обработчику регулярных выражений нужно выполнить следующие действия:

* Он проверяет, что находится в начале строки, после чего проверяет первые пять символов строки на совпадение с шаблоном a+. Затем проверяет, что в строке нет других групп символов "a". Затем выполняется проверка до конца строки. Поскольку в строке содержится один дополнительный символ, проверка оказывается неудачной. Этот отрицательный результат требует 9 сравнений. Обработчик регулярных выражений также сохраняет информацию о состоянии при совпадениях "a" (совпадение 1), "aa" (совпадение 2), "aaa" (совпадение 3) и "aaaa" (совпадение 4).

* Затем он возвращается к предварительно сохраненному совпадению 4. Далее устанавливается наличие дополнительного символа "a", который назначается дополнительной захваченной группе. Затем выполняется проверка до конца строки. Поскольку в строке содержится один дополнительный символ, проверка оказывается неудачной. Этот отрицательный результат требует 4 сравнений. Таким образом, всего выполнено 13 сравнений.

* Затем он возвращается к предварительно сохраненному совпадению 3. Он устанавливает наличие двух дополнительных символов "a", которые назначаются дополнительной захваченной группе. Однако проверка на наличие окончания строки не проходит. Обработчик возвращается к совпадению 3 и пытается сопоставить два дополнительных символа "a" с двумя дополнительными захваченными группами. Проверка на наличие окончания строки не проходит. Для получения этих неуспешных совпадений потребовалось 12 сравнений. Таким образом, всего выполнено 25 сравнений. 

Сравнение входной строки с регулярным выражением продолжается таким же образом, пока обработчик регулярных выражений не переберет все возможные комбинации совпадений, заключив, что совпадений нет. Из-за наличия вложенных квантификаторов это сравнение представляет собой операцию экспоненциальной сложности O(2n), где n — количество символов входной строки. Это значит, что в худшем случае входная строка, состоящая из 30 символов, требует по примерным подсчетам 1 073 741 824 сравнений, а входная строка длиной 40 символов — 1 099 511 627 776 сравнений. При использовании строк такого или большего размера методы, выполняющие регулярные выражения, могут выполняться очень долго, прежде чем будет установлено, что входная строка не совпадает с шаблоном регулярного выражения.

## <a name="controlling-backtracking"></a>Управление поиском с возвратом

Поиск с возвратом позволяет создавать мощные и гибкие регулярные выражения. Однако, как было показано в предыдущем разделе, эти преимущества могут сопровождаться неприемлемо низкой производительностью. Чтобы предотвратить излишнее использование поиска с возвратом, необходимо указать интервал времени ожидания при создании экземпляра объекта [Regex](xref:System.Text.RegularExpressions.Regex) или вызвать соответствующий метод статического регулярного выражения. Этот метод будет рассмотрен в следующем разделе. Кроме того, в .NET Core поддерживается три элемента языка регулярных выражений, ограничивающих или подавляющих поиск с возвратом, что позволяет выполнять сложные регулярные выражения при небольшом снижении производительности или без такового: [невозвращающиеся части выражения](#nonbacktracking-subexpression), [утверждения просмотра назад](#lookbehind-assertions) и [утверждения просмотра вперед](#lookahead-assertions). Дополнительные сведения об этих элементах языка см. в разделе [Конструкции группировки в регулярных выражениях](grouping.md).

### <a name="defining-a-timeout-interval"></a>Определение интервала времени ожидания

Можно задать значение времени ожидания, которое равняется значению самого длинного интервала, необходимого обработчику регулярных выражений для выполнения поиска до первого совпадения, пока он не приостановит попытки найти соответствие и не вызовет исключение [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException). Чтобы задать интервал ожидания, укажите значение [TimeSpan](xref:System.TimeSpan) в конструкторе `Regex(String, RegexOptions, TimeSpan)` регулярных выражений экземпляра. Кроме того, каждый статический метод сравнения с шаблоном имеет перегруженную версию значения [TimeSpan](xref:System.TimeSpan) с параметром [Regex.Regex(String, RegexOptions, TimeSpan)], который позволяет указать значение времени ожидания. По умолчанию интервал времени ожидания задается в [Regex.InfiniteMatchTimeout](xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout), и время ожидания обработчика регулярных выражений не истекает. 

> [!IMPORTANT]
> Рекомендуется всегда устанавливать интервал времени ожидания, если регулярное выражение использует поиск с возвратом.
 
Выражение [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException) указывает на то, что обработчику регулярных выражений не удалось найти совпадение в пределах заданного интервала времени ожидания, но не указывает причину создания исключения. Причина может быть как в излишнем поиске с возвратом, так и в недостаточном значении интервала времени ожидания для текущей загруженности системы на момент создания исключения. При обработке исключения можно прервать дальнейший поиск совпадений входной строки или увеличить интервал времени ожидания и повторно выполнить операцию поиска. 

Например, следующий код вызывает конструктор `Regex(String, RegexOptions, TimeSpan)` для создания экземпляра объекта Regex со значением времени ожидания, равным одной секунде. Шаблон регулярного выражения `(a+)+$`, который сопоставляется с последовательностью из одного или нескольких символов "a" в конце строки, относится к шаблонам с чрезмерным использованием поиска с возвратом. Если создается исключение [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException), интервал времени ожидания в данном примере увеличивается до максимального значения, равного трем секундам. После этого попытки найти соответствие шаблону будут прерваны.

```csharp
using System;
using System.ComponentModel;
using System.Diagnostics;
using System.Security;
using System.Text.RegularExpressions;
using System.Threading; 

public class Example
{
   const int MaxTimeoutInSeconds = 3;

   public static void Main()
   {
      string pattern = @"(a+)+$";    // DO NOT REUSE THIS PATTERN.
      Regex rgx = new Regex(pattern, RegexOptions.IgnoreCase, TimeSpan.FromSeconds(1));       
      Stopwatch sw = null;

      string[] inputs= { "aa", "aaaa>", 
                         "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
                         "aaaaaaaaaaaaaaaaaaaaaa>",
                         "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>" };

      foreach (var inputValue in inputs) {
         Console.WriteLine("Processing {0}", inputValue);
         bool timedOut = false;
         do { 
            try {
               sw = Stopwatch.StartNew();
               // Display the result.
               if (rgx.IsMatch(inputValue)) {
                  sw.Stop();
                  Console.WriteLine(@"Valid: '{0}' ({1:ss\.fffffff} seconds)", 
                                    inputValue, sw.Elapsed); 
               }
               else {
                  sw.Stop();
                  Console.WriteLine(@"'{0}' is not a valid string. ({1:ss\.fffff} seconds)", 
                                    inputValue, sw.Elapsed);
               }
            }
            catch (RegexMatchTimeoutException e) {   
               sw.Stop();
               // Display the elapsed time until the exception.
               Console.WriteLine(@"Timeout with '{0}' after {1:ss\.fffff}", 
                                 inputValue, sw.Elapsed);
               Thread.Sleep(1500);       // Pause for 1.5 seconds.

               // Increase the timeout interval and retry.
               TimeSpan timeout = e.MatchTimeout.Add(TimeSpan.FromSeconds(1));
               if (timeout.TotalSeconds > MaxTimeoutInSeconds) {
                  Console.WriteLine("Maximum timeout interval of {0} seconds exceeded.",
                                    MaxTimeoutInSeconds);
                  timedOut = false;
               }
               else {               
                  Console.WriteLine("Changing the timeout interval to {0}", 
                                    timeout); 
                  rgx = new Regex(pattern, RegexOptions.IgnoreCase, timeout);
                  timedOut = true;
               }
            }
         } while (timedOut);
         Console.WriteLine();
      }   
   }
}
// The example displays output like the following :
//    Processing aa
//    Valid: 'aa' (00.0000779 seconds)
//    
//    Processing aaaa>
//    'aaaa>' is not a valid string. (00.00005 seconds)
//    
//    Processing aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
//    Valid: 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa' (00.0000043 seconds)
//    
//    Processing aaaaaaaaaaaaaaaaaaaaaa>
//    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 01.00469
//    Changing the timeout interval to 00:00:02
//    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 02.01202
//    Changing the timeout interval to 00:00:03
//    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 03.01043
//    Maximum timeout interval of 3 seconds exceeded.
//    
//    Processing aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>
//    Timeout with 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>' after 03.01018
//    Maximum timeout interval of 3 seconds exceeded.
```

```vb
Imports System.ComponentModel
Imports System.Diagnostics
Imports System.Security
Imports System.Text.RegularExpressions
Imports System.Threading 

Module Example
   Const MaxTimeoutInSeconds As Integer = 3

   Public Sub Main()
      Dim pattern As String = "(a+)+$"    ' DO NOT REUSE THIS PATTERN.
      Dim rgx As New Regex(pattern, RegexOptions.IgnoreCase, TimeSpan.FromSeconds(1))       
      Dim sw As Stopwatch = Nothing

      Dim inputs() As String = { "aa", "aaaa>", 
                                 "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
                                 "aaaaaaaaaaaaaaaaaaaaaa>",
                                 "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>" }

      For Each inputValue In inputs
         Console.WriteLine("Processing {0}", inputValue)
         Dim timedOut As Boolean = False
         Do 
            Try
               sw = Stopwatch.StartNew()
               ' Display the result.
               If rgx.IsMatch(inputValue) Then
                  sw.Stop()
                  Console.WriteLine("Valid: '{0}' ({1:ss\.fffffff} seconds)", 
                                    inputValue, sw.Elapsed) 
               Else
                  sw.Stop()
                  Console.WriteLine("'{0}' is not a valid string. ({1:ss\.fffff} seconds)", 
                                    inputValue, sw.Elapsed)
               End If
            Catch e As RegexMatchTimeoutException   
               sw.Stop()
               ' Display the elapsed time until the exception.
               Console.WriteLine("Timeout with '{0}' after {1:ss\.fffff}", 
                                 inputValue, sw.Elapsed)
               Thread.Sleep(1500)       ' Pause for 1.5 seconds.

               ' Increase the timeout interval and retry.
               Dim timeout As TimeSpan = e.MatchTimeout.Add(TimeSpan.FromSeconds(1))
               If timeout.TotalSeconds > MaxTimeoutInSeconds Then
                  Console.WriteLine("Maximum timeout interval of {0} seconds exceeded.",
                                    MaxTimeoutInSeconds)
                  timedOut = False
               Else                
                  Console.WriteLine("Changing the timeout interval to {0}", 
                                    timeout) 
                  rgx = New Regex(pattern, RegexOptions.IgnoreCase, timeout)
                  timedOut = True
               End If
            End Try
         Loop While timedOut
         Console.WriteLine()
      Next   
   End Sub 
End Module
' The example displays output like the following:
'    Processing aa
'    Valid: 'aa' (00.0000779 seconds)
'    
'    Processing aaaa>
'    'aaaa>' is not a valid string. (00.00005 seconds)
'    
'    Processing aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
'    Valid: 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa' (00.0000043 seconds)
'    
'    Processing aaaaaaaaaaaaaaaaaaaaaa>
'    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 01.00469
'    Changing the timeout interval to 00:00:02
'    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 02.01202
'    Changing the timeout interval to 00:00:03
'    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 03.01043
'    Maximum timeout interval of 3 seconds exceeded.
'    
'    Processing aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>
'    Timeout with 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>' after 03.01018
'    Maximum timeout interval of 3 seconds exceeded.
```

### <a name="nonbacktracking-subexpression"></a>Невозвращающиеся подвыражения

Элемент языка **(?>** _subexpression_**)** подавляет поиск с возвратом в части выражения. Это полезно для предотвращения проблем с производительностью, связанных с неуспешным совпадением. 

В следующем примере показано, как подавление поиска с возвратом улучшает производительность при использовании вложенных квантификаторов. В нем измеряется время, которое требуется обработчику регулярных выражений, чтобы определить, что входная строка не совпадает с двумя регулярными выражениями. В первом регулярном выражении поиск с возвратом используется для поиска строки, содержащей последовательно одну и более шестнадцатеричных цифр, двоеточие, одну и более шестнадцатеричных цифр и два двоеточия. Второе регулярное выражение аналогично первому, но в нем отключен поиск с возвратом. Как показывают выходные данные примера, отключение поиска с возвратом приводит к существенному росту производительности.

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "b51:4:1DB:9EE1:5:27d60:f44:D4:cd:E:5:0A5:4a:D24:41Ad:";
      bool matched;
      Stopwatch sw;

      Console.WriteLine("With backtracking:");
      string backPattern = "^(([0-9a-fA-F]{1,4}:)*([0-9a-fA-F]{1,4}))*(::)$";
      sw = Stopwatch.StartNew();
      matched = Regex.IsMatch(input, backPattern);
      sw.Stop();
      Console.WriteLine("Match: {0} in {1}", Regex.IsMatch(input, backPattern), sw.Elapsed);
      Console.WriteLine();

      Console.WriteLine("Without backtracking:");
      string noBackPattern = "^((?>[0-9a-fA-F]{1,4}:)*(?>[0-9a-fA-F]{1,4}))*(::)$";
      sw = Stopwatch.StartNew();
      matched = Regex.IsMatch(input, noBackPattern);
      sw.Stop();
      Console.WriteLine("Match: {0} in {1}", Regex.IsMatch(input, noBackPattern), sw.Elapsed);
   }
}
// The example displays output like the following:
//       With backtracking:
//       Match: False in 00:00:27.4282019
//       
//       Without backtracking:
//       Match: False in 00:00:00.0001391
```

```vb
Imports System.Diagnostics
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "b51:4:1DB:9EE1:5:27d60:f44:D4:cd:E:5:0A5:4a:D24:41Ad:"
      Dim matched As Boolean
      Dim sw As Stopwatch

      Console.WriteLine("With backtracking:")
      Dim backPattern As String = "^(([0-9a-fA-F]{1,4}:)*([0-9a-fA-F]{1,4}))*(::)$"
      sw = Stopwatch.StartNew()
      matched = Regex.IsMatch(input, backPattern)
      sw.Stop()
      Console.WriteLine("Match: {0} in {1}", Regex.IsMatch(input, backPattern), sw.Elapsed)
      Console.WriteLine()

      Console.WriteLine("Without backtracking:")
      Dim noBackPattern As String = "^((?>[0-9a-fA-F]{1,4}:)*(?>[0-9a-fA-F]{1,4}))*(::)$"
      sw = Stopwatch.StartNew()
      matched = Regex.IsMatch(input, noBackPattern)
      sw.Stop()
      Console.WriteLine("Match: {0} in {1}", Regex.IsMatch(input, noBackPattern), sw.Elapsed)
   End Sub
End Module
' The example displays the following output:
'       With backtracking:
'       Match: False in 00:00:27.4282019
'       
'       Without backtracking:
'       Match: False in 00:00:00.0001391
```

### <a name="lookbehind-assertions"></a>Проверочные утверждения с просмотром назад

В платформу .NET входят два элемента языка, **(?<**=_subexpression_**)** и **(?<!**_subexpression_**)**, совпадающие с предыдущими символами во входной строке. Оба элемента языка являются утверждениями нулевой ширины; они определяют, должны ли символы, непосредственно предшествующие текущему, соответствовать *subexpression*. Смещения или поиска с возвратом не происходит. 

**(?<**=_subexpression_**)** — это утверждение положительного просмотра назад; символы, непосредственно предшествующие текущему, должны соответствовать *subexpression*. **(?<!**_subexpression_**)** — это утверждение отрицательного просмотра назад; символы, непосредственно предшествующие текущему, не должны соответствовать *subexpression*. Утверждения положительного и отрицательного просмотра назад наиболее полезны, если *subexpression* является подмножеством предыдущей *части выражения*. 

В следующем примере используются два равнозначных шаблона регулярного выражения, проверяющих имя пользователя в адресе электронной почты. Первый шаблон демонстрирует низкую производительность из-за неоправданного использования поиска с возвратом. Во втором шаблоне то же самое регулярное выражение изменено. Вложенный квантификатор заменен на утверждение положительного просмотра назад. Выходные данные примера демонстрируют время выполнения метода [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)).

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      Stopwatch sw;
      string input = "aaaaaaaaaaaaaaaaaaaa";
      bool result;

      string pattern = @"^[0-9A-Z]([-.\w]*[0-9A-Z])?@";
      sw = Stopwatch.StartNew();
      result = Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase);
      sw.Stop();
      Console.WriteLine("Match: {0} in {1}", result, sw.Elapsed);

      string behindPattern = @"^[0-9A-Z][-.\w]*(?<=[0-9A-Z])@";
      sw = Stopwatch.StartNew();
      result = Regex.IsMatch(input, behindPattern, RegexOptions.IgnoreCase);
      sw.Stop();
      Console.WriteLine("Match with Lookbehind: {0} in {1}", result, sw.Elapsed);
   }
}
// The example displays output similar to the following:
//       Match: True in 00:00:00.0017549
//       Match with Lookbehind: True in 00:00:00.0000659
```

```vb
Module Example
   Public Sub Main()
      Dim sw As Stopwatch
      Dim input As String = "aaaaaaaaaaaaaaaaaaaa"
      Dim result As Boolean

      Dim pattern As String = "^[0-9A-Z]([-.\w]*[0-9A-Z])?@"
      sw = Stopwatch.StartNew()
      result = Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase)
      sw.Stop()
      Console.WriteLine("Match: {0} in {1}", result, sw.Elapsed)

      Dim behindPattern As String = "^[0-9A-Z][-.\w]*(?<=[0-9A-Z])@"
      sw = Stopwatch.StartNew()
      result = Regex.IsMatch(input, behindPattern, RegexOptions.IgnoreCase)
      sw.Stop()
      Console.WriteLine("Match with Lookbehind: {0} in {1}", result, sw.Elapsed)
   End Sub
End Module
' The example displays output similar to the following:
'       Match: True in 00:00:00.0017549
'       Match with Lookbehind: True in 00:00:00.0000659
```

Первый шаблон регулярного выражения, `^[0-9A-Z]([-.\w]*[0-9A-Z])*@, is defined as shown in the following table.`

Шаблон | Описание
------- | ----------- 
`^` | Совпадение с началом строки.
`[0-9A-Z]` | Совпадение с алфавитно-цифровым символом. Поскольку метод [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) вызывается с параметром [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase), сравнение не зависит от регистра символов.
`[-.\w]*` | Нуль и более совпадений с дефисом, точкой или символом слова. 
`[0-9A-Z]` | Совпадение с алфавитно-цифровым символом. 
`([-.\w]*[0-9A-Z])*` | Ноль и более совпадений с комбинацией нуля и более дефисов, точек и символов слова, за которыми следует алфавитно-цифровой символ. Это первая группа записи.
`@` | Совпадение со знаком "@".
 
Второй шаблон регулярного выражения `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])@` использует утверждение положительного просмотра назад. Определяется, как показано в следующей таблице.

Шаблон | Описание
------- | ----------- 
`^` | Совпадение с началом строки.
`[0-9A-Z]` | Совпадение с алфавитно-цифровым символом. Поскольку метод [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) вызывается с параметром [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase), сравнение не зависит от регистра символов.
`[-.\w]*` | Нуль и более совпадений с дефисом, точкой или символом слова.
`(?<=[0-9A-Z])` | Выполняется просмотр назад последнего совпавшего символа; поиск совпадения продолжается, если этот символ является алфавитно-цифровым. Обратите внимание, что алфавитно-цифровой символ является подмножеством набора, образованного точкой, дефисом и всеми символами слова.
`@` | Совпадение со знаком "@".
 
### <a name="lookahead-assertions"></a>Проверочные утверждения с просмотром вперед

В платформу .NET входят два элемента языка, **(?**=_subexpression_**)** и **(?!**_subexpression_**)**, совпадающие со следующими символами во входной строке. Оба элемента языка являются утверждениями нулевой ширины; они определяют, должны ли символы, непосредственно следующие за текущим, соответствовать *subexpression*. Смещения или поиска с возвратом не происходит. 

**(?**=_subexpression_**)** — это утверждение положительного просмотра вперед; символы, непосредственно следующие за текущим, должны соответствовать *subexpression*. **(?!**_subexpression_**)** — это утверждение отрицательного просмотра вперед; символы, непосредственно следующие за текущим, не должны соответствовать *subexpression*. Утверждения положительного и отрицательного просмотра вперед наиболее полезны, если *subexpression* является подмножеством следующей *части выражения*. 

В следующем примере используются два одинаковых шаблона регулярного выражения, проверяющих полное имя типа. Первый шаблон демонстрирует низкую производительность из-за неоправданного использования поиска с возвратом. Во втором шаблоне то же самое регулярное выражение изменено. Вложенный квантификатор заменен на утверждение положительного просмотра вперед. Выходные данные примера демонстрируют время выполнения метода [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)).

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "aaaaaaaaaaaaaaaaaaaaaa.";
      bool result;
      Stopwatch sw;

      string pattern = @"^(([A-Z]\w*)+\.)*[A-Z]\w*$";
      sw = Stopwatch.StartNew();
      result = Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase);
      sw.Stop();
      Console.WriteLine("{0} in {1}", result, sw.Elapsed);

      string aheadPattern = @"^((?=[A-Z])\w+\.)*[A-Z]\w*$";
      sw = Stopwatch.StartNew();
      result = Regex.IsMatch(input, aheadPattern, RegexOptions.IgnoreCase);
      sw.Stop();
      Console.WriteLine("{0} in {1}", result, sw.Elapsed);
   }
}
// The example displays the following output:
//       False in 00:00:03.8003793
//       False in 00:00:00.0000866
```

```vb
Imports System.Diagnostics
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "aaaaaaaaaaaaaaaaaaaaaa."
      Dim result As Boolean
      Dim sw As Stopwatch

      Dim pattern As String = "^(([A-Z]\w*)+\.)*[A-Z]\w*$"
      sw = Stopwatch.StartNew()
      result = Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase)
      sw.Stop()
      Console.WriteLine("{0} in {1}", result, sw.Elapsed)

      Dim aheadPattern As String = "^((?=[A-Z])\w+\.)*[A-Z]\w*$"
      sw = Stopwatch.StartNew()
      result = Regex.IsMatch(input, aheadPattern, RegexOptions.IgnoreCase)
      sw.Stop()
      Console.WriteLine("{0} in {1}", result, sw.Elapsed)
   End Sub
End Module
' The example displays the following output:
'       False in 00:00:03.8003793
'       False in 00:00:00.0000866
```

Первый шаблон регулярного выражения `^(([A-Z]\w*)+\.)*[A-Z]\w*$` определяется, как показано в следующей таблице.

Шаблон | Описание
------- | ----------- 
`^` | Совпадение с началом строки.
`([A-Z]\w*)+\.` | Совпадение с алфавитным символом (A-Z), за которым следует ноль и более символов слова, повторенных ноль и более раз, за которыми следует точка. Поскольку метод [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) вызывается с параметром [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase), сравнение не зависит от регистра символов.
`(([A-Z]\w*)+\.)*` | Совпадение с предыдущим шаблоном ноль и более раз. 
`[A-Z]\w*` | Совпадение с алфавитно-цифровым символом, за которым следует ноль и более символов слова.
`$` | Совпадение должно заканчиваться в конце входной строки.
 

Второй шаблон регулярного выражения `^((?=[A-Z])\w+\.)*[A-Z]\w*$` использует утверждение положительного просмотра вперед. Определяется, как показано в следующей таблице.

Шаблон | Описание
------- | ----------- 
`^` | Совпадение с началом строки.
`(?=[A-Z])` | Выполняется просмотр вперед к следующему символу; если он является алфавитным (A-Z), продолжается поиск совпадения. Поскольку метод [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) вызывается с параметром [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase), сравнение не зависит от регистра символов.
`\w+\.` | Совпадение с одним или несколькими символами слова, за которыми следует точка.
`((?=[A-Z])\w+\.)*` | Совпадение с одним или несколькими символами слова, за которым следует ноль и более точек. Первый символ слова должен быть алфавитным. 
`[A-Z]\w*` | Совпадение с алфавитно-цифровым символом, за которым следует ноль и более символов слова.
`$` | Совпадение должно заканчиваться в конце входной строки.
 
## <a name="see-also"></a>См. также

[Регулярные выражения .NET](regular-expressions.md)

[Элементы языка регулярных выражений — краткий справочник](quick-ref.md)

[Квантификаторы в регулярных выражениях](quantifiers.md)

[Конструкции чередования в регулярных выражениях](alternation.md)

[Конструкции группировки в регулярных выражениях](grouping.md)




<!--HONumber=Nov16_HO3-->


