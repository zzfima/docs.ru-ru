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
# <a name="cancel-remaining-async-tasks-after-one-is-complete-c"></a><span data-ttu-id="50dae-102">Отмена оставшихся асинхронных задач после завершения одной из них (C#)</span><span class="sxs-lookup"><span data-stu-id="50dae-102">Cancel Remaining Async Tasks after One Is Complete (C#)</span></span>
<span data-ttu-id="50dae-103">Используя метод <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> вместе с <xref:System.Threading.CancellationToken>, можно отменить все оставшиеся задачи после выполнения отдельной задачи.</span><span class="sxs-lookup"><span data-stu-id="50dae-103">By using the <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> method together with a <xref:System.Threading.CancellationToken>, you can cancel all remaining tasks when one task is complete.</span></span> <span data-ttu-id="50dae-104">Метод `WhenAny` принимает аргумент, который представляет собой коллекцию задач.</span><span class="sxs-lookup"><span data-stu-id="50dae-104">The `WhenAny` method takes an argument that’s a collection of tasks.</span></span> <span data-ttu-id="50dae-105">Метод запускает все задачи и возвращает одну задачу.</span><span class="sxs-lookup"><span data-stu-id="50dae-105">The method starts all the tasks and returns a single task.</span></span> <span data-ttu-id="50dae-106">Одна задача считается завершенной, когда завершена любая задача в коллекции.</span><span class="sxs-lookup"><span data-stu-id="50dae-106">The single task is complete when any task in the collection is complete.</span></span>  
  
 <span data-ttu-id="50dae-107">В этом примере показано, как использовать маркер отмены в сочетании с `WhenAny` для приостановки завершения первой задачи из коллекции задач и отмены оставшихся задач.</span><span class="sxs-lookup"><span data-stu-id="50dae-107">This example demonstrates how to use a cancellation token in conjunction with `WhenAny` to hold onto the first task to finish from the collection of tasks and to cancel the remaining tasks.</span></span> <span data-ttu-id="50dae-108">Каждая задача загружает содержимое веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="50dae-108">Each task downloads the contents of a website.</span></span> <span data-ttu-id="50dae-109">Пример отображает длину содержимого первой завершаемой загрузки и отменяет другие загрузки.</span><span class="sxs-lookup"><span data-stu-id="50dae-109">The example displays the length of the contents of the first download to complete and cancels the other downloads.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50dae-110">Для выполнения примеров необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="50dae-110">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="50dae-111">Загрузка примера</span><span class="sxs-lookup"><span data-stu-id="50dae-111">Downloading the Example</span></span>  
 <span data-ttu-id="50dae-112">Вы можете скачать весь проект Windows Presentation Foundation (WPF) со страницы [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea), а затем выполнить необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="50dae-112">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>  
  
1. <span data-ttu-id="50dae-113">Распакуйте загруженный файл, а затем запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="50dae-113">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2. <span data-ttu-id="50dae-114">В строке меню выберите **Файл**, **Открыть**, **Проект/Решение**.</span><span class="sxs-lookup"><span data-stu-id="50dae-114">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3. <span data-ttu-id="50dae-115">В диалоговом окне **Открытие проекта** откройте папку с примером кода, который вы распаковали, а затем откройте файл решения (SLN) для AsyncFineTuningCS.</span><span class="sxs-lookup"><span data-stu-id="50dae-115">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>  
  
4. <span data-ttu-id="50dae-116">В **обозревателе решений** откройте контекстное меню проекта **CancelAfterOneTask** и выберите команду **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="50dae-116">In **Solution Explorer**, open the shortcut menu for the **CancelAfterOneTask** project, and then choose **Set as StartUp Project**.</span></span>  
  
5. <span data-ttu-id="50dae-117">Нажмите клавишу F5, чтобы запустить проект.</span><span class="sxs-lookup"><span data-stu-id="50dae-117">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="50dae-118">Нажмите сочетание клавиш CTRL+F5, чтобы запустить проект без отладки.</span><span class="sxs-lookup"><span data-stu-id="50dae-118">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6. <span data-ttu-id="50dae-119">Запустите программу несколько раз, чтобы убедиться, что разные задачи завершаются первыми.</span><span class="sxs-lookup"><span data-stu-id="50dae-119">Run the program several times to verify that different downloads finish first.</span></span>  
  
 <span data-ttu-id="50dae-120">Если вы не хотите скачивать проект, можете просмотреть файл MainWindow.xaml.cs в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="50dae-120">If you don't want to download the project, you can review the MainWindow.xaml.cs file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="50dae-121">Построение примера</span><span class="sxs-lookup"><span data-stu-id="50dae-121">Building the Example</span></span>  
 <span data-ttu-id="50dae-122">Пример в этом разделе добавляется в проект для отмены списка задач, разработка которого описывается в разделе [Отмена асинхронной задачи или списка задач (C#)](./cancel-an-async-task-or-a-list-of-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="50dae-122">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) to cancel a list of tasks.</span></span> <span data-ttu-id="50dae-123">В примере используется тот же пользовательский интерфейс, хотя кнопка **Отмена** не используется явно.</span><span class="sxs-lookup"><span data-stu-id="50dae-123">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>  
  
 <span data-ttu-id="50dae-124">Для самостоятельной сборки примера шаг за шагом следуйте инструкциям в разделе "Загрузка примера", но выберите в качестве **запускаемого проекта** проект **CancelAfterOneTask**.</span><span class="sxs-lookup"><span data-stu-id="50dae-124">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="50dae-125">Добавьте изменения, приведенные в данном разделе, в этот проект.</span><span class="sxs-lookup"><span data-stu-id="50dae-125">Add the changes in this topic to that project.</span></span>  
  
 <span data-ttu-id="50dae-126">В файле MainWindow.xaml.cs проекта **CancelAListOfTasks** запустите переход, переместив шаги обработки для каждого веб-сайта из цикла в `AccessTheWebAsync` в следующий асинхронный метод.</span><span class="sxs-lookup"><span data-stu-id="50dae-126">In the MainWindow.xaml.cs file of the **CancelAListOfTasks** project, start the transition by moving the processing steps for each website from the loop in `AccessTheWebAsync` to the following async method.</span></span>  
  
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
  
 <span data-ttu-id="50dae-127">В `AccessTheWebAsync` в этом примере используются запрос, метод <xref:System.Linq.Enumerable.ToArray%2A> и метод `WhenAny` для создания и запуска массива задач.</span><span class="sxs-lookup"><span data-stu-id="50dae-127">In `AccessTheWebAsync`, this example uses a query, the  <xref:System.Linq.Enumerable.ToArray%2A> method, and the `WhenAny` method to create and start an array of tasks.</span></span> <span data-ttu-id="50dae-128">Применение `WhenAny` к массиву возвращает одну задачу, которая, если ожидается, вычисляется как первая завершившаяся задача в массиве задач.</span><span class="sxs-lookup"><span data-stu-id="50dae-128">The application of `WhenAny` to the array returns a single task that, when awaited, evaluates to the first task to reach completion in the array of tasks.</span></span>  
  
 <span data-ttu-id="50dae-129">Внесите следующие изменения в `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="50dae-129">Make the following changes in `AccessTheWebAsync`.</span></span> <span data-ttu-id="50dae-130">Звездочками отмечены изменения в файле кода.</span><span class="sxs-lookup"><span data-stu-id="50dae-130">Asterisks mark the changes in the code file.</span></span>  
  
1. <span data-ttu-id="50dae-131">Закомментируйте или удалите цикл.</span><span class="sxs-lookup"><span data-stu-id="50dae-131">Comment out or delete the loop.</span></span>  
  
2. <span data-ttu-id="50dae-132">Создайте запрос, который во время выполнения создает коллекцию общих заданий.</span><span class="sxs-lookup"><span data-stu-id="50dae-132">Create a query that, when executed, produces a collection of generic tasks.</span></span> <span data-ttu-id="50dae-133">Каждый вызов `ProcessURLAsync` возвращает <xref:System.Threading.Tasks.Task%601>, где `TResult` — это целое число.</span><span class="sxs-lookup"><span data-stu-id="50dae-133">Each call to `ProcessURLAsync` returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>  
  
    ```csharp  
    // ***Create a query that, when executed, returns a collection of tasks.  
    IEnumerable<Task<int>> downloadTasksQuery =  
        from url in urlList select ProcessURLAsync(url, client, ct);  
    ```  
  
3. <span data-ttu-id="50dae-134">Вызовите `ToArray` для выполнения запроса и запуска задач.</span><span class="sxs-lookup"><span data-stu-id="50dae-134">Call `ToArray` to execute the query and start the tasks.</span></span> <span data-ttu-id="50dae-135">Применение метода `WhenAny` в следующем шаге будет выполнять запрос и запускать задачи без использования `ToArray`, однако этот режим может быть недоступен для других методов.</span><span class="sxs-lookup"><span data-stu-id="50dae-135">The application of the `WhenAny` method in the next step would execute the query and start the tasks without using `ToArray`, but other methods might not.</span></span> <span data-ttu-id="50dae-136">Наиболее безопасным способом является явное принудительное выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="50dae-136">The safest practice is to force execution of the query explicitly.</span></span>  
  
    ```csharp  
    // ***Use ToArray to execute the query and start the download tasks.
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();  
    ```  
  
4. <span data-ttu-id="50dae-137">Вызовите `WhenAny` для коллекции задач.</span><span class="sxs-lookup"><span data-stu-id="50dae-137">Call `WhenAny` on the collection of tasks.</span></span> <span data-ttu-id="50dae-138">`WhenAny` возвращает `Task(Of Task(Of Integer))` или `Task<Task<int>>`.</span><span class="sxs-lookup"><span data-stu-id="50dae-138">`WhenAny` returns a `Task(Of Task(Of Integer))` or `Task<Task<int>>`.</span></span>  <span data-ttu-id="50dae-139">То есть `WhenAny` возвращает задачу, которая вычисляется как одна задача `Task(Of Integer)` или `Task<int>`, если она ожидается.</span><span class="sxs-lookup"><span data-stu-id="50dae-139">That is, `WhenAny` returns a task that evaluates to a single `Task(Of Integer)` or `Task<int>` when it’s awaited.</span></span> <span data-ttu-id="50dae-140">Одна задача — это первая завершившаяся задача в коллекции.</span><span class="sxs-lookup"><span data-stu-id="50dae-140">That single task is the first task in the collection to finish.</span></span> <span data-ttu-id="50dae-141">Задача, которая завершается первой, назначается `firstFinishedTask`.</span><span class="sxs-lookup"><span data-stu-id="50dae-141">The task that finished first is assigned to `firstFinishedTask`.</span></span> <span data-ttu-id="50dae-142">`firstFinishedTask` имеет тип <xref:System.Threading.Tasks.Task%601>, где `TResult` является целым числом, поскольку это возвращаемый тип `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="50dae-142">The type of `firstFinishedTask` is <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer because that's the return type of `ProcessURLAsync`.</span></span>  
  
    ```csharp  
    // ***Call WhenAny and then await the result. The task that finishes
    // first is assigned to firstFinishedTask.  
    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
    ```  
  
5. <span data-ttu-id="50dae-143">В этом примере нас интересует только та задача, которая завершается первой.</span><span class="sxs-lookup"><span data-stu-id="50dae-143">In this example, you’re interested only in the task that finishes first.</span></span> <span data-ttu-id="50dae-144">Таким образом, используйте <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> для отмены оставшихся задач.</span><span class="sxs-lookup"><span data-stu-id="50dae-144">Therefore, use <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> to cancel the remaining tasks.</span></span>  
  
    ```csharp  
    // ***Cancel the rest of the downloads. You just want the first one.  
    cts.Cancel();  
    ```  
  
6. <span data-ttu-id="50dae-145">Наконец, мы ожидаем `firstFinishedTask` для получения длины скачанного содержимого.</span><span class="sxs-lookup"><span data-stu-id="50dae-145">Finally, await `firstFinishedTask` to retrieve the length of the downloaded content.</span></span>  
  
    ```csharp  
    var length = await firstFinishedTask;  
    resultsTextBox.Text += $"\r\nLength of the downloaded website:  {length}\r\n";
    ```  
  
 <span data-ttu-id="50dae-146">Запустите программу несколько раз, чтобы убедиться, что разные задачи завершаются первыми.</span><span class="sxs-lookup"><span data-stu-id="50dae-146">Run the program several times to verify that different downloads finish first.</span></span>  
  
## <a name="complete-example"></a><span data-ttu-id="50dae-147">Полный пример</span><span class="sxs-lookup"><span data-stu-id="50dae-147">Complete Example</span></span>  
 <span data-ttu-id="50dae-148">Приведенный ниже код — полный файл MainWindow.xaml.cs для примера.</span><span class="sxs-lookup"><span data-stu-id="50dae-148">The following code is the complete MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="50dae-149">Звездочками помечаются элементы, добавленные для этого примера.</span><span class="sxs-lookup"><span data-stu-id="50dae-149">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="50dae-150">Обратите внимание на то, что необходимо добавить ссылку для <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="50dae-150">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="50dae-151">Можно загрузить проект со страницы [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span><span class="sxs-lookup"><span data-stu-id="50dae-151">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="50dae-152">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="50dae-152">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- <span data-ttu-id="50dae-153">[Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md) (Тонкая настройка асинхронного приложения в C#)</span><span class="sxs-lookup"><span data-stu-id="50dae-153">[Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md)</span></span>
- [<span data-ttu-id="50dae-154">Асинхронное программирование с использованием ключевых слов Async и Await (C#)</span><span class="sxs-lookup"><span data-stu-id="50dae-154">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- [<span data-ttu-id="50dae-155">Пример асинхронности. Тонкая настройка приложения</span><span class="sxs-lookup"><span data-stu-id="50dae-155">Async Sample: Fine Tuning Your Application</span></span>](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
