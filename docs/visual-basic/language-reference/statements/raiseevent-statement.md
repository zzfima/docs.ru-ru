---
title: Оператор RaiseEvent
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: 19949fbdb1c1c54556876323d839b16fc01608f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605346"
---
# <a name="raiseevent-statement"></a><span data-ttu-id="ff9b5-102">Оператор RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="ff9b5-102">RaiseEvent Statement</span></span>
<span data-ttu-id="ff9b5-103">Вызывает событие, объявленное на уровне модуля в классе, форме или документе.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-103">Triggers an event declared at module level within a class, form, or document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff9b5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff9b5-104">Syntax</span></span>  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a><span data-ttu-id="ff9b5-105">Части</span><span class="sxs-lookup"><span data-stu-id="ff9b5-105">Parts</span></span>  
 `eventname`  
 <span data-ttu-id="ff9b5-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-106">Required.</span></span> <span data-ttu-id="ff9b5-107">Имя события.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-107">Name of the event to trigger.</span></span>  
  
 `argumentlist`  
 <span data-ttu-id="ff9b5-108">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-108">Optional.</span></span> <span data-ttu-id="ff9b5-109">Разделенный запятыми список переменных, массивов и выражений.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-109">Comma-delimited list of variables, arrays, or expressions.</span></span> <span data-ttu-id="ff9b5-110">`argumentlist` Аргумент должен быть заключен в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-110">The `argumentlist` argument must be enclosed by parentheses.</span></span> <span data-ttu-id="ff9b5-111">Если не указаны аргументы, следует опустить круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-111">If there are no arguments, the parentheses must be omitted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff9b5-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="ff9b5-112">Remarks</span></span>  
 <span data-ttu-id="ff9b5-113">Необходимая `eventname` является именем события, объявленного внутри модуля.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-113">The required `eventname` is the name of an event declared within the module.</span></span> <span data-ttu-id="ff9b5-114">Следует правилам именования переменных Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-114">It follows Visual Basic variable naming conventions.</span></span>  
  
 <span data-ttu-id="ff9b5-115">Если не был объявлен внутри модуля, в котором оно возникает событие, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-115">If the event has not been declared within the module in which it is raised, an error occurs.</span></span> <span data-ttu-id="ff9b5-116">В следующем фрагменте кода демонстрируется объявление события и процедура, в котором вызывается событие.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-116">The following code fragment illustrates an event declaration and a procedure in which the event is raised.</span></span>  
  
 [!code-vb[VbVbalrEvents#37](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]  
  
 <span data-ttu-id="ff9b5-117">Нельзя использовать `RaiseEvent` для вызова событий, которые не объявлены явно в модуле.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-117">You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module.</span></span> <span data-ttu-id="ff9b5-118">Например, наследуют все формы <xref:System.Windows.Forms.Control.Click> события из <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, не может быть изменен с помощью `RaiseEvent` в производной форме.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-118">For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, it cannot be raised using `RaiseEvent` in a derived form.</span></span> <span data-ttu-id="ff9b5-119">При объявлении `Click` событий в модуле формы, он скрывает формы собственные <xref:System.Windows.Forms.Control.Click> событий.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-119">If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="ff9b5-120">Формы можно по-прежнему вызывать <xref:System.Windows.Forms.Control.Click> события путем вызова <xref:System.Windows.Forms.Control.OnClick%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-120">You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="ff9b5-121">По умолчанию события, определенного в Visual Basic вызывает обработчики событий в порядке установки подключений.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-121">By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established.</span></span> <span data-ttu-id="ff9b5-122">Поскольку события могут содержать `ByRef` параметров, процесс, подключившийся позже, может получить параметры, измененные предыдущим обработчиком событий.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-122">Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler.</span></span> <span data-ttu-id="ff9b5-123">После выполнения обработчиков событий управление возвращается подпрограмме, вызвавшей событие.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-123">After the event handlers execute, control is returned to the subroutine that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff9b5-124">События, не являющиеся общими, не должен вызываться в конструкторе класса, в котором они объявлены.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-124">Non-shared events should not be raised within the constructor of the class in which they are declared.</span></span> <span data-ttu-id="ff9b5-125">Несмотря на то, что такие события не вызывают ошибки во время выполнения, они могут не обнаруживаться связанными обработчиками событий.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-125">Although such events do not cause run-time errors, they may fail to be caught by associated event handlers.</span></span> <span data-ttu-id="ff9b5-126">Используйте `Shared` модификатор для создания общего события, если необходимо вызвать событие в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-126">Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff9b5-127">Поведение события по умолчанию можно изменить, указав пользовательское событие.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-127">You can change the default behavior of events by defining a custom event.</span></span> <span data-ttu-id="ff9b5-128">Для пользовательских событий `RaiseEvent` инструкция вызывает событие `RaiseEvent` метода доступа.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-128">For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor.</span></span> <span data-ttu-id="ff9b5-129">Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ff9b5-129">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff9b5-130">Пример</span><span class="sxs-lookup"><span data-stu-id="ff9b5-130">Example</span></span>  
 <span data-ttu-id="ff9b5-131">В следующем примере события используются для выполнения обратного отсчета от 10 до 0 секунд.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-131">The following example uses events to count down seconds from 10 to 0.</span></span> <span data-ttu-id="ff9b5-132">Код иллюстрирует различные связанные с событиями методы, свойства и операторы, включая `RaiseEvent` инструкции.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-132">The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.</span></span>  
  
 <span data-ttu-id="ff9b5-133">Класс, который вызывает событие, является источником события, а методы, обрабатывающие события, — обработчиками событий.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-133">The class that raises an event is the event source, and the methods that process the event are the event handlers.</span></span> <span data-ttu-id="ff9b5-134">Источник события может иметь несколько обработчиков для создаваемых им событий.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-134">An event source can have multiple handlers for the events it generates.</span></span> <span data-ttu-id="ff9b5-135">Когда класс создает событие, это событие создается во всех классах, выбранных для обработки событий данного экземпляра объекта.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-135">When the class raises the event, that event is raised on every class that has elected to handle events for that instance of the object.</span></span>  
  
 <span data-ttu-id="ff9b5-136">В примере также используется форма (`Form1`) с кнопкой (`Button1`) и текстовым полем (`TextBox1`).</span><span class="sxs-lookup"><span data-stu-id="ff9b5-136">The example also uses a form (`Form1`) with a button (`Button1`) and a text box (`TextBox1`).</span></span> <span data-ttu-id="ff9b5-137">При нажатии кнопки в первом текстовом поле отображается обратный отсчет от 10 до 0 секунд.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-137">When you click the button, the first text box displays a countdown from 10 to 0 seconds.</span></span> <span data-ttu-id="ff9b5-138">По истечении всего времени (10 секунд) в первом текстовом поле отображается надпись Done.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-138">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
 <span data-ttu-id="ff9b5-139">Код для `Form1` указывает начальное и конечное состояния формы.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-139">The code for `Form1` specifies the initial and terminal states of the form.</span></span> <span data-ttu-id="ff9b5-140">Он также содержит код, выполняемый при создании событий.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-140">It also contains the code executed when events are raised.</span></span>  
  
 <span data-ttu-id="ff9b5-141">Чтобы использовать этот пример, откройте новый проект приложения Windows, добавьте кнопку с именем `Button1` и текстовое поле с именем `TextBox1` в главную форму с именем `Form1`.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-141">To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`.</span></span> <span data-ttu-id="ff9b5-142">Затем щелкните правой кнопкой мыши форму и нажмите кнопку **Просмотр кода** , чтобы открыть редактор кода.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-142">Then right-click the form and click **View Code** to open the Code Editor.</span></span>  
  
 <span data-ttu-id="ff9b5-143">Добавить `WithEvents` раздел объявлений переменных `Form1` класса.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-143">Add a `WithEvents` variable to the declarations section of the `Form1` class.</span></span>  
  
 [!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="ff9b5-144">Пример</span><span class="sxs-lookup"><span data-stu-id="ff9b5-144">Example</span></span>  
 <span data-ttu-id="ff9b5-145">Добавьте следующий код в код для `Form1`.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-145">Add the following code to the code for `Form1`.</span></span> <span data-ttu-id="ff9b5-146">Замените все повторяющиеся процедуры, которые могут существовать, такие как `Form_Load`, или `Button_Click`.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-146">Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.</span></span>  
  
 [!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]  
  
 <span data-ttu-id="ff9b5-147">Нажмите клавишу F5 для запуска примера и нажмите кнопку с многоточием **запустить**.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-147">Press F5 to run the preceding example, and click the button labeled **Start**.</span></span> <span data-ttu-id="ff9b5-148">Первое текстовое поле начинает обратный отсчет.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-148">The first text box starts to count down the seconds.</span></span> <span data-ttu-id="ff9b5-149">По истечении всего времени (10 секунд) в первом текстовом поле отображается надпись Done.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-149">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff9b5-150">`My.Application.DoEvents` Метод отличается от обработки событий в точно так же, как и в форме.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-150">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="ff9b5-151">Чтобы разрешить форме обрабатывать события напрямую, можно использовать многопоточность.</span><span class="sxs-lookup"><span data-stu-id="ff9b5-151">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="ff9b5-152">Дополнительные сведения см. в разделе [потоки](../../programming-guide/concepts/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="ff9b5-152">For more information, see [Threading](../../programming-guide/concepts/threading/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff9b5-153">См. также</span><span class="sxs-lookup"><span data-stu-id="ff9b5-153">See Also</span></span>  
 [<span data-ttu-id="ff9b5-154">События</span><span class="sxs-lookup"><span data-stu-id="ff9b5-154">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="ff9b5-155">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="ff9b5-155">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="ff9b5-156">Оператор AddHandler</span><span class="sxs-lookup"><span data-stu-id="ff9b5-156">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [<span data-ttu-id="ff9b5-157">Оператор RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="ff9b5-157">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [<span data-ttu-id="ff9b5-158">Handles</span><span class="sxs-lookup"><span data-stu-id="ff9b5-158">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
