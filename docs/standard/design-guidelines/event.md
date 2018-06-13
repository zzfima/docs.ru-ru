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
ms.openlocfilehash: 48d1ad0f02ae34675c0a910d7651d718c060db60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575398"
---
# <a name="event-design"></a><span data-ttu-id="9420d-102">Разработка событий</span><span class="sxs-lookup"><span data-stu-id="9420d-102">Event Design</span></span>
<span data-ttu-id="9420d-103">События, наиболее часто используемые формы обратных вызовов (конструкций, позволяющих framework вызов кода пользователя).</span><span class="sxs-lookup"><span data-stu-id="9420d-103">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="9420d-104">Другие механизмы обратного вызова включаются элементы, которые занимает делегатов, виртуальные члены и основанная на интерфейсах подключаемых модулей. Данные из исследования удобства использования указывает, что большинство разработчиков удобнее с помощью событий, не используют другие механизмы обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="9420d-104">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="9420d-105">События хорошо интегрированы с Visual Studio и многих языков.</span><span class="sxs-lookup"><span data-stu-id="9420d-105">Events are nicely integrated with Visual Studio and many languages.</span></span>  
  
 <span data-ttu-id="9420d-106">Это важно отметить, что имеются две группы событий: события, возникающие до изменений системы, событий и событий, возникающих после изменения состояния в состояние вызывается после события.</span><span class="sxs-lookup"><span data-stu-id="9420d-106">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="9420d-107">Примером событий до такого `Form.Closing`, который вызывается перед закрытием формы.</span><span class="sxs-lookup"><span data-stu-id="9420d-107">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="9420d-108">Пример после события будет `Form.Closed`, который вызывается после закрытия формы.</span><span class="sxs-lookup"><span data-stu-id="9420d-108">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>  
  
 <span data-ttu-id="9420d-109">**✓ СДЕЛАТЬ** использовать термин «raise» для событий, а не «fire» или «триггер».</span><span class="sxs-lookup"><span data-stu-id="9420d-109">**✓ DO** use the term "raise" for events rather than "fire" or "trigger."</span></span>  
  
 <span data-ttu-id="9420d-110">**СДЕЛАТЬ ✓** используйте <xref:System.EventHandler%601?displayProperty=nameWithType> вместо того чтобы вручную создавать новые делегаты для использования в качестве обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="9420d-110">**✓ DO** use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>  
  
 <span data-ttu-id="9420d-111">**✓ Попробуйте** с помощью подкласс <xref:System.EventArgs> в качестве аргумента события, пока не будет точно знать, что событие никогда не понадобится передавать данные метода обработки событий в этом случае можно использовать `EventArgs` ввести напрямую.</span><span class="sxs-lookup"><span data-stu-id="9420d-111">**✓ CONSIDER** using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>  
  
 <span data-ttu-id="9420d-112">Если планируется API с помощью `EventArgs` напрямую, никогда не появится возможность добавления всех данных выполнена без нарушения совместимости с событием.</span><span class="sxs-lookup"><span data-stu-id="9420d-112">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="9420d-113">При использовании подкласс, даже если изначально полностью пуста, вы сможете для добавления свойств в подклассе, если это требуется.</span><span class="sxs-lookup"><span data-stu-id="9420d-113">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>  
  
 <span data-ttu-id="9420d-114">**✓ СДЕЛАТЬ** использовать защищенный виртуальный метод для каждого события.</span><span class="sxs-lookup"><span data-stu-id="9420d-114">**✓ DO** use a protected virtual method to raise each event.</span></span> <span data-ttu-id="9420d-115">Это значение применимо только нестатические на незапечатанные классы, структуры, запечатанные классы или статические события для события.</span><span class="sxs-lookup"><span data-stu-id="9420d-115">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>  
  
 <span data-ttu-id="9420d-116">Метод предназначен для предоставления возможности для производного класса для обработки события, с помощью переопределения.</span><span class="sxs-lookup"><span data-stu-id="9420d-116">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="9420d-117">Переопределение является более гибким, быстрее и более естественным способом обработки событий базового класса в производных классах.</span><span class="sxs-lookup"><span data-stu-id="9420d-117">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="9420d-118">По соглашению имя метода должно начинаться с «On» и идти с именем события.</span><span class="sxs-lookup"><span data-stu-id="9420d-118">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>  
  
 <span data-ttu-id="9420d-119">Производный класс можно выбрать не вызвать базовую реализацию метода в его переопределения.</span><span class="sxs-lookup"><span data-stu-id="9420d-119">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="9420d-120">Быть готовым к этому, не включая какой-либо обработки, необходим для правильной работы базового класса в методе.</span><span class="sxs-lookup"><span data-stu-id="9420d-120">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>  
  
 <span data-ttu-id="9420d-121">**✓ СДЕЛАТЬ** принимать один параметр для защищенный метод, который вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="9420d-121">**✓ DO** take one parameter to the protected method that raises an event.</span></span>  
  
 <span data-ttu-id="9420d-122">Параметр должен иметь имя `e` и должны быть типизированы как класс аргументов события.</span><span class="sxs-lookup"><span data-stu-id="9420d-122">The parameter should be named `e` and should be typed as the event argument class.</span></span>  
  
 <span data-ttu-id="9420d-123">**X не** передает null в качестве отправителя при нестатические события.</span><span class="sxs-lookup"><span data-stu-id="9420d-123">**X DO NOT** pass null as the sender when raising a nonstatic event.</span></span>  
  
 <span data-ttu-id="9420d-124">**✓ СДЕЛАТЬ** передает null в качестве отправителя при статические события.</span><span class="sxs-lookup"><span data-stu-id="9420d-124">**✓ DO** pass null as the sender when raising a static event.</span></span>  
  
 <span data-ttu-id="9420d-125">**X не** передает null в качестве параметра данных события при возникновении события.</span><span class="sxs-lookup"><span data-stu-id="9420d-125">**X DO NOT** pass null as the event data parameter when raising an event.</span></span>  
  
 <span data-ttu-id="9420d-126">Необходимо передать `EventArgs.Empty` Если вы не хотите передавать все данные в метод обработки событий.</span><span class="sxs-lookup"><span data-stu-id="9420d-126">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="9420d-127">Разработчики предполагают, что этот параметр не должен иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="9420d-127">Developers expect this parameter not to be null.</span></span>  
  
 <span data-ttu-id="9420d-128">**✓ Попробуйте** вызов событий, которые можно отменить конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="9420d-128">**✓ CONSIDER** raising events that the end user can cancel.</span></span> <span data-ttu-id="9420d-129">Это относится только к событий.</span><span class="sxs-lookup"><span data-stu-id="9420d-129">This only applies to pre-events.</span></span>  
  
 <span data-ttu-id="9420d-130">Используйте <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> или его подкласс, в качестве аргумента события, чтобы разрешить конечным пользователям отмены события.</span><span class="sxs-lookup"><span data-stu-id="9420d-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>  
  
### <a name="custom-event-handler-design"></a><span data-ttu-id="9420d-131">Разработка настраиваемого обработчика событий</span><span class="sxs-lookup"><span data-stu-id="9420d-131">Custom Event Handler Design</span></span>  
 <span data-ttu-id="9420d-132">Существуют случаи, в котором `EventHandler<T>` не может использоваться, например, когда платформа должно работать в более ранних версиях среды CLR, который не поддерживает универсальные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="9420d-132">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="9420d-133">В таких случаях может потребоваться для проектирования и разработки делегата обработчика пользовательского события.</span><span class="sxs-lookup"><span data-stu-id="9420d-133">In such cases, you might need to design and develop a custom event handler delegate.</span></span>  
  
 <span data-ttu-id="9420d-134">**✓ СДЕЛАТЬ** использовать тип возвращаемого значения void для обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="9420d-134">**✓ DO** use a return type of void for event handlers.</span></span>  
  
 <span data-ttu-id="9420d-135">Обработчик событий может вызывать методы, возможно с несколькими объектами обработки нескольких событий.</span><span class="sxs-lookup"><span data-stu-id="9420d-135">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="9420d-136">Если допускается методы обработки событий для возврата значения, будет несколько значений для каждого вызова события.</span><span class="sxs-lookup"><span data-stu-id="9420d-136">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>  
  
 <span data-ttu-id="9420d-137">**СДЕЛАТЬ ✓** использовать `object` как тип первого аргумента обработчика событий и вызывает его `sender`.</span><span class="sxs-lookup"><span data-stu-id="9420d-137">**✓ DO** use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>  
  
 <span data-ttu-id="9420d-138">**СДЕЛАТЬ ✓** использовать <xref:System.EventArgs?displayProperty=nameWithType> или его подкласс в качестве типа второго аргумента обработчика событий и вызывает его `e`.</span><span class="sxs-lookup"><span data-stu-id="9420d-138">**✓ DO** use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>  
  
 <span data-ttu-id="9420d-139">**X не** иметь более двух параметров на обработчики событий.</span><span class="sxs-lookup"><span data-stu-id="9420d-139">**X DO NOT** have more than two parameters on event handlers.</span></span>  
  
 <span data-ttu-id="9420d-140">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="9420d-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9420d-141">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="9420d-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9420d-142">См. также</span><span class="sxs-lookup"><span data-stu-id="9420d-142">See Also</span></span>  
 [<span data-ttu-id="9420d-143">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="9420d-143">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="9420d-144">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="9420d-144">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
