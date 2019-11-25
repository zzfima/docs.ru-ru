---
title: Общие сведения о событиях
description: Сведения о событиях в .NET Core и наших задачах по разработке языка для них.
ms.date: 06/20/2016
ms.assetid: 9b8d2a00-1584-4a5b-8994-5003d54d8e0c
ms.openlocfilehash: ceae2b9319a1de9f01102987735c7db2c2883f18
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138517"
---
# <a name="introduction-to-events"></a><span data-ttu-id="bcc09-103">Общие сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="bcc09-103">Introduction to events</span></span>

[<span data-ttu-id="bcc09-104">Назад</span><span class="sxs-lookup"><span data-stu-id="bcc09-104">Previous</span></span>](delegates-patterns.md)

<span data-ttu-id="bcc09-105">События, так же как и делегаты, представляют собой механизм *позднего связывания*.</span><span class="sxs-lookup"><span data-stu-id="bcc09-105">Events are, like delegates, a *late binding* mechanism.</span></span> <span data-ttu-id="bcc09-106">На самом деле события основаны на тех же средствах языка, которые обеспечивают поддержку делегатов.</span><span class="sxs-lookup"><span data-stu-id="bcc09-106">In fact, events are built on the language support for delegates.</span></span>

<span data-ttu-id="bcc09-107">С помощью событий объект может сообщить всем компонентам системы, которым это необходимо, о том, что что-то произошло.</span><span class="sxs-lookup"><span data-stu-id="bcc09-107">Events are a way for an object to broadcast (to all interested components in the system) that something has happened.</span></span> <span data-ttu-id="bcc09-108">Любой другой компонент может подписаться на событие, чтобы получать уведомления о его наступлении.</span><span class="sxs-lookup"><span data-stu-id="bcc09-108">Any other component can subscribe to the event, and be notified when an event is raised.</span></span>

<span data-ttu-id="bcc09-109">Возможно, вы уже пользовались событиями при программировании.</span><span class="sxs-lookup"><span data-stu-id="bcc09-109">You've probably used events in some of your programming.</span></span> <span data-ttu-id="bcc09-110">Во многих графических системах есть модель событий, которая позволяет сообщать о действиях пользователей.</span><span class="sxs-lookup"><span data-stu-id="bcc09-110">Many graphical systems have an event model to report user interaction.</span></span> <span data-ttu-id="bcc09-111">Такие события сообщают о перемещениях мыши, нажатиях кнопок и иных подобных действиях.</span><span class="sxs-lookup"><span data-stu-id="bcc09-111">These events would report mouse movement, button presses and similar interactions.</span></span> <span data-ttu-id="bcc09-112">Это наиболее распространенный, но, безусловно, не единственный вариант использования событий.</span><span class="sxs-lookup"><span data-stu-id="bcc09-112">That's one of the most common, but certainly not the only scenario where events are used.</span></span>

<span data-ttu-id="bcc09-113">Вы можете определить события, которые должны вызываться для классов.</span><span class="sxs-lookup"><span data-stu-id="bcc09-113">You can define events that should be raised for your classes.</span></span> <span data-ttu-id="bcc09-114">Важным моментом при работе с событиями является то, что для определенного события может быть не зарегистрирован ни один объект.</span><span class="sxs-lookup"><span data-stu-id="bcc09-114">One important consideration when working with events is that there may not be any object registered for a particular event.</span></span> <span data-ttu-id="bcc09-115">Код необходимо писать так, чтобы он не вызывал событий, если прослушиватели не настроены.</span><span class="sxs-lookup"><span data-stu-id="bcc09-115">You must write your code so that it does not raise events when no listeners are configured.</span></span>

<span data-ttu-id="bcc09-116">При подписке на событие также создается взаимосвязь между двумя объектами (источником события и приемником событий).</span><span class="sxs-lookup"><span data-stu-id="bcc09-116">Subscribing to an event also creates a coupling between two objects (the event source, and the event sink).</span></span> <span data-ttu-id="bcc09-117">Если приемник событий больше не должен получать события, необходимо отменить его подписку на источник события.</span><span class="sxs-lookup"><span data-stu-id="bcc09-117">You need to ensure that the event sink unsubscribes from the event source when no longer interested in events.</span></span>

## <a name="design-goals-for-event-support"></a><span data-ttu-id="bcc09-118">Цели при проектировании поддержки событий</span><span class="sxs-lookup"><span data-stu-id="bcc09-118">Design goals for event support</span></span>

<span data-ttu-id="bcc09-119">Ниже перечислены цели модели событий, реализуемой в языке.</span><span class="sxs-lookup"><span data-stu-id="bcc09-119">The language design for events targets these goals:</span></span>

- <span data-ttu-id="bcc09-120">Между источником события и приемником событий должна быть минимальная взаимосвязь.</span><span class="sxs-lookup"><span data-stu-id="bcc09-120">Enable very minimal coupling between an event source and an event sink.</span></span> <span data-ttu-id="bcc09-121">Эти два компонента могут создаваться разными организациями и даже обновляться по совершенно разным графикам.</span><span class="sxs-lookup"><span data-stu-id="bcc09-121">These two components may not be written by the same organization, and may even be updated on totally different schedules.</span></span>

- <span data-ttu-id="bcc09-122">Подписка на событие и отмена подписки на него должны производиться максимально просто.</span><span class="sxs-lookup"><span data-stu-id="bcc09-122">It should be very simple to subscribe to an event, and to unsubscribe from that same event.</span></span>

- <span data-ttu-id="bcc09-123">Источники событий должны поддерживать несколько подписчиков на события.</span><span class="sxs-lookup"><span data-stu-id="bcc09-123">Event sources should support multiple event subscribers.</span></span> <span data-ttu-id="bcc09-124">Кроме того, должен поддерживаться сценарий, когда подписчики на события не подключены.</span><span class="sxs-lookup"><span data-stu-id="bcc09-124">It should also support having no event subscribers attached.</span></span>

<span data-ttu-id="bcc09-125">Как можно увидеть, цели в отношении событий очень похожи на цели в отношении делегатов.</span><span class="sxs-lookup"><span data-stu-id="bcc09-125">You can see that the goals for events are very similar to the goals for delegates.</span></span>
<span data-ttu-id="bcc09-126">Вот почему языковая поддержка событий основана на механизмах поддержки делегатов.</span><span class="sxs-lookup"><span data-stu-id="bcc09-126">That's why the event language support is built on the delegate language support.</span></span>

## <a name="language-support-for-events"></a><span data-ttu-id="bcc09-127">Языковая поддержка событий</span><span class="sxs-lookup"><span data-stu-id="bcc09-127">Language support for events</span></span>

<span data-ttu-id="bcc09-128">Синтаксис определения событий, а также подписки и отмены подписки на них является расширением синтаксиса для делегатов.</span><span class="sxs-lookup"><span data-stu-id="bcc09-128">The syntax for defining events, and subscribing or unsubscribing from events is an extension of the syntax for delegates.</span></span>

<span data-ttu-id="bcc09-129">Для определения события используется ключевое слово `event`.</span><span class="sxs-lookup"><span data-stu-id="bcc09-129">To define an event you use the `event` keyword:</span></span>

```csharp
public event EventHandler<FileListArgs> Progress;
```

<span data-ttu-id="bcc09-130">Тип события (в этом примере `EventHandler<FileListArgs>`) должен быть типом делегата.</span><span class="sxs-lookup"><span data-stu-id="bcc09-130">The type of the event (`EventHandler<FileListArgs>` in this example) must be a delegate type.</span></span> <span data-ttu-id="bcc09-131">При объявлении события должен соблюдаться ряд соглашений.</span><span class="sxs-lookup"><span data-stu-id="bcc09-131">There are a number of conventions that you should follow when declaring an event.</span></span> <span data-ttu-id="bcc09-132">Как правило, тип делегата события имеет возвращаемый тип void.</span><span class="sxs-lookup"><span data-stu-id="bcc09-132">Typically, the event delegate type has a void return.</span></span>
<span data-ttu-id="bcc09-133">Объявление события должно представлять собой глагол или глагольное словосочетание.</span><span class="sxs-lookup"><span data-stu-id="bcc09-133">Event declarations should be a verb, or a verb phrase.</span></span>
<span data-ttu-id="bcc09-134">Если событие сообщает о том, что уже произошло, используйте прошедшее время.</span><span class="sxs-lookup"><span data-stu-id="bcc09-134">Use past tense when the event reports something that has happened.</span></span> <span data-ttu-id="bcc09-135">Для сообщения о том, что должно произойти, используйте глагол в настоящем времени (например, `Closing`).</span><span class="sxs-lookup"><span data-stu-id="bcc09-135">Use a present tense verb (for example, `Closing`) to report something that is about to happen.</span></span> <span data-ttu-id="bcc09-136">Настоящее время часто указывает на то, что класс поддерживает какую-либо настройку.</span><span class="sxs-lookup"><span data-stu-id="bcc09-136">Often, using present tense indicates that your class supports some kind of customization behavior.</span></span> <span data-ttu-id="bcc09-137">Одна из самых распространенных ситуаций — поддержка отмены.</span><span class="sxs-lookup"><span data-stu-id="bcc09-137">One of the most common scenarios is to support cancellation.</span></span> <span data-ttu-id="bcc09-138">Например, событие `Closing` может иметь аргумент, который указывает на то, должна ли продолжаться операция закрытия.</span><span class="sxs-lookup"><span data-stu-id="bcc09-138">For example, a `Closing` event may include an argument that would indicate if the close operation should continue, or not.</span></span>  <span data-ttu-id="bcc09-139">В других ситуациях вызывающим объектам может предоставляться возможность изменения поведения путем изменения свойств аргументов события.</span><span class="sxs-lookup"><span data-stu-id="bcc09-139">Other scenarios may enable callers to modify behavior by updating properties of the event arguments.</span></span> <span data-ttu-id="bcc09-140">Событие может вызываться для указания действия, которое алгоритму предлагается выполнить в следующую очередь.</span><span class="sxs-lookup"><span data-stu-id="bcc09-140">You may raise an event to indicate a proposed next action an algorithm will take.</span></span> <span data-ttu-id="bcc09-141">Обработчик событий может предписать выполнение другого действия, изменив свойства аргумента события.</span><span class="sxs-lookup"><span data-stu-id="bcc09-141">The event handler may mandate a different action by modifying  properties of the event argument.</span></span>

<span data-ttu-id="bcc09-142">Если нужно инициировать событие, то следует вызвать соответствующий обработчик событий с помощью синтаксиса вызова делегатов:</span><span class="sxs-lookup"><span data-stu-id="bcc09-142">When you want to raise the event, you call the event handlers using the delegate invocation syntax:</span></span>

```csharp
Progress?.Invoke(this, new FileListArgs(file));
```

<span data-ttu-id="bcc09-143">Как описано в разделе, посвященном [делегатам](delegates-patterns.md), оператор ?.</span><span class="sxs-lookup"><span data-stu-id="bcc09-143">As discussed in the section on [delegates](delegates-patterns.md), the ?.</span></span>
<span data-ttu-id="bcc09-144">позволяет легко предотвратить попытки вызова события, если на него нет подписчиков.</span><span class="sxs-lookup"><span data-stu-id="bcc09-144">operator makes it easy to ensure that you do not attempt to raise the event when there are no subscribers to that event.</span></span>
 
<span data-ttu-id="bcc09-145">Подписка на событие производится с помощью оператора `+=`:</span><span class="sxs-lookup"><span data-stu-id="bcc09-145">You subscribe to an event by using the `+=` operator:</span></span>

```csharp
EventHandler<FileListArgs> onProgress = (sender, eventArgs) => 
    Console.WriteLine(eventArgs.FoundFile);

fileLister.Progress += onProgress;
```

<span data-ttu-id="bcc09-146">Имя метода обработчика обычно содержит имя события с префиксом On, как показано выше.</span><span class="sxs-lookup"><span data-stu-id="bcc09-146">The handler method typically has the prefix 'On' followed by the event name, as shown above.</span></span>

<span data-ttu-id="bcc09-147">Для отмены подписки на событие служит оператор `-=`:</span><span class="sxs-lookup"><span data-stu-id="bcc09-147">You unsubscribe using the `-=` operator:</span></span>

```csharp
fileLister.Progress -= onProgress;
```

<span data-ttu-id="bcc09-148">Важно отметить, что для выражения, представляющего обработчик событий, была объявлена локальная переменная.</span><span class="sxs-lookup"><span data-stu-id="bcc09-148">It's important to note that I declared a local variable for the expression that represents the event handler.</span></span> <span data-ttu-id="bcc09-149">Благодаря этому при отмене подписки обработчик удаляется.</span><span class="sxs-lookup"><span data-stu-id="bcc09-149">That ensures the unsubscribe removes the handler.</span></span>
<span data-ttu-id="bcc09-150">Если вместо этого использовалось тело лямбда-выражения, то производится попытка удалить обработчик, который не был подключен, что не приводит ни к какому результату.</span><span class="sxs-lookup"><span data-stu-id="bcc09-150">If, instead, you used the body of the lambda expression, you are attempting to remove a handler that has never been attached, which does nothing.</span></span>

<span data-ttu-id="bcc09-151">В следующей статье вы узнаете больше о типичных шаблонах событий и ознакомитесь с вариантами этого примера.</span><span class="sxs-lookup"><span data-stu-id="bcc09-151">In the next article, you'll learn more about typical event patterns, and different variations on this example.</span></span>

[<span data-ttu-id="bcc09-152">Вперед</span><span class="sxs-lookup"><span data-stu-id="bcc09-152">Next</span></span>](event-pattern.md)
