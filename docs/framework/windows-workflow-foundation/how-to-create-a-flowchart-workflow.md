---
title: "Как создать рабочий процесс блок-схемы"
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
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b7a8eab16b089597eecc03896f86827aae1ad85
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-flowchart-workflow"></a><span data-ttu-id="9b6f6-102">Как создать рабочий процесс блок-схемы</span><span class="sxs-lookup"><span data-stu-id="9b6f6-102">How to: Create a Flowchart Workflow</span></span>
<span data-ttu-id="9b6f6-103">Рабочие процессы могут создаваться как из встроенных, так и из пользовательских действий.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="9b6f6-104">В этом разделе шаги по созданию рабочего процесса, который использует оба встроенных действий, такие как <xref:System.Activities.Statements.Flowchart> действия и пользовательских действий из предыдущего [как: создается действие](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="9b6f6-105">Рабочий процесс моделирует игру по угадыванию числа.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b6f6-106">Каждый раздел в учебнике «Приступая к работе» построен на основе предыдущих разделов.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="9b6f6-107">Для изучения этого раздела, необходимо сначала выполнить [как: создается действие](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="9b6f6-107">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b6f6-108">Чтобы скачать завершенную версию учебника, см. раздел [Windows Workflow Foundation (WF45), учебник "Приступая к работе"](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="9b6f6-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="9b6f6-109">Создание рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9b6f6-109">To create the workflow</span></span>  
  
1.  <span data-ttu-id="9b6f6-110">Щелкните правой кнопкой мыши **NumberGuessWorkflowActivities** в **обозревателе решений** и выберите **добавить**, **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2.  <span data-ttu-id="9b6f6-111">В **установленные**, **общих элементов** выберите **рабочего процесса**.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="9b6f6-112">Выберите **действия** из **рабочего процесса** списка.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3.  <span data-ttu-id="9b6f6-113">Тип `FlowchartNumberGuessWorkflow` в **имя** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-113">Type `FlowchartNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4.  <span data-ttu-id="9b6f6-114">Перетащите **блок-схема** действия из **блок-схема** раздел **элементов** и поместите его в **Перетащите сюда действие** метки на область конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-114">Drag a **Flowchart** activity from the **Flowchart** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="9b6f6-115">Создание переменных и аргументов рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9b6f6-115">To create the workflow variables and arguments</span></span>  
  
1.  <span data-ttu-id="9b6f6-116">Дважды щелкните **FlowchartNumberGuessWorkflow.xaml** в **обозревателе решений** для отображения рабочего процесса в конструкторе, если он еще не отображается.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-116">Double-click **FlowchartNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2.  <span data-ttu-id="9b6f6-117">Нажмите кнопку **аргументы** в нижнем левом углу конструктора рабочих процессов для отображения **аргументы** области.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3.  <span data-ttu-id="9b6f6-118">Нажмите кнопку **создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-118">Click **Create Argument**.</span></span>  
  
4.  <span data-ttu-id="9b6f6-119">Тип `MaxNumber` в **имя** выберите **в** из **направление** раскрывающемся списке выберите **Int32** из **Тип аргумента** раскрывающегося списка и нажмите клавишу ВВОД, чтобы сохранить аргумент.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5.  <span data-ttu-id="9b6f6-120">Нажмите кнопку **создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-120">Click **Create Argument**.</span></span>  
  
6.  <span data-ttu-id="9b6f6-121">Тип `Turns` в **имя** поле, расположенном под только что добавленном `MaxNumber` аргумента выберите **Out** из **направление** раскрывающегося списка, выберите  **Int32** из **тип аргумента** раскрывающегося списка и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="9b6f6-122">Нажмите кнопку **аргументы** в нижнем левом углу конструктора действий, чтобы закрыть **аргументы** области.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8.  <span data-ttu-id="9b6f6-123">Нажмите кнопку **переменных** в нижнем левом углу конструктора рабочих процессов для отображения **переменных** области.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="9b6f6-124">Нажмите кнопку **создания переменной**.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="9b6f6-125">Если не **создать переменную** поле отображается, щелкните <xref:System.Activities.Statements.Flowchart> действие в рабочей области конструктора рабочих процессов, чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.Flowchart> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="9b6f6-126">Тип `Guess` в **имя** выберите **Int32** из **тип переменной** раскрывающегося списка и нажмите клавишу ВВОД, чтобы сохранить переменную.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="9b6f6-127">Нажмите кнопку **создания переменной**.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="9b6f6-128">Тип `Target` в **имя** выберите **Int32** из **тип переменной** раскрывающегося списка и нажмите клавишу ВВОД, чтобы сохранить переменную.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="9b6f6-129">Нажмите кнопку **переменных** в нижнем левом углу конструктора действий, чтобы закрыть **переменных** области.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="9b6f6-130">Добавление действий рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9b6f6-130">To add the workflow activities</span></span>  
  
1.  <span data-ttu-id="9b6f6-131">Перетащите **назначить** действия из **примитивы** раздел **элементов** и наведите его на **запустить** узел, который находится в верхней части Блок-схема.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and hover it over the **Start** node, which is at the top of the flowchart.</span></span> <span data-ttu-id="9b6f6-132">При **назначить** действия находится над **запустить** узел, появятся три треугольника вокруг **запустить** узла.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-132">When the **Assign** activity is over the **Start** node, three triangles will appear around the **Start** node.</span></span> <span data-ttu-id="9b6f6-133">Удалить **назначить** на треугольник непосредственно под **запустить** узла.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-133">Drop the **Assign** activity on the triangle that is directly below the **Start** node.</span></span> <span data-ttu-id="9b6f6-134">Это свяжет два элемента одновременно и обозначает **назначить** действия как первое действие в блок-схеме.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-134">This will link the two items together and designates the **Assign** activity as the first activity in the flowchart.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9b6f6-135">Действия можно также указывать в качестве начального действия в рабочем процессе, вручную связав их с действием в начальном узле.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-135">Activities can also be indicated as the starting activity in the workflow by manually linking them activity to the start node.</span></span> <span data-ttu-id="9b6f6-136">Для этого наведите указатель мыши **запустить** узел, выберите один из прямоугольников, появляющихся при наведении указателя мыши **запустить** узла и перетащите соединительную линию до нужного действия и поместите его на одном из появившихся прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-136">To do this, hover the mouse over the **Start** node, click one of the rectangles that appear when the mouse is over the **Start** node, and drag the connecting line down to the desired activity and drop it on one of the rectangles that appear.</span></span> <span data-ttu-id="9b6f6-137">Кроме того, можно назначить действие в качестве начального действия, щелкнув правой кнопкой мыши ИТ и выбрав **задать в качестве начального узла**.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-137">You can also designate and activity as the starting activity by right-clicking the it and choosing **Set as Start Node**.</span></span>  
  
2.  <span data-ttu-id="9b6f6-138">Тип `Target` в **для** поле и следующее выражение в **введите выражение C#** или **введите выражение VB** поле.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-138">Type `Target` into the **To** box and the following expression into the **Enter a C# Expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="9b6f6-139">Если **элементов** окно не отображается, выберите **элементов** из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-139">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="9b6f6-140">Перетащите **Prompt** действия из **NumberGuessWorkflowActivities** раздел **элементов**, поместите его под **назначить** действия из предыдущего шага и подключите **Prompt** действие **назначить** действия.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-140">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox**, drop it below the **Assign** activity from the previous step, and connect the **Prompt** activity to the **Assign** activity.</span></span> <span data-ttu-id="9b6f6-141">Соединить два действия можно тремя способами.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-141">There are three ways to connect the two activities.</span></span> <span data-ttu-id="9b6f6-142">Первый способ — подключить их при удалении **Prompt** в рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-142">The first way is to connect them as you drop the **Prompt** activity on the workflow.</span></span> <span data-ttu-id="9b6f6-143">Перетаскивая **Prompt** рабочий процесс, наведите его на **назначить** действия и поместите его в один из четырех треугольников, появляющихся, когда **Prompt** Действие находится над **назначить** действия.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-143">As you are dragging the **Prompt** activity to the workflow, hover it over the **Assign** activity and drop it onto one of the four triangles that appear when the **Prompt** activity is over the **Assign** activity.</span></span> <span data-ttu-id="9b6f6-144">Второй способ — сбросить **Prompt** в рабочем процессе в нужном месте.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-144">The second way is to drop the **Prompt** activity onto the workflow at the desired location.</span></span> <span data-ttu-id="9b6f6-145">Затем наведите указатель мыши **назначить** и перетащите один из прямоугольников, отображается вплоть до **Prompt** действия.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-145">Then, hover the mouse over the **Assign** activity and drag one of the rectangles that appears down to the **Prompt** activity.</span></span> <span data-ttu-id="9b6f6-146">Перетащите указатель мыши, чтобы соединительная линия от **назначить** соединилась с одним из прямоугольников **Prompt** действия, а затем отпустите кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-146">Drag the mouse so that the connecting line from the **Assign** activity connects to one of the rectangles of the **Prompt** activity, and then release the mouse button.</span></span> <span data-ttu-id="9b6f6-147">Третий способ похож на первый способ, но вместо перетаскивания **Prompt** действия из **элементов**, перетащите его из его расположения в рабочей области конструктора рабочих процессов, наведите указатель мыши на  **Назначьте** действия и поместите его в одном из появившихся треугольников.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-147">The third way is very similar to the first way, except that instead of dragging the **Prompt** activity from the **Toolbox**, you drag it from its location on the workflow design surface, hover it over the **Assign** activity, and drop it onto one of the triangles that appears.</span></span>  
  
4.  <span data-ttu-id="9b6f6-148">В **окно свойств** для **Prompt** введите `"EnterGuess"` кавычки, в том числе **BookmarkName** поле значения свойства.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-148">In the **Properties Window** for the **Prompt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box.</span></span> <span data-ttu-id="9b6f6-149">Тип `Guess` в **результат** поле значения свойства и введите следующее выражение в **текст** поле свойства.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-149">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="9b6f6-150">Если **окно свойств** не отображается, выберите **окно свойств** из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-150">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="9b6f6-151">Перетащите **назначить** действия из **примитивы** раздел **элементов** и соедините его с помощью одного из методов, описанных в предыдущем шаге, чтобы оно было под  **Запрос** действия.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-151">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and connect it using one of the methods described in the previous step so that it is below the **Prompt** activity.</span></span>  
  
6.  <span data-ttu-id="9b6f6-152">Тип `Turns` в **для** поле и `Turns + 1` в **введите выражение C#** или **введите выражение VB** поле.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-152">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression**  or **Enter a VB expression** box.</span></span>  
  
7.  <span data-ttu-id="9b6f6-153">Перетащите **FlowDecision** из **блок-схема** раздел **элементов** и соедините его **назначить** действия.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-153">Drag a **FlowDecision** from the **Flowchart** section of the **Toolbox** and connect it below the **Assign** activity.</span></span> <span data-ttu-id="9b6f6-154">В **окно свойств**, введите следующее выражение в **условие** поле значения свойства.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-154">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8.  <span data-ttu-id="9b6f6-155">Перетащите еще одно **FlowDecision** действия из **элементов** и поместите его под первым действием.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-155">Drag another **FlowDecision** activity from the **Toolbox** and drop it below the first one.</span></span> <span data-ttu-id="9b6f6-156">Соедините два действия путем перетаскивания из прямоугольника, который обозначен **False** в верхней части страницы **FlowDecision** действия в прямоугольник в верхней части второго **FlowDecision**действия.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-156">Connect the two activities by dragging from the rectangle that is labeled **False** on the top **FlowDecision** activity to the rectangle at the top of the second **FlowDecision** activity.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="9b6f6-157">Если вы не видите **True** и **False** метки на **FlowDecision**, наведите указатель мыши **FlowDecision**.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-157">If you do not see the **True** and **False** labels on the **FlowDecision**, hover the mouse over the **FlowDecision**.</span></span>  
  
9. <span data-ttu-id="9b6f6-158">Нажмите вторую кнопку **FlowDecision** действия, чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-158">Click the second **FlowDecision** activity to select it.</span></span> <span data-ttu-id="9b6f6-159">В **окно свойств**, введите следующее выражение в **условие** поле значения свойства.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-159">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
10. <span data-ttu-id="9b6f6-160">Перетащите два **WriteLine** действия из **примитивы** раздел **элементов** и разместите их так, чтобы они находились рядом друг с другом под двумя **FlowDecision**  действий.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-160">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that they are side by side below the two **FlowDecision** activities.</span></span> <span data-ttu-id="9b6f6-161">Подключение **True** нижнего действия **FlowDecision** с самым левым действием **WriteLine** действия и **False** действие правое **WriteLine** действия.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-161">Connect the **True** action of the bottom **FlowDecision** activity to the leftmost **WriteLine** activity, and the **False** action to the rightmost **WriteLine** activity.</span></span>  
  
11. <span data-ttu-id="9b6f6-162">Щелкните самое левое **WriteLine** действия, чтобы выбрать его и введите следующее выражение в **текст** поле значения свойства **окно свойств**.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-162">Click the leftmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```
    "Your guess is too low."  
    ```  
  
12. <span data-ttu-id="9b6f6-163">Подключение **WriteLine** левую часть **Prompt** действия, расположенных над ним.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-163">Connect the **WriteLine** to the left side of the **Prompt** activity that is above it.</span></span>  
  
13. <span data-ttu-id="9b6f6-164">Щелкните самое правое **WriteLine** действия, чтобы выбрать его и введите следующее выражение в **текст** поле значения свойства **окно свойств**.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-164">Click the rightmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```
    "Your guess is too high."  
    ```  
  
14. <span data-ttu-id="9b6f6-165">Подключение **WriteLine** действия правую часть **Prompt** действия над ним.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-165">Connect the **WriteLine** activity to the right side of the **Prompt** activity above it.</span></span>  
  
     <span data-ttu-id="9b6f6-166">В следующем примере показан завершенный рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-166">The following example illustrates the completed workflow.</span></span>  
  
     <span data-ttu-id="9b6f6-167">![Завершено Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/media/gettingstartedtutorialcompletedflowchart.PNG "GettingStartedTutorialCompletedFlowchart")</span><span class="sxs-lookup"><span data-stu-id="9b6f6-167">![Completed Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/media/gettingstartedtutorialcompletedflowchart.PNG "GettingStartedTutorialCompletedFlowchart")</span></span>  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="9b6f6-168">Построение рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9b6f6-168">To build the workflow</span></span>  
  
1.  <span data-ttu-id="9b6f6-169">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-169">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="9b6f6-170">Инструкции о том, как запустить рабочий процесс, см. следующий раздел [как: запуск рабочего процесса](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="9b6f6-170">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span> <span data-ttu-id="9b6f6-171">Если вы уже выполнили [как: запуск рабочего процесса](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) пошаговое с другой стиль рабочего процесса и будет выполняться с помощью блок-схема рабочего процесса на этом шаге, перейдите к [для построения и запуска приложения](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication)раздел [как: запуск рабочего процесса](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="9b6f6-171">If you have already completed the [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the flowchart workflow from this step, skip ahead to the [To build and run the application](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b6f6-172">См. также</span><span class="sxs-lookup"><span data-stu-id="9b6f6-172">See Also</span></span>  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [<span data-ttu-id="9b6f6-173">Программирование в Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="9b6f6-173">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [<span data-ttu-id="9b6f6-174">Разработка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="9b6f6-174">Designing Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [<span data-ttu-id="9b6f6-175">Руководство по началу работы</span><span class="sxs-lookup"><span data-stu-id="9b6f6-175">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [<span data-ttu-id="9b6f6-176">Практическое руководство. Создание действия</span><span class="sxs-lookup"><span data-stu-id="9b6f6-176">How to: Create an Activity</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [<span data-ttu-id="9b6f6-177">Практическое руководство. Запуск рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9b6f6-177">How to: Run a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
