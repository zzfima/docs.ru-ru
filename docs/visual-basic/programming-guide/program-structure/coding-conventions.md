---
title: "Соглашения о написании кода Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- coding conventions, Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
caps.latest.revision: 48
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 16d4ddccd3a16c48e58f297faf8909148899013f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="b7da0-102">Соглашения о написании кода в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b7da0-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="b7da0-103">Корпорация Майкрософт разрабатывает примеры и документация, следуйте рекомендациям в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b7da0-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="b7da0-104">Если следовать тем же правилам написания кода, могут получить следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="b7da0-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
-   <span data-ttu-id="b7da0-105">Код будет иметь согласованный вид, чтобы читателям лучше сосредоточиться на содержимом, а не на макете.</span><span class="sxs-lookup"><span data-stu-id="b7da0-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="b7da0-106">Читателям понимание кода более быстро, так как они могут делать предположения, основанные на опыте.</span><span class="sxs-lookup"><span data-stu-id="b7da0-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="b7da0-107">Можно скопировать, изменение и обслуживание кода проще.</span><span class="sxs-lookup"><span data-stu-id="b7da0-107">You can copy, change, and maintain the code more easily.</span></span>  
  
-   <span data-ttu-id="b7da0-108">Позволяет убедиться, что код демонстрирует «рекомендации» для Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b7da0-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="b7da0-109">Соглашения об именах</span><span class="sxs-lookup"><span data-stu-id="b7da0-109">Naming Conventions</span></span>  
  
-   <span data-ttu-id="b7da0-110">Сведения о правилах именования см. в разделе [правила именования](http://msdn.microsoft.com/library/fc076d66-9b5f-42d3-aa65-61d970c794a3) раздела.</span><span class="sxs-lookup"><span data-stu-id="b7da0-110">For information about naming guidelines, see [Naming Guidelines](http://msdn.microsoft.com/library/fc076d66-9b5f-42d3-aa65-61d970c794a3) topic.</span></span>  
  
-   <span data-ttu-id="b7da0-111">Не использовать «Мои» или «my» как часть имени переменной.</span><span class="sxs-lookup"><span data-stu-id="b7da0-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="b7da0-112">Такой подход создает путаницу с `My` объектов.</span><span class="sxs-lookup"><span data-stu-id="b7da0-112">This practice creates confusion with the `My` objects.</span></span>  
  
-   <span data-ttu-id="b7da0-113">Необходимо изменить имена объектов в автоматически сгенерированный код, чтобы сделать их соответствующими рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="b7da0-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="b7da0-114">Соглашения о расположении</span><span class="sxs-lookup"><span data-stu-id="b7da0-114">Layout Conventions</span></span>  
  
-   <span data-ttu-id="b7da0-115">Вставка табуляции в качестве пробелов и использовать интеллектуальных отступов с помощью отступов четыре пробела.</span><span class="sxs-lookup"><span data-stu-id="b7da0-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
-   <span data-ttu-id="b7da0-116">Используйте **красивое оформление код (форматирование) из** переформатировать кода в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="b7da0-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="b7da0-117">Дополнительные сведения см. в разделе [параметры, текстовый редактор, Basic (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="b7da0-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
-   <span data-ttu-id="b7da0-118">Использование только одного оператора в строке.</span><span class="sxs-lookup"><span data-stu-id="b7da0-118">Use only one statement per line.</span></span> <span data-ttu-id="b7da0-119">Не используйте знак разделителя строки Visual Basic (:).</span><span class="sxs-lookup"><span data-stu-id="b7da0-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
-   <span data-ttu-id="b7da0-120">Избегайте использования символа продолжения строки явную «_» пользу неявное продолжение строки там, где язык допускает его.</span><span class="sxs-lookup"><span data-stu-id="b7da0-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
-   <span data-ttu-id="b7da0-121">Используйте только одного объявления в строке.</span><span class="sxs-lookup"><span data-stu-id="b7da0-121">Use only one declaration per line.</span></span>  
  
-   <span data-ttu-id="b7da0-122">Если **красивое оформление код (форматирование) из** не продолжения строки формата автоматически, вручную отступ продолжения строки должен быть одним символом табуляции.</span><span class="sxs-lookup"><span data-stu-id="b7da0-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="b7da0-123">Тем не менее всегда влево элементов в списке.</span><span class="sxs-lookup"><span data-stu-id="b7da0-123">However, always left-align items in a list.</span></span>  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   <span data-ttu-id="b7da0-124">Добавьте по крайней мере одной пустой строки между определениями методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="b7da0-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="b7da0-125">Соглашения о комментариях</span><span class="sxs-lookup"><span data-stu-id="b7da0-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="b7da0-126">Поместите комментарии на отдельной строке, а не в конце строки кода.</span><span class="sxs-lookup"><span data-stu-id="b7da0-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="b7da0-127">Текст комментария с прописной буквы и end текст, содержащий точку начала.</span><span class="sxs-lookup"><span data-stu-id="b7da0-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
-   <span data-ttu-id="b7da0-128">Вставьте один пробел между разделителем комментария (') и текстом комментария.</span><span class="sxs-lookup"><span data-stu-id="b7da0-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     <span data-ttu-id="b7da0-129">[!code-vb[VbVbalrGuidelines&#2;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-129">[!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]</span></span>  
  
-   <span data-ttu-id="b7da0-130">Не заключайте комментарии с звездочек.</span><span class="sxs-lookup"><span data-stu-id="b7da0-130">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="b7da0-131">Структура программы</span><span class="sxs-lookup"><span data-stu-id="b7da0-131">Program Structure</span></span>  
  
-   <span data-ttu-id="b7da0-132">При использовании `Main` метода, используйте конструктор по умолчанию для новых консольных приложений и использовать `My` для аргументов командной строки.</span><span class="sxs-lookup"><span data-stu-id="b7da0-132">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     <span data-ttu-id="b7da0-133">[!code-vb[VbVbalrGuidelines&#3;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-133">[!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="b7da0-134">Рекомендации по работе с языком</span><span class="sxs-lookup"><span data-stu-id="b7da0-134">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="b7da0-135">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="b7da0-135">String Data Type</span></span>  
  
-   <span data-ttu-id="b7da0-136">Для объединения строк, используйте амперсанд (&).</span><span class="sxs-lookup"><span data-stu-id="b7da0-136">To concatenate strings, use an ampersand (&).</span></span>  
  
     <span data-ttu-id="b7da0-137">[!code-vb[VbVbalrGuidelines&#4;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-137">[!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]</span></span>  
  
-   <span data-ttu-id="b7da0-138">Для добавления строк в циклы, используйте <xref:System.Text.StringBuilder>объекта.</xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="b7da0-138">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     <span data-ttu-id="b7da0-139">[!code-vb[VbVbalrGuidelines&#5;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-139">[!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]</span></span>  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="b7da0-140">Ослабленные делегаты в обработчиках событий</span><span class="sxs-lookup"><span data-stu-id="b7da0-140">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="b7da0-141">Не присваивайте аргументы (Object и EventArgs) явно обработчикам событий.</span><span class="sxs-lookup"><span data-stu-id="b7da0-141">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="b7da0-142">Если вы не используете аргументы события, переданные в событие (например, отправитель как объект e EventArgs), используйте ослабленные делегаты и пропускайте аргументы событий в коде:</span><span class="sxs-lookup"><span data-stu-id="b7da0-142">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 <span data-ttu-id="b7da0-143">[!code-vb[VbVbalrGuidelines&#7;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-143">[!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]</span></span>  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="b7da0-144">Беззнаковый тип данных</span><span class="sxs-lookup"><span data-stu-id="b7da0-144">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="b7da0-145">Использование `Integer` вместо беззнаковых типов, за исключением того, где они необходимы.</span><span class="sxs-lookup"><span data-stu-id="b7da0-145">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="b7da0-146">Массивы</span><span class="sxs-lookup"><span data-stu-id="b7da0-146">Arrays</span></span>  
  
-   <span data-ttu-id="b7da0-147">Используйте короткий синтаксис при инициализации массивов в строке объявления.</span><span class="sxs-lookup"><span data-stu-id="b7da0-147">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="b7da0-148">Например используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="b7da0-148">For example, use the following syntax.</span></span>  
  
     <span data-ttu-id="b7da0-149">[!code-vb[VbVbalrGuidelines №&8;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-149">[!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]</span></span>  
  
     <span data-ttu-id="b7da0-150">Не используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="b7da0-150">Do not use the following syntax.</span></span>  
  
     <span data-ttu-id="b7da0-151">[!code-vb[VbVbalrGuidelines №&9;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-151">[!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]</span></span>  
  
-   <span data-ttu-id="b7da0-152">Установите обозначение массива, тип, отличный от переменной.</span><span class="sxs-lookup"><span data-stu-id="b7da0-152">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="b7da0-153">Например используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b7da0-153">For example, use the following syntax:</span></span>  
  
     <span data-ttu-id="b7da0-154">[!code-vb[VbVbalrGuidelines&11;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-154">[!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]</span></span>  
  
     <span data-ttu-id="b7da0-155">Не используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b7da0-155">Do not use the following syntax:</span></span>  
  
     <span data-ttu-id="b7da0-156">[!code-vb[VbVbalrGuidelines&#10;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-156">[!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]</span></span>  
  
-   <span data-ttu-id="b7da0-157">Используйте синтаксис {} при объявлении и инициализации массивов основных типов данных.</span><span class="sxs-lookup"><span data-stu-id="b7da0-157">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="b7da0-158">Например используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b7da0-158">For example, use the following syntax:</span></span>  
  
     <span data-ttu-id="b7da0-159">[!code-vb[VbVbalrGuidelines&#12;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-159">[!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]</span></span>  
  
     <span data-ttu-id="b7da0-160">Не используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b7da0-160">Do not use the following syntax:</span></span>  
  
     <span data-ttu-id="b7da0-161">[!code-vb[VbVbalrGuidelines&#13;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-161">[!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]</span></span>  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="b7da0-162">Используется с ключевым словом</span><span class="sxs-lookup"><span data-stu-id="b7da0-162">Use the With Keyword</span></span>  
 <span data-ttu-id="b7da0-163">При внесении ряда вызовов одного объекта, рассмотрите возможность использования `With` ключевое слово:</span><span class="sxs-lookup"><span data-stu-id="b7da0-163">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 <span data-ttu-id="b7da0-164">[!code-vb[VbVbalrGuidelines&#15;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-164">[!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]</span></span>  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="b7da0-165">Использование операторов Try... С помощью инструкций, при использовании обработки исключений и catch</span><span class="sxs-lookup"><span data-stu-id="b7da0-165">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="b7da0-166">Не используйте `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="b7da0-166">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="b7da0-167">Используйте ключевое слово IsNot</span><span class="sxs-lookup"><span data-stu-id="b7da0-167">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="b7da0-168">Используйте `IsNot` ключевое слово `Not...Is Nothing`.</span><span class="sxs-lookup"><span data-stu-id="b7da0-168">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="b7da0-169">New-ключевое слово</span><span class="sxs-lookup"><span data-stu-id="b7da0-169">New Keyword</span></span>  
  
-   <span data-ttu-id="b7da0-170">Используйте короткий способ создания экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b7da0-170">Use short instantiation.</span></span> <span data-ttu-id="b7da0-171">Например используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b7da0-171">For example, use the following syntax:</span></span>  
  
     <span data-ttu-id="b7da0-172">[!code-vb[VbVbalrGuidelines&#21;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-172">[!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]</span></span>  
  
     <span data-ttu-id="b7da0-173">Предыдущая строка эквивалентна следующей:</span><span class="sxs-lookup"><span data-stu-id="b7da0-173">The preceding line is equivalent to this:</span></span>  
  
     <span data-ttu-id="b7da0-174">[!code-vb[VbVbalrGuidelines&#22;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-174">[!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]</span></span>  
  
-   <span data-ttu-id="b7da0-175">Используйте инициализаторы объектов для новых объектов вместо конструкторов:</span><span class="sxs-lookup"><span data-stu-id="b7da0-175">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     <span data-ttu-id="b7da0-176">[!code-vb[VbVbalrGuidelines&#23;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-176">[!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]</span></span>  
  
### <a name="event-handling"></a><span data-ttu-id="b7da0-177">Обработка событий</span><span class="sxs-lookup"><span data-stu-id="b7da0-177">Event Handling</span></span>  
  
-   <span data-ttu-id="b7da0-178">Используйте `Handles` вместо `AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="b7da0-178">Use `Handles` rather than `AddHandler`:</span></span>  
  
     <span data-ttu-id="b7da0-179">[!code-vb[VbVbalrGuidelines&#24;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-179">[!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]</span></span>  
  
-   <span data-ttu-id="b7da0-180">Используйте `AddressOf`и не создавайте экземпляр делегата явным образом:</span><span class="sxs-lookup"><span data-stu-id="b7da0-180">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     <span data-ttu-id="b7da0-181">[!code-vb[VbVbalrGuidelines&#25;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-181">[!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]</span></span>  
  
-   <span data-ttu-id="b7da0-182">При определении события, используйте короткий синтаксис и позвольте компилятору определить делегат:</span><span class="sxs-lookup"><span data-stu-id="b7da0-182">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     <span data-ttu-id="b7da0-183">[!code-vb[VbVbalrGuidelines&#26;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-183">[!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]</span></span>  
  
-   <span data-ttu-id="b7da0-184">Проверяет, является ли событие `Nothing` (null), перед вызовом метода `RaiseEvent` метод.</span><span class="sxs-lookup"><span data-stu-id="b7da0-184">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="b7da0-185">`RaiseEvent`проверяет наличие `Nothing` перед его событие.</span><span class="sxs-lookup"><span data-stu-id="b7da0-185">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="b7da0-186">Использование общих членов</span><span class="sxs-lookup"><span data-stu-id="b7da0-186">Using Shared Members</span></span>  
 <span data-ttu-id="b7da0-187">Вызов `Shared` члены с помощью имени класса, а не переменной экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b7da0-187">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="b7da0-188">Использование XML-литералов</span><span class="sxs-lookup"><span data-stu-id="b7da0-188">Use XML Literals</span></span>  
 <span data-ttu-id="b7da0-189">Литералы XML упрощают наиболее распространенных задач, возникающих при работе с XML (например, загрузки, запроса и преобразования).</span><span class="sxs-lookup"><span data-stu-id="b7da0-189">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="b7da0-190">При разработке с использованием XML, придерживайтесь следующих рекомендаций:</span><span class="sxs-lookup"><span data-stu-id="b7da0-190">When you develop with XML, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="b7da0-191">Используйте литералы XML для создания XML-документов и фрагментов вместо непосредственного вызова интерфейсов API.</span><span class="sxs-lookup"><span data-stu-id="b7da0-191">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
-   <span data-ttu-id="b7da0-192">Импорт пространства имен XML на уровне проект или файл, чтобы воспользоваться преимуществами оптимизации производительности для XML-литералов.</span><span class="sxs-lookup"><span data-stu-id="b7da0-192">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
-   <span data-ttu-id="b7da0-193">Используйте свойства оси XML для доступа к элементам и атрибутам в XML-документ.</span><span class="sxs-lookup"><span data-stu-id="b7da0-193">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
-   <span data-ttu-id="b7da0-194">Использовать внедренные выражения для включения значений и создания XML из существующих значений вместо использования вызовов API, таких как `Add` метод:</span><span class="sxs-lookup"><span data-stu-id="b7da0-194">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     <span data-ttu-id="b7da0-195">[!code-vb[VbVbalrGuidelines&#27;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-195">[!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="b7da0-196">Запросы LINQ</span><span class="sxs-lookup"><span data-stu-id="b7da0-196">LINQ Queries</span></span>  
  
-   <span data-ttu-id="b7da0-197">Используйте значимые имена для переменных запроса:</span><span class="sxs-lookup"><span data-stu-id="b7da0-197">Use meaningful names for query variables:</span></span>  
  
     <span data-ttu-id="b7da0-198">[!code-vb[VbVbalrGuidelines&#28;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-198">[!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]</span></span>  
  
-   <span data-ttu-id="b7da0-199">Укажите имена для элементов в запросе, чтобы убедиться в том, что имена свойств анонимных типов верно используются прописные буквы с помощью языка Pascal регистр:</span><span class="sxs-lookup"><span data-stu-id="b7da0-199">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     <span data-ttu-id="b7da0-200">[!code-vb[VbVbalrGuidelines&#29;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-200">[!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]</span></span>  
  
-   <span data-ttu-id="b7da0-201">Переименуйте свойства, если имена свойств в результате могут быть неоднозначными.</span><span class="sxs-lookup"><span data-stu-id="b7da0-201">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="b7da0-202">Например, если запрос возвращает клиента, имя и идентификатор заказа, переименуйте их не оставляйте как `Name` и `ID` в результате:</span><span class="sxs-lookup"><span data-stu-id="b7da0-202">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     <span data-ttu-id="b7da0-203">[!code-vb[VbVbalrGuidelines&#30;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-203">[!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]</span></span>  
  
-   <span data-ttu-id="b7da0-204">Используйте вывод типа в объявлении переменных запроса и переменных диапазона:</span><span class="sxs-lookup"><span data-stu-id="b7da0-204">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     <span data-ttu-id="b7da0-205">[!code-vb[VbVbalrGuidelines&#31;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-205">[!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]</span></span>  
  
-   <span data-ttu-id="b7da0-206">Выравнивайте предложения запроса под `From` инструкции:</span><span class="sxs-lookup"><span data-stu-id="b7da0-206">Align query clauses under the `From` statement:</span></span>  
  
     <span data-ttu-id="b7da0-207">[!code-vb[VbVbalrGuidelines&#32;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-207">[!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]</span></span>  
  
-   <span data-ttu-id="b7da0-208">Используйте `Where` предложения перед другие предложения запроса, чтобы более поздние предложения запроса работают отфильтрованный набор данных:</span><span class="sxs-lookup"><span data-stu-id="b7da0-208">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     <span data-ttu-id="b7da0-209">[!code-vb[VbVbalrGuidelines&#33;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-209">[!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]</span></span>  
  
-   <span data-ttu-id="b7da0-210">Используйте `Join` предложение для явного определения операции соединения вместо `Where` предложение для неявного определения операции соединения:</span><span class="sxs-lookup"><span data-stu-id="b7da0-210">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     <span data-ttu-id="b7da0-211">[!code-vb[VbVbalrGuidelines&#34;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7da0-211">[!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7da0-212">См. также</span><span class="sxs-lookup"><span data-stu-id="b7da0-212">See Also</span></span>  
 [<span data-ttu-id="b7da0-213">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="b7da0-213">Secure Coding Guidelines</span></span>](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)
