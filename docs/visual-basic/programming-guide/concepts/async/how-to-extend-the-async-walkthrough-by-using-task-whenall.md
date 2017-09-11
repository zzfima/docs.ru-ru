---
title: "Практическое руководство: расширение Async пошагового руководства с использованием метода Task.WhenAll (Visual Basic) | Документы Microsoft"
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
ms.assetid: c06d386d-e996-4da9-bf3d-05a3b6c0a258
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 91cecc84899c9a87307ed5799485ec60ef341e65
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-visual-basic"></a><span data-ttu-id="8cc11-102">Практическое руководство: расширение Async пошагового руководства с использованием метода Task.WhenAll (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8cc11-102">How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)</span></span>
<span data-ttu-id="8cc11-103">Можно повысить производительность async решения в [Пошаговое руководство: доступ к Интернету с помощью Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) с помощью <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>метод.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8cc11-103">You can improve the performance of the async solution in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) by using the <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="8cc11-104">Этот метод асинхронно ждет несколько асинхронных операций, которые представлены в виде набора задач.</span><span class="sxs-lookup"><span data-stu-id="8cc11-104">This method asynchronously awaits multiple asynchronous operations, which are represented as a collection of tasks.</span></span>  
  
 <span data-ttu-id="8cc11-105">Можно заметить в этом пошаговом руководстве, веб-сайты загрузки с разной скоростью.</span><span class="sxs-lookup"><span data-stu-id="8cc11-105">You might have noticed in the walkthrough that the websites download at different rates.</span></span> <span data-ttu-id="8cc11-106">Иногда один веб-сайтов очень медленно, который откладывает все оставшиеся загрузки.</span><span class="sxs-lookup"><span data-stu-id="8cc11-106">Sometimes one of the websites is very slow, which delays all the remaining downloads.</span></span> <span data-ttu-id="8cc11-107">При выполнении асинхронной решения, создаваемые в пошаговом руководстве, можно завершить программу легко Если вы не хотите ждать, но лучшим вариантом было бы необходимо запустить все загрузки одновременно и позволяют быстрее загрузки продолжать выполнение без ожидания, задерживается.</span><span class="sxs-lookup"><span data-stu-id="8cc11-107">When you run the asynchronous solutions that you build in the walkthrough, you can end the program easily if you don't want to wait, but a better option would be to start all the downloads at the same time and let faster downloads continue without waiting for the one that’s delayed.</span></span>  
  
 <span data-ttu-id="8cc11-108">Можно применить `Task.WhenAll` метод коллекцию задач.</span><span class="sxs-lookup"><span data-stu-id="8cc11-108">You apply the `Task.WhenAll` method to a collection of tasks.</span></span> <span data-ttu-id="8cc11-109">Применение `WhenAll` возвращает одну задачу, которая еще не завершен до завершения каждой задачи в коллекции.</span><span class="sxs-lookup"><span data-stu-id="8cc11-109">The application of `WhenAll` returns a single task that isn’t complete until every task in the collection is completed.</span></span> <span data-ttu-id="8cc11-110">Задачи отображаются для параллельного выполнения, но создаются дополнительные потоки.</span><span class="sxs-lookup"><span data-stu-id="8cc11-110">The tasks appear to run in parallel, but no additional threads are created.</span></span> <span data-ttu-id="8cc11-111">Задачи можно выполнить в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="8cc11-111">The tasks can complete in any order.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8cc11-112">Следующие процедуры описывают расширения для асинхронных приложений, разработанных в [Пошаговое руководство: доступ к Интернету с помощью Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="8cc11-112">The following procedures describe extensions to the async applications that are developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="8cc11-113">Можно разрабатывать приложения, выполнив Пошаговое руководство или загрузка кода из [образцы кода разработчика](http://go.microsoft.com/fwlink/?LinkId=255191).</span><span class="sxs-lookup"><span data-stu-id="8cc11-113">You can develop the applications by either completing the walkthrough or downloading the code from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191).</span></span>  
>   
>  <span data-ttu-id="8cc11-114">Для выполнения данного примера необходимо установить Visual Studio 2012 или более поздней версии, установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8cc11-114">To run the example, you must have Visual Studio 2012 or later installed on your computer.</span></span>  
  
### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a><span data-ttu-id="8cc11-115">Добавление в решение GetURLContentsAsync метода Task.WhenAll</span><span class="sxs-lookup"><span data-stu-id="8cc11-115">To add Task.WhenAll to your GetURLContentsAsync solution</span></span>  
  
1.  <span data-ttu-id="8cc11-116">Добавить `ProcessURLAsync` метода к первому приложению, которое разрабатывается в [Пошаговое руководство: доступ к Интернету с помощью Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="8cc11-116">Add the `ProcessURLAsync` method to the first application that's developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    -   <span data-ttu-id="8cc11-117">Если вы загрузили код из [примеров кода для разработчиков](http://go.microsoft.com/fwlink/?LinkId=255191), откройте проект AsyncWalkthrough и затем добавить `ProcessURLAsync` в файл MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="8cc11-117">If you downloaded the code from  [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191), open the AsyncWalkthrough project, and then add `ProcessURLAsync` to the MainWindow.xaml.vb file.</span></span>  
  
    -   <span data-ttu-id="8cc11-118">Если вы разработали код путем выполнения данного пошагового руководства, добавьте `ProcessURLAsync` в приложение, которое включает в себя `GetURLContentsAsync` метод.</span><span class="sxs-lookup"><span data-stu-id="8cc11-118">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that includes the `GetURLContentsAsync` method.</span></span> <span data-ttu-id="8cc11-119">Файл MainWindow.xaml.vb для этого приложения является первый пример в разделе «Полный код примеров из пошагового руководства».</span><span class="sxs-lookup"><span data-stu-id="8cc11-119">The MainWindow.xaml.vb file for this application is the first example in the "Complete Code Examples from the Walkthrough" section.</span></span>  
  
     <span data-ttu-id="8cc11-120">`ProcessURLAsync` Метод объединяет действия в теле `For Each` цикл в `SumPageSizesAsync` в исходном Пошаговое руководство.</span><span class="sxs-lookup"><span data-stu-id="8cc11-120">The `ProcessURLAsync` method consolidates the actions in the body of the `For Each` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="8cc11-121">Метод асинхронно загружает содержимое веб-сайта, заданного в виде массива байтов и затем отображает и возвращает длину массива байтов.</span><span class="sxs-lookup"><span data-stu-id="8cc11-121">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)  
  
        Dim byteArray = Await GetURLContentsAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
    ```  
  
2.  <span data-ttu-id="8cc11-122">Закомментируйте или удалите `For Each` цикл в `SumPageSizesAsync`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="8cc11-122">Comment out or delete the `For Each` loop in `SumPageSizesAsync`, as the following code shows.</span></span>  
  
    ```vb  
    'Dim total = 0  
    'For Each url In urlList  
  
    '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
  
    '    ' The previous line abbreviates the following two assignment statements.  
  
    '    ' GetURLContentsAsync returns a task. At completion, the task  
    '    ' produces a byte array.  
    '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)  
    '    'Dim urlContents As Byte() = Await getContentsTask  
  
    '    DisplayResults(url, urlContents)  
  
    '    ' Update the total.  
    '    total += urlContents.Length  
    'Next  
    ```  
  
3.  <span data-ttu-id="8cc11-123">Создайте коллекцию задач.</span><span class="sxs-lookup"><span data-stu-id="8cc11-123">Create a collection of tasks.</span></span> <span data-ttu-id="8cc11-124">Следующий код определяет [запроса](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) , при выполнении <xref:System.Linq.Enumerable.ToArray%2A>метод создает коллекцию задач, которые загружают содержимое каждого веб-сайта.</xref:System.Linq.Enumerable.ToArray%2A></span><span class="sxs-lookup"><span data-stu-id="8cc11-124">The following code defines a [query](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="8cc11-125">Задачи, запускаются при вычислении запроса.</span><span class="sxs-lookup"><span data-stu-id="8cc11-125">The tasks are started when the query is evaluated.</span></span>  
  
     <span data-ttu-id="8cc11-126">Добавьте следующий код в метод `SumPageSizesAsync` после объявления `urlList`.</span><span class="sxs-lookup"><span data-stu-id="8cc11-126">Add the following code to method `SumPageSizesAsync` after the declaration of `urlList`.</span></span>  
  
    ```vb  
    ' Create a query.   
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
        From url In urlList Select ProcessURLAsync(url)  
  
    ' Use ToArray to execute the query and start the download tasks.  
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
    ```  
  
4.  <span data-ttu-id="8cc11-127">Применить `Task.WhenAll` в коллекцию задач, `downloadTasks`.</span><span class="sxs-lookup"><span data-stu-id="8cc11-127">Apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="8cc11-128">`Task.WhenAll`Возвращает одну задачу, которая завершается после завершения всех задач в коллекцию задач.</span><span class="sxs-lookup"><span data-stu-id="8cc11-128">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>  
  
     <span data-ttu-id="8cc11-129">В следующем примере `Await` выражение ожидает завершения одной задачи, `WhenAll` возвращает.</span><span class="sxs-lookup"><span data-stu-id="8cc11-129">In the following example, the `Await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="8cc11-130">Выражение принимает значение массива целых чисел, где каждое целое число является длина загруженного веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="8cc11-130">The expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="8cc11-131">Добавьте следующий код в `SumPageSizesAsync`точно так же после кода, добавленного на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="8cc11-131">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>  
  
    ```vb  
    ' Await the completion of all the running tasks.  
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
    '' The previous line is equivalent to the following two statements.  
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
    'Dim lengths As Integer() = Await whenAllTask  
    ```  
  
5.  <span data-ttu-id="8cc11-132">Наконец, используйте <xref:System.Linq.Enumerable.Sum%2A>метод для вычисления суммы длин всех веб-сайтов.</xref:System.Linq.Enumerable.Sum%2A></span><span class="sxs-lookup"><span data-stu-id="8cc11-132">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to calculate the sum of the lengths of all the websites.</span></span> <span data-ttu-id="8cc11-133">Добавьте следующую строку в `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="8cc11-133">Add the following line to `SumPageSizesAsync`.</span></span>  
  
    ```vb  
    Dim total = lengths.Sum()  
    ```  
  
### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a><span data-ttu-id="8cc11-134">Добавление метода Task.WhenAll HttpClient.GetByteArrayAsync решение</span><span class="sxs-lookup"><span data-stu-id="8cc11-134">To add Task.WhenAll to the HttpClient.GetByteArrayAsync solution</span></span>  
  
1.  <span data-ttu-id="8cc11-135">Добавьте следующую версию `ProcessURLAsync` для второго приложения, разработанные в [Пошаговое руководство: доступ к Интернету с помощью Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="8cc11-135">Add the following version of `ProcessURLAsync` to the second application that's developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    -   <span data-ttu-id="8cc11-136">Если вы загрузили код из [примеров кода для разработчиков](http://go.microsoft.com/fwlink/?LinkId=255191), откройте проект AsyncWalkthrough_HttpClient и затем добавить `ProcessURLAsync` в файл MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="8cc11-136">If you downloaded the code from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191), open the AsyncWalkthrough_HttpClient project, and then add `ProcessURLAsync` to the MainWindow.xaml.vb file.</span></span>  
  
    -   <span data-ttu-id="8cc11-137">Если вы разработали код путем выполнения данного пошагового руководства, добавьте `ProcessURLAsync` в приложение, которое использует `HttpClient.GetByteArrayAsync` метод.</span><span class="sxs-lookup"><span data-stu-id="8cc11-137">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that uses the `HttpClient.GetByteArrayAsync` method.</span></span> <span data-ttu-id="8cc11-138">Файл MainWindow.xaml.vb для этого приложения — во втором примере в разделе «Полный код примеров из пошагового руководства».</span><span class="sxs-lookup"><span data-stu-id="8cc11-138">The MainWindow.xaml.vb file for this application is the second example in the "Complete Code Examples from the Walkthrough" section.</span></span>  
  
     <span data-ttu-id="8cc11-139">`ProcessURLAsync` Метод объединяет действия в теле `For Each` цикл в `SumPageSizesAsync` в исходном Пошаговое руководство.</span><span class="sxs-lookup"><span data-stu-id="8cc11-139">The `ProcessURLAsync` method consolidates the actions in the body of the `For Each` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="8cc11-140">Метод асинхронно загружает содержимое веб-сайта, заданного в виде массива байтов и затем отображает и возвращает длину массива байтов.</span><span class="sxs-lookup"><span data-stu-id="8cc11-140">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>  
  
     <span data-ttu-id="8cc11-141">Единственное отличие от `ProcessURLAsync` используется метод в предыдущей процедуре <xref:System.Net.Http.HttpClient>экземпляра, `client`.</xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="8cc11-141">The only difference from the `ProcessURLAsync` method in the previous procedure is the use of the <xref:System.Net.Http.HttpClient> instance, `client`.</span></span>  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
    ```  
  
2.  <span data-ttu-id="8cc11-142">Закомментируйте или удалите `For Each` цикл в `SumPageSizesAsync`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="8cc11-142">Comment out or delete the `For Each` loop in `SumPageSizesAsync`, as the following code shows.</span></span>  
  
    ```vb  
    'Dim total = 0   
    'For Each url In urlList   
    '    ' GetByteArrayAsync returns a task. At completion, the task   
    '    ' produces a byte array.   
    '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)   
  
    '    ' The following two lines can replace the previous assignment statement.   
    '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)   
    '    'Dim urlContents As Byte() = Await getContentsTask   
  
    '    DisplayResults(url, urlContents)   
  
    '    ' Update the total.   
    '    total += urlContents.Length   
    'Next  
  
    ```  
  
3.  <span data-ttu-id="8cc11-143">Определение [запроса](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) , при выполнении <xref:System.Linq.Enumerable.ToArray%2A>метод создает коллекцию задач, которые загружают содержимое каждого веб-сайта.</xref:System.Linq.Enumerable.ToArray%2A></span><span class="sxs-lookup"><span data-stu-id="8cc11-143">Define a [query](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="8cc11-144">Задачи, запускаются при вычислении запроса.</span><span class="sxs-lookup"><span data-stu-id="8cc11-144">The tasks are started when the query is evaluated.</span></span>  
  
     <span data-ttu-id="8cc11-145">Добавьте следующий код в метод `SumPageSizesAsync` после объявления `client` и `urlList`.</span><span class="sxs-lookup"><span data-stu-id="8cc11-145">Add the following code to method `SumPageSizesAsync` after the declaration of `client` and `urlList`.</span></span>  
  
    ```vb  
    ' Create a query.  
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
        From url In urlList Select ProcessURLAsync(url, client)  
  
    ' Use ToArray to execute the query and start the download tasks.  
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
    ```  
  
4.  <span data-ttu-id="8cc11-146">Затем применить `Task.WhenAll` в коллекцию задач, `downloadTasks`.</span><span class="sxs-lookup"><span data-stu-id="8cc11-146">Next, apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="8cc11-147">`Task.WhenAll`Возвращает одну задачу, которая завершается после завершения всех задач в коллекцию задач.</span><span class="sxs-lookup"><span data-stu-id="8cc11-147">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>  
  
     <span data-ttu-id="8cc11-148">В следующем примере `Await` выражение ожидает завершения одной задачи, `WhenAll` возвращает.</span><span class="sxs-lookup"><span data-stu-id="8cc11-148">In the following example, the `Await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="8cc11-149">По завершении `Await` выражение массива целых чисел, где каждое целое число является длина загруженного веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="8cc11-149">When complete, the `Await` expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="8cc11-150">Добавьте следующий код в `SumPageSizesAsync`точно так же после кода, добавленного на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="8cc11-150">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>  
  
    ```vb  
    ' Await the completion of all the running tasks.  
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
    '' The previous line is equivalent to the following two statements.  
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
    'Dim lengths As Integer() = Await whenAllTask  
    ```  
  
5.  <span data-ttu-id="8cc11-151">Наконец, используйте <xref:System.Linq.Enumerable.Sum%2A>метод, чтобы получить сумма длин всех веб-сайтов.</xref:System.Linq.Enumerable.Sum%2A></span><span class="sxs-lookup"><span data-stu-id="8cc11-151">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to get the sum of the lengths of all the websites.</span></span> <span data-ttu-id="8cc11-152">Добавьте следующую строку в `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="8cc11-152">Add the following line to `SumPageSizesAsync`.</span></span>  
  
    ```vb  
    Dim total = lengths.Sum()  
    ```  
  
### <a name="to-test-the-taskwhenall-solutions"></a><span data-ttu-id="8cc11-153">Для тестирования решения метода Task.WhenAll</span><span class="sxs-lookup"><span data-stu-id="8cc11-153">To test the Task.WhenAll solutions</span></span>  
  
-   <span data-ttu-id="8cc11-154">Для любого решения, нажмите клавишу F5 для запуска программы, а затем выберите **запустить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="8cc11-154">For either solution, choose the F5 key to run the program, and then choose the **Start** button.</span></span> <span data-ttu-id="8cc11-155">Выходные данные должны иметь выходных данных из решений, async [Пошаговое руководство: доступ к Интернету с помощью Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="8cc11-155">The output should resemble the output from the async solutions in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="8cc11-156">Тем не менее Обратите внимание, что веб-сайты отображаются в другом порядке каждый раз.</span><span class="sxs-lookup"><span data-stu-id="8cc11-156">However, notice that the websites appear in a different order each time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cc11-157">Пример</span><span class="sxs-lookup"><span data-stu-id="8cc11-157">Example</span></span>  
 <span data-ttu-id="8cc11-158">В следующем коде показано расширений в проект, использующий `GetURLContentsAsync` метод для загрузки содержимого из Интернета.</span><span class="sxs-lookup"><span data-stu-id="8cc11-158">The following code shows the extensions to the project that uses the `GetURLContentsAsync` method to download content from the web.</span></span>  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        resultsTextBox.Clear()  
  
        ' One-step async call.  
        Await SumPageSizesAsync()  
  
        '' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' Create a query.   
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url)  
  
        ' Use ToArray to execute the query and start the download tasks.  
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
  
        ' You can do other work here before awaiting.  
  
        ' Await the completion of all the running tasks.  
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
        '' The previous line is equivalent to the following two statements.  
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
        'Dim lengths As Integer() = Await whenAllTask  
  
        Dim total = lengths.Sum()  
  
        'Dim total = 0  
        'For Each url In urlList  
  
        '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
  
        '    ' The previous line abbreviates the following two assignment statements.  
  
        '    ' GetURLContentsAsync returns a task. At completion, the task  
        '    ' produces a byte array.  
        '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)  
        '    'Dim urlContents As Byte() = Await getContentsTask  
  
        '    DisplayResults(url, urlContents)  
  
        '    ' Update the total.  
        '    total += urlContents.Length  
        'NextNext  
  
        ' Display the total count for all of the web addresses.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    ' The actions from the foreach loop are moved to this async method.  
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)  
  
        Dim byteArray = Await GetURLContentsAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
  
        ' The downloaded resource ends up in the variable named content.  
        Dim content = New MemoryStream()  
  
        ' Initialize an HttpWebRequest for the current URL.  
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
        ' Send the request to the Internet resource and wait for  
        ' the response.  
        Using response As WebResponse = Await webReq.GetResponseAsync()  
            ' Get the data stream that is associated with the specified URL.  
            Using responseStream As Stream = response.GetResponseStream()  
                ' Read the bytes in responseStream and copy them to content.    
                ' CopyToAsync returns a Task, not a Task<T>.  
                Await responseStream.CopyToAsync(content)  
            End Using  
        End Using  
  
        ' Return the result as a byte array.  
        Return content.ToArray()  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
## <a name="example"></a><span data-ttu-id="8cc11-159">Пример</span><span class="sxs-lookup"><span data-stu-id="8cc11-159">Example</span></span>  
 <span data-ttu-id="8cc11-160">В следующем коде показано расширений в проект, использующий метод `HttpClient.GetByteArrayAsync` для загрузки содержимого из Интернета.</span><span class="sxs-lookup"><span data-stu-id="8cc11-160">The following code shows the extensions to the project that uses method `HttpClient.GetByteArrayAsync` to download content from the web.</span></span>  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        resultsTextBox.Clear()  
  
        '' One-step async call.  
        Await SumPageSizesAsync()  
  
        '' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Declare an HttpClient object and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' Create a query.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client)  
  
        ' Use ToArray to execute the query and start the download tasks.  
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
  
        ' You can do other work here before awaiting.  
  
        ' Await the completion of all the running tasks.  
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
        '' The previous line is equivalent to the following two statements.  
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
        'Dim lengths As Integer() = Await whenAllTask  
  
        Dim total = lengths.Sum()  
  
        ''<snippet7>  
        'Dim total = 0  
        'For Each url In urlList  
        '    ' GetByteArrayAsync returns a task. At completion, the task  
        '    ' produces a byte array.  
        '    '<snippet31>  
        '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
        '    '</snippet31>  
  
        '    ' The following two lines can replace the previous assignment statement.  
        '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)  
        '    'Dim urlContents As Byte() = Await getContentsTask  
  
        '    DisplayResults(url, urlContents)  
  
        '    ' Update the total.  
        '    total += urlContents.Length  
        'NextNext  
  
        ' Display the total count for all of the web addresses.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://www.msdn.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="8cc11-161">См. также</span><span class="sxs-lookup"><span data-stu-id="8cc11-161">See Also</span></span>  
 <span data-ttu-id="8cc11-162"><xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8cc11-162"><xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></span></span>   
<span data-ttu-id="8cc11-163"> [Пошаговое руководство: Доступ к Интернету с помощью модификатора Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)</span><span class="sxs-lookup"><span data-stu-id="8cc11-163"> [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)</span></span>
