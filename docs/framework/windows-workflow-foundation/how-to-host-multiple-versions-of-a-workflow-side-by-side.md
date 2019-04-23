---
title: Практическое руководство. Параллельное размещение множества версий рабочего процесса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09c575df-e0a3-4f3b-9e01-a7ac59d65287
ms.openlocfilehash: 4fc4565db58d008f52bc047d26118fc849648770
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59329457"
---
# <a name="how-to-host-multiple-versions-of-a-workflow-side-by-side"></a><span data-ttu-id="6292d-102">Практическое руководство. Параллельное размещение множества версий рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="6292d-102">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>
<span data-ttu-id="6292d-103">`WorkflowIdentity` предоставляет разработчикам приложений рабочих процессов способ связать имя и версию с определением рабочего процесса, а также связать эти сведения с сохраненным экземпляром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="6292d-103">`WorkflowIdentity` provides a way for workflow application developers to associate a name and a version with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="6292d-104">Эти идентификационные данные могут быть использованы разработчиками приложений рабочего процесса для поддержки таких сценариев, как параллельное выполнение нескольких версий определения рабочего процесса, и являются ключевым элементом для других функциональных возможностей, таких как динамическое обновление.</span><span class="sxs-lookup"><span data-stu-id="6292d-104">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="6292d-105">Этот шаг в учебнике показывает, как использовать `WorkflowIdentity` для размещения нескольких версий рабочих процессов одновременно.</span><span class="sxs-lookup"><span data-stu-id="6292d-105">This step in the tutorial demonstrates how to use `WorkflowIdentity` to host multiple versions of a workflow at the same time.</span></span>

> [!NOTE]
>  <span data-ttu-id="6292d-106">Чтобы скачать полную версию или просмотреть пошаговое видео учебника, см. в разделе [Windows Workflow Foundation (WF45) - Приступая к работе](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="6292d-106">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-topic"></a><span data-ttu-id="6292d-107">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="6292d-107">In this topic</span></span>  
 <span data-ttu-id="6292d-108">На этом этапе учебника действия `WriteLine` в рабочем процессе изменены для предоставления дополнительных сведений и добавлено новое действие `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="6292d-108">In this step of the tutorial, the `WriteLine` activities in the workflow are modified to provide additional information, and a new `WriteLine` activity is added.</span></span> <span data-ttu-id="6292d-109">Копия исходной сборки рабочего процесса сохранена, а ведущее приложение обновлено для возможности одновременного выполнения исходных и обновленных рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="6292d-109">A copy of the original workflow assembly is stored, and the host application is updated so that it can run both the original and the updated workflows at the same time.</span></span>  
  
-   [<span data-ttu-id="6292d-110">Для создания копии проекта NumberGuessWorkflowActivities</span><span class="sxs-lookup"><span data-stu-id="6292d-110">To make a copy of the NumberGuessWorkflowActivities project</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BackupCopy)  
  
-   [<span data-ttu-id="6292d-111">Обновление рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="6292d-111">To update the workflows</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflows)  
  
    -   [<span data-ttu-id="6292d-112">Обновление рабочего процесса конечного автомата</span><span class="sxs-lookup"><span data-stu-id="6292d-112">To update the StateMachine workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateStateMachine)  
  
    -   [<span data-ttu-id="6292d-113">Обновление рабочего процесса блок-схема</span><span class="sxs-lookup"><span data-stu-id="6292d-113">To update the Flowchart workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateFlowchart)  
  
    -   [<span data-ttu-id="6292d-114">Обновление последовательного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="6292d-114">To update the Sequential workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateSequential)  
  
-   [<span data-ttu-id="6292d-115">Обновление WorkflowVersionMap для включения предыдущих версий рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="6292d-115">To update WorkflowVersionMap to include the previous workflow versions</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflowVersionMap)  
  
-   [<span data-ttu-id="6292d-116">Построение и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="6292d-116">To build and run the application</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BuildAndRun)  
  
> [!NOTE]
>  <span data-ttu-id="6292d-117">Перед выполнением действий, описанных в этом разделе, выполните приложение, запустите несколько рабочих процессов каждого типа и укажите одно или два предположения для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="6292d-117">Before following the steps in this topic, run the application, start several workflows of each type, and making one or two guesses for each one.</span></span> <span data-ttu-id="6292d-118">Сохраненные рабочие процессы используются в этом шаге и приведенную ниже [как: Обновить определение выполняющегося экземпляра рабочего процесса](how-to-update-the-definition-of-a-running-workflow-instance.md).</span><span class="sxs-lookup"><span data-stu-id="6292d-118">These persisted workflows are used in this step and the following step, [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="6292d-119">Каждый шаг в учебнике «Приступая к работе» построен на основе предыдущих шагов.</span><span class="sxs-lookup"><span data-stu-id="6292d-119">Each step in the Getting Started tutorial depends on the previous steps.</span></span> <span data-ttu-id="6292d-120">Если вы не прошли предыдущих шагов можно загрузить завершенную версию учебника [Windows Workflow Foundation (WF45) - Приступая к работе](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="6292d-120">If you did not complete the previous steps you can download a completed version of the tutorial from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="BKMK_BackupCopy"></a> <span data-ttu-id="6292d-121">Для создания копии проекта NumberGuessWorkflowActivities</span><span class="sxs-lookup"><span data-stu-id="6292d-121">To make a copy of the NumberGuessWorkflowActivities project</span></span>  
  
1. <span data-ttu-id="6292d-122">Откройте **WF45GettingStartedTutorial** решение в Visual Studio 2012, если оно еще не открыто.</span><span class="sxs-lookup"><span data-stu-id="6292d-122">Open the **WF45GettingStartedTutorial** solution in Visual Studio 2012 if it is not open.</span></span>  
  
2. <span data-ttu-id="6292d-123">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="6292d-123">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3. <span data-ttu-id="6292d-124">Закрыть **WF45GettingStartedTutorial** решения.</span><span class="sxs-lookup"><span data-stu-id="6292d-124">Close the **WF45GettingStartedTutorial** solution.</span></span>  
  
4. <span data-ttu-id="6292d-125">Откройте проводник Windows и перейдите в папку, где находятся файл решения и папки проекта.</span><span class="sxs-lookup"><span data-stu-id="6292d-125">Open Windows Explorer and navigate to the folder where the tutorial solution file and the project folders are located.</span></span>  
  
5. <span data-ttu-id="6292d-126">Создайте новую папку с именем **PreviousVersions** в той же папке, что **NumberGuessWorkflowHost** и **NumberGuessWorkflowActivities**.</span><span class="sxs-lookup"><span data-stu-id="6292d-126">Create a new folder named **PreviousVersions** in the same folder as **NumberGuessWorkflowHost** and **NumberGuessWorkflowActivities**.</span></span> <span data-ttu-id="6292d-127">Эта папка служит для хранения сборок, содержащих различные версии рабочих процессов, которые используются на последующих шагах учебника.</span><span class="sxs-lookup"><span data-stu-id="6292d-127">This folder is used to contain the assemblies that contain the different versions of the workflows used in the subsequent tutorial steps.</span></span>  
  
6. <span data-ttu-id="6292d-128">Перейдите к **NumberGuessWorkflowActivities\bin\debug** папку (или **bin\release** в зависимости от параметров проекта).</span><span class="sxs-lookup"><span data-stu-id="6292d-128">Navigate to the **NumberGuessWorkflowActivities\bin\debug** folder (or **bin\release** depending on your project settings).</span></span> <span data-ttu-id="6292d-129">Копировать **NumberGuessWorkflowActivities.dll** и вставьте его в **PreviousVersions** папки.</span><span class="sxs-lookup"><span data-stu-id="6292d-129">Copy **NumberGuessWorkflowActivities.dll** and paste it into the **PreviousVersions** folder.</span></span>  
  
7. <span data-ttu-id="6292d-130">Переименуйте **NumberGuessWorkflowActivities.dll** в **PreviousVersions** папку **NumberGuessWorkflowActivities_v1.dll**.</span><span class="sxs-lookup"><span data-stu-id="6292d-130">Rename **NumberGuessWorkflowActivities.dll** in the **PreviousVersions** folder to **NumberGuessWorkflowActivities_v1.dll**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6292d-131">Шаги в этом разделе демонстрируют один способ управления сборками, которые используются для хранения нескольких версий рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="6292d-131">The steps in this topic demonstrate one way to manage the assemblies used to contain multiple versions of the workflows.</span></span> <span data-ttu-id="6292d-132">Также можно использовать другие методы, такие как строгое наименование сборок и их регистрация в глобальном кэше сборок (GAC).</span><span class="sxs-lookup"><span data-stu-id="6292d-132">Other methods such as strong naming the assemblies and registering them in the global assembly cache could also be used.</span></span>

8. <span data-ttu-id="6292d-133">Создайте новую папку с именем **NumberGuessWorkflowActivities_du** в той же папке, что **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**и их вновь добавлен **PreviousVersions** папке и скопируйте все файлы и вложенные папки из **NumberGuessWorkflowActivities** в новую  **NumberGuessWorkflowActivities_du** папки.</span><span class="sxs-lookup"><span data-stu-id="6292d-133">Create a new folder named **NumberGuessWorkflowActivities_du** in the same folder as **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**, and the newly added **PreviousVersions** folder, and copy all of the files and subfolders from the **NumberGuessWorkflowActivities** folder into the new **NumberGuessWorkflowActivities_du** folder.</span></span> <span data-ttu-id="6292d-134">Эта резервная копия проекта для начальной версии действий используется в [как: Обновить определение выполняющегося экземпляра рабочего процесса](how-to-update-the-definition-of-a-running-workflow-instance.md).</span><span class="sxs-lookup"><span data-stu-id="6292d-134">This backup copy of the project for the initial version of the activities is used in [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>

9. <span data-ttu-id="6292d-135">Снова откройте **WF45GettingStartedTutorial** решение в Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="6292d-135">Re-open the **WF45GettingStartedTutorial** solution in Visual Studio 2012.</span></span>

### <a name="BKMK_UpdateWorkflows"></a> <span data-ttu-id="6292d-136">Обновление рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="6292d-136">To update the workflows</span></span>
 <span data-ttu-id="6292d-137">В этом разделе обновлены определения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="6292d-137">In this section, the workflow definitions are updated.</span></span> <span data-ttu-id="6292d-138">Обновлены два действия `WriteLine`, которые получают отзывы на пробное значение пользователя, и добавлено новое действие `WriteLine`, которое предоставляет дополнительные сведения об игре, как только будет угадано число.</span><span class="sxs-lookup"><span data-stu-id="6292d-138">The two `WriteLine` activities that give feedback on the user's guess are updated, and a new `WriteLine` activity is added that provides additional information about the game once the number is guessed.</span></span>

#### <a name="BKMK_UpdateStateMachine"></a> <span data-ttu-id="6292d-139">Обновление рабочего процесса конечного автомата</span><span class="sxs-lookup"><span data-stu-id="6292d-139">To update the StateMachine workflow</span></span>

1. <span data-ttu-id="6292d-140">В **обозревателе решений**в разделе **NumberGuessWorkflowActivities** проекта, дважды щелкните **StateMachineNumberGuessWorkflow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="6292d-140">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **StateMachineNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="6292d-141">Дважды щелкните **неверное пробное значение** перехода в конечном автомате.</span><span class="sxs-lookup"><span data-stu-id="6292d-141">Double-click the **Guess Incorrect** transition on the state machine.</span></span>

3. <span data-ttu-id="6292d-142">Обновите `Text` крайнего левого `WriteLine` в действии `If`.</span><span class="sxs-lookup"><span data-stu-id="6292d-142">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

4. <span data-ttu-id="6292d-143">Обновите `Text` крайнего правого `WriteLine` в действии `If`.</span><span class="sxs-lookup"><span data-stu-id="6292d-143">Update the `Text` of the right-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

5. <span data-ttu-id="6292d-144">Возврат к общему машины представление в конструкторе рабочих процессов состояния, нажав кнопку **StateMachine** на экране навигатора в верхней части конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="6292d-144">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>

6. <span data-ttu-id="6292d-145">Дважды щелкните **правильное пробное значение** перехода в конечном автомате.</span><span class="sxs-lookup"><span data-stu-id="6292d-145">Double-click the **Guess Correct** transition on the state machine.</span></span>

7. <span data-ttu-id="6292d-146">Перетащите **WriteLine** действия из **примитивы** раздел **элементов** и поместите его на **Перетащите сюда действие Action** метку Переход.</span><span class="sxs-lookup"><span data-stu-id="6292d-146">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the **Drop Action activity here** label of the transition.</span></span>

8. <span data-ttu-id="6292d-147">В поле свойств `Text` введите следующее выражение.</span><span class="sxs-lookup"><span data-stu-id="6292d-147">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="BKMK_UpdateFlowchart"></a> <span data-ttu-id="6292d-148">Обновление рабочего процесса блок-схема</span><span class="sxs-lookup"><span data-stu-id="6292d-148">To update the Flowchart workflow</span></span>

1. <span data-ttu-id="6292d-149">В **обозревателе решений**в разделе **NumberGuessWorkflowActivities** проекта, дважды щелкните **FlowchartNumberGuessWorkflow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="6292d-149">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **FlowchartNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="6292d-150">Обновите `Text` крайнего левого действия `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="6292d-150">Update the `Text` of the left-most `WriteLine` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3. <span data-ttu-id="6292d-151">Обновите `Text` крайнего правого действия `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="6292d-151">Update the `Text` of the right-most `WriteLine` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4. <span data-ttu-id="6292d-152">Перетащите **WriteLine** действия из **примитивы** раздел **элементов** и разместите его в точку удаления действия `True` самого верхнего `FlowDecision` .</span><span class="sxs-lookup"><span data-stu-id="6292d-152">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the drop point of the `True` action of the topmost `FlowDecision`.</span></span> <span data-ttu-id="6292d-153">Действие `WriteLine` добавляется к блок-схеме и связывается с действием `True``FlowDecision`.</span><span class="sxs-lookup"><span data-stu-id="6292d-153">The `WriteLine` activity is added to the flowchart and linked to the `True` action of the `FlowDecision`.</span></span>

5. <span data-ttu-id="6292d-154">В поле свойств `Text` введите следующее выражение.</span><span class="sxs-lookup"><span data-stu-id="6292d-154">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="BKMK_UpdateSequential"></a> <span data-ttu-id="6292d-155">Обновление последовательного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="6292d-155">To update the Sequential workflow</span></span>

1. <span data-ttu-id="6292d-156">В **обозревателе решений**в разделе **NumberGuessWorkflowActivities** проекта, дважды щелкните **SequentialNumberGuessWorkflow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="6292d-156">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **SequentialNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="6292d-157">Обновите `Text` крайнего левого `WriteLine` в действии `If`.</span><span class="sxs-lookup"><span data-stu-id="6292d-157">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3. <span data-ttu-id="6292d-158">Обновите `Text` крайнего правого действия `WriteLine` в действии `If`.</span><span class="sxs-lookup"><span data-stu-id="6292d-158">Update the `Text` of the right-most `WriteLine` activity in the `If` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4. <span data-ttu-id="6292d-159">Перетащите **WriteLine** действия из **примитивы** раздел **элементов** и поместите его после **DoWhile** действия, чтобы  **WriteLine** оказался последним действием в корневом каталоге `Sequence` действия.</span><span class="sxs-lookup"><span data-stu-id="6292d-159">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it after the **DoWhile** activity so that the **WriteLine** is the final activity in the root `Sequence` activity.</span></span>

5. <span data-ttu-id="6292d-160">В поле свойств `Text` введите следующее выражение.</span><span class="sxs-lookup"><span data-stu-id="6292d-160">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

### <a name="BKMK_UpdateWorkflowVersionMap"></a> <span data-ttu-id="6292d-161">Обновление WorkflowVersionMap для включения предыдущих версий рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="6292d-161">To update WorkflowVersionMap to include the previous workflow versions</span></span>

1. <span data-ttu-id="6292d-162">Дважды щелкните **WorkflowVersionMap.cs** (или **WorkflowVersionMap.vb**) в разделе **NumberGuessWorkflowHost** проекта, чтобы открыть его.</span><span class="sxs-lookup"><span data-stu-id="6292d-162">Double-click **WorkflowVersionMap.cs** (or **WorkflowVersionMap.vb**) under the **NumberGuessWorkflowHost** project to open it.</span></span>

2. <span data-ttu-id="6292d-163">Добавьте следующие инструкции `using` (или `Imports`) в начало файла с другими инструкциями `using` (или `Imports`).</span><span class="sxs-lookup"><span data-stu-id="6292d-163">Add the following `using` (or `Imports`) statements to the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Reflection
    Imports System.IO
    ```

    ```csharp
    using System.Reflection;
    using System.IO;
    ```

3. <span data-ttu-id="6292d-164">Добавьте три новых идентификатора рабочих процессов непосредственно под тремя существующими объявлениями идентификаторов рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="6292d-164">Add three new workflow identities just below the three existing workflow identity declarations.</span></span> <span data-ttu-id="6292d-165">Эти новые идентификаторы рабочих процессов `v1` будут использоваться для получения правильных определений рабочих процессов перед выполнением обновлений.</span><span class="sxs-lookup"><span data-stu-id="6292d-165">These new `v1` workflow identities will be used provide the correct workflow definition to workflows started before the updates were made.</span></span>

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

4. <span data-ttu-id="6292d-166">В конструкторе `WorkflowVersionMap` обновите свойство `Version` трех текущих идентификаторов рабочих процессов до `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="6292d-166">In the `WorkflowVersionMap` constructor, update the `Version` property of the three current workflow identities to `2.0.0.0`.</span></span>

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

     <span data-ttu-id="6292d-167">Код, который добавляет текущие версии рабочих процессов в словарь, использует текущие версии, которые указаны в проекте, чтобы код, который инициализирует определения рабочего процесса, не нужно было обновлять.</span><span class="sxs-lookup"><span data-stu-id="6292d-167">The code in that adds the current versions of the workflows to the dictionary uses the current versions that are referenced in the project, so the code that initializes the workflow definitions does not need to be updated.</span></span>

5. <span data-ttu-id="6292d-168">Добавьте следующий код в конструктор сразу после кода, добавляющего текущие версии в словарь.</span><span class="sxs-lookup"><span data-stu-id="6292d-168">Add the following code in the constructor just after the code that adds the current versions to the dictionary.</span></span>

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

     <span data-ttu-id="6292d-169">Эти удостоверения рабочих процессов связаны с первоначальными версиями соответствующих определений рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="6292d-169">These workflow identities are associated with the initial versions of the corresponding workflow definitions.</span></span>

6. <span data-ttu-id="6292d-170">Затем загрузите сборку, которая содержит первоначальную версию определений рабочих процессов, создайте соответствующие определения рабочих процессов и добавьте их в словарь.</span><span class="sxs-lookup"><span data-stu-id="6292d-170">Next, load the assembly that contains the initial version of the workflow definitions, and create and add the corresponding workflow definitions to the dictionary.</span></span>

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

     <span data-ttu-id="6292d-171">Ниже приведен полный список для обновленного класса `WorkflowVersionMap`.</span><span class="sxs-lookup"><span data-stu-id="6292d-171">The following example is the complete listing for the updated `WorkflowVersionMap` class.</span></span>

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

### <a name="BKMK_BuildAndRun"></a> <span data-ttu-id="6292d-172">Сборка и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="6292d-172">To build and run the application</span></span>

1. <span data-ttu-id="6292d-173">Нажмите сочетание клавиш CTRL+SHIFT+B, чтобы построить приложение, а затем сочетание клавиш CTRL+F5 для его запуска.</span><span class="sxs-lookup"><span data-stu-id="6292d-173">Press CTRL+SHIFT+B to build the application, and then CTRL+F5 to start.</span></span>

2. <span data-ttu-id="6292d-174">Запустить новый рабочий процесс, нажав кнопку **новую игру**.</span><span class="sxs-lookup"><span data-stu-id="6292d-174">Start a new workflow by clicking **New Game**.</span></span> <span data-ttu-id="6292d-175">Версия рабочего процесса отображается под окном состояния и отображает обновленную версию из связанного `WorkflowIdentity`.</span><span class="sxs-lookup"><span data-stu-id="6292d-175">The version of the workflow is displayed under the status window and reflects the updated version from the associated `WorkflowIdentity`.</span></span> <span data-ttu-id="6292d-176">Запишите `InstanceId`, чтобы просмотреть файл отслеживания для рабочего процесса после его завершения, а затем вводите предположения, пока игра не завершится.</span><span class="sxs-lookup"><span data-stu-id="6292d-176">Make a note of the `InstanceId` so you can view the tracking file for the workflow when it completes, and then enter guesses until the game is complete.</span></span> <span data-ttu-id="6292d-177">Обратите внимание на то, что догадка пользователя отображается в окне состояния в зависимости от обновлений действий `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="6292d-177">Note how the user's guess is displayed in the information displayed in the status window based on the updates to the `WriteLine` activities.</span></span>

 <span data-ttu-id="6292d-178">**Введите число от 1 до 10**</span><span class="sxs-lookup"><span data-stu-id="6292d-178">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="6292d-179">**5-слишком много.**</span><span class="sxs-lookup"><span data-stu-id="6292d-179">**5 is too high.**</span></span>  
<span data-ttu-id="6292d-180">**Введите число от 1 до 10**</span><span class="sxs-lookup"><span data-stu-id="6292d-180">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="6292d-181">**3-слишком много.**</span><span class="sxs-lookup"><span data-stu-id="6292d-181">**3 is too high.**</span></span>  
<span data-ttu-id="6292d-182">**Введите число от 1 до 10**</span><span class="sxs-lookup"><span data-stu-id="6292d-182">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="6292d-183">**1-слишком мало.**</span><span class="sxs-lookup"><span data-stu-id="6292d-183">**1 is too low.**</span></span>  
<span data-ttu-id="6292d-184">**Введите число от 1 до 10**</span><span class="sxs-lookup"><span data-stu-id="6292d-184">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="6292d-185">**Поздравляем, Вы угадали число за 4 попытки.**</span><span class="sxs-lookup"><span data-stu-id="6292d-185">**Congratulations, you guessed the number in 4 turns.**</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="6292d-186">Отображается обновленный текст из действий `WriteLine`, но выходные данные последнего действия `WriteLine`, которое было добавлено в этом разделе, отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="6292d-186">The updated text from the `WriteLine` activities is displayed, but the output of the final `WriteLine` activity that was added in this topic is not.</span></span> <span data-ttu-id="6292d-187">Это происходит потому, что окно состояния обновляется обработчиком `PersistableIdle`.</span><span class="sxs-lookup"><span data-stu-id="6292d-187">That is because the status window is updated by the `PersistableIdle` handler.</span></span> <span data-ttu-id="6292d-188">Поскольку рабочий процесс завершается, а не переходит в состояние бездействия после окончательного действия, обработчик `PersistableIdle` не вызывается.</span><span class="sxs-lookup"><span data-stu-id="6292d-188">Because the workflow completes and does not go idle after the final activity, the `PersistableIdle` handler is not called.</span></span> <span data-ttu-id="6292d-189">Однако похожее сообщение отображается обработчиком `Completed` в окне состояния.</span><span class="sxs-lookup"><span data-stu-id="6292d-189">However, a similar message is displayed in the status window by the `Completed` handler.</span></span> <span data-ttu-id="6292d-190">Если необходимо, код можно добавить в обработчик `Completed`, чтобы извлечь текст из `StringWriter` и показать его в окне состояния.</span><span class="sxs-lookup"><span data-stu-id="6292d-190">If desired, code could be added to the `Completed` handler to extract the text from the `StringWriter` and display it to the status window.</span></span>

3. <span data-ttu-id="6292d-191">Откройте проводник Windows и перейдите к **NumberGuessWorkflowHost\bin\debug** папку (или **bin\release** в зависимости от параметров проекта) и откройте файл трассировки с помощью блокнота, соответствующий для завершенного рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="6292d-191">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings) and open the tracking file using Notepad that corresponds to the completed workflow.</span></span> <span data-ttu-id="6292d-192">Если вы не вносили запишите `InstanceId`, можно определить правильный файл отслеживания с помощью **Дата изменения** сведения в обозревателе Windows.</span><span class="sxs-lookup"><span data-stu-id="6292d-192">If you did not make a note of the `InstanceId`, you can identify the correct tracking file by using the **Date modified** information in Windows Explorer.</span></span>

 <span data-ttu-id="6292d-193">**Введите число от 1 до 10**
**5-слишком много.** 
 **Введите число от 1 до 10**
**3 слишком велико.** 
 **Введите число от 1 до 10**
**1-слишком мало.** 
 **Введите число от 1 до 10**
**2-правильное число. Вы угадали число за 4 попытки.**</span><span class="sxs-lookup"><span data-stu-id="6292d-193">**Please enter a number between 1 and 10**
**5 is too high.**
**Please enter a number between 1 and 10**
**3 is too high.**
**Please enter a number between 1 and 10**
**1 is too low.**
**Please enter a number between 1 and 10**
**2 is correct. You guessed it in 4 turns.**</span></span>      <span data-ttu-id="6292d-194">Обновленные выходные данные `WriteLine` содержатся в файле отслеживания, в том числе выходные данные трассировки действия `WriteLine`, добавленного в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="6292d-194">The updated `WriteLine` output is contained within the tracking file, including the output of the `WriteLine` that was added in this topic.</span></span>

4. <span data-ttu-id="6292d-195">Перейдите к приложению отгадывания чисел и выберите один из рабочих процессов, который был запущен до выполнения обновлений.</span><span class="sxs-lookup"><span data-stu-id="6292d-195">Switch back to the number guessing application and select one of the workflows that was started before the updates were made.</span></span> <span data-ttu-id="6292d-196">Вы можете указать версию выбранного в данный момент рабочего процесса, посмотрев сведения о версии, отображаемые под окном состояния.</span><span class="sxs-lookup"><span data-stu-id="6292d-196">You can identify the version of the currently selected workflow by looking at the version information that is displayed below the status window.</span></span> <span data-ttu-id="6292d-197">Введите несколько предположений и обратите внимание на то, что некоторые обновления состояния соответствуют выходным данным действия `WriteLine` из предыдущей версии, но не включают предположение пользователя.</span><span class="sxs-lookup"><span data-stu-id="6292d-197">Enter some guesses and note that the status updates match the `WriteLine` activity output from the previous version, and do not include the user's guess.</span></span> <span data-ttu-id="6292d-198">Это происходит потому, что такие рабочие процессы используют предыдущее определение рабочего процесса, в котором не выполнены обновления `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="6292d-198">That is because these workflows are using the previous workflow definition that does not have the `WriteLine` updates.</span></span>

     <span data-ttu-id="6292d-199">На следующем шаге [как: Обновить определение запущенного экземпляра рабочего процесса](how-to-update-the-definition-of-a-running-workflow-instance.md), выполнение `v1` экземпляров рабочего процесса обновляются, чтобы они содержали новые функции в виде `v2` экземпляров.</span><span class="sxs-lookup"><span data-stu-id="6292d-199">In the next step, [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md), the running `v1` workflow instances are updated so they contain the new functionality as the `v2` instances.</span></span>
