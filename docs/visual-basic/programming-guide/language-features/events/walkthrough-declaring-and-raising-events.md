---
title: Объявление и вызов событий
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 6f4c303604f9cf55b4ecd500636e0d2772b6234c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345091"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="9a052-102">Пошаговое руководство. Объявление и создание событий (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a052-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="9a052-103">В этом пошаговом руководстве показано, как объявить и вызвать события для класса с именем `Widget`.</span><span class="sxs-lookup"><span data-stu-id="9a052-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="9a052-104">После выполнения этих действий может потребоваться прочитать сопутствующий раздел [Пошаговое руководство. Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), в которой показано, как использовать события из `Widget` объектов для предоставления сведений о состоянии в приложении.</span><span class="sxs-lookup"><span data-stu-id="9a052-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="9a052-105">Класс Widget</span><span class="sxs-lookup"><span data-stu-id="9a052-105">The Widget Class</span></span>  
 <span data-ttu-id="9a052-106">Предположим, что в момент, когда у вас есть `Widget` класс.</span><span class="sxs-lookup"><span data-stu-id="9a052-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="9a052-107">Класс `Widget` содержит метод, выполнение которого может занять много времени, и вы хотите, чтобы приложение могло поместить какой-либо индикатор завершения.</span><span class="sxs-lookup"><span data-stu-id="9a052-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="9a052-108">Конечно, можно сделать так, чтобы объект `Widget` отображал диалоговое окно «процент завершения», но это диалоговое окно будет зависнуть в каждом проекте, где использовался класс `Widget`.</span><span class="sxs-lookup"><span data-stu-id="9a052-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="9a052-109">Хорошим принципом проектирования объектов является предоставление приложению, использующему объект, обработку пользовательского интерфейса, если только цель объекта не заключается в управлении формой или диалоговым окном.</span><span class="sxs-lookup"><span data-stu-id="9a052-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="9a052-110">Целью `Widget` является выполнение других задач, поэтому лучше добавить событие `PercentDone` и позволить процедуре, вызывающей `Widget`методы, обменять это событие и отображать обновления состояния.</span><span class="sxs-lookup"><span data-stu-id="9a052-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="9a052-111">Событие `PercentDone` может также предоставлять механизм отмены задачи.</span><span class="sxs-lookup"><span data-stu-id="9a052-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="9a052-112">Создание примера кода для этого раздела</span><span class="sxs-lookup"><span data-stu-id="9a052-112">To build the code example for this topic</span></span>  
  
1. <span data-ttu-id="9a052-113">Откройте новый проект приложения Windows Visual Basic и создайте форму с именем `Form1`.</span><span class="sxs-lookup"><span data-stu-id="9a052-113">Open a new Visual Basic Windows Application project and create a form named `Form1`.</span></span>  
  
2. <span data-ttu-id="9a052-114">Добавьте две кнопки и метку для `Form1`.</span><span class="sxs-lookup"><span data-stu-id="9a052-114">Add two buttons and a label to `Form1`.</span></span>  
  
3. <span data-ttu-id="9a052-115">Присвойте им имена, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="9a052-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="9a052-116">Object</span><span class="sxs-lookup"><span data-stu-id="9a052-116">Object</span></span>|<span data-ttu-id="9a052-117">Свойство</span><span class="sxs-lookup"><span data-stu-id="9a052-117">Property</span></span>|<span data-ttu-id="9a052-118">Параметр</span><span class="sxs-lookup"><span data-stu-id="9a052-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="9a052-119">Задача запуска</span><span class="sxs-lookup"><span data-stu-id="9a052-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="9a052-120">Отмена</span><span class="sxs-lookup"><span data-stu-id="9a052-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="9a052-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="9a052-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="9a052-122">Лблперцентдоне, 0</span><span class="sxs-lookup"><span data-stu-id="9a052-122">lblPercentDone, 0</span></span>|  
  
4. <span data-ttu-id="9a052-123">В меню **проект** выберите команду **Добавить класс** , чтобы добавить класс с именем `Widget.vb` в проект.</span><span class="sxs-lookup"><span data-stu-id="9a052-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="9a052-124">Объявление события для класса Widget</span><span class="sxs-lookup"><span data-stu-id="9a052-124">To declare an event for the Widget class</span></span>  
  
- <span data-ttu-id="9a052-125">Используйте ключевое слово `Event` для объявления события в классе `Widget`.</span><span class="sxs-lookup"><span data-stu-id="9a052-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="9a052-126">Обратите внимание, что событие может иметь `ByVal` и `ByRef` аргументов, как событие `PercentDone` `Widget`демонстрируется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9a052-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 <span data-ttu-id="9a052-127">Когда вызывающий объект получает событие `PercentDone`, аргумент `Percent` содержит процент завершенной задачи.</span><span class="sxs-lookup"><span data-stu-id="9a052-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="9a052-128">Аргумент `Cancel` может иметь значение `True`, чтобы отменить метод, вызвавший событие.</span><span class="sxs-lookup"><span data-stu-id="9a052-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9a052-129">Аргументы событий можно объявлять точно так же, как аргументы процедур, со следующими исключениями: события не могут иметь `Optional` или `ParamArray` аргументов, а события не имеют возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="9a052-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="9a052-130">Событие `PercentDone` вызывается методом `LongTask` класса `Widget`.</span><span class="sxs-lookup"><span data-stu-id="9a052-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="9a052-131">`LongTask` принимает два аргумента: время, в течение которого метод должен выполнять работу, и минимальный интервал времени до приостановки `LongTask` для вызова события `PercentDone`.</span><span class="sxs-lookup"><span data-stu-id="9a052-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="9a052-132">Вызов события PercentDone</span><span class="sxs-lookup"><span data-stu-id="9a052-132">To raise the PercentDone event</span></span>  
  
1. <span data-ttu-id="9a052-133">Чтобы упростить доступ к свойству `Timer`, используемому этим классом, добавьте оператор `Imports` в верхнюю часть раздела объявлений модуля класса, над инструкцией `Class Widget`.</span><span class="sxs-lookup"><span data-stu-id="9a052-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. <span data-ttu-id="9a052-134">Добавьте следующий код в класс `Widget` :</span><span class="sxs-lookup"><span data-stu-id="9a052-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 <span data-ttu-id="9a052-135">Когда приложение вызывает метод `LongTask`, класс `Widget` вызывает событие `PercentDone` каждые `MinimumInterval` секунд.</span><span class="sxs-lookup"><span data-stu-id="9a052-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="9a052-136">При возвращении события `LongTask` проверяет, установлено ли для аргумента `Cancel` значение `True`.</span><span class="sxs-lookup"><span data-stu-id="9a052-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="9a052-137">Здесь требуется несколько отказов от ответственности.</span><span class="sxs-lookup"><span data-stu-id="9a052-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="9a052-138">Для простоты `LongTask` процедура предполагает, что вы заранее понимаете, сколько времени займет задача.</span><span class="sxs-lookup"><span data-stu-id="9a052-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="9a052-139">Это практически не так.</span><span class="sxs-lookup"><span data-stu-id="9a052-139">This is almost never the case.</span></span> <span data-ttu-id="9a052-140">Разделение задач на фрагменты даже размера может быть трудной задачей, и часто самое важное для пользователей — просто время, прошедшего до того, как получится, что что-то происходит.</span><span class="sxs-lookup"><span data-stu-id="9a052-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="9a052-141">Возможно, вы заметили другой изъян в этом примере.</span><span class="sxs-lookup"><span data-stu-id="9a052-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="9a052-142">Свойство `Timer` возвращает число секунд, прошедших с полуночи; Поэтому приложение зависает, если оно запускается непосредственно перед полуночью.</span><span class="sxs-lookup"><span data-stu-id="9a052-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="9a052-143">Более аккуратный подход к измерению времени приведет к рассмотрению таких условий, как это необходимо для рассмотрения, или избежать их вообще, используя такие свойства, как `Now`.</span><span class="sxs-lookup"><span data-stu-id="9a052-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="9a052-144">Теперь, когда класс `Widget` может создавать события, можно перейти к следующему пошаговому руководству.</span><span class="sxs-lookup"><span data-stu-id="9a052-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="9a052-145">[Пошаговое руководство. Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) демонстрирует использование `WithEvents` для связывания обработчика событий с событием `PercentDone`.</span><span class="sxs-lookup"><span data-stu-id="9a052-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a052-146">См. также</span><span class="sxs-lookup"><span data-stu-id="9a052-146">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [<span data-ttu-id="9a052-147">Пошаговое руководство. Обработка событий</span><span class="sxs-lookup"><span data-stu-id="9a052-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [<span data-ttu-id="9a052-148">События</span><span class="sxs-lookup"><span data-stu-id="9a052-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
