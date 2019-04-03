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
ms.openlocfilehash: 0f48c90232c00f53007e7d2f8f08e2107406ecad
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841008"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="3e188-102">Пошаговое руководство. Объявление и вызов событий (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e188-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="3e188-103">В этом пошаговом руководстве демонстрируется объявление и вызов событий для класса с именем `Widget`.</span><span class="sxs-lookup"><span data-stu-id="3e188-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="3e188-104">После выполнения действий, может потребоваться чтение сопутствующего раздела [Пошаговое руководство: Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), который показывает, как использовать события из `Widget` объекты, содержащие сведения о состоянии в приложении.</span><span class="sxs-lookup"><span data-stu-id="3e188-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="3e188-105">Класс мини-приложения</span><span class="sxs-lookup"><span data-stu-id="3e188-105">The Widget Class</span></span>  
 <span data-ttu-id="3e188-106">Предположим, у вас `Widget` класса.</span><span class="sxs-lookup"><span data-stu-id="3e188-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="3e188-107">Ваш `Widget` класс имеет метод, который может занять много времени для выполнения, и требуется обновлять приложение, чтобы иметь возможность создавать какой-то индикатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="3e188-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="3e188-108">Само собой, позволяющих улучшить `Widget` объект отображает процент завершения диалоговое окно, но затем это диалоговое окно будет присутствовать в каждом проекте, в котором использовались `Widget` класса.</span><span class="sxs-lookup"><span data-stu-id="3e188-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="3e188-109">Хороший подход при разработке объекта — приложение, использующий дескриптор объекта пользовательского интерфейса, если объект специально для управления в форме или диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="3e188-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="3e188-110">Цель `Widget` является для выполнения других задач, поэтому лучше добавьте `PercentDone` событий, а также ускоряют выполнение процедуры, которая вызывает `Widget`в методы обрабатывают что обновляет состояние событий и отображения.</span><span class="sxs-lookup"><span data-stu-id="3e188-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="3e188-111">`PercentDone` Событие также может предоставить механизм отмены задачи.</span><span class="sxs-lookup"><span data-stu-id="3e188-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="3e188-112">Для построения примера кода для этого раздела</span><span class="sxs-lookup"><span data-stu-id="3e188-112">To build the code example for this topic</span></span>  
  
1.  <span data-ttu-id="3e188-113">Откройте новый проект приложения Windows в Visual Basic и создайте форму с именем `Form1`.</span><span class="sxs-lookup"><span data-stu-id="3e188-113">Open a new Visual Basic Windows Application project and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="3e188-114">Добавьте две кнопки и метки для `Form1`.</span><span class="sxs-lookup"><span data-stu-id="3e188-114">Add two buttons and a label to `Form1`.</span></span>  
  
3.  <span data-ttu-id="3e188-115">Присвойте им имена, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="3e188-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="3e188-116">Объект</span><span class="sxs-lookup"><span data-stu-id="3e188-116">Object</span></span>|<span data-ttu-id="3e188-117">Свойство.</span><span class="sxs-lookup"><span data-stu-id="3e188-117">Property</span></span>|<span data-ttu-id="3e188-118">Параметр</span><span class="sxs-lookup"><span data-stu-id="3e188-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="3e188-119">Задача запуска</span><span class="sxs-lookup"><span data-stu-id="3e188-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="3e188-120">Отмена</span><span class="sxs-lookup"><span data-stu-id="3e188-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="3e188-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="3e188-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="3e188-122">lblPercentDone 0</span><span class="sxs-lookup"><span data-stu-id="3e188-122">lblPercentDone, 0</span></span>|  
  
4.  <span data-ttu-id="3e188-123">На **проекта** меню, выберите **Добавление класса** добавляемый класс с именем `Widget.vb` в проект.</span><span class="sxs-lookup"><span data-stu-id="3e188-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="3e188-124">Для объявления события для класса мини-приложения</span><span class="sxs-lookup"><span data-stu-id="3e188-124">To declare an event for the Widget class</span></span>  
  
-   <span data-ttu-id="3e188-125">Используйте `Event` ключевого слова для объявления события в `Widget` класса.</span><span class="sxs-lookup"><span data-stu-id="3e188-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="3e188-126">Обратите внимание, что событие может иметь `ByVal` и `ByRef` аргументы, как `Widget`в `PercentDone` демонстрирует событий:</span><span class="sxs-lookup"><span data-stu-id="3e188-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 <span data-ttu-id="3e188-127">Когда вызывающий объект получает `PercentDone` событий, `Percent` аргумент содержит процент завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="3e188-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="3e188-128">`Cancel` Аргумент может быть задан равным `True` отменить метод, который вызвал событие.</span><span class="sxs-lookup"><span data-stu-id="3e188-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e188-129">Аргументы событий можно объявлять так же, как аргументы процедур, за исключением следующих случаев: События не могут иметь `Optional` или `ParamArray` аргументов, а события не имеют возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="3e188-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="3e188-130">`PercentDone` Событие `LongTask` метод `Widget` класса.</span><span class="sxs-lookup"><span data-stu-id="3e188-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="3e188-131">`LongTask` принимает два аргумента: продолжительность времени метод симулирования выполнения работы и минимальный временной интервал перед `LongTask` приостанавливается, чтобы вызвать `PercentDone` событий.</span><span class="sxs-lookup"><span data-stu-id="3e188-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="3e188-132">Для вызова события PercentDone</span><span class="sxs-lookup"><span data-stu-id="3e188-132">To raise the PercentDone event</span></span>  
  
1.  <span data-ttu-id="3e188-133">Для упрощения доступа к `Timer` добавьте свойство, используемое этим классом, `Imports` в начало раздела объявлений класса модуля, выше `Class Widget` инструкции.</span><span class="sxs-lookup"><span data-stu-id="3e188-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2.  <span data-ttu-id="3e188-134">Добавьте следующий код в класс `Widget` :</span><span class="sxs-lookup"><span data-stu-id="3e188-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 <span data-ttu-id="3e188-135">Когда приложение вызывает `LongTask` метод, `Widget` формируемых классом `PercentDone` событий каждые `MinimumInterval` секунд.</span><span class="sxs-lookup"><span data-stu-id="3e188-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="3e188-136">По возвращении из события `LongTask` проверяет, если `Cancel` значение аргумента `True`.</span><span class="sxs-lookup"><span data-stu-id="3e188-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="3e188-137">Здесь необходимы несколько заявления об отказе.</span><span class="sxs-lookup"><span data-stu-id="3e188-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="3e188-138">Для простоты `LongTask` процедуре предполагается, заранее известно, сколько времени потребуется задачи.</span><span class="sxs-lookup"><span data-stu-id="3e188-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="3e188-139">Это не так.</span><span class="sxs-lookup"><span data-stu-id="3e188-139">This is almost never the case.</span></span> <span data-ttu-id="3e188-140">Разделение задания на равные части может быть сложным, и часто наиболее важным для пользователей — это просто объем времени, которое проходит, прежде чем они появятся сведения о происходящем.</span><span class="sxs-lookup"><span data-stu-id="3e188-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="3e188-141">Возможно, Вы отметили еще один недостаток в этом образце.</span><span class="sxs-lookup"><span data-stu-id="3e188-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="3e188-142">`Timer` Свойство возвращает количество секунд, прошедших с полуночи; таким образом, приложение зависает, если она запущена только до полуночи.</span><span class="sxs-lookup"><span data-stu-id="3e188-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="3e188-143">Для более точного измерения времени будет принять это во внимание или избежать их в общей сложности с помощью свойств, таких как `Now`.</span><span class="sxs-lookup"><span data-stu-id="3e188-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="3e188-144">Теперь, когда `Widget` класс может создавать события, можно переместить в следующих пошаговых руководствах.</span><span class="sxs-lookup"><span data-stu-id="3e188-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="3e188-145">[Пошаговое руководство: Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) демонстрирует использование `WithEvents` для связывания обработчика событий с `PercentDone` событий.</span><span class="sxs-lookup"><span data-stu-id="3e188-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e188-146">См. также</span><span class="sxs-lookup"><span data-stu-id="3e188-146">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [<span data-ttu-id="3e188-147">Пошаговое руководство: Обработка событий</span><span class="sxs-lookup"><span data-stu-id="3e188-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [<span data-ttu-id="3e188-148">События</span><span class="sxs-lookup"><span data-stu-id="3e188-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
