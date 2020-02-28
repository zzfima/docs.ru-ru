---
title: Обработка повторного входа в асинхронных приложениях (C#)
ms.date: 07/20/2015
ms.assetid: 47c5075e-c448-45ce-9155-ed4e7e98c677
ms.openlocfilehash: 67fbbd294ffe6219b58065f974543b2dd483a92c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451867"
---
# <a name="handling-reentrancy-in-async-apps-c"></a><span data-ttu-id="695bc-102">Обработка повторного входа в асинхронных приложениях (C#)</span><span class="sxs-lookup"><span data-stu-id="695bc-102">Handling Reentrancy in Async Apps (C#)</span></span>

<span data-ttu-id="695bc-103">При включении асинхронного кода в приложение следует учесть и по возможности избежать повторного входа, под которым подразумевается повторный ввод асинхронной операции до ее завершения.</span><span class="sxs-lookup"><span data-stu-id="695bc-103">When you include asynchronous code in your app, you should consider and possibly prevent reentrancy, which refers to reentering an asynchronous operation before it has completed.</span></span> <span data-ttu-id="695bc-104">Если не определить и не обработать возможности повторного входа, это может привести к непредвиденным результатам.</span><span class="sxs-lookup"><span data-stu-id="695bc-104">If you don't identify and handle possibilities for reentrancy, it can cause unexpected results.</span></span>

<span data-ttu-id="695bc-105">**Содержание раздела**</span><span class="sxs-lookup"><span data-stu-id="695bc-105">**In this topic**</span></span>

- [<span data-ttu-id="695bc-106">Распознавание поддержки повторного входа</span><span class="sxs-lookup"><span data-stu-id="695bc-106">Recognizing Reentrancy</span></span>](#BKMK_RecognizingReentrancy)

- [<span data-ttu-id="695bc-107">Обработка поддержки повторного входа</span><span class="sxs-lookup"><span data-stu-id="695bc-107">Handling Reentrancy</span></span>](#BKMK_HandlingReentrancy)

  - [<span data-ttu-id="695bc-108">Отключение кнопки запуска</span><span class="sxs-lookup"><span data-stu-id="695bc-108">Disable the Start Button</span></span>](#BKMK_DisableTheStartButton)

  - [<span data-ttu-id="695bc-109">Отмена и перезапуск операции</span><span class="sxs-lookup"><span data-stu-id="695bc-109">Cancel and Restart the Operation</span></span>](#BKMK_CancelAndRestart)

  - [<span data-ttu-id="695bc-110">Запуск нескольких операций и постановка выходных данных в очередь</span><span class="sxs-lookup"><span data-stu-id="695bc-110">Run Multiple Operations and Queue the Output</span></span>](#BKMK_RunMultipleOperations)

- [<span data-ttu-id="695bc-111">Проверка и выполнение примера приложения</span><span class="sxs-lookup"><span data-stu-id="695bc-111">Reviewing and Running the Example App</span></span>](#BKMD_SettingUpTheExample)

> [!NOTE]
> <span data-ttu-id="695bc-112">Для выполнения этого примера нужно, чтобы на компьютере были установлены Visual Studio 2012 или более поздней версии и .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="695bc-112">To run the example, you must have Visual Studio 2012 or newer and .NET Framework 4.5 or newer installed on your computer.</span></span>

> [!NOTE]
> <span data-ttu-id="695bc-113">Версия протокола TLS 1.2 теперь является минимальной версией для использования в разработке приложений.</span><span class="sxs-lookup"><span data-stu-id="695bc-113">Transport Layer Security (TLS) version 1.2 is now the minimum version to use in your app development.</span></span> <span data-ttu-id="695bc-114">Если приложение предназначено для более ранней версии .NET Framework, чем 4.7, обратитесь к следующей статье, чтобы ознакомиться с [рекомендациями по протоколу TLS в .NET Framework](../../../../framework/network-programming/tls.md).</span><span class="sxs-lookup"><span data-stu-id="695bc-114">If your app targets a .NET Framework version earlier than 4.7, refer to the following article for [Transport Layer Security (TLS) best practices with the .NET Framework](../../../../framework/network-programming/tls.md).</span></span>

## <a name="BKMK_RecognizingReentrancy"></a> <span data-ttu-id="695bc-115">Распознавание поддержки повторного входа</span><span class="sxs-lookup"><span data-stu-id="695bc-115">Recognizing Reentrancy</span></span>

<span data-ttu-id="695bc-116">В примере в этом разделе пользователь нажимает кнопку **Start**, чтобы инициировать асинхронное приложение, загружающее ряд веб-сайтов и вычисляющее общее число загруженных байтов.</span><span class="sxs-lookup"><span data-stu-id="695bc-116">In the example in this topic, users choose a **Start** button to initiate an asynchronous app that downloads a series of websites and calculates the total number of bytes that are downloaded.</span></span> <span data-ttu-id="695bc-117">Синхронная версия примера реагирует одинаково, независимо от того, сколько раз пользователь нажмет кнопку, поскольку после первого раза поток пользовательского интерфейса игнорирует эти события до завершения выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="695bc-117">A synchronous version of the example would respond the same way regardless of how many times a user chooses the button because, after the first time, the UI thread ignores those events until the app finishes running.</span></span> <span data-ttu-id="695bc-118">При этом в асинхронном приложении поток пользовательского интерфейса продолжает реагировать, и можно ввести асинхронную операцию повторно до ее завершения.</span><span class="sxs-lookup"><span data-stu-id="695bc-118">In an asynchronous app, however, the UI thread continues to respond, and you might reenter the asynchronous operation before it has completed.</span></span>

<span data-ttu-id="695bc-119">В следующем примере показаны ожидаемые выходные данные, если пользователь нажимает кнопку **Start** только один раз.</span><span class="sxs-lookup"><span data-stu-id="695bc-119">The following example shows the expected output if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="695bc-120">На экран выводится список загруженных веб-сайтов, размер которых указан в байтах.</span><span class="sxs-lookup"><span data-stu-id="695bc-120">A list of the downloaded websites appears with the size, in bytes, of each site.</span></span> <span data-ttu-id="695bc-121">Общее число байтов отображается в конце списка.</span><span class="sxs-lookup"><span data-stu-id="695bc-121">The total number of bytes appears at the end.</span></span>

```output
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

<span data-ttu-id="695bc-122">Однако если пользователь нажимает кнопку больше одного раза, обработчик событий вызывается несколько раз и процесс загрузки будет каждый раз выполняться повторно.</span><span class="sxs-lookup"><span data-stu-id="695bc-122">However, if the user chooses the button more than once, the event handler is invoked repeatedly, and the download process is reentered each time.</span></span> <span data-ttu-id="695bc-123">В результате одновременно запускается несколько асинхронных операций, получаемые выходные данные чередуются и счетчик общего числа байтов выдает неоднозначные результаты.</span><span class="sxs-lookup"><span data-stu-id="695bc-123">As a result, several asynchronous operations are running at the same time, the output interleaves the results, and the total number of bytes is confusing.</span></span>

```output
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
6. msdn.microsoft.com/library/ms404677.aspx               197325
3. msdn.microsoft.com/library/jj155761.aspx                29019
7. msdn.microsoft.com                                            42972
4. msdn.microsoft.com/library/hh290140.aspx               117152
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591

5. msdn.microsoft.com/library/hh524395.aspx                68959
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
6. msdn.microsoft.com/library/ms404677.aspx               197325
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
7. msdn.microsoft.com                                            42972
5. msdn.microsoft.com/library/hh524395.aspx                68959
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591

6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

<span data-ttu-id="695bc-124">Чтобы просмотреть код, создающий эти выходные данные, перейдите к концу раздела.</span><span class="sxs-lookup"><span data-stu-id="695bc-124">You can review the code that produces this output by scrolling to the end of this topic.</span></span> <span data-ttu-id="695bc-125">Можно поэкспериментировать с кодом, загрузив решение на локальный компьютер и затем запустив проект WebsiteDownload или воспользовавшись кодом в конце этого раздела для создания собственного проекта.</span><span class="sxs-lookup"><span data-stu-id="695bc-125">You can experiment with the code by downloading the solution to your local computer and then running the WebsiteDownload project or by using the code at the end of this topic to create your own project.</span></span> <span data-ttu-id="695bc-126">Дополнительные сведения и инструкции см. в разделе [Проверка и выполнение примера приложения](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="695bc-126">For more information and instructions, see [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span>

## <a name="BKMK_HandlingReentrancy"></a> <span data-ttu-id="695bc-127">Обработка поддержки повторного входа</span><span class="sxs-lookup"><span data-stu-id="695bc-127">Handling Reentrancy</span></span>

<span data-ttu-id="695bc-128">Обрабатывать повторный вход можно разными способами в зависимости от того, что требуется от приложения.</span><span class="sxs-lookup"><span data-stu-id="695bc-128">You can handle reentrancy in a variety of ways, depending on what you want your app to do.</span></span> <span data-ttu-id="695bc-129">В этом разделе представлены следующие примеры.</span><span class="sxs-lookup"><span data-stu-id="695bc-129">This topic presents the following examples:</span></span>

- [<span data-ttu-id="695bc-130">Отключение кнопки запуска</span><span class="sxs-lookup"><span data-stu-id="695bc-130">Disable the Start Button</span></span>](#BKMK_DisableTheStartButton)

  <span data-ttu-id="695bc-131">Отключение кнопки **Start** во время выполнения операции, чтобы пользователь не мог прервать ее выполнение.</span><span class="sxs-lookup"><span data-stu-id="695bc-131">Disable the **Start** button while the operation is running so that the user can't interrupt it.</span></span>

- [<span data-ttu-id="695bc-132">Отмена и перезапуск операции</span><span class="sxs-lookup"><span data-stu-id="695bc-132">Cancel and Restart the Operation</span></span>](#BKMK_CancelAndRestart)

  <span data-ttu-id="695bc-133">Отмена выполнения любой операции, которая выполняется в тот момент, когда пользователь снова нажимает кнопку **Start**, с последующим продолжением операции, которая была запрошена последней.</span><span class="sxs-lookup"><span data-stu-id="695bc-133">Cancel any operation that is still running when the user chooses the **Start** button again, and then let the most recently requested operation continue.</span></span>

- [<span data-ttu-id="695bc-134">Запуск нескольких операций и постановка выходных данных в очередь</span><span class="sxs-lookup"><span data-stu-id="695bc-134">Run Multiple Operations and Queue the Output</span></span>](#BKMK_RunMultipleOperations)

  <span data-ttu-id="695bc-135">Разрешение всем запрошенным операциям выполняться асинхронно и настройка согласования отображения выходных данных для вывода результатов каждой операции вместе и по порядку.</span><span class="sxs-lookup"><span data-stu-id="695bc-135">Allow all requested operations to run asynchronously, but coordinate the display of output so that the results from each operation appear together and in order.</span></span>

### <a name="BKMK_DisableTheStartButton"></a> <span data-ttu-id="695bc-136">Отключение кнопки запуска</span><span class="sxs-lookup"><span data-stu-id="695bc-136">Disable the Start Button</span></span>

<span data-ttu-id="695bc-137">Можно заблокировать кнопку **Start`StartButton_Click` во время операции, отключив кнопку в верхней части обработчика событий** .</span><span class="sxs-lookup"><span data-stu-id="695bc-137">You can block the **Start** button while an operation is running by disabling the button at the top of the `StartButton_Click` event handler.</span></span> <span data-ttu-id="695bc-138">Затем можно повторно включить кнопку из блока `finally` по завершении операции, чтобы пользователь мог запустить приложение повторно.</span><span class="sxs-lookup"><span data-stu-id="695bc-138">You can then reenable the button from within a  `finally` block when the operation finishes so that users can run the app again.</span></span>

<span data-ttu-id="695bc-139">Чтобы настроить этот сценарий, внесите следующие изменения в основной код, который содержится в разделе [Проверка и выполнение примера приложения](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="695bc-139">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span> <span data-ttu-id="695bc-140">Также можно загрузить готовое приложение в разделе [Примеры асинхронности. Поддержка повторного входа в классических приложениях .NET](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span><span class="sxs-lookup"><span data-stu-id="695bc-140">You also can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="695bc-141">Этот проект называется DisableStartButton.</span><span class="sxs-lookup"><span data-stu-id="695bc-141">The name of the project is DisableStartButton.</span></span>

```csharp
private async void StartButton_Click(object sender, RoutedEventArgs e)
{
    // This line is commented out to make the results clearer in the output.
    //ResultsTextBox.Text = "";

    // ***Disable the Start button until the downloads are complete.
    StartButton.IsEnabled = false;

    try
    {
        await AccessTheWebAsync();
    }
    catch (Exception)
    {
        ResultsTextBox.Text += "\r\nDownloads failed.";
    }
    // ***Enable the Start button in case you want to run the program again.
    finally
    {
        StartButton.IsEnabled = true;
    }
}
```

<span data-ttu-id="695bc-142">В результате этих изменений кнопка не будет реагировать в течение загрузки веб-сайтов методом `AccessTheWebAsync`, поэтому повторный вход в процесс будет невозможен.</span><span class="sxs-lookup"><span data-stu-id="695bc-142">As a result of the changes, the button doesn't respond while `AccessTheWebAsync` is downloading the websites, so the process can’t be reentered.</span></span>

### <a name="BKMK_CancelAndRestart"></a> <span data-ttu-id="695bc-143">Отмена и перезапуск операции</span><span class="sxs-lookup"><span data-stu-id="695bc-143">Cancel and Restart the Operation</span></span>

<span data-ttu-id="695bc-144">Вместо отключения кнопки **Start** можно оставить кнопку активной, но при этом, если пользователь нажмет эту кнопку еще раз, нужно отменить операцию, которая уже выполняется, и задать продолжение выполнения последней запущенной операции.</span><span class="sxs-lookup"><span data-stu-id="695bc-144">Instead of disabling the **Start** button, you can keep the button active but, if the user chooses that button again, cancel the operation that's already running and let the most recently started operation continue.</span></span>

<span data-ttu-id="695bc-145">Дополнительные сведения об отмене см. в разделе [Настройка асинхронного приложения (C#)](./fine-tuning-your-async-application.md).</span><span class="sxs-lookup"><span data-stu-id="695bc-145">For more information about cancellation, see [Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md).</span></span>

<span data-ttu-id="695bc-146">Чтобы настроить этот сценарий, внесите следующие изменения в основной код, который содержится в разделе [Проверка и выполнение примера приложения](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="695bc-146">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span> <span data-ttu-id="695bc-147">Также можно загрузить готовое приложение в разделе [Примеры асинхронности. Поддержка повторного входа в классических приложениях .NET](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span><span class="sxs-lookup"><span data-stu-id="695bc-147">You also can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="695bc-148">Этот проект называется CancelAndRestart.</span><span class="sxs-lookup"><span data-stu-id="695bc-148">The name of the project is CancelAndRestart.</span></span>

1. <span data-ttu-id="695bc-149">Объявите переменную <xref:System.Threading.CancellationTokenSource>, `cts`, которая находится в области действия всех методов.</span><span class="sxs-lookup"><span data-stu-id="695bc-149">Declare a <xref:System.Threading.CancellationTokenSource> variable, `cts`, that’s in scope for all methods.</span></span>

    ```csharp
    public partial class MainWindow : Window   // Or class MainPage
    {
        // *** Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;
    ```

2. <span data-ttu-id="695bc-150">В `StartButton_Click` определите, выполняется ли операция на данный момент.</span><span class="sxs-lookup"><span data-stu-id="695bc-150">In `StartButton_Click`, determine whether an operation is already underway.</span></span> <span data-ttu-id="695bc-151">Если значение `cts` — null, значит, активных операций нет.</span><span class="sxs-lookup"><span data-stu-id="695bc-151">If the value of `cts` is null, no operation is already active.</span></span> <span data-ttu-id="695bc-152">Если значение не равно null, выполняющаяся операция отменена.</span><span class="sxs-lookup"><span data-stu-id="695bc-152">If the value isn't null, the operation that is already running is canceled.</span></span>

    ```csharp
    // *** If a download process is already underway, cancel it.
    if (cts != null)
    {
        cts.Cancel();
    }
    ```

3. <span data-ttu-id="695bc-153">Задайте для `cts` другое значение, представляющее текущий процесс.</span><span class="sxs-lookup"><span data-stu-id="695bc-153">Set `cts` to a different value that represents the current process.</span></span>

    ```csharp
    // *** Now set cts to a new value that you can use to cancel the current process
    // if the button is chosen again.
    CancellationTokenSource newCTS = new CancellationTokenSource();
    cts = newCTS;
    ```

4. <span data-ttu-id="695bc-154">В конце процедуры `StartButton_Click` текущий процесс будет выполнен, поэтому верните для `cts` значение null.</span><span class="sxs-lookup"><span data-stu-id="695bc-154">At the end of `StartButton_Click`, the current process is complete, so set the value of `cts` back to null.</span></span>

    ```csharp
    // *** When the process is complete, signal that another process can begin.
    if (cts == newCTS)
        cts = null;
    ```

<span data-ttu-id="695bc-155">В следующем коде показаны все изменения в `StartButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="695bc-155">The following code shows all the changes in `StartButton_Click`.</span></span> <span data-ttu-id="695bc-156">Добавления помечены звездочками.</span><span class="sxs-lookup"><span data-stu-id="695bc-156">The additions are marked with asterisks.</span></span>

```csharp
private async void StartButton_Click(object sender, RoutedEventArgs e)
{
    // This line is commented out to make the results clearer in the output.
    //ResultsTextBox.Clear();

    // *** If a download process is already underway, cancel it.
    if (cts != null)
    {
        cts.Cancel();
    }

    // *** Now set cts to cancel the current process if the button is chosen again.
    CancellationTokenSource newCTS = new CancellationTokenSource();
    cts = newCTS;

    try
    {
        // ***Send cts.Token to carry the message if there is a cancellation request.
        await AccessTheWebAsync(cts.Token);

    }
    // *** Catch cancellations separately.
    catch (OperationCanceledException)
    {
        ResultsTextBox.Text += "\r\nDownloads canceled.\r\n";
    }
    catch (Exception)
    {
        ResultsTextBox.Text += "\r\nDownloads failed.\r\n";
    }
    // *** When the process is complete, signal that another process can proceed.
    if (cts == newCTS)
        cts = null;
}
```

<span data-ttu-id="695bc-157">В `AccessTheWebAsync` внесите следующие изменения.</span><span class="sxs-lookup"><span data-stu-id="695bc-157">In `AccessTheWebAsync`, make the following changes.</span></span>

- <span data-ttu-id="695bc-158">Добавьте параметр, чтобы принимать токен отмены из `StartButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="695bc-158">Add a parameter to accept the cancellation token from `StartButton_Click`.</span></span>

- <span data-ttu-id="695bc-159">Используйте метод <xref:System.Net.Http.HttpClient.GetAsync%2A> для загрузки веб-сайтов, так как `GetAsync` принимает аргумент <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="695bc-159">Use the <xref:System.Net.Http.HttpClient.GetAsync%2A> method to download the websites because `GetAsync` accepts a <xref:System.Threading.CancellationToken> argument.</span></span>

- <span data-ttu-id="695bc-160">Перед вызовом метода `DisplayResults` для отображения результатов для каждого загруженного веб-сайта проверьте `ct`, чтобы убедиться, что текущая операция не отменена.</span><span class="sxs-lookup"><span data-stu-id="695bc-160">Before calling `DisplayResults` to display the results for each downloaded website, check `ct` to verify that the current operation hasn’t been canceled.</span></span>

<span data-ttu-id="695bc-161">В следующем коде показаны эти изменения, которые помечены звездочками.</span><span class="sxs-lookup"><span data-stu-id="695bc-161">The following code shows these changes, which are marked with asterisks.</span></span>

```csharp
// *** Provide a parameter for the CancellationToken from StartButton_Click.
async Task AccessTheWebAsync(CancellationToken ct)
{
    // Declare an HttpClient object.
    HttpClient client = new HttpClient();

    // Make a list of web addresses.
    List<string> urlList = SetUpURLList();

    var total = 0;
    var position = 0;

    foreach (var url in urlList)
    {
        // *** Use the HttpClient.GetAsync method because it accepts a
        // cancellation token.
        HttpResponseMessage response = await client.GetAsync(url, ct);

        // *** Retrieve the website contents from the HttpResponseMessage.
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

        // *** Check for cancellations before displaying information about the
        // latest site.
        ct.ThrowIfCancellationRequested();

        DisplayResults(url, urlContents, ++position);

        // Update the total.
        total += urlContents.Length;
    }

    // Display the total count for all of the websites.
    ResultsTextBox.Text +=
        $"\r\n\r\nTOTAL bytes returned:  {total}\r\n";
}
```

<span data-ttu-id="695bc-162">При многократном нажатии кнопки **Start** во время выполнения этого приложения код должен создать результаты, похожие на следующие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="695bc-162">If you choose the **Start** button several times while this app is running, it should produce results that resemble the following output.</span></span>

```output
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               122505
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
Download canceled.

1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
Download canceled.

1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

<span data-ttu-id="695bc-163">Чтобы исключить частичные списки, раскомментируйте первую строку кода в `StartButton_Click`, чтобы очищать текстовое поле при каждом перезапуске операции.</span><span class="sxs-lookup"><span data-stu-id="695bc-163">To eliminate the partial lists, uncomment the first line of code in `StartButton_Click` to clear the text box each time the user restarts the operation.</span></span>

### <a name="BKMK_RunMultipleOperations"></a> <span data-ttu-id="695bc-164">Запуск нескольких операций и постановка выходных данных в очередь</span><span class="sxs-lookup"><span data-stu-id="695bc-164">Run Multiple Operations and Queue the Output</span></span>

<span data-ttu-id="695bc-165">Третий пример является наиболее сложным, так как приложение запускает другую асинхронную операцию каждый раз, когда пользователь нажимает кнопку **Start**, и все операции выполняются до завершения.</span><span class="sxs-lookup"><span data-stu-id="695bc-165">This third example is the most complicated in that the app starts another asynchronous operation each time that the user chooses the **Start** button, and all the operations run to completion.</span></span> <span data-ttu-id="695bc-166">Все запрошенные операции загружают веб-сайты из списка асинхронно, однако выходные данные операций представляются последовательно.</span><span class="sxs-lookup"><span data-stu-id="695bc-166">All the requested operations download websites from the list asynchronously, but the output from the operations is presented sequentially.</span></span> <span data-ttu-id="695bc-167">Получается, что фактические действия загрузки чередуются, как показывают выходные данные в разделе [Распознавание возникновения повторного входа](#BKMK_RecognizingReentrancy), однако список результатов для каждой группы отображается отдельно.</span><span class="sxs-lookup"><span data-stu-id="695bc-167">That is, the actual downloading activity is interleaved, as the output in [Recognizing Reentrancy](#BKMK_RecognizingReentrancy) shows, but the list of results for each group is presented separately.</span></span>

<span data-ttu-id="695bc-168">Операции совместно используют глобальную переменную <xref:System.Threading.Tasks.Task>, `pendingWork`, служащую привратником для процесса отображения.</span><span class="sxs-lookup"><span data-stu-id="695bc-168">The operations share a global <xref:System.Threading.Tasks.Task>, `pendingWork`, which serves as a gatekeeper for the display process.</span></span>

<span data-ttu-id="695bc-169">Чтобы настроить этот сценарий, внесите следующие изменения в основной код, который содержится в разделе [Проверка и выполнение примера приложения](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="695bc-169">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span> <span data-ttu-id="695bc-170">Также можно загрузить готовое приложение в разделе [Примеры асинхронности. Поддержка повторного входа в классических приложениях .NET](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span><span class="sxs-lookup"><span data-stu-id="695bc-170">You also can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="695bc-171">Этот проект называется QueueResults.</span><span class="sxs-lookup"><span data-stu-id="695bc-171">The name of the project is QueueResults.</span></span>

<span data-ttu-id="695bc-172">Ниже показаны выходные данные, отображаемые в результате нажатия кнопки **Start** только один раз.</span><span class="sxs-lookup"><span data-stu-id="695bc-172">The following output shows the result if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="695bc-173">Метка A указывает, что это результат первого нажатия кнопки **Start**.</span><span class="sxs-lookup"><span data-stu-id="695bc-173">The letter label, A, indicates that the result is from the first time the **Start** button is chosen.</span></span> <span data-ttu-id="695bc-174">Нумерация показывает порядок отображения URL-адресов в списке целевых объектов для загрузки.</span><span class="sxs-lookup"><span data-stu-id="695bc-174">The numbers show the order of the URLs in the list of download targets.</span></span>

```output
#Starting group A.
#Task assigned for group A.

A-1. msdn.microsoft.com/library/hh191443.aspx                87389
A-2. msdn.microsoft.com/library/aa578028.aspx               209858
A-3. msdn.microsoft.com/library/jj155761.aspx                30870
A-4. msdn.microsoft.com/library/hh290140.aspx               119027
A-5. msdn.microsoft.com/library/hh524395.aspx                71260
A-6. msdn.microsoft.com/library/ms404677.aspx               199186
A-7. msdn.microsoft.com                                            53266
A-8. msdn.microsoft.com/library/ff730837.aspx               148020

TOTAL bytes returned:  918876

#Group A is complete.
```

<span data-ttu-id="695bc-175">Если пользователь нажимает кнопку **Start** три раза, приложение выдает результат, похожий на приведенный ниже.</span><span class="sxs-lookup"><span data-stu-id="695bc-175">If the user chooses the **Start** button three times, the app produces output that resembles the following lines.</span></span> <span data-ttu-id="695bc-176">Информационные строки, начинающиеся с символа #, отслеживают ход выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="695bc-176">The information lines that start with a pound sign (#) trace the progress of the application.</span></span>

```output
#Starting group A.
#Task assigned for group A.

A-1. msdn.microsoft.com/library/hh191443.aspx                87389
A-2. msdn.microsoft.com/library/aa578028.aspx               207089
A-3. msdn.microsoft.com/library/jj155761.aspx                30870
A-4. msdn.microsoft.com/library/hh290140.aspx               119027
A-5. msdn.microsoft.com/library/hh524395.aspx                71259
A-6. msdn.microsoft.com/library/ms404677.aspx               199185

#Starting group B.
#Task assigned for group B.

A-7. msdn.microsoft.com                                            53266

#Starting group C.
#Task assigned for group C.

A-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  916095

B-1. msdn.microsoft.com/library/hh191443.aspx                87389
B-2. msdn.microsoft.com/library/aa578028.aspx               207089
B-3. msdn.microsoft.com/library/jj155761.aspx                30870
B-4. msdn.microsoft.com/library/hh290140.aspx               119027
B-5. msdn.microsoft.com/library/hh524395.aspx                71260
B-6. msdn.microsoft.com/library/ms404677.aspx               199186

#Group A is complete.

B-7. msdn.microsoft.com                                            53266
B-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  916097

C-1. msdn.microsoft.com/library/hh191443.aspx                87389
C-2. msdn.microsoft.com/library/aa578028.aspx               207089

#Group B is complete.

C-3. msdn.microsoft.com/library/jj155761.aspx                30870
C-4. msdn.microsoft.com/library/hh290140.aspx               119027
C-5. msdn.microsoft.com/library/hh524395.aspx                72765
C-6. msdn.microsoft.com/library/ms404677.aspx               199186
C-7. msdn.microsoft.com                                            56190
C-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  920526

#Group C is complete.
```

<span data-ttu-id="695bc-177">Группы B и C запускаются до завершения группы A, однако результаты для каждой группы отображаются отдельно.</span><span class="sxs-lookup"><span data-stu-id="695bc-177">Groups B and C start before group A has finished, but the output for the each group appears separately.</span></span> <span data-ttu-id="695bc-178">Все выходные данные для группы A отображаются сначала, затем идут все выходные данные для группы B и, наконец, для группы C. Приложение всегда отображает группы по порядку и для каждой группы всегда отображает сведения об отдельных веб-сайтах в порядке появления URL-адресов в списке URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="695bc-178">All the output for group A appears first, followed by all the output for group B, and then all the output for group C. The app always displays the groups in order and, for each group, always displays the information about the individual websites in the order that the URLs appear in the list of URLs.</span></span>

<span data-ttu-id="695bc-179">Тем не менее невозможно предсказать порядок, в котором фактически происходит загрузка.</span><span class="sxs-lookup"><span data-stu-id="695bc-179">However, you can't predict the order in which the downloads actually happen.</span></span> <span data-ttu-id="695bc-180">После запуска нескольких групп все созданные ими задачи загрузки остаются активными.</span><span class="sxs-lookup"><span data-stu-id="695bc-180">After multiple groups have been started, the download tasks that they generate are all active.</span></span> <span data-ttu-id="695bc-181">Не следует предполагать, что данные A-1 будут загружены до данных B-1, а данные A-1 будут загружены до данных A-2.</span><span class="sxs-lookup"><span data-stu-id="695bc-181">You can't assume that A-1 will be downloaded before B-1, and you can't assume that A-1 will be downloaded before A-2.</span></span>

#### <a name="global-definitions"></a><span data-ttu-id="695bc-182">Глобальные определения</span><span class="sxs-lookup"><span data-stu-id="695bc-182">Global Definitions</span></span>

<span data-ttu-id="695bc-183">Пример кода содержит объявление двух следующих глобальных переменных, доступных для всех методов.</span><span class="sxs-lookup"><span data-stu-id="695bc-183">The sample code contains the following two global declarations that are visible from all methods.</span></span>

```csharp
public partial class MainWindow : Window  // Class MainPage in Windows Store app.
{
    // ***Declare the following variables where all methods can access them.
    private Task pendingWork = null;
    private char group = (char)('A' - 1);
```

<span data-ttu-id="695bc-184">Переменная `Task`, `pendingWork`, отслеживает процесс отображения и предотвращает прерывание операции отображения одной группы другой группой.</span><span class="sxs-lookup"><span data-stu-id="695bc-184">The `Task` variable, `pendingWork`, oversees the display process and prevents any group from interrupting another group's display operation.</span></span> <span data-ttu-id="695bc-185">Символьная переменная, `group`, помечает выходные данные различных групп, чтобы гарантировать отображение результатов в ожидаемом порядке.</span><span class="sxs-lookup"><span data-stu-id="695bc-185">The character variable, `group`, labels the output from different groups to verify that results appear in the expected order.</span></span>

#### <a name="the-click-event-handler"></a><span data-ttu-id="695bc-186">Обработчик событий нажатия</span><span class="sxs-lookup"><span data-stu-id="695bc-186">The Click Event Handler</span></span>

<span data-ttu-id="695bc-187">Обработчик событий `StartButton_Click` увеличивает букву группы каждый раз, когда пользователь нажимает кнопку **Start**.</span><span class="sxs-lookup"><span data-stu-id="695bc-187">The event handler, `StartButton_Click`, increments the group letter each time the user chooses the **Start** button.</span></span> <span data-ttu-id="695bc-188">Затем обработчик вызывает метод `AccessTheWebAsync` для запуска операции загрузки.</span><span class="sxs-lookup"><span data-stu-id="695bc-188">Then the handler calls `AccessTheWebAsync` to run the downloading operation.</span></span>

```csharp
private async void StartButton_Click(object sender, RoutedEventArgs e)
{
    // ***Verify that each group's results are displayed together, and that
    // the groups display in order, by marking each group with a letter.
    group = (char)(group + 1);
    ResultsTextBox.Text += $"\r\n\r\n#Starting group {group}.";

    try
    {
        // *** Pass the group value to AccessTheWebAsync.
        char finishedGroup = await AccessTheWebAsync(group);

        // The following line verifies a successful return from the download and
        // display procedures.
        ResultsTextBox.Text += $"\r\n\r\n#Group {finishedGroup} is complete.\r\n";
    }
    catch (Exception)
    {
        ResultsTextBox.Text += "\r\nDownloads failed.";
    }
}
```

#### <a name="the-accessthewebasync-method"></a><span data-ttu-id="695bc-189">Метод AccessTheWebAsync</span><span class="sxs-lookup"><span data-stu-id="695bc-189">The AccessTheWebAsync Method</span></span>

<span data-ttu-id="695bc-190">В этом примере метод `AccessTheWebAsync` разбит на два метода.</span><span class="sxs-lookup"><span data-stu-id="695bc-190">This example splits `AccessTheWebAsync` into two methods.</span></span> <span data-ttu-id="695bc-191">Первый метод, `AccessTheWebAsync`, запускает все задачи загрузки для группы и передает задаче `pendingWork` управление процессом отображения.</span><span class="sxs-lookup"><span data-stu-id="695bc-191">The first method, `AccessTheWebAsync`, starts all the download tasks for a group and sets up `pendingWork` to control the display process.</span></span> <span data-ttu-id="695bc-192">Метод использует запрос LINQ и <xref:System.Linq.Enumerable.ToArray%2A> для запуска всех задач загрузки одновременно.</span><span class="sxs-lookup"><span data-stu-id="695bc-192">The method uses a Language Integrated Query (LINQ query) and <xref:System.Linq.Enumerable.ToArray%2A> to start all the download tasks at the same time.</span></span>

<span data-ttu-id="695bc-193">Затем метод `AccessTheWebAsync` вызывает метод `FinishOneGroupAsync` для ожидания завершения каждой загрузки и отображения ее длины.</span><span class="sxs-lookup"><span data-stu-id="695bc-193">`AccessTheWebAsync` then calls `FinishOneGroupAsync` to await the completion of each download and display its length.</span></span>

<span data-ttu-id="695bc-194">Метод `FinishOneGroupAsync` возвращает задачу, которая назначена `pendingWork`, в `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="695bc-194">`FinishOneGroupAsync` returns a task that's assigned to `pendingWork` in `AccessTheWebAsync`.</span></span> <span data-ttu-id="695bc-195">Это значение предотвращает прерывание другой операцией до завершения выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="695bc-195">That value prevents interruption by another operation before the task is complete.</span></span>

```csharp
private async Task<char> AccessTheWebAsync(char grp)
{
    HttpClient client = new HttpClient();

    // Make a list of the web addresses to download.
    List<string> urlList = SetUpURLList();

    // ***Kick off the downloads. The application of ToArray activates all the download tasks.
    Task<byte[]>[] getContentTasks = urlList.Select(url => client.GetByteArrayAsync(url)).ToArray();

    // ***Call the method that awaits the downloads and displays the results.
    // Assign the Task that FinishOneGroupAsync returns to the gatekeeper task, pendingWork.
    pendingWork = FinishOneGroupAsync(urlList, getContentTasks, grp);

    ResultsTextBox.Text += $"\r\n#Task assigned for group {grp}. Download tasks are active.\r\n";

    // ***This task is complete when a group has finished downloading and displaying.
    await pendingWork;

    // You can do other work here or just return.
    return grp;
}
```

#### <a name="the-finishonegroupasync-method"></a><span data-ttu-id="695bc-196">Метод FinishOneGroupAsync</span><span class="sxs-lookup"><span data-stu-id="695bc-196">The FinishOneGroupAsync Method</span></span>

<span data-ttu-id="695bc-197">Этот метод выполняет циклический переход по задачам загрузки в группе, ожидая каждую из них, отображая длину загруженного веб-сайта и добавляя длину в общую сумму.</span><span class="sxs-lookup"><span data-stu-id="695bc-197">This method cycles through the download tasks in a group, awaiting each one, displaying the length of the downloaded website, and adding the length to the total.</span></span>

<span data-ttu-id="695bc-198">Первый оператор в `FinishOneGroupAsync` использует `pendingWork`, чтобы гарантировать, что ввод метода не помешает выполнению операции, которая уже находится в процессе отображения или в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="695bc-198">The first statement in `FinishOneGroupAsync` uses `pendingWork` to make sure that entering the method doesn't interfere with an operation that is already in the display process or that's already waiting.</span></span> <span data-ttu-id="695bc-199">Если такая операция выполняется, новая операция должна дождаться своей очереди.</span><span class="sxs-lookup"><span data-stu-id="695bc-199">If such an operation is in progress, the entering operation must wait its turn.</span></span>

```csharp
private async Task FinishOneGroupAsync(List<string> urls, Task<byte[]>[] contentTasks, char grp)
{
    // ***Wait for the previous group to finish displaying results.
    if (pendingWork != null) await pendingWork;

    int total = 0;

    // contentTasks is the array of Tasks that was created in AccessTheWebAsync.
    for (int i = 0; i < contentTasks.Length; i++)
    {
        // Await the download of a particular URL, and then display the URL and
        // its length.
        byte[] content = await contentTasks[i];
        DisplayResults(urls[i], content, i, grp);
        total += content.Length;
    }

    // Display the total count for all of the websites.
    ResultsTextBox.Text +=
        $"\r\n\r\nTOTAL bytes returned:  {total}\r\n";
}
```

#### <a name="points-of-interest"></a><span data-ttu-id="695bc-200">Интересующие точки</span><span class="sxs-lookup"><span data-stu-id="695bc-200">Points of Interest</span></span>

<span data-ttu-id="695bc-201">Информационные строки, начинающиеся с символа # в выходных данных, поясняют, как работает этот пример.</span><span class="sxs-lookup"><span data-stu-id="695bc-201">The information lines that start with a pound sign (#) in the output clarify how this example works.</span></span>

<span data-ttu-id="695bc-202">Выходные данные демонстрируют следующие схемы.</span><span class="sxs-lookup"><span data-stu-id="695bc-202">The output shows the following patterns.</span></span>

- <span data-ttu-id="695bc-203">Группу можно запустить, когда предыдущая группа отображает свои выходные данные, но отображение выходных данных предыдущей группы не прерывается.</span><span class="sxs-lookup"><span data-stu-id="695bc-203">A group can be started while a previous group is displaying its output, but the display of the previous group's output isn't interrupted.</span></span>

    ```output
    #Starting group A.
    #Task assigned for group A. Download tasks are active.

    A-1. msdn.microsoft.com/library/hh191443.aspx                87389
    A-2. msdn.microsoft.com/library/aa578028.aspx               207089
    A-3. msdn.microsoft.com/library/jj155761.aspx                30870
    A-4. msdn.microsoft.com/library/hh290140.aspx               119037
    A-5. msdn.microsoft.com/library/hh524395.aspx                71260

    #Starting group B.
    #Task assigned for group B. Download tasks are active.

    A-6. msdn.microsoft.com/library/ms404677.aspx               199186
    A-7. msdn.microsoft.com                                            53078
    A-8. msdn.microsoft.com/library/ff730837.aspx               148010

    TOTAL bytes returned:  915919

    B-1. msdn.microsoft.com/library/hh191443.aspx                87388
    B-2. msdn.microsoft.com/library/aa578028.aspx               207089
    B-3. msdn.microsoft.com/library/jj155761.aspx                30870

    #Group A is complete.

    B-4. msdn.microsoft.com/library/hh290140.aspx               119027
    B-5. msdn.microsoft.com/library/hh524395.aspx                71260
    B-6. msdn.microsoft.com/library/ms404677.aspx               199186
    B-7. msdn.microsoft.com                                            53078
    B-8. msdn.microsoft.com/library/ff730837.aspx               148010

    TOTAL bytes returned:  915908
    ```

- <span data-ttu-id="695bc-204">Задача `pendingWork` имеет значение NULL при запуске метода `FinishOneGroupAsync` только для группы A, которая запускается первой.</span><span class="sxs-lookup"><span data-stu-id="695bc-204">The `pendingWork` task is null  at the start of `FinishOneGroupAsync` only for group A, which started first.</span></span> <span data-ttu-id="695bc-205">Группа A еще не завершила выражение await, когда она достигает метода `FinishOneGroupAsync`.</span><span class="sxs-lookup"><span data-stu-id="695bc-205">Group A hasn’t yet completed an await expression when it reaches `FinishOneGroupAsync`.</span></span> <span data-ttu-id="695bc-206">Таким образом, управление не возвращается `AccessTheWebAsync`, а первое присваивание задаче `pendingWork` не возникает.</span><span class="sxs-lookup"><span data-stu-id="695bc-206">Therefore, control hasn't returned to `AccessTheWebAsync`, and the first assignment to `pendingWork` hasn't occurred.</span></span>

- <span data-ttu-id="695bc-207">Следующие две строки всегда отображаются в выходных данных вместе.</span><span class="sxs-lookup"><span data-stu-id="695bc-207">The following two lines always appear together in the output.</span></span> <span data-ttu-id="695bc-208">Код не прерывается нигде между запуском операции группы в обработчике `StartButton_Click` и назначением задачи для группы в `pendingWork`.</span><span class="sxs-lookup"><span data-stu-id="695bc-208">The code is never interrupted between starting a group's operation in `StartButton_Click` and assigning a task for the group to `pendingWork`.</span></span>

    ```output
    #Starting group B.
    #Task assigned for group B. Download tasks are active.
    ```

    <span data-ttu-id="695bc-209">После входа группы в обработчик `StartButton_Click` операция не завершает выражение await до входа операции в метод `FinishOneGroupAsync`.</span><span class="sxs-lookup"><span data-stu-id="695bc-209">After a group enters `StartButton_Click`, the operation doesn't complete an await expression until the operation enters `FinishOneGroupAsync`.</span></span> <span data-ttu-id="695bc-210">Таким образом, другие операции не могут получить контроль во время выполнения этого фрагмента кода.</span><span class="sxs-lookup"><span data-stu-id="695bc-210">Therefore, no other operation can gain control during that segment of code.</span></span>

## <a name="BKMD_SettingUpTheExample"></a> <span data-ttu-id="695bc-211">Проверка и выполнение примера приложения</span><span class="sxs-lookup"><span data-stu-id="695bc-211">Reviewing and Running the Example App</span></span>

<span data-ttu-id="695bc-212">Чтобы лучше понять пример приложения, его можно загрузить, построить самостоятельно или просмотреть код в конце этого раздела, не реализуя приложение.</span><span class="sxs-lookup"><span data-stu-id="695bc-212">To better understand the example app, you can download it, build it yourself, or review the code at the end of this topic without implementing the app.</span></span>

> [!NOTE]
> <span data-ttu-id="695bc-213">Для выполнения этого примера как традиционного приложения Windows Presentation Foundation на компьютере должны быть установлены Visual Studio 2012 или более поздней версии и .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="695bc-213">To run the example as a Windows Presentation Foundation (WPF) desktop app, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

### <a name="BKMK_DownloadingTheApp"></a> <span data-ttu-id="695bc-214">Загрузка приложения</span><span class="sxs-lookup"><span data-stu-id="695bc-214">Downloading the App</span></span>

1. <span data-ttu-id="695bc-215">Скачайте сжатый файл в разделе [Примеры асинхронности. Поддержка повторного входа в классических приложениях .NET](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span><span class="sxs-lookup"><span data-stu-id="695bc-215">Download the compressed file from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span>

2. <span data-ttu-id="695bc-216">Распакуйте загруженный файл, а затем запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="695bc-216">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

3. <span data-ttu-id="695bc-217">В строке меню выберите **Файл**, **Открыть**, **Проект/Решение**.</span><span class="sxs-lookup"><span data-stu-id="695bc-217">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

4. <span data-ttu-id="695bc-218">Перейдите к папке, содержащей распакованный пример кода, а затем откройте файл решения (SLN-файл).</span><span class="sxs-lookup"><span data-stu-id="695bc-218">Navigate to the folder that holds the decompressed sample code, and then open the solution (.sln) file.</span></span>

5. <span data-ttu-id="695bc-219">В **обозревателе решений** откройте контекстное меню нужного проекта и выберите пункт **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="695bc-219">In **Solution Explorer**, open the shortcut menu for the project that you want to run, and then choose **Set as StartUpProject**.</span></span>

6. <span data-ttu-id="695bc-220">Нажмите сочетание клавиш CTRL+F5, чтобы выполнить сборку и запуск проекта.</span><span class="sxs-lookup"><span data-stu-id="695bc-220">Choose the CTRL+F5 keys to build and run the project.</span></span>

### <a name="BKMK_BuildingTheApp"></a> <span data-ttu-id="695bc-221">Сборка приложения</span><span class="sxs-lookup"><span data-stu-id="695bc-221">Building the App</span></span>

<span data-ttu-id="695bc-222">В следующих разделах приведен код для построения примера как приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="695bc-222">The following section provides the code to build the example as a WPF app.</span></span>

##### <a name="to-build-a-wpf-app"></a><span data-ttu-id="695bc-223">Построение приложения WPF</span><span class="sxs-lookup"><span data-stu-id="695bc-223">To build a WPF app</span></span>

1. <span data-ttu-id="695bc-224">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="695bc-224">Start Visual Studio.</span></span>

2. <span data-ttu-id="695bc-225">В строке меню выберите **Файл**, **Создать**, **Проект**.</span><span class="sxs-lookup"><span data-stu-id="695bc-225">On the menu bar, choose **File**, **New**, **Project**.</span></span>

     <span data-ttu-id="695bc-226">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="695bc-226">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="695bc-227">В области **Установленные шаблоны** разверните узел **Visual C#** и выберите **Windows**.</span><span class="sxs-lookup"><span data-stu-id="695bc-227">In the **Installed Templates** pane, expand **Visual C#**, and then expand **Windows**.</span></span>

4. <span data-ttu-id="695bc-228">В списке типов проектов выберите **Приложение WPF**.</span><span class="sxs-lookup"><span data-stu-id="695bc-228">In the list of project types, choose **WPF Application**.</span></span>

5. <span data-ttu-id="695bc-229">Присвойте проекту имя `WebsiteDownloadWPF`, выберите .NET Framework версии 4.6 или более поздней, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="695bc-229">Name the project `WebsiteDownloadWPF`, choose .NET Framework version of 4.6 or higher and then click the **OK** button.</span></span>

     <span data-ttu-id="695bc-230">В **обозревателе решений** появится новый проект.</span><span class="sxs-lookup"><span data-stu-id="695bc-230">The new project appears in **Solution Explorer**.</span></span>

6. <span data-ttu-id="695bc-231">В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="695bc-231">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

     <span data-ttu-id="695bc-232">Если вкладка не отображается, откройте контекстное меню для MainWindow.xaml в **обозревателе решений** и выберите пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="695bc-232">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>

7. <span data-ttu-id="695bc-233">Замените код в представлении **XAML** файла MainWindow.xaml на следующий.</span><span class="sxs-lookup"><span data-stu-id="695bc-233">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>

    ```csharp
    <Window x:Class="WebsiteDownloadWPF.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:WebsiteDownloadWPF"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        mc:Ignorable="d">

        <Grid Width="517" Height="360">
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="-1,0,0,0" VerticalAlignment="Top" Click="StartButton_Click" Height="53" Background="#FFA89B9B" FontSize="36" Width="518"  />
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" Margin="-1,53,0,-36" TextWrapping="Wrap" VerticalAlignment="Top" Height="343" FontSize="10" ScrollViewer.VerticalScrollBarVisibility="Visible" Width="518" FontFamily="Lucida Console" />
        </Grid>
    </Window>
    ```

     <span data-ttu-id="695bc-234">В представлении **Конструктор** файла MainWindow.xaml появится простое окно, содержащее кнопку и текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="695bc-234">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>

8. <span data-ttu-id="695bc-235">В **обозревателе решений** щелкните правой кнопкой мыши **Ссылки** и выберите **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="695bc-235">In **Solution Explorer**, right-click on **References** and select **Add Reference**.</span></span>

     <span data-ttu-id="695bc-236">Добавьте ссылку на <xref:System.Net.Http>, если она еще не выбрана.</span><span class="sxs-lookup"><span data-stu-id="695bc-236">Add a reference for <xref:System.Net.Http>, if it is not selected already.</span></span>

9. <span data-ttu-id="695bc-237">В **обозревателе решений** откройте контекстное меню для MainWindow.xaml.cs и выберите пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="695bc-237">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>

10. <span data-ttu-id="695bc-238">В MainWindow.xaml.cs замените код на следующий.</span><span class="sxs-lookup"><span data-stu-id="695bc-238">In MainWindow.xaml.cs, replace the code with the following code.</span></span>

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

    // Add the following using directives, and add a reference for System.Net.Http.
    using System.Net.Http;
    using System.Threading;

    namespace WebsiteDownloadWPF
    {
        public partial class MainWindow : Window
        {
            public MainWindow()
            {
                System.Net.ServicePointManager.SecurityProtocol |= System.Net.SecurityProtocolType.Tls12;
                InitializeComponent();
            }

            private async void StartButton_Click(object sender, RoutedEventArgs e)
            {
                // This line is commented out to make the results clearer in the output.
                //ResultsTextBox.Text = "";

                try
                {
                    await AccessTheWebAsync();
                }
                catch (Exception)
                {
                    ResultsTextBox.Text += "\r\nDownloads failed.";
                }
            }

            private async Task AccessTheWebAsync()
            {
                // Declare an HttpClient object.
                HttpClient client = new HttpClient();

                // Make a list of web addresses.
                List<string> urlList = SetUpURLList();

                var total = 0;
                var position = 0;

                foreach (var url in urlList)
                {
                    // GetByteArrayAsync returns a task. At completion, the task
                    // produces a byte array.
                    byte[] urlContents = await client.GetByteArrayAsync(url);

                    DisplayResults(url, urlContents, ++position);

                    // Update the total.
                    total += urlContents.Length;
                }

                // Display the total count for all of the websites.
                ResultsTextBox.Text +=
                    $"\r\n\r\nTOTAL bytes returned:  {total}\r\n";
            }

            private List<string> SetUpURLList()
            {
                List<string> urls = new List<string>
                {
                    "https://msdn.microsoft.com/library/hh191443.aspx",
                    "https://msdn.microsoft.com/library/aa578028.aspx",
                    "https://msdn.microsoft.com/library/jj155761.aspx",
                    "https://msdn.microsoft.com/library/hh290140.aspx",
                    "https://msdn.microsoft.com/library/hh524395.aspx",
                    "https://msdn.microsoft.com/library/ms404677.aspx",
                    "https://msdn.microsoft.com",
                    "https://msdn.microsoft.com/library/ff730837.aspx"
                };
                return urls;
            }

            private void DisplayResults(string url, byte[] content, int pos)
            {
                // Display the length of each website. The string format is designed
                // to be used with a monospaced font, such as Lucida Console or
                // Global Monospace.

                // Strip off the "https://".
                var displayURL = url.Replace("https://", "");
                // Display position in the URL list, the URL, and the number of bytes.
                ResultsTextBox.Text += $"\n{pos}. {displayURL,-58} {content.Length,8}";
            }
        }
    }
    ```

11. <span data-ttu-id="695bc-239">Нажмите сочетание клавиш CTRL+F5, чтобы запустить программу, а затем несколько раз нажмите кнопку **Start**.</span><span class="sxs-lookup"><span data-stu-id="695bc-239">Choose the CTRL+F5 keys to run the program, and then choose the **Start** button several times.</span></span>

12. <span data-ttu-id="695bc-240">Внесите изменения, описанные в разделах [Отключение кнопки запуска](#BKMK_DisableTheStartButton), [Отмена и перезапуск операции](#BKMK_CancelAndRestart) или [Запуск нескольких операций и постановка выходных данных в очередь](#BKMK_RunMultipleOperations) для обработки повторного входа.</span><span class="sxs-lookup"><span data-stu-id="695bc-240">Make the changes from [Disable the Start Button](#BKMK_DisableTheStartButton), [Cancel and Restart the Operation](#BKMK_CancelAndRestart), or [Run Multiple Operations and Queue the Output](#BKMK_RunMultipleOperations) to handle the reentrancy.</span></span>

## <a name="see-also"></a><span data-ttu-id="695bc-241">См. также</span><span class="sxs-lookup"><span data-stu-id="695bc-241">See also</span></span>

- [<span data-ttu-id="695bc-242">Пошаговое руководство: Доступ к Интернету с помощью модификатора Async и оператора Await в C#</span><span class="sxs-lookup"><span data-stu-id="695bc-242">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="695bc-243">Асинхронное программирование с использованием ключевых слов async и await (C#)</span><span class="sxs-lookup"><span data-stu-id="695bc-243">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
