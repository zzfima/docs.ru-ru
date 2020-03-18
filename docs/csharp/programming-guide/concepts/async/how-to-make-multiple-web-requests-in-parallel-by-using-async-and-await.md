---
title: Практическое руководство. Параллельное выполнение нескольких веб-запросов с использованием Async и Await (C#)
ms.date: 07/20/2015
ms.assetid: 19745899-f97a-4499-a7c7-e813d1447580
ms.openlocfilehash: 9f7420113d4af83d7d057b772af307bd8d4bcc00
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169953"
---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-c"></a>Практическое руководство. Параллельное выполнение нескольких веб-запросов с использованием Async и Await (C#)
В асинхронном методе задачи запускаются в момент создания. Оператор [Await](../../../language-reference/operators/await.md) применяется к задаче в той точке в методе, где обработка не может продолжаться до завершения задачи. Часто задачи ожидаются в момент создания, как показано в следующем примере.  
  
```csharp  
var result = await someWebAccessMethodAsync(url);  
```  
  
 Тем не менее можно отделить создание задачи от ее ожидания, если программа содержит другую работу, выполнение которой не зависит от завершения задачи.  
  
```csharp  
// The following line creates and starts the task.  
var myTask = someWebAccessMethodAsync(url);  
  
// While the task is running, you can do other work that doesn't depend  
// on the results of the task.  
// . . . . .  
  
// The application of await suspends the rest of this method until the task is complete.  
var result = await myTask;  
```  
  
 Между моментом запуска задачи и ее ожиданием можно запустить другие задачи. Дополнительные задачи неявно выполняются параллельно, однако дополнительные потоки не создаются.  
  
 Следующая программа запускает три асинхронные веб-загрузки, а затем ожидает их в том порядке, в котором они вызываются. Обратите внимание, что при запуске программы задачи не всегда завершаются в том порядке, в котором они созданы и ожидаются. Они начинают выполняться в момент создания, и одна или несколько задач могут завершиться прежде, чем метод достигает выражения await.  
  
> [!NOTE]
> Для выполнения этого проекта необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.  
  
 Другой пример, в котором одновременно запускается несколько задач, см. в разделе [Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).
  
 Код для этого примера можно скачать на странице [Примеры кода от разработчиков](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e).  
  
### <a name="to-set-up-the-project"></a>Настройка проекта  
  
1. Чтобы настроить приложение WPF, выполните следующие действия. Подробные инструкции для выполнения этих действий можно найти в разделе [Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).  
  
    - Создайте приложение WPF, которое содержит текстовое поле и кнопку. Назовите кнопку `startButton`, а текстовое поле — `resultsTextBox`.  
  
    - Добавьте ссылку для <xref:System.Net.Http>.  
  
    - Добавьте в файл MainWindow.xaml.cs директиву `using` для `System.Net.Http`.  
  
### <a name="to-add-the-code"></a>Добавление кода  
  
1. В окне конструктора для MainWindow.xaml дважды нажмите кнопку, чтобы создать обработчик события `startButton_Click` в файле MainWindow.xaml.cs.  
  
2. Скопируйте следующий код в тело `startButton_Click` в файле MainWindow.xaml.cs.  
  
    ```csharp  
    resultsTextBox.Clear();  
    await CreateMultipleTasksAsync();  
    resultsTextBox.Text += "\r\n\r\nControl returned to startButton_Click.\r\n";  
    ```  
  
     Код вызывает асинхронный метод `CreateMultipleTasksAsync`, который управляет приложением.  
  
3. Добавьте следующие вспомогательные методы в проект:  
  
    - `ProcessURLAsync` использует метод <xref:System.Net.Http.HttpClient> для скачивания содержимого веб-сайта в виде массива байтов. Вспомогательный метод `ProcessURLAsync` затем отображает и возвращает длину массива.  
  
    - `DisplayResults` показывает число байтов в массиве байтов для каждого URL-адреса. Эти выходные данные показывают, когда именно каждая задача завершает загрузку.  
  
     Скопируйте следующие методы и вставьте их после обработчика событий `startButton_Click` в файле MainWindow.xaml.cs.  
  
    ```csharp  
    async Task<int> ProcessURLAsync(string url, HttpClient client)  
    {  
        var byteArray = await client.GetByteArrayAsync(url);  
        DisplayResults(url, byteArray);  
        return byteArray.Length;  
    }  
  
    private void DisplayResults(string url, byte[] content)  
    {  
        // Display the length of each website. The string format
        // is designed to be used with a monospaced font, such as  
        // Lucida Console or Global Monospace.  
        var bytes = content.Length;  
        // Strip off the "https://".  
        var displayURL = url.Replace("https://", "");  
        resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
    }  
    ```  
  
4. Наконец, определите метод `CreateMultipleTasksAsync`, который выполняет следующие действия.  
  
    - Этот метод объявляет объект `HttpClient`, который используется методом доступа <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> в `ProcessURLAsync`.  
  
    - Метод создает и запускает три задачи типа <xref:System.Threading.Tasks.Task%601>, где `TResult` является целым числом. При завершении каждой задачи `DisplayResults` отображает URL-адрес и длину загруженного содержимого задачи. Поскольку задачи выполняются асинхронно, порядок, в котором отображаются результаты, может отличаться от порядка, в котором они были объявлены.  
  
    - Метод ожидает завершения каждой задачи. Каждый оператор `await` приостанавливает выполнение `CreateMultipleTasksAsync` до завершения выполнения ожидаемой задачи. Оператор также получает возвращаемое значение вызова `ProcessURLAsync` от каждой завершенной задачи.  
  
    - После завершения задач и получения целочисленных значений метод суммирует длину веб-сайтов и отображает результат.  
  
     Скопируйте следующий метод и вставьте его в решение.  
  
    ```csharp  
    private async Task CreateMultipleTasksAsync()  
    {  
        // Declare an HttpClient object, and increase the buffer size. The  
        // default buffer size is 65,536.  
        HttpClient client =  
            new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
  
        // Create and start the tasks. As each task finishes, DisplayResults
        // displays its length.  
        Task<int> download1 =
            ProcessURLAsync("https://msdn.microsoft.com", client);  
        Task<int> download2 =
            ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client);  
        Task<int> download3 =
            ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client);  
  
        // Await each task.  
        int length1 = await download1;  
        int length2 = await download2;  
        int length3 = await download3;  
  
        int total = length1 + length2 + length3;  
  
        // Display the total count for the downloaded websites.  
        resultsTextBox.Text += $"\r\n\r\nTotal bytes returned:  {total}\r\n";
    }  
    ```  
  
5. Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .  
  
     Запустите программу несколько раз, чтобы убедиться, что три задачи не всегда завершаются в том же порядке, а порядок их завершения не обязательно совпадает с порядком, в котором они создаются и ожидаются.  
  
## <a name="example"></a>Пример  
 Следующий код содержит полный пример.  
  
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
  
// Add the following using directive, and add a reference for System.Net.Http.  
using System.Net.Http;  
  
namespace AsyncExample_MultipleTasks  
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
            await CreateMultipleTasksAsync();  
            resultsTextBox.Text += "\r\n\r\nControl returned to startButton_Click.\r\n";  
        }  
  
        private async Task CreateMultipleTasksAsync()  
        {  
            // Declare an HttpClient object, and increase the buffer size. The  
            // default buffer size is 65,536.  
            HttpClient client =  
                new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
  
            // Create and start the tasks. As each task finishes, DisplayResults
            // displays its length.  
            Task<int> download1 =
                ProcessURLAsync("https://msdn.microsoft.com", client);  
            Task<int> download2 =
                ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client);  
            Task<int> download3 =
                ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client);  
  
            // Await each task.  
            int length1 = await download1;  
            int length2 = await download2;  
            int length3 = await download3;  
  
            int total = length1 + length2 + length3;  
  
            // Display the total count for the downloaded websites.  
            resultsTextBox.Text += $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }  
  
        async Task<int> ProcessURLAsync(string url, HttpClient client)  
        {  
            var byteArray = await client.GetByteArrayAsync(url);  
            DisplayResults(url, byteArray);  
            return byteArray.Length;  
        }  
  
        private void DisplayResults(string url, byte[] content)  
        {  
            // Display the length of each website. The string format
            // is designed to be used with a monospaced font, such as  
            // Lucida Console or Global Monospace.  
            var bytes = content.Length;  
            // Strip off the "https://".  
            var displayURL = url.Replace("https://", "");  
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }  
}  
```  
  
## <a name="see-also"></a>См. также раздел

- [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) (Пошаговое руководство. Обращение к веб-сайтам с помощью async и await в C#)
- [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](./index.md)
- [Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
