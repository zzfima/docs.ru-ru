---
title: Руководство по программированию на C#. События
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 84a7eba7bf71f5ef5a0f46eb5863952e1af37c86
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635435"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="117ec-102">События (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="117ec-102">Events (C# Programming Guide)</span></span>
<span data-ttu-id="117ec-103">События позволяют [классу](../../language-reference/keywords/class.md) или объекту уведомлять другие классы или объекты о возникновении каких-либо ситуаций.</span><span class="sxs-lookup"><span data-stu-id="117ec-103">Events enable a [class](../../language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="117ec-104">Класс, отправляющий (или *порождающий*) событие, называется *издателем* , а классы, принимающие (или *обрабатывающие*) событие, называются *подписчиками*.</span><span class="sxs-lookup"><span data-stu-id="117ec-104">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
<span data-ttu-id="117ec-105">В типичном веб-приложении или приложении Windows Forms на C# вы подписываетесь на события, вызываемые элементами управления, такими как кнопки и списки.</span><span class="sxs-lookup"><span data-stu-id="117ec-105">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="117ec-106">Вы можете использовать интегрированную среду разработки (IDE) Visual C#, чтобы просмотреть события, публикуемые элементом управления, и выбрать те из них, которые необходимо обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="117ec-106">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="117ec-107">IDE позволяет автоматически добавлять пустой метод обработчика событий и код для подписки на событие.</span><span class="sxs-lookup"><span data-stu-id="117ec-107">The IDE provides an easy way to automatically add an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="117ec-108">Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="117ec-108">For more information, see [How to subscribe to and unsubscribe from events](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>
  
## <a name="events-overview"></a><span data-ttu-id="117ec-109">Общие сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="117ec-109">Events Overview</span></span>  
 <span data-ttu-id="117ec-110">События имеют следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="117ec-110">Events have the following properties:</span></span>  
  
- <span data-ttu-id="117ec-111">Издатель определяет, когда возникает событие; подписчики определяют, какое действие выполняется в ответ на событие.</span><span class="sxs-lookup"><span data-stu-id="117ec-111">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
- <span data-ttu-id="117ec-112">У события может быть несколько подписчиков.</span><span class="sxs-lookup"><span data-stu-id="117ec-112">An event can have multiple subscribers.</span></span> <span data-ttu-id="117ec-113">Подписчик может обрабатывать несколько событий от нескольких издателей.</span><span class="sxs-lookup"><span data-stu-id="117ec-113">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
- <span data-ttu-id="117ec-114">События, не имеющие подписчиков, никогда не возникают.</span><span class="sxs-lookup"><span data-stu-id="117ec-114">Events that have no subscribers are never raised.</span></span>  
  
- <span data-ttu-id="117ec-115">Обычно события используются для оповещения о действиях пользователя, например нажатиях кнопок или выборе пунктов меню в графических пользовательских интерфейсах.</span><span class="sxs-lookup"><span data-stu-id="117ec-115">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
- <span data-ttu-id="117ec-116">Если событие имеет несколько подписчиков, при возникновении события обработчики событий вызываются синхронно.</span><span class="sxs-lookup"><span data-stu-id="117ec-116">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="117ec-117">Сведения об асинхронном вызове событий см. в разделе [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="117ec-117">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
- <span data-ttu-id="117ec-118">В библиотеке классов .NET Framework события основываются на делегате <xref:System.EventHandler> и базовом классе <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="117ec-118">In the .NET Framework class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="117ec-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="117ec-119">Related Sections</span></span>  
 <span data-ttu-id="117ec-120">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="117ec-120">For more information, see:</span></span>  
  
- [<span data-ttu-id="117ec-121">Практическое руководство. Подписка и отмена подписки на события</span><span class="sxs-lookup"><span data-stu-id="117ec-121">How to subscribe to and unsubscribe from events</span></span>](./how-to-subscribe-to-and-unsubscribe-from-events.md)

- [<span data-ttu-id="117ec-122">Практическое руководство. Публикация событий, соответствующих рекомендациям .NET Framework</span><span class="sxs-lookup"><span data-stu-id="117ec-122">How to publish events that conform to .NET Framework Guidelines</span></span>](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)

- [<span data-ttu-id="117ec-123">Практическое руководство. Создание событий базового класса в производных классах</span><span class="sxs-lookup"><span data-stu-id="117ec-123">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)

- [<span data-ttu-id="117ec-124">Практическое руководство. Реализация событий интерфейса</span><span class="sxs-lookup"><span data-stu-id="117ec-124">How to implement interface events</span></span>](./how-to-implement-interface-events.md)

- [<span data-ttu-id="117ec-125">Практическое руководство. Реализация пользовательских методов доступа к событиям</span><span class="sxs-lookup"><span data-stu-id="117ec-125">How to implement custom event accessors</span></span>](./how-to-implement-custom-event-accessors.md)

## <a name="c-language-specification"></a><span data-ttu-id="117ec-126">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="117ec-126">C# Language Specification</span></span>  

<span data-ttu-id="117ec-127">Дополнительные сведения см. в разделе [События](~/_csharplang/spec/classes.md#events) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="117ec-127">For more information, see [Events](~/_csharplang/spec/classes.md#events) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="117ec-128">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="117ec-128">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="117ec-129">Главы в популярных книгах</span><span class="sxs-lookup"><span data-stu-id="117ec-129">Featured Book Chapters</span></span>  
 <span data-ttu-id="117ec-130">[Делегаты, события и лямбда-выражения](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) в [справочном руководстве по C# 3.0, третье издание. Более 250 решений для программистов на C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="117ec-130">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
 <span data-ttu-id="117ec-131">[Делегаты и события](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) в [изучении C# 3.0. Овладение основными понятиями C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="117ec-131">[Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="117ec-132">См. также</span><span class="sxs-lookup"><span data-stu-id="117ec-132">See also</span></span>

- <xref:System.EventHandler>
- [<span data-ttu-id="117ec-133">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="117ec-133">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="117ec-134">Делегаты</span><span class="sxs-lookup"><span data-stu-id="117ec-134">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="117ec-135">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="117ec-135">Creating Event Handlers in Windows Forms</span></span>](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)
