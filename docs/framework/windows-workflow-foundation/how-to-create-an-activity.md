---
title: "Как создать действие"
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
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 26385d91b4201820a5f6ba77b512e7bcfd5372c3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-an-activity"></a><span data-ttu-id="eb3bc-102">Как создать действие</span><span class="sxs-lookup"><span data-stu-id="eb3bc-102">How to: Create an Activity</span></span>
<span data-ttu-id="eb3bc-103">Действия являются базовой единицей режима работы в [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb3bc-103">Activities are the core unit of behavior in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="eb3bc-104">Логика выполнения действия может быть реализована в управляемом коде или с помощью других действий.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-104">The execution logic of an activity can be implemented in managed code or it can be implemented by using other activities.</span></span> <span data-ttu-id="eb3bc-105">В этом разделе показано создание двух действий.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-105">This topic demonstrates how to create two activities.</span></span> <span data-ttu-id="eb3bc-106">Первое действие - простое действие с использованием кода для реализации логики выполнения.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-106">The first activity is a simple activity that uses code to implement its execution logic.</span></span> <span data-ttu-id="eb3bc-107">Реализация второго действия определяется с помощью других действий.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-107">The implementation of the second activity is defined by using other activities.</span></span> <span data-ttu-id="eb3bc-108">Эти действия используются в следующих шагах учебника.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-108">These activities are used in following steps in the tutorial.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb3bc-109">Чтобы скачать завершенную версию учебника, см. раздел [Windows Workflow Foundation (WF45), учебник "Приступая к работе"](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="eb3bc-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-activity-library-project"></a><span data-ttu-id="eb3bc-110">Создание проекта библиотеки действия</span><span class="sxs-lookup"><span data-stu-id="eb3bc-110">To create the activity library project</span></span>  
  
1.  <span data-ttu-id="eb3bc-111">Откройте [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] и выберите **New**, **проекта** из **файл** меню.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-111">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and choose **New**,  **Project** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="eb3bc-112">Разверните **другие типы проектов** узел в **установленные**, **шаблоны** и выберите **решения Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-112">Expand the **Other Project Types** node in the **Installed**, **Templates** list and select **Visual Studio Solutions**.</span></span>  
  
3.  <span data-ttu-id="eb3bc-113">Выберите **пустое решение** из **решения Visual Studio** списка.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-113">Select **Blank Solution** from the **Visual Studio Solutions** list.</span></span> <span data-ttu-id="eb3bc-114">Убедитесь, что в раскрывающемся списке версий .NET Framework выбран пункт **.NET Framework 4.5** .</span><span class="sxs-lookup"><span data-stu-id="eb3bc-114">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="eb3bc-115">Тип `WF45GettingStartedTutorial` в **имя** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-115">Type `WF45GettingStartedTutorial` in the **Name** box and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="eb3bc-116">Щелкните правой кнопкой мыши **WF45GettingStartedTutorial** в **обозревателе решений** и выберите **добавить**, **новый проект**.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-116">Right-click **WF45GettingStartedTutorial** in **Solution Explorer** and choose **Add**, **New Project**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="eb3bc-117">Если окно **Обозреватель решений** не отображается, в меню **Вид** выберите пункт **Обозреватель решений** .</span><span class="sxs-lookup"><span data-stu-id="eb3bc-117">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="eb3bc-118">В узле **Установленные** выберите пункты **Visual C#**и **Рабочий процесс** (или **Visual Basic**и **Рабочий процесс**).</span><span class="sxs-lookup"><span data-stu-id="eb3bc-118">In the **Installed** node, select **Visual C#**, **Workflow** (or **Visual Basic**, **Workflow**).</span></span> <span data-ttu-id="eb3bc-119">Убедитесь, что **.NET Framework 4.5** выбран в [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] версии раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-119">Ensure that **.NET Framework 4.5** is selected in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] version drop-down list.</span></span> <span data-ttu-id="eb3bc-120">Выберите **библиотеки действий** из **рабочего процесса** списка.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-120">Select **Activity Library** from the **Workflow** list.</span></span> <span data-ttu-id="eb3bc-121">Тип `NumberGuessWorkflowActivities` в **имя** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-121">Type `NumberGuessWorkflowActivities` in the **Name** box and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eb3bc-122">В зависимости от того, какой язык программирования задан как основной в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], **Visual C#** или **Visual Basic** может находиться под **другие языки**узел в **установленные** узла.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-122">Depending on which programming language is configured as the primary language in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>  
  
6.  <span data-ttu-id="eb3bc-123">Щелкните правой кнопкой мыши **Activity1.xaml** в **обозревателе решений** и выберите **удалить**.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-123">Right-click **Activity1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="eb3bc-124">Нажмите кнопку **ОК** для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-124">Click **OK** to confirm.</span></span>  
  
### <a name="to-create-the-readint-activity"></a><span data-ttu-id="eb3bc-125">Создание действия ReadInt</span><span class="sxs-lookup"><span data-stu-id="eb3bc-125">To create the ReadInt activity</span></span>  
  
1.  <span data-ttu-id="eb3bc-126">Выберите **Добавление нового элемента** из **проекта** меню.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-126">Choose **Add New Item** from the **Project** menu.</span></span>  
  
2.  <span data-ttu-id="eb3bc-127">В **установленные**, **общих элементов** выберите **рабочего процесса**.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-127">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="eb3bc-128">Выберите **действие кода** из **рабочего процесса** списка.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-128">Select **Code Activity** from the **Workflow** list.</span></span>  
  
3.  <span data-ttu-id="eb3bc-129">Тип `ReadInt` в **имя** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-129">Type `ReadInt` into the **Name** box and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="eb3bc-130">Замените существующее определение `ReadInt` следующим определением.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-130">Replace the existing `ReadInt` definition with the following definition.</span></span>  
  
     [!code-csharp[CFX_WF_GettingStarted#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="eb3bc-131">Действие `ReadInt` является производным от <xref:System.Activities.NativeActivity%601>, а не от <xref:System.Activities.CodeActivity>, которое задается по умолчанию для шаблона действия кода.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-131">The `ReadInt` activity derives from <xref:System.Activities.NativeActivity%601> instead of <xref:System.Activities.CodeActivity>, which is the default for the code activity template.</span></span> <span data-ttu-id="eb3bc-132"><xref:System.Activities.CodeActivity%601> можно использовать, если действие возвращает один результат, который предоставляется с помощью аргумента <xref:System.Activities.Activity%601.Result%2A>. Однако <xref:System.Activities.CodeActivity%601> не поддерживает использование закладок, поэтому используется <xref:System.Activities.NativeActivity%601>.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-132"><xref:System.Activities.CodeActivity%601> can be used if the activity provides a single result, which is exposed through the <xref:System.Activities.Activity%601.Result%2A> argument, but <xref:System.Activities.CodeActivity%601> does not support the use of bookmarks, so <xref:System.Activities.NativeActivity%601> is used.</span></span>  
  
### <a name="to-create-the-prompt-activity"></a><span data-ttu-id="eb3bc-133">Создание действия Prompt</span><span class="sxs-lookup"><span data-stu-id="eb3bc-133">To create the Prompt activity</span></span>  
  
1.  <span data-ttu-id="eb3bc-134">Для сборки проекта нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-134">Press CTRL+SHIFT+B to build the project.</span></span> <span data-ttu-id="eb3bc-135">При сборке проекта включается действие `ReadInt`, которое будет использоваться для построения пользовательского действия, начиная с этого шага.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-135">Building the project enables the `ReadInt` activity in this project to be used to build the custom activity from this step.</span></span>  
  
2.  <span data-ttu-id="eb3bc-136">Выберите **Добавление нового элемента** из **проекта** меню.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-136">Choose **Add New Item** from the **Project** menu.</span></span>  
  
3.  <span data-ttu-id="eb3bc-137">В **установленные**, **общих элементов** выберите **рабочего процесса**.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-137">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="eb3bc-138">Выберите **действия** из **рабочего процесса** списка.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-138">Select **Activity** from the **Workflow** list.</span></span>  
  
4.  <span data-ttu-id="eb3bc-139">Тип `Prompt` в **имя** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-139">Type `Prompt` into the **Name** box and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="eb3bc-140">Дважды щелкните **Prompt.xaml** в **обозревателе решений** для его отображения в конструкторе, если он еще не отображается.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-140">Double-click **Prompt.xaml** in **Solution Explorer** to display it in the designer if it is not already displayed.</span></span>  
  
6.  <span data-ttu-id="eb3bc-141">Нажмите кнопку **аргументы** в нижнем левом углу конструктора действий для отображения **аргументы** области.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-141">Click **Arguments** in the lower-left side of the activity designer to display the **Arguments** pane.</span></span>  
  
7.  <span data-ttu-id="eb3bc-142">Нажмите кнопку **создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-142">Click **Create Argument**.</span></span>  
  
8.  <span data-ttu-id="eb3bc-143">Тип `BookmarkName` в **имя** выберите **в** из **направление** раскрывающемся списке выберите **строка** из **Тип аргумента** раскрывающегося списка и нажмите клавишу ВВОД, чтобы сохранить аргумент.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-143">Type `BookmarkName` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
9. <span data-ttu-id="eb3bc-144">Нажмите кнопку **создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-144">Click **Create Argument**.</span></span>  
  
10. <span data-ttu-id="eb3bc-145">Тип `Result` в **имя** под только что добавленном что `BookmarkName` аргумента выберите **Out** из **направление** раскрывающемся списке выберите **Int32** из **тип аргумента** раскрывающегося списка и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-145">Type `Result` into the **Name** box that is underneath the newly added `BookmarkName` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
11. <span data-ttu-id="eb3bc-146">Нажмите кнопку **создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-146">Click **Create Argument**.</span></span>  
  
12. <span data-ttu-id="eb3bc-147">Тип `Text` в **имя** выберите **в** из **направление** раскрывающемся списке выберите **строка** из **Тип аргумента** раскрывающегося списка и нажмите клавишу ВВОД, чтобы сохранить аргумент.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-147">Type `Text` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
     <span data-ttu-id="eb3bc-148">Эти три аргумента связаны с соответствующими аргументами действий <xref:System.Activities.Statements.WriteLine> и `ReadInt`, которые добавляются к действию `Prompt` на следующих этапах.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-148">These three arguments are bound to the corresponding arguments of the <xref:System.Activities.Statements.WriteLine> and `ReadInt` activities that are added to the `Prompt` activity in the following steps.</span></span>  
  
13. <span data-ttu-id="eb3bc-149">Нажмите кнопку **аргументы** в нижнем левом углу конструктора действий, чтобы закрыть **аргументы** области.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-149">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
14. <span data-ttu-id="eb3bc-150">Перетащите **последовательности** действия из **поток управления** раздел **элементов** и поместите его в **Перетащите сюда действие** метку **Prompt** конструктора действий.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-150">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Prompt** activity designer.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="eb3bc-151">Если **элементов** окно не отображается, выберите **элементов** из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-151">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
15. <span data-ttu-id="eb3bc-152">Перетащите **WriteLine** действия из **примитивы** раздел **элементов** и поместите его в **Перетащите сюда действие** метку **Последовательности** действия.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-152">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Sequence** activity.</span></span>  
  
16. <span data-ttu-id="eb3bc-153">Привязать **текст** аргумент **WriteLine** действие **текст** аргумент **Prompt** действия, введя `Text` в **введите выражение C#** или **введите выражение VB** поле **свойства** окно и нажмите клавишу TAB ключа два раза.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-153">Bind the **Text** argument of the **WriteLine** activity to the **Text** argument of the **Prompt** activity by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box in the **Properties** window, and then press the TAB key two times.</span></span> <span data-ttu-id="eb3bc-154">При этом окно элементов списка технологии IntelliSense закрывается, а значение свойства сохраняется посредством перемещения выбора вне свойства.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-154">This dismisses the IntelliSense list members window and saves the property value by moving the selection off the property.</span></span> <span data-ttu-id="eb3bc-155">Это свойство можно также задать, введя `Text` в **введите выражение C#** или **введите выражение VB** поле в самом действии.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-155">This property can also be set by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box on the activity itself.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="eb3bc-156">Если **окно свойств** не отображается, выберите **окно свойств** из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-156">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
17. <span data-ttu-id="eb3bc-157">Перетащите **ReadInt** действия из **NumberGuessWorkflowActivities** раздел **элементов** и поместите его **последовательности** действия, чтобы оно было расположено **WriteLine** действия.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-157">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the **WriteLine** activity.</span></span>  
  
18. <span data-ttu-id="eb3bc-158">Привязать **BookmarkName** аргумент **ReadInt** действие **BookmarkName** аргумент **Prompt** действия, введя `BookmarkName` в **введите выражение VB** поле справа от **BookmarkName** аргумент в **окно свойств**и нажмите клавишу TAB двух время, чтобы закрыть окно элементов списка технологии IntelliSense и сохранить свойства.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-158">Bind the **BookmarkName** argument of the **ReadInt** activity to the **BookmarkName** argument of the **Prompt** activity by typing `BookmarkName` into the **Enter a VB expression** box to the right of the **BookmarkName** argument in the **Properties Window**, and then press the TAB key two times to close the IntelliSense list members window and save the property.</span></span>  
  
19. <span data-ttu-id="eb3bc-159">Привязать **результат** аргумент **ReadInt** действие **результат** аргумент **Prompt** действия, введя `Result` в **введите выражение VB** поле справа от **результат** аргумент в **окно свойств**и затем дважды нажмите клавишу TAB.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-159">Bind the **Result** argument of the **ReadInt** activity to the **Result** argument of the **Prompt** activity by typing `Result` into the **Enter a VB expression** box to the right of the **Result** argument in the **Properties Window**, and then press the TAB key two times.</span></span>  
  
20. <span data-ttu-id="eb3bc-160">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="eb3bc-160">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="eb3bc-161">Инструкции по созданию рабочего процесса с помощью этих действий см. следующий шаг в учебнике [как: Создание рабочего процесса](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="eb3bc-161">For instructions on how to create a workflow by using these activities, see the next step in the tutorial, [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb3bc-162">См. также</span><span class="sxs-lookup"><span data-stu-id="eb3bc-162">See Also</span></span>  
 <xref:System.Activities.CodeActivity>  
 <xref:System.Activities.NativeActivity%601>  
 [<span data-ttu-id="eb3bc-163">Разработка и реализация настраиваемых действий</span><span class="sxs-lookup"><span data-stu-id="eb3bc-163">Designing and Implementing Custom Activities</span></span>](../../../docs/framework/windows-workflow-foundation/designing-and-implementing-custom-activities.md)  
 [<span data-ttu-id="eb3bc-164">Руководство по началу работы</span><span class="sxs-lookup"><span data-stu-id="eb3bc-164">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [<span data-ttu-id="eb3bc-165">Практическое руководство. Создание рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="eb3bc-165">How to: Create a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)  
 [<span data-ttu-id="eb3bc-166">Использование ExpressionTextBox в конструкторе пользовательских действий</span><span class="sxs-lookup"><span data-stu-id="eb3bc-166">Using the ExpressionTextBox in a Custom Activity Designer</span></span>](../../../docs/framework/windows-workflow-foundation/samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
