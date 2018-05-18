---
title: Запуск нескольких асинхронных задач и их обработка по мере завершения (C#)
ms.date: 07/20/2015
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: 29dc629abae13bb7ba3a9b0cb87300e6d1cbe2d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-c"></a>Запуск нескольких асинхронных задач и их обработка по мере завершения (C#)
С помощью <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> можно запускать несколько задач одновременно и обрабатывать их по одной по мере завершения, а не в порядке их запуска.  
  
 В следующем примере используется запрос для создания коллекции задач. Каждая задача загружает содержимое указанного веб-сайта. В каждой итерации цикла while ожидаемый вызов `WhenAny` возвращает задачу из коллекции задач, которая первой завершает свою загрузку. Эта задача удаляется из коллекции и обрабатывается. Цикл выполняется до тех пор, пока в коллекции еще есть задачи.  
  
> [!NOTE]
>  Для выполнения примеров необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.  
  
## <a name="downloading-the-example"></a>Загрузка примера  
 Вы можете скачать весь проект Windows Presentation Foundation (WPF) со страницы [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea), а затем выполнить необходимые действия.  
  
1.  Распакуйте загруженный файл, а затем запустите Visual Studio.  
  
2.  В строке меню выберите **Файл**, **Открыть**, **Проект/Решение**.  
  
3.  В диалоговом окне **Открытие проекта** откройте папку с примером кода, который вы распаковали, а затем откройте файл решения (SLN) для AsyncFineTuningCS.  
  
4.  В **обозревателе решений** откройте контекстное меню проекта **ProcessTasksAsTheyFinish** и выберите команду **Назначить запускаемым проектом**.  
  
5.  Нажмите клавишу F5, чтобы запустить проект.  
  
     Нажмите сочетание клавиш CTRL+F5, чтобы запустить проект без отладки.  
  
6.  Запустите проект несколько раз, чтобы проверить, что загруженные размеры не всегда отображаются в одинаковом порядке.  
  
 Если вы не хотите скачивать проект, можете просмотреть файл MainWindow.xaml.cs в конце этого раздела.  
  
## <a name="building-the-example"></a>Построение примера  
 Код из этого примера добавляется к коду, разработанному в разделе [Отмена оставшихся асинхронных задач после завершения одной из них (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)[Отмена оставшихся асинхронных задач после завершения одной из них](http://msdn.microsoft.com/library/8e800b58-235a-44b7-a02c-fa4375591d76), и использует тот же пользовательский интерфейс.  
  
 Для самостоятельной сборки примера шаг за шагом следуйте инструкциям в разделе "Загрузка примера", но выберите **CancelAfterOneTask** как **запускаемый проект**. Добавьте изменения в данном разделе в метод `AccessTheWebAsync` в этом проекте. Изменения помечены звездочками.  
  
 Проект **CancelAfterOneTask** уже содержит запрос, который при выполнении создает коллекцию задач. Каждый вызов `ProcessURLAsync` в следующем коде возвращает <xref:System.Threading.Tasks.Task%601>, где `TResult` — целое число.  
  
```csharp  
IEnumerable<Task<int>> downloadTasksQuery =  
    from url in urlList select ProcessURL(url, client, ct);  
```  
  
 В файле MainWindow.xaml.cs проекта внесите следующие изменения в метод `AccessTheWebAsync`.  
  
-   Выполните запрос, применяя <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> вместо <xref:System.Linq.Enumerable.ToArray%2A>.  
  
    ```csharp  
    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();  
    ```  
  
-   Добавьте цикл while, выполняющий следующие действия для каждой задачи в коллекции.  
  
    1.  Ожидает вызов `WhenAny` для определения первой задачи в коллекции, чтобы завершить ее загрузку.  
  
        ```csharp  
        Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
        ```  
  
    2.  Удаляет эту задачу из коллекции.  
  
        ```csharp  
        downloadTasks.Remove(firstFinishedTask);  
        ```  
  
    3.  Ожидает `firstFinishedTask`, возвращаемый при вызове `ProcessURLAsync`. Переменная `firstFinishedTask` представляет собой <xref:System.Threading.Tasks.Task%601>, где `TReturn` — целое число. Задача уже завершена, но она ожидается для получения размера загруженного веб-сайта, как показано в следующем примере.  
  
        ```csharp  
        int length = await firstFinishedTask;  
        resultsTextBox.Text += String.Format("\r\nLength of the download:  {0}", length);  
        ```  
  
 Следует запустить проект несколько раз для проверки, что загруженные размеры не всегда отображаются в одинаковом порядке.  
  
> [!CAUTION]
>  Можно использовать `WhenAny` в цикле, как описано в примере, для решения проблем, которые включают небольшое число задач. Однако когда требуется обработка большого числа задач, другие методы будут более эффективны. Дополнительные сведения и примеры см. в разделе [Обработка задач по мере их завершения](https://blogs.msdn.microsoft.com/pfxteam/2012/08/02/processing-tasks-as-they-complete/).  
  
## <a name="complete-example"></a>Полный пример  
 Приведенный ниже код — полный текст файла MainWindow.xaml.cs для примера. Звездочками помечаются элементы, добавленные для этого примера.  
  
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
                    resultsTextBox.Text += String.Format("\r\nLength of the download:  {0}", length);  
            }  
        }  
  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>   
            {   
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Tasks.Task.WhenAny%2A>  
 [Fine-Tuning Your Async Application (C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md) (Тонкая настройка асинхронного приложения в C#)  
 [Асинхронное программирование с использованием ключевых слов async и await (C#)](../../../../csharp/programming-guide/concepts/async/index.md)  
 [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Пример использования async. Тонкая настройка асинхронного приложения)
