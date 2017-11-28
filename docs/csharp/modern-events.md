---
title: "Обновленный шаблон событий .NET Core"
description: "Сведения о том, за счет чего шаблон событий .NET Core обеспечивает гибкость и обратную совместимость, а также о способах реализации безопасной обработки событий с использованием асинхронных подписчиков."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 9aa627c3-3222-4094-9ca8-7e88e1071e06
ms.openlocfilehash: cf69cbe0a7adbd274d1cb9e9544dda77d9fa1740
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="the-updated-net-core-event-pattern"></a><span data-ttu-id="27718-104">Обновленный шаблон событий .NET Core</span><span class="sxs-lookup"><span data-stu-id="27718-104">The Updated .NET Core Event Pattern</span></span>

[<span data-ttu-id="27718-105">Назад</span><span class="sxs-lookup"><span data-stu-id="27718-105">Previous</span></span>](event-pattern.md)

<span data-ttu-id="27718-106">В предыдущей статье рассматривались наиболее распространенные шаблоны событий.</span><span class="sxs-lookup"><span data-stu-id="27718-106">The previous article discussed the most common event patterns.</span></span> <span data-ttu-id="27718-107">.NET Core имеет менее жесткий шаблон.</span><span class="sxs-lookup"><span data-stu-id="27718-107">.NET Core has a more relaxed pattern.</span></span> <span data-ttu-id="27718-108">В этой версии определение `EventHandler<TEventArgs>` больше не имеет ограничения, указывающего на то, что `TEventArgs` должен быть классом, производным от `System.EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="27718-108">In this version, the `EventHandler<TEventArgs>` definition no longer has the constraint that `TEventArgs` must be a class derived from `System.EventArgs`.</span></span>

<span data-ttu-id="27718-109">В результате повышается гибкость разработки и обеспечивается обратная совместимость.</span><span class="sxs-lookup"><span data-stu-id="27718-109">This increases flexibility for you, and is backwards compatible.</span></span> <span data-ttu-id="27718-110">Начнем с гибких возможностей.</span><span class="sxs-lookup"><span data-stu-id="27718-110">Let's start with the flexibility.</span></span> <span data-ttu-id="27718-111">Класс System.EventArgs представляет один метод: `MemberwiseClone()`, который создает неполную копию объекта.</span><span class="sxs-lookup"><span data-stu-id="27718-111">The class System.EventArgs introduces one method: `MemberwiseClone()`, which creates a shallow copy of the object.</span></span>
<span data-ttu-id="27718-112">Чтобы реализовать свою функциональность для любого класса, производного от `EventArgs`, этот метод должен использовать отражение.</span><span class="sxs-lookup"><span data-stu-id="27718-112">That method must use reflection in order to implement its functionality for any class derived from `EventArgs`.</span></span> <span data-ttu-id="27718-113">Функциональность проще создать в определенном производном классе.</span><span class="sxs-lookup"><span data-stu-id="27718-113">That functionality is easier to create in a specific derived class.</span></span> <span data-ttu-id="27718-114">Это фактически означает, что наследование от System.EventArgs является ограничением, которое регламентирует разработки, но не предоставляет никаких дополнительных преимуществ.</span><span class="sxs-lookup"><span data-stu-id="27718-114">That effectively means that deriving from System.EventArgs is a constraint that limits your designs, but does not provide any additional benefit.</span></span>
<span data-ttu-id="27718-115">На самом деле, можно изменить определения `FileFoundArgs` и `SearchDirectoryArgs` так, чтобы они не были производными от `EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="27718-115">In fact, you can changes the definitions of `FileFoundArgs` and `SearchDirectoryArgs` so that they do not derive from `EventArgs`.</span></span>
<span data-ttu-id="27718-116">Программа будет работать точно так же.</span><span class="sxs-lookup"><span data-stu-id="27718-116">The program will work exactly the same.</span></span>

<span data-ttu-id="27718-117">Можно также изменить `SearchDirectoryArgs` на структуру, если выполнить дополнительное изменение.</span><span class="sxs-lookup"><span data-stu-id="27718-117">You could also change the `SearchDirectoryArgs` to a struct, if you also make one more change:</span></span>

```csharp  
internal struct SearchDirectoryArgs  
{  
    internal string CurrentSearchDirectory { get; }  
    internal int TotalDirs { get; }  
    internal int CompletedDirs { get; }  
    
    internal SearchDirectoryArgs(string dir, int totalDirs, 
        int completedDirs) : this()  
    {  
        CurrentSearchDirectory = dir;  
        TotalDirs = totalDirs;  
        CompletedDirs = completedDirs;  
    }  
}  
```   

<span data-ttu-id="27718-118">Оно заключается в вызове конструктора по умолчанию перед открытием конструктора, который инициализирует все поля.</span><span class="sxs-lookup"><span data-stu-id="27718-118">The additional change is to call the default constructor before entering the constructor that initializes all the fields.</span></span> <span data-ttu-id="27718-119">Без этого согласно правилам языка C# будет выведено сообщение о получении доступа к свойствам до их назначения.</span><span class="sxs-lookup"><span data-stu-id="27718-119">Without that addition, the rules of C# would report that the properties are being accessed before they have been assigned.</span></span>

<span data-ttu-id="27718-120">Не следует изменять `FileFoundArgs` с класса (ссылочный тип) на структуру (тип значения).</span><span class="sxs-lookup"><span data-stu-id="27718-120">You should not change the `FileFoundArgs` from a class (reference type) to a struct (value type).</span></span> <span data-ttu-id="27718-121">Это связано с тем, что протокол для обработки отмены требует передачи аргументов события по ссылке.</span><span class="sxs-lookup"><span data-stu-id="27718-121">That's because the protocol for handling cancel requires that the event arguments are passed by reference.</span></span> <span data-ttu-id="27718-122">Если вы выполнили то же изменение, класс поиска файла никогда не сможет отслеживать изменения, внесенные подписчиками событий.</span><span class="sxs-lookup"><span data-stu-id="27718-122">If you made the same change, the file search class could never observe any changes made by any of the event subscribers.</span></span> <span data-ttu-id="27718-123">Для каждого подписчика будет использоваться новая копия, которая будет отличаться от той, которую обнаружил объект поиска файла.</span><span class="sxs-lookup"><span data-stu-id="27718-123">A new copy of the structure would be used for each subscriber, and that copy would be a different copy than the one seen by the file search object.</span></span>

<span data-ttu-id="27718-124">Теперь давайте рассмотрим обратную совместимость этого изменения.</span><span class="sxs-lookup"><span data-stu-id="27718-124">Next, let's consider how this change can be backwards compatible.</span></span>
<span data-ttu-id="27718-125">Удаление ограничения не влияет на существующий код.</span><span class="sxs-lookup"><span data-stu-id="27718-125">The removal of the constraint does not affect any existing code.</span></span> <span data-ttu-id="27718-126">Все имеющиеся типы аргументов событий по-прежнему являются производными от `System.EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="27718-126">Any existing event argument types do still derive from `System.EventArgs`.</span></span>
<span data-ttu-id="27718-127">Обратная совместимость является одной из основных причин, по которой они будут и далее являться производными от `System.EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="27718-127">Backwards compatibility is one major reason why they will continue to derive from `System.EventArgs`.</span></span> <span data-ttu-id="27718-128">Все существующие подписчики на события будут подписчиками на событие, следующее классическому шаблону.</span><span class="sxs-lookup"><span data-stu-id="27718-128">Any existing event subscribers will be subscribers to an event that followed the classic pattern.</span></span>

<span data-ttu-id="27718-129">Согласно аналогичной логике, теперь тип события аргумента не будет иметь подписчиков в существующих базах кода.</span><span class="sxs-lookup"><span data-stu-id="27718-129">Following similar logic, any event argument type created now would not have any subscribers in any existing codebases.</span></span> <span data-ttu-id="27718-130">Новые типы событий, которые не являются производными от `System.EventArgs`, не нарушат функциональность этих баз кода.</span><span class="sxs-lookup"><span data-stu-id="27718-130">New event types that do not derive from `System.EventArgs` will not break those codebases.</span></span>

## <a name="events-with-async-subscribers"></a><span data-ttu-id="27718-131">События с асинхронными подписчиками</span><span class="sxs-lookup"><span data-stu-id="27718-131">Events with Async subscribers</span></span>

<span data-ttu-id="27718-132">Вам осталось изучить последний шаблон: как правильно написать подписчики событий, которые вызывают асинхронный код.</span><span class="sxs-lookup"><span data-stu-id="27718-132">You have one final pattern to learn: How to correctly write event subscribers that call async code.</span></span> <span data-ttu-id="27718-133">Это описано в статье, посвященной [async и await](async.md).</span><span class="sxs-lookup"><span data-stu-id="27718-133">The challenge is described in the article on [async and await](async.md).</span></span> <span data-ttu-id="27718-134">Асинхронные методы могут иметь возвращаемый тип void, однако это крайне не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="27718-134">Async methods can have a void return type, but that is strongly discouraged.</span></span> <span data-ttu-id="27718-135">Когда код подписчика событий вызывает асинхронный метод, вам придется создать метод `async void`.</span><span class="sxs-lookup"><span data-stu-id="27718-135">When your event subscriber code calls an async method, you have no choice but to create an `async void` method.</span></span> <span data-ttu-id="27718-136">Это необходимо для сигнатуры обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="27718-136">The event handler signature requires it.</span></span>

<span data-ttu-id="27718-137">Вы должны найти правильное решение.</span><span class="sxs-lookup"><span data-stu-id="27718-137">You need to reconcile this opposing guidance.</span></span> <span data-ttu-id="27718-138">Каким-то образом необходимо создать безопасный метод `async void`.</span><span class="sxs-lookup"><span data-stu-id="27718-138">Somehow, you must create a safe `async void` method.</span></span> <span data-ttu-id="27718-139">Ниже приведены основные сведения о шаблоне, которым необходимо следовать.</span><span class="sxs-lookup"><span data-stu-id="27718-139">The basics of the pattern you need to implement are below:</span></span>

```csharp
worker.StartWorking += async (sender, eventArgs) =>
{
    try 
    {
        await DoWorkAsync();
    }
    catch (Exception e)
    {
        //Some form of logging.
        Console.WriteLine($"Async task failure: {e.ToString()}");
        // Consider gracefully, and quickly exiting.
    }
};
```

<span data-ttu-id="27718-140">Во-первых, обратите внимание на то, что обработчик помечен как асинхронный обработчик.</span><span class="sxs-lookup"><span data-stu-id="27718-140">First, notice that the handler is marked as an async handler.</span></span> <span data-ttu-id="27718-141">Поскольку он назначается типу делегата обработчика событий, он будет иметь возвращаемый тип void.</span><span class="sxs-lookup"><span data-stu-id="27718-141">Because it is being assigned to an event handler delegate type, it will have a void return type.</span></span> <span data-ttu-id="27718-142">Это означает, что необходимо следовать шаблону, приведенному в обработчике, и не допускать создания исключений вне контекста асинхронного обработчика.</span><span class="sxs-lookup"><span data-stu-id="27718-142">That means you must follow the pattern shown in the handler, and not allow any exceptions to be thrown out of the context of the async handler.</span></span> <span data-ttu-id="27718-143">Поскольку он не возвращает задачу, ничто не сообщает об ошибке при переходе в состояние сбоя.</span><span class="sxs-lookup"><span data-stu-id="27718-143">Because it does not return a task, there is no task that can report the error by entering the faulted state.</span></span> <span data-ttu-id="27718-144">Поскольку метод является асинхронным, он просто не может создать исключение.</span><span class="sxs-lookup"><span data-stu-id="27718-144">Because the method is async, the method can't simply throw the exception.</span></span> <span data-ttu-id="27718-145">(Вызывающий метод продолжал выполнение, так как это `async`.) Фактическое поведение во время выполнения будет определяться по-разному для разных сред.</span><span class="sxs-lookup"><span data-stu-id="27718-145">(The calling method has continued execution because it is `async`.) The actual runtime behavior will be defined differently for different environments.</span></span> <span data-ttu-id="27718-146">Оно может прекратить работу потока, завершить выполнение программы или оставить программу в неопределенном состоянии.</span><span class="sxs-lookup"><span data-stu-id="27718-146">It may terminate the thread, it may terminate the program, or it may leave the program in an undetermined state.</span></span> <span data-ttu-id="27718-147">Ничто из этого не является хорошим результатом.</span><span class="sxs-lookup"><span data-stu-id="27718-147">None of those are good outcomes.</span></span>

<span data-ttu-id="27718-148">Вот почему необходимо заключить оператор await для асинхронных задач в собственный блок try.</span><span class="sxs-lookup"><span data-stu-id="27718-148">That's why you should wrap the await statement for the async Task in your own try block.</span></span> <span data-ttu-id="27718-149">Если он приводит к сбою задачи, можно записать ошибку в журнал.</span><span class="sxs-lookup"><span data-stu-id="27718-149">If it does cause a faulted task, you can log the error.</span></span> <span data-ttu-id="27718-150">Если это ошибка, из-за которой невозможно восстановить приложение, можно быстро и правильно выйти из программы.</span><span class="sxs-lookup"><span data-stu-id="27718-150">If it is an error from which your application cannot recover, you can exit the program quickly and gracefully</span></span>

<span data-ttu-id="27718-151">Это были основные обновления шаблона событий .NET.</span><span class="sxs-lookup"><span data-stu-id="27718-151">Those are the major updates to the .NET event pattern.</span></span> <span data-ttu-id="27718-152">Затем вы увидите множество примеров предыдущих версий в библиотеках, с которыми вы работаете.</span><span class="sxs-lookup"><span data-stu-id="27718-152">You will see many examples of the earlier versions in the libraries you work with.</span></span> <span data-ttu-id="27718-153">Однако также необходимо иметь представление и о последних шаблонах.</span><span class="sxs-lookup"><span data-stu-id="27718-153">However, you should understand what the latest patterns are as well.</span></span>

<span data-ttu-id="27718-154">В следующей статье этой серии материалов вы узнаете об использовании `delegates` и `events` в своих проектах.</span><span class="sxs-lookup"><span data-stu-id="27718-154">The next article in this series helps you distinguish between using `delegates` and `events` in your designs.</span></span> <span data-ttu-id="27718-155">Это относительно схожие понятия, и сведения в этой статье помогут вам принять оптимальное решение.</span><span class="sxs-lookup"><span data-stu-id="27718-155">They are similar concepts, and that article will help you make the best decision for your programs.</span></span>

[<span data-ttu-id="27718-156">Далее</span><span class="sxs-lookup"><span data-stu-id="27718-156">Next</span></span>](distinguish-delegates-events.md)
