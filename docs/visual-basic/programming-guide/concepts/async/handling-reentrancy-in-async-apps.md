---
title: Обработка повторного входа в асинхронных приложениях
ms.date: 07/20/2015
ms.assetid: ef3dc73d-13fb-4c5f-a686-6b84148bbffe
ms.openlocfilehash: cd8b43aa9b2373b5ce038e5007678778201f0746
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354270"
---
# <a name="handling-reentrancy-in-async-apps-visual-basic"></a>Handling Reentrancy in Async Apps (Visual Basic)

При включении асинхронного кода в приложение следует учесть и по возможности избежать повторного входа, под которым подразумевается повторный ввод асинхронной операции до ее завершения. Если не определить и не обработать возможности повторного входа, это может привести к непредвиденным результатам.

> [!NOTE]
> Для выполнения этого примера на компьютере должны быть установлены Visual Studio 2012 или более поздней версии и .NET Framework 4.5 или более поздней версии.

> [!NOTE]
> Версия протокола TLS 1.2 теперь является минимальной версией для использования в разработке приложений. Если приложение предназначено для более ранней версии .NET Framework, чем 4.7, обратитесь к следующей статье, чтобы ознакомиться с [рекомендациями по протоколу TLS в .NET Framework](../../../../framework/network-programming/tls.md) 

## <a name="BKMK_RecognizingReentrancy"></a> Распознавание поддержки повторного входа

В примере в этом разделе пользователь нажимает кнопку **Start**, чтобы инициировать асинхронное приложение, загружающее ряд веб-сайтов и вычисляющее общее число загруженных байтов. Синхронная версия примера реагирует одинаково, независимо от того, сколько раз пользователь нажмет кнопку, поскольку после первого раза поток пользовательского интерфейса игнорирует эти события до завершения выполнения приложения. При этом в асинхронном приложении поток пользовательского интерфейса продолжает реагировать, и можно ввести асинхронную операцию повторно до ее завершения.

В следующем примере показаны ожидаемые выходные данные, если пользователь нажимает кнопку **Start** только один раз. На экран выводится список загруженных веб-сайтов, размер которых указан в байтах. Общее число байтов отображается в конце списка.

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

Однако если пользователь нажимает кнопку больше одного раза, обработчик событий вызывается несколько раз и процесс загрузки будет каждый раз выполняться повторно. В результате одновременно запускается несколько асинхронных операций, получаемые выходные данные чередуются и счетчик общего числа байтов выдает неоднозначные результаты.

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
6. msdn.microsoft.com/library/ms404677.aspx               197325
3. msdn.microsoft.com/library/jj155761.aspx                29019
7. msdn.microsoft.com                                            42972
4. msdn.microsoft.com/library/hh290140.aspx               117152
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591

5. msdn.microsoft.com/library/hh524395.aspx                68959
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
6. msdn.microsoft.com/library/ms404677.aspx               197325
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
7. msdn.microsoft.com                                            42972
5. msdn.microsoft.com/library/hh524395.aspx                68959
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591

6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

Чтобы просмотреть код, создающий эти выходные данные, перейдите к концу раздела. Можно поэкспериментировать с кодом, загрузив решение на локальный компьютер и затем запустив проект WebsiteDownload или воспользовавшись кодом в конце этого раздела для создания собственного проекта. Дополнительные сведения и инструкции см. в разделе [Проверка и выполнение примера приложения](#BKMD_SettingUpTheExample).

## <a name="BKMK_HandlingReentrancy"></a> Обработка поддержки повторного входа

Обрабатывать повторный вход можно разными способами в зависимости от того, что требуется от приложения. В этом разделе представлены следующие примеры.

- [Отключение кнопки запуска](#BKMK_DisableTheStartButton)

  Отключение кнопки **Start** во время выполнения операции, чтобы пользователь не мог прервать ее выполнение.

- [Отмена и перезапуск операции](#BKMK_CancelAndRestart)

  Отмена выполнения любой операции, которая выполняется в тот момент, когда пользователь снова нажимает кнопку **Start**, с последующим продолжением операции, которая была запрошена последней.

- [Запуск нескольких операций и постановка выходных данных в очередь](#BKMK_RunMultipleOperations)

  Разрешение всем запрошенным операциям выполняться асинхронно и настройка согласования отображения выходных данных для вывода результатов каждой операции вместе и по порядку.

### <a name="BKMK_DisableTheStartButton"></a> Отключение кнопки запуска

Можно заблокировать кнопку **Start`StartButton_Click` во время операции, отключив кнопку в верхней части обработчика событий** . Затем можно повторно включить кнопку из блока `Finally` по завершении операции, чтобы пользователь мог запустить приложение повторно.

В следующем коде показаны эти изменения, которые помечены звездочками. Вы можете добавить изменения в код в конце этого раздела или скачать готовое приложение в разделе [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06). Имя проекта — DisableStartButton.

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
    ' This line is commented out to make the results clearer in the output.
    'ResultsTextBox.Text = ""

    ' ***Disable the Start button until the downloads are complete.
    StartButton.IsEnabled = False

    Try
        Await AccessTheWebAsync()

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."
    ' ***Enable the Start button in case you want to run the program again.
    Finally
        StartButton.IsEnabled = True

    End Try
End Sub
```

В результате этих изменений кнопка не будет реагировать в течение загрузки веб-сайтов методом `AccessTheWebAsync`, поэтому повторный вход в процесс будет невозможен.

### <a name="BKMK_CancelAndRestart"></a> Отмена и перезапуск операции

Вместо отключения кнопки **Start** можно оставить кнопку активной, но при этом, если пользователь нажмет эту кнопку еще раз, нужно отменить операцию, которая уже выполняется, и задать продолжение выполнения последней запущенной операции.

For more information about cancellation, see [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md).

Чтобы настроить этот сценарий, внесите следующие изменения в основной код, который содержится в разделе [Проверка и выполнение примера приложения](#BKMD_SettingUpTheExample). Также можно загрузить готовое приложение в разделе [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06). Этот проект называется CancelAndRestart.

1. Объявите переменную <xref:System.Threading.CancellationTokenSource>, `cts`, которая находится в области действия всех методов.

    ```vb
    Class MainWindow // Or Class MainPage

        ' *** Declare a System.Threading.CancellationTokenSource.
        Dim cts As CancellationTokenSource
    ```

2. В `StartButton_Click` определите, выполняется ли операция на данный момент. If the value of `cts` is `Nothing`, no operation is already active. If the value isn't `Nothing`, the operation that is already running is canceled.

    ```vb
    ' *** If a download process is already underway, cancel it.
    If cts IsNot Nothing Then
        cts.Cancel()
    End If
    ```

3. Задайте для `cts` другое значение, представляющее текущий процесс.

    ```vb
    ' *** Now set cts to cancel the current process if the button is chosen again.
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()
    cts = newCTS
    ```

4. At the end of `StartButton_Click`, the current process is complete, so set the value of `cts` back to `Nothing`.

    ```vb
    ' *** When the process completes, signal that another process can proceed.
    If cts Is newCTS Then
        cts = Nothing
    End If
    ```

В следующем коде показаны все изменения в `StartButton_Click`. Добавления помечены звездочками.

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)

    ' This line is commented out to make the results clearer.
    'ResultsTextBox.Text = ""

    ' *** If a download process is underway, cancel it.
    If cts IsNot Nothing Then
        cts.Cancel()
    End If

    ' *** Now set cts to cancel the current process if the button is chosen again.
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()
    cts = newCTS

    Try
        ' *** Send a token to carry the message if the operation is canceled.
        Await AccessTheWebAsync(cts.Token)

    Catch ex As OperationCanceledException
        ResultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."
    End Try

    ' *** When the process is complete, signal that another process can proceed.
    If cts Is newCTS Then
        cts = Nothing
    End If
End Sub
```

В `AccessTheWebAsync` внесите следующие изменения.

- Добавьте параметр, чтобы принимать токен отмены из `StartButton_Click`.

- Используйте метод <xref:System.Net.Http.HttpClient.GetAsync%2A> для загрузки веб-сайтов, так как `GetAsync` принимает аргумент <xref:System.Threading.CancellationToken>.

- Перед вызовом метода `DisplayResults` для отображения результатов для каждого загруженного веб-сайта проверьте `ct`, чтобы убедиться, что текущая операция не отменена.

 В следующем коде показаны эти изменения, которые помечены звездочками.

```vb
' *** Provide a parameter for the CancellationToken from StartButton_Click.
Private Async Function AccessTheWebAsync(ct As CancellationToken) As Task

    ' Declare an HttpClient object.
    Dim client = New HttpClient()

    ' Make a list of web addresses.
    Dim urlList As List(Of String) = SetUpURLList()

    Dim total = 0
    Dim position = 0

    For Each url In urlList
        ' *** Use the HttpClient.GetAsync method because it accepts a
        ' cancellation token.
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

        ' *** Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        ' *** Check for cancellations before displaying information about the
        ' latest site.
        ct.ThrowIfCancellationRequested()

        position += 1
        DisplayResults(url, urlContents, position)

        ' Update the total.
        total += urlContents.Length
    Next

    ' Display the total count for all of the websites.
    ResultsTextBox.Text &=
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
End Function
```

If you choose the **Start** button several times while this app is running, it should produce results that resemble the following output:

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               122505
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
Download canceled.

1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
Download canceled.

1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

Чтобы исключить частичные списки, раскомментируйте первую строку кода в `StartButton_Click`, чтобы очищать текстовое поле при каждом перезапуске операции.

### <a name="BKMK_RunMultipleOperations"></a> Запуск нескольких операций и постановка выходных данных в очередь

Третий пример является наиболее сложным, так как приложение запускает другую асинхронную операцию каждый раз, когда пользователь нажимает кнопку **Start**, и все операции выполняются до завершения. Все запрошенные операции загружают веб-сайты из списка асинхронно, однако выходные данные операций представляются последовательно. Получается, что фактические действия загрузки чередуются, как показывают выходные данные в разделе [Распознавание возникновения повторного входа](#BKMK_RecognizingReentrancy), однако список результатов для каждой группы отображается отдельно.

Операции совместно используют глобальную переменную <xref:System.Threading.Tasks.Task>, `pendingWork`, служащую привратником для процесса отображения.

Этот пример можно выполнить, вставив изменения в код в разделе [Сборка приложения](#BKMK_BuildingTheApp) или выполнив инструкции, приведенные в разделе [Загрузка приложения](#BKMK_DownloadingTheApp), чтобы скачать пример, а затем выполнить проект QueueResults.

Ниже показаны выходные данные, отображаемые в результате нажатия кнопки **Start** только один раз. Метка A указывает, что это результат первого нажатия кнопки **Start**. Нумерация показывает порядок отображения URL-адресов в списке целевых объектов для загрузки.

```console
#Starting group A.
#Task assigned for group A.

A-1. msdn.microsoft.com/library/hh191443.aspx                87389
A-2. msdn.microsoft.com/library/aa578028.aspx               209858
A-3. msdn.microsoft.com/library/jj155761.aspx                30870
A-4. msdn.microsoft.com/library/hh290140.aspx               119027
A-5. msdn.microsoft.com/library/hh524395.aspx                71260
A-6. msdn.microsoft.com/library/ms404677.aspx               199186
A-7. msdn.microsoft.com                                            53266
A-8. msdn.microsoft.com/library/ff730837.aspx               148020

TOTAL bytes returned:  918876

#Group A is complete.
```

Если пользователь нажимает кнопку **Start** три раза, приложение выдает результат, похожий на приведенный ниже. Информационные строки, начинающиеся с символа #, отслеживают ход выполнения приложения.

```console
#Starting group A.
#Task assigned for group A.

A-1. msdn.microsoft.com/library/hh191443.aspx                87389
A-2. msdn.microsoft.com/library/aa578028.aspx               207089
A-3. msdn.microsoft.com/library/jj155761.aspx                30870
A-4. msdn.microsoft.com/library/hh290140.aspx               119027
A-5. msdn.microsoft.com/library/hh524395.aspx                71259
A-6. msdn.microsoft.com/library/ms404677.aspx               199185

#Starting group B.
#Task assigned for group B.

A-7. msdn.microsoft.com                                            53266

#Starting group C.
#Task assigned for group C.

A-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  916095

B-1. msdn.microsoft.com/library/hh191443.aspx                87389
B-2. msdn.microsoft.com/library/aa578028.aspx               207089
B-3. msdn.microsoft.com/library/jj155761.aspx                30870
B-4. msdn.microsoft.com/library/hh290140.aspx               119027
B-5. msdn.microsoft.com/library/hh524395.aspx                71260
B-6. msdn.microsoft.com/library/ms404677.aspx               199186

#Group A is complete.

B-7. msdn.microsoft.com                                            53266
B-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  916097

C-1. msdn.microsoft.com/library/hh191443.aspx                87389
C-2. msdn.microsoft.com/library/aa578028.aspx               207089

#Group B is complete.

C-3. msdn.microsoft.com/library/jj155761.aspx                30870
C-4. msdn.microsoft.com/library/hh290140.aspx               119027
C-5. msdn.microsoft.com/library/hh524395.aspx                72765
C-6. msdn.microsoft.com/library/ms404677.aspx               199186
C-7. msdn.microsoft.com                                            56190
C-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  920526

#Group C is complete.
```

Группы B и C запускаются до завершения группы A, однако результаты для каждой группы отображаются отдельно. Все выходные данные для группы A отображаются сначала, затем идут все выходные данные для группы B и, наконец, для группы C. Приложение всегда отображает группы по порядку и для каждой группы всегда отображает сведения об отдельных веб-сайтах в порядке появления URL-адресов в списке URL-адресов.

Тем не менее невозможно предсказать порядок, в котором фактически происходит загрузка. После запуска нескольких групп все созданные ими задачи загрузки остаются активными. Не следует предполагать, что данные A-1 будут загружены до данных B-1, а данные A-1 будут загружены до данных A-2.

#### <a name="global-definitions"></a>Глобальные определения

Пример кода содержит объявление двух следующих глобальных переменных, доступных для всех методов.

```vb
Class MainWindow    ' Class MainPage in Windows Store app.

    ' ***Declare the following variables where all methods can access them.
    Private pendingWork As Task = Nothing
    Private group As Char = ChrW(AscW("A") - 1)
```

Переменная `Task`, `pendingWork`, отслеживает процесс отображения и предотвращает прерывание операции отображения одной группы другой группой. Символьная переменная, `group`, помечает выходные данные различных групп, чтобы гарантировать отображение результатов в ожидаемом порядке.

#### <a name="the-click-event-handler"></a>Обработчик событий нажатия

Обработчик событий `StartButton_Click` увеличивает букву группы каждый раз, когда пользователь нажимает кнопку **Start**. Затем обработчик вызывает метод `AccessTheWebAsync` для запуска операции загрузки.

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
    ' ***Verify that each group's results are displayed together, and that
    ' the groups display in order, by marking each group with a letter.
    group = ChrW(AscW(group) + 1)
    ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Starting group {0}.", group)

    Try
        ' *** Pass the group value to AccessTheWebAsync.
        Dim finishedGroup As Char = Await AccessTheWebAsync(group)

        ' The following line verifies a successful return from the download and
        ' display procedures.
        ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Group {0} is complete." & vbCrLf, finishedGroup)

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."

    End Try
End Sub
```

#### <a name="the-accessthewebasync-method"></a>Метод AccessTheWebAsync

В этом примере метод `AccessTheWebAsync` разбит на два метода. Первый метод, `AccessTheWebAsync`, запускает все задачи загрузки для группы и передает задаче `pendingWork` управление процессом отображения. Метод использует запрос LINQ и <xref:System.Linq.Enumerable.ToArray%2A> для запуска всех задач загрузки одновременно.

Затем метод `AccessTheWebAsync` вызывает метод `FinishOneGroupAsync` для ожидания завершения каждой загрузки и отображения ее длины.

Метод `FinishOneGroupAsync` возвращает задачу, которая назначена `pendingWork`, в `AccessTheWebAsync`. Это значение предотвращает прерывание другой операцией до завершения выполнения задачи.

```vb
Private Async Function AccessTheWebAsync(grp As Char) As Task(Of Char)

    Dim client = New HttpClient()

    ' Make a list of the web addresses to download.
    Dim urlList As List(Of String) = SetUpURLList()

    ' ***Kick off the downloads. The application of ToArray activates all the download tasks.
    Dim getContentTasks As Task(Of Byte())() =
        urlList.Select(Function(addr) client.GetByteArrayAsync(addr)).ToArray()

    ' ***Call the method that awaits the downloads and displays the results.
    ' Assign the Task that FinishOneGroupAsync returns to the gatekeeper task, pendingWork.
    pendingWork = FinishOneGroupAsync(urlList, getContentTasks, grp)

    ResultsTextBox.Text &=
        String.Format(vbCrLf & "#Task assigned for group {0}. Download tasks are active." & vbCrLf, grp)

    ' ***This task is complete when a group has finished downloading and displaying.
    Await pendingWork

    ' You can do other work here or just return.
    Return grp
End Function
```

#### <a name="the-finishonegroupasync-method"></a>Метод FinishOneGroupAsync

Этот метод выполняет циклический переход по задачам загрузки в группе, ожидая каждую из них, отображая длину загруженного веб-сайта и добавляя длину в общую сумму.

Первый оператор в `FinishOneGroupAsync` использует `pendingWork`, чтобы гарантировать, что ввод метода не помешает выполнению операции, которая уже находится в процессе отображения или в состоянии ожидания. Если такая операция выполняется, новая операция должна дождаться своей очереди.

```vb
Private Async Function FinishOneGroupAsync(urls As List(Of String), contentTasks As Task(Of Byte())(), grp As Char) As Task

    ' Wait for the previous group to finish displaying results.
    If pendingWork IsNot Nothing Then
        Await pendingWork
    End If

    Dim total = 0

    ' contentTasks is the array of Tasks that was created in AccessTheWebAsync.
    For i As Integer = 0 To contentTasks.Length - 1
        ' Await the download of a particular URL, and then display the URL and
        ' its length.
        Dim content As Byte() = Await contentTasks(i)
        DisplayResults(urls(i), content, i, grp)
        total += content.Length
    Next

    ' Display the total count for all of the websites.
    ResultsTextBox.Text &=
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
End Function
```

Этот пример можно выполнить, вставив изменения в код в разделе [Сборка приложения](#BKMK_BuildingTheApp) или выполнив инструкции, приведенные в разделе [Загрузка приложения](#BKMK_DownloadingTheApp), чтобы скачать пример, а затем выполнить проект QueueResults.

#### <a name="points-of-interest"></a>Интересующие точки

Информационные строки, начинающиеся с символа # в выходных данных, поясняют, как работает этот пример.

Выходные данные демонстрируют следующие схемы.

- Группу можно запустить, когда предыдущая группа отображает свои выходные данные, но отображение выходных данных предыдущей группы не прерывается.

  ```console
  #Starting group A.
  #Task assigned for group A. Download tasks are active.

  A-1. msdn.microsoft.com/library/hh191443.aspx                87389
  A-2. msdn.microsoft.com/library/aa578028.aspx               207089
  A-3. msdn.microsoft.com/library/jj155761.aspx                30870
  A-4. msdn.microsoft.com/library/hh290140.aspx               119037
  A-5. msdn.microsoft.com/library/hh524395.aspx                71260

  #Starting group B.
  #Task assigned for group B. Download tasks are active.

  A-6. msdn.microsoft.com/library/ms404677.aspx               199186
  A-7. msdn.microsoft.com                                            53078
  A-8. msdn.microsoft.com/library/ff730837.aspx               148010

  TOTAL bytes returned:  915919

  B-1. msdn.microsoft.com/library/hh191443.aspx                87388
  B-2. msdn.microsoft.com/library/aa578028.aspx               207089
  B-3. msdn.microsoft.com/library/jj155761.aspx                30870

  #Group A is complete.

  B-4. msdn.microsoft.com/library/hh290140.aspx               119027
  B-5. msdn.microsoft.com/library/hh524395.aspx                71260
  B-6. msdn.microsoft.com/library/ms404677.aspx               199186
  B-7. msdn.microsoft.com                                            53078
  B-8. msdn.microsoft.com/library/ff730837.aspx               148010

  TOTAL bytes returned:  915908
  ```

- The `pendingWork` task is `Nothing` at the start of `FinishOneGroupAsync` only for group A, which started first. Группа A еще не завершила выражение await, когда она достигает метода `FinishOneGroupAsync`. Таким образом, управление не возвращается `AccessTheWebAsync`, а первое присваивание задаче `pendingWork` не возникает.

- Следующие две строки всегда отображаются в выходных данных вместе. Код не прерывается нигде между запуском операции группы в обработчике `StartButton_Click` и назначением задачи для группы в `pendingWork`.

  ```console
  #Starting group B.
  #Task assigned for group B. Download tasks are active.
  ```

  После входа группы в обработчик `StartButton_Click` операция не завершает выражение await до входа операции в метод `FinishOneGroupAsync`. Таким образом, другие операции не могут получить контроль во время выполнения этого фрагмента кода.

## <a name="BKMD_SettingUpTheExample"></a> Проверка и выполнение примера приложения

Чтобы лучше понять пример приложения, его можно загрузить, построить самостоятельно или просмотреть код в конце этого раздела, не реализуя приложение.

> [!NOTE]
> Для выполнения этого примера как традиционного приложения Windows Presentation Foundation на компьютере должны быть установлены Visual Studio 2012 или более поздней версии и .NET Framework 4.5 или более поздней версии.

### <a name="BKMK_DownloadingTheApp"></a> Загрузка приложения

1. Скачайте сжатый файл в разделе [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).

2. Распакуйте загруженный файл, а затем запустите Visual Studio.

3. В строке меню выберите **Файл**, **Открыть**, **Проект/Решение**.

4. Перейдите к папке, содержащей распакованный пример кода, а затем откройте файл решения (SLN-файл).

5. В **обозревателе решений** откройте контекстное меню нужного проекта и выберите пункт **Назначить запускаемым проектом**.

6. Нажмите сочетание клавиш CTRL+F5, чтобы выполнить сборку и запуск проекта.

### <a name="BKMK_BuildingTheApp"></a> Сборка приложения

В следующих разделах приведен код для построения примера как приложения WPF.

##### <a name="to-build-a-wpf-app"></a>Построение приложения WPF

1. Запустите Visual Studio.

2. В строке меню выберите **Файл**, **Создать**, **Проект**.

     Откроется диалоговое окно **Новый проект** .

3. In the **Installed Templates** pane, expand **Visual Basic**, and then expand **Windows**.

4. В списке типов проектов выберите **Приложение WPF**.

5. Присвойте проекту имя `WebsiteDownloadWPF`, выберите .NET Framework версии 4.6 или более поздней, а затем нажмите кнопку **ОК**.

     В **обозревателе решений** появится новый проект.

6. В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .

     Если вкладка не отображается, откройте контекстное меню для MainWindow.xaml в **обозревателе решений** и выберите пункт **Просмотреть код**.

7. Замените код в представлении **XAML** файла MainWindow.xaml на следующий.

    ```xaml
    <Window x:Class="MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:WebsiteDownloadWPF"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        mc:Ignorable="d">

        <Grid Width="517" Height="360">
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="-1,0,0,0" VerticalAlignment="Top" Click="StartButton_Click" Height="53" Background="#FFA89B9B" FontSize="36" Width="518"  />
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" Margin="-1,53,0,-36" TextWrapping="Wrap" VerticalAlignment="Top" Height="343" FontSize="10" ScrollViewer.VerticalScrollBarVisibility="Visible" Width="518" FontFamily="Lucida Console" />
        </Grid>
    </Window>
    ```

     В представлении **Конструктор** файла MainWindow.xaml появится простое окно, содержащее кнопку и текстовое поле.

8. В **обозревателе решений** щелкните правой кнопкой мыши **Ссылки** и выберите **Добавить ссылку**.

     Добавьте ссылку на <xref:System.Net.Http>, если она еще не выбрана.

9. In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.

10. In MainWindow.xaml.vb , replace the code with the following code.

    ```vb
    ' Add the following Imports statements, and add a reference for System.Net.Http.
    Imports System.Net.Http
    Imports System.Threading

    Class MainWindow

        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
            System.Net.ServicePointManager.SecurityProtocol = System.Net.ServicePointManager.SecurityProtocol Or System.Net.SecurityProtocolType.Tls12

            ' This line is commented out to make the results clearer in the output.
            'ResultsTextBox.Text = ""

            Try
                Await AccessTheWebAsync()

            Catch ex As Exception
                ResultsTextBox.Text &= vbCrLf & "Downloads failed."

            End Try
        End Sub

        Private Async Function AccessTheWebAsync() As Task

            ' Declare an HttpClient object.
            Dim client = New HttpClient()

            ' Make a list of web addresses.
            Dim urlList As List(Of String) = SetUpURLList()

            Dim total = 0
            Dim position = 0

            For Each url In urlList
                ' GetByteArrayAsync returns a task. At completion, the task
                ' produces a byte array.
                Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

                position += 1
                DisplayResults(url, urlContents, position)

                ' Update the total.
                total += urlContents.Length
            Next

            ' Display the total count for all of the websites.
            ResultsTextBox.Text &=
                String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
        End Function

        Private Function SetUpURLList() As List(Of String)
            Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/hh191443.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/jj155761.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/hh524395.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
            Return urls
        End Function

        Private Sub DisplayResults(url As String, content As Byte(), pos As Integer)
            ' Display the length of each website. The string format is designed
            ' to be used with a monospaced font, such as Lucida Console or
            ' Global Monospace.

            ' Strip off the "http:'".
            Dim displayURL = url.Replace("https://", "")
            ' Display position in the URL list, the URL, and the number of bytes.
            ResultsTextBox.Text &= String.Format(vbCrLf & "{0}. {1,-58} {2,8}", pos, displayURL, content.Length)
        End Sub
    End Class
    ```

11. Нажмите сочетание клавиш CTRL+F5, чтобы запустить программу, а затем несколько раз нажмите кнопку **Start**.

12. Внесите изменения, описанные в разделах [Отключение кнопки запуска](#BKMK_DisableTheStartButton), [Отмена и перезапуск операции](#BKMK_CancelAndRestart) или [Запуск нескольких операций и постановка выходных данных в очередь](#BKMK_RunMultipleOperations) для обработки повторного входа.

## <a name="see-also"></a>См. также

- [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) (Пошаговое руководство. Доступ к веб-сайтам с помощью модификатора Async и оператора Await (Visual Basic))
- [Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
