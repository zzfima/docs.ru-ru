---
title: "Настройка асинхронного приложения (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e031c2e23430a62629424ee57a140a7d8da41777
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="fine-tuning-your-async-application-visual-basic"></a><span data-ttu-id="de21c-102">Настройка асинхронного приложения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de21c-102">Fine-Tuning Your Async Application (Visual Basic)</span></span>
<span data-ttu-id="de21c-103">Можно добавить точность и гибкость для асинхронных приложений с помощью методов и свойств, <xref:System.Threading.Tasks.Task>типа делает доступными.</xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="de21c-103">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="de21c-104">Подразделы в этом разделе примеры, использующие <xref:System.Threading.CancellationToken>и важных `Task` такие методы, как <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>и <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>.</xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName> </xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> </xref:System.Threading.CancellationToken></span><span class="sxs-lookup"><span data-stu-id="de21c-104">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="de21c-105">С помощью `WhenAny` и `WhenAll`, можно легко запустить несколько задач и ожидания их завершения путем наблюдения за одну задачу.</span><span class="sxs-lookup"><span data-stu-id="de21c-105">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
-   <span data-ttu-id="de21c-106">`WhenAny`Возвращает задачу, которая выполняется после завершения любой задачи в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="de21c-106">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="de21c-107">Примеры использования `WhenAny`, в разделе [отмена оставшихся асинхронных задач после одного завершено (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)и [запуск нескольких асинхронных задач и процесс их как они полностью (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span><span class="sxs-lookup"><span data-stu-id="de21c-107">For examples that use `WhenAny`, see  [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)and [Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
-   <span data-ttu-id="de21c-108">`WhenAll`Возвращает задачу, которая выполняется после выполнения всех задач в коллекции.</span><span class="sxs-lookup"><span data-stu-id="de21c-108">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="de21c-109">Дополнительные сведения и пример, использующий `WhenAll`, в разделе [как: расширение Async пошагового руководства, с использованием метода Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="de21c-109">For more information and an example that uses `WhenAll`, see [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="de21c-110">Этот раздел содержит следующие примеры.</span><span class="sxs-lookup"><span data-stu-id="de21c-110">This section includes the following examples.</span></span>  
  
-   <span data-ttu-id="de21c-111">[Отмена асинхронной задачи или списка задач (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="de21c-111">[Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
-   [<span data-ttu-id="de21c-112">Отмена асинхронных задач после определенного периода времени (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de21c-112">Cancel Async Tasks after a Period of Time (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [<span data-ttu-id="de21c-113">Отмена оставшихся асинхронных задач после один полный (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de21c-113">Cancel Remaining Async Tasks after One Is Complete (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [<span data-ttu-id="de21c-114">Запуск нескольких асинхронных задач и их обработка по мере завершения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de21c-114">Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  <span data-ttu-id="de21c-115">Для выполнения примеров, необходимо иметь Visual Studio 2012 или более поздней версии и платформы .NET Framework 4.5 или более новая версия вашего компьютера.</span><span class="sxs-lookup"><span data-stu-id="de21c-115">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="de21c-116">Проекты создания пользовательского интерфейса, который содержит кнопки, которая запускает процесс и кнопки, которая отменяет его, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="de21c-116">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="de21c-117">Кнопки называются `startButton` и `cancelButton`.</span><span class="sxs-lookup"><span data-stu-id="de21c-117">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="de21c-118">![Окно WPF с кнопкой "Отмена"](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "отмены")</span><span class="sxs-lookup"><span data-stu-id="de21c-118">![WPF window with Cancel button](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "Cancellation")</span></span>  
  
 <span data-ttu-id="de21c-119">Можно загрузить полный проектов Windows Presentation Foundation (WPF) из [образец Async: нормально Настройка приложения](http://go.microsoft.com/fwlink/?LinkId=255046).</span><span class="sxs-lookup"><span data-stu-id="de21c-119">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de21c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="de21c-120">See Also</span></span>  
 [<span data-ttu-id="de21c-121">Асинхронное программирование с использованием Async и Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de21c-121">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)
