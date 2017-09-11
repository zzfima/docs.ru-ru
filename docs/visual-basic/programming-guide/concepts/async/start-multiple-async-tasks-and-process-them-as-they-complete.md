---
title: "Запуск нескольких асинхронных задач и их обработка по мере завершения (Visual Basic) | Документы Microsoft"
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
ms.assetid: 57ffb748-af40-4794-bedd-bdb7fea062de
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6fbf4611ecd64abfd016963dff887d82aad333b7
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-visual-basic"></a><span data-ttu-id="7a798-102">Запуск нескольких асинхронных задач и их обработка по мере завершения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a798-102">Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)</span></span>
<span data-ttu-id="7a798-103">С помощью <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>, можно запустить несколько задач одновременно и обрабатывать их один за другим, как они время завершения, а не их обработки в порядке, в котором они запущены.</xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7a798-103">By using <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>, you can start multiple tasks at the same time and process them one by one as they’re completed rather than process them in the order in which they're started.</span></span>  
  
 <span data-ttu-id="7a798-104">В следующем примере запроса для создания коллекции задач.</span><span class="sxs-lookup"><span data-stu-id="7a798-104">The following example uses a query to create a collection of tasks.</span></span> <span data-ttu-id="7a798-105">Каждая задача загружает содержимое указанной веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="7a798-105">Each task downloads the contents of a specified website.</span></span> <span data-ttu-id="7a798-106">В каждой итерации некоторое время цикла, ожидаемый вызов `WhenAny` возвращает задачи в коллекцию задач, сначала завершения его загрузки.</span><span class="sxs-lookup"><span data-stu-id="7a798-106">In each iteration of a while loop, an awaited call to `WhenAny` returns the task in the collection of tasks that finishes its download first.</span></span> <span data-ttu-id="7a798-107">Эта задача удаляется из коллекции и обработки.</span><span class="sxs-lookup"><span data-stu-id="7a798-107">That task is removed from the collection and processed.</span></span> <span data-ttu-id="7a798-108">Цикл повторяется, пока коллекция не содержит несколько задач.</span><span class="sxs-lookup"><span data-stu-id="7a798-108">The loop repeats until the collection contains no more tasks.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a798-109">Для выполнения примеров, необходимо иметь Visual Studio 2012 или более поздней версии и платформы .NET Framework 4.5 или более новая версия вашего компьютера.</span><span class="sxs-lookup"><span data-stu-id="7a798-109">To run the examples, you must have Visual Studio 2012 or newer and  the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="7a798-110">Загрузка примера</span><span class="sxs-lookup"><span data-stu-id="7a798-110">Downloading the Example</span></span>  
 <span data-ttu-id="7a798-111">Можно загрузить весь проект Windows Presentation Foundation (WPF) из [образец Async: нормально Настройка приложения](http://go.microsoft.com/fwlink/?LinkId=255046) и затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7a798-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="7a798-112">Распакуйте загруженный файл, а затем запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7a798-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="7a798-113">В строке меню выберите **Файл**, **Открыть**, **Проект/Решение**.</span><span class="sxs-lookup"><span data-stu-id="7a798-113">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="7a798-114">В **открыть проект** диалоговом откройте папку, которая содержит пример кода, который можно распаковать и откройте файл решения (SLN) для AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="7a798-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="7a798-115">В **обозревателе решений**, откройте контекстное меню для **ProcessTasksAsTheyFinish** проекта, а затем выберите **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="7a798-115">In **Solution Explorer**, open the shortcut menu for the **ProcessTasksAsTheyFinish** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="7a798-116">Нажмите клавишу F5, чтобы запустить проект.</span><span class="sxs-lookup"><span data-stu-id="7a798-116">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="7a798-117">Нажмите сочетание клавиш Ctrl + F5 для запуска проекта без его отладки.</span><span class="sxs-lookup"><span data-stu-id="7a798-117">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6.  <span data-ttu-id="7a798-118">Запустите проект несколько раз, чтобы убедиться, что загруженный длины не всегда отображаются в том же порядке.</span><span class="sxs-lookup"><span data-stu-id="7a798-118">Run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>  
  
 <span data-ttu-id="7a798-119">Если вы не хотите загрузить проект, можно просмотреть файл MainWindow.xaml.vb в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="7a798-119">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="7a798-120">Построение примера</span><span class="sxs-lookup"><span data-stu-id="7a798-120">Building the Example</span></span>  
 <span data-ttu-id="7a798-121">В этом примере добавляется код, который был разработан в [отмена оставшихся асинхронных задач после одного завершено (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) и использует тот же пользовательский Интерфейс.</span><span class="sxs-lookup"><span data-stu-id="7a798-121">This example adds to the code that’s developed in [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) and uses the same UI.</span></span>  
  
 <span data-ttu-id="7a798-122">Для построения примера самостоятельно, шаг за шагом, следуйте инструкциям в разделе «Загрузка пример», но выбрать **CancelAfterOneTask** как **запускаемый проект**.</span><span class="sxs-lookup"><span data-stu-id="7a798-122">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAfterOneTask** as the **StartUp Project**.</span></span> <span data-ttu-id="7a798-123">Добавьте в этот раздел, чтобы изменения `AccessTheWebAsync` метод в этом проекте.</span><span class="sxs-lookup"><span data-stu-id="7a798-123">Add the changes in this topic to the `AccessTheWebAsync` method in that project.</span></span> <span data-ttu-id="7a798-124">Изменения помечаются звездочками.</span><span class="sxs-lookup"><span data-stu-id="7a798-124">The changes are marked with asterisks.</span></span>  
  
 <span data-ttu-id="7a798-125">**CancelAfterOneTask** проект уже содержит запрос, при выполнении создает коллекцию задач.</span><span class="sxs-lookup"><span data-stu-id="7a798-125">The **CancelAfterOneTask** project already includes a query that, when executed, creates a collection of tasks.</span></span> <span data-ttu-id="7a798-126">Каждый вызов `ProcessURLAsync` в следующем коде возвращает <xref:System.Threading.Tasks.Task%601>где `TResult` является целым числом.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="7a798-126">Each call to `ProcessURLAsync` in the following code returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>  
  
<span data-ttu-id="7a798-127"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7a798-127"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="7a798-128">В файле MainWindow.xaml.vb проекта, внесите следующие изменения в `AccessTheWebAsync` метод.</span><span class="sxs-lookup"><span data-stu-id="7a798-128">In the MainWindow.xaml.vb file of the  project, make the following changes to the `AccessTheWebAsync` method.</span></span>  
  
-   <span data-ttu-id="7a798-129">Выполните запрос, применяя <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>вместо <xref:System.Linq.Enumerable.ToArray%2A>.</xref:System.Linq.Enumerable.ToArray%2A> </xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7a798-129">Execute the query by applying <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> instead of <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
<span data-ttu-id="7a798-130"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7a798-130"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
-   <span data-ttu-id="7a798-131">Добавить некоторое время цикла, который выполняет следующие действия для каждой задачи в коллекции.</span><span class="sxs-lookup"><span data-stu-id="7a798-131">Add a while loop that performs the following steps for each task in the collection.</span></span>  
  
    1.  <span data-ttu-id="7a798-132">Ожидает вызова `WhenAny` для определения первой задачи в коллекции, чтобы завершить его загрузки.</span><span class="sxs-lookup"><span data-stu-id="7a798-132">Awaits a call to `WhenAny` to identify the first task in the collection to finish its download.</span></span>  
  
<span data-ttu-id="7a798-133"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7a798-133"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
    2.  <span data-ttu-id="7a798-134">Эта задача удаляет из коллекции.</span><span class="sxs-lookup"><span data-stu-id="7a798-134">Removes that task from the collection.</span></span>  
  
<span data-ttu-id="7a798-135"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7a798-135"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span></span>  
    3.  <span data-ttu-id="7a798-136">Ждет `firstFinishedTask`, который возвращается при вызове `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="7a798-136">Awaits `firstFinishedTask`, which is returned by a call to `ProcessURLAsync`.</span></span> <span data-ttu-id="7a798-137">`firstFinishedTask` Переменная <xref:System.Threading.Tasks.Task%601>где `TReturn` является целым числом.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="7a798-137">The `firstFinishedTask` variable is a <xref:System.Threading.Tasks.Task%601> where `TReturn` is an integer.</span></span> <span data-ttu-id="7a798-138">Задача уже завершена, но Ожидание получения длина загруженного веб-сайта, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7a798-138">The task is already complete, but you await it to retrieve the length of the downloaded website, as the following example shows.</span></span>  
  
        ```vb  
        Dim length = Await firstFinishedTask  
        resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
        ```  
  
 <span data-ttu-id="7a798-139">Следует запустить проект несколько раз, чтобы убедиться, что загруженный длины не всегда отображаются в том же порядке.</span><span class="sxs-lookup"><span data-stu-id="7a798-139">You should run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7a798-140">Можно использовать `WhenAny` в цикле, как описано в примере, чтобы устранить проблемы, включающие небольшое количество задач.</span><span class="sxs-lookup"><span data-stu-id="7a798-140">You can use `WhenAny` in a loop, as described in the example, to solve problems that involve a small number of tasks.</span></span> <span data-ttu-id="7a798-141">Однако когда требуется обработка большого числа задач, другие методы будут более эффективны.</span><span class="sxs-lookup"><span data-stu-id="7a798-141">However, other approaches are more efficient if you have a large number of tasks to process.</span></span> <span data-ttu-id="7a798-142">Дополнительные сведения и примеры см. в разделе [обработки задач, как они завершения](http://go.microsoft.com/fwlink/?LinkId=260810).</span><span class="sxs-lookup"><span data-stu-id="7a798-142">For more information and examples, see [Processing Tasks as they complete](http://go.microsoft.com/fwlink/?LinkId=260810).</span></span>  
  
## <a name="complete-example"></a><span data-ttu-id="7a798-143">Полный пример</span><span class="sxs-lookup"><span data-stu-id="7a798-143">Complete Example</span></span>  
 <span data-ttu-id="7a798-144">Ниже приведен полный текст файла MainWindow.xaml.vb для примера.</span><span class="sxs-lookup"><span data-stu-id="7a798-144">The following code is the complete text of the MainWindow.xaml.vb file for the example.</span></span> <span data-ttu-id="7a798-145">Звездочки пометить элементы, которые были добавлены в этом примере.</span><span class="sxs-lookup"><span data-stu-id="7a798-145">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="7a798-146">Обратите внимание, что необходимо добавить ссылку <xref:System.Net.Http>.</xref:System.Net.Http></span><span class="sxs-lookup"><span data-stu-id="7a798-146">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="7a798-147">Можно загрузить проект из [образец Async: нормально Настройка приложения](http://go.microsoft.com/fwlink/?LinkId=255046).</span><span class="sxs-lookup"><span data-stu-id="7a798-147">You can download the project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
```vb  
' Add an Imports directive and a reference for System.Net.Http.  
Imports System.Net.Http  
  
' Add the following Imports directive for System.Threading.  
Imports System.Threading  
  
Class MainWindow  
  
    ' Declare a System.Threading.CancellationTokenSource.  
    Dim cts As CancellationTokenSource  
  
    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)  
  
        ' Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
  
        resultsTextBox.Clear()  
  
        Try  
            Await AccessTheWebAsync(cts.Token)  
            resultsTextBox.Text &= vbCrLf & "Downloads complete."  
  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf  
        End Try  
  
        ' Set the CancellationTokenSource to Nothing when the download is complete.  
        cts = Nothing  
    End Sub  
  
    ' You can still include a Cancel button if you want to.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
  
    ' Provide a parameter for the CancellationToken.  
    ' Change the return type to Task because the method has no return statement.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task  
  
        Dim client As HttpClient = New HttpClient()  
  
        ' Call SetUpURLList to make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' ***Create a query that, when executed, returns a collection of tasks.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client, ct)  
  
        ' ***Use ToList to execute the query and start the download tasks.   
        Dim downloadTasks As List(Of Task(Of Integer)) = downloadTasksQuery.ToList()  
  
        ' ***Add a loop to process the tasks one at a time until none remain.  
        While downloadTasks.Count > 0  
            ' ***Identify the first task that completes.  
            Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
  
            ' ***Remove the selected task from the list so that you don't  
            ' process it more than once.  
            downloadTasks.Remove(firstFinishedTask)  
  
            ' ***Await the first completed task and display the results.  
            Dim length = Await firstFinishedTask  
            resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
        End While  
  
    End Function  
  
    ' Bundle the processing steps for a website into one async method.  
    Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        Return urlContents.Length  
    End Function  
  
    ' Add a method that creates a list of web addresses.  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
End Class  
  
' Sample output:  
  
' Length of the download:  226093  
' Length of the download:  412588  
' Length of the download:  175490  
' Length of the download:  204890  
' Length of the download:  158855  
' Length of the download:  145790  
' Length of the download:  44908  
' Downloads complete.  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a798-148">См. также</span><span class="sxs-lookup"><span data-stu-id="7a798-148">See Also</span></span>  
 <span data-ttu-id="7a798-149"><xref:System.Threading.Tasks.Task.WhenAny%2A></xref:System.Threading.Tasks.Task.WhenAny%2A></span><span class="sxs-lookup"><span data-stu-id="7a798-149"><xref:System.Threading.Tasks.Task.WhenAny%2A></span></span>   
<span data-ttu-id="7a798-150"> [Настройка асинхронного приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span><span class="sxs-lookup"><span data-stu-id="7a798-150"> [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span></span>  
<span data-ttu-id="7a798-151"> [Асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="7a798-151"> [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="7a798-152"> [Пример асинхронности: Точная настройка приложения](http://go.microsoft.com/fwlink/?LinkId=255046)</span><span class="sxs-lookup"><span data-stu-id="7a798-152"> [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046)</span></span>
