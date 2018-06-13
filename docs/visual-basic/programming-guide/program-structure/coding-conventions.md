---
title: Соглашения о написании кода в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: b686747b46529b53b0802a7deb38b5b4949f4d5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655365"
---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="57c9c-102">Соглашения о написании кода в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57c9c-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="57c9c-103">Корпорация Майкрософт разрабатывает примеров и документации, следуйте указаниям, изложенным в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="57c9c-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="57c9c-104">При таком же соглашения о написании кода, может получить следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="57c9c-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
-   <span data-ttu-id="57c9c-105">Код будет иметь согласованный внешний вид, чтобы читатели может лучше сосредоточиться на содержимом, а не на макете.</span><span class="sxs-lookup"><span data-stu-id="57c9c-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="57c9c-106">Читатели понимание кода более быстро, так как они могут делать предположения, основанные на опыте.</span><span class="sxs-lookup"><span data-stu-id="57c9c-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="57c9c-107">Копирование, изменение и обслуживать код проще.</span><span class="sxs-lookup"><span data-stu-id="57c9c-107">You can copy, change, and maintain the code more easily.</span></span>  
  
-   <span data-ttu-id="57c9c-108">Позволяет убедиться, что коде показано, как «рекомендации» для Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="57c9c-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="57c9c-109">Соглашения об именах</span><span class="sxs-lookup"><span data-stu-id="57c9c-109">Naming Conventions</span></span>  
  
-   <span data-ttu-id="57c9c-110">Сведения о рекомендациях по именованию см. в разделе [правила именования](../../../standard/design-guidelines/naming-guidelines.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="57c9c-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span></span>  
  
-   <span data-ttu-id="57c9c-111">Не используйте «My» или «my» как часть имени переменной.</span><span class="sxs-lookup"><span data-stu-id="57c9c-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="57c9c-112">Такой подход создает путаницы с `My` объектов.</span><span class="sxs-lookup"><span data-stu-id="57c9c-112">This practice creates confusion with the `My` objects.</span></span>  
  
-   <span data-ttu-id="57c9c-113">Необходимо изменить имена объектов в автоматически создаваемый код, чтобы сделать их соответствующими рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="57c9c-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="57c9c-114">Соглашения о расположении</span><span class="sxs-lookup"><span data-stu-id="57c9c-114">Layout Conventions</span></span>  
  
-   <span data-ttu-id="57c9c-115">Вставка табуляции в качестве пробелов и используйте интеллектуальных отступов с помощью отступов четыре пробела.</span><span class="sxs-lookup"><span data-stu-id="57c9c-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
-   <span data-ttu-id="57c9c-116">Используйте **довольно листинг кода (изменения форматирования)** переформатирование кода в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="57c9c-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="57c9c-117">Дополнительные сведения см. в разделе [параметры, текстовый редактор, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="57c9c-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
-   <span data-ttu-id="57c9c-118">Используйте только одну инструкцию в строке.</span><span class="sxs-lookup"><span data-stu-id="57c9c-118">Use only one statement per line.</span></span> <span data-ttu-id="57c9c-119">Не используйте знак разделителя строки Visual Basic (:).</span><span class="sxs-lookup"><span data-stu-id="57c9c-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
-   <span data-ttu-id="57c9c-120">Избегайте использования символа продолжения явные строки «_» пользу неявное продолжение строки там, где язык позволяет его.</span><span class="sxs-lookup"><span data-stu-id="57c9c-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
-   <span data-ttu-id="57c9c-121">Используйте только одно объявление в строке.</span><span class="sxs-lookup"><span data-stu-id="57c9c-121">Use only one declaration per line.</span></span>  
  
-   <span data-ttu-id="57c9c-122">Если **довольно листинг кода (изменения форматирования)** не продолжения строки формата автоматически, вручную отступ продолжения строки должен быть одним символом табуляции.</span><span class="sxs-lookup"><span data-stu-id="57c9c-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="57c9c-123">Однако всегда влево элементов в списке.</span><span class="sxs-lookup"><span data-stu-id="57c9c-123">However, always left-align items in a list.</span></span>  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   <span data-ttu-id="57c9c-124">Добавьте по крайней мере одной пустой строки между определениями методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="57c9c-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="57c9c-125">Соглашения о комментариях</span><span class="sxs-lookup"><span data-stu-id="57c9c-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="57c9c-126">Поместите комментарии на отдельной строке, а не в конце строки кода.</span><span class="sxs-lookup"><span data-stu-id="57c9c-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="57c9c-127">Текст комментария с заглавной буквы и end текст, содержащий точку начала.</span><span class="sxs-lookup"><span data-stu-id="57c9c-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
-   <span data-ttu-id="57c9c-128">Вставьте один пробел между разделителем комментария (') и текст комментария.</span><span class="sxs-lookup"><span data-stu-id="57c9c-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   <span data-ttu-id="57c9c-129">Не заключайте комментарии с звездочек.</span><span class="sxs-lookup"><span data-stu-id="57c9c-129">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="57c9c-130">Структура программы</span><span class="sxs-lookup"><span data-stu-id="57c9c-130">Program Structure</span></span>  
  
-   <span data-ttu-id="57c9c-131">При использовании `Main` метода, используйте конструктор по умолчанию для новых консольных приложений и использовать `My` для аргументов командной строки.</span><span class="sxs-lookup"><span data-stu-id="57c9c-131">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a><span data-ttu-id="57c9c-132">Рекомендации по работе с языком</span><span class="sxs-lookup"><span data-stu-id="57c9c-132">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="57c9c-133">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="57c9c-133">String Data Type</span></span>  
  
-   <span data-ttu-id="57c9c-134">Для объединения строк, используйте амперсанд (&).</span><span class="sxs-lookup"><span data-stu-id="57c9c-134">To concatenate strings, use an ampersand (&).</span></span>  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   <span data-ttu-id="57c9c-135">Для добавления строк в циклы, используйте <xref:System.Text.StringBuilder> объекта.</span><span class="sxs-lookup"><span data-stu-id="57c9c-135">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="57c9c-136">Ослабленные делегаты в обработчиках событий</span><span class="sxs-lookup"><span data-stu-id="57c9c-136">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="57c9c-137">Не определены аргументы (Object и EventArgs) явно обработчикам событий.</span><span class="sxs-lookup"><span data-stu-id="57c9c-137">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="57c9c-138">Если вы не используете аргументы события, которые передаются на событие (например, отправитель как объект e EventArgs), используйте ослабленные делегаты и пропускайте аргументы событий в коде:</span><span class="sxs-lookup"><span data-stu-id="57c9c-138">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="57c9c-139">Беззнаковый тип данных</span><span class="sxs-lookup"><span data-stu-id="57c9c-139">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="57c9c-140">Используйте `Integer` вместо беззнаковых типов, за исключением того, где они необходимы.</span><span class="sxs-lookup"><span data-stu-id="57c9c-140">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="57c9c-141">Массивы</span><span class="sxs-lookup"><span data-stu-id="57c9c-141">Arrays</span></span>  
  
-   <span data-ttu-id="57c9c-142">Используйте короткий синтаксис при инициализации массивов в строке объявления.</span><span class="sxs-lookup"><span data-stu-id="57c9c-142">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="57c9c-143">Например используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="57c9c-143">For example, use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     <span data-ttu-id="57c9c-144">Не используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="57c9c-144">Do not use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   <span data-ttu-id="57c9c-145">Установите обозначение массива, тип, отличный от переменной.</span><span class="sxs-lookup"><span data-stu-id="57c9c-145">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="57c9c-146">Например используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="57c9c-146">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     <span data-ttu-id="57c9c-147">Не используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="57c9c-147">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   <span data-ttu-id="57c9c-148">Используйте синтаксис {} при объявлении и инициализации массивов основных типов данных.</span><span class="sxs-lookup"><span data-stu-id="57c9c-148">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="57c9c-149">Например используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="57c9c-149">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     <span data-ttu-id="57c9c-150">Не используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="57c9c-150">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="57c9c-151">Используется с ключевым словом</span><span class="sxs-lookup"><span data-stu-id="57c9c-151">Use the With Keyword</span></span>  
 <span data-ttu-id="57c9c-152">Если вы внесли ряд вызовов одного объекта, рассмотрите возможность использования `With` ключевое слово:</span><span class="sxs-lookup"><span data-stu-id="57c9c-152">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="57c9c-153">Использование Try... С помощью инструкций, при использовании обработки исключений и catch</span><span class="sxs-lookup"><span data-stu-id="57c9c-153">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="57c9c-154">Не используйте `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="57c9c-154">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="57c9c-155">Используйте ключевое слово IsNot</span><span class="sxs-lookup"><span data-stu-id="57c9c-155">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="57c9c-156">Используйте `IsNot` ключевое слово, а не `Not...Is Nothing`.</span><span class="sxs-lookup"><span data-stu-id="57c9c-156">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="57c9c-157">Новое ключевое слово</span><span class="sxs-lookup"><span data-stu-id="57c9c-157">New Keyword</span></span>  
  
-   <span data-ttu-id="57c9c-158">Используйте короткие при создании экземпляра.</span><span class="sxs-lookup"><span data-stu-id="57c9c-158">Use short instantiation.</span></span> <span data-ttu-id="57c9c-159">Например используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="57c9c-159">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     <span data-ttu-id="57c9c-160">Предыдущая строка эквивалентна следующей:</span><span class="sxs-lookup"><span data-stu-id="57c9c-160">The preceding line is equivalent to this:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   <span data-ttu-id="57c9c-161">Для новых объектов, а не конструктор без параметров, используйте инициализаторы объектов:</span><span class="sxs-lookup"><span data-stu-id="57c9c-161">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a><span data-ttu-id="57c9c-162">Обработка событий</span><span class="sxs-lookup"><span data-stu-id="57c9c-162">Event Handling</span></span>  
  
-   <span data-ttu-id="57c9c-163">Используйте `Handles` вместо `AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="57c9c-163">Use `Handles` rather than `AddHandler`:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   <span data-ttu-id="57c9c-164">Используйте `AddressOf`и не создавайте экземпляр делегата явным образом:</span><span class="sxs-lookup"><span data-stu-id="57c9c-164">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   <span data-ttu-id="57c9c-165">При определении события, используйте короткий синтаксис и позвольте компилятору определить делегат:</span><span class="sxs-lookup"><span data-stu-id="57c9c-165">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   <span data-ttu-id="57c9c-166">Не проверять, является ли событие `Nothing` (null), перед вызовом метода `RaiseEvent` метод.</span><span class="sxs-lookup"><span data-stu-id="57c9c-166">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="57c9c-167">`RaiseEvent` проверяет наличие `Nothing` перед его вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="57c9c-167">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="57c9c-168">Использование общих членов</span><span class="sxs-lookup"><span data-stu-id="57c9c-168">Using Shared Members</span></span>  
 <span data-ttu-id="57c9c-169">Вызовите `Shared` члены с помощью имени класса, а не переменной экземпляра.</span><span class="sxs-lookup"><span data-stu-id="57c9c-169">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="57c9c-170">Использование XML-литералов</span><span class="sxs-lookup"><span data-stu-id="57c9c-170">Use XML Literals</span></span>  
 <span data-ttu-id="57c9c-171">Литералы XML упрощают наиболее распространенные задачи, которые возникают при работе с XML (например, загрузки, запроса и преобразования).</span><span class="sxs-lookup"><span data-stu-id="57c9c-171">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="57c9c-172">При разработке с использованием XML, придерживайтесь следующих правил:</span><span class="sxs-lookup"><span data-stu-id="57c9c-172">When you develop with XML, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="57c9c-173">Используйте литералы XML для создания XML-документы и фрагменты вместо непосредственного вызова интерфейсов API.</span><span class="sxs-lookup"><span data-stu-id="57c9c-173">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
-   <span data-ttu-id="57c9c-174">Импорт пространства имен XML на уровне файла или проекта, чтобы воспользоваться преимуществами оптимизации производительности для XML-литералов.</span><span class="sxs-lookup"><span data-stu-id="57c9c-174">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
-   <span data-ttu-id="57c9c-175">Используйте свойства оси XML для доступа к элементам и атрибутам в XML-документа.</span><span class="sxs-lookup"><span data-stu-id="57c9c-175">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
-   <span data-ttu-id="57c9c-176">Использование внедренных выражений для включения значений и создания XML на основе существующих значений вместо использования вызовов API, таких как `Add` метод:</span><span class="sxs-lookup"><span data-stu-id="57c9c-176">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a><span data-ttu-id="57c9c-177">Запросы LINQ</span><span class="sxs-lookup"><span data-stu-id="57c9c-177">LINQ Queries</span></span>  
  
-   <span data-ttu-id="57c9c-178">Используйте значимые имена для переменных запроса:</span><span class="sxs-lookup"><span data-stu-id="57c9c-178">Use meaningful names for query variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   <span data-ttu-id="57c9c-179">Укажите имена элементов в запросе, чтобы убедиться в том, что имена свойств анонимных типов верно используются прописные буквы с помощью языка Pascal регистр:</span><span class="sxs-lookup"><span data-stu-id="57c9c-179">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   <span data-ttu-id="57c9c-180">Переименуйте свойства, если имена свойств в результате могут быть неоднозначными.</span><span class="sxs-lookup"><span data-stu-id="57c9c-180">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="57c9c-181">Например, если запрос возвращает клиента, имя и идентификатор заказа, переименуйте их не оставляйте их в виде `Name` и `ID` в результате:</span><span class="sxs-lookup"><span data-stu-id="57c9c-181">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   <span data-ttu-id="57c9c-182">Используйте определение типа в объявлении переменных запроса и переменных диапазона:</span><span class="sxs-lookup"><span data-stu-id="57c9c-182">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   <span data-ttu-id="57c9c-183">Выравнивайте предложения запроса под `From` инструкции:</span><span class="sxs-lookup"><span data-stu-id="57c9c-183">Align query clauses under the `From` statement:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   <span data-ttu-id="57c9c-184">Используйте `Where` перед другие предложения запроса, чтобы более поздние предложения запроса работают отфильтрованный набор данных:</span><span class="sxs-lookup"><span data-stu-id="57c9c-184">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   <span data-ttu-id="57c9c-185">Используйте `Join` предложений, чтобы явно определить операцию join, вместо использования `Where` предложение для неявного определения операции соединения:</span><span class="sxs-lookup"><span data-stu-id="57c9c-185">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="57c9c-186">См. также</span><span class="sxs-lookup"><span data-stu-id="57c9c-186">See Also</span></span>  
 [<span data-ttu-id="57c9c-187">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="57c9c-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
