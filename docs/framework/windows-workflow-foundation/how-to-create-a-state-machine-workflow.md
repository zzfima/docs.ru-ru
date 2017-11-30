---
title: "Как создать рабочий процесс конечного автомата"
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
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 797cdc425c0f3088aa2b75c0285ca6bea2dd425b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-state-machine-workflow"></a><span data-ttu-id="bf4e1-102">Как создать рабочий процесс конечного автомата</span><span class="sxs-lookup"><span data-stu-id="bf4e1-102">How to: Create a State Machine Workflow</span></span>
<span data-ttu-id="bf4e1-103">Рабочие процессы могут создаваться как из встроенных, так и из пользовательских действий.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="bf4e1-104">В этом разделе шаги по созданию рабочего процесса, который использует оба встроенных действий, такие как <xref:System.Activities.Statements.StateMachine> действия и пользовательских действий из предыдущего [как: создается действие](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.StateMachine> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="bf4e1-105">Рабочий процесс моделирует игру по угадыванию числа.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf4e1-106">Каждый раздел в учебнике «Приступая к работе» построен на основе предыдущих разделов.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="bf4e1-107">Для изучения этого раздела, необходимо сначала выполнить [как: создается действие](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="bf4e1-107">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf4e1-108">Чтобы скачать завершенную версию учебника, см. раздел [Windows Workflow Foundation (WF45), учебник "Приступая к работе"](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="bf4e1-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="bf4e1-109">Создание рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="bf4e1-109">To create the workflow</span></span>  
  
1.  <span data-ttu-id="bf4e1-110">Щелкните правой кнопкой мыши **NumberGuessWorkflowActivities** в **обозревателе решений** и выберите **добавить**, **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2.  <span data-ttu-id="bf4e1-111">В **установленные**, **общих элементов** выберите **рабочего процесса**.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="bf4e1-112">Выберите **действия** из **рабочего процесса** списка.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3.  <span data-ttu-id="bf4e1-113">Тип `StateMachineNumberGuessWorkflow` в **имя** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-113">Type `StateMachineNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4.  <span data-ttu-id="bf4e1-114">Перетащите **StateMachine** действия из **конечного автомата** раздел **элементов** и поместите его в **Перетащите сюда действие** метки на области конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-114">Drag a **StateMachine** activity from the **State Machine** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="bf4e1-115">Создание переменных и аргументов рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="bf4e1-115">To create the workflow variables and arguments</span></span>  
  
1.  <span data-ttu-id="bf4e1-116">Дважды щелкните **StateMachineNumberGuessWorkflow.xaml** в **обозревателе решений** для отображения рабочего процесса в конструкторе, если он еще не отображается.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-116">Double-click **StateMachineNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2.  <span data-ttu-id="bf4e1-117">Нажмите кнопку **аргументы** в нижнем левом углу конструктора рабочих процессов для отображения **аргументы** области.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3.  <span data-ttu-id="bf4e1-118">Нажмите кнопку **создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-118">Click **Create Argument**.</span></span>  
  
4.  <span data-ttu-id="bf4e1-119">Тип `MaxNumber` в **имя** выберите **в** из **направление** раскрывающемся списке выберите **Int32** из **Тип аргумента** раскрывающегося списка и нажмите клавишу ВВОД, чтобы сохранить аргумент.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5.  <span data-ttu-id="bf4e1-120">Нажмите кнопку **создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-120">Click **Create Argument**.</span></span>  
  
6.  <span data-ttu-id="bf4e1-121">Тип `Turns` в **имя** поле, расположенном под только что добавленном `MaxNumber` аргумента выберите **Out** из **направление** раскрывающегося списка, выберите  **Int32** из **тип аргумента** раскрывающегося списка и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="bf4e1-122">Нажмите кнопку **аргументы** в нижнем левом углу конструктора действий, чтобы закрыть **аргументы** области.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8.  <span data-ttu-id="bf4e1-123">Нажмите кнопку **переменных** в нижнем левом углу конструктора рабочих процессов для отображения **переменных** области.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="bf4e1-124">Нажмите кнопку **создания переменной**.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="bf4e1-125">Если не **создать переменную** поле отображается, щелкните <xref:System.Activities.Statements.StateMachine> действие в рабочей области конструктора рабочих процессов, чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.StateMachine> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="bf4e1-126">Тип `Guess` в **имя** выберите **Int32** из **тип переменной** раскрывающегося списка и нажмите клавишу ВВОД, чтобы сохранить переменную.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="bf4e1-127">Нажмите кнопку **создания переменной**.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="bf4e1-128">Тип `Target` в **имя** выберите **Int32** из **тип переменной** раскрывающегося списка и нажмите клавишу ВВОД, чтобы сохранить переменную.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="bf4e1-129">Нажмите кнопку **переменных** в нижнем левом углу конструктора действий, чтобы закрыть **переменных** области.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="bf4e1-130">Добавление действий рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="bf4e1-130">To add the workflow activities</span></span>  
  
1.  <span data-ttu-id="bf4e1-131">Нажмите кнопку **State1** для ее выделения.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-131">Click **State1** to select it.</span></span> <span data-ttu-id="bf4e1-132">В **окно свойств**, изменить **DisplayName** для `Initialize Target`.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-132">In the **Properties Window**, change the **DisplayName** to `Initialize Target`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="bf4e1-133">Если **окно свойств** не отображается, выберите **окно свойств** из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-133">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
2.  <span data-ttu-id="bf4e1-134">Дважды щелкните только что переименованный **инициализировать целевой объект** состояния в конструкторе рабочих процессов, чтобы развернуть его.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-134">Double-click the newly renamed **Initialize Target** state in the workflow designer to expand it.</span></span>  
  
3.  <span data-ttu-id="bf4e1-135">Перетащите **назначить** действия из **примитивы** раздел **элементов** и поместите его в **входа** состояния.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-135">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span> <span data-ttu-id="bf4e1-136">Тип `Target` в **для** поле и следующее выражение в **введите выражение C#** или **введите выражение VB** поле.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-136">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="bf4e1-137">Если **элементов** окно не отображается, выберите **элементов** из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-137">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
4.  <span data-ttu-id="bf4e1-138">Возврат к общему состояния машины представление в конструкторе рабочих процессов, щелкнув **StateMachine** на экране навигатора отображать в верхней части конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-138">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
5.  <span data-ttu-id="bf4e1-139">Перетащите **состояние** действия из **конечного автомата** раздел **элементов** в конструктор рабочего процесса и наведите его на **инициализировать целевой объект** состояния.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-139">Drag a **State** activity from the **State Machine** section of the **Toolbox** onto the workflow designer and hover it over the **Initialize Target** state.</span></span> <span data-ttu-id="bf4e1-140">Обратите внимание, что вокруг будут отображены четыре треугольника **инициализировать целевой объект** состояния, когда новое состояние окажется над ним.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-140">Note that four triangles will appear around the **Initialize Target** state when the new state is over it.</span></span> <span data-ttu-id="bf4e1-141">Поместите новое состояние на треугольник непосредственно под **инициализировать целевой объект** состояния.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-141">Drop the new state on the triangle that is immediately below the **Initialize Target** state.</span></span> <span data-ttu-id="bf4e1-142">Это размещает новое состояние помещается в рабочий процесс и создает переход от **инициализировать целевой объект** состояния в новое состояние.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-142">This places the new state onto the workflow and creates a transition from the **Initialize Target** state to the new state.</span></span>  
  
6.  <span data-ttu-id="bf4e1-143">Нажмите кнопку **State1** для его выбора, измените **DisplayName** для `Enter Guess`, а затем дважды щелкните состояние в конструкторе рабочих процессов, чтобы развернуть его.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-143">Click **State1** to select it, change the **DisplayName** to `Enter Guess`, and then double-click the state in the workflow designer to expand it.</span></span>  
  
7.  <span data-ttu-id="bf4e1-144">Перетащите **WriteLine** действия из **примитивы** раздел **элементов** и поместите его в **входа** состояния.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-144">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span>  
  
8.  <span data-ttu-id="bf4e1-145">Введите следующее выражение в **текст** свойства **WriteLine**.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-145">Type the following expression into the **Text** property box of the **WriteLine**.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. <span data-ttu-id="bf4e1-146">Перетащите **назначить** действия из **примитивы** раздел **элементов** фигуру на **выхода** состояния.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-146">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop onto the **Exit** section of the state.</span></span>  
  
10. <span data-ttu-id="bf4e1-147">Тип `Turns` в **для** поле и `Turns + 1` в **введите выражение C#** или **введите выражение VB** поле.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-147">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
11. <span data-ttu-id="bf4e1-148">Возврат к общему состояния машины представление в конструкторе рабочих процессов, щелкнув **StateMachine** на экране навигатора отображать в верхней части конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-148">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
12. <span data-ttu-id="bf4e1-149">Перетащите **FinalState** действия из **конечного автомата** раздел **элементов**, наведите указатель мыши на **введите ответ** состояния и поместите его на треугольник, который отображается справа от **введите ответ** состояние для создания перехода между **введите ответ** и **FinalState**.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-149">Drag a **FinalState** activity from the **State Machine** section of the **Toolbox**, hover it over the **Enter Guess** state, and drop it onto the triangle that appears to the right of the **Enter Guess** state so that a transition is created between **Enter Guess** and **FinalState**.</span></span>  
  
13. <span data-ttu-id="bf4e1-150">Является именем по умолчанию перехода **T2**.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-150">The default name of the transition is **T2**.</span></span> <span data-ttu-id="bf4e1-151">Щелкните переход в конструкторе рабочих процессов, чтобы выбрать ее и задать его **DisplayName** для **правильное пробное**.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-151">Click the transition in the workflow designer to select it, and set its **DisplayName** to **Guess Correct**.</span></span> <span data-ttu-id="bf4e1-152">Затем щелкните и выберите **FinalState**и перетащите его вправо, чтобы было достаточно места для отображения полного имени перехода без наложения одним из двух состояний.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-152">Then click and select the **FinalState**, and drag it to the right so that there is room for the full transition name to be displayed without overlaying either of the two states.</span></span> <span data-ttu-id="bf4e1-153">Это позволит упростить выполнение оставшихся действий в учебнике.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-153">This will make it easier to complete the remaining steps in the tutorial.</span></span>  
  
14. <span data-ttu-id="bf4e1-154">Дважды щелкните только что переименованный **правильное пробное** перехода в конструкторе рабочих процессов, чтобы развернуть его.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-154">Double-click the newly renamed **Guess Correct** transition in the workflow designer to expand it.</span></span>  
  
15. <span data-ttu-id="bf4e1-155">Перетащите **ReadInt** действия из **NumberGuessWorkflowActivities** раздел **элементов** и поместите его **триггер** раздела перехода.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-155">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Trigger** section of the transition.</span></span>  
  
16. <span data-ttu-id="bf4e1-156">В **окно свойств** для **ReadInt** введите `"EnterGuess"` кавычки, в том числе **BookmarkName** поле значения свойства и тип `Guess`в **результат** поле значения свойства</span><span class="sxs-lookup"><span data-stu-id="bf4e1-156">In the **Properties Window** for the **ReadInt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box, and type `Guess` into the **Result** property value box</span></span>  
  
17. <span data-ttu-id="bf4e1-157">Введите следующее выражение в **правильное пробное** перехода **условие** поле значения свойства.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-157">Type the following expression into the **Guess Correct** transition’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. <span data-ttu-id="bf4e1-158">Возврат к общему состояния машины представление в конструкторе рабочих процессов, щелкнув **StateMachine** на экране навигатора отображать в верхней части конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-158">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bf4e1-159">Переход происходит при получении события триггера и оценке <xref:System.Activities.Statements.Transition.Condition%2A> значением `True` (если оно присутствует).</span><span class="sxs-lookup"><span data-stu-id="bf4e1-159">A transition occurs when the trigger event is received and the <xref:System.Activities.Statements.Transition.Condition%2A>, if present, evaluates to `True`.</span></span> <span data-ttu-id="bf4e1-160">Для этого перехода Если пользователь `Guess` соответствует случайно созданному `Target`, управление передается **FinalState** и завершения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-160">For this transition, if the user’s `Guess` matches the randomly generated `Target`, then control passes to the **FinalState** and the workflow completes.</span></span>  
  
19. <span data-ttu-id="bf4e1-161">В зависимости от того, является ли пробное значение правильным, рабочий процесс должен перейти либо **FinalState** или к **введите ответ** для другой попытки.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-161">Depending on whether the guess is correct, the workflow should transition either to the **FinalState** or back to the **Enter Guess** state for another try.</span></span> <span data-ttu-id="bf4e1-162">Оба перехода совместно используют один и тот же триггер ожидания догадка пользователя должны быть получены через **ReadInt** действия.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-162">Both transitions share the same trigger of waiting for the user’s guess to be received via the **ReadInt** activity.</span></span> <span data-ttu-id="bf4e1-163">Это называется общим переходом.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-163">This is called a shared transition.</span></span> <span data-ttu-id="bf4e1-164">Чтобы создать общий переход, щелкните круг, указывающий начало **правильное пробное** переход и перетащите его в нужное состояние.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-164">To create a shared transition, click the circle that indicates the start of the **Guess Correct** transition and drag it to the desired state.</span></span> <span data-ttu-id="bf4e1-165">В этом случае переход является переход на себя, поэтому перетащите начальную точку **правильное пробное** и поместите ее на нижнюю часть **введите ответ** состояния.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-165">In this case the transition is a self-transition, so drag the start point of the **Guess Correct** transition and drop it back onto the bottom of the **Enter Guess** state.</span></span> <span data-ttu-id="bf4e1-166">После создания перехода выберите его в конструкторе рабочих процессов и задать его **DisplayName** свойства **неверное пробное**.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-166">After creating the transition, select it in the workflow designer and set its **DisplayName** property to **Guess Incorrect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bf4e1-167">Общие переходы также можно создавать из в конструкторе переходов, щелкнув **добавить общий переход триггера** в нижней части конструктора, а затем выбрав требуемое целевое состояние из  **Состояния, доступные для подключения** раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-167">Shared transitions can also be created from within the transition designer by clicking **Add shared trigger transition** at the bottom of the transition designer, and then selecting the desired target state from the **Available states to connect** drop-down.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bf4e1-168">Обратите внимание, что если состояние <xref:System.Activities.Statements.Transition.Condition%2A> перехода оценивается как `false` (или все условия общего перехода триггера оцениваются как `false`), переход не выполняется, а все триггеры для всех переходов из состояния будут запланированы заново.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-168">Note that if the <xref:System.Activities.Statements.Transition.Condition%2A> of a transition evaluates to `false` (or all of the conditions of a shared trigger transition evaluate to `false`), the transition will not occur and all triggers for all the transitions from the state will be rescheduled.</span></span> <span data-ttu-id="bf4e1-169">В этом учебнике такая ситуация невозможна из-за способа настройки условий (имеются определенные действия для случая, если догадка верна или неверна).</span><span class="sxs-lookup"><span data-stu-id="bf4e1-169">In this tutorial, this situation cannot happen because of the way the conditions are configured (we have specific actions for whether the guess is correct or incorrect).</span></span>  
  
20. <span data-ttu-id="bf4e1-170">Дважды щелкните **неверное пробное** перехода в конструкторе рабочих процессов, чтобы развернуть его.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-170">Double-click the **Guess Incorrect** transition in the workflow designer to expand it.</span></span> <span data-ttu-id="bf4e1-171">Обратите внимание, что **триггер** уже имеет один и тот же **ReadInt** действия, который был использован **правильное пробное** перехода.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-171">Note that the **Trigger** is already set to the same **ReadInt** activity that was used by the **Guess Correct** transition.</span></span>  
  
21. <span data-ttu-id="bf4e1-172">Введите следующее выражение в **условие** поле значения свойства.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-172">Type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. <span data-ttu-id="bf4e1-173">Перетащите **Если** действия из **поток управления** раздел **элементов** и поместите его **действия** перехода.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-173">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Action** section of the transition.</span></span>  
  
23. <span data-ttu-id="bf4e1-174">Введите следующее выражение в **Если** действия **условие** поле значения свойства.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-174">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
24. <span data-ttu-id="bf4e1-175">Перетащите два **WriteLine** действия из **примитивы** раздел **элементов** и разместите их так, чтобы одно находилось в **затем** раздела **Если** действия, а другое — в **Else** раздела.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-175">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the **If** activity, and one is in the **Else** section.</span></span>  
  
25. <span data-ttu-id="bf4e1-176">Нажмите кнопку **WriteLine** действия в **затем** чтобы выбрать его и введите следующее выражение в **текст** поле значения свойства.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-176">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too low."  
    ```  
  
26. <span data-ttu-id="bf4e1-177">Нажмите кнопку **WriteLine** действия в **Else** чтобы выбрать его и введите следующее выражение в **текст** поле значения свойства.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-177">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too high."  
    ```  
  
27. <span data-ttu-id="bf4e1-178">Возврат к общему состояния машины представление в конструкторе рабочих процессов, щелкнув **StateMachine** на экране навигатора отображать в верхней части конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-178">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
     <span data-ttu-id="bf4e1-179">В следующем примере показан завершенный рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-179">The following example illustrates the completed workflow.</span></span>  
  
     <span data-ttu-id="bf4e1-180">![Завершения рабочего процесса конечного автомата](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")</span><span class="sxs-lookup"><span data-stu-id="bf4e1-180">![Completed State Machine Workflow](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")</span></span>  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="bf4e1-181">Построение рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="bf4e1-181">To build the workflow</span></span>  
  
1.  <span data-ttu-id="bf4e1-182">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="bf4e1-182">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="bf4e1-183">Инструкции о том, как запустить рабочий процесс, см. следующий раздел [как: запуск рабочего процесса](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="bf4e1-183">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span> <span data-ttu-id="bf4e1-184">Если вы уже выполнили [как: запуск рабочего процесса](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) пошаговое с другой стиль рабочего процесса и будет выполняться с помощью рабочего потока конечного компьютера на этом шаге, перейдите к [для построения и запуска приложения](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) раздел [как: запуск рабочего процесса](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="bf4e1-184">If you have already completed the [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the state machine workflow from this step, skip ahead to the [To build and run the application](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf4e1-185">См. также</span><span class="sxs-lookup"><span data-stu-id="bf4e1-185">See Also</span></span>  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [<span data-ttu-id="bf4e1-186">Программирование в Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="bf4e1-186">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [<span data-ttu-id="bf4e1-187">Разработка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="bf4e1-187">Designing Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [<span data-ttu-id="bf4e1-188">Руководство по началу работы</span><span class="sxs-lookup"><span data-stu-id="bf4e1-188">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [<span data-ttu-id="bf4e1-189">Практическое руководство. Создание действия</span><span class="sxs-lookup"><span data-stu-id="bf4e1-189">How to: Create an Activity</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [<span data-ttu-id="bf4e1-190">Практическое руководство. Запуск рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="bf4e1-190">How to: Run a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
