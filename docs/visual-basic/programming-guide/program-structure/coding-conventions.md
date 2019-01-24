---
title: Соглашения о написании кода в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: f2b1676ae959c5426af3021bbd340980115c5da6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724886"
---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="c9e3a-102">Соглашения о написании кода в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9e3a-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="c9e3a-103">Корпорация Microsoft разрабатывает примеры и документация, следуйте указаниям, изложенным в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="c9e3a-104">Если следовать тем же правилам кодирования, может получить следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
-   <span data-ttu-id="c9e3a-105">Код будет иметь согласованный вид, таким образом, чтобы читателям сосредоточиться на содержимом, а не на макете.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="c9e3a-106">Читателям понять ваш код более быстро, так как они могут делать предположения, основанные на опыте.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="c9e3a-107">Можно скопировать, изменить и сохранить код проще.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-107">You can copy, change, and maintain the code more easily.</span></span>  
  
-   <span data-ttu-id="c9e3a-108">Позволяет убедиться, что код демонстрирует «рекомендации» для Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="c9e3a-109">Соглашения об именах</span><span class="sxs-lookup"><span data-stu-id="c9e3a-109">Naming Conventions</span></span>  
  
-   <span data-ttu-id="c9e3a-110">Сведения о рекомендациях по именованию см. в разделе [рекомендации по именованию](../../../standard/design-guidelines/naming-guidelines.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span></span>  
  
-   <span data-ttu-id="c9e3a-111">Не используйте «Mу» или «my» как часть имени переменной.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="c9e3a-112">Этом создается путаница с `My` объектов.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-112">This practice creates confusion with the `My` objects.</span></span>  
  
-   <span data-ttu-id="c9e3a-113">У вас нет необходимости изменять имена объектов в автоматически созданный код, чтобы сделать их соответствие с правилами.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="c9e3a-114">Соглашения о расположении</span><span class="sxs-lookup"><span data-stu-id="c9e3a-114">Layout Conventions</span></span>  
  
-   <span data-ttu-id="c9e3a-115">Вставьте табуляции как пробелы и используйте автоматический отступы с 4 пробела.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
-   <span data-ttu-id="c9e3a-116">Используйте **автоматическое форматирование (переформатирование) кода** чтобы переформатировать код в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="c9e3a-117">Дополнительные сведения см. в разделе ["Параметры", "Текстовый редактор, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c9e3a-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
-   <span data-ttu-id="c9e3a-118">Используйте только одну инструкцию в строке.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-118">Use only one statement per line.</span></span> <span data-ttu-id="c9e3a-119">Не используйте Visual Basic символ разделения строки (:).</span><span class="sxs-lookup"><span data-stu-id="c9e3a-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
-   <span data-ttu-id="c9e3a-120">Избегайте использования символа продолжения явные строки «_» лучше неявное продолжение строки, везде, где это позволяет язык.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
-   <span data-ttu-id="c9e3a-121">Используйте только одно объявление в строке.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-121">Use only one declaration per line.</span></span>  
  
-   <span data-ttu-id="c9e3a-122">Если **автоматическое форматирование (переформатирование) кода** не форматирует строки продолжения автоматически, вручную отступ продолжения строки одним символом табуляции.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="c9e3a-123">Тем не менее всегда влево элементов в списке.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-123">However, always left-align items in a list.</span></span>  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   <span data-ttu-id="c9e3a-124">Добавьте по крайней мере одну пустую строку между определениями методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="c9e3a-125">Соглашения о комментариях</span><span class="sxs-lookup"><span data-stu-id="c9e3a-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="c9e3a-126">Размещение комментария в отдельной строке, а не в конце строки кода.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="c9e3a-127">Текст комментария с прописной буквы и заканчивайте текст комментария точкой начала.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
-   <span data-ttu-id="c9e3a-128">Вставьте один пробел между разделителем комментария (') и текстом комментария.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   <span data-ttu-id="c9e3a-129">Не окружайте комментарии звездочками.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-129">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="c9e3a-130">Структура программы</span><span class="sxs-lookup"><span data-stu-id="c9e3a-130">Program Structure</span></span>  
  
-   <span data-ttu-id="c9e3a-131">При использовании `Main` метод, применяйте конструктор по умолчанию для новых консольных приложений и использовать `My` для аргументов командной строки.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-131">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a><span data-ttu-id="c9e3a-132">Рекомендации по работе с языком</span><span class="sxs-lookup"><span data-stu-id="c9e3a-132">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="c9e3a-133">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="c9e3a-133">String Data Type</span></span>  
  
-   <span data-ttu-id="c9e3a-134">Для объединения строк, используется амперсанд (&).</span><span class="sxs-lookup"><span data-stu-id="c9e3a-134">To concatenate strings, use an ampersand (&).</span></span>  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   <span data-ttu-id="c9e3a-135">Для добавления строк в циклы, рекомендуется использовать <xref:System.Text.StringBuilder> объекта.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-135">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="c9e3a-136">Ослабленные делегаты в обработчиках событий</span><span class="sxs-lookup"><span data-stu-id="c9e3a-136">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="c9e3a-137">Не надо явным образом квалифицировать аргументы (объект и EventArgs) обработчикам событий.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-137">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="c9e3a-138">Если вы не используете аргументы события, которые передаются на событие (например, отправитель как объект, e как EventArgs), используйте ослабленные делегаты и пропускайте аргументы событий в коде:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-138">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="c9e3a-139">Беззнаковый тип данных</span><span class="sxs-lookup"><span data-stu-id="c9e3a-139">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="c9e3a-140">Используйте `Integer` вместо беззнаковых типов, за исключением случаев, когда они необходимы.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-140">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="c9e3a-141">Массивы</span><span class="sxs-lookup"><span data-stu-id="c9e3a-141">Arrays</span></span>  
  
-   <span data-ttu-id="c9e3a-142">Используйте короткий синтаксис при инициализации массивов в строке объявления.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-142">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="c9e3a-143">Например используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-143">For example, use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     <span data-ttu-id="c9e3a-144">Не используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-144">Do not use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   <span data-ttu-id="c9e3a-145">Установите обозначение массива как тип, а не на переменную.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-145">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="c9e3a-146">Например используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-146">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     <span data-ttu-id="c9e3a-147">Не используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-147">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   <span data-ttu-id="c9e3a-148">Используйте синтаксис {} при объявлении и инициализации массивов основных типов данных.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-148">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="c9e3a-149">Например используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-149">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     <span data-ttu-id="c9e3a-150">Не используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-150">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="c9e3a-151">Используется с ключевым словом</span><span class="sxs-lookup"><span data-stu-id="c9e3a-151">Use the With Keyword</span></span>  
 <span data-ttu-id="c9e3a-152">При выполнении ряда вызовов одного объекта, рассмотрите возможность использования `With` ключевое слово:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-152">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="c9e3a-153">Использование операторов Try... Catch и операторы Using при использовании обработки исключений</span><span class="sxs-lookup"><span data-stu-id="c9e3a-153">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="c9e3a-154">Не используйте `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-154">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="c9e3a-155">Используйте ключевое слово IsNot</span><span class="sxs-lookup"><span data-stu-id="c9e3a-155">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="c9e3a-156">Используйте `IsNot` ключевое слово `Not...Is Nothing`.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-156">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="c9e3a-157">Новое ключевое слово</span><span class="sxs-lookup"><span data-stu-id="c9e3a-157">New Keyword</span></span>  
  
-   <span data-ttu-id="c9e3a-158">Используйте короткий способ создания экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-158">Use short instantiation.</span></span> <span data-ttu-id="c9e3a-159">Например используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-159">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     <span data-ttu-id="c9e3a-160">Предыдущая строка эквивалентна следующей:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-160">The preceding line is equivalent to this:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   <span data-ttu-id="c9e3a-161">Используйте инициализаторы объектов для новых объектов вместо конструкторов:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-161">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a><span data-ttu-id="c9e3a-162">Обработка событий</span><span class="sxs-lookup"><span data-stu-id="c9e3a-162">Event Handling</span></span>  
  
-   <span data-ttu-id="c9e3a-163">Используйте `Handles` вместо `AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-163">Use `Handles` rather than `AddHandler`:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   <span data-ttu-id="c9e3a-164">Используйте `AddressOf`и не создавайте экземпляр делегата явным образом:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-164">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   <span data-ttu-id="c9e3a-165">При определении события, используйте короткий синтаксис и позвольте компилятору определить делегат:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-165">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   <span data-ttu-id="c9e3a-166">Не проверять, является ли событие `Nothing` (null), перед вызовом метода `RaiseEvent` метод.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-166">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="c9e3a-167">`RaiseEvent` проверяет наличие `Nothing` прежде, чем он вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-167">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="c9e3a-168">Использование общих членов</span><span class="sxs-lookup"><span data-stu-id="c9e3a-168">Using Shared Members</span></span>  
 <span data-ttu-id="c9e3a-169">Вызовите `Shared` члены с помощью имени класса, а не переменной экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-169">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="c9e3a-170">Использование XML-литералов</span><span class="sxs-lookup"><span data-stu-id="c9e3a-170">Use XML Literals</span></span>  
 <span data-ttu-id="c9e3a-171">Литералы XML упрощают наиболее распространенных задач, возникающих при работе с XML (например, нагрузки, запроса и преобразования).</span><span class="sxs-lookup"><span data-stu-id="c9e3a-171">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="c9e3a-172">При разработке с использованием XML, придерживайтесь следующих рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-172">When you develop with XML, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="c9e3a-173">Используйте литералы XML для создания XML-документов и фрагментов вместо прямого вызова интерфейсов API.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-173">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
-   <span data-ttu-id="c9e3a-174">Импортируйте пространство имен XML на уровне файла или проекта, чтобы воспользоваться преимуществами оптимизации производительности для XML-литералов.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-174">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
-   <span data-ttu-id="c9e3a-175">Используйте свойства оси XML для доступа к элементам и атрибутам в XML-документа.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-175">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
-   <span data-ttu-id="c9e3a-176">Используйте внедренные выражения для включения значений и создания XML на основе существующих значений вместо использования вызовов API, таких как `Add` метод:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-176">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a><span data-ttu-id="c9e3a-177">Запросы LINQ</span><span class="sxs-lookup"><span data-stu-id="c9e3a-177">LINQ Queries</span></span>  
  
-   <span data-ttu-id="c9e3a-178">Используйте значимые имена для переменных запроса:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-178">Use meaningful names for query variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   <span data-ttu-id="c9e3a-179">Обозначайте элементы в запросе, чтобы убедиться в том, что имена свойств анонимных типов правильно капитализированы при помощи языка Pascal регистр:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-179">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   <span data-ttu-id="c9e3a-180">Переименуйте свойства, если имена свойств в результате могут быть неоднозначными.</span><span class="sxs-lookup"><span data-stu-id="c9e3a-180">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="c9e3a-181">Например, если запрос возвращает клиента, имя и идентификатор заказа, переименовать их вместо использования их в виде `Name` и `ID` в результате:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-181">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   <span data-ttu-id="c9e3a-182">Используйте определение типа в объявлении переменных запроса и переменных диапазона:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-182">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   <span data-ttu-id="c9e3a-183">Выравнивайте предложения запроса под `From` инструкции:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-183">Align query clauses under the `From` statement:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   <span data-ttu-id="c9e3a-184">Используйте `Where` предложения перед другими предложения запроса, чтобы более поздние предложения запроса работают отфильтрованный набор данных:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-184">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   <span data-ttu-id="c9e3a-185">Используйте `Join` предложение для явного определения операции соединения вместо использования `Where` предложение для неявного определения операции соединения:</span><span class="sxs-lookup"><span data-stu-id="c9e3a-185">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c9e3a-186">См. также</span><span class="sxs-lookup"><span data-stu-id="c9e3a-186">See also</span></span>
- [<span data-ttu-id="c9e3a-187">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="c9e3a-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
