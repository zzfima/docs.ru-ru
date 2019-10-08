---
title: Соглашения о написании кода в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: 18c309e22cccfa5d835394996fc6974d95825b65
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003121"
---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="63545-102">Соглашения о написании кода в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63545-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="63545-103">Корпорация Майкрософт разрабатывает образцы и документацию, которые соответствуют рекомендациям, приведенным в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="63545-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="63545-104">Если следовать тем же соглашениям о написании кода, вы можете получить следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="63545-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
- <span data-ttu-id="63545-105">Ваш код будет иметь единообразный вид, чтобы читатели могли лучше сосредоточиться на содержимом, а не на макете.</span><span class="sxs-lookup"><span data-stu-id="63545-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
- <span data-ttu-id="63545-106">Читатели смогут быстрее понять код, так как они могут делать предположения на основе предыдущего опыта.</span><span class="sxs-lookup"><span data-stu-id="63545-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
- <span data-ttu-id="63545-107">Вы можете легко копировать, изменять и обслуживать код.</span><span class="sxs-lookup"><span data-stu-id="63545-107">You can copy, change, and maintain the code more easily.</span></span>  
  
- <span data-ttu-id="63545-108">Вы сможете убедиться в том, что код демонстрирует "рекомендации" для Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="63545-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="63545-109">Соглашения об именах</span><span class="sxs-lookup"><span data-stu-id="63545-109">Naming Conventions</span></span>  
  
- <span data-ttu-id="63545-110">Сведения о правилах именования см. в разделе [рекомендации по именованию](../../../standard/design-guidelines/naming-guidelines.md) .</span><span class="sxs-lookup"><span data-stu-id="63545-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span></span>  
  
- <span data-ttu-id="63545-111">Не используйте "My" или "My" как часть имени переменной.</span><span class="sxs-lookup"><span data-stu-id="63545-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="63545-112">Такой подход создает путаницу с объектами `My`.</span><span class="sxs-lookup"><span data-stu-id="63545-112">This practice creates confusion with the `My` objects.</span></span>  
  
- <span data-ttu-id="63545-113">Не нужно изменять имена объектов в автоматически создаваемом коде, чтобы они соответствовали рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="63545-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="63545-114">Соглашения о расположении</span><span class="sxs-lookup"><span data-stu-id="63545-114">Layout Conventions</span></span>  
  
- <span data-ttu-id="63545-115">Вставьте табуляцию в качестве пробелов и используйте интеллектуальные отступы с отступами в четырех пробелах.</span><span class="sxs-lookup"><span data-stu-id="63545-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
- <span data-ttu-id="63545-116">Чтобы переформатировать код в редакторе кода, используйте **достаточное переформатирование** .</span><span class="sxs-lookup"><span data-stu-id="63545-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="63545-117">Дополнительные сведения см. в разделе [Параметры, текстовый редактор, базовый (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="63545-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
- <span data-ttu-id="63545-118">Используйте только один оператор в строке.</span><span class="sxs-lookup"><span data-stu-id="63545-118">Use only one statement per line.</span></span> <span data-ttu-id="63545-119">Не используйте Visual Basic символ разделителя строки (:).</span><span class="sxs-lookup"><span data-stu-id="63545-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
- <span data-ttu-id="63545-120">Старайтесь не использовать явный символ продолжения строки "_" в пользу неявного продолжения строки везде, где это разрешено языком.</span><span class="sxs-lookup"><span data-stu-id="63545-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
- <span data-ttu-id="63545-121">Используйте только одно объявление в строке.</span><span class="sxs-lookup"><span data-stu-id="63545-121">Use only one declaration per line.</span></span>  
  
- <span data-ttu-id="63545-122">Если **Перечисление (переформатирование) кода** не приводит к автоматическому форматированию строк продолжения, следует вручную задать отступ для строк продолжения на одну позицию табуляции.</span><span class="sxs-lookup"><span data-stu-id="63545-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="63545-123">Однако всегда выровняйте элементы в списке по левому краю.</span><span class="sxs-lookup"><span data-stu-id="63545-123">However, always left-align items in a list.</span></span>  
  
    ```vb  
    a As Integer,  
    b As Integer  
    ```  
  
- <span data-ttu-id="63545-124">Добавьте хотя бы одну пустую строку между определениями методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="63545-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="63545-125">Соглашения о комментариях</span><span class="sxs-lookup"><span data-stu-id="63545-125">Commenting Conventions</span></span>  
  
- <span data-ttu-id="63545-126">Заключите комментарии в отдельную строку, а не в конец строки кода.</span><span class="sxs-lookup"><span data-stu-id="63545-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
- <span data-ttu-id="63545-127">Начинать текст комментария с прописной буквы и заканчивать текст комментария точкой.</span><span class="sxs-lookup"><span data-stu-id="63545-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
- <span data-ttu-id="63545-128">Вставьте один пробел между разделителем комментария (') и текстом комментария.</span><span class="sxs-lookup"><span data-stu-id="63545-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#2)]  
  
- <span data-ttu-id="63545-129">Не заключайте комментарии в форматированные блоки звездочек.</span><span class="sxs-lookup"><span data-stu-id="63545-129">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="63545-130">Структура программы</span><span class="sxs-lookup"><span data-stu-id="63545-130">Program Structure</span></span>  
  
- <span data-ttu-id="63545-131">При использовании метода `Main` используйте конструкцию по умолчанию для новых консольных приложений и используйте `My` для аргументов командной строки.</span><span class="sxs-lookup"><span data-stu-id="63545-131">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#3)]  
  
## <a name="language-guidelines"></a><span data-ttu-id="63545-132">Рекомендации по работе с языком</span><span class="sxs-lookup"><span data-stu-id="63545-132">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="63545-133">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="63545-133">String Data Type</span></span>  
  
- <span data-ttu-id="63545-134">Для сцепления коротких строк рекомендуется использовать [интерполяцию строк](https://docs.microsoft.com/dotnet/visual-basic/programming-guide/language-features/strings/interpolated-strings), как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="63545-134">Use [string interpolation](https://docs.microsoft.com/dotnet/visual-basic/programming-guide/language-features/strings/interpolated-strings) to concatenate short strings, as shown in the following code.</span></span>
  
     ```vb
     MsgBox($"hello{vbCrLf}goodbye")
     ```
  
- <span data-ttu-id="63545-135">Чтобы добавить строки в циклы, используйте объект <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="63545-135">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#5)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="63545-136">Ослабленные делегаты в обработчиках событий</span><span class="sxs-lookup"><span data-stu-id="63545-136">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="63545-137">Не следует явно уточнять аргументы (объект и EventArgs) обработчиками событий.</span><span class="sxs-lookup"><span data-stu-id="63545-137">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="63545-138">Если вы не используете аргументы события, передаваемые в событие (например, отправитель как объект, e как EventArgs), используйте ослабленные делегаты и оставьте аргументы событий в коде:</span><span class="sxs-lookup"><span data-stu-id="63545-138">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#7)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="63545-139">Беззнаковый тип данных</span><span class="sxs-lookup"><span data-stu-id="63545-139">Unsigned Data Type</span></span>  
  
- <span data-ttu-id="63545-140">Используйте `Integer` вместо неподписанных типов, за исключением тех случаев, когда они необходимы.</span><span class="sxs-lookup"><span data-stu-id="63545-140">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="63545-141">Массивы</span><span class="sxs-lookup"><span data-stu-id="63545-141">Arrays</span></span>  
  
- <span data-ttu-id="63545-142">Используйте короткий синтаксис при инициализации массивов в строке объявления.</span><span class="sxs-lookup"><span data-stu-id="63545-142">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="63545-143">Например, используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="63545-143">For example, use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#8)]  
  
     <span data-ttu-id="63545-144">Не используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="63545-144">Do not use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#9)]  
  
- <span data-ttu-id="63545-145">Установите обозначение массива на тип, а не на переменную.</span><span class="sxs-lookup"><span data-stu-id="63545-145">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="63545-146">Например, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="63545-146">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#11)]  
  
     <span data-ttu-id="63545-147">Не используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="63545-147">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#10)]  
  
- <span data-ttu-id="63545-148">Используйте синтаксис {} при объявлении и инициализации массивов базовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="63545-148">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="63545-149">Например, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="63545-149">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#12)]  
  
     <span data-ttu-id="63545-150">Не используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="63545-150">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#13)]  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="63545-151">Использование ключевого слова WITH</span><span class="sxs-lookup"><span data-stu-id="63545-151">Use the With Keyword</span></span>  
 <span data-ttu-id="63545-152">При выполнении серии вызовов одного объекта рассмотрите возможность использования ключевого слова `With`:</span><span class="sxs-lookup"><span data-stu-id="63545-152">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#15)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="63545-153">Используйте параметр try... Перехватывать и использовать операторы при использовании обработки исключений</span><span class="sxs-lookup"><span data-stu-id="63545-153">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="63545-154">Не используйте `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="63545-154">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="63545-155">Использование ключевого слова IsNot</span><span class="sxs-lookup"><span data-stu-id="63545-155">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="63545-156">Вместо `Not...Is Nothing` используйте ключевое слово `IsNot`.</span><span class="sxs-lookup"><span data-stu-id="63545-156">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="63545-157">Создать ключевое слово</span><span class="sxs-lookup"><span data-stu-id="63545-157">New Keyword</span></span>  
  
- <span data-ttu-id="63545-158">Используйте короткий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="63545-158">Use short instantiation.</span></span> <span data-ttu-id="63545-159">Например, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="63545-159">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#21)]  
  
     <span data-ttu-id="63545-160">Предыдущая строка эквивалентна следующей:</span><span class="sxs-lookup"><span data-stu-id="63545-160">The preceding line is equivalent to this:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#22)]  
  
- <span data-ttu-id="63545-161">Используйте инициализаторы объектов для новых объектов вместо конструктора без параметров:</span><span class="sxs-lookup"><span data-stu-id="63545-161">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#23)]  
  
### <a name="event-handling"></a><span data-ttu-id="63545-162">Обработка событий</span><span class="sxs-lookup"><span data-stu-id="63545-162">Event Handling</span></span>  
  
- <span data-ttu-id="63545-163">Используйте `Handles` вместо `AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="63545-163">Use `Handles` rather than `AddHandler`:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#24)]  
  
- <span data-ttu-id="63545-164">Используйте `AddressOf` и не создавайте делегата явным образом:</span><span class="sxs-lookup"><span data-stu-id="63545-164">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#25)]  
  
- <span data-ttu-id="63545-165">При определении события используйте короткий синтаксис и позвольте компилятору определить делегат:</span><span class="sxs-lookup"><span data-stu-id="63545-165">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#26)]  
  
- <span data-ttu-id="63545-166">Не проверяйте, является ли событие `Nothing` (null) перед вызовом метода `RaiseEvent`.</span><span class="sxs-lookup"><span data-stu-id="63545-166">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="63545-167">`RaiseEvent` проверяет наличие `Nothing` перед вызовом события.</span><span class="sxs-lookup"><span data-stu-id="63545-167">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="63545-168">Использование общих членов</span><span class="sxs-lookup"><span data-stu-id="63545-168">Using Shared Members</span></span>  
 <span data-ttu-id="63545-169">Вызовите `Shared` членов с помощью имени класса, а не из переменной экземпляра.</span><span class="sxs-lookup"><span data-stu-id="63545-169">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="63545-170">Использовать литералы XML</span><span class="sxs-lookup"><span data-stu-id="63545-170">Use XML Literals</span></span>  
 <span data-ttu-id="63545-171">XML-литералы упрощают наиболее распространенные задачи, возникающие при работе с XML (например, Загрузка, запрос и преобразование).</span><span class="sxs-lookup"><span data-stu-id="63545-171">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="63545-172">При разработке с использованием XML-кода следуйте приведенным ниже рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="63545-172">When you develop with XML, follow these guidelines:</span></span>  
  
- <span data-ttu-id="63545-173">Используйте литералы XML для создания XML-документов и фрагментов вместо непосредственного вызова API XML.</span><span class="sxs-lookup"><span data-stu-id="63545-173">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
- <span data-ttu-id="63545-174">Импортируйте пространства имен XML на уровне файла или проекта, чтобы воспользоваться преимуществами оптимизации производительности для XML-литералов.</span><span class="sxs-lookup"><span data-stu-id="63545-174">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
- <span data-ttu-id="63545-175">Используйте свойства осей XML для доступа к элементам и атрибутам в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="63545-175">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
- <span data-ttu-id="63545-176">Используйте внедренные выражения для включения значений и создания XML на основе существующих значений вместо использования вызовов API, таких как метод `Add`:</span><span class="sxs-lookup"><span data-stu-id="63545-176">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#27)]  
  
### <a name="linq-queries"></a><span data-ttu-id="63545-177">Запросы LINQ</span><span class="sxs-lookup"><span data-stu-id="63545-177">LINQ Queries</span></span>  
  
- <span data-ttu-id="63545-178">Используйте значимые имена для переменных запроса:</span><span class="sxs-lookup"><span data-stu-id="63545-178">Use meaningful names for query variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#28)]  
  
- <span data-ttu-id="63545-179">Укажите имена элементов в запросе, чтобы убедиться, что имена свойств анонимных типов правильно заменяются прописными буквами, используя регистр языка Pascal:</span><span class="sxs-lookup"><span data-stu-id="63545-179">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#29)]  
  
- <span data-ttu-id="63545-180">Переименуйте свойства, если имена свойств в результате могут быть неоднозначными.</span><span class="sxs-lookup"><span data-stu-id="63545-180">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="63545-181">Например, если запрос возвращает имя клиента и идентификатор заказа, переименуйте их вместо того, чтобы не выходить из них как `Name` и `ID` в результате:</span><span class="sxs-lookup"><span data-stu-id="63545-181">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#30)]  
  
- <span data-ttu-id="63545-182">Используйте определение типа в объявлении переменных запроса и переменных диапазона:</span><span class="sxs-lookup"><span data-stu-id="63545-182">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#31)]  
  
- <span data-ttu-id="63545-183">Выровняйте предложения запроса в операторе `From`:</span><span class="sxs-lookup"><span data-stu-id="63545-183">Align query clauses under the `From` statement:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#32)]  
  
- <span data-ttu-id="63545-184">Используйте предложения `Where` перед другими предложениями запроса, чтобы последующие предложения запроса работали с отфильтрованным набором данных:</span><span class="sxs-lookup"><span data-stu-id="63545-184">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#33)]  
  
- <span data-ttu-id="63545-185">Используйте предложение `Join`, чтобы явно определить операцию объединения вместо использования предложения `Where` для неявного определения операции объединения:</span><span class="sxs-lookup"><span data-stu-id="63545-185">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="63545-186">См. также</span><span class="sxs-lookup"><span data-stu-id="63545-186">See also</span></span>

- [<span data-ttu-id="63545-187">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="63545-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
