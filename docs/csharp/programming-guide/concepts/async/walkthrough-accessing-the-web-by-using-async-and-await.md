---
title: "Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: get-started-article
dev_langs:
- CSharp
ms.assetid: c95d8d71-5a98-4bf0-aaf4-45fed2ebbacd
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7c03cad060e2ba459277c28f929df88be70e4044
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-c"></a><span data-ttu-id="1a9bf-102">Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await (C#)</span><span class="sxs-lookup"><span data-stu-id="1a9bf-102">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>
<span data-ttu-id="1a9bf-103">Возможности Async и Await упрощают создание асинхронных программ.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-103">You can write asynchronous programs more easily and intuitively by using async/await features.</span></span> <span data-ttu-id="1a9bf-104">Можно написать асинхронный код, который выглядит как синхронный, и позволить компилятору обрабатывать трудные функции обратного вызова и продолжения, которые обычно включает асинхронный код.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-104">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>  
  
 <span data-ttu-id="1a9bf-105">Дополнительные сведения о возможности Async см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](../../../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="1a9bf-105">For more information about the Async feature, see [Asynchronous Programming with async and await (C#)](../../../../csharp/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="1a9bf-106">Это пошаговое руководство начинается с создания синхронного приложения Windows Presentation Foundation (WPF), которое суммирует число байтов в списке веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-106">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="1a9bf-107">Затем в рамках руководства приложение преобразуется в асинхронное решение с помощью новых возможностей.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-107">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>  
  
 <span data-ttu-id="1a9bf-108">Если вы не хотите создавать приложение самостоятельно, вы можете скачать пример "Пример Async. Пошаговое руководство по доступу к интернету (C# и Visual Basic)" со страницы [примеров кода для разработчиков](http://go.microsoft.com/fwlink/?LinkId=255191).</span><span class="sxs-lookup"><span data-stu-id="1a9bf-108">If you don't want to build the applications yourself, you can download "Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)" from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191).</span></span>  
  
 <span data-ttu-id="1a9bf-109">В этом пошаговом руководстве выполняются следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-109">In this walkthrough, you complete the following tasks:</span></span>  
  
-   [<span data-ttu-id="1a9bf-110">Создание приложения WPF</span><span class="sxs-lookup"><span data-stu-id="1a9bf-110">To create a WPF application</span></span>](#CreateWPFApp)  
  
-   [<span data-ttu-id="1a9bf-111">Разработка простого окна MainWindow WPF</span><span class="sxs-lookup"><span data-stu-id="1a9bf-111">To design a simple WPF MainWindow</span></span>](#MainWindow)  
  
-   [<span data-ttu-id="1a9bf-112">Добавление ссылки</span><span class="sxs-lookup"><span data-stu-id="1a9bf-112">To add a reference</span></span>](#AddRef)  
  
-   [<span data-ttu-id="1a9bf-113">Добавление необходимых директив using</span><span class="sxs-lookup"><span data-stu-id="1a9bf-113">To add necessary using directives</span></span>](#usingDir)  
  
-   [<span data-ttu-id="1a9bf-114">Создание синхронного приложения</span><span class="sxs-lookup"><span data-stu-id="1a9bf-114">To create a synchronous application</span></span>](#synchronous)  
  
-   [<span data-ttu-id="1a9bf-115">Тестирование синхронного решения</span><span class="sxs-lookup"><span data-stu-id="1a9bf-115">To test the synchronous solution</span></span>](#testSynch)  
  
-   [<span data-ttu-id="1a9bf-116">Преобразование GetURLContents в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="1a9bf-116">To convert GetURLContents to an asynchronous method</span></span>](#GetURLContents)  
  
-   [<span data-ttu-id="1a9bf-117">Преобразование SumPageSizes в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="1a9bf-117">To convert SumPageSizes to an asynchronous method</span></span>](#SumPageSizes)  
  
-   [<span data-ttu-id="1a9bf-118">Преобразование startButton_Click в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="1a9bf-118">To convert startButton_Click to an asynchronous method</span></span>](#startButton)  
  
-   [<span data-ttu-id="1a9bf-119">Тестирование асинхронного решения</span><span class="sxs-lookup"><span data-stu-id="1a9bf-119">To test the asynchronous solution</span></span>](#testAsynch)  
  
-   [<span data-ttu-id="1a9bf-120">Замена метода GetURLContentsAsync методом .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1a9bf-120">To replace method GetURLContentsAsync with a .NET Framework method</span></span>](#GetURLContentsAsync)  
  
-   [<span data-ttu-id="1a9bf-121">Пример</span><span class="sxs-lookup"><span data-stu-id="1a9bf-121">Example</span></span>](#BKMK_CompleteCodeExamples)  
  
## <a name="prerequisites"></a><span data-ttu-id="1a9bf-122">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1a9bf-122">Prerequisites</span></span>  
 <span data-ttu-id="1a9bf-123">На компьютере должна быть установлена среда Visual Studio 2012 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-123">Visual Studio 2012 or later must be installed on your computer.</span></span> <span data-ttu-id="1a9bf-124">Дополнительные сведения см. на [веб-сайте Майкрософт](http://go.microsoft.com/fwlink/?LinkId=235233).</span><span class="sxs-lookup"><span data-stu-id="1a9bf-124">For more information, see the [Microsoft website](http://go.microsoft.com/fwlink/?LinkId=235233).</span></span>  
  
###  <span data-ttu-id="1a9bf-125"><a name="CreateWPFApp"></a> Создание приложения WPF</span><span class="sxs-lookup"><span data-stu-id="1a9bf-125"><a name="CreateWPFApp"></a> To create a WPF application</span></span>  
  
1.  <span data-ttu-id="1a9bf-126">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-126">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="1a9bf-127">В строке меню выберите **Файл**, **Создать**, **Проект**.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-127">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="1a9bf-128">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="1a9bf-128">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="1a9bf-129">В области **Установленные шаблоны** выберите "Visual C#", а затем в списке типов проектов выберите **Приложение WPF**.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-129">In the **Installed Templates** pane, choose Visual C#, and then choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="1a9bf-130">В текстовом поле **Имя** введите `AsyncExampleWPF` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-130">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="1a9bf-131">В **обозревателе решений** появится новый проект.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-131">The new project appears in **Solution Explorer**.</span></span>  
  
##  <a name="BKMK_DesignWPFMainWin"></a>   
###  <span data-ttu-id="1a9bf-132"><a name="MainWindow"></a> Разработка простого окна MainWindow WPF</span><span class="sxs-lookup"><span data-stu-id="1a9bf-132"><a name="MainWindow"></a> To design a simple WPF MainWindow</span></span>  
  
1.  <span data-ttu-id="1a9bf-133">В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="1a9bf-133">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
2.  <span data-ttu-id="1a9bf-134">Если окно **Панель элементов** не отображается, в меню **Вид** выберите пункт **Панель элементов**.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-134">If the **Toolbox** window isn’t visible, open the **View** menu, and then choose **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="1a9bf-135">Добавьте элементы управления **Button** и **TextBox** в окно **MainWindow**.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-135">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>  
  
4.  <span data-ttu-id="1a9bf-136">Выделите элемент управления **TextBox** и в окне **Свойства** задайте указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-136">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="1a9bf-137">Задайте для свойства **Имя** значение `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-137">Set the **Name** property to `resultsTextBox`.</span></span>  
  
    -   <span data-ttu-id="1a9bf-138">Задайте для свойства **Высота** значение 250.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-138">Set the **Height** property to 250.</span></span>  
  
    -   <span data-ttu-id="1a9bf-139">Задайте для свойства **Ширина** значение 500.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-139">Set the **Width** property to 500.</span></span>  
  
    -   <span data-ttu-id="1a9bf-140">На вкладке **Текст** укажите моноширинный шрифт, например Lucida Console или Global Monospace.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-140">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>  
  
5.  <span data-ttu-id="1a9bf-141">Выделите элемент управления **Button** и в окне **Свойства** задайте указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-141">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="1a9bf-142">Задайте для свойства **Имя** значение `startButton`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-142">Set the **Name** property to `startButton`.</span></span>  
  
    -   <span data-ttu-id="1a9bf-143">Измените значение свойства **Содержимое** с **Button** на **Start**.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-143">Change the value of the **Content** property from **Button** to **Start**.</span></span>  
  
6.  <span data-ttu-id="1a9bf-144">Поместите текстовое поле и кнопку так, чтобы оба элемента управления отображались в окне **MainWindow**.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-144">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>  
  
     <span data-ttu-id="1a9bf-145">Дополнительные сведения о конструкторе XAML WPF см. в разделе [Создание пользовательского интерфейса с помощью конструктора XAML](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="1a9bf-145">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>  
  
##  <a name="BKMK_AddReference"></a>   
###  <span data-ttu-id="1a9bf-146"><a name="AddRef"></a> Добавление ссылки</span><span class="sxs-lookup"><span data-stu-id="1a9bf-146"><a name="AddRef"></a> To add a reference</span></span>  
  
1.  <span data-ttu-id="1a9bf-147">В **обозревателе решений** выделите имя проекта.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-147">In **Solution Explorer**, highlight your project's name.</span></span>  
  
2.  <span data-ttu-id="1a9bf-148">В строке меню выберите **Проект**, **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-148">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="1a9bf-149">Откроется диалоговое окно **Диспетчер ссылок**.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-149">The **Reference Manager** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="1a9bf-150">Вверху диалогового окна убедитесь в том, что проект предназначен для платформы .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-150">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>  
  
4.  <span data-ttu-id="1a9bf-151">В области **Сборки** выберите **Платформа**, если этот вариант еще не выбран.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-151">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>  
  
5.  <span data-ttu-id="1a9bf-152">В списке имен установите флажок **System.Net.Http**.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-152">In the list of names, select the **System.Net.Http** check box.</span></span>  
  
6.  <span data-ttu-id="1a9bf-153">Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-153">Choose the **OK** button to close the dialog box.</span></span>  
  
##  <a name="BKMK_AddStatesandDirs"></a>   
###  <span data-ttu-id="1a9bf-154"><a name="usingDir"></a> Добавление необходимых директив using</span><span class="sxs-lookup"><span data-stu-id="1a9bf-154"><a name="usingDir"></a> To add necessary using directives</span></span>  
  
1.  <span data-ttu-id="1a9bf-155">В **обозревателе решений** откройте контекстное меню для MainWindow.xaml.cs и выберите пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-155">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="1a9bf-156">В начало файла с кодом добавьте указанные ниже директивы `using`, если они отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-156">Add the following `using` directives at the top of the code file if they’re not already present.</span></span>  
  
    ```csharp  
    using System.Net.Http;  
    using System.Net;  
    using System.IO;  
    ```  
  
##  <a name="BKMK_CreatSynchApp"></a>   
###  <span data-ttu-id="1a9bf-157"><a name="synchronous"></a> Создание синхронного приложения</span><span class="sxs-lookup"><span data-stu-id="1a9bf-157"><a name="synchronous"></a> To create a synchronous application</span></span>  
  
1.  <span data-ttu-id="1a9bf-158">В окне конструктора для MainWindow.xaml дважды щелкните кнопку **Start**, чтобы создать обработчик событий `startButton_Click` в файле MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-158">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>  
  
2.  <span data-ttu-id="1a9bf-159">В файле MainWindow.xaml.cs скопируйте следующий код в тело `startButton_Click`:</span><span class="sxs-lookup"><span data-stu-id="1a9bf-159">In MainWindow.xaml.cs, copy the following code into the body of `startButton_Click`:</span></span>  
  
    ```csharp  
    resultsTextBox.Clear();  
    SumPageSizes();  
    resultsTextBox.Text += "\r\nControl returned to startButton_Click.";  
    ```  
  
     <span data-ttu-id="1a9bf-160">Код вызывает метод, который управляет приложением `SumPageSizes` и выводит на экран сообщение, когда элемент управления возвращается к `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-160">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>  
  
3.  <span data-ttu-id="1a9bf-161">Код для синхронного решения содержит следующие четыре метода:</span><span class="sxs-lookup"><span data-stu-id="1a9bf-161">The code for the synchronous solution contains the following four methods:</span></span>  
  
    -   <span data-ttu-id="1a9bf-162">`SumPageSizes`, который получает список URL-адресов веб-страниц из `SetUpURLList`, а затем вызывает метод `GetURLContents` и `DisplayResults` для обработки каждого URL-адреса;</span><span class="sxs-lookup"><span data-stu-id="1a9bf-162">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>  
  
    -   <span data-ttu-id="1a9bf-163">`SetUpURLList`, который создает и возвращает список веб-адресов;</span><span class="sxs-lookup"><span data-stu-id="1a9bf-163">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>  
  
    -   <span data-ttu-id="1a9bf-164">`GetURLContents`, который загружает содержимое каждого веб-сайта и возвращает содержимое в виде массива байтов;</span><span class="sxs-lookup"><span data-stu-id="1a9bf-164">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>  
  
    -   <span data-ttu-id="1a9bf-165">`DisplayResults`, который показывает число байтов в массиве байтов для каждого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-165">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>  
  
     <span data-ttu-id="1a9bf-166">Скопируйте следующие четыре метода, а затем вставьте их в обработчик событий `startButton_Click` в файле MainWindow.xaml.cs:</span><span class="sxs-lookup"><span data-stu-id="1a9bf-166">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.cs:</span></span>  
  
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
###  <span data-ttu-id="1a9bf-167"><a name="testSynch"></a> Тестирование синхронного решения</span><span class="sxs-lookup"><span data-stu-id="1a9bf-167"><a name="testSynch"></a> To test the synchronous solution</span></span>  
  
1.  <span data-ttu-id="1a9bf-168">Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .</span><span class="sxs-lookup"><span data-stu-id="1a9bf-168">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="1a9bf-169">Программа должна выдать результаты, похожие на следующий список.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-169">Output that resembles the following list should appear.</span></span>  
  
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
  
     <span data-ttu-id="1a9bf-170">Обратите внимание, что вывод результатов на экран занимает несколько секунд.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-170">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="1a9bf-171">В течение этого времени поток пользовательского интерфейса заблокирован, пока он ожидает загрузку запрошенных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-171">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="1a9bf-172">Соответственно, после нажатия кнопки **Start** окно нельзя перемещать, разворачивать, сворачивать или даже закрывать.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-172">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="1a9bf-173">Эти действия будут завершаться сбоем, пока не появятся результаты подсчета.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-173">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="1a9bf-174">Если веб-сайт не отвечает, вы не можете определить, на каком сайте произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-174">If a website isn’t responding, you have no indication of which site failed.</span></span> <span data-ttu-id="1a9bf-175">Трудно даже остановить ожидание и закрыть программу.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-175">It is difficult even to stop waiting and close the program.</span></span>  
  
##  <a name="BKMK_ConvertGtBtArr"></a>   
###  <span data-ttu-id="1a9bf-176"><a name="GetURLContents"></a> Преобразование GetURLContents в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="1a9bf-176"><a name="GetURLContents"></a> To convert GetURLContents to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="1a9bf-177">Чтобы преобразовать синхронное решение в асинхронное, лучше всего начать с метода `GetURLContents`, поскольку вызовы метода <xref:System.Net.HttpWebRequest> <xref:System.Net.HttpWebRequest.GetResponse%2A> и метода <xref:System.IO.Stream> <xref:System.IO.Stream.CopyTo%2A> выполняются, когда приложение подключается к Интернету.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-177">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest> method <xref:System.Net.HttpWebRequest.GetResponse%2A> and to the <xref:System.IO.Stream> method <xref:System.IO.Stream.CopyTo%2A> are where the application accesses the web.</span></span> <span data-ttu-id="1a9bf-178">Платформа .NET Framework упрощает преобразование путем предоставления асинхронных версий этих методов.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-178">The .NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>  
  
     <span data-ttu-id="1a9bf-179">Дополнительные сведения о методах, которые используются в `GetURLContents`, см. в разделе <xref:System.Net.WebRequest>.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-179">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1a9bf-180">По мере выполнения шагов в этом пошаговом руководстве возникают различные ошибки компилятора.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-180">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="1a9bf-181">Их можно игнорировать и продолжить процедуры пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-181">You can ignore them and continue with the walkthrough.</span></span>  
  
     <span data-ttu-id="1a9bf-182">Измените метод, который вызывается в третьей строке `GetURLContents` из `GetResponse`, асинхронным методом <xref:System.Net.WebRequest.GetResponseAsync%2A>, основанным на задачах.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-182">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>  
  
    ```csharp  
    using (WebResponse response = webReq.GetResponseAsync())  
    ```  
  
2.  <span data-ttu-id="1a9bf-183">`GetResponseAsync` возвращает значение типа <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-183">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="1a9bf-184">В этом случае *переменная, возвращаемая задачей*, `TResult`, имеет тип <xref:System.Net.WebResponse>.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-184">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="1a9bf-185">Задача является обещанием создать фактический объект `WebResponse` после загрузки запрошенных данных и выполнения задачи до завершения.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-185">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>  
  
     <span data-ttu-id="1a9bf-186">Для получения значения `WebResponse` из задачи примените оператор [await](../../../../csharp/language-reference/keywords/await.md) для вызова метода `GetResponseAsync`, как показано в приведенном ниже примере кода.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-186">To retrieve the `WebResponse` value from the task, apply an [await](../../../../csharp/language-reference/keywords/await.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>  
  
    ```csharp  
    using (WebResponse response = await webReq.GetResponseAsync())  
    ```  
  
     <span data-ttu-id="1a9bf-187">Оператор `await` приостанавливает выполнение текущего метода `GetURLContents`, пока не будет завершена ожидаемая задача.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-187">The `await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="1a9bf-188">На это время управление возвращается вызывающему объекту текущего метода.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-188">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="1a9bf-189">В этом примере текущим методом является `GetURLContents`, а вызывающим объектом — `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-189">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="1a9bf-190">После завершения задачи создается обещанный объект `WebResponse` в качестве значения ожидаемой задачи, который присваивается переменной `response`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-190">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>  
  
     <span data-ttu-id="1a9bf-191">Предыдущий оператор можно разделить на следующие два оператора для уточнения выполняемых операций.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-191">The previous statement can be separated into the following two statements to clarify what happens.</span></span>  
  
    ```csharp  
    //Task<WebResponse> responseTask = webReq.GetResponseAsync();  
    //using (WebResponse response = await responseTask)  
    ```  
  
     <span data-ttu-id="1a9bf-192">Вызов `webReq.GetResponseAsync` возвращает `Task(Of WebResponse)` или `Task<WebResponse>`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-192">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="1a9bf-193">Затем оператор await применяется к задаче для получения значения `WebResponse`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-193">Then an await operator is applied to the task to retrieve the `WebResponse` value.</span></span>  
  
     <span data-ttu-id="1a9bf-194">Если асинхронному методу нужно выполнить определенную работу, не связанную с завершением конкретной задачи, он может проделать это между выполнением этих двух операторов: после вызова метода async и перед применением оператора `await`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-194">If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the `await` operator is applied.</span></span> <span data-ttu-id="1a9bf-195">Примеры см. в статьях [Практическое руководство. Параллельное выполнение нескольких веб-запросов с использованием Async и Await (C#)](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) и [Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="1a9bf-195">For examples, see [How to: Make Multiple Web Requests in Parallel by Using async and await (C#)](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
3.  <span data-ttu-id="1a9bf-196">Из-за добавления оператора `await` в предыдущем шаге возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-196">Because you added the `await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="1a9bf-197">Этот оператор можно использовать только в методах, помеченных модификатором [async](../../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="1a9bf-197">The operator can be used only in methods that are marked with the [async](../../../../csharp/language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="1a9bf-198">Пропустите ошибку, повторяя действия по замене вызова `CopyTo` вызовом метода `CopyToAsync`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-198">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>  
  
    -   <span data-ttu-id="1a9bf-199">Измените имя метода, вызывающего <xref:System.IO.Stream.CopyToAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-199">Change the name of the method that’s called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>  
  
    -   <span data-ttu-id="1a9bf-200">Метод `CopyTo` или `CopyToAsync` копирует байты в свой аргумент `content` и не возвращает осмысленное значение.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-200">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn’t return a meaningful value.</span></span> <span data-ttu-id="1a9bf-201">В синхронной версии вызов метода `CopyTo` — это просто оператор, который не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-201">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="1a9bf-202">Асинхронная версия — `CopyToAsync` — возвращает <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-202">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="1a9bf-203">Задача работает как Task(void) и позволяет ожидать метод.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-203">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="1a9bf-204">Примените `Await` или `await` к вызову `CopyToAsync`, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-204">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>  
  
        ```csharp  
        await responseStream.CopyToAsync(content);  
        ```  
  
         <span data-ttu-id="1a9bf-205">Предыдущий оператор сокращает две следующие строки кода.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-205">The previous statement abbreviates the following two lines of code.</span></span>  
  
        ```csharp  
        // CopyToAsync returns a Task, not a Task<T>.  
        //Task copyTask = responseStream.CopyToAsync(content);  
  
        // When copyTask is completed, content contains a copy of  
        // responseStream.  
        //await copyTask;  
        ```  
  
4.  <span data-ttu-id="1a9bf-206">Все, что остается сделать в `GetURLContents`, — это изменить подпись метода.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-206">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="1a9bf-207">Оператор `await` можно использовать только в методах, помеченных модификатором [async](../../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="1a9bf-207">You can use the `await` operator only in methods that are marked with the [async](../../../../csharp/language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="1a9bf-208">Добавьте модификатор, чтобы пометить метод как *асинхронный*, как показано в приведенном ниже примере кода.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-208">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>  
  
    ```csharp  
    private async byte[] GetURLContents(string url)  
    ```  
  
5.  <span data-ttu-id="1a9bf-209">Возвращаемым типом асинхронного метода может быть только <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> или `void` в C#.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-209">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, or `void` in C#.</span></span> <span data-ttu-id="1a9bf-210">Как правило, тип возвращаемого значения `void` используется только в асинхронном обработчике событий, где `void` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-210">Typically, a return type of `void` is used only in an async event handler, where `void` is required.</span></span> <span data-ttu-id="1a9bf-211">В других случаях используется `Task(T)`, если завершенный метод имеет оператор [return](../../../../csharp/language-reference/keywords/return.md), возвращающий значение типа T, или `Task`, если завершенный метод не возвращает осмысленное значение.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-211">In other cases, you use `Task(T)` if the completed method has a [return](../../../../csharp/language-reference/keywords/return.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.</span></span> <span data-ttu-id="1a9bf-212">Можно представить тип возвращаемого значения `Task` как Task(void).</span><span class="sxs-lookup"><span data-stu-id="1a9bf-212">You can think of the `Task` return type as meaning "Task(void)."</span></span>  
  
     <span data-ttu-id="1a9bf-213">Дополнительные сведения см. в разделе [Асинхронные типы возвращаемых значений (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="1a9bf-213">For more information, see [Async Return Types (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
     <span data-ttu-id="1a9bf-214">Метод `GetURLContents` имеет оператор return, который возвращает массив байтов.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-214">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="1a9bf-215">Таким образом, тип возвращаемого значения асинхронной версии — Task(T), где T — массив байтов.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-215">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="1a9bf-216">Внесите следующие изменения в подпись метода.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-216">Make the following changes in the method signature:</span></span>  
  
    -   <span data-ttu-id="1a9bf-217">Измените тип возвращаемого значения на `Task<byte[]>`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-217">Change the return type to `Task<byte[]>`.</span></span>  
  
    -   <span data-ttu-id="1a9bf-218">По соглашению об именовании асинхронные методы имеют имена, заканчивающиеся на Async, поэтому переименуйте метод в `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-218">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>  
  
     <span data-ttu-id="1a9bf-219">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-219">The following code shows these changes.</span></span>  
  
    ```csharp  
    private async Task<byte[]> GetURLContentsAsync(string url)  
    ```  
  
     <span data-ttu-id="1a9bf-220">После внесения этих изменений преобразование `GetURLContents` в асинхронный метод завершено.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-220">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>  
  
##  <a name="BKMK_ConvertSumPagSzs"></a>   
###  <span data-ttu-id="1a9bf-221"><a name="SumPageSizes"></a> Преобразование SumPageSizes в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="1a9bf-221"><a name="SumPageSizes"></a> To convert SumPageSizes to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="1a9bf-222">Повторите шаги из предыдущей процедуры для `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-222">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="1a9bf-223">Во-первых, преобразуйте вызов метода `GetURLContents` в вызов асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-223">First, change the call to `GetURLContents` to an asynchronous call.</span></span>  
  
    -   <span data-ttu-id="1a9bf-224">Измените имя вызываемого метода с `GetURLContents` на `GetURLContentsAsync`, если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-224">Change the name of the method that’s called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>  
  
    -   <span data-ttu-id="1a9bf-225">Примените оператор `await` к задаче, возвращаемой методом `GetURLContentsAsync`, для получения значения байтового массива.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-225">Apply `await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>  
  
     <span data-ttu-id="1a9bf-226">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-226">The following code shows these changes.</span></span>  
  
    ```csharp  
    byte[] urlContents = await GetURLContentsAsync(url);  
    ```  
  
     <span data-ttu-id="1a9bf-227">Предыдущее назначение сокращает две следующие строки кода.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-227">The previous assignment abbreviates the following two lines of code.</span></span>  
  
    ```csharp  
    // GetURLContentsAsync returns a Task<T>. At completion, the task  
    // produces a byte array.  
    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);  
    //byte[] urlContents = await getContentsTask;  
    ```  
  
2.  <span data-ttu-id="1a9bf-228">Внесите следующие изменения в подпись метода.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-228">Make the following changes in the method's signature:</span></span>  
  
    -   <span data-ttu-id="1a9bf-229">Пометьте метод модификатором `async`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-229">Mark the method with the `async` modifier.</span></span>  
  
    -   <span data-ttu-id="1a9bf-230">Добавьте в имя метода Async.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-230">Add "Async" to the method name.</span></span>  
  
    -   <span data-ttu-id="1a9bf-231">В этот раз нет возвращаемой переменной задачи T, поскольку `SumPageSizesAsync` не возвращает значение для T. (В этом методе нет оператора `return`.) Тем не менее метод должен возвращать `Task`, чтобы для него можно было задать ожидание.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-231">There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="1a9bf-232">Поэтому измените тип возвращаемого значения метода с `void` на `Task`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-232">Therefore, change the return type of the method from `void` to `Task`.</span></span>  
  
     <span data-ttu-id="1a9bf-233">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-233">The following code shows these changes.</span></span>  
  
    ```csharp  
    private async Task SumPageSizesAsync()  
    ```  
  
     <span data-ttu-id="1a9bf-234">Преобразование `SumPageSizes` в `SumPageSizesAsync` завершено.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-234">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>  
  
##  <a name="BKMK_Cnvrtbttn1"></a>   
###  <span data-ttu-id="1a9bf-235"><a name="startButton"></a> Преобразование startButton_Click в асинхронный метод</span><span class="sxs-lookup"><span data-stu-id="1a9bf-235"><a name="startButton"></a> To convert startButton_Click to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="1a9bf-236">В обработчике событий измените имя вызываемого метода с `SumPageSizes` на `SumPageSizesAsync`, если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-236">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven’t already done so.</span></span>  
  
2.  <span data-ttu-id="1a9bf-237">Поскольку `SumPageSizesAsync` является асинхронным методом, измените код в обработчике событий для ожидания результата.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-237">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>  
  
     <span data-ttu-id="1a9bf-238">Вызов `SumPageSizesAsync` отражает вызов `CopyToAsync` в `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-238">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="1a9bf-239">Вызов возвращает `Task`, а не `Task(T)`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-239">The call returns a `Task`, not a `Task(T)`.</span></span>  
  
     <span data-ttu-id="1a9bf-240">Как и в предыдущих процедурах, вызов можно преобразовать, используя один или два оператора.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-240">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="1a9bf-241">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-241">The following code shows these changes.</span></span>  
  
    ```csharp  
    // One-step async call.  
    await SumPageSizesAsync();  
  
    // Two-step async call.  
    //Task sumTask = SumPageSizesAsync();  
    //await sumTask;  
    ```  
  
3.  <span data-ttu-id="1a9bf-242">Чтобы предотвратить случайное повторное введение операции, добавьте следующий оператор в верхней части `startButton_Click`, чтобы отключить кнопку **Start**.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-242">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>  
  
    ```csharp  
    // Disable the button until the operation is complete.  
    startButton.IsEnabled = false;  
    ```  
  
     <span data-ttu-id="1a9bf-243">Можно снова включить кнопку в конце обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-243">You can reenable the button at the end of the event handler.</span></span>  
  
    ```csharp  
    // Reenable the button in case you want to run the operation again.  
    startButton.IsEnabled = true;  
    ```  
  
     <span data-ttu-id="1a9bf-244">Дополнительные сведения о повторном входе см. в разделе [Обработка повторного входа в асинхронных приложениях (C#)](../../../../csharp/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span><span class="sxs-lookup"><span data-stu-id="1a9bf-244">For more information about reentrancy, see [Handling Reentrancy in Async Apps (C#)](../../../../csharp/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span></span>  
  
4.  <span data-ttu-id="1a9bf-245">Наконец, добавьте модификатор `async` в объявление, чтобы обработчик событий мог ожидать `SumPagSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-245">Finally, add the `async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>  
  
    ```csharp  
    private async void startButton_Click(object sender, RoutedEventArgs e)  
    ```  
  
     <span data-ttu-id="1a9bf-246">Как правило, имена обработчиков событий не изменяются.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-246">Typically, the names of event handlers aren’t changed.</span></span> <span data-ttu-id="1a9bf-247">Тип возвращаемого значения не изменяется на `Task`, так как обработчики событий должны возвращать `void`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-247">The return type isn’t changed to `Task` because event handlers must return `void`.</span></span>  
  
     <span data-ttu-id="1a9bf-248">Преобразование проекта из синхронного в асинхронный завершено.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-248">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>  
  
##  <a name="BKMK_testAsynchSolution"></a>   
###  <span data-ttu-id="1a9bf-249"><a name="testAsynch"></a> Тестирование асинхронного решения</span><span class="sxs-lookup"><span data-stu-id="1a9bf-249"><a name="testAsynch"></a> To test the asynchronous solution</span></span>  
  
1.  <span data-ttu-id="1a9bf-250">Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .</span><span class="sxs-lookup"><span data-stu-id="1a9bf-250">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
2.  <span data-ttu-id="1a9bf-251">Появившиеся результаты должны напоминать результаты синхронного решения.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-251">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="1a9bf-252">Однако имеются следующие различия.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-252">However, notice the following differences.</span></span>  
  
    -   <span data-ttu-id="1a9bf-253">Все результаты не отображаются одновременно после завершения обработки.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-253">The results don’t all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="1a9bf-254">Например, обе программы содержат строку в `startButton_Click`, которая очищает текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-254">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="1a9bf-255">Ее цель состоит в том, чтобы очистить текстовое поле между запусками при нажатии кнопки **Start** во второй раз после появления одного набора результатов.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-255">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="1a9bf-256">В синхронной версии текстовое поле очищается перед отображением данных во второй раз, после завершения загрузки и высвобождения потока пользовательского интерфейса для выполнения других операций.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-256">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="1a9bf-257">В асинхронной версии текстовое поле очищается сразу же после нажатия кнопки **Start**.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-257">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>  
  
    -   <span data-ttu-id="1a9bf-258">И что самое главное, поток пользовательского интерфейса не блокируется во время загрузки.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-258">Most importantly, the UI thread isn’t blocked during the downloads.</span></span> <span data-ttu-id="1a9bf-259">Можно перемещать окно или изменять его размер во время загрузки, подсчета и отображения веб-ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-259">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="1a9bf-260">Если один из веб-сайтов работает медленно или не отвечает, можно отменить операцию, нажав кнопку **Закрыть** (красный крестик в правом верхнем углу окна).</span><span class="sxs-lookup"><span data-stu-id="1a9bf-260">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>  
  
##  <a name="BKMK_ReplaceGetByteArrayAsync"></a>   
###  <span data-ttu-id="1a9bf-261"><a name="GetURLContentsAsync"></a> Замена GetURLContentsAsync методом .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1a9bf-261"><a name="GetURLContentsAsync"></a> To replace method GetURLContentsAsync with a .NET Framework method</span></span>  
  
1.  <span data-ttu-id="1a9bf-262">Платформа .NET Framework 4.5 предоставляет много асинхронных методов, которые вы можете использовать.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-262">The .NET Framework 4.5 provides many async methods that you can use.</span></span> <span data-ttu-id="1a9bf-263">Один из них, метод <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29> <xref:System.Net.Http.HttpClient>, выполняет именно те операции, которые требуются для данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-263">One of them, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, does just what you need for this walkthrough.</span></span> <span data-ttu-id="1a9bf-264">Его можно использовать вместо метода `GetURLContentsAsync`, созданного в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-264">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>  
  
     <span data-ttu-id="1a9bf-265">Первым шагом является создание объекта `HttpClient` в методе `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-265">The first step is to create an `HttpClient` object in method `SumPageSizesAsync`.</span></span> <span data-ttu-id="1a9bf-266">Добавьте следующее объявление в начале метода.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-266">Add the following declaration at the start of the method.</span></span>  
  
    ```csharp  
    // Declare an HttpClient object and increase the buffer size. The  
    // default buffer size is 65,536.  
    HttpClient client =  
        new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
    ```  
  
2.  <span data-ttu-id="1a9bf-267">В `SumPageSizesAsync,` замените вызов метода `GetURLContentsAsync` вызовом метода `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-267">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>  
  
    ```csharp  
    byte[] urlContents = await client.GetByteArrayAsync(url);  
    ```  
  
3.  <span data-ttu-id="1a9bf-268">Удалите или прокомментируйте метод `GetURLContentsAsync`, который вы написали.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-268">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>  
  
4.  <span data-ttu-id="1a9bf-269">Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .</span><span class="sxs-lookup"><span data-stu-id="1a9bf-269">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="1a9bf-270">Поведение этой версии проекта должно соответствовать поведению, которое описывается в процедуре "Тестирование асинхронного решения"; при этом с вашей стороны требуется даже меньше усилий.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-270">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>  
  
##  <span data-ttu-id="1a9bf-271"><a name="BKMK_CompleteCodeExamples"></a> Пример</span><span class="sxs-lookup"><span data-stu-id="1a9bf-271"><a name="BKMK_CompleteCodeExamples"></a> Example</span></span>  
 <span data-ttu-id="1a9bf-272">Следующий код содержит полный пример преобразования решения из синхронного в асинхронное с помощью написанного вами асинхронного метода `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-272">The following code contains the full example of the conversion from a synchronous to an asynchronous solution by using the asynchronous `GetURLContentsAsync` method that you wrote.</span></span> <span data-ttu-id="1a9bf-273">Обратите внимание, что он очень напоминает исходное синхронное решение.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-273">Notice that it strongly resembles the original, synchronous solution.</span></span>  
  
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
  
 <span data-ttu-id="1a9bf-274">Следующий код содержит полный пример решения, использующего метод `HttpClient`, `GetByteArrayAsync`.</span><span class="sxs-lookup"><span data-stu-id="1a9bf-274">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1a9bf-275">См. также</span><span class="sxs-lookup"><span data-stu-id="1a9bf-275">See Also</span></span>  
 <span data-ttu-id="1a9bf-276">[Пример асинхронности. Пошаговое руководство "Доступ к сети" (C# и Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255191) </span><span class="sxs-lookup"><span data-stu-id="1a9bf-276">[Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255191) </span></span>  
 <span data-ttu-id="1a9bf-277">[async](../../../../csharp/language-reference/keywords/async.md) </span><span class="sxs-lookup"><span data-stu-id="1a9bf-277">[async](../../../../csharp/language-reference/keywords/async.md) </span></span>  
 <span data-ttu-id="1a9bf-278">[await](../../../../csharp/language-reference/keywords/await.md) </span><span class="sxs-lookup"><span data-stu-id="1a9bf-278">[await](../../../../csharp/language-reference/keywords/await.md) </span></span>  
 <span data-ttu-id="1a9bf-279">[Асинхронное программирование с использованием ключевых слов Async и Await (C#)](../../../../csharp/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="1a9bf-279">[Asynchronous Programming with async and await (C#)](../../../../csharp/programming-guide/concepts/async/index.md) </span></span>  
 <span data-ttu-id="1a9bf-280">[Асинхронные типы возвращаемых значений (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md) </span><span class="sxs-lookup"><span data-stu-id="1a9bf-280">[Async Return Types (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md) </span></span>  
 <span data-ttu-id="1a9bf-281">[Асинхронное программирование на основе задач (TAP)](http://go.microsoft.com/fwlink/?LinkId=204847) </span><span class="sxs-lookup"><span data-stu-id="1a9bf-281">[Task-based Asynchronous Programming (TAP)](http://go.microsoft.com/fwlink/?LinkId=204847) </span></span>  
 <span data-ttu-id="1a9bf-282">[Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) </span><span class="sxs-lookup"><span data-stu-id="1a9bf-282">[How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) </span></span>  
 [<span data-ttu-id="1a9bf-283">Практическое руководство. Параллельное выполнение нескольких веб-запросов с использованием Async и Await (C#)</span><span class="sxs-lookup"><span data-stu-id="1a9bf-283">How to: Make Multiple Web Requests in Parallel by Using async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)

