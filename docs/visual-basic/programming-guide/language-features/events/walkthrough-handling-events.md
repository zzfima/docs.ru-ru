---
title: Обработка событий (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c1743e5f5d9dcdf83ab646407cd1fcdc77ff71cd
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-handling-events-visual-basic"></a><span data-ttu-id="791f3-102">Пошаговое руководство. Обработка событий (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="791f3-102">Walkthrough: Handling Events (Visual Basic)</span></span>
<span data-ttu-id="791f3-103">Это вторая из двух разделов, которые демонстрируют, как работать с событиями.</span><span class="sxs-lookup"><span data-stu-id="791f3-103">This is the second of two topics that demonstrate how to work with events.</span></span> <span data-ttu-id="791f3-104">Первый раздел [Пошаговое руководство: объявление и создание событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), показано, как объявить и инициировать события.</span><span class="sxs-lookup"><span data-stu-id="791f3-104">The first topic, [Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), shows how to declare and raise events.</span></span> <span data-ttu-id="791f3-105">В этом разделе используется форма и класс из предыдущего примера для демонстрации способов обработки событий при их возникновении.</span><span class="sxs-lookup"><span data-stu-id="791f3-105">This section uses the form and class from that walkthrough to show how to handle events when they take place.</span></span>  
  
 <span data-ttu-id="791f3-106">`Widget` Пример класса используются традиционные инструкции обработки событий.</span><span class="sxs-lookup"><span data-stu-id="791f3-106">The `Widget` class example uses traditional event-handling statements.</span></span> <span data-ttu-id="791f3-107">Visual Basic предоставляет другие методы для работы с событиями.</span><span class="sxs-lookup"><span data-stu-id="791f3-107">Visual Basic provides other techniques for working with events.</span></span> <span data-ttu-id="791f3-108">В качестве упражнения, можно изменить в этом примере для использования `AddHandler` и `Handles` инструкции.</span><span class="sxs-lookup"><span data-stu-id="791f3-108">As an exercise, you can modify this example to use the `AddHandler` and `Handles` statements.</span></span>  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a><span data-ttu-id="791f3-109">Для обработки события PercentDone класса мини-приложения</span><span class="sxs-lookup"><span data-stu-id="791f3-109">To handle the PercentDone event of the Widget class</span></span>  
  
1.  <span data-ttu-id="791f3-110">Поместите следующий код в `Form1`:</span><span class="sxs-lookup"><span data-stu-id="791f3-110">Place the following code in `Form1`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]  
  
     <span data-ttu-id="791f3-111">`WithEvents` Ключевое слово указывает, что переменная `mWidget` используется для обработки событий объекта.</span><span class="sxs-lookup"><span data-stu-id="791f3-111">The `WithEvents` keyword specifies that the variable `mWidget` is used to handle an object's events.</span></span> <span data-ttu-id="791f3-112">Укажите тип объекта, указав имя класса, из которого будет создан объект.</span><span class="sxs-lookup"><span data-stu-id="791f3-112">You specify the kind of object by supplying the name of the class from which the object will be created.</span></span>  
  
     <span data-ttu-id="791f3-113">Переменная `mWidget` объявляется в `Form1` из-за `WithEvents` переменные должны быть уровня класса.</span><span class="sxs-lookup"><span data-stu-id="791f3-113">The variable `mWidget` is declared in `Form1` because `WithEvents` variables must be class-level.</span></span> <span data-ttu-id="791f3-114">Это верно независимо от типа класса, который они помещены.</span><span class="sxs-lookup"><span data-stu-id="791f3-114">This is true regardless of the type of class you place them in.</span></span>  
  
     <span data-ttu-id="791f3-115">Переменная `mblnCancel` используется для отмены `LongTask` метод.</span><span class="sxs-lookup"><span data-stu-id="791f3-115">The variable `mblnCancel` is used to cancel the `LongTask` method.</span></span>  
  
## <a name="writing-code-to-handle-an-event"></a><span data-ttu-id="791f3-116">Написание кода для обработки событий</span><span class="sxs-lookup"><span data-stu-id="791f3-116">Writing Code to Handle an Event</span></span>  
 <span data-ttu-id="791f3-117">Сразу после объявления переменной с помощью `WithEvents`, имя переменной появляется в левом раскрывающемся списке класса **редактор кода**.</span><span class="sxs-lookup"><span data-stu-id="791f3-117">As soon as you declare a variable using `WithEvents`, the variable name appears in the left drop-down list of the class's **Code Editor**.</span></span> <span data-ttu-id="791f3-118">При выборе `mWidget`, `Widget` класса события отображаются в правом раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="791f3-118">When you select `mWidget`, the `Widget` class's events appear in the right drop-down list.</span></span> <span data-ttu-id="791f3-119">При выборе события отображаются соответствующей процедуры события с префиксом `mWidget` и символ подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="791f3-119">Selecting an event displays the corresponding event procedure, with the prefix `mWidget` and an underscore.</span></span> <span data-ttu-id="791f3-120">Все процедуры события, связанные с `WithEvents` переменной, назначается имя переменной как префикс.</span><span class="sxs-lookup"><span data-stu-id="791f3-120">All the event procedures associated with a `WithEvents` variable are given the variable name as a prefix.</span></span>  
  
#### <a name="to-handle-an-event"></a><span data-ttu-id="791f3-121">Чтобы обработать событие</span><span class="sxs-lookup"><span data-stu-id="791f3-121">To handle an event</span></span>  
  
1.  <span data-ttu-id="791f3-122">Выберите `mWidget` из левого раскрывающегося списка в **редактор кода**.</span><span class="sxs-lookup"><span data-stu-id="791f3-122">Select `mWidget` from the left drop-down list in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="791f3-123">Выберите `PercentDone` событий из правого раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="791f3-123">Select the `PercentDone` event from the right drop-down list.</span></span> <span data-ttu-id="791f3-124">**Редактор кода** открывает `mWidget_PercentDone` процедуру обработки события.</span><span class="sxs-lookup"><span data-stu-id="791f3-124">The **Code Editor** opens the `mWidget_PercentDone` event procedure.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="791f3-125">**Редактор кода** может быть полезным, но не обязательно для вставки новых обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="791f3-125">The **Code Editor** is useful, but not required, for inserting new event handlers.</span></span> <span data-ttu-id="791f3-126">В этом пошаговом руководстве является наиболее простым способом просто скопировать обработчики событий, непосредственно в код.</span><span class="sxs-lookup"><span data-stu-id="791f3-126">In this walkthrough, it is more direct to just copy the event handlers directly into your code.</span></span>  
  
3.  <span data-ttu-id="791f3-127">Добавьте следующий код в обработчик событий `mWidget_PercentDone`.</span><span class="sxs-lookup"><span data-stu-id="791f3-127">Add the following code to the `mWidget_PercentDone` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]  
  
     <span data-ttu-id="791f3-128">Каждый раз, когда `PercentDone` события, процедура события отображает процент выполнения в `Label` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="791f3-128">Whenever the `PercentDone` event is raised, the event procedure displays the percent complete in a `Label` control.</span></span> <span data-ttu-id="791f3-129">`DoEvents` Метода позволяет обновить надпись, а также предоставляет пользователю возможность воспользоваться **отменить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="791f3-129">The `DoEvents` method allows the label to repaint, and also gives the user the opportunity to click the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="791f3-130">Добавьте следующий код для `Button2_Click` обработчик событий:</span><span class="sxs-lookup"><span data-stu-id="791f3-130">Add the following code for the `Button2_Click` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]  
  
 <span data-ttu-id="791f3-131">При нажатии кнопки **отменить** кнопки при `LongTask` работает, `Button2_Click` событие выполняется сразу после `DoEvents` оператор разрешает обработки события.</span><span class="sxs-lookup"><span data-stu-id="791f3-131">If the user clicks the **Cancel** button while `LongTask` is running, the `Button2_Click` event is executed as soon as the `DoEvents` statement allows event processing to occur.</span></span> <span data-ttu-id="791f3-132">Переменной уровня класса `mblnCancel` равно `True`и `mWidget_PercentDone` событий затем проверяет и устанавливает `ByRef Cancel` аргумент `True`.</span><span class="sxs-lookup"><span data-stu-id="791f3-132">The class-level variable `mblnCancel` is set to `True`, and the `mWidget_PercentDone` event then tests it and sets the `ByRef Cancel` argument to `True`.</span></span>  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a><span data-ttu-id="791f3-133">Подключение к объекту переменная WithEvents</span><span class="sxs-lookup"><span data-stu-id="791f3-133">Connecting a WithEvents Variable to an Object</span></span>  
 <span data-ttu-id="791f3-134">`Form1` Теперь настроен для обработки `Widget` событий объекта.</span><span class="sxs-lookup"><span data-stu-id="791f3-134">`Form1` is now set up to handle a `Widget` object's events.</span></span> <span data-ttu-id="791f3-135">Остается найти `Widget` где-либо.</span><span class="sxs-lookup"><span data-stu-id="791f3-135">All that remains is to find a `Widget` somewhere.</span></span>  
  
 <span data-ttu-id="791f3-136">При объявлении переменной `WithEvents` во время разработки, с ним связан ни один из объектов.</span><span class="sxs-lookup"><span data-stu-id="791f3-136">When you declare a variable `WithEvents` at design time, no object is associated with it.</span></span> <span data-ttu-id="791f3-137">Объект `WithEvents` переменная является так же, как и любой другой переменной объекта.</span><span class="sxs-lookup"><span data-stu-id="791f3-137">A `WithEvents` variable is just like any other object variable.</span></span> <span data-ttu-id="791f3-138">Необходимо создать объект и назначить ссылку на него с `WithEvents` переменной.</span><span class="sxs-lookup"><span data-stu-id="791f3-138">You have to create an object and assign a reference to it with the `WithEvents` variable.</span></span>  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a><span data-ttu-id="791f3-139">Чтобы создать объект и назначить ссылку на него</span><span class="sxs-lookup"><span data-stu-id="791f3-139">To create an object and assign a reference to it</span></span>  
  
1.  <span data-ttu-id="791f3-140">Выберите **(события Form1)** из левого раскрывающегося списка в **редактор кода**.</span><span class="sxs-lookup"><span data-stu-id="791f3-140">Select **(Form1 Events)** from the left drop-down list in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="791f3-141">Выберите `Load` событий из правого раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="791f3-141">Select the `Load` event from the right drop-down list.</span></span> <span data-ttu-id="791f3-142">**Редактор кода** открывает `Form1_Load` процедуру обработки события.</span><span class="sxs-lookup"><span data-stu-id="791f3-142">The **Code Editor** opens the `Form1_Load` event procedure.</span></span>  
  
3.  <span data-ttu-id="791f3-143">Добавьте следующий код для `Form1_Load` процедуру обработки событий для создания `Widget`:</span><span class="sxs-lookup"><span data-stu-id="791f3-143">Add the following code for the `Form1_Load` event procedure to create the `Widget`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]  
  
 <span data-ttu-id="791f3-144">При выполнении этого кода Visual Basic создает `Widget` объекта и подключает его события к процедурам события, связанные с `mWidget`.</span><span class="sxs-lookup"><span data-stu-id="791f3-144">When this code executes, Visual Basic creates a `Widget` object and connects its events to the event procedures associated with `mWidget`.</span></span> <span data-ttu-id="791f3-145">Из этой точки, каждый раз, когда `Widget` вызывает его `PercentDone` событий, `mWidget_PercentDone` выполняется процедура события.</span><span class="sxs-lookup"><span data-stu-id="791f3-145">From that point on, whenever the `Widget` raises its `PercentDone` event, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
#### <a name="to-call-the-longtask-method"></a><span data-ttu-id="791f3-146">Для вызова метода LongTask</span><span class="sxs-lookup"><span data-stu-id="791f3-146">To call the LongTask method</span></span>  
  
-   <span data-ttu-id="791f3-147">Добавьте следующий код в обработчик событий `Button1_Click`.</span><span class="sxs-lookup"><span data-stu-id="791f3-147">Add the following code to the `Button1_Click` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]  
  
 <span data-ttu-id="791f3-148">Прежде чем `LongTask` вызывается метод, метка отображает процент завершения должен быть инициализирован и на уровне класса `Boolean` флаг для отмены метода должно быть присвоено `False`.</span><span class="sxs-lookup"><span data-stu-id="791f3-148">Before the `LongTask` method is called, the label that displays the percent complete must be initialized, and the class-level `Boolean` flag for canceling the method must be set to `False`.</span></span>  
  
 <span data-ttu-id="791f3-149">`LongTask` вызывается для задачи с продолжительностью 12,2 секунды.</span><span class="sxs-lookup"><span data-stu-id="791f3-149">`LongTask` is called with a task duration of 12.2 seconds.</span></span> <span data-ttu-id="791f3-150">`PercentDone` Событие возникает один раз каждые треть доли секунды.</span><span class="sxs-lookup"><span data-stu-id="791f3-150">The `PercentDone` event is raised once every one-third of a second.</span></span> <span data-ttu-id="791f3-151">Каждый раз при возникновении события `mWidget_PercentDone` выполняется процедура события.</span><span class="sxs-lookup"><span data-stu-id="791f3-151">Each time the event is raised, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
 <span data-ttu-id="791f3-152">Когда `LongTask` будет сделано, `mblnCancel` проверяется на предмет `LongTask` нормально, или если он остановлен, так как `mblnCancel` было задано значение `True`.</span><span class="sxs-lookup"><span data-stu-id="791f3-152">When `LongTask` is done, `mblnCancel` is tested to see if `LongTask` ended normally, or if it stopped because `mblnCancel` was set to `True`.</span></span> <span data-ttu-id="791f3-153">Процент завершения обновляется только в первом случае.</span><span class="sxs-lookup"><span data-stu-id="791f3-153">The percent complete is updated only in the former case.</span></span>  
  
#### <a name="to-run-the-program"></a><span data-ttu-id="791f3-154">Чтобы выполнить программу, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="791f3-154">To run the program</span></span>  
  
1.  <span data-ttu-id="791f3-155">Нажмите клавишу F5, чтобы включить в проект в режиме выполнения.</span><span class="sxs-lookup"><span data-stu-id="791f3-155">Press F5 to put the project in run mode.</span></span>  
  
2.  <span data-ttu-id="791f3-156">Нажмите кнопку **запустить задачу** кнопки.</span><span class="sxs-lookup"><span data-stu-id="791f3-156">Click the **Start Task** button.</span></span> <span data-ttu-id="791f3-157">Каждый раз `PercentDone` события, метка обновляется с указанием процента выполненной задачи.</span><span class="sxs-lookup"><span data-stu-id="791f3-157">Each time the `PercentDone` event is raised, the label is updated with the percentage of the task that is complete.</span></span>  
  
3.  <span data-ttu-id="791f3-158">Нажмите кнопку **отменить** кнопку, чтобы остановить задание.</span><span class="sxs-lookup"><span data-stu-id="791f3-158">Click the **Cancel** button to stop the task.</span></span> <span data-ttu-id="791f3-159">Обратите внимание, что внешний вид **отменить** сразу после нажатия кнопки не изменяется.</span><span class="sxs-lookup"><span data-stu-id="791f3-159">Notice that the appearance of the **Cancel** button does not change immediately when you click it.</span></span> <span data-ttu-id="791f3-160">`Click` Событие не происходит до `My.Application.DoEvents` оператор разрешает обработку событий.</span><span class="sxs-lookup"><span data-stu-id="791f3-160">The `Click` event cannot happen until the `My.Application.DoEvents` statement allows event processing.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="791f3-161">`My.Application.DoEvents` Метод отличается от обработки событий в точно так же, как и в форме.</span><span class="sxs-lookup"><span data-stu-id="791f3-161">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="791f3-162">Например, в этом пошаговом руководстве, необходимо нажать кнопку **отменить** дважды.</span><span class="sxs-lookup"><span data-stu-id="791f3-162">For example, in this walkthrough, you must click the **Cancel** button twice.</span></span> <span data-ttu-id="791f3-163">Чтобы разрешить форме обрабатывать события напрямую, можно использовать многопоточность.</span><span class="sxs-lookup"><span data-stu-id="791f3-163">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="791f3-164">Дополнительные сведения см. в разделе [потоки](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span><span class="sxs-lookup"><span data-stu-id="791f3-164">For more information, see [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
 <span data-ttu-id="791f3-165">Может оказаться полезным для запуска программы с F11 и пошаговое выполнение кода строки одновременно.</span><span class="sxs-lookup"><span data-stu-id="791f3-165">You may find it instructive to run the program with F11 and step through the code a line at a time.</span></span> <span data-ttu-id="791f3-166">Можно точно просмотреть, как начинается выполнение `LongTask`и затем кратко снова появляется `Form1` каждый раз `PercentDone` события.</span><span class="sxs-lookup"><span data-stu-id="791f3-166">You can clearly see how execution enters `LongTask`, and then briefly re-enters `Form1` each time the `PercentDone` event is raised.</span></span>  
  
 <span data-ttu-id="791f3-167">Что может произойти, если во время выполнения обратно в код `Form1`, `LongTask` снова вызывается метод?</span><span class="sxs-lookup"><span data-stu-id="791f3-167">What would happen if, while execution was back in the code of `Form1`, the `LongTask` method were called again?</span></span> <span data-ttu-id="791f3-168">В худшем случае может произойти переполнение стека, если `LongTask` вызывался каждый раз при возникновении события.</span><span class="sxs-lookup"><span data-stu-id="791f3-168">At worst, a stack overflow might occur if `LongTask` were called every time the event was raised.</span></span>  
  
 <span data-ttu-id="791f3-169">Может привести к переменной `mWidget` для обработки событий для другой `Widget` объекта путем назначения ссылки на новый `Widget` для `mWidget`.</span><span class="sxs-lookup"><span data-stu-id="791f3-169">You can cause the variable `mWidget` to handle events for a different `Widget` object by assigning a reference to the new `Widget` to `mWidget`.</span></span> <span data-ttu-id="791f3-170">На самом деле, может сделать код в `Button1_Click` этого каждый раз при нажатии кнопки.</span><span class="sxs-lookup"><span data-stu-id="791f3-170">In fact, you can make the code in `Button1_Click` do this every time you click the button.</span></span>  
  
#### <a name="to-handle-events-for-a-different-widget"></a><span data-ttu-id="791f3-171">Для обработки событий для разных мини-приложения</span><span class="sxs-lookup"><span data-stu-id="791f3-171">To handle events for a different widget</span></span>  
  
-   <span data-ttu-id="791f3-172">Добавьте следующую строку кода, чтобы `Button1_Click` процедуры, непосредственно перед строкой, которая считывает `mWidget.LongTask(12.2, 0.33)`:</span><span class="sxs-lookup"><span data-stu-id="791f3-172">Add the following line of code to the `Button1_Click` procedure, immediately preceding the line that reads `mWidget.LongTask(12.2, 0.33)`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]  
  
 <span data-ttu-id="791f3-173">Приведенный выше код создает новый `Widget` каждый раз при нажатии кнопки.</span><span class="sxs-lookup"><span data-stu-id="791f3-173">The code above creates a new `Widget` each time the button is clicked.</span></span> <span data-ttu-id="791f3-174">Как только `LongTask` метод завершения, ссылку на `Widget` освобождается и `Widget` уничтожается.</span><span class="sxs-lookup"><span data-stu-id="791f3-174">As soon as the `LongTask` method completes, the reference to the `Widget` is released, and the `Widget` is destroyed.</span></span>  
  
 <span data-ttu-id="791f3-175">A `WithEvents` переменная может содержать только одну ссылку на время, поэтому если при назначении `Widget` объект `mWidget`, предыдущий `Widget` событий объекта больше не будет обрабатываться.</span><span class="sxs-lookup"><span data-stu-id="791f3-175">A `WithEvents` variable can contain only one object reference at a time, so if you assign a different `Widget` object to `mWidget`, the previous `Widget` object's events will no longer be handled.</span></span> <span data-ttu-id="791f3-176">Если `mWidget` является единственной объектной переменной, содержащей ссылку на старый `Widget`, объект ликвидируется.</span><span class="sxs-lookup"><span data-stu-id="791f3-176">If `mWidget` is the only object variable containing a reference to the old `Widget`, the object is destroyed.</span></span> <span data-ttu-id="791f3-177">Если вы хотите обрабатывать события от нескольких `Widget` объекты, используют `AddHandler` инструкции для обработки событий из каждого объекта отдельно.</span><span class="sxs-lookup"><span data-stu-id="791f3-177">If you want to handle events from several `Widget` objects, use the `AddHandler` statement to process events from each object separately.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="791f3-178">Можно объявить столько `WithEvents` нужна переменных, но массивы `WithEvents` переменные не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="791f3-178">You can declare as many `WithEvents` variables as you need, but arrays of `WithEvents` variables are not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="791f3-179">См. также</span><span class="sxs-lookup"><span data-stu-id="791f3-179">See Also</span></span>  
 [<span data-ttu-id="791f3-180">Пошаговое руководство. Объявление и создание событий</span><span class="sxs-lookup"><span data-stu-id="791f3-180">Walkthrough: Declaring and Raising Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)  
 [<span data-ttu-id="791f3-181">События</span><span class="sxs-lookup"><span data-stu-id="791f3-181">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
