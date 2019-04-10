---
title: Практическое руководство. Запуск рабочего процесса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f814ff82-fe2b-4614-aebb-b768c3e61179
ms.openlocfilehash: 06ac34f5ba5d95bd9f000a35036cf288d3c8f7f7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59319928"
---
# <a name="how-to-run-a-workflow"></a><span data-ttu-id="b33cd-102">Практическое руководство. Запуск рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="b33cd-102">How to: Run a Workflow</span></span>
<span data-ttu-id="b33cd-103">Этот раздел продолжает учебник Windows Workflow Foundation Приступая к работе и описывает, как создать узел рабочего процесса и запустить рабочий процесс, описанный в предыдущем [как: Создание рабочего процесса](how-to-create-a-workflow.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="b33cd-103">This topic is a continuation of the Windows Workflow Foundation Getting Started tutorial and discusses how to create a workflow host and run the workflow defined in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) topic.</span></span>

> [!NOTE]
>  <span data-ttu-id="b33cd-104">Каждый раздел в учебнике «Приступая к работе» построен на основе предыдущих разделов.</span><span class="sxs-lookup"><span data-stu-id="b33cd-104">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="b33cd-105">Для изучения этого раздела, необходимо сначала выполнить [как: Создание действия](how-to-create-an-activity.md) и [как: Создание рабочего процесса](how-to-create-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="b33cd-105">To complete this topic you must first complete [How to: Create an Activity](how-to-create-an-activity.md) and [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="b33cd-106">Чтобы скачать завершенную версию учебника, см. раздел [Windows Workflow Foundation (WF45), учебник "Приступая к работе"](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="b33cd-106">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow-host-project"></a><span data-ttu-id="b33cd-107">Создание проекта узла рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="b33cd-107">To create the workflow host project</span></span>  
  
1. <span data-ttu-id="b33cd-108">Откройте решение из предыдущего [как: Создание действия](how-to-create-an-activity.md) темам с помощью Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="b33cd-108">Open the solution from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic by using Visual Studio 2012.</span></span>  
  
2. <span data-ttu-id="b33cd-109">Щелкните правой кнопкой мыши решение **WF45GettingStartedTutorial** в окне **Обозреватель решений** и выберите **Добавить**, **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="b33cd-109">Right-click the **WF45GettingStartedTutorial** solution in **Solution Explorer** and select **Add**, **New Project**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="b33cd-110">Если окно **Обозреватель решений** не отображается, в меню **Вид** выберите пункт **Обозреватель решений** .</span><span class="sxs-lookup"><span data-stu-id="b33cd-110">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="b33cd-111">В узле **Установленные** выберите пункты **Visual C#** и **Рабочий процесс** (или **Visual Basic**и **Рабочий процесс**).</span><span class="sxs-lookup"><span data-stu-id="b33cd-111">In the **Installed** node, select **Visual C#**, **Workflow** (or **Visual Basic**, **Workflow**).</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b33cd-112">В зависимости от того, какой язык программирования задан как основной в Visual Studio, узел **Visual C#** или **Visual Basic** может находиться в разделе **Другие языки** узла **Установленные** .</span><span class="sxs-lookup"><span data-stu-id="b33cd-112">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>

     <span data-ttu-id="b33cd-113">Убедитесь, что в раскрывающемся списке версий .NET Framework выбран пункт **.NET Framework 4.5** .</span><span class="sxs-lookup"><span data-stu-id="b33cd-113">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="b33cd-114">В списке **Рабочий процесс** выберите **Консольное приложение рабочего процесса** .</span><span class="sxs-lookup"><span data-stu-id="b33cd-114">Select **Workflow Console Application** from the **Workflow** list.</span></span> <span data-ttu-id="b33cd-115">Введите `NumberGuessWorkflowHost` в поле **Имя** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b33cd-115">Type `NumberGuessWorkflowHost` into the **Name** box and click **OK**.</span></span> <span data-ttu-id="b33cd-116">Будет создано начальное приложение рабочего процесса с базовой поддержкой размещения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b33cd-116">This creates a starter workflow application with basic workflow hosting support.</span></span> <span data-ttu-id="b33cd-117">Этот базовый код размещения изменяется и используется для выполнения приложения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b33cd-117">This basic hosting code is modified and used to run the workflow application.</span></span>

4. <span data-ttu-id="b33cd-118">Щелкните правой кнопкой мыши созданный проект **NumberGuessWorkflowHost** в **обозревателе решений** и выберите **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="b33cd-118">Right-click the newly added **NumberGuessWorkflowHost** project in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="b33cd-119">Выберите **Решение** из списка **Добавление ссылки** , установите флажок рядом с **NumberGuessWorkflowActivities**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b33cd-119">Select **Solution** from the **Add Reference** list, check the checkbox beside **NumberGuessWorkflowActivities**, and then click **OK**.</span></span>

5. <span data-ttu-id="b33cd-120">Щелкните правой кнопкой мыши **Workflow1.xaml** в окне **Обозреватель решений** и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b33cd-120">Right-click **Workflow1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="b33cd-121">Нажмите кнопку **ОК** для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="b33cd-121">Click **OK** to confirm.</span></span>

### <a name="to-modify-the-workflow-hosting-code"></a><span data-ttu-id="b33cd-122">Изменение кода размещения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="b33cd-122">To modify the workflow hosting code</span></span>

1. <span data-ttu-id="b33cd-123">В **Solution Explorer** дважды щелкните **Program.cs** или **Module1.vb** для вывода кода.</span><span class="sxs-lookup"><span data-stu-id="b33cd-123">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to display the code.</span></span>

    > [!TIP]
    >  <span data-ttu-id="b33cd-124">Если окно **Обозреватель решений** не отображается, в меню **Вид** выберите пункт **Обозреватель решений** .</span><span class="sxs-lookup"><span data-stu-id="b33cd-124">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>

     <span data-ttu-id="b33cd-125">Поскольку этот проект был создан с помощью шаблона **Консольное приложение рабочего процесса** , **Program.cs** или **Module1.vb** содержит следующий базовый код размещения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b33cd-125">Because this project was created by using the **Workflow Console Application** template, **Program.cs** or **Module1.vb** contains the following basic workflow hosting code.</span></span>

    ```vb
    ' Create and cache the workflow definition
    Activity workflow1 = new Workflow1()
    WorkflowInvoker.Invoke(workflow1)
    ```

    ```csharp
    // Create and cache the workflow definition
    Activity workflow1 = new Workflow1();
    WorkflowInvoker.Invoke(workflow1);
    ```

     <span data-ttu-id="b33cd-126">Этот код размещения использует <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="b33cd-126">This generated hosting code uses <xref:System.Activities.WorkflowInvoker>.</span></span> <xref:System.Activities.WorkflowInvoker> <span data-ttu-id="b33cd-127">предоставляет простой способ вызова рабочего процесса аналогично вызову метода и может использоваться только для рабочих процессов, не использующих сохраняемость.</span><span class="sxs-lookup"><span data-stu-id="b33cd-127">provides a simple way for invoking a workflow as if it were a method call and can be used only for workflows that do not use persistence.</span></span> <xref:System.Activities.WorkflowApplication> <span data-ttu-id="b33cd-128">предоставляет улучшенную модель выполнения рабочих процессов, включающую уведомления о событиях жизненного цикла, управление выполнением, возобновления закладок и сохраняемость.</span><span class="sxs-lookup"><span data-stu-id="b33cd-128">provides a richer model for executing workflows that includes notification of life-cycle events, execution control, bookmark resumption, and persistence.</span></span> <span data-ttu-id="b33cd-129">В этом примере используются закладки, а для размещения рабочего процесса используется <xref:System.Activities.WorkflowApplication> .</span><span class="sxs-lookup"><span data-stu-id="b33cd-129">This example uses bookmarks and <xref:System.Activities.WorkflowApplication> is used for hosting the workflow.</span></span> <span data-ttu-id="b33cd-130">Добавьте инструкцию `using` или **Imports** в начало файла **Program.cs** или **Module1.vb** после существующих инструкций **using** или **Imports** .</span><span class="sxs-lookup"><span data-stu-id="b33cd-130">Add the following `using` or **Imports** statement at the top of **Program.cs** or **Module1.vb** below the existing **using** or **Imports** statements.</span></span>

    ```vb
    Imports NumberGuessWorkflowActivities
    Imports System.Threading
    ```

    ```csharp
    using NumberGuessWorkflowActivities;
    using System.Threading;
    ```

     <span data-ttu-id="b33cd-131">Замените строки кода, использующие <xref:System.Activities.WorkflowInvoker> , следующим базовым кодом размещения <xref:System.Activities.WorkflowApplication> .</span><span class="sxs-lookup"><span data-stu-id="b33cd-131">Replace the lines of code that use <xref:System.Activities.WorkflowInvoker> with the following basic <xref:System.Activities.WorkflowApplication> hosting code.</span></span> <span data-ttu-id="b33cd-132">Этот образец кода размещения показывает основные шаги по размещению и вызову рабочего процесса, но пока не обладает достаточной функциональностью для успешного выполнения рабочего процесса, описанного в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="b33cd-132">This sample hosting code demonstrates the basic steps for hosting and invoking a workflow, but does not yet contain the functionality to successfully run the workflow from this topic.</span></span> <span data-ttu-id="b33cd-133">В ходе следующих шагов этот базовый код модифицируется и добавляются дополнительные функции, пока приложение не будет полностью готово.</span><span class="sxs-lookup"><span data-stu-id="b33cd-133">In the following steps, this basic code is modified and additional features are added until the application is complete.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b33cd-134">Замените `Workflow1` в этих примерах на `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, или `StateMachineNumberGuessWorkflow`, в зависимости от рабочего процесса, который вы выполнили на предыдущем [как: Создание рабочего процесса](how-to-create-a-workflow.md) шаг.</span><span class="sxs-lookup"><span data-stu-id="b33cd-134">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="b33cd-135">Если не заменить `Workflow1` , то при попытке создать или запустить рабочий процесс будут выданы ошибки сборки.</span><span class="sxs-lookup"><span data-stu-id="b33cd-135">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#4](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#4)]
     [!code-vb[CFX_WF_GettingStarted#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#4)]

     <span data-ttu-id="b33cd-136">Этот код создает объект <xref:System.Activities.WorkflowApplication>, подписывается на три события из жизненного цикла рабочего процесса, начинает рабочий процесс вызовом <xref:System.Activities.WorkflowApplication.Run%2A>, а затем ждет завершения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b33cd-136">This code creates a <xref:System.Activities.WorkflowApplication>, subscribes to three workflow life-cycle events, starts the workflow with a call to <xref:System.Activities.WorkflowApplication.Run%2A>, and then waits for the workflow to complete.</span></span> <span data-ttu-id="b33cd-137">После завершения рабочего процесса устанавливается <xref:System.Threading.AutoResetEvent> и ведущее приложение завершает работу.</span><span class="sxs-lookup"><span data-stu-id="b33cd-137">When the workflow completes, the <xref:System.Threading.AutoResetEvent> is set and the host application completes.</span></span>

### <a name="to-set-input-arguments-of-a-workflow"></a><span data-ttu-id="b33cd-138">Настройка входных аргументов рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="b33cd-138">To set input arguments of a workflow</span></span>

1. <span data-ttu-id="b33cd-139">Добавьте следующую инструкцию в начало файла **Program.cs** или **Module1.vb** после существующих инструкций `using` или `Imports` .</span><span class="sxs-lookup"><span data-stu-id="b33cd-139">Add the following statement at the top of **Program.cs** or **Module1.vb** below the existing `using` or `Imports` statements.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#5](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#5)]
     [!code-vb[CFX_WF_GettingStarted#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#5)]

2. <span data-ttu-id="b33cd-140">Замените строку кода, создающую новое <xref:System.Activities.WorkflowApplication> , следующим кодом, который создает и передает словарь параметров рабочему процессу, когда процесс создается.</span><span class="sxs-lookup"><span data-stu-id="b33cd-140">Replace the line of code that creates the new <xref:System.Activities.WorkflowApplication> with the following code that creates and passes a dictionary of parameters to the workflow when it is created.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b33cd-141">Замените `Workflow1` в этих примерах на `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, или `StateMachineNumberGuessWorkflow`, в зависимости от рабочего процесса, который вы выполнили на предыдущем [как: Создание рабочего процесса](how-to-create-a-workflow.md) шаг.</span><span class="sxs-lookup"><span data-stu-id="b33cd-141">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="b33cd-142">Если не заменить `Workflow1` , то при попытке создать или запустить рабочий процесс будут выданы ошибки сборки.</span><span class="sxs-lookup"><span data-stu-id="b33cd-142">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     <span data-ttu-id="b33cd-143">В этом словаре содержится один элемент с ключом `MaxNumber`.</span><span class="sxs-lookup"><span data-stu-id="b33cd-143">This dictionary contains one element with a key of `MaxNumber`.</span></span> <span data-ttu-id="b33cd-144">Ключи в словаре входных данных соответствуют входным аргументам в корневом действии рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b33cd-144">Keys in the input dictionary correspond to input arguments on the root activity of the workflow.</span></span> `MaxNumber` <span data-ttu-id="b33cd-145">используется рабочим процессом для определения верхней границы случайного числа.</span><span class="sxs-lookup"><span data-stu-id="b33cd-145">is used by the workflow to determine the upper bound for the randomly generated number.</span></span>

### <a name="to-retrieve-output-arguments-of-a-workflow"></a><span data-ttu-id="b33cd-146">Извлечение выходных аргументов рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="b33cd-146">To retrieve output arguments of a workflow</span></span>

1. <span data-ttu-id="b33cd-147">Модифицируйте обработчик <xref:System.Activities.WorkflowApplication.Completed%2A> , чтобы извлечь и отобразить число ходов, использованных рабочим процессом.</span><span class="sxs-lookup"><span data-stu-id="b33cd-147">Modify the <xref:System.Activities.WorkflowApplication.Completed%2A> handler to retrieve and display the number of turns used by the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#7](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#7)]
     [!code-vb[CFX_WF_GettingStarted#7](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#7)]

### <a name="to-resume-a-bookmark"></a><span data-ttu-id="b33cd-148">Возобновление закладки</span><span class="sxs-lookup"><span data-stu-id="b33cd-148">To resume a bookmark</span></span>

1. <span data-ttu-id="b33cd-149">Добавьте следующий код в начало метода `Main` сразу после существующего объявления <xref:System.Threading.AutoResetEvent> .</span><span class="sxs-lookup"><span data-stu-id="b33cd-149">Add the following code at the top of the `Main` method just after the existing <xref:System.Threading.AutoResetEvent> declaration.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#8](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#8)]
     [!code-vb[CFX_WF_GettingStarted#8](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#8)]

2. <span data-ttu-id="b33cd-150">Добавьте следующий обработчик <xref:System.Activities.WorkflowApplication.Idle%2A> сразу после трех существующих обработчиков жизненного цикла процесса в `Main`.</span><span class="sxs-lookup"><span data-stu-id="b33cd-150">Add the following <xref:System.Activities.WorkflowApplication.Idle%2A> handler just below the existing three workflow life-cycle handlers in `Main`.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#9](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#9)]
     [!code-vb[CFX_WF_GettingStarted#9](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#9)]

     <span data-ttu-id="b33cd-151">Каждый раз, когда рабочий процесс переходит в неактивный режим в ожидании следующего предположения, вызывается этот обработчик и устанавливается `idleAction` <xref:System.Threading.AutoResetEvent> .</span><span class="sxs-lookup"><span data-stu-id="b33cd-151">Each time the workflow becomes idle waiting for the next guess, this handler is called and the `idleAction` <xref:System.Threading.AutoResetEvent> is set.</span></span> <span data-ttu-id="b33cd-152">Код на следующем этапе использует `idleEvent` и `syncEvent` , чтобы определить, ждет рабочий процесс следующего предположения или он завершился.</span><span class="sxs-lookup"><span data-stu-id="b33cd-152">The code in the following step uses `idleEvent` and `syncEvent` to determine whether the workflow is waiting for the next guess or is complete.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b33cd-153">В этом примере ведущее приложение использует события автоматического сброса в обработчиках <xref:System.Activities.WorkflowApplication.Completed%2A> и <xref:System.Activities.WorkflowApplication.Idle%2A> , чтобы синхронизировать ведущее приложение с ходом выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b33cd-153">In this example, the host application uses auto-reset events in the <xref:System.Activities.WorkflowApplication.Completed%2A> and <xref:System.Activities.WorkflowApplication.Idle%2A> handlers to synchronize the host application with the progress of the workflow.</span></span> <span data-ttu-id="b33cd-154">Устанавливать блокировку и ждать неактивности рабочего процесса перед возобновлением закладки не обязательно, но в этом примере требуются события синхронизации, чтобы узел знал, завершен ли рабочий процесс, или он ждет дальнейшего ввода данных от пользователя с помощью <xref:System.Activities.Bookmark>.</span><span class="sxs-lookup"><span data-stu-id="b33cd-154">It is not necessary to block and wait for the workflow to become idle before resuming a bookmark, but in this example the synchronization events are required so the host knows whether the workflow is complete or whether it is waiting on more user input by using the <xref:System.Activities.Bookmark>.</span></span> <span data-ttu-id="b33cd-155">Дополнительные сведения см. в разделе [закладки](bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="b33cd-155">For more information, see [Bookmarks](bookmarks.md).</span></span>

3. <span data-ttu-id="b33cd-156">Удалите вызов `WaitOne`, замените его кодом для сборки входных данных от пользователя и возобновите <xref:System.Activities.Bookmark>.</span><span class="sxs-lookup"><span data-stu-id="b33cd-156">Remove the call to `WaitOne`, and replace it with code to gather input from the user and resume the <xref:System.Activities.Bookmark>.</span></span>

     <span data-ttu-id="b33cd-157">Удалите следующую строку кода.</span><span class="sxs-lookup"><span data-stu-id="b33cd-157">Remove the following line of code.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#10](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#10)]
     [!code-vb[CFX_WF_GettingStarted#10](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#10)]

     <span data-ttu-id="b33cd-158">Замените ее следующим примером.</span><span class="sxs-lookup"><span data-stu-id="b33cd-158">Replace it with the following example.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#11](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#11)]
     [!code-vb[CFX_WF_GettingStarted#11](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#11)]

## <a name="BKMK_ToRunTheApplication"></a> <span data-ttu-id="b33cd-159">Сборка и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="b33cd-159">To build and run the application</span></span>

1. <span data-ttu-id="b33cd-160">Щелкните правой кнопкой мыши **NumberGuessWorkflowHost** в окне **Обозреватель решений** и выберите команду **Установить как запускаемый проект**.</span><span class="sxs-lookup"><span data-stu-id="b33cd-160">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and select **Set as StartUp Project**.</span></span>

2. <span data-ttu-id="b33cd-161">Нажмите клавиши CTRL+F5 для сборки и запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="b33cd-161">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="b33cd-162">Попробуйте угадать число с наименьшим числом попыток.</span><span class="sxs-lookup"><span data-stu-id="b33cd-162">Try to guess the number in as few turns as possible.</span></span>

     <span data-ttu-id="b33cd-163">Чтобы протестировать приложение с другим стилем рабочего процесса, замените `Workflow1` в коде, который создает <xref:System.Activities.WorkflowApplication> , на `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`или `StateMachineNumberGuessWorkflow`в зависимости от того, какой стиль рабочего процесса нужен.</span><span class="sxs-lookup"><span data-stu-id="b33cd-163">To try the application with one of the other styles of workflow, replace `Workflow1` in the code that creates the <xref:System.Activities.WorkflowApplication> with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow style you desire.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     <span data-ttu-id="b33cd-164">Инструкции по добавлению сохраняемости к приложению рабочего процесса см. в следующем разделе [как: Создание и запуск длительно выполняющимся процессом](how-to-create-and-run-a-long-running-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="b33cd-164">For instructions about how to add persistence to a workflow application, see the next topic, [How to: Create and Run a Long Running Workflow](how-to-create-and-run-a-long-running-workflow.md).</span></span>

## <a name="example"></a><span data-ttu-id="b33cd-165">Пример</span><span class="sxs-lookup"><span data-stu-id="b33cd-165">Example</span></span>
 <span data-ttu-id="b33cd-166">Ниже приведен полный код для метода `Main` .</span><span class="sxs-lookup"><span data-stu-id="b33cd-166">The following example is the complete code listing for the `Main` method.</span></span>

> [!NOTE]
>  <span data-ttu-id="b33cd-167">Замените `Workflow1` в этих примерах на `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, или `StateMachineNumberGuessWorkflow`, в зависимости от рабочего процесса, который вы выполнили на предыдущем [как: Создание рабочего процесса](how-to-create-a-workflow.md) шаг.</span><span class="sxs-lookup"><span data-stu-id="b33cd-167">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="b33cd-168">Если не заменить `Workflow1` , то при попытке создать или запустить рабочий процесс будут выданы ошибки сборки.</span><span class="sxs-lookup"><span data-stu-id="b33cd-168">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

 [!code-csharp[CFX_WF_GettingStarted#12](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#12)]
 [!code-vb[CFX_WF_GettingStarted#12](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#12)]

## <a name="see-also"></a><span data-ttu-id="b33cd-169">См. также</span><span class="sxs-lookup"><span data-stu-id="b33cd-169">See also</span></span>

- <xref:System.Activities.WorkflowApplication>
- <xref:System.Activities.Bookmark>
- [<span data-ttu-id="b33cd-170">Программирование в Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="b33cd-170">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="b33cd-171">Учебник по началу работы</span><span class="sxs-lookup"><span data-stu-id="b33cd-171">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="b33cd-172">Практическое руководство. Создание рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="b33cd-172">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)
- [<span data-ttu-id="b33cd-173">Практическое руководство. Создание и запуск длительного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="b33cd-173">How to: Create and Run a Long Running Workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md)
- [<span data-ttu-id="b33cd-174">Ожидание входных данных в рабочем процессе</span><span class="sxs-lookup"><span data-stu-id="b33cd-174">Waiting for Input in a Workflow</span></span>](waiting-for-input-in-a-workflow.md)
- [<span data-ttu-id="b33cd-175">Размещение рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="b33cd-175">Hosting Workflows</span></span>](hosting-workflows.md)