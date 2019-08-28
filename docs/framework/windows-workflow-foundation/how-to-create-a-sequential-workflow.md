---
title: Практическое руководство. Создание последовательного рабочего процесса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: d94843e696848010791b1e22d06e4852d35bc68e
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044411"
---
# <a name="how-to-create-a-sequential-workflow"></a><span data-ttu-id="59a94-102">Практическое руководство. Создание последовательного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="59a94-102">How to: Create a Sequential Workflow</span></span>

<span data-ttu-id="59a94-103">Рабочие процессы могут создаваться как из встроенных, так и из пользовательских действий.</span><span class="sxs-lookup"><span data-stu-id="59a94-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="59a94-104">В этом разделе описывается создание рабочего процесса, который использует как встроенные действия, такие как <xref:System.Activities.Statements.Sequence> действие, так и пользовательские действия из предыдущего [руководства. Создание раздела действия](how-to-create-an-activity.md) .</span><span class="sxs-lookup"><span data-stu-id="59a94-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Sequence> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="59a94-105">Рабочий процесс моделирует игру по угадыванию числа.</span><span class="sxs-lookup"><span data-stu-id="59a94-105">The workflow models a number guessing game.</span></span>

> [!NOTE]
> <span data-ttu-id="59a94-106">Каждый раздел в учебнике «Приступая к работе» построен на основе предыдущих разделов.</span><span class="sxs-lookup"><span data-stu-id="59a94-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="59a94-107">Для выполнения этой статьи сначала необходимо выполнить [следующие действия: Создайте действие](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="59a94-107">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>

> [!NOTE]
> <span data-ttu-id="59a94-108">Чтобы скачать завершенную версию учебника, см. раздел [Windows Workflow Foundation (WF45), учебник "Приступая к работе"](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="59a94-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="to-create-the-workflow"></a><span data-ttu-id="59a94-109">Создание рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="59a94-109">To create the workflow</span></span>

1. <span data-ttu-id="59a94-110">Щелкните правой кнопкой мыши **NumberGuessWorkflowActivities** в **Обозреватель решений** и выберите **добавить**, **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="59a94-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>

2. <span data-ttu-id="59a94-111">В узле **установленные** **Общие элементы** выберите **Рабочий процесс**.</span><span class="sxs-lookup"><span data-stu-id="59a94-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="59a94-112">Выберите **действие** из списка **Рабочий процесс** .</span><span class="sxs-lookup"><span data-stu-id="59a94-112">Select **Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="59a94-113">Введите `SequentialNumberGuessWorkflow` в поле **имя** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="59a94-113">Type `SequentialNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>

4. <span data-ttu-id="59a94-114">Перетащите действие **Sequence** из раздела **поток управления** на **панели элементов** и поместите его на метку **перетащите действие сюда** в рабочей области конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="59a94-114">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>

## <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="59a94-115">Создание переменных и аргументов рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="59a94-115">To create the workflow variables and arguments</span></span>

1. <span data-ttu-id="59a94-116">Дважды щелкните **SequentialNumberGuessWorkflow. XAML** в **Обозреватель решений** , чтобы отобразить рабочий процесс в конструкторе, если он еще не отображается.</span><span class="sxs-lookup"><span data-stu-id="59a94-116">Double-click **SequentialNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>

2. <span data-ttu-id="59a94-117">Щелкните **аргументы** в левой нижней части конструктора рабочих процессов, чтобы отобразить панель **аргументы** .</span><span class="sxs-lookup"><span data-stu-id="59a94-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>

3. <span data-ttu-id="59a94-118">Нажмите кнопку **Создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="59a94-118">Click **Create Argument**.</span></span>

4. <span data-ttu-id="59a94-119">Введите `MaxNumber` в поле **имя** , выберите **в** раскрывающемся списке **направление** значение **Int32** , а затем нажмите клавишу ВВОД , чтобы сохранить аргумент.</span><span class="sxs-lookup"><span data-stu-id="59a94-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>

5. <span data-ttu-id="59a94-120">Нажмите кнопку **Создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="59a94-120">Click **Create Argument**.</span></span>

6. <span data-ttu-id="59a94-121">Введите `Turns` в поле **имя** , которое находится ниже вновь добавленного `MaxNumber` аргумента, выберите из раскрывающегося списка **направление** , выберите **Int32** из раскрывающегося списка **тип аргумента** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="59a94-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>

7. <span data-ttu-id="59a94-122">Щелкните **аргументы** в нижней левой части конструктора операций, чтобы закрыть панель **аргументы** .</span><span class="sxs-lookup"><span data-stu-id="59a94-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

8. <span data-ttu-id="59a94-123">Щелкните **переменные** в левой нижней части конструктора рабочих процессов, чтобы отобразить панель **переменные** .</span><span class="sxs-lookup"><span data-stu-id="59a94-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>

9. <span data-ttu-id="59a94-124">Нажмите кнопку **создать переменную**.</span><span class="sxs-lookup"><span data-stu-id="59a94-124">Click **Create Variable**.</span></span>

    > [!TIP]
    > <span data-ttu-id="59a94-125">Если поле **создать переменную** не отображается, щелкните действие последовательностей в области конструктора рабочих процессов, чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="59a94-125">If no **Create Variable** box is displayed, click the **Sequence** activity on the workflow designer surface to select it.</span></span>

10. <span data-ttu-id="59a94-126">Введите `Guess` в поле **имя** , выберите **Int32** в раскрывающемся списке **тип переменной** и нажмите клавишу ВВОД, чтобы сохранить переменную.</span><span class="sxs-lookup"><span data-stu-id="59a94-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

11. <span data-ttu-id="59a94-127">Нажмите кнопку **создать переменную**.</span><span class="sxs-lookup"><span data-stu-id="59a94-127">Click **Create Variable**.</span></span>

12. <span data-ttu-id="59a94-128">Введите `Target` в поле **имя** , выберите **Int32** в раскрывающемся списке **тип переменной** и нажмите клавишу ВВОД, чтобы сохранить переменную.</span><span class="sxs-lookup"><span data-stu-id="59a94-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

13. <span data-ttu-id="59a94-129">Щелкните **переменные** в левой нижней части конструктора действий, чтобы закрыть панель **переменные** .</span><span class="sxs-lookup"><span data-stu-id="59a94-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>

## <a name="to-add-the-workflow-activities"></a><span data-ttu-id="59a94-130">Добавление действий рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="59a94-130">To add the workflow activities</span></span>

1. <span data-ttu-id="59a94-131">Перетащите действие **Assign (назначение** ) из раздела примитивы на **панели элементов** и поместите его в действие **Sequence** .</span><span class="sxs-lookup"><span data-stu-id="59a94-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Sequence** activity.</span></span> <span data-ttu-id="59a94-132">Введите `Target` в поле **to** и следующее выражение в поле **введите C# выражение** или **введите выражение VB** .</span><span class="sxs-lookup"><span data-stu-id="59a94-132">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

    ```vb
    New System.Random().Next(1, MaxNumber + 1)
    ```

    ```csharp
    new System.Random().Next(1, MaxNumber + 1)
    ```

    > [!TIP]
    > <span data-ttu-id="59a94-133">Если окно **панель элементов** не отображается, в меню **вид** выберите пункт **область элементов** .</span><span class="sxs-lookup"><span data-stu-id="59a94-133">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

2. <span data-ttu-id="59a94-134">Перетащите действие **DoWhile** из раздела **поток управления** на **панели элементов** и поместите его в рабочий процесс, чтобы он был ниже действия Assign ( **назначить** ).</span><span class="sxs-lookup"><span data-stu-id="59a94-134">Drag a **DoWhile** activity from the **Control Flow** section of the **Toolbox** and drop it on the workflow so that it is below the **Assign** activity.</span></span>

3. <span data-ttu-id="59a94-135">Введите следующее выражение в поле значения свойства **Condition** действия **DoWhile** .</span><span class="sxs-lookup"><span data-stu-id="59a94-135">Type the following expression into the **DoWhile** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

     <span data-ttu-id="59a94-136">Действие <xref:System.Activities.Statements.DoWhile> выполняет дочерние действия, а затем выполняет оценку своего условия <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span><span class="sxs-lookup"><span data-stu-id="59a94-136">A <xref:System.Activities.Statements.DoWhile> activity executes its child activities and then evaluates its <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span></span> <span data-ttu-id="59a94-137">Если <xref:System.Activities.Statements.DoWhile.Condition%2A> имеет значение `True`, то действия в <xref:System.Activities.Statements.DoWhile> выполняются повторно.</span><span class="sxs-lookup"><span data-stu-id="59a94-137">If the <xref:System.Activities.Statements.DoWhile.Condition%2A> evaluates to `True`, then the activities in the <xref:System.Activities.Statements.DoWhile> execute again.</span></span> <span data-ttu-id="59a94-138">В этом примере проверяется догадка пользователя и <xref:System.Activities.Statements.DoWhile> продолжается до тех пор, пока догадка не будет правильной.</span><span class="sxs-lookup"><span data-stu-id="59a94-138">In this example, the user’s guess is evaluated and the <xref:System.Activities.Statements.DoWhile> continues until the guess is correct.</span></span>

4. <span data-ttu-id="59a94-139">Перетащите действие **запрос** из раздела **NumberGuessWorkflowActivities** на **панели элементов** и поместите его в действие **DoWhile** из предыдущего шага.</span><span class="sxs-lookup"><span data-stu-id="59a94-139">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **DoWhile** activity from the previous step.</span></span>

5. <span data-ttu-id="59a94-140">В **окне Свойства**введите `"EnterGuess"` , включая кавычки, в поле значение свойства **BookmarkName** для действия **Prompt** .</span><span class="sxs-lookup"><span data-stu-id="59a94-140">In the **Properties Window**, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box for the **Prompt** activity.</span></span> <span data-ttu-id="59a94-141">Введите `Guess` в поле значение свойства **результата** и введите следующее выражение в поле свойства **текста** .</span><span class="sxs-lookup"><span data-stu-id="59a94-141">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>

    ```vb
    "Please enter a number between 1 and " & MaxNumber
    ```

    ```csharp
    "Please enter a number between 1 and " + MaxNumber
    ```

    > [!TIP]
    > <span data-ttu-id="59a94-142">Если **окно Свойства** не отображается, в меню **вид** выберите пункт **окно свойств** .</span><span class="sxs-lookup"><span data-stu-id="59a94-142">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

6. <span data-ttu-id="59a94-143">Перетащите действие **Assign (назначение** ) из раздела примитивы на **панели элементов** и поместите его в действие **DoWhile** , чтобы оно применяно к действию **Prompt** .</span><span class="sxs-lookup"><span data-stu-id="59a94-143">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it in the **DoWhile** activity so that it follows the **Prompt** activity.</span></span>

    > [!NOTE]
    > <span data-ttu-id="59a94-144">При удалении действия **Assign (назначение** ) Обратите внимание на то, как конструктор рабочих процессов автоматически добавляет действие **Sequence** , которое содержит как действие **Prompt** , так и вновь добавленное действие **назначение** .</span><span class="sxs-lookup"><span data-stu-id="59a94-144">When you drop the **Assign** activity, note how the workflow designer automatically adds a **Sequence** activity to contain both the **Prompt** activity and the newly added **Assign** activity.</span></span>

7. <span data-ttu-id="59a94-145">Введите `Turns` в поле **Кому** и `Turns + 1` в поле **введите C# выражение** или **введите выражение VB** .</span><span class="sxs-lookup"><span data-stu-id="59a94-145">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

8. <span data-ttu-id="59a94-146">Перетащите действие **If** из раздела **поток управления** на **панели элементов** и поместите его в действие **Sequence** , чтобы оно применялись к вновь добавленному действию **Assign** .</span><span class="sxs-lookup"><span data-stu-id="59a94-146">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the newly added **Assign** activity.</span></span>

9. <span data-ttu-id="59a94-147">Введите следующее выражение в поле значение свойства **Condition** действия **If** .</span><span class="sxs-lookup"><span data-stu-id="59a94-147">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

10. <span data-ttu-id="59a94-148">Перетащите другой элемент, **Если** действие находится в разделе **поток управления** **области элементов** , и поместите его в раздел **then** первого действия **If** .</span><span class="sxs-lookup"><span data-stu-id="59a94-148">Drag another **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Then** section of the first **If** activity.</span></span>

11. <span data-ttu-id="59a94-149">Введите следующее выражение в поле значение свойства **условия** для действия, добавленного в действие.</span><span class="sxs-lookup"><span data-stu-id="59a94-149">Type the following expression into the newly added **If** activity’s **Condition** property value box.</span></span>

    ```
    Guess < Target
    ```

12. <span data-ttu-id="59a94-150">Перетащите два действия **WriteLine** из раздела **примитивы** на **панели элементов** и поместите их так, чтобы они находящегося в разделе **then** добавленного действия **If** , а другой — в разделе **else** .</span><span class="sxs-lookup"><span data-stu-id="59a94-150">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the newly added **If** activity, and one is in the **Else** section.</span></span>

13. <span data-ttu-id="59a94-151">Щелкните действие **WriteLine** в разделе **then (затем** ), чтобы выбрать его, и введите следующее выражение в поле значение свойства **текста** .</span><span class="sxs-lookup"><span data-stu-id="59a94-151">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too low."
    ```

14. <span data-ttu-id="59a94-152">Щелкните действие **WriteLine** в разделе **else** , чтобы выбрать его, и введите следующее выражение в поле значение свойства **текста** .</span><span class="sxs-lookup"><span data-stu-id="59a94-152">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too high."
    ```

     <span data-ttu-id="59a94-153">В следующем примере показан готовый рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="59a94-153">The following example illustrates the completed workflow:</span></span>

     ![Снимок экрана, показывающий завершенный последовательный рабочий процесс.](./media/how-to-create-a-sequential-workflow/complete-sequential-workflow.jpg)

## <a name="to-build-the-workflow"></a><span data-ttu-id="59a94-155">Построение рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="59a94-155">To build the workflow</span></span>

1. <span data-ttu-id="59a94-156">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="59a94-156">Press CTRL+SHIFT+B to build the solution.</span></span>

     <span data-ttu-id="59a94-157">Инструкции по запуску рабочего процесса см. в следующем разделе [: Запустите рабочий процесс](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="59a94-157">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="59a94-158">Если вы уже выполнили [действия в следующих случаях: Запустите этап рабочего](how-to-run-a-workflow.md) процесса с другим стилем рабочего процесса и запустите его с помощью последовательного рабочего процесса из этого шага, перейдите к разделу [ [Создание и запуск приложения](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) , посвященного следующим инструкциям. Запустите рабочий процесс](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="59a94-158">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the sequential workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="59a94-159">См. также</span><span class="sxs-lookup"><span data-stu-id="59a94-159">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="59a94-160">Программирование в Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="59a94-160">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="59a94-161">Разработка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="59a94-161">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="59a94-162">Руководство по началу работы</span><span class="sxs-lookup"><span data-stu-id="59a94-162">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="59a94-163">Практическое руководство. Создание действия</span><span class="sxs-lookup"><span data-stu-id="59a94-163">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="59a94-164">Практическое руководство. Запуск рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="59a94-164">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
