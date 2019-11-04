---
title: Шаблоны слабых событий
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: c0bf92c9b6046d531e75771a9205e6dffe0fd367
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458484"
---
# <a name="weak-event-patterns"></a><span data-ttu-id="eb942-102">Шаблоны слабых событий</span><span class="sxs-lookup"><span data-stu-id="eb942-102">Weak Event Patterns</span></span>
<span data-ttu-id="eb942-103">В приложениях возможно, что обработчики, присоединенные к источникам событий, не будут уничтожены в координации с объектом прослушивателя, который присоединил обработчик к источнику.</span><span class="sxs-lookup"><span data-stu-id="eb942-103">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="eb942-104">Такая ситуация может привести к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="eb942-104">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="eb942-105">представляет шаблон проектирования, который можно использовать для решения этой проблемы, предоставляя выделенный класс диспетчера для конкретных событий и реализуя интерфейс в прослушивателях для этого события.</span><span class="sxs-lookup"><span data-stu-id="eb942-105">introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="eb942-106">Этот шаблон разработки известен как *шаблон слабых событий*.</span><span class="sxs-lookup"><span data-stu-id="eb942-106">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="eb942-107">Зачем реализовывать шаблон слабых событий?</span><span class="sxs-lookup"><span data-stu-id="eb942-107">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="eb942-108">Прослушивание событий может привести к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="eb942-108">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="eb942-109">Типичным приемом для прослушивания события является использование синтаксиса, зависящего от языка, который прикрепляет обработчик к событию в источнике.</span><span class="sxs-lookup"><span data-stu-id="eb942-109">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="eb942-110">Например, в C#используется следующий синтаксис: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span><span class="sxs-lookup"><span data-stu-id="eb942-110">For example, in C#, that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="eb942-111">Этот метод создает строгую ссылку из источника событий в прослушиватель событий.</span><span class="sxs-lookup"><span data-stu-id="eb942-111">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="eb942-112">Обычно присоединение обработчика событий для прослушивателя приводит к тому, что прослушиватель имеет время существования объекта, на которое влияет время существования объекта источника (если только обработчик событий не удаляется явным образом).</span><span class="sxs-lookup"><span data-stu-id="eb942-112">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="eb942-113">Но в некоторых случаях может потребоваться, чтобы время существования объекта прослушивателя управлялось другими факторами, например, если он принадлежит визуальному дереву приложения, а не времени существования источника.</span><span class="sxs-lookup"><span data-stu-id="eb942-113">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="eb942-114">Каждый раз, когда время существования исходного объекта выходит за пределы времени существования объекта прослушивателя, шаблон обычного события приводит к утечке памяти: прослушиватель поддерживается дольше, чем планировалось.</span><span class="sxs-lookup"><span data-stu-id="eb942-114">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="eb942-115">Шаблон слабых событий предназначен для решения этой проблемы утечки памяти.</span><span class="sxs-lookup"><span data-stu-id="eb942-115">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="eb942-116">Шаблон слабых событий можно использовать всякий раз, когда прослушивателю необходимо зарегистрироваться для события, но прослушиватель не знает, когда следует отменять регистрацию.</span><span class="sxs-lookup"><span data-stu-id="eb942-116">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="eb942-117">Шаблон слабых событий также можно использовать всякий раз, когда время существования объекта источника превышает полезное время существования объекта прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="eb942-117">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="eb942-118">(В этом случае *полезно* определить.) Шаблон слабых событий позволяет прослушивателю регистрироваться и принимать события, не влияя на характеристики времени существования объекта прослушивателя любым способом.</span><span class="sxs-lookup"><span data-stu-id="eb942-118">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="eb942-119">Фактически неявная ссылка из источника не определяет, подходит ли прослушиватель для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="eb942-119">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="eb942-120">Ссылка является слабой ссылкой, то есть наименованием шаблона слабых событий и связанных с ним API.</span><span class="sxs-lookup"><span data-stu-id="eb942-120">The reference is a weak reference, thus the naming of the weak event pattern and the related APIs.</span></span> <span data-ttu-id="eb942-121">Прослушиватель может быть собран или удален сборщиком мусора, и источник можно продолжить без удержания ссылок на Несобираемые обработчики на уже уничтоженный объект.</span><span class="sxs-lookup"><span data-stu-id="eb942-121">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="eb942-122">Кто должен реализовывать шаблон слабых событий?</span><span class="sxs-lookup"><span data-stu-id="eb942-122">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="eb942-123">Реализация шаблона слабых событий является наиболее интересной в основном для авторов элементов управления.</span><span class="sxs-lookup"><span data-stu-id="eb942-123">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="eb942-124">Как автор элемента управления, вы в основном отвечаете за поведение и включение элемента управления и влияние его на приложения, в которых он вставлен.</span><span class="sxs-lookup"><span data-stu-id="eb942-124">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="eb942-125">Это включает в себя поведение времени существования управляющего объекта, в частности, обработку описанной проблемы утечки памяти.</span><span class="sxs-lookup"><span data-stu-id="eb942-125">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="eb942-126">Некоторые сценарии изначально предоставляются для применения шаблона слабых событий.</span><span class="sxs-lookup"><span data-stu-id="eb942-126">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="eb942-127">Одним из таких сценариев является привязка данных.</span><span class="sxs-lookup"><span data-stu-id="eb942-127">One such scenario is data binding.</span></span> <span data-ttu-id="eb942-128">В привязке данных обычно исходный объект полностью независим от объекта listener, который является целевым объектом привязки.</span><span class="sxs-lookup"><span data-stu-id="eb942-128">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="eb942-129">Многие аспекты [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] привязки данных уже имеют шаблон слабых событий, применяемый в способе реализации событий.</span><span class="sxs-lookup"><span data-stu-id="eb942-129">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="eb942-130">Реализация шаблона слабых событий</span><span class="sxs-lookup"><span data-stu-id="eb942-130">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="eb942-131">Существует три способа реализации шаблона слабых событий.</span><span class="sxs-lookup"><span data-stu-id="eb942-131">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="eb942-132">В следующей таблице перечислены три подхода и приведены некоторые рекомендации по их использованию.</span><span class="sxs-lookup"><span data-stu-id="eb942-132">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="eb942-133">Подход</span><span class="sxs-lookup"><span data-stu-id="eb942-133">Approach</span></span>|<span data-ttu-id="eb942-134">Когда следует реализовывать</span><span class="sxs-lookup"><span data-stu-id="eb942-134">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="eb942-135">Использование существующего класса диспетчера слабых событий</span><span class="sxs-lookup"><span data-stu-id="eb942-135">Use an existing weak event manager class</span></span>|<span data-ttu-id="eb942-136">Если событие, на которое вы хотите подписываться, имеет соответствующую <xref:System.Windows.WeakEventManager>, используйте существующий диспетчер слабых событий.</span><span class="sxs-lookup"><span data-stu-id="eb942-136">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="eb942-137">Список слабых диспетчеров событий, входящих в состав WPF, см. в разделе Иерархия наследования в классе <xref:System.Windows.WeakEventManager>.</span><span class="sxs-lookup"><span data-stu-id="eb942-137">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="eb942-138">Поскольку входящие диспетчеры событий ограничены, вам, вероятно, потребуется выбрать один из других подходов.</span><span class="sxs-lookup"><span data-stu-id="eb942-138">Because the included weak event managers are limited, you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="eb942-139">Использование универсального класса диспетчера слабых событий</span><span class="sxs-lookup"><span data-stu-id="eb942-139">Use a generic weak event manager class</span></span>|<span data-ttu-id="eb942-140">Используйте универсальный <xref:System.Windows.WeakEventManager%602> если имеющийся <xref:System.Windows.WeakEventManager> недоступен, вы хотите легко реализовать и не беспокоиться об эффективности.</span><span class="sxs-lookup"><span data-stu-id="eb942-140">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="eb942-141">Универсальный <xref:System.Windows.WeakEventManager%602> менее эффективен, чем существующий или пользовательский диспетчер слабых событий.</span><span class="sxs-lookup"><span data-stu-id="eb942-141">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="eb942-142">Например, универсальный класс делает больше отражения для обнаружения события в заданном имени события.</span><span class="sxs-lookup"><span data-stu-id="eb942-142">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="eb942-143">Кроме того, код для регистрации события с помощью универсального <xref:System.Windows.WeakEventManager%602> является более подробным, чем использование существующего или пользовательского <xref:System.Windows.WeakEventManager>.</span><span class="sxs-lookup"><span data-stu-id="eb942-143">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="eb942-144">Создание пользовательского класса диспетчера слабых событий</span><span class="sxs-lookup"><span data-stu-id="eb942-144">Create a custom weak event manager class</span></span>|<span data-ttu-id="eb942-145">Создайте настраиваемый <xref:System.Windows.WeakEventManager>, если существующий <xref:System.Windows.WeakEventManager> недоступен и требуется лучшая эффективность.</span><span class="sxs-lookup"><span data-stu-id="eb942-145">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="eb942-146">Использование настраиваемых <xref:System.Windows.WeakEventManager> для подписки на событие будет более эффективным, но в начале придется писать больше кода.</span><span class="sxs-lookup"><span data-stu-id="eb942-146">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
|<span data-ttu-id="eb942-147">Использование стороннего диспетчера слабых событий</span><span class="sxs-lookup"><span data-stu-id="eb942-147">Use a third-party weak event manager</span></span>|<span data-ttu-id="eb942-148">NuGet имеет [несколько диспетчеров слабых событий](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) , а многие платформы WPF также поддерживают шаблон (например, см. [документацию по Prism по слабо связанной подписке на события](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)).</span><span class="sxs-lookup"><span data-stu-id="eb942-148">NuGet has [several weak event managers](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) and many WPF frameworks also support the pattern (for instance, see [Prism's documentation on loosely coupled event subscription](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)).</span></span>|

 <span data-ttu-id="eb942-149">В следующих разделах описывается реализация шаблона слабых событий.</span><span class="sxs-lookup"><span data-stu-id="eb942-149">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="eb942-150">В рамках этого обсуждения событие, для которого подписывается, имеет следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="eb942-150">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
- <span data-ttu-id="eb942-151">Имя события — `SomeEvent`.</span><span class="sxs-lookup"><span data-stu-id="eb942-151">The event name is `SomeEvent`.</span></span>  
  
- <span data-ttu-id="eb942-152">Событие вызывается классом `EventSource`.</span><span class="sxs-lookup"><span data-stu-id="eb942-152">The event is raised by the `EventSource` class.</span></span>  
  
- <span data-ttu-id="eb942-153">Обработчик событий имеет тип: `SomeEventEventHandler` (или `EventHandler<SomeEventEventArgs>`).</span><span class="sxs-lookup"><span data-stu-id="eb942-153">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
- <span data-ttu-id="eb942-154">Событие передает параметр типа `SomeEventEventArgs` обработчикам событий.</span><span class="sxs-lookup"><span data-stu-id="eb942-154">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="eb942-155">Использование существующего класса диспетчера слабых событий</span><span class="sxs-lookup"><span data-stu-id="eb942-155">Using an Existing Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="eb942-156">Найдите существующий диспетчер слабых событий.</span><span class="sxs-lookup"><span data-stu-id="eb942-156">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="eb942-157">Список слабых диспетчеров событий, входящих в состав WPF, см. в разделе Иерархия наследования в классе <xref:System.Windows.WeakEventManager>.</span><span class="sxs-lookup"><span data-stu-id="eb942-157">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2. <span data-ttu-id="eb942-158">Используйте новый диспетчер слабых событий вместо обычного подключения к событию.</span><span class="sxs-lookup"><span data-stu-id="eb942-158">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="eb942-159">Например, если в коде для подписки на событие используется следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="eb942-159">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="eb942-160">Измените его на следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="eb942-160">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="eb942-161">Аналогично, если в коде используется следующий шаблон для отмены подписки на событие:</span><span class="sxs-lookup"><span data-stu-id="eb942-161">Similarly, if your code uses the following pattern to unsubscribe from an event:</span></span>  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="eb942-162">Измените его на следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="eb942-162">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="eb942-163">Использование универсального класса диспетчера слабых событий</span><span class="sxs-lookup"><span data-stu-id="eb942-163">Using the Generic Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="eb942-164">Вместо обычного подключения к событию используйте универсальный класс <xref:System.Windows.WeakEventManager%602>.</span><span class="sxs-lookup"><span data-stu-id="eb942-164">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="eb942-165">При использовании <xref:System.Windows.WeakEventManager%602> для регистрации прослушивателей событий необходимо указать источник события и тип <xref:System.EventArgs> в качестве параметров типа для класса и вызвать <xref:System.Windows.WeakEventManager%602.AddHandler%2A>, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="eb942-165">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```csharp  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="eb942-166">Создание пользовательского класса диспетчера слабых событий</span><span class="sxs-lookup"><span data-stu-id="eb942-166">Creating a Custom Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="eb942-167">Скопируйте следующий шаблон класса в проект.</span><span class="sxs-lookup"><span data-stu-id="eb942-167">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="eb942-168">Этот класс наследуется от класса <xref:System.Windows.WeakEventManager>.</span><span class="sxs-lookup"><span data-stu-id="eb942-168">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. <span data-ttu-id="eb942-169">Замените имя `SomeEventWeakEventManager` именем.</span><span class="sxs-lookup"><span data-stu-id="eb942-169">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3. <span data-ttu-id="eb942-170">Замените три имени, описанные выше, соответствующими именами для события.</span><span class="sxs-lookup"><span data-stu-id="eb942-170">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="eb942-171">(`SomeEvent`, `EventSource`и `SomeEventEventArgs`)</span><span class="sxs-lookup"><span data-stu-id="eb942-171">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4. <span data-ttu-id="eb942-172">Задайте для свойства Visibility (открытый/внутренний/частный) класс диспетчера событий ту же видимость, что и управляемое им событие.</span><span class="sxs-lookup"><span data-stu-id="eb942-172">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5. <span data-ttu-id="eb942-173">Используйте новый диспетчер слабых событий вместо обычного подключения к событию.</span><span class="sxs-lookup"><span data-stu-id="eb942-173">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="eb942-174">Например, если в коде для подписки на событие используется следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="eb942-174">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="eb942-175">Измените его на следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="eb942-175">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="eb942-176">Аналогично, если в коде используется следующий шаблон для отмены подписки на событие:</span><span class="sxs-lookup"><span data-stu-id="eb942-176">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="eb942-177">Измените его на следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="eb942-177">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="eb942-178">См. также</span><span class="sxs-lookup"><span data-stu-id="eb942-178">See also</span></span>

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [<span data-ttu-id="eb942-179">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="eb942-179">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="eb942-180">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="eb942-180">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
