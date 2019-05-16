---
title: Практическое руководство. Создание действия
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: 6d74af6af6cea0d65c33db67ecbfd71ac1d5c346
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636944"
---
# <a name="how-to-create-an-activity"></a><span data-ttu-id="8f510-102">Практическое руководство. Создание действия</span><span class="sxs-lookup"><span data-stu-id="8f510-102">How to: Create an Activity</span></span>

<span data-ttu-id="8f510-103">Действия являются базовой единицей режима работы в [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f510-103">Activities are the core unit of behavior in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="8f510-104">Логика выполнения действия может быть реализована в управляемом коде или с помощью других действий.</span><span class="sxs-lookup"><span data-stu-id="8f510-104">The execution logic of an activity can be implemented in managed code or it can be implemented by using other activities.</span></span> <span data-ttu-id="8f510-105">В этом разделе показано создание двух действий.</span><span class="sxs-lookup"><span data-stu-id="8f510-105">This topic demonstrates how to create two activities.</span></span> <span data-ttu-id="8f510-106">Первое действие - простое действие с использованием кода для реализации логики выполнения.</span><span class="sxs-lookup"><span data-stu-id="8f510-106">The first activity is a simple activity that uses code to implement its execution logic.</span></span> <span data-ttu-id="8f510-107">Реализация второго действия определяется с помощью других действий.</span><span class="sxs-lookup"><span data-stu-id="8f510-107">The implementation of the second activity is defined by using other activities.</span></span> <span data-ttu-id="8f510-108">Эти действия используются в следующих шагах учебника.</span><span class="sxs-lookup"><span data-stu-id="8f510-108">These activities are used in following steps in the tutorial.</span></span>

> [!NOTE]
> <span data-ttu-id="8f510-109">Чтобы скачать завершенную версию учебника, см. раздел [Windows Workflow Foundation (WF45), учебник "Приступая к работе"](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="8f510-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="create-the-activity-library-project"></a><span data-ttu-id="8f510-110">Создание проекта библиотеки действий</span><span class="sxs-lookup"><span data-stu-id="8f510-110">Create the activity library project</span></span>

1. <span data-ttu-id="8f510-111">Откройте Visual Studio и выберите **New** > **проекта** из **файл** меню.</span><span class="sxs-lookup"><span data-stu-id="8f510-111">Open Visual Studio and choose **New** > **Project** from the **File** menu.</span></span>

2. <span data-ttu-id="8f510-112">В **новый проект** диалогового окна в разделе **установленные** категорию **Visual C#** > **рабочего процесса** (или **Visual Basic** > **рабочего процесса**).</span><span class="sxs-lookup"><span data-stu-id="8f510-112">In the **New Project** dialog, under the **Installed** category, select **Visual C#** > **Workflow** (or **Visual Basic** > **Workflow**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="8f510-113">Если вы не видите **рабочего процесса** Категория шаблона, может потребоваться установить **Windows Workflow Foundation** компонент Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8f510-113">If you don't see the **Workflow** template category, you may need to install the **Windows Workflow Foundation** component of Visual Studio.</span></span> <span data-ttu-id="8f510-114">Выберите **открыть установщик Visual Studio** ссылку в левой части **новый проект** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="8f510-114">Choose the **Open Visual Studio Installer** link on the left-hand side of the **New Project** dialog.</span></span> <span data-ttu-id="8f510-115">В Visual Studio Installer, выберите **отдельные компоненты** вкладки. Затем в разделе **действия разработки** категорию **Windows Workflow Foundation** компонента.</span><span class="sxs-lookup"><span data-stu-id="8f510-115">In Visual Studio Installer, select the **Individual components** tab. Then, under the **Development activities** category, select the **Windows Workflow Foundation** component.</span></span> <span data-ttu-id="8f510-116">Выберите **изменить** для установки компонента.</span><span class="sxs-lookup"><span data-stu-id="8f510-116">Choose **Modify** to install the component.</span></span>

3. <span data-ttu-id="8f510-117">Выберите **библиотеки действий** шаблона проекта.</span><span class="sxs-lookup"><span data-stu-id="8f510-117">Select the **Activity Library** project template.</span></span> <span data-ttu-id="8f510-118">Тип `NumberGuessWorkflowActivities` в **имя** поле и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8f510-118">Type `NumberGuessWorkflowActivities` in the **Name** box and then click **OK**.</span></span>

4. <span data-ttu-id="8f510-119">Щелкните правой кнопкой мыши **Activity1.xaml** в **обозревателе решений** и выберите **удалить**.</span><span class="sxs-lookup"><span data-stu-id="8f510-119">Right-click **Activity1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="8f510-120">Нажмите кнопку **ОК** для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="8f510-120">Click **OK** to confirm.</span></span>

## <a name="create-the-readint-activity"></a><span data-ttu-id="8f510-121">Создание действия ReadInt</span><span class="sxs-lookup"><span data-stu-id="8f510-121">Create the ReadInt activity</span></span>

1. <span data-ttu-id="8f510-122">Выберите **Добавление нового элемента** из **проекта** меню.</span><span class="sxs-lookup"><span data-stu-id="8f510-122">Choose **Add New Item** from the **Project** menu.</span></span>

2. <span data-ttu-id="8f510-123">В **установленные** > **общих элементов** выберите **рабочего процесса**.</span><span class="sxs-lookup"><span data-stu-id="8f510-123">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="8f510-124">Выберите **действие кода** из **рабочего процесса** списка.</span><span class="sxs-lookup"><span data-stu-id="8f510-124">Select **Code Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="8f510-125">Тип `ReadInt` в **имя** поле и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="8f510-125">Type `ReadInt` into the **Name** box and then click **Add**.</span></span>

4. <span data-ttu-id="8f510-126">Замените существующее определение `ReadInt` следующим определением.</span><span class="sxs-lookup"><span data-stu-id="8f510-126">Replace the existing `ReadInt` definition with the following definition.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]

    > [!NOTE]
    > <span data-ttu-id="8f510-127">Действие `ReadInt` является производным от <xref:System.Activities.NativeActivity%601>, а не от <xref:System.Activities.CodeActivity>, которое задается по умолчанию для шаблона действия кода.</span><span class="sxs-lookup"><span data-stu-id="8f510-127">The `ReadInt` activity derives from <xref:System.Activities.NativeActivity%601> instead of <xref:System.Activities.CodeActivity>, which is the default for the code activity template.</span></span> <span data-ttu-id="8f510-128"><xref:System.Activities.CodeActivity%601> можно использовать, если действие возвращает один результат, который предоставляется с помощью аргумента <xref:System.Activities.Activity%601.Result%2A>. Однако <xref:System.Activities.CodeActivity%601> не поддерживает использование закладок, поэтому используется <xref:System.Activities.NativeActivity%601>.</span><span class="sxs-lookup"><span data-stu-id="8f510-128"><xref:System.Activities.CodeActivity%601> can be used if the activity provides a single result, which is exposed through the <xref:System.Activities.Activity%601.Result%2A> argument, but <xref:System.Activities.CodeActivity%601> does not support the use of bookmarks, so <xref:System.Activities.NativeActivity%601> is used.</span></span>

## <a name="create-the-prompt-activity"></a><span data-ttu-id="8f510-129">Создание действия Prompt</span><span class="sxs-lookup"><span data-stu-id="8f510-129">Create the Prompt activity</span></span>

1. <span data-ttu-id="8f510-130">Нажмите клавишу **Ctrl**+**Shift**+**B** для сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="8f510-130">Press **Ctrl**+**Shift**+**B** to build the project.</span></span> <span data-ttu-id="8f510-131">При сборке проекта включается действие `ReadInt`, которое будет использоваться для построения пользовательского действия, начиная с этого шага.</span><span class="sxs-lookup"><span data-stu-id="8f510-131">Building the project enables the `ReadInt` activity in this project to be used to build the custom activity from this step.</span></span>

2. <span data-ttu-id="8f510-132">Выберите **Добавление нового элемента** из **проекта** меню.</span><span class="sxs-lookup"><span data-stu-id="8f510-132">Choose **Add New Item** from the **Project** menu.</span></span>

3. <span data-ttu-id="8f510-133">В **установленные** > **общих элементов** выберите **рабочего процесса**.</span><span class="sxs-lookup"><span data-stu-id="8f510-133">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="8f510-134">Выберите **действия** из **рабочего процесса** списка.</span><span class="sxs-lookup"><span data-stu-id="8f510-134">Select **Activity** from the **Workflow** list.</span></span>

4. <span data-ttu-id="8f510-135">Тип `Prompt` в **имя** поле и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="8f510-135">Type `Prompt` into the **Name** box and then click **Add**.</span></span>

5. <span data-ttu-id="8f510-136">Дважды щелкните **Prompt.xaml** в **обозревателе решений** чтобы отобразить его в конструкторе, если он еще не отображается.</span><span class="sxs-lookup"><span data-stu-id="8f510-136">Double-click **Prompt.xaml** in **Solution Explorer** to display it in the designer if it is not already displayed.</span></span>

6. <span data-ttu-id="8f510-137">Нажмите кнопку **аргументы** в нижнем левом углу конструктора действий для отображения **аргументы** области.</span><span class="sxs-lookup"><span data-stu-id="8f510-137">Click **Arguments** in the lower-left side of the activity designer to display the **Arguments** pane.</span></span>

7. <span data-ttu-id="8f510-138">Нажмите кнопку **создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="8f510-138">Click **Create Argument**.</span></span>

8. <span data-ttu-id="8f510-139">Тип `BookmarkName` в **имя** выберите **в** из **направление** стрелку раскрывающегося списка выберите **строка** из **Тип аргумента** стрелку раскрывающегося списка и нажмите клавишу **ввод** чтобы сохранить аргумент.</span><span class="sxs-lookup"><span data-stu-id="8f510-139">Type `BookmarkName` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

9. <span data-ttu-id="8f510-140">Нажмите кнопку **создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="8f510-140">Click **Create Argument**.</span></span>

10. <span data-ttu-id="8f510-141">Тип `Result` в **имя** окно, в котором находится под только что добавленного `BookmarkName` аргумента выберите **Out** из **направление** раскрывающемся списке выберите **Int32** из **тип аргумента** стрелку раскрывающегося списка и нажмите клавишу **ввод**.</span><span class="sxs-lookup"><span data-stu-id="8f510-141">Type `Result` into the **Name** box that is underneath the newly added `BookmarkName` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press **Enter**.</span></span>

11. <span data-ttu-id="8f510-142">Нажмите кнопку **создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="8f510-142">Click **Create Argument**.</span></span>

12. <span data-ttu-id="8f510-143">Тип `Text` в **имя** выберите **в** из **направление** стрелку раскрывающегося списка выберите **строка** из **Тип аргумента** стрелку раскрывающегося списка и нажмите клавишу **ввод** чтобы сохранить аргумент.</span><span class="sxs-lookup"><span data-stu-id="8f510-143">Type `Text` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

     <span data-ttu-id="8f510-144">Эти три аргумента связаны с соответствующими аргументами действий <xref:System.Activities.Statements.WriteLine> и `ReadInt`, которые добавляются к действию `Prompt` на следующих этапах.</span><span class="sxs-lookup"><span data-stu-id="8f510-144">These three arguments are bound to the corresponding arguments of the <xref:System.Activities.Statements.WriteLine> and `ReadInt` activities that are added to the `Prompt` activity in the following steps.</span></span>

13. <span data-ttu-id="8f510-145">Нажмите кнопку **аргументы** в нижнем левом углу конструктора действий, чтобы закрыть **аргументы** области.</span><span class="sxs-lookup"><span data-stu-id="8f510-145">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

14. <span data-ttu-id="8f510-146">Перетащите **последовательности** действия из **поток управления** раздел **элементов** и сбросьте его в **Перетащите сюда действие** метку **Prompt** конструктора действий.</span><span class="sxs-lookup"><span data-stu-id="8f510-146">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Prompt** activity designer.</span></span>

    > [!TIP]
    > <span data-ttu-id="8f510-147">Если **элементов** окно не отображается, выберите **элементов** из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="8f510-147">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

15. <span data-ttu-id="8f510-148">Перетащите **WriteLine** действия из **примитивы** раздел **элементов** и сбросьте его в **Перетащите сюда действие** метку **Последовательности** действия.</span><span class="sxs-lookup"><span data-stu-id="8f510-148">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Sequence** activity.</span></span>

16. <span data-ttu-id="8f510-149">Привязать **текст** аргумент **WriteLine** действие **текст** аргумент **Prompt** действия, введя `Text` в **введите выражение C#** или **введите выражение VB** поле **свойства** окна, а затем нажмите клавишу **вкладке** ключ два раза.</span><span class="sxs-lookup"><span data-stu-id="8f510-149">Bind the **Text** argument of the **WriteLine** activity to the **Text** argument of the **Prompt** activity by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box in the **Properties** window, and then press the **Tab** key two times.</span></span> <span data-ttu-id="8f510-150">При этом окно элементов списка технологии IntelliSense закрывается, а значение свойства сохраняется посредством перемещения выбора вне свойства.</span><span class="sxs-lookup"><span data-stu-id="8f510-150">This dismisses the IntelliSense list members window and saves the property value by moving the selection off the property.</span></span> <span data-ttu-id="8f510-151">Это свойство также можно задать, введя `Text` в **введите выражение C#** или **введите выражение VB** поле в самом действии.</span><span class="sxs-lookup"><span data-stu-id="8f510-151">This property can also be set by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box on the activity itself.</span></span>

    > [!TIP]
    > <span data-ttu-id="8f510-152">Если **окно "Свойства"** не отображается, выберите **окно "Свойства"** из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="8f510-152">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

17. <span data-ttu-id="8f510-153">Перетащите **ReadInt** действия из **NumberGuessWorkflowActivities** раздел **элементов** и поместите его **последовательности** действия, чтобы оно следовало **WriteLine** действия.</span><span class="sxs-lookup"><span data-stu-id="8f510-153">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the **WriteLine** activity.</span></span>

18. <span data-ttu-id="8f510-154">Привязать **BookmarkName** аргумент **ReadInt** действие **BookmarkName** аргумент **Prompt** действия, введя `BookmarkName` в **введите выражение VB** поле справа от **BookmarkName** аргумента в **окно "Свойства"**, а затем нажмите клавишу **Вкладке** два раза, чтобы закрыть окно элементов списка IntelliSense и сохранить свойство ключа.</span><span class="sxs-lookup"><span data-stu-id="8f510-154">Bind the **BookmarkName** argument of the **ReadInt** activity to the **BookmarkName** argument of the **Prompt** activity by typing `BookmarkName` into the **Enter a VB expression** box to the right of the **BookmarkName** argument in the **Properties Window**, and then press the **Tab** key two times to close the IntelliSense list members window and save the property.</span></span>

19. <span data-ttu-id="8f510-155">Привязать **результат** аргумент **ReadInt** действие **результат** аргумент **Prompt** действия, введя `Result` в **введите выражение VB** поле справа от **результат** аргумента в **окно "Свойства"**, а затем нажмите клавишу **вкладке** ключа два раза.</span><span class="sxs-lookup"><span data-stu-id="8f510-155">Bind the **Result** argument of the **ReadInt** activity to the **Result** argument of the **Prompt** activity by typing `Result` into the **Enter a VB expression** box to the right of the **Result** argument in the **Properties Window**, and then press the **Tab** key two times.</span></span>

20. <span data-ttu-id="8f510-156">Нажмите клавишу **Ctrl**+**Shift**+**B** для сборки решения.</span><span class="sxs-lookup"><span data-stu-id="8f510-156">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8f510-157">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="8f510-157">Next steps</span></span>

<span data-ttu-id="8f510-158">Инструкции по созданию рабочего процесса с помощью этих действий см. Далее в этом руководстве, [как: Создание рабочего процесса](how-to-create-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="8f510-158">For instructions on how to create a workflow by using these activities, see the next step in the tutorial, [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8f510-159">См. также</span><span class="sxs-lookup"><span data-stu-id="8f510-159">See also</span></span>

- <xref:System.Activities.CodeActivity>
- <xref:System.Activities.NativeActivity%601>
- [<span data-ttu-id="8f510-160">Разработка и реализация настраиваемых действий</span><span class="sxs-lookup"><span data-stu-id="8f510-160">Designing and Implementing Custom Activities</span></span>](designing-and-implementing-custom-activities.md)
- [<span data-ttu-id="8f510-161">Руководство по началу работы</span><span class="sxs-lookup"><span data-stu-id="8f510-161">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="8f510-162">Практическое руководство. Создание рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="8f510-162">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)
- [<span data-ttu-id="8f510-163">Использование ExpressionTextBox в пользовательском конструкторе действия</span><span class="sxs-lookup"><span data-stu-id="8f510-163">Using the ExpressionTextBox in a Custom Activity Designer</span></span>](./samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
