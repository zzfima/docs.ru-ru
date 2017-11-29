---
title: "Многопоточные приложения(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: b7015cfb-d506-4eac-b2f8-b2caaa9cc977
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 48b056172e3260952155eb40a1a393d86da78344
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="multithreaded-applications-c"></a><span data-ttu-id="75058-102">Многопоточные приложения(C#)</span><span class="sxs-lookup"><span data-stu-id="75058-102">Multithreaded Applications (C#)</span></span>
<span data-ttu-id="75058-103">С помощью языка C# можно создавать приложения, которые выполняют несколько задач одновременно.</span><span class="sxs-lookup"><span data-stu-id="75058-103">With C#, you can write applications that perform multiple tasks at the same time.</span></span> <span data-ttu-id="75058-104">Задачи, которые потенциально могут задержать выполнение других задач, выполняются в отдельных потоках; такой способ организации работы приложения называется *многопоточностью* или *свободным созданием потоков*.</span><span class="sxs-lookup"><span data-stu-id="75058-104">Tasks with the potential of holding up other tasks can execute on separate threads, a process known as *multithreading* or *free threading*.</span></span>  
  
 <span data-ttu-id="75058-105">Приложения, использующие многопоточность, более оперативно реагируют на действия пользователя, поскольку пользовательский интерфейс остается активным, в то время как задачи, требующие интенсивной работы процессора, выполняются в других потоках.</span><span class="sxs-lookup"><span data-stu-id="75058-105">Applications that use multithreading are more responsive to user input because the user interface stays active as processor-intensive tasks execute on separate threads.</span></span> <span data-ttu-id="75058-106">Многопоточность также эффективна при создании масштабируемых приложений, поскольку пользователь может добавлять потоки при увеличении рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="75058-106">Multithreading is also useful when you create scalable applications, because you can add threads as the workload increases.</span></span>  
  
## <a name="creating-and-using-threads"></a><span data-ttu-id="75058-107">Создание и использование потоков</span><span class="sxs-lookup"><span data-stu-id="75058-107">Creating and Using Threads</span></span>  
 <span data-ttu-id="75058-108">Если требуется больший контроль над поведением потоков приложения, можно управлять потоками самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="75058-108">If you need more control over the behavior of your application's threads, you can manage the threads yourself.</span></span> <span data-ttu-id="75058-109">Однако необходимо иметь в виду, что написание правильных многопоточных приложений может быть сложной задачей. Приложение может перестать отвечать на запросы или могут возникать временные ошибки, вызванные конфликтами.</span><span class="sxs-lookup"><span data-stu-id="75058-109">However, realize that writing correct multithreaded applications can be difficult: Your application may stop responding or experience transient errors caused by race conditions.</span></span> <span data-ttu-id="75058-110">Дополнительные сведения см. в разделе [Потокобезопасные компоненты](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).</span><span class="sxs-lookup"><span data-stu-id="75058-110">For more information, see [Thread-Safe Components](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).</span></span>  
  
 <span data-ttu-id="75058-111">Новый поток создается путем объявления переменной типа <xref:System.Threading.Thread> и вызова конструктора, которому предоставляется имя процедуры или метода, которые требуется выполнить в новом потоке.</span><span class="sxs-lookup"><span data-stu-id="75058-111">You create a new thread by declaring a variable of type <xref:System.Threading.Thread> and calling the constructor, providing the name of the procedure or method that you want to execute on the new thread.</span></span> <span data-ttu-id="75058-112">Ниже приведен пример кода.</span><span class="sxs-lookup"><span data-stu-id="75058-112">The following code provides an example.</span></span>  
  
```csharp  
System.Threading.Thread newThread =  
    new System.Threading.Thread(AMethod);  
```  
  
### <a name="starting-and-stopping-threads"></a><span data-ttu-id="75058-113">Запуск и остановка потоков</span><span class="sxs-lookup"><span data-stu-id="75058-113">Starting and Stopping Threads</span></span>  
 <span data-ttu-id="75058-114">Чтобы начать выполнение нового потока, используйте метод <xref:System.Threading.Thread.Start%2A>, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="75058-114">To start the execution of a new thread, use the <xref:System.Threading.Thread.Start%2A> method, as shown in the following code.</span></span>  
  
```csharp  
newThread.Start();  
```  
  
 <span data-ttu-id="75058-115">Чтобы остановить выполнение потока, используйте метод <xref:System.Threading.Thread.Abort%2A>, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="75058-115">To stop the execution of a thread, use the <xref:System.Threading.Thread.Abort%2A> method, as shown in the following code.</span></span>  
  
```csharp  
newThread.Abort();  
```  
  
 <span data-ttu-id="75058-116">Помимо запуска и остановки, вы также можете приостанавливать потоки с помощью метода <xref:System.Threading.Thread.Sleep%2A> или <xref:System.Threading.Thread.Suspend%2A>, возобновлять приостановленный поток с помощью метода <xref:System.Threading.Thread.Resume%2A>, а также уничтожать поток, используя метод <xref:System.Threading.Thread.Abort%2A>.</span><span class="sxs-lookup"><span data-stu-id="75058-116">Besides starting and stopping threads, you can also pause threads by calling the <xref:System.Threading.Thread.Sleep%2A> or <xref:System.Threading.Thread.Suspend%2A> method, resume a suspended thread by using the <xref:System.Threading.Thread.Resume%2A> method, and destroy a thread by using the <xref:System.Threading.Thread.Abort%2A> method</span></span>  
  
### <a name="thread-methods"></a><span data-ttu-id="75058-117">Методы управления потоками</span><span class="sxs-lookup"><span data-stu-id="75058-117">Thread Methods</span></span>  
 <span data-ttu-id="75058-118">В следующей таблице приводятся методы, с помощью которых можно управлять отдельными потоками.</span><span class="sxs-lookup"><span data-stu-id="75058-118">The following table shows some of the methods that you can use to control individual threads.</span></span>  
  
|<span data-ttu-id="75058-119">Метод</span><span class="sxs-lookup"><span data-stu-id="75058-119">Method</span></span>|<span data-ttu-id="75058-120">Действие</span><span class="sxs-lookup"><span data-stu-id="75058-120">Action</span></span>|  
|------------|------------|  
|<xref:System.Threading.Thread.Start%2A>|<span data-ttu-id="75058-121">Запускает поток.</span><span class="sxs-lookup"><span data-stu-id="75058-121">Causes a thread to start to run.</span></span>|  
|<xref:System.Threading.Thread.Sleep%2A>|<span data-ttu-id="75058-122">Приостанавливает поток на определенное время.</span><span class="sxs-lookup"><span data-stu-id="75058-122">Pauses a thread for a specified time.</span></span>|  
|<xref:System.Threading.Thread.Suspend%2A>|<span data-ttu-id="75058-123">Приостанавливает поток, когда он достигает безопасной точки.</span><span class="sxs-lookup"><span data-stu-id="75058-123">Pauses a thread when it reaches a safe point.</span></span>|  
|<xref:System.Threading.Thread.Abort%2A>|<span data-ttu-id="75058-124">Останавливает поток, когда он достигает безопасной точки.</span><span class="sxs-lookup"><span data-stu-id="75058-124">Stops a thread when it reaches a safe point.</span></span>|  
|<xref:System.Threading.Thread.Resume%2A>|<span data-ttu-id="75058-125">Возобновляет работу приостановленного потока.</span><span class="sxs-lookup"><span data-stu-id="75058-125">Restarts a suspended thread</span></span>|  
|<xref:System.Threading.Thread.Join%2A>|<span data-ttu-id="75058-126">Приостанавливает текущий поток до тех пор, пока не будет завершен другой поток.</span><span class="sxs-lookup"><span data-stu-id="75058-126">Causes the current thread to wait for another thread to finish.</span></span> <span data-ttu-id="75058-127">При заданном времени ожидания этот метод возвращает значение `True` при условии, что другой поток закончится за это время.</span><span class="sxs-lookup"><span data-stu-id="75058-127">If used with a time-out value, this method returns `True` if the thread finishes in the allocated time.</span></span>|  
  
### <a name="safe-points"></a><span data-ttu-id="75058-128">Безопасные точки</span><span class="sxs-lookup"><span data-stu-id="75058-128">Safe Points</span></span>  
 <span data-ttu-id="75058-129">Названия этих методов говорят сами за себя, однако концепция *безопасных точек* может оказаться новой для пользователя.</span><span class="sxs-lookup"><span data-stu-id="75058-129">Most of these methods are self-explanatory, but the concept of *safe points* may be new to you.</span></span> <span data-ttu-id="75058-130">Безопасные точки располагаются в тех местах кода, в которых среда CLR может безопасно выполнить автоматическую *сборку мусора* — процесс уничтожения неиспользуемых переменных и освобождения памяти.</span><span class="sxs-lookup"><span data-stu-id="75058-130">Safe points are locations in code where it is safe for the common language runtime to perform automatic *garbage collection*, the process of releasing unused variables and reclaiming memory.</span></span> <span data-ttu-id="75058-131">При вызове методов потока <xref:System.Threading.Thread.Abort%2A> или <xref:System.Threading.Thread.Suspend%2A> среда CLR анализирует код и определяет подходящее место для остановки потока.</span><span class="sxs-lookup"><span data-stu-id="75058-131">When you call the <xref:System.Threading.Thread.Abort%2A> or <xref:System.Threading.Thread.Suspend%2A> method of a thread, the common language runtime analyzes the code and determines the location of an appropriate location for the thread to stop running.</span></span>  
  
### <a name="thread-properties"></a><span data-ttu-id="75058-132">Свойства потока</span><span class="sxs-lookup"><span data-stu-id="75058-132">Thread Properties</span></span>  
 <span data-ttu-id="75058-133">Потоки также имеют несколько полезных свойств, которые приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="75058-133">Threads also contain several useful properties, as shown in the following table:</span></span>  
  
|<span data-ttu-id="75058-134">Свойство</span><span class="sxs-lookup"><span data-stu-id="75058-134">Property</span></span>|<span data-ttu-id="75058-135">Значение</span><span class="sxs-lookup"><span data-stu-id="75058-135">Value</span></span>|  
|--------------|-----------|  
|<xref:System.Threading.Thread.IsAlive%2A>|<span data-ttu-id="75058-136">Содержит значение `True`, если поток активен.</span><span class="sxs-lookup"><span data-stu-id="75058-136">Contains the value `True` if a thread is active.</span></span>|  
|<xref:System.Threading.Thread.IsBackground%2A>|<span data-ttu-id="75058-137">Возвращает или задает логическое значение, которое указывает, является ли поток (должен ли являться) фоновым потоком.</span><span class="sxs-lookup"><span data-stu-id="75058-137">Gets or sets a Boolean that indicates if a thread is or should be a background thread.</span></span> <span data-ttu-id="75058-138">Фоновые потоки отличаются от основного потока лишь тем, что они не влияют на завершение процесса.</span><span class="sxs-lookup"><span data-stu-id="75058-138">Background threads are like foreground threads, but a background thread does not prevent a process from stopping.</span></span> <span data-ttu-id="75058-139">Когда обработка всех основных потоков закончена, общеязыковая среда выполнения завершает процесс, применяя метод <xref:System.Threading.Thread.Abort%2A> к тем фоновым потокам, которые еще продолжают существовать.</span><span class="sxs-lookup"><span data-stu-id="75058-139">Once all foreground threads that belong to a process have stopped, the common language runtime ends the process by calling the <xref:System.Threading.Thread.Abort%2A> method on background threads that are still alive.</span></span>|  
|<xref:System.Threading.Thread.Name%2A>|<span data-ttu-id="75058-140">Возвращает или задает имя потока.</span><span class="sxs-lookup"><span data-stu-id="75058-140">Gets or sets the name of a thread.</span></span> <span data-ttu-id="75058-141">Наиболее часто используется для обнаружения отдельных потоков при отладке.</span><span class="sxs-lookup"><span data-stu-id="75058-141">Most frequently used to discover individual threads when you debug.</span></span>|  
|<xref:System.Threading.Thread.Priority%2A>|<span data-ttu-id="75058-142">Возвращает или задает значение, которое используется операционной системой для установки приоритетов потоков.</span><span class="sxs-lookup"><span data-stu-id="75058-142">Gets or sets a value that is used by the operating system to prioritize thread scheduling.</span></span>|  
|<xref:System.Threading.Thread.ThreadState%2A>|<span data-ttu-id="75058-143">Содержит значение, описывающее состояние или состояния потока.</span><span class="sxs-lookup"><span data-stu-id="75058-143">Contains a value that describes a thread's state or states.</span></span>|  
  
## <a name="thread-priorities"></a><span data-ttu-id="75058-144">Приоритеты потоков</span><span class="sxs-lookup"><span data-stu-id="75058-144">Thread Priorities</span></span>  
 <span data-ttu-id="75058-145">Каждый поток имеет приоритетное свойство, которое определяет, какую часть процессорного времени он должен занять при выполнении.</span><span class="sxs-lookup"><span data-stu-id="75058-145">Every thread has a priority property that determines how big or small a slice of processor time it has to execute.</span></span> <span data-ttu-id="75058-146">Операционная система выделяет более длинные отрезки времени на потоки с высоким приоритетом и более короткие отрезки времени потоки с низким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="75058-146">The operating system allocates longer time slices to high-priority threads and shorter time slices to low-priority threads.</span></span> <span data-ttu-id="75058-147">Новые потоки создаются со значением `Normal`, однако вы можете присвоить свойству <xref:System.Threading.Thread.Priority%2A> любое значение из перечисления <xref:System.Threading.ThreadPriority>.</span><span class="sxs-lookup"><span data-stu-id="75058-147">New threads are created with the value of `Normal`, but you can change the <xref:System.Threading.Thread.Priority%2A> property to any value in the <xref:System.Threading.ThreadPriority> enumeration.</span></span>  
  
 <span data-ttu-id="75058-148">Подробное описание приоритетов потоков см. в разделе <xref:System.Threading.ThreadPriority>.</span><span class="sxs-lookup"><span data-stu-id="75058-148">See <xref:System.Threading.ThreadPriority> for a detailed description of the various thread priorities.</span></span>  
  
## <a name="foreground-and-background-threads"></a><span data-ttu-id="75058-149">Основные и фоновые потоки</span><span class="sxs-lookup"><span data-stu-id="75058-149">Foreground and Background Threads</span></span>  
 <span data-ttu-id="75058-150">*Основной поток* выполняется бесконечно, тогда как *фоновый поток* останавливается сразу после остановки последнего основного потока.</span><span class="sxs-lookup"><span data-stu-id="75058-150">A *foreground thread* runs indefinitely, whereas a *background thread* stops as soon as the last foreground thread has stopped.</span></span> <span data-ttu-id="75058-151">Для определения или изменения фонового статуса потока можно использовать свойство <xref:System.Threading.Thread.IsBackground%2A>.</span><span class="sxs-lookup"><span data-stu-id="75058-151">You can use the <xref:System.Threading.Thread.IsBackground%2A> property to determine or change the background status of a thread.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75058-152">См. также</span><span class="sxs-lookup"><span data-stu-id="75058-152">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="75058-153">Синхронизация потоков (C#)</span><span class="sxs-lookup"><span data-stu-id="75058-153">Thread Synchronization (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
 [<span data-ttu-id="75058-154">Параметры и возвращаемые значения для многопоточных процедур (C#)</span><span class="sxs-lookup"><span data-stu-id="75058-154">Parameters and Return Values for Multithreaded Procedures (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)  
 <span data-ttu-id="75058-155">[Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md) (Работа с потоками (C#))</span><span class="sxs-lookup"><span data-stu-id="75058-155">[Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md)</span></span>
