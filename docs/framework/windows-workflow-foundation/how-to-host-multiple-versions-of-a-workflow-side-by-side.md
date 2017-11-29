---
title: "Как разместить параллельно несколько версий рабочего процесса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 09c575df-e0a3-4f3b-9e01-a7ac59d65287
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 713417131338dd683906eb2de56e615d4aa13c10
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-host-multiple-versions-of-a-workflow-side-by-side"></a><span data-ttu-id="b6a9e-102">Как разместить параллельно несколько версий рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="b6a9e-102">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>
<span data-ttu-id="b6a9e-103">`WorkflowIdentity` предоставляет разработчикам приложений рабочих процессов способ связать имя и версию с определением рабочего процесса, а также связать эти сведения с сохраненным экземпляром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-103">`WorkflowIdentity` provides a way for workflow application developers to associate a name and a version with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="b6a9e-104">Эти идентификационные данные могут быть использованы разработчиками приложений рабочего процесса для поддержки таких сценариев, как параллельное выполнение нескольких версий определения рабочего процесса, и являются ключевым элементом для других функциональных возможностей, таких как динамическое обновление.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-104">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="b6a9e-105">Этот шаг в учебнике показывает, как использовать `WorkflowIdentity` для размещения нескольких версий рабочих процессов одновременно.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-105">This step in the tutorial demonstrates how to use `WorkflowIdentity` to host multiple versions of a workflow at the same time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6a9e-106">Чтобы загрузить полную версию или просмотреть пошаговое видео учебника, см. [Windows Workflow Foundation (WF45) — учебник по началу работы](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="b6a9e-106">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-topic"></a><span data-ttu-id="b6a9e-107">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="b6a9e-107">In this topic</span></span>  
 <span data-ttu-id="b6a9e-108">На этом этапе учебника действия `WriteLine` в рабочем процессе изменены для предоставления дополнительных сведений и добавлено новое действие `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-108">In this step of the tutorial, the `WriteLine` activities in the workflow are modified to provide additional information, and a new `WriteLine` activity is added.</span></span> <span data-ttu-id="b6a9e-109">Копия исходной сборки рабочего процесса сохранена, а ведущее приложение обновлено для возможности одновременного выполнения исходных и обновленных рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-109">A copy of the original workflow assembly is stored, and the host application is updated so that it can run both the original and the updated workflows at the same time.</span></span>  
  
-   [<span data-ttu-id="b6a9e-110">Создание копии проекта NumberGuessWorkflowActivities</span><span class="sxs-lookup"><span data-stu-id="b6a9e-110">To make a copy of the NumberGuessWorkflowActivities project</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BackupCopy)  
  
-   [<span data-ttu-id="b6a9e-111">Обновление рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="b6a9e-111">To update the workflows</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflows)  
  
    -   [<span data-ttu-id="b6a9e-112">Обновление рабочего процесса StateMachine</span><span class="sxs-lookup"><span data-stu-id="b6a9e-112">To update the StateMachine workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateStateMachine)  
  
    -   [<span data-ttu-id="b6a9e-113">Обновление рабочего процесса блок-схемы</span><span class="sxs-lookup"><span data-stu-id="b6a9e-113">To update the Flowchart workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateFlowchart)  
  
    -   [<span data-ttu-id="b6a9e-114">Обновление последовательного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="b6a9e-114">To update the Sequential workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateSequential)  
  
-   [<span data-ttu-id="b6a9e-115">Обновление WorkflowVersionMap для включения предыдущие версии рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="b6a9e-115">To update WorkflowVersionMap to include the previous workflow versions</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflowVersionMap)  
  
-   [<span data-ttu-id="b6a9e-116">Построение и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="b6a9e-116">To build and run the application</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BuildAndRun)  
  
> [!NOTE]
>  <span data-ttu-id="b6a9e-117">Перед выполнением действий, описанных в этом разделе, выполните приложение, запустите несколько рабочих процессов каждого типа и укажите одно или два предположения для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-117">Before following the steps in this topic, run the application, start several workflows of each type, and making one or two guesses for each one.</span></span> <span data-ttu-id="b6a9e-118">Эти сохраненных рабочих процессов используются в этом шаге и следующий шаг [как: обновление определения экземпляра рабочего процесса запущен](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span><span class="sxs-lookup"><span data-stu-id="b6a9e-118">These persisted workflows are used in this step and the following step, [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6a9e-119">Каждый шаг в учебнике «Приступая к работе» построен на основе предыдущих шагов.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-119">Each step in the Getting Started tutorial depends on the previous steps.</span></span> <span data-ttu-id="b6a9e-120">Если вы не завершили предыдущие шаги можно загрузить полную версию учебника из [Windows Workflow Foundation (WF45) — учебник по началу работы](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="b6a9e-120">If you did not complete the previous steps you can download a completed version of the tutorial from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
###  <span data-ttu-id="b6a9e-121"><a name="BKMK_BackupCopy"></a>Создание копии проекта NumberGuessWorkflowActivities</span><span class="sxs-lookup"><span data-stu-id="b6a9e-121"><a name="BKMK_BackupCopy"></a> To make a copy of the NumberGuessWorkflowActivities project</span></span>  
  
1.  <span data-ttu-id="b6a9e-122">Откройте **WF45GettingStartedTutorial** решения в [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] , если она еще не открыта.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-122">Open the **WF45GettingStartedTutorial** solution in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] if it is not open.</span></span>  
  
2.  <span data-ttu-id="b6a9e-123">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-123">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="b6a9e-124">Закрыть **WF45GettingStartedTutorial** решения.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-124">Close the **WF45GettingStartedTutorial** solution.</span></span>  
  
4.  <span data-ttu-id="b6a9e-125">Откройте проводник Windows и перейдите в папку, где находятся файл решения и папки проекта.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-125">Open Windows Explorer and navigate to the folder where the tutorial solution file and the project folders are located.</span></span>  
  
5.  <span data-ttu-id="b6a9e-126">Создайте новую папку с именем **PreviousVersions** в той же папке, что **NumberGuessWorkflowHost** и **NumberGuessWorkflowActivities**.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-126">Create a new folder named **PreviousVersions** in the same folder as **NumberGuessWorkflowHost** and **NumberGuessWorkflowActivities**.</span></span> <span data-ttu-id="b6a9e-127">Эта папка служит для хранения сборок, содержащих различные версии рабочих процессов, которые используются на последующих шагах учебника.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-127">This folder is used to contain the assemblies that contain the different versions of the workflows used in the subsequent tutorial steps.</span></span>  
  
6.  <span data-ttu-id="b6a9e-128">Перейдите к **NumberGuessWorkflowActivities\bin\debug** папку (или **bin\release** в зависимости от параметров проекта).</span><span class="sxs-lookup"><span data-stu-id="b6a9e-128">Navigate to the **NumberGuessWorkflowActivities\bin\debug** folder (or **bin\release** depending on your project settings).</span></span> <span data-ttu-id="b6a9e-129">Копировать **NumberGuessWorkflowActivities.dll** и вставьте его в **PreviousVersions** папки.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-129">Copy **NumberGuessWorkflowActivities.dll** and paste it into the **PreviousVersions** folder.</span></span>  
  
7.  <span data-ttu-id="b6a9e-130">Переименуйте **NumberGuessWorkflowActivities.dll** в **PreviousVersions** папки **NumberGuessWorkflowActivities_v1.dll**.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-130">Rename **NumberGuessWorkflowActivities.dll** in the **PreviousVersions** folder to **NumberGuessWorkflowActivities_v1.dll**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b6a9e-131">Шаги в этом разделе демонстрируют один способ управления сборками, которые используются для хранения нескольких версий рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-131">The steps in this topic demonstrate one way to manage the assemblies used to contain multiple versions of the workflows.</span></span> <span data-ttu-id="b6a9e-132">Также можно использовать другие методы, такие как строгое наименование сборок и их регистрация в глобальном кэше сборок (GAC).</span><span class="sxs-lookup"><span data-stu-id="b6a9e-132">Other methods such as strong naming the assemblies and registering them in the global assembly cache could also be used.</span></span>  
  
8.  <span data-ttu-id="b6a9e-133">Создайте новую папку с именем **NumberGuessWorkflowActivities_du** в той же папке, что **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**и вновь добавлен **PreviousVersions** папке и скопируйте все файлы и вложенные папки из **NumberGuessWorkflowActivities** в новую  **NumberGuessWorkflowActivities_du** папки.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-133">Create a new folder named **NumberGuessWorkflowActivities_du** in the same folder as **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**, and the newly added **PreviousVersions** folder, and copy all of the files and subfolders from the **NumberGuessWorkflowActivities** folder into the new **NumberGuessWorkflowActivities_du** folder.</span></span> <span data-ttu-id="b6a9e-134">Такая копия проекта для первоначальной версии действий используется в [как: обновление определения экземпляра рабочего процесса запущен](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span><span class="sxs-lookup"><span data-stu-id="b6a9e-134">This backup copy of the project for the initial version of the activities is used in [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>  
  
9. <span data-ttu-id="b6a9e-135">Снова откройте **WF45GettingStartedTutorial** решения в [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6a9e-135">Re-open the **WF45GettingStartedTutorial** solution in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span>  
  
###  <span data-ttu-id="b6a9e-136"><a name="BKMK_UpdateWorkflows"></a>Обновление рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="b6a9e-136"><a name="BKMK_UpdateWorkflows"></a> To update the workflows</span></span>  
 <span data-ttu-id="b6a9e-137">В этом разделе обновлены определения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-137">In this section, the workflow definitions are updated.</span></span> <span data-ttu-id="b6a9e-138">Обновлены два действия `WriteLine`, которые получают отзывы на пробное значение пользователя, и добавлено новое действие `WriteLine`, которое предоставляет дополнительные сведения об игре, как только будет угадано число.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-138">The two `WriteLine` activities that give feedback on the user's guess are updated, and a new `WriteLine` activity is added that provides additional information about the game once the number is guessed.</span></span>  
  
####  <span data-ttu-id="b6a9e-139"><a name="BKMK_UpdateStateMachine"></a>Обновление рабочего процесса StateMachine</span><span class="sxs-lookup"><span data-stu-id="b6a9e-139"><a name="BKMK_UpdateStateMachine"></a> To update the StateMachine workflow</span></span>  
  
1.  <span data-ttu-id="b6a9e-140">В **обозревателе решений**в разделе **NumberGuessWorkflowActivities** проекта, дважды щелкните **StateMachineNumberGuessWorkflow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-140">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **StateMachineNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="b6a9e-141">Дважды щелкните **неверное пробное** переход конечного автомата.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-141">Double-click the **Guess Incorrect** transition on the state machine.</span></span>  
  
3.  <span data-ttu-id="b6a9e-142">Обновите `Text` крайнего левого `WriteLine` в действии `If`.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-142">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
4.  <span data-ttu-id="b6a9e-143">Обновите `Text` крайнего правого `WriteLine` в действии `If`.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-143">Update the `Text` of the right-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
5.  <span data-ttu-id="b6a9e-144">Возврат к общему состояния машины представление в конструкторе рабочих процессов, щелкнув **StateMachine** на экране навигатора отображать в верхней части конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-144">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
6.  <span data-ttu-id="b6a9e-145">Дважды щелкните **правильное пробное** переход конечного автомата.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-145">Double-click the **Guess Correct** transition on the state machine.</span></span>  
  
7.  <span data-ttu-id="b6a9e-146">Перетащите **WriteLine** действия из **примитивы** раздел **элементов** и поместите его на **Перетащите сюда действие Action** метку Переход.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-146">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the **Drop Action activity here** label of the transition.</span></span>  
  
8.  <span data-ttu-id="b6a9e-147">В поле свойств `Text` введите следующее выражение.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-147">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
####  <span data-ttu-id="b6a9e-148"><a name="BKMK_UpdateFlowchart"></a>Обновление рабочего процесса блок-схемы</span><span class="sxs-lookup"><span data-stu-id="b6a9e-148"><a name="BKMK_UpdateFlowchart"></a> To update the Flowchart workflow</span></span>  
  
1.  <span data-ttu-id="b6a9e-149">В **обозревателе решений**в разделе **NumberGuessWorkflowActivities** проекта, дважды щелкните **FlowchartNumberGuessWorkflow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-149">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **FlowchartNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="b6a9e-150">Обновите `Text` крайнего левого действия `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-150">Update the `Text` of the left-most `WriteLine` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
3.  <span data-ttu-id="b6a9e-151">Обновите `Text` крайнего правого действия `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-151">Update the `Text` of the right-most `WriteLine` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
4.  <span data-ttu-id="b6a9e-152">Перетащите **WriteLine** действия из **примитивы** раздел **элементов** и поместите его на точку удаления действия `True` самого верхнего `FlowDecision` .</span><span class="sxs-lookup"><span data-stu-id="b6a9e-152">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the drop point of the `True` action of the topmost `FlowDecision`.</span></span> <span data-ttu-id="b6a9e-153">Действие `WriteLine` добавляется к блок-схеме и связывается с действием `True` `FlowDecision`.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-153">The `WriteLine` activity is added to the flowchart and linked to the `True` action of the `FlowDecision`.</span></span>  
  
5.  <span data-ttu-id="b6a9e-154">В поле свойств `Text` введите следующее выражение.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-154">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
####  <span data-ttu-id="b6a9e-155"><a name="BKMK_UpdateSequential"></a>Обновление последовательного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="b6a9e-155"><a name="BKMK_UpdateSequential"></a> To update the Sequential workflow</span></span>  
  
1.  <span data-ttu-id="b6a9e-156">В **обозревателе решений**в разделе **NumberGuessWorkflowActivities** проекта, дважды щелкните **SequentialNumberGuessWorkflow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-156">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **SequentialNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="b6a9e-157">Обновите `Text` крайнего левого `WriteLine` в действии `If`.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-157">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
3.  <span data-ttu-id="b6a9e-158">Обновите `Text` крайнего правого действия `WriteLine` в действии `If`.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-158">Update the `Text` of the right-most `WriteLine` activity in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
4.  <span data-ttu-id="b6a9e-159">Перетащите **WriteLine** действия из **примитивы** раздел **элементов** и поместите его после **DoWhile** действия, чтобы  **WriteLine** оказался последним действием в корневом `Sequence` действия.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-159">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it after the **DoWhile** activity so that the **WriteLine** is the final activity in the root `Sequence` activity.</span></span>  
  
5.  <span data-ttu-id="b6a9e-160">В поле свойств `Text` введите следующее выражение.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-160">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
###  <span data-ttu-id="b6a9e-161"><a name="BKMK_UpdateWorkflowVersionMap"></a>Обновление WorkflowVersionMap для включения предыдущие версии рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="b6a9e-161"><a name="BKMK_UpdateWorkflowVersionMap"></a> To update WorkflowVersionMap to include the previous workflow versions</span></span>  
  
1.  <span data-ttu-id="b6a9e-162">Дважды щелкните **WorkflowVersionMap.cs** (или **WorkflowVersionMap.vb**) в разделе **NumberGuessWorkflowHost** проект, чтобы открыть его.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-162">Double-click **WorkflowVersionMap.cs** (or **WorkflowVersionMap.vb**) under the **NumberGuessWorkflowHost** project to open it.</span></span>  
  
2.  <span data-ttu-id="b6a9e-163">Добавьте следующие инструкции `using` (или `Imports`) в начало файла с другими инструкциями `using` (или `Imports`).</span><span class="sxs-lookup"><span data-stu-id="b6a9e-163">Add the following `using` (or `Imports`) statements to the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Reflection  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Reflection;  
    using System.IO;  
    ```  
  
3.  <span data-ttu-id="b6a9e-164">Добавьте три новых идентификатора рабочих процессов непосредственно под тремя существующими объявлениями идентификаторов рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-164">Add three new workflow identities just below the three existing workflow identity declarations.</span></span> <span data-ttu-id="b6a9e-165">Эти новые идентификаторы рабочих процессов `v1` будут использоваться для получения правильных определений рабочих процессов перед выполнением обновлений.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-165">These new `v1` workflow identities will be used provide the correct workflow definition to workflows started before the updates were made.</span></span>  
  
    ```vb  
    'Current version identities.  
    Public StateMachineNumberGuessIdentity As WorkflowIdentity  
    Public FlowchartNumberGuessIdentity As WorkflowIdentity  
    Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
    'v1 Identities.  
    Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity  
    Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity  
    Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity  
    ```  
  
    ```csharp  
    // Current version identities.  
    static public WorkflowIdentity StateMachineNumberGuessIdentity;  
    static public WorkflowIdentity FlowchartNumberGuessIdentity;  
    static public WorkflowIdentity SequentialNumberGuessIdentity;  
  
    // v1 identities.  
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;  
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;  
    static public WorkflowIdentity SequentialNumberGuessIdentity_v1;  
    ```  
  
4.  <span data-ttu-id="b6a9e-166">В конструкторе `WorkflowVersionMap` обновите свойство `Version` трех текущих идентификаторов рабочих процессов до `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-166">In the `WorkflowVersionMap` constructor, update the `Version` property of the three current workflow identities to `2.0.0.0`.</span></span>  
  
    ```vb  
    'Add the current workflow version identities.  
    StateMachineNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "StateMachineNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    FlowchartNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "FlowchartNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    SequentialNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "SequentialNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
    map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
    map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
    ```  
  
    ```csharp  
    // Add the current workflow version identities.  
    StateMachineNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "StateMachineNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    FlowchartNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "FlowchartNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    SequentialNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "SequentialNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
    map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
    map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
    ```  
  
     <span data-ttu-id="b6a9e-167">Код, который добавляет текущие версии рабочих процессов в словарь, использует текущие версии, которые указаны в проекте, чтобы код, который инициализирует определения рабочего процесса, не нужно было обновлять.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-167">The code in that adds the current versions of the workflows to the dictionary uses the current versions that are referenced in the project, so the code that initializes the workflow definitions does not need to be updated.</span></span>  
  
5.  <span data-ttu-id="b6a9e-168">Добавьте следующий код в конструктор сразу после кода, добавляющего текущие версии в словарь.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-168">Add the following code in the constructor just after the code that adds the current versions to the dictionary.</span></span>  
  
    ```vb  
    'Initialize the previous workflow version identities.  
    StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "StateMachineNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
  
    FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "FlowchartNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
  
    SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "SequentialNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
    ```  
  
    ```csharp  
    // Initialize the previous workflow version identities.  
    StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "StateMachineNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
  
    FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "FlowchartNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
  
    SequentialNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "SequentialNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
    ```  
  
     <span data-ttu-id="b6a9e-169">Эти удостоверения рабочих процессов связаны с первоначальными версиями соответствующих определений рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-169">These workflow identities are associated with the initial versions of the corresponding workflow definitions.</span></span>  
  
6.  <span data-ttu-id="b6a9e-170">Затем загрузите сборку, которая содержит первоначальную версию определений рабочих процессов, создайте соответствующие определения рабочих процессов и добавьте их в словарь.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-170">Next, load the assembly that contains the initial version of the workflow definitions, and create and add the corresponding workflow definitions to the dictionary.</span></span>  
  
    ```vb  
    'Add the previous version workflow identities to the dictionary along with  
    'the corresponding workflow definitions loaded from the v1 assembly.  
    'Assembly.LoadFile requires an absolute path so convert this relative path  
    'to an absolute path.  
    Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"  
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)  
    Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)  
  
    map.Add(StateMachineNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))  
  
    map.Add(SequentialNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))  
  
    map.Add(FlowchartNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))  
    ```  
  
    ```csharp  
    // Add the previous version workflow identities to the dictionary along with  
    // the corresponding workflow definitions loaded from the v1 assembly.  
    // Assembly.LoadFile requires an absolute path so convert this relative path  
    // to an absolute path.  
    string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";  
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);  
    Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);  
  
    map.Add(StateMachineNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);  
  
    map.Add(SequentialNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);  
  
    map.Add(FlowchartNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);  
    ```  
  
     <span data-ttu-id="b6a9e-171">Ниже приведен полный список для обновленного класса `WorkflowVersionMap`.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-171">The following example is the complete listing for the updated `WorkflowVersionMap` class.</span></span>  
  
    ```vb  
    Public Module WorkflowVersionMap  
        Dim map As Dictionary(Of WorkflowIdentity, Activity)  
  
        'Current version identities.  
        Public StateMachineNumberGuessIdentity As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity As WorkflowIdentity  
        Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
        'v1 Identities.  
        Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity  
        Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity  
  
        Sub New()  
            map = New Dictionary(Of WorkflowIdentity, Activity)  
  
            'Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
  
            'Initialize the previous workflow version identities.  
            StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            'Add the previous version workflow identities to the dictionary along with  
            'the corresponding workflow definitions loaded from the v1 assembly.  
            'Assembly.LoadFile requires an absolute path so convert this relative path  
            'to an absolute path.  
            Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"  
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)  
            Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)  
  
            map.Add(StateMachineNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))  
  
            map.Add(SequentialNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))  
  
            map.Add(FlowchartNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))  
        End Sub  
  
        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity  
            Return map(identity)  
        End Function  
  
        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String  
            Return identity.ToString()  
        End Function  
    End Module  
    ```  
  
    ```csharp  
    public static class WorkflowVersionMap  
    {  
        static Dictionary<WorkflowIdentity, Activity> map;  
  
        // Current version identities.  
        static public WorkflowIdentity StateMachineNumberGuessIdentity;  
        static public WorkflowIdentity FlowchartNumberGuessIdentity;  
        static public WorkflowIdentity SequentialNumberGuessIdentity;  
  
        // v1 identities.  
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;  
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;  
        static public WorkflowIdentity SequentialNumberGuessIdentity_v1;  
  
        static WorkflowVersionMap()  
        {  
            map = new Dictionary<WorkflowIdentity, Activity>();  
  
            // Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
  
            // Initialize the previous workflow version identities.  
            StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            // Add the previous version workflow identities to the dictionary along with  
            // the corresponding workflow definitions loaded from the v1 assembly.  
            // Assembly.LoadFile requires an absolute path so convert this relative path  
            // to an absolute path.  
            string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";  
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);  
            Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);  
  
            map.Add(StateMachineNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);  
  
            map.Add(SequentialNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);  
  
            map.Add(FlowchartNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);  
        }  
  
        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)  
        {  
            return map[identity];  
        }  
  
        public static string GetIdentityDescription(WorkflowIdentity identity)  
        {  
            return identity.ToString();  
        }  
    }  
    ```  
  
###  <span data-ttu-id="b6a9e-172"><a name="BKMK_BuildAndRun"></a>Построение и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="b6a9e-172"><a name="BKMK_BuildAndRun"></a> To build and run the application</span></span>  
  
1.  <span data-ttu-id="b6a9e-173">Нажмите сочетание клавиш CTRL+SHIFT+B, чтобы построить приложение, а затем сочетание клавиш CTRL+F5 для его запуска.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-173">Press CTRL+SHIFT+B to build the application, and then CTRL+F5 to start.</span></span>  
  
2.  <span data-ttu-id="b6a9e-174">Запустить новый рабочий процесс, нажав кнопку **новая игра**.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-174">Start a new workflow by clicking **New Game**.</span></span> <span data-ttu-id="b6a9e-175">Версия рабочего процесса отображается под окном состояния и отображает обновленную версию из связанного `WorkflowIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-175">The version of the workflow is displayed under the status window and reflects the updated version from the associated `WorkflowIdentity`.</span></span> <span data-ttu-id="b6a9e-176">Запишите `InstanceId`, чтобы просмотреть файл отслеживания для рабочего процесса после его завершения, а затем вводите предположения, пока игра не завершится.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-176">Make a note of the `InstanceId` so you can view the tracking file for the workflow when it completes, and then enter guesses until the game is complete.</span></span> <span data-ttu-id="b6a9e-177">Обратите внимание на то, что догадка пользователя отображается в окне состояния в зависимости от обновлений действий `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-177">Note how the user's guess is displayed in the information displayed in the status window based on the updates to the `WriteLine` activities.</span></span>  
  
 <span data-ttu-id="b6a9e-178">**Введите число от 1 до 10**</span><span class="sxs-lookup"><span data-stu-id="b6a9e-178">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="b6a9e-179">**5-слишком много.** </span><span class="sxs-lookup"><span data-stu-id="b6a9e-179">**5 is too high.** </span></span>  
<span data-ttu-id="b6a9e-180">**Введите число от 1 до 10** </span><span class="sxs-lookup"><span data-stu-id="b6a9e-180">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="b6a9e-181">**3-слишком много.** </span><span class="sxs-lookup"><span data-stu-id="b6a9e-181">**3 is too high.** </span></span>  
<span data-ttu-id="b6a9e-182">**Введите число от 1 до 10** </span><span class="sxs-lookup"><span data-stu-id="b6a9e-182">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="b6a9e-183">**1-слишком мало.** </span><span class="sxs-lookup"><span data-stu-id="b6a9e-183">**1 is too low.** </span></span>  
<span data-ttu-id="b6a9e-184">**Введите число от 1 до 10** </span><span class="sxs-lookup"><span data-stu-id="b6a9e-184">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="b6a9e-185">**Поздравляем, Вы угадали число за 4 попытки.**</span><span class="sxs-lookup"><span data-stu-id="b6a9e-185">**Congratulations, you guessed the number in 4 turns.**</span></span>    
    > [!NOTE]
    >  <span data-ttu-id="b6a9e-186">Отображается обновленный текст из действий `WriteLine`, но выходные данные последнего действия `WriteLine`, которое было добавлено в этом разделе, отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-186">The updated text from the `WriteLine` activities is displayed, but the output of the final `WriteLine` activity that was added in this topic is not.</span></span> <span data-ttu-id="b6a9e-187">Это происходит потому, что окно состояния обновляется обработчиком `PersistableIdle`.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-187">That is because the status window is updated by the `PersistableIdle` handler.</span></span> <span data-ttu-id="b6a9e-188">Поскольку рабочий процесс завершается, а не переходит в состояние бездействия после окончательного действия, обработчик `PersistableIdle` не вызывается.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-188">Because the workflow completes and does not go idle after the final activity, the `PersistableIdle` handler is not called.</span></span> <span data-ttu-id="b6a9e-189">Однако похожее сообщение отображается обработчиком `Completed` в окне состояния.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-189">However, a similar message is displayed in the status window by the `Completed` handler.</span></span> <span data-ttu-id="b6a9e-190">Если необходимо, код можно добавить в обработчик `Completed`, чтобы извлечь текст из `StringWriter` и показать его в окне состояния.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-190">If desired, code could be added to the `Completed` handler to extract the text from the `StringWriter` and display it to the status window.</span></span>  
  
3.  <span data-ttu-id="b6a9e-191">Откройте проводник и перейдите к **NumberGuessWorkflowHost\bin\debug** папку (или **bin\release** в зависимости от параметров проекта) и откройте в блокноте, соответствующий файл отслеживания для завершенного рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-191">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings) and open the tracking file using Notepad that corresponds to the completed workflow.</span></span> <span data-ttu-id="b6a9e-192">Если вы не вносили или запишите `InstanceId`, можно определить правильный файл отслеживания с помощью **Дата изменения** сведения в проводнике Windows.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-192">If you did not make a note of the `InstanceId`, you can identify the correct tracking file by using the **Date modified** information in Windows Explorer.</span></span>  
  
 <span data-ttu-id="b6a9e-193">**Введите число от 1 до 10**</span><span class="sxs-lookup"><span data-stu-id="b6a9e-193">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="b6a9e-194">**5-слишком много.** </span><span class="sxs-lookup"><span data-stu-id="b6a9e-194">**5 is too high.** </span></span>  
<span data-ttu-id="b6a9e-195">**Введите число от 1 до 10** </span><span class="sxs-lookup"><span data-stu-id="b6a9e-195">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="b6a9e-196">**3-слишком много.** </span><span class="sxs-lookup"><span data-stu-id="b6a9e-196">**3 is too high.** </span></span>  
<span data-ttu-id="b6a9e-197">**Введите число от 1 до 10** </span><span class="sxs-lookup"><span data-stu-id="b6a9e-197">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="b6a9e-198">**1-слишком мало.** </span><span class="sxs-lookup"><span data-stu-id="b6a9e-198">**1 is too low.** </span></span>  
<span data-ttu-id="b6a9e-199">**Введите число от 1 до 10** </span><span class="sxs-lookup"><span data-stu-id="b6a9e-199">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="b6a9e-200">**2-правильное число. Вы угадали число за 4 попытки.**</span><span class="sxs-lookup"><span data-stu-id="b6a9e-200">**2 is correct. You guessed it in 4 turns.**</span></span>      <span data-ttu-id="b6a9e-201">Обновленные выходные данные `WriteLine` содержатся в файле отслеживания, в том числе выходные данные трассировки действия `WriteLine`, добавленного в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-201">The updated `WriteLine` output is contained within the tracking file, including the output of the `WriteLine` that was added in this topic.</span></span>  
  
4.  <span data-ttu-id="b6a9e-202">Перейдите к приложению отгадывания чисел и выберите один из рабочих процессов, который был запущен до выполнения обновлений.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-202">Switch back to the number guessing application and select one of the workflows that was started before the updates were made.</span></span> <span data-ttu-id="b6a9e-203">Вы можете указать версию выбранного в данный момент рабочего процесса, посмотрев сведения о версии, отображаемые под окном состояния.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-203">You can identify the version of the currently selected workflow by looking at the version information that is displayed below the status window.</span></span> <span data-ttu-id="b6a9e-204">Введите несколько предположений и обратите внимание на то, что некоторые обновления состояния соответствуют выходным данным действия `WriteLine` из предыдущей версии, но не включают предположение пользователя.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-204">Enter some guesses and note that the status updates match the `WriteLine` activity output from the previous version, and do not include the user's guess.</span></span> <span data-ttu-id="b6a9e-205">Это происходит потому, что такие рабочие процессы используют предыдущее определение рабочего процесса, в котором не выполнены обновления `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-205">That is because these workflows are using the previous workflow definition that does not have the `WriteLine` updates.</span></span>  
  
     <span data-ttu-id="b6a9e-206">На следующем шаге [как: обновление определения экземпляра рабочего процесса запущен](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md), выполнение `v1` экземпляры рабочего процесса обновляются, поэтому они содержат новые функциональные возможности, что `v2` экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b6a9e-206">In the next step, [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md), the running `v1` workflow instances are updated so they contain the new functionality as the `v2` instances.</span></span>
