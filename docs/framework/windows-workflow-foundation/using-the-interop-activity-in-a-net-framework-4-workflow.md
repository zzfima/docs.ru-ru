---
title: Использование действия «Interop» в рабочем процессе платформы .NET Framework 4
ms.date: 03/30/2017
ms.assetid: 9bb747f0-eb33-4f70-84cd-317382372dcd
ms.openlocfilehash: 64e8aef01aefa23dc98b42ab835de097d6c222df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-interop-activity-in-a-net-framework-4-workflow"></a><span data-ttu-id="6b47d-102">Использование действия «Interop» в рабочем процессе платформы .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="6b47d-102">Using the Interop Activity in a .NET Framework 4 Workflow</span></span>
<span data-ttu-id="6b47d-103">Действия, созданные в [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] или в [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], могут использоваться в рабочем процессе [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] посредством использования действия <xref:System.Activities.Statements.Interop>.</span><span class="sxs-lookup"><span data-stu-id="6b47d-103">Activities created using [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] or [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] can be used in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow by using the <xref:System.Activities.Statements.Interop> activity.</span></span> <span data-ttu-id="6b47d-104">В этом разделе приведены общие сведения об использовании действия <xref:System.Activities.Statements.Interop>.</span><span class="sxs-lookup"><span data-stu-id="6b47d-104">This topic provides an overview of using the <xref:System.Activities.Statements.Interop> activity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b47d-105"><xref:System.Activities.Statements.Interop> Действия не отображается в области элементов конструктора рабочих процессов, если проект рабочего процесса имеет его **требуемой версии .NET Framework** задано значение **.Net Framework 4** или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="6b47d-105">The <xref:System.Activities.Statements.Interop> activity does not appear in the workflow designer toolbox unless the workflow's project has its **Target Framework** setting set to **.Net Framework 4** or later.</span></span>  
  
## <a name="using-the-interop-activity-in-net-framework-45-workflows"></a><span data-ttu-id="6b47d-106">Использование действия Interop в рабочих процессах платформы .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="6b47d-106">Using the Interop Activity in .NET Framework 4.5 Workflows</span></span>  
 <span data-ttu-id="6b47d-107">В данном разделе создается библиотека действий [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], содержащая действие `DiscountCalculator`.</span><span class="sxs-lookup"><span data-stu-id="6b47d-107">In this topic, a [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity library is created that contains a `DiscountCalculator` activity.</span></span> <span data-ttu-id="6b47d-108">Действие `DiscountCalculator` вычисляет скидку на основе стоимости приобретений и состоит из действия <xref:System.Workflow.Activities.SequenceActivity>, содержащего действие <xref:System.Workflow.Activities.PolicyActivity>.</span><span class="sxs-lookup"><span data-stu-id="6b47d-108">The `DiscountCalculator` calculates a discount based on a purchase amount and consists of a <xref:System.Workflow.Activities.SequenceActivity> that contains a <xref:System.Workflow.Activities.PolicyActivity>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b47d-109">Действие [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], создаваемое в этом разделе, использует действие <xref:System.Workflow.Activities.PolicyActivity> для реализации логики действия.</span><span class="sxs-lookup"><span data-stu-id="6b47d-109">The [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity created in this topic uses a <xref:System.Workflow.Activities.PolicyActivity> to implement the logic of the activity.</span></span> <span data-ttu-id="6b47d-110">Для использования правил в рабочем процессе [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] не обязательно использовать пользовательское действие <xref:System.Activities.Statements.Interop> или действие [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b47d-110">It is not required to use a custom [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity or the <xref:System.Activities.Statements.Interop> activity in order to use rules in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow.</span></span> <span data-ttu-id="6b47d-111">Пример использования правила в [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] рабочего процесса без использования <xref:System.Activities.Statements.Interop> действия, в разделе [действие политики в .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) образца.</span><span class="sxs-lookup"><span data-stu-id="6b47d-111">For an example of using rules in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow without using the <xref:System.Activities.Statements.Interop> activity, see the [Policy Activity in .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) sample.</span></span>  
  
#### <a name="to-create-the-net-framework-35-activity-library-project"></a><span data-ttu-id="6b47d-112">Создание проекта библиотеки действий платформы .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="6b47d-112">To create the .NET Framework 3.5 activity library project</span></span>  
  
1.  <span data-ttu-id="6b47d-113">Откройте [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] и выберите **New** и затем **проекта...**</span><span class="sxs-lookup"><span data-stu-id="6b47d-113">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and select **New** and then **Project…**</span></span> <span data-ttu-id="6b47d-114">из **файл** меню.</span><span class="sxs-lookup"><span data-stu-id="6b47d-114">from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="6b47d-115">Разверните **другие типы проектов** узел в **установленные шаблоны** области и выберите команду **решения Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-115">Expand the **Other Project Types** node in the **Installed Templates** pane and select **Visual Studio Solutions**.</span></span>  
  
3.  <span data-ttu-id="6b47d-116">Выберите **пустое решение** из **решения Visual Studio** списка.</span><span class="sxs-lookup"><span data-stu-id="6b47d-116">Select **Blank Solution** from the **Visual Studio Solutions** list.</span></span> <span data-ttu-id="6b47d-117">Тип `PolicyInteropDemo` в **имя** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-117">Type `PolicyInteropDemo` in the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="6b47d-118">Щелкните правой кнопкой мыши **PolicyInteropDemo** в **обозревателе решений** и выберите **добавить** и затем **новый проект...** .</span><span class="sxs-lookup"><span data-stu-id="6b47d-118">Right-click **PolicyInteropDemo** in **Solution Explorer** and select **Add** and then **New Project…**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="6b47d-119">Если **обозревателе решений** окно не отображается, выберите пункт **обозревателе решений** из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="6b47d-119">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="6b47d-120">В **установленные шаблоны** выберите **Visual C#** и затем **рабочего процесса**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-120">In the **Installed Templates** list, select **Visual C#** and then **Workflow**.</span></span> <span data-ttu-id="6b47d-121">Выберите **.NET Framework 3.5** в раскрывающемся списке версий .NET Framework, а затем выберите **библиотека действий рабочих процессов** из **шаблоны** списка.</span><span class="sxs-lookup"><span data-stu-id="6b47d-121">Select **.NET Framework 3.5** from the .NET Framework version drop-down list, and then select **Workflow Activity Library** from the **Templates** list.</span></span>  
  
6.  <span data-ttu-id="6b47d-122">Тип `PolicyActivityLibrary` в **имя** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-122">Type `PolicyActivityLibrary` in the **Name** box and click **OK**.</span></span>  
  
7.  <span data-ttu-id="6b47d-123">Щелкните правой кнопкой мыши **Activity1.cs** в **обозревателе решений** и выберите **удалить**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-123">Right-click **Activity1.cs** in **Solution Explorer** and select **Delete**.</span></span> <span data-ttu-id="6b47d-124">Нажмите кнопку **ОК** для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="6b47d-124">Click **OK** to confirm.</span></span>  
  
#### <a name="to-create-the-discountcalculator-activity"></a><span data-ttu-id="6b47d-125">Создание действия DiscountCalculator</span><span class="sxs-lookup"><span data-stu-id="6b47d-125">To create the DiscountCalculator activity</span></span>  
  
1.  <span data-ttu-id="6b47d-126">Щелкните правой кнопкой мыши **PolicyActivityLibrary** в **обозревателе решений** и выберите **добавить** и затем **действия...** .</span><span class="sxs-lookup"><span data-stu-id="6b47d-126">Right-click **PolicyActivityLibrary** in **Solution Explorer** and select **Add** and then **Activity…**.</span></span>  
  
2.  <span data-ttu-id="6b47d-127">Выберите **действие (с разделением кода)** из **элементы Visual C#** списка.</span><span class="sxs-lookup"><span data-stu-id="6b47d-127">Select **Activity (with code separation)** from the **Visual C# Items** list.</span></span> <span data-ttu-id="6b47d-128">Тип `DiscountCalculator` в **имя** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-128">Type `DiscountCalculator` in the **Name** box and click **OK**.</span></span>  
  
3.  <span data-ttu-id="6b47d-129">Щелкните правой кнопкой мыши **DiscountCalculator.xoml** в **обозревателе решений** и выберите **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-129">Right-click **DiscountCalculator.xoml** in **Solution Explorer** and select **View Code**.</span></span>  
  
4.  <span data-ttu-id="6b47d-130">Добавьте в класс `DiscountCalculator` приведенные ниже три свойства.</span><span class="sxs-lookup"><span data-stu-id="6b47d-130">Add the following three properties to the `DiscountCalculator` class.</span></span>  
  
    ```csharp  
    public partial class DiscountCalculator : SequenceActivity  
    {  
        public double Subtotal { get; set; }  
        public double DiscountPercent { get; set; }  
        public double Total { get; set; }  
    }  
    ```  
  
5.  <span data-ttu-id="6b47d-131">Щелкните правой кнопкой мыши **DiscountCalculator.xoml** в **обозревателе решений** и выберите **конструктор представлений**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-131">Right-click **DiscountCalculator.xoml** in **Solution Explorer** and select **View Designer**.</span></span>  
  
6.  <span data-ttu-id="6b47d-132">Перетащите **политики** действия из **Windows Workflow v3.0** раздел **элементов** и поместите его **DiscountCalculator** действия .</span><span class="sxs-lookup"><span data-stu-id="6b47d-132">Drag a **Policy** activity from the **Windows Workflow v3.0** section of the **Toolbox** and drop it in the **DiscountCalculator** activity.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="6b47d-133">Если **элементов** окно не отображается, выберите пункт **элементов** из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="6b47d-133">If the **Toolbox** window is not visible, select **Toolbox** from the **View** menu.</span></span>  
  
#### <a name="to-configure-the-rules"></a><span data-ttu-id="6b47d-134">Настройка правил</span><span class="sxs-lookup"><span data-stu-id="6b47d-134">To configure the rules</span></span>  
  
1.  <span data-ttu-id="6b47d-135">Щелкните только что добавленном **политики** действия, чтобы выбрать его, если он еще не выбран.</span><span class="sxs-lookup"><span data-stu-id="6b47d-135">Click the newly added **Policy** activity to select it, if it is not already selected.</span></span>  
  
2.  <span data-ttu-id="6b47d-136">Нажмите кнопку **RuleSetReference** свойство в **свойства** окно, чтобы выбрать ее и нажмите кнопку с многоточием справа от свойства.</span><span class="sxs-lookup"><span data-stu-id="6b47d-136">Click the **RuleSetReference** property in the **Properties** window to select it, and click the ellipsis button to the right of the property.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="6b47d-137">Если **свойства** окно не отображается, выберите **окно свойств** из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="6b47d-137">If the **Properties** window is not visible, choose **Properties Window** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="6b47d-138">Выберите **щелкните Добавить...** .</span><span class="sxs-lookup"><span data-stu-id="6b47d-138">Select **Click New…**.</span></span>  
  
4.  <span data-ttu-id="6b47d-139">Нажмите кнопку **добавить правило**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-139">Click **Add Rule**.</span></span>  
  
5.  <span data-ttu-id="6b47d-140">Введите следующее выражение в **условие** поле.</span><span class="sxs-lookup"><span data-stu-id="6b47d-140">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.Subtotal >= 50 && this.Subtotal < 100  
    ```  
  
6.  <span data-ttu-id="6b47d-141">Введите следующее выражение в **действия Then** поле.</span><span class="sxs-lookup"><span data-stu-id="6b47d-141">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.DiscountPercent = 0.075  
    ```  
  
7.  <span data-ttu-id="6b47d-142">Нажмите кнопку **добавить правило**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-142">Click **Add Rule**.</span></span>  
  
8.  <span data-ttu-id="6b47d-143">Введите следующее выражение в **условие** поле.</span><span class="sxs-lookup"><span data-stu-id="6b47d-143">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.Subtotal >= 100  
    ```  
  
9. <span data-ttu-id="6b47d-144">Введите следующее выражение в **действия Then** поле.</span><span class="sxs-lookup"><span data-stu-id="6b47d-144">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.DiscountPercent = 0.15  
    ```  
  
10. <span data-ttu-id="6b47d-145">Нажмите кнопку **добавить правило**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-145">Click **Add Rule**.</span></span>  
  
11. <span data-ttu-id="6b47d-146">Введите следующее выражение в **условие** поле.</span><span class="sxs-lookup"><span data-stu-id="6b47d-146">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.DiscountPercent > 0  
    ```  
  
12. <span data-ttu-id="6b47d-147">Введите следующее выражение в **действия Then** поле.</span><span class="sxs-lookup"><span data-stu-id="6b47d-147">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent  
    ```  
  
13. <span data-ttu-id="6b47d-148">Введите следующее выражение в **действия Else** поле.</span><span class="sxs-lookup"><span data-stu-id="6b47d-148">Type the following expression into the **Else Actions** box.</span></span>  
  
    ```  
    this.Total = this.Subtotal  
    ```  
  
14. <span data-ttu-id="6b47d-149">Нажмите кнопку **ОК** закрыть **редактор набора правил** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="6b47d-149">Click **OK** to close the **Rule Set Editor** dialog box.</span></span>  
  
15. <span data-ttu-id="6b47d-150">Убедитесь, что вновь созданные <xref:System.Workflow.Activities.Rules.RuleSet> выбран в **имя** списке и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-150">Ensure that the newly-created <xref:System.Workflow.Activities.Rules.RuleSet> is selected in the **Name** list, and click **OK**.</span></span>  
  
16. <span data-ttu-id="6b47d-151">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="6b47d-151">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
 <span data-ttu-id="6b47d-152">Правила, добавленные в действие `DiscountCalculator` в ходе выполнения этой процедуры, показаны в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="6b47d-152">The rules added to the `DiscountCalculator` activity in this procedure are shown in the following code example.</span></span>  
  
```  
Rule1: IF this.Subtotal >= 50 && this.Subtotal < 100   
       THEN this.DiscountPercent = 0.075   
  
Rule2: IF this. Subtotal >= 100   
       THEN this.DiscountPercent = 0.15   
  
Rule3: IF this.DiscountPercent > 0   
       THEN this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent   
       ELSE this.Total = this.Subtotal  
```  
  
 <span data-ttu-id="6b47d-153">При выполнении действия <xref:System.Workflow.Activities.PolicyActivity> выполняется оценка этих трех правил, которые соответственно изменяют значения свойств `Subtotal`, `DiscountPercent` и `Total` для действия `DiscountCalculator` с целью вычисления требуемой скидки.</span><span class="sxs-lookup"><span data-stu-id="6b47d-153">When the <xref:System.Workflow.Activities.PolicyActivity> executes, these three rules evaluate and modify the `Subtotal`, `DiscountPercent`, and `Total` property values of the `DiscountCalculator` activity to calculate the desired discount.</span></span>  
  
## <a name="using-the-discountcalculator-activity-with-the-interop-activity"></a><span data-ttu-id="6b47d-154">Использование действия DiscountCalculator совместно с действием Interop</span><span class="sxs-lookup"><span data-stu-id="6b47d-154">Using the DiscountCalculator Activity with the Interop Activity</span></span>  
 <span data-ttu-id="6b47d-155">Чтобы использовать действие `DiscountCalculator` в рабочем процессе [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], используется действие <xref:System.Activities.Statements.Interop>.</span><span class="sxs-lookup"><span data-stu-id="6b47d-155">To use the `DiscountCalculator` activity inside a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow, the <xref:System.Activities.Statements.Interop> activity is used.</span></span> <span data-ttu-id="6b47d-156">В данном разделе создаются два рабочих процесса (один с использованием кода и один с помощью конструктора рабочего процесса), которые демонстрируют использование действия <xref:System.Activities.Statements.Interop> совместно с действием `DiscountCalculator`.</span><span class="sxs-lookup"><span data-stu-id="6b47d-156">In this section two workflows are created, one using code and one using the workflow designer, which show how to use the <xref:System.Activities.Statements.Interop> activity with the `DiscountCalculator` activity.</span></span> <span data-ttu-id="6b47d-157">Для обоих рабочих процессов используется одно ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="6b47d-157">The same host application is used for both workflows.</span></span>  
  
#### <a name="to-create-the-host-application"></a><span data-ttu-id="6b47d-158">Создание ведущего приложения</span><span class="sxs-lookup"><span data-stu-id="6b47d-158">To create the host application</span></span>  
  
1.  <span data-ttu-id="6b47d-159">Щелкните правой кнопкой мыши **PolicyInteropDemo** в **обозревателе решений** и выберите **добавить**, а затем **новый проект...** .</span><span class="sxs-lookup"><span data-stu-id="6b47d-159">Right-click **PolicyInteropDemo** in **Solution Explorer** and select **Add**, and then **New Project…**.</span></span>  
  
2.  <span data-ttu-id="6b47d-160">Убедитесь, что **.NET Framework 4.5** выбран в раскрывающемся списке версий .NET Framework и выберите **консольное приложение рабочего процесса** из **элементы Visual C#** списка.</span><span class="sxs-lookup"><span data-stu-id="6b47d-160">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list, and select  **Workflow Console Application** from the **Visual C# Items** list.</span></span>  
  
3.  <span data-ttu-id="6b47d-161">Тип `PolicyInteropHost` в **имя** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-161">Type `PolicyInteropHost` into the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="6b47d-162">Щелкните правой кнопкой мыши **PolicyInteropHost** в **обозревателе решений** и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-162">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="6b47d-163">В **требуемой версии .NET framework** раскрывающемся списке, измените выбранный вариант с **клиентский профиль .NET Framework 4** для **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-163">In the **Target framework** drop-down list, change the selection from **.NET Framework 4 Client Profile** to **.NET Framework 4.5**.</span></span> <span data-ttu-id="6b47d-164">Нажмите кнопку **Да** для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="6b47d-164">Click **Yes** to confirm.</span></span>  
  
6.  <span data-ttu-id="6b47d-165">Щелкните правой кнопкой мыши **PolicyInteropHost** в **обозревателе решений** и выберите **добавить ссылку...** .</span><span class="sxs-lookup"><span data-stu-id="6b47d-165">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add Reference…**.</span></span>  
  
7.  <span data-ttu-id="6b47d-166">Выберите **PolicyActivityLibrary** из **проекты** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-166">Select **PolicyActivityLibrary** from the **Projects** tab and click **OK**.</span></span>  
  
8.  <span data-ttu-id="6b47d-167">Щелкните правой кнопкой мыши **PolicyInteropHost** в **обозревателе решений** и выберите **добавить ссылку...** .</span><span class="sxs-lookup"><span data-stu-id="6b47d-167">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add Reference…**.</span></span>  
  
9. <span data-ttu-id="6b47d-168">Выберите **System.Workflow.Activities**, **System.Workflow.ComponentModel**, а затем **System.Workflow.Runtime** из **.NET**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-168">Select **System.Workflow.Activities**, **System.Workflow.ComponentModel**, and then **System.Workflow.Runtime** from the **.NET** tab and click **OK**.</span></span>  
  
10. <span data-ttu-id="6b47d-169">Щелкните правой кнопкой мыши **PolicyInteropHost** в **обозревателе решений** и выберите **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-169">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Set as StartUp Project**.</span></span>  
  
11. <span data-ttu-id="6b47d-170">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="6b47d-170">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
### <a name="using-the-interop-activity-in-code"></a><span data-ttu-id="6b47d-171">Использование действия Interop в коде</span><span class="sxs-lookup"><span data-stu-id="6b47d-171">Using the Interop Activity in Code</span></span>  
 <span data-ttu-id="6b47d-172">В данном примере определение рабочего процесса создается с использованием кода, содержащего действия <xref:System.Activities.Statements.Interop> и `DiscountCalculator`.</span><span class="sxs-lookup"><span data-stu-id="6b47d-172">In this example, a workflow definition is created using code that contains the <xref:System.Activities.Statements.Interop> activity and the `DiscountCalculator` activity.</span></span> <span data-ttu-id="6b47d-173">Этот рабочий процесс вызывается с помощью <xref:System.Activities.WorkflowInvoker>, а результаты оценки правила записываются в консоль с использованием действия <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="6b47d-173">This workflow is invoked using <xref:System.Activities.WorkflowInvoker> and the results of the rule evaluation are written to the console using a <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
##### <a name="to-use-the-interop-activity-in-code"></a><span data-ttu-id="6b47d-174">Использование действия Interop в коде</span><span class="sxs-lookup"><span data-stu-id="6b47d-174">To use the Interop activity in code</span></span>  
  
1.  <span data-ttu-id="6b47d-175">Щелкните правой кнопкой мыши **Program.cs** в **обозревателе решений** и выберите **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-175">Right-click **Program.cs** in **Solution Explorer** and select **View Code**.</span></span>  
  
2.  <span data-ttu-id="6b47d-176">Добавьте следующую инструкцию`using` в начало файла.</span><span class="sxs-lookup"><span data-stu-id="6b47d-176">Add the following `using` statement at the top of the file.</span></span>  
  
    ```csharp  
    using PolicyActivityLibrary;  
    ```  
  
3.  <span data-ttu-id="6b47d-177">Удалите содержимое метода `Main` и замените его следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="6b47d-177">Remove the contents of the `Main` method and replace with the following code.</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
4.  <span data-ttu-id="6b47d-178">Создайте новый метод в классе `Program` с именем `CalculateDiscountUsingCodeWorkflow`, который содержит следующий код.</span><span class="sxs-lookup"><span data-stu-id="6b47d-178">Create a new method in the `Program` class called `CalculateDiscountUsingCodeWorkflow` that contains the following code.</span></span>  
  
    ```csharp  
    static void CalculateDiscountUsingCodeWorkflow()  
    {  
        Variable<double> Subtotal = new Variable<double>  
        {  
            Default = 75.99,  
            Name = "Subtotal"  
        };  
  
        Variable<double> DiscountPercent = new Variable<double>  
        {  
            Name = "DiscountPercent"  
        };  
  
        Variable<double> Total = new Variable<double>  
        {  
            Name = "Total"  
        };  
  
        Activity wf = new Sequence  
        {  
            Variables = { Subtotal, DiscountPercent, Total },  
            Activities =   
            {  
                new Interop  
                {  
                    ActivityType = typeof(DiscountCalculator),  
                    ActivityProperties =   
                    {  
                        { "Subtotal", new InArgument<double>(Subtotal) },  
                        { "DiscountPercentOut", new OutArgument<double>(DiscountPercent) },  
                        { "TotalOut", new OutArgument<double>(Total) }  
                    }  
                },  
                new WriteLine  
                {  
                    Text =  new InArgument<string>(env =>   
                        string.Format("Subtotal: {0:C}, Discount {1}%, Total {2:C}",   
                        Subtotal.Get(env), DiscountPercent.Get(env) * 100, Total.Get(env)))  
                }  
            }  
        };  
  
        WorkflowInvoker.Invoke(wf);  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="6b47d-179">Свойства `Subtotal`, `DiscountPercent` и `Total` действия `DiscountCalculator` отображаются как аргументы действия <xref:System.Activities.Statements.Interop>, привязанные к переменным локального рабочего процесса в коллекции <xref:System.Activities.Statements.Interop> действия <xref:System.Activities.Statements.Interop.ActivityProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="6b47d-179">The `Subtotal`, `DiscountPercent`, and `Total` properties of the `DiscountCalculator` activity are surfaced as arguments of the <xref:System.Activities.Statements.Interop> activity, and bound to local workflow variables in the <xref:System.Activities.Statements.Interop> activity’s <xref:System.Activities.Statements.Interop.ActivityProperties%2A> collection.</span></span> <span data-ttu-id="6b47d-180">`Subtotal` добавляется как аргумент <xref:System.Activities.ArgumentDirection.In>, поскольку данные `Subtotal` направляются действию <xref:System.Activities.Statements.Interop>, а `DiscountPercent` и `Total` добавляются как аргументы <xref:System.Activities.ArgumentDirection.Out>, так как их потоки данных происходят из действия <xref:System.Activities.Statements.Interop>.</span><span class="sxs-lookup"><span data-stu-id="6b47d-180">`Subtotal` is added as an <xref:System.Activities.ArgumentDirection.In> argument because the `Subtotal` data flows into the <xref:System.Activities.Statements.Interop> activity, and `DiscountPercent` and `Total` are added as <xref:System.Activities.ArgumentDirection.Out> arguments because their data flows out of the <xref:System.Activities.Statements.Interop> activity.</span></span> <span data-ttu-id="6b47d-181">Следует заметить, что аргументы <xref:System.Activities.ArgumentDirection.Out> добавляются с именами `DiscountPercentOut` и `TotalOut` чтобы показать, что они представляют аргументы с направлением <xref:System.Activities.ArgumentDirection.Out>.</span><span class="sxs-lookup"><span data-stu-id="6b47d-181">Note that the two <xref:System.Activities.ArgumentDirection.Out> arguments are added with the names `DiscountPercentOut` and `TotalOut` to indicate that they represent <xref:System.Activities.ArgumentDirection.Out> arguments.</span></span> <span data-ttu-id="6b47d-182">Тип `DiscountCalculator` указан как тип <xref:System.Activities.Statements.Interop> действия <xref:System.Activities.Statements.Interop.ActivityType%2A>.</span><span class="sxs-lookup"><span data-stu-id="6b47d-182">The `DiscountCalculator` type is specified as the <xref:System.Activities.Statements.Interop> activity’s <xref:System.Activities.Statements.Interop.ActivityType%2A>.</span></span>  
  
5.  <span data-ttu-id="6b47d-183">Нажмите клавиши CTRL+F5 для сборки и запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="6b47d-183">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="6b47d-184">Подставляя различные значения в качестве значения `Subtotal`, можно проверить различные уровни скидок, реализуемые действием `DiscountCalculator`.</span><span class="sxs-lookup"><span data-stu-id="6b47d-184">Substitute different values for the `Subtotal` value to test out the different discount levels provided by the `DiscountCalculator` activity.</span></span>  
  
    ```csharp  
    Variable<double> Subtotal = new Variable<double>  
    {  
        Default = 75.99, // Change this value.  
        Name = "Subtotal"  
    };  
    ```  
  
### <a name="using-the-interop-activity-in-the-workflow-designer"></a><span data-ttu-id="6b47d-185">Использование действия Interop в конструкторе рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="6b47d-185">Using the Interop Activity in the Workflow Designer</span></span>  
 <span data-ttu-id="6b47d-186">В данном примере рабочий процесс создается с использованием конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="6b47d-186">In this example, a workflow is created using the workflow designer.</span></span> <span data-ttu-id="6b47d-187">Рабочий процесс выполняет те же функции, что и предыдущий пример, за одним исключением: вместо использования действия <xref:System.Activities.Statements.WriteLine> для отображения скидки ведущее приложение получает и отображает сведения о скидке при завершении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="6b47d-187">This workflow has the same functionality as the previous example, except than instead of using a <xref:System.Activities.Statements.WriteLine> activity to display the discount, the host application retrieves and displays the discount information when the workflow completes.</span></span> <span data-ttu-id="6b47d-188">Также локальные переменные рабочего процесса не используются для хранения данных. Вместо этого аргументы создаются в конструкторе рабочих процессов, а значения передаются из ведущего приложения при вызове рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="6b47d-188">Also, instead of using local workflow variables to contain the data, arguments are created in the workflow designer and the values are passed in from the host when the workflow is invoked.</span></span>  
  
##### <a name="to-host-the-policyactivity-using-a-workflow-designer-created-workflow"></a><span data-ttu-id="6b47d-189">Размещение PolicyActivity с использованием рабочего процесса, созданного в конструкторе рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="6b47d-189">To host the PolicyActivity using a Workflow Designer-created workflow</span></span>  
  
1.  <span data-ttu-id="6b47d-190">Щелкните правой кнопкой мыши **Workflow1.xaml** в **обозревателе решений** и выберите **удалить**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-190">Right-click **Workflow1.xaml** in **Solution Explorer** and select **Delete**.</span></span> <span data-ttu-id="6b47d-191">Нажмите кнопку **ОК** для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="6b47d-191">Click **OK** to confirm.</span></span>  
  
2.  <span data-ttu-id="6b47d-192">Щелкните правой кнопкой мыши **PolicyInteropHost** в **обозревателе решений** и выберите **добавить**, **новый элемент...** .</span><span class="sxs-lookup"><span data-stu-id="6b47d-192">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add**, **New Item…**.</span></span>  
  
3.  <span data-ttu-id="6b47d-193">Разверните **элементы Visual C#** , а затем выберите **рабочего процесса**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-193">Expand the **Visual C# Items** node and select **Workflow**.</span></span> <span data-ttu-id="6b47d-194">Выберите **действия** из **элементы Visual C#** списка.</span><span class="sxs-lookup"><span data-stu-id="6b47d-194">Select **Activity** from the **Visual C# Items** list.</span></span>  
  
4.  <span data-ttu-id="6b47d-195">Тип `DiscountWorkflow` в **имя** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-195">Type `DiscountWorkflow` into the **Name** box and click **Add**.</span></span>  
  
5.  <span data-ttu-id="6b47d-196">Нажмите кнопку **аргументы** кнопки в нижнем левом углу конструктора рабочих процессов для отображения **аргументы** области.</span><span class="sxs-lookup"><span data-stu-id="6b47d-196">Click the **Arguments** button on the lower left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
6.  <span data-ttu-id="6b47d-197">Нажмите кнопку **создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-197">Click **Create Argument**.</span></span>  
  
7.  <span data-ttu-id="6b47d-198">Тип `Subtotal` в **имя** выберите **в** из **направление** раскрывающийся список, выберите **двойные** из **Тип аргумента** раскрывающегося списка, а затем нажмите клавишу ВВОД, чтобы сохранить аргумент.</span><span class="sxs-lookup"><span data-stu-id="6b47d-198">Type `Subtotal` into the **Name** box, select **In** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b47d-199">Если **двойные** не находится в **тип аргумента** раскрывающемся списке выберите **поиск типов...** , тип `System.Double` в **имя типа** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-199">If **Double** is not in the **Argument type** drop-down list, select **Browse for Types …**, type `System.Double` in the **Type Name** box, and click **OK**.</span></span>  
  
8.  <span data-ttu-id="6b47d-200">Нажмите кнопку **создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-200">Click **Create Argument**.</span></span>  
  
9. <span data-ttu-id="6b47d-201">Тип `DiscountPercent` в **имя** выберите **Out** из **направление** раскрывающийся список, выберите **двойные** из **Тип аргумента** раскрывающегося списка, а затем нажмите клавишу ВВОД, чтобы сохранить аргумент.</span><span class="sxs-lookup"><span data-stu-id="6b47d-201">Type `DiscountPercent` into the **Name** box, select **Out** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
10. <span data-ttu-id="6b47d-202">Нажмите кнопку **создать аргумент**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-202">Click **Create Argument**.</span></span>  
  
11. <span data-ttu-id="6b47d-203">Тип `Total` в **имя** выберите **Out** из **направление** раскрывающийся список, выберите **двойные** из **Тип аргумента** раскрывающегося списка, а затем нажмите клавишу ВВОД, чтобы сохранить аргумент.</span><span class="sxs-lookup"><span data-stu-id="6b47d-203">Type `Total` into the **Name** box, select **Out** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
12. <span data-ttu-id="6b47d-204">Нажмите кнопку **аргументы** кнопки в нижнем левом углу конструктора рабочих процессов, чтобы закрыть **аргументы** области.</span><span class="sxs-lookup"><span data-stu-id="6b47d-204">Click the **Arguments** button on the lower left side of the workflow designer to close the **Arguments** pane.</span></span>  
  
13. <span data-ttu-id="6b47d-205">Перетащите **последовательности** действия из **поток управления** раздел **элементов** и поместите его на поверхность конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="6b47d-205">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the workflow designer surface.</span></span>  
  
14. <span data-ttu-id="6b47d-206">Перетащите **взаимодействия** действия из **миграции** раздел **элементов** и поместите его **последовательности** действия.</span><span class="sxs-lookup"><span data-stu-id="6b47d-206">Drag an **Interop** activity from the **Migration** section of the **Toolbox** and drop it in the **Sequence** activity.</span></span>  
  
15. <span data-ttu-id="6b47d-207">Нажмите кнопку **взаимодействия** действия на **нажмите, чтобы просмотреть...**</span><span class="sxs-lookup"><span data-stu-id="6b47d-207">Click the **Interop** activity on the **Click to browse…**</span></span> <span data-ttu-id="6b47d-208">Метка, введите **DiscountCalculator** в **имя типа** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-208">label, type **DiscountCalculator** in the **Type Name** box, and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b47d-209">Если действие <xref:System.Activities.Statements.Interop> добавляется в рабочий процесс, а тип `DiscountCalculator` указан в качестве типа <xref:System.Activities.Statements.Interop.ActivityType%2A>, то действие <xref:System.Activities.Statements.Interop> предоставит три аргумента <xref:System.Activities.ArgumentDirection.In> и три аргумента <xref:System.Activities.ArgumentDirection.Out>, представляющие три открытых свойства действия `DiscountCalculator`.</span><span class="sxs-lookup"><span data-stu-id="6b47d-209">When the <xref:System.Activities.Statements.Interop> activity is added to the workflow and the `DiscountCalculator` type is specified as its <xref:System.Activities.Statements.Interop.ActivityType%2A>, the <xref:System.Activities.Statements.Interop> activity exposes three <xref:System.Activities.ArgumentDirection.In> arguments and three <xref:System.Activities.ArgumentDirection.Out> arguments that represent the three public properties of the `DiscountCalculator` activity.</span></span> <span data-ttu-id="6b47d-210"><xref:System.Activities.ArgumentDirection.In> Аргументы имеют имя, совпадающее с именем и три открытых свойства, а также три <xref:System.Activities.ArgumentDirection.Out> аргументы имеют те же имена с **Out** добавляется к имени свойства.</span><span class="sxs-lookup"><span data-stu-id="6b47d-210">The <xref:System.Activities.ArgumentDirection.In> arguments have the same name as the three public properties, and the three <xref:System.Activities.ArgumentDirection.Out> arguments have the same names with **Out** appended to the property name.</span></span> <span data-ttu-id="6b47d-211">В ходе последующих шагов аргументы рабочего процесса, созданные ранее, привязываются к аргументам действия <xref:System.Activities.Statements.Interop>.</span><span class="sxs-lookup"><span data-stu-id="6b47d-211">In the following steps, the workflow arguments created in the previous steps are bound to the <xref:System.Activities.Statements.Interop> activity’s arguments.</span></span>  
  
16. <span data-ttu-id="6b47d-212">Тип `DiscountPercent` в **введите выражение VB** поле справа от **DiscountPercentOut** свойство и нажмите клавишу TAB.</span><span class="sxs-lookup"><span data-stu-id="6b47d-212">Type `DiscountPercent` into the **Enter a VB expression** box to the right of the **DiscountPercentOut** property and press TAB.</span></span>  
  
17. <span data-ttu-id="6b47d-213">Тип `Subtotal` в **введите выражение VB** поле справа от **Subtotal** свойство и нажмите клавишу TAB.</span><span class="sxs-lookup"><span data-stu-id="6b47d-213">Type `Subtotal` into the **Enter a VB expression** box to the right of the **Subtotal** property and press TAB.</span></span>  
  
18. <span data-ttu-id="6b47d-214">Тип `Total` в **введите выражение VB** поле справа от **TotalOut** свойство и нажмите клавишу TAB.</span><span class="sxs-lookup"><span data-stu-id="6b47d-214">Type `Total` into the **Enter a VB expression** box to the right of the **TotalOut** property and press TAB.</span></span>  
  
19. <span data-ttu-id="6b47d-215">Щелкните правой кнопкой мыши **Program.cs** в **обозревателе решений** и выберите **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="6b47d-215">Right-click **Program.cs** in **Solution Explorer** and select **View Code**.</span></span>  
  
20. <span data-ttu-id="6b47d-216">Добавьте следующую инструкцию`using` в начало файла.</span><span class="sxs-lookup"><span data-stu-id="6b47d-216">Add the following `using` statement at the top of the file.</span></span>  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
21. <span data-ttu-id="6b47d-217">Закомментируйте вызов метода `CalculateDiscountInCode` в методе `Main` и добавьте следующий код.</span><span class="sxs-lookup"><span data-stu-id="6b47d-217">Comment out the call to the `CalculateDiscountInCode` method in the `Main` method and add the following code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b47d-218">Если предыдущая процедура не была выполнена и код `Main` по умолчанию все еще присутствует, замените содержимое метода `Main` следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="6b47d-218">If you did not follow the previous procedure and the default `Main` code is present, replace the contents of `Main` with the following code.</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingDesignerWorkflow();  
        //CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
22. <span data-ttu-id="6b47d-219">Создайте новый метод в классе `Program` с именем `CalculateDiscountUsingDesignerWorkflow`, который содержит следующий код.</span><span class="sxs-lookup"><span data-stu-id="6b47d-219">Create a new method in the `Program` class called `CalculateDiscountUsingDesignerWorkflow` that contains the following code.</span></span>  
  
    ```csharp  
    static void CalculateDiscountUsingDesignerWorkflow()  
    {  
        double SubtotalValue = 125.99;  
        Dictionary<string, object> wfargs = new Dictionary<string, object>  
        {  
            {"Subtotal", SubtotalValue}  
        };  
  
        Activity wf = new DiscountWorkflow();  
  
        IDictionary<string, object> outputs =  
            WorkflowInvoker.Invoke(wf, wfargs);  
  
        Console.WriteLine("Subtotal: {0:C}, Discount {1}%, Total {2:C}",  
            SubtotalValue, (double)outputs["DiscountPercent"] * 100,  
            outputs["Total"]);  
    }  
    ```  
  
23. <span data-ttu-id="6b47d-220">Нажмите клавиши CTRL+F5 для сборки и запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="6b47d-220">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="6b47d-221">Чтобы задать другую сумму `Subtotal`, измените значение `SubtotalValue` в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="6b47d-221">To specify a different `Subtotal` amount, change the value of `SubtotalValue` in the following code.</span></span>  
  
    ```csharp  
    double SubtotalValue = 125.99; // Change this value.  
    ```  
  
## <a name="rules-features-overview"></a><span data-ttu-id="6b47d-222">Общие сведения об особенностях правил</span><span class="sxs-lookup"><span data-stu-id="6b47d-222">Rules Features Overview</span></span>  
 <span data-ttu-id="6b47d-223">Обработчик правил [!INCLUDE[wf1](../../../includes/wf1-md.md)] обеспечивает поддержку обработки правил с учетом приоритетов и поддержкой прямых логических цепочек.</span><span class="sxs-lookup"><span data-stu-id="6b47d-223">The [!INCLUDE[wf1](../../../includes/wf1-md.md)] rules engine provides support for processing rules in a priority-based manner with support for forward chaining.</span></span> <span data-ttu-id="6b47d-224">Оценка правил может проводиться для одного элемента или для элементов коллекции.</span><span class="sxs-lookup"><span data-stu-id="6b47d-224">Rules can be evaluated for a single item or for items in a collection.</span></span> <span data-ttu-id="6b47d-225">Общие сведения о правилах, а также сведения о функциональных возможностях отдельных правил см. в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="6b47d-225">For an overview of rules and information on specific rules functionality, please refer to the following table.</span></span>  
  
|<span data-ttu-id="6b47d-226">Возможность правил</span><span class="sxs-lookup"><span data-stu-id="6b47d-226">Rules Feature</span></span>|<span data-ttu-id="6b47d-227">Документация</span><span class="sxs-lookup"><span data-stu-id="6b47d-227">Documentation</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="6b47d-228">Общие сведения о правилах</span><span class="sxs-lookup"><span data-stu-id="6b47d-228">Rules Overview</span></span>|[<span data-ttu-id="6b47d-229">Введение в обработчик правил Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="6b47d-229">Introduction to the Windows Workflow Foundation Rules Engine</span></span>](http://go.microsoft.com/fwlink/?LinkID=152836)|  
|<span data-ttu-id="6b47d-230">RuleSet</span><span class="sxs-lookup"><span data-stu-id="6b47d-230">RuleSet</span></span>|<span data-ttu-id="6b47d-231">[Использование наборов правил в рабочих процессах](http://go.microsoft.com/fwlink/?LinkId=178516) и <xref:System.Workflow.Activities.Rules.RuleSet></span><span class="sxs-lookup"><span data-stu-id="6b47d-231">[Using RuleSets in Workflows](http://go.microsoft.com/fwlink/?LinkId=178516) and <xref:System.Workflow.Activities.Rules.RuleSet></span></span>|  
|<span data-ttu-id="6b47d-232">Оценка правил</span><span class="sxs-lookup"><span data-stu-id="6b47d-232">Evaluation of Rules</span></span>|[<span data-ttu-id="6b47d-233">Вычисление правил в наборы правил</span><span class="sxs-lookup"><span data-stu-id="6b47d-233">Rules Evaluation in RuleSets</span></span>](http://go.microsoft.com/fwlink/?LinkId=178517)|  
|<span data-ttu-id="6b47d-234">Цепочки правил</span><span class="sxs-lookup"><span data-stu-id="6b47d-234">Rules Chaining</span></span>|<span data-ttu-id="6b47d-235">[Прямой цепочки управления](http://go.microsoft.com/fwlink/?LinkId=178518) и [прямые логические цепочки правил](http://go.microsoft.com/fwlink/?LinkId=178519)</span><span class="sxs-lookup"><span data-stu-id="6b47d-235">[Forward Chaining Control](http://go.microsoft.com/fwlink/?LinkId=178518) and [Forward Chaining of Rules](http://go.microsoft.com/fwlink/?LinkId=178519)</span></span>|  
|<span data-ttu-id="6b47d-236">Обработка коллекций в правилах</span><span class="sxs-lookup"><span data-stu-id="6b47d-236">Processing Collections in Rules</span></span>|[<span data-ttu-id="6b47d-237">Обработка коллекций в правилах</span><span class="sxs-lookup"><span data-stu-id="6b47d-237">Processing Collections in Rules</span></span>](http://go.microsoft.com/fwlink/?LinkId=178520)|  
|<span data-ttu-id="6b47d-238">Использование действия PolicyActivity</span><span class="sxs-lookup"><span data-stu-id="6b47d-238">Using the PolicyActivity</span></span>|<span data-ttu-id="6b47d-239">[Использование действия PolicyActivity](http://go.microsoft.com/fwlink/?LinkId=178521) и <xref:System.Workflow.Activities.PolicyActivity></span><span class="sxs-lookup"><span data-stu-id="6b47d-239">[Using the PolicyActivity Activity](http://go.microsoft.com/fwlink/?LinkId=178521) and <xref:System.Workflow.Activities.PolicyActivity></span></span>|  
  
 <span data-ttu-id="6b47d-240">Рабочие процессы, созданные в [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], используют не все предоставляемые в [!INCLUDE[wf1](../../../includes/wf1-md.md)] возможности правил, например они не реализуют декларативные условия действий и условные действия, такие как <xref:System.Workflow.Activities.ConditionedActivityGroup> и <xref:System.Workflow.Activities.ReplicatorActivity>.</span><span class="sxs-lookup"><span data-stu-id="6b47d-240">Workflows created in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] do not use all of the rules features provided by [!INCLUDE[wf1](../../../includes/wf1-md.md)], such as declarative activity conditions and conditional activities such as the <xref:System.Workflow.Activities.ConditionedActivityGroup> and <xref:System.Workflow.Activities.ReplicatorActivity>.</span></span> <span data-ttu-id="6b47d-241">При необходимости можно воспользоваться этими функциональными возможностями в рабочих процессах, созданных с помощью [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] и [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b47d-241">If required, this functionality is available for workflows created using [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] and [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span></span> <span data-ttu-id="6b47d-242">Дополнительные сведения см. в разделе [руководство по миграции](../../../docs/framework/windows-workflow-foundation/migration-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="6b47d-242">For more information, see [Migration Guidance](../../../docs/framework/windows-workflow-foundation/migration-guidance.md).</span></span>
