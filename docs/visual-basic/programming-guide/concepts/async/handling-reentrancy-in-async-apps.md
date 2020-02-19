---
title: Обработка повторного входа в асинхронных приложениях
ms.date: 07/20/2015
ms.assetid: ef3dc73d-13fb-4c5f-a686-6b84148bbffe
ms.openlocfilehash: 44c2cdbadd02aef6b2bbb32bde8bcb9b19f8360d
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452582"
---
# <a name="handling-reentrancy-in-async-apps-visual-basic"></a><span data-ttu-id="eacc6-102">Обработка повторного входа в асинхронных приложениях (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eacc6-102">Handling Reentrancy in Async Apps (Visual Basic)</span></span>

<span data-ttu-id="eacc6-103">При включении асинхронного кода в приложение следует учесть и по возможности избежать повторного входа, под которым подразумевается повторный ввод асинхронной операции до ее завершения.</span><span class="sxs-lookup"><span data-stu-id="eacc6-103">When you include asynchronous code in your app, you should consider and possibly prevent reentrancy, which refers to reentering an asynchronous operation before it has completed.</span></span> <span data-ttu-id="eacc6-104">Если не определить и не обработать возможности повторного входа, это может привести к непредвиденным результатам.</span><span class="sxs-lookup"><span data-stu-id="eacc6-104">If you don't identify and handle possibilities for reentrancy, it can cause unexpected results.</span></span>

> [!NOTE]
> <span data-ttu-id="eacc6-105">Для выполнения этого примера на компьютере должны быть установлены Visual Studio 2012 или более поздней версии и .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="eacc6-105">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

> [!NOTE]
> <span data-ttu-id="eacc6-106">Версия протокола TLS 1.2 теперь является минимальной версией для использования в разработке приложений.</span><span class="sxs-lookup"><span data-stu-id="eacc6-106">Transport Layer Security (TLS) version 1.2 is now the minimum version to use in your app development.</span></span> <span data-ttu-id="eacc6-107">Если приложение предназначено для .NET Framework более ранней версии, чем 4,7, обратитесь к следующей статье, в которой приведены рекомендации по [обеспечению безопасности транспортного уровня (TLS) с .NET Framework](../../../../framework/network-programming/tls.md).</span><span class="sxs-lookup"><span data-stu-id="eacc6-107">If your app targets a .NET Framework version earlier than 4.7, refer to the following article for [Transport Layer Security (TLS) best practices with the .NET Framework](../../../../framework/network-programming/tls.md).</span></span>

## <a name="BKMK_RecognizingReentrancy"></a> <span data-ttu-id="eacc6-108">Распознавание поддержки повторного входа</span><span class="sxs-lookup"><span data-stu-id="eacc6-108">Recognizing Reentrancy</span></span>

<span data-ttu-id="eacc6-109">В примере в этом разделе пользователь нажимает кнопку **Start**, чтобы инициировать асинхронное приложение, загружающее ряд веб-сайтов и вычисляющее общее число загруженных байтов.</span><span class="sxs-lookup"><span data-stu-id="eacc6-109">In the example in this topic, users choose a **Start** button to initiate an asynchronous app that downloads a series of websites and calculates the total number of bytes that are downloaded.</span></span> <span data-ttu-id="eacc6-110">Синхронная версия примера реагирует одинаково, независимо от того, сколько раз пользователь нажмет кнопку, поскольку после первого раза поток пользовательского интерфейса игнорирует эти события до завершения выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="eacc6-110">A synchronous version of the example would respond the same way regardless of how many times a user chooses the button because, after the first time, the UI thread ignores those events until the app finishes running.</span></span> <span data-ttu-id="eacc6-111">При этом в асинхронном приложении поток пользовательского интерфейса продолжает реагировать, и можно ввести асинхронную операцию повторно до ее завершения.</span><span class="sxs-lookup"><span data-stu-id="eacc6-111">In an asynchronous app, however, the UI thread continues to respond, and you might reenter the asynchronous operation before it has completed.</span></span>

<span data-ttu-id="eacc6-112">В следующем примере показаны ожидаемые выходные данные, если пользователь нажимает кнопку **Start** только один раз.</span><span class="sxs-lookup"><span data-stu-id="eacc6-112">The following example shows the expected output if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="eacc6-113">На экран выводится список загруженных веб-сайтов, размер которых указан в байтах.</span><span class="sxs-lookup"><span data-stu-id="eacc6-113">A list of the downloaded websites appears with the size, in bytes, of each site.</span></span> <span data-ttu-id="eacc6-114">Общее число байтов отображается в конце списка.</span><span class="sxs-lookup"><span data-stu-id="eacc6-114">The total number of bytes appears at the end.</span></span>

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

<span data-ttu-id="eacc6-115">Однако если пользователь нажимает кнопку больше одного раза, обработчик событий вызывается несколько раз и процесс загрузки будет каждый раз выполняться повторно.</span><span class="sxs-lookup"><span data-stu-id="eacc6-115">However, if the user chooses the button more than once, the event handler is invoked repeatedly, and the download process is reentered each time.</span></span> <span data-ttu-id="eacc6-116">В результате одновременно запускается несколько асинхронных операций, получаемые выходные данные чередуются и счетчик общего числа байтов выдает неоднозначные результаты.</span><span class="sxs-lookup"><span data-stu-id="eacc6-116">As a result, several asynchronous operations are running at the same time, the output interleaves the results, and the total number of bytes is confusing.</span></span>

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
6. msdn.microsoft.com/library/ms404677.aspx               197325
3. msdn.microsoft.com/library/jj155761.aspx                29019
7. msdn.microsoft.com                                            42972
4. msdn.microsoft.com/library/hh290140.aspx               117152
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591

5. msdn.microsoft.com/library/hh524395.aspx                68959
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
6. msdn.microsoft.com/library/ms404677.aspx               197325
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
7. msdn.microsoft.com                                            42972
5. msdn.microsoft.com/library/hh524395.aspx                68959
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591

6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

<span data-ttu-id="eacc6-117">Чтобы просмотреть код, создающий эти выходные данные, перейдите к концу раздела.</span><span class="sxs-lookup"><span data-stu-id="eacc6-117">You can review the code that produces this output by scrolling to the end of this topic.</span></span> <span data-ttu-id="eacc6-118">Можно поэкспериментировать с кодом, загрузив решение на локальный компьютер и затем запустив проект WebsiteDownload или воспользовавшись кодом в конце этого раздела для создания собственного проекта. Дополнительные сведения и инструкции см. в разделе [Проверка и выполнение примера приложения](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="eacc6-118">You can experiment with the code by downloading the solution to your local computer and then running the WebsiteDownload project or by using the code at the end of this topic to create your own project For more information and instructions, see [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span>

## <a name="BKMK_HandlingReentrancy"></a> <span data-ttu-id="eacc6-119">Обработка поддержки повторного входа</span><span class="sxs-lookup"><span data-stu-id="eacc6-119">Handling Reentrancy</span></span>

<span data-ttu-id="eacc6-120">Обрабатывать повторный вход можно разными способами в зависимости от того, что требуется от приложения.</span><span class="sxs-lookup"><span data-stu-id="eacc6-120">You can handle reentrancy in a variety of ways, depending on what you want your app to do.</span></span> <span data-ttu-id="eacc6-121">В этом разделе представлены следующие примеры.</span><span class="sxs-lookup"><span data-stu-id="eacc6-121">This topic presents the following examples:</span></span>

- [<span data-ttu-id="eacc6-122">Отключение кнопки запуска</span><span class="sxs-lookup"><span data-stu-id="eacc6-122">Disable the Start Button</span></span>](#BKMK_DisableTheStartButton)

  <span data-ttu-id="eacc6-123">Отключение кнопки **Start** во время выполнения операции, чтобы пользователь не мог прервать ее выполнение.</span><span class="sxs-lookup"><span data-stu-id="eacc6-123">Disable the **Start** button while the operation is running so that the user can't interrupt it.</span></span>

- [<span data-ttu-id="eacc6-124">Отмена и перезапуск операции</span><span class="sxs-lookup"><span data-stu-id="eacc6-124">Cancel and Restart the Operation</span></span>](#BKMK_CancelAndRestart)

  <span data-ttu-id="eacc6-125">Отмена выполнения любой операции, которая выполняется в тот момент, когда пользователь снова нажимает кнопку **Start**, с последующим продолжением операции, которая была запрошена последней.</span><span class="sxs-lookup"><span data-stu-id="eacc6-125">Cancel any operation that is still running when the user chooses the **Start** button again, and then let the most recently requested operation continue.</span></span>

- [<span data-ttu-id="eacc6-126">Запуск нескольких операций и постановка выходных данных в очередь</span><span class="sxs-lookup"><span data-stu-id="eacc6-126">Run Multiple Operations and Queue the Output</span></span>](#BKMK_RunMultipleOperations)

  <span data-ttu-id="eacc6-127">Разрешение всем запрошенным операциям выполняться асинхронно и настройка согласования отображения выходных данных для вывода результатов каждой операции вместе и по порядку.</span><span class="sxs-lookup"><span data-stu-id="eacc6-127">Allow all requested operations to run asynchronously, but coordinate the display of output so that the results from each operation appear together and in order.</span></span>

### <a name="BKMK_DisableTheStartButton"></a> <span data-ttu-id="eacc6-128">Отключение кнопки запуска</span><span class="sxs-lookup"><span data-stu-id="eacc6-128">Disable the Start Button</span></span>

<span data-ttu-id="eacc6-129">Можно заблокировать кнопку **Start** во время операции, отключив кнопку в верхней части обработчика событий `StartButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="eacc6-129">You can block the **Start** button while an operation is running by disabling the button at the top of the `StartButton_Click` event handler.</span></span> <span data-ttu-id="eacc6-130">Затем можно повторно включить кнопку из блока `Finally` по завершении операции, чтобы пользователь мог запустить приложение повторно.</span><span class="sxs-lookup"><span data-stu-id="eacc6-130">You can then reenable the button from within a  `Finally` block when the operation finishes so that users can run the app again.</span></span>

<span data-ttu-id="eacc6-131">В следующем коде показаны эти изменения, которые помечены звездочками.</span><span class="sxs-lookup"><span data-stu-id="eacc6-131">The following code shows these changes, which are marked with asterisks.</span></span> <span data-ttu-id="eacc6-132">Вы можете добавить изменения в код в конце этого раздела или скачать готовое приложение в разделе [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span><span class="sxs-lookup"><span data-stu-id="eacc6-132">You can add the changes to the code at the end of this topic, or you can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="eacc6-133">Имя проекта — DisableStartButton.</span><span class="sxs-lookup"><span data-stu-id="eacc6-133">The project name is DisableStartButton.</span></span>

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
    ' This line is commented out to make the results clearer in the output.
    'ResultsTextBox.Text = ""

    ' ***Disable the Start button until the downloads are complete.
    StartButton.IsEnabled = False

    Try
        Await AccessTheWebAsync()

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."
    ' ***Enable the Start button in case you want to run the program again.
    Finally
        StartButton.IsEnabled = True

    End Try
End Sub
```

<span data-ttu-id="eacc6-134">В результате этих изменений кнопка не будет реагировать в течение загрузки веб-сайтов методом `AccessTheWebAsync`, поэтому повторный вход в процесс будет невозможен.</span><span class="sxs-lookup"><span data-stu-id="eacc6-134">As a result of the changes, the button doesn't respond while `AccessTheWebAsync` is downloading the websites, so the process can’t be reentered.</span></span>

### <a name="BKMK_CancelAndRestart"></a> <span data-ttu-id="eacc6-135">Отмена и перезапуск операции</span><span class="sxs-lookup"><span data-stu-id="eacc6-135">Cancel and Restart the Operation</span></span>

<span data-ttu-id="eacc6-136">Вместо отключения кнопки **Start** можно оставить кнопку активной, но при этом, если пользователь нажмет эту кнопку еще раз, нужно отменить операцию, которая уже выполняется, и задать продолжение выполнения последней запущенной операции.</span><span class="sxs-lookup"><span data-stu-id="eacc6-136">Instead of disabling the **Start** button, you can keep the button active but, if the user chooses that button again, cancel the operation that's already running and let the most recently started operation continue.</span></span>

<span data-ttu-id="eacc6-137">Дополнительные сведения об отмене см. [в разделе тонкая настройка асинхронного приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md).</span><span class="sxs-lookup"><span data-stu-id="eacc6-137">For more information about cancellation, see [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md).</span></span>

<span data-ttu-id="eacc6-138">Чтобы настроить этот сценарий, внесите следующие изменения в основной код, который содержится в разделе [Проверка и выполнение примера приложения](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="eacc6-138">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span> <span data-ttu-id="eacc6-139">Также можно загрузить готовое приложение в разделе [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span><span class="sxs-lookup"><span data-stu-id="eacc6-139">You also can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="eacc6-140">Этот проект называется CancelAndRestart.</span><span class="sxs-lookup"><span data-stu-id="eacc6-140">The name of this project is CancelAndRestart.</span></span>

1. <span data-ttu-id="eacc6-141">Объявите переменную <xref:System.Threading.CancellationTokenSource>, `cts`, которая находится в области действия всех методов.</span><span class="sxs-lookup"><span data-stu-id="eacc6-141">Declare a <xref:System.Threading.CancellationTokenSource> variable, `cts`, that’s in scope for all methods.</span></span>

    ```vb
    Class MainWindow // Or Class MainPage

        ' *** Declare a System.Threading.CancellationTokenSource.
        Dim cts As CancellationTokenSource
    ```

2. <span data-ttu-id="eacc6-142">В `StartButton_Click` определите, выполняется ли операция на данный момент.</span><span class="sxs-lookup"><span data-stu-id="eacc6-142">In `StartButton_Click`, determine whether an operation is already underway.</span></span> <span data-ttu-id="eacc6-143">Если значение `cts` равно `Nothing`, операция уже не активна.</span><span class="sxs-lookup"><span data-stu-id="eacc6-143">If the value of `cts` is `Nothing`, no operation is already active.</span></span> <span data-ttu-id="eacc6-144">Если значение не `Nothing`, операция, которая уже выполняется, отменяется.</span><span class="sxs-lookup"><span data-stu-id="eacc6-144">If the value isn't `Nothing`, the operation that is already running is canceled.</span></span>

    ```vb
    ' *** If a download process is already underway, cancel it.
    If cts IsNot Nothing Then
        cts.Cancel()
    End If
    ```

3. <span data-ttu-id="eacc6-145">Задайте для `cts` другое значение, представляющее текущий процесс.</span><span class="sxs-lookup"><span data-stu-id="eacc6-145">Set `cts` to a different value that represents the current process.</span></span>

    ```vb
    ' *** Now set cts to cancel the current process if the button is chosen again.
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()
    cts = newCTS
    ```

4. <span data-ttu-id="eacc6-146">В конце `StartButton_Click`текущий процесс завершен, поэтому установите для параметра `cts` обратно значение `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="eacc6-146">At the end of `StartButton_Click`, the current process is complete, so set the value of `cts` back to `Nothing`.</span></span>

    ```vb
    ' *** When the process completes, signal that another process can proceed.
    If cts Is newCTS Then
        cts = Nothing
    End If
    ```

<span data-ttu-id="eacc6-147">В следующем коде показаны все изменения в `StartButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="eacc6-147">The following code shows all the changes in `StartButton_Click`.</span></span> <span data-ttu-id="eacc6-148">Добавления помечены звездочками.</span><span class="sxs-lookup"><span data-stu-id="eacc6-148">The additions are marked with asterisks.</span></span>

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)

    ' This line is commented out to make the results clearer.
    'ResultsTextBox.Text = ""

    ' *** If a download process is underway, cancel it.
    If cts IsNot Nothing Then
        cts.Cancel()
    End If

    ' *** Now set cts to cancel the current process if the button is chosen again.
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()
    cts = newCTS

    Try
        ' *** Send a token to carry the message if the operation is canceled.
        Await AccessTheWebAsync(cts.Token)

    Catch ex As OperationCanceledException
        ResultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."
    End Try

    ' *** When the process is complete, signal that another process can proceed.
    If cts Is newCTS Then
        cts = Nothing
    End If
End Sub
```

<span data-ttu-id="eacc6-149">В `AccessTheWebAsync` внесите следующие изменения.</span><span class="sxs-lookup"><span data-stu-id="eacc6-149">In `AccessTheWebAsync`, make the following changes.</span></span>

- <span data-ttu-id="eacc6-150">Добавьте параметр, чтобы принимать токен отмены из `StartButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="eacc6-150">Add a parameter to accept the cancellation token from `StartButton_Click`.</span></span>

- <span data-ttu-id="eacc6-151">Используйте метод <xref:System.Net.Http.HttpClient.GetAsync%2A> для загрузки веб-сайтов, так как `GetAsync` принимает аргумент <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="eacc6-151">Use the <xref:System.Net.Http.HttpClient.GetAsync%2A> method to download the websites because `GetAsync` accepts a <xref:System.Threading.CancellationToken> argument.</span></span>

- <span data-ttu-id="eacc6-152">Перед вызовом метода `DisplayResults` для отображения результатов для каждого загруженного веб-сайта проверьте `ct`, чтобы убедиться, что текущая операция не отменена.</span><span class="sxs-lookup"><span data-stu-id="eacc6-152">Before calling `DisplayResults` to display the results for each downloaded website, check `ct` to verify that the current operation hasn’t been canceled.</span></span>

 <span data-ttu-id="eacc6-153">В следующем коде показаны эти изменения, которые помечены звездочками.</span><span class="sxs-lookup"><span data-stu-id="eacc6-153">The following code shows these changes, which are marked with asterisks.</span></span>

```vb
' *** Provide a parameter for the CancellationToken from StartButton_Click.
Private Async Function AccessTheWebAsync(ct As CancellationToken) As Task

    ' Declare an HttpClient object.
    Dim client = New HttpClient()

    ' Make a list of web addresses.
    Dim urlList As List(Of String) = SetUpURLList()

    Dim total = 0
    Dim position = 0

    For Each url In urlList
        ' *** Use the HttpClient.GetAsync method because it accepts a
        ' cancellation token.
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

        ' *** Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        ' *** Check for cancellations before displaying information about the
        ' latest site.
        ct.ThrowIfCancellationRequested()

        position += 1
        DisplayResults(url, urlContents, position)

        ' Update the total.
        total += urlContents.Length
    Next

    ' Display the total count for all of the websites.
    ResultsTextBox.Text &=
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
End Function
```

<span data-ttu-id="eacc6-154">Если вы наберете кнопку **запустить** несколько раз во время выполнения этого приложения, оно должно вывести результаты, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="eacc6-154">If you choose the **Start** button several times while this app is running, it should produce results that resemble the following output:</span></span>

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               122505
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
Download canceled.

1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
Download canceled.

1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

<span data-ttu-id="eacc6-155">Чтобы исключить частичные списки, раскомментируйте первую строку кода в `StartButton_Click`, чтобы очищать текстовое поле при каждом перезапуске операции.</span><span class="sxs-lookup"><span data-stu-id="eacc6-155">To eliminate the partial lists, uncomment the first line of code in `StartButton_Click` to clear the text box each time the user restarts the operation.</span></span>

### <a name="BKMK_RunMultipleOperations"></a> <span data-ttu-id="eacc6-156">Запуск нескольких операций и постановка выходных данных в очередь</span><span class="sxs-lookup"><span data-stu-id="eacc6-156">Run Multiple Operations and Queue the Output</span></span>

<span data-ttu-id="eacc6-157">Третий пример является наиболее сложным, так как приложение запускает другую асинхронную операцию каждый раз, когда пользователь нажимает кнопку **Start**, и все операции выполняются до завершения.</span><span class="sxs-lookup"><span data-stu-id="eacc6-157">This third example is the most complicated in that the app starts another asynchronous operation each time that the user chooses the **Start** button, and all the operations run to completion.</span></span> <span data-ttu-id="eacc6-158">Все запрошенные операции загружают веб-сайты из списка асинхронно, однако выходные данные операций представляются последовательно.</span><span class="sxs-lookup"><span data-stu-id="eacc6-158">All the requested operations download websites from the list asynchronously, but the output from the operations is presented sequentially.</span></span> <span data-ttu-id="eacc6-159">Получается, что фактические действия загрузки чередуются, как показывают выходные данные в разделе [Распознавание возникновения повторного входа](#BKMK_RecognizingReentrancy), однако список результатов для каждой группы отображается отдельно.</span><span class="sxs-lookup"><span data-stu-id="eacc6-159">That is, the actual downloading activity is interleaved, as the output in [Recognizing Reentrancy](#BKMK_RecognizingReentrancy) shows, but the list of results for each group is presented separately.</span></span>

<span data-ttu-id="eacc6-160">Операции совместно используют глобальную переменную <xref:System.Threading.Tasks.Task>, `pendingWork`, служащую привратником для процесса отображения.</span><span class="sxs-lookup"><span data-stu-id="eacc6-160">The operations share a global <xref:System.Threading.Tasks.Task>, `pendingWork`, which serves as a gatekeeper for the display process.</span></span>

<span data-ttu-id="eacc6-161">Этот пример можно выполнить, вставив изменения в код в разделе [Сборка приложения](#BKMK_BuildingTheApp) или выполнив инструкции, приведенные в разделе [Загрузка приложения](#BKMK_DownloadingTheApp), чтобы скачать пример, а затем выполнить проект QueueResults.</span><span class="sxs-lookup"><span data-stu-id="eacc6-161">You can run this example by pasting the changes into the code in [Building the App](#BKMK_BuildingTheApp), or you can follow the instructions in [Downloading the App](#BKMK_DownloadingTheApp) to download the sample and then run the QueueResults project.</span></span>

<span data-ttu-id="eacc6-162">Ниже показаны выходные данные, отображаемые в результате нажатия кнопки **Start** только один раз.</span><span class="sxs-lookup"><span data-stu-id="eacc6-162">The following output shows the result if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="eacc6-163">Метка A указывает, что это результат первого нажатия кнопки **Start**.</span><span class="sxs-lookup"><span data-stu-id="eacc6-163">The letter label, A, indicates that the result is from the first time the **Start** button is chosen.</span></span> <span data-ttu-id="eacc6-164">Нумерация показывает порядок отображения URL-адресов в списке целевых объектов для загрузки.</span><span class="sxs-lookup"><span data-stu-id="eacc6-164">The numbers show the order of the URLs in the list of download targets.</span></span>

```console
#Starting group A.
#Task assigned for group A.

A-1. msdn.microsoft.com/library/hh191443.aspx                87389
A-2. msdn.microsoft.com/library/aa578028.aspx               209858
A-3. msdn.microsoft.com/library/jj155761.aspx                30870
A-4. msdn.microsoft.com/library/hh290140.aspx               119027
A-5. msdn.microsoft.com/library/hh524395.aspx                71260
A-6. msdn.microsoft.com/library/ms404677.aspx               199186
A-7. msdn.microsoft.com                                            53266
A-8. msdn.microsoft.com/library/ff730837.aspx               148020

TOTAL bytes returned:  918876

#Group A is complete.
```

<span data-ttu-id="eacc6-165">Если пользователь нажимает кнопку **Start** три раза, приложение выдает результат, похожий на приведенный ниже.</span><span class="sxs-lookup"><span data-stu-id="eacc6-165">If the user chooses the **Start** button three times, the app produces output that resembles the following lines.</span></span> <span data-ttu-id="eacc6-166">Информационные строки, начинающиеся с символа #, отслеживают ход выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="eacc6-166">The information lines that start with a pound sign (#) trace the progress of the application.</span></span>

```console
#Starting group A.
#Task assigned for group A.

A-1. msdn.microsoft.com/library/hh191443.aspx                87389
A-2. msdn.microsoft.com/library/aa578028.aspx               207089
A-3. msdn.microsoft.com/library/jj155761.aspx                30870
A-4. msdn.microsoft.com/library/hh290140.aspx               119027
A-5. msdn.microsoft.com/library/hh524395.aspx                71259
A-6. msdn.microsoft.com/library/ms404677.aspx               199185

#Starting group B.
#Task assigned for group B.

A-7. msdn.microsoft.com                                            53266

#Starting group C.
#Task assigned for group C.

A-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  916095

B-1. msdn.microsoft.com/library/hh191443.aspx                87389
B-2. msdn.microsoft.com/library/aa578028.aspx               207089
B-3. msdn.microsoft.com/library/jj155761.aspx                30870
B-4. msdn.microsoft.com/library/hh290140.aspx               119027
B-5. msdn.microsoft.com/library/hh524395.aspx                71260
B-6. msdn.microsoft.com/library/ms404677.aspx               199186

#Group A is complete.

B-7. msdn.microsoft.com                                            53266
B-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  916097

C-1. msdn.microsoft.com/library/hh191443.aspx                87389
C-2. msdn.microsoft.com/library/aa578028.aspx               207089

#Group B is complete.

C-3. msdn.microsoft.com/library/jj155761.aspx                30870
C-4. msdn.microsoft.com/library/hh290140.aspx               119027
C-5. msdn.microsoft.com/library/hh524395.aspx                72765
C-6. msdn.microsoft.com/library/ms404677.aspx               199186
C-7. msdn.microsoft.com                                            56190
C-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  920526

#Group C is complete.
```

<span data-ttu-id="eacc6-167">Группы B и C запускаются до завершения группы A, однако результаты для каждой группы отображаются отдельно.</span><span class="sxs-lookup"><span data-stu-id="eacc6-167">Groups B and C start before group A has finished, but the output for the each group appears separately.</span></span> <span data-ttu-id="eacc6-168">Все выходные данные для группы A отображаются сначала, затем идут все выходные данные для группы B и, наконец, для группы C. Приложение всегда отображает группы по порядку и для каждой группы всегда отображает сведения об отдельных веб-сайтах в порядке появления URL-адресов в списке URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="eacc6-168">All the output for group A appears first, followed by all the output for group B, and then all the output for group C. The app always displays the groups in order and, for each group, always displays the information about the individual websites in the order that the URLs appear in the list of URLs.</span></span>

<span data-ttu-id="eacc6-169">Тем не менее невозможно предсказать порядок, в котором фактически происходит загрузка.</span><span class="sxs-lookup"><span data-stu-id="eacc6-169">However, you can't predict the order in which the downloads actually happen.</span></span> <span data-ttu-id="eacc6-170">После запуска нескольких групп все созданные ими задачи загрузки остаются активными.</span><span class="sxs-lookup"><span data-stu-id="eacc6-170">After multiple groups have been started, the download tasks that they generate are all active.</span></span> <span data-ttu-id="eacc6-171">Не следует предполагать, что данные A-1 будут загружены до данных B-1, а данные A-1 будут загружены до данных A-2.</span><span class="sxs-lookup"><span data-stu-id="eacc6-171">You can't assume that A-1 will be downloaded before B-1, and you can't assume that A-1 will be downloaded before A-2.</span></span>

#### <a name="global-definitions"></a><span data-ttu-id="eacc6-172">Глобальные определения</span><span class="sxs-lookup"><span data-stu-id="eacc6-172">Global Definitions</span></span>

<span data-ttu-id="eacc6-173">Пример кода содержит объявление двух следующих глобальных переменных, доступных для всех методов.</span><span class="sxs-lookup"><span data-stu-id="eacc6-173">The sample code contains the following two global declarations that are visible from all methods.</span></span>

```vb
Class MainWindow    ' Class MainPage in Windows Store app.

    ' ***Declare the following variables where all methods can access them.
    Private pendingWork As Task = Nothing
    Private group As Char = ChrW(AscW("A") - 1)
```

<span data-ttu-id="eacc6-174">Переменная `Task`, `pendingWork`, отслеживает процесс отображения и предотвращает прерывание операции отображения одной группы другой группой.</span><span class="sxs-lookup"><span data-stu-id="eacc6-174">The `Task` variable, `pendingWork`, oversees the display process and prevents any group from interrupting another group's display operation.</span></span> <span data-ttu-id="eacc6-175">Символьная переменная, `group`, помечает выходные данные различных групп, чтобы гарантировать отображение результатов в ожидаемом порядке.</span><span class="sxs-lookup"><span data-stu-id="eacc6-175">The character variable, `group`, labels the output from different groups to verify that results appear in the expected order.</span></span>

#### <a name="the-click-event-handler"></a><span data-ttu-id="eacc6-176">Обработчик событий нажатия</span><span class="sxs-lookup"><span data-stu-id="eacc6-176">The Click Event Handler</span></span>

<span data-ttu-id="eacc6-177">Обработчик событий `StartButton_Click` увеличивает букву группы каждый раз, когда пользователь нажимает кнопку **Start**.</span><span class="sxs-lookup"><span data-stu-id="eacc6-177">The event handler, `StartButton_Click`, increments the group letter each time the user chooses the **Start** button.</span></span> <span data-ttu-id="eacc6-178">Затем обработчик вызывает метод `AccessTheWebAsync` для запуска операции загрузки.</span><span class="sxs-lookup"><span data-stu-id="eacc6-178">Then the handler calls `AccessTheWebAsync` to run the downloading operation.</span></span>

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
    ' ***Verify that each group's results are displayed together, and that
    ' the groups display in order, by marking each group with a letter.
    group = ChrW(AscW(group) + 1)
    ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Starting group {0}.", group)

    Try
        ' *** Pass the group value to AccessTheWebAsync.
        Dim finishedGroup As Char = Await AccessTheWebAsync(group)

        ' The following line verifies a successful return from the download and
        ' display procedures.
        ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Group {0} is complete." & vbCrLf, finishedGroup)

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."

    End Try
End Sub
```

#### <a name="the-accessthewebasync-method"></a><span data-ttu-id="eacc6-179">Метод AccessTheWebAsync</span><span class="sxs-lookup"><span data-stu-id="eacc6-179">The AccessTheWebAsync Method</span></span>

<span data-ttu-id="eacc6-180">В этом примере метод `AccessTheWebAsync` разбит на два метода.</span><span class="sxs-lookup"><span data-stu-id="eacc6-180">This example splits `AccessTheWebAsync` into two methods.</span></span> <span data-ttu-id="eacc6-181">Первый метод, `AccessTheWebAsync`, запускает все задачи загрузки для группы и передает задаче `pendingWork` управление процессом отображения.</span><span class="sxs-lookup"><span data-stu-id="eacc6-181">The first method, `AccessTheWebAsync`, starts all the download tasks for a group and sets up `pendingWork` to control the display process.</span></span> <span data-ttu-id="eacc6-182">Метод использует запрос LINQ и <xref:System.Linq.Enumerable.ToArray%2A> для запуска всех задач загрузки одновременно.</span><span class="sxs-lookup"><span data-stu-id="eacc6-182">The method uses a Language Integrated Query (LINQ query) and <xref:System.Linq.Enumerable.ToArray%2A> to start all the download tasks at the same time.</span></span>

<span data-ttu-id="eacc6-183">Затем метод `AccessTheWebAsync` вызывает метод `FinishOneGroupAsync` для ожидания завершения каждой загрузки и отображения ее длины.</span><span class="sxs-lookup"><span data-stu-id="eacc6-183">`AccessTheWebAsync` then calls `FinishOneGroupAsync` to await the completion of each download and display its length.</span></span>

<span data-ttu-id="eacc6-184">Метод `FinishOneGroupAsync` возвращает задачу, которая назначена `pendingWork`, в `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="eacc6-184">`FinishOneGroupAsync` returns a task that's assigned to `pendingWork` in `AccessTheWebAsync`.</span></span> <span data-ttu-id="eacc6-185">Это значение предотвращает прерывание другой операцией до завершения выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="eacc6-185">That value prevents interruption by another operation before the task is complete.</span></span>

```vb
Private Async Function AccessTheWebAsync(grp As Char) As Task(Of Char)

    Dim client = New HttpClient()

    ' Make a list of the web addresses to download.
    Dim urlList As List(Of String) = SetUpURLList()

    ' ***Kick off the downloads. The application of ToArray activates all the download tasks.
    Dim getContentTasks As Task(Of Byte())() =
        urlList.Select(Function(addr) client.GetByteArrayAsync(addr)).ToArray()

    ' ***Call the method that awaits the downloads and displays the results.
    ' Assign the Task that FinishOneGroupAsync returns to the gatekeeper task, pendingWork.
    pendingWork = FinishOneGroupAsync(urlList, getContentTasks, grp)

    ResultsTextBox.Text &=
        String.Format(vbCrLf & "#Task assigned for group {0}. Download tasks are active." & vbCrLf, grp)

    ' ***This task is complete when a group has finished downloading and displaying.
    Await pendingWork

    ' You can do other work here or just return.
    Return grp
End Function
```

#### <a name="the-finishonegroupasync-method"></a><span data-ttu-id="eacc6-186">Метод FinishOneGroupAsync</span><span class="sxs-lookup"><span data-stu-id="eacc6-186">The FinishOneGroupAsync Method</span></span>

<span data-ttu-id="eacc6-187">Этот метод выполняет циклический переход по задачам загрузки в группе, ожидая каждую из них, отображая длину загруженного веб-сайта и добавляя длину в общую сумму.</span><span class="sxs-lookup"><span data-stu-id="eacc6-187">This method cycles through the download tasks in a group, awaiting each one, displaying the length of the downloaded website, and adding the length to the total.</span></span>

<span data-ttu-id="eacc6-188">Первый оператор в `FinishOneGroupAsync` использует `pendingWork`, чтобы гарантировать, что ввод метода не помешает выполнению операции, которая уже находится в процессе отображения или в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="eacc6-188">The first statement in `FinishOneGroupAsync` uses `pendingWork` to make sure that entering the method doesn't interfere with an operation that is already in the display process or that's already waiting.</span></span> <span data-ttu-id="eacc6-189">Если такая операция выполняется, новая операция должна дождаться своей очереди.</span><span class="sxs-lookup"><span data-stu-id="eacc6-189">If such an operation is in progress, the entering operation must wait its turn.</span></span>

```vb
Private Async Function FinishOneGroupAsync(urls As List(Of String), contentTasks As Task(Of Byte())(), grp As Char) As Task

    ' Wait for the previous group to finish displaying results.
    If pendingWork IsNot Nothing Then
        Await pendingWork
    End If

    Dim total = 0

    ' contentTasks is the array of Tasks that was created in AccessTheWebAsync.
    For i As Integer = 0 To contentTasks.Length - 1
        ' Await the download of a particular URL, and then display the URL and
        ' its length.
        Dim content As Byte() = Await contentTasks(i)
        DisplayResults(urls(i), content, i, grp)
        total += content.Length
    Next

    ' Display the total count for all of the websites.
    ResultsTextBox.Text &=
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
End Function
```

<span data-ttu-id="eacc6-190">Этот пример можно выполнить, вставив изменения в код в разделе [Сборка приложения](#BKMK_BuildingTheApp) или выполнив инструкции, приведенные в разделе [Загрузка приложения](#BKMK_DownloadingTheApp), чтобы скачать пример, а затем выполнить проект QueueResults.</span><span class="sxs-lookup"><span data-stu-id="eacc6-190">You can run this example by pasting the changes into the code in [Building the App](#BKMK_BuildingTheApp), or you can follow the instructions in [Downloading the App](#BKMK_DownloadingTheApp) to download the sample, and then run the QueueResults project.</span></span>

#### <a name="points-of-interest"></a><span data-ttu-id="eacc6-191">Достопримечательности</span><span class="sxs-lookup"><span data-stu-id="eacc6-191">Points of Interest</span></span>

<span data-ttu-id="eacc6-192">Информационные строки, начинающиеся с символа # в выходных данных, поясняют, как работает этот пример.</span><span class="sxs-lookup"><span data-stu-id="eacc6-192">The information lines that start with a pound sign (#) in the output clarify how this example works.</span></span>

<span data-ttu-id="eacc6-193">Выходные данные демонстрируют следующие схемы.</span><span class="sxs-lookup"><span data-stu-id="eacc6-193">The output shows the following patterns.</span></span>

- <span data-ttu-id="eacc6-194">Группу можно запустить, когда предыдущая группа отображает свои выходные данные, но отображение выходных данных предыдущей группы не прерывается.</span><span class="sxs-lookup"><span data-stu-id="eacc6-194">A group can be started while a previous group is displaying its output, but the display of the previous group's output isn't interrupted.</span></span>

  ```console
  #Starting group A.
  #Task assigned for group A. Download tasks are active.

  A-1. msdn.microsoft.com/library/hh191443.aspx                87389
  A-2. msdn.microsoft.com/library/aa578028.aspx               207089
  A-3. msdn.microsoft.com/library/jj155761.aspx                30870
  A-4. msdn.microsoft.com/library/hh290140.aspx               119037
  A-5. msdn.microsoft.com/library/hh524395.aspx                71260

  #Starting group B.
  #Task assigned for group B. Download tasks are active.

  A-6. msdn.microsoft.com/library/ms404677.aspx               199186
  A-7. msdn.microsoft.com                                            53078
  A-8. msdn.microsoft.com/library/ff730837.aspx               148010

  TOTAL bytes returned:  915919

  B-1. msdn.microsoft.com/library/hh191443.aspx                87388
  B-2. msdn.microsoft.com/library/aa578028.aspx               207089
  B-3. msdn.microsoft.com/library/jj155761.aspx                30870

  #Group A is complete.

  B-4. msdn.microsoft.com/library/hh290140.aspx               119027
  B-5. msdn.microsoft.com/library/hh524395.aspx                71260
  B-6. msdn.microsoft.com/library/ms404677.aspx               199186
  B-7. msdn.microsoft.com                                            53078
  B-8. msdn.microsoft.com/library/ff730837.aspx               148010

  TOTAL bytes returned:  915908
  ```

- <span data-ttu-id="eacc6-195">Задача `pendingWork` `Nothing` в начале `FinishOneGroupAsync` только для группы A, которая была запущена первой.</span><span class="sxs-lookup"><span data-stu-id="eacc6-195">The `pendingWork` task is `Nothing` at the start of `FinishOneGroupAsync` only for group A, which started first.</span></span> <span data-ttu-id="eacc6-196">Группа A еще не завершила выражение await, когда она достигает метода `FinishOneGroupAsync`.</span><span class="sxs-lookup"><span data-stu-id="eacc6-196">Group A hasn’t yet completed an await expression when it reaches `FinishOneGroupAsync`.</span></span> <span data-ttu-id="eacc6-197">Таким образом, управление не возвращается `AccessTheWebAsync`, а первое присваивание задаче `pendingWork` не возникает.</span><span class="sxs-lookup"><span data-stu-id="eacc6-197">Therefore, control hasn't returned to `AccessTheWebAsync`, and the first assignment to `pendingWork` hasn't occurred.</span></span>

- <span data-ttu-id="eacc6-198">Следующие две строки всегда отображаются в выходных данных вместе.</span><span class="sxs-lookup"><span data-stu-id="eacc6-198">The following two lines always appear together in the output.</span></span> <span data-ttu-id="eacc6-199">Код не прерывается нигде между запуском операции группы в обработчике `StartButton_Click` и назначением задачи для группы в `pendingWork`.</span><span class="sxs-lookup"><span data-stu-id="eacc6-199">The code is never interrupted between starting a group's operation in `StartButton_Click` and assigning a task for the group to `pendingWork`.</span></span>

  ```console
  #Starting group B.
  #Task assigned for group B. Download tasks are active.
  ```

  <span data-ttu-id="eacc6-200">После входа группы в обработчик `StartButton_Click` операция не завершает выражение await до входа операции в метод `FinishOneGroupAsync`.</span><span class="sxs-lookup"><span data-stu-id="eacc6-200">After a group enters `StartButton_Click`, the operation doesn't complete an await expression until the operation enters `FinishOneGroupAsync`.</span></span> <span data-ttu-id="eacc6-201">Таким образом, другие операции не могут получить контроль во время выполнения этого фрагмента кода.</span><span class="sxs-lookup"><span data-stu-id="eacc6-201">Therefore, no other operation can gain control during that segment of code.</span></span>

## <a name="BKMD_SettingUpTheExample"></a> <span data-ttu-id="eacc6-202">Проверка и выполнение примера приложения</span><span class="sxs-lookup"><span data-stu-id="eacc6-202">Reviewing and Running the Example App</span></span>

<span data-ttu-id="eacc6-203">Чтобы лучше понять пример приложения, его можно загрузить, построить самостоятельно или просмотреть код в конце этого раздела, не реализуя приложение.</span><span class="sxs-lookup"><span data-stu-id="eacc6-203">To better understand the example app, you can download it, build it yourself, or review the code at the end of this topic without implementing the app.</span></span>

> [!NOTE]
> <span data-ttu-id="eacc6-204">Для выполнения этого примера как традиционного приложения Windows Presentation Foundation на компьютере должны быть установлены Visual Studio 2012 или более поздней версии и .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="eacc6-204">To run the example as a Windows Presentation Foundation (WPF) desktop app, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

### <a name="BKMK_DownloadingTheApp"></a> <span data-ttu-id="eacc6-205">Загрузка приложения</span><span class="sxs-lookup"><span data-stu-id="eacc6-205">Downloading the App</span></span>

1. <span data-ttu-id="eacc6-206">Скачайте сжатый файл в разделе [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span><span class="sxs-lookup"><span data-stu-id="eacc6-206">Download the compressed file from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span>

2. <span data-ttu-id="eacc6-207">Распакуйте загруженный файл, а затем запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="eacc6-207">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

3. <span data-ttu-id="eacc6-208">В строке меню выберите **Файл**, **Открыть**, **Проект/Решение**.</span><span class="sxs-lookup"><span data-stu-id="eacc6-208">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

4. <span data-ttu-id="eacc6-209">Перейдите к папке, содержащей распакованный пример кода, а затем откройте файл решения (SLN-файл).</span><span class="sxs-lookup"><span data-stu-id="eacc6-209">Navigate to the folder that holds the decompressed sample code, and then open the solution (.sln) file.</span></span>

5. <span data-ttu-id="eacc6-210">В **обозревателе решений** откройте контекстное меню нужного проекта и выберите пункт **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="eacc6-210">In **Solution Explorer**, open the shortcut menu for the project that you want to run, and then choose **Set as StartUpProject**.</span></span>

6. <span data-ttu-id="eacc6-211">Нажмите сочетание клавиш CTRL+F5, чтобы выполнить сборку и запуск проекта.</span><span class="sxs-lookup"><span data-stu-id="eacc6-211">Choose the CTRL+F5 keys to build and run the project.</span></span>

### <a name="BKMK_BuildingTheApp"></a> <span data-ttu-id="eacc6-212">Сборка приложения</span><span class="sxs-lookup"><span data-stu-id="eacc6-212">Building the App</span></span>

<span data-ttu-id="eacc6-213">В следующих разделах приведен код для построения примера как приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="eacc6-213">The following section provides the code to build the example as a WPF app.</span></span>

##### <a name="to-build-a-wpf-app"></a><span data-ttu-id="eacc6-214">Построение приложения WPF</span><span class="sxs-lookup"><span data-stu-id="eacc6-214">To build a WPF app</span></span>

1. <span data-ttu-id="eacc6-215">Запустите среду Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="eacc6-215">Start Visual Studio.</span></span>

2. <span data-ttu-id="eacc6-216">В главном меню выберите **Файл**, **Создать**, **Проект**.</span><span class="sxs-lookup"><span data-stu-id="eacc6-216">On the menu bar, choose **File**, **New**, **Project**.</span></span>

     <span data-ttu-id="eacc6-217">Откроется диалоговое окно **Создание проекта** .</span><span class="sxs-lookup"><span data-stu-id="eacc6-217">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="eacc6-218">В области **Установленные шаблоны** разверните узел **Visual Basic**, а затем узел **Windows**.</span><span class="sxs-lookup"><span data-stu-id="eacc6-218">In the **Installed Templates** pane, expand **Visual Basic**, and then expand **Windows**.</span></span>

4. <span data-ttu-id="eacc6-219">В списке типов проектов выберите **Приложение WPF**.</span><span class="sxs-lookup"><span data-stu-id="eacc6-219">In the list of project types, choose **WPF Application**.</span></span>

5. <span data-ttu-id="eacc6-220">Присвойте проекту имя `WebsiteDownloadWPF`, выберите .NET Framework версии 4.6 или более поздней, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eacc6-220">Name the project `WebsiteDownloadWPF`, choose .NET Framework version of 4.6 or higher and then click the **OK** button.</span></span>

     <span data-ttu-id="eacc6-221">В **обозревателе решений** появится новый проект.</span><span class="sxs-lookup"><span data-stu-id="eacc6-221">The new project appears in **Solution Explorer**.</span></span>

6. <span data-ttu-id="eacc6-222">В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="eacc6-222">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

     <span data-ttu-id="eacc6-223">Если вкладка не отображается, откройте контекстное меню для MainWindow.xaml в **обозревателе решений** и выберите пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="eacc6-223">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>

7. <span data-ttu-id="eacc6-224">Замените код в представлении **XAML** файла MainWindow.xaml на следующий.</span><span class="sxs-lookup"><span data-stu-id="eacc6-224">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>

    ```xaml
    <Window x:Class="MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:WebsiteDownloadWPF"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        mc:Ignorable="d">

        <Grid Width="517" Height="360">
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="-1,0,0,0" VerticalAlignment="Top" Click="StartButton_Click" Height="53" Background="#FFA89B9B" FontSize="36" Width="518"  />
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" Margin="-1,53,0,-36" TextWrapping="Wrap" VerticalAlignment="Top" Height="343" FontSize="10" ScrollViewer.VerticalScrollBarVisibility="Visible" Width="518" FontFamily="Lucida Console" />
        </Grid>
    </Window>
    ```

     <span data-ttu-id="eacc6-225">В представлении **Конструктор** файла MainWindow.xaml появится простое окно, содержащее кнопку и текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="eacc6-225">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>

8. <span data-ttu-id="eacc6-226">В **обозревателе решений** щелкните правой кнопкой мыши **Ссылки** и выберите **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="eacc6-226">In **Solution Explorer**, right-click on **References** and select **Add Reference**.</span></span>

     <span data-ttu-id="eacc6-227">Добавьте ссылку на <xref:System.Net.Http>, если она еще не выбрана.</span><span class="sxs-lookup"><span data-stu-id="eacc6-227">Add a reference for <xref:System.Net.Http>, if it is not selected already.</span></span>

9. <span data-ttu-id="eacc6-228">В **Обозреватель решений**откройте контекстное меню файла MainWindow. XAML. vb и выберите пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="eacc6-228">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>

10. <span data-ttu-id="eacc6-229">В файле MainWindow. XAML. vb замените код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="eacc6-229">In MainWindow.xaml.vb , replace the code with the following code.</span></span>

    ```vb
    ' Add the following Imports statements, and add a reference for System.Net.Http.
    Imports System.Net.Http
    Imports System.Threading

    Class MainWindow

        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
            System.Net.ServicePointManager.SecurityProtocol = System.Net.ServicePointManager.SecurityProtocol Or System.Net.SecurityProtocolType.Tls12

            ' This line is commented out to make the results clearer in the output.
            'ResultsTextBox.Text = ""

            Try
                Await AccessTheWebAsync()

            Catch ex As Exception
                ResultsTextBox.Text &= vbCrLf & "Downloads failed."

            End Try
        End Sub

        Private Async Function AccessTheWebAsync() As Task

            ' Declare an HttpClient object.
            Dim client = New HttpClient()

            ' Make a list of web addresses.
            Dim urlList As List(Of String) = SetUpURLList()

            Dim total = 0
            Dim position = 0

            For Each url In urlList
                ' GetByteArrayAsync returns a task. At completion, the task
                ' produces a byte array.
                Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

                position += 1
                DisplayResults(url, urlContents, position)

                ' Update the total.
                total += urlContents.Length
            Next

            ' Display the total count for all of the websites.
            ResultsTextBox.Text &=
                String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
        End Function

        Private Function SetUpURLList() As List(Of String)
            Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/hh191443.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/jj155761.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/hh524395.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
            Return urls
        End Function

        Private Sub DisplayResults(url As String, content As Byte(), pos As Integer)
            ' Display the length of each website. The string format is designed
            ' to be used with a monospaced font, such as Lucida Console or
            ' Global Monospace.

            ' Strip off the "http:'".
            Dim displayURL = url.Replace("https://", "")
            ' Display position in the URL list, the URL, and the number of bytes.
            ResultsTextBox.Text &= String.Format(vbCrLf & "{0}. {1,-58} {2,8}", pos, displayURL, content.Length)
        End Sub
    End Class
    ```

11. <span data-ttu-id="eacc6-230">Нажмите сочетание клавиш CTRL+F5, чтобы запустить программу, а затем несколько раз нажмите кнопку **Start**.</span><span class="sxs-lookup"><span data-stu-id="eacc6-230">Choose the CTRL+F5 keys to run the program, and then choose the **Start** button several times.</span></span>

12. <span data-ttu-id="eacc6-231">Внесите изменения, описанные в разделах [Отключение кнопки запуска](#BKMK_DisableTheStartButton), [Отмена и перезапуск операции](#BKMK_CancelAndRestart) или [Запуск нескольких операций и постановка выходных данных в очередь](#BKMK_RunMultipleOperations) для обработки повторного входа.</span><span class="sxs-lookup"><span data-stu-id="eacc6-231">Make the changes from [Disable the Start Button](#BKMK_DisableTheStartButton), [Cancel and Restart the Operation](#BKMK_CancelAndRestart), or [Run Multiple Operations and Queue the Output](#BKMK_RunMultipleOperations) to handle the reentrancy.</span></span>

## <a name="see-also"></a><span data-ttu-id="eacc6-232">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="eacc6-232">See also</span></span>

- <span data-ttu-id="eacc6-233">[Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) (Пошаговое руководство. Доступ к веб-сайтам с помощью модификатора Async и оператора Await (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="eacc6-233">[Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)</span></span>
- [<span data-ttu-id="eacc6-234">Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eacc6-234">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)
