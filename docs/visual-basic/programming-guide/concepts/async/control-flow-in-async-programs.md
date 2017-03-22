---
title: "Управление ходом выполнения в асинхронных программах (Visual Basic) | Документы Microsoft"
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
ms.assetid: b0443af7-c586-4cb0-b476-742ae4098a96
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
ms.openlocfilehash: 15e02fbc023db9ae2f3ee9f40598faa7c9c027a0
ms.lasthandoff: 03/13/2017

---
# <a name="control-flow-in-async-programs-visual-basic"></a>Поток управления в асинхронных программах (Visual Basic)
Можно написать и более легко поддерживать асинхронные программы с помощью `Async` и `Await` ключевые слова. Однако результаты могут оказаться неожиданными Если вы не понимаете, как работает программа. Этот раздел трассировки, передачи потока управления через простой асинхронной программы, чтобы показать, когда элемент управления перемещается из одного метода другим и какие данные каждый раз.  
  
> [!NOTE]
>  Ключевые слова `Async` и `Await` появились в Visual Studio 2012.  
  
 В общем случае пометить методы, содержащие асинхронного кода с [Async](../../../../visual-basic/language-reference/modifiers/async.md) модификатор. В метод, помеченный с помощью модификатора async, можно использовать [Await (Visual Basic)](../../../../visual-basic/language-reference/operators/await-operator.md) оператор, чтобы указать, где метод приостанавливает для ожидания завершения вызванного асинхронного процесса. Дополнительные сведения см. в разделе [асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 В следующем примере асинхронные методы для загрузки содержимого веб-сайт, указанный как строка и отображения длину строки. Пример содержит два метода.  
  
-   `startButton_Click`, который вызывает метод `AccessTheWebAsync` и отображает результат.  
  
-   `AccessTheWebAsync`, который загружает содержимое веб-сайта в виде строки и возвращает длину строки. `AccessTheWebAsync`использует асинхронную <xref:System.Net.Http.HttpClient>метод <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, чтобы загрузить содержимое.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> </xref:System.Net.Http.HttpClient>  
  
 Нумерация отображаемые строки отображаются в стратегических точках в программе помогут вам понять, как работает программа и объясняется, что происходит на каждом этапе, который отмечен. Отображение линии обозначаются «Один» до «ШЕСТЬ.» Метки представляют порядок, в котором программа достигает этих строк кода.  
  
 В следующем коде показано структуры программы.  
  
```vb  
Class MainWindow  
  
    Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click  
  
        ' ONE  
        Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()  
  
        ' FOUR  
        Dim contentLength As Integer = Await getLengthTask  
  
        ' SIX  
        ResultsTextBox.Text &=  
            String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
    End Sub  
  
    Async Function AccessTheWebAsync() As Task(Of Integer)  
  
        ' TWO  
        Dim client As HttpClient = New HttpClient()   
        Dim getStringTask As Task(Of String) =   
            client.GetStringAsync("http://msdn.microsoft.com")  
  
        ' THREE  
        Dim urlContents As String = Await getStringTask  
  
        ' FIVE  
        Return urlContents.Length  
    End Function  
  
End Class  
  
```  
  
 Каждый из расположения с меткой, «Один» до «ШЕСТЬ,» отображает сведения о текущем состоянии программы. Получается следующий результат.  
  
```  
  
ONE:   Entering startButton_Click.  
           Calling AccessTheWebAsync.  
  
TWO:   Entering AccessTheWebAsync.  
           Calling HttpClient.GetStringAsync.  
  
THREE: Back in AccessTheWebAsync.  
           Task getStringTask is started.  
           About to await getStringTask & return a Task<int> to startButton_Click.  
  
FOUR:  Back in startButton_Click.  
           Task getLengthTask is started.  
           About to await getLengthTask -- no caller to return to.  
  
FIVE:  Back in AccessTheWebAsync.  
           Task getStringTask is complete.  
           Processing the return statement.  
           Exiting from AccessTheWebAsync.  
  
SIX:   Back in startButton_Click.  
           Task getLengthTask is finished.  
           Result from AccessTheWebAsync is stored in contentLength.  
           About to display contentLength and exit.  
  
Length of the downloaded string: 33946.  
```  
  
## <a name="set-up-the-program"></a>Настроить программу  
 Код, который используется в этом разделе можно загрузить с сайта MSDN, или можно выполнить его самостоятельно.  
  
> [!NOTE]
>  Чтобы выполнить этот пример, необходимо иметь Visual Studio 2012 или более поздней версии и платформы .NET Framework 4.5 или более новая версия вашего компьютера.  
  
### <a name="download-the-program"></a>Загрузка программы  
 Можно загрузить приложение из этого раздела [образец Async: поток управления в асинхронных программах](http://go.microsoft.com/fwlink/?LinkId=255285). Далее откройте и запустите программу.  
  
1.  Распакуйте загруженный файл, а затем запустите Visual Studio.  
  
2.  В строке меню выберите **Файл**, **Открыть**, **Проект/Решение**.  
  
3.  Перейдите к папке, содержащий распакованную образец кода, откройте файл решения (SLN-файл) и нажмите клавишу F5 для построения и запуска проекта.  
  
### <a name="build-the-program-yourself"></a>Самостоятельное построение программы  
 Следующий проект Windows Presentation Foundation (WPF) содержит пример кода для этой темы.  
  
 Чтобы запустить проект, выполните следующие действия.  
  
1.  Запустите Visual Studio.  
  
2.  В строке меню выберите **Файл**, **Создать**, **Проект**.  
  
     Откроется диалоговое окно **Новый проект** .  
  
3.  В **установленные шаблоны** область, выберите **Visual Basic**и нажмите кнопку **приложение WPF** в списке типов проектов.  
  
4.  Введите `AsyncTracer` как имя проекта, а затем выберите **ОК** кнопки.  
  
     Появится новый проект в **обозревателе решений**.  
  
5.  В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .  
  
     Если вкладка не отображается, откройте контекстное меню для MainWindow.xaml в **обозревателе решений**, а затем выберите **Просмотр кода**.  
  
6.  В **XAML** Просмотр файла MainWindow.XAML, замените код следующим кодом.  
  
    ```vb  
    <Window  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d" x:Class="MainWindow"  
        Title="Control Flow Trace" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="221,10,0,0" VerticalAlignment="Top" Width="75"/>  
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" TextWrapping="Wrap" VerticalAlignment="Bottom" Width="510" Height="265" FontFamily="Lucida Console" FontSize="10" VerticalScrollBarVisibility="Visible" d:LayoutOverrides="HorizontalMargin"/>  
  
        </Grid>  
    </Window>  
  
    ```  
  
     Появится простое окно, содержащее текстовое поле и кнопку в **разработки** файла MainWindow.XAML.  
  
7.  Добавить ссылку <xref:System.Net.Http>.</xref:System.Net.Http>  
  
8.  В **обозревателе решений**, откройте контекстное меню для MainWindow.xaml.vb и выберите **Просмотр кода**.  
  
9. В файл MainWindow.xaml.vb замените код следующим кодом.  
  
    ```vb  
    ' Add an Imports statement and a reference for System.Net.Http.  
    Imports System.Net.Http  
  
    Class MainWindow  
  
        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click  
  
            ' The display lines in the example lead you through the control shifts.  
            ResultsTextBox.Text &= "ONE:   Entering StartButton_Click." & vbCrLf &  
                "           Calling AccessTheWebAsync." & vbCrLf  
  
            Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()  
  
            ResultsTextBox.Text &= vbCrLf & "FOUR:  Back in StartButton_Click." & vbCrLf &  
                "           Task getLengthTask is started." & vbCrLf &  
                "           About to await getLengthTask -- no caller to return to." & vbCrLf  
  
            Dim contentLength As Integer = Await getLengthTask  
  
            ResultsTextBox.Text &= vbCrLf & "SIX:   Back in StartButton_Click." & vbCrLf &  
                "           Task getLengthTask is finished." & vbCrLf &  
                "           Result from AccessTheWebAsync is stored in contentLength." & vbCrLf &  
                "           About to display contentLength and exit." & vbCrLf  
  
            ResultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
        End Sub  
  
        Async Function AccessTheWebAsync() As Task(Of Integer)  
  
            ResultsTextBox.Text &= vbCrLf & "TWO:   Entering AccessTheWebAsync."  
  
            ' Declare an HttpClient object.  
            Dim client As HttpClient = New HttpClient()  
  
            ResultsTextBox.Text &= vbCrLf & "           Calling HttpClient.GetStringAsync." & vbCrLf  
  
            ' GetStringAsync returns a Task(Of String).   
            Dim getStringTask As Task(Of String) = client.GetStringAsync("http://msdn.microsoft.com")  
  
            ResultsTextBox.Text &= vbCrLf & "THREE: Back in AccessTheWebAsync." & vbCrLf &  
                "           Task getStringTask is started."  
  
            ' AccessTheWebAsync can continue to work until getStringTask is awaited.  
  
            ResultsTextBox.Text &=  
                vbCrLf & "           About to await getStringTask & return a Task(Of Integer) to StartButton_Click." & vbCrLf  
  
            ' Retrieve the website contents when task is complete.  
            Dim urlContents As String = Await getStringTask  
  
            ResultsTextBox.Text &= vbCrLf & "FIVE:  Back in AccessTheWebAsync." &  
                vbCrLf & "           Task getStringTask is complete." &  
                vbCrLf & "           Processing the return statement." &  
                vbCrLf & "           Exiting from AccessTheWebAsync." & vbCrLf  
  
            Return urlContents.Length  
        End Function  
  
    End Class  
    ```  
  
10. Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .  
  
     Должен появиться следующий результат.  
  
    ```  
    ONE:   Entering startButton_Click.  
               Calling AccessTheWebAsync.  
  
    TWO:   Entering AccessTheWebAsync.  
               Calling HttpClient.GetStringAsync.  
  
    THREE: Back in AccessTheWebAsync.  
               Task getStringTask is started.  
               About to await getStringTask & return a Task<int> to startButton_Click.  
  
    FOUR:  Back in startButton_Click.  
               Task getLengthTask is started.  
               About to await getLengthTask -- no caller to return to.  
  
    FIVE:  Back in AccessTheWebAsync.  
               Task getStringTask is complete.  
               Processing the return statement.  
               Exiting from AccessTheWebAsync.  
  
    SIX:   Back in startButton_Click.  
               Task getLengthTask is finished.  
               Result from AccessTheWebAsync is stored in contentLength.  
               About to display contentLength and exit.  
  
    Length of the downloaded string: 33946.  
    ```  
  
## <a name="trace-the-program"></a>Программа трассировки  
  
### <a name="steps-one-and-two"></a>Шаги ОДИН и ДВА  
 Отображение первых двух строк проследить путь как `startButton_Click` вызовов `AccessTheWebAsync`, и `AccessTheWebAsync` вызывает асинхронный <xref:System.Net.Http.HttpClient>метод <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> </xref:System.Net.Http.HttpClient> Ниже описаны вызовов из метода в метод.  
  
 ![Шаги&1; и&2;](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace ONETWO")  
  
 Тип возвращаемого значения и `AccessTheWebAsync` и `client.GetStringAsync` <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> Для `AccessTheWebAsync`, TResult является целым числом. Для `GetStringAsync`, TResult — строка. Дополнительные сведения о возвращаемых типов асинхронный метод в разделе [возвращают типы Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
 Возвращение задач асинхронный метод возвращает экземпляр задачи, когда элемент управления перемещается обратно вызывающему. Возвращает элемент управления из асинхронного метода вызывающему либо если `Await` оператор встречается в вызываемый метод или когда завершается вызванный метод. Отображение строки, помеченные как «ТРИ» до «6» трассировки эта часть процесса.  
  
### <a name="step-three"></a>Шаг ТРИ  
 В `AccessTheWebAsync`, асинхронный метод <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>вызывается для загрузки содержимого веб-страницы целевой.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> Возвращает элемент управления `client.GetStringAsync` для `AccessTheWebAsync` при `client.GetStringAsync` возвращает.  
  
 `client.GetStringAsync` Метод возвращает задачу, строки, назначенный `getStringTask` переменных в `AccessTheWebAsync`. Следующие строки в примере программы показано, как вызвать `client.GetStringAsync` и назначения.  
  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
 Можно считать задачи обещание по `client.GetStringAsync` для создания фактической строки со временем. В то же время Если `AccessTheWebAsync` есть работа, не зависящей от обещанной строку из `client.GetStringAsync`, что продолжением работы во время `client.GetStringAsync` ожидания. В этом примере следующие строки выходных данных, которые обозначены «ТРИ», представляют возможность работать независимо  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
 Следующая инструкция приостанавливает ход выполнения в `AccessTheWebAsync` при `getStringTask` будет ожидать.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
 На следующем рисунке поток управления из `client.GetStringAsync` для назначения `getStringTask` и от создания `getStringTask` в приложение оператор Await.  
  
 ![ТРЕТИЙ шаг](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "три AsyncTrace")  
  
 Выражение await приостанавливает `AccessTheWebAsync` до `client.GetStringAsync` возвращает. В то же время управление возвращается вызывающему объекту `AccessTheWebAsync`, `startButton_Click`.  
  
> [!NOTE]
>  Как правило вы сразу ожидать результата вызова асинхронного метода. Например, следующее присвоение может заменить предыдущий код, который создает и затем ожидает `getStringTask`:`Dim urlContents As String = Await client.GetStringAsync("http://msdn.microsoft.com")`  
>   
>  В этом разделе оператор await применяется позже для вывода линий, которые отмечают поток управления в программе.  
  
### <a name="step-four"></a>Шаг ЧЕТЫРЕ  
 Объявленный тип возвращаемого значения `AccessTheWebAsync` — `Task(Of Integer)`. Таким образом, когда `AccessTheWebAsync` будет приостановлен, он возвращает задачу, целого числа в `startButton_Click`. Следует понимать, что возвращаемая задача не `getStringTask`. Возвращаемая задача является новой задачи целое число, представляющее что остается сделать в приостановленном методе `AccessTheWebAsync`. Задача является обещание из `AccessTheWebAsync` производить целое число, при завершении задачи.  
  
 Следующий оператор назначает эту задачу, чтобы `getLengthTask` переменной.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
 Как и в `AccessTheWebAsync`, `startButton_Click` можно продолжить работу, не зависят от результатов асинхронной задачи (`getLengthTask`) пока не ожидать задачу. Следующие выходные данные строки представляют этой работы.  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
 Выполнение в `startButton_Click` при приостановке `getLengthTask` будет ожидать. Следующая инструкция назначения приостанавливает `startButton_Click` до `AccessTheWebAsync` завершения.  
  
<CodeContentPlaceHolder>10</CodeContentPlaceHolder>  
 На следующем рисунке стрелки Показать поток управления из выражения await в `AccessTheWebAsync` для присвоения значения для `getLengthTask`, следуют обычной обработки в `startButton_Click` до `getLengthTask` будет ожидать.  
  
 ![ЧЕТВЕРТЫЙ шаг](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace ЧЕТЫРЕ")  
  
### <a name="step-five"></a>Шаг ПЯТЬ  
 Когда `client.GetStringAsync` указывает, что завершения обработки в `AccessTheWebAsync` освобождается после приостановки и можно продолжить выполнение после оператора await. Приведенный ниже выходные данные представляют продолжение обработки.  
  
<CodeContentPlaceHolder>11</CodeContentPlaceHolder>  
 Операнд оператора return `urlContents.Length`, хранится в задаче, `AccessTheWebAsync` возвращает. Выражение await получает это значение из `getLengthTask` в `startButton_Click`.  
  
 На следующем рисунке показано перемещение элемента управления после `client.GetStringAsync` (и `getStringTask`) завершены.  
  
 ![ПЯТЫЙ шаг](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace&5;")  
  
 `AccessTheWebAsync`Возвращает выполняется до завершения и управления `startButton_Click`, который ожидает завершения.  
  
### <a name="step-six"></a>Шаг ШЕСТЬ  
 Когда `AccessTheWebAsync` сигнализирует завершения обработки можно продолжить выполнение после оператора await в `startButton_Async`. На самом деле программа имеет ничего общего дополнительные.  
  
 Приведенный ниже выходные данные представляют продолжение обработки в `startButton_Async`:  
  
<CodeContentPlaceHolder>12</CodeContentPlaceHolder>  
 Выражение await извлекает из `getLengthTask` целое значение, представляющее операнд оператора return в `AccessTheWebAsync`. Следующая инструкция присваивает это значение `contentLength` переменной.  
  
<CodeContentPlaceHolder>13</CodeContentPlaceHolder>  
 На следующем рисунке показано возвращение управления из `AccessTheWebAsync` в `startButton_Click`.  
  
 ![ШЕСТОЙ шаг](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace&6;")  
  
## <a name="see-also"></a>См. также  
 [Асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Асинхронные типы возвращаемых значений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)   
 [Пошаговое руководство: Доступ к Интернету с помощью модификатора Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [Пример асинхронности: Поток управления в асинхронных программах (C# и Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255285)
