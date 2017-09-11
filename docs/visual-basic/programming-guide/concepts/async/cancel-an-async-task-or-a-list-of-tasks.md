---
title: "Отмена асинхронной задачи или списка задач (Visual Basic) | Документы Microsoft"
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
ms.assetid: a9ee1b71-5bec-4736-a1e9-448042dd7215
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
ms.openlocfilehash: fe2df73aaf49f1b61dafcad9a6c6e0f3d014f8ec
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="cancel-an-async-task-or-a-list-of-tasks-visual-basic"></a><span data-ttu-id="a90b2-102">Отмена асинхронной задачи или списка задач (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a90b2-102">Cancel an Async Task or a List of Tasks (Visual Basic)</span></span>
<span data-ttu-id="a90b2-103">Можно настроить кнопки, который можно использовать для отмены асинхронного приложения, если вы не хотите ждать его завершения.</span><span class="sxs-lookup"><span data-stu-id="a90b2-103">You can set up a button that you can use to cancel an async application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="a90b2-104">Выполнив следующие примеры в этом разделе, можно добавить кнопку отмены для приложения, которое загружает содержимое из одного веб-сайта или список веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="a90b2-104">By following the examples in this topic, you can add a cancellation button to an application that downloads the contents of one website or a list of websites.</span></span>  
  
 <span data-ttu-id="a90b2-105">В примерах используется пользовательский Интерфейс, [Fine-Tuning асинхронного приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) описание.</span><span class="sxs-lookup"><span data-stu-id="a90b2-105">The examples use the UI that [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) describes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a90b2-106">Для выполнения примеров, необходимо иметь Visual Studio 2012 или более поздней версии и платформы .NET Framework 4.5 или более новая версия вашего компьютера.</span><span class="sxs-lookup"><span data-stu-id="a90b2-106">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
##  <span data-ttu-id="a90b2-107"><a name="BKMK_CancelaTask"></a>Отмена задачи</span><span class="sxs-lookup"><span data-stu-id="a90b2-107"><a name="BKMK_CancelaTask"></a> Cancel a Task</span></span>  
 <span data-ttu-id="a90b2-108">Первый пример связывает **отменить** кнопка с задачей «загрузки».</span><span class="sxs-lookup"><span data-stu-id="a90b2-108">The first example associates the **Cancel** button with a single download task.</span></span> <span data-ttu-id="a90b2-109">При нажатии кнопки при загрузке содержимого приложения загрузки отменяется.</span><span class="sxs-lookup"><span data-stu-id="a90b2-109">If you choose the button while the application is downloading content, the download is canceled.</span></span>  
  
### <a name="downloading-the-example"></a><span data-ttu-id="a90b2-110">Загрузка примера</span><span class="sxs-lookup"><span data-stu-id="a90b2-110">Downloading the Example</span></span>  
 <span data-ttu-id="a90b2-111">Можно загрузить весь проект Windows Presentation Foundation (WPF) из [образец Async: нормально Настройка приложения](http://go.microsoft.com/fwlink/?LinkId=255046) и затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a90b2-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="a90b2-112">Распакуйте загруженный файл, а затем запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a90b2-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="a90b2-113">В строке меню выберите **Файл**, **Открыть**, **Проект/Решение**.</span><span class="sxs-lookup"><span data-stu-id="a90b2-113">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="a90b2-114">В **открыть проект** диалоговом откройте папку, которая содержит пример кода, который можно распаковать и откройте файл решения (SLN) для AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="a90b2-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="a90b2-115">В **обозревателе решений**, откройте контекстное меню для **CancelATask** проекта, а затем выберите **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="a90b2-115">In **Solution Explorer**, open the shortcut menu for the **CancelATask** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="a90b2-116">Нажмите клавишу F5, чтобы запустить проект.</span><span class="sxs-lookup"><span data-stu-id="a90b2-116">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="a90b2-117">Нажмите сочетание клавиш Ctrl + F5 для запуска проекта без его отладки.</span><span class="sxs-lookup"><span data-stu-id="a90b2-117">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
 <span data-ttu-id="a90b2-118">Если вы не хотите загрузить проект, можно просмотреть файлы MainWindow.xaml.vb в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="a90b2-118">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>  
  
### <a name="building-the-example"></a><span data-ttu-id="a90b2-119">Построение примера</span><span class="sxs-lookup"><span data-stu-id="a90b2-119">Building the Example</span></span>  
 <span data-ttu-id="a90b2-120">Добавьте следующие изменения **отменить** кнопку, чтобы приложение, которое загружает веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="a90b2-120">The following changes add a **Cancel** button to an application that downloads a website.</span></span> <span data-ttu-id="a90b2-121">Если не требуется загружать или построения примера, можно просмотреть окончательный продукт в разделе «Примеры завершения» в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="a90b2-121">If you don't want to download or build the example, you can review the final product in the "Complete Examples" section at the end of this topic.</span></span> <span data-ttu-id="a90b2-122">Звездочки пометить изменения в коде.</span><span class="sxs-lookup"><span data-stu-id="a90b2-122">Asterisks mark the changes in the code.</span></span>  
  
 <span data-ttu-id="a90b2-123">Для построения примера самостоятельно, шаг за шагом, следуйте инструкциям в разделе «Загрузка пример», но выбрать **StarterCode** как **запускаемый проект** вместо **CancelATask**.</span><span class="sxs-lookup"><span data-stu-id="a90b2-123">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **StarterCode** as the **StartUp Project** instead of **CancelATask**.</span></span>  
  
 <span data-ttu-id="a90b2-124">Затем добавьте следующие изменения в файл MainWindow.xaml.vb этого проекта.</span><span class="sxs-lookup"><span data-stu-id="a90b2-124">Then add the following changes to the MainWindow.xaml.vb file of that project.</span></span>  
  
1.  <span data-ttu-id="a90b2-125">Объявите `CancellationTokenSource` переменной, `cts`, в области для всех методов, которые к нему доступ.</span><span class="sxs-lookup"><span data-stu-id="a90b2-125">Declare a `CancellationTokenSource` variable, `cts`, that’s in scope for all methods that access it.</span></span>  
  
    ```vb  
    Class MainWindow  
  
        ' ***Declare a System.Threading.CancellationTokenSource.  
        Dim cts As CancellationTokenSource  
    ```  
  
2.  <span data-ttu-id="a90b2-126">Добавьте следующий обработчик событий для **отменить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="a90b2-126">Add the following event handler for the **Cancel** button.</span></span> <span data-ttu-id="a90b2-127">Обработчик событий использует <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>метод для уведомления `cts` когда пользователь запрашивает отмену.</xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a90b2-127">The event handler uses the <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName> method to notify `cts` when the user requests cancellation.</span></span>  
  
    ```vb  
    ' ***Add an event handler for the Cancel button.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
    ```  
  
3.  <span data-ttu-id="a90b2-128">Сделать следующие изменения в событии обработчик для **запустить** кнопки `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="a90b2-128">Make the following changes in the event handler for the **Start** button, `startButton_Click`.</span></span>  
  
    -   <span data-ttu-id="a90b2-129">Создать экземпляр `CancellationTokenSource`, `cts`.</span><span class="sxs-lookup"><span data-stu-id="a90b2-129">Instantiate the `CancellationTokenSource`, `cts`.</span></span>  
  
        ```vb  
        ' ***Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
        ```  
  
    -   <span data-ttu-id="a90b2-130">При вызове `AccessTheWebAsync`, которое загружает содержимое указанной веб-сайта, отправляют <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName>свойство `cts` как аргумент.</xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a90b2-130">In the call to `AccessTheWebAsync`, which downloads the contents of a specified website, send the <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName> property of `cts` as an argument.</span></span> <span data-ttu-id="a90b2-131">`Token` Свойство распространяется сообщение при запросе отмены.</span><span class="sxs-lookup"><span data-stu-id="a90b2-131">The `Token` property propagates the message if cancellation is requested.</span></span> <span data-ttu-id="a90b2-132">Добавьте блок catch, который отображает сообщение, если пользователь решает отменить операцию загрузки.</span><span class="sxs-lookup"><span data-stu-id="a90b2-132">Add a catch block that displays a message if the user chooses to cancel the download operation.</span></span> <span data-ttu-id="a90b2-133">В следующем коде показано изменения.</span><span class="sxs-lookup"><span data-stu-id="a90b2-133">The following code shows the changes.</span></span>  
  
        ```vb  
        Try  
            ' ***Send a token to carry the message if cancellation is requested.  
            Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
            ' *** If cancellation is requested, an OperationCanceledException results.  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf  
        End Try  
        ```  
  
4.  <span data-ttu-id="a90b2-134">В `AccessTheWebAsync`, используйте <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName>перегрузки `GetAsync` метод <xref:System.Net.Http.HttpClient>типа, чтобы загрузить содержимое веб-сайта.</xref:System.Net.Http.HttpClient> </xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a90b2-134">In `AccessTheWebAsync`, use the  <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName> overload of the `GetAsync` method in the <xref:System.Net.Http.HttpClient> type to download the contents of a website.</span></span> <span data-ttu-id="a90b2-135">Передайте `ct`, <xref:System.Threading.CancellationToken>параметр `AccessTheWebAsync`, как второй аргумент.</xref:System.Threading.CancellationToken></span><span class="sxs-lookup"><span data-stu-id="a90b2-135">Pass `ct`, the <xref:System.Threading.CancellationToken> parameter of `AccessTheWebAsync`, as the second argument.</span></span> <span data-ttu-id="a90b2-136">Маркер содержит сообщение, если пользователь нажимает кнопку **отменить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="a90b2-136">The token carries the message if the user chooses the **Cancel** button.</span></span>  
  
     <span data-ttu-id="a90b2-137">В следующем коде показано изменения в `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="a90b2-137">The following code shows the changes in `AccessTheWebAsync`.</span></span>  
  
    ```vb  
    ' ***Provide a parameter for the CancellationToken.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)  
  
        Dim client As HttpClient = New HttpClient()  
  
        resultsTextBox.Text &=  
            String.Format(vbCrLf & "Ready to download." & vbCrLf)  
  
        ' You might need to slow things down to have a chance to cancel.  
        Await Task.Delay(250)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' ***The ct argument carries the message if the Cancel button is chosen.  
        Dim response As HttpResponseMessage = Await client.GetAsync("http://msdn.microsoft.com/library/dd470362.aspx", ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ' The result of the method is the length of the downloaded website.  
        Return urlContents.Length  
    End Function  
    ```  
  
5.  <span data-ttu-id="a90b2-138">Если не отменить программы, он выдает следующий результат.</span><span class="sxs-lookup"><span data-stu-id="a90b2-138">If you don’t cancel the program, it produces the following output.</span></span>  
  
    ```  
    Ready to download.  
    Length of the downloaded string: 158125.  
    ```  
  
     <span data-ttu-id="a90b2-139">При выборе **отменить** кнопки, прежде чем программа завершает загрузку содержимого, программа выдает следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="a90b2-139">If you choose the **Cancel** button before the program finishes downloading the content, the program produces the following output.</span></span>  
  
    ```  
    Ready to download.  
    Download canceled.  
    ```  
  
##  <span data-ttu-id="a90b2-140"><a name="BKMK_CancelaListofTasks"></a>Отмена список задач</span><span class="sxs-lookup"><span data-stu-id="a90b2-140"><a name="BKMK_CancelaListofTasks"></a> Cancel a List of Tasks</span></span>  
 <span data-ttu-id="a90b2-141">Вы можете расширить предыдущий пример, чтобы отменить многие задачи, связав же `CancellationTokenSource` экземпляра для каждой задачи.</span><span class="sxs-lookup"><span data-stu-id="a90b2-141">You can extend the previous example to cancel many tasks by associating the same `CancellationTokenSource` instance with each task.</span></span> <span data-ttu-id="a90b2-142">При выборе **отменить** кнопку Отменить все задачи, которые еще не завершено.</span><span class="sxs-lookup"><span data-stu-id="a90b2-142">If you choose the **Cancel** button, you cancel all tasks that aren’t yet complete.</span></span>  
  
### <a name="downloading-the-example"></a><span data-ttu-id="a90b2-143">Загрузка примера</span><span class="sxs-lookup"><span data-stu-id="a90b2-143">Downloading the Example</span></span>  
 <span data-ttu-id="a90b2-144">Можно загрузить весь проект Windows Presentation Foundation (WPF) из [образец Async: нормально Настройка приложения](http://go.microsoft.com/fwlink/?LinkId=255046) и затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a90b2-144">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="a90b2-145">Распакуйте загруженный файл, а затем запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a90b2-145">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="a90b2-146">В строке меню выберите **Файл**, **Открыть**, **Проект/Решение**.</span><span class="sxs-lookup"><span data-stu-id="a90b2-146">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="a90b2-147">В **открыть проект** диалоговом откройте папку, которая содержит пример кода, который можно распаковать и откройте файл решения (SLN) для AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="a90b2-147">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="a90b2-148">В **обозревателе решений**, откройте контекстное меню для **CancelAListOfTasks** проекта, а затем выберите **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="a90b2-148">In **Solution Explorer**, open the shortcut menu for the **CancelAListOfTasks** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="a90b2-149">Нажмите клавишу F5, чтобы запустить проект.</span><span class="sxs-lookup"><span data-stu-id="a90b2-149">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="a90b2-150">Нажмите сочетание клавиш Ctrl + F5 для запуска проекта без его отладки.</span><span class="sxs-lookup"><span data-stu-id="a90b2-150">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
 <span data-ttu-id="a90b2-151">Если вы не хотите загрузить проект, можно просмотреть файлы MainWindow.xaml.vb в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="a90b2-151">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>  
  
### <a name="building-the-example"></a><span data-ttu-id="a90b2-152">Построение примера</span><span class="sxs-lookup"><span data-stu-id="a90b2-152">Building the Example</span></span>  
 <span data-ttu-id="a90b2-153">Чтобы распространить пример самостоятельно, шаг за шагом, следуйте инструкциям в разделе «Загрузка пример», но выбрать **CancelATask** как **запускаемый проект**.</span><span class="sxs-lookup"><span data-stu-id="a90b2-153">To extend the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelATask** as the **StartUp Project**.</span></span> <span data-ttu-id="a90b2-154">Добавьте следующие изменения для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="a90b2-154">Add the following changes to that project.</span></span> <span data-ttu-id="a90b2-155">Звездочки отметить изменения в программе.</span><span class="sxs-lookup"><span data-stu-id="a90b2-155">Asterisks mark the changes in the program.</span></span>  
  
1.  <span data-ttu-id="a90b2-156">Добавьте метод для создания списка веб-адресов.</span><span class="sxs-lookup"><span data-stu-id="a90b2-156">Add a method to create a list of web addresses.</span></span>  
  
    ```vb  
    ' ***Add a method that creates a list of web addresses.  
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
    ```  
  
2.  <span data-ttu-id="a90b2-157">Вызовите метод в `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="a90b2-157">Call the method in `AccessTheWebAsync`.</span></span>  
  
    ```vb  
    ' ***Call SetUpURLList to make a list of web addresses.  
    Dim urlList As List(Of String) = SetUpURLList()  
    ```  
  
3.  <span data-ttu-id="a90b2-158">Добавьте следующий цикл в `AccessTheWebAsync` для обработки каждого веб-адрес в списке.</span><span class="sxs-lookup"><span data-stu-id="a90b2-158">Add the following loop in `AccessTheWebAsync` to process each web address in the list.</span></span>  
  
    ```vb  
    ' ***Add a loop to process the list of web addresses.  
    For Each url In urlList  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' Argument ct carries the message if the Cancel button is chosen.   
        ' ***Note that the Cancel button can cancel all remaining downloads.  
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        resultsTextBox.Text &=  
            String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
    Next  
    ```  
  
4.  <span data-ttu-id="a90b2-159">Поскольку `AccessTheWebAsync` отображает длину, метод не требуется возвращать.</span><span class="sxs-lookup"><span data-stu-id="a90b2-159">Because `AccessTheWebAsync` displays the lengths, the method doesn't need to return anything.</span></span> <span data-ttu-id="a90b2-160">Удалите оператор return и изменить тип возврата метода, чтобы <xref:System.Threading.Tasks.Task>вместо <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="a90b2-160">Remove the return statement, and change the return type of the method to <xref:System.Threading.Tasks.Task> instead of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
<span data-ttu-id="a90b2-161"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="a90b2-161"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span></span>  
     <span data-ttu-id="a90b2-162">Вызовите метод из `startButton_Click` с помощью инструкции вместо выражения.</span><span class="sxs-lookup"><span data-stu-id="a90b2-162">Call the method from `startButton_Click` by using a statement instead of an expression.</span></span>  
  
    ```vb  
    Await AccessTheWebAsync(cts.Token)  
    ```  
  
5.  <span data-ttu-id="a90b2-163">Если не отменить программы, он выдает следующий результат.</span><span class="sxs-lookup"><span data-stu-id="a90b2-163">If you don’t cancel the program, it produces the following output.</span></span>  
  
    ```  
  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Length of the downloaded string: 158124.  
  
    Length of the downloaded string: 204890.  
  
    Length of the downloaded string: 175488.  
  
    Length of the downloaded string: 145790.  
  
    Downloads complete.  
  
    ```  
  
     <span data-ttu-id="a90b2-164">При выборе **отменить** кнопки до завершения загрузки, выходные данные содержат длин всех загружаемых файлов, до отмены.</span><span class="sxs-lookup"><span data-stu-id="a90b2-164">If you choose the **Cancel** button before the downloads are complete, the output contains the lengths of the downloads that completed before the cancellation.</span></span>  
  
    ```  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Downloads canceled.  
  
    ```  
  
##  <span data-ttu-id="a90b2-165"><a name="BKMK_CompleteExamples"></a>Полные примеры</span><span class="sxs-lookup"><span data-stu-id="a90b2-165"><a name="BKMK_CompleteExamples"></a> Complete Examples</span></span>  
 <span data-ttu-id="a90b2-166">Следующие разделы содержат код для каждого из предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="a90b2-166">The following sections contain the code for each of the previous examples.</span></span> <span data-ttu-id="a90b2-167">Обратите внимание, что необходимо добавить ссылку <xref:System.Net.Http>.</xref:System.Net.Http></span><span class="sxs-lookup"><span data-stu-id="a90b2-167">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="a90b2-168">Вы можете загрузить проекты из [образец Async: нормально Настройка приложения](http://go.microsoft.com/fwlink/?LinkId=255046).</span><span class="sxs-lookup"><span data-stu-id="a90b2-168">You can download the projects from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
### <a name="cancel-a-task-example"></a><span data-ttu-id="a90b2-169">Отмена пример задач</span><span class="sxs-lookup"><span data-stu-id="a90b2-169">Cancel a Task Example</span></span>  
 <span data-ttu-id="a90b2-170">Ниже приведен полный файл MainWindow.xaml.vb, например, которая отменяет одну задачу.</span><span class="sxs-lookup"><span data-stu-id="a90b2-170">The following code is the complete MainWindow.xaml.vb file for the example that cancels a single task.</span></span>  
  
```vb  
' Add an Imports directive and a reference for System.Net.Http.  
Imports System.Net.Http  
  
' Add the following Imports directive for System.Threading.  
Imports System.Threading  
  
Class MainWindow  
  
    ' ***Declare a System.Threading.CancellationTokenSource.  
    Dim cts As CancellationTokenSource  
  
    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)  
        ' ***Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
  
        resultsTextBox.Clear()  
  
        Try  
            ' ***Send a token to carry the message if cancellation is requested.  
            Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
            ' *** If cancellation is requested, an OperationCanceledException results.  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf  
        End Try  
  
        ' ***Set the CancellationTokenSource to Nothing when the download is complete.  
        cts = Nothing  
    End Sub  
  
    ' ***Add an event handler for the Cancel button.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
  
    ' ***Provide a parameter for the CancellationToken.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)  
  
        Dim client As HttpClient = New HttpClient()  
  
        resultsTextBox.Text &=  
            String.Format(vbCrLf & "Ready to download." & vbCrLf)  
  
        ' You might need to slow things down to have a chance to cancel.  
        Await Task.Delay(250)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' ***The ct argument carries the message if the Cancel button is chosen.  
        Dim response As HttpResponseMessage = Await client.GetAsync("http://msdn.microsoft.com/library/dd470362.aspx", ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ' The result of the method is the length of the downloaded website.  
        Return urlContents.Length  
    End Function  
End Class  
  
' Output for a successful download:  
  
' Ready to download.  
  
' Length of the downloaded string: 158125.  
  
' Or, if you cancel:  
  
' Ready to download.  
  
' Download canceled.  
```  
  
### <a name="cancel-a-list-of-tasks-example"></a><span data-ttu-id="a90b2-171">Отмена список пример задач</span><span class="sxs-lookup"><span data-stu-id="a90b2-171">Cancel a List of Tasks Example</span></span>  
 <span data-ttu-id="a90b2-172">Ниже приведен полный файл MainWindow.xaml.vb пример отменяет список задач.</span><span class="sxs-lookup"><span data-stu-id="a90b2-172">The following code is the complete MainWindow.xaml.vb file for the example that cancels a list of tasks.</span></span>  
  
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
            ' ***AccessTheWebAsync returns a Task, not a Task(Of Integer).  
            Await AccessTheWebAsync(cts.Token)  
            '  ***Small change in the display lines.  
            resultsTextBox.Text &= vbCrLf & "Downloads complete."  
  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf  
        End Try  
  
        ' Set the CancellationTokenSource to Nothing when the download is complete.  
        cts = Nothing  
    End Sub  
  
    ' Add an event handler for the Cancel button.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
  
    ' Provide a parameter for the CancellationToken.  
    ' ***Change the return type to Task because the method has no return statement.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task  
  
        Dim client As HttpClient = New HttpClient()  
  
        ' ***Call SetUpURLList to make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' ***Add a loop to process the list of web addresses.  
        For Each url In urlList  
            ' GetAsync returns a Task(Of HttpResponseMessage).   
            ' Argument ct carries the message if the Cancel button is chosen.   
            ' ***Note that the Cancel button can cancel all remaining downloads.  
            Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
            ' Retrieve the website contents from the HttpResponseMessage.  
            Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        Next  
    End Function  
  
    ' ***Add a method that creates a list of web addresses.  
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
  
' Output if you do not choose to cancel:  
  
' Length of the downloaded string: 35939.  
  
' Length of the downloaded string: 237682.  
  
' Length of the downloaded string: 128607.  
  
' Length of the downloaded string: 158124.  
  
' Length of the downloaded string: 204890.  
  
' Length of the downloaded string: 175488.  
  
' Length of the downloaded string: 145790.  
  
' Downloads complete.  
  
'  Sample output if you choose to cancel:  
  
' Length of the downloaded string: 35939.  
  
' Length of the downloaded string: 237682.  
  
' Length of the downloaded string: 128607.  
  
' Downloads canceled.  
```  
  
## <a name="see-also"></a><span data-ttu-id="a90b2-173">См. также</span><span class="sxs-lookup"><span data-stu-id="a90b2-173">See Also</span></span>  
 <span data-ttu-id="a90b2-174"><xref:System.Threading.CancellationTokenSource></xref:System.Threading.CancellationTokenSource></span><span class="sxs-lookup"><span data-stu-id="a90b2-174"><xref:System.Threading.CancellationTokenSource></span></span>   
 <span data-ttu-id="a90b2-175"><xref:System.Threading.CancellationToken></xref:System.Threading.CancellationToken></span><span class="sxs-lookup"><span data-stu-id="a90b2-175"><xref:System.Threading.CancellationToken></span></span>   
<span data-ttu-id="a90b2-176"> [Асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="a90b2-176"> [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="a90b2-177"> [Настройка асинхронного приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span><span class="sxs-lookup"><span data-stu-id="a90b2-177"> [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span></span>  
<span data-ttu-id="a90b2-178"> [Пример асинхронности: Точная настройка приложения](http://go.microsoft.com/fwlink/?LinkId=255046)</span><span class="sxs-lookup"><span data-stu-id="a90b2-178"> [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046)</span></span>
