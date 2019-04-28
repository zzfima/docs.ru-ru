---
title: Поток управления в асинхронных программах (Visual Basic)
ms.date: 07/20/2015
ms.assetid: b0443af7-c586-4cb0-b476-742ae4098a96
ms.openlocfilehash: ed993943bcf7341f900c575744a1faa53a4a8a2e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923673"
---
# <a name="control-flow-in-async-programs-visual-basic"></a>Поток управления в асинхронных программах (Visual Basic)
Можно намного проще создавать и обслуживать асинхронные программы с помощью ключевых слов `Async` и `Await`. Однако при непонимании механизма работы асинхронной программы результаты могут удивить. В этом разделе выполняется трассировка потока управления с помощью простой асинхронной программы, чтобы продемонстрировать переход потока управления от одного метода к другому, включая данные, передаваемые в каждом случае.  
  
> [!NOTE]
>  Ключевые слова `Async` и `Await` появились в Visual Studio 2012.  
  
 Как правило, вы помечаете методы, содержащие асинхронный код [Async](../../../../visual-basic/language-reference/modifiers/async.md) модификатор. В методе, помеченном модификатором async, можно использовать [Await (Visual Basic)](../../../../visual-basic/language-reference/operators/await-operator.md) оператор, чтобы указать, где метод приостанавливается для ожидания завершения вызванного асинхронного процесса. Дополнительные сведения см. в разделе [асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 В следующем примере асинхронные методы используются для загрузки содержимого указанного веб-сайта в виде строки и отображения длины строки. Пример содержит следующие два метода:  
  
- `startButton_Click`, который вызывает метод `AccessTheWebAsync` и выводит результат;  
  
- `AccessTheWebAsync`, который загружает содержимое веб-сайта в виде строки и возвращает длину строки. `AccessTheWebAsync` использует для загрузки содержимого асинхронный метод <xref:System.Net.Http.HttpClient> <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.  
  
 Выводимые строки помечены номерами на стратегических этапах программы, чтобы помочь вам понять, как работает программа и что происходит на каждом отмеченном этапе. Выводимые строки обозначены номерами от ONE (один) до SIX (шесть). Метки представляют порядок, в котором программа достигает эти строки кода.  
  
 В следующем примере кода показана структура программы.  
  
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
            client.GetStringAsync("https://msdn.microsoft.com")  
  
        ' THREE  
        Dim urlContents As String = Await getStringTask  
  
        ' FIVE  
        Return urlContents.Length  
    End Function  
  
End Class  
```  
  
 Каждое из расположений, обозначенное от одного до шести, отображает сведения о текущем состоянии программы. Выводятся следующие результаты.  
  
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
  
## <a name="set-up-the-program"></a>Настройка программы  
 Можно загрузить используемый в этом разделе код из MSDN, или же можно создать его самостоятельно.  
  
> [!NOTE]
>  Чтобы запустить пример, вам потребуются Visual Studio 2012 или более поздней версии и .NET Framework 4.5 или более поздняя версия на компьютере.  
  
### <a name="download-the-program"></a>Скачайте программу  
 Вы можете скачать приложение для этого раздела на странице примеров [Пример Async: поток управления в асинхронных программах](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0). Следующие шаги описывают процесс открытия и запуска программы.  
  
1. Распакуйте загруженный файл, а затем запустите Visual Studio.  
  
2. В строке меню выберите **Файл**, **Открыть**, **Проект/Решение**.  
  
3. Перейдите к папке, содержащей распакованный пример кода, откройте файл решения (SLN), а затем нажмите клавишу F5 для сборки и выполнения проекта.  
  
### <a name="build-the-program-yourself"></a>Самостоятельное построение программы  
 Следующий проект Windows Presentation Foundation (WPF) содержит примеры кода для этого раздела.  
  
 Чтобы запустить проект, выполните следующие действия.  
  
1. Запустите Visual Studio.  
  
2. В строке меню выберите **Файл**, **Создать**, **Проект**.  
  
     Откроется диалоговое окно **Новый проект** .  
  
3. В **установленные шаблоны** панели выберите **Visual Basic**, а затем выберите **приложение WPF** в списке типов проектов.  
  
4. Введите `AsyncTracer` в качестве имени проекта и нажмите кнопку **ОК**.  
  
     В **обозревателе решений** появится новый проект.  
  
5. В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .  
  
     Если вкладка не отображается, откройте контекстное меню для MainWindow.xaml в **обозревателе решений** и выберите пункт **Просмотреть код**.  
  
6. Замените код в представлении **XAML** файла MainWindow.xaml на следующий.  
  
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
  
     В представлении **Конструктор** файла MainWindow.xaml появится простое окно, содержащее кнопку и текстовое поле.  
  
7. Добавьте ссылку для <xref:System.Net.Http>.  
  
8. В **обозревателе решений**, откройте контекстное меню для MainWindow.xaml.vb и затем выберите **Просмотр кода**.  
  
9. В файле MainWindow.xaml.vb замените код следующим кодом.  
  
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
            Dim getStringTask As Task(Of String) = client.GetStringAsync("https://msdn.microsoft.com")  
  
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
  
## <a name="trace-the-program"></a>Трассировка программы  
  
### <a name="steps-one-and-two"></a>Шаги ОДИН и ДВА  
 В первых двух строках прослеживается путь по мере того, как метод `startButton_Click` вызывает `AccessTheWebAsync`, а `AccessTheWebAsync` вызывает асинхронный метод <xref:System.Net.Http.HttpClient> <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>. Ниже показаны вызовы из метода в метод.  
  
 ![Шаги ONE (один) и TWO (два)](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace-ONETWO")  
  
 Типом возвращаемого значения и для `AccessTheWebAsync`, и для `client.GetStringAsync` является <xref:System.Threading.Tasks.Task%601>. Для `AccessTheWebAsync` значение TResult является целым числом. Для `GetStringAsync` значение TResult является строкой. Дополнительные сведения о возвращаемых типах асинхронных методов, см. в разделе [асинхронные типы возвращаемых значений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
 Асинхронный метод, возвращающий задачи, возвращает экземпляр задачи, когда контроль управления возвращается к вызывающему объекту. Управление передается от асинхронного метода его вызывающему методу, когда в вызванном методе обнаруживается оператор `Await` или когда вызванный метод завершается. Отображаемые строки, которые помечены от трёх до шести, отслеживают эту часть процесса.  
  
### <a name="step-three"></a>Шаг ТРИ  
 В `AccessTheWebAsync` для загрузки содержимого целевой веб-страницы вызывается асинхронный метод <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>. Управление передается от `client.GetStringAsync` методу `AccessTheWebAsync` при возвращении результатов методом `client.GetStringAsync`.  
  
 Метод `client.GetStringAsync` возвращает задачу строки, назначенной переменной `getStringTask` в `AccessTheWebAsync`. Следующая строка в примере программы демонстрирует вызов `client.GetStringAsync` и назначение.  
  
```vb  
Dim getStringTask As Task(Of String) = client.GetStringAsync("https://msdn.microsoft.com")  
```  
  
 Можно представить себе задачу как обещание `client.GetStringAsync` создать в конечном итоге фактическую строку. В то же время, если у `AccessTheWebAsync` есть работа, не зависящая от обещанной строки, от `client.GetStringAsync`, эта работа будет продолжена во время ожидания `client.GetStringAsync`. В этом примере следующие строки вывода, которые обозначены как "THREE", представляют возможность сделать независимую работу.  
  
```  
THREE: Back in AccessTheWebAsync.  
           Task getStringTask is started.  
           About to await getStringTask & return a Task<int> to startButton_Click.  
```  
  
 Следующая инструкция приостанавливает ход выполнения в `AccessTheWebAsync` при ожидании `getStringTask`.  
  
```vb  
Dim urlContents As String = Await getStringTask  
```  
  
 На следующем рисунке поток управления из `client.GetStringAsync` к назначению `getStringTask` и от создания `getStringTask` для применения оператора Await.  
  
 ![Шаг THREE (три)](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace-Three")  
  
 Выражение await приостанавливает `AccessTheWebAsync` до возвращения результатов `client.GetStringAsync`. На это время управление возвращается вызывающему объекту метода `AccessTheWebAsync`, `startButton_Click`.  
  
> [!NOTE]
>  Как правило, ожидание вызова асинхронного метода выполняется немедленно. Например, следующее присвоение может заменить предыдущий код, который создает, а затем ожидает `getStringTask`: `Dim urlContents As String = Await client.GetStringAsync("https://msdn.microsoft.com")`  
>   
>  В этом разделе оператор await применяется позже для размещения строк, которые отмечают поток управления в программе.  
  
### <a name="step-four"></a>Шаг ЧЕТЫРЕ  
 Объявленный тип возвращаемого значения `AccessTheWebAsync` — `Task(Of Integer)`. Таким образом, когда выполнение `AccessTheWebAsync` приостанавливается, он возвращает задачу целого числа в `startButton_Click`. Следует понимать, что возвращаемая задача — не `getStringTask`. Возвращаемая задача — это новая задача целого числа, представляющая оставшуюся работу в приостановленном методе `AccessTheWebAsync`. Задача является обещанием `AccessTheWebAsync` создать фактическое целое число после завершения задачи.  
  
 Следующий оператор назначает эту задачу переменной `getLengthTask`.  
  
```vb  
Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()  
```  
  
 Как и в `AccessTheWebAsync`, `startButton_Click` может продолжать работу, которая не зависит от результатов асинхронной задачи (`getLengthTask`), во время ожидания задачи. Следующие выходные строки представляют такую работу.  
  
```  
FOUR:  Back in startButton_Click.  
           Task getLengthTask is started.  
           About to await getLengthTask -- no caller to return to.  
```  
  
 Выполнение в `startButton_Click` приостанавливается при ожидании `getLengthTask`. Следующая инструкция назначения приостанавливает `startButton_Click` до завершения `AccessTheWebAsync`.  
  
```vb  
Dim contentLength As Integer = Await getLengthTask  
```  
  
 На следующем рисунке стрелками показан поток управления из выражения await в `AccessTheWebAsync` к назначению значения `getLengthTask`, за которым следует обычная обработка в методе `startButton_Click` до ожидания `getLengthTask`.  
  
 ![Шаг FOUR (четыре)](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace-FOUR")  
  
### <a name="step-five"></a>Шаг ПЯТЬ  
 Когда `client.GetStringAsync` уведомляет о завершении, обработка в `AccessTheWebAsync` возобновляется и может продолжаться после оператора await. Приведенные ниже строки выходных данных представляют возобновление обработки.  
  
```  
FIVE:  Back in AccessTheWebAsync.  
           Task getStringTask is complete.  
           Processing the return statement.  
           Exiting from AccessTheWebAsync.  
```  
  
 Операнд оператора return, `urlContents.Length`, хранится в задаче, возвращаемой `AccessTheWebAsync`. Выражение await получает это значение из `getLengthTask` в `startButton_Click`.  
  
 На следующем рисунке показана передача управления после завершения `client.GetStringAsync` (и `getStringTask`).  
  
 ![Шаг FIVE (пять)](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace-FIVE")  
  
 `AccessTheWebAsync` выполняется до завершения, и управление возвращается к `startButton_Click`, который ожидает завершения.  
  
### <a name="step-six"></a>Шаг ШЕСТЬ  
 Когда `AccessTheWebAsync` уведомляет о завершении, обработка может продолжаться после оператора await в `startButton_Async`. Фактически, на этом работа программы завершается.  
  
 Приведенные ниже строки выходных данных представляют возобновление обработки в `startButton_Async`:  
  
```  
SIX:   Back in startButton_Click.  
           Task getLengthTask is finished.  
           Result from AccessTheWebAsync is stored in contentLength.  
           About to display contentLength and exit.  
```  
  
 Выражение await получает из `getLengthTask` целое значение, представляющее операнд оператора return в `AccessTheWebAsync`. Следующий оператор назначает это значение переменной `contentLength`.  
  
```vb  
Dim contentLength As Integer = Await getLengthTask  
```  
  
 На следующем рисунке показано возвращение управления от `AccessTheWebAsync` к `startButton_Click`.  
  
 ![Шаг SIX (шесть)](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace-SIX")  
  
## <a name="see-also"></a>См. также

- [Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
- [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) (Типы возвращаемых значений Async (Visual Basic))
- [Пошаговое руководство: Доступ к Интернету с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Пример использования Async. Поток управления в асинхронных программах (C# и Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)
