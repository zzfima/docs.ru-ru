---
title: Группировка потоков в пул (C#)
ms.date: 07/20/2015
ms.assetid: 98ae68c1-ace8-44b9-9317-8920ac9ef2b6
ms.openlocfilehash: 42e1dcedc1897dc82bbd13f12882cbef6a5da4c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334201"
---
# <a name="thread-pooling-c"></a><span data-ttu-id="11719-102">Группировка потоков в пул (C#)</span><span class="sxs-lookup"><span data-stu-id="11719-102">Thread Pooling (C#)</span></span>
<span data-ttu-id="11719-103">*Пул потоков* — это коллекция потоков, которые могут использоваться для выполнения нескольких задач в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="11719-103">A *thread pool* is a collection of threads that can be used to perform several tasks in the background.</span></span> <span data-ttu-id="11719-104">(Базовые сведения см. в разделе [Работа с потоками (C#)](../../../../csharp/programming-guide/concepts/threading/index.md).) Это позволяет разгрузить главный поток для асинхронного выполнения других задач.</span><span class="sxs-lookup"><span data-stu-id="11719-104">(See [Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md) for background information.) This leaves the primary thread free to perform other tasks asynchronously.</span></span>  
  
 <span data-ttu-id="11719-105">Пулы потоков часто используются в серверных приложениях.</span><span class="sxs-lookup"><span data-stu-id="11719-105">Thread pools are often employed in server applications.</span></span> <span data-ttu-id="11719-106">Каждый входящий запрос назначается потоку из пула, таким образом запрос может обрабатываться асинхронно без задействования главного потока и задержки обработки последующих запросов.</span><span class="sxs-lookup"><span data-stu-id="11719-106">Each incoming request is assigned to a thread from the thread pool, so that the request can be processed asynchronously, without tying up the primary thread or delaying the processing of subsequent requests.</span></span>  
  
 <span data-ttu-id="11719-107">Когда поток в пуле завершает выполнение задачи, он возвращается в очередь ожидания, в которой может быть повторно использован.</span><span class="sxs-lookup"><span data-stu-id="11719-107">Once a thread in the pool completes its task, it is returned to a queue of waiting threads, where it can be reused.</span></span> <span data-ttu-id="11719-108">Повторное использование позволяет приложениям избежать дополнительных затрат на создание новых потоков для каждой задачи.</span><span class="sxs-lookup"><span data-stu-id="11719-108">This reuse enables applications to avoid the cost of creating a new thread for each task.</span></span>  
  
 <span data-ttu-id="11719-109">Обычно пулы имеют максимальное количество потоков.</span><span class="sxs-lookup"><span data-stu-id="11719-109">Thread pools typically have a maximum number of threads.</span></span> <span data-ttu-id="11719-110">Если все потоки заняты, дополнительные задачи помещаются в очередь, где находятся до тех пор, пока не появятся свободные потоки.</span><span class="sxs-lookup"><span data-stu-id="11719-110">If all the threads are busy, additional tasks are put in queue until they can be serviced as threads become available.</span></span>  
  
 <span data-ttu-id="11719-111">Можно реализовать собственный пул потоков, но гораздо проще использовать пул потоков, предоставляемых .NET Framework через класс <xref:System.Threading.ThreadPool>.</span><span class="sxs-lookup"><span data-stu-id="11719-111">You can implement your own thread pool, but it is easier to use the thread pool provided by the .NET Framework through the <xref:System.Threading.ThreadPool> class.</span></span>  
  
 <span data-ttu-id="11719-112">Используя группировку потоков в пул, можно вызвать метод <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> с делегатом для процедуры, которую требуется выполнить, а C# создает поток и выполнит указанную процедуру.</span><span class="sxs-lookup"><span data-stu-id="11719-112">With thread pooling, you call the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> method with a delegate for the procedure you want to run, and C# creates the thread and runs your procedure.</span></span>  
  
## <a name="thread-pooling-example"></a><span data-ttu-id="11719-113">Пример группировки потоков в пул</span><span class="sxs-lookup"><span data-stu-id="11719-113">Thread Pooling Example</span></span>  
 <span data-ttu-id="11719-114">В следующем примере показано, как можно использовать группировку потоков в пул для запуска нескольких задач.</span><span class="sxs-lookup"><span data-stu-id="11719-114">The following example shows how you can use thread pooling to start several tasks.</span></span>  
  
```csharp  
public void DoWork()  
{  
    // Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        new System.Threading.WaitCallback(SomeLongTask));  
    // Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        new System.Threading.WaitCallback(AnotherLongTask));  
}  
  
private void SomeLongTask(Object state)  
{  
    // Insert code to perform a long task.  
}  
  
private void AnotherLongTask(Object state)  
{  
    // Insert code to perform a long task.  
}  
```  
  
 <span data-ttu-id="11719-115">Одно из преимуществ группировки потоков заключается в возможности передачи аргументов в процедуру задачи в виде объекта состояния.</span><span class="sxs-lookup"><span data-stu-id="11719-115">One advantage of thread pooling is that you can pass arguments in a state object to the task procedure.</span></span> <span data-ttu-id="11719-116">Если вызываемой процедуре требуется несколько аргументов, можно привести структуру или экземпляр некоторого класса к типу данных `Object`.</span><span class="sxs-lookup"><span data-stu-id="11719-116">If the procedure you are calling requires more than one argument, you can cast a structure or an instance of a class into an `Object` data type.</span></span>  
  
## <a name="thread-pool-parameters-and-return-values"></a><span data-ttu-id="11719-117">Параметры и возвращаемые значения пула потоков</span><span class="sxs-lookup"><span data-stu-id="11719-117">Thread Pool Parameters and Return Values</span></span>  
 <span data-ttu-id="11719-118">Получение возвращаемого значения из пула потоков является не такой простой задачей.</span><span class="sxs-lookup"><span data-stu-id="11719-118">Returning values from a thread-pool thread is not straightforward.</span></span> <span data-ttu-id="11719-119">Стандартный способ получения возвращаемого значения при вызове функции использовать нельзя, поскольку помещать в очередь на выполнение в пуле потоков можно только процедуры `Sub`.</span><span class="sxs-lookup"><span data-stu-id="11719-119">The standard way of returning values from a function call is not allowed because `Sub` procedures are the only type of procedure that can be queued to a thread pool.</span></span> <span data-ttu-id="11719-120">Один из способов обеспечить передачу параметров и возвращения значений — это заключение параметров, возвращаемых значений и методов в класс-оболочку, как описано в разделе [Параметры и возвращаемые значения для многопоточных процедур (C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="11719-120">One way you can provide parameters and return values is by wrapping the parameters, return values, and methods in a wrapper class as described in [Parameters and Return Values for Multithreaded Procedures (C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span></span>  
  
 <span data-ttu-id="11719-121">Параметры и возвращаемые значения проще предоставить с помощью необязательной переменной объекта состояния `ByVal` метода <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="11719-121">An easier way to provide parameters and return values is by using the optional `ByVal` state object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="11719-122">Если эта переменная используется для передачи ссылки на экземпляр класса, члены экземпляра могут быть изменены потоком, входящим в пул потоков, и использоваться в качестве возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="11719-122">If you use this variable to pass a reference to an instance of a class, the members of the instance can be modified by the thread-pool thread and used as return values.</span></span>  
  
 <span data-ttu-id="11719-123">На первый взгляд, возможность изменения объекта, на который ссылается переданная по значению переменная, не является очевидной.</span><span class="sxs-lookup"><span data-stu-id="11719-123">At first it may not be obvious that you can modify an object referred to by a variable that is passed by value.</span></span> <span data-ttu-id="11719-124">На самом деле это возможно, потому что по значению передается только ссылка на объект.</span><span class="sxs-lookup"><span data-stu-id="11719-124">You can do this because only the object reference is passed by value.</span></span> <span data-ttu-id="11719-125">При изменении членов объекта, указанного в ссылке, изменения применяются к реальному экземпляру класса.</span><span class="sxs-lookup"><span data-stu-id="11719-125">When you make changes to members of the object referred to by the object reference, the changes apply to the actual class instance.</span></span>  
  
 <span data-ttu-id="11719-126">Структуры, входящие в состав объектов состояния, нельзя использовать для получения возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="11719-126">Structures cannot be used to return values inside state objects.</span></span> <span data-ttu-id="11719-127">Поскольку структуры являются типами, передаваемыми по значению, изменения, вносимые асинхронным процессом, не влияют на члены исходной структуры.</span><span class="sxs-lookup"><span data-stu-id="11719-127">Because structures are value types, changes that the asynchronous process makes do not change the members of the original structure.</span></span> <span data-ttu-id="11719-128">Структуры следует использовать для передачи параметров, когда не требуется получать возвращаемые значения.</span><span class="sxs-lookup"><span data-stu-id="11719-128">Use structures to provide parameters when return values are not needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11719-129">См. также</span><span class="sxs-lookup"><span data-stu-id="11719-129">See Also</span></span>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="11719-130">Практическое руководство. Использование пула потоков (C#)</span><span class="sxs-lookup"><span data-stu-id="11719-130">How to: Use a Thread Pool (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)  
 <span data-ttu-id="11719-131">[Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md) (Работа с потоками (C#))</span><span class="sxs-lookup"><span data-stu-id="11719-131">[Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md)</span></span>  
 [<span data-ttu-id="11719-132">Многопоточные приложения(C#)</span><span class="sxs-lookup"><span data-stu-id="11719-132">Multithreaded Applications (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="11719-133">Синхронизация потоков (C#)</span><span class="sxs-lookup"><span data-stu-id="11719-133">Thread Synchronization (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)
