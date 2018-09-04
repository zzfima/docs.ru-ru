---
title: События (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 03c2ffc37bc6c2e820b8e28599f415cde1be9be5
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43521961"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="115f7-102">События (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="115f7-102">Events (C# Programming Guide)</span></span>
<span data-ttu-id="115f7-103">События позволяют [классу](../../../csharp/language-reference/keywords/class.md) или объекту уведомлять другие классы или объекты о возникновении каких-либо ситуаций.</span><span class="sxs-lookup"><span data-stu-id="115f7-103">Events enable a [class](../../../csharp/language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="115f7-104">Класс, отправляющий (или *порождающий*) событие, называется *издателем* , а классы, принимающие (или *обрабатывающие*) событие, называются *подписчиками*.</span><span class="sxs-lookup"><span data-stu-id="115f7-104">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
 <span data-ttu-id="115f7-105">В типичном веб-приложении или приложении Windows Forms C# вы подписываетесь на события, вызываемые элементами управления, такими как кнопки и списки.</span><span class="sxs-lookup"><span data-stu-id="115f7-105">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="115f7-106">Вы можете использовать интегрированную среду разработки (IDE) Visual C#, чтобы просмотреть события, публикуемые элементом управления, и выбрать те из них, которые необходимо обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="115f7-106">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="115f7-107">IDE автоматически добавляет пустой метод обработчика событий и код для подписки на событие.</span><span class="sxs-lookup"><span data-stu-id="115f7-107">The IDE automatically adds an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="115f7-108">Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="115f7-108">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="events-overview"></a><span data-ttu-id="115f7-109">Общие сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="115f7-109">Events Overview</span></span>  
 <span data-ttu-id="115f7-110">События имеют следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="115f7-110">Events have the following properties:</span></span>  
  
-   <span data-ttu-id="115f7-111">Издатель определяет, когда возникает событие; подписчики определяют, какое действие выполняется в ответ на событие.</span><span class="sxs-lookup"><span data-stu-id="115f7-111">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
-   <span data-ttu-id="115f7-112">У события может быть несколько подписчиков.</span><span class="sxs-lookup"><span data-stu-id="115f7-112">An event can have multiple subscribers.</span></span> <span data-ttu-id="115f7-113">Подписчик может обрабатывать несколько событий от нескольких издателей.</span><span class="sxs-lookup"><span data-stu-id="115f7-113">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
-   <span data-ttu-id="115f7-114">События, не имеющие подписчиков, никогда не возникают.</span><span class="sxs-lookup"><span data-stu-id="115f7-114">Events that have no subscribers are never raised.</span></span>  
  
-   <span data-ttu-id="115f7-115">Обычно события используются для оповещения о действиях пользователя, например нажатиях кнопок или выборе пунктов меню в графических пользовательских интерфейсах.</span><span class="sxs-lookup"><span data-stu-id="115f7-115">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
-   <span data-ttu-id="115f7-116">Если событие имеет несколько подписчиков, при возникновении события обработчики событий вызываются синхронно.</span><span class="sxs-lookup"><span data-stu-id="115f7-116">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="115f7-117">Сведения об асинхронном вызове событий см. в разделе [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="115f7-117">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
-   <span data-ttu-id="115f7-118">В библиотеке классов [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] события основываются на делегате <xref:System.EventHandler> и базовом классе <xref:System.EventArgs> .</span><span class="sxs-lookup"><span data-stu-id="115f7-118">In the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="115f7-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="115f7-119">Related Sections</span></span>  
 <span data-ttu-id="115f7-120">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="115f7-120">For more information, see:</span></span>  
  
-   [<span data-ttu-id="115f7-121">Практическое руководство. Подписка и отмена подписки на события</span><span class="sxs-lookup"><span data-stu-id="115f7-121">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [<span data-ttu-id="115f7-122">Практическое руководство. Публикация событий, соответствующих рекомендациям для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="115f7-122">How to: Publish Events that Conform to .NET Framework Guidelines</span></span>](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [<span data-ttu-id="115f7-123">Практическое руководство. Создание событий базового класса в производных классах</span><span class="sxs-lookup"><span data-stu-id="115f7-123">How to: Raise Base Class Events in Derived Classes</span></span>](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [<span data-ttu-id="115f7-124">Практическое руководство. Реализация событий интерфейса</span><span class="sxs-lookup"><span data-stu-id="115f7-124">How to:  Implement Interface Events</span></span>](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [<span data-ttu-id="115f7-125">Синхронизация потоков</span><span class="sxs-lookup"><span data-stu-id="115f7-125">Thread Synchronization</span></span>](../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
  
-   [<span data-ttu-id="115f7-126">Практическое руководство. Использование словаря для хранения экземпляров событий</span><span class="sxs-lookup"><span data-stu-id="115f7-126">How to: Use a Dictionary to Store Event Instances</span></span>](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [<span data-ttu-id="115f7-127">Практическое руководство. Реализация пользовательских методов доступа к событиям</span><span class="sxs-lookup"><span data-stu-id="115f7-127">How to: Implement Custom Event Accessors</span></span>](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="115f7-128">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="115f7-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="115f7-129">Главы в популярных книгах</span><span class="sxs-lookup"><span data-stu-id="115f7-129">Featured Book Chapters</span></span>  
 <span data-ttu-id="115f7-130">[Делегаты, события и лямбда-выражения](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) в [справочном руководстве по C# 3.0, третье издание: более 250 решений для программистов на C# 3.0](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span><span class="sxs-lookup"><span data-stu-id="115f7-130">[Delegates, Events, and Lambda Expressions](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span></span>  
  
 <span data-ttu-id="115f7-131">[Делегаты и события](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) в статье [Изучение C# 3.0: овладение основными понятиями C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span><span class="sxs-lookup"><span data-stu-id="115f7-131">[Delegates and Events](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="115f7-132">См. также</span><span class="sxs-lookup"><span data-stu-id="115f7-132">See Also</span></span>

- <xref:System.EventHandler>  
- [<span data-ttu-id="115f7-133">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="115f7-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="115f7-134">Делегаты</span><span class="sxs-lookup"><span data-stu-id="115f7-134">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
- [<span data-ttu-id="115f7-135">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="115f7-135">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
