---
title: Практическое руководство. Параллельное выполнение нескольких веб-запросов с использованием Async и Await
ms.date: 07/20/2015
ms.assetid: a894b99b-7cfd-4a38-adfb-20d24f986730
ms.openlocfilehash: 616efca79312883f17ba837d17a5ee9c97d15b34
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346140"
---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-visual-basic"></a>Инструкции. Параллельное выполнение нескольких веб-запросов с помощью Async и await (Visual Basic)

В асинхронном методе задачи запускаются в момент создания. Оператор [await](../../../../visual-basic/language-reference/operators/await-operator.md) применяется к задаче в точке метода, где обработка не может быть продолжена до завершения задачи. Часто задачи ожидаются в момент создания, как показано в следующем примере.

```vb
Dim result = Await someWebAccessMethodAsync(url)
```

Тем не менее можно отделить создание задачи от ее ожидания, если программа содержит другую работу, выполнение которой не зависит от завершения задачи.

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

Между моментом запуска задачи и ее ожиданием можно запустить другие задачи. Дополнительные задачи неявно выполняются параллельно, однако дополнительные потоки не создаются.

Следующая программа запускает три асинхронные веб-загрузки, а затем ожидает их в том порядке, в котором они вызываются. Обратите внимание, что при запуске программы задачи не всегда завершаются в том порядке, в котором они созданы и ожидаются. Они начинают выполняться в момент создания, и одна или несколько задач могут завершиться прежде, чем метод достигает выражения await.

> [!NOTE]
> Для выполнения этого проекта необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.

Другой пример, в котором одновременно запускается несколько задач, см. в разделе [Практическое руководство. расширение асинхронного пошагового руководства с помощью Task. WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).

Код для этого примера можно скачать на странице [Примеры кода от разработчиков](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e).

### <a name="to-set-up-the-project"></a>Настройка проекта

1. Чтобы настроить приложение WPF, выполните следующие действия. Подробные инструкции по выполнению этих действий см. в [разделе Пошаговое руководство. доступ к Интернету с помощью Async и await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).

    - Создайте приложение WPF, которое содержит текстовое поле и кнопку. Назовите кнопку `startButton`, а текстовое поле — `resultsTextBox`.

    - Добавьте ссылку для <xref:System.Net.Http>.

    - В файле MainWindow. XAML. vb добавьте инструкцию `Imports` для `System.Net.Http`.

### <a name="to-add-the-code"></a>Добавление кода

1. В окне конструктора MainWindow. XAML дважды щелкните кнопку, чтобы создать обработчик событий `startButton_Click` в файле MainWindow. XAML. vb.

2. Скопируйте приведенный ниже код и вставьте его в текст `startButton_Click` в файле MainWindow. XAML. vb.

    ```vb
    resultsTextBox.Clear()
    Await CreateMultipleTasksAsync()
    resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    ```

     Код вызывает асинхронный метод `CreateMultipleTasksAsync`, который управляет приложением.

3. Добавьте следующие вспомогательные методы в проект:

    - `ProcessURLAsync` использует метод <xref:System.Net.Http.HttpClient> для скачивания содержимого веб-сайта в виде массива байтов. Вспомогательный метод `ProcessURLAsync` затем отображает и возвращает длину массива.

    - `DisplayResults` показывает число байтов в массиве байтов для каждого URL-адреса. Эти выходные данные показывают, когда именно каждая задача завершает загрузку.

     Скопируйте следующие методы и вставьте их после обработчика событий `startButton_Click` в файле MainWindow. XAML. vb.

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
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub
    ```

4. Наконец, определите метод `CreateMultipleTasksAsync`, который выполняет следующие действия.

    - Этот метод объявляет объект `HttpClient`, который используется методом доступа <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> в `ProcessURLAsync`.

    - Метод создает и запускает три задачи типа <xref:System.Threading.Tasks.Task%601>, где `TResult` является целым числом. При завершении каждой задачи `DisplayResults` отображает URL-адрес и длину загруженного содержимого задачи. Поскольку задачи выполняются асинхронно, порядок, в котором отображаются результаты, может отличаться от порядка, в котором они были объявлены.

    - Метод ожидает завершения каждой задачи. Каждый оператор `Await` приостанавливает выполнение `CreateMultipleTasksAsync` до завершения выполнения ожидаемой задачи. Оператор также получает возвращаемое значение вызова `ProcessURLAsync` от каждой завершенной задачи.

    - После завершения задач и получения целочисленных значений метод суммирует длину веб-сайтов и отображает результат.

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
            ProcessURLAsync("https://msdn.microsoft.com", client)
        Dim download2 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)
        Dim download3 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client)

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

5. Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .

     Запустите программу несколько раз, чтобы убедиться, что три задачи не всегда завершаются в том же порядке, а порядок их завершения не обязательно совпадает с порядком, в котором они создаются и ожидаются.

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
            ProcessURLAsync("https://msdn.microsoft.com", client)
        Dim download2 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)
        Dim download3 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client)

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
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub
End Class
```

## <a name="see-also"></a>См. также

- [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) (Пошаговое руководство. Доступ к веб-сайтам с помощью модификатора Async и оператора Await (Visual Basic))
- [Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
- [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) (Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll (Visual Basic))
