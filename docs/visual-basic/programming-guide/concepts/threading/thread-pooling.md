---
title: "Группировка потоков в пул (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 4903fb7a-eaad-435a-9add-1d1b32de3b83
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: eea7c94dffe525bb36c677bf3414f25ed0210074
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="thread-pooling-visual-basic"></a><span data-ttu-id="c6ec8-102">Группировка потоков в пул (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6ec8-102">Thread Pooling (Visual Basic)</span></span>
<span data-ttu-id="c6ec8-103">Объект *пул потоков* — это коллекция потоков, которые могут использоваться для выполнения нескольких задач в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-103">A *thread pool* is a collection of threads that can be used to perform several tasks in the background.</span></span> <span data-ttu-id="c6ec8-104">(См. [потоки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) сведения общего характера.) Это оставляет главный поток для асинхронного выполнения других задач.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-104">(See [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) for background information.) This leaves the primary thread free to perform other tasks asynchronously.</span></span>  
  
 <span data-ttu-id="c6ec8-105">Пулы потоков часто используются в серверных приложениях.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-105">Thread pools are often employed in server applications.</span></span> <span data-ttu-id="c6ec8-106">Каждый входящий запрос назначается потоку из пула потоков, таким образом, запрос может обрабатываться асинхронно, без прерывания основного потока и задержки обработки последующих запросов.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-106">Each incoming request is assigned to a thread from the thread pool, so that the request can be processed asynchronously, without tying up the primary thread or delaying the processing of subsequent requests.</span></span>  
  
 <span data-ttu-id="c6ec8-107">Когда поток в пуле завершает выполнение задачи, возвращается в очередь ожидающих потоков, где он может быть повторно использован.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-107">Once a thread in the pool completes its task, it is returned to a queue of waiting threads, where it can be reused.</span></span> <span data-ttu-id="c6ec8-108">Повторное использование позволяет приложениям избежать затрат на создание новых потоков для каждой задачи.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-108">This reuse enables applications to avoid the cost of creating a new thread for each task.</span></span>  
  
 <span data-ttu-id="c6ec8-109">Обычно пулы имеют максимальное количество потоков.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-109">Thread pools typically have a maximum number of threads.</span></span> <span data-ttu-id="c6ec8-110">Если все потоки заняты, дополнительные задачи помещаются в очередь, пока они могут обслуживаться как потоки становятся доступными.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-110">If all the threads are busy, additional tasks are put in queue until they can be serviced as threads become available.</span></span>  
  
 <span data-ttu-id="c6ec8-111">Можно реализовать собственный пул потоков, но проще использовать пул потоков, предоставляемых .NET Framework с помощью <xref:System.Threading.ThreadPool>класса.</xref:System.Threading.ThreadPool></span><span class="sxs-lookup"><span data-stu-id="c6ec8-111">You can implement your own thread pool, but it is easier to use the thread pool provided by the .NET Framework through the <xref:System.Threading.ThreadPool> class.</span></span>  
  
 <span data-ttu-id="c6ec8-112">При группировке потоков вызвать <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName>метод с помощью делегата для процедуры требуется запустить, и Visual Basic создает поток и запускает указанную процедуру.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c6ec8-112">With thread pooling, you call the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName> method with a delegate for the procedure you want to run, and Visual Basic creates the thread and runs your procedure.</span></span>  
  
## <a name="thread-pooling-example"></a><span data-ttu-id="c6ec8-113">Пример группировки потоков</span><span class="sxs-lookup"><span data-stu-id="c6ec8-113">Thread Pooling Example</span></span>  
 <span data-ttu-id="c6ec8-114">В следующем примере показано, как можно использовать группировку потоков для запуска нескольких задач.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-114">The following example shows how you can use thread pooling to start several tasks.</span></span>  
  
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
  
 <span data-ttu-id="c6ec8-115">Одно из преимуществ группировки потоков — можно передать аргументы в виде объекта процедуры.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-115">One advantage of thread pooling is that you can pass arguments in a state object to the task procedure.</span></span> <span data-ttu-id="c6ec8-116">Если вызываемой процедуре требуется нескольких аргументов, можно привести структуру или экземпляр класса в `Object` тип данных.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-116">If the procedure you are calling requires more than one argument, you can cast a structure or an instance of a class into an `Object` data type.</span></span>  
  
## <a name="thread-pool-parameters-and-return-values"></a><span data-ttu-id="c6ec8-117">Параметры пула потоков и возвращаемые значения</span><span class="sxs-lookup"><span data-stu-id="c6ec8-117">Thread Pool Parameters and Return Values</span></span>  
 <span data-ttu-id="c6ec8-118">Получение возвращаемых значений от поток из пула потоков не является простой задачей.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-118">Returning values from a thread-pool thread is not straightforward.</span></span> <span data-ttu-id="c6ec8-119">Стандартный способ получения возвращаемого значения при вызове функции не допускается, поскольку `Sub` процедуры — это единственный тип процедуры, которые могут быть поставлены в очередь в пул потоков.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-119">The standard way of returning values from a function call is not allowed because `Sub` procedures are the only type of procedure that can be queued to a thread pool.</span></span> <span data-ttu-id="c6ec8-120">Один из способов можно указать параметры и возврата значений — это заключение параметров, возвращаемых значений и методов в оболочку класса, как описано в [параметры и возвращаемые значения для многопоточных процедур (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c6ec8-120">One way you can provide parameters and return values is by wrapping the parameters, return values, and methods in a wrapper class as described in [Parameters and Return Values for Multithreaded Procedures (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span></span>  
  
 <span data-ttu-id="c6ec8-121">Более простым способом передачи параметров и возвращаемых значений является использование необязательной `ByVal` объекта <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>метод.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span><span class="sxs-lookup"><span data-stu-id="c6ec8-121">An easer way to provide parameters and return values is by using the optional `ByVal` state object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="c6ec8-122">Если эта переменная используется для передачи ссылки на экземпляр класса, члены экземпляра можно изменить потоком пула потоков и используется в качестве возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-122">If you use this variable to pass a reference to an instance of a class, the members of the instance can be modified by the thread-pool thread and used as return values.</span></span>  
  
 <span data-ttu-id="c6ec8-123">Поначалу может оказаться очевидно, что можно изменить объект, на который ссылается переменная, который передается по значению.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-123">At first it may not be obvious that you can modify an object referred to by a variable that is passed by value.</span></span> <span data-ttu-id="c6ec8-124">Это можно сделать, поскольку только ссылка на объект передается по значению.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-124">You can do this because only the object reference is passed by value.</span></span> <span data-ttu-id="c6ec8-125">При изменении членов объекта, указанного в ссылке, изменения применяются к реальному экземпляру класса.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-125">When you make changes to members of the object referred to by the object reference, the changes apply to the actual class instance.</span></span>  
  
 <span data-ttu-id="c6ec8-126">Структуры не может использоваться для возврата значения, входящие в состав объектов.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-126">Structures cannot be used to return values inside state objects.</span></span> <span data-ttu-id="c6ec8-127">Поскольку структуры являются типами значений, изменения, вносимые асинхронным процессом, не изменяйте элементы исходной структуры.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-127">Because structures are value types, changes that the asynchronous process makes do not change the members of the original structure.</span></span> <span data-ttu-id="c6ec8-128">Используйте структуры для предоставления параметров, когда возвращаемые значения не требуется.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-128">Use structures to provide parameters when return values are not needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6ec8-129">См. также</span><span class="sxs-lookup"><span data-stu-id="c6ec8-129">See Also</span></span>  
 <span data-ttu-id="c6ec8-130"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span><span class="sxs-lookup"><span data-stu-id="c6ec8-130"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span></span>   
 <span data-ttu-id="c6ec8-131"><xref:System.Threading></xref:System.Threading></span><span class="sxs-lookup"><span data-stu-id="c6ec8-131"><xref:System.Threading></span></span>   
 <span data-ttu-id="c6ec8-132"><xref:System.Threading.ThreadPool></xref:System.Threading.ThreadPool></span><span class="sxs-lookup"><span data-stu-id="c6ec8-132"><xref:System.Threading.ThreadPool></span></span>   
<span data-ttu-id="c6ec8-133"> [Практическое руководство: использование пула потоков (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md) </span><span class="sxs-lookup"><span data-stu-id="c6ec8-133"> [How to: Use a Thread Pool (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md) </span></span>  
<span data-ttu-id="c6ec8-134"> [Работа с потоками (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span><span class="sxs-lookup"><span data-stu-id="c6ec8-134"> [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span></span>  
<span data-ttu-id="c6ec8-135"> [Многопоточные приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span><span class="sxs-lookup"><span data-stu-id="c6ec8-135"> [Multithreaded Applications (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span></span>  
<span data-ttu-id="c6ec8-136"> [Синхронизация потоков (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="c6ec8-136"> [Thread Synchronization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)</span></span>
