---
title: Разработка событий
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b257da73d33fae54ef464e9dd69906316b87fd88
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2018
ms.locfileid: "45638916"
---
# <a name="event-design"></a><span data-ttu-id="f00e6-102">Разработка событий</span><span class="sxs-lookup"><span data-stu-id="f00e6-102">Event Design</span></span>
<span data-ttu-id="f00e6-103">События являются наиболее часто используемые формой обратные вызовы (конструкции, которые позволяют framework для вызова пользовательского кода).</span><span class="sxs-lookup"><span data-stu-id="f00e6-103">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="f00e6-104">Другие механизмы обратного вызова участием делегатов, виртуальные члены и основанная на интерфейсах подключаемых модулей. Данные из исследований об удобстве использования, указывают, что большинство разработчиков удобнее работать с помощью событий, чем они при использовании других методов обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="f00e6-104">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="f00e6-105">События хорошо интегрированы с Visual Studio и многих языков.</span><span class="sxs-lookup"><span data-stu-id="f00e6-105">Events are nicely integrated with Visual Studio and many languages.</span></span>  
  
 <span data-ttu-id="f00e6-106">Важно отметить, что две группы событий: события, возникающие до состояния изменения в системе, вызывается предварительного события и события, возникающие после изменения состояния, вызывается после события.</span><span class="sxs-lookup"><span data-stu-id="f00e6-106">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="f00e6-107">Примером предварительного события может служить `Form.Closing`, который вызывается перед закрытием формы.</span><span class="sxs-lookup"><span data-stu-id="f00e6-107">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="f00e6-108">Примером после события может служить `Form.Closed`, который вызывается после закрытия формы.</span><span class="sxs-lookup"><span data-stu-id="f00e6-108">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>  
  
 <span data-ttu-id="f00e6-109">**✓ DO** использовать термин «raise» для событий, а не «fire» или «триггер».</span><span class="sxs-lookup"><span data-stu-id="f00e6-109">**✓ DO** use the term "raise" for events rather than "fire" or "trigger."</span></span>  
  
 <span data-ttu-id="f00e6-110">**✓ DO** используйте <xref:System.EventHandler%601?displayProperty=nameWithType> вместо того чтобы вручную создавать новые делегаты для использования в качестве обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="f00e6-110">**✓ DO** use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>  
  
 <span data-ttu-id="f00e6-111">**✓ CONSIDER** с помощью подкласс <xref:System.EventArgs> в качестве аргумента события, пока не будет точно знать, что событие никогда не понадобится передавать данные метода обработки событий в этом случае можно использовать `EventArgs` ввести напрямую.</span><span class="sxs-lookup"><span data-stu-id="f00e6-111">**✓ CONSIDER** using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>  
  
 <span data-ttu-id="f00e6-112">При доставке API с помощью `EventArgs` напрямую, вы никогда не сможете добавить данные, разделяя без риска нарушить совместимость с событием.</span><span class="sxs-lookup"><span data-stu-id="f00e6-112">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="f00e6-113">Если вы используете подкласс, даже если изначально полностью пустым, можно для добавления свойств в подкласс, при необходимости.</span><span class="sxs-lookup"><span data-stu-id="f00e6-113">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>  
  
 <span data-ttu-id="f00e6-114">**✓ DO** использовать защищенный виртуальный метод для каждого события.</span><span class="sxs-lookup"><span data-stu-id="f00e6-114">**✓ DO** use a protected virtual method to raise each event.</span></span> <span data-ttu-id="f00e6-115">Это значение применимо только на нестатические события незапечатанных классов, не для структур, запечатанные классы или статические события.</span><span class="sxs-lookup"><span data-stu-id="f00e6-115">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>  
  
 <span data-ttu-id="f00e6-116">Метод предназначена для предоставления способа для производного класса для обработки события с помощью переопределения.</span><span class="sxs-lookup"><span data-stu-id="f00e6-116">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="f00e6-117">Переопределение является более гибким, быстрее и более естественный способ обработки событий базового класса в производных классах.</span><span class="sxs-lookup"><span data-stu-id="f00e6-117">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="f00e6-118">По соглашению имя метода должно начинаться с «On» и следовать имя события.</span><span class="sxs-lookup"><span data-stu-id="f00e6-118">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>  
  
 <span data-ttu-id="f00e6-119">Производный класс можно не вызывать базовую реализацию метода в его переопределения.</span><span class="sxs-lookup"><span data-stu-id="f00e6-119">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="f00e6-120">Быть готовы к этому, не включив обработку в метод, который необходим для базового класса для правильной работы.</span><span class="sxs-lookup"><span data-stu-id="f00e6-120">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>  
  
 <span data-ttu-id="f00e6-121">**✓ DO** принимать один параметр для защищенный метод, который вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="f00e6-121">**✓ DO** take one parameter to the protected method that raises an event.</span></span>  
  
 <span data-ttu-id="f00e6-122">Параметр должен иметь имя `e` и должны быть типизированы как класс аргументов события.</span><span class="sxs-lookup"><span data-stu-id="f00e6-122">The parameter should be named `e` and should be typed as the event argument class.</span></span>  
  
 <span data-ttu-id="f00e6-123">**X DO NOT** передает null в качестве отправителя при нестатические события.</span><span class="sxs-lookup"><span data-stu-id="f00e6-123">**X DO NOT** pass null as the sender when raising a nonstatic event.</span></span>  
  
 <span data-ttu-id="f00e6-124">**✓ DO** передает null в качестве отправителя при статические события.</span><span class="sxs-lookup"><span data-stu-id="f00e6-124">**✓ DO** pass null as the sender when raising a static event.</span></span>  
  
 <span data-ttu-id="f00e6-125">**X DO NOT** передает null в качестве параметра данных события при возникновении события.</span><span class="sxs-lookup"><span data-stu-id="f00e6-125">**X DO NOT** pass null as the event data parameter when raising an event.</span></span>  
  
 <span data-ttu-id="f00e6-126">Необходимо передать `EventArgs.Empty` Если вы не хотите передавать все данные в метод обработки события.</span><span class="sxs-lookup"><span data-stu-id="f00e6-126">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="f00e6-127">Разработчики предполагают, что этот параметр не должен иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="f00e6-127">Developers expect this parameter not to be null.</span></span>  
  
 <span data-ttu-id="f00e6-128">**✓ CONSIDER** вызов событий, которые можно отменить конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="f00e6-128">**✓ CONSIDER** raising events that the end user can cancel.</span></span> <span data-ttu-id="f00e6-129">Это относится только к предварительного события.</span><span class="sxs-lookup"><span data-stu-id="f00e6-129">This only applies to pre-events.</span></span>  
  
 <span data-ttu-id="f00e6-130">Используйте <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> или его подкласс как аргумент и позволяющие конечным пользователям для отмены события.</span><span class="sxs-lookup"><span data-stu-id="f00e6-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>  
  
### <a name="custom-event-handler-design"></a><span data-ttu-id="f00e6-131">Разработка настраиваемого обработчика событий</span><span class="sxs-lookup"><span data-stu-id="f00e6-131">Custom Event Handler Design</span></span>  
 <span data-ttu-id="f00e6-132">Бывают случаи, в котором `EventHandler<T>` не может использоваться, например когда платформа должна работать в более ранних версиях среды CLR, который не поддерживает универсальные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="f00e6-132">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="f00e6-133">В таких случаях может потребоваться для проектирования и разработки делегат обработчика пользовательского события.</span><span class="sxs-lookup"><span data-stu-id="f00e6-133">In such cases, you might need to design and develop a custom event handler delegate.</span></span>  
  
 <span data-ttu-id="f00e6-134">**✓ DO** использовать тип возвращаемого значения void для обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="f00e6-134">**✓ DO** use a return type of void for event handlers.</span></span>  
  
 <span data-ttu-id="f00e6-135">Обработчик событий может вызывать несколько событий, обработка методов, возможно, на несколько объектов.</span><span class="sxs-lookup"><span data-stu-id="f00e6-135">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="f00e6-136">Если методы обработки событий было разрешено для возврата значения, то должно быть несколько возвращаемые значения для каждого вызова событий.</span><span class="sxs-lookup"><span data-stu-id="f00e6-136">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>  
  
 <span data-ttu-id="f00e6-137">**✓ DO** использовать `object` как тип первого аргумента обработчика событий и вызывает его `sender`.</span><span class="sxs-lookup"><span data-stu-id="f00e6-137">**✓ DO** use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>  
  
 <span data-ttu-id="f00e6-138">**✓ DO** использовать <xref:System.EventArgs?displayProperty=nameWithType> или его подкласс в качестве типа второго аргумента обработчика событий и вызывает его `e`.</span><span class="sxs-lookup"><span data-stu-id="f00e6-138">**✓ DO** use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>  
  
 <span data-ttu-id="f00e6-139">**X DO NOT** иметь более двух параметров на обработчики событий.</span><span class="sxs-lookup"><span data-stu-id="f00e6-139">**X DO NOT** have more than two parameters on event handlers.</span></span>  
  
 <span data-ttu-id="f00e6-140">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="f00e6-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f00e6-141">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="f00e6-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f00e6-142">См. также</span><span class="sxs-lookup"><span data-stu-id="f00e6-142">See also</span></span>

- [<span data-ttu-id="f00e6-143">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="f00e6-143">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="f00e6-144">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="f00e6-144">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
