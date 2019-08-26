---
title: Отмена асинхронных задач после определенного периода времени (C#)
ms.date: 07/20/2015
ms.assetid: 194282c2-399f-46da-a7a6-96674e00b0b3
ms.openlocfilehash: e00ff51e987275c6c84822f7095c82ed03b53176
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595757"
---
# <a name="cancel-async-tasks-after-a-period-of-time-c"></a>Отмена асинхронных задач после определенного периода времени (C#)

Если не нужно дожидаться, пока завершится выполнение асинхронной операции, ее можно отменить по истечении определенного периода времени с помощью метода <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType>. Этот метод планирует отмену всех связанных задач, не завершенных в течение времени, установленного выражением `CancelAfter`.

В этом примере добавляется код, составленный в разделе [Отмена асинхронной задачи или списка задач (C#)](./cancel-an-async-task-or-a-list-of-tasks.md), для загрузки списка веб-сайтов и отображения длины содержимого каждого из них.

> [!NOTE]
> Для выполнения примеров необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.

## <a name="download-the-example"></a>Скачивание примера

Скачать полный проект Windows Presentation Foundation (WPF) можно со страницы [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea). Затем выполните следующие шаги.

1. Распакуйте загруженный файл, а затем запустите Visual Studio.

2. В строке меню выберите **Файл** > **Открыть** > **Решение или проект**.

3. В диалоговом окне **Открытие проекта** откройте папку с примером кода, который вы распаковали, а затем откройте файл решения (SLN) для AsyncFineTuningCS.

4. В **обозревателе решений** откройте контекстное меню проекта **CancelAfterTime** и выберите команду **Назначить запускаемым проектом**.

5. Нажмите клавишу **F5**, чтобы запустить проект. (Или нажмите **CTRL**+**F5**, чтобы запустить проект без отладки).

6. Выполните программу несколько раз, чтобы убедиться, что ее выходные данные могут содержать выходные данные по всем веб-сайтам, по некоторым из них или не содержать никакие данные по веб-сайтам.

Если вы не хотите скачивать проект, можете просмотреть файл MainWindow.xaml.cs в конце этого раздела.

## <a name="build-the-example"></a>Сборка примера

Пример в этом разделе добавляется в проект для отмены списка задач, разработка которого описывается в разделе [Отмена асинхронной задачи или списка задач (C#)](./cancel-an-async-task-or-a-list-of-tasks.md). В примере используется тот же пользовательский интерфейс, хотя кнопка **Отмена** не используется явно.

Для самостоятельной сборки примера шаг за шагом следуйте инструкциям в разделе "Загрузка примера", но выберите в качестве **запускаемого проекта** проект **CancelAfterOneTask**. Добавьте изменения, приведенные в данном разделе, в этот проект.

Чтобы задать максимальный период времени, по истечении которого задачи будут отмечены как отмененные, добавьте вызов `CancelAfter` в `startButton_Click`, как показано в приведенном ниже примере. Добавления помечены звездочками.

```csharp
private async void startButton_Click(object sender, RoutedEventArgs e)
{
    // Instantiate the CancellationTokenSource.
    cts = new CancellationTokenSource();

    resultsTextBox.Clear();

    try
    {
        // ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
        // can adjust the time.)
        cts.CancelAfter(2500);

        await AccessTheWebAsync(cts.Token);
        resultsTextBox.Text += "\r\nDownloads succeeded.\r\n";
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
```

 Выполните программу несколько раз, чтобы убедиться, что ее выходные данные могут содержать выходные данные по всем веб-сайтам, по некоторым из них или не содержать никакие данные по веб-сайтам. Следующие результаты приводятся для примера.

```
Length of the downloaded string: 35990.

Length of the downloaded string: 407399.

Length of the downloaded string: 226091.

Downloads canceled.
```

## <a name="complete-example"></a>Полный пример

Приведенный ниже код — полный текст файла MainWindow.xaml.cs для примера. Звездочками помечаются элементы, добавленные для этого примера.

Обратите внимание на то, что необходимо добавить ссылку для <xref:System.Net.Http>.

Вы можете скачать проект из статьи [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).

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

namespace CancelAfterTime
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
                // ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
                // can adjust the time.)
                cts.CancelAfter(2500);

                await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text += "\r\nDownloads succeeded.\r\n";
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

        // You can still include a Cancel button if you want to.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        async Task AccessTheWebAsync(CancellationToken ct)
        {
            // Declare an HttpClient object.
            HttpClient client = new HttpClient();

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            foreach (var url in urlList)
            {
                // GetAsync returns a Task<HttpResponseMessage>.
                // Argument ct carries the message if the Cancel button is chosen.
                // Note that the Cancel button cancels all remaining downloads.
                HttpResponseMessage response = await client.GetAsync(url, ct);

                // Retrieve the website contents from the HttpResponseMessage.
                byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
            }
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }
    }

    // Sample Output:

    // Length of the downloaded string: 35990.

    // Length of the downloaded string: 407399.

    // Length of the downloaded string: 226091.

    // Downloads canceled.
}
```

## <a name="see-also"></a>См. также

- [Асинхронное программирование с использованием ключевых слов async и await (C#)](./index.md)
- [Пошаговое руководство: Доступ к Интернету с помощью модификатора Async и оператора Await в C#](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Отмена асинхронной задачи или списка задач в C#](./cancel-an-async-task-or-a-list-of-tasks.md)
- [Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md) (Тонкая настройка асинхронного приложения в C#)
- [Пример использования Async. Настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
