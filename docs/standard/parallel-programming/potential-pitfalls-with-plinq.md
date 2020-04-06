---
title: Потенциальные ошибки, связанные с PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, pitfalls
ms.assetid: 75a38b55-4bc4-488a-87d5-89dbdbdc76a2
ms.openlocfilehash: 44f40d6caad9187376a790f9a0ed09e22c861e37
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588600"
---
# <a name="potential-pitfalls-with-plinq"></a><span data-ttu-id="4375d-102">Потенциальные ошибки, связанные с PLINQ</span><span class="sxs-lookup"><span data-stu-id="4375d-102">Potential pitfalls with PLINQ</span></span>

<span data-ttu-id="4375d-103">Во многих случаях PLINQ может значительно повысить производительность по сравнению с последовательным выполнением запросов LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="4375d-103">In many cases, PLINQ can provide significant performance improvements over sequential LINQ to Objects queries.</span></span> <span data-ttu-id="4375d-104">Но сам процесс параллелизации запроса может оказаться сложным и вызвать дополнительные проблемы, которые в последовательном коде не типичны или совсем не встречаются.</span><span class="sxs-lookup"><span data-stu-id="4375d-104">However, the work of parallelizing the query execution introduces complexity that can lead to problems that, in sequential code, are not as common or are not encountered at all.</span></span> <span data-ttu-id="4375d-105">В этом разделе перечислены некоторые рекомендации по составлению запросов PLINQ.</span><span class="sxs-lookup"><span data-stu-id="4375d-105">This topic lists some practices to avoid when you write PLINQ queries.</span></span>

## <a name="dont-assume-that-parallel-is-always-faster"></a><span data-ttu-id="4375d-106">Не считайте, что параллельные процессы всегда быстрее</span><span class="sxs-lookup"><span data-stu-id="4375d-106">Don't assume that parallel is always faster</span></span>

<span data-ttu-id="4375d-107">Иногда параллелизация приводит к тому, что запрос PLINQ выполняется медленнее, чем его эквивалент в LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="4375d-107">Parallelization sometimes causes a PLINQ query to run slower than its LINQ to Objects equivalent.</span></span> <span data-ttu-id="4375d-108">Главное правило заключается в том, что запросы с небольшим числом исходных элементов и быстрыми пользовательскими делегатами обычно не дают большого ускорения.</span><span class="sxs-lookup"><span data-stu-id="4375d-108">The basic rule of thumb is that queries that have few source elements and fast user delegates are unlikely to speedup much.</span></span> <span data-ttu-id="4375d-109">Но на производительность влияет множество разных факторов, поэтому мы рекомендуем всегда оценивать фактические результаты при принятии решения об использовании PLINQ.</span><span class="sxs-lookup"><span data-stu-id="4375d-109">However, because many factors are involved in performance, we recommend that you measure actual results before you decide whether to use PLINQ.</span></span> <span data-ttu-id="4375d-110">Дополнительные сведения см. в разделе [Общее представление об ускорении выполнения в PLINQ](understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="4375d-110">For more information, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span>

## <a name="avoid-writing-to-shared-memory-locations"></a><span data-ttu-id="4375d-111">Избегайте размещения в общей памяти</span><span class="sxs-lookup"><span data-stu-id="4375d-111">Avoid writing to shared memory locations</span></span>

<span data-ttu-id="4375d-112">В последовательном коде для чтения и записи часто используются статические переменные и поля классов.</span><span class="sxs-lookup"><span data-stu-id="4375d-112">In sequential code, it is not uncommon to read from or write to static variables or class fields.</span></span> <span data-ttu-id="4375d-113">Но всякий раз, когда к таким переменным обращаются сразу несколько потоков, может возникать состояние гонки.</span><span class="sxs-lookup"><span data-stu-id="4375d-113">However, whenever multiple threads are accessing such variables concurrently, there is a big potential for race conditions.</span></span> <span data-ttu-id="4375d-114">Несмотря на то что для синхронизации доступа к переменной можно использовать блокировки, связанные с нею затраты ресурсов могут снизить производительность.</span><span class="sxs-lookup"><span data-stu-id="4375d-114">Even though you can use locks to synchronize access to the variable, the cost of synchronization can hurt performance.</span></span> <span data-ttu-id="4375d-115">В связи с этим рекомендуем не использовать или хотя бы максимально ограничить обращение к общему состоянию в запросах PLINQ.</span><span class="sxs-lookup"><span data-stu-id="4375d-115">Therefore, we recommend that you avoid, or at least limit, access to shared state in a PLINQ query as much as possible.</span></span>

## <a name="avoid-over-parallelization"></a><span data-ttu-id="4375d-116">Избегайте излишней параллелизации</span><span class="sxs-lookup"><span data-stu-id="4375d-116">Avoid over-parallelization</span></span>

<span data-ttu-id="4375d-117">Использование метода `AsParallel` приводит к накладным расходам на секционирование исходной коллекции и синхронизацию рабочих потоков.</span><span class="sxs-lookup"><span data-stu-id="4375d-117">By using the `AsParallel` method, you incur the overhead costs of partitioning the source collection and synchronizing the worker threads.</span></span> <span data-ttu-id="4375d-118">Преимущества параллелизации также ограничивает число процессоров на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4375d-118">The benefits of parallelization are further limited by the number of processors on the computer.</span></span> <span data-ttu-id="4375d-119">Выполнение сразу нескольких потоков с большим количеством вычислений на одном и том же процессоре не повысит производительность.</span><span class="sxs-lookup"><span data-stu-id="4375d-119">There is no speedup to be gained by running multiple compute-bound threads on just one processor.</span></span> <span data-ttu-id="4375d-120">В связи с этим излишней параллелизации запроса следует избегать.</span><span class="sxs-lookup"><span data-stu-id="4375d-120">Therefore, you must be careful not to over-parallelize a query.</span></span>

<span data-ttu-id="4375d-121">Параллелизация чаще всего становится излишней во вложенных запросах, как показано в следующем фрагменте кода.</span><span class="sxs-lookup"><span data-stu-id="4375d-121">The most common scenario in which over-parallelization can occur is in nested queries, as shown in the following snippet.</span></span>

[!code-csharp[PLINQ#20](~/samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
[!code-vb[PLINQ#20](~/samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]

<span data-ttu-id="4375d-122">В этом примере выгоднее параллелизовать только внешний источник данных (клиенты), если не выполняется хотя бы одно из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="4375d-122">In this case, it is best to parallelize only the outer data source (customers) unless one or more of the following conditions apply:</span></span>

- <span data-ttu-id="4375d-123">Внутренний источник данных (пользовательские заказы) содержит заведомо огромное число элементов.</span><span class="sxs-lookup"><span data-stu-id="4375d-123">The inner data source (cust.Orders) is known to be very long.</span></span>

- <span data-ttu-id="4375d-124">С каждым заказом вы выполняете дорогостоящие вычисления.</span><span class="sxs-lookup"><span data-stu-id="4375d-124">You are performing an expensive computation on each order.</span></span> <span data-ttu-id="4375d-125">(Операция, показанная в примере, не является дорогостоящей.)</span><span class="sxs-lookup"><span data-stu-id="4375d-125">(The operation shown in the example is not expensive.)</span></span>

- <span data-ttu-id="4375d-126">Целевая система имеет достаточно процессоров для обработки того количества потоков, которое будет создано при параллелизации запроса в `cust.Orders`.</span><span class="sxs-lookup"><span data-stu-id="4375d-126">The target system is known to have enough processors to handle the number of threads that will be produced by parallelizing the query on `cust.Orders`.</span></span>

<span data-ttu-id="4375d-127">В любом случае лучший способ определения оптимальной формы запроса — это проверка и измерение.</span><span class="sxs-lookup"><span data-stu-id="4375d-127">In all cases, the best way to determine the optimum query shape is to test and measure.</span></span> <span data-ttu-id="4375d-128">Дополнительные сведения см. в разделе [Практическое руководство. Измерение производительности запросов PLINQ](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).</span><span class="sxs-lookup"><span data-stu-id="4375d-128">For more information, see [How to: Measure PLINQ Query Performance](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).</span></span>

## <a name="avoid-calls-to-non-thread-safe-methods"></a><span data-ttu-id="4375d-129">Избегайте вызова методов, небезопасных для потоков</span><span class="sxs-lookup"><span data-stu-id="4375d-129">Avoid calls to non-thread-safe methods</span></span>

<span data-ttu-id="4375d-130">Запись из запроса PLINQ в методы экземпляров, не являющиеся потокобезопасными, может привести к повреждению данных. Такое изменение даже может остаться незамеченным в программе.</span><span class="sxs-lookup"><span data-stu-id="4375d-130">Writing to non-thread-safe instance methods from a PLINQ query can lead to data corruption which may or may not go undetected in your program.</span></span> <span data-ttu-id="4375d-131">Кроме того, она может вызывать исключения.</span><span class="sxs-lookup"><span data-stu-id="4375d-131">It can also lead to exceptions.</span></span> <span data-ttu-id="4375d-132">В следующем примере несколько потоков одновременно пытаются вызвать метод `FileStream.Write`, но этот класс не поддерживает такое поведение.</span><span class="sxs-lookup"><span data-stu-id="4375d-132">In the following example, multiple threads would be attempting to call the `FileStream.Write` method simultaneously, which is not supported by the class.</span></span>

```vb
Dim fs As FileStream = File.OpenWrite(…)
a.AsParallel().Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))
```

```csharp
FileStream fs = File.OpenWrite(...);
a.AsParallel().Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));
```

## <a name="limit-calls-to-thread-safe-methods"></a><span data-ttu-id="4375d-133">Ограничение вызовов потокобезопасных методов</span><span class="sxs-lookup"><span data-stu-id="4375d-133">Limit calls to thread-safe methods</span></span>

<span data-ttu-id="4375d-134">Большинство статических методов на платформе .NET Framework безопасны для потоков и могут вызываться из нескольких потоков одновременно.</span><span class="sxs-lookup"><span data-stu-id="4375d-134">Most static methods in the .NET Framework are thread-safe and can be called from multiple threads concurrently.</span></span> <span data-ttu-id="4375d-135">Но даже в этих случаях соответствующая синхронизация может значительно замедлить запрос.</span><span class="sxs-lookup"><span data-stu-id="4375d-135">However, even in these cases, the synchronization involved can lead to significant slowdown in the query.</span></span>

> [!NOTE]
> <span data-ttu-id="4375d-136">Вы можете проверить это самостоятельно, добавив в запросы несколько вызовов <xref:System.Console.WriteLine%2A>.</span><span class="sxs-lookup"><span data-stu-id="4375d-136">You can test for this yourself by inserting some calls to <xref:System.Console.WriteLine%2A> in your queries.</span></span> <span data-ttu-id="4375d-137">Несмотря на то, что этот метод часто приводится в демонстрационных примерах, его не следует использовать в запросах PLINQ.</span><span class="sxs-lookup"><span data-stu-id="4375d-137">Although this method is used in the documentation examples for demonstration purposes, do not use it in PLINQ queries.</span></span>

## <a name="avoid-unnecessary-ordering-operations"></a><span data-ttu-id="4375d-138">Избегайте ненужных операций упорядочения</span><span class="sxs-lookup"><span data-stu-id="4375d-138">Avoid unnecessary ordering operations</span></span>

<span data-ttu-id="4375d-139">Если PLINQ выполняет запрос параллельно, исходная последовательность разделяется на секции, которые могут обрабатываться одновременно в нескольких потоках.</span><span class="sxs-lookup"><span data-stu-id="4375d-139">When PLINQ executes a query in parallel, it divides the source sequence into partitions that can be operated on concurrently on multiple threads.</span></span> <span data-ttu-id="4375d-140">По умолчанию порядок обработки этих секций и порядок получения результатов не является прогнозируемым (за исключением отдельных операторов, например `OrderBy`).</span><span class="sxs-lookup"><span data-stu-id="4375d-140">By default, the order in which the partitions are processed and the results are delivered is not predictable (except for operators such as `OrderBy`).</span></span> <span data-ttu-id="4375d-141">Вы можете сообщить PLINQ, что нужно сохранить порядок всех исходных последовательностей, но это снизит производительность.</span><span class="sxs-lookup"><span data-stu-id="4375d-141">You can instruct PLINQ to preserve the ordering of any source sequence, but this has a negative impact on performance.</span></span> <span data-ttu-id="4375d-142">Везде, где это возможно, мы рекомендуем структурировать запросы так, чтобы они не полагались на сохранение порядка.</span><span class="sxs-lookup"><span data-stu-id="4375d-142">The best practice, whenever possible, is to structure queries so that they do not rely on order preservation.</span></span> <span data-ttu-id="4375d-143">Дополнительные сведения см. в разделе [Сохранение порядка в PLINQ](order-preservation-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="4375d-143">For more information, see [Order Preservation in PLINQ](order-preservation-in-plinq.md).</span></span>

## <a name="prefer-forall-to-foreach-when-it-is-possible"></a><span data-ttu-id="4375d-144">Выбирайте ForAll вместо ForEach везде, где это возможно</span><span class="sxs-lookup"><span data-stu-id="4375d-144">Prefer ForAll to ForEach when it is possible</span></span>

<span data-ttu-id="4375d-145">Несмотря на то, что PLINQ выполняет запрос в нескольких потоках, результаты придется собрать в один поток, если используется цикл `foreach` (`For Each` в Visual Basic), чтобы перечислитель обращался к ним последовательно.</span><span class="sxs-lookup"><span data-stu-id="4375d-145">Although PLINQ executes a query on multiple threads, if you consume the results in a `foreach` loop (`For Each` in Visual Basic), then the query results must be merged back into one thread and accessed serially by the enumerator.</span></span> <span data-ttu-id="4375d-146">В некоторых случаях это неизбежно. Но если возможно, всегда используйте метод `ForAll`, чтобы каждый поток мог выводить свои результаты независимо от других. Например, выполняйте запись в потокобезопасную коллекцию типа <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4375d-146">In some cases, this is unavoidable; however, whenever possible, use the `ForAll` method to enable each thread to output its own results, for example, by writing to a thread-safe collection such as <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="4375d-147">Такая же проблема распространяется на <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4375d-147">The same issue applies to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4375d-148">Другими словами, вариант `source.AsParallel().Where().ForAll(...)` должен быть более предпочтительным, чем `Parallel.ForEach(source.AsParallel().Where(), ...)`.</span><span class="sxs-lookup"><span data-stu-id="4375d-148">In other words, `source.AsParallel().Where().ForAll(...)` should be strongly preferred to `Parallel.ForEach(source.AsParallel().Where(), ...)`.</span></span>

## <a name="be-aware-of-thread-affinity-issues"></a><span data-ttu-id="4375d-149">Помните о проблемах сходства потоков</span><span class="sxs-lookup"><span data-stu-id="4375d-149">Be aware of thread affinity issues</span></span>

<span data-ttu-id="4375d-150">Некоторые технологии, например COM-взаимодействие для компонентов однопотокового подразделения (STA), Windows Forms и Windows Presentation Foundation (WPF), накладывают ограничения на сходство потоков, требующие, чтобы код выполнялся в определенном потоке.</span><span class="sxs-lookup"><span data-stu-id="4375d-150">Some technologies, for example, COM interoperability for Single-Threaded Apartment (STA) components, Windows Forms, and Windows Presentation Foundation (WPF), impose thread affinity restrictions that require code to run on a specific thread.</span></span> <span data-ttu-id="4375d-151">Например, и в Windows Forms, и в WPF элемент управления может быть доступен только в том потоке, в котором он был создан.</span><span class="sxs-lookup"><span data-stu-id="4375d-151">For example, in both Windows Forms and WPF, a control can only be accessed on the thread on which it was created.</span></span> <span data-ttu-id="4375d-152">Если при выполнении запроса PLINQ попытаться получить доступ к общему состоянию элемента управления Windows Forms, в отладчике произойдет исключение.</span><span class="sxs-lookup"><span data-stu-id="4375d-152">If you try to access the shared state of a Windows Forms control in a PLINQ query, an exception is raised if you are running in the debugger.</span></span> <span data-ttu-id="4375d-153">(Этот параметр можно отключить.) Но если запрос обрабатывается в потоке пользовательского интерфейса, элемент управления можно вызвать из цикла `foreach`, который перечисляет результаты запроса, так как этот код выполняется только в одном потоке.</span><span class="sxs-lookup"><span data-stu-id="4375d-153">(This setting can be turned off.) However, if your query is consumed on the UI thread, then you can access the control from the `foreach` loop that enumerates the query results because that code executes on just one thread.</span></span>

## <a name="dont-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a><span data-ttu-id="4375d-154">Не считайте, что итерации операторов ForEach, For и ForAll всегда выполняются параллельно</span><span class="sxs-lookup"><span data-stu-id="4375d-154">Don't assume that iterations of ForEach, For, and ForAll always execute in parallel</span></span>

<span data-ttu-id="4375d-155">Важно помнить, что отдельные итерации цикла <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> или <xref:System.Linq.ParallelEnumerable.ForAll%2A> иногда могут выполняться параллельно, но это не гарантируется.</span><span class="sxs-lookup"><span data-stu-id="4375d-155">It is important to keep in mind that individual iterations in a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>, or <xref:System.Linq.ParallelEnumerable.ForAll%2A> loop may but do not have to execute in parallel.</span></span> <span data-ttu-id="4375d-156">В связи с этим старайтесь не писать код, который будет зависеть от правильности параллельного выполнения итераций или от выполнения итераций в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="4375d-156">Therefore, you should avoid writing any code that depends for correctness on parallel execution of iterations or on the execution of iterations in any particular order.</span></span>

<span data-ttu-id="4375d-157">Например, этот код может вызвать взаимоблокировку:</span><span class="sxs-lookup"><span data-stu-id="4375d-157">For example, this code is likely to deadlock:</span></span>

```vb
Dim mre = New ManualResetEventSlim()
Enumerable.Range(0, Environment.ProcessorCount * 100).AsParallel().ForAll(Sub(j)
   If j = Environment.ProcessorCount Then
       Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)
       mre.Set()
   Else
       Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)
       mre.Wait()
   End If
End Sub) ' deadlocks
```

```csharp
ManualResetEventSlim mre = new ManualResetEventSlim();
Enumerable.Range(0, Environment.ProcessorCount * 100).AsParallel().ForAll((j) =>
{
    if (j == Environment.ProcessorCount)
    {
        Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);
        mre.Set();
    }
    else
    {
        Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);
        mre.Wait();
    }
}); //deadlocks
```

<span data-ttu-id="4375d-158">В этом примере одна итерация задает событие, а все остальные его ожидают.</span><span class="sxs-lookup"><span data-stu-id="4375d-158">In this example, one iteration sets an event, and all other iterations wait on the event.</span></span> <span data-ttu-id="4375d-159">Ни одна из ожидающих итераций не может быть завершена, пока не завершится итерация, задающая событие.</span><span class="sxs-lookup"><span data-stu-id="4375d-159">None of the waiting iterations can complete until the event-setting iteration has completed.</span></span> <span data-ttu-id="4375d-160">При этом ожидающие итерации способны заблокировать все потоки, которые используются для выполнения параллельного цикла, прежде чем будет выполнена итерация, задающая событие.</span><span class="sxs-lookup"><span data-stu-id="4375d-160">However, it is possible that the waiting iterations block all threads that are used to execute the parallel loop, before the event-setting iteration has had a chance to execute.</span></span> <span data-ttu-id="4375d-161">Это приведет к взаимоблокировке — итерация, задающая событие, никогда не будет выполнена, а ожидающие итерации никогда не активизируются.</span><span class="sxs-lookup"><span data-stu-id="4375d-161">This results in a deadlock – the event-setting iteration will never execute, and the waiting iterations will never wake up.</span></span>

<span data-ttu-id="4375d-162">Таким образом, для выполнения работы необходимо, чтобы ни одна итерация параллельного цикла не ожидала другой итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="4375d-162">In particular, one iteration of a parallel loop should never wait on another iteration of the loop to make progress.</span></span> <span data-ttu-id="4375d-163">Если параллельный цикл решит запланировать итерации последовательно, но в обратном порядке, может возникнуть взаимоблокировка.</span><span class="sxs-lookup"><span data-stu-id="4375d-163">If the parallel loop decides to schedule the iterations sequentially but in the opposite order, a deadlock will occur.</span></span>

## <a name="see-also"></a><span data-ttu-id="4375d-164">См. также</span><span class="sxs-lookup"><span data-stu-id="4375d-164">See also</span></span>

- [<span data-ttu-id="4375d-165">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="4375d-165">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
