---
title: "Отмена асинхронных задач после определенного периода времени (Visual Basic) | Документы Microsoft"
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
ms.assetid: a48045a3-6a99-42af-b824-af340f0b9a5d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9c2c7c09f9af7c9b7bdcb6411b6db6e2ca4984cb
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="cancel-async-tasks-after-a-period-of-time-visual-basic"></a><span data-ttu-id="17e4d-102">Отмена асинхронных задач после определенного периода времени (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17e4d-102">Cancel Async Tasks after a Period of Time (Visual Basic)</span></span>
<span data-ttu-id="17e4d-103">Можно отменить асинхронную операцию после определенного периода времени с использованием <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName>метод, если вы не хотите ждать завершения операции.</xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="17e4d-103">You can cancel an asynchronous operation after a period of time by using the  <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName> method if you don't want to wait for the operation to finish.</span></span> <span data-ttu-id="17e4d-104">Этот метод планирует отмену всех связанных задач, которые не выполнены в течение периода времени, который указывает `CancelAfter` выражение.</span><span class="sxs-lookup"><span data-stu-id="17e4d-104">This method schedules the cancellation of any associated tasks that aren’t complete within the period of time that’s designated by the `CancelAfter` expression.</span></span>  
  
 <span data-ttu-id="17e4d-105">В этом примере добавляется код, который был разработан в [Отмена асинхронной задачи или списка из задач (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) для загрузки списка веб-сайтов и отображения длину содержимого для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="17e4d-105">This example adds to the code that’s developed in [Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) to download a list of websites and to display the length of the contents of each one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17e4d-106">Для выполнения примеров, необходимо установить Visual Studio 2012 или более поздней версии и платформы .NET Framework 4.5 или более поздней версии, установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="17e4d-106">To run the examples, you must have Visual Studio 2012 or later and the .NET Framework 4.5 or later installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="17e4d-107">Загрузка примера</span><span class="sxs-lookup"><span data-stu-id="17e4d-107">Downloading the Example</span></span>  
 <span data-ttu-id="17e4d-108">Можно загрузить весь проект Windows Presentation Foundation (WPF) из [образец Async: нормально Настройка приложения](http://go.microsoft.com/fwlink/?LinkId=255046) и затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="17e4d-108">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="17e4d-109">Распакуйте загруженный файл, а затем запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="17e4d-109">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="17e4d-110">В строке меню выберите **Файл**, **Открыть**, **Проект/Решение**.</span><span class="sxs-lookup"><span data-stu-id="17e4d-110">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="17e4d-111">В **открыть проект** диалоговом откройте папку, которая содержит пример кода, который можно распаковать и откройте файл решения (SLN) для AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="17e4d-111">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="17e4d-112">В **обозревателе решений**, откройте контекстное меню для **CancelAfterTime** проекта, а затем выберите **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="17e4d-112">In **Solution Explorer**, open the shortcut menu for the **CancelAfterTime** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="17e4d-113">Нажмите клавишу F5, чтобы запустить проект.</span><span class="sxs-lookup"><span data-stu-id="17e4d-113">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="17e4d-114">Нажмите сочетание клавиш Ctrl + F5 для запуска проекта без его отладки.</span><span class="sxs-lookup"><span data-stu-id="17e4d-114">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6.  <span data-ttu-id="17e4d-115">Запустите программу несколько раз, чтобы убедиться, что выходные данные могут Показать выходные данные для всех веб-сайтов, веб-сайты не или некоторых веб-узлов.</span><span class="sxs-lookup"><span data-stu-id="17e4d-115">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span>  
  
 <span data-ttu-id="17e4d-116">Если вы не хотите загрузить проект, можно просмотреть файл MainWindow.xaml.vb в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="17e4d-116">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="17e4d-117">Построение примера</span><span class="sxs-lookup"><span data-stu-id="17e4d-117">Building the Example</span></span>  
 <span data-ttu-id="17e4d-118">В этом разделе добавляется в проект, который был разработан в [Отмена асинхронной задачи или списка из задач (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) отменить список задач.</span><span class="sxs-lookup"><span data-stu-id="17e4d-118">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) to cancel a list of tasks.</span></span> <span data-ttu-id="17e4d-119">В примере используется тот же пользовательский Интерфейс, хотя **отменить** кнопка не используется явно.</span><span class="sxs-lookup"><span data-stu-id="17e4d-119">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>  
  
 <span data-ttu-id="17e4d-120">Для построения примера самостоятельно, шаг за шагом, следуйте инструкциям в разделе «Загрузка пример», но выбрать **CancelAListOfTasks** как **запускаемый проект**.</span><span class="sxs-lookup"><span data-stu-id="17e4d-120">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="17e4d-121">К проекту, добавьте изменения в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="17e4d-121">Add the changes in this topic to that project.</span></span>  
  
 <span data-ttu-id="17e4d-122">Чтобы задать максимальное время, прежде чем задачи, помечаются как отмененные, добавьте вызов `CancelAfter` в `startButton_Click`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="17e4d-122">To specify a maximum time before the tasks are marked as canceled, add a call to `CancelAfter` to `startButton_Click`, as the following example shows.</span></span> <span data-ttu-id="17e4d-123">Добавление помеченные звездочками.</span><span class="sxs-lookup"><span data-stu-id="17e4d-123">The addition is marked with asterisks.</span></span>  
  
```vb  
Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)  
  
    ' Instantiate the CancellationTokenSource.  
    cts = New CancellationTokenSource()  
  
    resultsTextBox.Clear()  
  
    Try  
        ' ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You   
        ' can adjust the time.)  
        cts.CancelAfter(2500)  
  
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
```  
  
 <span data-ttu-id="17e4d-124">Запустите программу несколько раз, чтобы убедиться, что выходные данные могут Показать выходные данные для всех веб-сайтов, веб-сайты не или некоторых веб-узлов.</span><span class="sxs-lookup"><span data-stu-id="17e4d-124">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span> <span data-ttu-id="17e4d-125">Образец получает следующий результат.</span><span class="sxs-lookup"><span data-stu-id="17e4d-125">The following output is a sample.</span></span>  
  
```  
Length of the downloaded string: 35990.  
  
Length of the downloaded string: 407399.  
  
Length of the downloaded string: 226091.  
  
Downloads canceled.  
```  
  
## <a name="complete-example"></a><span data-ttu-id="17e4d-126">Полный пример</span><span class="sxs-lookup"><span data-stu-id="17e4d-126">Complete Example</span></span>  
 <span data-ttu-id="17e4d-127">Ниже приведен полный текст файла MainWindow.xaml.vb для примера.</span><span class="sxs-lookup"><span data-stu-id="17e4d-127">The following code is the complete text of the MainWindow.xaml.vb file for the example.</span></span> <span data-ttu-id="17e4d-128">Звездочки пометить элементы, которые были добавлены в этом примере.</span><span class="sxs-lookup"><span data-stu-id="17e4d-128">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="17e4d-129">Обратите внимание, что необходимо добавить ссылку <xref:System.Net.Http>.</xref:System.Net.Http></span><span class="sxs-lookup"><span data-stu-id="17e4d-129">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="17e4d-130">Можно загрузить проект из [образец Async: нормально Настройка приложения](http://go.microsoft.com/fwlink/?LinkId=255046).</span><span class="sxs-lookup"><span data-stu-id="17e4d-130">You can download the project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
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
            ' ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You   
            ' can adjust the time.)  
            cts.CancelAfter(2500)  
  
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
  
        ' Process each element in the list of web addresses.  
        For Each url In urlList  
            ' GetAsync returns a Task(Of HttpResponseMessage).   
            ' Argument ct carries the message if the Cancel button is chosen.   
            ' Note that the Cancel button can cancel all remaining downloads.  
            Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
            ' Retrieve the website contents from the HttpResponseMessage.  
            Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        Next  
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
  
' Length of the downloaded string: 35990.  
  
' Length of the downloaded string: 407399.  
  
' Length of the downloaded string: 226091.  
  
' Downloads canceled.  
```  
  
## <a name="see-also"></a><span data-ttu-id="17e4d-131">См. также</span><span class="sxs-lookup"><span data-stu-id="17e4d-131">See Also</span></span>  
 <span data-ttu-id="17e4d-132">[Асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="17e4d-132">[Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="17e4d-133"> [Пошаговое руководство: Доступ к Интернету с помощью модификатора Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="17e4d-133"> [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
<span data-ttu-id="17e4d-134"> [Отмена асинхронной задачи или списка задач (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="17e4d-134"> [Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) </span></span>  
<span data-ttu-id="17e4d-135"> [Настройка асинхронного приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span><span class="sxs-lookup"><span data-stu-id="17e4d-135"> [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span></span>  
<span data-ttu-id="17e4d-136"> [Пример асинхронности: Точная настройка приложения](http://go.microsoft.com/fwlink/?LinkId=255046)</span><span class="sxs-lookup"><span data-stu-id="17e4d-136"> [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046)</span></span>
