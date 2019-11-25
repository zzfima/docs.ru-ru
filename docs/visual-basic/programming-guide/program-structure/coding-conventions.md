---
title: Соглашения о написании кода
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: 36cd3a927d2fdf197e6b496d9308fc43a555d59b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346155"
---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="370ad-102">Соглашения о написании кода в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="370ad-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="370ad-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span><span class="sxs-lookup"><span data-stu-id="370ad-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="370ad-104">If you follow the same coding conventions, you may gain the following benefits:</span><span class="sxs-lookup"><span data-stu-id="370ad-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
- <span data-ttu-id="370ad-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span><span class="sxs-lookup"><span data-stu-id="370ad-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
- <span data-ttu-id="370ad-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span><span class="sxs-lookup"><span data-stu-id="370ad-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
- <span data-ttu-id="370ad-107">You can copy, change, and maintain the code more easily.</span><span class="sxs-lookup"><span data-stu-id="370ad-107">You can copy, change, and maintain the code more easily.</span></span>  
  
- <span data-ttu-id="370ad-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="370ad-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="370ad-109">Соглашения об именах</span><span class="sxs-lookup"><span data-stu-id="370ad-109">Naming Conventions</span></span>  
  
- <span data-ttu-id="370ad-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span><span class="sxs-lookup"><span data-stu-id="370ad-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span></span>  
  
- <span data-ttu-id="370ad-111">Do not use "My" or "my" as part of a variable name.</span><span class="sxs-lookup"><span data-stu-id="370ad-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="370ad-112">This practice creates confusion with the `My` objects.</span><span class="sxs-lookup"><span data-stu-id="370ad-112">This practice creates confusion with the `My` objects.</span></span>  
  
- <span data-ttu-id="370ad-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span><span class="sxs-lookup"><span data-stu-id="370ad-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="370ad-114">Соглашения о расположении</span><span class="sxs-lookup"><span data-stu-id="370ad-114">Layout Conventions</span></span>  
  
- <span data-ttu-id="370ad-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span><span class="sxs-lookup"><span data-stu-id="370ad-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
- <span data-ttu-id="370ad-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span><span class="sxs-lookup"><span data-stu-id="370ad-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="370ad-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="370ad-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
- <span data-ttu-id="370ad-118">Use only one statement per line.</span><span class="sxs-lookup"><span data-stu-id="370ad-118">Use only one statement per line.</span></span> <span data-ttu-id="370ad-119">Don't use the Visual Basic line separator character (:).</span><span class="sxs-lookup"><span data-stu-id="370ad-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
- <span data-ttu-id="370ad-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span><span class="sxs-lookup"><span data-stu-id="370ad-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
- <span data-ttu-id="370ad-121">Use only one declaration per line.</span><span class="sxs-lookup"><span data-stu-id="370ad-121">Use only one declaration per line.</span></span>  
  
- <span data-ttu-id="370ad-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span><span class="sxs-lookup"><span data-stu-id="370ad-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="370ad-123">However, always left-align items in a list.</span><span class="sxs-lookup"><span data-stu-id="370ad-123">However, always left-align items in a list.</span></span>  
  
    ```vb  
    a As Integer,  
    b As Integer  
    ```  
  
- <span data-ttu-id="370ad-124">Add at least one blank line between method and property definitions.</span><span class="sxs-lookup"><span data-stu-id="370ad-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="370ad-125">Соглашения о комментариях</span><span class="sxs-lookup"><span data-stu-id="370ad-125">Commenting Conventions</span></span>  
  
- <span data-ttu-id="370ad-126">Put comments on a separate line instead of at the end of a line of code.</span><span class="sxs-lookup"><span data-stu-id="370ad-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
- <span data-ttu-id="370ad-127">Start comment text with an uppercase letter, and end comment text with a period.</span><span class="sxs-lookup"><span data-stu-id="370ad-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
- <span data-ttu-id="370ad-128">Insert one space between the comment delimiter (') and the comment text.</span><span class="sxs-lookup"><span data-stu-id="370ad-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#2)]  
  
- <span data-ttu-id="370ad-129">Do not surround comments with formatted blocks of asterisks.</span><span class="sxs-lookup"><span data-stu-id="370ad-129">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="370ad-130">Структура программы</span><span class="sxs-lookup"><span data-stu-id="370ad-130">Program Structure</span></span>  
  
- <span data-ttu-id="370ad-131">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span><span class="sxs-lookup"><span data-stu-id="370ad-131">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#3)]  
  
## <a name="language-guidelines"></a><span data-ttu-id="370ad-132">Рекомендации по работе с языком</span><span class="sxs-lookup"><span data-stu-id="370ad-132">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="370ad-133">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="370ad-133">String Data Type</span></span>  
  
- <span data-ttu-id="370ad-134">Для сцепления коротких строк рекомендуется использовать [интерполяцию строк](https://docs.microsoft.com/dotnet/visual-basic/programming-guide/language-features/strings/interpolated-strings), как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="370ad-134">Use [string interpolation](https://docs.microsoft.com/dotnet/visual-basic/programming-guide/language-features/strings/interpolated-strings) to concatenate short strings, as shown in the following code.</span></span>
  
     ```vb
     MsgBox($"hello{vbCrLf}goodbye")
     ```
  
- <span data-ttu-id="370ad-135">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span><span class="sxs-lookup"><span data-stu-id="370ad-135">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#5)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="370ad-136">Relaxed Delegates in Event Handlers</span><span class="sxs-lookup"><span data-stu-id="370ad-136">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="370ad-137">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span><span class="sxs-lookup"><span data-stu-id="370ad-137">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="370ad-138">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span><span class="sxs-lookup"><span data-stu-id="370ad-138">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#7)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="370ad-139">Беззнаковый тип данных</span><span class="sxs-lookup"><span data-stu-id="370ad-139">Unsigned Data Type</span></span>  
  
- <span data-ttu-id="370ad-140">Use `Integer` rather than unsigned types, except where they are necessary.</span><span class="sxs-lookup"><span data-stu-id="370ad-140">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="370ad-141">Массивы</span><span class="sxs-lookup"><span data-stu-id="370ad-141">Arrays</span></span>  
  
- <span data-ttu-id="370ad-142">Use the short syntax when you initialize arrays on the declaration line.</span><span class="sxs-lookup"><span data-stu-id="370ad-142">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="370ad-143">For example, use the following syntax.</span><span class="sxs-lookup"><span data-stu-id="370ad-143">For example, use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#8)]  
  
     <span data-ttu-id="370ad-144">Do not use the following syntax.</span><span class="sxs-lookup"><span data-stu-id="370ad-144">Do not use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#9)]  
  
- <span data-ttu-id="370ad-145">Put the array designator on the type, not on the variable.</span><span class="sxs-lookup"><span data-stu-id="370ad-145">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="370ad-146">For example, use the following syntax:</span><span class="sxs-lookup"><span data-stu-id="370ad-146">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#11)]  
  
     <span data-ttu-id="370ad-147">Do not use the following syntax:</span><span class="sxs-lookup"><span data-stu-id="370ad-147">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#10)]  
  
- <span data-ttu-id="370ad-148">Use the { } syntax when you declare and initialize arrays of basic data types.</span><span class="sxs-lookup"><span data-stu-id="370ad-148">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="370ad-149">For example, use the following syntax:</span><span class="sxs-lookup"><span data-stu-id="370ad-149">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#12)]  
  
     <span data-ttu-id="370ad-150">Do not use the following syntax:</span><span class="sxs-lookup"><span data-stu-id="370ad-150">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#13)]  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="370ad-151">Use the With Keyword</span><span class="sxs-lookup"><span data-stu-id="370ad-151">Use the With Keyword</span></span>  
 <span data-ttu-id="370ad-152">When you make a series of calls to one object, consider using the `With` keyword:</span><span class="sxs-lookup"><span data-stu-id="370ad-152">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#15)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="370ad-153">Use the Try...Catch and Using Statements when you use Exception Handling</span><span class="sxs-lookup"><span data-stu-id="370ad-153">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="370ad-154">Не используйте `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="370ad-154">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="370ad-155">Use the IsNot Keyword</span><span class="sxs-lookup"><span data-stu-id="370ad-155">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="370ad-156">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span><span class="sxs-lookup"><span data-stu-id="370ad-156">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="370ad-157">New Keyword</span><span class="sxs-lookup"><span data-stu-id="370ad-157">New Keyword</span></span>  
  
- <span data-ttu-id="370ad-158">Use short instantiation.</span><span class="sxs-lookup"><span data-stu-id="370ad-158">Use short instantiation.</span></span> <span data-ttu-id="370ad-159">For example, use the following syntax:</span><span class="sxs-lookup"><span data-stu-id="370ad-159">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#21)]  
  
     <span data-ttu-id="370ad-160">The preceding line is equivalent to this:</span><span class="sxs-lookup"><span data-stu-id="370ad-160">The preceding line is equivalent to this:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#22)]  
  
- <span data-ttu-id="370ad-161">Use object initializers for new objects instead of the parameterless constructor:</span><span class="sxs-lookup"><span data-stu-id="370ad-161">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#23)]  
  
### <a name="event-handling"></a><span data-ttu-id="370ad-162">Обработка событий</span><span class="sxs-lookup"><span data-stu-id="370ad-162">Event Handling</span></span>  
  
- <span data-ttu-id="370ad-163">Use `Handles` rather than `AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="370ad-163">Use `Handles` rather than `AddHandler`:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#24)]  
  
- <span data-ttu-id="370ad-164">Use `AddressOf`, and do not instantiate the delegate explicitly:</span><span class="sxs-lookup"><span data-stu-id="370ad-164">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#25)]  
  
- <span data-ttu-id="370ad-165">When you define an event, use the short syntax, and let the compiler define the delegate:</span><span class="sxs-lookup"><span data-stu-id="370ad-165">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#26)]  
  
- <span data-ttu-id="370ad-166">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span><span class="sxs-lookup"><span data-stu-id="370ad-166">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="370ad-167">`RaiseEvent` checks for `Nothing` before it raises the event.</span><span class="sxs-lookup"><span data-stu-id="370ad-167">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="370ad-168">Using Shared Members</span><span class="sxs-lookup"><span data-stu-id="370ad-168">Using Shared Members</span></span>  
 <span data-ttu-id="370ad-169">Call `Shared` members by using the class name, not from an instance variable.</span><span class="sxs-lookup"><span data-stu-id="370ad-169">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="370ad-170">Use XML Literals</span><span class="sxs-lookup"><span data-stu-id="370ad-170">Use XML Literals</span></span>  
 <span data-ttu-id="370ad-171">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span><span class="sxs-lookup"><span data-stu-id="370ad-171">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="370ad-172">When you develop with XML, follow these guidelines:</span><span class="sxs-lookup"><span data-stu-id="370ad-172">When you develop with XML, follow these guidelines:</span></span>  
  
- <span data-ttu-id="370ad-173">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span><span class="sxs-lookup"><span data-stu-id="370ad-173">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
- <span data-ttu-id="370ad-174">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span><span class="sxs-lookup"><span data-stu-id="370ad-174">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
- <span data-ttu-id="370ad-175">Use the XML axis properties to access elements and attributes in an XML document.</span><span class="sxs-lookup"><span data-stu-id="370ad-175">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
- <span data-ttu-id="370ad-176">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span><span class="sxs-lookup"><span data-stu-id="370ad-176">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#27)]  
  
### <a name="linq-queries"></a><span data-ttu-id="370ad-177">Запросы LINQ</span><span class="sxs-lookup"><span data-stu-id="370ad-177">LINQ Queries</span></span>  
  
- <span data-ttu-id="370ad-178">Use meaningful names for query variables:</span><span class="sxs-lookup"><span data-stu-id="370ad-178">Use meaningful names for query variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#28)]  
  
- <span data-ttu-id="370ad-179">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span><span class="sxs-lookup"><span data-stu-id="370ad-179">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#29)]  
  
- <span data-ttu-id="370ad-180">Переименуйте свойства, если имена свойств в результате могут быть неоднозначными.</span><span class="sxs-lookup"><span data-stu-id="370ad-180">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="370ad-181">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span><span class="sxs-lookup"><span data-stu-id="370ad-181">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#30)]  
  
- <span data-ttu-id="370ad-182">Use type inference in the declaration of query variables and range variables:</span><span class="sxs-lookup"><span data-stu-id="370ad-182">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#31)]  
  
- <span data-ttu-id="370ad-183">Align query clauses under the `From` statement:</span><span class="sxs-lookup"><span data-stu-id="370ad-183">Align query clauses under the `From` statement:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#32)]  
  
- <span data-ttu-id="370ad-184">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span><span class="sxs-lookup"><span data-stu-id="370ad-184">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#33)]  
  
- <span data-ttu-id="370ad-185">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span><span class="sxs-lookup"><span data-stu-id="370ad-185">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="370ad-186">См. также</span><span class="sxs-lookup"><span data-stu-id="370ad-186">See also</span></span>

- [<span data-ttu-id="370ad-187">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="370ad-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
