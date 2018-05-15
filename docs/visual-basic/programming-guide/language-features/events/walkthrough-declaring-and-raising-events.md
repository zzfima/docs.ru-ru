---
title: Объявление и вызов событий (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 67bbf7bc95a0fe1ee8e9c2a6cf07d850d30bb028
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="91c17-102">Пошаговое руководство. Объявление и создание событий (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91c17-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="91c17-103">В этом пошаговом руководстве демонстрируется объявление и вызов событий для класса с именем `Widget`.</span><span class="sxs-lookup"><span data-stu-id="91c17-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="91c17-104">После выполнения шагов можно ознакомиться с разделом дополнительное [Пошаговое руководство: обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), который показывает, как использовать события из `Widget` объектов для предоставления сведений о состоянии в приложении.</span><span class="sxs-lookup"><span data-stu-id="91c17-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="91c17-105">Класс мини-приложения</span><span class="sxs-lookup"><span data-stu-id="91c17-105">The Widget Class</span></span>  
 <span data-ttu-id="91c17-106">Предположим, что у вас есть `Widget` класса.</span><span class="sxs-lookup"><span data-stu-id="91c17-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="91c17-107">Ваш `Widget` класс содержит метод, который может занять много времени для выполнения и приложение, чтобы иметь возможность создавать какой-то индикатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="91c17-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="91c17-108">Конечно, может сделать `Widget` объект отображает диалоговое окно Процент завершения, но затем это диалоговое окно будет присутствовать в каждом проекте, использующем `Widget` класса.</span><span class="sxs-lookup"><span data-stu-id="91c17-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="91c17-109">Хороший подход при разработке объекта — это передать приложению, использующему дескриптор объекта пользовательского интерфейса, если объект специально для управления формой или диалоговым окном.</span><span class="sxs-lookup"><span data-stu-id="91c17-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="91c17-110">Назначение `Widget` является выполнение других задач, поэтому рекомендуется добавить `PercentDone` событий и позволяют процедуры, которая вызывает `Widget`методы обработки, обновляет состояние события и отображения.</span><span class="sxs-lookup"><span data-stu-id="91c17-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="91c17-111">`PercentDone` Событий также могут предоставлять механизм отмены задачи.</span><span class="sxs-lookup"><span data-stu-id="91c17-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="91c17-112">Для построения примера кода для этого раздела</span><span class="sxs-lookup"><span data-stu-id="91c17-112">To build the code example for this topic</span></span>  
  
1.  <span data-ttu-id="91c17-113">Откройте новый проект приложения Windows в Visual Basic и создайте форму с именем `Form1`.</span><span class="sxs-lookup"><span data-stu-id="91c17-113">Open a new Visual Basic Windows Application project and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="91c17-114">Добавьте две кнопки и метку для `Form1`.</span><span class="sxs-lookup"><span data-stu-id="91c17-114">Add two buttons and a label to `Form1`.</span></span>  
  
3.  <span data-ttu-id="91c17-115">Присвойте им имена, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="91c17-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="91c17-116">Объект</span><span class="sxs-lookup"><span data-stu-id="91c17-116">Object</span></span>|<span data-ttu-id="91c17-117">Свойство</span><span class="sxs-lookup"><span data-stu-id="91c17-117">Property</span></span>|<span data-ttu-id="91c17-118">Параметр</span><span class="sxs-lookup"><span data-stu-id="91c17-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="91c17-119">Задача запуска</span><span class="sxs-lookup"><span data-stu-id="91c17-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="91c17-120">Отмена</span><span class="sxs-lookup"><span data-stu-id="91c17-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="91c17-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="91c17-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="91c17-122">lblPercentDone 0</span><span class="sxs-lookup"><span data-stu-id="91c17-122">lblPercentDone, 0</span></span>|  
  
4.  <span data-ttu-id="91c17-123">На **проекта** меню, выберите **добавить класс** добавить класс с именем `Widget.vb` в проект.</span><span class="sxs-lookup"><span data-stu-id="91c17-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="91c17-124">Для объявления события для класса мини-приложения</span><span class="sxs-lookup"><span data-stu-id="91c17-124">To declare an event for the Widget class</span></span>  
  
-   <span data-ttu-id="91c17-125">Используйте `Event` ключевое слово для объявления события в `Widget` класса.</span><span class="sxs-lookup"><span data-stu-id="91c17-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="91c17-126">Обратите внимание, что событие может иметь `ByVal` и `ByRef` аргументы, как `Widget` `PercentDone` демонстрирует событий:</span><span class="sxs-lookup"><span data-stu-id="91c17-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 <span data-ttu-id="91c17-127">Когда вызывающий объект получает `PercentDone` событий, `Percent` аргумент содержит процент завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="91c17-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="91c17-128">`Cancel` Аргумент может иметь значение `True` отменить метод, создавший событие.</span><span class="sxs-lookup"><span data-stu-id="91c17-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91c17-129">Аргументы событий можно объявлять так же, как аргументы процедур, за следующими исключениями: события не могут иметь `Optional` или `ParamArray` аргументы и события не имеют возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="91c17-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="91c17-130">`PercentDone` Событие `LongTask` метод `Widget` класса.</span><span class="sxs-lookup"><span data-stu-id="91c17-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="91c17-131">`LongTask` принимает два аргумента: продолжительность времени симулирования методом выполнения работы и минимальный интервал времени перед `LongTask` приостанавливает свою работу, чтобы вызвать `PercentDone` событий.</span><span class="sxs-lookup"><span data-stu-id="91c17-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="91c17-132">Для вызова события PercentDone</span><span class="sxs-lookup"><span data-stu-id="91c17-132">To raise the PercentDone event</span></span>  
  
1.  <span data-ttu-id="91c17-133">Чтобы упростить доступ к `Timer` добавить свойства, используемого этим классом `Imports` инструкции в начало раздела объявлений модуля класса, выше `Class Widget` инструкции.</span><span class="sxs-lookup"><span data-stu-id="91c17-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  <span data-ttu-id="91c17-134">Добавьте следующий код в класс `Widget` :</span><span class="sxs-lookup"><span data-stu-id="91c17-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 <span data-ttu-id="91c17-135">Когда приложение вызывает метод `LongTask` метода `Widget` формируемых классом `PercentDone` событие каждый `MinimumInterval` секунд.</span><span class="sxs-lookup"><span data-stu-id="91c17-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="91c17-136">После завершения события, `LongTask` проверяет `Cancel` значение аргумента `True`.</span><span class="sxs-lookup"><span data-stu-id="91c17-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="91c17-137">Здесь необходимы несколько отказы от ответственности.</span><span class="sxs-lookup"><span data-stu-id="91c17-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="91c17-138">Для простоты `LongTask` процедуре предполагается, как долго задачи известно заранее.</span><span class="sxs-lookup"><span data-stu-id="91c17-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="91c17-139">Это не так.</span><span class="sxs-lookup"><span data-stu-id="91c17-139">This is almost never the case.</span></span> <span data-ttu-id="91c17-140">Разделение задания на равные части может быть сложным и часто наиболее пользователям важно просто объем времени, которое проходит, прежде чем они появятся сведения о происходящем.</span><span class="sxs-lookup"><span data-stu-id="91c17-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="91c17-141">Можно найти еще один недостаток в этом образце.</span><span class="sxs-lookup"><span data-stu-id="91c17-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="91c17-142">`Timer` Свойство возвращает число секунд, прошедших с полуночи; таким образом, приложение зависает, если он запущен только до полуночи.</span><span class="sxs-lookup"><span data-stu-id="91c17-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="91c17-143">Для более точного измерения времени бы принять это во внимание или избежать их вообще, такие как с помощью свойства `Now`.</span><span class="sxs-lookup"><span data-stu-id="91c17-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="91c17-144">Теперь, когда `Widget` класс может создавать события, можно переместить в следующем пошаговом руководстве.</span><span class="sxs-lookup"><span data-stu-id="91c17-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="91c17-145">[Пошаговое руководство: Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) демонстрируется использование `WithEvents` для связывания обработчика событий с `PercentDone` событий.</span><span class="sxs-lookup"><span data-stu-id="91c17-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91c17-146">См. также</span><span class="sxs-lookup"><span data-stu-id="91c17-146">See Also</span></span>  
 <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>  
 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>  
 [<span data-ttu-id="91c17-147">Пошаговое руководство. Обработка событий</span><span class="sxs-lookup"><span data-stu-id="91c17-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)  
 [<span data-ttu-id="91c17-148">События</span><span class="sxs-lookup"><span data-stu-id="91c17-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
