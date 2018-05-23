---
title: Стандартные шаблоны событий .NET
description: Сведения о шаблонах событий .NET, а также о создании источников стандартных событий, подписке на такие события и их обработке в коде.
ms.date: 06/20/2016
ms.assetid: 8a3133d6-4ef2-46f9-9c8d-a8ea8898e4c9
ms.openlocfilehash: 633a90062f2d068cfa050c0aa151885608cc4172
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="standard-net-event-patterns"></a><span data-ttu-id="86276-103">Стандартные шаблоны событий .NET</span><span class="sxs-lookup"><span data-stu-id="86276-103">Standard .NET event patterns</span></span>

[<span data-ttu-id="86276-104">Назад</span><span class="sxs-lookup"><span data-stu-id="86276-104">Previous</span></span>](events-overview.md)

<span data-ttu-id="86276-105">События .NET обычно следуют нескольким известным шаблонам.</span><span class="sxs-lookup"><span data-stu-id="86276-105">.NET events generally follow a few known patterns.</span></span> <span data-ttu-id="86276-106">Стандартизация на основе этих шаблонов означает, что разработчики могут использовать знание таких стандартных шаблонов, применяя их к любой программе событий .NET.</span><span class="sxs-lookup"><span data-stu-id="86276-106">Standardizing on these patterns means that developers can leverage knowledge of those standard patterns, which can be applied to any .NET event program.</span></span>

<span data-ttu-id="86276-107">Мы разберем эти стандартные шаблоны, чтобы снабдить вас знаниями, необходимыми для создания источников стандартных событий, подписки и обработки стандартных событий в коде.</span><span class="sxs-lookup"><span data-stu-id="86276-107">Let's go through these standard patterns so you will have all the knowledge you need to create standard event sources, and subscribe and process standard events in your code.</span></span>

## <a name="event-delegate-signatures"></a><span data-ttu-id="86276-108">Сигнатуры делегатов событий</span><span class="sxs-lookup"><span data-stu-id="86276-108">Event Delegate Signatures</span></span>

<span data-ttu-id="86276-109">Стандартной сигнатурой делегата события .NET является:</span><span class="sxs-lookup"><span data-stu-id="86276-109">The standard signature for a .NET event delegate is:</span></span>

```csharp
void OnEventRaised(object sender, EventArgs args);
```

<span data-ttu-id="86276-110">Тип возвращаемого значения — void.</span><span class="sxs-lookup"><span data-stu-id="86276-110">The return type is void.</span></span> <span data-ttu-id="86276-111">События основаны на делегатах и являются делегатами многоадресной рассылки.</span><span class="sxs-lookup"><span data-stu-id="86276-111">Events are based on delegates and are multicast delegates.</span></span> <span data-ttu-id="86276-112">Это обеспечивает поддержку нескольких подписчиков для любого источника событий.</span><span class="sxs-lookup"><span data-stu-id="86276-112">That supports multiple subscribers for any event source.</span></span> <span data-ttu-id="86276-113">Одно значение, возвращаемое из метода, не масштабируется на несколько подписчиков событий.</span><span class="sxs-lookup"><span data-stu-id="86276-113">The single return value from a method doesn't scale to multiple event subscribers.</span></span> <span data-ttu-id="86276-114">Какое возвращаемое значение доступно источнику события после возникновения события?</span><span class="sxs-lookup"><span data-stu-id="86276-114">Which return value does the event source see after raising an event?</span></span> <span data-ttu-id="86276-115">Далее в этой статье будет показано, как создавать протоколы событий, которые поддерживают подписчики на события, передающие данные в источник событий.</span><span class="sxs-lookup"><span data-stu-id="86276-115">Later in this article you'll see how to create event protocols that support event subscribers that report information to the event source.</span></span>

<span data-ttu-id="86276-116">Список аргументов содержит два аргумента: отправителя и аргументы события.</span><span class="sxs-lookup"><span data-stu-id="86276-116">The argument list contains two arguments: the sender, and the event arguments.</span></span> <span data-ttu-id="86276-117">Тип времени компиляции `sender` — `System.Object`, даже если вам, вероятно, известен более производный тип, который всегда является правильным.</span><span class="sxs-lookup"><span data-stu-id="86276-117">The compile time type of `sender` is `System.Object`, even though you likely know a more derived type that would always be correct.</span></span> <span data-ttu-id="86276-118">По соглашению используйте `object`.</span><span class="sxs-lookup"><span data-stu-id="86276-118">By convention, use `object`.</span></span>

<span data-ttu-id="86276-119">Второй аргумент обычно являлся типом, производным от `System.EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="86276-119">The second argument has typically been a type that is derived from `System.EventArgs`.</span></span> <span data-ttu-id="86276-120">(В [следующем разделе](modern-events.md) вы увидите, что это соглашение больше не является обязательным.) Даже если тип события не требует дополнительных аргументов, необходимо предоставить оба аргумента.</span><span class="sxs-lookup"><span data-stu-id="86276-120">(You'll see in the [next section](modern-events.md) that this convention is no longer enforced.) If your event type does not need any additional arguments, you will still provide both arguments.</span></span>
<span data-ttu-id="86276-121">Существует специальное значение `EventArgs.Empty`, которое следует использовать для обозначения того, что событие не содержит никаких дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="86276-121">There is a special value, `EventArgs.Empty` that you should use to denote that your event does not contain any additional information.</span></span>

<span data-ttu-id="86276-122">Создадим класс, который перечисляет соответствующие шаблону файлы в каталоге или любом из его подкаталогов.</span><span class="sxs-lookup"><span data-stu-id="86276-122">Let's build a class that lists files in a directory, or any of its subdirectories that follow a pattern.</span></span> <span data-ttu-id="86276-123">Этот компонент создает событие для каждого найденного файла, который соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="86276-123">This component raises an event for each file found that matches the pattern.</span></span>

<span data-ttu-id="86276-124">Использование модели событий обеспечивает некоторые преимущества разработки.</span><span class="sxs-lookup"><span data-stu-id="86276-124">Using an event model provides some design advantages.</span></span> <span data-ttu-id="86276-125">Можно создать несколько прослушивателей событий, которые выполняют разные действия при нахождении искомого файла.</span><span class="sxs-lookup"><span data-stu-id="86276-125">You can create multiple event listeners that perform different actions when a sought file is found.</span></span> <span data-ttu-id="86276-126">Сочетание разных прослушивателей позволяет создавать более надежные алгоритмы.</span><span class="sxs-lookup"><span data-stu-id="86276-126">Combining the different listeners can create more robust algorithms.</span></span>

<span data-ttu-id="86276-127">Ниже показано объявление аргумента исходного события для поиска искомого файла:</span><span class="sxs-lookup"><span data-stu-id="86276-127">Here is the initial event argument declaration for finding a sought file:</span></span> 

```csharp
public class FileFoundArgs : EventArgs
{
    public string FoundFile { get; }

    public FileFoundArgs(string fileName)
    {
        FoundFile = fileName;
    }
}
```

<span data-ttu-id="86276-128">Несмотря на то, что этот тип выглядит как небольшой тип, содержащий только данные, вы должны выполнить соглашение и назначить его ссылочным типом (`class`).</span><span class="sxs-lookup"><span data-stu-id="86276-128">Even though this type looks like a small, data-only type, you should follow the convention and make it a reference (`class`) type.</span></span> <span data-ttu-id="86276-129">Это означает, что объект аргумента будет передаваться по ссылке, а любые обновления данных будут доступны всем подписчикам.</span><span class="sxs-lookup"><span data-stu-id="86276-129">That means the argument object will be passed by reference, and any updates to the data will be viewed by all subscribers.</span></span> <span data-ttu-id="86276-130">Первая версия является неизменяемым объектом.</span><span class="sxs-lookup"><span data-stu-id="86276-130">The first version is an immutable object.</span></span> <span data-ttu-id="86276-131">Рекомендуется сделать свойства в типе аргумента события неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="86276-131">You should prefer to make the properties in your event argument type immutable.</span></span> <span data-ttu-id="86276-132">Таким образом, один подписчик не сможет изменить значения до того, как их увидит другой подписчик.</span><span class="sxs-lookup"><span data-stu-id="86276-132">That way, one subscriber cannot change the values before another subscriber sees them.</span></span> <span data-ttu-id="86276-133">(Существуют исключения, как можно будет увидеть ниже.)</span><span class="sxs-lookup"><span data-stu-id="86276-133">(There are exceptions to this, as you'll see below.)</span></span>  

<span data-ttu-id="86276-134">Затем нужно создать объявление события в классе FileSearcher.</span><span class="sxs-lookup"><span data-stu-id="86276-134">Next, we need to create the event declaration in the FileSearcher class.</span></span> <span data-ttu-id="86276-135">Использование типа `EventHandler<T>` означает, что вам не требуется создавать еще одно определение типа.</span><span class="sxs-lookup"><span data-stu-id="86276-135">Leveraging the `EventHandler<T>` type means that you don't need to create yet another type definition.</span></span> <span data-ttu-id="86276-136">Вы просто используете универсальную специализацию.</span><span class="sxs-lookup"><span data-stu-id="86276-136">You simply use a generic specialization.</span></span>

<span data-ttu-id="86276-137">Заполним класс FileSearcher для поиска файлов, соответствующих шаблону, и вызова правильного события при обнаружении совпадения.</span><span class="sxs-lookup"><span data-stu-id="86276-137">Let's fill out the FileSearcher class to search for files that match a pattern, and raise the correct event when a match is discovered.</span></span>

```csharp
public class FileSearcher
{
    public event EventHandler<FileFoundArgs> FileFound;

    public void Search(string directory, string searchPattern)
    {
        foreach (var file in Directory.EnumerateFiles(directory, searchPattern))
        {
            FileFound?.Invoke(this, new FileFoundArgs(file));
        }
    }
}
```

## <a name="definining-and-raising-field-like-events"></a><span data-ttu-id="86276-138">Определение и вызов событий, подобных полям</span><span class="sxs-lookup"><span data-stu-id="86276-138">Definining and Raising Field-Like Events</span></span>

<span data-ttu-id="86276-139">Самый простой способ добавить событие в класс — объявить это событие как открытое поле, как показано в приведенном выше примере.</span><span class="sxs-lookup"><span data-stu-id="86276-139">The simplest way to add an event to your class is to declare that event as a public field, as in the above example:</span></span>

```csharp
public event EventHandler<FileFoundArgs> FileFound;
```

<span data-ttu-id="86276-140">Создание открытых полей не рекомендуется в объектно-ориентированном программировании,</span><span class="sxs-lookup"><span data-stu-id="86276-140">This looks like it's declaring a public field, which would appear to be bad object oriented practice.</span></span> <span data-ttu-id="86276-141">поскольку необходимо обеспечить защиту доступа к данным с помощью свойств и методов.</span><span class="sxs-lookup"><span data-stu-id="86276-141">You want to protect data access through properties, or methods.</span></span> <span data-ttu-id="86276-142">Хотя это выглядит нарушением рекомендаций, код, созданный компилятором, создает программы-оболочки, чтобы доступ к объектам событий мог осуществляться только безопасным образом.</span><span class="sxs-lookup"><span data-stu-id="86276-142">While this make look like a bad practice, the code generated by the compiler does create wrappers so that the event objects can only be accessed in safe ways.</span></span> <span data-ttu-id="86276-143">Единственные операции, доступные для событий, подобных полям, — обработчик add:</span><span class="sxs-lookup"><span data-stu-id="86276-143">The only operations available on a field-like event are add handler:</span></span>

```csharp
EventHandler<FileFoundArgs> onFileFound = (sender, eventArgs) =>
    Console.WriteLine(eventArgs.FoundFile);
lister.FileFound += onFileFound;
```

<span data-ttu-id="86276-144">и обработчик remove:</span><span class="sxs-lookup"><span data-stu-id="86276-144">and remove handler:</span></span>

```csharp
lister.FileFound -= onFileFound;
```

<span data-ttu-id="86276-145">Обратите внимание, что для обработчика используется локальная переменная.</span><span class="sxs-lookup"><span data-stu-id="86276-145">Note that there's a local variable for the handler.</span></span> <span data-ttu-id="86276-146">Если вы используете тело лямбда-выражения, удаление не будет работать корректно.</span><span class="sxs-lookup"><span data-stu-id="86276-146">If you used the body of the lambda, the remove would not work correctly.</span></span> <span data-ttu-id="86276-147">Будет существовать другой экземпляр делегата, не выполняющий никаких действий.</span><span class="sxs-lookup"><span data-stu-id="86276-147">It would be a different instance of the delegate, and silently do nothing.</span></span>

<span data-ttu-id="86276-148">Код вне класса не может вызывать события, а также выполнять другие операции.</span><span class="sxs-lookup"><span data-stu-id="86276-148">Code outside the class cannot raise the event, nor can it perform any other operations.</span></span>

## <a name="returning-values-from-event-subscribers"></a><span data-ttu-id="86276-149">Получение возвращаемых значений от подписчиков на событие</span><span class="sxs-lookup"><span data-stu-id="86276-149">Returning Values from Event Subscribers</span></span>

<span data-ttu-id="86276-150">Простая версия работает нормально.</span><span class="sxs-lookup"><span data-stu-id="86276-150">Your simple version is working fine.</span></span> <span data-ttu-id="86276-151">Давайте добавим еще одну возможность — отмену.</span><span class="sxs-lookup"><span data-stu-id="86276-151">Let's add another feature: Cancellation.</span></span>

<span data-ttu-id="86276-152">При вызове события нахождения прослушиватели должны иметь возможность остановить дальнейшую обработку, если этот файл является последним искомым.</span><span class="sxs-lookup"><span data-stu-id="86276-152">When you raise the found event, listeners should be able to stop further processing, if this file is that last one sought.</span></span>

<span data-ttu-id="86276-153">Обработчики событий не возвращают значение, поэтому вам нужно выполнить это другим способом.</span><span class="sxs-lookup"><span data-stu-id="86276-153">The event handlers do not return a value, so you need to communicate that in another way.</span></span> <span data-ttu-id="86276-154">Стандартный шаблон события использует объект EventArgs для включения полей, которые подписчики на события могут использовать для передачи сообщения об отмене.</span><span class="sxs-lookup"><span data-stu-id="86276-154">The standard event pattern uses the EventArgs object to include fields that event subscribers can use to communicate cancel.</span></span>

<span data-ttu-id="86276-155">Для этого случая предусмотрено два разных шаблона, которые можно использовать в зависимости от семантики контракта "Отмена".</span><span class="sxs-lookup"><span data-stu-id="86276-155">There are two different patterns that could be used, based on the semantics of the Cancel contract.</span></span> <span data-ttu-id="86276-156">В обоих случаях в EventArguments добавляется логическое поле для события найденного файла.</span><span class="sxs-lookup"><span data-stu-id="86276-156">In both cases, you'll add a boolean field to the EventArguments for the found file event.</span></span> 

<span data-ttu-id="86276-157">Один шаблон позволяет любому одному подписчику отменить операцию.</span><span class="sxs-lookup"><span data-stu-id="86276-157">One pattern would allow any one subscriber to cancel the operation.</span></span>
<span data-ttu-id="86276-158">Для этого шаблона новое поле инициализируется значением `false`.</span><span class="sxs-lookup"><span data-stu-id="86276-158">For this pattern, the new field is initialized to `false`.</span></span> <span data-ttu-id="86276-159">Любой подписчик можно изменить его на `true`.</span><span class="sxs-lookup"><span data-stu-id="86276-159">Any subscriber can change it to `true`.</span></span> <span data-ttu-id="86276-160">После того как все подписчики увидят событие, компонент FileSearcher проверяет логическое значение и выполняет действие.</span><span class="sxs-lookup"><span data-stu-id="86276-160">After all subscribers have seen the event raised, the FileSearcher component examines the boolean value and takes action.</span></span>

<span data-ttu-id="86276-161">Второй шаблон отменяет операцию, только если все подписчики подтвердили ее отмену.</span><span class="sxs-lookup"><span data-stu-id="86276-161">The second pattern would only cancel the operation if all subscribers wanted the operation cancelled.</span></span> <span data-ttu-id="86276-162">В этом шаблоне новое поле инициализируется для указания того, что операцию следует отменить, и любой подписчик может изменить его, чтобы указать, что следует продолжить операцию.</span><span class="sxs-lookup"><span data-stu-id="86276-162">In this pattern, the new field is initialized to indicate the operation should cancel, and any subscriber could change it to indicate the operation should continue.</span></span>
<span data-ttu-id="86276-163">После того как все подписчики увидят событие, компонент FileSearcher проверяет логическое значение и выполняет действие.</span><span class="sxs-lookup"><span data-stu-id="86276-163">After all subscribers have seen the event raised, the FileSearcher component examines the boolean and takes action.</span></span> <span data-ttu-id="86276-164">В этом шаблоне есть еще один дополнительный шаг: компонент должен знать, все ли подписчики видели событие.</span><span class="sxs-lookup"><span data-stu-id="86276-164">There is one extra step in this pattern: the component needs to know if any subscribers have seen the event.</span></span> <span data-ttu-id="86276-165">Если подписчики отсутствуют, поле неверно сообщит об отмене.</span><span class="sxs-lookup"><span data-stu-id="86276-165">If there are no subscribers, the field would indicate a cancel incorrectly.</span></span>

<span data-ttu-id="86276-166">Реализуем первую версию для этого примера.</span><span class="sxs-lookup"><span data-stu-id="86276-166">Let's implement the first version for this sample.</span></span> <span data-ttu-id="86276-167">Вам потребуется добавить логическое поле типа FileFoundEventArgs:</span><span class="sxs-lookup"><span data-stu-id="86276-167">You need to add a boolean field to the FileFoundEventArgs type:</span></span>

```csharp
public class FileFoundArgs : EventArgs
{
    public string FoundFile { get; }
    public bool CancelRequested { get; set; }

    public FileFoundArgs(string fileName)
    {
        FoundFile = fileName;
    }
}
```

<span data-ttu-id="86276-168">Это новое поле должно быть инициализировано значением false, чтобы не выполнять отмену без причины.</span><span class="sxs-lookup"><span data-stu-id="86276-168">This new Field should be initialized to false, so you don't cancel for no reason.</span></span> <span data-ttu-id="86276-169">Это значение по умолчанию для логического поля, поэтому оно задается автоматически.</span><span class="sxs-lookup"><span data-stu-id="86276-169">That is the default value for a boolean field, so that happens automatically.</span></span> <span data-ttu-id="86276-170">Единственным другим изменением в компоненте является установка флага после вызова события для просмотра, если любой из подписчиков запросил отмену:</span><span class="sxs-lookup"><span data-stu-id="86276-170">The only other change to the component is to check the flag after raising the event to see if any of the subscribers have requested a cancellation:</span></span>

```csharp
public void List(string directory, string searchPattern)
{
    foreach (var file in Directory.EnumerateFiles(directory, searchPattern))
    {
        var args = new FileFoundArgs(file);
        FileFound?.Invoke(this, args);
        if (args.CancelRequested)
            break;
    }
}
```

<span data-ttu-id="86276-171">Одно из преимуществ этого шаблона заключается в том, что это не является критическим изменением.</span><span class="sxs-lookup"><span data-stu-id="86276-171">One advantage of this pattern is that it isn't a breaking change.</span></span>
<span data-ttu-id="86276-172">Ни один из подписчиков не запросил отмену и не запрашивает до сих пор.</span><span class="sxs-lookup"><span data-stu-id="86276-172">None of the subscribers requested a cancel before, and they still are not.</span></span> <span data-ttu-id="86276-173">Код подписчиков не требует обновления, если не требуется поддержка нового протокола отмены.</span><span class="sxs-lookup"><span data-stu-id="86276-173">None of the subscriber code needs updating unless they want to support the new cancel protocol.</span></span> <span data-ttu-id="86276-174">Они очень слабо связаны.</span><span class="sxs-lookup"><span data-stu-id="86276-174">It's very loosely coupled.</span></span>

<span data-ttu-id="86276-175">Изменим подписчик, чтобы он запрашивал отмену, когда обнаруживает первый исполняемый файл:</span><span class="sxs-lookup"><span data-stu-id="86276-175">Let's update the subscriber so that it requests a cancellation once it finds the first executable:</span></span>

```csharp
EventHandler<FileFoundArgs> onFileFound = (sender, eventArgs) =>
{
    Console.WriteLine(eventArgs.FoundFile);
    eventArgs.CancelRequested = true;
};
```

## <a name="adding-another-event-declaration"></a><span data-ttu-id="86276-176">Добавление другого объявления события</span><span class="sxs-lookup"><span data-stu-id="86276-176">Adding Another Event Declaration</span></span>

<span data-ttu-id="86276-177">Добавим еще одну возможность и продемонстрируем другие выражения языка для событий.</span><span class="sxs-lookup"><span data-stu-id="86276-177">Let's add one more feature, and demonstrate other language idioms for events.</span></span> <span data-ttu-id="86276-178">Добавим перегрузку метода `Search()`, который проходит через все подкаталоги в поиске файлов.</span><span class="sxs-lookup"><span data-stu-id="86276-178">Let's add an overload of the `Search()` method that traverses all subdirectories in search of files.</span></span>

<span data-ttu-id="86276-179">Эта операция может выполняться длительное время в каталоге с большим числом вложенных каталогов.</span><span class="sxs-lookup"><span data-stu-id="86276-179">This could get to be a lengthy operation in a directory with many sub-directories.</span></span> <span data-ttu-id="86276-180">Добавим событие, которое вызывается в начале каждого нового поиска в каталоге.</span><span class="sxs-lookup"><span data-stu-id="86276-180">Let's add an event that gets raised when each new directory search begins.</span></span> <span data-ttu-id="86276-181">Это позволяет подписчикам отслеживать ход выполнения и сообщать о нем пользователю.</span><span class="sxs-lookup"><span data-stu-id="86276-181">This enables subscribers to track progress, and update the user as to progress.</span></span> <span data-ttu-id="86276-182">Все примеры, которые мы создали до сих пор, являются открытыми.</span><span class="sxs-lookup"><span data-stu-id="86276-182">All the samples you've created so far are public.</span></span> <span data-ttu-id="86276-183">Сделаем это событие внутренним.</span><span class="sxs-lookup"><span data-stu-id="86276-183">Let's make this one an internal event.</span></span> <span data-ttu-id="86276-184">Это означает, что типы, используемые для аргументов, также можно сделать внутренними.</span><span class="sxs-lookup"><span data-stu-id="86276-184">That means you can also make the types used for the arguments internal as well.</span></span>

<span data-ttu-id="86276-185">Вы начнете с создания нового производного класса EventArgs для передачи сведений о новом каталоге и ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="86276-185">You'll start by creating the new EventArgs derived class for reporting the new directory and progress.</span></span> 

```csharp
internal class SearchDirectoryArgs : EventArgs
{
    internal string CurrentSearchDirectory { get; }
    internal int TotalDirs { get; }
    internal int CompletedDirs { get; }

    internal SearchDirectoryArgs(string dir, int totalDirs, int completedDirs)
    {
        CurrentSearchDirectory = dir;
        TotalDirs = totalDirs;
        CompletedDirs = completedDirs;
    }
}
``` 

<span data-ttu-id="86276-186">Опять же, вы можете следовать рекомендациям по созданию неизменяемого ссылочного типа для аргументов событий.</span><span class="sxs-lookup"><span data-stu-id="86276-186">Again, you can follow the recommendations to make an immutable reference type for the event arguments.</span></span>

<span data-ttu-id="86276-187">Теперь определим событие.</span><span class="sxs-lookup"><span data-stu-id="86276-187">Next, define the event.</span></span> <span data-ttu-id="86276-188">На этот раз будет использоваться другой синтаксис.</span><span class="sxs-lookup"><span data-stu-id="86276-188">This time, you'll use a different syntax.</span></span> <span data-ttu-id="86276-189">Помимо синтаксиса полей можно явно создать свойство c помощью обработчиков add и remove.</span><span class="sxs-lookup"><span data-stu-id="86276-189">In addition to using the field syntax, you can explicitly create the property, with add and remove handlers.</span></span> <span data-ttu-id="86276-190">В этом примере вам не потребуется дополнительный код в этих обработчиках в данном проекте, тем не менее здесь демонстрируется их создание.</span><span class="sxs-lookup"><span data-stu-id="86276-190">In this sample, you won't need extra code in those handlers in this project, but this shows how you would create them.</span></span>

```csharp
internal event EventHandler<SearchDirectoryArgs> DirectoryChanged
{
    add { directoryChanged += value; }
    remove { directoryChanged -= value; }
}
private EventHandler<SearchDirectoryArgs> directoryChanged;
```

<span data-ttu-id="86276-191">По большей части код, созданный здесь, отражает код, создаваемый компилятором для определения полей событий, как было показано ранее.</span><span class="sxs-lookup"><span data-stu-id="86276-191">In may ways, the code you write here mirrors the code the compiler generates for the field event definitions you've seen earlier.</span></span> <span data-ttu-id="86276-192">Для создания события используется синтаксис, очень похожий на используемый для [свойств](properties.md).</span><span class="sxs-lookup"><span data-stu-id="86276-192">You create the event using syntax very similar to that used for [properties](properties.md).</span></span> <span data-ttu-id="86276-193">Обратите внимание, что обработчики имеют разные имена: `add` и `remove`.</span><span class="sxs-lookup"><span data-stu-id="86276-193">Notice that the handlers have different names: `add` and `remove`.</span></span> <span data-ttu-id="86276-194">Они вызываются для подписки на событие или отмены подписки на событие.</span><span class="sxs-lookup"><span data-stu-id="86276-194">These are called to subscribe to the event, or unsubscribe from the event.</span></span> <span data-ttu-id="86276-195">Учтите, что вы также должны объявить закрытое резервное поле для хранения переменной событий.</span><span class="sxs-lookup"><span data-stu-id="86276-195">Notice that you also must declare a private backing field to store the event variable.</span></span> <span data-ttu-id="86276-196">Оно инициализируется значением NULL.</span><span class="sxs-lookup"><span data-stu-id="86276-196">It is initialized to null.</span></span>

<span data-ttu-id="86276-197">Теперь добавим перегрузку метода Search(), который проходит по подкаталогам и вызывает оба события.</span><span class="sxs-lookup"><span data-stu-id="86276-197">Next, let's add the overload of the Search() method that traverses subdirectories and raises both events.</span></span> <span data-ttu-id="86276-198">Для этого проще всего использовать аргумент по умолчанию для задания поиска по всем каталогам:</span><span class="sxs-lookup"><span data-stu-id="86276-198">The easiest way to accomplish this is to use a default argument to specify that you want to search all directories:</span></span>

```csharp
public void Search(string directory, string searchPattern, bool searchSubDirs = false)
{
    if (searchSubDirs)
    {
        var allDirectories = Directory.GetDirectories(directory, "*.*", SearchOption.AllDirectories);
        var completedDirs = 0;
        var totalDirs = allDirectories.Length + 1;
        foreach (var dir in allDirectories)
        {
            directoryChanged?.Invoke(this,
                new SearchDirectoryArgs(dir, totalDirs, completedDirs++));
            // Recursively search this child directory:
            SearchDirectory(dir, searchPattern);
        }
        // Include the Current Directory:
        directoryChanged?.Invoke(this,
            new SearchDirectoryArgs(directory, totalDirs, completedDirs++));
        SearchDirectory(directory, searchPattern);
    }
    else
    {
        SearchDirectory(directory, searchPattern);
    }
}

private void SearchDirectory(string directory, string searchPattern)
{
    foreach (var file in Directory.EnumerateFiles(directory, searchPattern))
    {
        var args = new FileFoundArgs(file);
        FileFound?.Invoke(this, args);
        if (args.CancelRequested)
            break;
    }
}
```

<span data-ttu-id="86276-199">На этом этапе можно запустить приложение, вызывающее перегруженный метод для поиска всех вложенных каталогов.</span><span class="sxs-lookup"><span data-stu-id="86276-199">At this point, you can run the application calling the overload for searching all sub-directories.</span></span> <span data-ttu-id="86276-200">Для нового события `ChangeDirectory` нет подписчиков, однако благодаря использованию идиомы `?.Invoke()` мы можем гарантировать правильную работу метода.</span><span class="sxs-lookup"><span data-stu-id="86276-200">There are no subscribers on the new `ChangeDirectory` event, but using the `?.Invoke()` idiom ensures that this works correctly.</span></span>

 <span data-ttu-id="86276-201">Добавим обработчик для написания строки, показывающей ход выполнения в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="86276-201">Let's add a handler to write a line that shows the progress in the console window.</span></span> 

```csharp
lister.DirectoryChanged += (sender, eventArgs) =>
{
    Console.Write($"Entering '{eventArgs.CurrentSearchDirectory}'.");
    Console.WriteLine($" {eventArgs.CompletedDirs} of {eventArgs.TotalDirs} completed...");
};
```

<span data-ttu-id="86276-202">Мы познакомились с шаблонами, которые используются во всей экосистеме .NET.</span><span class="sxs-lookup"><span data-stu-id="86276-202">You've seen patterns that are followed throughout the .NET ecosystem.</span></span>
<span data-ttu-id="86276-203">Научившись использовать эти шаблоны и соглашения, вы сможете быстро создавать код C# и .NET на основе идиом.</span><span class="sxs-lookup"><span data-stu-id="86276-203">By learning these patterns and conventions, you'll be writing idiomatic C# and .NET quickly.</span></span>

<span data-ttu-id="86276-204">Далее мы рассмотрим некоторые изменения в этих шаблонах в самой последней версии .NET.</span><span class="sxs-lookup"><span data-stu-id="86276-204">Next, you'll see some changes in these patterns in the most recent release of .NET.</span></span>

[<span data-ttu-id="86276-205">Вперед</span><span class="sxs-lookup"><span data-stu-id="86276-205">Next</span></span>](modern-events.md)
