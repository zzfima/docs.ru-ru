---
title: "Управление ходом выполнения в асинхронных программах (Visual Basic) | Документы Microsoft"
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
ms.assetid: b0443af7-c586-4cb0-b476-742ae4098a96
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
ms.openlocfilehash: 15e02fbc023db9ae2f3ee9f40598faa7c9c027a0
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="control-flow-in-async-programs-visual-basic"></a><span data-ttu-id="c249c-102">Поток управления в асинхронных программах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c249c-102">Control Flow in Async Programs (Visual Basic)</span></span>
<span data-ttu-id="c249c-103">Можно написать и более легко поддерживать асинхронные программы с помощью `Async` и `Await` ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="c249c-103">You can write and maintain asynchronous programs more easily by using the `Async` and `Await` keywords.</span></span> <span data-ttu-id="c249c-104">Однако результаты могут оказаться неожиданными Если вы не понимаете, как работает программа.</span><span class="sxs-lookup"><span data-stu-id="c249c-104">However, the results might surprise you if you don't understand how your program operates.</span></span> <span data-ttu-id="c249c-105">Этот раздел трассировки, передачи потока управления через простой асинхронной программы, чтобы показать, когда элемент управления перемещается из одного метода другим и какие данные каждый раз.</span><span class="sxs-lookup"><span data-stu-id="c249c-105">This topic traces the flow of control through a simple async program to show you when control moves from one method to another and what information is transferred each time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c249c-106">Ключевые слова `Async` и `Await` появились в Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="c249c-106">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span>  
  
 <span data-ttu-id="c249c-107">В общем случае пометить методы, содержащие асинхронного кода с [Async](../../../../visual-basic/language-reference/modifiers/async.md) модификатор.</span><span class="sxs-lookup"><span data-stu-id="c249c-107">In general, you mark methods that contain asynchronous code with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="c249c-108">В метод, помеченный с помощью модификатора async, можно использовать [Await (Visual Basic)](../../../../visual-basic/language-reference/operators/await-operator.md) оператор, чтобы указать, где метод приостанавливает для ожидания завершения вызванного асинхронного процесса.</span><span class="sxs-lookup"><span data-stu-id="c249c-108">In a method that's marked with an async modifier, you can use an [Await (Visual Basic)](../../../../visual-basic/language-reference/operators/await-operator.md) operator to specify where the method pauses to wait for a called asynchronous process to complete.</span></span> <span data-ttu-id="c249c-109">Дополнительные сведения см. в разделе [асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="c249c-109">For more information, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="c249c-110">В следующем примере асинхронные методы для загрузки содержимого веб-сайт, указанный как строка и отображения длину строки.</span><span class="sxs-lookup"><span data-stu-id="c249c-110">The following example uses async methods to download the contents of a specified website as a string and to display the length of the string.</span></span> <span data-ttu-id="c249c-111">Пример содержит два метода.</span><span class="sxs-lookup"><span data-stu-id="c249c-111">The example contains the following two methods.</span></span>  
  
-   <span data-ttu-id="c249c-112">`startButton_Click`, который вызывает метод `AccessTheWebAsync` и отображает результат.</span><span class="sxs-lookup"><span data-stu-id="c249c-112">`startButton_Click`, which calls `AccessTheWebAsync` and displays the result.</span></span>  
  
-   <span data-ttu-id="c249c-113">`AccessTheWebAsync`, который загружает содержимое веб-сайта в виде строки и возвращает длину строки.</span><span class="sxs-lookup"><span data-stu-id="c249c-113">`AccessTheWebAsync`, which downloads the contents of a website as a string and returns the length of the string.</span></span> <span data-ttu-id="c249c-114">`AccessTheWebAsync`использует асинхронную <xref:System.Net.Http.HttpClient>метод <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, чтобы загрузить содержимое.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> </xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="c249c-114">`AccessTheWebAsync` uses an asynchronous <xref:System.Net.Http.HttpClient> method, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, to download the contents.</span></span>  
  
 <span data-ttu-id="c249c-115">Нумерация отображаемые строки отображаются в стратегических точках в программе помогут вам понять, как работает программа и объясняется, что происходит на каждом этапе, который отмечен.</span><span class="sxs-lookup"><span data-stu-id="c249c-115">Numbered display lines appear at strategic points throughout the program to help you understand how the program runs and to explain what happens at each point that is marked.</span></span> <span data-ttu-id="c249c-116">Отображение линии обозначаются «Один» до «ШЕСТЬ.»</span><span class="sxs-lookup"><span data-stu-id="c249c-116">The display lines are labeled "ONE" through "SIX."</span></span> <span data-ttu-id="c249c-117">Метки представляют порядок, в котором программа достигает этих строк кода.</span><span class="sxs-lookup"><span data-stu-id="c249c-117">The labels represent the order in which the program reaches these lines of code.</span></span>  
  
 <span data-ttu-id="c249c-118">В следующем коде показано структуры программы.</span><span class="sxs-lookup"><span data-stu-id="c249c-118">The following code shows an outline of the program.</span></span>  
  
```vb  
Class MainWindow  
  
    Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click  
  
        ' ONE  
        Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()  
  
        ' FOUR  
        Dim contentLength As Integer = Await getLengthTask  
  
        ' SIX  
        ResultsTextBox.Text &=  
            String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
    End Sub  
  
    Async Function AccessTheWebAsync() As Task(Of Integer)  
  
        ' TWO  
        Dim client As HttpClient = New HttpClient()   
        Dim getStringTask As Task(Of String) =   
            client.GetStringAsync("http://msdn.microsoft.com")  
  
        ' THREE  
        Dim urlContents As String = Await getStringTask  
  
        ' FIVE  
        Return urlContents.Length  
    End Function  
  
End Class  
  
```  
  
 <span data-ttu-id="c249c-119">Каждый из расположения с меткой, «Один» до «ШЕСТЬ,» отображает сведения о текущем состоянии программы.</span><span class="sxs-lookup"><span data-stu-id="c249c-119">Each of the labeled locations, "ONE" through "SIX," displays information about the current state of the program.</span></span> <span data-ttu-id="c249c-120">Получается следующий результат.</span><span class="sxs-lookup"><span data-stu-id="c249c-120">The following output is produced.</span></span>  
  
```  
  
ONE:   Entering startButton_Click.  
           Calling AccessTheWebAsync.  
  
TWO:   Entering AccessTheWebAsync.  
           Calling HttpClient.GetStringAsync.  
  
THREE: Back in AccessTheWebAsync.  
           Task getStringTask is started.  
           About to await getStringTask & return a Task<int> to startButton_Click.  
  
FOUR:  Back in startButton_Click.  
           Task getLengthTask is started.  
           About to await getLengthTask -- no caller to return to.  
  
FIVE:  Back in AccessTheWebAsync.  
           Task getStringTask is complete.  
           Processing the return statement.  
           Exiting from AccessTheWebAsync.  
  
SIX:   Back in startButton_Click.  
           Task getLengthTask is finished.  
           Result from AccessTheWebAsync is stored in contentLength.  
           About to display contentLength and exit.  
  
Length of the downloaded string: 33946.  
```  
  
## <a name="set-up-the-program"></a><span data-ttu-id="c249c-121">Настроить программу</span><span class="sxs-lookup"><span data-stu-id="c249c-121">Set Up the Program</span></span>  
 <span data-ttu-id="c249c-122">Код, который используется в этом разделе можно загрузить с сайта MSDN, или можно выполнить его самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="c249c-122">You can download the code that this topic uses from MSDN, or you can build it yourself.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c249c-123">Чтобы выполнить этот пример, необходимо иметь Visual Studio 2012 или более поздней версии и платформы .NET Framework 4.5 или более новая версия вашего компьютера.</span><span class="sxs-lookup"><span data-stu-id="c249c-123">To run the example, you must have Visual Studio 2012 or newer and  the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
### <a name="download-the-program"></a><span data-ttu-id="c249c-124">Загрузка программы</span><span class="sxs-lookup"><span data-stu-id="c249c-124">Download the Program</span></span>  
 <span data-ttu-id="c249c-125">Можно загрузить приложение из этого раздела [образец Async: поток управления в асинхронных программах](http://go.microsoft.com/fwlink/?LinkId=255285).</span><span class="sxs-lookup"><span data-stu-id="c249c-125">You can download the application for this topic from [Async Sample: Control Flow in Async Programs](http://go.microsoft.com/fwlink/?LinkId=255285).</span></span> <span data-ttu-id="c249c-126">Далее откройте и запустите программу.</span><span class="sxs-lookup"><span data-stu-id="c249c-126">The following steps open and run the program.</span></span>  
  
1.  <span data-ttu-id="c249c-127">Распакуйте загруженный файл, а затем запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c249c-127">Unzip the downloaded file, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="c249c-128">В строке меню выберите **Файл**, **Открыть**, **Проект/Решение**.</span><span class="sxs-lookup"><span data-stu-id="c249c-128">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="c249c-129">Перейдите к папке, содержащий распакованную образец кода, откройте файл решения (SLN-файл) и нажмите клавишу F5 для построения и запуска проекта.</span><span class="sxs-lookup"><span data-stu-id="c249c-129">Navigate to the folder that holds the unzipped sample code, open the solution (.sln) file, and then choose the F5 key to build and run the project.</span></span>  
  
### <a name="build-the-program-yourself"></a><span data-ttu-id="c249c-130">Самостоятельное построение программы</span><span class="sxs-lookup"><span data-stu-id="c249c-130">Build the Program Yourself</span></span>  
 <span data-ttu-id="c249c-131">Следующий проект Windows Presentation Foundation (WPF) содержит пример кода для этой темы.</span><span class="sxs-lookup"><span data-stu-id="c249c-131">The following Windows Presentation Foundation (WPF) project contains the code example for this topic.</span></span>  
  
 <span data-ttu-id="c249c-132">Чтобы запустить проект, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="c249c-132">To run the project, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="c249c-133">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c249c-133">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="c249c-134">В строке меню выберите **Файл**, **Создать**, **Проект**.</span><span class="sxs-lookup"><span data-stu-id="c249c-134">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="c249c-135">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="c249c-135">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="c249c-136">В **установленные шаблоны** область, выберите **Visual Basic**и нажмите кнопку **приложение WPF** в списке типов проектов.</span><span class="sxs-lookup"><span data-stu-id="c249c-136">In the **Installed Templates** pane, choose **Visual Basic**, and then choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="c249c-137">Введите `AsyncTracer` как имя проекта, а затем выберите **ОК** кнопки.</span><span class="sxs-lookup"><span data-stu-id="c249c-137">Enter `AsyncTracer` as the name of the project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="c249c-138">Появится новый проект в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="c249c-138">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="c249c-139">В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="c249c-139">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="c249c-140">Если вкладка не отображается, откройте контекстное меню для MainWindow.xaml в **обозревателе решений**, а затем выберите **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="c249c-140">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
6.  <span data-ttu-id="c249c-141">В **XAML** Просмотр файла MainWindow.XAML, замените код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="c249c-141">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>  
  
    ```vb  
    <Window  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d" x:Class="MainWindow"  
        Title="Control Flow Trace" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="221,10,0,0" VerticalAlignment="Top" Width="75"/>  
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" TextWrapping="Wrap" VerticalAlignment="Bottom" Width="510" Height="265" FontFamily="Lucida Console" FontSize="10" VerticalScrollBarVisibility="Visible" d:LayoutOverrides="HorizontalMargin"/>  
  
        </Grid>  
    </Window>  
  
    ```  
  
     <span data-ttu-id="c249c-142">Появится простое окно, содержащее текстовое поле и кнопку в **разработки** файла MainWindow.XAML.</span><span class="sxs-lookup"><span data-stu-id="c249c-142">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>  
  
7.  <span data-ttu-id="c249c-143">Добавить ссылку <xref:System.Net.Http>.</xref:System.Net.Http></span><span class="sxs-lookup"><span data-stu-id="c249c-143">Add a reference for <xref:System.Net.Http>.</span></span>  
  
8.  <span data-ttu-id="c249c-144">В **обозревателе решений**, откройте контекстное меню для MainWindow.xaml.vb и выберите **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="c249c-144">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
9. <span data-ttu-id="c249c-145">В файл MainWindow.xaml.vb замените код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="c249c-145">In MainWindow.xaml.vb , replace the code with the following code.</span></span>  
  
    ```vb  
    ' Add an Imports statement and a reference for System.Net.Http.  
    Imports System.Net.Http  
  
    Class MainWindow  
  
        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click  
  
            ' The display lines in the example lead you through the control shifts.  
            ResultsTextBox.Text &= "ONE:   Entering StartButton_Click." & vbCrLf &  
                "           Calling AccessTheWebAsync." & vbCrLf  
  
            Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()  
  
            ResultsTextBox.Text &= vbCrLf & "FOUR:  Back in StartButton_Click." & vbCrLf &  
                "           Task getLengthTask is started." & vbCrLf &  
                "           About to await getLengthTask -- no caller to return to." & vbCrLf  
  
            Dim contentLength As Integer = Await getLengthTask  
  
            ResultsTextBox.Text &= vbCrLf & "SIX:   Back in StartButton_Click." & vbCrLf &  
                "           Task getLengthTask is finished." & vbCrLf &  
                "           Result from AccessTheWebAsync is stored in contentLength." & vbCrLf &  
                "           About to display contentLength and exit." & vbCrLf  
  
            ResultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
        End Sub  
  
        Async Function AccessTheWebAsync() As Task(Of Integer)  
  
            ResultsTextBox.Text &= vbCrLf & "TWO:   Entering AccessTheWebAsync."  
  
            ' Declare an HttpClient object.  
            Dim client As HttpClient = New HttpClient()  
  
            ResultsTextBox.Text &= vbCrLf & "           Calling HttpClient.GetStringAsync." & vbCrLf  
  
            ' GetStringAsync returns a Task(Of String).   
            Dim getStringTask As Task(Of String) = client.GetStringAsync("http://msdn.microsoft.com")  
  
            ResultsTextBox.Text &= vbCrLf & "THREE: Back in AccessTheWebAsync." & vbCrLf &  
                "           Task getStringTask is started."  
  
            ' AccessTheWebAsync can continue to work until getStringTask is awaited.  
  
            ResultsTextBox.Text &=  
                vbCrLf & "           About to await getStringTask & return a Task(Of Integer) to StartButton_Click." & vbCrLf  
  
            ' Retrieve the website contents when task is complete.  
            Dim urlContents As String = Await getStringTask  
  
            ResultsTextBox.Text &= vbCrLf & "FIVE:  Back in AccessTheWebAsync." &  
                vbCrLf & "           Task getStringTask is complete." &  
                vbCrLf & "           Processing the return statement." &  
                vbCrLf & "           Exiting from AccessTheWebAsync." & vbCrLf  
  
            Return urlContents.Length  
        End Function  
  
    End Class  
    ```  
  
10. <span data-ttu-id="c249c-146">Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .</span><span class="sxs-lookup"><span data-stu-id="c249c-146">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="c249c-147">Должен появиться следующий результат.</span><span class="sxs-lookup"><span data-stu-id="c249c-147">The following output should appear.</span></span>  
  
    ```  
    ONE:   Entering startButton_Click.  
               Calling AccessTheWebAsync.  
  
    TWO:   Entering AccessTheWebAsync.  
               Calling HttpClient.GetStringAsync.  
  
    THREE: Back in AccessTheWebAsync.  
               Task getStringTask is started.  
               About to await getStringTask & return a Task<int> to startButton_Click.  
  
    FOUR:  Back in startButton_Click.  
               Task getLengthTask is started.  
               About to await getLengthTask -- no caller to return to.  
  
    FIVE:  Back in AccessTheWebAsync.  
               Task getStringTask is complete.  
               Processing the return statement.  
               Exiting from AccessTheWebAsync.  
  
    SIX:   Back in startButton_Click.  
               Task getLengthTask is finished.  
               Result from AccessTheWebAsync is stored in contentLength.  
               About to display contentLength and exit.  
  
    Length of the downloaded string: 33946.  
    ```  
  
## <a name="trace-the-program"></a><span data-ttu-id="c249c-148">Программа трассировки</span><span class="sxs-lookup"><span data-stu-id="c249c-148">Trace the Program</span></span>  
  
### <a name="steps-one-and-two"></a><span data-ttu-id="c249c-149">Шаги ОДИН и ДВА</span><span class="sxs-lookup"><span data-stu-id="c249c-149">Steps ONE and TWO</span></span>  
 <span data-ttu-id="c249c-150">Отображение первых двух строк проследить путь как `startButton_Click` вызовов `AccessTheWebAsync`, и `AccessTheWebAsync` вызывает асинхронный <xref:System.Net.Http.HttpClient>метод <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> </xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="c249c-150">The first two display lines trace the path as `startButton_Click` calls `AccessTheWebAsync`, and `AccessTheWebAsync` calls the asynchronous <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span></span> <span data-ttu-id="c249c-151">Ниже описаны вызовов из метода в метод.</span><span class="sxs-lookup"><span data-stu-id="c249c-151">The following image outlines the calls from method to method.</span></span>  
  
 <span data-ttu-id="c249c-152">![Шаги&1; и&2;](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace ONETWO")</span><span class="sxs-lookup"><span data-stu-id="c249c-152">![Steps ONE and TWO](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span></span>  
  
 <span data-ttu-id="c249c-153">Тип возвращаемого значения и `AccessTheWebAsync` и `client.GetStringAsync` <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="c249c-153">The return type of both `AccessTheWebAsync` and `client.GetStringAsync` is <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="c249c-154">Для `AccessTheWebAsync`, TResult является целым числом.</span><span class="sxs-lookup"><span data-stu-id="c249c-154">For `AccessTheWebAsync`, TResult is an integer.</span></span> <span data-ttu-id="c249c-155">Для `GetStringAsync`, TResult — строка.</span><span class="sxs-lookup"><span data-stu-id="c249c-155">For `GetStringAsync`, TResult is a string.</span></span> <span data-ttu-id="c249c-156">Дополнительные сведения о возвращаемых типов асинхронный метод в разделе [возвращают типы Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="c249c-156">For more information about async method return types, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
 <span data-ttu-id="c249c-157">Возвращение задач асинхронный метод возвращает экземпляр задачи, когда элемент управления перемещается обратно вызывающему.</span><span class="sxs-lookup"><span data-stu-id="c249c-157">A task-returning async method returns a task instance when control shifts back to the caller.</span></span> <span data-ttu-id="c249c-158">Возвращает элемент управления из асинхронного метода вызывающему либо если `Await` оператор встречается в вызываемый метод или когда завершается вызванный метод.</span><span class="sxs-lookup"><span data-stu-id="c249c-158">Control returns from an async method to its caller either when an `Await` operator is encountered in the called method or when the called method ends.</span></span> <span data-ttu-id="c249c-159">Отображение строки, помеченные как «ТРИ» до «6» трассировки эта часть процесса.</span><span class="sxs-lookup"><span data-stu-id="c249c-159">The display lines that are labeled "THREE" through "SIX" trace this part of the process.</span></span>  
  
### <a name="step-three"></a><span data-ttu-id="c249c-160">Шаг ТРИ</span><span class="sxs-lookup"><span data-stu-id="c249c-160">Step THREE</span></span>  
 <span data-ttu-id="c249c-161">В `AccessTheWebAsync`, асинхронный метод <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>вызывается для загрузки содержимого веб-страницы целевой.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="c249c-161">In `AccessTheWebAsync`, the asynchronous method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> is called to download the contents of the target webpage.</span></span> <span data-ttu-id="c249c-162">Возвращает элемент управления `client.GetStringAsync` для `AccessTheWebAsync` при `client.GetStringAsync` возвращает.</span><span class="sxs-lookup"><span data-stu-id="c249c-162">Control returns from `client.GetStringAsync` to `AccessTheWebAsync` when `client.GetStringAsync` returns.</span></span>  
  
 <span data-ttu-id="c249c-163">`client.GetStringAsync` Метод возвращает задачу, строки, назначенный `getStringTask` переменных в `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="c249c-163">The `client.GetStringAsync` method returns a task of string that’s assigned to the `getStringTask` variable in `AccessTheWebAsync`.</span></span> <span data-ttu-id="c249c-164">Следующие строки в примере программы показано, как вызвать `client.GetStringAsync` и назначения.</span><span class="sxs-lookup"><span data-stu-id="c249c-164">The following line in the example program shows the call to `client.GetStringAsync` and the assignment.</span></span>  
  
<span data-ttu-id="c249c-165"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="c249c-165"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="c249c-166">Можно считать задачи обещание по `client.GetStringAsync` для создания фактической строки со временем.</span><span class="sxs-lookup"><span data-stu-id="c249c-166">You can think of the task as a promise by `client.GetStringAsync` to produce an actual string eventually.</span></span> <span data-ttu-id="c249c-167">В то же время Если `AccessTheWebAsync` есть работа, не зависящей от обещанной строку из `client.GetStringAsync`, что продолжением работы во время `client.GetStringAsync` ожидания.</span><span class="sxs-lookup"><span data-stu-id="c249c-167">In the meantime, if `AccessTheWebAsync` has work to do that doesn't depend on the promised string from `client.GetStringAsync`, that work can continue while  `client.GetStringAsync` waits.</span></span> <span data-ttu-id="c249c-168">В этом примере следующие строки выходных данных, которые обозначены «ТРИ», представляют возможность работать независимо</span><span class="sxs-lookup"><span data-stu-id="c249c-168">In the example, the following lines of output, which are labeled "THREE,” represent the opportunity to do independent work</span></span>  
  
<span data-ttu-id="c249c-169"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="c249c-169"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="c249c-170">Следующая инструкция приостанавливает ход выполнения в `AccessTheWebAsync` при `getStringTask` будет ожидать.</span><span class="sxs-lookup"><span data-stu-id="c249c-170">The following statement suspends progress in `AccessTheWebAsync` when `getStringTask` is awaited.</span></span>  
  
<span data-ttu-id="c249c-171"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="c249c-171"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="c249c-172">На следующем рисунке поток управления из `client.GetStringAsync` для назначения `getStringTask` и от создания `getStringTask` в приложение оператор Await.</span><span class="sxs-lookup"><span data-stu-id="c249c-172">The following image shows the flow of control from `client.GetStringAsync` to the assignment to `getStringTask` and from the creation of `getStringTask` to the application of an Await operator.</span></span>  
  
 <span data-ttu-id="c249c-173">![ТРЕТИЙ шаг](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "три AsyncTrace")</span><span class="sxs-lookup"><span data-stu-id="c249c-173">![Step THREE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace-Three")</span></span>  
  
 <span data-ttu-id="c249c-174">Выражение await приостанавливает `AccessTheWebAsync` до `client.GetStringAsync` возвращает.</span><span class="sxs-lookup"><span data-stu-id="c249c-174">The await expression suspends `AccessTheWebAsync` until `client.GetStringAsync` returns.</span></span> <span data-ttu-id="c249c-175">В то же время управление возвращается вызывающему объекту `AccessTheWebAsync`, `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="c249c-175">In the meantime, control returns to the caller of `AccessTheWebAsync`, `startButton_Click`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c249c-176">Как правило вы сразу ожидать результата вызова асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="c249c-176">Typically, you await the call to an asynchronous method immediately.</span></span> <span data-ttu-id="c249c-177">Например, следующее присвоение может заменить предыдущий код, который создает и затем ожидает `getStringTask`:`Dim urlContents As String = Await client.GetStringAsync("http://msdn.microsoft.com")`</span><span class="sxs-lookup"><span data-stu-id="c249c-177">For example, the following assignment could replace the previous code that creates and then awaits `getStringTask`: `Dim urlContents As String = Await client.GetStringAsync("http://msdn.microsoft.com")`</span></span>  
>   
>  <span data-ttu-id="c249c-178">В этом разделе оператор await применяется позже для вывода линий, которые отмечают поток управления в программе.</span><span class="sxs-lookup"><span data-stu-id="c249c-178">In this topic, the await operator is applied later to accommodate the output lines that mark the flow of control through the program.</span></span>  
  
### <a name="step-four"></a><span data-ttu-id="c249c-179">Шаг ЧЕТЫРЕ</span><span class="sxs-lookup"><span data-stu-id="c249c-179">Step FOUR</span></span>  
 <span data-ttu-id="c249c-180">Объявленный тип возвращаемого значения `AccessTheWebAsync` — `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="c249c-180">The declared return type of `AccessTheWebAsync` is `Task(Of Integer)`.</span></span> <span data-ttu-id="c249c-181">Таким образом, когда `AccessTheWebAsync` будет приостановлен, он возвращает задачу, целого числа в `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="c249c-181">Therefore, when `AccessTheWebAsync` is suspended, it returns a task of integer to `startButton_Click`.</span></span> <span data-ttu-id="c249c-182">Следует понимать, что возвращаемая задача не `getStringTask`.</span><span class="sxs-lookup"><span data-stu-id="c249c-182">You should understand that the returned task isn’t `getStringTask`.</span></span> <span data-ttu-id="c249c-183">Возвращаемая задача является новой задачи целое число, представляющее что остается сделать в приостановленном методе `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="c249c-183">The returned task is a new task of integer that represents what remains to be done in the suspended method, `AccessTheWebAsync`.</span></span> <span data-ttu-id="c249c-184">Задача является обещание из `AccessTheWebAsync` производить целое число, при завершении задачи.</span><span class="sxs-lookup"><span data-stu-id="c249c-184">The task is a promise from `AccessTheWebAsync` to produce an integer when the task is complete.</span></span>  
  
 <span data-ttu-id="c249c-185">Следующий оператор назначает эту задачу, чтобы `getLengthTask` переменной.</span><span class="sxs-lookup"><span data-stu-id="c249c-185">The following statement assigns this task to the `getLengthTask` variable.</span></span>  
  
<span data-ttu-id="c249c-186"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="c249c-186"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="c249c-187">Как и в `AccessTheWebAsync`, `startButton_Click` можно продолжить работу, не зависят от результатов асинхронной задачи (`getLengthTask`) пока не ожидать задачу.</span><span class="sxs-lookup"><span data-stu-id="c249c-187">As in `AccessTheWebAsync`, `startButton_Click` can continue with work that doesn’t depend on the results of the asynchronous task (`getLengthTask`) until the task is awaited.</span></span> <span data-ttu-id="c249c-188">Следующие выходные данные строки представляют этой работы.</span><span class="sxs-lookup"><span data-stu-id="c249c-188">The following output lines represent that work.</span></span>  
  
<span data-ttu-id="c249c-189"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="c249c-189"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="c249c-190">Выполнение в `startButton_Click` при приостановке `getLengthTask` будет ожидать.</span><span class="sxs-lookup"><span data-stu-id="c249c-190">Progress in `startButton_Click` is suspended when `getLengthTask` is awaited.</span></span> <span data-ttu-id="c249c-191">Следующая инструкция назначения приостанавливает `startButton_Click` до `AccessTheWebAsync` завершения.</span><span class="sxs-lookup"><span data-stu-id="c249c-191">The following assignment statement suspends `startButton_Click` until `AccessTheWebAsync` is complete.</span></span>  
  
<span data-ttu-id="c249c-192"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="c249c-192"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="c249c-193">На следующем рисунке стрелки Показать поток управления из выражения await в `AccessTheWebAsync` для присвоения значения для `getLengthTask`, следуют обычной обработки в `startButton_Click` до `getLengthTask` будет ожидать.</span><span class="sxs-lookup"><span data-stu-id="c249c-193">In the following illustration, the arrows show the flow of control from the await expression in `AccessTheWebAsync` to the assignment of a value to `getLengthTask`, followed by normal processing in `startButton_Click` until `getLengthTask` is awaited.</span></span>  
  
 <span data-ttu-id="c249c-194">![ЧЕТВЕРТЫЙ шаг](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace ЧЕТЫРЕ")</span><span class="sxs-lookup"><span data-stu-id="c249c-194">![Step FOUR](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace-FOUR")</span></span>  
  
### <a name="step-five"></a><span data-ttu-id="c249c-195">Шаг ПЯТЬ</span><span class="sxs-lookup"><span data-stu-id="c249c-195">Step FIVE</span></span>  
 <span data-ttu-id="c249c-196">Когда `client.GetStringAsync` указывает, что завершения обработки в `AccessTheWebAsync` освобождается после приостановки и можно продолжить выполнение после оператора await.</span><span class="sxs-lookup"><span data-stu-id="c249c-196">When `client.GetStringAsync` signals that it’s complete, processing in `AccessTheWebAsync` is released from suspension and can continue past the await statement.</span></span> <span data-ttu-id="c249c-197">Приведенный ниже выходные данные представляют продолжение обработки.</span><span class="sxs-lookup"><span data-stu-id="c249c-197">The following lines of output represent the resumption of processing.</span></span>  
  
<span data-ttu-id="c249c-198"><CodeContentPlaceHolder>11</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="c249c-198"><CodeContentPlaceHolder>11</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="c249c-199">Операнд оператора return `urlContents.Length`, хранится в задаче, `AccessTheWebAsync` возвращает.</span><span class="sxs-lookup"><span data-stu-id="c249c-199">The operand of the return statement, `urlContents.Length`, is stored in the task that  `AccessTheWebAsync` returns.</span></span> <span data-ttu-id="c249c-200">Выражение await получает это значение из `getLengthTask` в `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="c249c-200">The await expression retrieves that value from `getLengthTask` in `startButton_Click`.</span></span>  
  
 <span data-ttu-id="c249c-201">На следующем рисунке показано перемещение элемента управления после `client.GetStringAsync` (и `getStringTask`) завершены.</span><span class="sxs-lookup"><span data-stu-id="c249c-201">The following image shows the transfer of control after `client.GetStringAsync` (and `getStringTask`) are complete.</span></span>  
  
 <span data-ttu-id="c249c-202">![ПЯТЫЙ шаг](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace&5;")</span><span class="sxs-lookup"><span data-stu-id="c249c-202">![Step FIVE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace-FIVE")</span></span>  
  
 <span data-ttu-id="c249c-203">`AccessTheWebAsync`Возвращает выполняется до завершения и управления `startButton_Click`, который ожидает завершения.</span><span class="sxs-lookup"><span data-stu-id="c249c-203">`AccessTheWebAsync` runs to completion, and control returns to `startButton_Click`, which is awaiting the completion.</span></span>  
  
### <a name="step-six"></a><span data-ttu-id="c249c-204">Шаг ШЕСТЬ</span><span class="sxs-lookup"><span data-stu-id="c249c-204">Step SIX</span></span>  
 <span data-ttu-id="c249c-205">Когда `AccessTheWebAsync` сигнализирует завершения обработки можно продолжить выполнение после оператора await в `startButton_Async`.</span><span class="sxs-lookup"><span data-stu-id="c249c-205">When `AccessTheWebAsync` signals that it’s complete, processing can continue past the await statement in `startButton_Async`.</span></span> <span data-ttu-id="c249c-206">На самом деле программа имеет ничего общего дополнительные.</span><span class="sxs-lookup"><span data-stu-id="c249c-206">In fact, the program has nothing more to do.</span></span>  
  
 <span data-ttu-id="c249c-207">Приведенный ниже выходные данные представляют продолжение обработки в `startButton_Async`:</span><span class="sxs-lookup"><span data-stu-id="c249c-207">The following lines of output represent the resumption of processing in `startButton_Async`:</span></span>  
  
<span data-ttu-id="c249c-208"><CodeContentPlaceHolder>12</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="c249c-208"><CodeContentPlaceHolder>12</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="c249c-209">Выражение await извлекает из `getLengthTask` целое значение, представляющее операнд оператора return в `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="c249c-209">The await expression retrieves from `getLengthTask` the integer value that’s the operand of the return statement in `AccessTheWebAsync`.</span></span> <span data-ttu-id="c249c-210">Следующая инструкция присваивает это значение `contentLength` переменной.</span><span class="sxs-lookup"><span data-stu-id="c249c-210">The following statement assigns that value to the `contentLength` variable.</span></span>  
  
<span data-ttu-id="c249c-211"><CodeContentPlaceHolder>13</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="c249c-211"><CodeContentPlaceHolder>13</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="c249c-212">На следующем рисунке показано возвращение управления из `AccessTheWebAsync` в `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="c249c-212">The following image shows the return of control from `AccessTheWebAsync` to `startButton_Click`.</span></span>  
  
 <span data-ttu-id="c249c-213">![ШЕСТОЙ шаг](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace&6;")</span><span class="sxs-lookup"><span data-stu-id="c249c-213">![Step SIX](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace-SIX")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c249c-214">См. также</span><span class="sxs-lookup"><span data-stu-id="c249c-214">See Also</span></span>  
 <span data-ttu-id="c249c-215">[Асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="c249c-215">[Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="c249c-216"> [Асинхронные типы возвращаемых значений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span><span class="sxs-lookup"><span data-stu-id="c249c-216"> [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span></span>  
<span data-ttu-id="c249c-217"> [Пошаговое руководство: Доступ к Интернету с помощью модификатора Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="c249c-217"> [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
<span data-ttu-id="c249c-218"> [Пример асинхронности: Поток управления в асинхронных программах (C# и Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255285)</span><span class="sxs-lookup"><span data-stu-id="c249c-218"> [Async Sample: Control Flow in Async Programs (C# and Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255285)</span></span>
