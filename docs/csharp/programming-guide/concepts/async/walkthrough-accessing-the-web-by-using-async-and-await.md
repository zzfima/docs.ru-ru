---
title: "Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: get-started-article
ms.assetid: c95d8d71-5a98-4bf0-aaf4-45fed2ebbacd
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 533cb4b342e3de3eb3143b001f5a26e36e4d79b9
ms.sourcegitcommit: cec0525b2121c36198379525e69aa5388266db5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-c"></a><span data-ttu-id="bc0ba-102">Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await (C#)</span><span class="sxs-lookup"><span data-stu-id="bc0ba-102">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>
<span data-ttu-id="bc0ba-103">Возможности Async и Await упрощают создание асинхронных программ.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-103">You can write asynchronous programs more easily and intuitively by using async/await features.</span></span> <span data-ttu-id="bc0ba-104">Можно написать асинхронный код, который выглядит как синхронный, и позволить компилятору обрабатывать трудные функции обратного вызова и продолжения, которые обычно включает асинхронный код.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-104">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>  
  
 <span data-ttu-id="bc0ba-105">Дополнительные сведения о возможности Async см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](../../../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="bc0ba-105">For more information about the Async feature, see [Asynchronous Programming with async and await (C#)](../../../../csharp/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="bc0ba-106">Это пошаговое руководство начинается с создания синхронного приложения Windows Presentation Foundation (WPF), которое суммирует число байтов в списке веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-106">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="bc0ba-107">Затем в рамках руководства приложение преобразуется в асинхронное решение с помощью новых возможностей.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-107">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>  
  
 <span data-ttu-id="bc0ba-108">Если вы не хотите создавать приложение самостоятельно, можно скачать [Пример асинхронности. Пошаговое руководство по доступу к Интернету (C# и Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span><span class="sxs-lookup"><span data-stu-id="bc0ba-108">If you don't want to build the applications yourself, you can download [Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>  
  
 <span data-ttu-id="bc0ba-109">В этом пошаговом руководстве выполняются следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-109">In this walkthrough, you complete the following tasks:</span></span>  
  
-   [<span data-ttu-id="bc0ba-110">Создание приложения WPF</span><span class="sxs-lookup"><span data-stu-id="bc0ba-110">To create a WPF application</span></span>](#CreateWPFApp)  
  
-   [<span data-ttu-id="bc0ba-111">Разработка простого окна MainWindow WPF</span><span class="sxs-lookup"><span data-stu-id="bc0ba-111">To design a simple WPF MainWindow</span></span>](#MainWindow)  
  
-   [<span data-ttu-id="bc0ba-112">Добавление ссылки</span><span class="sxs-lookup"><span data-stu-id="bc0ba-112">To add a reference</span></span>](#AddRef)  
  
-   [<span data-ttu-id="bc0ba-113">Добавление необходимых директив using</span><span class="sxs-lookup"><span data-stu-id="bc0ba-113">To add necessary using directives</span></span>](#usingDir)  
  
-   [<span data-ttu-id="bc0ba-114">Создание синхронного приложения</span><span class="sxs-lookup"><span data-stu-id="bc0ba-114">To create a synchronous application</span></span>](#synchronous)  
  
-   [<span data-ttu-id="bc0ba-115">Тестирование синхронного решения</span><span class="sxs-lookup"><span data-stu-id="bc0ba-115">To test the synchronous solution</span></span>](#testSynch)  
  
-   [<span data-ttu-id="bc0ba-116">Преобразование GetURLContents в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="bc0ba-116">To convert GetURLContents to an asynchronous method</span></span>](#GetURLContents)  
  
-   [<span data-ttu-id="bc0ba-117">Преобразование SumPageSizes в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="bc0ba-117">To convert SumPageSizes to an asynchronous method</span></span>](#SumPageSizes)  
  
-   [<span data-ttu-id="bc0ba-118">Преобразование startButton_Click в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="bc0ba-118">To convert startButton_Click to an asynchronous method</span></span>](#startButton)  
  
-   [<span data-ttu-id="bc0ba-119">Тестирование асинхронного решения</span><span class="sxs-lookup"><span data-stu-id="bc0ba-119">To test the asynchronous solution</span></span>](#testAsynch)  
  
-   [<span data-ttu-id="bc0ba-120">Замена метода GetURLContentsAsync методом .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bc0ba-120">To replace method GetURLContentsAsync with a .NET Framework method</span></span>](#GetURLContentsAsync)  
  
-   [<span data-ttu-id="bc0ba-121">Пример</span><span class="sxs-lookup"><span data-stu-id="bc0ba-121">Example</span></span>](#BKMK_CompleteCodeExamples)  
  
> [!NOTE]
>  <span data-ttu-id="bc0ba-122">Для выполнения примеров необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-122">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
###  <a name="CreateWPFApp"></a> <span data-ttu-id="bc0ba-123">Создание приложения WPF</span><span class="sxs-lookup"><span data-stu-id="bc0ba-123">To create a WPF application</span></span>  
  
1.  <span data-ttu-id="bc0ba-124">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-124">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="bc0ba-125">В строке меню выберите **Файл**, **Создать**, **Проект**.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-125">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="bc0ba-126">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="bc0ba-126">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="bc0ba-127">В области **Установленные шаблоны** выберите "Visual C#", а затем в списке типов проектов выберите **Приложение WPF**.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-127">In the **Installed Templates** pane, choose Visual C#, and then choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="bc0ba-128">В текстовом поле **Имя** введите `AsyncExampleWPF` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-128">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="bc0ba-129">В **обозревателе решений** появится новый проект.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-129">The new project appears in **Solution Explorer**.</span></span>  
  
##  <a name="BKMK_DesignWPFMainWin"></a>   
###  <a name="MainWindow"></a> <span data-ttu-id="bc0ba-130">Разработка простого окна MainWindow WPF</span><span class="sxs-lookup"><span data-stu-id="bc0ba-130">To design a simple WPF MainWindow</span></span>  
  
1.  <span data-ttu-id="bc0ba-131">В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="bc0ba-131">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
2.  <span data-ttu-id="bc0ba-132">Если окно **Панель элементов** не отображается, в меню **Вид** выберите пункт **Панель элементов**.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-132">If the **Toolbox** window isn’t visible, open the **View** menu, and then choose **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="bc0ba-133">Добавьте элементы управления **Button** и **TextBox** в окно **MainWindow**.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-133">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>  
  
4.  <span data-ttu-id="bc0ba-134">Выделите элемент управления **TextBox** и в окне **Свойства** задайте указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-134">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="bc0ba-135">Задайте для свойства **Имя** значение `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-135">Set the **Name** property to `resultsTextBox`.</span></span>  
  
    -   <span data-ttu-id="bc0ba-136">Задайте для свойства **Высота** значение 250.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-136">Set the **Height** property to 250.</span></span>  
  
    -   <span data-ttu-id="bc0ba-137">Задайте для свойства **Ширина** значение 500.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-137">Set the **Width** property to 500.</span></span>  
  
    -   <span data-ttu-id="bc0ba-138">На вкладке **Текст** укажите моноширинный шрифт, например Lucida Console или Global Monospace.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-138">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>  
  
5.  <span data-ttu-id="bc0ba-139">Выделите элемент управления **Button** и в окне **Свойства** задайте указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-139">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="bc0ba-140">Задайте для свойства **Имя** значение `startButton`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-140">Set the **Name** property to `startButton`.</span></span>  
  
    -   <span data-ttu-id="bc0ba-141">Измените значение свойства **Содержимое** с **Button** на **Start**.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-141">Change the value of the **Content** property from **Button** to **Start**.</span></span>  
  
6.  <span data-ttu-id="bc0ba-142">Поместите текстовое поле и кнопку так, чтобы оба элемента управления отображались в окне **MainWindow**.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-142">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>  
  
     <span data-ttu-id="bc0ba-143">Дополнительные сведения о конструкторе XAML WPF см. в разделе [Создание пользовательского интерфейса с помощью конструктора XAML](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="bc0ba-143">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>  
  
##  <a name="BKMK_AddReference"></a>   
###  <a name="AddRef"></a> <span data-ttu-id="bc0ba-144">Добавление ссылки</span><span class="sxs-lookup"><span data-stu-id="bc0ba-144">To add a reference</span></span>  
  
1.  <span data-ttu-id="bc0ba-145">В **обозревателе решений** выделите имя проекта.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-145">In **Solution Explorer**, highlight your project's name.</span></span>  
  
2.  <span data-ttu-id="bc0ba-146">В строке меню выберите **Проект**, **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-146">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="bc0ba-147">Откроется диалоговое окно **Диспетчер ссылок**.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-147">The **Reference Manager** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="bc0ba-148">Вверху диалогового окна убедитесь в том, что проект предназначен для платформы .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-148">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>  
  
4.  <span data-ttu-id="bc0ba-149">В области **Сборки** выберите **Платформа**, если этот вариант еще не выбран.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-149">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>  
  
5.  <span data-ttu-id="bc0ba-150">В списке имен установите флажок **System.Net.Http**.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-150">In the list of names, select the **System.Net.Http** check box.</span></span>  
  
6.  <span data-ttu-id="bc0ba-151">Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-151">Choose the **OK** button to close the dialog box.</span></span>  
  
##  <a name="BKMK_AddStatesandDirs"></a>   
###  <a name="usingDir"></a> <span data-ttu-id="bc0ba-152">Добавление необходимых директив using</span><span class="sxs-lookup"><span data-stu-id="bc0ba-152">To add necessary using directives</span></span>  
  
1.  <span data-ttu-id="bc0ba-153">В **обозревателе решений** откройте контекстное меню для MainWindow.xaml.cs и выберите пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-153">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="bc0ba-154">В начало файла с кодом добавьте указанные ниже директивы `using`, если они отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-154">Add the following `using` directives at the top of the code file if they’re not already present.</span></span>  
  
    ```csharp  
    using System.Net.Http;  
    using System.Net;  
    using System.IO;  
    ```  
  
##  <a name="BKMK_CreatSynchApp"></a>   
###  <a name="synchronous"></a> <span data-ttu-id="bc0ba-155">Создание синхронного приложения</span><span class="sxs-lookup"><span data-stu-id="bc0ba-155">To create a synchronous application</span></span>  
  
1.  <span data-ttu-id="bc0ba-156">В окне конструктора для MainWindow.xaml дважды щелкните кнопку **Start**, чтобы создать обработчик событий `startButton_Click` в файле MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-156">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>  
  
2.  <span data-ttu-id="bc0ba-157">В файле MainWindow.xaml.cs скопируйте следующий код в тело `startButton_Click`:</span><span class="sxs-lookup"><span data-stu-id="bc0ba-157">In MainWindow.xaml.cs, copy the following code into the body of `startButton_Click`:</span></span>  
  
    ```csharp  
    resultsTextBox.Clear();  
    SumPageSizes();  
    resultsTextBox.Text += "\r\nControl returned to startButton_Click.";  
    ```  
  
     <span data-ttu-id="bc0ba-158">Код вызывает метод, который управляет приложением `SumPageSizes` и выводит на экран сообщение, когда элемент управления возвращается к `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-158">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>  
  
3.  <span data-ttu-id="bc0ba-159">Код для синхронного решения содержит следующие четыре метода:</span><span class="sxs-lookup"><span data-stu-id="bc0ba-159">The code for the synchronous solution contains the following four methods:</span></span>  
  
    -   <span data-ttu-id="bc0ba-160">`SumPageSizes`, который получает список URL-адресов веб-страниц из `SetUpURLList`, а затем вызывает метод `GetURLContents` и `DisplayResults` для обработки каждого URL-адреса;</span><span class="sxs-lookup"><span data-stu-id="bc0ba-160">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>  
  
    -   <span data-ttu-id="bc0ba-161">`SetUpURLList`, который создает и возвращает список веб-адресов;</span><span class="sxs-lookup"><span data-stu-id="bc0ba-161">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>  
  
    -   <span data-ttu-id="bc0ba-162">`GetURLContents`, который загружает содержимое каждого веб-сайта и возвращает содержимое в виде массива байтов;</span><span class="sxs-lookup"><span data-stu-id="bc0ba-162">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>  
  
    -   <span data-ttu-id="bc0ba-163">`DisplayResults`, который показывает число байтов в массиве байтов для каждого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-163">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>  
  
     <span data-ttu-id="bc0ba-164">Скопируйте следующие четыре метода, а затем вставьте их в обработчик событий `startButton_Click` в файле MainWindow.xaml.cs:</span><span class="sxs-lookup"><span data-stu-id="bc0ba-164">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.cs:</span></span>  
  
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
        resultsTextBox.Text +=   
            string.Format("\r\n\r\nTotal bytes returned:  {0}\r\n", total);  
    }  
  
    private List<string> SetUpURLList()  
    {  
        var urls = new List<string>   
        {   
            "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
            "http://msdn.microsoft.com",  
            "http://msdn.microsoft.com/library/hh290136.aspx",  
            "http://msdn.microsoft.com/library/ee256749.aspx",  
            "http://msdn.microsoft.com/library/hh290138.aspx",  
            "http://msdn.microsoft.com/library/hh290140.aspx",  
            "http://msdn.microsoft.com/library/dd470362.aspx",  
            "http://msdn.microsoft.com/library/aa578028.aspx",  
            "http://msdn.microsoft.com/library/ms404677.aspx",  
            "http://msdn.microsoft.com/library/ff730837.aspx"  
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
        // Strip off the "http://".  
        var displayURL = url.Replace("http://", "");  
        resultsTextBox.Text += string.Format("\n{0,-58} {1,8}", displayURL, bytes);  
    }  
    ```  
  
##  <a name="BKMK_TestSynchSol"></a>   
###  <a name="testSynch"></a> <span data-ttu-id="bc0ba-165">Тестирование синхронного решения</span><span class="sxs-lookup"><span data-stu-id="bc0ba-165">To test the synchronous solution</span></span>  
  
1.  <span data-ttu-id="bc0ba-166">Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .</span><span class="sxs-lookup"><span data-stu-id="bc0ba-166">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="bc0ba-167">Программа должна выдать результаты, похожие на следующий список.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-167">Output that resembles the following list should appear.</span></span>  
  
    ```  
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
  
     <span data-ttu-id="bc0ba-168">Обратите внимание, что вывод результатов на экран занимает несколько секунд.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-168">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="bc0ba-169">В течение этого времени поток пользовательского интерфейса заблокирован, пока он ожидает загрузку запрошенных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-169">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="bc0ba-170">Соответственно, после нажатия кнопки **Start** окно нельзя перемещать, разворачивать, сворачивать или даже закрывать.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-170">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="bc0ba-171">Эти действия будут завершаться сбоем, пока не появятся результаты подсчета.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-171">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="bc0ba-172">Если веб-сайт не отвечает, вы не можете определить, на каком сайте произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-172">If a website isn’t responding, you have no indication of which site failed.</span></span> <span data-ttu-id="bc0ba-173">Трудно даже остановить ожидание и закрыть программу.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-173">It is difficult even to stop waiting and close the program.</span></span>  
  
##  <a name="BKMK_ConvertGtBtArr"></a>   
###  <a name="GetURLContents"></a> <span data-ttu-id="bc0ba-174">Преобразование GetURLContents в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="bc0ba-174">To convert GetURLContents to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="bc0ba-175">Чтобы преобразовать синхронное решение в асинхронное, лучше всего начать с метода `GetURLContents`, поскольку вызовы метода <xref:System.Net.HttpWebRequest> <xref:System.Net.HttpWebRequest.GetResponse%2A> и метода <xref:System.IO.Stream> <xref:System.IO.Stream.CopyTo%2A> выполняются, когда приложение подключается к Интернету.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-175">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest> method <xref:System.Net.HttpWebRequest.GetResponse%2A> and to the <xref:System.IO.Stream> method <xref:System.IO.Stream.CopyTo%2A> are where the application accesses the web.</span></span> <span data-ttu-id="bc0ba-176">Платформа .NET Framework упрощает преобразование путем предоставления асинхронных версий этих методов.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-176">The .NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>  
  
     <span data-ttu-id="bc0ba-177">Дополнительные сведения о методах, которые используются в `GetURLContents`, см. в разделе <xref:System.Net.WebRequest>.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-177">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc0ba-178">По мере выполнения шагов в этом пошаговом руководстве возникают различные ошибки компилятора.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-178">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="bc0ba-179">Их можно игнорировать и продолжить процедуры пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-179">You can ignore them and continue with the walkthrough.</span></span>  
  
     <span data-ttu-id="bc0ba-180">Измените метод, который вызывается в третьей строке `GetURLContents` из `GetResponse`, асинхронным методом <xref:System.Net.WebRequest.GetResponseAsync%2A>, основанным на задачах.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-180">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>  
  
    ```csharp  
    using (WebResponse response = webReq.GetResponseAsync())  
    ```  
  
2.  <span data-ttu-id="bc0ba-181">`GetResponseAsync` возвращает значение типа <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-181">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="bc0ba-182">В этом случае *переменная, возвращаемая задачей*, `TResult`, имеет тип <xref:System.Net.WebResponse>.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-182">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="bc0ba-183">Задача является обещанием создать фактический объект `WebResponse` после загрузки запрошенных данных и выполнения задачи до завершения.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-183">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>  
  
     <span data-ttu-id="bc0ba-184">Для получения значения `WebResponse` из задачи примените оператор [await](../../../../csharp/language-reference/keywords/await.md) для вызова метода `GetResponseAsync`, как показано в приведенном ниже примере кода.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-184">To retrieve the `WebResponse` value from the task, apply an [await](../../../../csharp/language-reference/keywords/await.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>  
  
    ```csharp  
    using (WebResponse response = await webReq.GetResponseAsync())  
    ```  
  
     <span data-ttu-id="bc0ba-185">Оператор `await` приостанавливает выполнение текущего метода `GetURLContents`, пока не будет завершена ожидаемая задача.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-185">The `await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="bc0ba-186">На это время управление возвращается вызывающему объекту текущего метода.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-186">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="bc0ba-187">В этом примере текущим методом является `GetURLContents`, а вызывающим объектом — `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-187">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="bc0ba-188">После завершения задачи создается обещанный объект `WebResponse` в качестве значения ожидаемой задачи, который присваивается переменной `response`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-188">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>  
  
     <span data-ttu-id="bc0ba-189">Предыдущий оператор можно разделить на следующие два оператора для уточнения выполняемых операций.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-189">The previous statement can be separated into the following two statements to clarify what happens.</span></span>  
  
    ```csharp  
    //Task<WebResponse> responseTask = webReq.GetResponseAsync();  
    //using (WebResponse response = await responseTask)  
    ```  
  
     <span data-ttu-id="bc0ba-190">Вызов `webReq.GetResponseAsync` возвращает `Task(Of WebResponse)` или `Task<WebResponse>`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-190">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="bc0ba-191">Затем оператор await применяется к задаче для получения значения `WebResponse`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-191">Then an await operator is applied to the task to retrieve the `WebResponse` value.</span></span>  
  
     <span data-ttu-id="bc0ba-192">Если асинхронному методу нужно выполнить определенную работу, не связанную с завершением конкретной задачи, он может проделать это между выполнением этих двух операторов: после вызова метода async и перед применением оператора `await`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-192">If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the `await` operator is applied.</span></span> <span data-ttu-id="bc0ba-193">Примеры см. в статьях [Практическое руководство. Параллельное выполнение нескольких веб-запросов с использованием Async и Await (C#)](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) и [Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="bc0ba-193">For examples, see [How to: Make Multiple Web Requests in Parallel by Using async and await (C#)](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
3.  <span data-ttu-id="bc0ba-194">Из-за добавления оператора `await` в предыдущем шаге возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-194">Because you added the `await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="bc0ba-195">Этот оператор можно использовать только в методах, помеченных модификатором [async](../../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="bc0ba-195">The operator can be used only in methods that are marked with the [async](../../../../csharp/language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="bc0ba-196">Пропустите ошибку, повторяя действия по замене вызова `CopyTo` вызовом метода `CopyToAsync`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-196">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>  
  
    -   <span data-ttu-id="bc0ba-197">Измените имя метода, вызывающего <xref:System.IO.Stream.CopyToAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-197">Change the name of the method that’s called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>  
  
    -   <span data-ttu-id="bc0ba-198">Метод `CopyTo` или `CopyToAsync` копирует байты в свой аргумент `content` и не возвращает осмысленное значение.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-198">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn’t return a meaningful value.</span></span> <span data-ttu-id="bc0ba-199">В синхронной версии вызов метода `CopyTo` — это просто оператор, который не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-199">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="bc0ba-200">Асинхронная версия — `CopyToAsync` — возвращает <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-200">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="bc0ba-201">Задача работает как Task(void) и позволяет ожидать метод.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-201">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="bc0ba-202">Примените `Await` или `await` к вызову `CopyToAsync`, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-202">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>  
  
        ```csharp  
        await responseStream.CopyToAsync(content);  
        ```  
  
         <span data-ttu-id="bc0ba-203">Предыдущий оператор сокращает две следующие строки кода.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-203">The previous statement abbreviates the following two lines of code.</span></span>  
  
        ```csharp  
        // CopyToAsync returns a Task, not a Task<T>.  
        //Task copyTask = responseStream.CopyToAsync(content);  
  
        // When copyTask is completed, content contains a copy of  
        // responseStream.  
        //await copyTask;  
        ```  
  
4.  <span data-ttu-id="bc0ba-204">Все, что остается сделать в `GetURLContents`, — это изменить подпись метода.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-204">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="bc0ba-205">Оператор `await` можно использовать только в методах, помеченных модификатором [async](../../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="bc0ba-205">You can use the `await` operator only in methods that are marked with the [async](../../../../csharp/language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="bc0ba-206">Добавьте модификатор, чтобы пометить метод как *асинхронный*, как показано в приведенном ниже примере кода.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-206">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>  
  
    ```csharp  
    private async byte[] GetURLContents(string url)  
    ```  
  
5.  <span data-ttu-id="bc0ba-207">Возвращаемым типом асинхронного метода может быть только <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> или `void` в C#.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-207">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, or `void` in C#.</span></span> <span data-ttu-id="bc0ba-208">Как правило, тип возвращаемого значения `void` используется только в асинхронном обработчике событий, где `void` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-208">Typically, a return type of `void` is used only in an async event handler, where `void` is required.</span></span> <span data-ttu-id="bc0ba-209">В других случаях используется `Task(T)`, если завершенный метод имеет оператор [return](../../../../csharp/language-reference/keywords/return.md), возвращающий значение типа T, или `Task`, если завершенный метод не возвращает осмысленное значение.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-209">In other cases, you use `Task(T)` if the completed method has a [return](../../../../csharp/language-reference/keywords/return.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.</span></span> <span data-ttu-id="bc0ba-210">Можно представить тип возвращаемого значения `Task` как Task(void).</span><span class="sxs-lookup"><span data-stu-id="bc0ba-210">You can think of the `Task` return type as meaning "Task(void)."</span></span>  
  
     <span data-ttu-id="bc0ba-211">Дополнительные сведения см. в разделе [Асинхронные типы возвращаемых значений (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="bc0ba-211">For more information, see [Async Return Types (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
     <span data-ttu-id="bc0ba-212">Метод `GetURLContents` имеет оператор return, который возвращает массив байтов.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-212">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="bc0ba-213">Таким образом, тип возвращаемого значения асинхронной версии — Task(T), где T — массив байтов.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-213">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="bc0ba-214">Внесите следующие изменения в подпись метода.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-214">Make the following changes in the method signature:</span></span>  
  
    -   <span data-ttu-id="bc0ba-215">Измените тип возвращаемого значения на `Task<byte[]>`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-215">Change the return type to `Task<byte[]>`.</span></span>  
  
    -   <span data-ttu-id="bc0ba-216">По соглашению об именовании асинхронные методы имеют имена, заканчивающиеся на Async, поэтому переименуйте метод в `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-216">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>  
  
     <span data-ttu-id="bc0ba-217">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-217">The following code shows these changes.</span></span>  
  
    ```csharp  
    private async Task<byte[]> GetURLContentsAsync(string url)  
    ```  
  
     <span data-ttu-id="bc0ba-218">После внесения этих изменений преобразование `GetURLContents` в асинхронный метод завершено.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-218">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>  
  
##  <a name="BKMK_ConvertSumPagSzs"></a>   
###  <a name="SumPageSizes"></a> <span data-ttu-id="bc0ba-219">Преобразование SumPageSizes в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="bc0ba-219">To convert SumPageSizes to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="bc0ba-220">Повторите шаги из предыдущей процедуры для `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-220">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="bc0ba-221">Во-первых, преобразуйте вызов метода `GetURLContents` в вызов асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-221">First, change the call to `GetURLContents` to an asynchronous call.</span></span>  
  
    -   <span data-ttu-id="bc0ba-222">Измените имя вызываемого метода с `GetURLContents` на `GetURLContentsAsync`, если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-222">Change the name of the method that’s called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>  
  
    -   <span data-ttu-id="bc0ba-223">Примените оператор `await` к задаче, возвращаемой методом `GetURLContentsAsync`, для получения значения байтового массива.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-223">Apply `await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>  
  
     <span data-ttu-id="bc0ba-224">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-224">The following code shows these changes.</span></span>  
  
    ```csharp  
    byte[] urlContents = await GetURLContentsAsync(url);  
    ```  
  
     <span data-ttu-id="bc0ba-225">Предыдущее назначение сокращает две следующие строки кода.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-225">The previous assignment abbreviates the following two lines of code.</span></span>  
  
    ```csharp  
    // GetURLContentsAsync returns a Task<T>. At completion, the task  
    // produces a byte array.  
    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);  
    //byte[] urlContents = await getContentsTask;  
    ```  
  
2.  <span data-ttu-id="bc0ba-226">Внесите следующие изменения в подпись метода.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-226">Make the following changes in the method's signature:</span></span>  
  
    -   <span data-ttu-id="bc0ba-227">Пометьте метод модификатором `async`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-227">Mark the method with the `async` modifier.</span></span>  
  
    -   <span data-ttu-id="bc0ba-228">Добавьте в имя метода Async.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-228">Add "Async" to the method name.</span></span>  
  
    -   <span data-ttu-id="bc0ba-229">В этот раз нет возвращаемой переменной задачи T, поскольку `SumPageSizesAsync` не возвращает значение для T. (В этом методе нет оператора `return`.) Тем не менее метод должен возвращать `Task`, чтобы для него можно было задать ожидание.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-229">There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="bc0ba-230">Поэтому измените тип возвращаемого значения метода с `void` на `Task`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-230">Therefore, change the return type of the method from `void` to `Task`.</span></span>  
  
     <span data-ttu-id="bc0ba-231">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-231">The following code shows these changes.</span></span>  
  
    ```csharp  
    private async Task SumPageSizesAsync()  
    ```  
  
     <span data-ttu-id="bc0ba-232">Преобразование `SumPageSizes` в `SumPageSizesAsync` завершено.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-232">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>  
  
##  <a name="BKMK_Cnvrtbttn1"></a>   
###  <a name="startButton"></a> <span data-ttu-id="bc0ba-233">Преобразование startButton_Click в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="bc0ba-233">To convert startButton_Click to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="bc0ba-234">В обработчике событий измените имя вызываемого метода с `SumPageSizes` на `SumPageSizesAsync`, если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-234">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven’t already done so.</span></span>  
  
2.  <span data-ttu-id="bc0ba-235">Поскольку `SumPageSizesAsync` является асинхронным методом, измените код в обработчике событий для ожидания результата.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-235">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>  
  
     <span data-ttu-id="bc0ba-236">Вызов `SumPageSizesAsync` отражает вызов `CopyToAsync` в `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-236">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="bc0ba-237">Вызов возвращает `Task`, а не `Task(T)`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-237">The call returns a `Task`, not a `Task(T)`.</span></span>  
  
     <span data-ttu-id="bc0ba-238">Как и в предыдущих процедурах, вызов можно преобразовать, используя один или два оператора.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-238">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="bc0ba-239">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-239">The following code shows these changes.</span></span>  
  
    ```csharp  
    // One-step async call.  
    await SumPageSizesAsync();  
  
    // Two-step async call.  
    //Task sumTask = SumPageSizesAsync();  
    //await sumTask;  
    ```  
  
3.  <span data-ttu-id="bc0ba-240">Чтобы предотвратить случайное повторное введение операции, добавьте следующий оператор в верхней части `startButton_Click`, чтобы отключить кнопку **Start**.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-240">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>  
  
    ```csharp  
    // Disable the button until the operation is complete.  
    startButton.IsEnabled = false;  
    ```  
  
     <span data-ttu-id="bc0ba-241">Можно снова включить кнопку в конце обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-241">You can reenable the button at the end of the event handler.</span></span>  
  
    ```csharp  
    // Reenable the button in case you want to run the operation again.  
    startButton.IsEnabled = true;  
    ```  
  
     <span data-ttu-id="bc0ba-242">Дополнительные сведения о повторном входе см. в разделе [Обработка повторного входа в асинхронных приложениях (C#)](../../../../csharp/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span><span class="sxs-lookup"><span data-stu-id="bc0ba-242">For more information about reentrancy, see [Handling Reentrancy in Async Apps (C#)](../../../../csharp/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span></span>  
  
4.  <span data-ttu-id="bc0ba-243">Наконец, добавьте модификатор `async` в объявление, чтобы обработчик событий мог ожидать `SumPagSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-243">Finally, add the `async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>  
  
    ```csharp  
    private async void startButton_Click(object sender, RoutedEventArgs e)  
    ```  
  
     <span data-ttu-id="bc0ba-244">Как правило, имена обработчиков событий не изменяются.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-244">Typically, the names of event handlers aren’t changed.</span></span> <span data-ttu-id="bc0ba-245">Тип возвращаемого значения не изменяется на `Task`, так как обработчики событий должны возвращать `void`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-245">The return type isn’t changed to `Task` because event handlers must return `void`.</span></span>  
  
     <span data-ttu-id="bc0ba-246">Преобразование проекта из синхронного в асинхронный завершено.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-246">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>  
  
##  <a name="BKMK_testAsynchSolution"></a>   
###  <a name="testAsynch"></a> <span data-ttu-id="bc0ba-247">Тестирование асинхронного решения</span><span class="sxs-lookup"><span data-stu-id="bc0ba-247">To test the asynchronous solution</span></span>  
  
1.  <span data-ttu-id="bc0ba-248">Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .</span><span class="sxs-lookup"><span data-stu-id="bc0ba-248">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
2.  <span data-ttu-id="bc0ba-249">Появившиеся результаты должны напоминать результаты синхронного решения.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-249">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="bc0ba-250">Однако имеются следующие различия.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-250">However, notice the following differences.</span></span>  
  
    -   <span data-ttu-id="bc0ba-251">Все результаты не отображаются одновременно после завершения обработки.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-251">The results don’t all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="bc0ba-252">Например, обе программы содержат строку в `startButton_Click`, которая очищает текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-252">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="bc0ba-253">Ее цель состоит в том, чтобы очистить текстовое поле между запусками при нажатии кнопки **Start** во второй раз после появления одного набора результатов.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-253">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="bc0ba-254">В синхронной версии текстовое поле очищается перед отображением данных во второй раз, после завершения загрузки и высвобождения потока пользовательского интерфейса для выполнения других операций.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-254">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="bc0ba-255">В асинхронной версии текстовое поле очищается сразу же после нажатия кнопки **Start**.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-255">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>  
  
    -   <span data-ttu-id="bc0ba-256">И что самое главное, поток пользовательского интерфейса не блокируется во время загрузки.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-256">Most importantly, the UI thread isn’t blocked during the downloads.</span></span> <span data-ttu-id="bc0ba-257">Можно перемещать окно или изменять его размер во время загрузки, подсчета и отображения веб-ресурсов.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-257">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="bc0ba-258">Если один из веб-сайтов работает медленно или не отвечает, можно отменить операцию, нажав кнопку **Закрыть** (красный крестик в правом верхнем углу окна).</span><span class="sxs-lookup"><span data-stu-id="bc0ba-258">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>  
  
##  <a name="BKMK_ReplaceGetByteArrayAsync"></a>   
###  <a name="GetURLContentsAsync"></a> <span data-ttu-id="bc0ba-259">Замена GetURLContentsAsync методом .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bc0ba-259">To replace method GetURLContentsAsync with a .NET Framework method</span></span>  
  
1.  <span data-ttu-id="bc0ba-260">Платформа .NET Framework 4.5 предоставляет много асинхронных методов, которые вы можете использовать.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-260">The .NET Framework 4.5 provides many async methods that you can use.</span></span> <span data-ttu-id="bc0ba-261">Один из них, метод <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29> <xref:System.Net.Http.HttpClient>, выполняет именно те операции, которые требуются для данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-261">One of them, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, does just what you need for this walkthrough.</span></span> <span data-ttu-id="bc0ba-262">Его можно использовать вместо метода `GetURLContentsAsync`, созданного в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-262">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>  
  
     <span data-ttu-id="bc0ba-263">Первым шагом является создание объекта `HttpClient` в методе `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-263">The first step is to create an `HttpClient` object in method `SumPageSizesAsync`.</span></span> <span data-ttu-id="bc0ba-264">Добавьте следующее объявление в начале метода.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-264">Add the following declaration at the start of the method.</span></span>  
  
    ```csharp  
    // Declare an HttpClient object and increase the buffer size. The  
    // default buffer size is 65,536.  
    HttpClient client =  
        new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
    ```  
  
2.  <span data-ttu-id="bc0ba-265">В `SumPageSizesAsync,` замените вызов метода `GetURLContentsAsync` вызовом метода `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-265">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>  
  
    ```csharp  
    byte[] urlContents = await client.GetByteArrayAsync(url);  
    ```  
  
3.  <span data-ttu-id="bc0ba-266">Удалите или прокомментируйте метод `GetURLContentsAsync`, который вы написали.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-266">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>  
  
4.  <span data-ttu-id="bc0ba-267">Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .</span><span class="sxs-lookup"><span data-stu-id="bc0ba-267">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="bc0ba-268">Поведение этой версии проекта должно соответствовать поведению, которое описывается в процедуре "Тестирование асинхронного решения"; при этом с вашей стороны требуется даже меньше усилий.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-268">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>  
  
##  <a name="BKMK_CompleteCodeExamples"></a> <span data-ttu-id="bc0ba-269">Пример</span><span class="sxs-lookup"><span data-stu-id="bc0ba-269">Example</span></span>  
 <span data-ttu-id="bc0ba-270">Следующий код содержит полный пример преобразования решения из синхронного в асинхронное с помощью написанного вами асинхронного метода `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-270">The following code contains the full example of the conversion from a synchronous to an asynchronous solution by using the asynchronous `GetURLContentsAsync` method that you wrote.</span></span> <span data-ttu-id="bc0ba-271">Обратите внимание, что он очень напоминает исходное синхронное решение.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-271">Notice that it strongly resembles the original, synchronous solution.</span></span>  
  
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
                string.Format("\r\n\r\nTotal bytes returned:  {0}\r\n", total);  
        }  
  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>   
            {   
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
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
            // Strip off the "http://".  
            var displayURL = url.Replace("http://", "");  
            resultsTextBox.Text += string.Format("\n{0,-58} {1,8}", displayURL, bytes);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="bc0ba-272">Следующий код содержит полный пример решения, использующего метод `HttpClient`, `GetByteArrayAsync`.</span><span class="sxs-lookup"><span data-stu-id="bc0ba-272">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>  
  
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
                string.Format("\r\n\r\nTotal bytes returned:  {0}\r\n", total);  
        }  
  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>   
            {   
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            };  
            return urls;  
        }  
  
        private void DisplayResults(string url, byte[] content)  
        {  
            // Display the length of each website. The string format   
            // is designed to be used with a monospaced font, such as  
            // Lucida Console or Global Monospace.  
            var bytes = content.Length;  
            // Strip off the "http://".  
            var displayURL = url.Replace("http://", "");  
            resultsTextBox.Text += string.Format("\n{0,-58} {1,8}", displayURL, bytes);  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc0ba-273">См. также</span><span class="sxs-lookup"><span data-stu-id="bc0ba-273">See Also</span></span>  
 [<span data-ttu-id="bc0ba-274">Пример асинхронности. Пошаговое руководство "Доступ к сети" (C# и Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc0ba-274">Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)</span></span>](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)  
 [<span data-ttu-id="bc0ba-275">async</span><span class="sxs-lookup"><span data-stu-id="bc0ba-275">async</span></span>](../../../../csharp/language-reference/keywords/async.md)  
 [<span data-ttu-id="bc0ba-276">await</span><span class="sxs-lookup"><span data-stu-id="bc0ba-276">await</span></span>](../../../../csharp/language-reference/keywords/await.md)  
 [<span data-ttu-id="bc0ba-277">Асинхронное программирование с использованием ключевых слов async и await (C#)</span><span class="sxs-lookup"><span data-stu-id="bc0ba-277">Asynchronous Programming with async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/index.md)  
 <span data-ttu-id="bc0ba-278">[Async Return Types (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md) (Типы возвращаемых значений асинхронных операций в C#)</span><span class="sxs-lookup"><span data-stu-id="bc0ba-278">[Async Return Types (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md)</span></span>  
 [<span data-ttu-id="bc0ba-279">Асинхронное программирование на основе задач (TAP)</span><span class="sxs-lookup"><span data-stu-id="bc0ba-279">Task-based Asynchronous Programming (TAP)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=19957)  
 <span data-ttu-id="bc0ba-280">[How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) (Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll в C#)</span><span class="sxs-lookup"><span data-stu-id="bc0ba-280">[How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)</span></span>  
 <span data-ttu-id="bc0ba-281">[How to: Make Multiple Web Requests in Parallel by Using async and await (C#)](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) (Практическое руководство. Параллельное выполнение нескольких веб-запросов в C# с использованием async и await)</span><span class="sxs-lookup"><span data-stu-id="bc0ba-281">[How to: Make Multiple Web Requests in Parallel by Using async and await (C#)](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)</span></span>
