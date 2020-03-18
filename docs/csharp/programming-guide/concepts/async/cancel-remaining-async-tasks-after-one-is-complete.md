---
title: Отмена оставшихся асинхронных задач после завершения одной из них (C#)
ms.date: 07/20/2015
ms.assetid: d3cebc74-c392-497b-b1e6-62a262eabe05
ms.openlocfilehash: e829254c1cd47da16b14aa9c2c90312a97b4b581
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169978"
---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-c"></a>Отмена оставшихся асинхронных задач после завершения одной из них (C#)
Используя метод <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> вместе с <xref:System.Threading.CancellationToken>, можно отменить все оставшиеся задачи после выполнения отдельной задачи. Метод `WhenAny` принимает аргумент, который представляет собой коллекцию задач. Метод запускает все задачи и возвращает одну задачу. Одна задача считается завершенной, когда завершена любая задача в коллекции.  
  
 В этом примере показано, как использовать маркер отмены в сочетании с `WhenAny` для приостановки завершения первой задачи из коллекции задач и отмены оставшихся задач. Каждая задача загружает содержимое веб-сайта. Пример отображает длину содержимого первой завершаемой загрузки и отменяет другие загрузки.  
  
> [!NOTE]
> Для выполнения примеров необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.  
  
## <a name="downloading-the-example"></a>Загрузка примера  
 Вы можете скачать весь проект Windows Presentation Foundation (WPF) со страницы [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea), а затем выполнить необходимые действия.  
  
1. Распакуйте загруженный файл, а затем запустите Visual Studio.  
  
2. В строке меню выберите **Файл**, **Открыть**, **Проект/Решение**.  
  
3. В диалоговом окне **Открытие проекта** откройте папку с примером кода, который вы распаковали, а затем откройте файл решения (SLN) для AsyncFineTuningCS.  
  
4. В **обозревателе решений** откройте контекстное меню проекта **CancelAfterOneTask** и выберите команду **Назначить запускаемым проектом**.  
  
5. Нажмите клавишу F5, чтобы запустить проект.  
  
     Нажмите сочетание клавиш CTRL+F5, чтобы запустить проект без отладки.  
  
6. Запустите программу несколько раз, чтобы убедиться, что разные задачи завершаются первыми.  
  
 Если вы не хотите скачивать проект, можете просмотреть файл MainWindow.xaml.cs в конце этого раздела.  
  
## <a name="building-the-example"></a>Построение примера  
 Пример в этом разделе добавляется в проект для отмены списка задач, разработка которого описывается в разделе [Отмена асинхронной задачи или списка задач (C#)](./cancel-an-async-task-or-a-list-of-tasks.md). В примере используется тот же пользовательский интерфейс, хотя кнопка **Отмена** не используется явно.  
  
 Для самостоятельной сборки примера шаг за шагом следуйте инструкциям в разделе "Загрузка примера", но выберите в качестве **запускаемого проекта** проект **CancelAfterOneTask**. Добавьте изменения, приведенные в данном разделе, в этот проект.  
  
 В файле MainWindow.xaml.cs проекта **CancelAListOfTasks** запустите переход, переместив шаги обработки для каждого веб-сайта из цикла в `AccessTheWebAsync` в следующий асинхронный метод.  
  
```csharp  
// ***Bundle the processing steps for a website into one async method.  
async Task<int> ProcessURLAsync(string url, HttpClient client, CancellationToken ct)  
{  
    // GetAsync returns a Task<HttpResponseMessage>.
    HttpResponseMessage response = await client.GetAsync(url, ct);  
  
    // Retrieve the website contents from the HttpResponseMessage.  
    byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
    return urlContents.Length;  
}  
```  
  
 В `AccessTheWebAsync` в этом примере используются запрос, метод <xref:System.Linq.Enumerable.ToArray%2A> и метод `WhenAny` для создания и запуска массива задач. Применение `WhenAny` к массиву возвращает одну задачу, которая, если ожидается, вычисляется как первая завершившаяся задача в массиве задач.  
  
 Внесите следующие изменения в `AccessTheWebAsync`. Звездочками отмечены изменения в файле кода.  
  
1. Закомментируйте или удалите цикл.  
  
2. Создайте запрос, который во время выполнения создает коллекцию общих заданий. Каждый вызов `ProcessURLAsync` возвращает <xref:System.Threading.Tasks.Task%601>, где `TResult` — это целое число.  
  
    ```csharp  
    // ***Create a query that, when executed, returns a collection of tasks.  
    IEnumerable<Task<int>> downloadTasksQuery =  
        from url in urlList select ProcessURLAsync(url, client, ct);  
    ```  
  
3. Вызовите `ToArray` для выполнения запроса и запуска задач. Применение метода `WhenAny` в следующем шаге будет выполнять запрос и запускать задачи без использования `ToArray`, однако этот режим может быть недоступен для других методов. Наиболее безопасным способом является явное принудительное выполнения запроса.  
  
    ```csharp  
    // ***Use ToArray to execute the query and start the download tasks.
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();  
    ```  
  
4. Вызовите `WhenAny` для коллекции задач. `WhenAny` возвращает `Task(Of Task(Of Integer))` или `Task<Task<int>>`.  То есть `WhenAny` возвращает задачу, которая вычисляется как одна задача `Task(Of Integer)` или `Task<int>`, если она ожидается. Одна задача — это первая завершившаяся задача в коллекции. Задача, которая завершается первой, назначается `firstFinishedTask`. `firstFinishedTask` имеет тип <xref:System.Threading.Tasks.Task%601>, где `TResult` является целым числом, поскольку это возвращаемый тип `ProcessURLAsync`.  
  
    ```csharp  
    // ***Call WhenAny and then await the result. The task that finishes
    // first is assigned to firstFinishedTask.  
    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
    ```  
  
5. В этом примере нас интересует только та задача, которая завершается первой. Таким образом, используйте <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> для отмены оставшихся задач.  
  
    ```csharp  
    // ***Cancel the rest of the downloads. You just want the first one.  
    cts.Cancel();  
    ```  
  
6. Наконец, мы ожидаем `firstFinishedTask` для получения длины скачанного содержимого.  
  
    ```csharp  
    var length = await firstFinishedTask;  
    resultsTextBox.Text += $"\r\nLength of the downloaded website:  {length}\r\n";
    ```  
  
 Запустите программу несколько раз, чтобы убедиться, что разные задачи завершаются первыми.  
  
## <a name="complete-example"></a>Полный пример  
 Приведенный ниже код — полный файл MainWindow.xaml.cs для примера. Звездочками помечаются элементы, добавленные для этого примера.  
  
 Обратите внимание на то, что необходимо добавить ссылку для <xref:System.Net.Http>.  
  
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
  
namespace CancelAfterOneTask  
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
                resultsTextBox.Text += "\r\nDownload complete.";  
            }  
            catch (OperationCanceledException)  
            {  
                resultsTextBox.Text += "\r\nDownload canceled.";  
            }  
            catch (Exception)  
            {  
                resultsTextBox.Text += "\r\nDownload failed.";  
            }  
  
            // Set the CancellationTokenSource to null when the download is complete.  
            cts = null;  
        }  
  
        // You can still include a Cancel button if you want to.  
        private void cancelButton_Click(object sender, RoutedEventArgs e)  
        {  
            if (cts != null)  
            {  
                cts.Cancel();  
            }  
        }  
  
        // Provide a parameter for the CancellationToken.  
        async Task AccessTheWebAsync(CancellationToken ct)  
        {  
            HttpClient client = new HttpClient();  
  
            // Call SetUpURLList to make a list of web addresses.  
            List<string> urlList = SetUpURLList();  
  
            // ***Comment out or delete the loop.  
            //foreach (var url in urlList)  
            //{  
            //    // GetAsync returns a Task<HttpResponseMessage>.
            //    // Argument ct carries the message if the Cancel button is chosen.
            //    // ***Note that the Cancel button can cancel all remaining downloads.  
            //    HttpResponseMessage response = await client.GetAsync(url, ct);  
  
            //    // Retrieve the website contents from the HttpResponseMessage.  
            //    byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
            //    resultsTextBox.Text +=  
            //        $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
            //}  
  
            // ***Create a query that, when executed, returns a collection of tasks.  
            IEnumerable<Task<int>> downloadTasksQuery =  
                from url in urlList select ProcessURLAsync(url, client, ct);  
  
            // ***Use ToArray to execute the query and start the download tasks.
            Task<int>[] downloadTasks = downloadTasksQuery.ToArray();  
  
            // ***Call WhenAny and then await the result. The task that finishes
            // first is assigned to firstFinishedTask.  
            Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
  
            // ***Cancel the rest of the downloads. You just want the first one.  
            cts.Cancel();  
  
            // ***Await the first completed task and display the results.
            // Run the program several times to demonstrate that different  
            // websites can finish first.  
            var length = await firstFinishedTask;  
            resultsTextBox.Text += $"\r\nLength of the downloaded website:  {length}\r\n";
        }  
  
        // ***Bundle the processing steps for a website into one async method.  
        async Task<int> ProcessURLAsync(string url, HttpClient client, CancellationToken ct)  
        {  
            // GetAsync returns a Task<HttpResponseMessage>.
            HttpResponseMessage response = await client.GetAsync(url, ct);  
  
            // Retrieve the website contents from the HttpResponseMessage.  
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
            return urlContents.Length;  
        }  
  
        // Add a method that creates a list of web addresses.  
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
    // Sample output:  
  
    // Length of the downloaded website:  158856  
  
    // Download complete.  
}  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md) (Тонкая настройка асинхронного приложения в C#)
- [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](./index.md)
- [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
