---
title: Шаблоны слабых событий
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: 0c5bae64fbbeddedd905e5df0b5789542e29f2f1
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833932"
---
# <a name="weak-event-patterns"></a><span data-ttu-id="91b5e-102">Шаблоны слабых событий</span><span class="sxs-lookup"><span data-stu-id="91b5e-102">Weak Event Patterns</span></span>
<span data-ttu-id="91b5e-103">В приложениях возможно, что обработчики, присоединенные к источникам событий, не будут уничтожены в соответствии с объектом прослушиватель, который присоединил обработчик к источнику.</span><span class="sxs-lookup"><span data-stu-id="91b5e-103">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="91b5e-104">Это может привести к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="91b5e-104">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="91b5e-105">представляет шаблон, который может использоваться для решения этой проблемы путем предоставления выделенного класса диспетчера для конкретных событий и реализации интерфейса прослушивателей для данного события.</span><span class="sxs-lookup"><span data-stu-id="91b5e-105">introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="91b5e-106">Этот шаблон разработки называется *шаблоне слабых событий*.</span><span class="sxs-lookup"><span data-stu-id="91b5e-106">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="91b5e-107">Почему реализация шаблона слабых событий?</span><span class="sxs-lookup"><span data-stu-id="91b5e-107">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="91b5e-108">Прослушивание событий может привести к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="91b5e-108">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="91b5e-109">Обычным методом для прослушивания событий — использовать синтаксис конкретного языка, который присоединяет обработчик к событию на источнике.</span><span class="sxs-lookup"><span data-stu-id="91b5e-109">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="91b5e-110">Например, в C#, что синтаксис является: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span><span class="sxs-lookup"><span data-stu-id="91b5e-110">For example, in C#, that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="91b5e-111">Этот метод создает строгую ссылку из источника события для прослушивателя событий.</span><span class="sxs-lookup"><span data-stu-id="91b5e-111">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="91b5e-112">Обычно присоединение обработчика события для прослушивателя вызывает прослушиватель для времени жизни объекта, зависит от времени существования объекта источника (если не будет явно удален обработчик событий).</span><span class="sxs-lookup"><span data-stu-id="91b5e-112">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="91b5e-113">Но в некоторых случаях вы можете время жизни объекта прослушивателя управляются другими факторами, например, принадлежит ли он в настоящее время к визуальному дереву приложения, а не по времени существования источника.</span><span class="sxs-lookup"><span data-stu-id="91b5e-113">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="91b5e-114">Каждый раз, когда время жизни объекта источника выходит за пределы время жизни объекта-прослушивателя, обычный шаблон события приводит к утечке памяти: прослушиватель хранится дольше, чем планировалось.</span><span class="sxs-lookup"><span data-stu-id="91b5e-114">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="91b5e-115">Шаблон слабых событий предназначен для решения проблемы утечки памяти.</span><span class="sxs-lookup"><span data-stu-id="91b5e-115">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="91b5e-116">Шаблон слабых событий можно использовать всякий раз, когда прослушиватель должен зарегистрироваться для получения события, но прослушиватель не знает, явно отмены регистрации.</span><span class="sxs-lookup"><span data-stu-id="91b5e-116">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="91b5e-117">Шаблон слабых событий можно также использоваться всякий раз, когда время жизни объекта-источника превышает время существования полезных объект прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="91b5e-117">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="91b5e-118">(В этом случае *полезные* определяется пользователем.) Шаблон слабых событий позволяет прослушивателя, чтобы зарегистрироваться и получить событие, не затрагивая характеристики времени жизни объекта прослушивателя любым способом.</span><span class="sxs-lookup"><span data-stu-id="91b5e-118">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="91b5e-119">По сути неявная ссылка из источника не определяет, является ли прослушиватель под сбор мусора.</span><span class="sxs-lookup"><span data-stu-id="91b5e-119">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="91b5e-120">Ссылка является слабой ссылки, таким образом система именования шаблона слабых событий и в сопутствующих [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91b5e-120">The reference is a weak reference, thus the naming of the weak event pattern and the related [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].</span></span> <span data-ttu-id="91b5e-121">Прослушиватель может быть собран как мусор или в противном случае уничтожения, а источник может продолжить без сохранения только что уничтоженный обработчика ссылок на объект.</span><span class="sxs-lookup"><span data-stu-id="91b5e-121">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="91b5e-122">Кто должен реализовывать шаблон слабых событий?</span><span class="sxs-lookup"><span data-stu-id="91b5e-122">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="91b5e-123">Реализация шаблона слабых событий представляет интерес в первую очередь для разработчиков элементов управления.</span><span class="sxs-lookup"><span data-stu-id="91b5e-123">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="91b5e-124">Как разработчик элемента управления — во многом за поведение и включения элемента управления и его влияние на приложения, в которых она вставляется.</span><span class="sxs-lookup"><span data-stu-id="91b5e-124">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="91b5e-125">Это включает и поведения времени существования объекта элемента управления, в частности, обработка описанной проблемы утечки памяти.</span><span class="sxs-lookup"><span data-stu-id="91b5e-125">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="91b5e-126">Некоторые сценарии изначально подходят для применения этого шаблона слабых событий.</span><span class="sxs-lookup"><span data-stu-id="91b5e-126">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="91b5e-127">Одним из таких сценариев является привязка данных.</span><span class="sxs-lookup"><span data-stu-id="91b5e-127">One such scenario is data binding.</span></span> <span data-ttu-id="91b5e-128">В привязке данных, довольно часто для исходного объекта, была полностью независима от объект-прослушиватель, который является целевым объектом привязки.</span><span class="sxs-lookup"><span data-stu-id="91b5e-128">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="91b5e-129">Многие аспекты [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] привязки данных уже имеют шаблон слабых событий, примененный в порядок реализации событий.</span><span class="sxs-lookup"><span data-stu-id="91b5e-129">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="91b5e-130">Реализация шаблона слабых событий</span><span class="sxs-lookup"><span data-stu-id="91b5e-130">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="91b5e-131">Реализация шаблона слабых событий тремя способами.</span><span class="sxs-lookup"><span data-stu-id="91b5e-131">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="91b5e-132">В следующей таблице перечислены три подхода и приводятся рекомендации по при их использованию.</span><span class="sxs-lookup"><span data-stu-id="91b5e-132">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="91b5e-133">Подход</span><span class="sxs-lookup"><span data-stu-id="91b5e-133">Approach</span></span>|<span data-ttu-id="91b5e-134">Когда следует реализовать</span><span class="sxs-lookup"><span data-stu-id="91b5e-134">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="91b5e-135">Использовать существующий класс manager слабых событий</span><span class="sxs-lookup"><span data-stu-id="91b5e-135">Use an existing weak event manager class</span></span>|<span data-ttu-id="91b5e-136">Если вы хотите подписаться на событие имеет соответствующий <xref:System.Windows.WeakEventManager>, с помощью существующего диспетчера слабых событий.</span><span class="sxs-lookup"><span data-stu-id="91b5e-136">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="91b5e-137">Список диспетчеров слабых событий, которые входят в состав WPF, см. в разделе иерархии наследования в <xref:System.Windows.WeakEventManager> класса.</span><span class="sxs-lookup"><span data-stu-id="91b5e-137">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="91b5e-138">Так, как диспетчеры включены слабых событий ограничены, возможно, необходимо будет выбрать один из других подходов.</span><span class="sxs-lookup"><span data-stu-id="91b5e-138">Because the included weak event managers are limited, you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="91b5e-139">Использовать класс manager универсального слабых событий</span><span class="sxs-lookup"><span data-stu-id="91b5e-139">Use a generic weak event manager class</span></span>|<span data-ttu-id="91b5e-140">Используйте универсальный <xref:System.Windows.WeakEventManager%602> существующей <xref:System.Windows.WeakEventManager> не доступен, требуется, чтобы легко реализовать, и вы не занимается увеличивает производительность работы.</span><span class="sxs-lookup"><span data-stu-id="91b5e-140">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="91b5e-141">Универсальный <xref:System.Windows.WeakEventManager%602> является менее эффективным, чем диспетчер слабых событий существующих или пользовательских.</span><span class="sxs-lookup"><span data-stu-id="91b5e-141">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="91b5e-142">Например универсальный класс выполняет дополнительные отражение для обнаружения событий, имени события.</span><span class="sxs-lookup"><span data-stu-id="91b5e-142">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="91b5e-143">Кроме того, код для регистрации событий с помощью универсального <xref:System.Windows.WeakEventManager%602> является более подробным по сравнению с помощью существующего или пользовательских <xref:System.Windows.WeakEventManager>.</span><span class="sxs-lookup"><span data-stu-id="91b5e-143">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="91b5e-144">Создайте класс manager пользовательских слабых событий</span><span class="sxs-lookup"><span data-stu-id="91b5e-144">Create a custom weak event manager class</span></span>|<span data-ttu-id="91b5e-145">Создание пользовательского <xref:System.Windows.WeakEventManager> существующей <xref:System.Windows.WeakEventManager> недоступен и нужно, чтобы повышения эффективности работы.</span><span class="sxs-lookup"><span data-stu-id="91b5e-145">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="91b5e-146">С помощью пользовательского <xref:System.Windows.WeakEventManager> подписаться на событие будет более эффективной, но вы затраты на создавать больше кода в начале.</span><span class="sxs-lookup"><span data-stu-id="91b5e-146">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
|<span data-ttu-id="91b5e-147">С помощью диспетчера сторонних слабых событий</span><span class="sxs-lookup"><span data-stu-id="91b5e-147">Use a third-party weak event manager</span></span>|<span data-ttu-id="91b5e-148">NuGet имеет [несколько диспетчеров слабых событий](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) и многие платформы WPF также поддерживать шаблон (например, см. в разделе [документации призмы подписка слабо связанных событий](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)).</span><span class="sxs-lookup"><span data-stu-id="91b5e-148">NuGet has [several weak event managers](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) and many WPF frameworks also support the pattern (for instance, see [Prism's documentation on loosely coupled event subscription](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)).</span></span>|

 <span data-ttu-id="91b5e-149">В следующих разделах рассматривается реализация шаблона слабых событий.</span><span class="sxs-lookup"><span data-stu-id="91b5e-149">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="91b5e-150">Для целей данного обсуждения Чтобы подписаться на событие имеет следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="91b5e-150">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
- <span data-ttu-id="91b5e-151">Имя события находится `SomeEvent`.</span><span class="sxs-lookup"><span data-stu-id="91b5e-151">The event name is `SomeEvent`.</span></span>  
  
- <span data-ttu-id="91b5e-152">Событие `EventSource` класс.</span><span class="sxs-lookup"><span data-stu-id="91b5e-152">The event is raised by the `EventSource` class.</span></span>  
  
- <span data-ttu-id="91b5e-153">Обработчик событий имеет тип: `SomeEventEventHandler` (или `EventHandler<SomeEventEventArgs>`).</span><span class="sxs-lookup"><span data-stu-id="91b5e-153">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
- <span data-ttu-id="91b5e-154">Событие передает параметр типа `SomeEventEventArgs` обработчикам событий.</span><span class="sxs-lookup"><span data-stu-id="91b5e-154">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="91b5e-155">С помощью существующего класса слабого диспетчера событий</span><span class="sxs-lookup"><span data-stu-id="91b5e-155">Using an Existing Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="91b5e-156">Найдите событие слабые manager.</span><span class="sxs-lookup"><span data-stu-id="91b5e-156">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="91b5e-157">Список диспетчеров слабых событий, которые входят в состав WPF, см. в разделе иерархии наследования в <xref:System.Windows.WeakEventManager> класса.</span><span class="sxs-lookup"><span data-stu-id="91b5e-157">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2. <span data-ttu-id="91b5e-158">Использование нового диспетчера слабых событий вместо обычной привязке события.</span><span class="sxs-lookup"><span data-stu-id="91b5e-158">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="91b5e-159">Например, если ваш код использует следующий шаблон для подписки на событие:</span><span class="sxs-lookup"><span data-stu-id="91b5e-159">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="91b5e-160">Измените его на следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="91b5e-160">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="91b5e-161">Аналогично Если ваш код использует следующий шаблон для отмены подписки на событие:</span><span class="sxs-lookup"><span data-stu-id="91b5e-161">Similarly, if your code uses the following pattern to unsubscribe from an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="91b5e-162">Измените его на следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="91b5e-162">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="91b5e-163">Использование универсального класса слабого диспетчера событий</span><span class="sxs-lookup"><span data-stu-id="91b5e-163">Using the Generic Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="91b5e-164">Использование универсального <xref:System.Windows.WeakEventManager%602> класса вместо обычной привязке события.</span><span class="sxs-lookup"><span data-stu-id="91b5e-164">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="91b5e-165">При использовании <xref:System.Windows.WeakEventManager%602> Чтобы зарегистрировать прослушивателей событий, необходимо указать источник события и <xref:System.EventArgs> тип как параметры типа для класса и вызове <xref:System.Windows.WeakEventManager%602.AddHandler%2A> как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="91b5e-165">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="91b5e-166">Создание пользовательского класса слабого диспетчера событий</span><span class="sxs-lookup"><span data-stu-id="91b5e-166">Creating a Custom Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="91b5e-167">Скопируйте следующий шаблон класса в проект.</span><span class="sxs-lookup"><span data-stu-id="91b5e-167">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="91b5e-168">Этот класс наследует от <xref:System.Windows.WeakEventManager> класса.</span><span class="sxs-lookup"><span data-stu-id="91b5e-168">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. <span data-ttu-id="91b5e-169">Замените `SomeEventWeakEventManager` с собственным именем.</span><span class="sxs-lookup"><span data-stu-id="91b5e-169">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3. <span data-ttu-id="91b5e-170">Замените имена трех, описанные ранее, с соответствующими именами для события.</span><span class="sxs-lookup"><span data-stu-id="91b5e-170">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="91b5e-171">(`SomeEvent`, `EventSource`, и `SomeEventEventArgs`)</span><span class="sxs-lookup"><span data-stu-id="91b5e-171">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4. <span data-ttu-id="91b5e-172">Настроить видимость (открытый / внутренней / закрытый) для класса manager слабых событий в ту же видимость, что событие, которыми она управляет.</span><span class="sxs-lookup"><span data-stu-id="91b5e-172">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5. <span data-ttu-id="91b5e-173">Использование нового диспетчера слабых событий вместо обычной привязке события.</span><span class="sxs-lookup"><span data-stu-id="91b5e-173">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="91b5e-174">Например, если ваш код использует следующий шаблон для подписки на событие:</span><span class="sxs-lookup"><span data-stu-id="91b5e-174">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="91b5e-175">Измените его на следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="91b5e-175">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="91b5e-176">Аналогично Если ваш код использует следующий шаблон для отмены подписки на события:</span><span class="sxs-lookup"><span data-stu-id="91b5e-176">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="91b5e-177">Измените его на следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="91b5e-177">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="91b5e-178">См. также</span><span class="sxs-lookup"><span data-stu-id="91b5e-178">See also</span></span>

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [<span data-ttu-id="91b5e-179">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="91b5e-179">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="91b5e-180">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="91b5e-180">Data Binding Overview</span></span>](../data/data-binding-overview.md)
