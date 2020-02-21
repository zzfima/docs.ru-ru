---
title: События
description: Узнайте, F# как события позволяют связывать вызовы функций с действиями пользователя, которые важны для программирования GUI.
ms.date: 05/16/2016
ms.openlocfilehash: ad60aff318832ab3ba5e9f7c43928898e171cea8
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543629"
---
# <a name="events"></a>События

> [!NOTE]
> Ссылки на справочник по API в этой статье ведут на сайт MSDN.  Работа над справочником по API docs.microsoft.com не завершена.

События позволяют связывать вызовы функций с действиями пользователя и являются важным элементом в программировании графического интерфейса пользователя. События могут также инициироваться приложениями или операционной системой.

## <a name="handling-events"></a>Обработка событий

При использовании библиотеки графического интерфейса пользователя, такой как Windows Forms или Windows Presentation Foundation (WPF), значительная часть кода в приложении выполняется в ответ на события, предопределенные в библиотеке. Эти предопределенные события являются членами классов графического интерфейса пользователя, таких как формы и элементы управления. Можно добавить произвольное поведение к уже существующему событию, такому как нажатие кнопки, сославшись на интересующее именованное событие (например, событие `Click` класса `Form`) и вызвав метод `Add`, как показано в следующем коде. При запуске этого кода из F# Interactive вызов метода `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)` следует опустить.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3601.fs)]

Тип метода `Add` — `('a -> unit) -> unit`. Следовательно, метод, обрабатывающий событие, принимает один параметр — обычно аргументы события — и возвращает значение типа `unit`. В предыдущем примере обработчик события показан как лямбда-выражение. Обработчик события также может представлять собой значение функции, как в следующем примере кода. В следующем примере кода также показано использование параметров обработчика события, содержащих данные, зависящие от типа события. Для события `MouseMove` система передает объект `System.Windows.Forms.MouseEventArgs`, содержащий координаты `X` и `Y` положения указателя.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3602.fs)]

## <a name="creating-custom-events"></a>Создание пользовательских событий

F#события представлены F# классом [событий](https://msdn.microsoft.com/library/f3b47c8a-4ee5-4ce8-9a72-ad305a17c4b9) , реализующим интерфейс [IEvent](https://msdn.microsoft.com/library/8dbca0df-f8a1-40bd-8d50-aa26f6a8b862) . `IEvent` является интерфейсом, объединяющим функциональность двух других интерфейсов, `System.IObservable<'T>` и [IDelegateEvent](https://msdn.microsoft.com/library/3d849465-6b8e-4fc5-b36c-2941d734268a). Следовательно, события `Event` обладают функциональными возможностями, эквивалентными возможностям делегатов в других языках, и дополнительно функциональными возможностями интерфейса `IObservable`; это означает, что события F# поддерживают фильтрацию событий и использование функций первого класса и лямбда-выражений языка F# в качестве обработчиков событий. Эта функция предоставляется в [модуле Event](https://msdn.microsoft.com/library/8b883baa-a460-4840-9baa-de8260351bc7).

Чтобы создать для класса событие, которое ведет себя точно так же, как любое другое событие платформы .NET Framework, добавьте в класс привязку `let`, определяющую событие `Event` как поле в классе. В качестве аргумента типа можно указать требуемый тип аргумента события или оставить его пустым, чтобы соответствующий тип был выведен компилятором. Необходимо также определить член события, предоставляющего это событие как событие CLI. Этот элемент должен иметь атрибут [CLIEvent](https://msdn.microsoft.com/library/d359f1dd-ffa5-42fb-8808-b4c8131a0333) . Он объявляется как свойство, а его реализация — просто вызовом свойства [публикации](https://msdn.microsoft.com/library/b0fdaad5-25e5-43d0-9c0c-ce37c4aeb68e) события. Пользователи класса могут использовать метод `Add` опубликованного события для добавления обработчика. Аргумент метода `Add` может быть лямбда-выражением. Для вызова события можно использовать его свойство `Trigger`, передавая аргументы функции обработчика. Это показано в следующем примере кода. В этом примере выведенный аргумент типа для события — кортеж, представляющий аргументы для лямбда-выражения.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3605.fs)]

Выходные данные выглядят следующим образом.

```console
Event1 occurred! Object data: Hello World!
```

Здесь иллюстрируется дополнительная функциональная возможность, обеспечиваемая модулем `Event`. Следующий пример кода иллюстрирует основное использование функции `Event.create` для создания события и метода-триггера, добавления двух обработчиков события в виде лямбда-выражений и последующего инициирования события для выполнения обоих лямбда-выражений.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3603.fs)]

Результат выполнения приведенного кода будет следующим.

```console
Event occurred.
Given a value: Event occurred.
```

## <a name="processing-event-streams"></a>Обработка потоков событий

Вместо добавления обработчика событий для события с помощью функции [Event. Add](https://msdn.microsoft.com/library/10670d3b-8d47-4f6e-b8df-ebc6f64ef4fd) можно использовать функции в модуле `Event`, чтобы обрабатывать потоки событий в крайне настраиваемых способах. Это делается путем использования оператора прямого конвейера (`|>`) вместе с событием в качестве первого значения в серии вызовов функций и функций модуля `Event` в качестве последующих вызовов функций.

В следующем примере кода демонстрируется, как настроить событие, обработчик которого вызывается только при определенных условиях.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3604.fs)]

[Наблюдаемый модуль](https://msdn.microsoft.com/library/16b8610b-b30a-4df7-aa99-d9d352276227) содержит аналогичные функции, которые работают с наблюдаемыми объектами. Наблюдаемые объекты аналогичны событиям, но они активно подписываются на события только при создании подписки на такой объект.

## <a name="implementing-an-interface-event"></a>Реализация события интерфейса

Разработка компонентов пользовательского интерфейса часто начинается с создания новой формы или нового элемента управления, наследуемых от существующих формы или элемента управления. События часто определяются в интерфейсе. В этом случае для реализации события необходимо реализовать интерфейс. Интерфейс `System.ComponentModel.INotifyPropertyChanged` определяет одно событие `System.ComponentModel.INotifyPropertyChanged.PropertyChanged`. В представленном ниже коде показана реализация события, которое определил этот унаследованный интерфейс:

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
        this.Click |> Event.add(fun evArgs ->
            this.Property1 <- "text2"
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

Если требуется подключить событие в конструкторе, код будет несколько сложнее, поскольку подключение события должно находиться в блоке `then` дополнительного конструктора, как показано в следующем примере:

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
        this.Click |> Event.add(fun evArgs ->
            this.Property1 <- "text2"
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

## <a name="see-also"></a>См. также раздел

- [Участники](index.md)
- [Обработка и вызов событий](../../../standard/events/index.md)
- [Лямбда-выражения: ключевое слово `fun`](../functions/lambda-expressions-the-fun-keyword.md)
- [Модуль Control. Event](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event-module-%5bfsharp%5d)
- [&#62; Класс Control. Event&#60;](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27t%5d-class-%5bfsharp%5d)
- [Класс args&#62; элемента&#60;управления. Event](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27delegate%2c%27args%5d-class-%5bfsharp%5d)
