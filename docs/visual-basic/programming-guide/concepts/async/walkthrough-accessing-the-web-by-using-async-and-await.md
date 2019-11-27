---
title: Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await
ms.date: 07/20/2015
ms.assetid: 84fd047f-fab8-4d89-8ced-104fb7310a91
ms.openlocfilehash: c13e592eb155d14c2e7cb2388a96925a7f1fa413
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349095"
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a><span data-ttu-id="ac372-102">Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac372-102">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>

<span data-ttu-id="ac372-103">Возможности Async и Await упрощают создание асинхронных программ.</span><span class="sxs-lookup"><span data-stu-id="ac372-103">You can write asynchronous programs more easily and intuitively by using async/await features.</span></span> <span data-ttu-id="ac372-104">Можно написать асинхронный код, который выглядит как синхронный, и позволить компилятору обрабатывать трудные функции обратного вызова и продолжения, которые обычно включает асинхронный код.</span><span class="sxs-lookup"><span data-stu-id="ac372-104">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>

<span data-ttu-id="ac372-105">Дополнительные сведения о функции Async см. в разделе [Асинхронное программирование с использованием Async и await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="ac372-105">For more information about the Async feature, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

<span data-ttu-id="ac372-106">Это пошаговое руководство начинается с создания синхронного приложения Windows Presentation Foundation (WPF), которое суммирует число байтов в списке веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="ac372-106">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="ac372-107">Затем в рамках руководства приложение преобразуется в асинхронное решение с помощью новых возможностей.</span><span class="sxs-lookup"><span data-stu-id="ac372-107">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>

<span data-ttu-id="ac372-108">Если вы не хотите создавать приложение самостоятельно, вы можете скачать пример "Пример Async. Пошаговое руководство по доступу к интернету (C# и Visual Basic)" со страницы [примеров кода для разработчиков](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span><span class="sxs-lookup"><span data-stu-id="ac372-108">If you don't want to build the applications yourself, you can download "Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)" from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>

<span data-ttu-id="ac372-109">В этом пошаговом руководстве выполняются следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="ac372-109">In this walkthrough, you complete the following tasks:</span></span>

> [!div class="checklist"]
>
> - [<span data-ttu-id="ac372-110">Создание приложения WPF</span><span class="sxs-lookup"><span data-stu-id="ac372-110">Create a WPF application</span></span>](#create-a-wpf-application)
> - [<span data-ttu-id="ac372-111">Проектирование простого WPF MainWindow</span><span class="sxs-lookup"><span data-stu-id="ac372-111">Design a simple WPF MainWindow</span></span>](#design-a-simple-wpf-mainwindow)
> - [<span data-ttu-id="ac372-112">Добавление ссылки</span><span class="sxs-lookup"><span data-stu-id="ac372-112">Add a reference</span></span>](#add-a-reference)
> - [<span data-ttu-id="ac372-113">Добавление необходимых операторов Imports</span><span class="sxs-lookup"><span data-stu-id="ac372-113">Add necessary Imports statements</span></span>](#add-necessary-imports-statements)
> - [<span data-ttu-id="ac372-114">Создание синхронного приложения</span><span class="sxs-lookup"><span data-stu-id="ac372-114">Create a synchronous application</span></span>](#create-a-synchronous-application)
> - [<span data-ttu-id="ac372-115">Тестирование синхронного решения</span><span class="sxs-lookup"><span data-stu-id="ac372-115">Test the synchronous solution</span></span>](#test-the-synchronous-solution)
> - [<span data-ttu-id="ac372-116">Преобразование GetURLContents в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="ac372-116">Convert GetURLContents to an asynchronous method</span></span>](#convert-geturlcontents-to-an-asynchronous-method)
> - [<span data-ttu-id="ac372-117">Преобразование SumPageSizes в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="ac372-117">Convert SumPageSizes to an asynchronous method</span></span>](#convert-sumpagesizes-to-an-asynchronous-method)
> - [<span data-ttu-id="ac372-118">Преобразование startButton_Click в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="ac372-118">Convert startButton_Click to an asynchronous method</span></span>](#convert-startbutton_click-to-an-asynchronous-method)
> - [<span data-ttu-id="ac372-119">Тестирование асинхронного решения</span><span class="sxs-lookup"><span data-stu-id="ac372-119">Test the asynchronous solution</span></span>](#test-the-asynchronous-solution)
> - [<span data-ttu-id="ac372-120">Замените метод GetURLContentsAsync методом .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ac372-120">Replace the GetURLContentsAsync method with a .NET Framework method</span></span>](#replace-the-geturlcontentsasync-method-with-a-net-framework-method)

<span data-ttu-id="ac372-121">Полный пример асинхронной работы см. в разделе " [Пример](#example) ".</span><span class="sxs-lookup"><span data-stu-id="ac372-121">See the [Example](#example) section for the complete asynchronous example.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ac372-122">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="ac372-122">Prerequisites</span></span>

<span data-ttu-id="ac372-123">На компьютере должна быть установлена среда Visual Studio 2012 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="ac372-123">Visual Studio 2012 or later must be installed on your computer.</span></span> <span data-ttu-id="ac372-124">Дополнительные сведения см. на странице [загрузки](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ac372-124">For more information, see the Visual Studio [Downloads](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) page.</span></span>

## <a name="create-a-wpf-application"></a><span data-ttu-id="ac372-125">Создание приложения WPF</span><span class="sxs-lookup"><span data-stu-id="ac372-125">Create a WPF application</span></span>

1. <span data-ttu-id="ac372-126">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ac372-126">Start Visual Studio.</span></span>

2. <span data-ttu-id="ac372-127">В строке меню выберите **Файл**, **Создать**, **Проект**.</span><span class="sxs-lookup"><span data-stu-id="ac372-127">On the menu bar, choose **File**, **New**, **Project**.</span></span>

    <span data-ttu-id="ac372-128">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="ac372-128">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="ac372-129">В области **Установленные шаблоны** выберите Visual Basic, а затем выберите **приложение WPF** в списке типов проектов.</span><span class="sxs-lookup"><span data-stu-id="ac372-129">In the **Installed Templates** pane, choose Visual Basic, and then choose **WPF Application** from the list of project types.</span></span>

4. <span data-ttu-id="ac372-130">В текстовом поле **Имя** введите `AsyncExampleWPF` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ac372-130">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>

    <span data-ttu-id="ac372-131">В **обозревателе решений** появится новый проект.</span><span class="sxs-lookup"><span data-stu-id="ac372-131">The new project appears in **Solution Explorer**.</span></span>

## <a name="design-a-simple-wpf-mainwindow"></a><span data-ttu-id="ac372-132">Разработка простого окна MainWindow WPF</span><span class="sxs-lookup"><span data-stu-id="ac372-132">Design a simple WPF MainWindow</span></span>

1. <span data-ttu-id="ac372-133">В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="ac372-133">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

2. <span data-ttu-id="ac372-134">Если окно **Панель элементов** не отображается, в меню **Вид** выберите пункт **Панель элементов**.</span><span class="sxs-lookup"><span data-stu-id="ac372-134">If the **Toolbox** window isn’t visible, open the **View** menu, and then choose **Toolbox**.</span></span>

3. <span data-ttu-id="ac372-135">Добавьте элементы управления **Button** и **TextBox** в окно **MainWindow**.</span><span class="sxs-lookup"><span data-stu-id="ac372-135">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>

4. <span data-ttu-id="ac372-136">Выделите элемент управления **TextBox** и в окне **Свойства** задайте указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="ac372-136">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="ac372-137">Задайте для свойства **Имя** значение `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="ac372-137">Set the **Name** property to `resultsTextBox`.</span></span>

    - <span data-ttu-id="ac372-138">Задайте для свойства **Высота** значение 250.</span><span class="sxs-lookup"><span data-stu-id="ac372-138">Set the **Height** property to 250.</span></span>

    - <span data-ttu-id="ac372-139">Задайте для свойства **Ширина** значение 500.</span><span class="sxs-lookup"><span data-stu-id="ac372-139">Set the **Width** property to 500.</span></span>

    - <span data-ttu-id="ac372-140">На вкладке **Текст** укажите моноширинный шрифт, например Lucida Console или Global Monospace.</span><span class="sxs-lookup"><span data-stu-id="ac372-140">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>

5. <span data-ttu-id="ac372-141">Выделите элемент управления **Button** и в окне **Свойства** задайте указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="ac372-141">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="ac372-142">Задайте для свойства **Имя** значение `startButton`.</span><span class="sxs-lookup"><span data-stu-id="ac372-142">Set the **Name** property to `startButton`.</span></span>

    - <span data-ttu-id="ac372-143">Измените значение свойства **Содержимое** с **Button** на **Start**.</span><span class="sxs-lookup"><span data-stu-id="ac372-143">Change the value of the **Content** property from **Button** to **Start**.</span></span>

6. <span data-ttu-id="ac372-144">Поместите текстовое поле и кнопку так, чтобы оба элемента управления отображались в окне **MainWindow**.</span><span class="sxs-lookup"><span data-stu-id="ac372-144">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>

    <span data-ttu-id="ac372-145">Дополнительные сведения о конструкторе XAML WPF см. в разделе [Создание пользовательского интерфейса с помощью конструктора XAML](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="ac372-145">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>

## <a name="add-a-reference"></a><span data-ttu-id="ac372-146">Добавление ссылки</span><span class="sxs-lookup"><span data-stu-id="ac372-146">Add a reference</span></span>

1. <span data-ttu-id="ac372-147">В **обозревателе решений** выделите имя проекта.</span><span class="sxs-lookup"><span data-stu-id="ac372-147">In **Solution Explorer**, highlight your project's name.</span></span>

2. <span data-ttu-id="ac372-148">В строке меню выберите **Проект**, **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="ac372-148">On the menu bar, choose **Project**, **Add Reference**.</span></span>

    <span data-ttu-id="ac372-149">Откроется диалоговое окно **Диспетчер ссылок**.</span><span class="sxs-lookup"><span data-stu-id="ac372-149">The **Reference Manager** dialog box appears.</span></span>

3. <span data-ttu-id="ac372-150">Вверху диалогового окна убедитесь в том, что проект предназначен для платформы .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="ac372-150">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>

4. <span data-ttu-id="ac372-151">В области **Сборки** выберите **Платформа**, если этот вариант еще не выбран.</span><span class="sxs-lookup"><span data-stu-id="ac372-151">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>

5. <span data-ttu-id="ac372-152">В списке имен установите флажок **System.Net.Http**.</span><span class="sxs-lookup"><span data-stu-id="ac372-152">In the list of names, select the **System.Net.Http** check box.</span></span>

6. <span data-ttu-id="ac372-153">Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="ac372-153">Choose the **OK** button to close the dialog box.</span></span>

## <a name="add-necessary-imports-statements"></a><span data-ttu-id="ac372-154">Добавление необходимых операторов Imports</span><span class="sxs-lookup"><span data-stu-id="ac372-154">Add necessary Imports statements</span></span>

1. <span data-ttu-id="ac372-155">В **Обозреватель решений**откройте контекстное меню файла MainWindow. XAML. vb и выберите пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="ac372-155">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>

2. <span data-ttu-id="ac372-156">Добавьте следующие инструкции `Imports` в начало файла кода, если они еще не установлены.</span><span class="sxs-lookup"><span data-stu-id="ac372-156">Add the following `Imports` statements at the top of the code file if they’re not already present.</span></span>

    ```vb
    Imports System.Net.Http
    Imports System.Net
    Imports System.IO
    ```

## <a name="create-a-synchronous-application"></a><span data-ttu-id="ac372-157">Создание синхронного приложения</span><span class="sxs-lookup"><span data-stu-id="ac372-157">Create a synchronous application</span></span>

1. <span data-ttu-id="ac372-158">В окне конструктора MainWindow. XAML дважды щелкните кнопку **Start** , чтобы создать обработчик событий `startButton_Click` в файле MainWindow. XAML. vb.</span><span class="sxs-lookup"><span data-stu-id="ac372-158">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>

2. <span data-ttu-id="ac372-159">В файле MainWindow. XAML. vb скопируйте следующий код в текст `startButton_Click`:</span><span class="sxs-lookup"><span data-stu-id="ac372-159">In MainWindow.xaml.vb, copy the following code into the body of `startButton_Click`:</span></span>

    ```vb
    resultsTextBox.Clear()
    SumPageSizes()
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."
    ```

    <span data-ttu-id="ac372-160">Код вызывает метод, который управляет приложением `SumPageSizes` и выводит на экран сообщение, когда элемент управления возвращается к `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="ac372-160">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>

3. <span data-ttu-id="ac372-161">Код для синхронного решения содержит следующие четыре метода:</span><span class="sxs-lookup"><span data-stu-id="ac372-161">The code for the synchronous solution contains the following four methods:</span></span>

    - <span data-ttu-id="ac372-162">`SumPageSizes`, который получает список URL-адресов веб-страниц из `SetUpURLList`, а затем вызывает метод `GetURLContents` и `DisplayResults` для обработки каждого URL-адреса;</span><span class="sxs-lookup"><span data-stu-id="ac372-162">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>

    - <span data-ttu-id="ac372-163">`SetUpURLList`, который создает и возвращает список веб-адресов;</span><span class="sxs-lookup"><span data-stu-id="ac372-163">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>

    - <span data-ttu-id="ac372-164">`GetURLContents`, который загружает содержимое каждого веб-сайта и возвращает содержимое в виде массива байтов;</span><span class="sxs-lookup"><span data-stu-id="ac372-164">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>

    - <span data-ttu-id="ac372-165">`DisplayResults`, который показывает число байтов в массиве байтов для каждого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="ac372-165">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>

    <span data-ttu-id="ac372-166">Скопируйте следующие четыре метода и вставьте их в обработчик событий `startButton_Click` в файле MainWindow. XAML. vb:</span><span class="sxs-lookup"><span data-stu-id="ac372-166">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.vb:</span></span>

    ```vb
    Private Sub SumPageSizes()

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            ' GetURLContents returns the contents of url as a byte array.
            Dim urlContents As Byte() = GetURLContents(url)

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the web addresses.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "Total bytes returned:  {0}" & vbCrLf, total)
    End Sub

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
    End Function

    Private Function GetURLContents(url As String) As Byte()

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        ' Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.
        Using response As WebResponse = webReq.GetResponse()
            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                responseStream.CopyTo(content)
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
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub
    ```

## <a name="test-the-synchronous-solution"></a><span data-ttu-id="ac372-167">Тестирование синхронного решения</span><span class="sxs-lookup"><span data-stu-id="ac372-167">Test the synchronous solution</span></span>

1. <span data-ttu-id="ac372-168">Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .</span><span class="sxs-lookup"><span data-stu-id="ac372-168">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

    <span data-ttu-id="ac372-169">Программа должна выдать результаты, похожие на следующий список:</span><span class="sxs-lookup"><span data-stu-id="ac372-169">Output that resembles the following list should appear:</span></span>

    ```console
    msdn.microsoft.com/library/windows/apps/br211380.aspx        383832
    msdn.microsoft.com                                            33964
    msdn.microsoft.com/library/hh290136.aspx               225793
    msdn.microsoft.com/library/ee256749.aspx               143577
    msdn.microsoft.com/library/hh290138.aspx               237372
    msdn.microsoft.com/library/hh290140.aspx               128279
    msdn.microsoft.com/library/dd470362.aspx               157649
    msdn.microsoft.com/library/aa578028.aspx               204457
    msdn.microsoft.com/library/ms404677.aspx               176405
    msdn.microsoft.com/library/ff730837.aspx               143474

    Total bytes returned:  1834802

    Control returned to startButton_Click.
    ```

    <span data-ttu-id="ac372-170">Обратите внимание, что вывод результатов на экран занимает несколько секунд.</span><span class="sxs-lookup"><span data-stu-id="ac372-170">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="ac372-171">В течение этого времени поток пользовательского интерфейса заблокирован, пока он ожидает загрузку запрошенных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ac372-171">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="ac372-172">Соответственно, после нажатия кнопки **Start** окно нельзя перемещать, разворачивать, сворачивать или даже закрывать.</span><span class="sxs-lookup"><span data-stu-id="ac372-172">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="ac372-173">Эти действия будут завершаться сбоем, пока не появятся результаты подсчета.</span><span class="sxs-lookup"><span data-stu-id="ac372-173">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="ac372-174">Если веб-сайт не отвечает, вы не можете определить, на каком сайте произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="ac372-174">If a website isn’t responding, you have no indication of which site failed.</span></span> <span data-ttu-id="ac372-175">Трудно даже остановить ожидание и закрыть программу.</span><span class="sxs-lookup"><span data-stu-id="ac372-175">It is difficult even to stop waiting and close the program.</span></span>

## <a name="convert-geturlcontents-to-an-asynchronous-method"></a><span data-ttu-id="ac372-176">Преобразование GetURLContents в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="ac372-176">Convert GetURLContents to an asynchronous method</span></span>

1. <span data-ttu-id="ac372-177">Для преобразования синхронного решения в асинхронное решение лучше начать с `GetURLContents` так как вызовы метода <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> и метода <xref:System.IO.Stream.CopyTo%2A?displayProperty=nameWithType> — это место, где приложение обращается к веб-приложению.</span><span class="sxs-lookup"><span data-stu-id="ac372-177">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> method and to the <xref:System.IO.Stream.CopyTo%2A?displayProperty=nameWithType> method are where the application accesses the web.</span></span> <span data-ttu-id="ac372-178">Платформа .NET Framework упрощает преобразование путем предоставления асинхронных версий этих методов.</span><span class="sxs-lookup"><span data-stu-id="ac372-178">The .NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>

    <span data-ttu-id="ac372-179">Дополнительные сведения о методах, которые используются в `GetURLContents`, см. в разделе <xref:System.Net.WebRequest>.</span><span class="sxs-lookup"><span data-stu-id="ac372-179">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac372-180">По мере выполнения шагов в этом пошаговом руководстве возникают различные ошибки компилятора.</span><span class="sxs-lookup"><span data-stu-id="ac372-180">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="ac372-181">Их можно игнорировать и продолжить процедуры пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="ac372-181">You can ignore them and continue with the walkthrough.</span></span>

    <span data-ttu-id="ac372-182">Измените метод, который вызывается в третьей строке `GetURLContents` из `GetResponse`, асинхронным методом <xref:System.Net.WebRequest.GetResponseAsync%2A>, основанным на задачах.</span><span class="sxs-lookup"><span data-stu-id="ac372-182">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>

    ```vb
    Using response As WebResponse = webReq.GetResponseAsync()
    ```

2. <span data-ttu-id="ac372-183">`GetResponseAsync` возвращает значение типа <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="ac372-183">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="ac372-184">В этом случае *переменная, возвращаемая задачей*, `TResult`, имеет тип <xref:System.Net.WebResponse>.</span><span class="sxs-lookup"><span data-stu-id="ac372-184">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="ac372-185">Задача является обещанием создать фактический объект `WebResponse` после загрузки запрошенных данных и выполнения задачи до завершения.</span><span class="sxs-lookup"><span data-stu-id="ac372-185">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>

    <span data-ttu-id="ac372-186">Чтобы получить значение `WebResponse` из задачи, примените оператор [await](../../../../visual-basic/language-reference/operators/await-operator.md) к вызову `GetResponseAsync`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="ac372-186">To retrieve the `WebResponse` value from the task, apply an [Await](../../../../visual-basic/language-reference/operators/await-operator.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>

    ```vb
    Using response As WebResponse = Await webReq.GetResponseAsync()
    ```

    <span data-ttu-id="ac372-187">Оператор `Await` приостанавливает выполнение текущего метода `GetURLContents`, пока не будет завершена ожидаемая задача.</span><span class="sxs-lookup"><span data-stu-id="ac372-187">The `Await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="ac372-188">На это время управление возвращается вызывающему объекту текущего метода.</span><span class="sxs-lookup"><span data-stu-id="ac372-188">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="ac372-189">В этом примере текущим методом является `GetURLContents`, а вызывающим объектом — `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="ac372-189">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="ac372-190">После завершения задачи создается обещанный объект `WebResponse` в качестве значения ожидаемой задачи, который присваивается переменной `response`.</span><span class="sxs-lookup"><span data-stu-id="ac372-190">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>

    <span data-ttu-id="ac372-191">Предыдущий оператор можно разделить на следующие два оператора для уточнения выполняемых операций.</span><span class="sxs-lookup"><span data-stu-id="ac372-191">The previous statement can be separated into the following two statements to clarify what happens.</span></span>

    ```vb
    Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()
    Using response As WebResponse = Await responseTask
    ```

    <span data-ttu-id="ac372-192">Вызов `webReq.GetResponseAsync` возвращает `Task(Of WebResponse)` или `Task<WebResponse>`.</span><span class="sxs-lookup"><span data-stu-id="ac372-192">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="ac372-193">Затем к задаче применяется оператор `Await` для получения значения `WebResponse`.</span><span class="sxs-lookup"><span data-stu-id="ac372-193">Then an `Await` operator is applied to the task to retrieve the `WebResponse` value.</span></span>

    <span data-ttu-id="ac372-194">Если асинхронный метод выполняет какие-то действия, это не зависит от выполнения задачи, метод может продолжать свои действия между выполнениями этих двух операторов: после вызова асинхронного метода и перед применением оператора await.</span><span class="sxs-lookup"><span data-stu-id="ac372-194">If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the await operator is applied.</span></span> <span data-ttu-id="ac372-195">Примеры см. [в разделе Практическое руководство. Параллельное выполнение нескольких веб-запросов с помощью инструкций Async и await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) и [Практическое руководство. расширение асинхронного пошагового руководства с помощью Task. WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="ac372-195">For examples, see [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>

3. <span data-ttu-id="ac372-196">Из-за добавления оператора `Await` в предыдущем шаге возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="ac372-196">Because you added the `Await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="ac372-197">Оператор можно использовать только в методах, помеченных модификатором [Async](../../../../visual-basic/language-reference/modifiers/async.md) .</span><span class="sxs-lookup"><span data-stu-id="ac372-197">The operator can be used only in methods that are marked with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="ac372-198">Пропустите ошибку, повторяя действия по замене вызова `CopyTo` вызовом метода `CopyToAsync`.</span><span class="sxs-lookup"><span data-stu-id="ac372-198">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>

    - <span data-ttu-id="ac372-199">Измените имя метода, вызывающего <xref:System.IO.Stream.CopyToAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="ac372-199">Change the name of the method that’s called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>

    - <span data-ttu-id="ac372-200">Метод `CopyTo` или `CopyToAsync` копирует байты в свой аргумент `content` и не возвращает осмысленное значение.</span><span class="sxs-lookup"><span data-stu-id="ac372-200">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn’t return a meaningful value.</span></span> <span data-ttu-id="ac372-201">В синхронной версии вызов метода `CopyTo` — это просто оператор, который не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="ac372-201">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="ac372-202">Асинхронная версия — `CopyToAsync` — возвращает <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="ac372-202">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="ac372-203">Задача работает как Task(void) и позволяет ожидать метод.</span><span class="sxs-lookup"><span data-stu-id="ac372-203">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="ac372-204">Примените `Await` или `await` к вызову `CopyToAsync`, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="ac372-204">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>

        ```vb
        Await responseStream.CopyToAsync(content)
        ```

         <span data-ttu-id="ac372-205">Предыдущий оператор сокращает две следующие строки кода.</span><span class="sxs-lookup"><span data-stu-id="ac372-205">The previous statement abbreviates the following two lines of code.</span></span>

        ```vb
        ' CopyToAsync returns a Task, not a Task<T>.
        Dim copyTask As Task = responseStream.CopyToAsync(content)

        ' When copyTask is completed, content contains a copy of
        ' responseStream.
        Await copyTask
        ```

4. <span data-ttu-id="ac372-206">Все, что остается сделать в `GetURLContents`, — это изменить подпись метода.</span><span class="sxs-lookup"><span data-stu-id="ac372-206">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="ac372-207">Оператор `Await` можно использовать только в методах, помеченных модификатором [Async](../../../../visual-basic/language-reference/modifiers/async.md) .</span><span class="sxs-lookup"><span data-stu-id="ac372-207">You can use the `Await` operator only in methods that are marked with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="ac372-208">Добавьте модификатор, чтобы пометить метод как *асинхронный*, как показано в приведенном ниже примере кода.</span><span class="sxs-lookup"><span data-stu-id="ac372-208">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>

    ```vb
    Private Async Function GetURLContents(url As String) As Byte()
    ```

5. <span data-ttu-id="ac372-209">Тип возвращаемого значения асинхронного метода может быть только <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="ac372-209">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="ac372-210">В Visual Basic метод должен являться функцией `Function`, возвращающей `Task` или `Task(Of T)`, либо он должен быть `Sub`.</span><span class="sxs-lookup"><span data-stu-id="ac372-210">In Visual Basic, the method must be a `Function` that returns a `Task` or a `Task(Of T)`, or the method must be a `Sub`.</span></span> <span data-ttu-id="ac372-211">Как правило, метод `Sub` используется только в асинхронном обработчике событий, где требуется `Sub`.</span><span class="sxs-lookup"><span data-stu-id="ac372-211">Typically, a `Sub` method  is used only in an async event handler, where `Sub` is required.</span></span> <span data-ttu-id="ac372-212">В других случаях используется `Task(T)`, если метод Completed имеет оператор [return](../../../../visual-basic/language-reference/statements/return-statement.md) , возвращающий значение типа t, и используется `Task`, если завершенный метод не возвращает осмысленное значение.</span><span class="sxs-lookup"><span data-stu-id="ac372-212">In other cases, you use `Task(T)` if the completed method has a [Return](../../../../visual-basic/language-reference/statements/return-statement.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.</span></span>

    <span data-ttu-id="ac372-213">Дополнительные сведения см. в разделе [асинхронные типы возвращаемых данных (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="ac372-213">For more information, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>

    <span data-ttu-id="ac372-214">Метод `GetURLContents` имеет оператор return, который возвращает массив байтов.</span><span class="sxs-lookup"><span data-stu-id="ac372-214">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="ac372-215">Таким образом, тип возвращаемого значения асинхронной версии — Task(T), где T — массив байтов.</span><span class="sxs-lookup"><span data-stu-id="ac372-215">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="ac372-216">Внесите следующие изменения в подпись метода.</span><span class="sxs-lookup"><span data-stu-id="ac372-216">Make the following changes in the method signature:</span></span>

    - <span data-ttu-id="ac372-217">Измените тип возвращаемого значения на `Task(Of Byte())`.</span><span class="sxs-lookup"><span data-stu-id="ac372-217">Change the return type to `Task(Of Byte())`.</span></span>

    - <span data-ttu-id="ac372-218">По соглашению об именовании асинхронные методы имеют имена, заканчивающиеся на Async, поэтому переименуйте метод в `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="ac372-218">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>

    <span data-ttu-id="ac372-219">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="ac372-219">The following code shows these changes.</span></span>

    ```vb
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())
    ```

    <span data-ttu-id="ac372-220">После внесения этих изменений преобразование `GetURLContents` в асинхронный метод завершено.</span><span class="sxs-lookup"><span data-stu-id="ac372-220">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>

## <a name="convert-sumpagesizes-to-an-asynchronous-method"></a><span data-ttu-id="ac372-221">Преобразование SumPageSizes в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="ac372-221">Convert SumPageSizes to an asynchronous method</span></span>

1. <span data-ttu-id="ac372-222">Повторите шаги из предыдущей процедуры для `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="ac372-222">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="ac372-223">Во-первых, преобразуйте вызов метода `GetURLContents` в вызов асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="ac372-223">First, change the call to `GetURLContents` to an asynchronous call.</span></span>

    - <span data-ttu-id="ac372-224">Измените имя вызываемого метода с `GetURLContents` на `GetURLContentsAsync`, если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="ac372-224">Change the name of the method that’s called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>

    - <span data-ttu-id="ac372-225">Примените оператор `Await` к задаче, возвращаемой методом `GetURLContentsAsync`, для получения значения байтового массива.</span><span class="sxs-lookup"><span data-stu-id="ac372-225">Apply `Await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>

    <span data-ttu-id="ac372-226">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="ac372-226">The following code shows these changes.</span></span>

    ```vb
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)
    ```

    <span data-ttu-id="ac372-227">Предыдущее назначение сокращает две следующие строки кода.</span><span class="sxs-lookup"><span data-stu-id="ac372-227">The previous assignment abbreviates the following two lines of code.</span></span>

    ```vb
    ' GetURLContentsAsync returns a task. At completion, the task
    ' produces a byte array.
    Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
    Dim urlContents As Byte() = Await getContentsTask
    ```

2. <span data-ttu-id="ac372-228">Внесите следующие изменения в подпись метода.</span><span class="sxs-lookup"><span data-stu-id="ac372-228">Make the following changes in the method's signature:</span></span>

    - <span data-ttu-id="ac372-229">Пометьте метод модификатором `Async`.</span><span class="sxs-lookup"><span data-stu-id="ac372-229">Mark the method with the `Async` modifier.</span></span>

    - <span data-ttu-id="ac372-230">Добавьте в имя метода Async.</span><span class="sxs-lookup"><span data-stu-id="ac372-230">Add "Async" to the method name.</span></span>

    - <span data-ttu-id="ac372-231">В настоящее время нет возвращаемой переменной задачи T, так как `SumPageSizesAsync` не возвращает значение для T. (метод не имеет `Return` инструкции.) Однако метод должен возвращать `Task` для ожидания.</span><span class="sxs-lookup"><span data-stu-id="ac372-231">There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `Return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="ac372-232">Поэтому измените тип метода с `Sub` на `Function`.</span><span class="sxs-lookup"><span data-stu-id="ac372-232">Therefore, change the method type from `Sub` to `Function`.</span></span> <span data-ttu-id="ac372-233">Тип значения, возвращаемого функцией, — `Task`.</span><span class="sxs-lookup"><span data-stu-id="ac372-233">The return type of the function is `Task`.</span></span>

    <span data-ttu-id="ac372-234">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="ac372-234">The following code shows these changes.</span></span>

    ```vb
    Private Async Function SumPageSizesAsync() As Task
    ```

    <span data-ttu-id="ac372-235">Преобразование `SumPageSizes` в `SumPageSizesAsync` завершено.</span><span class="sxs-lookup"><span data-stu-id="ac372-235">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>

## <a name="convert-startbutton_click-to-an-asynchronous-method"></a><span data-ttu-id="ac372-236">Преобразование startButton_Click в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="ac372-236">Convert startButton_Click to an asynchronous method</span></span>

1. <span data-ttu-id="ac372-237">В обработчике событий измените имя вызываемого метода с `SumPageSizes` на `SumPageSizesAsync`, если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="ac372-237">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven’t already done so.</span></span>

2. <span data-ttu-id="ac372-238">Поскольку `SumPageSizesAsync` является асинхронным методом, измените код в обработчике событий для ожидания результата.</span><span class="sxs-lookup"><span data-stu-id="ac372-238">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>

    <span data-ttu-id="ac372-239">Вызов `SumPageSizesAsync` отражает вызов `CopyToAsync` в `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="ac372-239">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="ac372-240">Вызов возвращает `Task`, а не `Task(T)`.</span><span class="sxs-lookup"><span data-stu-id="ac372-240">The call returns a `Task`, not a `Task(T)`.</span></span>

    <span data-ttu-id="ac372-241">Как и в предыдущих процедурах, вызов можно преобразовать, используя один или два оператора.</span><span class="sxs-lookup"><span data-stu-id="ac372-241">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="ac372-242">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="ac372-242">The following code shows these changes.</span></span>

    ```vb
    ' One-step async call.
    Await SumPageSizesAsync()

    ' Two-step async call.
    Dim sumTask As Task = SumPageSizesAsync()
    Await sumTask
    ```

3. <span data-ttu-id="ac372-243">Чтобы предотвратить случайное повторное введение операции, добавьте следующий оператор в верхней части `startButton_Click`, чтобы отключить кнопку **Start**.</span><span class="sxs-lookup"><span data-stu-id="ac372-243">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>

    ```vb
    ' Disable the button until the operation is complete.
    startButton.IsEnabled = False
    ```

    <span data-ttu-id="ac372-244">Можно снова включить кнопку в конце обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="ac372-244">You can reenable the button at the end of the event handler.</span></span>

    ```vb
    ' Reenable the button in case you want to run the operation again.
    startButton.IsEnabled = True
    ```

    <span data-ttu-id="ac372-245">Дополнительные сведения о повторном входе см. в статье обработка повторного [входа в асинхронных приложениях (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span><span class="sxs-lookup"><span data-stu-id="ac372-245">For more information about reentrancy, see [Handling Reentrancy in Async Apps (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span></span>

4. <span data-ttu-id="ac372-246">Наконец, добавьте модификатор `Async` в объявление, чтобы обработчик событий мог ожидать `SumPagSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="ac372-246">Finally, add the `Async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>

    ```vb
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click
    ```

    <span data-ttu-id="ac372-247">Как правило, имена обработчиков событий не изменяются.</span><span class="sxs-lookup"><span data-stu-id="ac372-247">Typically, the names of event handlers aren’t changed.</span></span> <span data-ttu-id="ac372-248">Тип возвращаемого значения не изменен на `Task`, так как обработчики событий должны быть `Sub` процедурах в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ac372-248">The return type isn’t changed to `Task` because event handlers must be `Sub` procedures in Visual Basic.</span></span>

    <span data-ttu-id="ac372-249">Преобразование проекта из синхронного в асинхронный завершено.</span><span class="sxs-lookup"><span data-stu-id="ac372-249">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>

## <a name="test-the-asynchronous-solution"></a><span data-ttu-id="ac372-250">Тестирование асинхронного решения</span><span class="sxs-lookup"><span data-stu-id="ac372-250">Test the asynchronous solution</span></span>

1. <span data-ttu-id="ac372-251">Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .</span><span class="sxs-lookup"><span data-stu-id="ac372-251">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

2. <span data-ttu-id="ac372-252">Появившиеся результаты должны напоминать результаты синхронного решения.</span><span class="sxs-lookup"><span data-stu-id="ac372-252">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="ac372-253">Однако имеются следующие различия.</span><span class="sxs-lookup"><span data-stu-id="ac372-253">However, notice the following differences.</span></span>

    - <span data-ttu-id="ac372-254">Все результаты не отображаются одновременно после завершения обработки.</span><span class="sxs-lookup"><span data-stu-id="ac372-254">The results don’t all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="ac372-255">Например, обе программы содержат строку в `startButton_Click`, которая очищает текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="ac372-255">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="ac372-256">Ее цель состоит в том, чтобы очистить текстовое поле между запусками при нажатии кнопки **Start** во второй раз после появления одного набора результатов.</span><span class="sxs-lookup"><span data-stu-id="ac372-256">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="ac372-257">В синхронной версии текстовое поле очищается перед отображением данных во второй раз, после завершения загрузки и высвобождения потока пользовательского интерфейса для выполнения других операций.</span><span class="sxs-lookup"><span data-stu-id="ac372-257">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="ac372-258">В асинхронной версии текстовое поле очищается сразу же после нажатия кнопки **Start**.</span><span class="sxs-lookup"><span data-stu-id="ac372-258">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>

    - <span data-ttu-id="ac372-259">И что самое главное, поток пользовательского интерфейса не блокируется во время загрузки.</span><span class="sxs-lookup"><span data-stu-id="ac372-259">Most importantly, the UI thread isn’t blocked during the downloads.</span></span> <span data-ttu-id="ac372-260">Можно перемещать окно или изменять его размер во время загрузки, подсчета и отображения веб-ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ac372-260">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="ac372-261">Если один из веб-сайтов работает медленно или не отвечает, можно отменить операцию, нажав кнопку **Закрыть** (красный крестик в правом верхнем углу окна).</span><span class="sxs-lookup"><span data-stu-id="ac372-261">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>

## <a name="replace-the-geturlcontentsasync-method-with-a-net-framework-method"></a><span data-ttu-id="ac372-262">Замените метод GetURLContentsAsync методом .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ac372-262">Replace the GetURLContentsAsync method with a .NET Framework method</span></span>

1. <span data-ttu-id="ac372-263">.NET Framework предоставляет множество асинхронных методов, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="ac372-263">The .NET Framework provides many async methods that you can use.</span></span> <span data-ttu-id="ac372-264">Один из них, метод <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29?displayProperty=nameWithType>, делает то, что необходимо для этого пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="ac372-264">One of them, the <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29?displayProperty=nameWithType> method, does just what you need for this walkthrough.</span></span> <span data-ttu-id="ac372-265">Его можно использовать вместо метода `GetURLContentsAsync`, созданного в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="ac372-265">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>

    <span data-ttu-id="ac372-266">Первым шагом является создание объекта <xref:System.Net.Http.HttpClient> в методе `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="ac372-266">The first step is to create an <xref:System.Net.Http.HttpClient> object in the `SumPageSizesAsync` method.</span></span> <span data-ttu-id="ac372-267">Добавьте следующее объявление в начале метода.</span><span class="sxs-lookup"><span data-stu-id="ac372-267">Add the following declaration at the start of the method.</span></span>

    ```vb
    ' Declare an HttpClient object and increase the buffer size. The
    ' default buffer size is 65,536.
    Dim client As HttpClient =
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}
    ```

2. <span data-ttu-id="ac372-268">В `SumPageSizesAsync,` замените вызов метода `GetURLContentsAsync` вызовом метода `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="ac372-268">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>

    ```vb
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)
    ```

3. <span data-ttu-id="ac372-269">Удалите или прокомментируйте метод `GetURLContentsAsync`, который вы написали.</span><span class="sxs-lookup"><span data-stu-id="ac372-269">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>

4. <span data-ttu-id="ac372-270">Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .</span><span class="sxs-lookup"><span data-stu-id="ac372-270">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

    <span data-ttu-id="ac372-271">Поведение этой версии проекта должно соответствовать поведению, которое описывается в процедуре "Тестирование асинхронного решения"; при этом с вашей стороны требуется даже меньше усилий.</span><span class="sxs-lookup"><span data-stu-id="ac372-271">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>

## <a name="example"></a><span data-ttu-id="ac372-272">Пример</span><span class="sxs-lookup"><span data-stu-id="ac372-272">Example</span></span>

<span data-ttu-id="ac372-273">Ниже приведен полный пример преобразованного асинхронного решения, использующего асинхронный метод `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="ac372-273">The following is the full example of the converted asynchronous solution that uses the asynchronous `GetURLContentsAsync` method.</span></span> <span data-ttu-id="ac372-274">Обратите внимание, что он очень напоминает исходное синхронное решение.</span><span class="sxs-lookup"><span data-stu-id="ac372-274">Notice that it strongly resembles the original, synchronous solution.</span></span>

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        ' Disable the button until the operation is complete.
        startButton.IsEnabled = False

        resultsTextBox.Clear()

        '' One-step async call.
        Await SumPageSizesAsync()

        ' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."

        ' Reenable the button in case you want to run the operation again.
        startButton.IsEnabled = True
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            Dim urlContents As Byte() = Await GetURLContentsAsync(url)

            ' The previous line abbreviates the following two assignment statements.

            '//<snippet21>
            ' GetURLContentsAsync returns a task. At completion, the task
            ' produces a byte array.
            'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
            'Dim urlContents As Byte() = Await getContentsTask

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
    End Function

    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        Using response As WebResponse = Await webReq.GetResponseAsync()

            ' The previous statement abbreviates the following two statements.

            'Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()
            'Using response As WebResponse = Await responseTask

            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                Await responseStream.CopyToAsync(content)

                ' The previous statement abbreviates the following two statements.

                ' CopyToAsync returns a Task, not a Task<T>.
                'Dim copyTask As Task = responseStream.CopyToAsync(content)

                ' When copyTask is completed, content contains a copy of
                ' responseStream.
                'Await copyTask
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
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub

End Class
```

<span data-ttu-id="ac372-275">Следующий код содержит полный пример решения, использующего метод `HttpClient`, `GetByteArrayAsync`.</span><span class="sxs-lookup"><span data-stu-id="ac372-275">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        resultsTextBox.Clear()

        ' Disable the button until the operation is complete.
        startButton.IsEnabled = False

        ' One-step async call.
        Await SumPageSizesAsync()

        ' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."

        ' Reenable the button in case you want to run the operation again.
        startButton.IsEnabled = True
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Declare an HttpClient object and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            ' GetByteArrayAsync returns a task. At completion, the task
            ' produces a byte array.
            Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

            ' The following two lines can replace the previous assignment statement.
            'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
            'Dim urlContents As Byte() = Await getContentsTask

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
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

## <a name="see-also"></a><span data-ttu-id="ac372-276">См. также</span><span class="sxs-lookup"><span data-stu-id="ac372-276">See also</span></span>

- [<span data-ttu-id="ac372-277">Пример асинхронности. Пошаговое руководство "Доступ к сети" (C# и Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac372-277">Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)</span></span>](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)
- [<span data-ttu-id="ac372-278">Оператор Await</span><span class="sxs-lookup"><span data-stu-id="ac372-278">Await Operator</span></span>](../../../../visual-basic/language-reference/operators/await-operator.md)
- [<span data-ttu-id="ac372-279">Async</span><span class="sxs-lookup"><span data-stu-id="ac372-279">Async</span></span>](../../../../visual-basic/language-reference/modifiers/async.md)
- [<span data-ttu-id="ac372-280">Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac372-280">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)
- <span data-ttu-id="ac372-281">[Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) (Типы возвращаемых значений Async (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="ac372-281">[Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)</span></span>
- [<span data-ttu-id="ac372-282">Асинхронное программирование на основе задач (TAP)</span><span class="sxs-lookup"><span data-stu-id="ac372-282">Task-based Asynchronous Programming (TAP)</span></span>](https://go.microsoft.com/fwlink/?LinkId=204847)
- <span data-ttu-id="ac372-283">[How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) (Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="ac372-283">[How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)</span></span>
- <span data-ttu-id="ac372-284">[How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) (Практическое руководство. Параллельное выполнение нескольких веб-запросов с использованием Async и Await (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="ac372-284">[How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)</span></span>
