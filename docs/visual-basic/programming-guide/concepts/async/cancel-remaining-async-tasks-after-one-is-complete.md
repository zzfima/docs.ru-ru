---
title: "Отмена оставшихся асинхронных задач после один полный (Visual Basic) | Документы Microsoft"
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
ms.assetid: c928b5a1-622f-4441-8baf-adca1dde197f
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
ms.openlocfilehash: 1b70822edd972ac33614ab49faad6ff50b0e80b7
ms.lasthandoff: 03/13/2017

---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-visual-basic"></a>Отмена оставшихся асинхронных задач после один полный (Visual Basic)
С помощью <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>метод вместе с <xref:System.Threading.CancellationToken>, можно отменить все остальные задачи, если одна задача завершена.</xref:System.Threading.CancellationToken> </xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName> `WhenAny` Принимает в качестве аргумента, который представляет собой набор задач. Метод запускает все задачи и возвращает одну задачу. Задача завершается, когда все задачи в коллекции.  
  
 В этом примере показано, как использовать токен отмены в сочетании с `WhenAny` к удержанию первой задачи для завершения из коллекции задач и отменить оставшиеся задачи. Каждая задача загружает содержимое веб-сайта. Пример отображает длину содержимого для завершения первой загрузки и отменяет другие загружаемые файлы.  
  
> [!NOTE]
>  Для выполнения примеров, необходимо иметь Visual Studio 2012 или более поздней версии и платформы .NET Framework 4.5 или более новая версия вашего компьютера.  
  
## <a name="downloading-the-example"></a>Загрузка примера  
 Можно загрузить весь проект Windows Presentation Foundation (WPF) из [образец Async: нормально Настройка приложения](http://go.microsoft.com/fwlink/?LinkId=255046) и затем выполните следующие действия.  
  
1.  Распакуйте загруженный файл, а затем запустите Visual Studio.  
  
2.  В строке меню выберите **Файл**, **Открыть**, **Проект/Решение**.  
  
3.  В **открыть проект** диалоговом откройте папку, которая содержит пример кода, который можно распаковать и откройте файл решения (SLN) для AsyncFineTuningVB.  
  
4.  В **обозревателе решений**, откройте контекстное меню для **CancelAfterOneTask** проекта, а затем выберите **Назначить запускаемым проектом**.  
  
5.  Нажмите клавишу F5, чтобы запустить проект.  
  
     Нажмите сочетание клавиш Ctrl + F5 для запуска проекта без его отладки.  
  
6.  Запустите программу несколько раз для проверки различных загрузки закончит первой.  
  
 Если вы не хотите загрузить проект, можно просмотреть файл MainWindow.xaml.vb в конце этого раздела.  
  
## <a name="building-the-example"></a>Построение примера  
 В этом разделе добавляется в проект, который был разработан в [Отмена асинхронной задачи или списка задач](http://msdn.microsoft.com/library/d6e4e801-df64-4705-98fc-df725a577fb0) отменить список задач. В примере используется тот же пользовательский Интерфейс, хотя **отменить** кнопка не используется явно.  
  
 Для построения примера самостоятельно, шаг за шагом, следуйте инструкциям в разделе «Загрузка пример», но выбрать **CancelAListOfTasks** как **запускаемый проект**. К проекту, добавьте изменения в этом разделе.  
  
 В файле MainWindow.xaml.vb **CancelAListOfTasks** проект, запустите переход, перенос шагов обработки для каждого веб-сайта из цикла в `AccessTheWebAsync` следующие асинхронного метода.  
  
```vb  
' ***Bundle the processing steps for a website into one async method.  
Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)  
  
    ' GetAsync returns a Task(Of HttpResponseMessage).   
    Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
    ' Retrieve the website contents from the HttpResponseMessage.  
    Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
    Return urlContents.Length  
End Function  
```  
  
 В `AccessTheWebAsync`, в этом примере используется запрос, <xref:System.Linq.Enumerable.ToArray%2A>метода и `WhenAny` метод для создания и запуска массив задач.</xref:System.Linq.Enumerable.ToArray%2A> Применение `WhenAny` в массив возвращает одну задачу, когда ожидается, результатом которого является первой задачи до завершения задачи в массиве.  
  
 Внесите следующие изменения в `AccessTheWebAsync`. Звездочки отметить изменения в файле кода.  
  
1.  Закомментируйте или удалите цикла.  
  
2.  Создать запрос, который во время выполнения создает коллекцию базовых заданий. Каждый вызов `ProcessURLAsync` возвращает <xref:System.Threading.Tasks.Task%601>где `TResult` является целым числом.</xref:System.Threading.Tasks.Task%601>  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
3.  Вызов `ToArray` для выполнения запроса и запуска задачи. Применение `WhenAny` метод на следующем шаге будет выполнить запрос и запустить задачи без использования `ToArray`, но другие методы не могут. Наиболее безопасным способом является явно принудительного выполнения запроса.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
4.  Вызов `WhenAny` на коллекцию задач. `WhenAny`Возвращает `Task(Of Task(Of Integer))` или `Task<Task<int>>`.  То есть `WhenAny` Возвращает задачу, которая вычисляет единое `Task(Of Integer)` или `Task<int>` при ее ожидать. Одна задача — первая задача в коллекции, чтобы завершить. Сначала завершенной задачи назначены `firstFinishedTask`. Тип `firstFinishedTask` — <xref:System.Threading.Tasks.Task%601>где `TResult` является целым числом, поскольку это возвращаемый тип `ProcessURLAsync`.</xref:System.Threading.Tasks.Task%601>  
  
```vb  
' ***Call WhenAny and then await the result. The task that finishes   
' first is assigned to firstFinishedTask.  
Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
```  
  
5.  В этом примере вы заинтересованы только в задачу, которая завершает сначала. Таким образом, использовать <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>Отменить оставшиеся задачи.</xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>  
  
```vb  
' ***Cancel the rest of the downloads. You just want the first one.  
cts.Cancel()  
```  
  
6.  Наконец, await `firstFinishedTask` для получения длины загруженного содержимого.  
  
```vb  
Dim length = Await firstFinishedTask  
resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
```  
  
 Запустите программу несколько раз для проверки различных загрузки закончит первой.  
  
## <a name="complete-example"></a>Полный пример  
 Ниже приведен полный файл MainWindow.xaml.vb или MainWindow.xaml.cs для примера. Звездочки пометить элементы, которые были добавлены в этом примере.  
  
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
            resultsTextBox.Text &= vbCrLf & "Download complete."  
  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf  
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
  
        '' Comment out or delete the loop.  
        ''For Each url In urlList  
        ''    ' GetAsync returns a Task(Of HttpResponseMessage).   
        ''    ' Argument ct carries the message if the Cancel button is chosen.   
        ''    ' Note that the Cancel button can cancel all remaining downloads.  
        ''    Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ''    ' Retrieve the website contents from the HttpResponseMessage.  
        ''    Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ''    resultsTextBox.Text &=  
        ''        String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        ''Next  
  
        ' ***Create a query that, when executed, returns a collection of tasks.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client, ct)  
  
        ' ***Use ToArray to execute the query and start the download tasks.   
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
  
        ' ***Call WhenAny and then await the result. The task that finishes   
        ' first is assigned to firstFinishedTask.  
        Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
  
        ' ***Cancel the rest of the downloads. You just want the first one.  
        cts.Cancel()  
  
        ' ***Await the first completed task and display the results  
        ' Run the program several times to demonstrate that different  
        ' websites can finish first.  
        Dim length = Await firstFinishedTask  
        resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
    End Function  
  
    ' ***Bundle the processing steps for a website into one async method.  
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
  
' Length of the downloaded website:  158856  
  
' Download complete.  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Tasks.Task.WhenAny%2A></xref:System.Threading.Tasks.Task.WhenAny%2A>   
 [Настройка асинхронного приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)   
 [Асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Пример асинхронности: Точная настройка приложения](http://go.microsoft.com/fwlink/?LinkId=255046)
