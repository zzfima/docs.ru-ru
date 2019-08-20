---
title: Руководство по программированию на C#. События
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 7a8a8e6b6a393f151d69d1879f475e04f44df5fa
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69590378"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="09136-102">События (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="09136-102">Events (C# Programming Guide)</span></span>
<span data-ttu-id="09136-103">События позволяют [классу](../../language-reference/keywords/class.md) или объекту уведомлять другие классы или объекты о возникновении каких-либо ситуаций.</span><span class="sxs-lookup"><span data-stu-id="09136-103">Events enable a [class](../../language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="09136-104">Класс, отправляющий (или *порождающий*) событие, называется *издателем* , а классы, принимающие (или *обрабатывающие*) событие, называются *подписчиками*.</span><span class="sxs-lookup"><span data-stu-id="09136-104">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
 <span data-ttu-id="09136-105">В типичном веб-приложении или приложении Windows Forms на C# вы подписываетесь на события, вызываемые элементами управления, такими как кнопки и списки.</span><span class="sxs-lookup"><span data-stu-id="09136-105">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="09136-106">Вы можете использовать интегрированную среду разработки (IDE) Visual C#, чтобы просмотреть события, публикуемые элементом управления, и выбрать те из них, которые необходимо обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="09136-106">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="09136-107">IDE позволяет автоматически добавлять пустой метод обработчика событий и код для подписки на событие.</span><span class="sxs-lookup"><span data-stu-id="09136-107">The IDE provides an easy way to automatically add an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="09136-108">Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="09136-108">For more information, see [How to: Subscribe to and Unsubscribe from Events](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="events-overview"></a><span data-ttu-id="09136-109">Общие сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="09136-109">Events Overview</span></span>  
 <span data-ttu-id="09136-110">События имеют следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="09136-110">Events have the following properties:</span></span>  
  
- <span data-ttu-id="09136-111">Издатель определяет, когда возникает событие; подписчики определяют, какое действие выполняется в ответ на событие.</span><span class="sxs-lookup"><span data-stu-id="09136-111">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
- <span data-ttu-id="09136-112">У события может быть несколько подписчиков.</span><span class="sxs-lookup"><span data-stu-id="09136-112">An event can have multiple subscribers.</span></span> <span data-ttu-id="09136-113">Подписчик может обрабатывать несколько событий от нескольких издателей.</span><span class="sxs-lookup"><span data-stu-id="09136-113">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
- <span data-ttu-id="09136-114">События, не имеющие подписчиков, никогда не возникают.</span><span class="sxs-lookup"><span data-stu-id="09136-114">Events that have no subscribers are never raised.</span></span>  
  
- <span data-ttu-id="09136-115">Обычно события используются для оповещения о действиях пользователя, например нажатиях кнопок или выборе пунктов меню в графических пользовательских интерфейсах.</span><span class="sxs-lookup"><span data-stu-id="09136-115">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
- <span data-ttu-id="09136-116">Если событие имеет несколько подписчиков, при возникновении события обработчики событий вызываются синхронно.</span><span class="sxs-lookup"><span data-stu-id="09136-116">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="09136-117">Сведения об асинхронном вызове событий см. в разделе [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="09136-117">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
- <span data-ttu-id="09136-118">В библиотеке классов .NET Framework события основываются на делегате <xref:System.EventHandler> и базовом классе <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="09136-118">In the .NET Framework class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="09136-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="09136-119">Related Sections</span></span>  
 <span data-ttu-id="09136-120">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="09136-120">For more information, see:</span></span>  
  
- [<span data-ttu-id="09136-121">Практическое руководство. Подписка и отмена подписки на события</span><span class="sxs-lookup"><span data-stu-id="09136-121">How to: Subscribe to and Unsubscribe from Events</span></span>](./how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
- [<span data-ttu-id="09136-122">Практическое руководство. Публикация событий в соответствии с руководствами по .NET Framework</span><span class="sxs-lookup"><span data-stu-id="09136-122">How to: Publish Events that Conform to .NET Framework Guidelines</span></span>](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
- [<span data-ttu-id="09136-123">Практическое руководство. Создание событий базового класса в производных классах</span><span class="sxs-lookup"><span data-stu-id="09136-123">How to: Raise Base Class Events in Derived Classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)  
  
- [<span data-ttu-id="09136-124">Практическое руководство.  Реализация событий интерфейса</span><span class="sxs-lookup"><span data-stu-id="09136-124">How to:  Implement Interface Events</span></span>](./how-to-implement-interface-events.md)  
  
- [<span data-ttu-id="09136-125">Практическое руководство. Реализация пользовательских методов доступа к событиям</span><span class="sxs-lookup"><span data-stu-id="09136-125">How to: Implement Custom Event Accessors</span></span>](./how-to-implement-custom-event-accessors.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="09136-126">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="09136-126">C# Language Specification</span></span>  

<span data-ttu-id="09136-127">Дополнительные сведения см. в разделе [События](~/_csharplang/spec/classes.md#events) в [Спецификации языка C#](../../language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="09136-127">For more information, see [Events](~/_csharplang/spec/classes.md#events) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="09136-128">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="09136-128">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="09136-129">Главы в популярных книгах</span><span class="sxs-lookup"><span data-stu-id="09136-129">Featured Book Chapters</span></span>  
 <span data-ttu-id="09136-130">[Делегаты, события и лямбда-выражения](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) в [справочном руководстве по C# 3.0, третье издание. Более 250 решений для программистов на C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="09136-130">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
 <span data-ttu-id="09136-131">[Делегаты и события](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) в [изучении C# 3.0. Овладение основными понятиями C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="09136-131">[Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09136-132">См. также</span><span class="sxs-lookup"><span data-stu-id="09136-132">See also</span></span>

- <xref:System.EventHandler>
- [<span data-ttu-id="09136-133">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="09136-133">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="09136-134">Делегаты</span><span class="sxs-lookup"><span data-stu-id="09136-134">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="09136-135">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="09136-135">Creating Event Handlers in Windows Forms</span></span>](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)
