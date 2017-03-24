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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 643fff648336c664961ad7956308acbaea262f61
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a>Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await (Visual Basic)
Можно написать асинхронные программы легко и интуитивно с помощью функций, которые были введены в [!INCLUDE[vs_dev11_long](../../../../csharp/includes/vs_dev11_long_md.md)]. Можно написать асинхронный код, который выглядит как синхронный, и позволить компилятору обрабатывать трудные функции обратного вызова и продолжения, которые обычно включает асинхронный код.  
  
 Дополнительные сведения о функции асинхронного см [асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 Это пошаговое руководство начинается с создания синхронного приложения Windows Presentation Foundation (WPF), которое суммирует число байтов в списке веб-сайтов. Затем в рамках руководства приложение преобразуется в асинхронное решение с помощью новых возможностей.  
  
 Если вы не хотите самостоятельно создавать приложения, можно загрузить «образец Async: доступ к Web пошагового руководства (C# и Visual Basic)» из [образцы кода разработчика](http://go.microsoft.com/fwlink/?LinkId=255191).  
  
 В этом пошаговом руководстве выполняются следующие задачи.  
  
-   [Создание приложения WPF](#CreateWPFApp)  
  
-   [Для разработки простого MainWindow WPF](#MainWindow)  
  
-   [Добавление ссылки](#AddRef)  
  
-   [Добавление необходимых операторов Imports](#ImportsState)  
  
-   [Создание синхронного приложения](#synchronous)  
  
-   [Чтобы проверить синхронного решения](#testSynch)  
  
-   [Чтобы преобразовать в асинхронный метод GetURLContents](#GetURLContents)  
  
-   [Чтобы преобразовать в асинхронный метод SumPageSizes](#SumPageSizes)  
  
-   [Чтобы преобразовать в асинхронный метод startButton_Click](#startButton)  
  
-   [Чтобы проверить асинхронных решений](#testAsynch)  
  
-   [Чтобы заменить метод GetURLContentsAsync метод .NET Framework](#GetURLContentsAsync)  
  
-   [Пример](#BKMK_CompleteCodeExamples)  
  
## <a name="prerequisites"></a>Предварительные требования  
 Visual Studio 2012 или более поздней версии необходимо установить на компьютере. Дополнительные сведения см. в разделе [веб-сайте Майкрософт](http://go.microsoft.com/fwlink/?LinkId=235233).  
  
###  <a name="CreateWPFApp"></a>Создание приложения WPF  
  
1.  Запустите Visual Studio.  
  
2.  В строке меню выберите **Файл**, **Создать**, **Проект**.  
  
     Откроется диалоговое окно **Новый проект** .  
  
3.  В **установленные шаблоны** области выберите Visual Basic и выберите **приложение WPF** в списке типов проектов.  
  
4.  В **имя** текста введите `AsyncExampleWPF`, а затем выберите **ОК** кнопки.  
  
     Появится новый проект в **обозревателе решений**.  
  
##  <a name="BKMK_DesignWPFMainWin"></a>   
###  <a name="MainWindow"></a>Для разработки простого MainWindow WPF  
  
1.  В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .  
  
2.  Если **элементов** окно не отображается, откройте **представление** меню и выберите **элементов**.  
  
3.  Добавить **кнопку** управления и **TextBox** управления **MainWindow** окна.  
  
4.  Выделите **TextBox** управления и в **свойства** установите следующие значения:  
  
    -   Задайте **имя** свойства `resultsTextBox`.  
  
    -   Задайте **высота** свойство до 250.  
  
    -   Задайте **ширина** значение 500.  
  
    -   На **текст** укажите моноширинный шрифт, например Lucida Console или глобальных Моноширинный.  
  
5.  Выделите **кнопку** управления и в **свойства** установите следующие значения:  
  
    -   Задайте **имя** свойства `startButton`.  
  
    -   Измените значение **содержимого** свойства из **кнопку** для **запустить**.  
  
6.  Поместите текстовое поле и кнопку, чтобы одновременно появляться в **MainWindow** окна.  
  
     Дополнительные сведения о конструкторе WPF XAML см. в разделе [Создание пользовательского интерфейса с помощью конструктора XAML](https://docs.microsoft.com/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).  
  
##  <a name="BKMK_AddReference"></a>   
###  <a name="AddRef"></a>Добавление ссылки  
  
1.  В **обозревателе**, выделите имя проекта.  
  
2.  В строке меню выберите **проекта**, **добавить ссылку**.  
  
     **Диспетчер ссылок** откроется диалоговое окно.  
  
3.  Вверху диалогового окна убедитесь, что проект предназначен для .NET Framework 4.5 или более поздней версии.  
  
4.  В **сборки** область, выберите **Framework** , если он еще не выбран.  
  
5.  В списке имен, выберите **System.Net.Http** флажок.  
  
6.  Выберите **ОК** кнопку, чтобы закрыть диалоговое окно.  
  
##  <a name="BKMK_AddStatesandDirs"></a>   
###  <a name="ImportsState"></a>Добавление необходимых операторов Imports  
  
1.  В **обозревателе решений**, откройте контекстное меню для MainWindow.xaml.vb и выберите **Просмотр кода**.  
  
2.  Добавьте следующие `Imports` в начало файла кода, если они еще не существуют.  
  
    ```vb  
    Imports System.Net.Http  
    Imports System.Net  
    Imports System.IO  
    ```  
  
##  <a name="BKMK_CreatSynchApp"></a>   
###  <a name="synchronous"></a>Создание синхронного приложения  
  
1.  Дважды щелкните в окне конструктора, файл MainWindow.xaml **запустить** кнопку, чтобы создать `startButton_Click` обработчика событий в файл MainWindow.xaml.vb.  
  
2.  В MainWindow.xaml.vb, скопируйте следующий код в теле `startButton_Click`:  
  
    ```vb  
    resultsTextBox.Clear()  
    SumPageSizes()  
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."  
    ```  
  
     Код вызывает метод, который управляет приложением `SumPageSizes` и выводит на экран сообщение, когда элемент управления возвращается к `startButton_Click`.  
  
3.  Код для синхронного решения содержит следующие четыре метода:  
  
    -   `SumPageSizes`, который получает список URL-адресов веб-страниц из `SetUpURLList`, а затем вызывает метод `GetURLContents` и `DisplayResults` для обработки каждого URL-адреса;  
  
    -   `SetUpURLList`, который создает и возвращает список веб-адресов;  
  
    -   `GetURLContents`, который загружает содержимое каждого веб-сайта и возвращает содержимое в виде массива байтов;  
  
    -   `DisplayResults`, который показывает число байтов в массиве байтов для каждого URL-адреса.  
  
     Скопируйте следующие четыре метода и затем вставить их в разделе `startButton_Click` обработчика событий в файл MainWindow.xaml.vb:  
  
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
###  <a name="testSynch"></a>Чтобы проверить синхронного решения  
  
1.  Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .  
  
     Программа должна выдать результаты, похожие на следующий список.  
  
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
  
     Обратите внимание, что вывод результатов на экран занимает несколько секунд. В течение этого времени поток пользовательского интерфейса заблокирован, пока он ожидает загрузку запрошенных ресурсов. В результате нельзя перемещать, максимизировать, минимизировать или даже закрыть окна после выбора **запустить** кнопки. Эти действия будут завершаться сбоем, пока не появятся результаты подсчета. Если веб-сайт не отвечает, вы не можете определить, на каком сайте произошел сбой. Трудно даже остановить ожидание и закрыть программу.  
  
##  <a name="BKMK_ConvertGtBtArr"></a>   
###  <a name="GetURLContents"></a>Чтобы преобразовать в асинхронный метод GetURLContents  
  
1.  Преобразование синхронного решения для асинхронных решений, лучше всего начать находится в `GetURLContents` из-за вызовов <xref:System.Net.HttpWebRequest>метод <xref:System.Net.HttpWebRequest.GetResponse%2A>и <xref:System.IO.Stream>метод <xref:System.IO.Stream.CopyTo%2A>— это когда приложение подключается к Интернету.</xref:System.IO.Stream.CopyTo%2A> </xref:System.IO.Stream> </xref:System.Net.HttpWebRequest.GetResponse%2A> </xref:System.Net.HttpWebRequest> Платформа .NET Framework упрощает преобразование путем предоставления асинхронных версий этих методов.  
  
     Дополнительные сведения о методах, которые используются в `GetURLContents`, <xref:System.Net.WebRequest>.</xref:System.Net.WebRequest> см.  
  
    > [!NOTE]
    >  По мере выполнения шагов в этом пошаговом руководстве возникают различные ошибки компилятора. Их можно игнорировать и продолжить процедуры пошагового руководства.  
  
     Измените метод, вызываемый в третьей строке `GetURLContents` из `GetResponse` асинхронным, основанные на задачах <xref:System.Net.WebRequest.GetResponseAsync%2A>метод.</xref:System.Net.WebRequest.GetResponseAsync%2A>  
  
    ```vb  
    Using response As WebResponse = webReq.GetResponseAsync()  
    ```  
  
2.  `GetResponseAsync`Возвращает <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> В этом случае *задач возвращаемой переменной*, `TResult`, имеет тип <xref:System.Net.WebResponse>.</xref:System.Net.WebResponse> Задача является обещанием создать фактический объект `WebResponse` после загрузки запрошенных данных и выполнения задачи до завершения.  
  
     Для получения `WebResponse` значения из задачи, применить [Await](../../../../visual-basic/language-reference/operators/await-operator.md) оператор для вызова `GetResponseAsync`, как показано в следующем коде.  
  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
     `Await` Оператор приостанавливает выполнение текущего метода `GetURLContents`, пока не будет завершена ожидаемая задача. На это время управление возвращается вызывающему объекту текущего метода. В этом примере текущим методом является `GetURLContents`, а вызывающим объектом — `SumPageSizes`. После завершения задачи создается обещанный объект `WebResponse` в качестве значения ожидаемой задачи, который присваивается переменной `response`.  
  
     The previous statement can be separated into the following two statements to clarify what happens.  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
     Вызов `webReq.GetResponseAsync` возвращает `Task(Of WebResponse)` или `Task<WebResponse>`. Затем `Await` оператор применяется к задачу, чтобы получить `WebResponse` значение.  
  
     If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the await operator is applied. For examples, see [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
3.  Так как вы добавили `Await` оператор в предыдущем шаге, возникает ошибка компилятора. Оператор может использоваться только в методы, помеченные атрибутом [Async](../../../../visual-basic/language-reference/modifiers/async.md) модификатор. Пропустите ошибку, повторяя действия по замене вызова `CopyTo` вызовом метода `CopyToAsync`.  
  
    -   Измените имя метода, который вызывается для <xref:System.IO.Stream.CopyToAsync%2A>.</xref:System.IO.Stream.CopyToAsync%2A>  
  
    -   Метод `CopyTo` или `CopyToAsync` копирует байты в свой аргумент `content` и не возвращает осмысленное значение. В синхронной версии вызов метода `CopyTo` — это просто оператор, который не возвращает значение. Асинхронная версия `CopyToAsync`, возвращает <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> Задача работает как Task(void) и позволяет ожидать метод. Примените `Await` или `await` к вызову `CopyToAsync`, как показано в следующем примере кода.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
         Предыдущий оператор сокращает две следующие строки кода.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
4.  Все, что остается сделать в `GetURLContents`, — это изменить подпись метода. Можно использовать `Await` оператор только в методы, помеченные атрибутом [Async](../../../../visual-basic/language-reference/modifiers/async.md) модификатор. Добавьте модификатор пометить метод как *асинхронный метод*, как показано в следующем коде.  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
5.  Возвращаемый тип асинхронный метод может быть только <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task> В Visual Basic метод должен являться функцией `Function`, возвращающей `Task` или `Task(Of T)`, либо он должен быть `Sub`. Как правило `Sub` метод используется только в асинхронный обработчик событий, где `Sub` является обязательным. В других случаях используйте `Task(T)` Если завершенного метода [вернуть](../../../../visual-basic/language-reference/statements/return-statement.md) инструкцию, возвращающую значение типа T, после чего использовать `Task` Если завершенного метода не возвращает допустимое значение.  
  
     Дополнительные сведения см. в разделе [возвращают типы Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
     Метод `GetURLContents` имеет оператор return, который возвращает массив байтов. Таким образом, тип возвращаемого значения асинхронной версии — Task(T), где T — массив байтов. Внесите следующие изменения в подпись метода.  
  
    -   Изменить тип возврата для `Task(Of Byte())`.  
  
    -   По соглашению об именовании асинхронные методы имеют имена, заканчивающиеся на Async, поэтому переименуйте метод в `GetURLContentsAsync`.  
  
     В следующем примере кода показаны эти изменения.  
  
    ```vb  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
    ```  
  
     После внесения этих изменений преобразование `GetURLContents` в асинхронный метод завершено.  
  
##  <a name="BKMK_ConvertSumPagSzs"></a>   
###  <a name="SumPageSizes"></a>Чтобы преобразовать в асинхронный метод SumPageSizes  
  
1.  Повторите шаги из предыдущей процедуры для `SumPageSizes`. Во-первых, преобразуйте вызов метода `GetURLContents` в вызов асинхронного метода.  
  
    -   Измените имя вызываемого метода с `GetURLContents` на `GetURLContentsAsync`, если это еще не сделано.  
  
    -   Применить `Await` к задаче, `GetURLContentsAsync` значение возвращает для получения байтов массива.  
  
     В следующем примере кода показаны эти изменения.  
  
    ```vb  
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
    ```  
  
     Предыдущее назначение сокращает две следующие строки кода.  
  
    ```vb  
    ' GetURLContentsAsync returns a task. At completion, the task   
    ' produces a byte array.   
    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)   
    'Dim urlContents As Byte() = Await getContentsTask  
  
    ```  
  
2.  Внесите следующие изменения в подпись метода.  
  
    -   Пометьте метод `Async` модификатор.  
  
    -   Добавьте в имя метода Async.  
  
    -   В этот раз нет возвращаемой переменной задачи T, поскольку `SumPageSizesAsync` не возвращает значение для T. (Не имеет метода `Return` инструкции.) Тем не менее метод должен возвращать `Task`, чтобы для него можно было задать ожидание. Таким образом, измените тип метода с `Sub` в `Function`. Тип значения, возвращаемого функцией, — `Task`.  
  
     В следующем примере кода показаны эти изменения.  
  
    ```vb  
    Private Async Function SumPageSizesAsync() As Task  
    ```  
  
     Преобразование `SumPageSizes` в `SumPageSizesAsync` завершено.  
  
##  <a name="BKMK_Cnvrtbttn1"></a>   
###  <a name="startButton"></a>Чтобы преобразовать в асинхронный метод startButton_Click  
  
1.  В обработчике событий измените имя вызываемого метода с `SumPageSizes` на `SumPageSizesAsync`, если это еще не сделано.  
  
2.  Поскольку `SumPageSizesAsync` является асинхронным методом, измените код в обработчике событий для ожидания результата.  
  
     Вызов `SumPageSizesAsync` отражает вызов `CopyToAsync` в `GetURLContentsAsync`. Вызов возвращает `Task`, а не `Task(T)`.  
  
     Как и в предыдущих процедурах, вызов можно преобразовать, используя один или два оператора. В следующем примере кода показаны эти изменения.  
  
    ```vb  
    '' One-step async call.  
    Await SumPageSizesAsync()  
  
    ' Two-step async call.  
    'Dim sumTask As Task = SumPageSizesAsync()  
    'Await sumTask  
    ```  
  
3.  Чтобы избежать случайного повторного ввода операции, добавьте следующий оператор в верхней части `startButton_Click` отключение **запустить** кнопки.  
  
    ```vb  
    ' Disable the button until the operation is complete.  
    startButton.IsEnabled = False  
    ```  
  
     Можно снова включить кнопку в конце обработчика событий.  
  
    ```vb  
    ' Reenable the button in case you want to run the operation again.  
    startButton.IsEnabled = True  
    ```  
  
     Дополнительные сведения о повторный вход в разделе [обработка повторного входа в асинхронных приложениях (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).  
  
4.  Наконец, добавьте `Async` модификатор объявление, чтобы обработчик событий может ожидать `SumPagSizesAsync`.  
  
    ```vb  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
    ```  
  
     Как правило, имена обработчиков событий не изменяются. Тип возвращаемого значения не изменено на `Task` поскольку обработчики событий должны быть `Sub` процедуры в Visual Basic.  
  
     Преобразование проекта из синхронного в асинхронный завершено.  
  
##  <a name="BKMK_testAsynchSolution"></a>   
###  <a name="testAsynch"></a>Чтобы проверить асинхронных решений  
  
1.  Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .  
  
2.  Появившиеся результаты должны напоминать результаты синхронного решения. Однако имеются следующие различия.  
  
    -   Все результаты не отображаются одновременно после завершения обработки. Например, обе программы содержат строку в `startButton_Click`, которая очищает текстовое поле. Целью является очистите поле между запусками, при выборе **запустить** кнопку второй раз, после появления одного набора результатов. В синхронной версии текстовое поле очищается перед отображением данных во второй раз, после завершения загрузки и высвобождения потока пользовательского интерфейса для выполнения других операций. В асинхронной версии текстовое поле снимается сразу после выбора **запустить** кнопки.  
  
    -   И что самое главное, поток пользовательского интерфейса не блокируется во время загрузки. Можно перемещать окно или изменять его размер во время загрузки, подсчета и отображения веб-ресурсов. Если один из веб-сайтов выполняется слишком медленно или не отвечает, можно отменить операцию, выбрав **закрыть** кнопку (x, в поле "красный" в правом верхнем углу).  
  
##  <a name="BKMK_ReplaceGetByteArrayAsync"></a>   
###  <a name="GetURLContentsAsync"></a>Чтобы заменить метод GetURLContentsAsync метод .NET Framework  
  
1.  Платформа .NET Framework 4.5 предоставляет много асинхронных методов, которые вы можете использовать. Одно из них, <xref:System.Net.Http.HttpClient>метод <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, только необходимые для этого пошагового руководства.</xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29> </xref:System.Net.Http.HttpClient> Его можно использовать вместо метода `GetURLContentsAsync`, созданного в предыдущей процедуре.  
  
     Первым шагом является создание объекта `HttpClient` в методе `SumPageSizesAsync`. Добавьте следующее объявление в начале метода.  
  
    ```vb  
    ' Declare an HttpClient object and increase the buffer size. The  
    ' default buffer size is 65,536.  
    Dim client As HttpClient =  
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
    ```  
  
2.  В `SumPageSizesAsync,` замените вызов метода `GetURLContentsAsync` вызовом метода `HttpClient`.  
  
    ```vb  
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
    ```  
  
3.  Удалите или прокомментируйте метод `GetURLContentsAsync`, который вы написали.  
  
4.  Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .  
  
     Поведение этой версии проекта должно соответствовать поведению, которое описывается в процедуре "Тестирование асинхронного решения"; при этом с вашей стороны требуется даже меньше усилий.  
  
##  <a name="BKMK_CompleteCodeExamples"></a>Пример  
 Следующий код содержит полный пример преобразования решения из синхронного в асинхронное с помощью написанного вами асинхронного метода `GetURLContentsAsync`. Обратите внимание, что он очень напоминает исходное синхронное решение.  
  
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
  
## <a name="see-also"></a>См. также  
 [Образец ASYNC: Доступ к Web пошагового руководства (C# и Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255191)   
 [Оператор await](../../../../visual-basic/language-reference/operators/await-operator.md)   
 [Async](../../../../visual-basic/language-reference/modifiers/async.md)   
 [Асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Асинхронные типы возвращаемых значений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)   
 [Асинхронное программирование, основанные на задачах (TAP)](http://go.microsoft.com/fwlink/?LinkId=204847)   
 [Практическое руководство: расширение Async пошагового руководства с использованием метода Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)   
 [Практическое руководство: параллельное выполнение нескольких веб-запросов с помощью модификатора Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)
