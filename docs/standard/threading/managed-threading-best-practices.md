---
title: Рекомендации по работе с потоками
ms.date: 10/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threading [.NET Framework], design guidelines
- threading [.NET Framework], best practices
- managed threading
ms.assetid: e51988e7-7f4b-4646-a06d-1416cee8d557
ms.openlocfilehash: 26b0535fa918a802dd0922554ae197ba10396d56
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129564"
---
# <a name="managed-threading-best-practices"></a><span data-ttu-id="11d04-102">Рекомендации по работе с потоками</span><span class="sxs-lookup"><span data-stu-id="11d04-102">Managed threading best practices</span></span>
<span data-ttu-id="11d04-103">Многопоточность требует тщательного программирования.</span><span class="sxs-lookup"><span data-stu-id="11d04-103">Multithreading requires careful programming.</span></span> <span data-ttu-id="11d04-104">Большинство задач можно упростить, поместив запросы на выполнение в очередь по потокам пулов потоков.</span><span class="sxs-lookup"><span data-stu-id="11d04-104">For most tasks, you can reduce complexity by queuing requests for execution by thread pool threads.</span></span> <span data-ttu-id="11d04-105">В этом разделе рассматриваются более сложные ситуации, такие как координация работы нескольких потоков или обработка потоков, вызывающих блокировку.</span><span class="sxs-lookup"><span data-stu-id="11d04-105">This topic addresses more difficult situations, such as coordinating the work of multiple threads, or handling threads that block.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="11d04-106">Начиная с версии .NET Framework 4 библиотека параллельных задач и PLINQ предоставляют интерфейсы API, которые несколько снижают сложность и риски многопоточного программирования.</span><span class="sxs-lookup"><span data-stu-id="11d04-106">Starting with the .NET Framework 4, the Task Parallel Library and PLINQ provide APIs that reduce some of the complexity and risks of multi-threaded programming.</span></span> <span data-ttu-id="11d04-107">Дополнительные сведения см. в статье [Параллельное программирование в .NET](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="11d04-107">For more information, see [Parallel Programming in .NET](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="deadlocks-and-race-conditions"></a><span data-ttu-id="11d04-108">Взаимоблокировки и состояние гонки</span><span class="sxs-lookup"><span data-stu-id="11d04-108">Deadlocks and race conditions</span></span>  
 <span data-ttu-id="11d04-109">Многопоточность позволяет решить проблемы с пропускной способностью и скоростью реагирования, но при этом возникают новые проблемы: взаимоблокировки и конфликты.</span><span class="sxs-lookup"><span data-stu-id="11d04-109">Multithreading solves problems with throughput and responsiveness, but in doing so it introduces new problems: deadlocks and race conditions.</span></span>  
  
### <a name="deadlocks"></a><span data-ttu-id="11d04-110">Взаимоблокировки</span><span class="sxs-lookup"><span data-stu-id="11d04-110">Deadlocks</span></span>  
 <span data-ttu-id="11d04-111">Взаимоблокировка происходит, когда каждый из двух потоков пытается заблокировать ресурс, уже заблокированный другим потоком.</span><span class="sxs-lookup"><span data-stu-id="11d04-111">A deadlock occurs when each of two threads tries to lock a resource the other has already locked.</span></span> <span data-ttu-id="11d04-112">Ни один из потоков не может продолжить работу.</span><span class="sxs-lookup"><span data-stu-id="11d04-112">Neither thread can make any further progress.</span></span>  
  
 <span data-ttu-id="11d04-113">Многие методы классов управляемых потоков предоставляют значения времени ожидания для обнаружения взаимоблокировок.</span><span class="sxs-lookup"><span data-stu-id="11d04-113">Many methods of the managed threading classes provide time-outs to help you detect deadlocks.</span></span> <span data-ttu-id="11d04-114">Например, следующий код пытается получить блокировку для объекта с именем `lockObject`.</span><span class="sxs-lookup"><span data-stu-id="11d04-114">For example, the following code attempts to acquire a lock on an object named `lockObject`.</span></span> <span data-ttu-id="11d04-115">Если блокировка не будет получена в течение 300 миллисекунд, <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> возвратит `false`.</span><span class="sxs-lookup"><span data-stu-id="11d04-115">If the lock is not obtained in 300 milliseconds, <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> returns `false`.</span></span>  
  
```vb  
If Monitor.TryEnter(lockObject, 300) Then  
    Try  
        ' Place code protected by the Monitor here.  
    Finally  
        Monitor.Exit(lockObject)  
    End Try  
Else  
    ' Code to execute if the attempt times out.  
End If  
```  
  
```csharp  
if (Monitor.TryEnter(lockObject, 300)) {  
    try {  
        // Place code protected by the Monitor here.  
    }  
    finally {  
        Monitor.Exit(lockObject);  
    }  
}  
else {  
    // Code to execute if the attempt times out.  
}  
```  
  
### <a name="race-conditions"></a><span data-ttu-id="11d04-116">Состояние гонки</span><span class="sxs-lookup"><span data-stu-id="11d04-116">Race conditions</span></span>  
 <span data-ttu-id="11d04-117">Конфликт — это ошибка, которая возникает, когда результат программы зависит от того, какой из двух или более потоков первым достигнет определенного блока кода.</span><span class="sxs-lookup"><span data-stu-id="11d04-117">A race condition is a bug that occurs when the outcome of a program depends on which of two or more threads reaches a particular block of code first.</span></span> <span data-ttu-id="11d04-118">Выполнение программы часто дает различные результаты, и предсказать результат выполнения конкретного запуска невозможно.</span><span class="sxs-lookup"><span data-stu-id="11d04-118">Running the program many times produces different results, and the result of any given run cannot be predicted.</span></span>  
  
 <span data-ttu-id="11d04-119">Простой пример состояния гонки — увеличение поля.</span><span class="sxs-lookup"><span data-stu-id="11d04-119">A simple example of a race condition is incrementing a field.</span></span> <span data-ttu-id="11d04-120">Предположим, что класс содержит закрытое поле **static** (**Shared** в Visual Basic), которое увеличивается всякий раз при создании класса с помощью кода, например `objCt++;` (в C#) или `objCt += 1` (в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="11d04-120">Suppose a class has a private **static** field (**Shared** in Visual Basic) that is incremented every time an instance of the class is created, using code such as `objCt++;` (C#) or `objCt += 1` (Visual Basic).</span></span> <span data-ttu-id="11d04-121">Для этой операции необходимо загрузить значение из `objCt` в регистр, увеличить или уменьшить это значение и сохранить его в `objCt`.</span><span class="sxs-lookup"><span data-stu-id="11d04-121">This operation requires loading the value from `objCt` into a register, incrementing the value, and storing it in `objCt`.</span></span>  
  
 <span data-ttu-id="11d04-122">В многопоточных приложениях поток, загружающий и увеличивающий значение, может быть вытеснен другим потоком, который выполняет все три эти действия; если первый поток возобновляет выполнение и сохраняет его значение, он переопределяет `objCt`, не принимая во внимание тот факт, что в промежутке значение изменилось.</span><span class="sxs-lookup"><span data-stu-id="11d04-122">In a multithreaded application, a thread that has loaded and incremented the value might be preempted by another thread which performs all three steps; when the first thread resumes execution and stores its value, it overwrites `objCt` without taking into account the fact that the value has changed in the interim.</span></span>  
  
 <span data-ttu-id="11d04-123">Конкретно этого состояния гонки можно легко избежать, применяя методы класса <xref:System.Threading.Interlocked>, например <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="11d04-123">This particular race condition is easily avoided by using methods of the <xref:System.Threading.Interlocked> class, such as <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="11d04-124">Сведения о других технологиях синхронизации данных между несколькими потоками см. в разделе [Синхронизация данных для многопоточности](../../../docs/standard/threading/synchronizing-data-for-multithreading.md).</span><span class="sxs-lookup"><span data-stu-id="11d04-124">To read about other techniques for synchronizing data among multiple threads, see [Synchronizing Data for Multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md).</span></span>  
  
 <span data-ttu-id="11d04-125">Конфликты могут также возникать при синхронизации действий различных потоков.</span><span class="sxs-lookup"><span data-stu-id="11d04-125">Race conditions can also occur when you synchronize the activities of multiple threads.</span></span> <span data-ttu-id="11d04-126">При написании каждой строки кода необходимо учитывать, что может произойти, если поток будет вытеснен другим потоком до ее выполнения (или до одной из индивидуальных машинных команд, составляющих эту строку).</span><span class="sxs-lookup"><span data-stu-id="11d04-126">Whenever you write a line of code, you must consider what might happen if a thread were preempted before executing the line (or before any of the individual machine instructions that make up the line), and another thread overtook it.</span></span>  
  
## <a name="static-members-and-static-constructors"></a><span data-ttu-id="11d04-127">Статические члены и статические конструкторы</span><span class="sxs-lookup"><span data-stu-id="11d04-127">Static members and static constructors</span></span>  
 <span data-ttu-id="11d04-128">Класс не инициализируется, пока не завершится выполнение его конструктора (конструктор `static` в C# `Shared Sub New` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="11d04-128">A class is not initialized until its class constructor (`static` constructor in C#, `Shared Sub New` in Visual Basic) has finished running.</span></span> <span data-ttu-id="11d04-129">Чтобы предотвратить выполнение кода в еще не инициализированном типе, CLR блокирует все вызовы из других потоков для членов класса `static` (члены `Shared` в Visual Basic) до тех пор, пока выполнение конструктора класса не будет завершено.</span><span class="sxs-lookup"><span data-stu-id="11d04-129">To prevent the execution of code on a type that is not initialized, the common language runtime blocks all calls from other threads to `static` members of the class (`Shared` members in Visual Basic) until the class constructor has finished running.</span></span>  
  
 <span data-ttu-id="11d04-130">Например, если конструктор класса запускает новый поток, а процедура потока вызывает член `static` класса, новый поток блокируется до завершения конструктора класса.</span><span class="sxs-lookup"><span data-stu-id="11d04-130">For example, if a class constructor starts a new thread, and the thread procedure calls a `static` member of the class, the new thread blocks until the class constructor completes.</span></span>  
  
 <span data-ttu-id="11d04-131">Это относится к любому типу, который может иметь конструктор `static`.</span><span class="sxs-lookup"><span data-stu-id="11d04-131">This applies to any type that can have a `static` constructor.</span></span>  

## <a name="number-of-processors"></a><span data-ttu-id="11d04-132">Число процессоров</span><span class="sxs-lookup"><span data-stu-id="11d04-132">Number of processors</span></span>

<span data-ttu-id="11d04-133">Наличие нескольких процессоров или только одного процессора в системе может повлиять на многопоточную архитектуру.</span><span class="sxs-lookup"><span data-stu-id="11d04-133">Whether there are multiple processors or only one processor available on a system can influence multithreaded architecture.</span></span> <span data-ttu-id="11d04-134">Дополнительные сведения см. в разделе [Количество процессоров](https://docs.microsoft.com/previous-versions/dotnet/netframework-1.1/1c9txz50(v%3dvs.71)#number-of-processors).</span><span class="sxs-lookup"><span data-stu-id="11d04-134">For more information, see [Number of Processors](https://docs.microsoft.com/previous-versions/dotnet/netframework-1.1/1c9txz50(v%3dvs.71)#number-of-processors).</span></span>

<span data-ttu-id="11d04-135">Используйте свойство <xref:System.Environment.ProcessorCount?displayProperty=nameWithType>, чтобы определить количество процессоров, доступных во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="11d04-135">Use the <xref:System.Environment.ProcessorCount?displayProperty=nameWithType> property to determine the number of processors available at runtime.</span></span>
  
## <a name="general-recommendations"></a><span data-ttu-id="11d04-136">Основные рекомендации</span><span class="sxs-lookup"><span data-stu-id="11d04-136">General recommendations</span></span>  
 <span data-ttu-id="11d04-137">При использовании нескольких потоков соблюдайте следующие рекомендации:</span><span class="sxs-lookup"><span data-stu-id="11d04-137">Consider the following guidelines when using multiple threads:</span></span>  
  
- <span data-ttu-id="11d04-138">Не используйте <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> для завершения других потоков.</span><span class="sxs-lookup"><span data-stu-id="11d04-138">Don't use <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate other threads.</span></span> <span data-ttu-id="11d04-139">Вызов метода **Abort** для другого потока аналогичен вызову исключения в этом потоке, когда неизвестно, на каком этапе находится обработка этого потока.</span><span class="sxs-lookup"><span data-stu-id="11d04-139">Calling **Abort** on another thread is akin to throwing an exception on that thread, without knowing what point that thread has reached in its processing.</span></span>  
  
- <span data-ttu-id="11d04-140">Не используйте <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> и <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType> для синхронизации действий между потоками.</span><span class="sxs-lookup"><span data-stu-id="11d04-140">Don't use <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> and <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType> to synchronize the activities of multiple threads.</span></span> <span data-ttu-id="11d04-141">Используйте вместо этого <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent> и <xref:System.Threading.Monitor>.</span><span class="sxs-lookup"><span data-stu-id="11d04-141">Do use <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent>, and <xref:System.Threading.Monitor>.</span></span>  
  
- <span data-ttu-id="11d04-142">Не контролируйте выполнение рабочих потоков из основной программы (например, с помощью событий).</span><span class="sxs-lookup"><span data-stu-id="11d04-142">Don't control the execution of worker threads from your main program (using events, for example).</span></span> <span data-ttu-id="11d04-143">Вместо этого составьте программу так, чтобы рабочие потоки ожидали доступности задания, выполняли его и оповещали другие части программы о его завершении.</span><span class="sxs-lookup"><span data-stu-id="11d04-143">Instead, design your program so that worker threads are responsible for waiting until work is available, executing it, and notifying other parts of your program when finished.</span></span> <span data-ttu-id="11d04-144">Если рабочие потоки не блокируются, можно использовать потоки из пула потоков.</span><span class="sxs-lookup"><span data-stu-id="11d04-144">If your worker threads do not block, consider using thread pool threads.</span></span> <span data-ttu-id="11d04-145"><xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType> можно использовать в ситуациях, когда рабочие потоки блокируются.</span><span class="sxs-lookup"><span data-stu-id="11d04-145"><xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType> is useful in situations where worker threads block.</span></span>  
  
- <span data-ttu-id="11d04-146">Не используйте типы как объекты блокировки.</span><span class="sxs-lookup"><span data-stu-id="11d04-146">Don't use types as lock objects.</span></span> <span data-ttu-id="11d04-147">Это означает, что следует избегать кода `lock(typeof(X))` в C# или `SyncLock(GetType(X))` в Visual Basic, а также использования <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> с объектами <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="11d04-147">That is, avoid code such as `lock(typeof(X))` in C# or `SyncLock(GetType(X))` in Visual Basic, or the use of <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> with <xref:System.Type> objects.</span></span> <span data-ttu-id="11d04-148">Для каждого конкретного типа существует только один экземпляр <xref:System.Type?displayProperty=nameWithType> в каждом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="11d04-148">For a given type, there is only one instance of <xref:System.Type?displayProperty=nameWithType> per application domain.</span></span> <span data-ttu-id="11d04-149">Если блокируемый тип является открытым, его может заблокировать чужой код, вызвав тем самым взаимоблокировку.</span><span class="sxs-lookup"><span data-stu-id="11d04-149">If the type you take a lock on is public, code other than your own can take locks on it, leading to deadlocks.</span></span> <span data-ttu-id="11d04-150">Дополнительные вопросы см. [Рекомендации по обеспечению надежности](../../../docs/framework/performance/reliability-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="11d04-150">For additional issues, see [Reliability Best Practices](../../../docs/framework/performance/reliability-best-practices.md).</span></span>  
  
- <span data-ttu-id="11d04-151">Будьте внимательны при блокировке экземпляров, например `lock(this)` в C# или `SyncLock(Me)` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="11d04-151">Use caution when locking on instances, for example `lock(this)` in C# or `SyncLock(Me)` in Visual Basic.</span></span> <span data-ttu-id="11d04-152">Если другой код в приложении, который является внешним для типа, заблокирует объект, может возникнуть взаимоблокировка.</span><span class="sxs-lookup"><span data-stu-id="11d04-152">If other code in your application, external to the type, takes a lock on the object, deadlocks could occur.</span></span>  
  
- <span data-ttu-id="11d04-153">Следите за тем, чтобы каждый поток, который входит в монитор, обязательно вышел из этого монитора, даже если за время, пока поток находится в мониторе, возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="11d04-153">Do ensure that a thread that has entered a monitor always leaves that monitor, even if an exception occurs while the thread is in the monitor.</span></span> <span data-ttu-id="11d04-154">Оператор C# [lock](../../csharp/language-reference/keywords/lock-statement.md) и оператор Visual Basic [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md) делают это автоматически, обеспечивая вызов метода <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType> с помощью блока **finally**.</span><span class="sxs-lookup"><span data-stu-id="11d04-154">The C# [lock](../../csharp/language-reference/keywords/lock-statement.md) statement and the Visual Basic [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md) statement provide this behavior automatically, employing a **finally** block to ensure that <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType> is called.</span></span> <span data-ttu-id="11d04-155">Если вы не можете проконтролировать вызов метода **Exit**, включите в свое приложение **мьютекс**.</span><span class="sxs-lookup"><span data-stu-id="11d04-155">If you cannot ensure that **Exit** will be called, consider changing your design to use **Mutex**.</span></span> <span data-ttu-id="11d04-156">Мьютекс автоматически освобождается, как только прекращается выполнение владеющего им потока.</span><span class="sxs-lookup"><span data-stu-id="11d04-156">A mutex is automatically released when the thread that currently owns it terminates.</span></span>  
  
- <span data-ttu-id="11d04-157">Для задач, которые требуют различных ресурсов, используйте несколько потоков и старайтесь не назначать несколько потоков одному ресурсу.</span><span class="sxs-lookup"><span data-stu-id="11d04-157">Do use multiple threads for tasks that require different resources, and avoid assigning multiple threads to a single resource.</span></span> <span data-ttu-id="11d04-158">Например, любая задача с использованием ввода-вывода выигрывает от наличия собственного потока, поскольку во время операций ввода-вывода этот поток блокируется и, таким образом, разрешает выполнение других потоков.</span><span class="sxs-lookup"><span data-stu-id="11d04-158">For example, any task involving I/O benefits from having its own thread, because that thread will block during I/O operations and thus allow other threads to execute.</span></span> <span data-ttu-id="11d04-159">Входные данные пользователя — еще один ресурс, которому пойдет на пользу выделенный поток.</span><span class="sxs-lookup"><span data-stu-id="11d04-159">User input is another resource that benefits from a dedicated thread.</span></span> <span data-ttu-id="11d04-160">На однопроцессорном компьютере задача, требующая активных вычислений, сосуществует с входными данными пользователя и задачами, которые предусматривают операции ввода-вывода, однако несколько ресурсоемких задач могут конкурировать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="11d04-160">On a single-processor computer, a task that involves intensive computation coexists with user input and with tasks that involve I/O, but multiple computation-intensive tasks contend with each other.</span></span>  
  
- <span data-ttu-id="11d04-161">Вместо оператора `lock` (`SyncLock` в Visual Basic) для простого изменения состояния лучше использовать методы класса <xref:System.Threading.Interlocked>.</span><span class="sxs-lookup"><span data-stu-id="11d04-161">Consider using methods of the <xref:System.Threading.Interlocked> class for simple state changes, instead of using the `lock` statement (`SyncLock` in Visual Basic).</span></span> <span data-ttu-id="11d04-162">Оператор `lock` — хороший универсальный инструмент, но класс <xref:System.Threading.Interlocked> обеспечивает высокую производительность для обновлений, которые должны быть атомарными.</span><span class="sxs-lookup"><span data-stu-id="11d04-162">The `lock` statement is a good general-purpose tool, but the <xref:System.Threading.Interlocked> class provides better performance for updates that must be atomic.</span></span> <span data-ttu-id="11d04-163">Если конкуренции нет, он выполняет внутри единственный префикс lock.</span><span class="sxs-lookup"><span data-stu-id="11d04-163">Internally, it executes a single lock prefix if there is no contention.</span></span> <span data-ttu-id="11d04-164">При проверке кода ищите код, похожий на показанный в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="11d04-164">In code reviews, watch for code like that shown in the following examples.</span></span> <span data-ttu-id="11d04-165">В первом примере увеличивается переменная состояния:</span><span class="sxs-lookup"><span data-stu-id="11d04-165">In the first example, a state variable is incremented:</span></span>  
  
    ```vb  
    SyncLock lockObject  
        myField += 1  
    End SyncLock  
    ```  
  
    ```csharp  
    lock(lockObject)   
    {  
        myField++;  
    }  
    ```  
  
     <span data-ttu-id="11d04-166">Вы можете повысить производительность, применяя метод <xref:System.Threading.Interlocked.Increment%2A> вместо оператора `lock`, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="11d04-166">You can improve performance by using the <xref:System.Threading.Interlocked.Increment%2A> method instead of the `lock` statement, as follows:</span></span>  
  
    ```vb  
    System.Threading.Interlocked.Increment(myField)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.Increment(myField);  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="11d04-167">В .NET Framework 2.0 и более поздних версий используйте метод <xref:System.Threading.Interlocked.Add%2A> для атомарных приращений более 1.</span><span class="sxs-lookup"><span data-stu-id="11d04-167">In the .NET Framework 2.0 and later, use the <xref:System.Threading.Interlocked.Add%2A> method for atomic increments larger than 1.</span></span>  
  
     <span data-ttu-id="11d04-168">Во втором примере переменная ссылочного типа обновляется только в том случае, если она является пустой ссылкой (`Nothing` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="11d04-168">In the second example, a reference type variable is updated only if it is a null reference (`Nothing` in Visual Basic).</span></span>  
  
    ```vb  
    If x Is Nothing Then  
        SyncLock lockObject  
            If x Is Nothing Then  
                x = y  
            End If  
        End SyncLock  
    End If  
    ```  
  
    ```csharp  
    if (x == null)  
    {  
        lock (lockObject)  
        {  
            x ??= y;
        }  
    }  
    ```  
  
     <span data-ttu-id="11d04-169">Чтобы повысить производительность, применяйте вместо этого метод <xref:System.Threading.Interlocked.CompareExchange%2A>, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="11d04-169">Performance can be improved by using the <xref:System.Threading.Interlocked.CompareExchange%2A> method instead, as follows:</span></span>  
  
    ```vb  
    System.Threading.Interlocked.CompareExchange(x, y, Nothing)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.CompareExchange(ref x, y, null);  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="11d04-170">Начиная с .NET Framework 2.0 перегрузка метода <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29> предоставляет типобезопасную альтернативу для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="11d04-170">Beginning with .NET Framework 2.0, the <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29> method overload provides a type-safe alternative for reference types.</span></span>
  
## <a name="recommendations-for-class-libraries"></a><span data-ttu-id="11d04-171">Рекомендации для библиотек классов</span><span class="sxs-lookup"><span data-stu-id="11d04-171">Recommendations for class libraries</span></span>  
 <span data-ttu-id="11d04-172">При разработке библиотек классов для многопоточности необходимо учитывать следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="11d04-172">Consider the following guidelines when designing class libraries for multithreading:</span></span>  
  
- <span data-ttu-id="11d04-173">Старайтесь не создавать потребность в синхронизации.</span><span class="sxs-lookup"><span data-stu-id="11d04-173">Avoid the need for synchronization, if possible.</span></span> <span data-ttu-id="11d04-174">Особенно это относится к коду, который используется наиболее часто.</span><span class="sxs-lookup"><span data-stu-id="11d04-174">This is especially true for heavily used code.</span></span> <span data-ttu-id="11d04-175">Например, алгоритм можно скорректировать таким образом, чтобы он допускал конфликты, а не устранял их.</span><span class="sxs-lookup"><span data-stu-id="11d04-175">For example, an algorithm might be adjusted to tolerate a race condition rather than eliminate it.</span></span> <span data-ttu-id="11d04-176">Ненужная синхронизация снижает производительность и может привести к взаимоблокировке и конфликтам.</span><span class="sxs-lookup"><span data-stu-id="11d04-176">Unnecessary synchronization decreases performance and creates the possibility of deadlocks and race conditions.</span></span>  
  
- <span data-ttu-id="11d04-177">Сделайте статические данные (`Shared` в Visual Basic) по умолчанию потокобезопасными.</span><span class="sxs-lookup"><span data-stu-id="11d04-177">Make static data (`Shared` in Visual Basic) thread safe by default.</span></span>  
  
- <span data-ttu-id="11d04-178">Данные экземпляров не должны быть потокобезопасными по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="11d04-178">Do not make instance data thread safe by default.</span></span> <span data-ttu-id="11d04-179">Добавление блокировок для создания потокобезопасного кода снижает производительность, увеличивает конфликт блокировки и создает условия для возникновения взаимоблокировок.</span><span class="sxs-lookup"><span data-stu-id="11d04-179">Adding locks to create thread-safe code decreases performance, increases lock contention, and creates the possibility for deadlocks to occur.</span></span> <span data-ttu-id="11d04-180">В обычных моделях приложений пользовательский код одновременно выполняется только одним потоком, что уменьшает необходимость потокобезопасности.</span><span class="sxs-lookup"><span data-stu-id="11d04-180">In common application models, only one thread at a time executes user code, which minimizes the need for thread safety.</span></span> <span data-ttu-id="11d04-181">По этой причине библиотеки классов .NET Framework не являются потокобезопасными по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="11d04-181">For this reason, the .NET Framework class libraries are not thread safe by default.</span></span>  
  
- <span data-ttu-id="11d04-182">Не предоставляйте статические методы, изменяющие статическое состояние.</span><span class="sxs-lookup"><span data-stu-id="11d04-182">Avoid providing static methods that alter static state.</span></span> <span data-ttu-id="11d04-183">В обычных сценариях сервера статическое состояние используется запросами совместно, а значит, код одновременно могут выполнять сразу несколько потоков.</span><span class="sxs-lookup"><span data-stu-id="11d04-183">In common server scenarios, static state is shared across requests, which means multiple threads can execute that code at the same time.</span></span> <span data-ttu-id="11d04-184">Это открывает возможность для появления потоковых ошибок.</span><span class="sxs-lookup"><span data-stu-id="11d04-184">This opens up the possibility of threading bugs.</span></span> <span data-ttu-id="11d04-185">Попробуйте применить конструктивный шаблон, инкапсулирующий данные в экземпляры, которые не являются общими для запросов.</span><span class="sxs-lookup"><span data-stu-id="11d04-185">Consider using a design pattern that encapsulates data into instances that are not shared across requests.</span></span> <span data-ttu-id="11d04-186">Кроме того, если статические данные синхронизируются, вызовы между статическими методами, изменяющие состояние, могут приводить к взаимоблокировкам или избыточной синхронизации, что, в свою очередь, снижает производительность.</span><span class="sxs-lookup"><span data-stu-id="11d04-186">Furthermore, if static data are synchronized, calls between static methods that alter state can result in deadlocks or redundant synchronization, adversely affecting performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11d04-187">См. также</span><span class="sxs-lookup"><span data-stu-id="11d04-187">See also</span></span>

- [<span data-ttu-id="11d04-188">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="11d04-188">Threading</span></span>](../../../docs/standard/threading/index.md)
- [<span data-ttu-id="11d04-189">Потоки и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="11d04-189">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)
