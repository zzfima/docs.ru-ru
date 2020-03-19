---
title: Поток управления в асинхронных программах (C#)
ms.date: 07/20/2015
ms.assetid: fc92b08b-fe1d-4d07-84ab-5192fafe06bb
ms.openlocfilehash: 99f80a86f14179c5f270064a9f96e35f8611ef13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "70204441"
---
# <a name="control-flow-in-async-programs-c"></a>Поток управления в асинхронных программах (C#)

Можно намного проще создавать и обслуживать асинхронные программы с помощью ключевых слов `async` и `await`. Однако при непонимании механизма работы асинхронной программы результаты могут удивить. В этом разделе выполняется трассировка потока управления с помощью простой асинхронной программы, чтобы продемонстрировать переход потока управления от одного метода к другому, включая данные, передаваемые в каждом случае.

Как правило, вы помечаете методы, содержащие асинхронный код, с помощью модификатора [async (C#)](../../../language-reference/keywords/async.md). В методе, помеченном с помощью модификатора async, можно использовать оператор [await (C#)](../../../language-reference/operators/await.md), чтобы указать место приостановки метода для ожидания завершения вызванного асинхронного процесса. Дополнительные сведения см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](./index.md).

В следующем примере асинхронные методы используются для загрузки содержимого указанного веб-сайта в виде строки и отображения длины строки. Пример содержит следующие два метода:

- `startButton_Click`, который вызывает метод `AccessTheWebAsync` и выводит результат;

- `AccessTheWebAsync`, который загружает содержимое веб-сайта в виде строки и возвращает длину строки. `AccessTheWebAsync` использует для загрузки содержимого асинхронный метод <xref:System.Net.Http.HttpClient><xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.

Выводимые строки помечены номерами на стратегических этапах программы, чтобы помочь вам понять, как работает программа и что происходит на каждом отмеченном этапе. Выводимые строки обозначены номерами от ONE (один) до SIX (шесть). Метки представляют порядок, в котором программа достигает эти строки кода.

В следующем примере кода показана структура программы.

```csharp
public partial class MainWindow : Window
{
    // . . .
    private async void startButton_Click(object sender, RoutedEventArgs e)
    {
        // ONE
        Task<int> getLengthTask = AccessTheWebAsync();

        // FOUR
        int contentLength = await getLengthTask;

        // SIX
        resultsTextBox.Text +=
            $"\r\nLength of the downloaded string: {contentLength}.\r\n";
    }

    async Task<int> AccessTheWebAsync()
    {
        // TWO
        HttpClient client = new HttpClient();
        Task<string> getStringTask =
            client.GetStringAsync("https://msdn.microsoft.com");

        // THREE
        string urlContents = await getStringTask;

        // FIVE
        return urlContents.Length;
    }
}
```

Каждое из расположений, обозначенное от одного до шести, отображает сведения о текущем состоянии программы. Выводятся следующие результаты.

```output
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
> Для выполнения этого примера на компьютере должны быть установлены Visual Studio 2012 или более поздней версии и .NET Framework 4.5 или более поздней версии.

### <a name="download-the-program"></a>Скачивание программы

Вы можете скачать приложение для этого раздела на странице примеров [Пример Async: поток управления в асинхронных программах](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0). Следующие шаги описывают процесс открытия и запуска программы.

1. Распакуйте загруженный файл, а затем запустите Visual Studio.

2. В строке меню выберите **Файл** > **Открыть** > **Решение или проект**.

3. Перейдите к папке, содержащей распакованный пример кода, откройте файл решения (SLN), а затем нажмите клавишу **F5** для сборки и выполнения проекта.

### <a name="create-the-program-yourself"></a>Самостоятельное создание программы

Следующий проект Windows Presentation Foundation (WPF) содержит примеры кода для этого раздела.

Чтобы запустить проект, выполните следующие действия.

1. Запустите Visual Studio.

2. В строке меню выберите **Файл** > **Создать** > **Проект**.

     Откроется диалоговое окно **Новый проект** .

3. Выберите категории **Установленные** > **Visual C#**  > **Windows Desktop**, а затем выберите **Приложение WPF** в списке шаблонов проектов.

4. Введите `AsyncTracer` в качестве имени проекта и нажмите кнопку **ОК**.

     В **обозревателе решений** появится новый проект.

5. В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .

     Если вкладка не отображается, откройте контекстное меню для MainWindow.xaml в **обозревателе решений** и выберите пункт **Просмотреть код**.

6. Замените код в представлении **XAML** файла MainWindow.xaml на следующий.

    ```csharp
    <Window
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d" x:Class="AsyncTracer.MainWindow"
            Title="Control Flow Trace" Height="350" Width="592">
        <Grid>
            <Button x:Name="startButton" Content="Start
    " HorizontalAlignment="Left" Margin="250,10,0,0" VerticalAlignment="Top" Width="75" Height="24"  Click="startButton_Click" d:LayoutOverrides="GridBox"/>
            <TextBox x:Name="resultsTextBox" HorizontalAlignment="Left" TextWrapping="Wrap" VerticalAlignment="Bottom" Width="576" Height="265" FontFamily="Lucida Console" FontSize="10" VerticalScrollBarVisibility="Visible" Grid.ColumnSpan="3"/>
        </Grid>
    </Window>
    ```

     В представлении **Конструктор** файла MainWindow.xaml появится простое окно, содержащее кнопку и текстовое поле.

7. Добавьте ссылку для <xref:System.Net.Http>.

8. В **обозревателе решений** откройте контекстное меню для MainWindow.xaml.cs и выберите пункт **Просмотреть код**.

9. В MainWindow.xaml.cs замените код на следующий.

    ```csharp
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

    // Add a using directive and a reference for System.Net.Http;
    using System.Net.Http;

    namespace AsyncTracer
    {
        public partial class MainWindow : Window
        {
            public MainWindow()
            {
                InitializeComponent();
            }

            private async void startButton_Click(object sender, RoutedEventArgs e)
            {
                // The display lines in the example lead you through the control shifts.
                resultsTextBox.Text += "ONE:   Entering startButton_Click.\r\n" +
                    "           Calling AccessTheWebAsync.\r\n";

                Task<int> getLengthTask = AccessTheWebAsync();

                resultsTextBox.Text += "\r\nFOUR:  Back in startButton_Click.\r\n" +
                    "           Task getLengthTask is started.\r\n" +
                    "           About to await getLengthTask -- no caller to return to.\r\n";

                int contentLength = await getLengthTask;

                resultsTextBox.Text += "\r\nSIX:   Back in startButton_Click.\r\n" +
                    "           Task getLengthTask is finished.\r\n" +
                    "           Result from AccessTheWebAsync is stored in contentLength.\r\n" +
                    "           About to display contentLength and exit.\r\n";

                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {contentLength}.\r\n";
            }

            async Task<int> AccessTheWebAsync()
            {
                resultsTextBox.Text += "\r\nTWO:   Entering AccessTheWebAsync.";

                // Declare an HttpClient object.
                HttpClient client = new HttpClient();

                resultsTextBox.Text += "\r\n           Calling HttpClient.GetStringAsync.\r\n";

                // GetStringAsync returns a Task<string>.
                Task<string> getStringTask = client.GetStringAsync("https://msdn.microsoft.com");

                resultsTextBox.Text += "\r\nTHREE: Back in AccessTheWebAsync.\r\n" +
                    "           Task getStringTask is started.";

                // AccessTheWebAsync can continue to work until getStringTask is awaited.

                resultsTextBox.Text +=
                    "\r\n           About to await getStringTask and return a Task<int> to startButton_Click.\r\n";

                // Retrieve the website contents when task is complete.
                string urlContents = await getStringTask;

                resultsTextBox.Text += "\r\nFIVE:  Back in AccessTheWebAsync." +
                    "\r\n           Task getStringTask is complete." +
                    "\r\n           Processing the return statement." +
                    "\r\n           Exiting from AccessTheWebAsync.\r\n";

                return urlContents.Length;
            }
        }
    }
    ```

10. Нажмите клавишу **F5**, чтобы запустить программу, а затем нажмите кнопку **Запуск**.

    Появится следующий результат:

    ```output
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

В первых двух строках прослеживается путь по мере того, как метод `startButton_Click` вызывает `AccessTheWebAsync`, а `AccessTheWebAsync` вызывает асинхронный метод <xref:System.Net.Http.HttpClient><xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>. Ниже показаны вызовы из метода в метод.

![Шаги ОДИН и ДВА](./media/asynctrace-onetwo.png "AsyncTrace-ONETWO")

Типом возвращаемого значения и для `AccessTheWebAsync`, и для `client.GetStringAsync` является <xref:System.Threading.Tasks.Task%601>. Для `AccessTheWebAsync` значение TResult является целым числом. Для `GetStringAsync` значение TResult является строкой. Дополнительные сведения о возвращаемых типах асинхронных методов см. в разделе [Асинхронные типы возвращаемых значений (C#)](./async-return-types.md).

Асинхронный метод, возвращающий задачи, возвращает экземпляр задачи, когда контроль управления возвращается к вызывающему объекту. Управление передается от асинхронного метода его вызывающему методу, когда в вызванном методе обнаруживается оператор `await` или когда вызванный метод завершается. Отображаемые строки, которые помечены от трёх до шести, отслеживают эту часть процесса.

### <a name="step-three"></a>Шаг ТРИ

В `AccessTheWebAsync` для загрузки содержимого целевой веб-страницы вызывается асинхронный метод <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>. Управление передается от `client.GetStringAsync` методу `AccessTheWebAsync` при возвращении результатов методом `client.GetStringAsync`.

 Метод `client.GetStringAsync` возвращает задачу строки, назначенной переменной `getStringTask` в `AccessTheWebAsync`. Следующая строка в примере программы демонстрирует вызов `client.GetStringAsync` и назначение.

```csharp
Task<string> getStringTask = client.GetStringAsync("https://msdn.microsoft.com");
```

 Можно представить себе задачу как обещание `client.GetStringAsync` создать в конечном итоге фактическую строку. В то же время, если у `AccessTheWebAsync` есть работа, не зависящая от обещанной строки, от `client.GetStringAsync`, эта работа будет продолжена во время ожидания `client.GetStringAsync`. В этом примере следующие строки вывода, которые обозначены как "THREE", представляют возможность сделать независимую работу.

```output
THREE: Back in AccessTheWebAsync.
           Task getStringTask is started.
           About to await getStringTask & return a Task<int> to startButton_Click.
```

 Следующая инструкция приостанавливает ход выполнения в `AccessTheWebAsync` при ожидании `getStringTask`.

```csharp
string urlContents = await getStringTask;
```

 На следующем рисунке показан поток управления из `client.GetStringAsync` к назначению `getStringTask` и из создания `getStringTask` к применению оператора await.

 ![Шаг ТРИ](./media/asynctrace-three.png "AsyncTrace-Three")

 Выражение await приостанавливает `AccessTheWebAsync` до возвращения результатов `client.GetStringAsync`. На это время управление возвращается вызывающему объекту метода `AccessTheWebAsync`, `startButton_Click`.

> [!NOTE]
> Как правило, ожидание вызова асинхронного метода выполняется немедленно. Например, следующее присвоение может заменить предыдущий код, который создает, а затем ожидает `getStringTask`: `string urlContents = await client.GetStringAsync("https://msdn.microsoft.com");`
>
> В этом разделе оператор await применяется позже для размещения строк, которые отмечают поток управления в программе.

### <a name="step-four"></a>Шаг ЧЕТЫРЕ

Объявленный тип возвращаемого значения `AccessTheWebAsync` — `Task<int>`. Таким образом, когда выполнение `AccessTheWebAsync` приостанавливается, он возвращает задачу целого числа в `startButton_Click`. Следует понимать, что возвращаемая задача — не `getStringTask`. Возвращаемая задача — это новая задача целого числа, представляющая оставшуюся работу в приостановленном методе `AccessTheWebAsync`. Задача является обещанием `AccessTheWebAsync` создать фактическое целое число после завершения задачи.

Следующий оператор назначает эту задачу переменной `getLengthTask`.

```csharp
Task<int> getLengthTask = AccessTheWebAsync();
```

 Как и в `AccessTheWebAsync`, `startButton_Click` может продолжать работу, которая не зависит от результатов асинхронной задачи (`getLengthTask`), во время ожидания задачи. Следующие выходные строки представляют такую работу.

```output
FOUR:  Back in startButton_Click.
           Task getLengthTask is started.
           About to await getLengthTask -- no caller to return to.
```

 Выполнение в `startButton_Click` приостанавливается при ожидании `getLengthTask`. Следующая инструкция назначения приостанавливает `startButton_Click` до завершения `AccessTheWebAsync`.

```csharp
int contentLength = await getLengthTask;
```

 На следующем рисунке стрелками показан поток управления из выражения await в `AccessTheWebAsync` к назначению значения `getLengthTask`, за которым следует обычная обработка в методе `startButton_Click` до ожидания `getLengthTask`.

 ![Шаг ЧЕТЫРЕ](./media/asynctrace-four.png "AsyncTrace-FOUR")

### <a name="step-five"></a>Шаг ПЯТЬ

Когда `client.GetStringAsync` уведомляет о завершении, обработка в `AccessTheWebAsync` возобновляется и может продолжаться после оператора await. Приведенные ниже строки выходных данных представляют возобновление обработки.

```output
FIVE:  Back in AccessTheWebAsync.
           Task getStringTask is complete.
           Processing the return statement.
           Exiting from AccessTheWebAsync.
```

 Операнд оператора return, `urlContents.Length`, хранится в задаче, возвращаемой `AccessTheWebAsync`. Выражение await получает это значение из `getLengthTask` в `startButton_Click`.

 На следующем рисунке показана передача управления после завершения `client.GetStringAsync` (и `getStringTask`).

 ![Шаг ПЯТЬ](./media/asynctrace-five.png "AsyncTrace-FIVE")

 `AccessTheWebAsync` выполняется до завершения, и управление возвращается к `startButton_Click`, который ожидает завершения.

### <a name="step-six"></a>Шаг ШЕСТЬ

Когда `AccessTheWebAsync` уведомляет о завершении, обработка может продолжаться после оператора await в `startButton_Async`. Фактически, на этом работа программы завершается.

Приведенные ниже строки выходных данных представляют возобновление обработки в `startButton_Async`:

```output
SIX:   Back in startButton_Click.
           Task getLengthTask is finished.
           Result from AccessTheWebAsync is stored in contentLength.
           About to display contentLength and exit.
```

 Выражение await получает из `getLengthTask` целое значение, представляющее операнд оператора return в `AccessTheWebAsync`. Следующий оператор назначает это значение переменной `contentLength`.

```csharp
int contentLength = await getLengthTask;
```

 На следующем рисунке показано возвращение управления от `AccessTheWebAsync` к `startButton_Click`.

 ![Шаг ШЕСТЬ](./media/asynctrace-six.png "AsyncTrace-SIX")

## <a name="see-also"></a>См. также

- [Асинхронное программирование с использованием ключевых слов async и await (C#)](./index.md)
- [Async Return Types (C#)](./async-return-types.md) (Типы возвращаемых значений асинхронных операций в C#)
- [Пошаговое руководство: Доступ к Интернету с помощью модификатора Async и оператора Await в C#](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Пример использования Async. Поток управления в асинхронных программах (C# и Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)
