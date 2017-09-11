---
title: "Соглашения о написании кода на C# (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9f32fdc0eb1954cdac30c39e05c74d43301d850c
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="c-coding-conventions-c-programming-guide"></a><span data-ttu-id="87f21-102">Соглашения о написании кода на C# (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="87f21-102">C# Coding Conventions (C# Programming Guide)</span></span>
<span data-ttu-id="87f21-103">[Спецификация языка C#](http://go.microsoft.com/fwlink/?LinkId=199552) не определяет стандарт кодирования.</span><span class="sxs-lookup"><span data-stu-id="87f21-103">The [C# Language Specification](http://go.microsoft.com/fwlink/?LinkId=199552) does not define a coding standard.</span></span> <span data-ttu-id="87f21-104">Однако корпорация Майкрософт использует приведенные в этом разделе рекомендации для разработки примеров и документации.</span><span class="sxs-lookup"><span data-stu-id="87f21-104">However, the guidelines in this topic are used by Microsoft to develop samples and documentation.</span></span>  
  
 <span data-ttu-id="87f21-105">Соглашения о написании кода предназначены для реализации следующих целей.</span><span class="sxs-lookup"><span data-stu-id="87f21-105">Coding conventions serve the following purposes:</span></span>  
  
-   <span data-ttu-id="87f21-106">Создание согласованного вида кода, позволяющего читателям сосредоточиться на содержимом, а не на структуре.</span><span class="sxs-lookup"><span data-stu-id="87f21-106">They create a consistent look to the code, so that readers can focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="87f21-107">Предоставление читателям возможности делать предположения, основанные на опыте, и поэтому быстрее понимать код.</span><span class="sxs-lookup"><span data-stu-id="87f21-107">They enable readers to understand the code more quickly by making assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="87f21-108">Упрощение процессов копирования, изменения и обслуживания кода.</span><span class="sxs-lookup"><span data-stu-id="87f21-108">They facilitate copying, changing, and maintaining the code.</span></span>  
  
-   <span data-ttu-id="87f21-109">Предоставление лучших методик C#.</span><span class="sxs-lookup"><span data-stu-id="87f21-109">They demonstrate C# best practices.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="87f21-110">Соглашения об именах</span><span class="sxs-lookup"><span data-stu-id="87f21-110">Naming Conventions</span></span>  
  
-   <span data-ttu-id="87f21-111">В коротких примерах, не содержащих [директив using](../../../csharp/language-reference/keywords/using-directive.md), рекомендуется использовать полные указания для пространства имен.</span><span class="sxs-lookup"><span data-stu-id="87f21-111">In short examples that do not include [using directives](../../../csharp/language-reference/keywords/using-directive.md), use namespace qualifications.</span></span> <span data-ttu-id="87f21-112">Если известно, что пространство имен импортировано в проект по умолчанию, не требуется указывать полные имена из этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="87f21-112">If you know that a namespace is imported by default in a project, you do not have to fully qualify the names from that namespace.</span></span> <span data-ttu-id="87f21-113">Полные имена, если они слишком длинные для одной строки, можно разбить после точки (.), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="87f21-113">Qualified names can be broken after a dot (.) if they are too long for a single line, as shown in the following example.</span></span>  
  
     <span data-ttu-id="87f21-114">[!code-cs[csProgGuideCodingConventions#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-114">[!code-cs[csProgGuideCodingConventions#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_1.cs)]</span></span>  
  
-   <span data-ttu-id="87f21-115">Нет необходимости изменять имена объектов, созданных с помощью инструментов разработки Visual Studio, чтобы привести их в соответствие с другими соглашениями.</span><span class="sxs-lookup"><span data-stu-id="87f21-115">You do not have to change the names of objects that were created by using the Visual Studio designer tools to make them fit other guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="87f21-116">Соглашения о расположении</span><span class="sxs-lookup"><span data-stu-id="87f21-116">Layout Conventions</span></span>  
 <span data-ttu-id="87f21-117">Чтобы выделить структуру кода и облегчить чтение кода, в хорошем макете используется форматирование.</span><span class="sxs-lookup"><span data-stu-id="87f21-117">Good layout uses formatting to emphasize the structure of your code and to make the code easier to read.</span></span> <span data-ttu-id="87f21-118">Примеры и образцы корпорации Майкрософт соответствуют следующим соглашениям.</span><span class="sxs-lookup"><span data-stu-id="87f21-118">Microsoft examples and samples conform to the following conventions:</span></span>  
  
-   <span data-ttu-id="87f21-119">Использование параметров редактора кода по умолчанию (логичные отступы, отступы по четыре символа, использование пробелов для табуляции).</span><span class="sxs-lookup"><span data-stu-id="87f21-119">Use the default Code Editor settings (smart indenting, four-character indents, tabs saved as spaces).</span></span> <span data-ttu-id="87f21-120">Дополнительные сведения см. в разделе ["Параметры", "Текстовый редактор", C#, "Форматирование"](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span><span class="sxs-lookup"><span data-stu-id="87f21-120">For more information, see [Options, Text Editor, C#, Formatting](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span></span>  
  
-   <span data-ttu-id="87f21-121">Запись только одного оператора в строке.</span><span class="sxs-lookup"><span data-stu-id="87f21-121">Write only one statement per line.</span></span>  
  
-   <span data-ttu-id="87f21-122">Запись только одного объявления в строке.</span><span class="sxs-lookup"><span data-stu-id="87f21-122">Write only one declaration per line.</span></span>  
  
-   <span data-ttu-id="87f21-123">Если отступ для дополнительных строк не ставится автоматически, необходимо сделать для них отступ на одну позицию табуляции (четыре пробела).</span><span class="sxs-lookup"><span data-stu-id="87f21-123">If continuation lines are not indented automatically, indent them one tab stop (four spaces).</span></span>  
  
-   <span data-ttu-id="87f21-124">Добавление по крайней мере одной пустой строки между определениями методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="87f21-124">Add at least one blank line between method definitions and property definitions.</span></span>  
  
-   <span data-ttu-id="87f21-125">Использование скобок для ясности предложений в выражениях, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="87f21-125">Use parentheses to make clauses in an expression apparent, as shown in the following code.</span></span>  
  
     <span data-ttu-id="87f21-126">[!code-cs[csProgGuideCodingConventions#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-126">[!code-cs[csProgGuideCodingConventions#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_2.cs)]</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="87f21-127">Соглашения о комментариях</span><span class="sxs-lookup"><span data-stu-id="87f21-127">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="87f21-128">Комментарий размещается на отдельной строке, а не в конце строки кода.</span><span class="sxs-lookup"><span data-stu-id="87f21-128">Place the comment on a separate line, not at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="87f21-129">Текст комментария начинается с заглавной буквы.</span><span class="sxs-lookup"><span data-stu-id="87f21-129">Begin comment text with an uppercase letter.</span></span>  
  
-   <span data-ttu-id="87f21-130">Текст комментария завершается точкой.</span><span class="sxs-lookup"><span data-stu-id="87f21-130">End comment text with a period.</span></span>  
  
-   <span data-ttu-id="87f21-131">Между разделителем комментария (/ /) и текстом комментария вставляется один пробел, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="87f21-131">Insert one space between the comment delimiter (//) and the comment text, as shown in the following example.</span></span>  
  
     <span data-ttu-id="87f21-132">[!code-cs[csProgGuideCodingConventions#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-132">[!code-cs[csProgGuideCodingConventions#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_3.cs)]</span></span>  
  
-   <span data-ttu-id="87f21-133">Вокруг комментариев не должно быть звездочек.</span><span class="sxs-lookup"><span data-stu-id="87f21-133">Do not create formatted blocks of asterisks around comments.</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="87f21-134">Рекомендации по работе с языком</span><span class="sxs-lookup"><span data-stu-id="87f21-134">Language Guidelines</span></span>  
 <span data-ttu-id="87f21-135">В следующих подразделах описаны методики, которыми руководствуется команда C# для подготовки примеров и образцов кода.</span><span class="sxs-lookup"><span data-stu-id="87f21-135">The following sections describe practices that the C# team follows to prepare code examples and samples.</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="87f21-136">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="87f21-136">String Data Type</span></span>  
  
-   <span data-ttu-id="87f21-137">Для сцепления коротких строк рекомендуется использовать оператор `+`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="87f21-137">Use the `+` operator to concatenate short strings, as shown in the following code.</span></span>  
  
     <span data-ttu-id="87f21-138">[!code-cs[csProgGuideCodingConventions#6](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-138">[!code-cs[csProgGuideCodingConventions#6](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_4.cs)]</span></span>  
  
-   <span data-ttu-id="87f21-139">Для добавления строк в циклы, особенно при работе с текстами больших размеров, рекомендуется использовать объект <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="87f21-139">To append strings in loops, especially when you are working with large amounts of text, use a <xref:System.Text.StringBuilder> object.</span></span>  
  
     <span data-ttu-id="87f21-140">[!code-cs[csProgGuideCodingConventions#7](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-140">[!code-cs[csProgGuideCodingConventions#7](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_5.cs)]</span></span>  
  
### <a name="implicitly-typed-local-variables"></a><span data-ttu-id="87f21-141">Неявно типизированные локальные переменные</span><span class="sxs-lookup"><span data-stu-id="87f21-141">Implicitly Typed Local Variables</span></span>  
  
-   <span data-ttu-id="87f21-142">В случаях, когда тип переменной понятен из правой части назначения или когда точный тип не важен, рекомендуется использовать [неявное типизирование](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) для локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="87f21-142">Use [implicit typing](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) for local variables when the type of the variable is obvious from the right side of the assignment, or when the precise type is not important.</span></span>  
  
     <span data-ttu-id="87f21-143">[!code-cs[csProgGuideCodingConventions#8](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-143">[!code-cs[csProgGuideCodingConventions#8](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_6.cs)]</span></span>  
  
-   <span data-ttu-id="87f21-144">Если тип из правой части назначения не является очевидным, не рекомендуется использовать [var](../../../csharp/language-reference/keywords/var.md).</span><span class="sxs-lookup"><span data-stu-id="87f21-144">Do not use [var](../../../csharp/language-reference/keywords/var.md) when the type is not apparent from the right side of the assignment.</span></span>  
  
     <span data-ttu-id="87f21-145">[!code-cs[csProgGuideCodingConventions#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-145">[!code-cs[csProgGuideCodingConventions#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_7.cs)]</span></span>  
  
-   <span data-ttu-id="87f21-146">При указании типа переменной не следует полагаться на имя переменной.</span><span class="sxs-lookup"><span data-stu-id="87f21-146">Do not rely on the variable name to specify the type of the variable.</span></span> <span data-ttu-id="87f21-147">Имя может быть неверным.</span><span class="sxs-lookup"><span data-stu-id="87f21-147">It might not be correct.</span></span>  
  
     <span data-ttu-id="87f21-148">[!code-cs[csProgGuideCodingConventions#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-148">[!code-cs[csProgGuideCodingConventions#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_8.cs)]</span></span>  
  
-   <span data-ttu-id="87f21-149">Рекомендуется избегать использования `var` вместо [dynamic](../../../csharp/language-reference/keywords/dynamic.md).</span><span class="sxs-lookup"><span data-stu-id="87f21-149">Avoid the use of `var` in place of [dynamic](../../../csharp/language-reference/keywords/dynamic.md).</span></span>  
  
-   <span data-ttu-id="87f21-150">Рекомендуется использовать неявное типизирование для определения типа переменной цикла в циклах [for](../../../csharp/language-reference/keywords/for.md) и [foreach](../../../csharp/language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="87f21-150">Use implicit typing to determine the type of the loop variable in [for](../../../csharp/language-reference/keywords/for.md) and [foreach](../../../csharp/language-reference/keywords/foreach-in.md) loops.</span></span>  
  
     <span data-ttu-id="87f21-151">В следующем примере неявное типизирование используется в операторе `for`.</span><span class="sxs-lookup"><span data-stu-id="87f21-151">The following example uses implicit typing in a `for` statement.</span></span>  
  
     <span data-ttu-id="87f21-152">[!code-cs[csProgGuideCodingConventions#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-152">[!code-cs[csProgGuideCodingConventions#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_9.cs)]</span></span>  
  
     <span data-ttu-id="87f21-153">В следующем примере неявное типизирование используется в операторе `foreach`.</span><span class="sxs-lookup"><span data-stu-id="87f21-153">The following example uses implicit typing in a `foreach` statement.</span></span>  
  
     <span data-ttu-id="87f21-154">[!code-cs[csProgGuideCodingConventions#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-154">[!code-cs[csProgGuideCodingConventions#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_10.cs)]</span></span>  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="87f21-155">Беззнаковый тип данных</span><span class="sxs-lookup"><span data-stu-id="87f21-155">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="87f21-156">Как правило, рекомендуется использовать `int` вместо беззнаковых типов.</span><span class="sxs-lookup"><span data-stu-id="87f21-156">In general, use `int` rather than unsigned types.</span></span> <span data-ttu-id="87f21-157">В C# обычно используется `int`. Использование `int` упрощает взаимодействие с другими библиотеками.</span><span class="sxs-lookup"><span data-stu-id="87f21-157">The use of `int` is common throughout C#, and it is easier to interact with other libraries when you use `int`.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="87f21-158">Массивы</span><span class="sxs-lookup"><span data-stu-id="87f21-158">Arrays</span></span>  
  
-   <span data-ttu-id="87f21-159">При инициализации массивов в строке объявления рекомендуется использовать сокращенный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="87f21-159">Use the concise syntax when you initialize arrays on the declaration line.</span></span>  
  
     <span data-ttu-id="87f21-160">[!code-cs[csProgGuideCodingConventions#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_11.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-160">[!code-cs[csProgGuideCodingConventions#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_11.cs)]</span></span>  
  
### <a name="delegates"></a><span data-ttu-id="87f21-161">Делегаты</span><span class="sxs-lookup"><span data-stu-id="87f21-161">Delegates</span></span>  
  
-   <span data-ttu-id="87f21-162">Для создания экземпляров типа делегата рекомендуется использовать сокращенный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="87f21-162">Use the concise syntax to create instances of a delegate type.</span></span>  
  
     <span data-ttu-id="87f21-163">[!code-cs[csProgGuideCodingConventions#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_12.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-163">[!code-cs[csProgGuideCodingConventions#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_12.cs)]</span></span>  
  
     <span data-ttu-id="87f21-164">[!code-cs[csProgGuideCodingConventions#15](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_13.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-164">[!code-cs[csProgGuideCodingConventions#15](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_13.cs)]</span></span>  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a><span data-ttu-id="87f21-165">Операторы try-catch и using в процессе обработки исключений</span><span class="sxs-lookup"><span data-stu-id="87f21-165">try-catch and using Statements in Exception Handling</span></span>  
  
-   <span data-ttu-id="87f21-166">Рекомендуется использовать оператор [try-catch](../../../csharp/language-reference/keywords/try-catch.md) для обработки большей части исключений.</span><span class="sxs-lookup"><span data-stu-id="87f21-166">Use a [try-catch](../../../csharp/language-reference/keywords/try-catch.md) statement for most exception handling.</span></span>  
  
     <span data-ttu-id="87f21-167">[!code-cs[csProgGuideCodingConventions#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_14.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-167">[!code-cs[csProgGuideCodingConventions#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_14.cs)]</span></span>  
  
-   <span data-ttu-id="87f21-168">Использование [оператора C# using](../../../csharp/language-reference/keywords/using-statement.md) упрощает код.</span><span class="sxs-lookup"><span data-stu-id="87f21-168">Simplify your code by using the C# [using statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span> <span data-ttu-id="87f21-169">При наличии оператора [try-finally](../../../csharp/language-reference/keywords/try-finally.md), код которого в блоке `finally` содержит только вызов метода <xref:System.IDisposable.Dispose%2A>, вместо него рекомендуется использовать оператор `using`.</span><span class="sxs-lookup"><span data-stu-id="87f21-169">If you have a [try-finally](../../../csharp/language-reference/keywords/try-finally.md) statement in which the only code in the `finally` block is a call to the <xref:System.IDisposable.Dispose%2A> method, use a `using` statement instead.</span></span>  
  
     <span data-ttu-id="87f21-170">[!code-cs[csProgGuideCodingConventions#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_15.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-170">[!code-cs[csProgGuideCodingConventions#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_15.cs)]</span></span>  
  
### <a name="-and-124124-operators"></a><span data-ttu-id="87f21-171">Операторы && и ||</span><span class="sxs-lookup"><span data-stu-id="87f21-171">&& and &#124;&#124; Operators</span></span>  
  
-   <span data-ttu-id="87f21-172">Чтобы избежать возникновения исключений и увеличить производительность за счет пропуска необязательных сравнений, рекомендуется использовать [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) вместо [&](../../../csharp/language-reference/operators/and-operator.md) и [||](../../../csharp/language-reference/operators/conditional-or-operator.md) вместо [|](../../../csharp/language-reference/operators/or-operator.md) при выполнении сравнений, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="87f21-172">To avoid exceptions and increase performance by skipping unnecessary comparisons, use [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) instead of [&](../../../csharp/language-reference/operators/and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) instead of [&#124;](../../../csharp/language-reference/operators/or-operator.md) when you perform comparisons, as shown in the following example.</span></span>  
  
     <span data-ttu-id="87f21-173">[!code-cs[csProgGuideCodingConventions#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_16.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-173">[!code-cs[csProgGuideCodingConventions#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_16.cs)]</span></span>  
  
### <a name="new-operator"></a><span data-ttu-id="87f21-174">Оператор New</span><span class="sxs-lookup"><span data-stu-id="87f21-174">New Operator</span></span>  
  
-   <span data-ttu-id="87f21-175">Рекомендуется использовать сокращенную форму создания экземпляра для объекта с неявным типизированием, как показано в следующем объявлении.</span><span class="sxs-lookup"><span data-stu-id="87f21-175">Use the concise form of object instantiation, with implicit typing, as shown in the following declaration.</span></span>  
  
     <span data-ttu-id="87f21-176">[!code-cs[csProgGuideCodingConventions#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_17.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-176">[!code-cs[csProgGuideCodingConventions#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_17.cs)]</span></span>  
  
     <span data-ttu-id="87f21-177">Предыдущая строка соответствует следующему объявлению.</span><span class="sxs-lookup"><span data-stu-id="87f21-177">The previous line is equivalent to the following declaration.</span></span>  
  
     <span data-ttu-id="87f21-178">[!code-cs[csProgGuideCodingConventions#20](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_18.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-178">[!code-cs[csProgGuideCodingConventions#20](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_18.cs)]</span></span>  
  
-   <span data-ttu-id="87f21-179">Рекомендуется использовать инициализаторы объектов для упрощения создания объектов.</span><span class="sxs-lookup"><span data-stu-id="87f21-179">Use object initializers to simplify object creation.</span></span>  
  
     <span data-ttu-id="87f21-180">[!code-cs[csProgGuideCodingConventions#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_19.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-180">[!code-cs[csProgGuideCodingConventions#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_19.cs)]</span></span>  
  
### <a name="event-handling"></a><span data-ttu-id="87f21-181">Обработка событий</span><span class="sxs-lookup"><span data-stu-id="87f21-181">Event Handling</span></span>  
  
-   <span data-ttu-id="87f21-182">При определении обработчика событий, которого не требуется удалять позднее, рекомендуется использовать лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="87f21-182">If you are defining an event handler that you do not need to remove later, use a lambda expression.</span></span>  
  
     <span data-ttu-id="87f21-183">[!code-cs[csProgGuideCodingConventions#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_20.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-183">[!code-cs[csProgGuideCodingConventions#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_20.cs)]</span></span>  
  
     <span data-ttu-id="87f21-184">[!code-cs[csProgGuideCodingConventions#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_21.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-184">[!code-cs[csProgGuideCodingConventions#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_21.cs)]</span></span>  
  
### <a name="static-members"></a><span data-ttu-id="87f21-185">Статический члены</span><span class="sxs-lookup"><span data-stu-id="87f21-185">Static Members</span></span>  
  
-   <span data-ttu-id="87f21-186">Для вызова [статических](../../../csharp/language-reference/keywords/static.md) членов следует использовать имя класса: *ClassName.StaticMember*.</span><span class="sxs-lookup"><span data-stu-id="87f21-186">Call [static](../../../csharp/language-reference/keywords/static.md) members by using the class name: *ClassName.StaticMember*.</span></span> <span data-ttu-id="87f21-187">В этом случае код становится более удобочитаемым за счет четкого доступа.</span><span class="sxs-lookup"><span data-stu-id="87f21-187">This practice makes code more readable by making static access clear.</span></span>  <span data-ttu-id="87f21-188">Не присваивайте статическому члену, определенному в базовом классе, имя производного класса.</span><span class="sxs-lookup"><span data-stu-id="87f21-188">Do not qualify a static member defined in a base class with the name of a derived class.</span></span>  <span data-ttu-id="87f21-189">Во время компиляции кода его читаемость нарушается, и если добавить статический член с тем же именем в производный классе, код может быть поврежден.</span><span class="sxs-lookup"><span data-stu-id="87f21-189">While that code compiles, the code readability is misleading, and the code may break in the future if you add a static member with the same name to the derived class.</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="87f21-190">Запросы LINQ</span><span class="sxs-lookup"><span data-stu-id="87f21-190">LINQ Queries</span></span>  
  
-   <span data-ttu-id="87f21-191">Используйте значимые имена для переменных запроса.</span><span class="sxs-lookup"><span data-stu-id="87f21-191">Use meaningful names for query variables.</span></span> <span data-ttu-id="87f21-192">В следующем примере используется `seattleCustomers` для клиентов, находящихся в Сиэтле.</span><span class="sxs-lookup"><span data-stu-id="87f21-192">The following example uses `seattleCustomers` for customers who are located in Seattle.</span></span>  
  
     <span data-ttu-id="87f21-193">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-193">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span></span>  
  
-   <span data-ttu-id="87f21-194">Рекомендуется использовать псевдонимы для уверенности в том, что в именах свойств анонимных типов верно используются прописные буквы при помощи правил использования прописных и строчных букв языка Pascal.</span><span class="sxs-lookup"><span data-stu-id="87f21-194">Use aliases to make sure that property names of anonymous types are correctly capitalized, using Pascal casing.</span></span>  
  
     <span data-ttu-id="87f21-195">[!code-cs[csProgGuideCodingConventions#26](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_23.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-195">[!code-cs[csProgGuideCodingConventions#26](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_23.cs)]</span></span>  
  
-   <span data-ttu-id="87f21-196">Переименуйте свойства, если имена свойств в результате могут быть неоднозначными.</span><span class="sxs-lookup"><span data-stu-id="87f21-196">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="87f21-197">Например, если запрос возвращает имя клиента и идентификатор распространителя, не оставляйте имена в виде `Name` и `ID`, а переименуйте их, чтобы было ясно, что `Name` — имя клиента и `ID` — идентификатор распространителя.</span><span class="sxs-lookup"><span data-stu-id="87f21-197">For example, if your query returns a customer name and a distributor ID, instead of leaving them as `Name` and `ID` in the result, rename them to clarify that `Name` is the name of a customer, and `ID` is the ID of a distributor.</span></span>  
  
     <span data-ttu-id="87f21-198">[!code-cs[csProgGuideCodingConventions#27](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_24.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-198">[!code-cs[csProgGuideCodingConventions#27](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_24.cs)]</span></span>  
  
-   <span data-ttu-id="87f21-199">Рекомендуется использовать неявное типизирование в объявлении переменных запроса и переменных диапазона.</span><span class="sxs-lookup"><span data-stu-id="87f21-199">Use implicit typing in the declaration of query variables and range variables.</span></span>  
  
     <span data-ttu-id="87f21-200">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-200">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span></span>  
  
-   <span data-ttu-id="87f21-201">Выравнивайте предложения запроса под предложением [from](../../../csharp/language-reference/keywords/from-clause.md), как показано в предыдущих примерах.</span><span class="sxs-lookup"><span data-stu-id="87f21-201">Align query clauses under the [from](../../../csharp/language-reference/keywords/from-clause.md) clause, as shown in the previous examples.</span></span>  
  
-   <span data-ttu-id="87f21-202">Чтобы гарантировать, что более поздние предложения запроса работают с ограниченным, отфильтрованным набором данных, используйте предложение [where](../../../csharp/language-reference/keywords/where-clause.md) перед другими предложениями запроса.</span><span class="sxs-lookup"><span data-stu-id="87f21-202">Use [where](../../../csharp/language-reference/keywords/where-clause.md) clauses before other query clauses to ensure that later query clauses operate on the reduced, filtered set of data.</span></span>  
  
     <span data-ttu-id="87f21-203">[!code-cs[csProgGuideCodingConventions#29](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_25.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-203">[!code-cs[csProgGuideCodingConventions#29](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_25.cs)]</span></span>  
  
-   <span data-ttu-id="87f21-204">Используйте несколько предложений `from` для доступа к внутренним коллекциям вместо предложения [join](../../../csharp/language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="87f21-204">Use multiple `from` clauses instead of a [join](../../../csharp/language-reference/keywords/join-clause.md) clause to access inner collections.</span></span> <span data-ttu-id="87f21-205">Например, коллекция объектов `Student` может содержать коллекцию результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="87f21-205">For example, a collection of `Student` objects might each contain a collection of test scores.</span></span> <span data-ttu-id="87f21-206">При выполнении следующего запроса возвращаются результаты, превышающие 90 балов, а также фамилии учащихся, получивших такие оценки.</span><span class="sxs-lookup"><span data-stu-id="87f21-206">When the following query is executed, it returns each score that is over 90, along with the last name of the student who received the score.</span></span>  
  
     <span data-ttu-id="87f21-207">[!code-cs[csProgGuideCodingConventions#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_26.cs)]</span><span class="sxs-lookup"><span data-stu-id="87f21-207">[!code-cs[csProgGuideCodingConventions#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_26.cs)]</span></span>  
  
## <a name="security"></a><span data-ttu-id="87f21-208">Безопасность</span><span class="sxs-lookup"><span data-stu-id="87f21-208">Security</span></span>  
 <span data-ttu-id="87f21-209">Следуйте указаниям, изложенным в [правилах написания безопасного кода](../../../standard/security/secure-coding-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="87f21-209">Follow the guidelines in [Secure Coding Guidelines](../../../standard/security/secure-coding-guidelines.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87f21-210">См. также</span><span class="sxs-lookup"><span data-stu-id="87f21-210">See Also</span></span>  
 <span data-ttu-id="87f21-211">[Соглашения о написании кода в Visual Basic](../../../visual-basic/programming-guide/program-structure/coding-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="87f21-211">[Visual Basic Coding Conventions](../../../visual-basic/programming-guide/program-structure/coding-conventions.md) </span></span>  
 [<span data-ttu-id="87f21-212">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="87f21-212">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)

