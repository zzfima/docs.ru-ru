---
title: События (F#)
description: 'Узнайте, как события F #, которые позволяют связывать вызовы функций с действиями пользователя, играющие важную роль в программировании графического интерфейса пользователя.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 5c5f152830d4d91a25c79a09800263cdd85ed8b7
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="events"></a><span data-ttu-id="72d9c-103">События</span><span class="sxs-lookup"><span data-stu-id="72d9c-103">Events</span></span>

> [!NOTE]
<span data-ttu-id="72d9c-104">Ссылки на справочник по API в этой статье ведут на сайт MSDN.</span><span class="sxs-lookup"><span data-stu-id="72d9c-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="72d9c-105">Работа над справочником по API docs.microsoft.com не завершена.</span><span class="sxs-lookup"><span data-stu-id="72d9c-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="72d9c-106">События позволяют связывать вызовы функций с действиями пользователя и являются важным элементом в программировании графического интерфейса пользователя.</span><span class="sxs-lookup"><span data-stu-id="72d9c-106">Events enable you to associate function calls with user actions and are important in GUI programming.</span></span> <span data-ttu-id="72d9c-107">События могут также инициироваться приложениями или операционной системой.</span><span class="sxs-lookup"><span data-stu-id="72d9c-107">Events can also be triggered by your applications or by the operating system.</span></span>

## <a name="handling-events"></a><span data-ttu-id="72d9c-108">Обработка событий</span><span class="sxs-lookup"><span data-stu-id="72d9c-108">Handling Events</span></span>
<span data-ttu-id="72d9c-109">При использовании библиотеки графического интерфейса пользователя, такой как Windows Forms или Windows Presentation Foundation (WPF), значительная часть кода в приложении выполняется в ответ на события, предопределенные в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="72d9c-109">When you use a GUI library like Windows Forms or Windows Presentation Foundation (WPF), much of the code in your application runs in response to events that are predefined by the library.</span></span> <span data-ttu-id="72d9c-110">Эти предопределенные события являются членами классов графического интерфейса пользователя, таких как формы и элементы управления.</span><span class="sxs-lookup"><span data-stu-id="72d9c-110">These predefined events are members of GUI classes such as forms and controls.</span></span> <span data-ttu-id="72d9c-111">Можно добавить произвольное поведение к уже существующему событию, такому как нажатие кнопки, сославшись на интересующее именованное событие (например, событие `Click` класса `Form`) и вызвав метод `Add`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="72d9c-111">You can add custom behavior to a preexisting event, such as a button click, by referencing the specific named event of interest (for example, the `Click` event of the `Form` class) and invoking the `Add` method, as shown in the following code.</span></span> <span data-ttu-id="72d9c-112">При запуске этого кода из F# Interactive вызов метода `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)` следует опустить.</span><span class="sxs-lookup"><span data-stu-id="72d9c-112">If you run this from F# Interactive, omit the call to `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3601.fs)]

<span data-ttu-id="72d9c-113">Тип метода `Add` — `('a -> unit) -> unit`.</span><span class="sxs-lookup"><span data-stu-id="72d9c-113">The type of the `Add` method is `('a -> unit) -> unit`.</span></span> <span data-ttu-id="72d9c-114">Следовательно, метод, обрабатывающий событие, принимает один параметр — обычно аргументы события — и возвращает значение типа `unit`.</span><span class="sxs-lookup"><span data-stu-id="72d9c-114">Therefore, the event handler method takes one parameter, typically the event arguments, and returns `unit`.</span></span> <span data-ttu-id="72d9c-115">В предыдущем примере обработчик события показан как лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="72d9c-115">The previous example shows the event handler as a lambda expression.</span></span> <span data-ttu-id="72d9c-116">Обработчик события также может представлять собой значение функции, как в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="72d9c-116">The event handler can also be a function value, as in the following code example.</span></span> <span data-ttu-id="72d9c-117">В следующем примере кода также показано использование параметров обработчика события, содержащих данные, зависящие от типа события.</span><span class="sxs-lookup"><span data-stu-id="72d9c-117">The following code example also shows the use of the event handler parameters, which provide information specific to the type of event.</span></span> <span data-ttu-id="72d9c-118">Для события `MouseMove` система передает объект `System.Windows.Forms.MouseEventArgs`, содержащий координаты `X` и `Y` положения указателя.</span><span class="sxs-lookup"><span data-stu-id="72d9c-118">For a `MouseMove` event, the system passes a `System.Windows.Forms.MouseEventArgs` object, which contains the `X` and `Y` position of the pointer.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3602.fs)]
    
## <a name="creating-custom-events"></a><span data-ttu-id="72d9c-119">Создание пользовательских событий</span><span class="sxs-lookup"><span data-stu-id="72d9c-119">Creating Custom Events</span></span>
<span data-ttu-id="72d9c-120">События F # представлены F # [событий](https://msdn.microsoft.com/library/f3b47c8a-4ee5-4ce8-9a72-ad305a17c4b9) класса, который реализует [IEvent](https://msdn.microsoft.com/library/8dbca0df-f8a1-40bd-8d50-aa26f6a8b862) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="72d9c-120">F# events are represented by the F# [Event](https://msdn.microsoft.com/library/f3b47c8a-4ee5-4ce8-9a72-ad305a17c4b9) class, which implements the [IEvent](https://msdn.microsoft.com/library/8dbca0df-f8a1-40bd-8d50-aa26f6a8b862) interface.</span></span> <span data-ttu-id="72d9c-121">`IEvent` представляет собой интерфейс, объединяющий функциональные возможности двух других интерфейсов, `System.IObservable<'T>` и [IDelegateEvent](https://msdn.microsoft.com/library/3d849465-6b8e-4fc5-b36c-2941d734268a).</span><span class="sxs-lookup"><span data-stu-id="72d9c-121">`IEvent` is itself an interface that combines the functionality of two other interfaces, `System.IObservable<'T>` and [IDelegateEvent](https://msdn.microsoft.com/library/3d849465-6b8e-4fc5-b36c-2941d734268a).</span></span> <span data-ttu-id="72d9c-122">Следовательно, события `Event` обладают функциональными возможностями, эквивалентными возможностям делегатов в других языках, и дополнительно функциональными возможностями интерфейса `IObservable`; это означает, что события F# поддерживают фильтрацию событий и использование функций первого класса и лямбда-выражений языка F# в качестве обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="72d9c-122">Therefore, `Event`s have the equivalent functionality of delegates in other languages, plus the additional functionality from `IObservable`, which means that F# events support event filtering and using F# first-class functions and lambda expressions as event handlers.</span></span> <span data-ttu-id="72d9c-123">Эта функциональность обеспечивается в [модуля событий](https://msdn.microsoft.com/library/8b883baa-a460-4840-9baa-de8260351bc7).</span><span class="sxs-lookup"><span data-stu-id="72d9c-123">This functionality is provided in the [Event module](https://msdn.microsoft.com/library/8b883baa-a460-4840-9baa-de8260351bc7).</span></span>

<span data-ttu-id="72d9c-124">Чтобы создать для класса событие, которое ведет себя точно так же, как любое другое событие платформы .NET Framework, добавьте в класс привязку `let`, определяющую событие `Event` как поле в классе.</span><span class="sxs-lookup"><span data-stu-id="72d9c-124">To create an event on a class that acts just like any other .NET Framework event, add to the class a `let` binding that defines an `Event` as a field in a class.</span></span> <span data-ttu-id="72d9c-125">В качестве аргумента типа можно указать требуемый тип аргумента события или оставить его пустым, чтобы соответствующий тип был выведен компилятором.</span><span class="sxs-lookup"><span data-stu-id="72d9c-125">You can specify the desired event argument type as the type argument, or leave it blank and have the compiler infer the appropriate type.</span></span> <span data-ttu-id="72d9c-126">Необходимо также определить член события, предоставляющего это событие как событие CLI.</span><span class="sxs-lookup"><span data-stu-id="72d9c-126">You also must define an event member that exposes the event as a CLI event.</span></span> <span data-ttu-id="72d9c-127">Этот член должен иметь [CLIEvent](https://msdn.microsoft.com/library/d359f1dd-ffa5-42fb-8808-b4c8131a0333) атрибута.</span><span class="sxs-lookup"><span data-stu-id="72d9c-127">This member should have the [CLIEvent](https://msdn.microsoft.com/library/d359f1dd-ffa5-42fb-8808-b4c8131a0333) attribute.</span></span> <span data-ttu-id="72d9c-128">Он объявляется как свойство и его реализация представляет собой просто вызов [публикации](https://msdn.microsoft.com/library/b0fdaad5-25e5-43d0-9c0c-ce37c4aeb68e) свойства события.</span><span class="sxs-lookup"><span data-stu-id="72d9c-128">It is declared like a property and its implementation is just a call to the [Publish](https://msdn.microsoft.com/library/b0fdaad5-25e5-43d0-9c0c-ce37c4aeb68e) property of the event.</span></span> <span data-ttu-id="72d9c-129">Пользователи класса могут использовать метод `Add` опубликованного события для добавления обработчика.</span><span class="sxs-lookup"><span data-stu-id="72d9c-129">Users of your class can use the `Add` method of the published event to add a handler.</span></span> <span data-ttu-id="72d9c-130">Аргумент метода `Add` может быть лямбда-выражением.</span><span class="sxs-lookup"><span data-stu-id="72d9c-130">The argument for the `Add` method can be a lambda expression.</span></span> <span data-ttu-id="72d9c-131">Для вызова события можно использовать его свойство `Trigger`, передавая аргументы функции обработчика.</span><span class="sxs-lookup"><span data-stu-id="72d9c-131">You can use the `Trigger` property of the event to raise the event, passing the arguments to the handler function.</span></span> <span data-ttu-id="72d9c-132">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="72d9c-132">The following code example illustrates this.</span></span> <span data-ttu-id="72d9c-133">В этом примере выведенный аргумент типа для события — кортеж, представляющий аргументы для лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="72d9c-133">In this example, the inferred type argument for the event is a tuple, which represents the arguments for the lambda expression.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3605.fs)]

<span data-ttu-id="72d9c-134">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="72d9c-134">The output is as follows.</span></span>

```
Event1 occurred! Object data: Hello World!
```

<span data-ttu-id="72d9c-135">Здесь иллюстрируется дополнительная функциональная возможность, обеспечиваемая модулем `Event`.</span><span class="sxs-lookup"><span data-stu-id="72d9c-135">The additional functionality provided by the `Event` module is illustrated here.</span></span> <span data-ttu-id="72d9c-136">Следующий пример кода иллюстрирует основное использование функции `Event.create` для создания события и метода-триггера, добавления двух обработчиков события в виде лямбда-выражений и последующего инициирования события для выполнения обоих лямбда-выражений.</span><span class="sxs-lookup"><span data-stu-id="72d9c-136">The following code example illustrates the basic use of `Event.create` to create an event and a trigger method, add two event handlers in the form of lambda expressions, and then trigger the event to execute both lambda expressions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3603.fs)]

<span data-ttu-id="72d9c-137">Результат выполнения приведенного кода будет следующим.</span><span class="sxs-lookup"><span data-stu-id="72d9c-137">The output of the previous code is as follows.</span></span>

```
Event occurred.
Given a value: Event occurred.
```

## <a name="processing-event-streams"></a><span data-ttu-id="72d9c-138">Обработка потоков событий</span><span class="sxs-lookup"><span data-stu-id="72d9c-138">Processing Event Streams</span></span>
<span data-ttu-id="72d9c-139">Вместо простого добавления обработчика событий для события с помощью [Event.add](https://msdn.microsoft.com/library/10670d3b-8d47-4f6e-b8df-ebc6f64ef4fd) функции, можно использовать функции в `Event` модуль для обработки потоков событий настраиваемыми способами.</span><span class="sxs-lookup"><span data-stu-id="72d9c-139">Instead of just adding an event handler for an event by using the [Event.add](https://msdn.microsoft.com/library/10670d3b-8d47-4f6e-b8df-ebc6f64ef4fd) function, you can use the functions in the `Event` module to process streams of events in highly customized ways.</span></span> <span data-ttu-id="72d9c-140">Это делается путем использования оператора прямого конвейера (`|>`) вместе с событием в качестве первого значения в серии вызовов функций и функций модуля `Event` в качестве последующих вызовов функций.</span><span class="sxs-lookup"><span data-stu-id="72d9c-140">To do this, you use the forward pipe (`|>`) together with the event as the first value in a series of function calls, and the `Event` module functions as subsequent function calls.</span></span>

<span data-ttu-id="72d9c-141">В следующем примере кода демонстрируется, как настроить событие, обработчик которого вызывается только при определенных условиях.</span><span class="sxs-lookup"><span data-stu-id="72d9c-141">The following code example shows how to set up an event for which the handler is only called under certain conditions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3604.fs)]

<span data-ttu-id="72d9c-142">[Модуль Observable](https://msdn.microsoft.com/library/16b8610b-b30a-4df7-aa99-d9d352276227) содержит аналогичные функции, действующие на наблюдаемые объекты.</span><span class="sxs-lookup"><span data-stu-id="72d9c-142">The [Observable module](https://msdn.microsoft.com/library/16b8610b-b30a-4df7-aa99-d9d352276227) contains similar functions that operate on observable objects.</span></span> <span data-ttu-id="72d9c-143">Наблюдаемые объекты аналогичны событиям, но они активно подписываются на события только при создании подписки на такой объект.</span><span class="sxs-lookup"><span data-stu-id="72d9c-143">Observable objects are similar to events but only actively subscribe to events if they themselves are being subscribed to.</span></span>


## <a name="implementing-an-interface-event"></a><span data-ttu-id="72d9c-144">Реализация события интерфейса</span><span class="sxs-lookup"><span data-stu-id="72d9c-144">Implementing an Interface Event</span></span>
<span data-ttu-id="72d9c-145">Разработка компонентов пользовательского интерфейса часто начинается с создания новой формы или нового элемента управления, наследуемых от существующих формы или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="72d9c-145">As you develop UI components, you often start by creating a new form or a new control that inherits from an existing form or control.</span></span> <span data-ttu-id="72d9c-146">События часто определяются в интерфейсе. В этом случае для реализации события необходимо реализовать интерфейс.</span><span class="sxs-lookup"><span data-stu-id="72d9c-146">Events are frequently defined on an interface, and, in that case, you must implement the interface to implement the event.</span></span> <span data-ttu-id="72d9c-147">Интерфейс `System.ComponentModel.INotifyPropertyChanged` определяет одно событие `System.ComponentModel.INotifyPropertyChanged.PropertyChanged`.</span><span class="sxs-lookup"><span data-stu-id="72d9c-147">The `System.ComponentModel.INotifyPropertyChanged` interface defines a single `System.ComponentModel.INotifyPropertyChanged.PropertyChanged` event.</span></span> <span data-ttu-id="72d9c-148">В представленном ниже коде показана реализация события, которое определил этот унаследованный интерфейс:</span><span class="sxs-lookup"><span data-stu-id="72d9c-148">The following code illustrates how to implement the event that this inherited interface defined:</span></span>

```fsharp
module CustomForm

open System.Windows.Forms
open System.ComponentModel

type AppForm() as this =
    inherit Form()

    // Define the propertyChanged event.
    let propertyChanged = Event<PropertyChangedEventHandler, PropertyChangedEventArgs>()
    let mutable underlyingValue = "text0"

    // Set up a click event to change the properties.
    do
        this.Click |> Event.add(fun evArgs -> this.Property1 <- "text2"
        this.Property2 <- "text3")

    // This property does not have the property-changed event set.
    member val Property1 : string = "text" with get, set

    // This property has the property-changed event set.
    member this.Property2
        with get() = underlyingValue
        and set(newValue) =
            underlyingValue <- newValue
            propertyChanged.Trigger(this, new PropertyChangedEventArgs("Property2"))

    // Expose the PropertyChanged event as a first class .NET event.
    [<CLIEvent>]
    member this.PropertyChanged = propertyChanged.Publish


    // Define the add and remove methods to implement this interface.
    interface INotifyPropertyChanged with
        member this.add_PropertyChanged(handler) = propertyChanged.Publish.AddHandler(handler)
        member this.remove_PropertyChanged(handler) = propertyChanged.Publish.RemoveHandler(handler)

    // This is the event-handler method.
    member this.OnPropertyChanged(args : PropertyChangedEventArgs) =
        let newProperty = this.GetType().GetProperty(args.PropertyName)
        let newValue = newProperty.GetValue(this :> obj) :?> string
        printfn "Property %s changed its value to %s" args.PropertyName newValue

// Create a form, hook up the event handler, and start the application.
let appForm = new AppForm()
let inpc = appForm :> INotifyPropertyChanged
inpc.PropertyChanged.Add(appForm.OnPropertyChanged)
Application.Run(appForm)
```

<span data-ttu-id="72d9c-149">Если требуется подключить событие в конструкторе, код будет несколько сложнее, поскольку подключение события должно находиться в блоке `then` дополнительного конструктора, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="72d9c-149">If you want to hook up the event in the constructor, the code is a bit more complicated because the event hookup must be in a `then` block in an additional constructor, as in the following example:</span></span>

```fsharp
module CustomForm

open System.Windows.Forms
open System.ComponentModel

// Create a private constructor with a dummy argument so that the public
// constructor can have no arguments.
type AppForm private (dummy) as this =
    inherit Form()

    // Define the propertyChanged event.
    let propertyChanged = Event<PropertyChangedEventHandler, PropertyChangedEventArgs>()
    let mutable underlyingValue = "text0"

    // Set up a click event to change the properties.
    do
        this.Click |> Event.add(fun evArgs -> this.Property1 <- "text2"
        this.Property2 <- "text3")


    // This property does not have the property changed event set.
    member val Property1 : string = "text" with get, set

    // This property has the property changed event set.
    member this.Property2
        with get() = underlyingValue
        and set(newValue) =
            underlyingValue <- newValue
            propertyChanged.Trigger(this, new PropertyChangedEventArgs("Property2"))

    [<CLIEvent>]
    member this.PropertyChanged = propertyChanged.Publish

    // Define the add and remove methods to implement this interface.
    interface INotifyPropertyChanged with
        member this.add_PropertyChanged(handler) = this.PropertyChanged.AddHandler(handler)
        member this.remove_PropertyChanged(handler) = this.PropertyChanged.RemoveHandler(handler)

    // This is the event handler method.
    member this.OnPropertyChanged(args : PropertyChangedEventArgs) =
        let newProperty = this.GetType().GetProperty(args.PropertyName)
        let newValue = newProperty.GetValue(this :> obj) :?> string
        printfn "Property %s changed its value to %s" args.PropertyName newValue

    new() as this =
        new AppForm(0)
        then
            let inpc = this :> INotifyPropertyChanged
            inpc.PropertyChanged.Add(this.OnPropertyChanged)


// Create a form, hook up the event handler, and start the application.
let appForm = new AppForm()
Application.Run(appForm)
```

## <a name="see-also"></a><span data-ttu-id="72d9c-150">См. также</span><span class="sxs-lookup"><span data-stu-id="72d9c-150">See Also</span></span>
[<span data-ttu-id="72d9c-151">Члены</span><span class="sxs-lookup"><span data-stu-id="72d9c-151">Members</span></span>](index.md)

[<span data-ttu-id="72d9c-152">Обработка и вызов событий</span><span class="sxs-lookup"><span data-stu-id="72d9c-152">Handling and Raising Events</span></span>](../../../../docs/standard/events/index.md)

[<span data-ttu-id="72d9c-153">Лямбда-выражения: `fun` ключевое слово</span><span class="sxs-lookup"><span data-stu-id="72d9c-153">Lambda Expressions: The `fun` Keyword</span></span>](../functions/lambda-expressions-the-fun-keyword.md)

[<span data-ttu-id="72d9c-154">Модуль Control.Event</span><span class="sxs-lookup"><span data-stu-id="72d9c-154">Control.Event Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event-module-%5bfsharp%5d)

[<span data-ttu-id="72d9c-155">Control.Event&#60;'T&#62; класса</span><span class="sxs-lookup"><span data-stu-id="72d9c-155">Control.Event&#60;'T&#62; Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27t%5d-class-%5bfsharp%5d)

[<span data-ttu-id="72d9c-156">Control.Event&#60;«Делегат» Args&#62; класса</span><span class="sxs-lookup"><span data-stu-id="72d9c-156">Control.Event&#60;'Delegate,'Args&#62; Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27delegate%2c%27args%5d-class-%5bfsharp%5d)
