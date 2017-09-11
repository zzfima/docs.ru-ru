---
title: "Рекомендации по использованию регулярных выражений"
description: "Рекомендации по использованию регулярных выражений"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 096fd614-91bf-4296-be24-12f62b062294
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: cf9c83de791fa4990a991689a26d4bbdd84cfe7d
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="best-practices-for-regular-expressions"></a><span data-ttu-id="e263f-104">Рекомендации по использованию регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="e263f-104">Best practices for regular expressions</span></span>

<span data-ttu-id="e263f-105">Обработчик регулярных выражений в .NET — мощное средство, обрабатывающее текст на основе совпадения шаблонов, а не сравнивающее непосредственно текст.</span><span class="sxs-lookup"><span data-stu-id="e263f-105">The regular expression engine in .NET is a powerful, full-featured tool that processes text based on pattern matches rather than on comparing and matching literal text.</span></span> <span data-ttu-id="e263f-106">В большинстве случаев сопоставление шаблонов выполняется быстро и эффективно.</span><span class="sxs-lookup"><span data-stu-id="e263f-106">In most cases, it performs pattern matching rapidly and efficiently.</span></span> <span data-ttu-id="e263f-107">Однако в некоторых случаях обработчик регулярных выражений может работать очень медленно.</span><span class="sxs-lookup"><span data-stu-id="e263f-107">However, in some cases, the regular expression engine can appear to be very slow.</span></span> <span data-ttu-id="e263f-108">В крайних случаях он даже может перестать отвечать, обрабатывая относительно небольшой объем входной информации в течение часов или даже дней.</span><span class="sxs-lookup"><span data-stu-id="e263f-108">In extreme cases, it can even appear to stop responding as it processes a relatively small input over the course of hours or even days.</span></span> 

<span data-ttu-id="e263f-109">В этом разделе приведены некоторые рекомендации для разработчиков по обеспечению оптимальной производительности регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="e263f-109">This topic outlines some of the best practices that developers can adopt to ensure that their regular expressions achieve optimal performance.</span></span> <span data-ttu-id="e263f-110">Он содержит следующие подразделы:</span><span class="sxs-lookup"><span data-stu-id="e263f-110">It contains the following sections:</span></span>

* [<span data-ttu-id="e263f-111">Учет источника входных данных</span><span class="sxs-lookup"><span data-stu-id="e263f-111">Consider the input source</span></span>](#consider-the-input-source)

* [<span data-ttu-id="e263f-112">Правильное создание объектов</span><span class="sxs-lookup"><span data-stu-id="e263f-112">Handle object instantiation appropriately</span></span>](#handle-object-instantiation-appropriately)

* [<span data-ttu-id="e263f-113">Грамотное использование поиска с возвратом</span><span class="sxs-lookup"><span data-stu-id="e263f-113">Take charge of backtracking</span></span>](#take-charge-of-backtracking)

* [<span data-ttu-id="e263f-114">Использование значений времени ожидания</span><span class="sxs-lookup"><span data-stu-id="e263f-114">Use time-out values</span></span>](#use-time-out-values)

* [<span data-ttu-id="e263f-115">Захват только в случае необходимости</span><span class="sxs-lookup"><span data-stu-id="e263f-115">Capture only when necessary</span></span>](#capture-only-when-necessary)

* [<span data-ttu-id="e263f-116">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="e263f-116">Related topics</span></span>](#related-topics)

## <a name="consider-the-input-source"></a><span data-ttu-id="e263f-117">Учет источника входных данных</span><span class="sxs-lookup"><span data-stu-id="e263f-117">Consider the input source</span></span>

<span data-ttu-id="e263f-118">Регулярные выражения могут принимать два типа входных данных: определенные и произвольные.</span><span class="sxs-lookup"><span data-stu-id="e263f-118">In general, regular expressions can accept two types of input: constrained or unconstrained.</span></span> <span data-ttu-id="e263f-119">Определенные входные данные — это текст, происходящий из известного надежного источника в заранее определенном формате.</span><span class="sxs-lookup"><span data-stu-id="e263f-119">Constrained input is text that originates from a known or reliable source and follows a predefined format.</span></span> <span data-ttu-id="e263f-120">Произвольные входные данные — это текст, происходящий из ненадежного источника, например от пользователя в Интернете, который может не соответствовать заданному или ожидаемому формату.</span><span class="sxs-lookup"><span data-stu-id="e263f-120">Unconstrained input is text that originates from an unreliable source, such as a web user, and may not follow a predefined or expected format.</span></span>

<span data-ttu-id="e263f-121">Шаблоны регулярных выражений обычно ориентированы на подходящие входные данные.</span><span class="sxs-lookup"><span data-stu-id="e263f-121">Regular expression patterns are typically written to match valid input.</span></span> <span data-ttu-id="e263f-122">Это значит, что разработчик анализирует текст, который требуется найти, и составляет шаблон регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="e263f-122">That is, developers examine the text that they want to match and then write a regular expression pattern that matches it.</span></span> <span data-ttu-id="e263f-123">Затем разработчик определяет, требуется ли корректировка шаблона или его уточнение, тестируя его с различными подходящими входными данными.</span><span class="sxs-lookup"><span data-stu-id="e263f-123">Developers then determine whether this pattern requires correction or further elaboration by testing it with multiple valid input items.</span></span> <span data-ttu-id="e263f-124">Когда шаблон соответствует всем возможным подходящим вариантам входных данных, считается, что он готов и его можно включить в выпускаемое приложение.</span><span class="sxs-lookup"><span data-stu-id="e263f-124">When the pattern matches all presumed valid inputs, it is declared to be production-ready and can be included in a released application.</span></span> <span data-ttu-id="e263f-125">В результате этих действий шаблон регулярного выражения готов для сопоставления с определенными входными данными.</span><span class="sxs-lookup"><span data-stu-id="e263f-125">This makes a regular expression pattern suitable for matching constrained input.</span></span> <span data-ttu-id="e263f-126">Но он не готов для сопоставления с произвольными входными данными.</span><span class="sxs-lookup"><span data-stu-id="e263f-126">However, it does not make it suitable for matching unconstrained input.</span></span>

<span data-ttu-id="e263f-127">Для сопоставления с произвольными входными данными шаблон регулярного выражения должен уметь обрабатывать три вида текста:</span><span class="sxs-lookup"><span data-stu-id="e263f-127">To match unconstrained input, a regular expression must be able to efficiently handle three kinds of text:</span></span>

<span data-ttu-id="e263f-128">• Текст, соответствующий шаблону регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="e263f-128">• Text that matches the regular expression pattern.</span></span>

<span data-ttu-id="e263f-129">• Текст, не соответствующий шаблону регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="e263f-129">• Text that does not match the regular expression pattern.</span></span>

<span data-ttu-id="e263f-130">• Текст, почти соответствующий шаблону регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="e263f-130">• Text that nearly matches the regular expression pattern.</span></span>

<span data-ttu-id="e263f-131">Последний вид текста представляет особую проблему для регулярных выражений, написанных для обработки определенных входных данных.</span><span class="sxs-lookup"><span data-stu-id="e263f-131">The last text type is especially problematic for a regular expression that has been written to handle constrained input.</span></span> <span data-ttu-id="e263f-132">Если в регулярном выражении также широко используется [поиск с возвратом](backtracking.md), обработчик регулярных выражений может неожиданно долго (в некоторых случаях часы или дни) обрабатывать, казалось бы, безобидный текст.</span><span class="sxs-lookup"><span data-stu-id="e263f-132">If that regular expression also relies on extensive [backtracking](backtracking.md), the regular expression engine can spend an inordinate amount of time (in some cases, many hours or days) processing seemingly innocuous text.</span></span> 

> [!WARNING]
> <span data-ttu-id="e263f-133">В следующем примере используется регулярное выражение, которое подвержено избыточному использованию поиска с возвратом и может отклонить допустимые адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e263f-133">The following example uses a regular expression that is prone to excessive backtracking and that is likely to reject valid email addresses.</span></span> <span data-ttu-id="e263f-134">Использовать его для проверки электронной почты не следует.</span><span class="sxs-lookup"><span data-stu-id="e263f-134">You should not use it in an email validation routine.</span></span> <span data-ttu-id="e263f-135">Если требуется регулярное выражение, проверяющее адреса электронной почты, обратитесь к статье [Практическое руководство. Проверка строк на соответствие формату электронной почты](verify-format.md).</span><span class="sxs-lookup"><span data-stu-id="e263f-135">If you would like a regular expression that validates email addresses, see [How to: Verify that strings are in valid email format](verify-format.md).</span></span> 


<span data-ttu-id="e263f-136">Например, рассмотрим очень часто используемое и при этом очень проблематичное регулярное выражение для проверки псевдонима адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e263f-136">For example, consider a very commonly used but extremely problematic regular expression for validating the alias of an email address.</span></span> <span data-ttu-id="e263f-137">Регулярное выражение `^[0-9A-Z]([-.\w]*[0-9A-Z])*$` предназначено для обработки допустимого адреса электронной почты и состоит из алфавитно-цифрового символа, за которым следует ноль или более знаков, которые могут представлять собой алфавитно-цифровые символы, точки или дефисы.</span><span class="sxs-lookup"><span data-stu-id="e263f-137">The regular expression `^[0-9A-Z]([-.\w]*[0-9A-Z])*$` is written to process what is considered to be a valid email address, which consists of an alphanumeric character, followed by zero or more characters that can be alphanumeric, periods, or hyphens.</span></span> <span data-ttu-id="e263f-138">Регулярное выражение должно оканчиваться алфавитно-цифровым символом.</span><span class="sxs-lookup"><span data-stu-id="e263f-138">The regular expression must end with an alphanumeric character.</span></span> <span data-ttu-id="e263f-139">Однако, как показывает следующий пример, несмотря на то что это регулярное выражение хорошо обрабатывает подходящие входные данные, оно очень неэффективно при обработке почти подходящих входных данных.</span><span class="sxs-lookup"><span data-stu-id="e263f-139">However, as the following example shows, although this regular expression handles valid input easily, its performance is very inefficient when it is processing nearly valid input.</span></span>

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

<span data-ttu-id="e263f-140">Как видно по выводу примера, обработчик регулярных выражений обрабатывает подходящие псевдонимы электронной почты различной длины практически за одинаковое время.</span><span class="sxs-lookup"><span data-stu-id="e263f-140">As the output from the example shows, the regular expression engine processes the valid email alias in about the same time interval regardless of its length.</span></span> <span data-ttu-id="e263f-141">С другой стороны, если почти подходящий адрес электронной почты содержит более&5; символов, время обработки удваивается для каждого дополнительного символа в строке.</span><span class="sxs-lookup"><span data-stu-id="e263f-141">On the other hand, when the nearly valid email address has more than five characters, processing time approximately doubles for each additional character in the string.</span></span> <span data-ttu-id="e263f-142">Это значит, что почти подходящая строка из 28 символов будет обрабатываться более часа, а на обработку почти подходящей строки из 33 символов уйдет около дня.</span><span class="sxs-lookup"><span data-stu-id="e263f-142">This means that a nearly valid 28-character string would take over an hour to process, and a nearly valid 33-character string would take nearly a day to process.</span></span> 

<span data-ttu-id="e263f-143">Поскольку это регулярное выражение ориентировано только на формат подходящих входных данных, оно плохо работает со входными данными, не соответствующими шаблону.</span><span class="sxs-lookup"><span data-stu-id="e263f-143">Because this regular expression was developed solely by considering the format of input to be matched, it fails to take account of input that does not match the pattern.</span></span> <span data-ttu-id="e263f-144">А это может привести к тому, что произвольные входные данные, почти соответствующие шаблону регулярного выражения, могут существенно снизить производительность.</span><span class="sxs-lookup"><span data-stu-id="e263f-144">This, in turn, can allow unconstrained input that nearly matches the regular expression pattern to significantly degrade performance.</span></span>

<span data-ttu-id="e263f-145">Чтобы устранить эту проблему, можно выполнить одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="e263f-145">To solve this problem, you can do the following:</span></span>

* <span data-ttu-id="e263f-146">При создании шаблона необходимо учитывать, как поиск с возвратом может повлиять на производительность обработчика регулярных выражений, особенно если регулярное выражение должно обрабатывать произвольные входные данные.</span><span class="sxs-lookup"><span data-stu-id="e263f-146">When developing a pattern, you should consider how backtracking might affect the performance of the regular expression engine, particularly if your regular expression is designed to process unconstrained input.</span></span> <span data-ttu-id="e263f-147">Дополнительные сведения см. в разделе [Грамотное использование поиска с возвратом](#take-charge-of-backtracking).</span><span class="sxs-lookup"><span data-stu-id="e263f-147">For more information, see the [Take charge of backtracking](#take-charge-of-backtracking) section.</span></span>

* <span data-ttu-id="e263f-148">Следует тщательно протестировать регулярное выражение с использованием неподходящих и почти подходящих входных данных.</span><span class="sxs-lookup"><span data-stu-id="e263f-148">Thoroughly test your regular expression using invalid and near-valid input as well as valid input.</span></span> <span data-ttu-id="e263f-149">Для генерации произвольных входных данных для конкретного регулярного выражения можно использовать [Rex](http://research.microsoft.com/en-us/projects/rex/) — средство исследования регулярных выражений, разработанное группой Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="e263f-149">To generate input for a particular regular expression randomly, you can use [Rex](http://research.microsoft.com/en-us/projects/rex/), which is a regular expression exploration tool from Microsoft Research.</span></span>

## <a name="handle-object-instantiation-appropriately"></a><span data-ttu-id="e263f-150">Правильное создание объектов</span><span class="sxs-lookup"><span data-stu-id="e263f-150">Handle object instantiation appropriately</span></span>

<span data-ttu-id="e263f-151">Сердцем объектной модели регулярных выражений .NET является класс [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex), представляющий обработчик регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="e263f-151">At the heart of .NET’s regular expression object model is the [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) class, which represents the regular expression engine.</span></span> <span data-ttu-id="e263f-152">Часто производительность регулярного выражения зависит именно от того, как используется обработчик [Regex](xref:System.Text.RegularExpressions.Regex).</span><span class="sxs-lookup"><span data-stu-id="e263f-152">Often, the single greatest factor that affects regular expression performance is the way in which the [Regex](xref:System.Text.RegularExpressions.Regex) engine is used.</span></span> <span data-ttu-id="e263f-153">Определение регулярного выражения предполагает установление тесной взаимозависимости между обработчиком регулярных выражений и шаблоном регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="e263f-153">Defining a regular expression involves tightly coupling the regular expression engine with a regular expression pattern.</span></span> <span data-ttu-id="e263f-154">Процесс установления этой взаимозависимости является затратным, независимо от того, происходит ли создание объекта [Regex](xref:System.Text.RegularExpressions.Regex) путем передачи его конструктору шаблона регулярного выражения или вызов статического метода путем передачи ему шаблона регулярного выражения и входной строки.</span><span class="sxs-lookup"><span data-stu-id="e263f-154">That coupling process, whether it involves instantiating a [Regex](xref:System.Text.RegularExpressions.Regex) object by passing its constructor a regular expression pattern or calling a static method by passing it the regular expression pattern along with the string to be analyzed, is by necessity an expensive one.</span></span>

<span data-ttu-id="e263f-155">Можно установить связь между обработчиком регулярных выражений и конкретным шаблоном регулярного выражения, а затем использовать обработчик для поиска совпадения в тексте несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="e263f-155">You can couple the regular expression engine with a particular regular expression pattern and then use the engine to match text in several ways:</span></span>

* <span data-ttu-id="e263f-156">Можно вызвать статический метод поиска совпадения с шаблоном, такой как [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String)).</span><span class="sxs-lookup"><span data-stu-id="e263f-156">You can call a static pattern-matching method, such as [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String)).</span></span> <span data-ttu-id="e263f-157">При этом не требуется создание объекта регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="e263f-157">This does not require instantiation of a regular expression object.</span></span>

* <span data-ttu-id="e263f-158">Можно создать экземпляр объекта [Regex](xref:System.Text.RegularExpressions.Regex) и вызвать метод поиска совпадения с шаблоном этого экземпляра для интерпретированного регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="e263f-158">You can instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object and call an instance pattern-matching method of an interpreted regular expression.</span></span> <span data-ttu-id="e263f-159">Это метод по умолчанию для привязки обработчика регулярных выражений к шаблону регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="e263f-159">This is the default method for binding the regular expression engine to a regular expression pattern.</span></span> <span data-ttu-id="e263f-160">Он дает результат, когда объект [Regex](xref:System.Text.RegularExpressions.Regex) создается без аргумента options, который включает флаг [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled).</span><span class="sxs-lookup"><span data-stu-id="e263f-160">It results when a [Regex](xref:System.Text.RegularExpressions.Regex) object is instantiated without an options argument that includes the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) flag.</span></span>

* <span data-ttu-id="e263f-161">Можно создать экземпляр объекта [Regex](xref:System.Text.RegularExpressions.Regex) и вызвать метод поиска совпадения с шаблоном этого экземпляра для скомпилированного регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="e263f-161">You can instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object and call an instance pattern-matching method of a compiled regular expression.</span></span> <span data-ttu-id="e263f-162">Объекты регулярных выражений представляют скомпилированные шаблоны, когда объект [Regex](xref:System.Text.RegularExpressions.Regex) создается с аргументом options с флагом [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled).</span><span class="sxs-lookup"><span data-stu-id="e263f-162">Regular expression objects represent compiled patterns when a [Regex](xref:System.Text.RegularExpressions.Regex) object is instantiated with an options argument that includes the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) flag.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e263f-163">Способ вызова метода (статический, интерпретированный, скомпилированный) влияет на производительность, если одно регулярное выражение используется многократно при вызове методов или если приложение активно использует объекты регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="e263f-163">The form of the method call (static, interpreted, compiled) affects performance if the same regular expression is used repeatedly in method calls, or if an application makes extensive use of regular expression objects.</span></span>
 
### <a name="static-regular-expressions"></a><span data-ttu-id="e263f-164">Статические регулярные выражения</span><span class="sxs-lookup"><span data-stu-id="e263f-164">Static regular expressions</span></span>

<span data-ttu-id="e263f-165">Статические методы регулярных выражений рекомендуется использовать как альтернативу многократному созданию объектов регулярных выражений с одним регулярным выражением.</span><span class="sxs-lookup"><span data-stu-id="e263f-165">Static regular expression methods are recommended as an alternative to repeatedly instantiating a regular expression object with the same regular expression.</span></span> <span data-ttu-id="e263f-166">В отличие от шаблонов регулярных выражений, используемых объектами регулярных выражений, коды операций или скомпилированный MSIL-код шаблонов, используемых при вызове методов экземпляра, кэшируются внутренне обработчиком регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="e263f-166">Unlike regular expression patterns used by regular expression objects, either the operation codes or the compiled Microsoft intermediate language (MSIL) from patterns used in instance method calls is cached internally by the regular expression engine.</span></span> 

<span data-ttu-id="e263f-167">Например, можно вызывать метод для проверки ввода пользователя.</span><span class="sxs-lookup"><span data-stu-id="e263f-167">For example, you might call a method to validate user input.</span></span> <span data-ttu-id="e263f-168">В этом примере метод с именем `IsValidCurrency` проверяет, что пользователь ввел обозначение денежной единицы и еще по крайней мере один десятичный знак.</span><span class="sxs-lookup"><span data-stu-id="e263f-168">In this example, a method named `IsValidCurrency` checks whether the user has entered a currency symbol followed by at least one decimal digit.</span></span> <span data-ttu-id="e263f-169">Очень неэффективная реализация метода `IsValidCurrency` показана в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e263f-169">A very inefficient implementation of the `IsValidCurrency` method is shown in the following example.</span></span> <span data-ttu-id="e263f-170">Обратите внимание, что при каждом вызове метода заново создается объект [Regex](xref:System.Text.RegularExpressions.Regex) с одним и тем же шаблоном.</span><span class="sxs-lookup"><span data-stu-id="e263f-170">Note that each method call reinstantiates a [Regex](xref:System.Text.RegularExpressions.Regex) object with the same pattern.</span></span> <span data-ttu-id="e263f-171">А это значит, что шаблон регулярного выражения перекомпилируется при каждом вызове метода.</span><span class="sxs-lookup"><span data-stu-id="e263f-171">This, in turn, means that the regular expression pattern must be recompiled each time the method is called.</span></span>

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

<span data-ttu-id="e263f-172">Этот неэффективный код следует заменить вызовом статического метода [Regex.IsMatch(String, String)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String)).</span><span class="sxs-lookup"><span data-stu-id="e263f-172">You should replace this inefficient code with a call to the static [Regex.IsMatch(String, String)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String)) method.</span></span> <span data-ttu-id="e263f-173">Исчезнет необходимость заново создавать объект [Regex](xref:System.Text.RegularExpressions.Regex) при каждом вызове метода поиска совпадения с шаблоном, обработчик регулярных выражений сможет извлекать скомпилированную версию регулярного выражения из кэша.</span><span class="sxs-lookup"><span data-stu-id="e263f-173">This eliminates the need to instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object each time you want to call a pattern-matching method, and enables the regular expression engine to retrieve a compiled version of the regular expression from its cache.</span></span>

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

<span data-ttu-id="e263f-174">По умолчанию кэшируется 15 последних использованных шаблонов статических регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="e263f-174">By default, the last 15 most recently used static regular expression patterns are cached.</span></span> <span data-ttu-id="e263f-175">Для приложений, которым требуется большее число кэшированных статических регулярных выражений, размер кэша можно задать с помощью свойства [Regex.CacheSize](xref:System.Text.RegularExpressions.Regex.CacheSize).</span><span class="sxs-lookup"><span data-stu-id="e263f-175">For applications that require a larger number of cached static regular expressions, the size of the cache can be adjusted by setting the [Regex.CacheSize](xref:System.Text.RegularExpressions.Regex.CacheSize) property.</span></span>

<span data-ttu-id="e263f-176">Регулярное выражение `\p{Sc}+\s*\d+`, используемое в этом примере, проверяет, что входная строка состоит из обозначения валюты и по меньшей мере одного десятичного знака.</span><span class="sxs-lookup"><span data-stu-id="e263f-176">The regular expression `\p{Sc}+\s*\d+` that is used in this example verifies that the input string consists of a currency symbol and at least one decimal digit.</span></span> <span data-ttu-id="e263f-177">Шаблон определяется, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="e263f-177">The pattern is defined as shown in the following table.</span></span>

<span data-ttu-id="e263f-178">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e263f-178">Pattern</span></span> | <span data-ttu-id="e263f-179">Описание</span><span class="sxs-lookup"><span data-stu-id="e263f-179">Description</span></span>
------- | -----------
`\p{Sc}+` | <span data-ttu-id="e263f-180">Совпадение с одним или несколькими символами Unicode Symbol, Currency (символ валюты в Юникоде).</span><span class="sxs-lookup"><span data-stu-id="e263f-180">Match one or more characters in the Unicode Symbol, Currency category.</span></span>
`\s*` | <span data-ttu-id="e263f-181">Соответствует нулю или нескольким символам пробела.</span><span class="sxs-lookup"><span data-stu-id="e263f-181">Match zero or more white-space characters.</span></span>
`\d+` | <span data-ttu-id="e263f-182">Совпадение с одной или несколькими десятичными цифрами.</span><span class="sxs-lookup"><span data-stu-id="e263f-182">Match one or more decimal digits.</span></span>
 
### <a name="interpreted-vs-compiled-regular-expressions"></a><span data-ttu-id="e263f-183">Интерпретированные и скомпилированные регулярные выражения</span><span class="sxs-lookup"><span data-stu-id="e263f-183">Interpreted vs. compiled regular expressions</span></span>

<span data-ttu-id="e263f-184">Шаблоны регулярных выражений, не привязанные к обработчику регулярных выражений указанием параметра [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled), интерпретируются.</span><span class="sxs-lookup"><span data-stu-id="e263f-184">Regular expression patterns that are not bound to the regular expression engine through the specification of the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) option are interpreted.</span></span> <span data-ttu-id="e263f-185">При создании объекта регулярного выражения обработчик регулярных выражений преобразует регулярное выражение в набор кодов операций.</span><span class="sxs-lookup"><span data-stu-id="e263f-185">When a regular expression object is instantiated, the regular expression engine converts the regular expression to a set of operation codes.</span></span> <span data-ttu-id="e263f-186">При вызове метода экземпляра коды операций преобразуются в MSIL-код и выполняются JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="e263f-186">When an instance method is called, the operation codes are converted to MSIL and executed by the JIT compiler.</span></span> <span data-ttu-id="e263f-187">Аналогично, при вызове статического метода регулярного выражения, если не удается найти регулярное выражение в кэше, обработчик регулярных выражений преобразует регулярное выражение в набор кодов операций и хранит их в кэше.</span><span class="sxs-lookup"><span data-stu-id="e263f-187">Similarly, when a static regular expression method is called and the regular expression cannot be found in the cache, the regular expression engine converts the regular expression to a set of operation codes and stores them in the cache.</span></span> <span data-ttu-id="e263f-188">Затем эти коды операций преобразуются в MSIL-код, чтобы JIT-компилятор мог выполнить их.</span><span class="sxs-lookup"><span data-stu-id="e263f-188">It then converts these operation codes to MSIL so that the JIT compiler can execute them.</span></span> <span data-ttu-id="e263f-189">Интерпретированные регулярные выражения снижают время запуска ценой более медленного выполнения.</span><span class="sxs-lookup"><span data-stu-id="e263f-189">Interpreted regular expressions reduce startup time at the cost of slower execution time.</span></span> <span data-ttu-id="e263f-190">Поэтому их лучше всего использовать, когда регулярное выражение используется с небольшим числом вызовов методов или если точное число вызовов методов регулярных выражений неизвестно, но предполагается, что оно будет небольшим.</span><span class="sxs-lookup"><span data-stu-id="e263f-190">Because of this, they are best used when the regular expression is used in a small number of method calls, or if the exact number of calls to regular expression methods is unknown but is expected to be small.</span></span> <span data-ttu-id="e263f-191">По мере увеличения числа вызовов методов выгоду по производительности от быстрого запуска перевешивает низкая скорость выполнения.</span><span class="sxs-lookup"><span data-stu-id="e263f-191">As the number of method calls increases, the performance gain from reduced startup time is outstripped by the slower execution speed.</span></span>

<span data-ttu-id="e263f-192">Шаблоны регулярных выражений, привязанные к обработчику регулярных выражений указанием параметра [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled), компилируются.</span><span class="sxs-lookup"><span data-stu-id="e263f-192">Regular expression patterns that are bound to the regular expression engine through the specification of the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) option are compiled.</span></span> <span data-ttu-id="e263f-193">Это значит, что при создании объекта регулярного выражения или при вызове статического метода регулярного выражения, если не удается найти регулярное выражение в кэше, обработчик регулярных выражений преобразует регулярное выражение в промежуточный набор кодов операций, который затем преобразуется в MSIL-код.</span><span class="sxs-lookup"><span data-stu-id="e263f-193">This means that, when a regular expression object is instantiated, or when a static regular expression method is called and the regular expression cannot be found in the cache, the regular expression engine converts the regular expression to an intermediary set of operation codes, which it then converts to MSIL.</span></span> <span data-ttu-id="e263f-194">Когда вызывается метод, JIT-компилятор выполняет MSIL-код.</span><span class="sxs-lookup"><span data-stu-id="e263f-194">When a method is called, the JIT compiler executes the MSIL.</span></span> <span data-ttu-id="e263f-195">В отличие от интерпретированных регулярных выражений, скомпилированные регулярные выражения увеличивают время запуска, но позволяют выполнять отдельные методы поиска совпадения с шаблоном быстрее.</span><span class="sxs-lookup"><span data-stu-id="e263f-195">In contrast to interpreted regular expressions, compiled regular expressions increase startup time but execute individual pattern-matching methods faster.</span></span> <span data-ttu-id="e263f-196">В результате выгода по производительности от скомпилированных регулярных выражений увеличивается пропорционально числу вызовов методов регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="e263f-196">As a result, the performance benefit that results from compiling the regular expression increases in proportion to the number of regular expression methods called.</span></span>

<span data-ttu-id="e263f-197">Подводя итог, мы рекомендуем использовать интерпретированные регулярные выражения, когда методы регулярного выражения с конкретным регулярным выражением вызываются относительно редко.</span><span class="sxs-lookup"><span data-stu-id="e263f-197">To summarize, we recommend that you use interpreted regular expressions when you call regular expression methods with a specific regular expression relatively infrequently.</span></span> <span data-ttu-id="e263f-198">Скомпилированные регулярные выражения следует использовать, когда методы регулярного выражения с конкретным регулярным выражением вызываются относительно часто.</span><span class="sxs-lookup"><span data-stu-id="e263f-198">You should use compiled regular expressions when you call regular expression methods with a specific regular expression relatively frequently.</span></span> <span data-ttu-id="e263f-199">Точное пороговое значение, начиная с которого низкая скорость выполнения интерпретированных регулярных выражений перевешивает выгоду от быстрого запуска, или пороговое значение, при котором медленный запуск скомпилированных регулярных выражений перевешивает выгоду от быстрого выполнения, трудно указать.</span><span class="sxs-lookup"><span data-stu-id="e263f-199">The exact threshold at which the slower execution speeds of interpreted regular expressions outweigh gains from their reduced startup time, or the threshold at which the slower startup times of compiled regular expressions outweigh gains from their faster execution speeds, is difficult to determine.</span></span> <span data-ttu-id="e263f-200">Оно зависит от нескольких факторов, в том числе от сложности регулярного выражения и конкретных обрабатываемых данных.</span><span class="sxs-lookup"><span data-stu-id="e263f-200">It depends on a variety of factors, including the complexity of the regular expression and the specific data that it processes.</span></span> <span data-ttu-id="e263f-201">Чтобы определить, что позволит добиться лучшей производительности — интерпретированные или скомпилированные регулярные выражения, — можно использовать класс [Stopwatch](xref:System.Diagnostics.Stopwatch), чтобы сравнить время выполнения в обоих случаях.</span><span class="sxs-lookup"><span data-stu-id="e263f-201">To determine whether interpreted or compiled regular expressions offer the best performance for your particular application scenario, you can use the [Stopwatch](xref:System.Diagnostics.Stopwatch) class to compare their execution times.</span></span>

<span data-ttu-id="e263f-202">В следующем примере сравнивается производительность скомпилированных и интерпретированных регулярных выражений при чтении первых десяти предложений, а также при чтении всех предложений текста книги "Финансист" Теодора Драйзера.</span><span class="sxs-lookup"><span data-stu-id="e263f-202">The following example compares the performance of compiled and interpreted regular expressions when reading the first ten sentences and when reading all the sentences in the text of Theodore Dreiser's The Financier.</span></span> <span data-ttu-id="e263f-203">Как показывает вывод примера, если требуется выполнить только&10; вызовов методов поиска совпадения, интерпретированное регулярное выражение дает более высокую производительность.</span><span class="sxs-lookup"><span data-stu-id="e263f-203">As the output from the example shows, when only ten calls are made to regular expression matching methods, an interpreted regular expression offers better performance than a compiled regular expression.</span></span> <span data-ttu-id="e263f-204">Однако скомпилированное регулярное выражение обеспечивает более высокую производительность при большом числе вызовов (в данном случае 13 000).</span><span class="sxs-lookup"><span data-stu-id="e263f-204">However, a compiled regular expression offers better performance when a large number of calls (in this case, over 13,000) are made.</span></span> 

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

<span data-ttu-id="e263f-205">Используемый в примере шаблон регулярного выражения `\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]` определяется, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="e263f-205">The regular expression pattern used in the example, `\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]`, is defined as shown in the following table.</span></span>

<span data-ttu-id="e263f-206">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e263f-206">Pattern</span></span> | <span data-ttu-id="e263f-207">Описание</span><span class="sxs-lookup"><span data-stu-id="e263f-207">Description</span></span>
------- | -----------
`\b` | <span data-ttu-id="e263f-208">Совпадение должно начинаться на границе слова.</span><span class="sxs-lookup"><span data-stu-id="e263f-208">Begin the match at a word boundary.</span></span>
`\w+` | <span data-ttu-id="e263f-209">Совпадение с одним или несколькими символами слова.</span><span class="sxs-lookup"><span data-stu-id="e263f-209">Match one or more word characters.</span></span>
<span data-ttu-id="e263f-210">(\r?\n)</span><span class="sxs-lookup"><span data-stu-id="e263f-210">\`(\r?\n)</span></span>|<span data-ttu-id="e263f-211">,?\s)</span><span class="sxs-lookup"><span data-stu-id="e263f-211">,?\s)\`</span></span> | <span data-ttu-id="e263f-212">Соответствует нулю или одному возврату каретки и последующему символу новой строки; или нулю или одной запятой с последующим пробелом.</span><span class="sxs-lookup"><span data-stu-id="e263f-212">Match either zero or one carriage return followed by a newline character, or zero or one comma followed by a white-space character.</span></span>
<span data-ttu-id="e263f-213">(\w+((\r?\n)</span><span class="sxs-lookup"><span data-stu-id="e263f-213">\`(\w+((\r?\n)</span></span>|<span data-ttu-id="e263f-214">,?\s))*</span><span class="sxs-lookup"><span data-stu-id="e263f-214">,?\s))*\`</span></span> | <span data-ttu-id="e263f-215">Совпадение с одним или несколькими символами слова, за которыми следует ноль или один возврат каретки и символ новой строки, или ноль или одна запятая с последующим пробелом.</span><span class="sxs-lookup"><span data-stu-id="e263f-215">Match zero or more occurrences of one or more word characters that are followed either by zero or one carriage return and a newline character, or by zero or one comma followed by a white-space character.</span></span>
`\w+` | <span data-ttu-id="e263f-216">Совпадение с одним или несколькими символами слова.</span><span class="sxs-lookup"><span data-stu-id="e263f-216">Match one or more word characters.</span></span>
`[.?:;!]` | <span data-ttu-id="e263f-217">Совпадение с точкой, вопросительным знаком, двоеточием, точкой с запятой или восклицательным знаком.</span><span class="sxs-lookup"><span data-stu-id="e263f-217">Match a period, question mark, colon, semicolon, or exclamation point.</span></span>
 
## <a name="take-charge-of-backtracking"></a><span data-ttu-id="e263f-218">Грамотное использование поиска с возвратом</span><span class="sxs-lookup"><span data-stu-id="e263f-218">Take charge of backtracking</span></span>

<span data-ttu-id="e263f-219">Обычно обработчик регулярных выражений двигается по входной строке линейным образом, сравнивая ее с шаблоном регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="e263f-219">Ordinarily, the regular expression engine uses linear progression to move through an input string and compare it to a regular expression pattern.</span></span> <span data-ttu-id="e263f-220">Однако когда в шаблоне регулярного выражения используются неопределенные квантификаторы, такие как __*__, **+** и **?**,</span><span class="sxs-lookup"><span data-stu-id="e263f-220">However, when indeterminate quantifiers such as __*__, **+**, and **?**</span></span> <span data-ttu-id="e263f-221">обработчик регулярных выражений может отбрасывать частичное совпадение и возвращаться к ранее сохраненному состоянию, чтобы искать совпадение с шаблоном целиком.</span><span class="sxs-lookup"><span data-stu-id="e263f-221">are used in a regular expression pattern, the regular expression engine may give up a portion of successful partial matches and return to a previously saved state in order to search for a successful match for the entire pattern.</span></span> <span data-ttu-id="e263f-222">Этот процесс известен как поиск с возвратом.</span><span class="sxs-lookup"><span data-stu-id="e263f-222">This process is known as backtracking.</span></span>

> [!NOTE]
> <span data-ttu-id="e263f-223">Дополнительные сведения о поиске с возвратом см. в статьях [Подробные сведения о поведении регулярных выражений](regex-behavior.md) и [Поиск с возвратом в регулярных выражениях](backtracking.md).</span><span class="sxs-lookup"><span data-stu-id="e263f-223">For more information on backtracking, see [Details of regular expression behavior](regex-behavior.md) and [Backtracking in regular expressions](backtracking.md).</span></span>
 
<span data-ttu-id="e263f-224">Поддержка поиска с возвратом обеспечивает мощность и гибкость регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="e263f-224">Support for backtracking gives regular expressions power and flexibility.</span></span> <span data-ttu-id="e263f-225">При этом ответственность за управление работой обработчика регулярных выражений лежит на разработчике регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="e263f-225">It also places the responsibility for controlling the operation of the regular expression engine in the hands of regular expression developers.</span></span> <span data-ttu-id="e263f-226">Поскольку разработчики часто не отдают себе отчет в этой ответственности, неправильное или излишнее использование поиска с возвратом часто становится причиной снижения производительности регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="e263f-226">Because developers are often not aware of this responsibility, their misuse of backtracking or reliance on excessive backtracking often plays the most significant role in degrading regular expression performance.</span></span> <span data-ttu-id="e263f-227">В самом неблагоприятном случае время обработки может удваиваться при каждом добавлении символа во входную строку.</span><span class="sxs-lookup"><span data-stu-id="e263f-227">In a worst-case scenario, execution time can double for each additional character in the input string.</span></span> <span data-ttu-id="e263f-228">Чрезмерно используя поиск с возвратом, очень легко создать программный аналог бесконечной петли, если входные данные почти совпадают с шаблоном регулярного выражения. Обработчик регулярных выражений может в течение часов или даже дней обрабатывать относительно короткую входную строку.</span><span class="sxs-lookup"><span data-stu-id="e263f-228">In fact, by using backtracking excessively, it is easy to create the programmatic equivalent of an endless loop if input nearly matches the regular expression pattern; the regular expression engine may take hours or even days to process a relatively short input string.</span></span>

<span data-ttu-id="e263f-229">Часто приложения имеют сниженную производительность из-за использования поиска с возвратом, хотя поиск с возвратом не очень важен для обнаружения совпадения.</span><span class="sxs-lookup"><span data-stu-id="e263f-229">Often, applications pay a performance penalty for using backtracking despite the fact that backtracking is not essential for a match.</span></span> <span data-ttu-id="e263f-230">Например, регулярное выражение `\b\p{Lu}\w*\b` совпадает со всеми словами, начинающимися с символа верхнего регистра, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="e263f-230">For example, the regular expression `\b\p{Lu}\w*\b` matches all words that begin with an uppercase character, as the following table shows.</span></span>

<span data-ttu-id="e263f-231">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e263f-231">Pattern</span></span> | <span data-ttu-id="e263f-232">Описание</span><span class="sxs-lookup"><span data-stu-id="e263f-232">Description</span></span>
------- | -----------
`\b` | <span data-ttu-id="e263f-233">Совпадение должно начинаться на границе слова.</span><span class="sxs-lookup"><span data-stu-id="e263f-233">Begin the match at a word boundary.</span></span>
`\p{Lu}` | <span data-ttu-id="e263f-234">Совпадение с символом верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="e263f-234">Match an uppercase character.</span></span>
`\w*` | <span data-ttu-id="e263f-235">Совпадение с нулем или большим числом буквенных символов.</span><span class="sxs-lookup"><span data-stu-id="e263f-235">Match zero or more word characters.</span></span>
`\b` | <span data-ttu-id="e263f-236">Совпадение должно заканчиваться на границе слова.</span><span class="sxs-lookup"><span data-stu-id="e263f-236">End the match at a word boundary.</span></span>
 
<span data-ttu-id="e263f-237">Поскольку граница слова не является символом слова (или подмножеством символов слова), нет шанса, что регулярное выражение перейдет границу слова, сопоставляя символы слова.</span><span class="sxs-lookup"><span data-stu-id="e263f-237">Because a word boundary is not the same as, or a subset of, a word character, there is no possibility that the regular expression engine will cross a word boundary when matching word characters.</span></span> <span data-ttu-id="e263f-238">Это значит, что для этого регулярного выражения поиск с возвратом не принесет никакой пользы, а только снизит производительность, поскольку обработчик регулярных выражений вынужден сохранять свое состояние для каждого возможного совпадения.</span><span class="sxs-lookup"><span data-stu-id="e263f-238">This means that for this regular expression, backtracking can never contribute to the overall success of any match -- it can only degrade performance, because the regular expression engine is forced to save its state for each successful preliminary match of a word character.</span></span>

<span data-ttu-id="e263f-239">Если вы понимаете, что нет необходимости использовать поиск с возвратом, его можно отключить с помощью языкового элемента **(?>**_subexpression_**)**.</span><span class="sxs-lookup"><span data-stu-id="e263f-239">If you determine that backtracking is not necessary, you can disable it by using the **(?>**_subexpression_**)** language element.</span></span> <span data-ttu-id="e263f-240">В следующем примере производится анализ входной строки с использованием двух регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="e263f-240">The following example parses an input string by using two regular expressions.</span></span> <span data-ttu-id="e263f-241">Функционирование первого регулярного выражения, `\b\p{Lu}\w*\b`, основано на поиске с возвратом.</span><span class="sxs-lookup"><span data-stu-id="e263f-241">The first, `\b\p{Lu}\w*\b`, relies on backtracking.</span></span> <span data-ttu-id="e263f-242">Второе регулярное выражение, `\b\p{Lu}(?>\w*)\b`, отключает поиск с возвратом.</span><span class="sxs-lookup"><span data-stu-id="e263f-242">The second, `\b\p{Lu}(?>\w*)\b`, disables backtracking.</span></span> <span data-ttu-id="e263f-243">Как видно по выводу, выражения дают одинаковый результат.</span><span class="sxs-lookup"><span data-stu-id="e263f-243">As the output from the example shows, they both produce the same result.</span></span>

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

<span data-ttu-id="e263f-244">Часто поиск с возвратом очень важен для поиска во входной строке совпадения с шаблоном регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="e263f-244">In many cases, backtracking is essential for matching a regular expression pattern to input text.</span></span> <span data-ttu-id="e263f-245">Тем не менее избыточное использование поиска с возвратом может сильно снизить производительность и создать впечатление, что приложение перестало отвечать.</span><span class="sxs-lookup"><span data-stu-id="e263f-245">However, excessive backtracking can severely degrade performance and create the impression that an application has stopped responding.</span></span> <span data-ttu-id="e263f-246">Например, так происходит, когда используются вложенные квантификаторы и текст, совпадающий со внешней частью выражения, является подмножеством текста, совпадающего со внутренней частью выражения.</span><span class="sxs-lookup"><span data-stu-id="e263f-246">In particular, this happens when quantifiers are nested and the text that matches the outer subexpression is a subset of the text that matches the inner subexpression.</span></span> 

> [!WARNING]
> <span data-ttu-id="e263f-247">Помимо того, что следует избегать избыточного использования поиска с возвратом, необходимо использовать возможность времени ожидания, чтобы убедиться, что избыточный поиск с возвратом не слишком сильно снижает производительность регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="e263f-247">In addition to avoiding excessive backtracking, you should use the timeout feature to ensure that excessive backtracking does not severely degrade regular expression performance.</span></span> <span data-ttu-id="e263f-248">Дополнительные сведения см. в разделе [Использование значений времени ожидания](#use-time-out-values).</span><span class="sxs-lookup"><span data-stu-id="e263f-248">For more information, see the [Use time-out values](#use-time-out-values) section.</span></span>
 
<span data-ttu-id="e263f-249">Например, шаблон регулярного выражения `^[0-9A-Z]([-.\w]*[0-9A-Z])*\$$` должен искать номер части, состоящий из по крайней мере одного алфавитно-цифрового символа.</span><span class="sxs-lookup"><span data-stu-id="e263f-249">For example, the regular expression pattern `^[0-9A-Z]([-.\w]*[0-9A-Z])*\$$` is intended to match a part number that consists of at least one alphanumeric character.</span></span> <span data-ttu-id="e263f-250">Дополнительные символы могут включать в себя алфавитно-цифровые символы, дефис, подчеркивание или точку, но последний символ должен быть алфавитно-цифровым.</span><span class="sxs-lookup"><span data-stu-id="e263f-250">Any additional characters can consist of an alphanumeric character, a hyphen, an underscore, or a period, though the last character must be alphanumeric.</span></span> <span data-ttu-id="e263f-251">Знак доллара завершает номер части.</span><span class="sxs-lookup"><span data-stu-id="e263f-251">A dollar sign terminates the part number.</span></span> <span data-ttu-id="e263f-252">В некоторых случаях этот шаблон регулярного выражения может привести к очень низкой производительности, поскольку в нем используются вложенные квантификаторы и часть выражения `[0-9A-Z]` является подмножеством части выражения `[-.\w]*`.</span><span class="sxs-lookup"><span data-stu-id="e263f-252">In some cases, this regular expression pattern can exhibit extremely poor performance because quantifiers are nested, and because the subexpression `[0-9A-Z]` is a subset of the subexpression `[-.\w]*`.</span></span>

<span data-ttu-id="e263f-253">В таких случаях можно оптимизировать производительность, удалив вложенные квантификаторы и заменив внешнюю часть выражения утверждением просмотра вперед или назад нулевой ширины.</span><span class="sxs-lookup"><span data-stu-id="e263f-253">In these cases, you can optimize regular expression performance by removing the nested quantifiers and replacing the outer subexpression with a zero-width lookahead or lookbehind assertion.</span></span> <span data-ttu-id="e263f-254">Утверждения просмотра вперед и назад являются "якорями". Они не перемещают указатель во входной строке, а выполняют поиск впереди или позади, проверяя, выполняется ли заданное условие.</span><span class="sxs-lookup"><span data-stu-id="e263f-254">Lookahead and lookbehind assertions are anchors; they do not move the pointer in the input string, but instead look ahead or behind to check whether a specified condition is met.</span></span> <span data-ttu-id="e263f-255">Например, регулярное выражение для поиска номера части можно записать следующим образом: `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$`.</span><span class="sxs-lookup"><span data-stu-id="e263f-255">For example, the part number regular expression can be rewritten as `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$`.</span></span> <span data-ttu-id="e263f-256">Этот шаблон регулярного выражения определяется, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="e263f-256">This regular expression pattern is defined as shown in the following table.</span></span>

<span data-ttu-id="e263f-257">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e263f-257">Pattern</span></span> | <span data-ttu-id="e263f-258">Описание</span><span class="sxs-lookup"><span data-stu-id="e263f-258">Description</span></span>
------- | -----------
`^` | <span data-ttu-id="e263f-259">Начало совпадения в начале входной строки.</span><span class="sxs-lookup"><span data-stu-id="e263f-259">Begin the match at the beginning of the input string.</span></span>
`[0-9A-Z]` | <span data-ttu-id="e263f-260">Совпадение с алфавитно-цифровым символом.</span><span class="sxs-lookup"><span data-stu-id="e263f-260">Match an alphanumeric character.</span></span> <span data-ttu-id="e263f-261">Номер части должен состоять по меньшей мере из этого символа.</span><span class="sxs-lookup"><span data-stu-id="e263f-261">The part number must consist of at least this character.</span></span>
`[-.\w]*` | <span data-ttu-id="e263f-262">Совпадение с нулем или большим числом вхождений любого символа слова, дефиса или точки.</span><span class="sxs-lookup"><span data-stu-id="e263f-262">Match zero or more occurrences of any word character, hyphen, or period.</span></span>
<span data-ttu-id="e263f-263">\`\$]</span><span class="sxs-lookup"><span data-stu-id="e263f-263">\`\$]</span></span> | <span data-ttu-id="e263f-264">Совпадение со знаком доллара.</span><span class="sxs-lookup"><span data-stu-id="e263f-264">Match a dollar sign.</span></span>
`(?<=[0-9A-Z])` | <span data-ttu-id="e263f-265">Посмотреть перед конечным знаком доллара, чтобы проверить, что предыдущий символ — это алфавитно-цифровой символ.</span><span class="sxs-lookup"><span data-stu-id="e263f-265">Look ahead of the ending dollar sign to ensure that the previous character is alphanumeric.</span></span>
<span data-ttu-id="e263f-266">`$`: совпадение должно заканчиваться в конце входной строки.</span><span class="sxs-lookup"><span data-stu-id="e263f-266">`$` End the match at the end of the input string.</span></span>
 
<span data-ttu-id="e263f-267">В приведенном ниже примере демонстрируется использование этого регулярного выражения для поиска совпадений в массиве потенциальных номеров частей.</span><span class="sxs-lookup"><span data-stu-id="e263f-267">The following example illustrates the use of this regular expression to match an array containing possible part numbers.</span></span>

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

<span data-ttu-id="e263f-268">Язык регулярных выражений в .NET включает следующие языковые элементы, которые можно использовать для исключения вложенных квантификаторов.</span><span class="sxs-lookup"><span data-stu-id="e263f-268">The regular expression language in .NET includes the following language elements that you can use to eliminate nested quantifiers.</span></span> <span data-ttu-id="e263f-269">Дополнительные сведения см. в статье [Конструкции группировки в регулярных выражениях](grouping.md).</span><span class="sxs-lookup"><span data-stu-id="e263f-269">For more information, see [Grouping constructs in regular expressions](grouping.md).</span></span>

<span data-ttu-id="e263f-270">Элемент языка</span><span class="sxs-lookup"><span data-stu-id="e263f-270">Language element</span></span> | <span data-ttu-id="e263f-271">Описание</span><span class="sxs-lookup"><span data-stu-id="e263f-271">Description</span></span>
---------------- | ----------- 
<span data-ttu-id="e263f-272">**(?**=_subexpression_**)**</span><span class="sxs-lookup"><span data-stu-id="e263f-272">**(?**=_subexpression_**)**</span></span> | <span data-ttu-id="e263f-273">Положительный просмотр вперед нулевой ширины.</span><span class="sxs-lookup"><span data-stu-id="e263f-273">Zero-width positive lookahead.</span></span> <span data-ttu-id="e263f-274">Поиск перед текущей позицией с целью проверить, совпадает ли параметр *subexpression* со входной строкой.</span><span class="sxs-lookup"><span data-stu-id="e263f-274">Look ahead of the current position to determine whether *subexpression* matches the input string.</span></span>
<span data-ttu-id="e263f-275">**(?!**_subexpression_**)**</span><span class="sxs-lookup"><span data-stu-id="e263f-275">**(?!**_subexpression_**)**</span></span> | <span data-ttu-id="e263f-276">Отрицательный просмотр вперед нулевой ширины.</span><span class="sxs-lookup"><span data-stu-id="e263f-276">Zero-width negative lookahead.</span></span> <span data-ttu-id="e263f-277">Поиск перед текущей позицией с целью проверить, что параметр *subexpression* не совпадает со входной строкой.</span><span class="sxs-lookup"><span data-stu-id="e263f-277">Look ahead of the current position to determine whether *subexpression* does not match the input string.</span></span>
<span data-ttu-id="e263f-278">**(?<**=_subexpression_**)**</span><span class="sxs-lookup"><span data-stu-id="e263f-278">**(?<**=_subexpression_**)**</span></span> | <span data-ttu-id="e263f-279">Положительный просмотр назад нулевой ширины.</span><span class="sxs-lookup"><span data-stu-id="e263f-279">Zero-width positive lookbehind.</span></span> <span data-ttu-id="e263f-280">Поиск за текущей позицией с целью проверить, что параметр *subexpression* совпадает со входной строкой.</span><span class="sxs-lookup"><span data-stu-id="e263f-280">Look behind the current position to determine whether *subexpression* matches the input string.</span></span>
<span data-ttu-id="e263f-281">**(?<!**_subexpression_**)**</span><span class="sxs-lookup"><span data-stu-id="e263f-281">**(?<!**_subexpression_**)**</span></span> | <span data-ttu-id="e263f-282">Отрицательный просмотр назад нулевой ширины.</span><span class="sxs-lookup"><span data-stu-id="e263f-282">Zero-width negative lookbehind.</span></span> <span data-ttu-id="e263f-283">Поиск за текущей позицией с целью проверить, что параметр *subexpression* не совпадает со входной строкой.</span><span class="sxs-lookup"><span data-stu-id="e263f-283">Look behind the current position to determine whether *subexpression* does not match the input string.</span></span>
 
## <a name="use-time-out-values"></a><span data-ttu-id="e263f-284">Использование значений времени ожидания</span><span class="sxs-lookup"><span data-stu-id="e263f-284">Use time-out values</span></span>

<span data-ttu-id="e263f-285">Если регулярные выражения обрабатывают входные данные, которые почти совпадают с шаблоном регулярного выражения, зачастую они могут использовать избыточный поиск с возвратом, что сильно влияет на их производительность.</span><span class="sxs-lookup"><span data-stu-id="e263f-285">If your regular expressions processes input that nearly matches the regular expression pattern, it can often rely on excessive backtracking, which impacts its performance significantly.</span></span> <span data-ttu-id="e263f-286">Помимо того, что следует тщательно обдумывать использование поиска с возвратом и тестировать регулярное выражение на почти совпадающих входных данных, необходимо всегда устанавливать значение времени ожидания для минимизации влияния на производительность избыточного поиска с возвратом, если он все же используется.</span><span class="sxs-lookup"><span data-stu-id="e263f-286">In addition to carefully considering your use of backtracking and testing the regular expression against near-matching input, you should always set a time-out value to ensure that the impact of excessive backtracking, if it occurs, is minimized.</span></span>

<span data-ttu-id="e263f-287">Интервал времени ожидания регулярного выражения определяет период времени, в течение которого обработчик регулярных выражений выполняет поиск одного совпадения, после чего время ожидания истекает.</span><span class="sxs-lookup"><span data-stu-id="e263f-287">The regular expression time-out interval defines the period of time that the regular expression engine will look for a single match before it times out.</span></span> <span data-ttu-id="e263f-288">По умолчанию интервал времени ожидания равен [Regex.InfiniteMatchTimeout](xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout), что означает, что регулярное выражение имеет неограниченное время ожидания.</span><span class="sxs-lookup"><span data-stu-id="e263f-288">The default time-out interval is [Regex.InfiniteMatchTimeout](xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout), which means that the regular expression will not time out.</span></span> <span data-ttu-id="e263f-289">Можно переопределить это значение и задать интервал времени ожидания следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e263f-289">You can override this value and define a time-out interval as follows:</span></span> 

* <span data-ttu-id="e263f-290">предоставив значение времени ожидания при создании экземпляра объекта [Regex](xref:System.Text.RegularExpressions.Regex) путем вызова конструктора [Regex(String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.%23ctor(System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan));</span><span class="sxs-lookup"><span data-stu-id="e263f-290">By providing a time-out value when you instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object by calling the [Regex(String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.%23ctor(System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) constructor.</span></span>

* <span data-ttu-id="e263f-291">путем вызова статического метода поиска совпадения с шаблоном, такого как [Regex.Match(String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) или [Regex.Replace(String, String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)), который имеет параметр *matchTimeout*.</span><span class="sxs-lookup"><span data-stu-id="e263f-291">By calling a static pattern matching method, such as [Regex.Match(String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) or [Regex.Replace(String, String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)), that includes a *matchTimeout* parameter.</span></span>

<span data-ttu-id="e263f-292">Если определен интервал времени ожидания и по истечении этого интервала совпадение не найдено, метод регулярного выражения вызывает исключение [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException).</span><span class="sxs-lookup"><span data-stu-id="e263f-292">If you have defined a time-out interval and a match is not found at the end of that interval, the regular expression method throws a [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException) exception.</span></span> <span data-ttu-id="e263f-293">В обработчике исключений можно принять решение о том, повторить ли поиск совпадения с более длинным интервалом времени ожидания, отказаться от попытки поиска совпадения и предположить, что совпадение не найдено, или же отказаться от попытки поиска совпадения и зарегистрировать сведения об исключении в журнале для анализа в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="e263f-293">In your exception handler, you can choose to retry the match with a longer time-out interval, abandon the match attempt and assume that there is no match, or abandon the match attempt and log the exception information for future analysis.</span></span>

<span data-ttu-id="e263f-294">В следующем примере определяется метод `GetWordData`, который создает регулярное выражение с интервалом времени ожидания 350 миллисекунд, чтобы вычислить количество слов и среднее количество символов в слове в текстовом документе.</span><span class="sxs-lookup"><span data-stu-id="e263f-294">The following example defines a `GetWordData` method that instantiates a regular expression with a time-out interval of 350 milliseconds to calculate the number of words and average number of characters in a word in a text document.</span></span> <span data-ttu-id="e263f-295">Если время ожидания для операции поиска совпадения истекает, интервал времени ожидания увеличивается на 350 миллисекунд, и объект [Regex](xref:System.Text.RegularExpressions.Regex) создается заново.</span><span class="sxs-lookup"><span data-stu-id="e263f-295">If the matching operation times out, the time-out interval is increased by 350 milliseconds and the [Regex](xref:System.Text.RegularExpressions.Regex) object is re-instantiated.</span></span> <span data-ttu-id="e263f-296">Если новый интервал времени ожидания превышает 1 секунду, метод передает исключение вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="e263f-296">If the new time-out interval exceeds 1 second, the method re-throws the exception to the caller.</span></span>

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

## <a name="capture-only-when-necessary"></a><span data-ttu-id="e263f-297">Захват только в случае необходимости</span><span class="sxs-lookup"><span data-stu-id="e263f-297">Capture only when necessary</span></span>

<span data-ttu-id="e263f-298">Регулярные выражения в .NET поддерживают ряд конструкций группирования, позволяющих группировать шаблон регулярного выражения в виде одной или более частей.</span><span class="sxs-lookup"><span data-stu-id="e263f-298">Regular expressions in .NET support a number of grouping constructs, which let you group a regular expression pattern into one or more subexpressions.</span></span> <span data-ttu-id="e263f-299">Наиболее часто в языке регулярных выражений .NET используются конструкции группирования **(**_subexpression_**)**, которая определяет нумерованную группу записи, и **(?<*_name_**>**_subexpression_**)**, которая определяет именованную группу записи.</span><span class="sxs-lookup"><span data-stu-id="e263f-299">The most commonly used grouping constructs in .NET regular expression language are **(**_subexpression_**)**, which defines a numbered capturing group, and **(?<*_name_**>**_subexpression_**)**, which defines a named capturing group.</span></span> <span data-ttu-id="e263f-300">Конструкции группирования крайне важны для создания обратных ссылок и для определения части выражения, к которой должен применяться квантификатор.</span><span class="sxs-lookup"><span data-stu-id="e263f-300">Grouping constructs are essential for creating backreferences and for defining a subexpression to which a quantifier is applied.</span></span> 

<span data-ttu-id="e263f-301">Однако использование этих языковых элементов имеет последствия.</span><span class="sxs-lookup"><span data-stu-id="e263f-301">However, the use of these language elements has a cost.</span></span> <span data-ttu-id="e263f-302">Объект [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection), возвращаемый свойством [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups), заполняется наиболее новыми неименованными или именованными захваченными объектами, и если одна конструкция группирования захватила несколько подстрок из входной строки, они заполняют объект [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection), возвращаемый свойством [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) определенной группы захвата с несколькими объектами [Capture](xref:System.Text.RegularExpressions.Capture).</span><span class="sxs-lookup"><span data-stu-id="e263f-302">They cause the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) object returned by the [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) property to be populated with the most recent unnamed or named captures, and if a single grouping construct has captured multiple substrings in the input string, they also populate the [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) object returned by the [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) property of a particular capturing group with multiple [Capture](xref:System.Text.RegularExpressions.Capture) objects.</span></span>

<span data-ttu-id="e263f-303">Часто конструкции группирования используются в регулярном выражении только для того, чтобы к нему можно было применить квантификаторы, и группы, захваченные этими частями выражения затем не используются.</span><span class="sxs-lookup"><span data-stu-id="e263f-303">Often, grouping constructs are used in a regular expression only so that quantifiers can be applied to them, and the groups captured by these subexpressions are not subsequently used.</span></span> <span data-ttu-id="e263f-304">Например, регулярное выражение `\b(\w+[;,]?\s?)+[.?!]` предназначено для записи всего предложения.</span><span class="sxs-lookup"><span data-stu-id="e263f-304">For example, the regular expression `\b(\w+[;,]?\s?)+[.?!]` is designed to capture an entire sentence.</span></span> <span data-ttu-id="e263f-305">В следующей таблице описаны языковые элементы этого шаблона регулярных выражений и их влияние на коллекции [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) и [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) объекта [Match](xref:System.Text.RegularExpressions.Match).</span><span class="sxs-lookup"><span data-stu-id="e263f-305">The following table describes the language elements in this regular expression pattern and their effect on the [Match](xref:System.Text.RegularExpressions.Match) object's [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) and [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) collections.</span></span>

<span data-ttu-id="e263f-306">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e263f-306">Pattern</span></span> | <span data-ttu-id="e263f-307">Описание</span><span class="sxs-lookup"><span data-stu-id="e263f-307">Description</span></span>
------- | -----------
`\b` | <span data-ttu-id="e263f-308">Совпадение должно начинаться на границе слова.</span><span class="sxs-lookup"><span data-stu-id="e263f-308">Begin the match at a word boundary.</span></span>
`\w+` | <span data-ttu-id="e263f-309">Совпадение с одним или несколькими символами слова.</span><span class="sxs-lookup"><span data-stu-id="e263f-309">Match one or more word characters.</span></span>
`[;,]?` | <span data-ttu-id="e263f-310">Совпадение с нулем или одной запятой или точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="e263f-310">Match zero or one comma or semicolon.</span></span>
`\s?` | <span data-ttu-id="e263f-311">Совпадение с нулем или одним символом пробела.</span><span class="sxs-lookup"><span data-stu-id="e263f-311">Match zero or one white-space character.</span></span>
`(\w+[;,]?\s?)+` | <span data-ttu-id="e263f-312">Совпадение с одним или большим числом символов слова; затем, необязательно, запятой или точкой с запятой; затем, необязательно, пробелом.</span><span class="sxs-lookup"><span data-stu-id="e263f-312">Match one or more occurrences of one or more word characters followed by an optional comma or semicolon followed by an optional white-space character.</span></span> <span data-ttu-id="e263f-313">Здесь определена первая группа захвата, которая необходима, чтобы набор нескольких символов слова (то есть слово) и необязательно следующий за ним знак препинания повторялись, пока регулярное выражение не достигнет конца предложения.</span><span class="sxs-lookup"><span data-stu-id="e263f-313">This defines the first capturing group, which is necessary so that the combination of multiple word characters (that is, a word) followed by an optional punctuation symbol will be repeated until the regular expression engine reaches the end of a sentence.</span></span>
`[.?!]` | <span data-ttu-id="e263f-314">Совпадение с точкой, вопросительным знаком или восклицательным знаком.</span><span class="sxs-lookup"><span data-stu-id="e263f-314">Match a period, question mark, or exclamation point.</span></span>
 
<span data-ttu-id="e263f-315">Как показано в следующем примере, когда совпадение найдено, объекты [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) и [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) заполняются захваченными объектами из совпадения.</span><span class="sxs-lookup"><span data-stu-id="e263f-315">As the following example shows, when a match is found, both the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) and [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) objects are populated with captures from the match.</span></span> <span data-ttu-id="e263f-316">В этом случае используется группа записи `(\w+[;,]?\s?)`, чтобы к ней можно было применить квантификатор **+**, который позволяет шаблону регулярного выражения сопоставить каждое слово в предложении.</span><span class="sxs-lookup"><span data-stu-id="e263f-316">In this case, the capturing group `(\w+[;,]?\s?)` exists so that the **+** quantifier can be applied to it, which enables the regular expression pattern to match each word in a sentence.</span></span> <span data-ttu-id="e263f-317">В противном случае было бы найдено совпадение только с последним словом предложения.</span><span class="sxs-lookup"><span data-stu-id="e263f-317">Otherwise, it would match the last word in a sentence.</span></span>

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

<span data-ttu-id="e263f-318">Если части выражения используются только для применения к ним квантификаторов и захваченный текст не нужен, следует отменить захваты групп.</span><span class="sxs-lookup"><span data-stu-id="e263f-318">When you use subexpressions only to apply quantifiers to them, and you are not interested in the captured text, you should disable group captures.</span></span> <span data-ttu-id="e263f-319">Например, языковой элемент **(?:**_subexpression_**)** не позволяет группе, к которой он применен, захватывать совпавшие подстроки.</span><span class="sxs-lookup"><span data-stu-id="e263f-319">For example, the **(?:**_subexpression_**)** language element prevents the group to which it applies from capturing matched substrings.</span></span> <span data-ttu-id="e263f-320">В следующем примере шаблон регулярного выражения из предыдущего примера изменен на `\b(?:\w+[;,]?\s?)+[.?!]`.</span><span class="sxs-lookup"><span data-stu-id="e263f-320">In the following example, the regular expression pattern from the previous example is changed to `\b(?:\w+[;,]?\s?)+[.?!]`.</span></span> <span data-ttu-id="e263f-321">Как показывает вывод, обработчик регулярных выражений не заполняет коллекции [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) и [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection).</span><span class="sxs-lookup"><span data-stu-id="e263f-321">As the output shows, it prevents the regular expression engine from populating the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) and [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) collections.</span></span>

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

<span data-ttu-id="e263f-322">Отключить захват можно одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="e263f-322">You can disable captures in one of the following ways:</span></span>

* <span data-ttu-id="e263f-323">Использовать языковой элемент **(?:**_subexpression_**)**.</span><span class="sxs-lookup"><span data-stu-id="e263f-323">Use the **(?:**_subexpression_**)** language element.</span></span> <span data-ttu-id="e263f-324">Этот элемент отключает захват совпавших подстрок в группе, к которой он применен.</span><span class="sxs-lookup"><span data-stu-id="e263f-324">This element prevents the capture of matched substrings in the group to which it applies.</span></span> <span data-ttu-id="e263f-325">Во вложенных группах захват подстрок не отключается.</span><span class="sxs-lookup"><span data-stu-id="e263f-325">It does not disable substring captures in any nested groups.</span></span>

* <span data-ttu-id="e263f-326">Использовать параметр [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture).</span><span class="sxs-lookup"><span data-stu-id="e263f-326">Use the [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) option.</span></span> <span data-ttu-id="e263f-327">Он отключает все неименованные и неявные захваты для шаблона регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="e263f-327">It disables all unnamed or implicit captures in the regular expression pattern.</span></span> <span data-ttu-id="e263f-328">При использовании этого параметра могут захватываться только подстроки, совпадающие с именованными группами, определенными с помощью языкового элемента **(?<**_name_**>**_subexpression_**)**.</span><span class="sxs-lookup"><span data-stu-id="e263f-328">When you use this option, only substrings that match named groups defined with the **(?<**_name_**>**_subexpression_**)** language element can be captured.</span></span> <span data-ttu-id="e263f-329">Флаг [ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) можно передать в параметр options конструктора класса [Regex](xref:System.Text.RegularExpressions.Regex) или в параметр options статического метода поиска совпадения [Regex](xref:System.Text.RegularExpressions.Regex).</span><span class="sxs-lookup"><span data-stu-id="e263f-329">The [ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) flag can be passed to the options parameter of a [Regex](xref:System.Text.RegularExpressions.Regex) class constructor or to the options parameter of a [Regex](xref:System.Text.RegularExpressions.Regex) static matching method.</span></span>

* <span data-ttu-id="e263f-330">Использовать параметр **n** в языковом элементе **(?imnsx)**.</span><span class="sxs-lookup"><span data-stu-id="e263f-330">Use the **n** option in the **(?imnsx)** language element.</span></span> <span data-ttu-id="e263f-331">Этот параметр отключает все неименованные или неявные захваты, начиная с того места, на котором находится этот элемент в шаблоне регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="e263f-331">This option disables all unnamed or implicit captures from the point in the regular expression pattern at which the element appears.</span></span> <span data-ttu-id="e263f-332">Захват отключается либо до конца шаблона, либо пока захват для неименованных и неявных объектов не будет включен параметром **(-n)**.</span><span class="sxs-lookup"><span data-stu-id="e263f-332">Captures are disabled either until the end of the pattern or until the **(-n)** option enables unnamed or implicit captures.</span></span> <span data-ttu-id="e263f-333">Дополнительные сведения см. в статье [Другие конструкции в регулярных выражениях](miscellaneous.md).</span><span class="sxs-lookup"><span data-stu-id="e263f-333">For more information, see [Miscellaneous constructs in regular expressions](miscellaneous.md).</span></span>

* <span data-ttu-id="e263f-334">Использовать параметр **n** в языковом элементе **(?imnsx:**_subexpression_**)**.</span><span class="sxs-lookup"><span data-stu-id="e263f-334">Use the **n** option in the **(?imnsx:**_subexpression_**)** language element.</span></span> <span data-ttu-id="e263f-335">Этот параметр отключает все неименованные и неявные захваты в части выражения *subexpression*.</span><span class="sxs-lookup"><span data-stu-id="e263f-335">This option disables all unnamed or implicit captures in *subexpression*.</span></span> <span data-ttu-id="e263f-336">Захваты для всех вложенных неименованных и неявных групп также отключаются.</span><span class="sxs-lookup"><span data-stu-id="e263f-336">Captures by any unnamed or implicit nested capturing groups are disabled as well.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e263f-337">См. также</span><span class="sxs-lookup"><span data-stu-id="e263f-337">Related topics</span></span>

<span data-ttu-id="e263f-338">Заголовок</span><span class="sxs-lookup"><span data-stu-id="e263f-338">Title</span></span> | <span data-ttu-id="e263f-339">Описание</span><span class="sxs-lookup"><span data-stu-id="e263f-339">Description</span></span>
----- | ----------- 
[<span data-ttu-id="e263f-340">Подробные сведения о поведении регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="e263f-340">Details of regular expression behavior</span></span>](regex-behavior.md) | <span data-ttu-id="e263f-341">Описание реализации обработчика регулярных выражений в .NET.</span><span class="sxs-lookup"><span data-stu-id="e263f-341">Examines the implementation of the regular expression engine in .NET.</span></span> <span data-ttu-id="e263f-342">В этом разделе основное внимание уделено гибкости регулярных выражений; кроме того, рассказывается об ответственности разработчика за эффективную и надежную работу обработчика регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="e263f-342">The topic focuses on the flexibility of regular expressions and explains the developer's responsibility for ensuring the efficient and robust operation of the regular expression engine.</span></span>
[<span data-ttu-id="e263f-343">Поиск с возвратом в регулярных выражениях</span><span class="sxs-lookup"><span data-stu-id="e263f-343">Backtracking in regular expressions</span></span>](backtracking.md) | <span data-ttu-id="e263f-344">Описание поиска с возвратом и того, как он влияет на производительность регулярных выражений. Описание языковых элементов, которые можно использовать вместо поиска с возвратом.</span><span class="sxs-lookup"><span data-stu-id="e263f-344">Explains what backtracking is and how it affects regular expression performance, and examines language elements that provide alternatives to backtracking.</span></span>
[<span data-ttu-id="e263f-345">Элементы языка регулярных выражений — краткий справочник</span><span class="sxs-lookup"><span data-stu-id="e263f-345">Regular expression language - quick reference</span></span>](quick-ref.md) | <span data-ttu-id="e263f-346">Описание элементов языка регулярных выражений в .NET и ссылки на подробную документацию для каждого языкового элемента.</span><span class="sxs-lookup"><span data-stu-id="e263f-346">Describes the elements of the regular expression language in .NET and provides links to detailed documentation for each language element.</span></span>
 


