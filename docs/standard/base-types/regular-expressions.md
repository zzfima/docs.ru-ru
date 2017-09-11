---
title: "Регулярные выражения в .NET"
description: "Регулярные выражения в .NET"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: d1a640cf-09ca-48f7-800c-a627a6d549c9
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: ac26821819b22aa3ea47e6945bb5c8575dcd9807
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="regular-expressions-in-net"></a><span data-ttu-id="6fd26-104">Регулярные выражения в .NET</span><span class="sxs-lookup"><span data-stu-id="6fd26-104">Regular expressions in .NET</span></span>

<span data-ttu-id="6fd26-105">Регулярные выражения предоставляют мощный, гибкий и эффективный способ обработки текста.</span><span class="sxs-lookup"><span data-stu-id="6fd26-105">Regular expressions provide a powerful, flexible, and efficient method for processing text.</span></span> <span data-ttu-id="6fd26-106">Комплексная нотация сопоставления шаблонов регулярных выражений позволяет быстро анализировать большие объемы текста для поиска определенных шаблонов символов, проверять текст на соответствие предопределенному шаблону (например, адресу электронной почты, извлекать, изменять, заменять и удалять текстовые подстроки, а также добавлять извлеченные строки в коллекцию для создания отчета.</span><span class="sxs-lookup"><span data-stu-id="6fd26-106">The extensive pattern-matching notation of regular expressions enables you to quickly parse large amounts of text to find specific character patterns; to validate text to ensure that it matches a predefined pattern (such as an e-mail address); to extract, edit, replace, or delete text substrings; and to add the extracted strings to a collection in order to generate a report.</span></span> <span data-ttu-id="6fd26-107">Для многих приложений, которые работают со строками или анализируют большие блоки текста, регулярные выражения — незаменимый инструмент.</span><span class="sxs-lookup"><span data-stu-id="6fd26-107">For many applications that deal with strings or that parse large blocks of text, regular expressions are an indispensable tool.</span></span>

## <a name="how-regular-expressions-work"></a><span data-ttu-id="6fd26-108">Принцип работы регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="6fd26-108">How Regular Expressions Work</span></span>

<span data-ttu-id="6fd26-109">Главный компонент обработки текста с помощью регулярных выражений — это механизм регулярных выражений, представленный в платформе .NET объектом [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex).</span><span class="sxs-lookup"><span data-stu-id="6fd26-109">The centerpiece of text processing with regular expressions is the regular expression engine, which is represented by the [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) object in .NET.</span></span> <span data-ttu-id="6fd26-110">Как минимум, для обработки текста с использованием в регулярных выражений механизму регулярных выражений необходимо предоставить два следующих элемента:</span><span class="sxs-lookup"><span data-stu-id="6fd26-110">At a minimum, processing text using regular expressions requires that the regular expression engine be provided with the following two items of information:</span></span>

* <span data-ttu-id="6fd26-111">Шаблон регулярного выражения для определения текста.</span><span class="sxs-lookup"><span data-stu-id="6fd26-111">The regular expression pattern to identify in the text.</span></span> 
  
  <span data-ttu-id="6fd26-112">В .NET шаблоны регулярных выражений определяются специальным синтаксисом или языком, который совместим с регулярными выражениями Perl 5 и добавляет дополнительные возможности, например сопоставление справа налево.</span><span class="sxs-lookup"><span data-stu-id="6fd26-112">In .NET, regular expression patterns are defined by a special syntax or language, which is compatible with Perl 5 regular expressions and adds some additional features such as right-to-left matching.</span></span> <span data-ttu-id="6fd26-113">Дополнительные сведения см. в разделе [Элементы языка регулярных выражений. Краткий справочник](quick-ref.md).</span><span class="sxs-lookup"><span data-stu-id="6fd26-113">For more information, see [Regular Expression Language - Quick Reference](quick-ref.md).</span></span>
  
* <span data-ttu-id="6fd26-114">Текст, который будет проанализирован на соответствие шаблону регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="6fd26-114">The text to parse for the regular expression pattern.</span></span>

<span data-ttu-id="6fd26-115">Методы класса [Regex](xref:System.Text.RegularExpressions.Regex) позволяют выполнять перечисленные далее операции.</span><span class="sxs-lookup"><span data-stu-id="6fd26-115">The methods of the [Regex](xref:System.Text.RegularExpressions.Regex) class let you perform the following operations:</span></span>

* <span data-ttu-id="6fd26-116">Определить, входит ли шаблон регулярного выражения во входной текст, с помощью метода [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)).</span><span class="sxs-lookup"><span data-stu-id="6fd26-116">Determine whether the regular expression pattern occurs in the input text by calling the [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) method.</span></span> <span data-ttu-id="6fd26-117">Пример, в котором для проверки текста используется метод [IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)), см. в разделе [Практическое руководство. Проверка соответствия формата строк формату электронной почты](verify-format.md).</span><span class="sxs-lookup"><span data-stu-id="6fd26-117">For an example that uses the [IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) method for validating text, see [How to: Verify that Strings Are in Valid Email Format](verify-format.md).</span></span>

* <span data-ttu-id="6fd26-118">Получить один или все экземпляры текста, соответствующего шаблону регулярного выражения, с помощью метода [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) или [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)).</span><span class="sxs-lookup"><span data-stu-id="6fd26-118">Retrieve one or all occurrences of text that matches the regular expression pattern by calling the [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) or [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) method.</span></span> <span data-ttu-id="6fd26-119">Первый метод возвращает объект [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match), который предоставляет сведения о соответствующем тексте.</span><span class="sxs-lookup"><span data-stu-id="6fd26-119">The former method returns a [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) object that provides information about the matching text.</span></span> <span data-ttu-id="6fd26-120">Второй метод возвращает объект [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection), содержащий один объект [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) для каждого соответствия, обнаруженного в обработанном тексте.</span><span class="sxs-lookup"><span data-stu-id="6fd26-120">The latter returns a [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) object that contains one [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) object for each match found in the parsed text.</span></span> 

* <span data-ttu-id="6fd26-121">Заменить текст, соответствующий шаблону регулярного выражения, с помощью метода [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)).</span><span class="sxs-lookup"><span data-stu-id="6fd26-121">Replace text that matches the regular expression pattern by calling the [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) method.</span></span> <span data-ttu-id="6fd26-122">Примеры использования метода [Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) для изменения форматов даты и удаления недопустимых символов из строки см. в разделах [Практическое руководство. Исключение недопустимых символов из строки](strip-characters.md) и [Пример регулярного выражения. Изменение форматов даты](changing-formats.md).</span><span class="sxs-lookup"><span data-stu-id="6fd26-122">For examples that use the [Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) method to change date formats and remove invalid characters from a string, see [How to: Strip Invalid Characters from a String](strip-characters.md) and [Regular Expression Example: Changing Date Formats](changing-formats.md).</span></span>

<span data-ttu-id="6fd26-123">Обзор объектной модели регулярных выражений см. в разделе [Объектная модель регулярных выражений](object-model.md).</span><span class="sxs-lookup"><span data-stu-id="6fd26-123">For an overview of the regular expression object model, see [The Regular Expression Object Model](object-model.md).</span></span>

<span data-ttu-id="6fd26-124">Дополнительные сведения о языке регулярных выражений см. в разделе [Элементы языка регулярных выражений. Краткий справочник](quick-ref.md).</span><span class="sxs-lookup"><span data-stu-id="6fd26-124">For more information about the regular expression language, see [Regular Expression Language - Quick Reference](quick-ref.md).</span></span>

## <a name="regular-expression-examples"></a><span data-ttu-id="6fd26-125">Примеры регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="6fd26-125">Regular Expression Examples</span></span>

<span data-ttu-id="6fd26-126">Класс [String](xref:System.String) содержит ряд методов для поиска и замены строк, которые можно использовать для поиска строковых литералов в длинных строках.</span><span class="sxs-lookup"><span data-stu-id="6fd26-126">The [String](xref:System.String) class includes a number of string search and replacement methods that you can use when you want to locate literal strings in a larger string.</span></span> <span data-ttu-id="6fd26-127">Регулярные выражения максимально полезны, если требуется найти одну из нескольких подстрок в длинной строке или определить шаблоны в строке, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="6fd26-127">Regular expressions are most useful either when you want to locate one of several substrings in a larger string, or when you want to identify patterns in a string, as the following examples illustrate.</span></span> 

### <a name="example-1-replacing-substrings"></a><span data-ttu-id="6fd26-128">Пример 1. Замена подстрок</span><span class="sxs-lookup"><span data-stu-id="6fd26-128">Example 1: Replacing Substrings</span></span>

<span data-ttu-id="6fd26-129">Предположим, что список рассылки содержит имена, в которые иногда входит обращение (Mr., Mrs., Miss или Ms.) в дополнение к имени и фамилии.</span><span class="sxs-lookup"><span data-stu-id="6fd26-129">Assume that a mailing list contains names that sometimes include a title (Mr., Mrs., Miss, or Ms.) along with a first and last name.</span></span> <span data-ttu-id="6fd26-130">Если вы не хотите включать обращения при создании этикеток для конвертов из списка, с помощью регулярного выражения их можно удалить, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6fd26-130">If you do not want to include the titles when you generate envelope labels from the list, you can use a regular expression to remove the titles, as the following example illustrates.</span></span>

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

<span data-ttu-id="6fd26-131">Шаблон регулярного выражения `(Mr\.? |Mrs\.? |Miss |Ms\.? )` сопоставляет все вхождения строк "Mr", "Mr.", "Mrs", "Mrs.", "Miss", "Ms" или "Ms.".</span><span class="sxs-lookup"><span data-stu-id="6fd26-131">The regular expression pattern `(Mr\.? |Mrs\.? |Miss |Ms\.? )` matches any occurrence of "Mr ", "Mr. ", "Mrs ", "Mrs. ", "Miss ", "Ms or "Ms. ".</span></span> <span data-ttu-id="6fd26-132">После вызова метода [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) сопоставленная строка заменяется на [String.Empty](xref:System.String.Empty). Другими словами, она удаляется из исходной строки.</span><span class="sxs-lookup"><span data-stu-id="6fd26-132">The call to the [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) method replaces the matched string with [String.Empty](xref:System.String.Empty); in other words, it removes it from the original string.</span></span>

### <a name="example-2-identifying-duplicated-words"></a><span data-ttu-id="6fd26-133">Пример 2. Поиск повторяющихся слов</span><span class="sxs-lookup"><span data-stu-id="6fd26-133">Example 2: Identifying Duplicated Words</span></span>

<span data-ttu-id="6fd26-134">Случайный повтор слов — это распространенная ошибка при написании текстов.</span><span class="sxs-lookup"><span data-stu-id="6fd26-134">Accidentally duplicating words is a common error that writers make.</span></span> <span data-ttu-id="6fd26-135">Регулярное выражение можно использовать для определения повторяющихся слов, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6fd26-135">A regular expression can be used to identify duplicated words, as the following example shows.</span></span>

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

<span data-ttu-id="6fd26-136">Шаблон регулярного выражения `\b(\w+?)\s\1\b` интерпретируется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6fd26-136">The regular expression pattern `\b(\w+?)\s\1\b` can be interpreted as follows:</span></span>

<span data-ttu-id="6fd26-137">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6fd26-137">Syntax</span></span> | <span data-ttu-id="6fd26-138">Значение</span><span class="sxs-lookup"><span data-stu-id="6fd26-138">Meaning</span></span>
------ | -------
`\b` | <span data-ttu-id="6fd26-139">Начало на границе слова.</span><span class="sxs-lookup"><span data-stu-id="6fd26-139">Start at a word boundary.</span></span>
`(\w+?)` | <span data-ttu-id="6fd26-140">Соответствует одному или нескольким символам слова (как можно меньшему количеству).</span><span class="sxs-lookup"><span data-stu-id="6fd26-140">Match one or more word characters, but as few characters as possible.</span></span> <span data-ttu-id="6fd26-141">Вместе они формируют группу, к которой можно обращаться как к `\1`.</span><span class="sxs-lookup"><span data-stu-id="6fd26-141">Together, they form a group that can be referred to as `\1`.</span></span>
`\s` | <span data-ttu-id="6fd26-142">Соответствует пробелу.</span><span class="sxs-lookup"><span data-stu-id="6fd26-142">Match a white-space character.</span></span>
`\1` | <span data-ttu-id="6fd26-143">Сопоставление подстроки, равной группе с именем `\1`.</span><span class="sxs-lookup"><span data-stu-id="6fd26-143">Match the substring that is equal to the group named `\1`.</span></span>
`\b` | <span data-ttu-id="6fd26-144">Соответствует границе слова.</span><span class="sxs-lookup"><span data-stu-id="6fd26-144">Match a word boundary.</span></span>

<span data-ttu-id="6fd26-145">Метод [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) вызывается с параметрами регулярного выражения [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase).</span><span class="sxs-lookup"><span data-stu-id="6fd26-145">The [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) method is called with regular expression options set to [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase).</span></span> <span data-ttu-id="6fd26-146">Поэтому операция сопоставления учитывает регистр, а пример указывает, что подстрока "This this" является повтором.</span><span class="sxs-lookup"><span data-stu-id="6fd26-146">Therefore, the match operation is case-insensitive, and the example identifies the substring "This this" as a duplication.</span></span>

<span data-ttu-id="6fd26-147">Обратите внимание, что входная строка содержит подстроку "this?</span><span class="sxs-lookup"><span data-stu-id="6fd26-147">Note that the input string includes the substring "this?</span></span> <span data-ttu-id="6fd26-148">This".</span><span class="sxs-lookup"><span data-stu-id="6fd26-148">This".</span></span> <span data-ttu-id="6fd26-149">Но из-за знака пунктуации она не считается повторением.</span><span class="sxs-lookup"><span data-stu-id="6fd26-149">However, because of the intervening punctuation mark, it is not identified as a duplication.</span></span>

### <a name="example-3-dynamically-building-a-culture-sensitive-regular-expression"></a><span data-ttu-id="6fd26-150">Пример 3. Динамическое создание регулярного выражения с учетом языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="6fd26-150">Example 3: Dynamically Building a Culture-Sensitive Regular Expression</span></span>

<span data-ttu-id="6fd26-151">Следующий пример демонстрирует преимущества использования регулярных выражений с гибкими возможностями глобализации .NET.</span><span class="sxs-lookup"><span data-stu-id="6fd26-151">The following example illustrates the power of regular expressions combined with the flexibility offered by .NET's globalization features.</span></span> <span data-ttu-id="6fd26-152">В примере объект [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) применяется для определения формата денежных значений в текущем языке и региональных параметрах системы.</span><span class="sxs-lookup"><span data-stu-id="6fd26-152">It uses the [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object to determine the format of currency values in the system's current culture.</span></span> <span data-ttu-id="6fd26-153">Затем эти данные используются для динамического создания регулярного выражения, которое извлекает денежные значения из текста.</span><span class="sxs-lookup"><span data-stu-id="6fd26-153">It then uses that information to dynamically construct a regular expression that extracts currency values from the text.</span></span> <span data-ttu-id="6fd26-154">Для каждого совпадения извлекается подгруппа, содержащая только числовые строки, которая преобразуется в значение [Decimal](xref:System.Decimal), после чего рассчитывается промежуточный итог.</span><span class="sxs-lookup"><span data-stu-id="6fd26-154">For each match, it extracts the subgroup that contains the numeric string only, converts it to a [Decimal](xref:System.Decimal) value, and calculates a running total.</span></span> 

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

<span data-ttu-id="6fd26-155">На компьютере с региональными параметрами "English - United States (en-US)" пример динамически создает регулярное выражение `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`.</span><span class="sxs-lookup"><span data-stu-id="6fd26-155">On a computer whose current culture is English - United States (en-US), the example dynamically builds the regular expression `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`.</span></span> <span data-ttu-id="6fd26-156">Шаблон регулярного выражения интерпретируется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6fd26-156">This regular expression pattern can be interpreted as follows:</span></span>

<span data-ttu-id="6fd26-157">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6fd26-157">Syntax</span></span> | <span data-ttu-id="6fd26-158">Значение</span><span class="sxs-lookup"><span data-stu-id="6fd26-158">Meaning</span></span>
------ | -------
`\$` | <span data-ttu-id="6fd26-159">Выполняется поиск одного вхождения символа доллара ($) во входной строке.</span><span class="sxs-lookup"><span data-stu-id="6fd26-159">Look for a single occurrence of the dollar symbol ($) in the input string.</span></span> <span data-ttu-id="6fd26-160">Строка шаблона регулярного выражения содержит обратную косую черту, что говорит о том, что символ доллара интерпретируется буквально, а не как привязка регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="6fd26-160">The regular expression pattern string includes a backslash to indicate that the dollar symbol is to be interpreted literally rather than as a regular expression anchor.</span></span> <span data-ttu-id="6fd26-161">(Отдельный символ $ указывает, что механизм регулярных выражений должен начинать сопоставление с конца строки.) Чтобы правильно обработать текущий символ валюты, в примере вызывается метод [Escape](xref:System.Text.RegularExpressions.Regex.Escape(System.String)), который экранирует символ.</span><span class="sxs-lookup"><span data-stu-id="6fd26-161">(The $ symbol alone would indicate that the regular expression engine should try to begin its match at the end of a string.) To ensure that the current culture's currency symbol is not misinterpreted as a regular expression symbol, the example calls the [Escape](xref:System.Text.RegularExpressions.Regex.Escape(System.String)) method to escape the character.</span></span>
`\s*` | <span data-ttu-id="6fd26-162">Поиск нуля или нескольких вхождений пробела.</span><span class="sxs-lookup"><span data-stu-id="6fd26-162">Look for zero or more occurrences of a white-space character.</span></span>
`[-+]?` | <span data-ttu-id="6fd26-163">Поиск нуля или нескольких вхождений знака плюс или минус.</span><span class="sxs-lookup"><span data-stu-id="6fd26-163">Look for zero or one occurrence of either a positive sign or a negative sign.</span></span>
`([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)` | <span data-ttu-id="6fd26-164">Внешние круглые скобки вокруг этого выражения делают его захватываемой группой или частью выражения.</span><span class="sxs-lookup"><span data-stu-id="6fd26-164">The outer parentheses around this expression define it as a capturing group or a subexpression.</span></span> <span data-ttu-id="6fd26-165">Если найдено соответствие, сведения об этой части строки можно получить из второго объекта [Group](xref:System.Text.RegularExpressions.Group) в объекте [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection), который возвращается свойством [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups).</span><span class="sxs-lookup"><span data-stu-id="6fd26-165">If a match is found, information about this part of the matching string can be retrieved from the second [Group](xref:System.Text.RegularExpressions.Group) object in the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) object returned by the [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) property.</span></span> <span data-ttu-id="6fd26-166">(Первый элемент в коллекции представляет все сопоставление.)</span><span class="sxs-lookup"><span data-stu-id="6fd26-166">(The first element in the collection represents the entire match.)</span></span>
`[0-9]{0,3}` | <span data-ttu-id="6fd26-167">Поиск 0-3 вхождений десятичных цифр (0-9).</span><span class="sxs-lookup"><span data-stu-id="6fd26-167">Look for zero to three occurrences of the decimal digits 0 through 9.</span></span>
`(,[0-9]{3})*` | <span data-ttu-id="6fd26-168">Поиск нуля или нескольких вхождений разделителя группы, за которыми следуют три десятичные цифры.</span><span class="sxs-lookup"><span data-stu-id="6fd26-168">Look for zero or more occurrences of a group separator followed by three decimal digits.</span></span>
`\.` | <span data-ttu-id="6fd26-169">Поиск одного вхождения десятичного разделителя.</span><span class="sxs-lookup"><span data-stu-id="6fd26-169">Look for a single occurrence of the decimal separator.</span></span>
`[0-9]+` | <span data-ttu-id="6fd26-170">Поиск одной или нескольких десятичных цифр.</span><span class="sxs-lookup"><span data-stu-id="6fd26-170">Look for one or more decimal digits.</span></span>
`(\.[0-9]+)?` | <span data-ttu-id="6fd26-171">Поиск нуля или одного вхождения десятичного разделителя, за которым следует по крайней мере одна десятичная цифра.</span><span class="sxs-lookup"><span data-stu-id="6fd26-171">Look for zero or one occurrence of the decimal separator followed by at least one decimal digit.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6fd26-172">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6fd26-172">Related Topics</span></span>

<span data-ttu-id="6fd26-173">Заголовок</span><span class="sxs-lookup"><span data-stu-id="6fd26-173">Title</span></span> | <span data-ttu-id="6fd26-174">Описание</span><span class="sxs-lookup"><span data-stu-id="6fd26-174">Description</span></span>
----- | -----------
[<span data-ttu-id="6fd26-175">Элементы языка регулярных выражений — краткий справочник</span><span class="sxs-lookup"><span data-stu-id="6fd26-175">Regular expression language - quick reference</span></span>](quick-ref.md) | <span data-ttu-id="6fd26-176">Сведения о наборе символов, операторов и конструкций, которые можно использовать для определения регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="6fd26-176">Provides information on the set of characters, operators, and constructs that you can use to define regular expressions.</span></span>
[<span data-ttu-id="6fd26-177">Объектная модель регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="6fd26-177">The regular expression object model</span></span>](object-model.md) | <span data-ttu-id="6fd26-178">Сведения об использовании классов регулярных выражений и примеры кода.</span><span class="sxs-lookup"><span data-stu-id="6fd26-178">Provides information and code examples that illustrate how to use the regular expression classes.</span></span>
[<span data-ttu-id="6fd26-179">Подробные сведения о поведении регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="6fd26-179">Details of regular expression behavior</span></span>](regex-behavior.md) | <span data-ttu-id="6fd26-180">Сведения о возможностях и поведении регулярных выражений платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="6fd26-180">Provides information about the capabilities and behavior of .NETregular expressions.</span></span>
[<span data-ttu-id="6fd26-181">Примеры регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="6fd26-181">Regular expression examples</span></span>](regex-examples.md) | <span data-ttu-id="6fd26-182">Примеры кода, демонстрирующие типичное применение регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="6fd26-182">Provides code examples that illustrate typical uses of regular expressions.</span></span>


## <a name="reference"></a><span data-ttu-id="6fd26-183">Ссылка</span><span class="sxs-lookup"><span data-stu-id="6fd26-183">Reference</span></span>

[<span data-ttu-id="6fd26-184">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="6fd26-184">System.Text.RegularExpressions</span></span>](xref:System.Text.RegularExpressions)

[<span data-ttu-id="6fd26-185">System.Text.RegularExpressions.Regex</span><span class="sxs-lookup"><span data-stu-id="6fd26-185">System.Text.RegularExpressions.Regex</span></span>](xref:System.Text.RegularExpressions.Regex)


