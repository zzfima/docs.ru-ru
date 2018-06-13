---
title: Как создать последовательный рабочий процесс
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: d7379e6e4d24ccc23d57486c3271c482a7f17edd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33519406"
---
# <a name="how-to-create-a-sequential-workflow"></a><span data-ttu-id="a8efd-102">Как создать последовательный рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="a8efd-102">How to: Create a Sequential Workflow</span></span>
<span data-ttu-id="a8efd-103">Рабочие процессы могут создаваться как из встроенных, так и из пользовательских действий.</span><span class="sxs-lookup"><span data-stu-id="a8efd-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="a8efd-104">В этом разделе шаги по созданию рабочего процесса, который использует оба встроенных действий, такие как <xref:System.Activities.Statements.Sequence> действия и пользовательских действий из предыдущего [как: создается действие](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="a8efd-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Sequence> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="a8efd-105">Рабочий процесс моделирует игру по угадыванию числа.</span><span class="sxs-lookup"><span data-stu-id="a8efd-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8efd-106">Каждый раздел в учебнике «Приступая к работе» построен на основе предыдущих разделов.</span><span class="sxs-lookup"><span data-stu-id="a8efd-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="a8efd-107">Для изучения этого раздела, необходимо сначала выполнить [как: создается действие](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="a8efd-107">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8efd-108">Чтобы скачать завершенную версию учебника, см. раздел [Windows Workflow Foundation (WF45), учебник "Приступая к работе"](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="a8efd-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="a8efd-109">Создание рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="a8efd-109">To create the workflow</span></span>  
  
1.  <span data-ttu-id="a8efd-110">Щелкните правой кнопкой мыши **NumberGuessWorkflowActivities** в **обозревателе решений** и выберите **добавить**, **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="a8efd-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2.  <span data-ttu-id="a8efd-111">В **установленные**, **общих элементов** выберите **рабочего процесса**.</span><span class="sxs-lookup"><span data-stu-id="a8efd-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="a8efd-112">Выберите **действия** из **рабочего процесса** списка.</span><span class="sxs-lookup"><span data-stu-id="a8efd-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3.  <span data-ttu-id="a8efd-113">Тип `SequentialNumberGuessWorkflow` в **имя** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="a8efd-113">Type `SequentialNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4.  <span data-ttu-id="a8efd-114">Перетащите **последовательности** действия из **поток управления** раздел **элементов** и поместите его в **Перетащите сюда действие** метки на область конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="a8efd-114">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="a8efd-115">Создание переменных и аргументов рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="a8efd-115">To create the workflow variables and arguments</span></span>  
  
1.  <span data-ttu-id="a8efd-116">Дважды щелкните **SequentialNumberGuessWorkflow.xaml** в **обозревателе решений** для отображения рабочего процесса в конструкторе, если он еще не отображается.</span><span class="sxs-lookup"><span data-stu-id="a8efd-116">Double-click **SequentialNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2.  <span data-ttu-id="a8efd-117">Нажмите кнопку **аргументы** в нижнем левом углу конструктора рабочих процессов для отображения **аргументы** области.</span><span class="sxs-lookup"><span data-stu-id="a8efd-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3.  <span data-ttu-id="a8efd-118">Нажмите кнопку **создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="a8efd-118">Click **Create Argument**.</span></span>  
  
4.  <span data-ttu-id="a8efd-119">Тип `MaxNumber` в **имя** выберите **в** из **направление** раскрывающемся списке выберите **Int32** из **Тип аргумента** раскрывающегося списка и нажмите клавишу ВВОД, чтобы сохранить аргумент.</span><span class="sxs-lookup"><span data-stu-id="a8efd-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5.  <span data-ttu-id="a8efd-120">Нажмите кнопку **создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="a8efd-120">Click **Create Argument**.</span></span>  
  
6.  <span data-ttu-id="a8efd-121">Тип `Turns` в **имя** поле, расположенном под только что добавленном `MaxNumber` аргумента выберите **Out** из **направление** раскрывающегося списка, выберите  **Int32** из **тип аргумента** раскрывающегося списка и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="a8efd-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="a8efd-122">Нажмите кнопку **аргументы** в нижнем левом углу конструктора действий, чтобы закрыть **аргументы** области.</span><span class="sxs-lookup"><span data-stu-id="a8efd-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8.  <span data-ttu-id="a8efd-123">Нажмите кнопку **переменных** в нижнем левом углу конструктора рабочих процессов для отображения **переменных** области.</span><span class="sxs-lookup"><span data-stu-id="a8efd-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="a8efd-124">Нажмите кнопку **создания переменной**.</span><span class="sxs-lookup"><span data-stu-id="a8efd-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="a8efd-125">Если не **создать переменную** поле отображается, щелкните **последовательности** действие в рабочей области конструктора рабочих процессов, чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="a8efd-125">If no **Create Variable** box is displayed, click the **Sequence** activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="a8efd-126">Тип `Guess` в **имя** выберите **Int32** из **тип переменной** раскрывающегося списка и нажмите клавишу ВВОД, чтобы сохранить переменную.</span><span class="sxs-lookup"><span data-stu-id="a8efd-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="a8efd-127">Нажмите кнопку **создания переменной**.</span><span class="sxs-lookup"><span data-stu-id="a8efd-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="a8efd-128">Тип `Target` в **имя** выберите **Int32** из **тип переменной** раскрывающегося списка и нажмите клавишу ВВОД, чтобы сохранить переменную.</span><span class="sxs-lookup"><span data-stu-id="a8efd-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="a8efd-129">Нажмите кнопку **переменных** в нижнем левом углу конструктора действий, чтобы закрыть **переменных** области.</span><span class="sxs-lookup"><span data-stu-id="a8efd-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="a8efd-130">Добавление действий рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="a8efd-130">To add the workflow activities</span></span>  
  
1.  <span data-ttu-id="a8efd-131">Перетащите **назначить** действия из **примитивы** раздел **элементов** и поместите его в **последовательности** действия.</span><span class="sxs-lookup"><span data-stu-id="a8efd-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Sequence** activity.</span></span> <span data-ttu-id="a8efd-132">Тип `Target` в **для** поле и следующее выражение в **введите выражение C#** или **введите выражение VB** поле.</span><span class="sxs-lookup"><span data-stu-id="a8efd-132">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="a8efd-133">Если **элементов** окно не отображается, выберите **элементов** из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="a8efd-133">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
2.  <span data-ttu-id="a8efd-134">Перетащите **DoWhile** действия из **поток управления** раздел **элементов** и поместите его в рабочем процессе, чтобы оно было под **назначить** действие.</span><span class="sxs-lookup"><span data-stu-id="a8efd-134">Drag a **DoWhile** activity from the **Control Flow** section of the **Toolbox** and drop it on the workflow so that it is below the **Assign** activity.</span></span>  
  
3.  <span data-ttu-id="a8efd-135">Введите следующее выражение в **DoWhile** действия **условие** поле значения свойства.</span><span class="sxs-lookup"><span data-stu-id="a8efd-135">Type the following expression into the **DoWhile** activity’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
     <span data-ttu-id="a8efd-136">Действие <xref:System.Activities.Statements.DoWhile> выполняет дочерние действия, а затем выполняет оценку своего условия <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span><span class="sxs-lookup"><span data-stu-id="a8efd-136">A <xref:System.Activities.Statements.DoWhile> activity executes its child activities and then evaluates its <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span></span> <span data-ttu-id="a8efd-137">Если <xref:System.Activities.Statements.DoWhile.Condition%2A> имеет значение `True`, то действия в <xref:System.Activities.Statements.DoWhile> выполняются повторно.</span><span class="sxs-lookup"><span data-stu-id="a8efd-137">If the <xref:System.Activities.Statements.DoWhile.Condition%2A> evaluates to `True`, then the activities in the <xref:System.Activities.Statements.DoWhile> execute again.</span></span> <span data-ttu-id="a8efd-138">В этом примере проверяется догадка пользователя и <xref:System.Activities.Statements.DoWhile> продолжается до тех пор, пока догадка не будет правильной.</span><span class="sxs-lookup"><span data-stu-id="a8efd-138">In this example, the user’s guess is evaluated and the <xref:System.Activities.Statements.DoWhile> continues until the guess is correct.</span></span>  
  
4.  <span data-ttu-id="a8efd-139">Перетащите **Prompt** действия из **NumberGuessWorkflowActivities** раздел **элементов** и поместите его **DoWhile** действия на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="a8efd-139">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **DoWhile** activity from the previous step.</span></span>  
  
5.  <span data-ttu-id="a8efd-140">В **окно свойств**, тип `"EnterGuess"` кавычки, в том числе **BookmarkName** поле значения свойства для **Prompt** действия.</span><span class="sxs-lookup"><span data-stu-id="a8efd-140">In the **Properties Window**, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box for the **Prompt** activity.</span></span> <span data-ttu-id="a8efd-141">Тип `Guess` в **результат** поле значения свойства и введите следующее выражение в **текст** поле свойства.</span><span class="sxs-lookup"><span data-stu-id="a8efd-141">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="a8efd-142">Если **окно свойств** не отображается, выберите **окно свойств** из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="a8efd-142">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
6.  <span data-ttu-id="a8efd-143">Перетащите **назначить** действия из **примитивы** раздел **элементов** и поместите его **DoWhile** так, чтобы оно было расположено **Prompt** действия.</span><span class="sxs-lookup"><span data-stu-id="a8efd-143">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it in the **DoWhile** activity so that it follows the **Prompt** activity.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a8efd-144">При удалении **назначить** Обратите внимание, как в конструкторе рабочих процессов автоматически добавляет **последовательности** куда помещается **Prompt** действия и вновь добавленная **Назначить** действия.</span><span class="sxs-lookup"><span data-stu-id="a8efd-144">When you drop the **Assign** activity, note how the workflow designer automatically adds a **Sequence** activity to contain both the **Prompt** activity and the newly added **Assign** activity.</span></span>  
  
7.  <span data-ttu-id="a8efd-145">Тип `Turns` в **для** поле и `Turns + 1` в **введите выражение C#** или **введите выражение VB** поле.</span><span class="sxs-lookup"><span data-stu-id="a8efd-145">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
8.  <span data-ttu-id="a8efd-146">Перетащите **Если** действия из **поток управления** раздел **элементов** и поместите его **последовательности** так, чтобы оно было расположено добавленный **назначить** действия.</span><span class="sxs-lookup"><span data-stu-id="a8efd-146">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the newly added **Assign** activity.</span></span>  
  
9. <span data-ttu-id="a8efd-147">Введите следующее выражение в **Если** действия **условие** поле значения свойства.</span><span class="sxs-lookup"><span data-stu-id="a8efd-147">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
10. <span data-ttu-id="a8efd-148">Перетащите еще одно **Если** действия из **поток управления** раздел **элементов** и поместите его **затем** первого **Если** действия.</span><span class="sxs-lookup"><span data-stu-id="a8efd-148">Drag another **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Then** section of the first **If** activity.</span></span>  
  
11. <span data-ttu-id="a8efd-149">Введите следующее выражение в только что добавленном **Если** действия **условие** поле значения свойства.</span><span class="sxs-lookup"><span data-stu-id="a8efd-149">Type the following expression into the newly added **If** activity’s **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
12. <span data-ttu-id="a8efd-150">Перетащите два **WriteLine** действия из **примитивы** раздел **элементов** и разместите их так, чтобы одно находилось в **затем** раздела добавленный **Если** действия, а другое — в **Else** раздела.</span><span class="sxs-lookup"><span data-stu-id="a8efd-150">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the newly added **If** activity, and one is in the **Else** section.</span></span>  
  
13. <span data-ttu-id="a8efd-151">Нажмите кнопку **WriteLine** действия в **затем** чтобы выбрать его и введите следующее выражение в **текст** поле значения свойства.</span><span class="sxs-lookup"><span data-stu-id="a8efd-151">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```vb  
    "Your guess is too low."  
    ```  
  
14. <span data-ttu-id="a8efd-152">Нажмите кнопку **WriteLine** действия в **Else** чтобы выбрать его и введите следующее выражение в **текст** поле значения свойства.</span><span class="sxs-lookup"><span data-stu-id="a8efd-152">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```vb  
    "Your guess is too high."  
    ```  
  
     <span data-ttu-id="a8efd-153">В следующем примере показан завершенный рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="a8efd-153">The following example illustrates the completed workflow.</span></span>  
  
     <span data-ttu-id="a8efd-154">![Полный последовательный рабочий процесс](../../../docs/framework/windows-workflow-foundation/media/wfsequentialgettingstartedtutorialcomplete.JPG "WFSequentialGettingStartedTutorialComplete")</span><span class="sxs-lookup"><span data-stu-id="a8efd-154">![Completed Sequential Workflow](../../../docs/framework/windows-workflow-foundation/media/wfsequentialgettingstartedtutorialcomplete.JPG "WFSequentialGettingStartedTutorialComplete")</span></span>  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="a8efd-155">Построение рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="a8efd-155">To build the workflow</span></span>  
  
1.  <span data-ttu-id="a8efd-156">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="a8efd-156">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="a8efd-157">Инструкции о том, как запустить рабочий процесс, см. следующий раздел [как: запуск рабочего процесса](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="a8efd-157">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span> <span data-ttu-id="a8efd-158">Если вы уже выполнили [как: запуск рабочего процесса](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) пошаговое с другой стиль рабочего процесса и будет выполняться с помощью последовательных рабочих процессов на этом шаге, перейдите к [для построения и запуска приложения](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication)раздел [как: запуск рабочего процесса](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="a8efd-158">If you have already completed the [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the sequential workflow from this step, skip ahead to the [To build and run the application](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8efd-159">См. также</span><span class="sxs-lookup"><span data-stu-id="a8efd-159">See Also</span></span>  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [<span data-ttu-id="a8efd-160">Программирование в Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="a8efd-160">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [<span data-ttu-id="a8efd-161">Разработка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="a8efd-161">Designing Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [<span data-ttu-id="a8efd-162">Руководство по началу работы</span><span class="sxs-lookup"><span data-stu-id="a8efd-162">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [<span data-ttu-id="a8efd-163">Практическое руководство. Создание действия</span><span class="sxs-lookup"><span data-stu-id="a8efd-163">How to: Create an Activity</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [<span data-ttu-id="a8efd-164">Практическое руководство. Запуск рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="a8efd-164">How to: Run a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
