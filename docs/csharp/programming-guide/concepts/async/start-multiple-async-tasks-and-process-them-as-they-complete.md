---
title: Обработка асинхронных задач по мере завершения
ms.date: 09/12/2018
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: b618fd6bf80551231d2b285fd0e8aef688d00d93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "71736730"
---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-c"></a>Запуск нескольких асинхронных задач и их обработка по мере завершения (C#)

С помощью <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> можно запускать несколько задач одновременно и обрабатывать их по одной по мере завершения, а не в порядке их запуска.

В следующем примере используется запрос для создания коллекции задач. Каждая задача загружает содержимое указанного веб-сайта. В каждой итерации цикла while ожидаемый вызов `WhenAny` возвращает задачу из коллекции задач, которая первой завершает свою загрузку. Эта задача удаляется из коллекции и обрабатывается. Цикл выполняется до тех пор, пока в коллекции еще есть задачи.

> [!NOTE]
> Для выполнения примеров необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.

## <a name="download-an-example-solution"></a>Скачивание примера решения

Вы можете скачать весь проект Windows Presentation Foundation (WPF) со страницы [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea), а затем выполнить необходимые действия.

> [!TIP]
> Если вы не хотите скачивать проект, просто изучите файл *MainWindow.xaml.cs* в конце этого раздела.

1. Извлеките файлы из скачанного *ZIP-файла* и запустите Visual Studio.

2. В строке меню выберите **Файл** > **Открыть** > **Решение или проект**.

3. В диалоговом окне **Открытие проекта** откройте папку с примером кода, который вы скачали, а затем файл решения (в формате *SLN*) *AsyncFineTuningCS*/*AsyncFineTuningVB*.

4. В **обозревателе решений** откройте контекстное меню проекта **ProcessTasksAsTheyFinish** и выберите команду **Назначить запускаемым проектом**.

5. Нажмите клавишу <kbd>F5</kbd>, чтобы запустить программу с отладкой (или нажмите сочетание клавиш <kbd>Ctrl</kbd>+<kbd>F5</kbd>, чтобы запустить программу без отладки).

6. Запустите проект несколько раз, чтобы проверить, что загруженные размеры не всегда отображаются в одинаковом порядке.

## <a name="create-the-program-yourself"></a>Самостоятельное создание программы

Код из этого примера добавляется к коду, который вы создали в руководстве [Отмена оставшихся асинхронных задач после завершения одной из них (C#)](cancel-remaining-async-tasks-after-one-is-complete.md), и использует тот же пользовательский интерфейс.

Чтобы самостоятельно собрать пример, шаг за шагом выполните инструкции из раздела [Скачивание примера](cancel-remaining-async-tasks-after-one-is-complete.md#downloading-the-example), выбрав в качестве запускаемого проекта **CancelAfterOneTask**. Добавьте изменения в данном разделе в метод `AccessTheWebAsync` в этом проекте. Изменения помечены звездочками.

Проект **CancelAfterOneTask** уже содержит запрос, который при выполнении создает коллекцию задач. Каждый вызов `ProcessURLAsync` в следующем коде возвращает <xref:System.Threading.Tasks.Task%601>, где `TResult` — целое число.

```csharp
IEnumerable<Task<int>> downloadTasksQuery = from url in urlList select ProcessURL(url, client, ct);
```

В файле *MainWindow.xaml.cs* этого проекта внесите следующие изменения в метод `AccessTheWebAsync`:

- Выполните запрос, применяя <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> вместо <xref:System.Linq.Enumerable.ToArray%2A>.

    ```csharp
    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();
    ```

- Добавьте цикл `while`, который выполняет следующие действия для каждой задачи в коллекции.

    1. Ожидает вызов `WhenAny` для определения первой задачи в коллекции, чтобы завершить ее загрузку.

        ```csharp
        Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);
        ```

    2. Удаляет эту задачу из коллекции.

        ```csharp
        downloadTasks.Remove(firstFinishedTask);
        ```

    3. Ожидает `firstFinishedTask`, возвращаемый при вызове `ProcessURLAsync`. Переменная `firstFinishedTask` представляет собой <xref:System.Threading.Tasks.Task%601>, где `TReturn` — целое число. Задача уже завершена, но она ожидается для получения размера загруженного веб-сайта, как показано в следующем примере. В случае сбоя задачи `await` выдаст первое исключение дочернего элемента, хранящееся в `AggregateException`, в отличие от считывания свойства `Result`, которое выдаст `AggregateException`.

        ```csharp
        int length = await firstFinishedTask;
        resultsTextBox.Text += $"\r\nLength of the download:  {length}";
        ```

Запустите проект несколько раз и убедитесь, что размеры скачанных файлов не всегда отображаются в одном и том же порядке.

> [!CAUTION]
> Можно использовать `WhenAny` в цикле, как описано в примере, для решения проблем, которые включают небольшое число задач. Однако когда требуется обработка большого числа задач, другие методы будут более эффективны. Дополнительные сведения и примеры см. в разделе [Обработка задач по мере их завершения](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete/).

## <a name="complete-example"></a>Полный пример

Приведенный ниже код — это полный текст файла *MainWindow.xaml.cs* для примера. Звездочками помечаются элементы, добавленные для этого примера. Также обратите внимание, что необходимо добавить ссылку для <xref:System.Net.Http>.

Можно загрузить проект со страницы [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).

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

// Add the following using directive.
using System.Threading;

namespace ProcessTasksAsTheyFinish
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
            resultsTextBox.Clear();

            // Instantiate the CancellationTokenSource.
            cts = new CancellationTokenSource();

            try
            {
                await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text += "\r\nDownloads complete.";
            }
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownloads canceled.\r\n";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownloads failed.\r\n";
            }

            cts = null;
        }

        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        async Task AccessTheWebAsync(CancellationToken ct)
        {
            HttpClient client = new HttpClient();

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // ***Create a query that, when executed, returns a collection of tasks.
            IEnumerable<Task<int>> downloadTasksQuery =
                from url in urlList select ProcessURL(url, client, ct);

            // ***Use ToList to execute the query and start the tasks.
            List<Task<int>> downloadTasks = downloadTasksQuery.ToList();

            // ***Add a loop to process the tasks one at a time until none remain.
            while (downloadTasks.Count > 0)
            {
                    // Identify the first task that completes.
                    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);

                    // ***Remove the selected task from the list so that you don't
                    // process it more than once.
                    downloadTasks.Remove(firstFinishedTask);

                    // Await the completed task.
                    int length = await firstFinishedTask;
                    resultsTextBox.Text += $"\r\nLength of the download:  {length}";
            }
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        async Task<int> ProcessURL(string url, HttpClient client, CancellationToken ct)
        {
            // GetAsync returns a Task<HttpResponseMessage>.
            HttpResponseMessage response = await client.GetAsync(url, ct);

            // Retrieve the website contents from the HttpResponseMessage.
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

            return urlContents.Length;
        }
    }
}

// Sample Output:

// Length of the download:  226093
// Length of the download:  412588
// Length of the download:  175490
// Length of the download:  204890
// Length of the download:  158855
// Length of the download:  145790
// Length of the download:  44908
// Downloads complete.
```

## <a name="see-also"></a>См. также раздел

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [Fine-Tuning Your Async Application (C#)](fine-tuning-your-async-application.md) (Тонкая настройка асинхронного приложения в C#)
- [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](index.md)
- [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
