---
title: "Доступ к Интернету с помощью Async и Await (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- VB
ms.assetid: 84fd047f-fab8-4d89-8ced-104fb7310a91
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
ms.openlocfilehash: 643fff648336c664961ad7956308acbaea262f61
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a><span data-ttu-id="e1c67-102">Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1c67-102">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>
<span data-ttu-id="e1c67-103">Можно написать асинхронные программы легко и интуитивно с помощью функций, которые были введены в [!INCLUDE[vs_dev11_long](../../../../csharp/includes/vs_dev11_long_md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1c67-103">You can write asynchronous programs more easily and intuitively by using features that were introduced in [!INCLUDE[vs_dev11_long](../../../../csharp/includes/vs_dev11_long_md.md)].</span></span> <span data-ttu-id="e1c67-104">Можно написать асинхронный код, который выглядит как синхронный, и позволить компилятору обрабатывать трудные функции обратного вызова и продолжения, которые обычно включает асинхронный код.</span><span class="sxs-lookup"><span data-stu-id="e1c67-104">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>  
  
 <span data-ttu-id="e1c67-105">Дополнительные сведения о функции асинхронного см [асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="e1c67-105">For more information about the Async feature, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="e1c67-106">Это пошаговое руководство начинается с создания синхронного приложения Windows Presentation Foundation (WPF), которое суммирует число байтов в списке веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="e1c67-106">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="e1c67-107">Затем в рамках руководства приложение преобразуется в асинхронное решение с помощью новых возможностей.</span><span class="sxs-lookup"><span data-stu-id="e1c67-107">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>  
  
 <span data-ttu-id="e1c67-108">Если вы не хотите самостоятельно создавать приложения, можно загрузить «образец Async: доступ к Web пошагового руководства (C# и Visual Basic)» из [образцы кода разработчика](http://go.microsoft.com/fwlink/?LinkId=255191).</span><span class="sxs-lookup"><span data-stu-id="e1c67-108">If you don't want to build the applications yourself, you can download "Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)" from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191).</span></span>  
  
 <span data-ttu-id="e1c67-109">В этом пошаговом руководстве выполняются следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="e1c67-109">In this walkthrough, you complete the following tasks:</span></span>  
  
-   [<span data-ttu-id="e1c67-110">Создание приложения WPF</span><span class="sxs-lookup"><span data-stu-id="e1c67-110">To create a WPF application</span></span>](#CreateWPFApp)  
  
-   [<span data-ttu-id="e1c67-111">Для разработки простого MainWindow WPF</span><span class="sxs-lookup"><span data-stu-id="e1c67-111">To design a simple WPF MainWindow</span></span>](#MainWindow)  
  
-   [<span data-ttu-id="e1c67-112">Добавление ссылки</span><span class="sxs-lookup"><span data-stu-id="e1c67-112">To add a reference</span></span>](#AddRef)  
  
-   [<span data-ttu-id="e1c67-113">Добавление необходимых операторов Imports</span><span class="sxs-lookup"><span data-stu-id="e1c67-113">To add necessary Imports statements</span></span>](#ImportsState)  
  
-   [<span data-ttu-id="e1c67-114">Создание синхронного приложения</span><span class="sxs-lookup"><span data-stu-id="e1c67-114">To create a synchronous application</span></span>](#synchronous)  
  
-   [<span data-ttu-id="e1c67-115">Чтобы проверить синхронного решения</span><span class="sxs-lookup"><span data-stu-id="e1c67-115">To test the synchronous solution</span></span>](#testSynch)  
  
-   [<span data-ttu-id="e1c67-116">Чтобы преобразовать в асинхронный метод GetURLContents</span><span class="sxs-lookup"><span data-stu-id="e1c67-116">To convert GetURLContents to an asynchronous method</span></span>](#GetURLContents)  
  
-   [<span data-ttu-id="e1c67-117">Чтобы преобразовать в асинхронный метод SumPageSizes</span><span class="sxs-lookup"><span data-stu-id="e1c67-117">To convert SumPageSizes to an asynchronous method</span></span>](#SumPageSizes)  
  
-   [<span data-ttu-id="e1c67-118">Чтобы преобразовать в асинхронный метод startButton_Click</span><span class="sxs-lookup"><span data-stu-id="e1c67-118">To convert startButton_Click to an asynchronous method</span></span>](#startButton)  
  
-   [<span data-ttu-id="e1c67-119">Чтобы проверить асинхронных решений</span><span class="sxs-lookup"><span data-stu-id="e1c67-119">To test the asynchronous solution</span></span>](#testAsynch)  
  
-   [<span data-ttu-id="e1c67-120">Чтобы заменить метод GetURLContentsAsync метод .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e1c67-120">To replace method GetURLContentsAsync with a .NET Framework method</span></span>](#GetURLContentsAsync)  
  
-   [<span data-ttu-id="e1c67-121">Пример</span><span class="sxs-lookup"><span data-stu-id="e1c67-121">Example</span></span>](#BKMK_CompleteCodeExamples)  
  
## <a name="prerequisites"></a><span data-ttu-id="e1c67-122">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="e1c67-122">Prerequisites</span></span>  
 <span data-ttu-id="e1c67-123">Visual Studio 2012 или более поздней версии необходимо установить на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e1c67-123">Visual Studio 2012 or later must be installed on your computer.</span></span> <span data-ttu-id="e1c67-124">Дополнительные сведения см. в разделе [веб-сайте Майкрософт](http://go.microsoft.com/fwlink/?LinkId=235233).</span><span class="sxs-lookup"><span data-stu-id="e1c67-124">For more information, see the [Microsoft website](http://go.microsoft.com/fwlink/?LinkId=235233).</span></span>  
  
###  <span data-ttu-id="e1c67-125"><a name="CreateWPFApp"></a>Создание приложения WPF</span><span class="sxs-lookup"><span data-stu-id="e1c67-125"><a name="CreateWPFApp"></a> To create a WPF application</span></span>  
  
1.  <span data-ttu-id="e1c67-126">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e1c67-126">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="e1c67-127">В строке меню выберите **Файл**, **Создать**, **Проект**.</span><span class="sxs-lookup"><span data-stu-id="e1c67-127">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="e1c67-128">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="e1c67-128">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="e1c67-129">В **установленные шаблоны** области выберите Visual Basic и выберите **приложение WPF** в списке типов проектов.</span><span class="sxs-lookup"><span data-stu-id="e1c67-129">In the **Installed Templates** pane, choose Visual Basic, and then choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="e1c67-130">В **имя** текста введите `AsyncExampleWPF`, а затем выберите **ОК** кнопки.</span><span class="sxs-lookup"><span data-stu-id="e1c67-130">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="e1c67-131">Появится новый проект в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="e1c67-131">The new project appears in **Solution Explorer**.</span></span>  
  
##  <a name="BKMK_DesignWPFMainWin"></a>   
###  <span data-ttu-id="e1c67-132"><a name="MainWindow"></a>Для разработки простого MainWindow WPF</span><span class="sxs-lookup"><span data-stu-id="e1c67-132"><a name="MainWindow"></a> To design a simple WPF MainWindow</span></span>  
  
1.  <span data-ttu-id="e1c67-133">В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="e1c67-133">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
2.  <span data-ttu-id="e1c67-134">Если **элементов** окно не отображается, откройте **представление** меню и выберите **элементов**.</span><span class="sxs-lookup"><span data-stu-id="e1c67-134">If the **Toolbox** window isn’t visible, open the **View** menu, and then choose **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="e1c67-135">Добавить **кнопку** управления и **TextBox** управления **MainWindow** окна.</span><span class="sxs-lookup"><span data-stu-id="e1c67-135">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>  
  
4.  <span data-ttu-id="e1c67-136">Выделите **TextBox** управления и в **свойства** установите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="e1c67-136">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="e1c67-137">Задайте **имя** свойства `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-137">Set the **Name** property to `resultsTextBox`.</span></span>  
  
    -   <span data-ttu-id="e1c67-138">Задайте **высота** свойство до 250.</span><span class="sxs-lookup"><span data-stu-id="e1c67-138">Set the **Height** property to 250.</span></span>  
  
    -   <span data-ttu-id="e1c67-139">Задайте **ширина** значение 500.</span><span class="sxs-lookup"><span data-stu-id="e1c67-139">Set the **Width** property to 500.</span></span>  
  
    -   <span data-ttu-id="e1c67-140">На **текст** укажите моноширинный шрифт, например Lucida Console или глобальных Моноширинный.</span><span class="sxs-lookup"><span data-stu-id="e1c67-140">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>  
  
5.  <span data-ttu-id="e1c67-141">Выделите **кнопку** управления и в **свойства** установите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="e1c67-141">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="e1c67-142">Задайте **имя** свойства `startButton`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-142">Set the **Name** property to `startButton`.</span></span>  
  
    -   <span data-ttu-id="e1c67-143">Измените значение **содержимого** свойства из **кнопку** для **запустить**.</span><span class="sxs-lookup"><span data-stu-id="e1c67-143">Change the value of the **Content** property from **Button** to **Start**.</span></span>  
  
6.  <span data-ttu-id="e1c67-144">Поместите текстовое поле и кнопку, чтобы одновременно появляться в **MainWindow** окна.</span><span class="sxs-lookup"><span data-stu-id="e1c67-144">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>  
  
     <span data-ttu-id="e1c67-145">Дополнительные сведения о конструкторе WPF XAML см. в разделе [Создание пользовательского интерфейса с помощью конструктора XAML](https://docs.microsoft.com/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="e1c67-145">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](https://docs.microsoft.com/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>  
  
##  <a name="BKMK_AddReference"></a>   
###  <span data-ttu-id="e1c67-146"><a name="AddRef"></a>Добавление ссылки</span><span class="sxs-lookup"><span data-stu-id="e1c67-146"><a name="AddRef"></a> To add a reference</span></span>  
  
1.  <span data-ttu-id="e1c67-147">В **обозревателе**, выделите имя проекта.</span><span class="sxs-lookup"><span data-stu-id="e1c67-147">In **Solution Explorer**, highlight your project's name.</span></span>  
  
2.  <span data-ttu-id="e1c67-148">В строке меню выберите **проекта**, **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="e1c67-148">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="e1c67-149">**Диспетчер ссылок** откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="e1c67-149">The **Reference Manager** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="e1c67-150">Вверху диалогового окна убедитесь, что проект предназначен для .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="e1c67-150">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>  
  
4.  <span data-ttu-id="e1c67-151">В **сборки** область, выберите **Framework** , если он еще не выбран.</span><span class="sxs-lookup"><span data-stu-id="e1c67-151">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>  
  
5.  <span data-ttu-id="e1c67-152">В списке имен, выберите **System.Net.Http** флажок.</span><span class="sxs-lookup"><span data-stu-id="e1c67-152">In the list of names, select the **System.Net.Http** check box.</span></span>  
  
6.  <span data-ttu-id="e1c67-153">Выберите **ОК** кнопку, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="e1c67-153">Choose the **OK** button to close the dialog box.</span></span>  
  
##  <a name="BKMK_AddStatesandDirs"></a>   
###  <span data-ttu-id="e1c67-154"><a name="ImportsState"></a>Добавление необходимых операторов Imports</span><span class="sxs-lookup"><span data-stu-id="e1c67-154"><a name="ImportsState"></a> To add necessary Imports statements</span></span>  
  
1.  <span data-ttu-id="e1c67-155">В **обозревателе решений**, откройте контекстное меню для MainWindow.xaml.vb и выберите **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="e1c67-155">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="e1c67-156">Добавьте следующие `Imports` в начало файла кода, если они еще не существуют.</span><span class="sxs-lookup"><span data-stu-id="e1c67-156">Add the following `Imports` statements at the top of the code file if they’re not already present.</span></span>  
  
    ```vb  
    Imports System.Net.Http  
    Imports System.Net  
    Imports System.IO  
    ```  
  
##  <a name="BKMK_CreatSynchApp"></a>   
###  <span data-ttu-id="e1c67-157"><a name="synchronous"></a>Создание синхронного приложения</span><span class="sxs-lookup"><span data-stu-id="e1c67-157"><a name="synchronous"></a> To create a synchronous application</span></span>  
  
1.  <span data-ttu-id="e1c67-158">Дважды щелкните в окне конструктора, файл MainWindow.xaml **запустить** кнопку, чтобы создать `startButton_Click` обработчика событий в файл MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="e1c67-158">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="e1c67-159">В MainWindow.xaml.vb, скопируйте следующий код в теле `startButton_Click`:</span><span class="sxs-lookup"><span data-stu-id="e1c67-159">In MainWindow.xaml.vb, copy the following code into the body of `startButton_Click`:</span></span>  
  
    ```vb  
    resultsTextBox.Clear()  
    SumPageSizes()  
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."  
    ```  
  
     <span data-ttu-id="e1c67-160">Код вызывает метод, который управляет приложением `SumPageSizes` и выводит на экран сообщение, когда элемент управления возвращается к `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-160">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>  
  
3.  <span data-ttu-id="e1c67-161">Код для синхронного решения содержит следующие четыре метода:</span><span class="sxs-lookup"><span data-stu-id="e1c67-161">The code for the synchronous solution contains the following four methods:</span></span>  
  
    -   <span data-ttu-id="e1c67-162">`SumPageSizes`, который получает список URL-адресов веб-страниц из `SetUpURLList`, а затем вызывает метод `GetURLContents` и `DisplayResults` для обработки каждого URL-адреса;</span><span class="sxs-lookup"><span data-stu-id="e1c67-162">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>  
  
    -   <span data-ttu-id="e1c67-163">`SetUpURLList`, который создает и возвращает список веб-адресов;</span><span class="sxs-lookup"><span data-stu-id="e1c67-163">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>  
  
    -   <span data-ttu-id="e1c67-164">`GetURLContents`, который загружает содержимое каждого веб-сайта и возвращает содержимое в виде массива байтов;</span><span class="sxs-lookup"><span data-stu-id="e1c67-164">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>  
  
    -   <span data-ttu-id="e1c67-165">`DisplayResults`, который показывает число байтов в массиве байтов для каждого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="e1c67-165">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>  
  
     <span data-ttu-id="e1c67-166">Скопируйте следующие четыре метода и затем вставить их в разделе `startButton_Click` обработчика событий в файл MainWindow.xaml.vb:</span><span class="sxs-lookup"><span data-stu-id="e1c67-166">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.vb:</span></span>  
  
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
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
    ```  
  
##  <a name="BKMK_TestSynchSol"></a>   
###  <span data-ttu-id="e1c67-167"><a name="testSynch"></a>Чтобы проверить синхронного решения</span><span class="sxs-lookup"><span data-stu-id="e1c67-167"><a name="testSynch"></a> To test the synchronous solution</span></span>  
  
1.  <span data-ttu-id="e1c67-168">Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .</span><span class="sxs-lookup"><span data-stu-id="e1c67-168">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="e1c67-169">Программа должна выдать результаты, похожие на следующий список.</span><span class="sxs-lookup"><span data-stu-id="e1c67-169">Output that resembles the following list should appear.</span></span>  
  
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
  
     <span data-ttu-id="e1c67-170">Обратите внимание, что вывод результатов на экран занимает несколько секунд.</span><span class="sxs-lookup"><span data-stu-id="e1c67-170">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="e1c67-171">В течение этого времени поток пользовательского интерфейса заблокирован, пока он ожидает загрузку запрошенных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e1c67-171">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="e1c67-172">В результате нельзя перемещать, максимизировать, минимизировать или даже закрыть окна после выбора **запустить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="e1c67-172">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="e1c67-173">Эти действия будут завершаться сбоем, пока не появятся результаты подсчета.</span><span class="sxs-lookup"><span data-stu-id="e1c67-173">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="e1c67-174">Если веб-сайт не отвечает, вы не можете определить, на каком сайте произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="e1c67-174">If a website isn’t responding, you have no indication of which site failed.</span></span> <span data-ttu-id="e1c67-175">Трудно даже остановить ожидание и закрыть программу.</span><span class="sxs-lookup"><span data-stu-id="e1c67-175">It is difficult even to stop waiting and close the program.</span></span>  
  
##  <a name="BKMK_ConvertGtBtArr"></a>   
###  <span data-ttu-id="e1c67-176"><a name="GetURLContents"></a>Чтобы преобразовать в асинхронный метод GetURLContents</span><span class="sxs-lookup"><span data-stu-id="e1c67-176"><a name="GetURLContents"></a> To convert GetURLContents to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="e1c67-177">Преобразование синхронного решения для асинхронных решений, лучше всего начать находится в `GetURLContents` из-за вызовов <xref:System.Net.HttpWebRequest>метод <xref:System.Net.HttpWebRequest.GetResponse%2A>и <xref:System.IO.Stream>метод <xref:System.IO.Stream.CopyTo%2A>— это когда приложение подключается к Интернету.</xref:System.IO.Stream.CopyTo%2A> </xref:System.IO.Stream> </xref:System.Net.HttpWebRequest.GetResponse%2A> </xref:System.Net.HttpWebRequest></span><span class="sxs-lookup"><span data-stu-id="e1c67-177">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest> method <xref:System.Net.HttpWebRequest.GetResponse%2A> and to the <xref:System.IO.Stream> method <xref:System.IO.Stream.CopyTo%2A> are where the application accesses the web.</span></span> <span data-ttu-id="e1c67-178">Платформа .NET Framework упрощает преобразование путем предоставления асинхронных версий этих методов.</span><span class="sxs-lookup"><span data-stu-id="e1c67-178">The .NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>  
  
     <span data-ttu-id="e1c67-179">Дополнительные сведения о методах, которые используются в `GetURLContents`, <xref:System.Net.WebRequest>.</xref:System.Net.WebRequest> см.</span><span class="sxs-lookup"><span data-stu-id="e1c67-179">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e1c67-180">По мере выполнения шагов в этом пошаговом руководстве возникают различные ошибки компилятора.</span><span class="sxs-lookup"><span data-stu-id="e1c67-180">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="e1c67-181">Их можно игнорировать и продолжить процедуры пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="e1c67-181">You can ignore them and continue with the walkthrough.</span></span>  
  
     <span data-ttu-id="e1c67-182">Измените метод, вызываемый в третьей строке `GetURLContents` из `GetResponse` асинхронным, основанные на задачах <xref:System.Net.WebRequest.GetResponseAsync%2A>метод.</xref:System.Net.WebRequest.GetResponseAsync%2A></span><span class="sxs-lookup"><span data-stu-id="e1c67-182">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>  
  
    ```vb  
    Using response As WebResponse = webReq.GetResponseAsync()  
    ```  
  
2.  <span data-ttu-id="e1c67-183">`GetResponseAsync`Возвращает <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="e1c67-183">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="e1c67-184">В этом случае *задач возвращаемой переменной*, `TResult`, имеет тип <xref:System.Net.WebResponse>.</xref:System.Net.WebResponse></span><span class="sxs-lookup"><span data-stu-id="e1c67-184">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="e1c67-185">Задача является обещанием создать фактический объект `WebResponse` после загрузки запрошенных данных и выполнения задачи до завершения.</span><span class="sxs-lookup"><span data-stu-id="e1c67-185">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>  
  
     <span data-ttu-id="e1c67-186">Для получения `WebResponse` значения из задачи, применить [Await](../../../../visual-basic/language-reference/operators/await-operator.md) оператор для вызова `GetResponseAsync`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="e1c67-186">To retrieve the `WebResponse` value from the task, apply an [Await](../../../../visual-basic/language-reference/operators/await-operator.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>  
  
<span data-ttu-id="e1c67-187"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="e1c67-187"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
     <span data-ttu-id="e1c67-188">`Await` Оператор приостанавливает выполнение текущего метода `GetURLContents`, пока не будет завершена ожидаемая задача.</span><span class="sxs-lookup"><span data-stu-id="e1c67-188">The `Await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="e1c67-189">На это время управление возвращается вызывающему объекту текущего метода.</span><span class="sxs-lookup"><span data-stu-id="e1c67-189">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="e1c67-190">В этом примере текущим методом является `GetURLContents`, а вызывающим объектом — `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-190">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="e1c67-191">После завершения задачи создается обещанный объект `WebResponse` в качестве значения ожидаемой задачи, который присваивается переменной `response`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-191">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>  
  
     The previous statement can be separated into the following two statements to clarify what happens.  
  
<span data-ttu-id="e1c67-192"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="e1c67-192"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
     <span data-ttu-id="e1c67-193">Вызов `webReq.GetResponseAsync` возвращает `Task(Of WebResponse)` или `Task<WebResponse>`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-193">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="e1c67-194">Затем `Await` оператор применяется к задачу, чтобы получить `WebResponse` значение.</span><span class="sxs-lookup"><span data-stu-id="e1c67-194">Then an `Await` operator is applied to the task to retrieve the `WebResponse` value.</span></span>  
  
     If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the await operator is applied. For examples, see [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
3.  <span data-ttu-id="e1c67-195">Так как вы добавили `Await` оператор в предыдущем шаге, возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="e1c67-195">Because you added the `Await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="e1c67-196">Оператор может использоваться только в методы, помеченные атрибутом [Async](../../../../visual-basic/language-reference/modifiers/async.md) модификатор.</span><span class="sxs-lookup"><span data-stu-id="e1c67-196">The operator can be used only in methods that are marked with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="e1c67-197">Пропустите ошибку, повторяя действия по замене вызова `CopyTo` вызовом метода `CopyToAsync`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-197">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>  
  
    -   <span data-ttu-id="e1c67-198">Измените имя метода, который вызывается для <xref:System.IO.Stream.CopyToAsync%2A>.</xref:System.IO.Stream.CopyToAsync%2A></span><span class="sxs-lookup"><span data-stu-id="e1c67-198">Change the name of the method that’s called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>  
  
    -   <span data-ttu-id="e1c67-199">Метод `CopyTo` или `CopyToAsync` копирует байты в свой аргумент `content` и не возвращает осмысленное значение.</span><span class="sxs-lookup"><span data-stu-id="e1c67-199">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn’t return a meaningful value.</span></span> <span data-ttu-id="e1c67-200">В синхронной версии вызов метода `CopyTo` — это просто оператор, который не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="e1c67-200">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="e1c67-201">Асинхронная версия `CopyToAsync`, возвращает <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="e1c67-201">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="e1c67-202">Задача работает как Task(void) и позволяет ожидать метод.</span><span class="sxs-lookup"><span data-stu-id="e1c67-202">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="e1c67-203">Примените `Await` или `await` к вызову `CopyToAsync`, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="e1c67-203">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>  
  
<span data-ttu-id="e1c67-204"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="e1c67-204"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span></span>  
         <span data-ttu-id="e1c67-205">Предыдущий оператор сокращает две следующие строки кода.</span><span class="sxs-lookup"><span data-stu-id="e1c67-205">The previous statement abbreviates the following two lines of code.</span></span>  
  
<span data-ttu-id="e1c67-206"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="e1c67-206"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
4.  <span data-ttu-id="e1c67-207">Все, что остается сделать в `GetURLContents`, — это изменить подпись метода.</span><span class="sxs-lookup"><span data-stu-id="e1c67-207">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="e1c67-208">Можно использовать `Await` оператор только в методы, помеченные атрибутом [Async](../../../../visual-basic/language-reference/modifiers/async.md) модификатор.</span><span class="sxs-lookup"><span data-stu-id="e1c67-208">You can use the `Await` operator only in methods that are marked with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="e1c67-209">Добавьте модификатор пометить метод как *асинхронный метод*, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="e1c67-209">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>  
  
<span data-ttu-id="e1c67-210"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="e1c67-210"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
5.  <span data-ttu-id="e1c67-211">Возвращаемый тип асинхронный метод может быть только <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="e1c67-211">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="e1c67-212">В Visual Basic метод должен являться функцией `Function`, возвращающей `Task` или `Task(Of T)`, либо он должен быть `Sub`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-212">In Visual Basic, the method must be a `Function` that returns a `Task` or a `Task(Of T)`, or the method must be a `Sub`.</span></span> <span data-ttu-id="e1c67-213">Как правило `Sub` метод используется только в асинхронный обработчик событий, где `Sub` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="e1c67-213">Typically, a `Sub` method  is used only in an async event handler, where `Sub` is required.</span></span> <span data-ttu-id="e1c67-214">В других случаях используйте `Task(T)` Если завершенного метода [вернуть](../../../../visual-basic/language-reference/statements/return-statement.md) инструкцию, возвращающую значение типа T, после чего использовать `Task` Если завершенного метода не возвращает допустимое значение.</span><span class="sxs-lookup"><span data-stu-id="e1c67-214">In other cases, you use `Task(T)` if the completed method has a [Return](../../../../visual-basic/language-reference/statements/return-statement.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.</span></span>  
  
     <span data-ttu-id="e1c67-215">Дополнительные сведения см. в разделе [возвращают типы Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="e1c67-215">For more information, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
     <span data-ttu-id="e1c67-216">Метод `GetURLContents` имеет оператор return, который возвращает массив байтов.</span><span class="sxs-lookup"><span data-stu-id="e1c67-216">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="e1c67-217">Таким образом, тип возвращаемого значения асинхронной версии — Task(T), где T — массив байтов.</span><span class="sxs-lookup"><span data-stu-id="e1c67-217">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="e1c67-218">Внесите следующие изменения в подпись метода.</span><span class="sxs-lookup"><span data-stu-id="e1c67-218">Make the following changes in the method signature:</span></span>  
  
    -   <span data-ttu-id="e1c67-219">Изменить тип возврата для `Task(Of Byte())`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-219">Change the return type to `Task(Of Byte())`.</span></span>  
  
    -   <span data-ttu-id="e1c67-220">По соглашению об именовании асинхронные методы имеют имена, заканчивающиеся на Async, поэтому переименуйте метод в `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-220">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>  
  
     <span data-ttu-id="e1c67-221">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="e1c67-221">The following code shows these changes.</span></span>  
  
    ```vb  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
    ```  
  
     <span data-ttu-id="e1c67-222">После внесения этих изменений преобразование `GetURLContents` в асинхронный метод завершено.</span><span class="sxs-lookup"><span data-stu-id="e1c67-222">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>  
  
##  <a name="BKMK_ConvertSumPagSzs"></a>   
###  <span data-ttu-id="e1c67-223"><a name="SumPageSizes"></a>Чтобы преобразовать в асинхронный метод SumPageSizes</span><span class="sxs-lookup"><span data-stu-id="e1c67-223"><a name="SumPageSizes"></a> To convert SumPageSizes to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="e1c67-224">Повторите шаги из предыдущей процедуры для `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-224">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="e1c67-225">Во-первых, преобразуйте вызов метода `GetURLContents` в вызов асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="e1c67-225">First, change the call to `GetURLContents` to an asynchronous call.</span></span>  
  
    -   <span data-ttu-id="e1c67-226">Измените имя вызываемого метода с `GetURLContents` на `GetURLContentsAsync`, если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="e1c67-226">Change the name of the method that’s called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>  
  
    -   <span data-ttu-id="e1c67-227">Применить `Await` к задаче, `GetURLContentsAsync` значение возвращает для получения байтов массива.</span><span class="sxs-lookup"><span data-stu-id="e1c67-227">Apply `Await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>  
  
     <span data-ttu-id="e1c67-228">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="e1c67-228">The following code shows these changes.</span></span>  
  
    ```vb  
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
    ```  
  
     <span data-ttu-id="e1c67-229">Предыдущее назначение сокращает две следующие строки кода.</span><span class="sxs-lookup"><span data-stu-id="e1c67-229">The previous assignment abbreviates the following two lines of code.</span></span>  
  
    ```vb  
    ' GetURLContentsAsync returns a task. At completion, the task   
    ' produces a byte array.   
    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)   
    'Dim urlContents As Byte() = Await getContentsTask  
  
    ```  
  
2.  <span data-ttu-id="e1c67-230">Внесите следующие изменения в подпись метода.</span><span class="sxs-lookup"><span data-stu-id="e1c67-230">Make the following changes in the method's signature:</span></span>  
  
    -   <span data-ttu-id="e1c67-231">Пометьте метод `Async` модификатор.</span><span class="sxs-lookup"><span data-stu-id="e1c67-231">Mark the method with the `Async` modifier.</span></span>  
  
    -   <span data-ttu-id="e1c67-232">Добавьте в имя метода Async.</span><span class="sxs-lookup"><span data-stu-id="e1c67-232">Add "Async" to the method name.</span></span>  
  
    -   <span data-ttu-id="e1c67-233">В этот раз нет возвращаемой переменной задачи T, поскольку `SumPageSizesAsync` не возвращает значение для T. (Не имеет метода `Return` инструкции.) Тем не менее метод должен возвращать `Task`, чтобы для него можно было задать ожидание.</span><span class="sxs-lookup"><span data-stu-id="e1c67-233">There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `Return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="e1c67-234">Таким образом, измените тип метода с `Sub` в `Function`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-234">Therefore, change the method type from `Sub` to `Function`.</span></span> <span data-ttu-id="e1c67-235">Тип значения, возвращаемого функцией, — `Task`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-235">The return type of the function is `Task`.</span></span>  
  
     <span data-ttu-id="e1c67-236">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="e1c67-236">The following code shows these changes.</span></span>  
  
    ```vb  
    Private Async Function SumPageSizesAsync() As Task  
    ```  
  
     <span data-ttu-id="e1c67-237">Преобразование `SumPageSizes` в `SumPageSizesAsync` завершено.</span><span class="sxs-lookup"><span data-stu-id="e1c67-237">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>  
  
##  <a name="BKMK_Cnvrtbttn1"></a>   
###  <span data-ttu-id="e1c67-238"><a name="startButton"></a>Чтобы преобразовать в асинхронный метод startButton_Click</span><span class="sxs-lookup"><span data-stu-id="e1c67-238"><a name="startButton"></a> To convert startButton_Click to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="e1c67-239">В обработчике событий измените имя вызываемого метода с `SumPageSizes` на `SumPageSizesAsync`, если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="e1c67-239">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven’t already done so.</span></span>  
  
2.  <span data-ttu-id="e1c67-240">Поскольку `SumPageSizesAsync` является асинхронным методом, измените код в обработчике событий для ожидания результата.</span><span class="sxs-lookup"><span data-stu-id="e1c67-240">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>  
  
     <span data-ttu-id="e1c67-241">Вызов `SumPageSizesAsync` отражает вызов `CopyToAsync` в `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-241">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="e1c67-242">Вызов возвращает `Task`, а не `Task(T)`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-242">The call returns a `Task`, not a `Task(T)`.</span></span>  
  
     <span data-ttu-id="e1c67-243">Как и в предыдущих процедурах, вызов можно преобразовать, используя один или два оператора.</span><span class="sxs-lookup"><span data-stu-id="e1c67-243">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="e1c67-244">В следующем примере кода показаны эти изменения.</span><span class="sxs-lookup"><span data-stu-id="e1c67-244">The following code shows these changes.</span></span>  
  
    ```vb  
    '' One-step async call.  
    Await SumPageSizesAsync()  
  
    ' Two-step async call.  
    'Dim sumTask As Task = SumPageSizesAsync()  
    'Await sumTask  
    ```  
  
3.  <span data-ttu-id="e1c67-245">Чтобы избежать случайного повторного ввода операции, добавьте следующий оператор в верхней части `startButton_Click` отключение **запустить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="e1c67-245">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>  
  
    ```vb  
    ' Disable the button until the operation is complete.  
    startButton.IsEnabled = False  
    ```  
  
     <span data-ttu-id="e1c67-246">Можно снова включить кнопку в конце обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="e1c67-246">You can reenable the button at the end of the event handler.</span></span>  
  
    ```vb  
    ' Reenable the button in case you want to run the operation again.  
    startButton.IsEnabled = True  
    ```  
  
     <span data-ttu-id="e1c67-247">Дополнительные сведения о повторный вход в разделе [обработка повторного входа в асинхронных приложениях (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span><span class="sxs-lookup"><span data-stu-id="e1c67-247">For more information about reentrancy, see [Handling Reentrancy in Async Apps (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span></span>  
  
4.  <span data-ttu-id="e1c67-248">Наконец, добавьте `Async` модификатор объявление, чтобы обработчик событий может ожидать `SumPagSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-248">Finally, add the `Async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>  
  
    ```vb  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
    ```  
  
     <span data-ttu-id="e1c67-249">Как правило, имена обработчиков событий не изменяются.</span><span class="sxs-lookup"><span data-stu-id="e1c67-249">Typically, the names of event handlers aren’t changed.</span></span> <span data-ttu-id="e1c67-250">Тип возвращаемого значения не изменено на `Task` поскольку обработчики событий должны быть `Sub` процедуры в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e1c67-250">The return type isn’t changed to `Task` because event handlers must be `Sub` procedures in Visual Basic.</span></span>  
  
     <span data-ttu-id="e1c67-251">Преобразование проекта из синхронного в асинхронный завершено.</span><span class="sxs-lookup"><span data-stu-id="e1c67-251">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>  
  
##  <a name="BKMK_testAsynchSolution"></a>   
###  <span data-ttu-id="e1c67-252"><a name="testAsynch"></a>Чтобы проверить асинхронных решений</span><span class="sxs-lookup"><span data-stu-id="e1c67-252"><a name="testAsynch"></a> To test the asynchronous solution</span></span>  
  
1.  <span data-ttu-id="e1c67-253">Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .</span><span class="sxs-lookup"><span data-stu-id="e1c67-253">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
2.  <span data-ttu-id="e1c67-254">Появившиеся результаты должны напоминать результаты синхронного решения.</span><span class="sxs-lookup"><span data-stu-id="e1c67-254">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="e1c67-255">Однако имеются следующие различия.</span><span class="sxs-lookup"><span data-stu-id="e1c67-255">However, notice the following differences.</span></span>  
  
    -   <span data-ttu-id="e1c67-256">Все результаты не отображаются одновременно после завершения обработки.</span><span class="sxs-lookup"><span data-stu-id="e1c67-256">The results don’t all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="e1c67-257">Например, обе программы содержат строку в `startButton_Click`, которая очищает текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="e1c67-257">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="e1c67-258">Целью является очистите поле между запусками, при выборе **запустить** кнопку второй раз, после появления одного набора результатов.</span><span class="sxs-lookup"><span data-stu-id="e1c67-258">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="e1c67-259">В синхронной версии текстовое поле очищается перед отображением данных во второй раз, после завершения загрузки и высвобождения потока пользовательского интерфейса для выполнения других операций.</span><span class="sxs-lookup"><span data-stu-id="e1c67-259">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="e1c67-260">В асинхронной версии текстовое поле снимается сразу после выбора **запустить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="e1c67-260">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>  
  
    -   <span data-ttu-id="e1c67-261">И что самое главное, поток пользовательского интерфейса не блокируется во время загрузки.</span><span class="sxs-lookup"><span data-stu-id="e1c67-261">Most importantly, the UI thread isn’t blocked during the downloads.</span></span> <span data-ttu-id="e1c67-262">Можно перемещать окно или изменять его размер во время загрузки, подсчета и отображения веб-ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e1c67-262">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="e1c67-263">Если один из веб-сайтов выполняется слишком медленно или не отвечает, можно отменить операцию, выбрав **закрыть** кнопку (x, в поле "красный" в правом верхнем углу).</span><span class="sxs-lookup"><span data-stu-id="e1c67-263">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>  
  
##  <a name="BKMK_ReplaceGetByteArrayAsync"></a>   
###  <span data-ttu-id="e1c67-264"><a name="GetURLContentsAsync"></a>Чтобы заменить метод GetURLContentsAsync метод .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e1c67-264"><a name="GetURLContentsAsync"></a> To replace method GetURLContentsAsync with a .NET Framework method</span></span>  
  
1.  <span data-ttu-id="e1c67-265">Платформа .NET Framework 4.5 предоставляет много асинхронных методов, которые вы можете использовать.</span><span class="sxs-lookup"><span data-stu-id="e1c67-265">The .NET Framework 4.5 provides many async methods that you can use.</span></span> <span data-ttu-id="e1c67-266">Одно из них, <xref:System.Net.Http.HttpClient>метод <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, только необходимые для этого пошагового руководства.</xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29> </xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="e1c67-266">One of them, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, does just what you need for this walkthrough.</span></span> <span data-ttu-id="e1c67-267">Его можно использовать вместо метода `GetURLContentsAsync`, созданного в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="e1c67-267">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>  
  
     <span data-ttu-id="e1c67-268">Первым шагом является создание объекта `HttpClient` в методе `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-268">The first step is to create an `HttpClient` object in method `SumPageSizesAsync`.</span></span> <span data-ttu-id="e1c67-269">Добавьте следующее объявление в начале метода.</span><span class="sxs-lookup"><span data-stu-id="e1c67-269">Add the following declaration at the start of the method.</span></span>  
  
    ```vb  
    ' Declare an HttpClient object and increase the buffer size. The  
    ' default buffer size is 65,536.  
    Dim client As HttpClient =  
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
    ```  
  
2.  <span data-ttu-id="e1c67-270">В `SumPageSizesAsync,` замените вызов метода `GetURLContentsAsync` вызовом метода `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-270">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>  
  
    ```vb  
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
    ```  
  
3.  <span data-ttu-id="e1c67-271">Удалите или прокомментируйте метод `GetURLContentsAsync`, который вы написали.</span><span class="sxs-lookup"><span data-stu-id="e1c67-271">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>  
  
4.  <span data-ttu-id="e1c67-272">Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .</span><span class="sxs-lookup"><span data-stu-id="e1c67-272">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="e1c67-273">Поведение этой версии проекта должно соответствовать поведению, которое описывается в процедуре "Тестирование асинхронного решения"; при этом с вашей стороны требуется даже меньше усилий.</span><span class="sxs-lookup"><span data-stu-id="e1c67-273">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>  
  
##  <span data-ttu-id="e1c67-274"><a name="BKMK_CompleteCodeExamples"></a>Пример</span><span class="sxs-lookup"><span data-stu-id="e1c67-274"><a name="BKMK_CompleteCodeExamples"></a> Example</span></span>  
 <span data-ttu-id="e1c67-275">Следующий код содержит полный пример преобразования решения из синхронного в асинхронное с помощью написанного вами асинхронного метода `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-275">The following code contains the full example of the conversion from a synchronous to an asynchronous solution by using the asynchronous `GetURLContentsAsync` method that you wrote.</span></span> <span data-ttu-id="e1c67-276">Обратите внимание, что он очень напоминает исходное синхронное решение.</span><span class="sxs-lookup"><span data-stu-id="e1c67-276">Notice that it strongly resembles the original, synchronous solution.</span></span>  
  
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
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
 <span data-ttu-id="e1c67-277">Следующий код содержит полный пример решения, использующего метод `HttpClient`, `GetByteArrayAsync`.</span><span class="sxs-lookup"><span data-stu-id="e1c67-277">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>  
  
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
  
        '' Two-step async call.  
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
            }  
        Return urls  
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
  
## <a name="see-also"></a><span data-ttu-id="e1c67-278">См. также</span><span class="sxs-lookup"><span data-stu-id="e1c67-278">See Also</span></span>  
 <span data-ttu-id="e1c67-279">[Образец ASYNC: Доступ к Web пошагового руководства (C# и Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255191) </span><span class="sxs-lookup"><span data-stu-id="e1c67-279">[Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255191) </span></span>  
<span data-ttu-id="e1c67-280"> [Оператор await](../../../../visual-basic/language-reference/operators/await-operator.md) </span><span class="sxs-lookup"><span data-stu-id="e1c67-280"> [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) </span></span>  
<span data-ttu-id="e1c67-281"> [Async](../../../../visual-basic/language-reference/modifiers/async.md) </span><span class="sxs-lookup"><span data-stu-id="e1c67-281"> [Async](../../../../visual-basic/language-reference/modifiers/async.md) </span></span>  
<span data-ttu-id="e1c67-282"> [Асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="e1c67-282"> [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="e1c67-283"> [Асинхронные типы возвращаемых значений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span><span class="sxs-lookup"><span data-stu-id="e1c67-283"> [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span></span>  
<span data-ttu-id="e1c67-284"> [Асинхронное программирование, основанные на задачах (TAP)](http://go.microsoft.com/fwlink/?LinkId=204847) </span><span class="sxs-lookup"><span data-stu-id="e1c67-284"> [Task-based Asynchronous Programming (TAP)](http://go.microsoft.com/fwlink/?LinkId=204847) </span></span>  
<span data-ttu-id="e1c67-285"> [Практическое руководство: расширение Async пошагового руководства с использованием метода Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) </span><span class="sxs-lookup"><span data-stu-id="e1c67-285"> [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) </span></span>  
<span data-ttu-id="e1c67-286"> [Практическое руководство: параллельное выполнение нескольких веб-запросов с помощью модификатора Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)</span><span class="sxs-lookup"><span data-stu-id="e1c67-286"> [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)</span></span>
