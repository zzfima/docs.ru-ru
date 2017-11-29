---
title: "Группировка потоков в пул (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4903fb7a-eaad-435a-9add-1d1b32de3b83
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 33b89d261aa2d038926f8c7e1832436b0cd34019
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="thread-pooling-visual-basic"></a><span data-ttu-id="0c26c-102">Группировка потоков в пул (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c26c-102">Thread Pooling (Visual Basic)</span></span>
<span data-ttu-id="0c26c-103">*Пул потоков* — это коллекция потоков, которые могут использоваться для выполнения нескольких задач в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="0c26c-103">A *thread pool* is a collection of threads that can be used to perform several tasks in the background.</span></span> <span data-ttu-id="0c26c-104">(См. [потоки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) сведения общего характера.) Это позволяет разгрузить главный поток для асинхронного выполнения других задач.</span><span class="sxs-lookup"><span data-stu-id="0c26c-104">(See [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) for background information.) This leaves the primary thread free to perform other tasks asynchronously.</span></span>  
  
 <span data-ttu-id="0c26c-105">Пулы потоков часто используются в серверных приложениях.</span><span class="sxs-lookup"><span data-stu-id="0c26c-105">Thread pools are often employed in server applications.</span></span> <span data-ttu-id="0c26c-106">Каждый входящий запрос назначается потоку из пула, таким образом запрос может обрабатываться асинхронно без задействования главного потока и задержки обработки последующих запросов.</span><span class="sxs-lookup"><span data-stu-id="0c26c-106">Each incoming request is assigned to a thread from the thread pool, so that the request can be processed asynchronously, without tying up the primary thread or delaying the processing of subsequent requests.</span></span>  
  
 <span data-ttu-id="0c26c-107">Когда поток в пуле завершает выполнение задачи, он возвращается в очередь ожидания, в которой может быть повторно использован.</span><span class="sxs-lookup"><span data-stu-id="0c26c-107">Once a thread in the pool completes its task, it is returned to a queue of waiting threads, where it can be reused.</span></span> <span data-ttu-id="0c26c-108">Повторное использование позволяет приложениям избежать дополнительных затрат на создание новых потоков для каждой задачи.</span><span class="sxs-lookup"><span data-stu-id="0c26c-108">This reuse enables applications to avoid the cost of creating a new thread for each task.</span></span>  
  
 <span data-ttu-id="0c26c-109">Обычно пулы имеют максимальное количество потоков.</span><span class="sxs-lookup"><span data-stu-id="0c26c-109">Thread pools typically have a maximum number of threads.</span></span> <span data-ttu-id="0c26c-110">Если все потоки заняты, дополнительные задачи помещаются в очередь, где находятся до тех пор, пока не появятся свободные потоки.</span><span class="sxs-lookup"><span data-stu-id="0c26c-110">If all the threads are busy, additional tasks are put in queue until they can be serviced as threads become available.</span></span>  
  
 <span data-ttu-id="0c26c-111">Можно реализовать собственный пул потоков, но гораздо проще использовать пул потоков, предоставляемых .NET Framework через класс <xref:System.Threading.ThreadPool>.</span><span class="sxs-lookup"><span data-stu-id="0c26c-111">You can implement your own thread pool, but it is easier to use the thread pool provided by the .NET Framework through the <xref:System.Threading.ThreadPool> class.</span></span>  
  
 <span data-ttu-id="0c26c-112">При группировке потоков вызова <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> метод с помощью делегата для процедуры требуется запустить, и Visual Basic создает поток и запускает указанную процедуру.</span><span class="sxs-lookup"><span data-stu-id="0c26c-112">With thread pooling, you call the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> method with a delegate for the procedure you want to run, and Visual Basic creates the thread and runs your procedure.</span></span>  
  
## <a name="thread-pooling-example"></a><span data-ttu-id="0c26c-113">Пример группировки потоков в пул</span><span class="sxs-lookup"><span data-stu-id="0c26c-113">Thread Pooling Example</span></span>  
 <span data-ttu-id="0c26c-114">В следующем примере показано, как можно использовать группировку потоков в пул для запуска нескольких задач.</span><span class="sxs-lookup"><span data-stu-id="0c26c-114">The following example shows how you can use thread pooling to start several tasks.</span></span>  
  
```vb  
Public Sub DoWork()  
    ' Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf SomeLongTask))  
    ' Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf AnotherLongTask))  
End Sub  
Private Sub SomeLongTask(ByVal state As Object)  
    ' Insert code to perform a long task.  
End Sub  
Private Sub AnotherLongTask(ByVal state As Object)  
    ' Insert code to perform another long task.  
End Sub  
```  
  
 <span data-ttu-id="0c26c-115">Одно из преимуществ группировки потоков заключается в возможности передачи аргументов в процедуру задачи в виде объекта состояния.</span><span class="sxs-lookup"><span data-stu-id="0c26c-115">One advantage of thread pooling is that you can pass arguments in a state object to the task procedure.</span></span> <span data-ttu-id="0c26c-116">Если вызываемой процедуре требуется несколько аргументов, можно привести структуру или экземпляр некоторого класса к типу данных `Object`.</span><span class="sxs-lookup"><span data-stu-id="0c26c-116">If the procedure you are calling requires more than one argument, you can cast a structure or an instance of a class into an `Object` data type.</span></span>  
  
## <a name="thread-pool-parameters-and-return-values"></a><span data-ttu-id="0c26c-117">Параметры и возвращаемые значения пула потоков</span><span class="sxs-lookup"><span data-stu-id="0c26c-117">Thread Pool Parameters and Return Values</span></span>  
 <span data-ttu-id="0c26c-118">Получение возвращаемого значения из пула потоков является не такой простой задачей.</span><span class="sxs-lookup"><span data-stu-id="0c26c-118">Returning values from a thread-pool thread is not straightforward.</span></span> <span data-ttu-id="0c26c-119">Стандартный способ получения возвращаемого значения при вызове функции использовать нельзя, поскольку помещать в очередь на выполнение в пуле потоков можно только процедуры `Sub`.</span><span class="sxs-lookup"><span data-stu-id="0c26c-119">The standard way of returning values from a function call is not allowed because `Sub` procedures are the only type of procedure that can be queued to a thread pool.</span></span> <span data-ttu-id="0c26c-120">Одним из способов вы можете передачи параметров и возвращаемых значений — это заключение параметров, возвращаемых значений и методов в оболочке класса, как описано в [параметры и возвращаемые значения для многопоточных процедур (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="0c26c-120">One way you can provide parameters and return values is by wrapping the parameters, return values, and methods in a wrapper class as described in [Parameters and Return Values for Multithreaded Procedures (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span></span>  
  
 <span data-ttu-id="0c26c-121">Параметры и возвращаемые значения проще предоставить с помощью необязательной переменной объекта состояния `ByVal` метода <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c26c-121">An easer way to provide parameters and return values is by using the optional `ByVal` state object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="0c26c-122">Если эта переменная используется для передачи ссылки на экземпляр класса, члены экземпляра могут быть изменены потоком, входящим в пул потоков, и использоваться в качестве возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="0c26c-122">If you use this variable to pass a reference to an instance of a class, the members of the instance can be modified by the thread-pool thread and used as return values.</span></span>  
  
 <span data-ttu-id="0c26c-123">На первый взгляд, возможность изменения объекта, на который ссылается переданная по значению переменная, не является очевидной.</span><span class="sxs-lookup"><span data-stu-id="0c26c-123">At first it may not be obvious that you can modify an object referred to by a variable that is passed by value.</span></span> <span data-ttu-id="0c26c-124">На самом деле это возможно, потому что по значению передается только ссылка на объект.</span><span class="sxs-lookup"><span data-stu-id="0c26c-124">You can do this because only the object reference is passed by value.</span></span> <span data-ttu-id="0c26c-125">При изменении членов объекта, указанного в ссылке, изменения применяются к реальному экземпляру класса.</span><span class="sxs-lookup"><span data-stu-id="0c26c-125">When you make changes to members of the object referred to by the object reference, the changes apply to the actual class instance.</span></span>  
  
 <span data-ttu-id="0c26c-126">Структуры, входящие в состав объектов состояния, нельзя использовать для получения возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="0c26c-126">Structures cannot be used to return values inside state objects.</span></span> <span data-ttu-id="0c26c-127">Поскольку структуры являются типами, передаваемыми по значению, изменения, вносимые асинхронным процессом, не влияют на члены исходной структуры.</span><span class="sxs-lookup"><span data-stu-id="0c26c-127">Because structures are value types, changes that the asynchronous process makes do not change the members of the original structure.</span></span> <span data-ttu-id="0c26c-128">Структуры следует использовать для передачи параметров, когда не требуется получать возвращаемые значения.</span><span class="sxs-lookup"><span data-stu-id="0c26c-128">Use structures to provide parameters when return values are not needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c26c-129">См. также</span><span class="sxs-lookup"><span data-stu-id="0c26c-129">See Also</span></span>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="0c26c-130">Практическое руководство. Использование пула потоков (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c26c-130">How to: Use a Thread Pool (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)  
 <span data-ttu-id="0c26c-131">[Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) (Работа с потоками (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="0c26c-131">[Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)</span></span>  
 [<span data-ttu-id="0c26c-132">Многопоточные приложения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c26c-132">Multithreaded Applications (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="0c26c-133">Синхронизация потоков (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c26c-133">Thread Synchronization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)
