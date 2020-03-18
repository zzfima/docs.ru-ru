---
title: Отмена асинхронной задачи или списка задач (C#)
ms.date: 07/20/2015
ms.assetid: eec32dbb-70ea-4c88-bd27-fa2e34546914
ms.openlocfilehash: 93526f772f79e993767fd8f29087b6caf4e29468
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69595719"
---
# <a name="cancel-an-async-task-or-a-list-of-tasks-c"></a>Отмена асинхронной задачи или списка задач в C#

Вы можете настроить кнопку, которая позволит отменить асинхронное приложение в случае, если вы не захотите дожидаться его завершения. Выполнив код в приведенных ниже примерах, вы сможете добавить в приложение кнопку отмены, загружающую содержимое одного веб-сайта или список веб-сайтов.

В этих примерах используется пользовательский интерфейс, описанный в разделе [Настройка асинхронного приложения (C#)](./fine-tuning-your-async-application.md).

> [!NOTE]
> Для выполнения примеров необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.

## <a name="cancel-a-task"></a>Отмена задачи

Код в первом примере связывает кнопку **Отмена** с отдельной задачей загрузки. Если нажать эту кнопку, когда приложение загружает содержимое, загрузка будет отменена.

### <a name="download-the-example"></a>Скачивание примера

Вы можете скачать весь проект Windows Presentation Foundation (WPF) со страницы [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea), а затем выполнить необходимые действия.

1. Распакуйте загруженный файл, а затем запустите Visual Studio.

2. В строке меню выберите **Файл** > **Открыть** > **Решение или проект**.

3. В диалоговом окне **Открытие проекта** откройте папку с примером кода, который вы распаковали, а затем откройте файл решения (SLN) для AsyncFineTuningCS.

4. В **обозревателе решений** откройте контекстное меню проекта **CancelATask** и выберите команду **Назначить запускаемым проектом**.

5. Нажмите клавишу **F5**, чтобы запустить проект (или нажмите клавиши **Ctrl**+**F5**, чтобы запустить проект без отладки).

> [!TIP]
> Если не хотите скачивать проект, можете просмотреть файл MainWindow.xaml.cs в конце этого раздела.

### <a name="build-the-example"></a>Сборка примера
 Следующие изменения добавляют кнопку **Отмена** в приложение, загружающее веб-сайт. Если вы не хотите загружать или собирать пример, просмотрите конечный результат в разделе "Завершенные примеры" в конце раздела. Звездочками отмечены изменения в коде.

 Для самостоятельной сборки примера шаг за шагом выполните инструкции в разделе "Загрузка примера", но в качестве **запускаемого проекта** выберите проект **StarterCode**, а не **CancelATask**.

 Внесите в файл MainWindow.xaml.cs проекта указанные ниже изменения.

1. Объявите переменную `CancellationTokenSource`, `cts`, которая находится в области действия всех методов, имеющих к ней доступ.

    ```csharp
    public partial class MainWindow : Window
    {
        // ***Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;
    ```

2. Добавьте следующий обработчик событий для кнопки **Отмена**. Этот обработчик событий использует метод <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> для отправки уведомления в `cts` при запросе отмены пользователем.

    ```csharp
    // ***Add an event handler for the Cancel button.
    private void cancelButton_Click(object sender, RoutedEventArgs e)
    {
        if (cts != null)
        {
            cts.Cancel();
        }
    }
    ```

3. Внесите в обработчик событий указанные ниже изменения для кнопки **Пуск**, `startButton_Click`.

    - Создайте экземпляр `CancellationTokenSource`, `cts`.

        ```csharp
        // ***Instantiate the CancellationTokenSource.
        cts = new CancellationTokenSource();
        ```

    - В вызове `AccessTheWebAsync`, который скачивает содержимое заданного веб-сайта, отправьте свойство <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> объекта `cts` в качестве аргумента. Если запрашивается отмена, свойство `Token` распространяет сообщение. Добавьте блок catch, который отображает сообщение в случае, если пользователь решает отменить операцию загрузки. Эти изменения показаны в следующем примере кода.

        ```csharp
        try
        {
            // ***Send a token to carry the message if cancellation is requested.
            int contentLength = await AccessTheWebAsync(cts.Token);
            resultsTextBox.Text += $"\r\nLength of the downloaded string: {contentLength}.\r\n";
        }
        // *** If cancellation is requested, an OperationCanceledException results.
        catch (OperationCanceledException)
        {
            resultsTextBox.Text += "\r\nDownload canceled.\r\n";
        }
        catch (Exception)
        {
            resultsTextBox.Text += "\r\nDownload failed.\r\n";
        }
        ```

4. В `AccessTheWebAsync` используйте перегрузку <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> метода `GetAsync` в типе <xref:System.Net.Http.HttpClient> для скачивания содержимого веб-сайта. Передайте `ct` параметр <xref:System.Threading.CancellationToken> метода `AccessTheWebAsync` в качестве второго аргумента. Благодаря токену, если пользователь нажмет кнопку **Отмена**, будет выведено соответствующее сообщение.

     Эти изменения в `AccessTheWebAsync` показаны в следующем примере кода.

    ```csharp
    // ***Provide a parameter for the CancellationToken.
    async Task<int> AccessTheWebAsync(CancellationToken ct)
    {
        HttpClient client = new HttpClient();

        resultsTextBox.Text += "\r\nReady to download.\r\n";

        // You might need to slow things down to have a chance to cancel.
        await Task.Delay(250);

        // GetAsync returns a Task<HttpResponseMessage>.
        // ***The ct argument carries the message if the Cancel button is chosen.
        HttpResponseMessage response = await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct);

        // Retrieve the website contents from the HttpResponseMessage.
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

        // The result of the method is the length of the downloaded website.
        return urlContents.Length;
    }
    ```

5. Если программа не отменяется, она выдает представленный ниже результат.

    ```text
    Ready to download.
    Length of the downloaded string: 158125.
    ```

     Если вы нажмете кнопку **Отмена**, прежде чем программа завершит загрузку содержимого, будет выдан представленный ниже результат.

    ```text
    Ready to download.
    Download canceled.
    ```

## <a name="cancel-a-list-of-tasks"></a>Отмена списка задач

Вы можете расширить предыдущий пример до отмены сразу нескольких задач, связав с каждой из них один и тот же экземпляр `CancellationTokenSource`. В этом случае кнопка **Отмена** отменяет сразу все незавершенные задачи.

### <a name="download-the-example"></a>Скачивание примера

Вы можете скачать весь проект Windows Presentation Foundation (WPF) со страницы [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea), а затем выполнить необходимые действия.

1. Распакуйте загруженный файл, а затем запустите Visual Studio.

2. В строке меню выберите **Файл** > **Открыть** > **Решение или проект**.

3. В диалоговом окне **Открытие проекта** откройте папку с примером кода, который вы распаковали, а затем откройте файл решения (SLN) для AsyncFineTuningCS.

4. В **обозревателе решений** откройте контекстное меню проекта **CancelAListOfTasks** и выберите команду **Назначить запускаемым проектом**.

5. Нажмите клавишу **F5**, чтобы запустить проект.

     Нажмите клавиши **CTRL**+**F5**, чтобы запустить проект без отладки.

Если не хотите скачивать проект, можете просмотреть файл MainWindow.xaml.cs в конце этого раздела.

### <a name="build-the-example"></a>Сборка примера

Для самостоятельного построения примера шаг за шагом выполните инструкции в разделе "Загрузка примера", но выберите **CancelATask** как **запускаемый проект**. Добавьте в проект указанные ниже изменения. Звездочками отмечены изменения в программе.

1. Добавьте метод для создания списка веб-адресов.

    ```csharp
    // ***Add a method that creates a list of web addresses.
    private List<string> SetUpURLList()
    {
        List<string> urls = new List<string>
        {
            "https://msdn.microsoft.com",
            "https://msdn.microsoft.com/library/hh290138.aspx",
            "https://msdn.microsoft.com/library/hh290140.aspx",
            "https://msdn.microsoft.com/library/dd470362.aspx",
            "https://msdn.microsoft.com/library/aa578028.aspx",
            "https://msdn.microsoft.com/library/ms404677.aspx",
            "https://msdn.microsoft.com/library/ff730837.aspx"
        };
        return urls;
    }
    ```

2. Вызовите метод в `AccessTheWebAsync`.

    ```csharp
    // ***Call SetUpURLList to make a list of web addresses.
    List<string> urlList = SetUpURLList();
    ```

3. Добавьте в `AccessTheWebAsync` следующий цикл для обработки каждого веб-адреса в списке.

    ```csharp
    // ***Add a loop to process the list of web addresses.
    foreach (var url in urlList)
    {
        // GetAsync returns a Task<HttpResponseMessage>.
        // Argument ct carries the message if the Cancel button is chosen.
        // ***Note that the Cancel button can cancel all remaining downloads.
        HttpResponseMessage response = await client.GetAsync(url, ct);

        // Retrieve the website contents from the HttpResponseMessage.
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

        resultsTextBox.Text +=
            $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
    }
    ```

4. Поскольку `AccessTheWebAsync` отображает длину, метод не должен ничего возвращать. Удалите инструкцию return и измените тип возвращаемого значения на <xref:System.Threading.Tasks.Task> вместо <xref:System.Threading.Tasks.Task%601>.

    ```csharp
    async Task AccessTheWebAsync(CancellationToken ct)
    ```

     Вызовите метод из `startButton_Click`, используя не выражение, а оператор.

    ```csharp
    await AccessTheWebAsync(cts.Token);
    ```

5. Если программа не отменяется, она выдает представленный ниже результат.

    ```text
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Length of the downloaded string: 158124.

    Length of the downloaded string: 204890.

    Length of the downloaded string: 175488.

    Length of the downloaded string: 145790.

    Downloads complete.
    ```

     При нажатии кнопки **Отмена** до завершения загрузки выходные данные будут включать объем данных, загруженных до отмены.

    ```text
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Downloads canceled.
    ```

## <a name="complete-examples"></a>Полные примеры

Следующие разделы содержат код каждого из приведенных выше примеров. Обратите внимание на то, что необходимо добавить ссылку для <xref:System.Net.Http>.

Проекты можно загрузить со страницы [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).

### <a name="example---cancel-a-task"></a>Пример отмены задачи

Приведенный ниже код представляет собой полный файл MainWindow.xaml.cs, демонстрирующий отмену отдельной задачи.

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

// Add a using directive and a reference for System.Net.Http.
using System.Net.Http;

// Add the following using directive for System.Threading.

using System.Threading;
namespace CancelATask
{
    public partial class MainWindow : Window
    {
        // ***Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;

        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            // ***Instantiate the CancellationTokenSource.
            cts = new CancellationTokenSource();

            resultsTextBox.Clear();

            try
            {
                // ***Send a token to carry the message if cancellation is requested.
                int contentLength = await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {contentLength}.\r\n";
            }
            // *** If cancellation is requested, an OperationCanceledException results.
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownload canceled.\r\n";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownload failed.\r\n";
            }

            // ***Set the CancellationTokenSource to null when the download is complete.
            cts = null;
        }

        // ***Add an event handler for the Cancel button.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        // ***Provide a parameter for the CancellationToken.
        async Task<int> AccessTheWebAsync(CancellationToken ct)
        {
            HttpClient client = new HttpClient();

            resultsTextBox.Text += "\r\nReady to download.\r\n";

            // You might need to slow things down to have a chance to cancel.
            await Task.Delay(250);

            // GetAsync returns a Task<HttpResponseMessage>.
            // ***The ct argument carries the message if the Cancel button is chosen.
            HttpResponseMessage response = await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct);

            // Retrieve the website contents from the HttpResponseMessage.
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

            // The result of the method is the length of the downloaded website.
            return urlContents.Length;
        }
    }

    // Output for a successful download:

    // Ready to download.

    // Length of the downloaded string: 158125.

    // Or, if you cancel:

    // Ready to download.

    // Download canceled.
}
```

### <a name="example---cancel-a-list-of-tasks"></a>Примеры отмены списка задач

Приведенный ниже код представляет собой полный файл MainWindow.xaml.cs, демонстрирующий отмену списка задач.

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

// Add a using directive and a reference for System.Net.Http.
using System.Net.Http;

// Add the following using directive for System.Threading.
using System.Threading;

namespace CancelAListOfTasks
{
    public partial class MainWindow : Window
    {
        // Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;

        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            // Instantiate the CancellationTokenSource.
            cts = new CancellationTokenSource();

            resultsTextBox.Clear();

            try
            {
                await AccessTheWebAsync(cts.Token);
                // ***Small change in the display lines.
                resultsTextBox.Text += "\r\nDownloads complete.";
            }
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownloads canceled.";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownloads failed.";
            }

            // Set the CancellationTokenSource to null when the download is complete.
            cts = null;
        }

        // Add an event handler for the Cancel button.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        // Provide a parameter for the CancellationToken.
        // ***Change the return type to Task because the method has no return statement.
        async Task AccessTheWebAsync(CancellationToken ct)
        {
            // Declare an HttpClient object.
            HttpClient client = new HttpClient();

            // ***Call SetUpURLList to make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // ***Add a loop to process the list of web addresses.
            foreach (var url in urlList)
            {
                // GetAsync returns a Task<HttpResponseMessage>.
                // Argument ct carries the message if the Cancel button is chosen.
                // ***Note that the Cancel button can cancel all remaining downloads.
                HttpResponseMessage response = await client.GetAsync(url, ct);

                // Retrieve the website contents from the HttpResponseMessage.
                byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
            }
        }

        // ***Add a method that creates a list of web addresses.
        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }
    }

    // Output if you do not choose to cancel:

    //Length of the downloaded string: 35939.

    //Length of the downloaded string: 237682.

    //Length of the downloaded string: 128607.

    //Length of the downloaded string: 158124.

    //Length of the downloaded string: 204890.

    //Length of the downloaded string: 175488.

    //Length of the downloaded string: 145790.

    //Downloads complete.

    // Sample output if you choose to cancel:

    //Length of the downloaded string: 35939.

    //Length of the downloaded string: 237682.

    //Length of the downloaded string: 128607.

    //Downloads canceled.
}
```

## <a name="see-also"></a>См. также раздел

- <xref:System.Threading.CancellationTokenSource>
- <xref:System.Threading.CancellationToken>
- [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](./index.md)
- [Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md) (Тонкая настройка асинхронного приложения в C#)
- [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
