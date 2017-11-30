---
title: "Соглашения о написании кода на C# (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
caps.latest.revision: "32"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 84ddc2b3cebb6bad95f5076889de11f12624b4de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="c-coding-conventions-c-programming-guide"></a><span data-ttu-id="935bc-102">Соглашения о написании кода на C# (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="935bc-102">C# Coding Conventions (C# Programming Guide)</span></span>
<span data-ttu-id="935bc-103">[Спецификация языка C#](http://go.microsoft.com/fwlink/?LinkId=199552) не определяет стандарт кодирования.</span><span class="sxs-lookup"><span data-stu-id="935bc-103">The [C# Language Specification](http://go.microsoft.com/fwlink/?LinkId=199552) does not define a coding standard.</span></span> <span data-ttu-id="935bc-104">Однако корпорация Майкрософт использует приведенные в этом разделе рекомендации для разработки примеров и документации.</span><span class="sxs-lookup"><span data-stu-id="935bc-104">However, the guidelines in this topic are used by Microsoft to develop samples and documentation.</span></span>  
  
 <span data-ttu-id="935bc-105">Соглашения о написании кода предназначены для реализации следующих целей.</span><span class="sxs-lookup"><span data-stu-id="935bc-105">Coding conventions serve the following purposes:</span></span>  
  
-   <span data-ttu-id="935bc-106">Создание согласованного вида кода, позволяющего читателям сосредоточиться на содержимом, а не на структуре.</span><span class="sxs-lookup"><span data-stu-id="935bc-106">They create a consistent look to the code, so that readers can focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="935bc-107">Предоставление читателям возможности делать предположения, основанные на опыте, и поэтому быстрее понимать код.</span><span class="sxs-lookup"><span data-stu-id="935bc-107">They enable readers to understand the code more quickly by making assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="935bc-108">Упрощение процессов копирования, изменения и обслуживания кода.</span><span class="sxs-lookup"><span data-stu-id="935bc-108">They facilitate copying, changing, and maintaining the code.</span></span>  
  
-   <span data-ttu-id="935bc-109">Предоставление лучших методик C#.</span><span class="sxs-lookup"><span data-stu-id="935bc-109">They demonstrate C# best practices.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="935bc-110">Соглашения об именах</span><span class="sxs-lookup"><span data-stu-id="935bc-110">Naming Conventions</span></span>  
  
-   <span data-ttu-id="935bc-111">В коротких примерах, не содержащих [директив using](../../../csharp/language-reference/keywords/using-directive.md), рекомендуется использовать полные указания для пространства имен.</span><span class="sxs-lookup"><span data-stu-id="935bc-111">In short examples that do not include [using directives](../../../csharp/language-reference/keywords/using-directive.md), use namespace qualifications.</span></span> <span data-ttu-id="935bc-112">Если известно, что пространство имен импортировано в проект по умолчанию, не требуется указывать полные имена из этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="935bc-112">If you know that a namespace is imported by default in a project, you do not have to fully qualify the names from that namespace.</span></span> <span data-ttu-id="935bc-113">Полные имена, если они слишком длинные для одной строки, можно разбить после точки (.), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="935bc-113">Qualified names can be broken after a dot (.) if they are too long for a single line, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#1](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#1)]  
  
-   <span data-ttu-id="935bc-114">Нет необходимости изменять имена объектов, созданных с помощью инструментов разработки Visual Studio, чтобы привести их в соответствие с другими соглашениями.</span><span class="sxs-lookup"><span data-stu-id="935bc-114">You do not have to change the names of objects that were created by using the Visual Studio designer tools to make them fit other guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="935bc-115">Соглашения о расположении</span><span class="sxs-lookup"><span data-stu-id="935bc-115">Layout Conventions</span></span>  
 <span data-ttu-id="935bc-116">Чтобы выделить структуру кода и облегчить чтение кода, в хорошем макете используется форматирование.</span><span class="sxs-lookup"><span data-stu-id="935bc-116">Good layout uses formatting to emphasize the structure of your code and to make the code easier to read.</span></span> <span data-ttu-id="935bc-117">Примеры и образцы корпорации Майкрософт соответствуют следующим соглашениям.</span><span class="sxs-lookup"><span data-stu-id="935bc-117">Microsoft examples and samples conform to the following conventions:</span></span>  
  
-   <span data-ttu-id="935bc-118">Использование параметров редактора кода по умолчанию (логичные отступы, отступы по четыре символа, использование пробелов для табуляции).</span><span class="sxs-lookup"><span data-stu-id="935bc-118">Use the default Code Editor settings (smart indenting, four-character indents, tabs saved as spaces).</span></span> <span data-ttu-id="935bc-119">Дополнительные сведения см. в разделе ["Параметры", "Текстовый редактор", C#, "Форматирование"](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span><span class="sxs-lookup"><span data-stu-id="935bc-119">For more information, see [Options, Text Editor, C#, Formatting](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span></span>  
  
-   <span data-ttu-id="935bc-120">Запись только одного оператора в строке.</span><span class="sxs-lookup"><span data-stu-id="935bc-120">Write only one statement per line.</span></span>  
  
-   <span data-ttu-id="935bc-121">Запись только одного объявления в строке.</span><span class="sxs-lookup"><span data-stu-id="935bc-121">Write only one declaration per line.</span></span>  
  
-   <span data-ttu-id="935bc-122">Если отступ для дополнительных строк не ставится автоматически, необходимо сделать для них отступ на одну позицию табуляции (четыре пробела).</span><span class="sxs-lookup"><span data-stu-id="935bc-122">If continuation lines are not indented automatically, indent them one tab stop (four spaces).</span></span>  
  
-   <span data-ttu-id="935bc-123">Добавление по крайней мере одной пустой строки между определениями методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="935bc-123">Add at least one blank line between method definitions and property definitions.</span></span>  
  
-   <span data-ttu-id="935bc-124">Использование скобок для ясности предложений в выражениях, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="935bc-124">Use parentheses to make clauses in an expression apparent, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#2)]  
  
## <a name="commenting-conventions"></a><span data-ttu-id="935bc-125">Соглашения о комментариях</span><span class="sxs-lookup"><span data-stu-id="935bc-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="935bc-126">Комментарий размещается на отдельной строке, а не в конце строки кода.</span><span class="sxs-lookup"><span data-stu-id="935bc-126">Place the comment on a separate line, not at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="935bc-127">Текст комментария начинается с заглавной буквы.</span><span class="sxs-lookup"><span data-stu-id="935bc-127">Begin comment text with an uppercase letter.</span></span>  
  
-   <span data-ttu-id="935bc-128">Текст комментария завершается точкой.</span><span class="sxs-lookup"><span data-stu-id="935bc-128">End comment text with a period.</span></span>  
  
-   <span data-ttu-id="935bc-129">Между разделителем комментария (/ /) и текстом комментария вставляется один пробел, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="935bc-129">Insert one space between the comment delimiter (//) and the comment text, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#3](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#3)]  
  
-   <span data-ttu-id="935bc-130">Вокруг комментариев не должно быть звездочек.</span><span class="sxs-lookup"><span data-stu-id="935bc-130">Do not create formatted blocks of asterisks around comments.</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="935bc-131">Рекомендации по работе с языком</span><span class="sxs-lookup"><span data-stu-id="935bc-131">Language Guidelines</span></span>  
 <span data-ttu-id="935bc-132">В следующих подразделах описаны методики, которыми руководствуется команда C# для подготовки примеров и образцов кода.</span><span class="sxs-lookup"><span data-stu-id="935bc-132">The following sections describe practices that the C# team follows to prepare code examples and samples.</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="935bc-133">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="935bc-133">String Data Type</span></span>  
  
-   <span data-ttu-id="935bc-134">Для сцепления коротких строк рекомендуется использовать оператор `+`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="935bc-134">Use the `+` operator to concatenate short strings, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#6](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#6)]  
  
-   <span data-ttu-id="935bc-135">Для добавления строк в циклы, особенно при работе с текстами больших размеров, рекомендуется использовать объект <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="935bc-135">To append strings in loops, especially when you are working with large amounts of text, use a <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
### <a name="implicitly-typed-local-variables"></a><span data-ttu-id="935bc-136">Неявно типизированные локальные переменные</span><span class="sxs-lookup"><span data-stu-id="935bc-136">Implicitly Typed Local Variables</span></span>  
  
-   <span data-ttu-id="935bc-137">В случаях, когда тип переменной понятен из правой части назначения или когда точный тип не важен, рекомендуется использовать [неявное типизирование](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) для локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="935bc-137">Use [implicit typing](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) for local variables when the type of the variable is obvious from the right side of the assignment, or when the precise type is not important.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#8](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#8)]  
  
-   <span data-ttu-id="935bc-138">Если тип из правой части назначения не является очевидным, не рекомендуется использовать [var](../../../csharp/language-reference/keywords/var.md).</span><span class="sxs-lookup"><span data-stu-id="935bc-138">Do not use [var](../../../csharp/language-reference/keywords/var.md) when the type is not apparent from the right side of the assignment.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#9](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#9)]  
  
-   <span data-ttu-id="935bc-139">При указании типа переменной не следует полагаться на имя переменной.</span><span class="sxs-lookup"><span data-stu-id="935bc-139">Do not rely on the variable name to specify the type of the variable.</span></span> <span data-ttu-id="935bc-140">Имя может быть неверным.</span><span class="sxs-lookup"><span data-stu-id="935bc-140">It might not be correct.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#10](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#10)]  
  
-   <span data-ttu-id="935bc-141">Рекомендуется избегать использования `var` вместо [dynamic](../../../csharp/language-reference/keywords/dynamic.md).</span><span class="sxs-lookup"><span data-stu-id="935bc-141">Avoid the use of `var` in place of [dynamic](../../../csharp/language-reference/keywords/dynamic.md).</span></span>  
  
-   <span data-ttu-id="935bc-142">Рекомендуется использовать неявное типизирование для определения типа переменной цикла в циклах [for](../../../csharp/language-reference/keywords/for.md) и [foreach](../../../csharp/language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="935bc-142">Use implicit typing to determine the type of the loop variable in [for](../../../csharp/language-reference/keywords/for.md) and [foreach](../../../csharp/language-reference/keywords/foreach-in.md) loops.</span></span>  
  
     <span data-ttu-id="935bc-143">В следующем примере неявное типизирование используется в операторе `for`.</span><span class="sxs-lookup"><span data-stu-id="935bc-143">The following example uses implicit typing in a `for` statement.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#11](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#11)]  
  
     <span data-ttu-id="935bc-144">В следующем примере неявное типизирование используется в операторе `foreach`.</span><span class="sxs-lookup"><span data-stu-id="935bc-144">The following example uses implicit typing in a `foreach` statement.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#12](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#12)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="935bc-145">Беззнаковый тип данных</span><span class="sxs-lookup"><span data-stu-id="935bc-145">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="935bc-146">Как правило, рекомендуется использовать `int` вместо беззнаковых типов.</span><span class="sxs-lookup"><span data-stu-id="935bc-146">In general, use `int` rather than unsigned types.</span></span> <span data-ttu-id="935bc-147">В C# обычно используется `int`. Использование `int` упрощает взаимодействие с другими библиотеками.</span><span class="sxs-lookup"><span data-stu-id="935bc-147">The use of `int` is common throughout C#, and it is easier to interact with other libraries when you use `int`.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="935bc-148">Массивы</span><span class="sxs-lookup"><span data-stu-id="935bc-148">Arrays</span></span>  
  
-   <span data-ttu-id="935bc-149">При инициализации массивов в строке объявления рекомендуется использовать сокращенный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="935bc-149">Use the concise syntax when you initialize arrays on the declaration line.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#13](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#13)]  
  
### <a name="delegates"></a><span data-ttu-id="935bc-150">Делегаты</span><span class="sxs-lookup"><span data-stu-id="935bc-150">Delegates</span></span>  
  
-   <span data-ttu-id="935bc-151">Для создания экземпляров типа делегата рекомендуется использовать сокращенный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="935bc-151">Use the concise syntax to create instances of a delegate type.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#14](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#14)]  
  
     [!code-csharp[csProgGuideCodingConventions#15](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#15)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a><span data-ttu-id="935bc-152">Операторы try-catch и using в процессе обработки исключений</span><span class="sxs-lookup"><span data-stu-id="935bc-152">try-catch and using Statements in Exception Handling</span></span>  
  
-   <span data-ttu-id="935bc-153">Рекомендуется использовать оператор [try-catch](../../../csharp/language-reference/keywords/try-catch.md) для обработки большей части исключений.</span><span class="sxs-lookup"><span data-stu-id="935bc-153">Use a [try-catch](../../../csharp/language-reference/keywords/try-catch.md) statement for most exception handling.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#16](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#16)]  
  
-   <span data-ttu-id="935bc-154">Использование [оператора C# using](../../../csharp/language-reference/keywords/using-statement.md) упрощает код.</span><span class="sxs-lookup"><span data-stu-id="935bc-154">Simplify your code by using the C# [using statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span> <span data-ttu-id="935bc-155">При наличии оператора [try-finally](../../../csharp/language-reference/keywords/try-finally.md), код которого в блоке `finally` содержит только вызов метода <xref:System.IDisposable.Dispose%2A>, вместо него рекомендуется использовать оператор `using`.</span><span class="sxs-lookup"><span data-stu-id="935bc-155">If you have a [try-finally](../../../csharp/language-reference/keywords/try-finally.md) statement in which the only code in the `finally` block is a call to the <xref:System.IDisposable.Dispose%2A> method, use a `using` statement instead.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#17](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#17)]  
  
### <a name="-and-124124-operators"></a><span data-ttu-id="935bc-156">Операторы && и ||</span><span class="sxs-lookup"><span data-stu-id="935bc-156">&& and &#124;&#124; Operators</span></span>  
  
-   <span data-ttu-id="935bc-157">Чтобы избежать возникновения исключений и увеличить производительность за счет пропуска необязательных сравнений, рекомендуется использовать [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) вместо [&](../../../csharp/language-reference/operators/and-operator.md) и [||](../../../csharp/language-reference/operators/conditional-or-operator.md) вместо [|](../../../csharp/language-reference/operators/or-operator.md) при выполнении сравнений, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="935bc-157">To avoid exceptions and increase performance by skipping unnecessary comparisons, use [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) instead of [&](../../../csharp/language-reference/operators/and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) instead of [&#124;](../../../csharp/language-reference/operators/or-operator.md) when you perform comparisons, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#18](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#18)]  
  
### <a name="new-operator"></a><span data-ttu-id="935bc-158">Оператор New</span><span class="sxs-lookup"><span data-stu-id="935bc-158">New Operator</span></span>  
  
-   <span data-ttu-id="935bc-159">Рекомендуется использовать сокращенную форму создания экземпляра для объекта с неявным типизированием, как показано в следующем объявлении.</span><span class="sxs-lookup"><span data-stu-id="935bc-159">Use the concise form of object instantiation, with implicit typing, as shown in the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#19](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#19)]  
  
     <span data-ttu-id="935bc-160">Предыдущая строка соответствует следующему объявлению.</span><span class="sxs-lookup"><span data-stu-id="935bc-160">The previous line is equivalent to the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#20](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#20)]  
  
-   <span data-ttu-id="935bc-161">Рекомендуется использовать инициализаторы объектов для упрощения создания объектов.</span><span class="sxs-lookup"><span data-stu-id="935bc-161">Use object initializers to simplify object creation.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#21](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#21)]  
  
### <a name="event-handling"></a><span data-ttu-id="935bc-162">Обработка событий</span><span class="sxs-lookup"><span data-stu-id="935bc-162">Event Handling</span></span>  
  
-   <span data-ttu-id="935bc-163">При определении обработчика событий, которого не требуется удалять позднее, рекомендуется использовать лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="935bc-163">If you are defining an event handler that you do not need to remove later, use a lambda expression.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#22](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#22)]  
  
     [!code-csharp[csProgGuideCodingConventions#23](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#23)]  
  
### <a name="static-members"></a><span data-ttu-id="935bc-164">Статический члены</span><span class="sxs-lookup"><span data-stu-id="935bc-164">Static Members</span></span>  
  
-   <span data-ttu-id="935bc-165">Для вызова [статических](../../../csharp/language-reference/keywords/static.md) членов следует использовать имя класса: *ClassName.StaticMember*.</span><span class="sxs-lookup"><span data-stu-id="935bc-165">Call [static](../../../csharp/language-reference/keywords/static.md) members by using the class name: *ClassName.StaticMember*.</span></span> <span data-ttu-id="935bc-166">В этом случае код становится более удобочитаемым за счет четкого доступа.</span><span class="sxs-lookup"><span data-stu-id="935bc-166">This practice makes code more readable by making static access clear.</span></span>  <span data-ttu-id="935bc-167">Не присваивайте статическому члену, определенному в базовом классе, имя производного класса.</span><span class="sxs-lookup"><span data-stu-id="935bc-167">Do not qualify a static member defined in a base class with the name of a derived class.</span></span>  <span data-ttu-id="935bc-168">Во время компиляции кода его читаемость нарушается, и если добавить статический член с тем же именем в производный классе, код может быть поврежден.</span><span class="sxs-lookup"><span data-stu-id="935bc-168">While that code compiles, the code readability is misleading, and the code may break in the future if you add a static member with the same name to the derived class.</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="935bc-169">Запросы LINQ</span><span class="sxs-lookup"><span data-stu-id="935bc-169">LINQ Queries</span></span>  
  
-   <span data-ttu-id="935bc-170">Используйте значимые имена для переменных запроса.</span><span class="sxs-lookup"><span data-stu-id="935bc-170">Use meaningful names for query variables.</span></span> <span data-ttu-id="935bc-171">В следующем примере используется `seattleCustomers` для клиентов, находящихся в Сиэтле.</span><span class="sxs-lookup"><span data-stu-id="935bc-171">The following example uses `seattleCustomers` for customers who are located in Seattle.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
-   <span data-ttu-id="935bc-172">Рекомендуется использовать псевдонимы для уверенности в том, что в именах свойств анонимных типов верно используются прописные буквы при помощи правил использования прописных и строчных букв языка Pascal.</span><span class="sxs-lookup"><span data-stu-id="935bc-172">Use aliases to make sure that property names of anonymous types are correctly capitalized, using Pascal casing.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#26](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#26)]  
  
-   <span data-ttu-id="935bc-173">Переименуйте свойства, если имена свойств в результате могут быть неоднозначными.</span><span class="sxs-lookup"><span data-stu-id="935bc-173">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="935bc-174">Например, если запрос возвращает имя клиента и идентификатор распространителя, не оставляйте имена в виде `Name` и `ID`, а переименуйте их, чтобы было ясно, что `Name` — имя клиента и `ID` — идентификатор распространителя.</span><span class="sxs-lookup"><span data-stu-id="935bc-174">For example, if your query returns a customer name and a distributor ID, instead of leaving them as `Name` and `ID` in the result, rename them to clarify that `Name` is the name of a customer, and `ID` is the ID of a distributor.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#27](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#27)]  
  
-   <span data-ttu-id="935bc-175">Рекомендуется использовать неявное типизирование в объявлении переменных запроса и переменных диапазона.</span><span class="sxs-lookup"><span data-stu-id="935bc-175">Use implicit typing in the declaration of query variables and range variables.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
-   <span data-ttu-id="935bc-176">Выравнивайте предложения запроса под предложением [from](../../../csharp/language-reference/keywords/from-clause.md), как показано в предыдущих примерах.</span><span class="sxs-lookup"><span data-stu-id="935bc-176">Align query clauses under the [from](../../../csharp/language-reference/keywords/from-clause.md) clause, as shown in the previous examples.</span></span>  
  
-   <span data-ttu-id="935bc-177">Чтобы гарантировать, что более поздние предложения запроса работают с ограниченным, отфильтрованным набором данных, используйте предложение [where](../../../csharp/language-reference/keywords/where-clause.md) перед другими предложениями запроса.</span><span class="sxs-lookup"><span data-stu-id="935bc-177">Use [where](../../../csharp/language-reference/keywords/where-clause.md) clauses before other query clauses to ensure that later query clauses operate on the reduced, filtered set of data.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#29](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#29)]  
  
-   <span data-ttu-id="935bc-178">Используйте несколько предложений `from` для доступа к внутренним коллекциям вместо предложения [join](../../../csharp/language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="935bc-178">Use multiple `from` clauses instead of a [join](../../../csharp/language-reference/keywords/join-clause.md) clause to access inner collections.</span></span> <span data-ttu-id="935bc-179">Например, коллекция объектов `Student` может содержать коллекцию результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="935bc-179">For example, a collection of `Student` objects might each contain a collection of test scores.</span></span> <span data-ttu-id="935bc-180">При выполнении следующего запроса возвращаются результаты, превышающие 90 балов, а также фамилии учащихся, получивших такие оценки.</span><span class="sxs-lookup"><span data-stu-id="935bc-180">When the following query is executed, it returns each score that is over 90, along with the last name of the student who received the score.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#30](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#30)]  
  
## <a name="security"></a><span data-ttu-id="935bc-181">Безопасность</span><span class="sxs-lookup"><span data-stu-id="935bc-181">Security</span></span>  
 <span data-ttu-id="935bc-182">Следуйте указаниям, изложенным в [правилах написания безопасного кода](../../../standard/security/secure-coding-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="935bc-182">Follow the guidelines in [Secure Coding Guidelines](../../../standard/security/secure-coding-guidelines.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="935bc-183">См. также</span><span class="sxs-lookup"><span data-stu-id="935bc-183">See Also</span></span>  
 [<span data-ttu-id="935bc-184">Соглашения о написании кода Visual Basic</span><span class="sxs-lookup"><span data-stu-id="935bc-184">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 [<span data-ttu-id="935bc-185">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="935bc-185">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
