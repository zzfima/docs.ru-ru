---
title: Практическое руководство. Параллельное выполнение нескольких веб-запросов с использованием Async и Await
ms.date: 07/20/2015
ms.assetid: a894b99b-7cfd-4a38-adfb-20d24f986730
ms.openlocfilehash: 616efca79312883f17ba837d17a5ee9c97d15b34
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346140"
---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-visual-basic"></a><span data-ttu-id="383d8-102">Инструкции. Параллельное выполнение нескольких веб-запросов с помощью Async и await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="383d8-102">How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)</span></span>

<span data-ttu-id="383d8-103">В асинхронном методе задачи запускаются в момент создания.</span><span class="sxs-lookup"><span data-stu-id="383d8-103">In an async method, tasks are started when they’re created.</span></span> <span data-ttu-id="383d8-104">Оператор [await](../../../../visual-basic/language-reference/operators/await-operator.md) применяется к задаче в точке метода, где обработка не может быть продолжена до завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="383d8-104">The [Await](../../../../visual-basic/language-reference/operators/await-operator.md) operator is applied to the task at the point in the method where processing can’t continue until the task finishes.</span></span> <span data-ttu-id="383d8-105">Часто задачи ожидаются в момент создания, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="383d8-105">Often a task is awaited as soon as it’s created, as the following example shows.</span></span>

```vb
Dim result = Await someWebAccessMethodAsync(url)
```

<span data-ttu-id="383d8-106">Тем не менее можно отделить создание задачи от ее ожидания, если программа содержит другую работу, выполнение которой не зависит от завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="383d8-106">However, you can separate creating the task from awaiting the task if your program has other work to accomplish that doesn’t depend on the completion of the task.</span></span>

```vb
' The following line creates and starts the task.
Dim myTask = someWebAccessMethodAsync(url)

' While the task is running, you can do other work that does not depend
' on the results of the task.
' . . . . .

' The application of Await suspends the rest of this method until the task is
' complete.
Dim result = Await myTask
```

<span data-ttu-id="383d8-107">Между моментом запуска задачи и ее ожиданием можно запустить другие задачи.</span><span class="sxs-lookup"><span data-stu-id="383d8-107">Between starting a task and awaiting it, you can start other tasks.</span></span> <span data-ttu-id="383d8-108">Дополнительные задачи неявно выполняются параллельно, однако дополнительные потоки не создаются.</span><span class="sxs-lookup"><span data-stu-id="383d8-108">The additional tasks implicitly run in parallel, but no additional threads are created.</span></span>

<span data-ttu-id="383d8-109">Следующая программа запускает три асинхронные веб-загрузки, а затем ожидает их в том порядке, в котором они вызываются.</span><span class="sxs-lookup"><span data-stu-id="383d8-109">The following program starts three asynchronous web downloads and then awaits them in the order in which they’re called.</span></span> <span data-ttu-id="383d8-110">Обратите внимание, что при запуске программы задачи не всегда завершаются в том порядке, в котором они созданы и ожидаются.</span><span class="sxs-lookup"><span data-stu-id="383d8-110">Notice, when you run the program, that the tasks don’t always finish in the order in which they’re created and awaited.</span></span> <span data-ttu-id="383d8-111">Они начинают выполняться в момент создания, и одна или несколько задач могут завершиться прежде, чем метод достигает выражения await.</span><span class="sxs-lookup"><span data-stu-id="383d8-111">They start to run when they’re created, and one or more of the tasks might finish before the method reaches the await expressions.</span></span>

> [!NOTE]
> <span data-ttu-id="383d8-112">Для выполнения этого проекта необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="383d8-112">To complete this project, you must have Visual Studio 2012 or higher and the .NET Framework 4.5 or higher installed on your computer.</span></span>

<span data-ttu-id="383d8-113">Другой пример, в котором одновременно запускается несколько задач, см. в разделе [Практическое руководство. расширение асинхронного пошагового руководства с помощью Task. WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="383d8-113">For another example that starts multiple tasks at the same time, see [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>

<span data-ttu-id="383d8-114">Код для этого примера можно скачать на странице [Примеры кода от разработчиков](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e).</span><span class="sxs-lookup"><span data-stu-id="383d8-114">You can download the code for this example from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e).</span></span>

### <a name="to-set-up-the-project"></a><span data-ttu-id="383d8-115">Настройка проекта</span><span class="sxs-lookup"><span data-stu-id="383d8-115">To set up the project</span></span>

1. <span data-ttu-id="383d8-116">Чтобы настроить приложение WPF, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="383d8-116">To set up a WPF application, complete the following steps.</span></span> <span data-ttu-id="383d8-117">Подробные инструкции по выполнению этих действий см. в [разделе Пошаговое руководство. доступ к Интернету с помощью Async и await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="383d8-117">You can find detailed instructions for these steps in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>

    - <span data-ttu-id="383d8-118">Создайте приложение WPF, которое содержит текстовое поле и кнопку.</span><span class="sxs-lookup"><span data-stu-id="383d8-118">Create a WPF application that contains a text box and a button.</span></span> <span data-ttu-id="383d8-119">Назовите кнопку `startButton`, а текстовое поле — `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="383d8-119">Name the button `startButton`, and name the text box `resultsTextBox`.</span></span>

    - <span data-ttu-id="383d8-120">Добавьте ссылку для <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="383d8-120">Add a reference for <xref:System.Net.Http>.</span></span>

    - <span data-ttu-id="383d8-121">В файле MainWindow. XAML. vb добавьте инструкцию `Imports` для `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="383d8-121">In the MainWindow.xaml.vb file, add an `Imports` statement for `System.Net.Http`.</span></span>

### <a name="to-add-the-code"></a><span data-ttu-id="383d8-122">Добавление кода</span><span class="sxs-lookup"><span data-stu-id="383d8-122">To add the code</span></span>

1. <span data-ttu-id="383d8-123">В окне конструктора MainWindow. XAML дважды щелкните кнопку, чтобы создать обработчик событий `startButton_Click` в файле MainWindow. XAML. vb.</span><span class="sxs-lookup"><span data-stu-id="383d8-123">In the design window, MainWindow.xaml, double-click the button to create the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>

2. <span data-ttu-id="383d8-124">Скопируйте приведенный ниже код и вставьте его в текст `startButton_Click` в файле MainWindow. XAML. vb.</span><span class="sxs-lookup"><span data-stu-id="383d8-124">Copy the following code, and paste it into the body of `startButton_Click` in MainWindow.xaml.vb.</span></span>

    ```vb
    resultsTextBox.Clear()
    Await CreateMultipleTasksAsync()
    resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    ```

     <span data-ttu-id="383d8-125">Код вызывает асинхронный метод `CreateMultipleTasksAsync`, который управляет приложением.</span><span class="sxs-lookup"><span data-stu-id="383d8-125">The code calls an asynchronous method, `CreateMultipleTasksAsync`, which drives the application.</span></span>

3. <span data-ttu-id="383d8-126">Добавьте следующие вспомогательные методы в проект:</span><span class="sxs-lookup"><span data-stu-id="383d8-126">Add the following support methods to the project:</span></span>

    - <span data-ttu-id="383d8-127">`ProcessURLAsync` использует метод <xref:System.Net.Http.HttpClient> для скачивания содержимого веб-сайта в виде массива байтов.</span><span class="sxs-lookup"><span data-stu-id="383d8-127">`ProcessURLAsync` uses an <xref:System.Net.Http.HttpClient> method to download the contents of a website as a byte array.</span></span> <span data-ttu-id="383d8-128">Вспомогательный метод `ProcessURLAsync` затем отображает и возвращает длину массива.</span><span class="sxs-lookup"><span data-stu-id="383d8-128">The support method, `ProcessURLAsync` then displays and returns the length of the array.</span></span>

    - <span data-ttu-id="383d8-129">`DisplayResults` показывает число байтов в массиве байтов для каждого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="383d8-129">`DisplayResults` displays the number of bytes in the byte array for each URL.</span></span> <span data-ttu-id="383d8-130">Эти выходные данные показывают, когда именно каждая задача завершает загрузку.</span><span class="sxs-lookup"><span data-stu-id="383d8-130">This display shows when each task has finished downloading.</span></span>

     <span data-ttu-id="383d8-131">Скопируйте следующие методы и вставьте их после обработчика событий `startButton_Click` в файле MainWindow. XAML. vb.</span><span class="sxs-lookup"><span data-stu-id="383d8-131">Copy the following methods, and paste them after the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>

    ```vb
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
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub
    ```

4. <span data-ttu-id="383d8-132">Наконец, определите метод `CreateMultipleTasksAsync`, который выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="383d8-132">Finally, define method `CreateMultipleTasksAsync`, which performs the following steps.</span></span>

    - <span data-ttu-id="383d8-133">Этот метод объявляет объект `HttpClient`, который используется методом доступа <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> в `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="383d8-133">The method declares an `HttpClient` object,which you need  to access method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> in `ProcessURLAsync`.</span></span>

    - <span data-ttu-id="383d8-134">Метод создает и запускает три задачи типа <xref:System.Threading.Tasks.Task%601>, где `TResult` является целым числом.</span><span class="sxs-lookup"><span data-stu-id="383d8-134">The method creates and starts three tasks of type <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer.</span></span> <span data-ttu-id="383d8-135">При завершении каждой задачи `DisplayResults` отображает URL-адрес и длину загруженного содержимого задачи.</span><span class="sxs-lookup"><span data-stu-id="383d8-135">As each task finishes, `DisplayResults` displays the task's URL and the length of the downloaded contents.</span></span> <span data-ttu-id="383d8-136">Поскольку задачи выполняются асинхронно, порядок, в котором отображаются результаты, может отличаться от порядка, в котором они были объявлены.</span><span class="sxs-lookup"><span data-stu-id="383d8-136">Because the tasks are running asynchronously, the order in which the results appear might differ from the order in which they were declared.</span></span>

    - <span data-ttu-id="383d8-137">Метод ожидает завершения каждой задачи.</span><span class="sxs-lookup"><span data-stu-id="383d8-137">The method awaits the completion of each task.</span></span> <span data-ttu-id="383d8-138">Каждый оператор `Await` приостанавливает выполнение `CreateMultipleTasksAsync` до завершения выполнения ожидаемой задачи.</span><span class="sxs-lookup"><span data-stu-id="383d8-138">Each `Await` operator suspends execution of `CreateMultipleTasksAsync` until the awaited task is finished.</span></span> <span data-ttu-id="383d8-139">Оператор также получает возвращаемое значение вызова `ProcessURLAsync` от каждой завершенной задачи.</span><span class="sxs-lookup"><span data-stu-id="383d8-139">The operator also retrieves the return value from the call to `ProcessURLAsync` from each completed task.</span></span>

    - <span data-ttu-id="383d8-140">После завершения задач и получения целочисленных значений метод суммирует длину веб-сайтов и отображает результат.</span><span class="sxs-lookup"><span data-stu-id="383d8-140">When the tasks have been completed and the integer values have been retrieved, the method sums the lengths of the websites and displays the result.</span></span>

     <span data-ttu-id="383d8-141">Скопируйте следующий метод и вставьте его в решение.</span><span class="sxs-lookup"><span data-stu-id="383d8-141">Copy the following method, and paste it into your solution.</span></span>

    ```vb
    Private Async Function CreateMultipleTasksAsync() As Task

        ' Declare an HttpClient object, and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Create and start the tasks. As each task finishes, DisplayResults
        ' displays its length.
        Dim download1 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com", client)
        Dim download2 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)
        Dim download3 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client)

        ' Await each task.
        Dim length1 As Integer = Await download1
        Dim length2 As Integer = Await download2
        Dim length3 As Integer = Await download3

        Dim total As Integer = length1 + length2 + length3

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function
    ```

5. <span data-ttu-id="383d8-142">Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .</span><span class="sxs-lookup"><span data-stu-id="383d8-142">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

     <span data-ttu-id="383d8-143">Запустите программу несколько раз, чтобы убедиться, что три задачи не всегда завершаются в том же порядке, а порядок их завершения не обязательно совпадает с порядком, в котором они создаются и ожидаются.</span><span class="sxs-lookup"><span data-stu-id="383d8-143">Run the program several times to verify that the three tasks don’t always finish in the same order and that the order in which they finish isn't necessarily the order in which they’re created and awaited.</span></span>

## <a name="example"></a><span data-ttu-id="383d8-144">Пример</span><span class="sxs-lookup"><span data-stu-id="383d8-144">Example</span></span>

<span data-ttu-id="383d8-145">Следующий код содержит полный пример.</span><span class="sxs-lookup"><span data-stu-id="383d8-145">The following code contains the full example.</span></span>

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click
        resultsTextBox.Clear()
        Await CreateMultipleTasksAsync()
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    End Sub

    Private Async Function CreateMultipleTasksAsync() As Task

        ' Declare an HttpClient object, and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Create and start the tasks. As each task finishes, DisplayResults
        ' displays its length.
        Dim download1 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com", client)
        Dim download2 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)
        Dim download3 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client)

        ' Await each task.
        Dim length1 As Integer = Await download1
        Dim length2 As Integer = Await download2
        Dim length3 As Integer = Await download3

        Dim total As Integer = length1 + length2 + length3

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
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
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="383d8-146">См. также</span><span class="sxs-lookup"><span data-stu-id="383d8-146">See also</span></span>

- <span data-ttu-id="383d8-147">[Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) (Пошаговое руководство. Доступ к веб-сайтам с помощью модификатора Async и оператора Await (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="383d8-147">[Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)</span></span>
- [<span data-ttu-id="383d8-148">Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="383d8-148">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)
- <span data-ttu-id="383d8-149">[How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) (Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="383d8-149">[How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)</span></span>
