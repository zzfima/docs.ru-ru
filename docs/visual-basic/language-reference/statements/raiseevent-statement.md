---
title: "Оператор RaiseEvent | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
dev_langs:
- VB
helpviewer_keywords:
- raising events, RaiseEvent statement
- RaiseEvent statement
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
caps.latest.revision: 19
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
ms.openlocfilehash: 6a0cf1c5635335f22fddd57c7dd2baaeca6ddd23
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="raiseevent-statement"></a><span data-ttu-id="e62d8-102">Оператор RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="e62d8-102">RaiseEvent Statement</span></span>
<span data-ttu-id="e62d8-103">Вызывает событие, объявленное на уровне модуля в классе, форме или документе.</span><span class="sxs-lookup"><span data-stu-id="e62d8-103">Triggers an event declared at module level within a class, form, or document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e62d8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e62d8-104">Syntax</span></span>  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a><span data-ttu-id="e62d8-105">Части</span><span class="sxs-lookup"><span data-stu-id="e62d8-105">Parts</span></span>  
 `eventname`  
 <span data-ttu-id="e62d8-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="e62d8-106">Required.</span></span> <span data-ttu-id="e62d8-107">Имя события.</span><span class="sxs-lookup"><span data-stu-id="e62d8-107">Name of the event to trigger.</span></span>  
  
 `argumentlist`  
 <span data-ttu-id="e62d8-108">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="e62d8-108">Optional.</span></span> <span data-ttu-id="e62d8-109">Разделенный запятыми список переменных, массивов и выражений.</span><span class="sxs-lookup"><span data-stu-id="e62d8-109">Comma-delimited list of variables, arrays, or expressions.</span></span> <span data-ttu-id="e62d8-110">`argumentlist` Аргумент должен быть заключен в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="e62d8-110">The `argumentlist` argument must be enclosed by parentheses.</span></span> <span data-ttu-id="e62d8-111">Если не указано никаких аргументов, скобки следует опустить.</span><span class="sxs-lookup"><span data-stu-id="e62d8-111">If there are no arguments, the parentheses must be omitted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e62d8-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="e62d8-112">Remarks</span></span>  
 <span data-ttu-id="e62d8-113">Обязательный `eventname` имя события, объявленного внутри модуля.</span><span class="sxs-lookup"><span data-stu-id="e62d8-113">The required `eventname` is the name of an event declared within the module.</span></span> <span data-ttu-id="e62d8-114">Следует правилам именования переменных Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e62d8-114">It follows Visual Basic variable naming conventions.</span></span>  
  
 <span data-ttu-id="e62d8-115">Если не была объявлена в модуле, в котором возникает событие, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="e62d8-115">If the event has not been declared within the module in which it is raised, an error occurs.</span></span> <span data-ttu-id="e62d8-116">В следующем фрагменте кода демонстрируется объявление события и процедура, в которой возникает событие.</span><span class="sxs-lookup"><span data-stu-id="e62d8-116">The following code fragment illustrates an event declaration and a procedure in which the event is raised.</span></span>  
  
 <span data-ttu-id="e62d8-117">[!code-vb[VbVbalrEvents&#37;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e62d8-117">[!code-vb[VbVbalrEvents#37](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]</span></span>  
  
 <span data-ttu-id="e62d8-118">Нельзя использовать `RaiseEvent` для создания событий, которые не объявлены явно в модуле.</span><span class="sxs-lookup"><span data-stu-id="e62d8-118">You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module.</span></span> <span data-ttu-id="e62d8-119">Например, наследуют все формы <xref:System.Windows.Forms.Control.Click>событие <xref:System.Windows.Forms.Form?displayProperty=fullName>, не может быть изменен с помощью `RaiseEvent` в производной форме.</xref:System.Windows.Forms.Form?displayProperty=fullName> </xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="e62d8-119">For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=fullName>, it cannot be raised using `RaiseEvent` in a derived form.</span></span> <span data-ttu-id="e62d8-120">При объявлении `Click` событий в модуле формы он скрывает формы собственный <xref:System.Windows.Forms.Control.Click>событий.</xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="e62d8-120">If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="e62d8-121">Можно по-прежнему вызывать формы <xref:System.Windows.Forms.Control.Click>событие путем вызова <xref:System.Windows.Forms.Control.OnClick%2A>метод.</xref:System.Windows.Forms.Control.OnClick%2A> </xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="e62d8-121">You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="e62d8-122">По умолчанию события, определенные в Visual Basic вызывает обработчики событий в порядке установки подключений.</span><span class="sxs-lookup"><span data-stu-id="e62d8-122">By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established.</span></span> <span data-ttu-id="e62d8-123">Поскольку события могут содержать `ByRef` параметров, процесс, подключившийся позже, может получить параметры, измененные предыдущим обработчиком события.</span><span class="sxs-lookup"><span data-stu-id="e62d8-123">Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler.</span></span> <span data-ttu-id="e62d8-124">После выполнения обработчиков событий управление возвращается подпрограмме, вызвавшей событие.</span><span class="sxs-lookup"><span data-stu-id="e62d8-124">After the event handlers execute, control is returned to the subroutine that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e62d8-125">Обычные события не должна возникать в конструкторе класса, в котором они объявлены.</span><span class="sxs-lookup"><span data-stu-id="e62d8-125">Non-shared events should not be raised within the constructor of the class in which they are declared.</span></span> <span data-ttu-id="e62d8-126">Хотя такие события не вызывают ошибки во время выполнения, они не будут перехватываться связанными обработчиками событий.</span><span class="sxs-lookup"><span data-stu-id="e62d8-126">Although such events do not cause run-time errors, they may fail to be caught by associated event handlers.</span></span> <span data-ttu-id="e62d8-127">Используйте `Shared` модификатор для создания совместно используемых событий, если необходимо вызвать событие из конструктора.</span><span class="sxs-lookup"><span data-stu-id="e62d8-127">Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e62d8-128">События по умолчанию можно изменить, определив пользовательское событие.</span><span class="sxs-lookup"><span data-stu-id="e62d8-128">You can change the default behavior of events by defining a custom event.</span></span> <span data-ttu-id="e62d8-129">Для пользовательских событий `RaiseEvent` инструкция вызывает событие `RaiseEvent` доступа.</span><span class="sxs-lookup"><span data-stu-id="e62d8-129">For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor.</span></span> <span data-ttu-id="e62d8-130">Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e62d8-130">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e62d8-131">Пример</span><span class="sxs-lookup"><span data-stu-id="e62d8-131">Example</span></span>  
 <span data-ttu-id="e62d8-132">В следующем примере события используются для выполнения обратного отсчета от 10 до 0 секунд.</span><span class="sxs-lookup"><span data-stu-id="e62d8-132">The following example uses events to count down seconds from 10 to 0.</span></span> <span data-ttu-id="e62d8-133">Код иллюстрирует некоторые из связанных с событием методы, свойства и операторы, включая `RaiseEvent` инструкции.</span><span class="sxs-lookup"><span data-stu-id="e62d8-133">The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.</span></span>  
  
 <span data-ttu-id="e62d8-134">Класс, который вызывает событие, является источником события, а методы, обрабатывающие события, — обработчиками событий.</span><span class="sxs-lookup"><span data-stu-id="e62d8-134">The class that raises an event is the event source, and the methods that process the event are the event handlers.</span></span> <span data-ttu-id="e62d8-135">Источник события может иметь несколько обработчиков для создаваемых им событий.</span><span class="sxs-lookup"><span data-stu-id="e62d8-135">An event source can have multiple handlers for the events it generates.</span></span> <span data-ttu-id="e62d8-136">Когда класс создает событие, это событие создается во всех классах, выбранных для обработки событий данного экземпляра объекта.</span><span class="sxs-lookup"><span data-stu-id="e62d8-136">When the class raises the event, that event is raised on every class that has elected to handle events for that instance of the object.</span></span>  
  
 <span data-ttu-id="e62d8-137">В примере также используется форма (`Form1`) с кнопкой (`Button1`) и текстовым полем (`TextBox1`).</span><span class="sxs-lookup"><span data-stu-id="e62d8-137">The example also uses a form (`Form1`) with a button (`Button1`) and a text box (`TextBox1`).</span></span> <span data-ttu-id="e62d8-138">При нажатии кнопки в первом текстовом поле отображается обратный отсчет от 10 до 0 секунд.</span><span class="sxs-lookup"><span data-stu-id="e62d8-138">When you click the button, the first text box displays a countdown from 10 to 0 seconds.</span></span> <span data-ttu-id="e62d8-139">По истечении всего времени (10 секунд) в первом текстовом поле отображается надпись Done.</span><span class="sxs-lookup"><span data-stu-id="e62d8-139">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
 <span data-ttu-id="e62d8-140">Код для `Form1` указывает начальное и конечное состояния формы.</span><span class="sxs-lookup"><span data-stu-id="e62d8-140">The code for `Form1` specifies the initial and terminal states of the form.</span></span> <span data-ttu-id="e62d8-141">Он также содержит код, выполняемый при создании событий.</span><span class="sxs-lookup"><span data-stu-id="e62d8-141">It also contains the code executed when events are raised.</span></span>  
  
 <span data-ttu-id="e62d8-142">Чтобы использовать этот пример, откройте новый проект приложения Windows, добавьте кнопку с именем `Button1` и текстовое поле с именем `TextBox1` в главную форму с именем `Form1`.</span><span class="sxs-lookup"><span data-stu-id="e62d8-142">To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`.</span></span> <span data-ttu-id="e62d8-143">Затем щелкните правой кнопкой мыши форму и нажмите кнопку **просмотреть код** , чтобы открыть редактор кода.</span><span class="sxs-lookup"><span data-stu-id="e62d8-143">Then right-click the form and click **View Code** to open the Code Editor.</span></span>  
  
 <span data-ttu-id="e62d8-144">Добавить `WithEvents` переменных в раздел объявлений `Form1` класса.</span><span class="sxs-lookup"><span data-stu-id="e62d8-144">Add a `WithEvents` variable to the declarations section of the `Form1` class.</span></span>  
  
 <span data-ttu-id="e62d8-145">[!code-vb[VbVbalrEvents&#14;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e62d8-145">[!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e62d8-146">Пример</span><span class="sxs-lookup"><span data-stu-id="e62d8-146">Example</span></span>  
 <span data-ttu-id="e62d8-147">Добавьте следующий код в код для `Form1`.</span><span class="sxs-lookup"><span data-stu-id="e62d8-147">Add the following code to the code for `Form1`.</span></span> <span data-ttu-id="e62d8-148">Замените все дубликаты процедур, которые могут существовать, такие как `Form_Load`, или `Button_Click`.</span><span class="sxs-lookup"><span data-stu-id="e62d8-148">Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.</span></span>  
  
 <span data-ttu-id="e62d8-149">[!code-vb[VbVbalrEvents&#15;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="e62d8-149">[!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]</span></span>  
  
 <span data-ttu-id="e62d8-150">Нажмите клавишу F5 для запуска примера и нажмите кнопку с надписью **запустить**.</span><span class="sxs-lookup"><span data-stu-id="e62d8-150">Press F5 to run the preceding example, and click the button labeled **Start**.</span></span> <span data-ttu-id="e62d8-151">Первое текстовое поле начинает обратный отсчет.</span><span class="sxs-lookup"><span data-stu-id="e62d8-151">The first text box starts to count down the seconds.</span></span> <span data-ttu-id="e62d8-152">По истечении всего времени (10 секунд) в первом текстовом поле отображается надпись Done.</span><span class="sxs-lookup"><span data-stu-id="e62d8-152">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e62d8-153">`My.Application.DoEvents` Метод не обрабатывает события в точно так же, как формы.</span><span class="sxs-lookup"><span data-stu-id="e62d8-153">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="e62d8-154">Чтобы разрешить форме непосредственно обрабатывать события, можно использовать многопоточность.</span><span class="sxs-lookup"><span data-stu-id="e62d8-154">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="e62d8-155">Дополнительные сведения см. в разделе [потоки](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span><span class="sxs-lookup"><span data-stu-id="e62d8-155">For more information, see [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e62d8-156">См. также</span><span class="sxs-lookup"><span data-stu-id="e62d8-156">See Also</span></span>  
 <span data-ttu-id="e62d8-157">[События](../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="e62d8-157">[Events](../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="e62d8-158"> [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="e62d8-158"> [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="e62d8-159"> [Оператор AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="e62d8-159"> [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span></span>  
<span data-ttu-id="e62d8-160"> [Оператор RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="e62d8-160"> [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span></span>  
<span data-ttu-id="e62d8-161"> [Обрабатывает](../../../visual-basic/language-reference/statements/handles-clause.md)</span><span class="sxs-lookup"><span data-stu-id="e62d8-161"> [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)</span></span>
