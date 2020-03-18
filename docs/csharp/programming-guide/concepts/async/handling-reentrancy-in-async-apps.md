---
title: Обработка повторного входа в асинхронных приложениях (C#)
ms.date: 07/20/2015
ms.assetid: 47c5075e-c448-45ce-9155-ed4e7e98c677
ms.openlocfilehash: 67fbbd294ffe6219b58065f974543b2dd483a92c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77451867"
---
# <a name="handling-reentrancy-in-async-apps-c"></a>Обработка повторного входа в асинхронных приложениях (C#)

При включении асинхронного кода в приложение следует учесть и по возможности избежать повторного входа, под которым подразумевается повторный ввод асинхронной операции до ее завершения. Если не определить и не обработать возможности повторного входа, это может привести к непредвиденным результатам.

**В этом разделе**

- [Распознавание поддержки повторного входа](#BKMK_RecognizingReentrancy)

- [Обработка поддержки повторного входа](#BKMK_HandlingReentrancy)

  - [Отключение кнопки запуска](#BKMK_DisableTheStartButton)

  - [Отмена и перезапуск операции](#BKMK_CancelAndRestart)

  - [Запуск нескольких операций и постановка выходных данных в очередь](#BKMK_RunMultipleOperations)

- [Проверка и выполнение примера приложения](#BKMD_SettingUpTheExample)

> [!NOTE]
> Для выполнения этого примера нужно, чтобы на компьютере были установлены Visual Studio 2012 или более поздней версии и .NET Framework 4.5 или более поздней версии.

> [!NOTE]
> Версия протокола TLS 1.2 теперь является минимальной версией для использования в разработке приложений. Если приложение предназначено для более ранней версии .NET Framework, чем 4.7, обратитесь к следующей статье, чтобы ознакомиться с [рекомендациями по протоколу TLS в .NET Framework](../../../../framework/network-programming/tls.md).

## <a name="BKMK_RecognizingReentrancy"></a> Распознавание поддержки повторного входа

В примере в этом разделе пользователь нажимает кнопку **Start**, чтобы инициировать асинхронное приложение, загружающее ряд веб-сайтов и вычисляющее общее число загруженных байтов. Синхронная версия примера реагирует одинаково, независимо от того, сколько раз пользователь нажмет кнопку, поскольку после первого раза поток пользовательского интерфейса игнорирует эти события до завершения выполнения приложения. При этом в асинхронном приложении поток пользовательского интерфейса продолжает реагировать, и можно ввести асинхронную операцию повторно до ее завершения.

В следующем примере показаны ожидаемые выходные данные, если пользователь нажимает кнопку **Start** только один раз. На экран выводится список загруженных веб-сайтов, размер которых указан в байтах. Общее число байтов отображается в конце списка.

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

Однако если пользователь нажимает кнопку больше одного раза, обработчик событий вызывается несколько раз и процесс загрузки будет каждый раз выполняться повторно. В результате одновременно запускается несколько асинхронных операций, получаемые выходные данные чередуются и счетчик общего числа байтов выдает неоднозначные результаты.

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

Чтобы просмотреть код, создающий эти выходные данные, перейдите к концу раздела. Можно поэкспериментировать с кодом, загрузив решение на локальный компьютер и затем запустив проект WebsiteDownload или воспользовавшись кодом в конце этого раздела для создания собственного проекта. Дополнительные сведения и инструкции см. в разделе [Проверка и выполнение примера приложения](#BKMD_SettingUpTheExample).

## <a name="BKMK_HandlingReentrancy"></a> Обработка поддержки повторного входа

Обрабатывать повторный вход можно разными способами в зависимости от того, что требуется от приложения. В этом разделе представлены следующие примеры.

- [Отключение кнопки запуска](#BKMK_DisableTheStartButton)

  Отключение кнопки **Start** во время выполнения операции, чтобы пользователь не мог прервать ее выполнение.

- [Отмена и перезапуск операции](#BKMK_CancelAndRestart)

  Отмена выполнения любой операции, которая выполняется в тот момент, когда пользователь снова нажимает кнопку **Start**, с последующим продолжением операции, которая была запрошена последней.

- [Запуск нескольких операций и постановка выходных данных в очередь](#BKMK_RunMultipleOperations)

  Разрешение всем запрошенным операциям выполняться асинхронно и настройка согласования отображения выходных данных для вывода результатов каждой операции вместе и по порядку.

### <a name="BKMK_DisableTheStartButton"></a> Отключение кнопки запуска

Можно заблокировать кнопку **Start** во время операции, отключив кнопку в верхней части обработчика событий `StartButton_Click`. Затем можно повторно включить кнопку из блока `finally` по завершении операции, чтобы пользователь мог запустить приложение повторно.

Чтобы настроить этот сценарий, внесите следующие изменения в основной код, который содержится в разделе [Проверка и выполнение примера приложения](#BKMD_SettingUpTheExample). Также можно загрузить готовое приложение в разделе [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06). Этот проект называется DisableStartButton.

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

В результате этих изменений кнопка не будет реагировать в течение загрузки веб-сайтов методом `AccessTheWebAsync`, поэтому повторный вход в процесс будет невозможен.

### <a name="BKMK_CancelAndRestart"></a> Отмена и перезапуск операции

Вместо отключения кнопки **Start** можно оставить кнопку активной, но при этом, если пользователь нажмет эту кнопку еще раз, нужно отменить операцию, которая уже выполняется, и задать продолжение выполнения последней запущенной операции.

Дополнительные сведения об отмене см. в разделе [Настройка асинхронного приложения (C#)](./fine-tuning-your-async-application.md).

Чтобы настроить этот сценарий, внесите следующие изменения в основной код, который содержится в разделе [Проверка и выполнение примера приложения](#BKMD_SettingUpTheExample). Также можно загрузить готовое приложение в разделе [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06). Этот проект называется CancelAndRestart.

1. Объявите переменную <xref:System.Threading.CancellationTokenSource>, `cts`, которая находится в области действия всех методов.

    ```csharp
    public partial class MainWindow : Window   // Or class MainPage
    {
        // *** Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;
    ```

2. В `StartButton_Click` определите, выполняется ли операция на данный момент. Если значение `cts` — null, значит, активных операций нет. Если значение не равно null, выполняющаяся операция отменена.

    ```csharp
    // *** If a download process is already underway, cancel it.
    if (cts != null)
    {
        cts.Cancel();
    }
    ```

3. Задайте для `cts` другое значение, представляющее текущий процесс.

    ```csharp
    // *** Now set cts to a new value that you can use to cancel the current process
    // if the button is chosen again.
    CancellationTokenSource newCTS = new CancellationTokenSource();
    cts = newCTS;
    ```

4. В конце процедуры `StartButton_Click` текущий процесс будет выполнен, поэтому верните для `cts` значение null.

    ```csharp
    // *** When the process is complete, signal that another process can begin.
    if (cts == newCTS)
        cts = null;
    ```

В следующем коде показаны все изменения в `StartButton_Click`. Добавления помечены звездочками.

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

В `AccessTheWebAsync` внесите следующие изменения.

- Добавьте параметр, чтобы принимать токен отмены из `StartButton_Click`.

- Используйте метод <xref:System.Net.Http.HttpClient.GetAsync%2A> для загрузки веб-сайтов, так как `GetAsync` принимает аргумент <xref:System.Threading.CancellationToken>.

- Перед вызовом метода `DisplayResults` для отображения результатов для каждого загруженного веб-сайта проверьте `ct`, чтобы убедиться, что текущая операция не отменена.

В следующем коде показаны эти изменения, которые помечены звездочками.

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

При многократном нажатии кнопки **Start** во время выполнения этого приложения код должен создать результаты, похожие на следующие выходные данные.

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

Чтобы исключить частичные списки, раскомментируйте первую строку кода в `StartButton_Click`, чтобы очищать текстовое поле при каждом перезапуске операции.

### <a name="BKMK_RunMultipleOperations"></a> Запуск нескольких операций и постановка выходных данных в очередь

Третий пример является наиболее сложным, так как приложение запускает другую асинхронную операцию каждый раз, когда пользователь нажимает кнопку **Start**, и все операции выполняются до завершения. Все запрошенные операции загружают веб-сайты из списка асинхронно, однако выходные данные операций представляются последовательно. Получается, что фактические действия загрузки чередуются, как показывают выходные данные в разделе [Распознавание возникновения повторного входа](#BKMK_RecognizingReentrancy), однако список результатов для каждой группы отображается отдельно.

Операции совместно используют глобальную переменную <xref:System.Threading.Tasks.Task>, `pendingWork`, служащую привратником для процесса отображения.

Чтобы настроить этот сценарий, внесите следующие изменения в основной код, который содержится в разделе [Проверка и выполнение примера приложения](#BKMD_SettingUpTheExample). Также можно загрузить готовое приложение в разделе [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06). Этот проект называется QueueResults.

Ниже показаны выходные данные, отображаемые в результате нажатия кнопки **Start** только один раз. Метка A указывает, что это результат первого нажатия кнопки **Start**. Нумерация показывает порядок отображения URL-адресов в списке целевых объектов для загрузки.

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

Если пользователь нажимает кнопку **Start** три раза, приложение выдает результат, похожий на приведенный ниже. Информационные строки, начинающиеся с символа #, отслеживают ход выполнения приложения.

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

Группы B и C запускаются до завершения группы A, однако результаты для каждой группы отображаются отдельно. Все выходные данные для группы A отображаются сначала, затем идут все выходные данные для группы B и, наконец, для группы C. Приложение всегда отображает группы по порядку и для каждой группы всегда отображает сведения об отдельных веб-сайтах в порядке появления URL-адресов в списке URL-адресов.

Тем не менее невозможно предсказать порядок, в котором фактически происходит загрузка. После запуска нескольких групп все созданные ими задачи загрузки остаются активными. Не следует предполагать, что данные A-1 будут загружены до данных B-1, а данные A-1 будут загружены до данных A-2.

#### <a name="global-definitions"></a>Глобальные определения

Пример кода содержит объявление двух следующих глобальных переменных, доступных для всех методов.

```csharp
public partial class MainWindow : Window  // Class MainPage in Windows Store app.
{
    // ***Declare the following variables where all methods can access them.
    private Task pendingWork = null;
    private char group = (char)('A' - 1);
```

Переменная `Task`, `pendingWork`, отслеживает процесс отображения и предотвращает прерывание операции отображения одной группы другой группой. Символьная переменная, `group`, помечает выходные данные различных групп, чтобы гарантировать отображение результатов в ожидаемом порядке.

#### <a name="the-click-event-handler"></a>Обработчик событий нажатия

Обработчик событий `StartButton_Click` увеличивает букву группы каждый раз, когда пользователь нажимает кнопку **Start**. Затем обработчик вызывает метод `AccessTheWebAsync` для запуска операции загрузки.

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

#### <a name="the-accessthewebasync-method"></a>Метод AccessTheWebAsync

В этом примере метод `AccessTheWebAsync` разбит на два метода. Первый метод, `AccessTheWebAsync`, запускает все задачи загрузки для группы и передает задаче `pendingWork` управление процессом отображения. Метод использует запрос LINQ и <xref:System.Linq.Enumerable.ToArray%2A> для запуска всех задач загрузки одновременно.

Затем метод `AccessTheWebAsync` вызывает метод `FinishOneGroupAsync` для ожидания завершения каждой загрузки и отображения ее длины.

Метод `FinishOneGroupAsync` возвращает задачу, которая назначена `pendingWork`, в `AccessTheWebAsync`. Это значение предотвращает прерывание другой операцией до завершения выполнения задачи.

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

#### <a name="the-finishonegroupasync-method"></a>Метод FinishOneGroupAsync

Этот метод выполняет циклический переход по задачам загрузки в группе, ожидая каждую из них, отображая длину загруженного веб-сайта и добавляя длину в общую сумму.

Первый оператор в `FinishOneGroupAsync` использует `pendingWork`, чтобы гарантировать, что ввод метода не помешает выполнению операции, которая уже находится в процессе отображения или в состоянии ожидания. Если такая операция выполняется, новая операция должна дождаться своей очереди.

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

#### <a name="points-of-interest"></a>Интересующие точки

Информационные строки, начинающиеся с символа # в выходных данных, поясняют, как работает этот пример.

Выходные данные демонстрируют следующие схемы.

- Группу можно запустить, когда предыдущая группа отображает свои выходные данные, но отображение выходных данных предыдущей группы не прерывается.

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

- Задача `pendingWork` имеет значение NULL при запуске метода `FinishOneGroupAsync` только для группы A, которая запускается первой. Группа A еще не завершила выражение await, когда она достигает метода `FinishOneGroupAsync`. Таким образом, управление не возвращается `AccessTheWebAsync`, а первое присваивание задаче `pendingWork` не возникает.

- Следующие две строки всегда отображаются в выходных данных вместе. Код не прерывается нигде между запуском операции группы в обработчике `StartButton_Click` и назначением задачи для группы в `pendingWork`.

    ```output
    #Starting group B.
    #Task assigned for group B. Download tasks are active.
    ```

    После входа группы в обработчик `StartButton_Click` операция не завершает выражение await до входа операции в метод `FinishOneGroupAsync`. Таким образом, другие операции не могут получить контроль во время выполнения этого фрагмента кода.

## <a name="BKMD_SettingUpTheExample"></a> Проверка и выполнение примера приложения

Чтобы лучше понять пример приложения, его можно загрузить, построить самостоятельно или просмотреть код в конце этого раздела, не реализуя приложение.

> [!NOTE]
> Для выполнения этого примера как традиционного приложения Windows Presentation Foundation на компьютере должны быть установлены Visual Studio 2012 или более поздней версии и .NET Framework 4.5 или более поздней версии.

### <a name="BKMK_DownloadingTheApp"></a> Загрузка приложения

1. Скачайте сжатый файл в разделе [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).

2. Распакуйте загруженный файл, а затем запустите Visual Studio.

3. В строке меню выберите **Файл**, **Открыть**, **Проект/Решение**.

4. Перейдите к папке, содержащей распакованный пример кода, а затем откройте файл решения (SLN-файл).

5. В **обозревателе решений** откройте контекстное меню нужного проекта и выберите пункт **Назначить запускаемым проектом**.

6. Нажмите сочетание клавиш CTRL+F5, чтобы выполнить сборку и запуск проекта.

### <a name="BKMK_BuildingTheApp"></a> Сборка приложения

В следующих разделах приведен код для построения примера как приложения WPF.

##### <a name="to-build-a-wpf-app"></a>Построение приложения WPF

1. Запустите среду Visual Studio.

2. В главном меню выберите **Файл**, **Создать**, **Проект**.

     Откроется диалоговое окно **Новый проект** .

3. В области **Установленные шаблоны** разверните узел **Visual C#** и выберите **Windows**.

4. В списке типов проектов выберите **Приложение WPF**.

5. Присвойте проекту имя `WebsiteDownloadWPF`, выберите .NET Framework версии 4.6 или более поздней, а затем нажмите кнопку **ОК**.

     В **обозревателе решений** появится новый проект.

6. В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .

     Если вкладка не отображается, откройте контекстное меню для MainWindow.xaml в **обозревателе решений** и выберите пункт **Просмотреть код**.

7. Замените код в представлении **XAML** файла MainWindow.xaml на следующий.

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

     В представлении **Конструктор** файла MainWindow.xaml появится простое окно, содержащее кнопку и текстовое поле.

8. В **обозревателе решений** щелкните правой кнопкой мыши **Ссылки** и выберите **Добавить ссылку**.

     Добавьте ссылку на <xref:System.Net.Http>, если она еще не выбрана.

9. В **обозревателе решений** откройте контекстное меню для MainWindow.xaml.cs и выберите пункт **Просмотреть код**.

10. В MainWindow.xaml.cs замените код на следующий.

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

11. Нажмите сочетание клавиш CTRL+F5, чтобы запустить программу, а затем несколько раз нажмите кнопку **Start**.

12. Внесите изменения, описанные в разделах [Отключение кнопки запуска](#BKMK_DisableTheStartButton), [Отмена и перезапуск операции](#BKMK_CancelAndRestart) или [Запуск нескольких операций и постановка выходных данных в очередь](#BKMK_RunMultipleOperations) для обработки повторного входа.

## <a name="see-also"></a>См. также раздел

- [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) (Пошаговое руководство. Обращение к веб-сайтам с помощью async и await в C#)
- [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](./index.md)
