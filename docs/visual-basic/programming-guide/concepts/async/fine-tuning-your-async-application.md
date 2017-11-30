---
title: "Настройка асинхронного приложения (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: eb5f85701c3b298fea30586797c9411347e8ec84
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="fine-tuning-your-async-application-visual-basic"></a><span data-ttu-id="d4175-102">Настройка асинхронного приложения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4175-102">Fine-Tuning Your Async Application (Visual Basic)</span></span>
<span data-ttu-id="d4175-103">Методы и свойства, доступные при использовании типа <xref:System.Threading.Tasks.Task>, позволяют сделать приложение более точным и гибким.</span><span class="sxs-lookup"><span data-stu-id="d4175-103">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="d4175-104">В подразделах этого раздела приводятся примеры, в которых используются <xref:System.Threading.CancellationToken> и важные методы `Task`, такие как <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d4175-104">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="d4175-105">С помощью `WhenAny` и `WhenAll` можно легко запускать несколько задач и ожидать их завершения путем наблюдения за одной из них.</span><span class="sxs-lookup"><span data-stu-id="d4175-105">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
-   <span data-ttu-id="d4175-106">`WhenAny` возвращает задачу, которая завершается после завершения любой задачи в коллекции.</span><span class="sxs-lookup"><span data-stu-id="d4175-106">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="d4175-107">Примеры использования `WhenAny`, в разделе [отмена оставшихся асинхронных задач после одного завершено (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)и [запуск нескольких асинхронных задач и процесс их как они полностью (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span><span class="sxs-lookup"><span data-stu-id="d4175-107">For examples that use `WhenAny`, see  [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)and [Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
-   <span data-ttu-id="d4175-108">`WhenAll` возвращает задачу, которая завершается после завершения всех задач в коллекции.</span><span class="sxs-lookup"><span data-stu-id="d4175-108">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="d4175-109">Дополнительные сведения и пример, использующий `WhenAll`, в разделе [как: расширение Async пошагового руководства с использованием метода Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="d4175-109">For more information and an example that uses `WhenAll`, see [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="d4175-110">Этот раздел содержит следующие примеры.</span><span class="sxs-lookup"><span data-stu-id="d4175-110">This section includes the following examples.</span></span>  
  
-   <span data-ttu-id="d4175-111">[Отмена асинхронной задачи или списка задач (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="d4175-111">[Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
-   [<span data-ttu-id="d4175-112">Отмена асинхронных задач после определенного периода времени (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4175-112">Cancel Async Tasks after a Period of Time (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [<span data-ttu-id="d4175-113">Отмена оставшихся асинхронных задач после одной из них завершения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4175-113">Cancel Remaining Async Tasks after One Is Complete (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [<span data-ttu-id="d4175-114">Запуск нескольких асинхронных задач и их обработка по мере их выполнения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4175-114">Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  <span data-ttu-id="d4175-115">Для выполнения примеров необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="d4175-115">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="d4175-116">Проекты создают пользовательский интерфейс, содержащий кнопку, которая запускает процесс, и кнопку, которая его отменяет, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="d4175-116">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="d4175-117">Кнопки называются `startButton` и `cancelButton`.</span><span class="sxs-lookup"><span data-stu-id="d4175-117">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="d4175-118">![Окно WPF с кнопкой "Отмена"](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "Cancellation")</span><span class="sxs-lookup"><span data-stu-id="d4175-118">![WPF window with Cancel button](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "Cancellation")</span></span>  
  
 <span data-ttu-id="d4175-119">Скачать полный проект Windows Presentation Foundation (WPF) можно со страницы [Пример асинхронности. Тонкая настройка приложения](http://go.microsoft.com/fwlink/?LinkId=255046).</span><span class="sxs-lookup"><span data-stu-id="d4175-119">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4175-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d4175-120">See Also</span></span>  
 [<span data-ttu-id="d4175-121">Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4175-121">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)
