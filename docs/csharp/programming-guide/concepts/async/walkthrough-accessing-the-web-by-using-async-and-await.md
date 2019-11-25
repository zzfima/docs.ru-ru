---
title: Пошаговое руководство. Доступ к Интернету с помощью модификатора Async и оператора Await (C#)
ms.date: 07/20/2015
ms.assetid: c95d8d71-5a98-4bf0-aaf4-45fed2ebbacd
ms.openlocfilehash: 42b09dab26fd514e184163eaf41aff117d3a463f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281784"
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-c"></a><span data-ttu-id="85c94-102">Пошаговое руководство. Доступ к Интернету с помощью модификатора Async и оператора Await (C#)</span><span class="sxs-lookup"><span data-stu-id="85c94-102">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>

<span data-ttu-id="85c94-103">Возможности Async и Await упрощают создание асинхронных программ.</span><span class="sxs-lookup"><span data-stu-id="85c94-103">You can write asynchronous programs more easily and intuitively by using async/await features.</span></span> <span data-ttu-id="85c94-104">Можно написать асинхронный код, который выглядит как синхронный, и позволить компилятору обрабатывать трудные функции обратного вызова и продолжения, которые обычно включает асинхронный код.</span><span class="sxs-lookup"><span data-stu-id="85c94-104">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>

<span data-ttu-id="85c94-105">Дополнительные сведения о возможности Async см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](./index.md).</span><span class="sxs-lookup"><span data-stu-id="85c94-105">For more information about the Async feature, see [Asynchronous Programming with async and await (C#)](./index.md).</span></span>

<span data-ttu-id="85c94-106">Это пошаговое руководство начинается с создания синхронного приложения Windows Presentation Foundation (WPF), которое суммирует число байтов в списке веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="85c94-106">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="85c94-107">Затем в рамках руководства приложение преобразуется в асинхронное решение с помощью новых возможностей.</span><span class="sxs-lookup"><span data-stu-id="85c94-107">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>

<span data-ttu-id="85c94-108">Если вы не хотите создавать приложение самостоятельно, см. пошаговое руководство по [ доступу к Интернету и использованию Async (C# и Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span><span class="sxs-lookup"><span data-stu-id="85c94-108">If you don't want to build the applications yourself, you can download [Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>

> [!NOTE]
> <span data-ttu-id="85c94-109">Для выполнения примеров необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="85c94-109">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="create-a-wpf-application"></a><span data-ttu-id="85c94-110">Создание приложения WPF</span><span class="sxs-lookup"><span data-stu-id="85c94-110">Create a WPF application</span></span>

1. <span data-ttu-id="85c94-111">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="85c94-111">Start Visual Studio.</span></span>

2. <span data-ttu-id="85c94-112">В строке меню выберите **Файл** > **Создать** > **Проект**.</span><span class="sxs-lookup"><span data-stu-id="85c94-112">On the menu bar, choose **File** > **New** > **Project**.</span></span>

     <span data-ttu-id="85c94-113">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="85c94-113">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="85c94-114">В области **Установленные шаблоны** выберите "Visual C#", а затем в списке типов проектов выберите **Приложение WPF**.</span><span class="sxs-lookup"><span data-stu-id="85c94-114">In the **Installed Templates** pane, choose Visual C#, and then choose **WPF Application** from the list of project types.</span></span>

4. <span data-ttu-id="85c94-115">В текстовом поле **Имя** введите `AsyncExampleWPF` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="85c94-115">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>

     <span data-ttu-id="85c94-116">В **обозревателе решений** появится новый проект.</span><span class="sxs-lookup"><span data-stu-id="85c94-116">The new project appears in **Solution Explorer**.</span></span>

## <a name="design-a-simple-wpf-mainwindow"></a><span data-ttu-id="85c94-117">Разработка простого окна MainWindow WPF</span><span class="sxs-lookup"><span data-stu-id="85c94-117">Design a simple WPF MainWindow</span></span>

1. <span data-ttu-id="85c94-118">В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="85c94-118">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

2. <span data-ttu-id="85c94-119">Если окно **Панель элементов** не отображается, в меню **Вид** выберите пункт **Панель элементов**.</span><span class="sxs-lookup"><span data-stu-id="85c94-119">If the **Toolbox** window isn’t visible, open the **View** menu, and then choose **Toolbox**.</span></span>

3. <span data-ttu-id="85c94-120">Добавьте элементы управления **Button** и **TextBox** в окно **MainWindow**.</span><span class="sxs-lookup"><span data-stu-id="85c94-120">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>

4. <span data-ttu-id="85c94-121">Выделите элемент управления **TextBox** и в окне **Свойства** задайте указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="85c94-121">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="85c94-122">Задайте для свойства **Имя** значение `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="85c94-122">Set the **Name** property to `resultsTextBox`.</span></span>

    - <span data-ttu-id="85c94-123">Задайте для свойства **Высота** значение 250.</span><span class="sxs-lookup"><span data-stu-id="85c94-123">Set the **Height** property to 250.</span></span>

    - <span data-ttu-id="85c94-124">Задайте для свойства **Ширина** значение 500.</span><span class="sxs-lookup"><span data-stu-id="85c94-124">Set the **Width** property to 500.</span></span>

    - <span data-ttu-id="85c94-125">На вкладке **Текст** укажите моноширинный шрифт, например Lucida Console или Global Monospace.</span><span class="sxs-lookup"><span data-stu-id="85c94-125">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>

5. <span data-ttu-id="85c94-126">Выделите элемент управления **Button** и в окне **Свойства** задайте указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="85c94-126">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="85c94-127">Задайте для свойства **Имя** значение `startButton`.</span><span class="sxs-lookup"><span data-stu-id="85c94-127">Set the **Name** property to `startButton`.</span></span>

    - <span data-ttu-id="85c94-128">Измените значение свойства **Содержимое** с **Button** на **Start**.</span><span class="sxs-lookup"><span data-stu-id="85c94-128">Change the value of the **Content** property from **Button** to **Start**.</span></span>

6. <span data-ttu-id="85c94-129">Поместите текстовое поле и кнопку так, чтобы оба элемента управления отображались в окне **MainWindow**.</span><span class="sxs-lookup"><span data-stu-id="85c94-129">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>

     <span data-ttu-id="85c94-130">Дополнительные сведения о конструкторе XAML WPF см. в разделе [Создание пользовательского интерфейса с помощью конструктора XAML](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="85c94-130">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>

## <a name="add-a-reference"></a><span data-ttu-id="85c94-131">Добавление ссылки</span><span class="sxs-lookup"><span data-stu-id="85c94-131">Add a reference</span></span>

1. <span data-ttu-id="85c94-132">В **обозревателе решений** выделите имя проекта.</span><span class="sxs-lookup"><span data-stu-id="85c94-132">In **Solution Explorer**, highlight your project's name.</span></span>

2. <span data-ttu-id="85c94-133">В строке меню выберите **Проект** > **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="85c94-133">On the menu bar, choose **Project** > **Add Reference**.</span></span>

     <span data-ttu-id="85c94-134">Откроется диалоговое окно **Диспетчер ссылок**.</span><span class="sxs-lookup"><span data-stu-id="85c94-134">The **Reference Manager** dialog box appears.</span></span>

3. <span data-ttu-id="85c94-135">Вверху диалогового окна убедитесь в том, что проект предназначен для платформы .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="85c94-135">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>

4. <span data-ttu-id="85c94-136">В категории **Сборки** выберите **Платформа**, если этот вариант еще не выбран.</span><span class="sxs-lookup"><span data-stu-id="85c94-136">In the **Assemblies** category, choose **Framework** if it isn’t already chosen.</span></span>

5. <span data-ttu-id="85c94-137">В списке имен установите флажок **System.Net.Http**.</span><span class="sxs-lookup"><span data-stu-id="85c94-137">In the list of names, select the **System.Net.Http** check box.</span></span>

6. <span data-ttu-id="85c94-138">Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="85c94-138">Choose the **OK** button to close the dialog box.</span></span>

## <a name="add-necessary-using-directives"></a><span data-ttu-id="85c94-139">Добавление необходимых директив using</span><span class="sxs-lookup"><span data-stu-id="85c94-139">Add necessary using directives</span></span>

1. <span data-ttu-id="85c94-140">В **обозревателе решений** откройте контекстное меню для MainWindow.xaml.cs и выберите пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="85c94-140">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>

2. <span data-ttu-id="85c94-141">В начало файла с кодом добавьте указанные ниже директивы `using`, если они отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="85c94-141">Add the following `using` directives at the top of the code file if they’re not already present.</span></span>

    ```csharp
    using System.Net.Http;
    using System.Net;
    using System.IO;
    ```

## <a name="create-a-synchronous-app"></a><span data-ttu-id="85c94-142">Создание синхронного приложения</span><span class="sxs-lookup"><span data-stu-id="85c94-142">Create a synchronous app</span></span>

1. <span data-ttu-id="85c94-143">В окне конструктора для MainWindow.xaml дважды щелкните кнопку **Start**, чтобы создать обработчик событий `startButton_Click` в файле MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="85c94-143">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>

2. <span data-ttu-id="85c94-144">В файле MainWindow.xaml.cs скопируйте следующий код в тело `startButton_Click`:</span><span class="sxs-lookup"><span data-stu-id="85c94-144">In MainWindow.xaml.cs, copy the following code into the body of `startButton_Click`:</span></span>

    ```csharp
    resultsTextBox.Clear();
    SumPageSizes();
    resultsTextBox.Text += "\r\nControl returned to startButton_Click.";
    ```

    <span data-ttu-id="85c94-145">Код вызывает метод, который управляет приложением `SumPageSizes` и выводит на экран сообщение, когда элемент управления возвращается к `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="85c94-145">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>

3. <span data-ttu-id="85c94-146">Код для синхронного решения содержит следующие четыре метода:</span><span class="sxs-lookup"><span data-stu-id="85c94-146">The code for the synchronous solution contains the following four methods:</span></span>

    - <span data-ttu-id="85c94-147">`SumPageSizes`, который получает список URL-адресов веб-страниц из `SetUpURLList`, а затем вызывает метод `GetURLContents` и `DisplayResults` для обработки каждого URL-адреса;</span><span class="sxs-lookup"><span data-stu-id="85c94-147">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>

    - <span data-ttu-id="85c94-148">`SetUpURLList`, который создает и возвращает список веб-адресов;</span><span class="sxs-lookup"><span data-stu-id="85c94-148">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>

    - <span data-ttu-id="85c94-149">`GetURLContents`, который загружает содержимое каждого веб-сайта и возвращает содержимое в виде массива байтов;</span><span class="sxs-lookup"><span data-stu-id="85c94-149">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>

    - <span data-ttu-id="85c94-150">`DisplayResults`, который показывает число байтов в массиве байтов для каждого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="85c94-150">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>

    <span data-ttu-id="85c94-151">Скопируйте следующие четыре метода, а затем вставьте их в обработчик событий `startButton_Click` в файле MainWindow.xaml.cs:</span><span class="sxs-lookup"><span data-stu-id="85c94-151">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.cs:</span></span>

    ```csharp
    private void SumPageSizes()
    {
        // Make a list of web addresses.
        List<string> urlList = SetUpURLList();

        var total = 0;
        foreach (var url in urlList)
        {
            // GetURLContents returns the contents of url as a byte array.
            byte[] urlContents = GetURLContents(url);

            DisplayResults(url, urlContents);

            // Update the total.
            total += urlContents.Length;
        }

        // Display the total count for all of the web addresses.
        resultsTextBox.Text += $"\r\n\r\nTotal bytes returned:  {total}\r\n";
    }

    private List<string> SetUpURLList()
    {
        var urls = new List<string>
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
        };
        return urls;
    }

    private byte[] GetURLContents(string url)
    {
        // The downloaded resource ends up in the variable named content.
        var content = new MemoryStream();

        // Initialize an HttpWebRequest for the current URL.
        var webReq = (HttpWebRequest)WebRequest.Create(url);

        // Send the request to the Internet resource and wait for
        // the response.
        // Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.
        using (WebResponse response = webReq.GetResponse())
        {
            // Get the data stream that is associated with the specified URL.
            using (Stream responseStream = response.GetResponseStream())
            {
                // Read the bytes in responseStream and copy them to content.
                responseStream.CopyTo(content);
            }
        }

        // Return the result as a byte array.
        return content.ToArray();
    }

    private void DisplayResults(string url, byte[] content)
    {
        // Display the length of each website. The string format
        // is designed to be used with a monospaced font, such as
        // Lucida Console or Global Monospace.
        var bytes = content.Length;
        // Strip off the "https://".
        var displayURL = url.Replace("https://", "");
        resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
    }
    ```

## <a name="test-the-synchronous-solution"></a><span data-ttu-id="85c94-152">Тестирование синхронного решения</span><span class="sxs-lookup"><span data-stu-id="85c94-152">Test the synchronous solution</span></span>

<span data-ttu-id="85c94-153">Нажмите клавишу **F5**, чтобы запустить программу, а затем нажмите кнопку **Запуск**.</span><span class="sxs-lookup"><span data-stu-id="85c94-153">Choose the **F5** key to run the program, and then choose the **Start** button.</span></span>

<span data-ttu-id="85c94-154">Программа должна выдать результаты, похожие на следующий список:</span><span class="sxs-lookup"><span data-stu-id="85c94-154">Output that resembles the following list should appear:</span></span>

```text
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

<span data-ttu-id="85c94-155">Обратите внимание, что вывод результатов на экран занимает несколько секунд.</span><span class="sxs-lookup"><span data-stu-id="85c94-155">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="85c94-156">В течение этого времени поток пользовательского интерфейса заблокирован, пока он ожидает загрузку запрошенных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="85c94-156">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="85c94-157">Соответственно, после нажатия кнопки **Start** окно нельзя перемещать, разворачивать, сворачивать или даже закрывать.</span><span class="sxs-lookup"><span data-stu-id="85c94-157">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="85c94-158">Эти действия будут завершаться сбоем, пока не появятся результаты подсчета.</span><span class="sxs-lookup"><span data-stu-id="85c94-158">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="85c94-159">Если веб-сайт не отвечает, вы не можете определить, на каком сайте произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="85c94-159">If a website isn’t responding, you have no indication of which site failed.</span></span> <span data-ttu-id="85c94-160">Трудно даже остановить ожидание и закрыть программу.</span><span class="sxs-lookup"><span data-stu-id="85c94-160">It is difficult even to stop waiting and close the program.</span></span>

## <a name="convert-geturlcontents-to-an-asynchronous-method"></a><span data-ttu-id="85c94-161">Преобразование GetURLContents в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="85c94-161">Convert GetURLContents to an asynchronous method</span></span>

1. <span data-ttu-id="85c94-162">Чтобы преобразовать синхронное решение в асинхронное, лучше всего начать с метода `GetURLContents`, поскольку вызовы метода <xref:System.Net.HttpWebRequest> <xref:System.Net.HttpWebRequest.GetResponse%2A> и метода <xref:System.IO.Stream> <xref:System.IO.Stream.CopyTo%2A> выполняются, когда приложение подключается к Интернету.</span><span class="sxs-lookup"><span data-stu-id="85c94-162">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest> method <xref:System.Net.HttpWebRequest.GetResponse%2A> and to the <xref:System.IO.Stream> method <xref:System.IO.Stream.CopyTo%2A> are where the application accesses the web.</span></span> <span data-ttu-id="85c94-163">Платформа .NET Framework упрощает преобразование путем предоставления асинхронных версий этих методов.</span><span class="sxs-lookup"><span data-stu-id="85c94-163">The .NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>

     <span data-ttu-id="85c94-164">Дополнительные сведения о методах, которые используются в `GetURLContents`, см. в разделе <xref:System.Net.WebRequest>.</span><span class="sxs-lookup"><span data-stu-id="85c94-164">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>

    > [!NOTE]
    > <span data-ttu-id="85c94-165">По мере выполнения шагов в этом пошаговом руководстве возникают различные ошибки компилятора.</span><span class="sxs-lookup"><span data-stu-id="85c94-165">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="85c94-166">Их можно игнорировать и продолжить процедуры пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="85c94-166">You can ignore them and continue with the walkthrough.</span></span>

     <span data-ttu-id="85c94-167">Измените метод, который вызывается в третьей строке `GetURLContents` из `GetResponse`, асинхронным методом <xref:System.Net.WebRequest.GetResponseAsync%2A>, основанным на задачах.</span><span class="sxs-lookup"><span data-stu-id="85c94-167">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>

    ```csharp
    using (WebResponse response = webReq.GetResponseAsync())
    ```

2. <span data-ttu-id="85c94-168">`GetResponseAsync` возвращает значение типа <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="85c94-168">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="85c94-169">В этом случае *переменная, возвращаемая задачей*, `TResult`, имеет тип <xref:System.Net.WebResponse>.</span><span class="sxs-lookup"><span data-stu-id="85c94-169">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="85c94-170">Задача является обещанием создать фактический объект `WebResponse` после загрузки запрошенных данных и выполнения задачи до завершения.</span><span class="sxs-lookup"><span data-stu-id="85c94-170">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>

     <span data-ttu-id="85c94-171">Для получения значения `WebResponse` из задачи примените оператор [await](../../../language-reference/operators/await.md) для вызова метода `GetResponseAsync`, как показано в приведенном ниже примере кода.</span><span class="sxs-lookup"><span data-stu-id="85c94-171">To retrieve the `WebResponse` value from the task, apply an [await](../../../language-reference/operators/await.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>

    ```csharp
    using (WebResponse response = await webReq.GetResponseAsync())
    ```

     <span data-ttu-id="85c94-172">Оператор `await` приостанавливает выполнение текущего метода `GetURLContents`, пока не будет завершена ожидаемая задача.</span><span class="sxs-lookup"><span data-stu-id="85c94-172">The `await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="85c94-173">На это время управление возвращается вызывающему объекту текущего метода.</span><span class="sxs-lookup"><span data-stu-id="85c94-173">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="85c94-174">В этом примере текущим методом является `GetURLContents`, а вызывающим объектом — `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="85c94-174">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="85c94-175">После завершения задачи создается обещанный объект `WebResponse` в качестве значения ожидаемой задачи, который присваивается переменной `response`.</span><span class="sxs-lookup"><span data-stu-id="85c94-175">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>

     <span data-ttu-id="85c94-176">Предыдущий оператор можно разделить на следующие два оператора для уточнения выполняемых операций.</span><span class="sxs-lookup"><span data-stu-id="85c94-176">The previous statement can be separated into the following two statements to clarify what happens.</span></span>

    ```csharp
    //Task<WebResponse> responseTask = webReq.GetResponseAsync();
    //using (WebResponse response = await responseTask)
    ```

     <span data-ttu-id="85c94-177">Вызов `webReq.GetResponseAsync` возвращает `Task(Of WebResponse)` или `Task<WebResponse>`.</span><span class="sxs-lookup"><span data-stu-id="85c94-177">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="85c94-178">Затем оператор await применяется к задаче для получения значения `WebResponse`.</span><span class="sxs-lookup"><span data-stu-id="85c94-178">Then an await operator is applied to the task to retrieve the `WebResponse` value.</span></span>

     <span data-ttu-id="85c94-179">Если асинхронному методу нужно выполнить определенную работу, не связанную с завершением конкретной задачи, он может проделать это между выполнением этих двух операторов: после вызова метода async и перед применением оператора `await`.</span><span class="sxs-lookup"><span data-stu-id="85c94-179">If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the `await` operator is applied.</span></span> <span data-ttu-id="85c94-180">Примеры см. в статьях [Практическое руководство. Параллельное выполнение нескольких веб-запросов с использованием Async и Await (C#)](./how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) и [Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="85c94-180">For examples, see [How to make multiple web requests in parallel by using async and await (C#)](./how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to extend the async walkthrough by using Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>

3. <span data-ttu-id="85c94-181">Из-за добавления оператора `await` в предыдущем шаге возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="85c94-181">Because you added the `await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="85c94-182">Этот оператор можно использовать только в методах, помеченных модификатором [async](../../../language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="85c94-182">The operator can be used only in methods that are marked with the [async](../../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="85c94-183">Пропустите ошибку, повторяя действия по замене вызова `CopyTo` вызовом метода `CopyToAsync`.</span><span class="sxs-lookup"><span data-stu-id="85c94-183">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>

    - <span data-ttu-id="85c94-184">Измените имя метода, вызывающего <xref:System.IO.Stream.CopyToAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="85c94-184">Change the name of the method that’s called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>

    - <span data-ttu-id="85c94-185">Метод `CopyTo` или `CopyToAsync` копирует байты в свой аргумент `content` и не возвращает осмысленное значение.</span><span class="sxs-lookup"><span data-stu-id="85c94-185">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn’t return a meaningful value.</span></span> <span data-ttu-id="85c94-186">В синхронной версии вызов метода `CopyTo` — это просто оператор, который не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="85c94-186">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="85c94-187">Асинхронная версия — `CopyToAsync` — возвращает <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="85c94-187">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="85c94-188">Задача работает как Task(void) и позволяет ожидать метод.</span><span class="sxs-lookup"><span data-stu-id="85c94-188">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="85c94-189">Примените `Await` или `await` к вызову `CopyToAsync`, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="85c94-189">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>

        ```csharp
        await responseStream.CopyToAsync(content);
        ```

         <span data-ttu-id="85c94-190">Предыдущий оператор сокращает две следующие строки кода.</span><span class="sxs-lookup"><span data-stu-id="85c94-190">The previous statement abbreviates the following two lines of code.</span></span>

        ```csharp
        // CopyToAsync returns a Task, not a Task<T>.
        //Task copyTask = responseStream.CopyToAsync(content);

        // When copyTask is completed, content contains a copy of
        // responseStream.
        //await copyTask;
        ```

4. <span data-ttu-id="85c94-191">Все, что остается сделать в `GetURLContents`, — это изменить подпись метода.</span><span class="sxs-lookup"><span data-stu-id="85c94-191">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="85c94-192">Оператор `await` можно использовать только в методах, помеченных модификатором [async](../../../language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="85c94-192">You can use the `await` operator only in methods that are marked with the [async](../../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="85c94-193">Добавьте модификатор, чтобы пометить метод как *асинхронный*, как показано в приведенном ниже примере кода.</span><span class="sxs-lookup"><span data-stu-id="85c94-193">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>

    ```csharp
    private async byte[] GetURLContents(string url)
    ```

5. <span data-ttu-id="85c94-194">Типом возвращаемого значения асинхронного метода может быть только <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> или `void` в C#.</span><span class="sxs-lookup"><span data-stu-id="85c94-194">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, or `void` in C#.</span></span> <span data-ttu-id="85c94-195">Как правило, тип возвращаемого значения `void` используется только в асинхронном обработчике событий, где `void` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="85c94-195">Typically, a return type of `void` is used only in an async event handler, where `void` is required.</span></span> <span data-ttu-id="85c94-196">В других случаях используется `Task(T)`, если завершенный метод имеет оператор [return](../../../language-reference/keywords/return.md), возвращающий значение типа T, или `Task`, если завершенный метод не возвращает осмысленное значение.</span><span class="sxs-lookup"><span data-stu-id="85c94-196">In other cases, you use `Task(T)` if the completed method has a [return](../../../language-reference/keywords/return.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.</span></span> <span data-ttu-id="85c94-197">Можно представить тип возвращаемого значения `Task` как Task(void).</span><span class="sxs-lookup"><span data-stu-id="85c94-197">You can think of the `Task` return type as meaning "Task(void)."</span></span>

     <span data-ttu-id="85c94-198">Дополнительные сведения см. в разделе [Асинхронные типы возвращаемых значений (C#)](./async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="85c94-198">For more information, see [Async Return Types (C#)](./async-return-types.md).</span></span>

     <span data-ttu-id="85c94-199">Метод `GetURLContents` имеет оператор return, который возвращает массив байтов.</span><span class="sxs-lookup"><span data-stu-id="85c94-199">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="85c94-200">Таким образом, тип возвращаемого значения асинхронной версии — Task(T), где T — массив байтов.</span><span class="sxs-lookup"><span data-stu-id="85c94-200">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="85c94-201">Внесите следующие изменения в подпись метода.</span><span class="sxs-lookup"><span data-stu-id="85c94-201">Make the following changes in the method signature:</span></span>

    - <span data-ttu-id="85c94-202">Измените тип возвращаемого значения на `Task<byte[]>`.</span><span class="sxs-lookup"><span data-stu-id="85c94-202">Change the return type to `Task<byte[]>`.</span></span>

    - <span data-ttu-id="85c94-203">По соглашению об именовании асинхронные методы имеют имена, заканчивающиеся на Async, поэтому переименуйте метод в `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="85c94-203">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>

     <span data-ttu-id="85c94-204">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="85c94-204">The following code shows these changes.</span></span>

    ```csharp
    private async Task<byte[]> GetURLContentsAsync(string url)
    ```

     <span data-ttu-id="85c94-205">После внесения этих изменений преобразование `GetURLContents` в асинхронный метод завершено.</span><span class="sxs-lookup"><span data-stu-id="85c94-205">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>

## <a name="convert-sumpagesizes-to-an-asynchronous-method"></a><span data-ttu-id="85c94-206">Преобразование SumPageSizes в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="85c94-206">Convert SumPageSizes to an asynchronous method</span></span>

1. <span data-ttu-id="85c94-207">Повторите шаги из предыдущей процедуры для `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="85c94-207">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="85c94-208">Во-первых, преобразуйте вызов метода `GetURLContents` в вызов асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="85c94-208">First, change the call to `GetURLContents` to an asynchronous call.</span></span>

    - <span data-ttu-id="85c94-209">Измените имя вызываемого метода с `GetURLContents` на `GetURLContentsAsync`, если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="85c94-209">Change the name of the method that’s called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>

    - <span data-ttu-id="85c94-210">Примените оператор `await` к задаче, возвращаемой методом `GetURLContentsAsync`, для получения значения байтового массива.</span><span class="sxs-lookup"><span data-stu-id="85c94-210">Apply `await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>

     <span data-ttu-id="85c94-211">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="85c94-211">The following code shows these changes.</span></span>

    ```csharp
    byte[] urlContents = await GetURLContentsAsync(url);
    ```

     <span data-ttu-id="85c94-212">Предыдущее назначение сокращает две следующие строки кода.</span><span class="sxs-lookup"><span data-stu-id="85c94-212">The previous assignment abbreviates the following two lines of code.</span></span>

    ```csharp
    // GetURLContentsAsync returns a Task<T>. At completion, the task
    // produces a byte array.
    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
    //byte[] urlContents = await getContentsTask;
    ```

2. <span data-ttu-id="85c94-213">Внесите следующие изменения в подпись метода.</span><span class="sxs-lookup"><span data-stu-id="85c94-213">Make the following changes in the method's signature:</span></span>

    - <span data-ttu-id="85c94-214">Пометьте метод модификатором `async`.</span><span class="sxs-lookup"><span data-stu-id="85c94-214">Mark the method with the `async` modifier.</span></span>

    - <span data-ttu-id="85c94-215">Добавьте в имя метода Async.</span><span class="sxs-lookup"><span data-stu-id="85c94-215">Add "Async" to the method name.</span></span>

    - <span data-ttu-id="85c94-216">В этот раз нет возвращаемой переменной задачи T, поскольку `SumPageSizesAsync` не возвращает значение для T. (В этом методе нет оператора `return`.) Тем не менее метод должен возвращать `Task`, чтобы для него можно было задать ожидание.</span><span class="sxs-lookup"><span data-stu-id="85c94-216">There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="85c94-217">Поэтому измените тип возвращаемого значения метода с `void` на `Task`.</span><span class="sxs-lookup"><span data-stu-id="85c94-217">Therefore, change the return type of the method from `void` to `Task`.</span></span>

    <span data-ttu-id="85c94-218">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="85c94-218">The following code shows these changes.</span></span>

    ```csharp
    private async Task SumPageSizesAsync()
    ```

     <span data-ttu-id="85c94-219">Преобразование `SumPageSizes` в `SumPageSizesAsync` завершено.</span><span class="sxs-lookup"><span data-stu-id="85c94-219">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>

## <a name="convert-startbutton_click-to-an-asynchronous-method"></a><span data-ttu-id="85c94-220">Преобразование startButton_Click в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="85c94-220">Convert startButton_Click to an asynchronous method</span></span>

1. <span data-ttu-id="85c94-221">В обработчике событий измените имя вызываемого метода с `SumPageSizes` на `SumPageSizesAsync`, если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="85c94-221">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven’t already done so.</span></span>

2. <span data-ttu-id="85c94-222">Поскольку `SumPageSizesAsync` является асинхронным методом, измените код в обработчике событий для ожидания результата.</span><span class="sxs-lookup"><span data-stu-id="85c94-222">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>

     <span data-ttu-id="85c94-223">Вызов `SumPageSizesAsync` отражает вызов `CopyToAsync` в `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="85c94-223">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="85c94-224">Вызов возвращает `Task`, а не `Task(T)`.</span><span class="sxs-lookup"><span data-stu-id="85c94-224">The call returns a `Task`, not a `Task(T)`.</span></span>

     <span data-ttu-id="85c94-225">Как и в предыдущих процедурах, вызов можно преобразовать, используя один или два оператора.</span><span class="sxs-lookup"><span data-stu-id="85c94-225">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="85c94-226">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="85c94-226">The following code shows these changes.</span></span>

    ```csharp
    // One-step async call.
    await SumPageSizesAsync();

    // Two-step async call.
    //Task sumTask = SumPageSizesAsync();
    //await sumTask;
    ```

3. <span data-ttu-id="85c94-227">Чтобы предотвратить случайное повторное введение операции, добавьте следующий оператор в верхней части `startButton_Click`, чтобы отключить кнопку **Start**.</span><span class="sxs-lookup"><span data-stu-id="85c94-227">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>

    ```csharp
    // Disable the button until the operation is complete.
    startButton.IsEnabled = false;
    ```

     <span data-ttu-id="85c94-228">Можно снова включить кнопку в конце обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="85c94-228">You can reenable the button at the end of the event handler.</span></span>

    ```csharp
    // Reenable the button in case you want to run the operation again.
    startButton.IsEnabled = true;
    ```

     <span data-ttu-id="85c94-229">Дополнительные сведения о повторном входе см. в разделе [Обработка повторного входа в асинхронных приложениях (C#)](./handling-reentrancy-in-async-apps.md).</span><span class="sxs-lookup"><span data-stu-id="85c94-229">For more information about reentrancy, see [Handling Reentrancy in Async Apps (C#)](./handling-reentrancy-in-async-apps.md).</span></span>

4. <span data-ttu-id="85c94-230">Наконец, добавьте модификатор `async` в объявление, чтобы обработчик событий мог ожидать `SumPagSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="85c94-230">Finally, add the `async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>

    ```csharp
    private async void startButton_Click(object sender, RoutedEventArgs e)
    ```

     <span data-ttu-id="85c94-231">Как правило, имена обработчиков событий не изменяются.</span><span class="sxs-lookup"><span data-stu-id="85c94-231">Typically, the names of event handlers aren’t changed.</span></span> <span data-ttu-id="85c94-232">Тип возвращаемого значения не изменяется на `Task`, так как обработчики событий должны возвращать `void`.</span><span class="sxs-lookup"><span data-stu-id="85c94-232">The return type isn’t changed to `Task` because event handlers must return `void`.</span></span>

     <span data-ttu-id="85c94-233">Преобразование проекта из синхронного в асинхронный завершено.</span><span class="sxs-lookup"><span data-stu-id="85c94-233">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>

## <a name="test-the-asynchronous-solution"></a><span data-ttu-id="85c94-234">Тестирование асинхронного решения</span><span class="sxs-lookup"><span data-stu-id="85c94-234">Test the asynchronous solution</span></span>

1. <span data-ttu-id="85c94-235">Нажмите клавишу **F5**, чтобы запустить программу, а затем нажмите кнопку **Запуск**.</span><span class="sxs-lookup"><span data-stu-id="85c94-235">Choose the **F5** key to run the program, and then choose the **Start** button.</span></span>

2. <span data-ttu-id="85c94-236">Появившиеся результаты должны напоминать результаты синхронного решения.</span><span class="sxs-lookup"><span data-stu-id="85c94-236">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="85c94-237">Однако имеются следующие различия.</span><span class="sxs-lookup"><span data-stu-id="85c94-237">However, notice the following differences.</span></span>

    - <span data-ttu-id="85c94-238">Все результаты не отображаются одновременно после завершения обработки.</span><span class="sxs-lookup"><span data-stu-id="85c94-238">The results don’t all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="85c94-239">Например, обе программы содержат строку в `startButton_Click`, которая очищает текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="85c94-239">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="85c94-240">Ее цель состоит в том, чтобы очистить текстовое поле между запусками при нажатии кнопки **Start** во второй раз после появления одного набора результатов.</span><span class="sxs-lookup"><span data-stu-id="85c94-240">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="85c94-241">В синхронной версии текстовое поле очищается перед отображением данных во второй раз, после завершения загрузки и высвобождения потока пользовательского интерфейса для выполнения других операций.</span><span class="sxs-lookup"><span data-stu-id="85c94-241">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="85c94-242">В асинхронной версии текстовое поле очищается сразу же после нажатия кнопки **Start**.</span><span class="sxs-lookup"><span data-stu-id="85c94-242">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>

    - <span data-ttu-id="85c94-243">И что самое главное, поток пользовательского интерфейса не блокируется во время загрузки.</span><span class="sxs-lookup"><span data-stu-id="85c94-243">Most importantly, the UI thread isn’t blocked during the downloads.</span></span> <span data-ttu-id="85c94-244">Можно перемещать окно или изменять его размер во время загрузки, подсчета и отображения веб-ресурсов.</span><span class="sxs-lookup"><span data-stu-id="85c94-244">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="85c94-245">Если один из веб-сайтов работает медленно или не отвечает, можно отменить операцию, нажав кнопку **Закрыть** (красный крестик в правом верхнем углу окна).</span><span class="sxs-lookup"><span data-stu-id="85c94-245">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>

## <a name="replace-method-geturlcontentsasync-with-a-net-framework-method"></a><span data-ttu-id="85c94-246">Замена GetURLContentsAsync методом .NET Framework</span><span class="sxs-lookup"><span data-stu-id="85c94-246">Replace method GetURLContentsAsync with a .NET Framework method</span></span>

1. <span data-ttu-id="85c94-247">Платформа .NET Framework 4.5 предоставляет много асинхронных методов, которые вы можете использовать.</span><span class="sxs-lookup"><span data-stu-id="85c94-247">The .NET Framework 4.5 provides many async methods that you can use.</span></span> <span data-ttu-id="85c94-248">Один из них, метод <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29> <xref:System.Net.Http.HttpClient>, выполняет именно те операции, которые требуются для данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="85c94-248">One of them, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, does just what you need for this walkthrough.</span></span> <span data-ttu-id="85c94-249">Его можно использовать вместо метода `GetURLContentsAsync`, созданного в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="85c94-249">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>

     <span data-ttu-id="85c94-250">Первым шагом является создание объекта `HttpClient` в методе `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="85c94-250">The first step is to create an `HttpClient` object in method `SumPageSizesAsync`.</span></span> <span data-ttu-id="85c94-251">Добавьте следующее объявление в начале метода.</span><span class="sxs-lookup"><span data-stu-id="85c94-251">Add the following declaration at the start of the method.</span></span>

    ```csharp
    // Declare an HttpClient object and increase the buffer size. The
    // default buffer size is 65,536.
    HttpClient client =
        new HttpClient() { MaxResponseContentBufferSize = 1000000 };
    ```

2. <span data-ttu-id="85c94-252">В `SumPageSizesAsync,` замените вызов метода `GetURLContentsAsync` вызовом метода `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="85c94-252">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>

    ```csharp
    byte[] urlContents = await client.GetByteArrayAsync(url);
    ```

3. <span data-ttu-id="85c94-253">Удалите или прокомментируйте метод `GetURLContentsAsync`, который вы написали.</span><span class="sxs-lookup"><span data-stu-id="85c94-253">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>

4. <span data-ttu-id="85c94-254">Нажмите клавишу **F5**, чтобы запустить программу, а затем нажмите кнопку **Запуск**.</span><span class="sxs-lookup"><span data-stu-id="85c94-254">Choose the **F5** key to run the program, and then choose the **Start** button.</span></span>

     <span data-ttu-id="85c94-255">Поведение этой версии проекта должно соответствовать поведению, которое описывается в процедуре "Тестирование асинхронного решения"; при этом с вашей стороны требуется даже меньше усилий.</span><span class="sxs-lookup"><span data-stu-id="85c94-255">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>

## <a name="example-code"></a><span data-ttu-id="85c94-256">пример кода</span><span class="sxs-lookup"><span data-stu-id="85c94-256">Example code</span></span>

<span data-ttu-id="85c94-257">Следующий код содержит полный пример преобразования решения из синхронного в асинхронное с помощью написанного вами асинхронного метода `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="85c94-257">The following code contains the full example of the conversion from a synchronous to an asynchronous solution by using the asynchronous `GetURLContentsAsync` method that you wrote.</span></span> <span data-ttu-id="85c94-258">Обратите внимание, что он очень напоминает исходное синхронное решение.</span><span class="sxs-lookup"><span data-stu-id="85c94-258">Notice that it strongly resembles the original, synchronous solution.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;

// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            // Disable the button until the operation is complete.
            startButton.IsEnabled = false;

            resultsTextBox.Clear();

            // One-step async call.
            await SumPageSizesAsync();

            // Two-step async call.
            //Task sumTask = SumPageSizesAsync();
            //await sumTask;

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";

            // Reenable the button in case you want to run the operation again.
            startButton.IsEnabled = true;
        }

        private async Task SumPageSizesAsync()
        {
            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            var total = 0;

            foreach (var url in urlList)
            {
                byte[] urlContents = await GetURLContentsAsync(url);

                // The previous line abbreviates the following two assignment statements.

                // GetURLContentsAsync returns a Task<T>. At completion, the task
                // produces a byte array.
                //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
                //byte[] urlContents = await getContentsTask;

                DisplayResults(url, urlContents);

                // Update the total.
                total += urlContents.Length;
            }
            // Display the total count for all of the websites.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
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
            };
            return urls;
        }

        private async Task<byte[]> GetURLContentsAsync(string url)
        {
            // The downloaded resource ends up in the variable named content.
            var content = new MemoryStream();

            // Initialize an HttpWebRequest for the current URL.
            var webReq = (HttpWebRequest)WebRequest.Create(url);

            // Send the request to the Internet resource and wait for
            // the response.
            using (WebResponse response = await webReq.GetResponseAsync())

            // The previous statement abbreviates the following two statements.

            //Task<WebResponse> responseTask = webReq.GetResponseAsync();
            //using (WebResponse response = await responseTask)
            {
                // Get the data stream that is associated with the specified url.
                using (Stream responseStream = response.GetResponseStream())
                {
                    // Read the bytes in responseStream and copy them to content.
                    await responseStream.CopyToAsync(content);

                    // The previous statement abbreviates the following two statements.

                    // CopyToAsync returns a Task, not a Task<T>.
                    //Task copyTask = responseStream.CopyToAsync(content);

                    // When copyTask is completed, content contains a copy of
                    // responseStream.
                    //await copyTask;
                }
            }
            // Return the result as a byte array.
            return content.ToArray();
        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each website. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

<span data-ttu-id="85c94-259">Следующий код содержит полный пример решения, использующего метод `HttpClient`, `GetByteArrayAsync`.</span><span class="sxs-lookup"><span data-stu-id="85c94-259">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;

// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            resultsTextBox.Clear();

            // Disable the button until the operation is complete.
            startButton.IsEnabled = false;

            // One-step async call.
            await SumPageSizesAsync();

            //// Two-step async call.
            //Task sumTask = SumPageSizesAsync();
            //await sumTask;

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";

            // Reenable the button in case you want to run the operation again.
            startButton.IsEnabled = true;
        }

        private async Task SumPageSizesAsync()
        {
            // Declare an HttpClient object and increase the buffer size. The
            // default buffer size is 65,536.
            HttpClient client =
                new HttpClient() { MaxResponseContentBufferSize = 1000000 };

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            var total = 0;

            foreach (var url in urlList)
            {
                // GetByteArrayAsync returns a task. At completion, the task
                // produces a byte array.
                byte[] urlContents = await client.GetByteArrayAsync(url);

                // The following two lines can replace the previous assignment statement.
                //Task<byte[]> getContentsTask = client.GetByteArrayAsync(url);
                //byte[] urlContents = await getContentsTask;

                DisplayResults(url, urlContents);

                // Update the total.
                total += urlContents.Length;
            }

            // Display the total count for all of the websites.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
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
            };
            return urls;
        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each website. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="85c94-260">См. также</span><span class="sxs-lookup"><span data-stu-id="85c94-260">See also</span></span>

- <span data-ttu-id="85c94-261">[Пример использования Async. Пошаговое руководство. Обращение к веб-сайтам (C# и Visual Basic)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/hh300224(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="85c94-261">[Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/hh300224(v=vs.110))</span></span>
- [<span data-ttu-id="85c94-262">async</span><span class="sxs-lookup"><span data-stu-id="85c94-262">async</span></span>](../../../language-reference/keywords/async.md)
- [<span data-ttu-id="85c94-263">await</span><span class="sxs-lookup"><span data-stu-id="85c94-263">await</span></span>](../../../language-reference/operators/await.md)
- [<span data-ttu-id="85c94-264">Асинхронное программирование с использованием ключевых слов async и await (C#)</span><span class="sxs-lookup"><span data-stu-id="85c94-264">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- <span data-ttu-id="85c94-265">[Async Return Types (C#)](./async-return-types.md) (Типы возвращаемых значений асинхронных операций в C#)</span><span class="sxs-lookup"><span data-stu-id="85c94-265">[Async Return Types (C#)](./async-return-types.md)</span></span>
- [<span data-ttu-id="85c94-266">Асинхронное программирование на основе задач (TAP)</span><span class="sxs-lookup"><span data-stu-id="85c94-266">Task-based Asynchronous Programming (TAP)</span></span>](https://www.microsoft.com/download/details.aspx?id=19957)
- [<span data-ttu-id="85c94-267">Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll (C#)</span><span class="sxs-lookup"><span data-stu-id="85c94-267">How to extend the async walkthrough by using Task.WhenAll (C#)</span></span>](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
- [<span data-ttu-id="85c94-268">Практическое руководство. Параллельное выполнение нескольких веб-запросов с использованием Async и Await (C#)</span><span class="sxs-lookup"><span data-stu-id="85c94-268">How to make multiple web requests in parallel by using async and await (C#)</span></span>](./how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)
