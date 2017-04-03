---
title: "Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: get-started-article
dev_langs:
- CSharp
ms.assetid: c95d8d71-5a98-4bf0-aaf4-45fed2ebbacd
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f2cd8842a9fcc0a075d6504c5f310d8de88dc09c
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-c"></a>Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await (C#)
Возможности, представленные в [!INCLUDE[vs_dev11_long](../../../../csharp/includes/vs_dev11_long_md.md)], упрощают написание асинхронных программ. Можно написать асинхронный код, который выглядит как синхронный, и позволить компилятору обрабатывать трудные функции обратного вызова и продолжения, которые обычно включает асинхронный код.  
  
 Дополнительные сведения о возможности Async см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](../../../../csharp/programming-guide/concepts/async/index.md).  
  
 Это пошаговое руководство начинается с создания синхронного приложения Windows Presentation Foundation (WPF), которое суммирует число байтов в списке веб-сайтов. Затем в рамках руководства приложение преобразуется в асинхронное решение с помощью новых возможностей.  
  
 Если вы не хотите создавать приложение самостоятельно, вы можете скачать пример "Пример Async. Пошаговое руководство по доступу к интернету (C# и Visual Basic)" со страницы [примеров кода для разработчиков](http://go.microsoft.com/fwlink/?LinkId=255191).  
  
 В этом пошаговом руководстве выполняются следующие задачи.  
  
-   [Создание приложения WPF](#CreateWPFApp)  
  
-   [Разработка простого окна MainWindow WPF](#MainWindow)  
  
-   [Добавление ссылки](#AddRef)  
  
-   [Добавление необходимых директив using](#usingDir)  
  
-   [Создание синхронного приложения](#synchronous)  
  
-   [Тестирование синхронного решения](#testSynch)  
  
-   [Преобразование GetURLContents в асинхронный метод](#GetURLContents)  
  
-   [Преобразование SumPageSizes в асинхронный метод](#SumPageSizes)  
  
-   [Преобразование startButton_Click в асинхронный метод](#startButton)  
  
-   [Тестирование асинхронного решения](#testAsynch)  
  
-   [Замена метода GetURLContentsAsync методом .NET Framework](#GetURLContentsAsync)  
  
-   [Пример](#BKMK_CompleteCodeExamples)  
  
## <a name="prerequisites"></a>Предварительные требования  
 На компьютере должна быть установлена среда Visual Studio 2012 или более поздней версии. Дополнительные сведения см. на [веб-сайте Майкрософт](http://go.microsoft.com/fwlink/?LinkId=235233).  
  
###  <a name="CreateWPFApp"></a> Создание приложения WPF  
  
1.  Запустите Visual Studio.  
  
2.  В строке меню выберите **Файл**, **Создать**, **Проект**.  
  
     Откроется диалоговое окно **Новый проект** .  
  
3.  В области **Установленные шаблоны** выберите "Visual C#", а затем в списке типов проектов выберите **Приложение WPF**.  
  
4.  В текстовом поле **Имя** введите `AsyncExampleWPF` и нажмите кнопку **ОК**.  
  
     В **обозревателе решений** появится новый проект.  
  
##  <a name="BKMK_DesignWPFMainWin"></a>   
###  <a name="MainWindow"></a> Разработка простого окна MainWindow WPF  
  
1.  В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .  
  
2.  Если окно **Панель элементов** не отображается, в меню **Вид** выберите пункт **Панель элементов**.  
  
3.  Добавьте элементы управления **Button** и **TextBox** в окно **MainWindow**.  
  
4.  Выделите элемент управления **TextBox** и в окне **Свойства** задайте указанные ниже значения.  
  
    -   Задайте для свойства **Имя** значение `resultsTextBox`.  
  
    -   Задайте для свойства **Высота** значение 250.  
  
    -   Задайте для свойства **Ширина** значение 500.  
  
    -   На вкладке **Текст** укажите моноширинный шрифт, например Lucida Console или Global Monospace.  
  
5.  Выделите элемент управления **Button** и в окне **Свойства** задайте указанные ниже значения.  
  
    -   Задайте для свойства **Имя** значение `startButton`.  
  
    -   Измените значение свойства **Содержимое** с **Button** на **Start**.  
  
6.  Поместите текстовое поле и кнопку так, чтобы оба элемента управления отображались в окне **MainWindow**.  
  
     Дополнительные сведения о конструкторе XAML WPF см. в разделе [Создание пользовательского интерфейса с помощью конструктора XAML](https://docs.microsoft.com/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).  
  
##  <a name="BKMK_AddReference"></a>   
###  <a name="AddRef"></a> Добавление ссылки  
  
1.  В **обозревателе решений** выделите имя проекта.  
  
2.  В строке меню выберите **Проект**, **Добавить ссылку**.  
  
     Откроется диалоговое окно **Диспетчер ссылок**.  
  
3.  Вверху диалогового окна убедитесь в том, что проект предназначен для платформы .NET Framework 4.5 или более поздней версии.  
  
4.  В области **Сборки** выберите **Платформа**, если этот вариант еще не выбран.  
  
5.  В списке имен установите флажок **System.Net.Http**.  
  
6.  Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.  
  
##  <a name="BKMK_AddStatesandDirs"></a>   
###  <a name="usingDir"></a> Добавление необходимых директив using  
  
1.  В **обозревателе решений** откройте контекстное меню для MainWindow.xaml.cs и выберите пункт **Просмотреть код**.  
  
2.  В начало файла с кодом добавьте указанные ниже директивы `using`, если они отсутствуют.  
  
    ```cs  
    using System.Net.Http;  
    using System.Net;  
    using System.IO;  
    ```  
  
##  <a name="BKMK_CreatSynchApp"></a>   
###  <a name="synchronous"></a> Создание синхронного приложения  
  
1.  В окне конструктора для MainWindow.xaml дважды щелкните кнопку **Start**, чтобы создать обработчик событий `startButton_Click` в файле MainWindow.xaml.cs.  
  
2.  В файле MainWindow.xaml.cs скопируйте следующий код в тело `startButton_Click`:  
  
    ```cs  
    resultsTextBox.Clear();  
    SumPageSizes();  
    resultsTextBox.Text += "\r\nControl returned to startButton_Click.";  
    ```  
  
     Код вызывает метод, который управляет приложением `SumPageSizes` и выводит на экран сообщение, когда элемент управления возвращается к `startButton_Click`.  
  
3.  Код для синхронного решения содержит следующие четыре метода:  
  
    -   `SumPageSizes`, который получает список URL-адресов веб-страниц из `SetUpURLList`, а затем вызывает метод `GetURLContents` и `DisplayResults` для обработки каждого URL-адреса;  
  
    -   `SetUpURLList`, который создает и возвращает список веб-адресов;  
  
    -   `GetURLContents`, который загружает содержимое каждого веб-сайта и возвращает содержимое в виде массива байтов;  
  
    -   `DisplayResults`, который показывает число байтов в массиве байтов для каждого URL-адреса.  
  
     Скопируйте следующие четыре метода, а затем вставьте их в обработчик событий `startButton_Click` в файле MainWindow.xaml.cs:  
  
    ```cs  
    private void SumPageSizes()  
    {  
        // Make a list of web addresses.  
        List<string> urlList = SetUpURLList();   
  
        var total = 0;  
        foreach (var url in urlList)  
        {  
            // GetURLContents returns the contents of url as a byte array.  
            byte[] urlContents = GetURLContents(url);  
  
            DisplayResults(url, urlContents);  
  
            // Update the total.  
            total += urlContents.Length;  
        }  
  
        // Display the total count for all of the web addresses.  
        resultsTextBox.Text +=   
            string.Format("\r\n\r\nTotal bytes returned:  {0}\r\n", total);  
    }  
  
    private List<string> SetUpURLList()  
    {  
        var urls = new List<string>   
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
        };  
        return urls;  
    }  
  
    private byte[] GetURLContents(string url)  
    {  
        // The downloaded resource ends up in the variable named content.  
        var content = new MemoryStream();  
  
        // Initialize an HttpWebRequest for the current URL.  
        var webReq = (HttpWebRequest)WebRequest.Create(url);  
  
        // Send the request to the Internet resource and wait for  
        // the response.  
        // Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.  
        using (WebResponse response = webReq.GetResponse())  
        {  
            // Get the data stream that is associated with the specified URL.  
            using (Stream responseStream = response.GetResponseStream())  
            {  
                // Read the bytes in responseStream and copy them to content.    
                responseStream.CopyTo(content);  
            }  
        }  
  
        // Return the result as a byte array.  
        return content.ToArray();  
    }  
  
    private void DisplayResults(string url, byte[] content)  
    {  
        // Display the length of each website. The string format   
        // is designed to be used with a monospaced font, such as  
        // Lucida Console or Global Monospace.  
        var bytes = content.Length;  
        // Strip off the "http://".  
        var displayURL = url.Replace("http://", "");  
        resultsTextBox.Text += string.Format("\n{0,-58} {1,8}", displayURL, bytes);  
    }  
    ```  
  
##  <a name="BKMK_TestSynchSol"></a>   
###  <a name="testSynch"></a> Тестирование синхронного решения  
  
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
  
     Обратите внимание, что вывод результатов на экран занимает несколько секунд. В течение этого времени поток пользовательского интерфейса заблокирован, пока он ожидает загрузку запрошенных ресурсов. Соответственно, после нажатия кнопки **Start** окно нельзя перемещать, разворачивать, сворачивать или даже закрывать. Эти действия будут завершаться сбоем, пока не появятся результаты подсчета. Если веб-сайт не отвечает, вы не можете определить, на каком сайте произошел сбой. Трудно даже остановить ожидание и закрыть программу.  
  
##  <a name="BKMK_ConvertGtBtArr"></a>   
###  <a name="GetURLContents"></a> Преобразование GetURLContents в асинхронный метод  
  
1.  Для преобразования синхронного решения в асинхронное лучше всего начать с `GetURLContents`, так как вызовы метода <xref:System.Net.HttpWebRequest.GetResponse%2A> <xref:System.Net.HttpWebRequest> и метода <xref:System.IO.Stream.CopyTo%2A> <xref:System.IO.Stream> используются тогда, когда приложение обращается к сети. Платформа .NET Framework упрощает преобразование путем предоставления асинхронных версий этих методов.  
  
     Дополнительные сведения о методах, которые используются в `GetURLContents`, см. в разделе <xref:System.Net.WebRequest>.  
  
    > [!NOTE]
    >  По мере выполнения шагов в этом пошаговом руководстве возникают различные ошибки компилятора. Их можно игнорировать и продолжить процедуры пошагового руководства.  
  
     Измените метод, который вызывается в третьей строке `GetURLContents` из `GetResponse`, на асинхронный метод <xref:System.Net.WebRequest.GetResponseAsync%2A>, основанный на задачах.  
  
    ```cs  
    using (WebResponse response = webReq.GetResponseAsync())  
    ```  
  
2.  `GetResponseAsync` возвращает <xref:System.Threading.Tasks.Task%601>. В этом случае *переменная, возвращаемая задачей*, `TResult`, имеет тип <xref:System.Net.WebResponse>. Задача является обещанием создать фактический объект `WebResponse` после загрузки запрошенных данных и выполнения задачи до завершения.  
  
     Для получения значения `WebResponse` из задачи примените оператор [await](../../../../csharp/language-reference/keywords/await.md) для вызова метода `GetResponseAsync`, как показано в приведенном ниже примере кода.  
  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
     Оператор `await` приостанавливает выполнение текущего метода `GetURLContents`, пока не будет завершена ожидаемая задача. На это время управление возвращается вызывающему объекту текущего метода. В этом примере текущим методом является `GetURLContents`, а вызывающим объектом — `SumPageSizes`. После завершения задачи создается обещанный объект `WebResponse` в качестве значения ожидаемой задачи, который присваивается переменной `response`.  
  
     The previous statement can be separated into the following two statements to clarify what happens.  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
     Вызов `webReq.GetResponseAsync` возвращает `Task(Of WebResponse)` или `Task<WebResponse>`. Затем оператор await применяется к задаче для получения значения `WebResponse`.  
  
     If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the `await` operator is applied. For examples, see [How to: Make Multiple Web Requests in Parallel by Using async and await (C#)](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
3.  Из-за добавления оператора `await` в предыдущем шаге возникает ошибка компилятора. Этот оператор можно использовать только в методах, помеченных модификатором [async](../../../../csharp/language-reference/keywords/async.md). Пропустите ошибку, повторяя действия по замене вызова `CopyTo` вызовом метода `CopyToAsync`.  
  
    -   Измените имя вызываемого метода на <xref:System.IO.Stream.CopyToAsync%2A>.  
  
    -   Метод `CopyTo` или `CopyToAsync` копирует байты в свой аргумент `content` и не возвращает осмысленное значение. В синхронной версии вызов метода `CopyTo` — это просто оператор, который не возвращает значение. Асинхронная версия (`CopyToAsync`) возвращает <xref:System.Threading.Tasks.Task>. Задача работает как Task(void) и позволяет ожидать метод. Примените `Await` или `await` к вызову `CopyToAsync`, как показано в следующем примере кода.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
         Предыдущий оператор сокращает две следующие строки кода.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
4.  Все, что остается сделать в `GetURLContents`, — это изменить подпись метода. Оператор `await` можно использовать только в методах, помеченных модификатором [async](../../../../csharp/language-reference/keywords/async.md). Добавьте модификатор, чтобы пометить метод как *асинхронный*, как показано в приведенном ниже примере кода.  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
5.  Тип возвращаемого значения асинхронного метода может быть только <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> или `void` в C#. Как правило, тип возвращаемого значения `void` используется только в асинхронном обработчике событий, где `void` является обязательным. В других случаях используется `Task(T)`, если завершенный метод имеет оператор [return](../../../../csharp/language-reference/keywords/return.md), возвращающий значение типа T, или `Task`, если завершенный метод не возвращает осмысленное значение. Можно представить тип возвращаемого значения `Task` как Task(void).  
  
     Дополнительные сведения см. в разделе [Асинхронные типы возвращаемых значений (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md).  
  
     Метод `GetURLContents` имеет оператор return, который возвращает массив байтов. Таким образом, тип возвращаемого значения асинхронной версии — Task(T), где T — массив байтов. Внесите следующие изменения в подпись метода.  
  
    -   Измените тип возвращаемого значения на `Task<byte[]>`.  
  
    -   По соглашению об именовании асинхронные методы имеют имена, заканчивающиеся на Async, поэтому переименуйте метод в `GetURLContentsAsync`.  
  
     В следующем примере кода показаны эти изменения.  
  
    ```cs  
    private async Task<byte[]> GetURLContentsAsync(string url)  
    ```  
  
     После внесения этих изменений преобразование `GetURLContents` в асинхронный метод завершено.  
  
##  <a name="BKMK_ConvertSumPagSzs"></a>   
###  <a name="SumPageSizes"></a> Преобразование SumPageSizes в асинхронный метод  
  
1.  Повторите шаги из предыдущей процедуры для `SumPageSizes`. Во-первых, преобразуйте вызов метода `GetURLContents` в вызов асинхронного метода.  
  
    -   Измените имя вызываемого метода с `GetURLContents` на `GetURLContentsAsync`, если это еще не сделано.  
  
    -   Примените оператор `await` к задаче, возвращаемой методом `GetURLContentsAsync`, для получения значения байтового массива.  
  
     В следующем примере кода показаны эти изменения.  
  
    ```cs  
    byte[] urlContents = await GetURLContentsAsync(url);  
    ```  
  
     Предыдущее назначение сокращает две следующие строки кода.  
  
    ```cs  
    // GetURLContentsAsync returns a Task<T>. At completion, the task  
    // produces a byte array.  
    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);  
    //byte[] urlContents = await getContentsTask;  
    ```  
  
2.  Внесите следующие изменения в подпись метода.  
  
    -   Пометьте метод модификатором `async`.  
  
    -   Добавьте в имя метода Async.  
  
    -   В этот раз нет возвращаемой переменной задачи T, поскольку `SumPageSizesAsync` не возвращает значение для T. (В этом методе нет оператора `return`.) Тем не менее метод должен возвращать `Task`, чтобы для него можно было задать ожидание. Поэтому измените тип возвращаемого значения метода с `void` на `Task`.  
  
     В следующем примере кода показаны эти изменения.  
  
    ```cs  
    private async Task SumPageSizesAsync()  
    ```  
  
     Преобразование `SumPageSizes` в `SumPageSizesAsync` завершено.  
  
##  <a name="BKMK_Cnvrtbttn1"></a>   
###  <a name="startButton"></a> Преобразование startButton_Click в асинхронный метод  
  
1.  В обработчике событий измените имя вызываемого метода с `SumPageSizes` на `SumPageSizesAsync`, если это еще не сделано.  
  
2.  Поскольку `SumPageSizesAsync` является асинхронным методом, измените код в обработчике событий для ожидания результата.  
  
     Вызов `SumPageSizesAsync` отражает вызов `CopyToAsync` в `GetURLContentsAsync`. Вызов возвращает `Task`, а не `Task(T)`.  
  
     Как и в предыдущих процедурах, вызов можно преобразовать, используя один или два оператора. В следующем примере кода показаны эти изменения.  
  
    ```cs  
    // One-step async call.  
    await SumPageSizesAsync();  
  
    // Two-step async call.  
    //Task sumTask = SumPageSizesAsync();  
    //await sumTask;  
    ```  
  
3.  Чтобы предотвратить случайное повторное введение операции, добавьте следующий оператор в верхней части `startButton_Click`, чтобы отключить кнопку **Start**.  
  
    ```cs  
    // Disable the button until the operation is complete.  
    startButton.IsEnabled = false;  
    ```  
  
     Можно снова включить кнопку в конце обработчика событий.  
  
    ```cs  
    // Reenable the button in case you want to run the operation again.  
    startButton.IsEnabled = true;  
    ```  
  
     Дополнительные сведения о повторном входе см. в разделе [Обработка повторного входа в асинхронных приложениях (C#)](../../../../csharp/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).  
  
4.  Наконец, добавьте модификатор `async` в объявление, чтобы обработчик событий мог ожидать `SumPagSizesAsync`.  
  
    ```cs  
    private async void startButton_Click(object sender, RoutedEventArgs e)  
    ```  
  
     Как правило, имена обработчиков событий не изменяются. Тип возвращаемого значения не изменяется на `Task`, так как обработчики событий должны возвращать `void`.  
  
     Преобразование проекта из синхронного в асинхронный завершено.  
  
##  <a name="BKMK_testAsynchSolution"></a>   
###  <a name="testAsynch"></a> Тестирование асинхронного решения  
  
1.  Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .  
  
2.  Появившиеся результаты должны напоминать результаты синхронного решения. Однако имеются следующие различия.  
  
    -   Все результаты не отображаются одновременно после завершения обработки. Например, обе программы содержат строку в `startButton_Click`, которая очищает текстовое поле. Ее цель состоит в том, чтобы очистить текстовое поле между запусками при нажатии кнопки **Start** во второй раз после появления одного набора результатов. В синхронной версии текстовое поле очищается перед отображением данных во второй раз, после завершения загрузки и высвобождения потока пользовательского интерфейса для выполнения других операций. В асинхронной версии текстовое поле очищается сразу же после нажатия кнопки **Start**.  
  
    -   И что самое главное, поток пользовательского интерфейса не блокируется во время загрузки. Можно перемещать окно или изменять его размер во время загрузки, подсчета и отображения веб-ресурсов. Если один из веб-сайтов работает медленно или не отвечает, можно отменить операцию, нажав кнопку **Закрыть** (красный крестик в правом верхнем углу окна).  
  
##  <a name="BKMK_ReplaceGetByteArrayAsync"></a>   
###  <a name="GetURLContentsAsync"></a> Замена GetURLContentsAsync методом .NET Framework  
  
1.  Платформа .NET Framework 4.5 предоставляет много асинхронных методов, которые вы можете использовать. Один из них, метод <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29> класса <xref:System.Net.Http.HttpClient>, выполняет то, что нужно для этого пошагового руководства. Его можно использовать вместо метода `GetURLContentsAsync`, созданного в предыдущей процедуре.  
  
     Первым шагом является создание объекта `HttpClient` в методе `SumPageSizesAsync`. Добавьте следующее объявление в начале метода.  
  
    ```cs  
    // Declare an HttpClient object and increase the buffer size. The  
    // default buffer size is 65,536.  
    HttpClient client =  
        new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
    ```  
  
2.  В `SumPageSizesAsync,` замените вызов метода `GetURLContentsAsync` вызовом метода `HttpClient`.  
  
    ```  
    byte[] urlContents = await client.GetByteArrayAsync(url);  
    ```  
  
3.  Удалите или прокомментируйте метод `GetURLContentsAsync`, который вы написали.  
  
4.  Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .  
  
     Поведение этой версии проекта должно соответствовать поведению, которое описывается в процедуре "Тестирование асинхронного решения"; при этом с вашей стороны требуется даже меньше усилий.  
  
##  <a name="BKMK_CompleteCodeExamples"></a> Пример  
 Следующий код содержит полный пример преобразования решения из синхронного в асинхронное с помощью написанного вами асинхронного метода `GetURLContentsAsync`. Обратите внимание, что он очень напоминает исходное синхронное решение.  
  
```cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Threading.Tasks;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Documents;  
using System.Windows.Input;  
using System.Windows.Media;  
using System.Windows.Media.Imaging;  
using System.Windows.Navigation;  
using System.Windows.Shapes;  
  
// Add the following using directives, and add a reference for System.Net.Http.  
using System.Net.Http;  
using System.IO;  
using System.Net;  
  
namespace AsyncExampleWPF  
{  
    public partial class MainWindow : Window  
    {  
        public MainWindow()  
        {  
            InitializeComponent();  
        }  
  
        private async void startButton_Click(object sender, RoutedEventArgs e)  
        {  
            // Disable the button until the operation is complete.  
            startButton.IsEnabled = false;  
  
            resultsTextBox.Clear();  
  
            // One-step async call.  
            await SumPageSizesAsync();  
  
            // Two-step async call.  
            //Task sumTask = SumPageSizesAsync();  
            //await sumTask;  
  
            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";  
  
            // Reenable the button in case you want to run the operation again.  
            startButton.IsEnabled = true;  
        }  
  
        private async Task SumPageSizesAsync()  
        {  
            // Make a list of web addresses.  
            List<string> urlList = SetUpURLList();  
  
            var total = 0;  
  
            foreach (var url in urlList)  
            {  
                byte[] urlContents = await GetURLContentsAsync(url);  
  
                // The previous line abbreviates the following two assignment statements.  
  
                // GetURLContentsAsync returns a Task<T>. At completion, the task  
                // produces a byte array.  
                //Task<byte[]> getContentsTask = GetURLContentsAsync(url);  
                //byte[] urlContents = await getContentsTask;  
  
                DisplayResults(url, urlContents);  
  
                // Update the total.            
                total += urlContents.Length;  
            }  
            // Display the total count for all of the websites.  
            resultsTextBox.Text +=  
                string.Format("\r\n\r\nTotal bytes returned:  {0}\r\n", total);  
        }  
  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>   
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
            };  
            return urls;  
        }  
  
        private async Task<byte[]> GetURLContentsAsync(string url)  
        {  
            // The downloaded resource ends up in the variable named content.  
            var content = new MemoryStream();  
  
            // Initialize an HttpWebRequest for the current URL.  
            var webReq = (HttpWebRequest)WebRequest.Create(url);  
  
            // Send the request to the Internet resource and wait for  
            // the response.                  
            using (WebResponse response = await webReq.GetResponseAsync())  
  
            // The previous statement abbreviates the following two statements.  
  
            //Task<WebResponse> responseTask = webReq.GetResponseAsync();  
            //using (WebResponse response = await responseTask)  
            {  
                // Get the data stream that is associated with the specified url.  
                using (Stream responseStream = response.GetResponseStream())  
                {  
                    // Read the bytes in responseStream and copy them to content.   
                    await responseStream.CopyToAsync(content);  
  
                    // The previous statement abbreviates the following two statements.  
  
                    // CopyToAsync returns a Task, not a Task<T>.  
                    //Task copyTask = responseStream.CopyToAsync(content);  
  
                    // When copyTask is completed, content contains a copy of  
                    // responseStream.  
                    //await copyTask;  
                }  
            }  
            // Return the result as a byte array.  
            return content.ToArray();  
        }  
  
        private void DisplayResults(string url, byte[] content)  
        {  
            // Display the length of each website. The string format   
            // is designed to be used with a monospaced font, such as  
            // Lucida Console or Global Monospace.  
            var bytes = content.Length;  
            // Strip off the "http://".  
            var displayURL = url.Replace("http://", "");  
            resultsTextBox.Text += string.Format("\n{0,-58} {1,8}", displayURL, bytes);  
        }  
    }  
}  
```  
  
 Следующий код содержит полный пример решения, использующего метод `HttpClient`, `GetByteArrayAsync`.  
  
```cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Threading.Tasks;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Documents;  
using System.Windows.Input;  
using System.Windows.Media;  
using System.Windows.Media.Imaging;  
using System.Windows.Navigation;  
using System.Windows.Shapes;  
  
// Add the following using directives, and add a reference for System.Net.Http.  
using System.Net.Http;  
using System.IO;  
using System.Net;  
  
namespace AsyncExampleWPF  
{  
    public partial class MainWindow : Window  
    {  
        public MainWindow()  
        {  
            InitializeComponent();  
        }  
  
        private async void startButton_Click(object sender, RoutedEventArgs e)  
        {  
            resultsTextBox.Clear();  
  
            // Disable the button until the operation is complete.  
            startButton.IsEnabled = false;  
  
            // One-step async call.  
            await SumPageSizesAsync();  
  
            //// Two-step async call.  
            //Task sumTask = SumPageSizesAsync();  
            //await sumTask;  
  
            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";  
  
            // Reenable the button in case you want to run the operation again.  
            startButton.IsEnabled = true;  
        }  
  
        private async Task SumPageSizesAsync()  
        {  
            // Declare an HttpClient object and increase the buffer size. The  
            // default buffer size is 65,536.  
            HttpClient client =  
                new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
  
            // Make a list of web addresses.  
            List<string> urlList = SetUpURLList();  
  
            var total = 0;  
  
            foreach (var url in urlList)  
            {  
                // GetByteArrayAsync returns a task. At completion, the task  
                // produces a byte array.  
                byte[] urlContents = await client.GetByteArrayAsync(url);                 
  
                // The following two lines can replace the previous assignment statement.  
                //Task<byte[]> getContentsTask = client.GetByteArrayAsync(url);  
                //byte[] urlContents = await getContentsTask;  
  
                DisplayResults(url, urlContents);  
  
                // Update the total.  
                total += urlContents.Length;  
            }  
  
            // Display the total count for all of the websites.  
            resultsTextBox.Text +=  
                string.Format("\r\n\r\nTotal bytes returned:  {0}\r\n", total);  
        }  
  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>   
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
            };  
            return urls;  
        }  
  
        private void DisplayResults(string url, byte[] content)  
        {  
            // Display the length of each website. The string format   
            // is designed to be used with a monospaced font, such as  
            // Lucida Console or Global Monospace.  
            var bytes = content.Length;  
            // Strip off the "http://".  
            var displayURL = url.Replace("http://", "");  
            resultsTextBox.Text += string.Format("\n{0,-58} {1,8}", displayURL, bytes);  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Пример асинхронности. Пошаговое руководство "Доступ к сети" (C# и Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255191)   
 [async](../../../../csharp/language-reference/keywords/async.md)   
 [await](../../../../csharp/language-reference/keywords/await.md)   
 [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](../../../../csharp/programming-guide/concepts/async/index.md)   
 [Асинхронные типы возвращаемых значений (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md)   
 [Асинхронное программирование на основе задач (TAP)](http://go.microsoft.com/fwlink/?LinkId=204847)   
 [Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)   
 [Практическое руководство. Параллельное выполнение нескольких веб-запросов с использованием Async и Await (C#)](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)
