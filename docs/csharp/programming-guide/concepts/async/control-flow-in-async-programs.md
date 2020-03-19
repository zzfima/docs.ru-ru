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
# <a name="control-flow-in-async-programs-c"></a><span data-ttu-id="f410f-102">Поток управления в асинхронных программах (C#)</span><span class="sxs-lookup"><span data-stu-id="f410f-102">Control flow in async programs (C#)</span></span>

<span data-ttu-id="f410f-103">Можно намного проще создавать и обслуживать асинхронные программы с помощью ключевых слов `async` и `await`.</span><span class="sxs-lookup"><span data-stu-id="f410f-103">You can write and maintain asynchronous programs more easily by using the `async` and `await` keywords.</span></span> <span data-ttu-id="f410f-104">Однако при непонимании механизма работы асинхронной программы результаты могут удивить.</span><span class="sxs-lookup"><span data-stu-id="f410f-104">However, the results might surprise you if you don't understand how your program operates.</span></span> <span data-ttu-id="f410f-105">В этом разделе выполняется трассировка потока управления с помощью простой асинхронной программы, чтобы продемонстрировать переход потока управления от одного метода к другому, включая данные, передаваемые в каждом случае.</span><span class="sxs-lookup"><span data-stu-id="f410f-105">This topic traces the flow of control through a simple async program to show you when control moves from one method to another and what information is transferred each time.</span></span>

<span data-ttu-id="f410f-106">Как правило, вы помечаете методы, содержащие асинхронный код, с помощью модификатора [async (C#)](../../../language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="f410f-106">In general, you mark methods that contain asynchronous code with the [async (C#)](../../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="f410f-107">В методе, помеченном с помощью модификатора async, можно использовать оператор [await (C#)](../../../language-reference/operators/await.md), чтобы указать место приостановки метода для ожидания завершения вызванного асинхронного процесса.</span><span class="sxs-lookup"><span data-stu-id="f410f-107">In a method that's marked with an async modifier, you can use an [await (C#)](../../../language-reference/operators/await.md) operator to specify where the method pauses to wait for a called asynchronous process to complete.</span></span> <span data-ttu-id="f410f-108">Дополнительные сведения см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](./index.md).</span><span class="sxs-lookup"><span data-stu-id="f410f-108">For more information, see [Asynchronous Programming with async and await (C#)](./index.md).</span></span>

<span data-ttu-id="f410f-109">В следующем примере асинхронные методы используются для загрузки содержимого указанного веб-сайта в виде строки и отображения длины строки.</span><span class="sxs-lookup"><span data-stu-id="f410f-109">The following example uses async methods to download the contents of a specified website as a string and to display the length of the string.</span></span> <span data-ttu-id="f410f-110">Пример содержит следующие два метода:</span><span class="sxs-lookup"><span data-stu-id="f410f-110">The example contains the following two methods.</span></span>

- <span data-ttu-id="f410f-111">`startButton_Click`, который вызывает метод `AccessTheWebAsync` и выводит результат;</span><span class="sxs-lookup"><span data-stu-id="f410f-111">`startButton_Click`, which calls `AccessTheWebAsync` and displays the result.</span></span>

- <span data-ttu-id="f410f-112">`AccessTheWebAsync`, который загружает содержимое веб-сайта в виде строки и возвращает длину строки.</span><span class="sxs-lookup"><span data-stu-id="f410f-112">`AccessTheWebAsync`, which downloads the contents of a website as a string and returns the length of the string.</span></span> <span data-ttu-id="f410f-113">`AccessTheWebAsync` использует для загрузки содержимого асинхронный метод <xref:System.Net.Http.HttpClient><xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="f410f-113">`AccessTheWebAsync` uses an asynchronous <xref:System.Net.Http.HttpClient> method, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, to download the contents.</span></span>

<span data-ttu-id="f410f-114">Выводимые строки помечены номерами на стратегических этапах программы, чтобы помочь вам понять, как работает программа и что происходит на каждом отмеченном этапе.</span><span class="sxs-lookup"><span data-stu-id="f410f-114">Numbered display lines appear at strategic points throughout the program to help you understand how the program runs and to explain what happens at each point that is marked.</span></span> <span data-ttu-id="f410f-115">Выводимые строки обозначены номерами от ONE (один) до SIX (шесть).</span><span class="sxs-lookup"><span data-stu-id="f410f-115">The display lines are labeled "ONE" through "SIX."</span></span> <span data-ttu-id="f410f-116">Метки представляют порядок, в котором программа достигает эти строки кода.</span><span class="sxs-lookup"><span data-stu-id="f410f-116">The labels represent the order in which the program reaches these lines of code.</span></span>

<span data-ttu-id="f410f-117">В следующем примере кода показана структура программы.</span><span class="sxs-lookup"><span data-stu-id="f410f-117">The following code shows an outline of the program.</span></span>

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

<span data-ttu-id="f410f-118">Каждое из расположений, обозначенное от одного до шести, отображает сведения о текущем состоянии программы.</span><span class="sxs-lookup"><span data-stu-id="f410f-118">Each of the labeled locations, "ONE" through "SIX," displays information about the current state of the program.</span></span> <span data-ttu-id="f410f-119">Выводятся следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="f410f-119">The following output is produced:</span></span>

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

## <a name="set-up-the-program"></a><span data-ttu-id="f410f-120">Настройка программы</span><span class="sxs-lookup"><span data-stu-id="f410f-120">Set up the program</span></span>

<span data-ttu-id="f410f-121">Можно загрузить используемый в этом разделе код из MSDN, или же можно создать его самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="f410f-121">You can download the code that this topic uses from MSDN, or you can build it yourself.</span></span>

> [!NOTE]
> <span data-ttu-id="f410f-122">Для выполнения этого примера на компьютере должны быть установлены Visual Studio 2012 или более поздней версии и .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="f410f-122">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

### <a name="download-the-program"></a><span data-ttu-id="f410f-123">Скачивание программы</span><span class="sxs-lookup"><span data-stu-id="f410f-123">Download the program</span></span>

<span data-ttu-id="f410f-124">Вы можете скачать приложение для этого раздела на странице примеров [Пример Async: поток управления в асинхронных программах](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0).</span><span class="sxs-lookup"><span data-stu-id="f410f-124">You can download the application for this topic from [Async Sample: Control Flow in Async Programs](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0).</span></span> <span data-ttu-id="f410f-125">Следующие шаги описывают процесс открытия и запуска программы.</span><span class="sxs-lookup"><span data-stu-id="f410f-125">The following steps open and run the program.</span></span>

1. <span data-ttu-id="f410f-126">Распакуйте загруженный файл, а затем запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f410f-126">Unzip the downloaded file, and then start Visual Studio.</span></span>

2. <span data-ttu-id="f410f-127">В строке меню выберите **Файл** > **Открыть** > **Решение или проект**.</span><span class="sxs-lookup"><span data-stu-id="f410f-127">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="f410f-128">Перейдите к папке, содержащей распакованный пример кода, откройте файл решения (SLN), а затем нажмите клавишу **F5** для сборки и выполнения проекта.</span><span class="sxs-lookup"><span data-stu-id="f410f-128">Navigate to the folder that holds the unzipped sample code, open the solution (.sln) file, and then choose the **F5** key to build and run the project.</span></span>

### <a name="create-the-program-yourself"></a><span data-ttu-id="f410f-129">Самостоятельное создание программы</span><span class="sxs-lookup"><span data-stu-id="f410f-129">Create the program Yourself</span></span>

<span data-ttu-id="f410f-130">Следующий проект Windows Presentation Foundation (WPF) содержит примеры кода для этого раздела.</span><span class="sxs-lookup"><span data-stu-id="f410f-130">The following Windows Presentation Foundation (WPF) project contains the code example for this topic.</span></span>

<span data-ttu-id="f410f-131">Чтобы запустить проект, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f410f-131">To run the project, perform the following steps:</span></span>

1. <span data-ttu-id="f410f-132">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f410f-132">Start Visual Studio.</span></span>

2. <span data-ttu-id="f410f-133">В строке меню выберите **Файл** > **Создать** > **Проект**.</span><span class="sxs-lookup"><span data-stu-id="f410f-133">On the menu bar, choose **File** > **New** > **Project**.</span></span>

     <span data-ttu-id="f410f-134">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="f410f-134">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="f410f-135">Выберите категории **Установленные** > **Visual C#**  > **Windows Desktop**, а затем выберите **Приложение WPF** в списке шаблонов проектов.</span><span class="sxs-lookup"><span data-stu-id="f410f-135">Choose the **Installed** > **Visual C#** > **Windows Desktop** category, and then choose **WPF App** from the list of project templates.</span></span>

4. <span data-ttu-id="f410f-136">Введите `AsyncTracer` в качестве имени проекта и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f410f-136">Enter `AsyncTracer` as the name of the project, and then choose the **OK** button.</span></span>

     <span data-ttu-id="f410f-137">В **обозревателе решений** появится новый проект.</span><span class="sxs-lookup"><span data-stu-id="f410f-137">The new project appears in **Solution Explorer**.</span></span>

5. <span data-ttu-id="f410f-138">В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="f410f-138">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

     <span data-ttu-id="f410f-139">Если вкладка не отображается, откройте контекстное меню для MainWindow.xaml в **обозревателе решений** и выберите пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="f410f-139">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>

6. <span data-ttu-id="f410f-140">Замените код в представлении **XAML** файла MainWindow.xaml на следующий.</span><span class="sxs-lookup"><span data-stu-id="f410f-140">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>

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

     <span data-ttu-id="f410f-141">В представлении **Конструктор** файла MainWindow.xaml появится простое окно, содержащее кнопку и текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="f410f-141">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>

7. <span data-ttu-id="f410f-142">Добавьте ссылку для <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="f410f-142">Add a reference for <xref:System.Net.Http>.</span></span>

8. <span data-ttu-id="f410f-143">В **обозревателе решений** откройте контекстное меню для MainWindow.xaml.cs и выберите пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="f410f-143">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>

9. <span data-ttu-id="f410f-144">В MainWindow.xaml.cs замените код на следующий.</span><span class="sxs-lookup"><span data-stu-id="f410f-144">In MainWindow.xaml.cs, replace the code with the following code.</span></span>

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

10. <span data-ttu-id="f410f-145">Нажмите клавишу **F5**, чтобы запустить программу, а затем нажмите кнопку **Запуск**.</span><span class="sxs-lookup"><span data-stu-id="f410f-145">Choose the **F5** key to run the program, and then choose the **Start** button.</span></span>

    <span data-ttu-id="f410f-146">Появится следующий результат:</span><span class="sxs-lookup"><span data-stu-id="f410f-146">The following output appears:</span></span>

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

## <a name="trace-the-program"></a><span data-ttu-id="f410f-147">Трассировка программы</span><span class="sxs-lookup"><span data-stu-id="f410f-147">Trace the program</span></span>

### <a name="steps-one-and-two"></a><span data-ttu-id="f410f-148">Шаги ОДИН и ДВА</span><span class="sxs-lookup"><span data-stu-id="f410f-148">Steps ONE and TWO</span></span>

<span data-ttu-id="f410f-149">В первых двух строках прослеживается путь по мере того, как метод `startButton_Click` вызывает `AccessTheWebAsync`, а `AccessTheWebAsync` вызывает асинхронный метод <xref:System.Net.Http.HttpClient><xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="f410f-149">The first two display lines trace the path as `startButton_Click` calls `AccessTheWebAsync`, and `AccessTheWebAsync` calls the asynchronous <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span></span> <span data-ttu-id="f410f-150">Ниже показаны вызовы из метода в метод.</span><span class="sxs-lookup"><span data-stu-id="f410f-150">The following image outlines the calls from method to method.</span></span>

<span data-ttu-id="f410f-151">![Шаги ОДИН и ДВА](./media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span><span class="sxs-lookup"><span data-stu-id="f410f-151">![Steps ONE and TWO](./media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span></span>

<span data-ttu-id="f410f-152">Типом возвращаемого значения и для `AccessTheWebAsync`, и для `client.GetStringAsync` является <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="f410f-152">The return type of both `AccessTheWebAsync` and `client.GetStringAsync` is <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="f410f-153">Для `AccessTheWebAsync` значение TResult является целым числом.</span><span class="sxs-lookup"><span data-stu-id="f410f-153">For `AccessTheWebAsync`, TResult is an integer.</span></span> <span data-ttu-id="f410f-154">Для `GetStringAsync` значение TResult является строкой.</span><span class="sxs-lookup"><span data-stu-id="f410f-154">For `GetStringAsync`, TResult is a string.</span></span> <span data-ttu-id="f410f-155">Дополнительные сведения о возвращаемых типах асинхронных методов см. в разделе [Асинхронные типы возвращаемых значений (C#)](./async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="f410f-155">For more information about async method return types, see [Async Return Types (C#)](./async-return-types.md).</span></span>

<span data-ttu-id="f410f-156">Асинхронный метод, возвращающий задачи, возвращает экземпляр задачи, когда контроль управления возвращается к вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="f410f-156">A task-returning async method returns a task instance when control shifts back to the caller.</span></span> <span data-ttu-id="f410f-157">Управление передается от асинхронного метода его вызывающему методу, когда в вызванном методе обнаруживается оператор `await` или когда вызванный метод завершается.</span><span class="sxs-lookup"><span data-stu-id="f410f-157">Control returns from an async method to its caller either when an `await` operator is encountered in the called method or when the called method ends.</span></span> <span data-ttu-id="f410f-158">Отображаемые строки, которые помечены от трёх до шести, отслеживают эту часть процесса.</span><span class="sxs-lookup"><span data-stu-id="f410f-158">The display lines that are labeled "THREE" through "SIX" trace this part of the process.</span></span>

### <a name="step-three"></a><span data-ttu-id="f410f-159">Шаг ТРИ</span><span class="sxs-lookup"><span data-stu-id="f410f-159">Step THREE</span></span>

<span data-ttu-id="f410f-160">В `AccessTheWebAsync` для загрузки содержимого целевой веб-страницы вызывается асинхронный метод <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="f410f-160">In `AccessTheWebAsync`, the asynchronous method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> is called to download the contents of the target webpage.</span></span> <span data-ttu-id="f410f-161">Управление передается от `client.GetStringAsync` методу `AccessTheWebAsync` при возвращении результатов методом `client.GetStringAsync`.</span><span class="sxs-lookup"><span data-stu-id="f410f-161">Control returns from `client.GetStringAsync` to `AccessTheWebAsync` when `client.GetStringAsync` returns.</span></span>

 <span data-ttu-id="f410f-162">Метод `client.GetStringAsync` возвращает задачу строки, назначенной переменной `getStringTask` в `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="f410f-162">The `client.GetStringAsync` method returns a task of string that’s assigned to the `getStringTask` variable in `AccessTheWebAsync`.</span></span> <span data-ttu-id="f410f-163">Следующая строка в примере программы демонстрирует вызов `client.GetStringAsync` и назначение.</span><span class="sxs-lookup"><span data-stu-id="f410f-163">The following line in the example program shows the call to `client.GetStringAsync` and the assignment.</span></span>

```csharp
Task<string> getStringTask = client.GetStringAsync("https://msdn.microsoft.com");
```

 <span data-ttu-id="f410f-164">Можно представить себе задачу как обещание `client.GetStringAsync` создать в конечном итоге фактическую строку.</span><span class="sxs-lookup"><span data-stu-id="f410f-164">You can think of the task as a promise by `client.GetStringAsync` to produce an actual string eventually.</span></span> <span data-ttu-id="f410f-165">В то же время, если у `AccessTheWebAsync` есть работа, не зависящая от обещанной строки, от `client.GetStringAsync`, эта работа будет продолжена во время ожидания `client.GetStringAsync`.</span><span class="sxs-lookup"><span data-stu-id="f410f-165">In the meantime, if `AccessTheWebAsync` has work to do that doesn't depend on the promised string from `client.GetStringAsync`, that work can continue while  `client.GetStringAsync` waits.</span></span> <span data-ttu-id="f410f-166">В этом примере следующие строки вывода, которые обозначены как "THREE", представляют возможность сделать независимую работу.</span><span class="sxs-lookup"><span data-stu-id="f410f-166">In the example, the following lines of output, which are labeled "THREE," represent the opportunity to do independent work</span></span>

```output
THREE: Back in AccessTheWebAsync.
           Task getStringTask is started.
           About to await getStringTask & return a Task<int> to startButton_Click.
```

 <span data-ttu-id="f410f-167">Следующая инструкция приостанавливает ход выполнения в `AccessTheWebAsync` при ожидании `getStringTask`.</span><span class="sxs-lookup"><span data-stu-id="f410f-167">The following statement suspends progress in `AccessTheWebAsync` when `getStringTask` is awaited.</span></span>

```csharp
string urlContents = await getStringTask;
```

 <span data-ttu-id="f410f-168">На следующем рисунке показан поток управления из `client.GetStringAsync` к назначению `getStringTask` и из создания `getStringTask` к применению оператора await.</span><span class="sxs-lookup"><span data-stu-id="f410f-168">The following image shows the flow of control from `client.GetStringAsync` to the assignment to `getStringTask` and from the creation of `getStringTask` to the application of an await operator.</span></span>

 <span data-ttu-id="f410f-169">![Шаг ТРИ](./media/asynctrace-three.png "AsyncTrace-Three")</span><span class="sxs-lookup"><span data-stu-id="f410f-169">![Step THREE](./media/asynctrace-three.png "AsyncTrace-Three")</span></span>

 <span data-ttu-id="f410f-170">Выражение await приостанавливает `AccessTheWebAsync` до возвращения результатов `client.GetStringAsync`.</span><span class="sxs-lookup"><span data-stu-id="f410f-170">The await expression suspends `AccessTheWebAsync` until `client.GetStringAsync` returns.</span></span> <span data-ttu-id="f410f-171">На это время управление возвращается вызывающему объекту метода `AccessTheWebAsync`, `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="f410f-171">In the meantime, control returns to the caller of `AccessTheWebAsync`, `startButton_Click`.</span></span>

> [!NOTE]
> <span data-ttu-id="f410f-172">Как правило, ожидание вызова асинхронного метода выполняется немедленно.</span><span class="sxs-lookup"><span data-stu-id="f410f-172">Typically, you await the call to an asynchronous method immediately.</span></span> <span data-ttu-id="f410f-173">Например, следующее присвоение может заменить предыдущий код, который создает, а затем ожидает `getStringTask`: `string urlContents = await client.GetStringAsync("https://msdn.microsoft.com");`</span><span class="sxs-lookup"><span data-stu-id="f410f-173">For example, the following assignment could replace the previous code that creates and then awaits `getStringTask`: `string urlContents = await client.GetStringAsync("https://msdn.microsoft.com");`</span></span>
>
> <span data-ttu-id="f410f-174">В этом разделе оператор await применяется позже для размещения строк, которые отмечают поток управления в программе.</span><span class="sxs-lookup"><span data-stu-id="f410f-174">In this topic, the await operator is applied later to accommodate the output lines that mark the flow of control through the program.</span></span>

### <a name="step-four"></a><span data-ttu-id="f410f-175">Шаг ЧЕТЫРЕ</span><span class="sxs-lookup"><span data-stu-id="f410f-175">Step FOUR</span></span>

<span data-ttu-id="f410f-176">Объявленный тип возвращаемого значения `AccessTheWebAsync` — `Task<int>`.</span><span class="sxs-lookup"><span data-stu-id="f410f-176">The declared return type of `AccessTheWebAsync` is `Task<int>`.</span></span> <span data-ttu-id="f410f-177">Таким образом, когда выполнение `AccessTheWebAsync` приостанавливается, он возвращает задачу целого числа в `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="f410f-177">Therefore, when `AccessTheWebAsync` is suspended, it returns a task of integer to `startButton_Click`.</span></span> <span data-ttu-id="f410f-178">Следует понимать, что возвращаемая задача — не `getStringTask`.</span><span class="sxs-lookup"><span data-stu-id="f410f-178">You should understand that the returned task isn’t `getStringTask`.</span></span> <span data-ttu-id="f410f-179">Возвращаемая задача — это новая задача целого числа, представляющая оставшуюся работу в приостановленном методе `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="f410f-179">The returned task is a new task of integer that represents what remains to be done in the suspended method, `AccessTheWebAsync`.</span></span> <span data-ttu-id="f410f-180">Задача является обещанием `AccessTheWebAsync` создать фактическое целое число после завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="f410f-180">The task is a promise from `AccessTheWebAsync` to produce an integer when the task is complete.</span></span>

<span data-ttu-id="f410f-181">Следующий оператор назначает эту задачу переменной `getLengthTask`.</span><span class="sxs-lookup"><span data-stu-id="f410f-181">The following statement assigns this task to the `getLengthTask` variable.</span></span>

```csharp
Task<int> getLengthTask = AccessTheWebAsync();
```

 <span data-ttu-id="f410f-182">Как и в `AccessTheWebAsync`, `startButton_Click` может продолжать работу, которая не зависит от результатов асинхронной задачи (`getLengthTask`), во время ожидания задачи.</span><span class="sxs-lookup"><span data-stu-id="f410f-182">As in `AccessTheWebAsync`, `startButton_Click` can continue with work that doesn’t depend on the results of the asynchronous task (`getLengthTask`) until the task is awaited.</span></span> <span data-ttu-id="f410f-183">Следующие выходные строки представляют такую работу.</span><span class="sxs-lookup"><span data-stu-id="f410f-183">The following output lines represent that work.</span></span>

```output
FOUR:  Back in startButton_Click.
           Task getLengthTask is started.
           About to await getLengthTask -- no caller to return to.
```

 <span data-ttu-id="f410f-184">Выполнение в `startButton_Click` приостанавливается при ожидании `getLengthTask`.</span><span class="sxs-lookup"><span data-stu-id="f410f-184">Progress in `startButton_Click` is suspended when `getLengthTask` is awaited.</span></span> <span data-ttu-id="f410f-185">Следующая инструкция назначения приостанавливает `startButton_Click` до завершения `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="f410f-185">The following assignment statement suspends `startButton_Click` until `AccessTheWebAsync` is complete.</span></span>

```csharp
int contentLength = await getLengthTask;
```

 <span data-ttu-id="f410f-186">На следующем рисунке стрелками показан поток управления из выражения await в `AccessTheWebAsync` к назначению значения `getLengthTask`, за которым следует обычная обработка в методе `startButton_Click` до ожидания `getLengthTask`.</span><span class="sxs-lookup"><span data-stu-id="f410f-186">In the following illustration, the arrows show the flow of control from the await expression in `AccessTheWebAsync` to the assignment of a value to `getLengthTask`, followed by normal processing in `startButton_Click` until `getLengthTask` is awaited.</span></span>

 <span data-ttu-id="f410f-187">![Шаг ЧЕТЫРЕ](./media/asynctrace-four.png "AsyncTrace-FOUR")</span><span class="sxs-lookup"><span data-stu-id="f410f-187">![Step FOUR](./media/asynctrace-four.png "AsyncTrace-FOUR")</span></span>

### <a name="step-five"></a><span data-ttu-id="f410f-188">Шаг ПЯТЬ</span><span class="sxs-lookup"><span data-stu-id="f410f-188">Step FIVE</span></span>

<span data-ttu-id="f410f-189">Когда `client.GetStringAsync` уведомляет о завершении, обработка в `AccessTheWebAsync` возобновляется и может продолжаться после оператора await.</span><span class="sxs-lookup"><span data-stu-id="f410f-189">When `client.GetStringAsync` signals that it’s complete, processing in `AccessTheWebAsync` is released from suspension and can continue past the await statement.</span></span> <span data-ttu-id="f410f-190">Приведенные ниже строки выходных данных представляют возобновление обработки.</span><span class="sxs-lookup"><span data-stu-id="f410f-190">The following lines of output represent the resumption of processing.</span></span>

```output
FIVE:  Back in AccessTheWebAsync.
           Task getStringTask is complete.
           Processing the return statement.
           Exiting from AccessTheWebAsync.
```

 <span data-ttu-id="f410f-191">Операнд оператора return, `urlContents.Length`, хранится в задаче, возвращаемой `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="f410f-191">The operand of the return statement, `urlContents.Length`, is stored in the task that  `AccessTheWebAsync` returns.</span></span> <span data-ttu-id="f410f-192">Выражение await получает это значение из `getLengthTask` в `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="f410f-192">The await expression retrieves that value from `getLengthTask` in `startButton_Click`.</span></span>

 <span data-ttu-id="f410f-193">На следующем рисунке показана передача управления после завершения `client.GetStringAsync` (и `getStringTask`).</span><span class="sxs-lookup"><span data-stu-id="f410f-193">The following image shows the transfer of control after `client.GetStringAsync` (and `getStringTask`) are complete.</span></span>

 <span data-ttu-id="f410f-194">![Шаг ПЯТЬ](./media/asynctrace-five.png "AsyncTrace-FIVE")</span><span class="sxs-lookup"><span data-stu-id="f410f-194">![Step FIVE](./media/asynctrace-five.png "AsyncTrace-FIVE")</span></span>

 <span data-ttu-id="f410f-195">`AccessTheWebAsync` выполняется до завершения, и управление возвращается к `startButton_Click`, который ожидает завершения.</span><span class="sxs-lookup"><span data-stu-id="f410f-195">`AccessTheWebAsync` runs to completion, and control returns to `startButton_Click`, which is awaiting the completion.</span></span>

### <a name="step-six"></a><span data-ttu-id="f410f-196">Шаг ШЕСТЬ</span><span class="sxs-lookup"><span data-stu-id="f410f-196">Step SIX</span></span>

<span data-ttu-id="f410f-197">Когда `AccessTheWebAsync` уведомляет о завершении, обработка может продолжаться после оператора await в `startButton_Async`.</span><span class="sxs-lookup"><span data-stu-id="f410f-197">When `AccessTheWebAsync` signals that it’s complete, processing can continue past the await statement in `startButton_Async`.</span></span> <span data-ttu-id="f410f-198">Фактически, на этом работа программы завершается.</span><span class="sxs-lookup"><span data-stu-id="f410f-198">In fact, the program has nothing more to do.</span></span>

<span data-ttu-id="f410f-199">Приведенные ниже строки выходных данных представляют возобновление обработки в `startButton_Async`:</span><span class="sxs-lookup"><span data-stu-id="f410f-199">The following lines of output represent the resumption of processing in `startButton_Async`:</span></span>

```output
SIX:   Back in startButton_Click.
           Task getLengthTask is finished.
           Result from AccessTheWebAsync is stored in contentLength.
           About to display contentLength and exit.
```

 <span data-ttu-id="f410f-200">Выражение await получает из `getLengthTask` целое значение, представляющее операнд оператора return в `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="f410f-200">The await expression retrieves from `getLengthTask` the integer value that’s the operand of the return statement in `AccessTheWebAsync`.</span></span> <span data-ttu-id="f410f-201">Следующий оператор назначает это значение переменной `contentLength`.</span><span class="sxs-lookup"><span data-stu-id="f410f-201">The following statement assigns that value to the `contentLength` variable.</span></span>

```csharp
int contentLength = await getLengthTask;
```

 <span data-ttu-id="f410f-202">На следующем рисунке показано возвращение управления от `AccessTheWebAsync` к `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="f410f-202">The following image shows the return of control from `AccessTheWebAsync` to `startButton_Click`.</span></span>

 <span data-ttu-id="f410f-203">![Шаг ШЕСТЬ](./media/asynctrace-six.png "AsyncTrace-SIX")</span><span class="sxs-lookup"><span data-stu-id="f410f-203">![Step SIX](./media/asynctrace-six.png "AsyncTrace-SIX")</span></span>

## <a name="see-also"></a><span data-ttu-id="f410f-204">См. также</span><span class="sxs-lookup"><span data-stu-id="f410f-204">See also</span></span>

- [<span data-ttu-id="f410f-205">Асинхронное программирование с использованием ключевых слов async и await (C#)</span><span class="sxs-lookup"><span data-stu-id="f410f-205">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- <span data-ttu-id="f410f-206">[Async Return Types (C#)](./async-return-types.md) (Типы возвращаемых значений асинхронных операций в C#)</span><span class="sxs-lookup"><span data-stu-id="f410f-206">[Async Return Types (C#)](./async-return-types.md)</span></span>
- [<span data-ttu-id="f410f-207">Пошаговое руководство: Доступ к Интернету с помощью модификатора Async и оператора Await в C#</span><span class="sxs-lookup"><span data-stu-id="f410f-207">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="f410f-208">Пример использования Async. Поток управления в асинхронных программах (C# и Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f410f-208">Async Sample: Control Flow in Async Programs (C# and Visual Basic)</span></span>](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)
