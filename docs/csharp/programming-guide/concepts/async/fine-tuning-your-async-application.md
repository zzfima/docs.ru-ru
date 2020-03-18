---
title: Настройка асинхронного приложения (C#)
ms.date: 07/20/2015
ms.assetid: 97696eb9-81fc-4940-9655-84daa8eb4d5c
ms.openlocfilehash: cff50e62ff62b70e97e7ea6e03714326d774e407
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "73970240"
---
# <a name="fine-tuning-your-async-application-c"></a><span data-ttu-id="c4e76-102">Настройка асинхронного приложения (C#)</span><span class="sxs-lookup"><span data-stu-id="c4e76-102">Fine-Tuning Your Async Application (C#)</span></span>
<span data-ttu-id="c4e76-103">Методы и свойства, доступные при использовании типа <xref:System.Threading.Tasks.Task>, позволяют сделать приложение более точным и гибким.</span><span class="sxs-lookup"><span data-stu-id="c4e76-103">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="c4e76-104">В подразделах этого раздела приводятся примеры, в которых используются <xref:System.Threading.CancellationToken> и важные методы `Task`, такие как <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c4e76-104">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="c4e76-105">С помощью `WhenAny` и `WhenAll` можно легко запускать несколько задач и ожидать их завершения путем наблюдения за одной из них.</span><span class="sxs-lookup"><span data-stu-id="c4e76-105">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
- <span data-ttu-id="c4e76-106">`WhenAny` возвращает задачу, которая завершается после завершения любой задачи в коллекции.</span><span class="sxs-lookup"><span data-stu-id="c4e76-106">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="c4e76-107">Примеры использования `WhenAny` см. в разделах [Отмена оставшихся асинхронных задач после завершения одной из них (C#)](./cancel-remaining-async-tasks-after-one-is-complete.md) и [Запуск нескольких асинхронных задач и их обработка по мере завершения (C#)](./start-multiple-async-tasks-and-process-them-as-they-complete.md).</span><span class="sxs-lookup"><span data-stu-id="c4e76-107">For examples that use `WhenAny`, see [Cancel Remaining Async Tasks after One Is Complete (C#)](./cancel-remaining-async-tasks-after-one-is-complete.md) and [Start Multiple Async Tasks and Process Them As They Complete (C#)](./start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
- <span data-ttu-id="c4e76-108">`WhenAll` возвращает задачу, которая завершается после завершения всех задач в коллекции.</span><span class="sxs-lookup"><span data-stu-id="c4e76-108">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="c4e76-109">Дополнительные сведения и пример, использующий метод `WhenAll`, см. в разделе [Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="c4e76-109">For more information and an example that uses `WhenAll`, see [How to extend the async walkthrough by using Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>
  
 <span data-ttu-id="c4e76-110">Этот раздел содержит следующие примеры.</span><span class="sxs-lookup"><span data-stu-id="c4e76-110">This section includes the following examples.</span></span>  
  
- <span data-ttu-id="c4e76-111">[Отмена асинхронной задачи или списка задач (C#)](./cancel-an-async-task-or-a-list-of-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="c4e76-111">[Cancel an Async Task or a List of Tasks (C#)](./cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
- [<span data-ttu-id="c4e76-112">Отмена асинхронных задач после определенного периода времени (C#)</span><span class="sxs-lookup"><span data-stu-id="c4e76-112">Cancel Async Tasks after a Period of Time (C#)</span></span>](./cancel-async-tasks-after-a-period-of-time.md)  
  
- [<span data-ttu-id="c4e76-113">Отмена оставшихся асинхронных задач после завершения одной из них (C#)</span><span class="sxs-lookup"><span data-stu-id="c4e76-113">Cancel Remaining Async Tasks after One Is Complete (C#)</span></span>](./cancel-remaining-async-tasks-after-one-is-complete.md)  
  
- [<span data-ttu-id="c4e76-114">Запуск нескольких асинхронных задач и их обработка по мере завершения (C#)</span><span class="sxs-lookup"><span data-stu-id="c4e76-114">Start Multiple Async Tasks and Process Them As They Complete (C#)</span></span>](./start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
> <span data-ttu-id="c4e76-115">Для выполнения примеров необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="c4e76-115">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="c4e76-116">Проекты создают пользовательский интерфейс, содержащий кнопку, которая запускает процесс, и кнопку, которая его отменяет, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="c4e76-116">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="c4e76-117">Кнопки называются `startButton` и `cancelButton`.</span><span class="sxs-lookup"><span data-stu-id="c4e76-117">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="c4e76-118">![Окно WPF с кнопкой "Отмена"](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Диалоговое окно с кнопкой запуска и остановки")</span><span class="sxs-lookup"><span data-stu-id="c4e76-118">![WPF window with Cancel button](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Dialog box with a Start and Stop button")</span></span>  
  
 <span data-ttu-id="c4e76-119">Скачать полный проект Windows Presentation Foundation (WPF) можно со страницы [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span><span class="sxs-lookup"><span data-stu-id="c4e76-119">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e76-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c4e76-120">See also</span></span>

- [<span data-ttu-id="c4e76-121">Асинхронное программирование с использованием ключевых слов Async и Await (C#)</span><span class="sxs-lookup"><span data-stu-id="c4e76-121">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
