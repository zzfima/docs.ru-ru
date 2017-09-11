---
title: "Объявление и создание событий (Visual Basic) | Документы Microsoft"
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
- declarations, events
- events [Visual Basic], walkthroughs
- declaring events, walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events, walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
caps.latest.revision: 16
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
ms.openlocfilehash: eca112aca39bd998697d379a1705845e8f607367
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="b8918-102">Пошаговое руководство. Объявление и создание событий (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8918-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="b8918-103">В этом пошаговом руководстве демонстрируется объявление и вызов событий для класса с именем `Widget`.</span><span class="sxs-lookup"><span data-stu-id="b8918-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="b8918-104">После выполнения шагов, может потребоваться чтение сопутствующего раздела [Пошаговое руководство: обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), который показывает, как использовать события из `Widget` объектов для предоставления сведений о состоянии в приложении.</span><span class="sxs-lookup"><span data-stu-id="b8918-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="b8918-105">Класс мини-приложения</span><span class="sxs-lookup"><span data-stu-id="b8918-105">The Widget Class</span></span>  
 <span data-ttu-id="b8918-106">Предположим, что у вас есть `Widget` класса.</span><span class="sxs-lookup"><span data-stu-id="b8918-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="b8918-107">Ваш `Widget` класс содержит метод, который может занять много времени для выполнения и приложение, чтобы иметь возможность создавать какой-то индикатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="b8918-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="b8918-108">Конечно, можно также `Widget` объекта Показать диалоговое окно Процент завершения, но затем это диалоговое окно будет присутствовать в каждом проекте, использующем `Widget` класса.</span><span class="sxs-lookup"><span data-stu-id="b8918-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="b8918-109">Хороший подход при разработке объекта — это передать приложению, использующему объект, обработку пользовательского интерфейса, если объект специально для управления формой или диалоговым окном.</span><span class="sxs-lookup"><span data-stu-id="b8918-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="b8918-110">Назначение `Widget` является для выполнения других задач, поэтому лучше добавить `PercentDone` событий и позволяют процедуры, которая вызывает `Widget`методы обработки, событий и отображаемое состояние обновлений.</span><span class="sxs-lookup"><span data-stu-id="b8918-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="b8918-111">`PercentDone` Событий также могут предоставлять механизм отмены данной задачи.</span><span class="sxs-lookup"><span data-stu-id="b8918-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="b8918-112">Чтобы создать пример кода для этого раздела</span><span class="sxs-lookup"><span data-stu-id="b8918-112">To build the code example for this topic</span></span>  
  
1.  <span data-ttu-id="b8918-113">Откройте новую [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] приложения Windows проект и создать форму с именем `Form1`.</span><span class="sxs-lookup"><span data-stu-id="b8918-113">Open a new [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows Application project and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="b8918-114">Добавьте две кнопки и метку, которая `Form1`.</span><span class="sxs-lookup"><span data-stu-id="b8918-114">Add two buttons and a label to `Form1`.</span></span>  
  
3.  <span data-ttu-id="b8918-115">Присвойте имена объектам, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="b8918-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="b8918-116">Объект</span><span class="sxs-lookup"><span data-stu-id="b8918-116">Object</span></span>|<span data-ttu-id="b8918-117">Свойство</span><span class="sxs-lookup"><span data-stu-id="b8918-117">Property</span></span>|<span data-ttu-id="b8918-118">Параметр</span><span class="sxs-lookup"><span data-stu-id="b8918-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="b8918-119">Задача запуска</span><span class="sxs-lookup"><span data-stu-id="b8918-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="b8918-120">Cancel</span><span class="sxs-lookup"><span data-stu-id="b8918-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="b8918-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="b8918-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="b8918-122">lblPercentDone 0</span><span class="sxs-lookup"><span data-stu-id="b8918-122">lblPercentDone, 0</span></span>|  
  
4.  <span data-ttu-id="b8918-123">На **проекта** меню, выберите **добавить класс** добавить класс с именем `Widget.vb` в проект.</span><span class="sxs-lookup"><span data-stu-id="b8918-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="b8918-124">Чтобы объявить событие для класса Widget</span><span class="sxs-lookup"><span data-stu-id="b8918-124">To declare an event for the Widget class</span></span>  
  
-   <span data-ttu-id="b8918-125">Используйте `Event` ключевое слово для объявления события в `Widget` класса.</span><span class="sxs-lookup"><span data-stu-id="b8918-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="b8918-126">Обратите внимание, что событие может иметь `ByVal` и `ByRef` аргументов, как `Widget`в `PercentDone` демонстрирует событий:</span><span class="sxs-lookup"><span data-stu-id="b8918-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     <span data-ttu-id="b8918-127">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#1;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b8918-127">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]</span></span>  
  
 <span data-ttu-id="b8918-128">Когда вызывающий объект получает `PercentDone` событий, `Percent` аргумент содержит процент выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="b8918-128">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="b8918-129">`Cancel` Аргументу присвоено `True` отменить метод, который вызвал событие.</span><span class="sxs-lookup"><span data-stu-id="b8918-129">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8918-130">Аргументы событий можно объявлять так же, как аргументы процедур, за несколькими исключениями: события не могут иметь `Optional` или `ParamArray` аргументы и события не имеют возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="b8918-130">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="b8918-131">`PercentDone` Событие `LongTask` метод `Widget` класса.</span><span class="sxs-lookup"><span data-stu-id="b8918-131">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="b8918-132">`LongTask`принимает два аргумента: продолжительность времени симулирования методом выполнения работы и минимальное время интервала перед `LongTask` будет приостановлен для создания `PercentDone` события.</span><span class="sxs-lookup"><span data-stu-id="b8918-132">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="b8918-133">Для вызова события PercentDone</span><span class="sxs-lookup"><span data-stu-id="b8918-133">To raise the PercentDone event</span></span>  
  
1.  <span data-ttu-id="b8918-134">Для упрощения доступа к `Timer` добавления свойств, используемых в этом классе `Imports` инструкции в начало раздела объявлений модуля класса, выше `Class Widget` инструкции.</span><span class="sxs-lookup"><span data-stu-id="b8918-134">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     <span data-ttu-id="b8918-135">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#2;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b8918-135">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]</span></span>  
  
2.  <span data-ttu-id="b8918-136">Добавьте следующий код в класс `Widget` :</span><span class="sxs-lookup"><span data-stu-id="b8918-136">Add the following code to the `Widget` class:</span></span>  
  
     <span data-ttu-id="b8918-137">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#3;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b8918-137">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]</span></span>  
  
 <span data-ttu-id="b8918-138">Когда приложение вызывает метод `LongTask` метода `Widget` класса вызывает `PercentDone` событие каждый `MinimumInterval` секунд.</span><span class="sxs-lookup"><span data-stu-id="b8918-138">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="b8918-139">При возвращении события `LongTask` проверяет `Cancel` значение аргумента `True`.</span><span class="sxs-lookup"><span data-stu-id="b8918-139">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="b8918-140">Здесь необходимы несколько отказ от ответственности.</span><span class="sxs-lookup"><span data-stu-id="b8918-140">A few disclaimers are necessary here.</span></span> <span data-ttu-id="b8918-141">Для простоты `LongTask` предполагается продолжительность задачи известно заранее.</span><span class="sxs-lookup"><span data-stu-id="b8918-141">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="b8918-142">Это не так.</span><span class="sxs-lookup"><span data-stu-id="b8918-142">This is almost never the case.</span></span> <span data-ttu-id="b8918-143">Разделение задания на равные части может вызвать трудности, и часто наиболее пользователям важно просто объем времени, которое проходит, прежде чем они появятся сведения о происходящем.</span><span class="sxs-lookup"><span data-stu-id="b8918-143">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="b8918-144">Можно найти еще один недостаток в этом образце.</span><span class="sxs-lookup"><span data-stu-id="b8918-144">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="b8918-145">`Timer` Свойство возвращает количество секунд, прошедших с полуночи; таким образом, приложение зависает, если он запущен только до полуночи.</span><span class="sxs-lookup"><span data-stu-id="b8918-145">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="b8918-146">Для более точного измерения времени будет принять это во внимание или избежать их вообще, такие как с помощью свойства `Now`.</span><span class="sxs-lookup"><span data-stu-id="b8918-146">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="b8918-147">Теперь, когда `Widget` класс может создавать события, можно переместить в следующем пошаговом руководстве.</span><span class="sxs-lookup"><span data-stu-id="b8918-147">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="b8918-148">[Пошаговое руководство: Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) демонстрирует использование `WithEvents` для сопоставления обработчика событий с `PercentDone` событий.</span><span class="sxs-lookup"><span data-stu-id="b8918-148">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8918-149">См. также</span><span class="sxs-lookup"><span data-stu-id="b8918-149">See Also</span></span>  
 <span data-ttu-id="b8918-150"><xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></span><span class="sxs-lookup"><span data-stu-id="b8918-150"><xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></span></span>   
 <span data-ttu-id="b8918-151"><xref:Microsoft.VisualBasic.DateAndTime.Now%2A></xref:Microsoft.VisualBasic.DateAndTime.Now%2A></span><span class="sxs-lookup"><span data-stu-id="b8918-151"><xref:Microsoft.VisualBasic.DateAndTime.Now%2A></span></span>   
<span data-ttu-id="b8918-152"> [Пошаговое руководство: Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) </span><span class="sxs-lookup"><span data-stu-id="b8918-152"> [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) </span></span>  
<span data-ttu-id="b8918-153"> [События](../../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="b8918-153"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
