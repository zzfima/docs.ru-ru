---
title: Разработка событий
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
ms.openlocfilehash: 78d765a7af77b1e6a6ecd483677cea2d4c6b0d5b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709430"
---
# <a name="event-design"></a><span data-ttu-id="994fd-102">Разработка событий</span><span class="sxs-lookup"><span data-stu-id="994fd-102">Event Design</span></span>
<span data-ttu-id="994fd-103">События — это наиболее часто используемая форма обратных вызовов (конструкций, позволяющая платформе вызывать пользовательский код).</span><span class="sxs-lookup"><span data-stu-id="994fd-103">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="994fd-104">Другие механизмы обратного вызова включают члены, принимающие делегаты, виртуальные члены и подключаемые модули на основе интерфейсов. данные из исследований удобства использования указывают на то, что большинство разработчиков более удобно использовать события, чем они используют другие механизмы обратного вызова. .</span><span class="sxs-lookup"><span data-stu-id="994fd-104">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="994fd-105">События хорошо интегрируются с Visual Studio и многими языками.</span><span class="sxs-lookup"><span data-stu-id="994fd-105">Events are nicely integrated with Visual Studio and many languages.</span></span>  
  
 <span data-ttu-id="994fd-106">Важно отметить, что существует две группы событий: события, вызванные до изменения состояния системы, называемые событиями pre-Events, и события, возникающие после изменения состояния, называемые событиями после.</span><span class="sxs-lookup"><span data-stu-id="994fd-106">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="994fd-107">Примером предварительного события может быть `Form.Closing`, который вызывается перед закрытием формы.</span><span class="sxs-lookup"><span data-stu-id="994fd-107">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="994fd-108">Примером события, поступающего после закрытия формы, может быть `Form.Closed`.</span><span class="sxs-lookup"><span data-stu-id="994fd-108">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>  
  
 <span data-ttu-id="994fd-109">**✓ DO** использовать термин «raise» для событий, а не «fire» или «триггер».</span><span class="sxs-lookup"><span data-stu-id="994fd-109">**✓ DO** use the term "raise" for events rather than "fire" or "trigger."</span></span>  
  
 <span data-ttu-id="994fd-110">**✓ DO** используйте <xref:System.EventHandler%601?displayProperty=nameWithType> вместо того чтобы вручную создавать новые делегаты для использования в качестве обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="994fd-110">**✓ DO** use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>  
  
 <span data-ttu-id="994fd-111">**✓ CONSIDER** с помощью подкласс <xref:System.EventArgs> в качестве аргумента события, пока не будет точно знать, что событие никогда не понадобится передавать данные метода обработки событий в этом случае можно использовать `EventArgs` ввести напрямую.</span><span class="sxs-lookup"><span data-stu-id="994fd-111">**✓ CONSIDER** using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>  
  
 <span data-ttu-id="994fd-112">Если вы подаете API с помощью `EventArgs` напрямую, вы никогда не сможете добавлять данные, которые будут перенесены с событием без нарушения совместимости.</span><span class="sxs-lookup"><span data-stu-id="994fd-112">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="994fd-113">Если вы используете подкласс, даже если изначально он полностью пуст, вы сможете добавлять свойства в подкласс при необходимости.</span><span class="sxs-lookup"><span data-stu-id="994fd-113">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>  
  
 <span data-ttu-id="994fd-114">**✓ DO** использовать защищенный виртуальный метод для каждого события.</span><span class="sxs-lookup"><span data-stu-id="994fd-114">**✓ DO** use a protected virtual method to raise each event.</span></span> <span data-ttu-id="994fd-115">Это применимо только к нестатическим событиям в незапечатанных классах, а не к структурам, запечатанным классам или статическим событиям.</span><span class="sxs-lookup"><span data-stu-id="994fd-115">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>  
  
 <span data-ttu-id="994fd-116">Цель метода — предоставить способ для производного класса, обрабатывающий событие с помощью переопределения.</span><span class="sxs-lookup"><span data-stu-id="994fd-116">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="994fd-117">Переопределение является более гибким, быстрым и естественным способом управления событиями базового класса в производных классах.</span><span class="sxs-lookup"><span data-stu-id="994fd-117">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="994fd-118">По соглашению имя метода должно начинаться с "on" и состоять из имени события.</span><span class="sxs-lookup"><span data-stu-id="994fd-118">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>  
  
 <span data-ttu-id="994fd-119">Производный класс может не вызывать базовую реализацию метода в его переопределении.</span><span class="sxs-lookup"><span data-stu-id="994fd-119">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="994fd-120">Будьте готовы к этому, не включая обработку в методе, который требуется для правильной работы базового класса.</span><span class="sxs-lookup"><span data-stu-id="994fd-120">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>  
  
 <span data-ttu-id="994fd-121">**✓ DO** принимать один параметр для защищенный метод, который вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="994fd-121">**✓ DO** take one parameter to the protected method that raises an event.</span></span>  
  
 <span data-ttu-id="994fd-122">Параметр должен иметь имя `e` и быть типизированным в качестве класса аргумента события.</span><span class="sxs-lookup"><span data-stu-id="994fd-122">The parameter should be named `e` and should be typed as the event argument class.</span></span>  
  
 <span data-ttu-id="994fd-123">**X DO NOT** передает null в качестве отправителя при нестатические события.</span><span class="sxs-lookup"><span data-stu-id="994fd-123">**X DO NOT** pass null as the sender when raising a nonstatic event.</span></span>  
  
 <span data-ttu-id="994fd-124">**✓ DO** передает null в качестве отправителя при статические события.</span><span class="sxs-lookup"><span data-stu-id="994fd-124">**✓ DO** pass null as the sender when raising a static event.</span></span>  
  
 <span data-ttu-id="994fd-125">**X DO NOT** передает null в качестве параметра данных события при возникновении события.</span><span class="sxs-lookup"><span data-stu-id="994fd-125">**X DO NOT** pass null as the event data parameter when raising an event.</span></span>  
  
 <span data-ttu-id="994fd-126">Следует передавать `EventArgs.Empty`, если вы не хотите передавать какие бы то ни было данные в метод обработки событий.</span><span class="sxs-lookup"><span data-stu-id="994fd-126">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="994fd-127">Разработчики предполагают, что этот параметр не должен иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="994fd-127">Developers expect this parameter not to be null.</span></span>  
  
 <span data-ttu-id="994fd-128">**✓ CONSIDER** вызов событий, которые можно отменить конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="994fd-128">**✓ CONSIDER** raising events that the end user can cancel.</span></span> <span data-ttu-id="994fd-129">Это относится только к предварительным событиям.</span><span class="sxs-lookup"><span data-stu-id="994fd-129">This only applies to pre-events.</span></span>  
  
 <span data-ttu-id="994fd-130">Используйте <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> или его подкласс в качестве аргумента события, чтобы разрешить конечному пользователю отменять события.</span><span class="sxs-lookup"><span data-stu-id="994fd-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>  
  
### <a name="custom-event-handler-design"></a><span data-ttu-id="994fd-131">Разработка пользовательского обработчика событий</span><span class="sxs-lookup"><span data-stu-id="994fd-131">Custom Event Handler Design</span></span>  
 <span data-ttu-id="994fd-132">Существуют случаи, в которых `EventHandler<T>` нельзя использовать, например, если платформа должна работать с более ранними версиями среды CLR, которые не поддерживали универсальные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="994fd-132">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="994fd-133">В таких случаях может потребоваться разработать и разработать пользовательский делегат обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="994fd-133">In such cases, you might need to design and develop a custom event handler delegate.</span></span>  
  
 <span data-ttu-id="994fd-134">**✓ DO** использовать тип возвращаемого значения void для обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="994fd-134">**✓ DO** use a return type of void for event handlers.</span></span>  
  
 <span data-ttu-id="994fd-135">Обработчик событий может вызывать несколько методов обработки событий, возможно, для нескольких объектов.</span><span class="sxs-lookup"><span data-stu-id="994fd-135">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="994fd-136">Если методы обработки событий позволяли возвращать значение, то для каждого вызова события было бы несколько возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="994fd-136">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>  
  
 <span data-ttu-id="994fd-137">**✓ DO** использовать `object` как тип первого аргумента обработчика событий и вызывает его `sender`.</span><span class="sxs-lookup"><span data-stu-id="994fd-137">**✓ DO** use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>  
  
 <span data-ttu-id="994fd-138">**✓ DO** использовать <xref:System.EventArgs?displayProperty=nameWithType> или его подкласс в качестве типа второго аргумента обработчика событий и вызывает его `e`.</span><span class="sxs-lookup"><span data-stu-id="994fd-138">**✓ DO** use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>  
  
 <span data-ttu-id="994fd-139">**X DO NOT** иметь более двух параметров на обработчики событий.</span><span class="sxs-lookup"><span data-stu-id="994fd-139">**X DO NOT** have more than two parameters on event handlers.</span></span>  
  
 <span data-ttu-id="994fd-140">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="994fd-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="994fd-141">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="994fd-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="994fd-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="994fd-142">See also</span></span>

- [<span data-ttu-id="994fd-143">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="994fd-143">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="994fd-144">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="994fd-144">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
