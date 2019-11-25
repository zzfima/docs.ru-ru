---
title: Практическое руководство. Параллельное выполнение нескольких веб-запросов с использованием Async и Await (C#)
ms.date: 07/20/2015
ms.assetid: 19745899-f97a-4499-a7c7-e813d1447580
ms.openlocfilehash: a6eef947e8f657cff574ffdf3afcd8943c665b8d
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73969949"
---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-c"></a><span data-ttu-id="5f318-102">Практическое руководство. Параллельное выполнение нескольких веб-запросов с использованием Async и Await (C#)</span><span class="sxs-lookup"><span data-stu-id="5f318-102">How to make multiple web requests in parallel by using async and await (C#)</span></span>
<span data-ttu-id="5f318-103">В асинхронном методе задачи запускаются в момент создания.</span><span class="sxs-lookup"><span data-stu-id="5f318-103">In an async method, tasks are started when they’re created.</span></span> <span data-ttu-id="5f318-104">Оператор [Await](../../../language-reference/operators/await.md) применяется к задаче в той точке в методе, где обработка не может продолжаться до завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="5f318-104">The [await](../../../language-reference/operators/await.md) operator is applied to the task at the point in the method where processing can’t continue until the task finishes.</span></span> <span data-ttu-id="5f318-105">Часто задачи ожидаются в момент создания, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5f318-105">Often a task is awaited as soon as it’s created, as the following example shows.</span></span>  
  
```csharp  
var result = await someWebAccessMethodAsync(url);  
```  
  
 <span data-ttu-id="5f318-106">Тем не менее можно отделить создание задачи от ее ожидания, если программа содержит другую работу, выполнение которой не зависит от завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="5f318-106">However, you can separate creating the task from awaiting the task if your program has other work to accomplish that doesn’t depend on the completion of the task.</span></span>  
  
```csharp  
// The following line creates and starts the task.  
var myTask = someWebAccessMethodAsync(url);  
  
// While the task is running, you can do other work that doesn't depend  
// on the results of the task.  
// . . . . .  
  
// The application of await suspends the rest of this method until the task is complete.  
var result = await myTask;  
```  
  
 <span data-ttu-id="5f318-107">Между моментом запуска задачи и ее ожиданием можно запустить другие задачи.</span><span class="sxs-lookup"><span data-stu-id="5f318-107">Between starting a task and awaiting it, you can start other tasks.</span></span> <span data-ttu-id="5f318-108">Дополнительные задачи неявно выполняются параллельно, однако дополнительные потоки не создаются.</span><span class="sxs-lookup"><span data-stu-id="5f318-108">The additional tasks implicitly run in parallel, but no additional threads are created.</span></span>  
  
 <span data-ttu-id="5f318-109">Следующая программа запускает три асинхронные веб-загрузки, а затем ожидает их в том порядке, в котором они вызываются.</span><span class="sxs-lookup"><span data-stu-id="5f318-109">The following program starts three asynchronous web downloads and then awaits them in the order in which they’re called.</span></span> <span data-ttu-id="5f318-110">Обратите внимание, что при запуске программы задачи не всегда завершаются в том порядке, в котором они созданы и ожидаются.</span><span class="sxs-lookup"><span data-stu-id="5f318-110">Notice, when you run the program, that the tasks don’t always finish in the order in which they’re created and awaited.</span></span> <span data-ttu-id="5f318-111">Они начинают выполняться в момент создания, и одна или несколько задач могут завершиться прежде, чем метод достигает выражения await.</span><span class="sxs-lookup"><span data-stu-id="5f318-111">They start to run when they’re created, and one or more of the tasks might finish before the method reaches the await expressions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f318-112">Для выполнения этого проекта необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="5f318-112">To complete this project, you must have Visual Studio 2012 or higher and the .NET Framework 4.5 or higher installed on your computer.</span></span>  
  
 <span data-ttu-id="5f318-113">Другой пример, в котором одновременно запускается несколько задач, см. в разделе [Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="5f318-113">For another example that starts multiple tasks at the same time, see [How to extend the async walkthrough by using Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>
  
 <span data-ttu-id="5f318-114">Код для этого примера можно скачать на странице [Примеры кода от разработчиков](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e).</span><span class="sxs-lookup"><span data-stu-id="5f318-114">You can download the code for this example from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e).</span></span>  
  
### <a name="to-set-up-the-project"></a><span data-ttu-id="5f318-115">Настройка проекта</span><span class="sxs-lookup"><span data-stu-id="5f318-115">To set up the project</span></span>  
  
1. <span data-ttu-id="5f318-116">Чтобы настроить приложение WPF, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5f318-116">To set up a WPF application, complete the following steps.</span></span> <span data-ttu-id="5f318-117">Подробные инструкции для выполнения этих действий можно найти в разделе [Пошаговое руководство. Доступ к Интернету с помощью модификатора Async и оператора Await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="5f318-117">You can find detailed instructions for these steps in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    - <span data-ttu-id="5f318-118">Создайте приложение WPF, которое содержит текстовое поле и кнопку.</span><span class="sxs-lookup"><span data-stu-id="5f318-118">Create a WPF application that contains a text box and a button.</span></span> <span data-ttu-id="5f318-119">Назовите кнопку `startButton`, а текстовое поле — `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="5f318-119">Name the button `startButton`, and name the text box `resultsTextBox`.</span></span>  
  
    - <span data-ttu-id="5f318-120">Добавьте ссылку для <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="5f318-120">Add a reference for <xref:System.Net.Http>.</span></span>  
  
    - <span data-ttu-id="5f318-121">Добавьте в файл MainWindow.xaml.cs директиву `using` для `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="5f318-121">In the MainWindow.xaml.cs file, add a `using` directive for `System.Net.Http`.</span></span>  
  
### <a name="to-add-the-code"></a><span data-ttu-id="5f318-122">Добавление кода</span><span class="sxs-lookup"><span data-stu-id="5f318-122">To add the code</span></span>  
  
1. <span data-ttu-id="5f318-123">В окне конструктора для MainWindow.xaml дважды нажмите кнопку, чтобы создать обработчик события `startButton_Click` в файле MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="5f318-123">In the design window, MainWindow.xaml, double-click the button to create the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>  
  
2. <span data-ttu-id="5f318-124">Скопируйте следующий код в тело `startButton_Click` в файле MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="5f318-124">Copy the following code, and paste it into the body of `startButton_Click` in MainWindow.xaml.cs.</span></span>  
  
    ```csharp  
    resultsTextBox.Clear();  
    await CreateMultipleTasksAsync();  
    resultsTextBox.Text += "\r\n\r\nControl returned to startButton_Click.\r\n";  
    ```  
  
     <span data-ttu-id="5f318-125">Код вызывает асинхронный метод `CreateMultipleTasksAsync`, который управляет приложением.</span><span class="sxs-lookup"><span data-stu-id="5f318-125">The code calls an asynchronous method, `CreateMultipleTasksAsync`, which drives the application.</span></span>  
  
3. <span data-ttu-id="5f318-126">Добавьте следующие вспомогательные методы в проект:</span><span class="sxs-lookup"><span data-stu-id="5f318-126">Add the following support methods to the project:</span></span>  
  
    - <span data-ttu-id="5f318-127">`ProcessURLAsync` использует метод <xref:System.Net.Http.HttpClient> для скачивания содержимого веб-сайта в виде массива байтов.</span><span class="sxs-lookup"><span data-stu-id="5f318-127">`ProcessURLAsync` uses an <xref:System.Net.Http.HttpClient> method to download the contents of a website as a byte array.</span></span> <span data-ttu-id="5f318-128">Вспомогательный метод `ProcessURLAsync` затем отображает и возвращает длину массива.</span><span class="sxs-lookup"><span data-stu-id="5f318-128">The support method, `ProcessURLAsync` then displays and returns the length of the array.</span></span>  
  
    - <span data-ttu-id="5f318-129">`DisplayResults` показывает число байтов в массиве байтов для каждого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="5f318-129">`DisplayResults` displays the number of bytes in the byte array for each URL.</span></span> <span data-ttu-id="5f318-130">Эти выходные данные показывают, когда именно каждая задача завершает загрузку.</span><span class="sxs-lookup"><span data-stu-id="5f318-130">This display shows when each task has finished downloading.</span></span>  
  
     <span data-ttu-id="5f318-131">Скопируйте следующие методы и вставьте их после обработчика событий `startButton_Click` в файле MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="5f318-131">Copy the following methods, and paste them after the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>  
  
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
  
4. <span data-ttu-id="5f318-132">Наконец, определите метод `CreateMultipleTasksAsync`, который выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5f318-132">Finally, define method `CreateMultipleTasksAsync`, which performs the following steps.</span></span>  
  
    - <span data-ttu-id="5f318-133">Этот метод объявляет объект `HttpClient`, который используется методом доступа <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> в `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="5f318-133">The method declares an `HttpClient` object,which you need  to access method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> in `ProcessURLAsync`.</span></span>  
  
    - <span data-ttu-id="5f318-134">Метод создает и запускает три задачи типа <xref:System.Threading.Tasks.Task%601>, где `TResult` является целым числом.</span><span class="sxs-lookup"><span data-stu-id="5f318-134">The method creates and starts three tasks of type <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer.</span></span> <span data-ttu-id="5f318-135">При завершении каждой задачи `DisplayResults` отображает URL-адрес и длину загруженного содержимого задачи.</span><span class="sxs-lookup"><span data-stu-id="5f318-135">As each task finishes, `DisplayResults` displays the task's URL and the length of the downloaded contents.</span></span> <span data-ttu-id="5f318-136">Поскольку задачи выполняются асинхронно, порядок, в котором отображаются результаты, может отличаться от порядка, в котором они были объявлены.</span><span class="sxs-lookup"><span data-stu-id="5f318-136">Because the tasks are running asynchronously, the order in which the results appear might differ from the order in which they were declared.</span></span>  
  
    - <span data-ttu-id="5f318-137">Метод ожидает завершения каждой задачи.</span><span class="sxs-lookup"><span data-stu-id="5f318-137">The method awaits the completion of each task.</span></span> <span data-ttu-id="5f318-138">Каждый оператор `await` приостанавливает выполнение `CreateMultipleTasksAsync` до завершения выполнения ожидаемой задачи.</span><span class="sxs-lookup"><span data-stu-id="5f318-138">Each `await` operator suspends execution of `CreateMultipleTasksAsync` until the awaited task is finished.</span></span> <span data-ttu-id="5f318-139">Оператор также получает возвращаемое значение вызова `ProcessURLAsync` от каждой завершенной задачи.</span><span class="sxs-lookup"><span data-stu-id="5f318-139">The operator also retrieves the return value from the call to `ProcessURLAsync` from each completed task.</span></span>  
  
    - <span data-ttu-id="5f318-140">После завершения задач и получения целочисленных значений метод суммирует длину веб-сайтов и отображает результат.</span><span class="sxs-lookup"><span data-stu-id="5f318-140">When the tasks have been completed and the integer values have been retrieved, the method sums the lengths of the websites and displays the result.</span></span>  
  
     <span data-ttu-id="5f318-141">Скопируйте следующий метод и вставьте его в решение.</span><span class="sxs-lookup"><span data-stu-id="5f318-141">Copy the following method, and paste it into your solution.</span></span>  
  
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
  
5. <span data-ttu-id="5f318-142">Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .</span><span class="sxs-lookup"><span data-stu-id="5f318-142">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="5f318-143">Запустите программу несколько раз, чтобы убедиться, что три задачи не всегда завершаются в том же порядке, а порядок их завершения не обязательно совпадает с порядком, в котором они создаются и ожидаются.</span><span class="sxs-lookup"><span data-stu-id="5f318-143">Run the program several times to verify that the three tasks don’t always finish in the same order and that the order in which they finish isn't necessarily the order in which they’re created and awaited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f318-144">Пример</span><span class="sxs-lookup"><span data-stu-id="5f318-144">Example</span></span>  
 <span data-ttu-id="5f318-145">Следующий код содержит полный пример.</span><span class="sxs-lookup"><span data-stu-id="5f318-145">The following code contains the full example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5f318-146">См. также</span><span class="sxs-lookup"><span data-stu-id="5f318-146">See also</span></span>

- [<span data-ttu-id="5f318-147">Пошаговое руководство: Доступ к Интернету с помощью модификатора Async и оператора Await в C#</span><span class="sxs-lookup"><span data-stu-id="5f318-147">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="5f318-148">Асинхронное программирование с использованием ключевых слов async и await (C#)</span><span class="sxs-lookup"><span data-stu-id="5f318-148">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- [<span data-ttu-id="5f318-149">Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll (C#)</span><span class="sxs-lookup"><span data-stu-id="5f318-149">How to extend the async walkthrough by using Task.WhenAll (C#)</span></span>](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
