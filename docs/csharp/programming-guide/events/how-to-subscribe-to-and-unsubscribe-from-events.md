---
title: "Практическое руководство. Подписка и отмена подписки на события (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- event handlers [C#], creating
- Code Editor, event handlers
- events [C#], creating using the IDE
ms.assetid: 6319f39f-282c-4173-8a62-6c4657cf51cd
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d444a2efe03ec127ff88236deadab719d0d64259
ms.contentlocale: ru-ru
ms.lasthandoff: 09/08/2017

---
# <a name="how-to-subscribe-to-and-unsubscribe-from-events-c-programming-guide"></a><span data-ttu-id="1d750-102">Практическое руководство. Подписка и отмена подписки на события (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="1d750-102">How to: Subscribe to and Unsubscribe from Events (C# Programming Guide)</span></span>
<span data-ttu-id="1d750-103">Необходимость подписки на событие, опубликованное другим классом, может возникнуть, когда требуется написать пользовательский код, вызываемый при инициировании такого события.</span><span class="sxs-lookup"><span data-stu-id="1d750-103">You subscribe to an event that is published by another class when you want to write custom code that is called when that event is raised.</span></span> <span data-ttu-id="1d750-104">Например, можно подписаться на событие кнопки `click`, чтобы приложение выполняло некоторое действие при нажатии пользователем кнопки.</span><span class="sxs-lookup"><span data-stu-id="1d750-104">For example, you might subscribe to a button's `click` event in order to make your application do something useful when the user clicks the button.</span></span>  
  
### <a name="to-subscribe-to-events-by-using-the-visual-studio-ide"></a><span data-ttu-id="1d750-105">Подписка на события в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1d750-105">To subscribe to events by using the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="1d750-106">Если окно **Свойства** закрыто, в представлении **Конструктор** щелкните правой кнопкой мыши форму или элемент управления, для которого требуется создать обработчик событий, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1d750-106">If you cannot see the **Properties** window, in **Design** view, right-click the form or control for which you want to create an event handler, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="1d750-107">Вверху окна **Свойства** щелкните значок **События**.</span><span class="sxs-lookup"><span data-stu-id="1d750-107">On top of the **Properties** window, click the **Events** icon.</span></span>  
  
3.  <span data-ttu-id="1d750-108">Дважды щелкните событие, которое требуется создать, например событие `Load`.</span><span class="sxs-lookup"><span data-stu-id="1d750-108">Double-click the event that you want to create, for example the `Load` event.</span></span>  
  
     [!INCLUDE[csprcs](~/includes/csprcs-md.md)]<span data-ttu-id="1d750-109"> создаст пустой метод обработчика событий и добавит его в код.</span><span class="sxs-lookup"><span data-stu-id="1d750-109"> creates an empty event handler method and adds it to your code.</span></span> <span data-ttu-id="1d750-110">Код можно также добавить вручную в представлении **Код**.</span><span class="sxs-lookup"><span data-stu-id="1d750-110">Alternatively you can add the code manually in **Code** view.</span></span> <span data-ttu-id="1d750-111">Например, приведенные ниже строки кода объявляют метод обработчика событий, который будет выполнен при вызове классом `Form` события `Load`.</span><span class="sxs-lookup"><span data-stu-id="1d750-111">For example, the following lines of code declare an event handler method that will be called when the `Form` class raises the `Load` event.</span></span>  
  
     <span data-ttu-id="1d750-112">[!code-cs[csProgGuideEvents#11](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-subscribe-to-and-unsubscribe-from-events_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1d750-112">[!code-cs[csProgGuideEvents#11](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-subscribe-to-and-unsubscribe-from-events_1.cs)]</span></span>  
  
     <span data-ttu-id="1d750-113">Строка кода, требуемая для подписки на событие, также создается автоматически в методе `InitializeComponent` в файле Form1.Designer.cs проекта.</span><span class="sxs-lookup"><span data-stu-id="1d750-113">The line of code that is required to subscribe to the event is also automatically generated in the `InitializeComponent` method in the Form1.Designer.cs file in your project.</span></span> <span data-ttu-id="1d750-114">Она имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="1d750-114">It resembles this:</span></span>  
  
    ```  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
### <a name="to-subscribe-to-events-programmatically"></a><span data-ttu-id="1d750-115">Подписка на события программными средствами</span><span class="sxs-lookup"><span data-stu-id="1d750-115">To subscribe to events programmatically</span></span>  
  
1.  <span data-ttu-id="1d750-116">Определите метод обработчика событий, сигнатура которого соответствует сигнатуре делегата для события.</span><span class="sxs-lookup"><span data-stu-id="1d750-116">Define an event handler method whose signature matches the delegate signature for the event.</span></span> <span data-ttu-id="1d750-117">Например, если событие основано на типе делегата <xref:System.EventHandler>, то следующий код представляет заглушку метода:</span><span class="sxs-lookup"><span data-stu-id="1d750-117">For example, if the event is based on the <xref:System.EventHandler> delegate type, the following code represents the method stub:</span></span>  
  
    ```  
    void HandleCustomEvent(object sender, CustomEventArgs a)  
    {  
       // Do something useful here.  
    }  
    ```  
  
2.  <span data-ttu-id="1d750-118">Чтобы присоединить обработчик событий к событию, используйте оператор присваивания сложения (`+=`).</span><span class="sxs-lookup"><span data-stu-id="1d750-118">Use the addition assignment operator (`+=`) to attach your event handler to the event.</span></span> <span data-ttu-id="1d750-119">В приведенном ниже примере предположим, что объект с именем `publisher` имеет событие с именем `RaiseCustomEvent`.</span><span class="sxs-lookup"><span data-stu-id="1d750-119">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent`.</span></span> <span data-ttu-id="1d750-120">Обратите внимание на то, что классу подписчика требуется ссылка на класс издателя, чтобы подписаться на его события.</span><span class="sxs-lookup"><span data-stu-id="1d750-120">Note that the subscriber class needs a reference to the publisher class in order to subscribe to its events.</span></span>  
  
    ```  
    publisher.RaiseCustomEvent += HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="1d750-121">Обратите внимание, что приведенный выше синтаксис появился только в C# 2.0.</span><span class="sxs-lookup"><span data-stu-id="1d750-121">Note that the previous syntax is new in C# 2.0.</span></span> <span data-ttu-id="1d750-122">Он в точности соответствует синтаксису C# 1.0, в котором с помощью ключевого слова `new` должен быть явно создан инкапсулирующий делегат.</span><span class="sxs-lookup"><span data-stu-id="1d750-122">It is exactly equivalent to the C# 1.0 syntax in which the encapsulating delegate must be explicitly created by using the `new` keyword:</span></span>  
  
    ```  
    publisher.RaiseCustomEvent += new CustomEventHandler(HandleCustomEvent);  
    ```  
  
     <span data-ttu-id="1d750-123">Для добавления обработчика событий можно также использовать лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="1d750-123">An event handler can also be added by using a lambda expression:</span></span>  
  
    ```  
    public Form1()  
    {  
        InitializeComponent();  
        // Use a lambda expression to define an event handler.  
        this.Click += (s,e) => { MessageBox.Show(  
           ((MouseEventArgs)e).Location.ToString());};  
    }  
    ```  
  
     <span data-ttu-id="1d750-124">Дополнительные сведения см. в разделе [Практическое руководство. Использование лямбда-выражений вне LINQ](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-outside-linq.md).</span><span class="sxs-lookup"><span data-stu-id="1d750-124">For more information, see [How to: Use Lambda Expressions Outside LINQ](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-outside-linq.md).</span></span>  
  
### <a name="to-subscribe-to-events-by-using-an-anonymous-method"></a><span data-ttu-id="1d750-125">Подписка на события с помощью анонимного метода</span><span class="sxs-lookup"><span data-stu-id="1d750-125">To subscribe to events by using an anonymous method</span></span>  
  
-   <span data-ttu-id="1d750-126">Если не нужно будет позже отменять подписку на событие, можно использовать оператор присваивания сложения (`+=`) для прикрепления к событию анонимного метода.</span><span class="sxs-lookup"><span data-stu-id="1d750-126">If you will not have to unsubscribe to an event later, you can use the addition assignment operator (`+=`) to attach an anonymous method to the event.</span></span> <span data-ttu-id="1d750-127">В следующем примере предположим, что объект с именем `publisher` имеет событие с именем `RaiseCustomEvent` и что класс `CustomEventArgs` также был определен и содержит некие относящиеся к событию сведения.</span><span class="sxs-lookup"><span data-stu-id="1d750-127">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent` and that a `CustomEventArgs` class has also been defined to carry some kind of specialized event information.</span></span> <span data-ttu-id="1d750-128">Обратите внимание на то, что классу подписчика требуется ссылка на `publisher`, чтобы подписаться на его события.</span><span class="sxs-lookup"><span data-stu-id="1d750-128">Note that the subscriber class needs a reference to `publisher` in order to subscribe to its events.</span></span>  
  
    ```  
    publisher.RaiseCustomEvent += delegate(object o, CustomEventArgs e)  
    {  
      string s = o.ToString() + " " + e.ToString();  
      Console.WriteLine(s);  
    };  
    ```  
  
     <span data-ttu-id="1d750-129">Важно отметить, что отменить подписку на событие не так просто, если для подписки на него использовалась анонимная функция.</span><span class="sxs-lookup"><span data-stu-id="1d750-129">It is important to notice that you cannot easily unsubscribe from an event if you used an anonymous function to subscribe to it.</span></span> <span data-ttu-id="1d750-130">Чтобы отменить подписку в этом случае, необходимо вернуться к коду, в котором была выполнена подписка на событие, сохранить анонимный метод в переменной делегата, а затем добавить делегат к событию.</span><span class="sxs-lookup"><span data-stu-id="1d750-130">To unsubscribe in this scenario, it is necessary to go back to the code where you subscribe to the event, store the anonymous method in a delegate variable, and then add the delegate to the event.</span></span> <span data-ttu-id="1d750-131">Как правило, мы рекомендуем не использовать анонимных функций для подписки на события, если предполагается, что в будущем будет нужно отменять подписку на событие.</span><span class="sxs-lookup"><span data-stu-id="1d750-131">In general, we recommend that you do not use anonymous functions to subscribe to events if you will have to unsubscribe from the event at some later point in your code.</span></span> <span data-ttu-id="1d750-132">Дополнительные сведения об анонимных функциях см. в разделе [Анонимные функции](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="1d750-132">For more information about anonymous functions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="unsubscribing"></a><span data-ttu-id="1d750-133">Отмена подписки</span><span class="sxs-lookup"><span data-stu-id="1d750-133">Unsubscribing</span></span>  
 <span data-ttu-id="1d750-134">Чтобы предотвратить вызов обработчика событий при инициировании события, подписку на событие необходимо отменить.</span><span class="sxs-lookup"><span data-stu-id="1d750-134">To prevent your event handler from being invoked when the event is raised, unsubscribe from the event.</span></span> <span data-ttu-id="1d750-135">Во избежание утечки ресурсов отменять подписку на события следует до удаления объекта подписчика.</span><span class="sxs-lookup"><span data-stu-id="1d750-135">In order to prevent resource leaks, you should unsubscribe from events before you dispose of a subscriber object.</span></span> <span data-ttu-id="1d750-136">До тех пор пока подписка на событие не отменена, делегат многоадресной рассылки, лежащий в основе события в публикующем объекте, будет ссылаться на делегат, инкапсулирующий обработчик событий подписчика.</span><span class="sxs-lookup"><span data-stu-id="1d750-136">Until you unsubscribe from an event, the multicast delegate that underlies the event in the publishing object has a reference to the delegate that encapsulates the subscriber's event handler.</span></span> <span data-ttu-id="1d750-137">Если ссылка присутствует в публикующем объекте, объект подписчика не будет удален при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="1d750-137">As long as the publishing object holds that reference, garbage collection will not delete your subscriber object.</span></span>  
  
#### <a name="to-unsubscribe-from-an-event"></a><span data-ttu-id="1d750-138">Отмена подписки на событие</span><span class="sxs-lookup"><span data-stu-id="1d750-138">To unsubscribe from an event</span></span>  
  
-   <span data-ttu-id="1d750-139">Чтобы отменить подписку на событие, воспользуйтесь оператором присваивания вычитания (`-=`).</span><span class="sxs-lookup"><span data-stu-id="1d750-139">Use the subtraction assignment operator (`-=`) to unsubscribe from an event:</span></span>  
  
    ```  
    publisher.RaiseCustomEvent -= HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="1d750-140">Если подписка на событие отменена для всех подписчиков, экземпляр события в классе издателя получает значение `null`.</span><span class="sxs-lookup"><span data-stu-id="1d750-140">When all subscribers have unsubscribed from an event, the event instance in the publisher class is set to `null`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d750-141">См. также</span><span class="sxs-lookup"><span data-stu-id="1d750-141">See Also</span></span>  
 <span data-ttu-id="1d750-142">[События](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="1d750-142">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 <span data-ttu-id="1d750-143">[event](../../../csharp/language-reference/keywords/event.md) </span><span class="sxs-lookup"><span data-stu-id="1d750-143">[event](../../../csharp/language-reference/keywords/event.md) </span></span>  
 <span data-ttu-id="1d750-144">[Практическое руководство. Публикация событий, соответствующих рекомендациям для .NET Framework](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md) </span><span class="sxs-lookup"><span data-stu-id="1d750-144">[How to: Publish Events that Conform to .NET Framework Guidelines](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md) </span></span>  
 <span data-ttu-id="1d750-145">[Оператор -= (справочник по C#)](../../language-reference/operators/subtraction-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="1d750-145">[-= Operator (C# Reference)](../../language-reference/operators/subtraction-assignment-operator.md) </span></span>  
 [<span data-ttu-id="1d750-146">Оператор +=</span><span class="sxs-lookup"><span data-stu-id="1d750-146">+= Operator</span></span>](../../../csharp/language-reference/operators/addition-assignment-operator.md)

