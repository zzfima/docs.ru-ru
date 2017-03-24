---
title: "Запуск нескольких асинхронных задач и их обработка по мере завершения (Visual Basic) | Документы Microsoft"
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
ms.assetid: 57ffb748-af40-4794-bedd-bdb7fea062de
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6fbf4611ecd64abfd016963dff887d82aad333b7
ms.lasthandoff: 03/13/2017

---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-visual-basic"></a>Запуск нескольких асинхронных задач и их обработка по мере завершения (Visual Basic)
С помощью <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>, можно запустить несколько задач одновременно и обрабатывать их один за другим, как они время завершения, а не их обработки в порядке, в котором они запущены.</xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>  
  
 В следующем примере запроса для создания коллекции задач. Каждая задача загружает содержимое указанной веб-сайта. В каждой итерации некоторое время цикла, ожидаемый вызов `WhenAny` возвращает задачи в коллекцию задач, сначала завершения его загрузки. Эта задача удаляется из коллекции и обработки. Цикл повторяется, пока коллекция не содержит несколько задач.  
  
> [!NOTE]
>  Для выполнения примеров, необходимо иметь Visual Studio 2012 или более поздней версии и платформы .NET Framework 4.5 или более новая версия вашего компьютера.  
  
## <a name="downloading-the-example"></a>Загрузка примера  
 Можно загрузить весь проект Windows Presentation Foundation (WPF) из [образец Async: нормально Настройка приложения](http://go.microsoft.com/fwlink/?LinkId=255046) и затем выполните следующие действия.  
  
1.  Распакуйте загруженный файл, а затем запустите Visual Studio.  
  
2.  В строке меню выберите **Файл**, **Открыть**, **Проект/Решение**.  
  
3.  В **открыть проект** диалоговом откройте папку, которая содержит пример кода, который можно распаковать и откройте файл решения (SLN) для AsyncFineTuningVB.  
  
4.  В **обозревателе решений**, откройте контекстное меню для **ProcessTasksAsTheyFinish** проекта, а затем выберите **Назначить запускаемым проектом**.  
  
5.  Нажмите клавишу F5, чтобы запустить проект.  
  
     Нажмите сочетание клавиш Ctrl + F5 для запуска проекта без его отладки.  
  
6.  Запустите проект несколько раз, чтобы убедиться, что загруженный длины не всегда отображаются в том же порядке.  
  
 Если вы не хотите загрузить проект, можно просмотреть файл MainWindow.xaml.vb в конце этого раздела.  
  
## <a name="building-the-example"></a>Построение примера  
 В этом примере добавляется код, который был разработан в [отмена оставшихся асинхронных задач после одного завершено (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) и использует тот же пользовательский Интерфейс.  
  
 Для построения примера самостоятельно, шаг за шагом, следуйте инструкциям в разделе «Загрузка пример», но выбрать **CancelAfterOneTask** как **запускаемый проект**. Добавьте в этот раздел, чтобы изменения `AccessTheWebAsync` метод в этом проекте. Изменения помечаются звездочками.  
  
 **CancelAfterOneTask** проект уже содержит запрос, при выполнении создает коллекцию задач. Каждый вызов `ProcessURLAsync` в следующем коде возвращает <xref:System.Threading.Tasks.Task%601>где `TResult` является целым числом.</xref:System.Threading.Tasks.Task%601>  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 В файле MainWindow.xaml.vb проекта, внесите следующие изменения в `AccessTheWebAsync` метод.  
  
-   Выполните запрос, применяя <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>вместо <xref:System.Linq.Enumerable.ToArray%2A>.</xref:System.Linq.Enumerable.ToArray%2A> </xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
-   Добавить некоторое время цикла, который выполняет следующие действия для каждой задачи в коллекции.  
  
    1.  Ожидает вызова `WhenAny` для определения первой задачи в коллекции, чтобы завершить его загрузки.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
    2.  Эта задача удаляет из коллекции.  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
    3.  Ждет `firstFinishedTask`, который возвращается при вызове `ProcessURLAsync`. `firstFinishedTask` Переменная <xref:System.Threading.Tasks.Task%601>где `TReturn` является целым числом.</xref:System.Threading.Tasks.Task%601> Задача уже завершена, но Ожидание получения длина загруженного веб-сайта, как показано в следующем примере.  
  
        ```vb  
        Dim length = Await firstFinishedTask  
        resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
        ```  
  
 Следует запустить проект несколько раз, чтобы убедиться, что загруженный длины не всегда отображаются в том же порядке.  
  
> [!CAUTION]
>  Можно использовать `WhenAny` в цикле, как описано в примере, чтобы устранить проблемы, включающие небольшое количество задач. Однако когда требуется обработка большого числа задач, другие методы будут более эффективны. Дополнительные сведения и примеры см. в разделе [обработки задач, как они завершения](http://go.microsoft.com/fwlink/?LinkId=260810).  
  
## <a name="complete-example"></a>Полный пример  
 Ниже приведен полный текст файла MainWindow.xaml.vb для примера. Звездочки пометить элементы, которые были добавлены в этом примере.  
  
 Обратите внимание, что необходимо добавить ссылку <xref:System.Net.Http>.</xref:System.Net.Http>  
  
 Можно загрузить проект из [образец Async: нормально Настройка приложения](http://go.microsoft.com/fwlink/?LinkId=255046).  
  
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
  
        ' ***Create a query that, when executed, returns a collection of tasks.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client, ct)  
  
        ' ***Use ToList to execute the query and start the download tasks.   
        Dim downloadTasks As List(Of Task(Of Integer)) = downloadTasksQuery.ToList()  
  
        ' ***Add a loop to process the tasks one at a time until none remain.  
        While downloadTasks.Count > 0  
            ' ***Identify the first task that completes.  
            Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
  
            ' ***Remove the selected task from the list so that you don't  
            ' process it more than once.  
            downloadTasks.Remove(firstFinishedTask)  
  
            ' ***Await the first completed task and display the results.  
            Dim length = Await firstFinishedTask  
            resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
        End While  
  
    End Function  
  
    ' Bundle the processing steps for a website into one async method.  
    Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        Return urlContents.Length  
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
  
' Length of the download:  226093  
' Length of the download:  412588  
' Length of the download:  175490  
' Length of the download:  204890  
' Length of the download:  158855  
' Length of the download:  145790  
' Length of the download:  44908  
' Downloads complete.  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Tasks.Task.WhenAny%2A></xref:System.Threading.Tasks.Task.WhenAny%2A>   
 [Настройка асинхронного приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)   
 [Асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Пример асинхронности: Точная настройка приложения](http://go.microsoft.com/fwlink/?LinkId=255046)
