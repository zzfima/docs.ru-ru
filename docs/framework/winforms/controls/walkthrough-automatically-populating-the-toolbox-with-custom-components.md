---
title: Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 8c40f4a58800183c142602d950e4fe1331c1eaf3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730273"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="ef7fe-102">Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами</span><span class="sxs-lookup"><span data-stu-id="ef7fe-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>
<span data-ttu-id="ef7fe-103">Если компоненты определяются в проекте в настоящее время в открытом решении, они автоматически будут отображаться в **элементов**, не выполняя никаких действий от вас требуется.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="ef7fe-104">Можно также вручную заполнять **элементов** компонентами с помощью [выберите элементов элементов-диалоговое окно (Visual Studio)](https://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb), но **элементов** принимает учетную запись элементов в своем решении выходные данные сборки со следующими характеристиками:</span><span class="sxs-lookup"><span data-stu-id="ef7fe-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](https://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>  
  
-   <span data-ttu-id="ef7fe-105">Реализует <xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="ef7fe-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>  
  
-   <span data-ttu-id="ef7fe-106">Не поддерживает <xref:System.ComponentModel.ToolboxItemAttribute> присвоено `false`;</span><span class="sxs-lookup"><span data-stu-id="ef7fe-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>  
  
-   <span data-ttu-id="ef7fe-107">Не поддерживает <xref:System.ComponentModel.DesignTimeVisibleAttribute> присвоено `false`.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef7fe-108">**Элементов** отслеживает цепочки ссылок, поэтому он не будет отображаться элементы, которые не были собраны проекта в решении.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-108">The **Toolbox** does not follow reference chains, so it will not display items that are not built by a project in your solution.</span></span>  
  
 <span data-ttu-id="ef7fe-109">В этом пошаговом руководстве показано, как пользовательский компонент автоматически появится в **элементов** после создания компонента.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="ef7fe-110">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-110">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="ef7fe-111">Создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-111">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="ef7fe-112">Создание пользовательского компонента.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-112">Creating a custom component.</span></span>  
  
-   <span data-ttu-id="ef7fe-113">Создание экземпляра пользовательского компонента.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-113">Creating an instance of a custom component.</span></span>  
  
-   <span data-ttu-id="ef7fe-114">Выгрузке и перезагрузке пользовательского компонента.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-114">Unloading and reloading a custom component.</span></span>  
  
 <span data-ttu-id="ef7fe-115">Когда вы закончите, вы увидите, что **элементов** заполняется компонентом, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef7fe-116">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ef7fe-117">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="ef7fe-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ef7fe-118">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="ef7fe-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="ef7fe-119">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="ef7fe-119">Creating the Project</span></span>  
 <span data-ttu-id="ef7fe-120">Первым шагом являются создание проекта и настройка формы.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-120">The first step is to create the project and to set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="ef7fe-121">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="ef7fe-121">To create the project</span></span>  
  
1.  <span data-ttu-id="ef7fe-122">Создайте проект приложения на основе Windows с именем `ToolboxExample` (**файл** > **New** > **проекта**  >  **Visual C#** или **Visual Basic** > **классический рабочий стол** > **Windows Forms Application**).</span><span class="sxs-lookup"><span data-stu-id="ef7fe-122">Create a Windows-based application project called `ToolboxExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="ef7fe-123">Добавьте новый компонент в проект.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-123">Add a new component to the project.</span></span> <span data-ttu-id="ef7fe-124">Назовите его `DemoComponent`.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-124">Call it `DemoComponent`.</span></span>  
  
     <span data-ttu-id="ef7fe-125">Дополнительные сведения см. в разделе [NIB: Практическое: Добавление новых элементов проекта](https://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span><span class="sxs-lookup"><span data-stu-id="ef7fe-125">For more information, see [NIB:How to: Add New Project Items](https://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span>  
  
3.  <span data-ttu-id="ef7fe-126">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-126">Build the project.</span></span>  
  
4.  <span data-ttu-id="ef7fe-127">Из **средства** меню, щелкните **параметры** элемента.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-127">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="ef7fe-128">Нажмите кнопку **Общие** под **конструктор Windows Forms** элемента и убедитесь, что **AutoToolboxPopulate** параметру присваивается **True**.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-128">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>  
  
## <a name="creating-an-instance-of-a-custom-component"></a><span data-ttu-id="ef7fe-129">Создание экземпляра пользовательского компонента</span><span class="sxs-lookup"><span data-stu-id="ef7fe-129">Creating an Instance of a Custom Component</span></span>  
 <span data-ttu-id="ef7fe-130">Следующим шагом является создание экземпляра пользовательского компонента в форме.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-130">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="ef7fe-131">Так как **элементов** автоматически учетных записей для нового компонента, это так же просто, как создание любого компонента или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-131">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a><span data-ttu-id="ef7fe-132">Для создания экземпляра пользовательского компонента</span><span class="sxs-lookup"><span data-stu-id="ef7fe-132">To create an instance of a custom component</span></span>  
  
1.  <span data-ttu-id="ef7fe-133">Откройте форму проекта в **конструктора**.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-133">Open the project's form in the **Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="ef7fe-134">В **элементов**, щелкните новый вкладку с именем **компоненты ToolboxExample**.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-134">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>  
  
     <span data-ttu-id="ef7fe-135">После нажатия кнопки вкладке вы увидите **DemoComponent**.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-135">Once you click the tab, you will see **DemoComponent**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef7fe-136">Для повышения производительности компонентов в области автоматически заполняемая **элементов** не имеют пользовательских точечных рисунков и <xref:System.Drawing.ToolboxBitmapAttribute> не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-136">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="ef7fe-137">Для отображения значка для пользовательского компонента в **элементов**, использовать **Выбор элементов панели элементов** диалоговое окно, чтобы загрузить компонент.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-137">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>  
  
3.  <span data-ttu-id="ef7fe-138">Перетащите в форму компонента.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-138">Drag your component onto your form.</span></span>  
  
     <span data-ttu-id="ef7fe-139">Экземпляр компонента создается и добавляется к **область компонентов**.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-139">An instance of the component is created and added to the **Component Tray**.</span></span>  
  
## <a name="unloading-and-reloading-a-custom-component"></a><span data-ttu-id="ef7fe-140">Выгрузке и перезагрузке пользовательского компонента</span><span class="sxs-lookup"><span data-stu-id="ef7fe-140">Unloading and Reloading a Custom Component</span></span>  
 <span data-ttu-id="ef7fe-141">**Элементов** принимает учетной записи компонентов в каждом загрузки проекта, а при выгрузке проекта ссылки на компоненты проекта удаляются.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-141">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a><span data-ttu-id="ef7fe-142">Чтобы поэкспериментировать с влиянием на панель элементов в выгрузки и загрузки компонентов</span><span class="sxs-lookup"><span data-stu-id="ef7fe-142">To experiment with the effect on the Toolbox of unloading and reloading components</span></span>  
  
1.  <span data-ttu-id="ef7fe-143">Выгрузите проект из решения.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-143">Unload the project from the solution.</span></span>  
  
     <span data-ttu-id="ef7fe-144">Дополнительные сведения о выгрузке проектов см. в разделе [NIB: Практическое: Выгрузите и перезагрузите проекты](https://msdn.microsoft.com/library/abc0155b-8fcb-4ffc-95b6-698518a7100b).</span><span class="sxs-lookup"><span data-stu-id="ef7fe-144">For more information about unloading projects, see [NIB:How to: Unload and Reload Projects](https://msdn.microsoft.com/library/abc0155b-8fcb-4ffc-95b6-698518a7100b).</span></span> <span data-ttu-id="ef7fe-145">Если вам будет предложено сохранить, выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-145">If you are prompted to save, choose **Yes**.</span></span>  
  
2.  <span data-ttu-id="ef7fe-146">Добавьте новый **приложения Windows** проекта к решению.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-146">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="ef7fe-147">Откройте форму в **конструктор**.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-147">Open the form in the **Designer**.</span></span>  
  
     <span data-ttu-id="ef7fe-148">**Компоненты ToolboxExample** вкладка из предыдущего проекта — теперь больше нет.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-148">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>  
  
3.  <span data-ttu-id="ef7fe-149">Перезагрузить `ToolboxExample` проекта.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-149">Reload the `ToolboxExample` project.</span></span>  
  
     <span data-ttu-id="ef7fe-150">**Компоненты ToolboxExample** вкладке теперь отобразится.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-150">The **ToolboxExample Components** tab now reappears.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ef7fe-151">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="ef7fe-151">Next Steps</span></span>  
 <span data-ttu-id="ef7fe-152">В этом пошаговом руководстве показано, что **элементов** компонентов проекта, но **элементов** учетная запись также принимает элементов управления.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-152">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="ef7fe-153">Поэкспериментируйте с собственные пользовательские элементы управления, добавляя и удаляя управления проекты из решения.</span><span class="sxs-lookup"><span data-stu-id="ef7fe-153">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef7fe-154">См. также</span><span class="sxs-lookup"><span data-stu-id="ef7fe-154">See also</span></span>
- [<span data-ttu-id="ef7fe-155">Страница "Общие", конструктор Windows Forms, диалоговое окно "Параметры</span><span class="sxs-lookup"><span data-stu-id="ef7fe-155">General, Windows Forms Designer, Options Dialog Box</span></span>](https://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834)
- [<span data-ttu-id="ef7fe-156">Практическое руководство. Управление вкладками панели элементов</span><span class="sxs-lookup"><span data-stu-id="ef7fe-156">How to: Manipulate Toolbox Tabs</span></span>](https://msdn.microsoft.com/library/21285050-cadd-455a-b1f5-a2289a89c4db)
- [<span data-ttu-id="ef7fe-157">Диалоговое окно "Выбор элементов панели элементов" (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="ef7fe-157">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](https://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)
- [<span data-ttu-id="ef7fe-158">Размещение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef7fe-158">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)
