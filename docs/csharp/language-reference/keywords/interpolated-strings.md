---
title: "Интерполированные строки (C#)"
ms.date: 2017-02-03
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 324f267e-1c61-431a-97ed-852c1530742d
caps.latest.revision: 9
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 03d1e3f0897713e25be7d7f893861a3eb4dac211
ms.openlocfilehash: ee35da0a008a19ad643fffff64d74485237d716f
ms.contentlocale: ru-ru
ms.lasthandoff: 09/11/2017

---
# <a name="interpolated-strings-c-reference"></a><span data-ttu-id="c5bb6-102">Интерполированные строки (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c5bb6-102">Interpolated Strings (C# Reference)</span></span>

<span data-ttu-id="c5bb6-103">Используется для создания строк.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-103">Used to construct strings.</span></span>  <span data-ttu-id="c5bb6-104">Интерполированное строковое выражение выглядит как строка шаблона, которая содержит *интерполированные выражения*.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-104">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span>  <span data-ttu-id="c5bb6-105">Интерполированная строка возвращает строку, которая заменяет содержащиеся в ней интерполированные выражения строковыми представлениями.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-105">An interpolated string returns a string that replaces the interpolated expressions that it contains with their string representations.</span></span>  

<span data-ttu-id="c5bb6-106">Аргументы интерполированной строки понять проще, чем [строку составного формата](../../../standard/base-types/composite-formatting.md#composite-format-string).</span><span class="sxs-lookup"><span data-stu-id="c5bb6-106">The arguments of an interpolated string are easier to understand than a [composite format string](../../../standard/base-types/composite-formatting.md#composite-format-string).</span></span>  <span data-ttu-id="c5bb6-107">Например, интерполированная строка</span><span class="sxs-lookup"><span data-stu-id="c5bb6-107">For example, the interpolated string</span></span>  
  
```csharp  
Console.WriteLine($"Name = {name}, hours = {hours:hh}"); 
```  
<span data-ttu-id="c5bb6-108">содержит два интерполированных выражения "{name}" и "{hours:hh}".</span><span class="sxs-lookup"><span data-stu-id="c5bb6-108">contains two interpolated expressions, '{name}' and '{hours:hh}'.</span></span> <span data-ttu-id="c5bb6-109">Эквивалентная строка составного формата имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="c5bb6-109">The equivalent composite format string is:</span></span>

```csharp
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours);  
```  

<span data-ttu-id="c5bb6-110">Структура интерполированной строки выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c5bb6-110">The structure of an interpolated string is:</span></span>  
  
```  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

<span data-ttu-id="c5bb6-111">где:</span><span class="sxs-lookup"><span data-stu-id="c5bb6-111">where:</span></span> 

- <span data-ttu-id="c5bb6-112">*field-width* — это целое число со знаком, указывающее количество символов в поле.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-112">*field-width* is a signed integer that indicates the number of characters in the field.</span></span> <span data-ttu-id="c5bb6-113">Если оно является положительным, поле выравнивается по правому краю, если оно отрицательное — по левому краю.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-113">If it is positive, the field is right-aligned; if negative, left-aligned.</span></span> 

- <span data-ttu-id="c5bb6-114">*format-string* — это строка формата, соответствующая типу форматируемого объекта.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-114">*format-string* is a format string appropriate for the type of object being formatted.</span></span> <span data-ttu-id="c5bb6-115">Например, для значения @System.DateTime это может быть строка стандартного формата даты и времени, например "D" или "d".</span><span class="sxs-lookup"><span data-stu-id="c5bb6-115">For example, for a @System.DateTime value, it could be a standard date and time format string such as "D" or "d".</span></span>

 <span data-ttu-id="c5bb6-116">Интерполированную строку можно использовать везде, где допустимо применять строковый литерал.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-116">You can use an interpolated string anywhere you can use a string literal.</span></span>  <span data-ttu-id="c5bb6-117">Интерполированная строка вычисляется каждый раз, когда выполняется код с интерполированной строкой.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-117">The interpolated string is evaluated each time the code with the interpolated string executes.</span></span> <span data-ttu-id="c5bb6-118">Это позволяет разделить определение и вычисление интерполированной строки.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-118">This allows you to separate the definition and evaluation of an interpolated string.</span></span>  
  
 <span data-ttu-id="c5bb6-119">Чтобы включить в интерполированную строку фигурные скобки ("{" или "}"), используйте две фигурные скобки — "{{" или "}}".</span><span class="sxs-lookup"><span data-stu-id="c5bb6-119">To include a curly brace ("{" or "}") in an interpolated string, use two curly braces, "{{" or "}}".</span></span>  <span data-ttu-id="c5bb6-120">Дополнительные сведения см в разделе «Неявные преобразования».</span><span class="sxs-lookup"><span data-stu-id="c5bb6-120">See the Implicit Conversions section for more details.</span></span>  

<span data-ttu-id="c5bb6-121">Если интерполированная строка содержит другие символы со специальным значением в интерполированной строке, например, знак кавычки ("), двоеточие (:) или запятая (,), их необходимо экранировать, если они встречаются в обычном тексте, или они должны быть включены в выражение, разделенное круглыми скобками, если они являются языковыми элементами, включенными в интерполированное выражение.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-121">If the interpolated string contains other characters with special meaning in an interpolated string, such as the quotation mark ("), colon (:), or comma (,), they should be escaped if they occur in literal text, or they should be included in an expression delimited by parentheses if they are language elements included in an interpolated expression.</span></span> <span data-ttu-id="c5bb6-122">В следующем примере показано экранирование кавычек, чтобы включить их в результирующую строку, и использование скобок для разделения выражения `(age == 1 ? "" : "s")`, чтобы двоеточие не интерпретировалось как начало строки формата.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-122">The following example escapes quotation marks to include them in the result string, and it uses parentheses to delimit the expression `(age == 1 ? "" : "s")` so that the colon is not interpreted as beginning a format string.</span></span>

<span data-ttu-id="c5bb6-123">[!code-cs[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings4.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c5bb6-123">[!code-cs[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings4.cs#1)]</span></span>  

## <a name="implicit-conversions"></a><span data-ttu-id="c5bb6-124">Неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="c5bb6-124">Implicit Conversions</span></span>  

<span data-ttu-id="c5bb6-125">Существует три преобразования неявных типов из интерполированных строк.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-125">There are three implicit type conversions from an interpolated string:</span></span>  

1. <span data-ttu-id="c5bb6-126">Преобразование интерполированной строки в @System.String.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-126">Conversion of an interpolated string to a @System.String.</span></span> <span data-ttu-id="c5bb6-127">В следующем примере возвращается строка, интерполированные строковые выражения которой были заменены их строковыми представлениями.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-127">The following example returns a string whose interpolated string expressions have been replaced with their string representations.</span></span> <span data-ttu-id="c5bb6-128">Пример:</span><span class="sxs-lookup"><span data-stu-id="c5bb6-128">For example:</span></span>

   <span data-ttu-id="c5bb6-129">[!code-cs[interpolated-strings1](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c5bb6-129">[!code-cs[interpolated-strings1](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings1.cs#1)]</span></span>  

   <span data-ttu-id="c5bb6-130">Это окончательный результат интерпретации строк.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-130">This is the final result of a string interpretation.</span></span> <span data-ttu-id="c5bb6-131">Все вхождения двойных фигурных скобок ("{{" и "}}") преобразуются в одиночную фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-131">All occurrences of double curly braces ("{{" and "}}") are converted to a single curly brace.</span></span> 

2. <span data-ttu-id="c5bb6-132">Преобразование интерполированной строки в переменную <xref:System.IFormattable>, которая позволяет создавать несколько результирующих строк с содержимым для конкретного языка из одного экземпляра <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-132">Conversion of an interpolated string to an <xref:System.IFormattable> variable that allows you create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span> <span data-ttu-id="c5bb6-133">Это полезно для включения правильных форматов чисел и дат для отдельных языков.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-133">This is useful for including such things as the correct numeric and date formats for individual cultures.</span></span>  <span data-ttu-id="c5bb6-134">Все вхождения двойных фигурных скобок ("{{" и "}}") остаются двойными фигурными скобками до тех пор, пока строка не будет отформатирована путем явного или неявного вызова метода @System.Object.ToString.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-134">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces until you format the string by explicitly or implicitly calling the @System.Object.ToString method.</span></span>  <span data-ttu-id="c5bb6-135">Все заключенные в скобки выражения интерполяции преобразуются в {0}, \{1\} и т. д.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-135">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   <span data-ttu-id="c5bb6-136">В следующем примере используется отражение для отображения членов, а также значений поля и свойства переменной <xref:System.IFormattable>, созданной из интерполированной строки.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-136">The following example uses reflection to display the members as well as the field and property values of an <xref:System.IFormattable> variable that is created from an interpolated string.</span></span> <span data-ttu-id="c5bb6-137">Кроме того, здесь переменная <xref:System.IFormattable> передается в метод @System.Console(System.String).</span><span class="sxs-lookup"><span data-stu-id="c5bb6-137">It also passes the <xref:System.IFormattable> variable to the @System.Console(System.String) method.</span></span>

   <span data-ttu-id="c5bb6-138">[!code-cs[interpolated-strings2](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings2.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c5bb6-138">[!code-cs[interpolated-strings2](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings2.cs#1)]</span></span>  

   <span data-ttu-id="c5bb6-139">Обратите внимание, что интерполированную строку можно проверить только с помощью отражения.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-139">Note that the interpolated string can be inspected only by using reflection.</span></span> <span data-ttu-id="c5bb6-140">Если она передается в метод форматирования строк, такой как @System.Console.WriteLine(System.String), происходит разрешение элементов форматирования и возвращается результирующая строка.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-140">If it is passed to a string formatting method, such as @System.Console.WriteLine(System.String), its format items are resolved and the result string returned.</span></span> 

3. <span data-ttu-id="c5bb6-141">Преобразование интерполированной строки в переменную <xref:System.FormattableString>, представляющую строку составного формата.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-141">Conversion of an interpolated string to an <xref:System.FormattableString> variable that represents a composite format string.</span></span> <span data-ttu-id="c5bb6-142">Проверка строки составного формата и способа ее отрисовки в виде результирующей строки может, например, обеспечивать защиту от атак путем внедрения кода, если выполнялось построение запроса.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-142">Inspecting the composite format string and how it renders as a result string might, for example, help you protect against an injection attack if you were building a query.</span></span>  <span data-ttu-id="c5bb6-143"><xref:System.FormattableString> также включает перегрузки <xref:System.FormattableString.ToString>, позволяющие создавать результирующие строки для @System.Globalization.InvariantCulture и @System.Globalization.CurrentCulture.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-143"><xref:System.FormattableString> also includes <xref:System.FormattableString.ToString> overloads that let you produce result strings for the @System.Globalization.InvariantCulture and @System.Globalization.CurrentCulture.</span></span>  <span data-ttu-id="c5bb6-144">Все вхождения двойных фигурных скобок ("{{" и "}}") остаются двойными фигурными скобками, пока не будет выполнено форматирование.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-144">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces, until you format.</span></span>  <span data-ttu-id="c5bb6-145">Все заключенные в скобки выражения интерполяции преобразуются в {0}, \{1\} и т. д.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-145">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   <span data-ttu-id="c5bb6-146">[!code-cs[interpolated-strings3](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings3.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c5bb6-146">[!code-cs[interpolated-strings3](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings3.cs#1)]</span></span>  

## <a name="language-specification"></a><span data-ttu-id="c5bb6-147">Спецификация языка</span><span class="sxs-lookup"><span data-stu-id="c5bb6-147">Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c5bb6-148">См. также</span><span class="sxs-lookup"><span data-stu-id="c5bb6-148">See Also</span></span>  
 <span data-ttu-id="c5bb6-149"><xref:System.IFormattable?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c5bb6-149"><xref:System.IFormattable?displayProperty=fullName></span></span>   
 <span data-ttu-id="c5bb6-150"><xref:System.FormattableString?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c5bb6-150"><xref:System.FormattableString?displayProperty=fullName></span></span>   
 <span data-ttu-id="c5bb6-151">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c5bb6-151">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="c5bb6-152">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c5bb6-152">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

