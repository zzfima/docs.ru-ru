---
title: "Обработка событий (Visual Basic) | Документы Microsoft"
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
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword, walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
caps.latest.revision: 18
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
ms.openlocfilehash: b4ad77b3b0236e762fc17b8aba9d34108c8d75b5
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-handling-events-visual-basic"></a><span data-ttu-id="958de-102">Пошаговое руководство. Обработка событий (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="958de-102">Walkthrough: Handling Events (Visual Basic)</span></span>
<span data-ttu-id="958de-103">Это второе из двух разделов, которые демонстрируют, как работать с событиями.</span><span class="sxs-lookup"><span data-stu-id="958de-103">This is the second of two topics that demonstrate how to work with events.</span></span> <span data-ttu-id="958de-104">Первый раздел [Пошаговое руководство: объявление и создание событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), показано, как объявлять и создавать события.</span><span class="sxs-lookup"><span data-stu-id="958de-104">The first topic, [Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), shows how to declare and raise events.</span></span> <span data-ttu-id="958de-105">В этом разделе используется форма и класс из предыдущего примера для демонстрации способов обработки событий при их возникновении.</span><span class="sxs-lookup"><span data-stu-id="958de-105">This section uses the form and class from that walkthrough to show how to handle events when they take place.</span></span>  
  
 <span data-ttu-id="958de-106">`Widget` Пример класса используются традиционные инструкции обработки событий.</span><span class="sxs-lookup"><span data-stu-id="958de-106">The `Widget` class example uses traditional event-handling statements.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="958de-107">имеются и другие способы работы с событиями.</span><span class="sxs-lookup"><span data-stu-id="958de-107"> provides other techniques for working with events.</span></span> <span data-ttu-id="958de-108">В качестве упражнения можно изменить для использования в этом примере `AddHandler` и `Handles` инструкции.</span><span class="sxs-lookup"><span data-stu-id="958de-108">As an exercise, you can modify this example to use the `AddHandler` and `Handles` statements.</span></span>  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a><span data-ttu-id="958de-109">Для обработки события PercentDone класса мини-приложения</span><span class="sxs-lookup"><span data-stu-id="958de-109">To handle the PercentDone event of the Widget class</span></span>  
  
1.  <span data-ttu-id="958de-110">Поместите следующий код в `Form1`:</span><span class="sxs-lookup"><span data-stu-id="958de-110">Place the following code in `Form1`:</span></span>  
  
     <span data-ttu-id="958de-111">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#4;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="958de-111">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]</span></span>  
  
     <span data-ttu-id="958de-112">`WithEvents` Ключевое слово указывает, что переменная `mWidget` используется для обработки событий объекта.</span><span class="sxs-lookup"><span data-stu-id="958de-112">The `WithEvents` keyword specifies that the variable `mWidget` is used to handle an object's events.</span></span> <span data-ttu-id="958de-113">Укажите тип объекта, указав имя класса, из которого объект будет создан.</span><span class="sxs-lookup"><span data-stu-id="958de-113">You specify the kind of object by supplying the name of the class from which the object will be created.</span></span>  
  
     <span data-ttu-id="958de-114">Переменная `mWidget` объявляется в `Form1` из-за `WithEvents` переменные должны быть уровня класса.</span><span class="sxs-lookup"><span data-stu-id="958de-114">The variable `mWidget` is declared in `Form1` because `WithEvents` variables must be class-level.</span></span> <span data-ttu-id="958de-115">Это верно независимо от типа класса, который они помещены.</span><span class="sxs-lookup"><span data-stu-id="958de-115">This is true regardless of the type of class you place them in.</span></span>  
  
     <span data-ttu-id="958de-116">Переменная `mblnCancel` используется для отмены `LongTask` метод.</span><span class="sxs-lookup"><span data-stu-id="958de-116">The variable `mblnCancel` is used to cancel the `LongTask` method.</span></span>  
  
## <a name="writing-code-to-handle-an-event"></a><span data-ttu-id="958de-117">Написание кода для обработки событий</span><span class="sxs-lookup"><span data-stu-id="958de-117">Writing Code to Handle an Event</span></span>  
 <span data-ttu-id="958de-118">Сразу после объявления переменной с помощью `WithEvents`, имя переменной появляется в левом раскрывающемся списке класса **редактор кода**.</span><span class="sxs-lookup"><span data-stu-id="958de-118">As soon as you declare a variable using `WithEvents`, the variable name appears in the left drop-down list of the class's **Code Editor**.</span></span> <span data-ttu-id="958de-119">При выборе `mWidget`, `Widget` класса события отображаются в правом раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="958de-119">When you select `mWidget`, the `Widget` class's events appear in the right drop-down list.</span></span> <span data-ttu-id="958de-120">Выбор события отображает соответствующей процедуры события с префиксом `mWidget` и символ подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="958de-120">Selecting an event displays the corresponding event procedure, with the prefix `mWidget` and an underscore.</span></span> <span data-ttu-id="958de-121">Всем процедурам событий, связанным с `WithEvents` переменной, получают имя переменной в качестве префикса.</span><span class="sxs-lookup"><span data-stu-id="958de-121">All the event procedures associated with a `WithEvents` variable are given the variable name as a prefix.</span></span>  
  
#### <a name="to-handle-an-event"></a><span data-ttu-id="958de-122">Чтобы обработать событие</span><span class="sxs-lookup"><span data-stu-id="958de-122">To handle an event</span></span>  
  
1.  <span data-ttu-id="958de-123">Выберите `mWidget` из левого раскрывающегося списка в **редактор кода**.</span><span class="sxs-lookup"><span data-stu-id="958de-123">Select `mWidget` from the left drop-down list in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="958de-124">Выберите `PercentDone` событий из правого раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="958de-124">Select the `PercentDone` event from the right drop-down list.</span></span> <span data-ttu-id="958de-125">**Редактор кода** открывает `mWidget_PercentDone` процедуру обработки события.</span><span class="sxs-lookup"><span data-stu-id="958de-125">The **Code Editor** opens the `mWidget_PercentDone` event procedure.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="958de-126">**Редактор кода** может быть полезным, но не обязательно для вставки новых обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="958de-126">The **Code Editor** is useful, but not required, for inserting new event handlers.</span></span> <span data-ttu-id="958de-127">В этом пошаговом руководстве является наиболее простым способом просто скопируйте обработчиков событий непосредственно в код.</span><span class="sxs-lookup"><span data-stu-id="958de-127">In this walkthrough, it is more direct to just copy the event handlers directly into your code.</span></span>  
  
3.  <span data-ttu-id="958de-128">Добавьте следующий код в обработчик событий `mWidget_PercentDone`.</span><span class="sxs-lookup"><span data-stu-id="958de-128">Add the following code to the `mWidget_PercentDone` event handler:</span></span>  
  
     <span data-ttu-id="958de-129">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#5;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="958de-129">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]</span></span>  
  
     <span data-ttu-id="958de-130">Каждый раз, когда `PercentDone` события, процедура события отображает процент выполнения в `Label` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="958de-130">Whenever the `PercentDone` event is raised, the event procedure displays the percent complete in a `Label` control.</span></span> <span data-ttu-id="958de-131">`DoEvents` Метод позволяет обновить надпись, а также предоставляет пользователю возможность воспользоваться **отменить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="958de-131">The `DoEvents` method allows the label to repaint, and also gives the user the opportunity to click the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="958de-132">Добавьте следующий код для `Button2_Click` обработчик событий:</span><span class="sxs-lookup"><span data-stu-id="958de-132">Add the following code for the `Button2_Click` event handler:</span></span>  
  
     <span data-ttu-id="958de-133">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents №&6;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="958de-133">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]</span></span>  
  
 <span data-ttu-id="958de-134">При нажатии кнопки **отменить** кнопки при `LongTask` работает, `Button2_Click` событий выполняется сразу после `DoEvents` оператор разрешает обработки события.</span><span class="sxs-lookup"><span data-stu-id="958de-134">If the user clicks the **Cancel** button while `LongTask` is running, the `Button2_Click` event is executed as soon as the `DoEvents` statement allows event processing to occur.</span></span> <span data-ttu-id="958de-135">Переменной уровня класса `mblnCancel` равен `True`и `mWidget_PercentDone` событий, затем проверяет ее и устанавливает `ByRef Cancel` аргумент `True`.</span><span class="sxs-lookup"><span data-stu-id="958de-135">The class-level variable `mblnCancel` is set to `True`, and the `mWidget_PercentDone` event then tests it and sets the `ByRef Cancel` argument to `True`.</span></span>  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a><span data-ttu-id="958de-136">Подключение к объекту переменная WithEvents</span><span class="sxs-lookup"><span data-stu-id="958de-136">Connecting a WithEvents Variable to an Object</span></span>  
 <span data-ttu-id="958de-137">`Form1`Теперь настроен для обработки `Widget` событий объекта.</span><span class="sxs-lookup"><span data-stu-id="958de-137">`Form1` is now set up to handle a `Widget` object's events.</span></span> <span data-ttu-id="958de-138">Все, что остается лишь найти `Widget` где-нибудь.</span><span class="sxs-lookup"><span data-stu-id="958de-138">All that remains is to find a `Widget` somewhere.</span></span>  
  
 <span data-ttu-id="958de-139">При объявлении переменной `WithEvents` во время разработки, объект не связан с ним.</span><span class="sxs-lookup"><span data-stu-id="958de-139">When you declare a variable `WithEvents` at design time, no object is associated with it.</span></span> <span data-ttu-id="958de-140">A `WithEvents` переменной — так же, как любой другой переменной объекта.</span><span class="sxs-lookup"><span data-stu-id="958de-140">A `WithEvents` variable is just like any other object variable.</span></span> <span data-ttu-id="958de-141">Необходимо создать объект и назначить ему ссылку с `WithEvents` переменной.</span><span class="sxs-lookup"><span data-stu-id="958de-141">You have to create an object and assign a reference to it with the `WithEvents` variable.</span></span>  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a><span data-ttu-id="958de-142">Чтобы создать объект и назначить ему ссылку</span><span class="sxs-lookup"><span data-stu-id="958de-142">To create an object and assign a reference to it</span></span>  
  
1.  <span data-ttu-id="958de-143">Выберите **(события Form1)** из левого раскрывающегося списка в **редактор кода**.</span><span class="sxs-lookup"><span data-stu-id="958de-143">Select **(Form1 Events)** from the left drop-down list in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="958de-144">Выберите `Load` событий из правого раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="958de-144">Select the `Load` event from the right drop-down list.</span></span> <span data-ttu-id="958de-145">**Редактор кода** открывает `Form1_Load` процедуру обработки события.</span><span class="sxs-lookup"><span data-stu-id="958de-145">The **Code Editor** opens the `Form1_Load` event procedure.</span></span>  
  
3.  <span data-ttu-id="958de-146">Добавьте следующий код для `Form1_Load` процедуру обработки события для создания `Widget`:</span><span class="sxs-lookup"><span data-stu-id="958de-146">Add the following code for the `Form1_Load` event procedure to create the `Widget`:</span></span>  
  
     <span data-ttu-id="958de-147">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#7;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="958de-147">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]</span></span>  
  
 <span data-ttu-id="958de-148">При выполнении этого кода [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] создает `Widget` объекта и подключает его события к процедурам события, связанным с `mWidget`.</span><span class="sxs-lookup"><span data-stu-id="958de-148">When this code executes, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] creates a `Widget` object and connects its events to the event procedures associated with `mWidget`.</span></span> <span data-ttu-id="958de-149">С этого момента, когда `Widget` вызывает его `PercentDone` событий, `mWidget_PercentDone` выполняется процедура обработки событий.</span><span class="sxs-lookup"><span data-stu-id="958de-149">From that point on, whenever the `Widget` raises its `PercentDone` event, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
#### <a name="to-call-the-longtask-method"></a><span data-ttu-id="958de-150">Чтобы вызвать метод LongTask</span><span class="sxs-lookup"><span data-stu-id="958de-150">To call the LongTask method</span></span>  
  
-   <span data-ttu-id="958de-151">Добавьте следующий код в обработчик событий `Button1_Click`.</span><span class="sxs-lookup"><span data-stu-id="958de-151">Add the following code to the `Button1_Click` event handler:</span></span>  
  
     <span data-ttu-id="958de-152">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents №&8;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="958de-152">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]</span></span>  
  
 <span data-ttu-id="958de-153">Прежде чем `LongTask` вызывается метод, метка отображается процент выполнения должен быть инициализирован и уровня класса `Boolean` флаг отмены метода должно быть присвоено `False`.</span><span class="sxs-lookup"><span data-stu-id="958de-153">Before the `LongTask` method is called, the label that displays the percent complete must be initialized, and the class-level `Boolean` flag for canceling the method must be set to `False`.</span></span>  
  
 <span data-ttu-id="958de-154">`LongTask`вызывается для задачи с продолжительностью 12,2 секунды.</span><span class="sxs-lookup"><span data-stu-id="958de-154">`LongTask` is called with a task duration of 12.2 seconds.</span></span> <span data-ttu-id="958de-155">`PercentDone` Событие возникает один раз каждые треть секунды.</span><span class="sxs-lookup"><span data-stu-id="958de-155">The `PercentDone` event is raised once every one-third of a second.</span></span> <span data-ttu-id="958de-156">Каждый раз при возникновении события `mWidget_PercentDone` выполняется процедура обработки событий.</span><span class="sxs-lookup"><span data-stu-id="958de-156">Each time the event is raised, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
 <span data-ttu-id="958de-157">Когда `LongTask` выполняется, `mblnCancel` проверяется на наличие `LongTask` нормально, или если он остановлен, так как `mblnCancel` было задано значение `True`.</span><span class="sxs-lookup"><span data-stu-id="958de-157">When `LongTask` is done, `mblnCancel` is tested to see if `LongTask` ended normally, or if it stopped because `mblnCancel` was set to `True`.</span></span> <span data-ttu-id="958de-158">Процент завершения обновляется только в первом случае.</span><span class="sxs-lookup"><span data-stu-id="958de-158">The percent complete is updated only in the former case.</span></span>  
  
#### <a name="to-run-the-program"></a><span data-ttu-id="958de-159">Чтобы выполнить программу, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="958de-159">To run the program</span></span>  
  
1.  <span data-ttu-id="958de-160">Нажмите клавишу F5, чтобы включить проект в режиме выполнения.</span><span class="sxs-lookup"><span data-stu-id="958de-160">Press F5 to put the project in run mode.</span></span>  
  
2.  <span data-ttu-id="958de-161">Щелкните **запустить задачу** кнопки.</span><span class="sxs-lookup"><span data-stu-id="958de-161">Click the **Start Task** button.</span></span> <span data-ttu-id="958de-162">Каждый раз при `PercentDone` события, метка обновляется с указанием процента завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="958de-162">Each time the `PercentDone` event is raised, the label is updated with the percentage of the task that is complete.</span></span>  
  
3.  <span data-ttu-id="958de-163">Щелкните **отменить** кнопку для отмены задачи.</span><span class="sxs-lookup"><span data-stu-id="958de-163">Click the **Cancel** button to stop the task.</span></span> <span data-ttu-id="958de-164">Обратите внимание, что внешний вид **отменить** сразу после нажатия кнопки не изменяется.</span><span class="sxs-lookup"><span data-stu-id="958de-164">Notice that the appearance of the **Cancel** button does not change immediately when you click it.</span></span> <span data-ttu-id="958de-165">`Click` Событие не происходит до `My.Application.DoEvents` оператор разрешает обработку событий.</span><span class="sxs-lookup"><span data-stu-id="958de-165">The `Click` event cannot happen until the `My.Application.DoEvents` statement allows event processing.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="958de-166">`My.Application.DoEvents` Метод не обрабатывает события в точно так же, как формы.</span><span class="sxs-lookup"><span data-stu-id="958de-166">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="958de-167">Например, в данном пошаговом руководстве необходимо нажать кнопку **отменить** кнопку дважды.</span><span class="sxs-lookup"><span data-stu-id="958de-167">For example, in this walkthrough, you must click the **Cancel** button twice.</span></span> <span data-ttu-id="958de-168">Чтобы разрешить форме непосредственно обрабатывать события, можно использовать многопоточность.</span><span class="sxs-lookup"><span data-stu-id="958de-168">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="958de-169">Дополнительные сведения см. в разделе [потоки](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span><span class="sxs-lookup"><span data-stu-id="958de-169">For more information, see [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
 <span data-ttu-id="958de-170">Может оказаться полезным для запуска программы с F11 и пошаговое выполнение кода строки одновременно.</span><span class="sxs-lookup"><span data-stu-id="958de-170">You may find it instructive to run the program with F11 and step through the code a line at a time.</span></span> <span data-ttu-id="958de-171">Очевидно, можно увидеть, как начинается выполнение `LongTask`и кратко повторно вводит `Form1` каждый раз `PercentDone` события.</span><span class="sxs-lookup"><span data-stu-id="958de-171">You can clearly see how execution enters `LongTask`, and then briefly re-enters `Form1` each time the `PercentDone` event is raised.</span></span>  
  
 <span data-ttu-id="958de-172">Что произойдет, если во время выполнения обратно в код `Form1`, `LongTask` снова вызван метод?</span><span class="sxs-lookup"><span data-stu-id="958de-172">What would happen if, while execution was back in the code of `Form1`, the `LongTask` method were called again?</span></span> <span data-ttu-id="958de-173">В худшем случае может произойти переполнение стека, если `LongTask` вызывался каждый раз при возникновении события.</span><span class="sxs-lookup"><span data-stu-id="958de-173">At worst, a stack overflow might occur if `LongTask` were called every time the event was raised.</span></span>  
  
 <span data-ttu-id="958de-174">Может привести к переменной `mWidget` для обработки различных событий `Widget` объекта путем назначения ссылки на новый `Widget` в `mWidget`.</span><span class="sxs-lookup"><span data-stu-id="958de-174">You can cause the variable `mWidget` to handle events for a different `Widget` object by assigning a reference to the new `Widget` to `mWidget`.</span></span> <span data-ttu-id="958de-175">На самом деле, может сделать код в `Button1_Click` этого каждый раз при нажатии кнопки.</span><span class="sxs-lookup"><span data-stu-id="958de-175">In fact, you can make the code in `Button1_Click` do this every time you click the button.</span></span>  
  
#### <a name="to-handle-events-for-a-different-widget"></a><span data-ttu-id="958de-176">Для обработки событий для другого объекта widget:</span><span class="sxs-lookup"><span data-stu-id="958de-176">To handle events for a different widget</span></span>  
  
-   <span data-ttu-id="958de-177">Добавьте следующую строку кода, чтобы `Button1_Click` процедура, непосредственно перед строкой, которая считывает `mWidget.LongTask(12.2, 0.33)`:</span><span class="sxs-lookup"><span data-stu-id="958de-177">Add the following line of code to the `Button1_Click` procedure, immediately preceding the line that reads `mWidget.LongTask(12.2, 0.33)`:</span></span>  
  
     <span data-ttu-id="958de-178">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents №&9;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="958de-178">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]</span></span>  
  
 <span data-ttu-id="958de-179">Приведенный выше код создает новый `Widget` каждый раз при нажатии кнопки.</span><span class="sxs-lookup"><span data-stu-id="958de-179">The code above creates a new `Widget` each time the button is clicked.</span></span> <span data-ttu-id="958de-180">Как только `LongTask` метод завершается, ссылка на `Widget` освобождается и `Widget` уничтожается.</span><span class="sxs-lookup"><span data-stu-id="958de-180">As soon as the `LongTask` method completes, the reference to the `Widget` is released, and the `Widget` is destroyed.</span></span>  
  
 <span data-ttu-id="958de-181">Объект `WithEvents` переменная может содержать только одну ссылку на время, поэтому если при назначении `Widget` объект `mWidget`, предыдущий `Widget` событий объекта больше не будет обрабатываться.</span><span class="sxs-lookup"><span data-stu-id="958de-181">A `WithEvents` variable can contain only one object reference at a time, so if you assign a different `Widget` object to `mWidget`, the previous `Widget` object's events will no longer be handled.</span></span> <span data-ttu-id="958de-182">Если `mWidget` является единственной объектной переменной, содержащей ссылку на старый `Widget`, то объект уничтожается.</span><span class="sxs-lookup"><span data-stu-id="958de-182">If `mWidget` is the only object variable containing a reference to the old `Widget`, the object is destroyed.</span></span> <span data-ttu-id="958de-183">Если требуется обрабатывать события из нескольких `Widget` объектов, используйте `AddHandler` инструкция для обработки событий из каждого объекта отдельно.</span><span class="sxs-lookup"><span data-stu-id="958de-183">If you want to handle events from several `Widget` objects, use the `AddHandler` statement to process events from each object separately.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="958de-184">Можно объявить столько `WithEvents` переменные, как вам требуется. но массивы `WithEvents` переменные не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="958de-184">You can declare as many `WithEvents` variables as you need, but arrays of `WithEvents` variables are not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="958de-185">См. также</span><span class="sxs-lookup"><span data-stu-id="958de-185">See Also</span></span>  
 <span data-ttu-id="958de-186">[Пошаговое руководство: Объявление и вызов событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md) </span><span class="sxs-lookup"><span data-stu-id="958de-186">[Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md) </span></span>  
<span data-ttu-id="958de-187"> [События](../../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="958de-187"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
