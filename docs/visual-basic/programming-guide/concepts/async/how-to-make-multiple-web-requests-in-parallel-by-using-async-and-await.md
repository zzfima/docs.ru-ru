---
title: "Практическое руководство: параллельное выполнение нескольких веб-запросов с помощью модификатора Async и Await (Visual Basic) | Документы Microsoft"
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
ms.assetid: a894b99b-7cfd-4a38-adfb-20d24f986730
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
ms.openlocfilehash: e4c41cc3813a9f96d944d115c6aaa5c5842a629b
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-visual-basic"></a>Практическое руководство: параллельное выполнение нескольких веб-запросов с помощью модификатора Async и Await (Visual Basic)
В асинхронном методе задачи, запускаются, когда они создаются. [Await](../../../../visual-basic/language-reference/operators/await-operator.md) оператор применяется к задаче в точке в методе, где обработка не может продолжаться до завершения задачи. Часто задачи ожидают, как только будет создан, как показано в следующем примере.  
  
```vb  
Dim result = Await someWebAccessMethodAsync(url)  
```  
  
 Тем не менее можно разделить, создание из ожидает задачу, если программа содержит другую работу для выполнения задачи, не зависят от завершения задачи.  
  
```vb  
' The following line creates and starts the task.  
Dim myTask = someWebAccessMethodAsync(url)  
  
' While the task is running, you can do other work that does not depend  
' on the results of the task.  
' . . . . .  
  
' The application of Await suspends the rest of this method until the task is   
' complete.  
Dim result = Await myTask  
  
```  
  
 Между датами начала задачи и ожидает его, можно запустить другие задачи. Дополнительные задачи неявно параллельного выполнения, но создаются дополнительные потоки.  
  
 Следующая программа запускает три асинхронные веб-загрузки и затем ждет их в порядке, в котором они называются. Обратите внимание, при запуске программы, задачи не всегда окончания в том порядке, в котором они созданы и ожидать. Они начнут выполняются, когда они создаются и один или несколько задач может завершиться до метода выражений await.  
  
> [!NOTE]
>  Для завершения этого проекта, необходимо установить Visual Studio 2012 или более поздней версии и платформы .NET Framework 4.5 или более поздней версии, установленной на компьютере.  
  
 Другой пример, в котором запускается несколько задач одновременно, в разделе [как: расширение Async пошагового руководства, с использованием метода Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
 Можно загрузить код для этого примера из [образцы кода разработчика](http://go.microsoft.com/fwlink/?LinkId=254906).  
  
### <a name="to-set-up-the-project"></a>Настройка проекта  
  
1.  Чтобы настроить приложение WPF, выполните следующие действия. Можно найти подробные инструкции для выполнения этих действий в [Пошаговое руководство: доступ к Интернету с помощью Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).  
  
    -   Создание приложения WPF, содержит текстовое поле и кнопку. Имя создаваемой кнопки `startButton`и имя текстового поля `resultsTextBox`.  
  
    -   Добавить ссылку <xref:System.Net.Http>.</xref:System.Net.Http>  
  
    -   Добавьте в файл MainWindow.xaml.vb `Imports` инструкции для `System.Net.Http`.  
  
### <a name="to-add-the-code"></a>Добавление кода  
  
1.  В окне конструктора файл MainWindow.xaml, дважды щелкните кнопку, чтобы создать `startButton_Click` обработчика событий в файл MainWindow.xaml.vb.  
  
2.  Скопируйте следующий код и вставьте его в тексте `startButton_Click` в MainWindow.xaml.vb.  
  
    ```vb  
    resultsTextBox.Clear()  
    Await CreateMultipleTasksAsync()  
    resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    ```  
  
     Код вызывает асинхронный метод `CreateMultipleTasksAsync`, который управляет приложения.  
  
3.  Добавьте следующие методы поддержки в проект:  
  
    -   `ProcessURLAsync`использует <xref:System.Net.Http.HttpClient>метод для загрузки содержимого веб-сайта в виде массива байтов.</xref:System.Net.Http.HttpClient> Метод поддержки `ProcessURLAsync` затем отображает и возвращает длину массива.  
  
    -   `DisplayResults`Отображение числа байтов в массиве байтов для каждого URL-адреса. Это отображения показывает, когда каждая задача завершена загрузка.  
  
     Скопируйте следующие методы и вставьте их после `startButton_Click` обработчика событий в файл MainWindow.xaml.vb.  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
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
  
4.  Наконец, определите метод `CreateMultipleTasksAsync`, который выполняет следующие действия.  
  
    -   Объявляет метод `HttpClient` объекта, который требуется для доступа к методу <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>в `ProcessURLAsync`.</xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>  
  
    -   Метод создает и запускает три задачи типа <xref:System.Threading.Tasks.Task%601>, где `TResult` является целым числом.</xref:System.Threading.Tasks.Task%601> При завершении каждой задачи, `DisplayResults` отображает задачи URL-адрес и длина загруженного содержимого. Поскольку задачи выполняются асинхронно, порядок, в котором отображаются результаты могут отличаться от порядка, в котором они были объявлены.  
  
    -   Метод ждет завершения каждой задачи. Каждый `Await` оператор приостанавливает выполнение `CreateMultipleTasksAsync` до завершения выполнения ожидаемой задачи. Оператор также получает возвращаемое значение вызова `ProcessURLAsync` от каждой завершенной задачи.  
  
    -   После завершения задач и получения целые значения, метод суммирует длину веб-сайты и отображает результат.  
  
     Скопируйте следующий метод и вставьте его в решение.  
  
    ```vb  
    Private Async Function CreateMultipleTasksAsync() As Task  
  
        ' Declare an HttpClient object, and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Create and start the tasks. As each task finishes, DisplayResults   
        ' displays its length.  
        Dim download1 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com", client)  
        Dim download2 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)  
        Dim download3 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/67w7t67f.aspx", client)  
  
        ' Await each task.  
        Dim length1 As Integer = Await download1  
        Dim length2 As Integer = Await download2  
        Dim length3 As Integer = Await download3  
  
        Dim total As Integer = length1 + length2 + length3  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
    ```  
  
5.  Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .  
  
     Запустите программу несколько раз, чтобы убедиться, что три задачи не всегда завершается, в том же порядке и порядок их завершения обязательно не порядок, в котором они созданы и ожидать.  
  
## <a name="example"></a>Пример  
 Следующий код содержит полный пример.  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
        resultsTextBox.Clear()  
        Await CreateMultipleTasksAsync()  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Private Async Function CreateMultipleTasksAsync() As Task  
  
        ' Declare an HttpClient object, and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Create and start the tasks. As each task finishes, DisplayResults   
        ' displays its length.  
        Dim download1 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com", client)  
        Dim download2 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)  
        Dim download3 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/67w7t67f.aspx", client)  
  
        ' Await each task.  
        Dim length1 As Integer = Await download1  
        Dim length2 As Integer = Await download2  
        Dim length3 As Integer = Await download3  
  
        Dim total As Integer = length1 + length2 + length3  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
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
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство: Доступ к Интернету с помощью модификатора Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [Асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Практическое руководство: расширение Async пошагового руководства с использованием метода Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
