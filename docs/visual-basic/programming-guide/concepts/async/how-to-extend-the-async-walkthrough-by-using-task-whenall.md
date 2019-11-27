---
title: Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll
ms.date: 07/20/2015
ms.assetid: c06d386d-e996-4da9-bf3d-05a3b6c0a258
ms.openlocfilehash: 6df29a90ff0012564c6d966c8156434d25cacdb1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354245"
---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-visual-basic"></a>Практическое руководство. расширение асинхронного пошагового руководства с помощью Task. WhenAll (Visual Basic)

Вы можете повысить производительность асинхронного решения в [пошаговом руководстве: доступ к Интернету с помощью методов async и await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) с помощью метода <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Этот метод асинхронно ожидает несколько асинхронных операций, которые представлены в виде коллекции задач.

Как вы могли заметить в этом пошаговом руководстве, веб-сайты загружаются с разной скоростью. Иногда один из веб-сайтов работает слишком медленно, что задерживает все остальные загрузки. Во время работы асинхронных программ, созданных в этом пошаговом руководстве, программу можно с легкостью завершить, если нет необходимости в ожидании, но было бы лучше начать все загрузки одновременно и дать возможность более быстрым загрузкам продолжаться без ожидания более медленных.

Метод `Task.WhenAll` можно применить к коллекции задач. Метод `WhenAll`, примененный к коллекции, возвращает одну задачу, которая остается незавершенной до тех пор, пока не будет выполнена каждая задача из коллекции. Как видим, задачи выполняются параллельно, однако дополнительные потоки не создаются. Задачи могут выполняться в любом порядке.

> [!IMPORTANT]
> Следующие процедуры описывают расширения для асинхронных приложений, разработанных в [пошаговом руководстве: доступ к Интернету с помощью Async и await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Вы можете разработать приложения, выполнив пошаговое руководство или скачав код на странице [Примеры кода от разработчиков](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).
>
> Для выполнения этого примера на компьютере должна быть установлена среда Visual Studio 2012 или более поздней версии.

### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a>Добавление метода Task.WhenAll в решение GetURLContentsAsync

1. Добавьте метод `ProcessURLAsync` в первое приложение, разработанное в [пошаговом руководстве: доступ к Интернету с помощью Async и await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).

    - Если вы скачали код из [примеров кода разработчика](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), откройте проект асинквалксраугх, а затем добавьте `ProcessURLAsync` в файл MainWindow. XAML. vb.

    - Если вы разработали код, выполнив пошаговое руководство, добавьте `ProcessURLAsync` в приложение, которое включает метод `GetURLContentsAsync`. Файл MainWindow. XAML. vb для этого приложения является первым примером в разделе «полные примеры кода из пошагового руководства».

     Метод `ProcessURLAsync` объединяет действия в теле цикла `For Each` в `SumPageSizesAsync` в исходном пошаговом руководстве. Метод асинхронно скачивает содержимое указанного веб-сайта в виде массива байтов и затем отображает и возвращает длину массива байтов.

    ```vb
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)

        Dim byteArray = Await GetURLContentsAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function
    ```

2. Закомментируйте или удалите цикл `For Each` в `SumPageSizesAsync`, как показано в следующем коде.

    ```vb
    'Dim total = 0
    'For Each url In urlList

    '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)

    '    ' The previous line abbreviates the following two assignment statements.

    '    ' GetURLContentsAsync returns a task. At completion, the task
    '    ' produces a byte array.
    '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
    '    'Dim urlContents As Byte() = Await getContentsTask

    '    DisplayResults(url, urlContents)

    '    ' Update the total.
    '    total += urlContents.Length
    'Next
    ```

3. Создайте коллекцию задач. Следующий код определяет [запрос](../../../../visual-basic/programming-guide/concepts/linq/index.md), который при выполнении метода <xref:System.Linq.Enumerable.ToArray%2A> создает коллекцию задач, скачивающих содержимое каждого веб-сайта. Задачи запускаются при вычислении запроса.

     Добавьте следующий код в метод `SumPageSizesAsync` после объявления `urlList`.

    ```vb
    ' Create a query.
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
        From url In urlList Select ProcessURLAsync(url)

    ' Use ToArray to execute the query and start the download tasks.
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()
    ```

4. Примените `Task.WhenAll` к коллекции задач, `downloadTasks`. `Task.WhenAll` возвращает одну задачу, которая завершается после завершения всех задач в коллекции задач.

     В следующем примере выражение `Await` ожидает завершения одной задачи, возвращаемой `WhenAll`. Результат этого выражения – массив целых чисел, каждое из которых – размер загруженного веб-сайта. Добавьте следующий код в `SumPageSizesAsync` сразу после кода, добавленного на предыдущем шаге.

    ```vb
    ' Await the completion of all the running tasks.
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

    '' The previous line is equivalent to the following two statements.
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
    'Dim lengths As Integer() = Await whenAllTask
    ```

5. И, наконец, используйте метод <xref:System.Linq.Enumerable.Sum%2A> для вычисления суммы длин всех веб-сайтов. Добавьте следующую строку в `SumPageSizesAsync`.

    ```vb
    Dim total = lengths.Sum()
    ```

### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a>Добавление метода Task.WhenAll в решение HttpClient.GetByteArrayAsync

1. Добавьте следующую версию `ProcessURLAsync` во второе приложение, разработанное в [пошаговом руководстве: доступ к Интернету с помощью Async и await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).

    - Если вы скачали код из [примеров кода разработчика](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), откройте проект AsyncWalkthrough_HttpClient, а затем добавьте `ProcessURLAsync` в файл MainWindow. XAML. vb.

    - Если вы разработали код, выполнив пошаговое руководство, добавьте `ProcessURLAsync` в приложение, которое использует метод `HttpClient.GetByteArrayAsync`. Файл MainWindow. XAML. vb для этого приложения является вторым примером в разделе «полные примеры кода из пошагового руководства».

     Метод `ProcessURLAsync` объединяет действия в теле цикла `For Each` в `SumPageSizesAsync` в исходном пошаговом руководстве. Метод асинхронно скачивает содержимое указанного веб-сайта в виде массива байтов и затем отображает и возвращает длину массива байтов.

     Единственное отличие от метода `ProcessURLAsync` из предыдущей процедуры заключается в использовании экземпляра <xref:System.Net.Http.HttpClient>, `client`.

    ```vb
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)

        Dim byteArray = Await client.GetByteArrayAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function
    ```

2. Закомментируйте или удалите цикл `For Each` в `SumPageSizesAsync`, как показано в следующем коде.

    ```vb
    'Dim total = 0
    'For Each url In urlList
    '    ' GetByteArrayAsync returns a task. At completion, the task
    '    ' produces a byte array.
    '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

    '    ' The following two lines can replace the previous assignment statement.
    '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
    '    'Dim urlContents As Byte() = Await getContentsTask

    '    DisplayResults(url, urlContents)

    '    ' Update the total.
    '    total += urlContents.Length
    'Next
    ```

3. Определите [запрос](../../../../visual-basic/programming-guide/concepts/linq/index.md), который при выполнении метода <xref:System.Linq.Enumerable.ToArray%2A> создает коллекцию задач, скачивающих содержимое каждого веб-сайта. Задачи запускаются при вычислении запроса.

     Добавьте следующий код в метод `SumPageSizesAsync` после объявления `client` и `urlList`.

    ```vb
    ' Create a query.
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
        From url In urlList Select ProcessURLAsync(url, client)

    ' Use ToArray to execute the query and start the download tasks.
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()
    ```

4. Затем примените `Task.WhenAll` к коллекции задач, `downloadTasks`. `Task.WhenAll` возвращает одну задачу, которая завершается после завершения всех задач в коллекции задач.

     В следующем примере выражение `Await` ожидает завершения одной задачи, возвращаемой `WhenAll`. Результат выражения `Await` — массив целых чисел, каждое из которых представляет размер скачанного веб-сайта. Добавьте следующий код в `SumPageSizesAsync` сразу после кода, добавленного на предыдущем шаге.

    ```vb
    ' Await the completion of all the running tasks.
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

    '' The previous line is equivalent to the following two statements.
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
    'Dim lengths As Integer() = Await whenAllTask
    ```

5. И, наконец, используйте метод <xref:System.Linq.Enumerable.Sum%2A> для получения суммы длин всех веб-сайтов. Добавьте следующую строку в `SumPageSizesAsync`.

    ```vb
    Dim total = lengths.Sum()
    ```

### <a name="to-test-the-taskwhenall-solutions"></a>Тестирование решений Task.WhenAll

Для любого из решений нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Запуск**. Выходные данные должны быть похожи на выходные данные асинхронных решений в [пошаговом руководстве: доступ к Интернету с использованием Async и await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Тем не менее обратите внимание, что веб-сайты каждый раз отображаются в другом порядке.

## <a name="example"></a>Пример

В следующем коде показано расширение для проекта, использующее метод `GetURLContentsAsync` для скачивания содержимого из Интернета.

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        resultsTextBox.Clear()

        ' One-step async call.
        Await SumPageSizesAsync()

        '' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        ' Create a query.
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
            From url In urlList Select ProcessURLAsync(url)

        ' Use ToArray to execute the query and start the download tasks.
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()

        ' You can do other work here before awaiting.

        ' Await the completion of all the running tasks.
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

        '' The previous line is equivalent to the following two statements.
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
        'Dim lengths As Integer() = Await whenAllTask

        Dim total = lengths.Sum()

        'Dim total = 0
        'For Each url In urlList

        '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)

        '    ' The previous line abbreviates the following two assignment statements.

        '    ' GetURLContentsAsync returns a task. At completion, the task
        '    ' produces a byte array.
        '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
        '    'Dim urlContents As Byte() = Await getContentsTask

        '    DisplayResults(url, urlContents)

        '    ' Update the total.
        '    total += urlContents.Length
        'NextNext

        ' Display the total count for all of the web addresses.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
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

    ' The actions from the foreach loop are moved to this async method.
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)

        Dim byteArray = Await GetURLContentsAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function

    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        Using response As WebResponse = Await webReq.GetResponseAsync()
            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                ' CopyToAsync returns a Task, not a Task<T>.
                Await responseStream.CopyToAsync(content)
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

## <a name="example"></a>Пример

В следующем коде показано расширение для проекта, использующее метод `HttpClient.GetByteArrayAsync` для скачивания содержимого из Интернета.

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        resultsTextBox.Clear()

        '' One-step async call.
        Await SumPageSizesAsync()

        '' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Declare an HttpClient object and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        ' Create a query.
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
            From url In urlList Select ProcessURLAsync(url, client)

        ' Use ToArray to execute the query and start the download tasks.
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()

        ' You can do other work here before awaiting.

        ' Await the completion of all the running tasks.
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

        '' The previous line is equivalent to the following two statements.
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
        'Dim lengths As Integer() = Await whenAllTask

        Dim total = lengths.Sum()

        ''<snippet7>
        'Dim total = 0
        'For Each url In urlList
        '    ' GetByteArrayAsync returns a task. At completion, the task
        '    ' produces a byte array.
        '    '<snippet31>
        '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)
        '    '</snippet31>

        '    ' The following two lines can replace the previous assignment statement.
        '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
        '    'Dim urlContents As Byte() = Await getContentsTask

        '    DisplayResults(url, urlContents)

        '    ' Update the total.
        '    total += urlContents.Length
        'NextNext

        ' Display the total count for all of the web addresses.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://www.msdn.com",
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
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub

End Class
```

## <a name="see-also"></a>См. также

- <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>
- [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) (Пошаговое руководство. Доступ к веб-сайтам с помощью модификатора Async и оператора Await (Visual Basic))
