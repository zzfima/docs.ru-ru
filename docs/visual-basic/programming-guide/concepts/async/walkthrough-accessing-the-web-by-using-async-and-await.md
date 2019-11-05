---
title: Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 84fd047f-fab8-4d89-8ced-104fb7310a91
ms.openlocfilehash: feaa1e298cda852492e020a5fa81845fb887f102
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197025"
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a>Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await (Visual Basic)

Возможности Async и Await упрощают создание асинхронных программ. Можно написать асинхронный код, который выглядит как синхронный, и позволить компилятору обрабатывать трудные функции обратного вызова и продолжения, которые обычно включает асинхронный код.

Дополнительные сведения о функции Async см. в разделе [Асинхронное программирование с использованием Async и await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).

Это пошаговое руководство начинается с создания синхронного приложения Windows Presentation Foundation (WPF), которое суммирует число байтов в списке веб-сайтов. Затем в рамках руководства приложение преобразуется в асинхронное решение с помощью новых возможностей.

Если вы не хотите создавать приложение самостоятельно, вы можете скачать пример "Пример Async. Пошаговое руководство по доступу к интернету (C# и Visual Basic)" со страницы [примеров кода для разработчиков](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).

В этом пошаговом руководстве выполняются следующие задачи.

> [!div class="checklist"]
>
> - [Создание приложения WPF](#create-a-wpf-application)
> - [Проектирование простого WPF MainWindow](#design-a-simple-wpf-mainwindow)
> - [Добавление ссылки](#add-a-reference)
> - [Добавление необходимых операторов Imports](#add-necessary-imports-statements)
> - [Создание синхронного приложения](#create-a-synchronous-application)
> - [Тестирование синхронного решения](#test-the-synchronous-solution)
> - [Преобразование GetURLContents в асинхронный метод](#convert-geturlcontents-to-an-asynchronous-method)
> - [Преобразование SumPageSizes в асинхронный метод](#convert-sumpagesizes-to-an-asynchronous-method)
> - [Преобразование startButton_Click в асинхронный метод](#convert-startbutton_click-to-an-asynchronous-method)
> - [Тестирование асинхронного решения](#test-the-asynchronous-solution)
> - [Замените метод GetURLContentsAsync методом .NET Framework](#replace-the-geturlcontentsasync-method-with-a-net-framework-method)

Полный пример асинхронной работы см. в разделе " [Пример](#example) ".

## <a name="prerequisites"></a>Необходимые компоненты

На компьютере должна быть установлена среда Visual Studio 2012 или более поздней версии. Дополнительные сведения см. на странице [загрузки](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) Visual Studio.

## <a name="create-a-wpf-application"></a>Создание приложения WPF

1. Запустите Visual Studio.

2. В строке меню выберите **Файл**, **Создать**, **Проект**.

    Откроется диалоговое окно **Новый проект** .

3. В области **Установленные шаблоны** выберите Visual Basic, а затем выберите **приложение WPF** в списке типов проектов.

4. В текстовом поле **Имя** введите `AsyncExampleWPF` и нажмите кнопку **ОК**.

    В **обозревателе решений** появится новый проект.

## <a name="design-a-simple-wpf-mainwindow"></a>Разработка простого окна MainWindow WPF

1. В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .

2. Если окно **Панель элементов** не отображается, в меню **Вид** выберите пункт **Панель элементов**.

3. Добавьте элементы управления **Button** и **TextBox** в окно **MainWindow**.

4. Выделите элемент управления **TextBox** и в окне **Свойства** задайте указанные ниже значения.

    - Задайте для свойства **Имя** значение `resultsTextBox`.

    - Задайте для свойства **Высота** значение 250.

    - Задайте для свойства **Ширина** значение 500.

    - На вкладке **Текст** укажите моноширинный шрифт, например Lucida Console или Global Monospace.

5. Выделите элемент управления **Button** и в окне **Свойства** задайте указанные ниже значения.

    - Задайте для свойства **Имя** значение `startButton`.

    - Измените значение свойства **Содержимое** с **Button** на **Start**.

6. Поместите текстовое поле и кнопку так, чтобы оба элемента управления отображались в окне **MainWindow**.

    Дополнительные сведения о конструкторе XAML WPF см. в разделе [Создание пользовательского интерфейса с помощью конструктора XAML](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio).

## <a name="add-a-reference"></a>Добавление ссылки

1. В **обозревателе решений** выделите имя проекта.

2. В строке меню выберите **Проект**, **Добавить ссылку**.

    Откроется диалоговое окно **Диспетчер ссылок**.

3. Вверху диалогового окна убедитесь в том, что проект предназначен для платформы .NET Framework 4.5 или более поздней версии.

4. В области **Сборки** выберите **Платформа**, если этот вариант еще не выбран.

5. В списке имен установите флажок **System.Net.Http**.

6. Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.

## <a name="add-necessary-imports-statements"></a>Добавление необходимых операторов Imports

1. В **Обозреватель решений**откройте контекстное меню файла MainWindow. XAML. vb и выберите пункт **Просмотреть код**.

2. Добавьте следующие инструкции `Imports` в начало файла кода, если они еще не установлены.

    ```vb
    Imports System.Net.Http
    Imports System.Net
    Imports System.IO
    ```

## <a name="create-a-synchronous-application"></a>Создание синхронного приложения

1. В окне конструктора MainWindow. XAML дважды щелкните кнопку **Start** , чтобы создать обработчик событий `startButton_Click` в файле MainWindow. XAML. vb.

2. В файле MainWindow. XAML. vb скопируйте следующий код в текст `startButton_Click`:

    ```vb
    resultsTextBox.Clear()
    SumPageSizes()
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."
    ```

    Код вызывает метод, который управляет приложением `SumPageSizes` и выводит на экран сообщение, когда элемент управления возвращается к `startButton_Click`.

3. Код для синхронного решения содержит следующие четыре метода:

    - `SumPageSizes`, который получает список URL-адресов веб-страниц из `SetUpURLList`, а затем вызывает метод `GetURLContents` и `DisplayResults` для обработки каждого URL-адреса;

    - `SetUpURLList`, который создает и возвращает список веб-адресов;

    - `GetURLContents`, который загружает содержимое каждого веб-сайта и возвращает содержимое в виде массива байтов;

    - `DisplayResults`, который показывает число байтов в массиве байтов для каждого URL-адреса.

    Скопируйте следующие четыре метода и вставьте их в обработчик событий `startButton_Click` в файле MainWindow. XAML. vb:

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
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
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
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub
    ```

## <a name="test-the-synchronous-solution"></a>Тестирование синхронного решения

1. Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .

    Программа должна выдать результаты, похожие на следующий список:

    ```console
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

    Обратите внимание, что вывод результатов на экран занимает несколько секунд. В течение этого времени поток пользовательского интерфейса заблокирован, пока он ожидает загрузку запрошенных ресурсов. Соответственно, после нажатия кнопки **Start** окно нельзя перемещать, разворачивать, сворачивать или даже закрывать. Эти действия будут завершаться сбоем, пока не появятся результаты подсчета. Если веб-сайт не отвечает, вы не можете определить, на каком сайте произошел сбой. Трудно даже остановить ожидание и закрыть программу.

## <a name="convert-geturlcontents-to-an-asynchronous-method"></a>Преобразование GetURLContents в асинхронный метод

1. Для преобразования синхронного решения в асинхронное решение лучше начать с `GetURLContents` так как вызовы метода <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> и метода <xref:System.IO.Stream.CopyTo%2A?displayProperty=nameWithType> — это место, где приложение обращается к веб-приложению. Платформа .NET Framework упрощает преобразование путем предоставления асинхронных версий этих методов.

    Дополнительные сведения о методах, которые используются в `GetURLContents`, см. в разделе <xref:System.Net.WebRequest>.

    > [!NOTE]
    > По мере выполнения шагов в этом пошаговом руководстве возникают различные ошибки компилятора. Их можно игнорировать и продолжить процедуры пошагового руководства.

    Измените метод, который вызывается в третьей строке `GetURLContents` из `GetResponse`, асинхронным методом <xref:System.Net.WebRequest.GetResponseAsync%2A>, основанным на задачах.

    ```vb
    Using response As WebResponse = webReq.GetResponseAsync()
    ```

2. `GetResponseAsync` возвращает значение типа <xref:System.Threading.Tasks.Task%601>. В этом случае *переменная, возвращаемая задачей*, `TResult`, имеет тип <xref:System.Net.WebResponse>. Задача является обещанием создать фактический объект `WebResponse` после загрузки запрошенных данных и выполнения задачи до завершения.

    Чтобы получить значение `WebResponse` из задачи, примените оператор [await](../../../../visual-basic/language-reference/operators/await-operator.md) к вызову `GetResponseAsync`, как показано в следующем коде.

    ```vb
    Using response As WebResponse = Await webReq.GetResponseAsync()
    ```

    Оператор `Await` приостанавливает выполнение текущего метода `GetURLContents`, пока не будет завершена ожидаемая задача. На это время управление возвращается вызывающему объекту текущего метода. В этом примере текущим методом является `GetURLContents`, а вызывающим объектом — `SumPageSizes`. После завершения задачи создается обещанный объект `WebResponse` в качестве значения ожидаемой задачи, который присваивается переменной `response`.

    Предыдущий оператор можно разделить на следующие два оператора для уточнения выполняемых операций.

    ```vb
    Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()
    Using response As WebResponse = Await responseTask
    ```

    Вызов `webReq.GetResponseAsync` возвращает `Task(Of WebResponse)` или `Task<WebResponse>`. Затем к задаче применяется оператор `Await` для получения значения `WebResponse`.

    Если асинхронный метод выполняет какие-то действия, это не зависит от выполнения задачи, метод может продолжать свои действия между выполнениями этих двух операторов: после вызова асинхронного метода и перед применением оператора await. Примеры см. [в разделе Практическое руководство. Параллельное выполнение нескольких веб-запросов с помощью инструкций Async и await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) и [Практическое руководство. расширение асинхронного пошагового руководства с помощью Task. WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).

3. Из-за добавления оператора `Await` в предыдущем шаге возникает ошибка компилятора. Оператор можно использовать только в методах, помеченных модификатором [Async](../../../../visual-basic/language-reference/modifiers/async.md) . Пропустите ошибку, повторяя действия по замене вызова `CopyTo` вызовом метода `CopyToAsync`.

    - Измените имя метода, вызывающего <xref:System.IO.Stream.CopyToAsync%2A>.

    - Метод `CopyTo` или `CopyToAsync` копирует байты в свой аргумент `content` и не возвращает осмысленное значение. В синхронной версии вызов метода `CopyTo` — это просто оператор, который не возвращает значение. Асинхронная версия — `CopyToAsync` — возвращает <xref:System.Threading.Tasks.Task>. Задача работает как Task(void) и позволяет ожидать метод. Примените `Await` или `await` к вызову `CopyToAsync`, как показано в следующем примере кода.

        ```vb
        Await responseStream.CopyToAsync(content)
        ```

         Предыдущий оператор сокращает две следующие строки кода.

        ```vb
        ' CopyToAsync returns a Task, not a Task<T>.
        Dim copyTask As Task = responseStream.CopyToAsync(content)

        ' When copyTask is completed, content contains a copy of
        ' responseStream.
        Await copyTask
        ```

4. Все, что остается сделать в `GetURLContents`, — это изменить подпись метода. Оператор `Await` можно использовать только в методах, помеченных модификатором [Async](../../../../visual-basic/language-reference/modifiers/async.md) . Добавьте модификатор, чтобы пометить метод как *асинхронный*, как показано в приведенном ниже примере кода.

    ```vb
    Private Async Function GetURLContents(url As String) As Byte()
    ```

5. Тип возвращаемого значения асинхронного метода может быть только <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>. В Visual Basic метод должен являться функцией `Function`, возвращающей `Task` или `Task(Of T)`, либо он должен быть `Sub`. Как правило, метод `Sub` используется только в асинхронном обработчике событий, где требуется `Sub`. В других случаях используется `Task(T)`, если метод Completed имеет оператор [return](../../../../visual-basic/language-reference/statements/return-statement.md) , возвращающий значение типа t, и используется `Task`, если завершенный метод не возвращает осмысленное значение.

    Дополнительные сведения см. в разделе [асинхронные типы возвращаемых данных (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).

    Метод `GetURLContents` имеет оператор return, который возвращает массив байтов. Таким образом, тип возвращаемого значения асинхронной версии — Task(T), где T — массив байтов. Внесите следующие изменения в подпись метода.

    - Измените тип возвращаемого значения на `Task(Of Byte())`.

    - По соглашению об именовании асинхронные методы имеют имена, заканчивающиеся на Async, поэтому переименуйте метод в `GetURLContentsAsync`.

    В следующем примере кода показаны эти изменения.

    ```vb
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())
    ```

    После внесения этих изменений преобразование `GetURLContents` в асинхронный метод завершено.

## <a name="convert-sumpagesizes-to-an-asynchronous-method"></a>Преобразование SumPageSizes в асинхронный метод

1. Повторите шаги из предыдущей процедуры для `SumPageSizes`. Во-первых, преобразуйте вызов метода `GetURLContents` в вызов асинхронного метода.

    - Измените имя вызываемого метода с `GetURLContents` на `GetURLContentsAsync`, если это еще не сделано.

    - Примените оператор `Await` к задаче, возвращаемой методом `GetURLContentsAsync`, для получения значения байтового массива.

    В следующем примере кода показаны эти изменения.

    ```vb
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)
    ```

    Предыдущее назначение сокращает две следующие строки кода.

    ```vb
    ' GetURLContentsAsync returns a task. At completion, the task
    ' produces a byte array.
    Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
    Dim urlContents As Byte() = Await getContentsTask
    ```

2. Внесите следующие изменения в подпись метода.

    - Пометьте метод модификатором `Async`.

    - Добавьте в имя метода Async.

    - В настоящее время нет возвращаемой переменной задачи T, так как `SumPageSizesAsync` не возвращает значение для T. (метод не имеет `Return` инструкции.) Однако метод должен возвращать `Task` для ожидания. Поэтому измените тип метода с `Sub` на `Function`. Тип значения, возвращаемого функцией, — `Task`.

    В следующем примере кода показаны эти изменения.

    ```vb
    Private Async Function SumPageSizesAsync() As Task
    ```

    Преобразование `SumPageSizes` в `SumPageSizesAsync` завершено.

## <a name="convert-startbutton_click-to-an-asynchronous-method"></a>Преобразование startButton_Click в асинхронный метод

1. В обработчике событий измените имя вызываемого метода с `SumPageSizes` на `SumPageSizesAsync`, если это еще не сделано.

2. Поскольку `SumPageSizesAsync` является асинхронным методом, измените код в обработчике событий для ожидания результата.

    Вызов `SumPageSizesAsync` отражает вызов `CopyToAsync` в `GetURLContentsAsync`. Вызов возвращает `Task`, а не `Task(T)`.

    Как и в предыдущих процедурах, вызов можно преобразовать, используя один или два оператора. В следующем примере кода показаны эти изменения.

    ```vb
    ' One-step async call.
    Await SumPageSizesAsync()

    ' Two-step async call.
    Dim sumTask As Task = SumPageSizesAsync()
    Await sumTask
    ```

3. Чтобы предотвратить случайное повторное введение операции, добавьте следующий оператор в верхней части `startButton_Click`, чтобы отключить кнопку **Start**.

    ```vb
    ' Disable the button until the operation is complete.
    startButton.IsEnabled = False
    ```

    Можно снова включить кнопку в конце обработчика событий.

    ```vb
    ' Reenable the button in case you want to run the operation again.
    startButton.IsEnabled = True
    ```

    Дополнительные сведения о повторном входе см. в статье обработка повторного [входа в асинхронных приложениях (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).

4. Наконец, добавьте модификатор `Async` в объявление, чтобы обработчик событий мог ожидать `SumPagSizesAsync`.

    ```vb
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click
    ```

    Как правило, имена обработчиков событий не изменяются. Тип возвращаемого значения не изменен на `Task`, так как обработчики событий должны быть `Sub` процедурах в Visual Basic.

    Преобразование проекта из синхронного в асинхронный завершено.

## <a name="test-the-asynchronous-solution"></a>Тестирование асинхронного решения

1. Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .

2. Появившиеся результаты должны напоминать результаты синхронного решения. Однако имеются следующие различия.

    - Все результаты не отображаются одновременно после завершения обработки. Например, обе программы содержат строку в `startButton_Click`, которая очищает текстовое поле. Ее цель состоит в том, чтобы очистить текстовое поле между запусками при нажатии кнопки **Start** во второй раз после появления одного набора результатов. В синхронной версии текстовое поле очищается перед отображением данных во второй раз, после завершения загрузки и высвобождения потока пользовательского интерфейса для выполнения других операций. В асинхронной версии текстовое поле очищается сразу же после нажатия кнопки **Start**.

    - И что самое главное, поток пользовательского интерфейса не блокируется во время загрузки. Можно перемещать окно или изменять его размер во время загрузки, подсчета и отображения веб-ресурсов. Если один из веб-сайтов работает медленно или не отвечает, можно отменить операцию, нажав кнопку **Закрыть** (красный крестик в правом верхнем углу окна).

## <a name="replace-the-geturlcontentsasync-method-with-a-net-framework-method"></a>Замените метод GetURLContentsAsync методом .NET Framework

1. .NET Framework предоставляет множество асинхронных методов, которые можно использовать. Один из них, метод <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29?displayProperty=nameWithType>, делает то, что необходимо для этого пошагового руководства. Его можно использовать вместо метода `GetURLContentsAsync`, созданного в предыдущей процедуре.

    Первым шагом является создание объекта <xref:System.Net.Http.HttpClient> в методе `SumPageSizesAsync`. Добавьте следующее объявление в начале метода.

    ```vb
    ' Declare an HttpClient object and increase the buffer size. The
    ' default buffer size is 65,536.
    Dim client As HttpClient =
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}
    ```

2. В `SumPageSizesAsync,` замените вызов метода `GetURLContentsAsync` вызовом метода `HttpClient`.

    ```vb
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)
    ```

3. Удалите или прокомментируйте метод `GetURLContentsAsync`, который вы написали.

4. Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .

    Поведение этой версии проекта должно соответствовать поведению, которое описывается в процедуре "Тестирование асинхронного решения"; при этом с вашей стороны требуется даже меньше усилий.

## <a name="example"></a>Пример

Ниже приведен полный пример преобразованного асинхронного решения, использующего асинхронный метод `GetURLContentsAsync`. Обратите внимание, что он очень напоминает исходное синхронное решение.

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
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
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
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub

End Class
```

Следующий код содержит полный пример решения, использующего метод `HttpClient`, `GetByteArrayAsync`.

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

        ' Two-step async call.
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
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
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

- [Пример асинхронности. Пошаговое руководство "Доступ к сети" (C# и Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)
- [Оператор Await](../../../../visual-basic/language-reference/operators/await-operator.md)
- [Async](../../../../visual-basic/language-reference/modifiers/async.md)
- [Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
- [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) (Типы возвращаемых значений Async (Visual Basic))
- [Асинхронное программирование на основе задач (TAP)](https://go.microsoft.com/fwlink/?LinkId=204847)
- [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) (Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll (Visual Basic))
- [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) (Практическое руководство. Параллельное выполнение нескольких веб-запросов с использованием Async и Await (Visual Basic))
