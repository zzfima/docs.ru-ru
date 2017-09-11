---
title: "Рекомендации по использованию строк"
description: "Рекомендации по использованию строк"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: b3cefaa4-0a3f-4a96-aba9-1de30fb07c29
ms.translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 3efd30bade564fe1b7dbf93237a9ff40c58c5f1e
ms.contentlocale: ru-ru
ms.lasthandoff: 11/05/2016

---

# <a name="best-practices-for-using-strings"></a><span data-ttu-id="8e653-104">Рекомендации по использованию строк</span><span class="sxs-lookup"><span data-stu-id="8e653-104">Best practices for using strings</span></span>

<span data-ttu-id="8e653-105">Платформа .NET предоставляет расширенную поддержку разработки локализованных и глобализованных приложений и упрощает применение правил текущего или какого-то определенного языка и региональных параметров при выполнении общих операций, таких как сортировка строк и их отображение.</span><span class="sxs-lookup"><span data-stu-id="8e653-105">.NET provides extensive support for developing localized and globalized applications, and makes it easy to apply the conventions of either the current culture or a specific culture when performing common operations such as sorting and displaying strings.</span></span> <span data-ttu-id="8e653-106">Однако сортировка и сравнение строк не всегда выполняется с учетом языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="8e653-106">But sorting or comparing strings is not always a culture-sensitive operation.</span></span> <span data-ttu-id="8e653-107">Например, строки, которые используются внутри приложения, как правило, должны обрабатываться одинаково независимо от выбранного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="8e653-107">For example, strings that are used internally by an application typically should be handled identically across all cultures.</span></span> <span data-ttu-id="8e653-108">Если независимые от языка и региональных параметров строковые данные, такие как теги XML, теги HTML, имена пользователей, пути к файлам и имена системных объектов, интерпретируются как зависимые от языка и региональных параметров, в коде приложения могут возникать незначительные ошибки, может наблюдаться низкая производительность, а в некоторых случаях и проблемы безопасности.</span><span class="sxs-lookup"><span data-stu-id="8e653-108">When culturally independent string data, such as XML tags, HTML tags, user names, file paths, and the names of system objects, are interpreted as if they were culture-sensitive, application code can be subject to subtle bugs, poor performance, and, in some cases, security issues.</span></span>

<span data-ttu-id="8e653-109">В этом разделе рассматриваются методы сортировки, сравнения строк и использования прописных и строчных букв в .NET, представлены рекомендации по выбору подходящего метода обработки строк и дополнительная информация об этих методах.</span><span class="sxs-lookup"><span data-stu-id="8e653-109">This article examines the string sorting, comparison, and casing methods in .NET, presents recommendations for selecting an appropriate string-handling method, and provides additional information about string-handling methods.</span></span> <span data-ttu-id="8e653-110">Кроме того, рассматривается отображение и хранение форматированных данных, например числовых данных или даты и времени.</span><span class="sxs-lookup"><span data-stu-id="8e653-110">It also examines how formatted data, such as numeric data and date and time data, is handled for display and for storage.</span></span> 

<span data-ttu-id="8e653-111">В этом разделе содержатся следующие подразделы:</span><span class="sxs-lookup"><span data-stu-id="8e653-111">This article contains the following sections:</span></span>

* [<span data-ttu-id="8e653-112">Рекомендации по использованию строк</span><span class="sxs-lookup"><span data-stu-id="8e653-112">Recommendations for string usage</span></span>](#recommendations-for-string-usage)

* [<span data-ttu-id="8e653-113">Явное задание сравнений строк</span><span class="sxs-lookup"><span data-stu-id="8e653-113">Specifying string comparisons explicitly</span></span>](#specifying-string-comparisons-explicitly)

* [<span data-ttu-id="8e653-114">Подробные сведения о сравнении строк</span><span class="sxs-lookup"><span data-stu-id="8e653-114">The details of string comparison</span></span>](#the-details-of-string-comparison)

* [<span data-ttu-id="8e653-115">Выбор элемента StringComparison для вызова своего метода</span><span class="sxs-lookup"><span data-stu-id="8e653-115">Choosing a StringComparison member for your method call</span></span>](#choosing-a-stringcomparison-member-for-your-method-call)

* [<span data-ttu-id="8e653-116">Общие методы сравнения строк</span><span class="sxs-lookup"><span data-stu-id="8e653-116">Common string comparison methods</span></span>](#common-string-comparison-methods)

* [<span data-ttu-id="8e653-117">Методы, сравнивающие строки опосредованно</span><span class="sxs-lookup"><span data-stu-id="8e653-117">Methods that perform string comparison indirectly</span></span>](#methods-that-perform-string-comparison-indirectly)

* [<span data-ttu-id="8e653-118">Отображение и сохранение форматированных данных</span><span class="sxs-lookup"><span data-stu-id="8e653-118">Displaying and persisting formatted data</span></span>](#displaying-and-persisting-formatted-data)

## <a name="recommendations-for-string-usage"></a><span data-ttu-id="8e653-119">Рекомендации по использованию строк</span><span class="sxs-lookup"><span data-stu-id="8e653-119">Recommendations for string usage</span></span>

<span data-ttu-id="8e653-120">Если вы выполняете разработку на платформе .NET, следуйте нескольким простым рекомендациям по работе со строками.</span><span class="sxs-lookup"><span data-stu-id="8e653-120">When you develop with .NET, follow these simple recommendations when you use strings:</span></span> 

* <span data-ttu-id="8e653-121">Используйте перегрузки, которые явно задают правила сравнения строк для операций со строками.</span><span class="sxs-lookup"><span data-stu-id="8e653-121">Use overloads that explicitly specify the string comparison rules for string operations.</span></span> <span data-ttu-id="8e653-122">Как правило, это подразумевает вызов перегрузки метода, который имеет параметр типа [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="8e653-122">Typically, this involves calling a method overload that has a parameter of type [StringComparison](xref:System.StringComparison).</span></span>

* <span data-ttu-id="8e653-123">Используйте [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) или [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) для сравнений в качестве безопасной альтернативы по умолчанию для сопоставления строк независимо от языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="8e653-123">Use [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) for comparisons as your safe default for culture-agnostic string matching.</span></span>

* <span data-ttu-id="8e653-124">Используйте сравнения с [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) или [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="8e653-124">Use comparisons with [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) for better performance.</span></span>

* <span data-ttu-id="8e653-125">Используйте строковые операции, основанные на [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture), при отображении выходных данных для пользователя.</span><span class="sxs-lookup"><span data-stu-id="8e653-125">Use string operations that are based on [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) when you display output to the user.</span></span>

* <span data-ttu-id="8e653-126">Используйте нелингвистические значения [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) или [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) вместо строковых операций на основе [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture), если лингвистические аспекты в сравнении не важны (например, выполняется сравнение символов).</span><span class="sxs-lookup"><span data-stu-id="8e653-126">Use the non-linguistic [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) values instead of string operations based on [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) when the comparison is linguistically irrelevant (symbolic, for example).</span></span>

* <span data-ttu-id="8e653-127">Используйте метод [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) вместо [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) при нормализации строк для сравнения.</span><span class="sxs-lookup"><span data-stu-id="8e653-127">Use the [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) method instead of the [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) method when you normalize strings for comparison.</span></span>

* <span data-ttu-id="8e653-128">Используйте перегрузку метода [String](xref:System.String) `Equals` для проверки равенства двух строк.</span><span class="sxs-lookup"><span data-stu-id="8e653-128">Use an overload of the [String](xref:System.String) `Equals` method to test whether two strings are equal.</span></span>

* <span data-ttu-id="8e653-129">Используйте перегрузку методов [String](xref:System.String) `Compare` и [String.CompareTo](xref:System.String.CompareTo(System.String)) для сортировки строк, а не для проверки их равенства.</span><span class="sxs-lookup"><span data-stu-id="8e653-129">Use an overload of the [String](xref:System.String) `Compare` and [String.CompareTo](xref:System.String.CompareTo(System.String)) methods to sort strings, not to check for equality.</span></span>

* <span data-ttu-id="8e653-130">Используйте форматирование с учетом языка и региональных параметров для отображения нестроковых данных, например чисел и дат, в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="8e653-130">Use culture-sensitive formatting to display non-string data, such as numbers and dates, in a user interface.</span></span> <span data-ttu-id="8e653-131">Для сохранения нестроковых данных в строковой форме используйте форматирование инвариантного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="8e653-131">Use formatting with the invariant culture to persist non-string data in string form.</span></span>

<span data-ttu-id="8e653-132">При использовании строк избегайте следующих действий.</span><span class="sxs-lookup"><span data-stu-id="8e653-132">Avoid the following practices when you use strings:</span></span>

* <span data-ttu-id="8e653-133">Не используйте перегрузки, которые не задают правила сравнения строк для операций со строками в явной или неявной форме.</span><span class="sxs-lookup"><span data-stu-id="8e653-133">Do not use overloads that do not explicitly or implicitly specify the string comparison rules for string operations.</span></span> 

* <span data-ttu-id="8e653-134">Не используйте перегрузку метода [String](xref:System.String) `Compare` или [String.CompareTo](xref:System.String.CompareTo(System.String)) и проверяйте возвращаемое значение (ноль), чтобы определить, равны ли строки.</span><span class="sxs-lookup"><span data-stu-id="8e653-134">Do not use an overload of the [String](xref:System.String) `Compare` or [String.CompareTo](xref:System.String.CompareTo(System.String)) methods and test for a return value of zero to determine whether two strings are equal.</span></span>

* <span data-ttu-id="8e653-135">Не используйте форматирование с учетом языка и региональных параметров для сохранения числовых данных или данных даты и времени в виде строки.</span><span class="sxs-lookup"><span data-stu-id="8e653-135">Do not use culture-sensitive formatting to persist numeric data or date and time data in string form.</span></span>

## <a name="specifying-string-comparisons-explicitly"></a><span data-ttu-id="8e653-136">Явное задание сравнений строк</span><span class="sxs-lookup"><span data-stu-id="8e653-136">Specifying string comparisons explicitly</span></span>

<span data-ttu-id="8e653-137">Большинство методов обработки строк в .NET являются перегруженными.</span><span class="sxs-lookup"><span data-stu-id="8e653-137">Most of the string manipulation methods in .NET are overloaded.</span></span> <span data-ttu-id="8e653-138">Как правило, одна или несколько перегрузок принимают настройки по умолчанию, а другие — нет и вместо этого определяют требуемый точный способ сравнения и обработки строк.</span><span class="sxs-lookup"><span data-stu-id="8e653-138">Typically, one or more overloads accept default settings, whereas others accept no defaults and instead define the precise way in which strings are to be compared or manipulated.</span></span> <span data-ttu-id="8e653-139">Большинство методов, не использующих значения по умолчанию, включают параметр типа [StringComparison](xref:System.StringComparison), который представляет собой перечисление, явно задающее правила сравнения строк по языку, региональным параметрам и регистру.</span><span class="sxs-lookup"><span data-stu-id="8e653-139">Most of the methods that do not rely on defaults include a parameter of type [StringComparison](xref:System.StringComparison), which is an enumeration that explicitly specifies rules for string comparison by culture and case.</span></span> <span data-ttu-id="8e653-140">В следующей таблице описаны элементы перечисления [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="8e653-140">The following table describes the [StringComparison](xref:System.StringComparison) enumeration members.</span></span> 

<span data-ttu-id="8e653-141">Элемент StringComparison</span><span class="sxs-lookup"><span data-stu-id="8e653-141">StringComparison member</span></span> | <span data-ttu-id="8e653-142">Описание</span><span class="sxs-lookup"><span data-stu-id="8e653-142">Description</span></span>
----------------------- | -----------
[<span data-ttu-id="8e653-143">StringComparison.CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="8e653-143">StringComparison.CurrentCulture</span></span>](xref:System.StringComparison.CurrentCulture) | <span data-ttu-id="8e653-144">Выполняет сравнение с учетом регистра, используя текущий язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="8e653-144">Performs a case-sensitive comparison using the current culture.</span></span>
[<span data-ttu-id="8e653-145">CurrentCultureIgnoreCase</span><span class="sxs-lookup"><span data-stu-id="8e653-145">CurrentCultureIgnoreCase</span></span>](xref:System.StringComparison.CurrentCultureIgnoreCase) | <span data-ttu-id="8e653-146">Выполняет сравнение без учета регистра, используя текущий язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="8e653-146">Performs a case-insensitive comparison using the current culture.</span></span>
[<span data-ttu-id="8e653-147">StringComparison.Ordinal</span><span class="sxs-lookup"><span data-stu-id="8e653-147">StringComparison.Ordinal</span></span>](xref:System.StringComparison.Ordinal) | <span data-ttu-id="8e653-148">Выполняет порядковое сравнение.</span><span class="sxs-lookup"><span data-stu-id="8e653-148">Performs an ordinal comparison.</span></span>
[<span data-ttu-id="8e653-149">StringComparison.OrdinalIgnoreCase</span><span class="sxs-lookup"><span data-stu-id="8e653-149">StringComparison.OrdinalIgnoreCase</span></span>](xref:System.StringComparison.OrdinalIgnoreCase) | <span data-ttu-id="8e653-150">Выполняет порядковое сравнение без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="8e653-150">Performs a case-insensitive ordinal comparison.</span></span>

<span data-ttu-id="8e653-151">Например, метод [String](xref:System.String) `IndexOf`, который возвращает индекс подстроки в объект [String](xref:System.String), соответствующий символу или строке, имеет девять перегрузок:</span><span class="sxs-lookup"><span data-stu-id="8e653-151">For example, the [String](xref:System.String) `IndexOf` method, which returns the index of a substring in a [String](xref:System.String) object that matches either a character or a string, has nine overloads:</span></span>

* <span data-ttu-id="8e653-152">[IndexOf(Char)](xref:System.String.IndexOf(System.Char)), [IndexOf(Char, Int32)](xref:System.String.IndexOf(System.Char,System.Int32)) и [IndexOf(Char, Int32, Int32)](xref:System.String.IndexOf(System.Char,System.Int32,System.Int32)), которые по умолчанию выполняют порядковый поиск символа в строке (с учетом регистра и без учета языка и региональных параметров).</span><span class="sxs-lookup"><span data-stu-id="8e653-152">[IndexOf(Char)](xref:System.String.IndexOf(System.Char)), [IndexOf(Char, Int32)](xref:System.String.IndexOf(System.Char,System.Int32)), and [IndexOf(Char, Int32, Int32)](xref:System.String.IndexOf(System.Char,System.Int32,System.Int32)), which by default perform an ordinal (case-sensitive and culture-insensitive) search for a character in the string.</span></span>

* <span data-ttu-id="8e653-153">[IndexOf(String)](xref:System.String.IndexOf(System.String)), [IndexOf(String, Int32)](xref:System.String.IndexOf(System.String,System.Int32)) и [IndexOf(String, Int32, Int32)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32)), которые по умолчанию выполняют порядковый поиск символа в строке (с учетом регистра и без учета языка и региональных параметров).</span><span class="sxs-lookup"><span data-stu-id="8e653-153">[IndexOf(String)](xref:System.String.IndexOf(System.String)), [IndexOf(String, Int32)](xref:System.String.IndexOf(System.String,System.Int32)), and [IndexOf(String, Int32, Int32)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32)), which by default perform a case-sensitive and culture-sensitive search for a substring in the string.</span></span>

* <span data-ttu-id="8e653-154">[IndexOf(String, StringComparison)](xref:System.String.IndexOf(System.String,System.StringComparison)), [IndexOf(String, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.StringComparison)) и [IndexOf(String, Int32, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32,System.StringComparison)), которые включают параметр типа StringComparison, что позволяет задать форму сравнения.</span><span class="sxs-lookup"><span data-stu-id="8e653-154">[IndexOf(String, StringComparison)](xref:System.String.IndexOf(System.String,System.StringComparison)), [IndexOf(String, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.StringComparison)), and [IndexOf(String, Int32, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32,System.StringComparison)), which include a parameter of type StringComparison that allows the form of the comparison to be specified.</span></span>

<span data-ttu-id="8e653-155">Рекомендуется выбрать перегрузку, не использующую значения по умолчанию, по следующим причинам.</span><span class="sxs-lookup"><span data-stu-id="8e653-155">We recommend that you select an overload that does not use default values, for the following reasons:</span></span>

* <span data-ttu-id="8e653-156">Некоторые перегрузки с параметрами по умолчанию (те, которые выполняют поиск [Char](xref:System.Char) в экземпляре строки) выполняют порядковое сравнение, в то время как другие (выполняющие поиск строки в экземпляре строки) учитывают язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="8e653-156">Some overloads with default parameters (those that search for a [Char](xref:System.Char) in the string instance) perform an ordinal comparison, whereas others (those that search for a string in the string instance) are culture-sensitive.</span></span> <span data-ttu-id="8e653-157">Сложно запомнить, какое значение по умолчанию использует тот или иной метод, перегрузки легко перепутать.</span><span class="sxs-lookup"><span data-stu-id="8e653-157">It is difficult to remember which method uses which default value, and easy to confuse the overloads.</span></span>

* <span data-ttu-id="8e653-158">Назначение кода, вызовы методов в котором зависят от значений по умолчанию, не ясно.</span><span class="sxs-lookup"><span data-stu-id="8e653-158">The intent of the code that relies on default values for method calls is not clear.</span></span> <span data-ttu-id="8e653-159">В следующем примере, где используются значения по умолчанию, сложно определить, действительно ли разработчик намеревался выполнить порядковое или лингвистическое сравнение двух строк или различие регистра между `protocol` и http могло привести к тому, что проверка на равенство возвратит значение `false`.</span><span class="sxs-lookup"><span data-stu-id="8e653-159">In the following example, which relies on defaults, it is difficult to know whether the developer actually intended an ordinal or a linguistic comparison of two strings, or whether a case difference between `protocol` and "http" might cause the test for equality to return `false`.</span></span>

  ```csharp
  string protocol = GetProtocol(url);       
  if (String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase)) {
     // ...Code to handle HTTP protocol.
  }
  else {
     throw new InvalidOperationException();
  }
  ```

  ```vb
  Dim protocol As String = GetProtocol(url)       
  If String.Equals(protocol, "http") Then
    ' ...Code to handle HTTP protocol.
  Else
     Throw New InvalidOperationException()
  End If
  ```

<span data-ttu-id="8e653-160">В общем случае рекомендуется вызывать метод, который не зависит от значений по умолчанию, поскольку это делает назначение кода однозначным.</span><span class="sxs-lookup"><span data-stu-id="8e653-160">In general, we recommend that you call a method that does not rely on defaults, because it makes the intent of the code unambiguous.</span></span> <span data-ttu-id="8e653-161">Это, в свою очередь, делает код более читаемым и упрощает отладку и обслуживание.</span><span class="sxs-lookup"><span data-stu-id="8e653-161">This, in turn, makes the code more readable and easier to debug and maintain.</span></span> <span data-ttu-id="8e653-162">В следующем примере рассматриваются вопросы, возникшие в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="8e653-162">The following example addresses the questions raised about the previous example.</span></span> <span data-ttu-id="8e653-163">Он явно демонстрирует, что используется порядковое сравнение и что различия регистра игнорируются.</span><span class="sxs-lookup"><span data-stu-id="8e653-163">It makes it clear that ordinal comparison is used and that differences in case are ignored.</span></span> 

```csharp
string protocol = GetProtocol(url);       
if (String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase)) {
   // ...Code to handle HTTP protocol.
}
else {
   throw new InvalidOperationException();
}
```

```vb
Dim protocol As String = GetProtocol(url)       
If String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase) Then
   ' ...Code to handle HTTP protocol.
Else
   Throw New InvalidOperationException()
End If
```

## <a name="the-details-of-string-comparison"></a><span data-ttu-id="8e653-164">Подробные сведения о сравнении строк</span><span class="sxs-lookup"><span data-stu-id="8e653-164">The details of string comparison</span></span>

<span data-ttu-id="8e653-165">Сравнение строк является основой многих связанных со строками операций, в частности сортировки и проверки на равенство.</span><span class="sxs-lookup"><span data-stu-id="8e653-165">String comparison is the heart of many string-related operations, particularly sorting and testing for equality.</span></span> <span data-ttu-id="8e653-166">Строки сортируются в определенном порядке: если my отображается до string в сортированном списке строк, текст my должен быть меньше или равен тексту string.</span><span class="sxs-lookup"><span data-stu-id="8e653-166">Strings sort in a determined order: If "my" appears before "string" in a sorted list of strings, "my" must compare less than or equal to "string".</span></span> <span data-ttu-id="8e653-167">Кроме того, неявное сравнение определяет равенство.</span><span class="sxs-lookup"><span data-stu-id="8e653-167">Additionally, comparison implicitly defines equality.</span></span> <span data-ttu-id="8e653-168">Операция сравнения возвращает 0 для строк, которые она считает равными.</span><span class="sxs-lookup"><span data-stu-id="8e653-168">The comparison operation returns zero for strings it deems equal.</span></span> <span data-ttu-id="8e653-169">Правильно интерпретировать это следующим образом: ни одна из строк не меньше другой.</span><span class="sxs-lookup"><span data-stu-id="8e653-169">A good interpretation is that neither string is less than the other.</span></span> <span data-ttu-id="8e653-170">Наиболее значимые операции со строками включают обе следующие процедуры или хотя бы одну из них: сравнение с другой строкой и выполнение правильно определенной операции сортировки.</span><span class="sxs-lookup"><span data-stu-id="8e653-170">Most meaningful operations involving strings include one or both of these procedures: comparing with another string, and executing a well-defined sort operation.</span></span>

<span data-ttu-id="8e653-171">Однако оценка двух строк на равенство или порядок сортировки не дает единственно верного результата; результат также зависит от критериев, используемых для сравнения строк.</span><span class="sxs-lookup"><span data-stu-id="8e653-171">However, evaluating two strings for equality or sort order does not yield a single, correct result; the outcome depends on the criteria used to compare the strings.</span></span> <span data-ttu-id="8e653-172">В частности, операции сравнения строк, которые являются порядковыми или основаны на правилах учета регистра или сортировки текущего языка и региональных параметров или инвариантного языка и региональных параметров (независимые от языкового стандарта региональные параметры на основе английского языка), могут давать разные результаты.</span><span class="sxs-lookup"><span data-stu-id="8e653-172">In particular, string comparisons that are ordinal or that are based on the casing and sorting conventions of the current culture or the invariant culture (a locale-agnostic culture based on the English language) may produce different results.</span></span>

### <a name="string-comparisons-that-use-the-current-culture"></a><span data-ttu-id="8e653-173">Сравнение строк с использованием текущего языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="8e653-173">String comparisons that use the current culture</span></span>

<span data-ttu-id="8e653-174">Одним из критериев является использование правил текущего языка и региональных параметров при сравнении строк.</span><span class="sxs-lookup"><span data-stu-id="8e653-174">One criterion involves using the conventions of the current culture when comparing strings.</span></span> <span data-ttu-id="8e653-175">В сравнениях, основанных на текущем языке и региональных параметрах, используется текущий язык, региональные параметры или языковой стандарт потока.</span><span class="sxs-lookup"><span data-stu-id="8e653-175">Comparisons that are based on the current culture use the thread's current culture or locale.</span></span> <span data-ttu-id="8e653-176">Следует всегда использовать сравнения на основе текущего языка и региональных параметров, если речь идет о лингвистически релевантных данных и данных, отражающих взаимодействие с пользователем, где важны язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="8e653-176">You should always use comparisons that are based on the current culture when data is linguistically relevant, and when it reflects culture-sensitive user interaction.</span></span> 

<span data-ttu-id="8e653-177">Однако поведение сравнения и использования регистра в .NET меняется при изменении языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="8e653-177">However, comparison and casing behavior in .NET changes when the culture changes.</span></span> <span data-ttu-id="8e653-178">Это происходит, если приложение выполняется на компьютере с другим языком и региональными параметрами, нежели на компьютере, где приложение было разработано, либо если выполняющий поток меняет свой язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="8e653-178">This happens when an application executes on a computer that has a different culture than the computer on which the application was developed, or when the executing thread changes its culture.</span></span> <span data-ttu-id="8e653-179">Это поведение является преднамеренным, однако до сих пор остается неочевидным для многих разработчиков.</span><span class="sxs-lookup"><span data-stu-id="8e653-179">This behavior is intentional, but it remains non-obvious to many developers.</span></span> <span data-ttu-id="8e653-180">В следующем примере показаны различия в порядке сортировки в американском английском (en-US) и шведском языке (sv-SE).</span><span class="sxs-lookup"><span data-stu-id="8e653-180">The following example illustrates differences in sort order between the U.S. English ("en-US") and Swedish ("sv-SE") cultures.</span></span> <span data-ttu-id="8e653-181">Обратите внимание, что слова ångström, Windows и Visual Studio показаны в разных местах массива сортированных строк.</span><span class="sxs-lookup"><span data-stu-id="8e653-181">Note that the words "ångström", "Windows", and "Visual Studio" appear in different positions in the sorted string arrays.</span></span>

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] values= { "able", "ångström", "apple", "Æble", 
                         "Windows", "Visual Studio" };
      Array.Sort(values);
      DisplayArray(values);

      // Change culture to Swedish (Sweden).
      string originalCulture = CultureInfo.CurrentCulture.Name;
      Thread.CurrentThread.CurrentCulture = new CultureInfo("sv-SE");
      Array.Sort(values);
      DisplayArray(values);

      // Restore the original culture.
      Thread.CurrentThread.CurrentCulture = new CultureInfo(originalCulture);
    }

    private static void DisplayArray(string[] values)
    {
      Console.WriteLine("Sorting using the {0} culture:",  
                        CultureInfo.CurrentCulture.Name);
      foreach (string value in values)
         Console.WriteLine("   {0}", value);

      Console.WriteLine();
    }
}
// The example displays the following output:
//       Sorting using the en-US culture:
//          able
//          Æble
//          ångström
//          apple
//          Visual Studio
//          Windows
//       
//       Sorting using the sv-SE culture:
//          able
//          Æble
//          apple
//          Windows
//          Visual Studio
//          ångström
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim values() As String = { "able", "ångström", "apple", _
                                 "Æble", "Windows", "Visual Studio" }
      Array.Sort(values)
      DisplayArray(values)

      ' Change culture to Swedish (Sweden).
      Dim originalCulture As String = CultureInfo.CurrentCulture.Name
      Thread.CurrentThread.CurrentCulture = New CultureInfo("sv-SE")
      Array.Sort(values)
      DisplayArray(values)

      ' Restore the original culture.
      Thread.CurrentThread.CurrentCulture = New CultureInfo(originalCulture)
    End Sub

    Private Sub DisplayArray(values() As String)
      Console.WRiteLine("Sorting using the {0} culture:", _ 
                        CultureInfo.CurrentCulture.Name)
      For Each value As String In values
         Console.WriteLine("   {0}", value)
      Next
      Console.WriteLine()   
    End Sub
End Module
' The example displays the following output:
'       Sorting using the en-US culture:
'          able
'          Æble
'          ångström
'          apple
'          Visual Studio
'          Windows
'       
'       Sorting using the sv-SE culture:
'          able
'          Æble
'          apple
'          Windows
'          Visual Studio
'          ångström
```

<span data-ttu-id="8e653-182">Сравнения без учета регистра, где используются текущий язык и региональные параметры, выполняются так же, как сравнения с учетом языка и региональных параметров с той разницей, что регистр игнорируется в соответствии с правилами текущего языка и региональных параметров потока.</span><span class="sxs-lookup"><span data-stu-id="8e653-182">Case-insensitive comparisons that use the current culture are the same as culture-sensitive comparisons, except that they ignore case as dictated by the thread's current culture.</span></span> <span data-ttu-id="8e653-183">Это поведение может также проявляться в порядке сортировки.</span><span class="sxs-lookup"><span data-stu-id="8e653-183">This behavior may manifest itself in sort orders as well.</span></span> 

<span data-ttu-id="8e653-184">Сравнения, использующие семантику текущего языка и региональных параметров, используются по умолчанию для следующих методов.</span><span class="sxs-lookup"><span data-stu-id="8e653-184">Comparisons that use current culture semantics are the default for the following methods:</span></span>

* <span data-ttu-id="8e653-185">Перегрузки [String](xref:System.String) `Compare`, не включающие параметр [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="8e653-185">[String](xref:System.String) `Compare` overloads that do not include a [StringComparison](xref:System.StringComparison) parameter.</span></span>

* <span data-ttu-id="8e653-186">Перегрузки [String.CompareTo](xref:System.String.CompareTo(System.String)).</span><span class="sxs-lookup"><span data-stu-id="8e653-186">[String.CompareTo](xref:System.String.CompareTo(System.String)) overloads.</span></span>

* <span data-ttu-id="8e653-187">Метод по умолчанию [String.StartsWith(String)](xref:System.String.StartsWith(System.String)).</span><span class="sxs-lookup"><span data-stu-id="8e653-187">The default [String.StartsWith(String)](xref:System.String.StartsWith(System.String)) method.</span></span> 

* <span data-ttu-id="8e653-188">Метод по умолчанию [String.EndsWith(String)](xref:System.String.EndsWith(System.String)).</span><span class="sxs-lookup"><span data-stu-id="8e653-188">The default [String.EndsWith(String)](xref:System.String.EndsWith(System.String)) method.</span></span>

* <span data-ttu-id="8e653-189">Перегрузки [String](xref:System.String) `IndexOf`, принимающие в качестве параметра поиска [String](xref:System.String) и не имеющие параметра [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="8e653-189">[String](xref:System.String) `IndexOf` overloads that accept a [String](xref:System.String) as a search parameter and that do not have a [StringComparison](xref:System.StringComparison) parameter.</span></span>

* <span data-ttu-id="8e653-190">Перегрузки [String](xref:System.String) `LastIndexOf`, принимающие в качестве параметра поиска [String](xref:System.String) и не имеющие параметра [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="8e653-190">[String](xref:System.String) `LastIndexOf` overloads that accept a [String](xref:System.String) as a search parameter and that do not have a [StringComparison](xref:System.StringComparison) parameter.</span></span>

<span data-ttu-id="8e653-191">В любом случае рекомендуется вызвать перегрузку, имеющую параметр [StringComparison](xref:System.StringComparison), чтобы сделать назначение вызова метода очевидным.</span><span class="sxs-lookup"><span data-stu-id="8e653-191">In any case, we recommend that you call an overload that has a [StringComparison](xref:System.StringComparison) parameter to make the intent of the method call clear.</span></span> 

<span data-ttu-id="8e653-192">При лингвистической интерпретации нелингвистических строковых данных, а также если строковые данные определенного языка и региональных параметров интерпретируются с использованием правил другого языка, могут возникать малозаметные и не столь малозаметные ошибки.</span><span class="sxs-lookup"><span data-stu-id="8e653-192">Subtle and not so subtle bugs can emerge when non-linguistic string data is interpreted linguistically, or when string data from a particular culture is interpreted using the conventions of another culture.</span></span> <span data-ttu-id="8e653-193">Типичный пример — проблема турецкого I.</span><span class="sxs-lookup"><span data-stu-id="8e653-193">The canonical example is the Turkish-I problem.</span></span>

<span data-ttu-id="8e653-194">Почти во всех латинских алфавитах, включая американский английский, символ i (\u0069) является строчной версией символа I (\u0049).</span><span class="sxs-lookup"><span data-stu-id="8e653-194">For nearly all Latin alphabets, including U.S. English, the character "i" (\u0069) is the lowercase version of the character "I" (\u0049).</span></span> <span data-ttu-id="8e653-195">Это правило учета регистра быстро становится значением по умолчанию для тех, кто программирует для этих языков.</span><span class="sxs-lookup"><span data-stu-id="8e653-195">This casing rule quickly becomes the default for someone programming in such a culture.</span></span> <span data-ttu-id="8e653-196">Однако в турецком алфавите (tr-TR) используется I с точкой — İ (\u0130), которая является прописной версией i.</span><span class="sxs-lookup"><span data-stu-id="8e653-196">However, the Turkish ("tr-TR") alphabet includes an "I with a dot" character "İ" (\u0130), which is the capital version of "i".</span></span> <span data-ttu-id="8e653-197">В турецком языке также есть строчная i без точки, ı (\u0131), прописной для которой является I.</span><span class="sxs-lookup"><span data-stu-id="8e653-197">Turkish also includes a lowercase "i without a dot" character, "ı" (\u0131), which capitalizes to "I".</span></span> <span data-ttu-id="8e653-198">Эта же особенность имеется и в азербайджанском языке ("az").</span><span class="sxs-lookup"><span data-stu-id="8e653-198">This behavior occurs in the Azerbaijani ("az") culture as well.</span></span>

<span data-ttu-id="8e653-199">Таким образом, допущения о прописной версии буквы i или строчной версии буквы I не являются правильными для всех языков.</span><span class="sxs-lookup"><span data-stu-id="8e653-199">Therefore, assumptions made about capitalizing "i" or lowercasing "I" are not valid among all cultures.</span></span> <span data-ttu-id="8e653-200">При использовании перегрузок по умолчанию для сравнения строк они будут меняться в зависимости от языков и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="8e653-200">If you use the default overloads for string comparison routines, they will be subject to variance between cultures.</span></span> <span data-ttu-id="8e653-201">Если сравниваются нелингвистические данные, при использовании перегрузок по умолчанию может быть получен нежелательный результат, как показывает следующий пример с попыткой сравнить строки file и FILE без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="8e653-201">If the data to be compared is non-linguistic, using the default overloads can produce undesirable results, as the following attempt to perform a case-insensitive comparison of the strings "file" and "FILE" illustrates.</span></span>

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string fileUrl = "file";
      Thread.CurrentThread.CurrentCulture = new CultureInfo("en-US");
      Console.WriteLine("Culture = {0}",
                        Thread.CurrentThread.CurrentCulture.DisplayName);
      Console.WriteLine("(file == FILE) = {0}", 
                       fileUrl.StartsWith("FILE", true, null));
      Console.WriteLine();

      Thread.CurrentThread.CurrentCulture = new CultureInfo("tr-TR");
      Console.WriteLine("Culture = {0}",
                        Thread.CurrentThread.CurrentCulture.DisplayName);
      Console.WriteLine("(file == FILE) = {0}", 
                        fileUrl.StartsWith("FILE", true, null));
   }
}
// The example displays the following output:
//       Culture = English (United States)
//       (file == FILE) = True
//       
//       Culture = Turkish (Turkey)
//       (file == FILE) = False
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim fileUrl = "file"
      Thread.CurrentThread.CurrentCulture = New CultureInfo("en-US")
      Console.WriteLine("Culture = {0}", _
                        Thread.CurrentThread.CurrentCulture.DisplayName)
      Console.WriteLine("(file == FILE) = {0}", _ 
                       fileUrl.StartsWith("FILE", True, Nothing))
      Console.WriteLine()

      Thread.CurrentThread.CurrentCulture = New CultureInfo("tr-TR")
      Console.WriteLine("Culture = {0}", _
                        Thread.CurrentThread.CurrentCulture.DisplayName)
      Console.WriteLine("(file == FILE) = {0}", _ 
                        fileUrl.StartsWith("FILE", True, Nothing))
   End Sub
End Module
' The example displays the following output:
'       Culture = English (United States)
'       (file == FILE) = True
'       
'       Culture = Turkish (Turkey)
'       (file == FILE) = False
```

<span data-ttu-id="8e653-202">Это сравнение может вызвать значительные проблемы, если язык и региональные параметры случайно использовались в конфиденциальных параметрах, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8e653-202">This comparison could cause significant problems if the culture is inadvertently used in security-sensitive settings, as in the following example.</span></span> <span data-ttu-id="8e653-203">Вызов метода, например `IsFileURI("file:")`, возвращает значение `true`, если текущий язык — американский английский, и значение `false`, если текущий язык — турецкий.</span><span class="sxs-lookup"><span data-stu-id="8e653-203">A method call such as `IsFileURI("file:")` returns `true` if the current culture is U.S. English, but `false` if the current culture is Turkish.</span></span> <span data-ttu-id="8e653-204">Следовательно, в системах на турецком языке кто-то может попытаться обойти механизмы безопасности, блокирующие доступ к URI без учета регистра, которые начинаются с текста «FILE:».</span><span class="sxs-lookup"><span data-stu-id="8e653-204">Thus, on Turkish systems, someone could circumvent security measures that block access to case-insensitive URIs that begin with "FILE:".</span></span>

```csharp
public static bool IsFileURI(String path) 
{
   return path.StartsWith("FILE:", true, null);
}
```

```vb
Public Shared Function IsFileURI(path As String) As Boolean 
   Return path.StartsWith("FILE:", True, Nothing)
End Function
```

<span data-ttu-id="8e653-205">В этом случае, поскольку «file:» должен интерпретироваться как нелингвистический идентификатор без учета языка и региональных параметров, нужно писать код, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8e653-205">In this case, because "file:" is meant to be interpreted as a non-linguistic, culture-insensitive identifier, the code should instead be written as shown in the following example.</span></span>

```csharp
public static bool IsFileURI(string path) 
{
   return path.StartsWith("FILE:", StringComparison.OrdinalIgnoreCase);
}
```

```vb
Public Shared Function IsFileURI(path As String) As Boolean 
    Return path.StartsWith("FILE:", StringComparison.OrdinalIgnoreCase)
End Function
```

## <a name="ordinal-string-operations"></a><span data-ttu-id="8e653-206">Порядковые операции со строками</span><span class="sxs-lookup"><span data-stu-id="8e653-206">Ordinal String Operations</span></span>

<span data-ttu-id="8e653-207">Указание значения [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) или [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) в вызове метода является признаком нелингвистического сравнения, в котором признаки естественного языка игнорируются.</span><span class="sxs-lookup"><span data-stu-id="8e653-207">Specifying the [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) value in a method call signifies a non-linguistic comparison in which the features of natural languages are ignored.</span></span> <span data-ttu-id="8e653-208">Методы, которые вызываются с этими значениями [StringComparison](xref:System.StringComparison), принимают решения о строковых операциях на основе простых байтовых сравнений, а не таблиц регистров или эквивалентности, которые параметризуются языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="8e653-208">Methods that are invoked with these [StringComparison](xref:System.StringComparison) values base string operation decisions on simple byte comparisons instead of casing or equivalence tables that are parameterized by culture.</span></span> <span data-ttu-id="8e653-209">В большинстве случаев такой подход наиболее соответствует предполагаемой интерпретации строк, ускоряя выполнение кода и делая его более надежным.</span><span class="sxs-lookup"><span data-stu-id="8e653-209">In most cases, this approach best fits the intended interpretation of strings while making code faster and more reliable.</span></span> 

<span data-ttu-id="8e653-210">Порядковые сравнения — это сравнения строк, в которых каждый байт каждой строки сравнивается без лингвистической интерпретации; например, windows не равно Windows.</span><span class="sxs-lookup"><span data-stu-id="8e653-210">Ordinal comparisons are string comparisons in which each byte of each string is compared without linguistic interpretation; for example, "windows" does not match "Windows".</span></span> <span data-ttu-id="8e653-211">Используйте такое сравнение, когда контекст определяет, что строки должны точно совпадать, или требует использования консервативной политики соответствия.</span><span class="sxs-lookup"><span data-stu-id="8e653-211">Use this comparison when the context dictates that strings should be matched exactly or demands conservative matching policy.</span></span> <span data-ttu-id="8e653-212">Кроме того, порядковое сравнение — это самая быстрая операция сравнения, потому что при расчете результата не применяются лингвистические правила.</span><span class="sxs-lookup"><span data-stu-id="8e653-212">Additionally, ordinal comparison is the fastest comparison operation because it applies no linguistic rules when determining a result.</span></span>

<span data-ttu-id="8e653-213">Строки в .NET могут содержать внедренные символы NULL.</span><span class="sxs-lookup"><span data-stu-id="8e653-213">Strings in .NET can contain embedded null characters.</span></span> <span data-ttu-id="8e653-214">Одним из очевидных различий между порядковым сравнением и сравнением с учетом языка и региональных параметров (включая сравнения, в которых используется инвариантный язык и региональные параметры) является различие в обработке внедренных символов null в строке.</span><span class="sxs-lookup"><span data-stu-id="8e653-214">One of the clearest differences between ordinal and culture-sensitive comparison (including comparisons that use the invariant culture) concerns the handling of embedded null characters in a string.</span></span> <span data-ttu-id="8e653-215">Эти символы игнорируются при использовании методов [String](xref:System.String) `Compare` и [String](xref:System.String) `Equals` для сравнений с учетом языка и региональных параметров (включая сравнения, использующие инвариантный язык).</span><span class="sxs-lookup"><span data-stu-id="8e653-215">These characters are ignored when you use the [String](xref:System.String) `Compare` and [String](xref:System.String) `Equals` methods to perform culture-sensitive comparisons (including comparisons that use the invariant culture).</span></span> <span data-ttu-id="8e653-216">В результате в сравнениях с учетом языка и региональных параметров строки, содержащие внедренные символы null, считаются равными строкам, которые таких символов не содержат.</span><span class="sxs-lookup"><span data-stu-id="8e653-216">As a result, in culture-sensitive comparisons, strings that contain embedded null characters can be considered equal to strings that do not.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="8e653-217">Несмотря на то, что в методах сравнения строк не учитываются внедренные символы NULL, методы поиска строк, такие как [String.Contains](xref:System.String.Contains(System.String)), [String.EndsWith](xref:System.String.EndsWith(System.String)), [String.IndexOf](xref:System.String.IndexOf(System.Char)), [String.LastIndexOf](xref:System.String.LastIndexOf(System.String)) и [String.StartsWith](xref:System.String.StartsWith(System.String)), эти символы учитывают.</span><span class="sxs-lookup"><span data-stu-id="8e653-217">Although string comparison methods disregard embedded null characters, string search methods such as [String.Contains](xref:System.String.Contains(System.String)), [String.EndsWith](xref:System.String.EndsWith(System.String)), [String.IndexOf](xref:System.String.IndexOf(System.Char)), [String.LastIndexOf](xref:System.String.LastIndexOf(System.String)), and [String.StartsWith](xref:System.String.StartsWith(System.String)) do not.</span></span> 

<span data-ttu-id="8e653-218">В следующем примере выполняется сравнение с учетом языка и региональных параметров строки Aa с аналогичной строкой, содержащей несколько внедренных символов null между А и а, и показано, почему две строки рассматриваются как равные.</span><span class="sxs-lookup"><span data-stu-id="8e653-218">The following example performs a culture-sensitive comparison of the string "Aa" with a similar string that contains several embedded null characters between "A" and "a", and shows how the two strings are considered equal.</span></span> 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string str1 = "Aa";
      string str2 = "A" + new String('\u0000', 3) + "a";
      Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", 
                        str1, ShowBytes(str1), str2, ShowBytes(str2));
      Console.WriteLine("   With String.Compare:");
      Console.WriteLine("      Current Culture: {0}", 
                        String.Compare(str1, str2, StringComparison.CurrentCulture));
      Console.WriteLine("      Invariant Culture: {0}", 
                        String.Compare(str1, str2, StringComparison.InvariantCulture));

      Console.WriteLine("   With String.Equals:");
      Console.WriteLine("      Current Culture: {0}", 
                        String.Equals(str1, str2, StringComparison.CurrentCulture));
      Console.WriteLine("      Invariant Culture: {0}", 
                        String.Equals(str1, str2, StringComparison.InvariantCulture));
   }

   private static string ShowBytes(string str)
   {
      string hexString = String.Empty;
      for (int ctr = 0; ctr < str.Length; ctr++)
      {
         string result = String.Empty;
         result = Convert.ToInt32(str[ctr]).ToString("X4");
         result = " " + result.Substring(0,2) + " " + result.Substring(2, 2);
         hexString += result;
      }
      return hexString.Trim();
   }
}
// The example displays the following output:
//    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
//       With String.Compare:
//          Current Culture: 0
//          Invariant Culture: 0
//       With String.Equals:
//          Current Culture: True
//          Invariant Culture: True
```

```vb
Module Example
   Public Sub Main()
      Dim str1 As String = "Aa"
      Dim str2 As String = "A" + New String(Convert.ToChar(0), 3) + "a"
      Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", _
                        str1, ShowBytes(str1), str2, ShowBytes(str2))
      Console.WriteLine("   With String.Compare:")
      Console.WriteLine("      Current Culture: {0}", _
                        String.Compare(str1, str2, StringComparison.CurrentCulture))
      Console.WriteLine("      Invariant Culture: {0}", _
                        String.Compare(str1, str2, StringComparison.InvariantCulture))

      Console.WriteLine("   With String.Equals:")
      Console.WriteLine("      Current Culture: {0}", _
                        String.Equals(str1, str2, StringComparison.CurrentCulture))
      Console.WriteLine("      Invariant Culture: {0}", _
                        String.Equals(str1, str2, StringComparison.InvariantCulture))
   End Sub

   Private Function ShowBytes(str As String) As String
      Dim hexString As String = String.Empty
      For ctr As Integer = 0 To str.Length - 1
         Dim result As String = String.Empty
         result = Convert.ToInt32(str.Chars(ctr)).ToString("X4")
         result = " " + result.Substring(0,2) + " " + result.Substring(2, 2)
         hexString += result
      Next
      Return hexString.Trim()
   End Function
End Module
```

<span data-ttu-id="8e653-219">Однако строки не считаются равными, если выполняется порядковое сравнение, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8e653-219">However, the strings are not considered equal when you use ordinal comparison, as the following example shows.</span></span>

```csharp
Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", 
                  str1, ShowBytes(str1), str2, ShowBytes(str2));
Console.WriteLine("   With String.Compare:");
Console.WriteLine("      Ordinal: {0}", 
                  String.Compare(str1, str2, StringComparison.Ordinal));

Console.WriteLine("   With String.Equals:");
Console.WriteLine("      Ordinal: {0}", 
                  String.Equals(str1, str2, StringComparison.Ordinal));
// The example displays the following output:
//    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
//       With String.Compare:
//          Ordinal: 97
//       With String.Equals:
//          Ordinal: False
```

```vb
Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", _
                  str1, ShowBytes(str1), str2, ShowBytes(str2))
Console.WriteLine("   With String.Compare:")
Console.WriteLine("      Ordinal: {0}", _
                  String.Compare(str1, str2, StringComparison.Ordinal))

Console.WriteLine("   With String.Equals:")
Console.WriteLine("      Ordinal: {0}", _
                  String.Equals(str1, str2, StringComparison.Ordinal))
' The example displays the following output:
'    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
'       With String.Compare:
'          Ordinal: 97
'       With String.Equals:
'          Ordinal: False
```

<span data-ttu-id="8e653-220">Порядковые сравнения без учета регистра — это следующий наиболее консервативной подход к решению задачи.</span><span class="sxs-lookup"><span data-stu-id="8e653-220">Case-insensitive ordinal comparisons are the next most conservative approach.</span></span> <span data-ttu-id="8e653-221">В этих сравнениях почти всегда игнорируется регистр. Так, windows совпадает с Windows.</span><span class="sxs-lookup"><span data-stu-id="8e653-221">These comparisons ignore most casing; for example, "windows" matches "Windows".</span></span> <span data-ttu-id="8e653-222">При работе с символами ASCII эта политика эквивалентна сравнению [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) за исключением того, что стандартные правила регистра ASCII игнорируются.</span><span class="sxs-lookup"><span data-stu-id="8e653-222">When dealing with ASCII characters, this policy is equivalent to [StringComparison.Ordinal](xref:System.StringComparison.Ordinal), except that it ignores the usual ASCII casing.</span></span> <span data-ttu-id="8e653-223">Следовательно, любой символ в последовательности [A, Z] (\u0041–\u005A) соответствует соответствующему символу в последовательности [a, z] (\u0061–\007A).</span><span class="sxs-lookup"><span data-stu-id="8e653-223">Therefore, any character in [A, Z] (\u0041-\u005A) matches the corresponding character in [a,z] (\u0061-\007A).</span></span> <span data-ttu-id="8e653-224">Правила регистра за пределами диапазона ASCII используют таблицы инвариантного языка.</span><span class="sxs-lookup"><span data-stu-id="8e653-224">Casing outside the ASCII range uses the invariant culture's tables.</span></span> <span data-ttu-id="8e653-225">Поэтому следующее сравнение</span><span class="sxs-lookup"><span data-stu-id="8e653-225">Therefore, the following comparison:</span></span>

```csharp
String.Compare(strA, strB, StringComparison.OrdinalIgnoreCase);
```

```vb
String.Compare(strA, strB, StringComparison.OrdinalIgnoreCase)
```

<span data-ttu-id="8e653-226">эквивалентно следующему сравнению (но выполняется быстрее):</span><span class="sxs-lookup"><span data-stu-id="8e653-226">is equivalent to (but faster than) this comparison:</span></span> 

```csharp
String.Compare(strA.ToUpperInvariant(), strB.ToUpperInvariant(), 
               StringComparison.Ordinal);
```

```vb
String.Compare(strA.ToUpperInvariant(), strB.ToUpperInvariant(), 
               StringComparison.Ordinal)
```

<span data-ttu-id="8e653-227">Эти сравнения по-прежнему выполняются очень быстро.</span><span class="sxs-lookup"><span data-stu-id="8e653-227">These comparisons are still very fast.</span></span>

<span data-ttu-id="8e653-228">И [StringComparison.Ordinal](xref:System.StringComparison.Ordinal), и [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) используют двоичные значения непосредственно и лучше всего подходят для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="8e653-228">Both [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) and [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) use the binary values directly, and are best suited for matching.</span></span> <span data-ttu-id="8e653-229">При отсутствии точной информации о параметрах сравнения используйте одно из этих двух значений.</span><span class="sxs-lookup"><span data-stu-id="8e653-229">When you are not sure about your comparison settings, use one of these two values.</span></span> <span data-ttu-id="8e653-230">Однако, поскольку они выполняют побайтовое сравнение, лингвистическая сортировка (как в словаре английского языка) не выполняется, однако используется двоичный порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="8e653-230">However, because they perform a byte-by-byte comparison, they do not sort by a linguistic sort order (like an English dictionary) but by a binary sort order.</span></span> <span data-ttu-id="8e653-231">В большинстве случаев для пользователя эти результаты будут выглядеть странно.</span><span class="sxs-lookup"><span data-stu-id="8e653-231">The results may look odd in most contexts if displayed to users.</span></span>

<span data-ttu-id="8e653-232">Порядковая семантика используется по умолчанию для перегрузок [String](xref:System.String) `Equals`, которые не содержат аргумент [StringComparison](xref:System.StringComparison) (включая оператор равенства).</span><span class="sxs-lookup"><span data-stu-id="8e653-232">Ordinal semantics are the default for [String](xref:System.String) `Equals` overloads that do not include a [StringComparison](xref:System.StringComparison) argument (including the equality operator).</span></span> <span data-ttu-id="8e653-233">В любом случае рекомендуется вызвать перегрузку, содержащую параметр [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="8e653-233">In any case, we recommend that you call an overload that has a [StringComparison](xref:System.StringComparison) parameter.</span></span>

### <a name="string-operations-that-use-the-invariant-culture"></a><span data-ttu-id="8e653-234">Строковые операции, использующие инвариантный язык и региональные параметры</span><span class="sxs-lookup"><span data-stu-id="8e653-234">String operations that use the invariant culture</span></span>

<span data-ttu-id="8e653-235">В сравнениях с инвариантным языком используется свойство [CompareInfo](xref:System.Globalization.CompareInfo), возвращаемое статическим свойством [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture).</span><span class="sxs-lookup"><span data-stu-id="8e653-235">Comparisons with the invariant culture use the [CompareInfo](xref:System.Globalization.CompareInfo) property returned by the static [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) property.</span></span> <span data-ttu-id="8e653-236">Это поведение одинаково во всех системах; оно преобразует любые символы за пределами своего диапазона в то, что оно считает эквивалентными инвариантными символами.</span><span class="sxs-lookup"><span data-stu-id="8e653-236">This behavior is the same on all systems; it translates any characters outside its range into what it believes are equivalent invariant characters.</span></span> <span data-ttu-id="8e653-237">Эта политика может пригодиться для реализации единого набора поведений строк в разных языках и региональных параметрах, однако часто это дает непредвиденные результаты.</span><span class="sxs-lookup"><span data-stu-id="8e653-237">This policy can be useful for maintaining one set of string behavior across cultures, but it often provides unexpected results.</span></span>

<span data-ttu-id="8e653-238">Сравнения без учета регистра с инвариантным языком также используют статическое свойство [CompareInfo](xref:System.Globalization.CompareInfo), возвращаемое статическим свойством [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) для сведений сравнения.</span><span class="sxs-lookup"><span data-stu-id="8e653-238">Case-insensitive comparisons with the invariant culture use the static [CompareInfo](xref:System.Globalization.CompareInfo) property returned by the static [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) property for comparison information as well.</span></span> <span data-ttu-id="8e653-239">Любые различия регистров в этих преобразуемых символах игнорируются.</span><span class="sxs-lookup"><span data-stu-id="8e653-239">Any case differences among these translated characters are ignored.</span></span>

<span data-ttu-id="8e653-240">Объект [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) заставляет метод [String](xref:System.String) `Compare` интерпретировать определенные наборы символов как эквивалентные.</span><span class="sxs-lookup"><span data-stu-id="8e653-240">The [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) object makes a [String](xref:System.String) `Compare` method interpret certain sets of characters as equivalent.</span></span> <span data-ttu-id="8e653-241">Например, следующие элементы эквивалентны только в инвариантном языке.</span><span class="sxs-lookup"><span data-stu-id="8e653-241">For example, the following equivalence is valid under the invariant culture:</span></span>

<span data-ttu-id="8e653-242">InvariantCulture: a + ̊ = å</span><span class="sxs-lookup"><span data-stu-id="8e653-242">InvariantCulture: a + ̊ = å</span></span>

<span data-ttu-id="8e653-243">Латинская строчная буква А, а (\u0061), находясь рядом с объединяющим кольцом над символом "+ " ̊"(\u030a), интерпретируется как строчная латинская буква а с кольцом над ней, å (\u00e5).</span><span class="sxs-lookup"><span data-stu-id="8e653-243">The latin small lette A character "a" (\u0061), when it is next to the combining ring above character "+ " ̊" (\u030a), is interpreted as the latin small letter A with ring above character "å" (\u00e5).</span></span> <span data-ttu-id="8e653-244">Как показано в следующем примере, это поведение отличается от порядкового сравнения.</span><span class="sxs-lookup"><span data-stu-id="8e653-244">As the following example shows, this behavior differs from ordinal comparison.</span></span>

```csharp
string separated = "\u0061\u030a";
string combined = "\u00e5";

Console.WriteLine("Equal sort weight of {0} and {1} using InvariantCulture: {2}",
                  separated, combined, 
                  String.Compare(separated, combined, 
                                 StringComparison.InvariantCulture) == 0);

Console.WriteLine("Equal sort weight of {0} and {1} using Ordinal: {2}",
                  separated, combined,
                  String.Compare(separated, combined, 
                                 StringComparison.Ordinal) == 0);
// The example displays the following output:
//    Equal sort weight of a° and å using InvariantCulture: True
//    Equal sort weight of a° and å using Ordinal: False 
```

```vb
Dim separated As String = ChrW(&h61) + ChrW(&h30a)
Dim combined As String = ChrW(&he5)

Console.WriteLine("Equal sort weight of {0} and {1} using InvariantCulture: {2}", _
                  separated, combined, _
                  String.Compare(separated, combined, _ 
                                 StringComparison.InvariantCulture) = 0)

Console.WriteLine("Equal sort weight of {0} and {1} using Ordinal: {2}", _
                  separated, combined, _
                  String.Compare(separated, combined, _
                                 StringComparison.Ordinal) = 0)
' The example displays the following output:
'    Equal sort weight of a° and å using InvariantCulture: True
'    Equal sort weight of a° and å using Ordinal: False
```

<span data-ttu-id="8e653-245">При интерпретации имен файлов, файлов cookie или чего-либо еще, где могут появляться такие сочетания, как å, порядковые сравнения по-прежнему являются наиболее понятным и подходящим поведением.</span><span class="sxs-lookup"><span data-stu-id="8e653-245">When interpreting file names, cookies, or anything else where a combination such as "å" can appear, ordinal comparisons still offer the most transparent and fitting behavior.</span></span>

<span data-ttu-id="8e653-246">В целом в инвариантном языке очень мало свойств, которые могли бы сделать его полезным для сравнения.</span><span class="sxs-lookup"><span data-stu-id="8e653-246">On balance, the invariant culture has very few properties that make it useful for comparison.</span></span> <span data-ttu-id="8e653-247">Он выполняет сравнения с учетом лингвистических параметров, что не позволяет гарантировать полную эквивалентность символов, однако не подходит для отображения на любом языке.</span><span class="sxs-lookup"><span data-stu-id="8e653-247">It does comparison in a linguistically relevant manner, which prevents it from guaranteeing full symbolic equivalence, but it is not the choice for display in any culture.</span></span> <span data-ttu-id="8e653-248">Например, если к приложению прилагается крупный файл данных, содержащий список сортированных идентификаторов для отображения, добавление в этот список потребует вставки элементов с сортировкой в инвариантном стиле.</span><span class="sxs-lookup"><span data-stu-id="8e653-248">For example, if a large data file that contains a list of sorted identifiers for display accompanies an application, adding to this list would require an insertion with invariant-style sorting.</span></span>

## <a name="choosing-a-stringcomparison-member-for-your-method-call"></a><span data-ttu-id="8e653-249">Выбор элемента StringComparison для вызова своего метода</span><span class="sxs-lookup"><span data-stu-id="8e653-249">Choosing a StringComparison member for your method call</span></span>

<span data-ttu-id="8e653-250">В следующей таблице приведено сопоставление семантического контекста строк элементу перечисления [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="8e653-250">The following table outlines the mapping from semantic string context to a [StringComparison](xref:System.StringComparison) enumeration member.</span></span>

<span data-ttu-id="8e653-251">Данные</span><span class="sxs-lookup"><span data-stu-id="8e653-251">Data</span></span> | <span data-ttu-id="8e653-252">Поведение</span><span class="sxs-lookup"><span data-stu-id="8e653-252">Behavior</span></span> | <span data-ttu-id="8e653-253">Соответствующее значение System.StringComparison</span><span class="sxs-lookup"><span data-stu-id="8e653-253">Corresponding System.StringComparison value</span></span>
---- | -------- | -------------------------------------------
<span data-ttu-id="8e653-254">Внутренние идентификаторы с учетом регистра, идентификаторы с учетом регистра в таких стандартах, как XML и HTTP или параметры безопасности с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="8e653-254">Case-sensitive internal identifiers, case-sensitive identifiers in standards such as XML and HTTP, or case-sensitive security-related settings.</span></span> | <span data-ttu-id="8e653-255">Нелингвистические идентификаторы с точным соответствием байтов.</span><span class="sxs-lookup"><span data-stu-id="8e653-255">A non-linguistic identifier, where bytes match exactly.</span></span> | [<span data-ttu-id="8e653-256">StringComparison.Ordinal</span><span class="sxs-lookup"><span data-stu-id="8e653-256">StringComparison.Ordinal</span></span>](xref:System.StringComparison.Ordinal)
<span data-ttu-id="8e653-257">Внутренние идентификаторы без учета регистра, идентификаторы без учета регистра в таких стандартах, как XML и HTTP, пути к файлам, разделы реестра и значения, переменные среды, идентификаторы ресурсов (например, имена дескрипторов) или параметры безопасности без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="8e653-257">Case-insensitive internal identifiers, case-insensitive identifiers in standards such as XML and HTTP, file paths, registry keys and values, environment variables, resource identifiers (for example, handle names), or case-insensitive security-related settings.</span></span> | <span data-ttu-id="8e653-258">Нелингвистический идентификатор, в котором регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="8e653-258">A non-linguistic identifier, where case is irrelevant.</span></span> | [<span data-ttu-id="8e653-259">StringComparison.OrdinalIgnoreCase</span><span class="sxs-lookup"><span data-stu-id="8e653-259">StringComparison.OrdinalIgnoreCase</span></span>](xref:System.StringComparison.OrdinalIgnoreCase)
<span data-ttu-id="8e653-260">Данные, отображаемые для пользователя, или пользовательский ввод в большинстве случаев.</span><span class="sxs-lookup"><span data-stu-id="8e653-260">Data displayed to the user or most user input.</span></span> | <span data-ttu-id="8e653-261">Данные, требующие местных лингвистических правил.</span><span class="sxs-lookup"><span data-stu-id="8e653-261">Data that requires local linguistic customs.</span></span> | <span data-ttu-id="8e653-262">[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) или [CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase)</span><span class="sxs-lookup"><span data-stu-id="8e653-262">[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) or [CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase)</span></span>

## <a name="common-string-comparison-methods"></a><span data-ttu-id="8e653-263">Общие методы сравнения строк</span><span class="sxs-lookup"><span data-stu-id="8e653-263">Common string comparison methods</span></span>

<span data-ttu-id="8e653-264">В следующих разделах описываются методы, которые чаще всего используются для сравнения строк.</span><span class="sxs-lookup"><span data-stu-id="8e653-264">The following sections describe the methods that are most commonly used for string comparison.</span></span>

### <a name="stringcompare"></a><span data-ttu-id="8e653-265">String.Compare</span><span class="sxs-lookup"><span data-stu-id="8e653-265">String.Compare</span></span>

<span data-ttu-id="8e653-266">Интерпретация по умолчанию: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="8e653-266">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="8e653-267">Поскольку эта операция наиболее тесно связана с интерпретацией строк, необходимо изучить все экземпляры вызовов этого метода, чтобы определить, должны ли строки интерпретироваться с учетом текущего языка и региональных параметров, либо их нужно (символически) отделить от языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="8e653-267">As the operation most central to string interpretation, all instances of these method calls should be examined to determine whether strings should be interpreted according to the current culture, or dissociated from the culture (symbolically).</span></span> <span data-ttu-id="8e653-268">Обычно выбирается последнее, и тогда должно использоваться сравнение [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span><span class="sxs-lookup"><span data-stu-id="8e653-268">Typically, it is the latter, and a [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) comparison should be used instead.</span></span>

<span data-ttu-id="8e653-269">Класс [System.Globalization.CompareInfo](xref:System.Globalization.CompareInfo), возвращаемый свойством [CultureInfo.CompareInfo](xref:System.Globalization.CultureInfo.CompareInfo), также включает метод [Compare](xref:System.Globalization.CompareInfo.Compare(System.String,System.Int32,System.String,System.Int32,System.Globalization.CompareOptions)), предоставляющий большое количество соответствующих параметров (порядковый, игнорирование пробела, игнорирование типа каны и т. д.) посредством перечисления флага [CompareOptions](xref:System.Globalization.CompareOptions).</span><span class="sxs-lookup"><span data-stu-id="8e653-269">The [System.Globalization.CompareInfo](xref:System.Globalization.CompareInfo) class, which is returned by the [CultureInfo.CompareInfo](xref:System.Globalization.CultureInfo.CompareInfo) property, also includes a [Compare](xref:System.Globalization.CompareInfo.Compare(System.String,System.Int32,System.String,System.Int32,System.Globalization.CompareOptions)) method that provides a large number of matching options (ordinal, ignoring white space, ignoring kana type, and so on) by means of the [CompareOptions](xref:System.Globalization.CompareOptions) flag enumeration.</span></span> 

### <a name="stringcompareto"></a><span data-ttu-id="8e653-270">String.CompareTo</span><span class="sxs-lookup"><span data-stu-id="8e653-270">String.CompareTo</span></span>

<span data-ttu-id="8e653-271">Интерпретация по умолчанию: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="8e653-271">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="8e653-272">Сейчас этот метод не предлагает перегрузку, задающую тип [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="8e653-272">This method does not currently offer an overload that specifies a [StringComparison](xref:System.StringComparison) type.</span></span> <span data-ttu-id="8e653-273">Обычно возможно преобразовать этот метод в рекомендованную форму [String.Compare (String, String, StringComparison)](xref:System.String.Compare(System.String,System.String,System.StringComparison)).</span><span class="sxs-lookup"><span data-stu-id="8e653-273">It is usually possible to convert this method to the recommended [String.Compare(String, String, StringComparison)](xref:System.String.Compare(System.String,System.String,System.StringComparison)) form.</span></span>

<span data-ttu-id="8e653-274">Типы, реализующие интерфейсы [IComparable](xref:System.IComparable) и [IComparable&lt;T&gt;](xref:System.IComparable%601), реализуют этот метод.</span><span class="sxs-lookup"><span data-stu-id="8e653-274">Types that implement the [IComparable](xref:System.IComparable) and [IComparable&lt;T&gt;](xref:System.IComparable%601) interfaces implement this method.</span></span> <span data-ttu-id="8e653-275">Поскольку параметр [StringComparison](xref:System.StringComparison) не предлагается, реализация типов часто позволяет пользователю задать [StringComparer](xref:System.StringComparer) в своем конструкторе.</span><span class="sxs-lookup"><span data-stu-id="8e653-275">Because it does not offer the option of a [StringComparison](xref:System.StringComparison) parameter, implementing types often let the user specify a [StringComparer](xref:System.StringComparer) in their constructor.</span></span> <span data-ttu-id="8e653-276">В следующем примере определяется класс `FileName`, конструктор класса которого включает параметр [StringComparer](xref:System.StringComparer).</span><span class="sxs-lookup"><span data-stu-id="8e653-276">The following example defines a `FileName` class whose class constructor includes a [StringComparer](xref:System.StringComparer) parameter.</span></span> <span data-ttu-id="8e653-277">Затем этот объект [StringComparer](xref:System.StringComparer) используется в методе `FileName.CompareTo`.</span><span class="sxs-lookup"><span data-stu-id="8e653-277">This [StringComparer](xref:System.StringComparer) object is then used in the `FileName.CompareTo` method.</span></span>

```csharp
using System;

public class FileName : IComparable
{
   string fname;
   StringComparer comparer; 

   public FileName(string name, StringComparer comparer)
   {
      if (String.IsNullOrEmpty(name))
         throw new ArgumentNullException("name");

      this.fname = name;

      if (comparer != null)
         this.comparer = comparer;
      else
         this.comparer = StringComparer.OrdinalIgnoreCase;
   }

   public string Name
   {
      get { return fname; }
   }

   public int CompareTo(object obj)
   {
      if (obj == null) return 1;

      if (! (obj is FileName))
         return comparer.Compare(this.fname, obj.ToString());
      else
         return comparer.Compare(this.fname, ((FileName) obj).Name);
   }
}
```

```vb
Public Class FileName : Implements IComparable
   Dim fname As String
   Dim comparer As StringComparer 

   Public Sub New(name As String, comparer As StringComparer)
      If String.IsNullOrEmpty(name) Then
         Throw New ArgumentNullException("name")
      End If

      Me.fname = name

      If comparer IsNot Nothing Then
         Me.comparer = comparer
      Else
         Me.comparer = StringComparer.OrdinalIgnoreCase
      End If      
   End Sub

   Public ReadOnly Property Name As String
      Get
         Return fname
      End Get   
   End Property

   Public Function CompareTo(obj As Object) As Integer _
          Implements IComparable.CompareTo
      If obj Is Nothing Then Return 1

      If Not TypeOf obj Is FileName Then
         obj = obj.ToString()
      Else
         obj = CType(obj, FileName).Name
      End If         
      Return comparer.Compare(Me.fname, obj)
   End Function
End Class
```

### <a name="stringequals"></a><span data-ttu-id="8e653-278">String.Equals</span><span class="sxs-lookup"><span data-stu-id="8e653-278">String.Equals</span></span>

<span data-ttu-id="8e653-279">Интерпретация по умолчанию: [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span><span class="sxs-lookup"><span data-stu-id="8e653-279">Default interpretation: [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span></span>

<span data-ttu-id="8e653-280">Класс [String](xref:System.String) позволяет выполнить проверку на равенство, вызвав статические перегрузки метода `Equals` или перегрузки экземпляров. Кроме того, можно воспользоваться оператором статического равенства.</span><span class="sxs-lookup"><span data-stu-id="8e653-280">The [String](xref:System.String) class lets you test for equality by calling either the static or instance `Equals` method overloads, or by using the static equality operator.</span></span> <span data-ttu-id="8e653-281">Перегрузки и оператор используют порядковое сравнение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8e653-281">The overloads and operator use ordinal comparison by default.</span></span> <span data-ttu-id="8e653-282">Однако рекомендуется вызывать перегрузку, которая явно задает тип [StringComparison](xref:System.StringComparison), даже если требуется выполнить порядковое сравнение. Это упрощает поиск кода для интерпретации определенной строки.</span><span class="sxs-lookup"><span data-stu-id="8e653-282">However, we still recommend that you call an overload that explicitly specifies the [StringComparison](xref:System.StringComparison) type even if you want to perform an ordinal comparison; this makes it easier to search code for a certain string interpretation.</span></span> 

### <a name="stringtoupper-and-stringtolower"></a><span data-ttu-id="8e653-283">String.ToUpper и String.ToLower</span><span class="sxs-lookup"><span data-stu-id="8e653-283">String.ToUpper and String.ToLower</span></span>

<span data-ttu-id="8e653-284">Интерпретация по умолчанию: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="8e653-284">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="8e653-285">Следует соблюдать осторожность, используя эти методы, поскольку принудительное преобразование строки в нижний или верхний регистр часто используется в качестве незначительной нормализации для сравнения строк независимо от регистра.</span><span class="sxs-lookup"><span data-stu-id="8e653-285">You should be careful when you use these methods, because forcing a string to a uppercase or lowercase is often used as a small normalization for comparing strings regardless of case.</span></span> <span data-ttu-id="8e653-286">В этом случае целесообразно выполнить сравнение без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="8e653-286">If so, consider using a case-insensitive comparison.</span></span> 

<span data-ttu-id="8e653-287">Также доступны методы [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) и [String.ToLowerInvariant](xref:System.String.ToLowerInvariant).</span><span class="sxs-lookup"><span data-stu-id="8e653-287">The [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) and [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) methods are also available.</span></span> <span data-ttu-id="8e653-288">[ToUpperInvariant](xref:System.String.ToUpperInvariant) — это стандартный способ нормализации регистра.</span><span class="sxs-lookup"><span data-stu-id="8e653-288">[ToUpperInvariant](xref:System.String.ToUpperInvariant) is the standard way to normalize case.</span></span> <span data-ttu-id="8e653-289">Сравнения, выполненные с помощью [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase), с точки зрения поведения представляют собой комбинацию из двух вызовов: вызов [ToUpperInvariant](xref:System.String.ToUpperInvariant) в обоих аргументах строки и выполнение сравнения с использованием [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span><span class="sxs-lookup"><span data-stu-id="8e653-289">Comparisons made using [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) are behaviorally the composition of two calls: calling [ToUpperInvariant](xref:System.String.ToUpperInvariant) on both string arguments, and doing a comparison using [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span></span>

<span data-ttu-id="8e653-290">Также доступны перегрузки для преобразования в верхний и нижний регистр в конкретном языке. Для этого передается объект [CultureInfo](xref:System.Globalization.CultureInfo), представляющий этот язык для метода.</span><span class="sxs-lookup"><span data-stu-id="8e653-290">Overloads are also available for converting to uppercase and lowercase in a specific culture, by passing a [CultureInfo](xref:System.Globalization.CultureInfo) object that represents that culture to the method.</span></span>

### <a name="chartoupper-and-chartolower"></a><span data-ttu-id="8e653-291">Char.ToUpper и Char.ToLower</span><span class="sxs-lookup"><span data-stu-id="8e653-291">Char.ToUpper and Char.ToLower</span></span>

<span data-ttu-id="8e653-292">Интерпретация по умолчанию: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="8e653-292">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="8e653-293">Эти методы работают аналогично методам [String.ToUpper](xref:System.String.ToUpper) и [String.ToLower](xref:System.String.ToLower), описанным выше.</span><span class="sxs-lookup"><span data-stu-id="8e653-293">These methods work similarly to the [String.ToUpper](xref:System.String.ToUpper) and [String.ToLower](xref:System.String.ToLower) methods described in the previous section.</span></span>

### <a name="stringstartswith-and-stringendswith"></a><span data-ttu-id="8e653-294">String.StartsWith и String.EndsWith</span><span class="sxs-lookup"><span data-stu-id="8e653-294">String.StartsWith and String.EndsWith</span></span>

<span data-ttu-id="8e653-295">Интерпретация по умолчанию: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="8e653-295">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="8e653-296">По умолчанию оба этих метода выполняют сравнение с учетом языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="8e653-296">By default, both of these methods perform a culture-sensitive comparison.</span></span>

### <a name="stringindexof-and-stringlastindexof"></a><span data-ttu-id="8e653-297">String.IndexOf и String.LastIndexOf</span><span class="sxs-lookup"><span data-stu-id="8e653-297">String.IndexOf and String.LastIndexOf</span></span>

<span data-ttu-id="8e653-298">Интерпретация по умолчанию: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="8e653-298">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="8e653-299">Перегрузки этих методов по умолчанию выполняют сравнения непоследовательно.</span><span class="sxs-lookup"><span data-stu-id="8e653-299">There is a lack of consistency in how the default overloads of these methods perform comparisons.</span></span> <span data-ttu-id="8e653-300">Все методы [String](xref:System.String) `IndexOf` и [String](xref:System.String) `LastIndexOf`, включающие параметр [Char](xref:System.Char), выполняют порядковое сравнение, однако методы [String](xref:System.String) `IndexOf` и [String`](xref:System.String) `LastIndexOf] по умолчанию, которые включают параметр [String](xref:System.String), выполняют сравнение с учетом языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="8e653-300">All [String](xref:System.String) `IndexOf` and [String](xref:System.String) `LastIndexOf` methods that include a [Char](xref:System.Char) parameter perform an ordinal comparison, but the default [String](xref:System.String) `IndexOf` and [String`](xref:System.String) `LastIndexOf\` methods that include a [String](xref:System.String) parameter perform a culture-sensitive comparison.</span></span> 

<span data-ttu-id="8e653-301">Если нужно вызвать метод ` `IndexOf` or `LastIndexOf и передать ему строку для определения ее местоположения в текущем экземпляре, рекомендуется вызвать перегрузку, которая явно задает тип [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="8e653-301">If you call ` `IndexOf` or `LastIndexOf\` method and pass it a string to locate in the current instance, we recommend that you call an overload that explicitly specifies the [StringComparison](xref:System.StringComparison) type.</span></span> <span data-ttu-id="8e653-302">Перегрузки, включающие аргумент [Char](xref:System.Char), не позволяют задать тип [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="8e653-302">The overloads that include a [Char](xref:System.Char) argument do not allow you to specify a [StringComparison](xref:System.StringComparison) type.</span></span>

## <a name="methods-that-perform-string-comparison-indirectly"></a><span data-ttu-id="8e653-303">Методы, сравнивающие строки опосредованно</span><span class="sxs-lookup"><span data-stu-id="8e653-303">Methods that perform string comparison indirectly</span></span>

<span data-ttu-id="8e653-304">Некоторые нестроковые методы, основным назначением которых является сравнение строк, используют тип [StringComparer](xref:System.StringComparer).</span><span class="sxs-lookup"><span data-stu-id="8e653-304">Some non-string methods that have string comparison as a central operation use the [StringComparer](xref:System.StringComparer) type.</span></span> <span data-ttu-id="8e653-305">Класс [StringComparer](xref:System.StringComparer) включает четыре статических свойства, возвращающих экземпляры [StringComparer](xref:System.StringComparer), методы `Compare` которых выполняют следующие типы сравнения строк.</span><span class="sxs-lookup"><span data-stu-id="8e653-305">The [StringComparer](xref:System.StringComparer) class includes four static properties that return [StringComparer](xref:System.StringComparer) instances whose `Compare` methods perform the following types of string comparisons:</span></span>

* <span data-ttu-id="8e653-306">Сравнения строк с учетом языка и региональных параметров с использованием текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="8e653-306">Culture-sensitive string comparisons using the current culture.</span></span> <span data-ttu-id="8e653-307">Этот объект [StringComparer](xref:System.StringComparer) возвращается свойством [StringComparer.CurrentCulture](xref:System.StringComparer.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="8e653-307">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.CurrentCulture](xref:System.StringComparer.CurrentCulture) property.</span></span>

* <span data-ttu-id="8e653-308">Сравнение без учета регистра с использованием текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="8e653-308">Case-insensitive comparisons using the current culture.</span></span> <span data-ttu-id="8e653-309">Этот объект [StringComparer](xref:System.StringComparer) возвращается свойством [StringComparer.CurrentCultureIgnoreCase](xref:System.StringComparer.CurrentCultureIgnoreCase).</span><span class="sxs-lookup"><span data-stu-id="8e653-309">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.CurrentCultureIgnoreCase](xref:System.StringComparer.CurrentCultureIgnoreCase) property.</span></span>

* <span data-ttu-id="8e653-310">Порядковое сравнение.</span><span class="sxs-lookup"><span data-stu-id="8e653-310">Ordinal comparison.</span></span> <span data-ttu-id="8e653-311">Этот объект [StringComparer](xref:System.StringComparer) возвращается свойством [StringComparer.Ordinal](xref:System.StringComparer.Ordinal).</span><span class="sxs-lookup"><span data-stu-id="8e653-311">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.Ordinal](xref:System.StringComparer.Ordinal) property.</span></span> 

* <span data-ttu-id="8e653-312">Порядковое сравнение без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="8e653-312">Case-insensitive ordinal comparison.</span></span> <span data-ttu-id="8e653-313">Этот объект [StringComparer](xref:System.StringComparer) возвращается свойством [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase).</span><span class="sxs-lookup"><span data-stu-id="8e653-313">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase) property.</span></span>

### <a name="arraysort-and-arraybinarysearch"></a><span data-ttu-id="8e653-314">Array.Sort и Array.BinarySearch</span><span class="sxs-lookup"><span data-stu-id="8e653-314">Array.Sort and Array.BinarySearch</span></span>

<span data-ttu-id="8e653-315">Интерпретация по умолчанию: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="8e653-315">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="8e653-316">При хранении любых данных в коллекции или считывании сохраненных данных из файла или базы данных в коллекцию изменение текущего языка и региональных параметров может сделать недействительными инварианты этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="8e653-316">When you store any data in a collection, or read persisted data from a file or database into a collection, switching the current culture can invalidate the invariants in the collection.</span></span> <span data-ttu-id="8e653-317">Метод [Array.BinarySearch](xref:System.Array.BinarySearch(System.Array,System.Object)) предполагает, что элементы в массиве, поиск которых необходимо выполнить, уже сортированы.</span><span class="sxs-lookup"><span data-stu-id="8e653-317">The [Array.BinarySearch](xref:System.Array.BinarySearch(System.Array,System.Object)) method assumes that the elements in the array to be searched are already sorted.</span></span> <span data-ttu-id="8e653-318">Чтобы отсортировать любой строковый элемент в массиве, метод [Array.Sort](xref:System.Array.Sort(System.Array)) вызывает метод [String] `Compare` для упорядочивания отдельных элементов.</span><span class="sxs-lookup"><span data-stu-id="8e653-318">To sort any string element in the array, the [Array.Sort](xref:System.Array.Sort(System.Array)) method calls the [String] `Compare` method to order individual elements.</span></span> <span data-ttu-id="8e653-319">Использовать средство сравнения с учетом языка и региональных параметров может быть опасно, если язык и региональные параметры изменяются в период между сортировкой массива и поиском в содержимом этого массива.</span><span class="sxs-lookup"><span data-stu-id="8e653-319">Using a culture-sensitive comparer can be dangerous if the culture changes between the time that the array is sorted and its contents are searched.</span></span> <span data-ttu-id="8e653-320">Например, в следующем коде для хранения и извлечения данных используется средство сравнения, которое неявно предоставляется свойством `Thread.CurrentThread.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="8e653-320">For example, in the following code, storage and retrieval operate on the comparer that is provided implicitly by the `Thread.CurrentThread.CurrentCulture` property.</span></span> <span data-ttu-id="8e653-321">Если язык и региональные параметры могут измениться между вызовом `StoreNames` и `DoesNameExist` и особенно если содержимое массива сохраняется в период между вызовами этих двух методов, двоичный поиск может завершиться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8e653-321">If the culture can change between the calls to `StoreNames` and `DoesNameExist`, and especially if the array contents are persisted somewhere between the two method calls, the binary search may fail.</span></span> 

```csharp
// Incorrect.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names); // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name) >= 0);  // Line B.
}
```

```vb
' Incorrect.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names)          ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name) >= 0      ' Line B.
End Function
```

<span data-ttu-id="8e653-322">Рекомендуемый вариант показан в следующем примере, где один и тот же метод порядкового сравнения (без учета языка и региональных параметров) используется для сортировки массива и поиска в нем.</span><span class="sxs-lookup"><span data-stu-id="8e653-322">A recommended variation appears in the following example, which uses the same ordinal (culture-insensitive) comparison method both to sort and to search the array.</span></span> <span data-ttu-id="8e653-323">Измененный код отражается в строках, помеченных в этих двух примерах как `Line A` и `Line B`.</span><span class="sxs-lookup"><span data-stu-id="8e653-323">The change code is reflected in the lines labeled `Line A` and `Line B` in the two examples.</span></span>

```csharp
// Correct.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names, StringComparer.Ordinal);  // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name, StringComparer.Ordinal) >= 0);  // Line B.
}
```

```vb
' Correct.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names, StringComparer.Ordinal)           ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name, StringComparer.Ordinal) >= 0      ' Line B.
End Function
```

<span data-ttu-id="8e653-324">Если эти данные сохраняются и перемещаются в разных языках, а для представления этих данных пользователю используется сортировка, целесообразно использовать `StringComparison.InvariantCulture`, действующий с учетом лингвистических правил и, следовательно, повышающий качество выводимых пользователю данных, но при этом не подверженный влиянию изменений в языке и региональных параметрах.</span><span class="sxs-lookup"><span data-stu-id="8e653-324">If this data is persisted and moved across cultures, and sorting is used to present this data to the user, you might consider using `StringComparison.InvariantCulture`, which operates linguistically for better user output but is unaffected by changes in culture.</span></span> <span data-ttu-id="8e653-325">В следующем примере два предыдущих примера изменяются так, чтобы для сортировки массива и поиска в нем использовался инвариантный язык.</span><span class="sxs-lookup"><span data-stu-id="8e653-325">The following example modifies the two previous examples to use the invariant culture for sorting and searching the array.</span></span>

```csharp
// Correct.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names, StringComparer.InvariantCulture);  // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name, StringComparer.InvariantCulture) >= 0);  // Line B.
}
```

```vb
' Correct.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names, StringComparer.InvariantCulture)           ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name, StringComparer.InvariantCulture) >= 0      ' Line B.
End Function
```

### <a name="collections-example-hashtable-constructor"></a><span data-ttu-id="8e653-326">Пример коллекций: доступный для кэширования конструктор</span><span class="sxs-lookup"><span data-stu-id="8e653-326">Collections Example: Hashtable Constructor</span></span>

<span data-ttu-id="8e653-327">Хэширование строк — это второй пример операции, на которую влияет способ сравнения строк.</span><span class="sxs-lookup"><span data-stu-id="8e653-327">Hashing strings provides a second example of an operation that is affected by the way in which strings are compared.</span></span> 

<span data-ttu-id="8e653-328">В следующем примере создается экземпляр объекта [Hashtable](xref:System.Collections.Hashtable) путем передачи его объекту [StringComparer](xref:System.StringComparer), который возвращается свойством [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase).</span><span class="sxs-lookup"><span data-stu-id="8e653-328">The following example instantiates a [Hashtable](xref:System.Collections.Hashtable) object by passing it the [StringComparer](xref:System.StringComparer) object that is returned by the [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase) property.</span></span> <span data-ttu-id="8e653-329">Поскольку класс [StringComparer](xref:System.StringComparer), который является производным от [StringComparer](xref:System.StringComparer), реализует интерфейс [IEqualityComparer](xref:System.Collections.IEqualityComparer), его метод [GetHashCode](xref:System.Collections.IEqualityComparer) используется для вычисления хэш-кода строк в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="8e653-329">Because a class [StringComparer](xref:System.StringComparer) that is derived from [StringComparer](xref:System.StringComparer) implements the [IEqualityComparer](xref:System.Collections.IEqualityComparer) interface, its [GetHashCode](xref:System.Collections.IEqualityComparer) method is used to compute the hash code of strings in the hash table.</span></span>

```csharp
const int initialTableCapacity = 100;
Hashtable h;

public void PopulateFileTable(string directory)
{
   h = new Hashtable(initialTableCapacity, 
                     StringComparer.OrdinalIgnoreCase);

   foreach (string file in Directory.GetFiles(directory))
         h.Add(file, File.GetCreationTime(file));
}

public void PrintCreationTime(string targetFile)
{
   Object dt = h[targetFile];
   if (dt != null)
   {
      Console.WriteLine("File {0} was created at time {1}.",
         targetFile, 
         (DateTime) dt);
   }
   else
   {
      Console.WriteLine("File {0} does not exist.", targetFile);
   }
}
```

```vb
Const initialTableCapacity As Integer = 100
Dim h As Hashtable

Public Sub PopulateFileTable(dir As String)
   h = New Hashtable(initialTableCapacity, _
                     StringComparer.OrdinalIgnoreCase)

   For Each filename As String In Directory.GetFiles(dir)
      h.Add(filename, File.GetCreationTime(filename))
   Next                        
End Sub

Public Sub PrintCreationTime(targetFile As String)
   Dim dt As Object = h(targetFile)
   If dt IsNot Nothing Then
      Console.WriteLine("File {0} was created at {1}.", _
         targetFile, _
         CDate(dt))
   Else
      Console.WriteLine("File {0} does not exist.", targetFile)
   End If
End Sub  
```

## <a name="displaying-and-persisting-formatted-data"></a><span data-ttu-id="8e653-330">Отображение и сохранение форматированных данных</span><span class="sxs-lookup"><span data-stu-id="8e653-330">Displaying and persisting formatted data</span></span>

<span data-ttu-id="8e653-331">При отображении нестроковых данных, например чисел, дат и времени, пользователям следует форматировать их с использованием параметров языка и региональных параметров пользователя.</span><span class="sxs-lookup"><span data-stu-id="8e653-331">When you display non-string data such as numbers and dates and times to users, format them by using the user's cultural settings.</span></span> <span data-ttu-id="8e653-332">По умолчанию метод [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) и методы `ToString` числовых типов и типов даты и времени используют текущий язык потока для операций форматирования.</span><span class="sxs-lookup"><span data-stu-id="8e653-332">By default, the [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) method and the `ToString` methods of the numeric types and the date and time types use the current thread culture for formatting operations.</span></span> <span data-ttu-id="8e653-333">Чтобы явно указать, что метод форматирования должен использовать текущий язык и региональные параметры, можно вызвать перегрузку метода форматирования, который имеет параметр provider, например [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) или [DateTime.ToString(IFormatProvider)](xref:System.DateTime.ToString(System.IFormatProvider)), и передать ему свойство [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="8e653-333">To explicitly specify that the formatting method should use the current culture, you can call an overload of a formatting method that has a provider parameter, such as [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) or [DateTime.ToString(IFormatProvider)](xref:System.DateTime.ToString(System.IFormatProvider)), and pass it the [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) property.</span></span> 

<span data-ttu-id="8e653-334">Нестроковые данные можно сохранить в виде двоичных или форматированных данных.</span><span class="sxs-lookup"><span data-stu-id="8e653-334">You can persist non-string data either as binary data or as formatted data.</span></span> <span data-ttu-id="8e653-335">Если решено сохранять данные в виде форматированных, нужно вызвать перегрузку метода форматирования, которая включает параметр *provider*, и передать ей свойство [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture).</span><span class="sxs-lookup"><span data-stu-id="8e653-335">If you choose to save it as formatted data, you should call a formatting method overload that includes a *provider* parameter and pass it the [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) property.</span></span> <span data-ttu-id="8e653-336">Инвариантный язык и региональные параметры предоставляют согласованный формат для форматированных данных независимо от языка, региональных параметров и компьютера.</span><span class="sxs-lookup"><span data-stu-id="8e653-336">The invariant culture provides a consistent format for formatted data that is independent of culture and machine.</span></span> <span data-ttu-id="8e653-337">Напротив, сохранение форматированных данных с использованием языков и региональных параметров, отличающихся от инвариантных, имеет ряд ограничений.</span><span class="sxs-lookup"><span data-stu-id="8e653-337">In contrast, persisting data that is formatted by using cultures other than the invariant culture has a number of limitations:</span></span> 

* <span data-ttu-id="8e653-338">Данные, вероятно, станут недоступными для использования после извлечения в системе с другим языком либо если пользователь текущей системы сменит текущий язык и попытается извлечь данные.</span><span class="sxs-lookup"><span data-stu-id="8e653-338">The data is likely to be unusable if it is retrieved on a system that has a different culture, or if the user of the current system changes the current culture and tries to retrieve the data.</span></span> 

* <span data-ttu-id="8e653-339">Свойства языка и региональных параметров на конкретном компьютере могут отличаться от стандартных значений.</span><span class="sxs-lookup"><span data-stu-id="8e653-339">The properties of a culture on a specific computer can differ from standard values.</span></span> <span data-ttu-id="8e653-340">Пользователь может в любой момент настроить параметры отображения с учетом языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="8e653-340">At any time, a user can customize culture-sensitive display settings.</span></span> <span data-ttu-id="8e653-341">По этой причине форматированные данные, которые сохраняются в системе, могут стать недоступными для чтения после изменения настроек языка пользователем.</span><span class="sxs-lookup"><span data-stu-id="8e653-341">Because of this, formatted data that is saved on a system may not be readable after the user customizes cultural settings.</span></span> <span data-ttu-id="8e653-342">Переносимость форматированных данных с одного компьютера на другой, вероятно, будет еще более ограниченной.</span><span class="sxs-lookup"><span data-stu-id="8e653-342">The portability of formatted data across computers is likely to be even more limited.</span></span> 

* <span data-ttu-id="8e653-343">Международные, региональные и национальные стандарты, регулирующие форматирование чисел, дат и времени, со временем меняются, и эти изменения отражаются в обновлениях операционной системы.</span><span class="sxs-lookup"><span data-stu-id="8e653-343">International, regional, or national standards that govern the formatting of numbers or dates and times change over time, and these changes are incorporated into operating system updates.</span></span> <span data-ttu-id="8e653-344">При изменении правил форматирования данные, форматированные с использованием старых правил, становятся недоступными для чтения.</span><span class="sxs-lookup"><span data-stu-id="8e653-344">When formatting conventions change, data that was formatted by using the previous conventions may become unreadable.</span></span> 

<span data-ttu-id="8e653-345">В следующем примере демонстрируется ограниченная переносимость в результате использования для сохранения данных форматирования с учетом языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="8e653-345">The following example illustrates the limited portability that results from using culture-sensitive formatting to persist data.</span></span> <span data-ttu-id="8e653-346">В этом примере массив значений даты и времени сохраняется в файл.</span><span class="sxs-lookup"><span data-stu-id="8e653-346">The example saves an array of date and time values to a file.</span></span> <span data-ttu-id="8e653-347">Данные форматируются с использованием правил английского языка (США).</span><span class="sxs-lookup"><span data-stu-id="8e653-347">These are formatted by using the conventions of the English (United States) culture.</span></span> <span data-ttu-id="8e653-348">После того как приложение сменит текущий язык потока на французский (Швейцария), оно попытается прочитать сохраненные значения, используя правила форматирования текущей культуры.</span><span class="sxs-lookup"><span data-stu-id="8e653-348">After the application changes the current thread culture to French (Switzerland), it tries to read the saved values by using the formatting conventions of the current culture.</span></span> <span data-ttu-id="8e653-349">При попытке чтения двух элементов данных создается исключение [FormatException](xref:System.FormatException), а массив дат теперь содержит два неправильных элемента, равных [MinValue](xref:System.DateTime.MinValue).</span><span class="sxs-lookup"><span data-stu-id="8e653-349">The attempt to read two of the data items throws a [FormatException](xref:System.FormatException) exception, and the array of dates now contains two incorrect elements that are equal to [MinValue](xref:System.DateTime.MinValue).</span></span> 

```csharp
using System;
using System.Globalization;
using System.IO;
using System.Text;
using System.Threading;

public class Example
{
   private static string filename = @".\dates.dat";

   public static void Main()
   {
      DateTime[] dates = { new DateTime(1758, 5, 6, 21, 26, 0), 
                           new DateTime(1818, 5, 5, 7, 19, 0), 
                           new DateTime(1870, 4, 22, 23, 54, 0),  
                           new DateTime(1890, 9, 8, 6, 47, 0), 
                           new DateTime(1905, 2, 18, 15, 12, 0) }; 
      // Write the data to a file using the current culture.
      WriteData(dates);
      // Change the current culture.
      Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture("fr-CH");
      // Read the data using the current culture.
      DateTime[] newDates = ReadData();
      foreach (var newDate in newDates)
         Console.WriteLine(newDate.ToString("g"));
   }

   private static void WriteData(DateTime[] dates) 
   {
      StreamWriter sw = new StreamWriter(filename, false, Encoding.UTF8);    
      for (int ctr = 0; ctr < dates.Length; ctr++) {
         sw.Write("{0}", dates[ctr].ToString("g", CultureInfo.CurrentCulture));
         if (ctr < dates.Length - 1) sw.Write("|");   
      }      
      sw.Close();
   }

   private static DateTime[] ReadData() 
   {
      bool exceptionOccurred = false;

      // Read file contents as a single string, then split it.
      StreamReader sr = new StreamReader(filename, Encoding.UTF8);
      string output = sr.ReadToEnd();
      sr.Close();   

      string[] values = output.Split( new char[] { '|' } );
      DateTime[] newDates = new DateTime[values.Length]; 
      for (int ctr = 0; ctr < values.Length; ctr++) {
         try {
            newDates[ctr] = DateTime.Parse(values[ctr], CultureInfo.CurrentCulture);
         }
         catch (FormatException) {
            Console.WriteLine("Failed to parse {0}", values[ctr]);
            exceptionOccurred = true;
         }
      }      
      if (exceptionOccurred) Console.WriteLine();
      return newDates;
   }
}
// The example displays the following output:
//       Failed to parse 4/22/1870 11:54 PM
//       Failed to parse 2/18/1905 3:12 PM
//       
//       05.06.1758 21:26
//       05.05.1818 07:19
//       01.01.0001 00:00
//       09.08.1890 06:47
//       01.01.0001 00:00
//       01.01.0001 00:00
```

```vb
Imports System.Globalization
Imports System.IO
Imports System.Text
Imports System.Threading

Module Example
   Private filename As String = ".\dates.dat"

   Public Sub Main()
      Dim dates() As Date = { #5/6/1758 9:26PM#, #5/5/1818 7:19AM#, _ 
                              #4/22/1870 11:54PM#, #9/8/1890 6:47AM#, _ 
                              #2/18/1905 3:12PM# }
      ' Write the data to a file using the current culture.
      WriteData(dates)
      ' Change the current culture.
      Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture("fr-CH")
      ' Read the data using the current culture.
      Dim newDates() As Date = ReadData()
      For Each newDate In newDates
         Console.WriteLine(newDate.ToString("g"))
      Next
   End Sub

   Private Sub WriteData(dates() As Date)
      Dim sw As New StreamWriter(filename, False, Encoding.Utf8)    
      For ctr As Integer = 0 To dates.Length - 1
         sw.Write("{0}", dates(ctr).ToString("g", CultureInfo.CurrentCulture))
         If ctr < dates.Length - 1 Then sw.Write("|")   
      Next      
      sw.Close()
   End Sub

   Private Function ReadData() As Date()
      Dim exceptionOccurred As Boolean = False

      ' Read file contents as a single string, then split it.
      Dim sr As New StreamReader(filename, Encoding.Utf8)
      Dim output As String = sr.ReadToEnd()
      sr.Close()   

      Dim values() As String = output.Split( {"|"c } )
      Dim newDates(values.Length - 1) As Date 
      For ctr As Integer = 0 To values.Length - 1
         Try
            newDates(ctr) = DateTime.Parse(values(ctr), CultureInfo.CurrentCulture)
         Catch e As FormatException
            Console.WriteLine("Failed to parse {0}", values(ctr))
            exceptionOccurred = True
         End Try
      Next      
      If exceptionOccurred Then Console.WriteLine()
      Return newDates
   End Function
End Module
' The example displays the following output:
'       Failed to parse 4/22/1870 11:54 PM
'       Failed to parse 2/18/1905 3:12 PM
'       
'       05.06.1758 21:26
'       05.05.1818 07:19
'       01.01.0001 00:00
'       09.08.1890 06:47
'       01.01.0001 00:00
'       01.01.0001 00:00
'
```

<span data-ttu-id="8e653-350">Однако если заменить свойство [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) на [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) в вызовах методов [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) и [DateTime.Parse(String, IFormatProvider)](xref:System.DateTime.Parse(System.String,System.IFormatProvider)), хранимые данные даты и времени восстанавливаются успешно, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="8e653-350">However, if you replace the [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) property with [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) in the calls to [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) and [DateTime.Parse(String, IFormatProvider)](xref:System.DateTime.Parse(System.String,System.IFormatProvider)), the persisted date and time data is successfully restored, as the following output shows.</span></span>

```
// 06.05.1758 21:26
// 05.05.1818 07:19
// 22.04.1870 23:54
// 08.09.1890 06:47
// 18.02.1905 15:12
```

## <a name="see-also"></a><span data-ttu-id="8e653-351">См. также</span><span class="sxs-lookup"><span data-stu-id="8e653-351">See also</span></span>

[<span data-ttu-id="8e653-352">Операции со строками</span><span class="sxs-lookup"><span data-stu-id="8e653-352">Manipulating strings</span></span>](manipulating-strings.md)

