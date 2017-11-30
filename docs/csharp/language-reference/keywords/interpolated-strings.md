---
title: "Интерполированные строки (C#)"
ms.date: 10/18/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 324f267e-1c61-431a-97ed-852c1530742d
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b8a1fe0be82a0e09d61c66ed463199ff626c9faa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="interpolated-strings-c-reference"></a><span data-ttu-id="1b7c6-102">Интерполированные строки (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1b7c6-102">Interpolated Strings (C# Reference)</span></span>

<span data-ttu-id="1b7c6-103">Используется для создания строк.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-103">Used to construct strings.</span></span>  <span data-ttu-id="1b7c6-104">Интерполированное строковое выражение выглядит как строка шаблона, которая содержит *интерполированные выражения*.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-104">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span>  <span data-ttu-id="1b7c6-105">Интерполированная строка возвращает строку, которая заменяет содержащиеся в ней интерполированные выражения строковыми представлениями.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-105">An interpolated string returns a string that replaces the interpolated expressions that it contains with their string representations.</span></span> <span data-ttu-id="1b7c6-106">Эта функция доступна в C# 6 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-106">This feature is available in C# 6 and later versions.</span></span>

<span data-ttu-id="1b7c6-107">Аргументы интерполированной строки понять проще, чем [строку составного формата](../../../standard/base-types/composite-formatting.md#composite-format-string).</span><span class="sxs-lookup"><span data-stu-id="1b7c6-107">The arguments of an interpolated string are easier to understand than a [composite format string](../../../standard/base-types/composite-formatting.md#composite-format-string).</span></span>  <span data-ttu-id="1b7c6-108">Например, интерполированная строка</span><span class="sxs-lookup"><span data-stu-id="1b7c6-108">For example, the interpolated string</span></span>  
  
```csharp  
Console.WriteLine($"Name = {name}, hours = {hours:hh}");
```  
<span data-ttu-id="1b7c6-109">содержит два выражения интерполированные, «{name}» и «{час: hh}».</span><span class="sxs-lookup"><span data-stu-id="1b7c6-109">contains two interpolated expressions, '{name}' and '{hour:hh}'.</span></span> <span data-ttu-id="1b7c6-110">Эквивалентная строка составного формата имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="1b7c6-110">The equivalent composite format string is:</span></span>

```csharp
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours); 
```  

<span data-ttu-id="1b7c6-111">Структура интерполированной строки выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1b7c6-111">The structure of an interpolated string is:</span></span>  
  
```  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

<span data-ttu-id="1b7c6-112">где:</span><span class="sxs-lookup"><span data-stu-id="1b7c6-112">where:</span></span> 

- <span data-ttu-id="1b7c6-113">*field-width* — это целое число со знаком, указывающее количество символов в поле.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-113">*field-width* is a signed integer that indicates the number of characters in the field.</span></span> <span data-ttu-id="1b7c6-114">Если оно является положительным, поле выравнивается по правому краю, если оно отрицательное — по левому краю.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-114">If it is positive, the field is right-aligned; if negative, left-aligned.</span></span> 

- <span data-ttu-id="1b7c6-115">*format-string* — это строка формата, соответствующая типу форматируемого объекта.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-115">*format-string* is a format string appropriate for the type of object being formatted.</span></span> <span data-ttu-id="1b7c6-116">Например, для значения <xref:System.DateTime> это может быть строка стандартного формата даты и времени, например "D" или "d".</span><span class="sxs-lookup"><span data-stu-id="1b7c6-116">For example, for a <xref:System.DateTime> value, it could be a standard date and time format string such as "D" or "d".</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b7c6-117">Не может иметь любой пробел между `$` и `"` , начинающегося в строке.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-117">You cannot have any whitespace between the `$` and the `"` that starts the string.</span></span> <span data-ttu-id="1b7c6-118">Это приводит к ошибке времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-118">Doing so causes a compile time error.</span></span>

 <span data-ttu-id="1b7c6-119">Интерполированную строку можно использовать везде, где допустимо применять строковый литерал.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-119">You can use an interpolated string anywhere you can use a string literal.</span></span>  <span data-ttu-id="1b7c6-120">Интерполированная строка вычисляется каждый раз, когда выполняется код с интерполированной строкой.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-120">The interpolated string is evaluated each time the code with the interpolated string executes.</span></span> <span data-ttu-id="1b7c6-121">Это позволяет разделить определение и вычисление интерполированной строки.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-121">This allows you to separate the definition and evaluation of an interpolated string.</span></span>  
  
 <span data-ttu-id="1b7c6-122">Чтобы включить в интерполированную строку фигурные скобки ("{" или "}"), используйте две фигурные скобки — "{{" или "}}".</span><span class="sxs-lookup"><span data-stu-id="1b7c6-122">To include a curly brace ("{" or "}") in an interpolated string, use two curly braces, "{{" or "}}".</span></span>  <span data-ttu-id="1b7c6-123">Дополнительные сведения см в разделе «Неявные преобразования».</span><span class="sxs-lookup"><span data-stu-id="1b7c6-123">See the Implicit Conversions section for more details.</span></span>  

<span data-ttu-id="1b7c6-124">Если интерполированная строка содержит другие символы со специальным значением в интерполированной строке, например, знак кавычки ("), двоеточие (:) или запятая (,), их необходимо экранировать, если они встречаются в обычном тексте, или они должны быть включены в выражение, разделенное круглыми скобками, если они являются языковыми элементами, включенными в интерполированное выражение.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-124">If the interpolated string contains other characters with special meaning in an interpolated string, such as the quotation mark ("), colon (:), or comma (,), they should be escaped if they occur in literal text, or they should be included in an expression delimited by parentheses if they are language elements included in an interpolated expression.</span></span> <span data-ttu-id="1b7c6-125">В следующем примере показано экранирование кавычек, чтобы включить их в результирующую строку, и использование скобок для разделения выражения `(age == 1 ? "" : "s")`, чтобы двоеточие не интерпретировалось как начало строки формата.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-125">The following example escapes quotation marks to include them in the result string, and it uses parentheses to delimit the expression `(age == 1 ? "" : "s")` so that the colon is not interpreted as beginning a format string.</span></span>

[!code-csharp[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings4.cs#1)]  

<span data-ttu-id="1b7c6-126">Буквально интерполируются строк, используемых `$` символов, за которым следует `@` символов.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-126">Verbatim interpolated strings use the `$` character followed by the `@` character.</span></span> <span data-ttu-id="1b7c6-127">Дополнительные сведения о строках verbatim см. в разделе [строка](string.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-127">For more information about verbatim strings, see the [string](string.md) topic.</span></span> <span data-ttu-id="1b7c6-128">Следующий код является модификацией предыдущего фрагмента с помощью verbatim интерполированные строки:</span><span class="sxs-lookup"><span data-stu-id="1b7c6-128">The following code is a modified version of the previous snippet using a verbatim interpolated string:</span></span>

[!code-csharp[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings5.cs#1)]  

<span data-ttu-id="1b7c6-129">Эти изменения необходимы, так как точные строки, которые не работают `\` escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-129">The formatting changes are necessary because verbatim strings do not obey `\` escape sequences.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b7c6-130">`$` Токен должен находиться перед `@` маркера в интерполированные буквальная строка.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-130">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>


## <a name="implicit-conversions"></a><span data-ttu-id="1b7c6-131">Неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="1b7c6-131">Implicit Conversions</span></span>  

<span data-ttu-id="1b7c6-132">Существует три преобразования неявных типов из интерполированных строк.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-132">There are three implicit type conversions from an interpolated string:</span></span>  

1. <span data-ttu-id="1b7c6-133">Преобразование интерполированной строки в <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-133">Conversion of an interpolated string to a <xref:System.String>.</span></span> <span data-ttu-id="1b7c6-134">В следующем примере возвращается строка, интерполированные строковые выражения которой были заменены их строковыми представлениями.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-134">The following example returns a string whose interpolated string expressions have been replaced with their string representations.</span></span> <span data-ttu-id="1b7c6-135">Пример:</span><span class="sxs-lookup"><span data-stu-id="1b7c6-135">For example:</span></span>

   [!code-csharp[interpolated-strings1](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings1.cs#1)]  

   <span data-ttu-id="1b7c6-136">Это окончательный результат интерпретации строк.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-136">This is the final result of a string interpretation.</span></span> <span data-ttu-id="1b7c6-137">Все вхождения двойных фигурных скобок ("{{" и "}}") преобразуются в одиночную фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-137">All occurrences of double curly braces ("{{" and "}}") are converted to a single curly brace.</span></span> 

2. <span data-ttu-id="1b7c6-138">Преобразование интерполированной строки в переменную <xref:System.IFormattable>, которая позволяет создавать несколько результирующих строк с содержимым для конкретного языка из одного экземпляра <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-138">Conversion of an interpolated string to an <xref:System.IFormattable> variable that allows you create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span> <span data-ttu-id="1b7c6-139">Это полезно для включения правильных форматов чисел и дат для отдельных языков.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-139">This is useful for including such things as the correct numeric and date formats for individual cultures.</span></span>  <span data-ttu-id="1b7c6-140">Все вхождения двойных фигурных скобок ("{{" и "}}") остаются двойными фигурными скобками до тех пор, пока строка не будет отформатирована путем явного или неявного вызова метода <xref:System.Object.ToString>.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-140">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces until you format the string by explicitly or implicitly calling the <xref:System.Object.ToString> method.</span></span>  <span data-ttu-id="1b7c6-141">Все заключенные в скобки выражения интерполяции преобразуются в {0}, \{1\} и т. д.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-141">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   <span data-ttu-id="1b7c6-142">В следующем примере используется отражение для отображения членов, а также значений поля и свойства переменной <xref:System.IFormattable>, созданной из интерполированной строки.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-142">The following example uses reflection to display the members as well as the field and property values of an <xref:System.IFormattable> variable that is created from an interpolated string.</span></span> <span data-ttu-id="1b7c6-143">Он также передает <xref:System.IFormattable> переменной <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-143">It also passes the <xref:System.IFormattable> variable to the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method.</span></span>

   [!code-csharp[interpolated-strings2](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings2.cs#1)]  

   <span data-ttu-id="1b7c6-144">Обратите внимание, что интерполированную строку можно проверить только с помощью отражения.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-144">Note that the interpolated string can be inspected only by using reflection.</span></span> <span data-ttu-id="1b7c6-145">Если оно передается строка форматирования, такие как <xref:System.Console.WriteLine(System.String)>, разрешаются элементами форматирования и возвращаются в результирующую строку.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-145">If it is passed to a string formatting method, such as <xref:System.Console.WriteLine(System.String)>, its format items are resolved and the result string returned.</span></span> 

3. <span data-ttu-id="1b7c6-146">Преобразование интерполированной строки в переменную <xref:System.FormattableString>, представляющую строку составного формата.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-146">Conversion of an interpolated string to an <xref:System.FormattableString> variable that represents a composite format string.</span></span> <span data-ttu-id="1b7c6-147">Проверка строки составного формата и способа ее отрисовки в виде результирующей строки может, например, обеспечивать защиту от атак путем внедрения кода, если выполнялось построение запроса.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-147">Inspecting the composite format string and how it renders as a result string might, for example, help you protect against an injection attack if you were building a query.</span></span> <span data-ttu-id="1b7c6-148"><xref:System.FormattableString> также включает перегрузки <xref:System.FormattableString.ToString>, позволяющие создавать результирующие строки для <xref:System.Globalization.CultureInfo.InvariantCulture> и <xref:System.Globalization.CultureInfo.CurrentCulture>.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-148"><xref:System.FormattableString> also includes <xref:System.FormattableString.ToString> overloads that let you produce result strings for the <xref:System.Globalization.CultureInfo.InvariantCulture> and <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>  <span data-ttu-id="1b7c6-149">Все вхождения двойных фигурных скобок ("{{" и "}}") остаются двойными фигурными скобками, пока не будет выполнено форматирование.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-149">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces, until you format.</span></span>  <span data-ttu-id="1b7c6-150">Все заключенные в скобки выражения интерполяции преобразуются в {0}, \{1\} и т. д.</span><span class="sxs-lookup"><span data-stu-id="1b7c6-150">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   [!code-csharp[interpolated-strings3](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings3.cs#1)]  

## <a name="language-specification"></a><span data-ttu-id="1b7c6-151">Спецификация языка</span><span class="sxs-lookup"><span data-stu-id="1b7c6-151">Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1b7c6-152">См. также</span><span class="sxs-lookup"><span data-stu-id="1b7c6-152">See Also</span></span>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 [<span data-ttu-id="1b7c6-153">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="1b7c6-153">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1b7c6-154">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1b7c6-154">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
