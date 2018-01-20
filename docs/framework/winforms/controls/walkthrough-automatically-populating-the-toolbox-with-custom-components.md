---
title: "Пример. Автоматическое заполнение панели элементов пользовательскими компонентами"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b60d4ee7908a5ed9dcb3393132ba7d0bd0a6cb5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="54c89-102">Пример. Автоматическое заполнение панели элементов пользовательскими компонентами</span><span class="sxs-lookup"><span data-stu-id="54c89-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>
<span data-ttu-id="54c89-103">Если компоненты определяются проектом в текущем открытом решении, они автоматически будут отображаться в **элементов**, с без дополнительных действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="54c89-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="54c89-104">Можно также вручную заполнять **элементов** компонентами с помощью [выберите Toolbox Items Dialog Box (Visual Studio)](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb), но **элементов** принимает учетной записи элементов в вашем решении выходным данным построения со следующими характеристиками:</span><span class="sxs-lookup"><span data-stu-id="54c89-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>  
  
-   <span data-ttu-id="54c89-105">Реализует <xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="54c89-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>  
  
-   <span data-ttu-id="54c89-106">Не поддерживает <xref:System.ComponentModel.ToolboxItemAttribute> значение `false`;</span><span class="sxs-lookup"><span data-stu-id="54c89-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>  
  
-   <span data-ttu-id="54c89-107">Не поддерживает <xref:System.ComponentModel.DesignTimeVisibleAttribute> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="54c89-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54c89-108">**Элементов** отслеживает цепочки ссылок, поэтому не будут показаны элементы, которые не были собраны проектом в вашем решении.</span><span class="sxs-lookup"><span data-stu-id="54c89-108">The **Toolbox** does not follow reference chains, so it will not display items that are not built by a project in your solution.</span></span>  
  
 <span data-ttu-id="54c89-109">В этом пошаговом руководстве показано, как пользовательский компонент автоматически появится в **элементов** при компонента.</span><span class="sxs-lookup"><span data-stu-id="54c89-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="54c89-110">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="54c89-110">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="54c89-111">Создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="54c89-111">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="54c89-112">Создание пользовательского компонента.</span><span class="sxs-lookup"><span data-stu-id="54c89-112">Creating a custom component.</span></span>  
  
-   <span data-ttu-id="54c89-113">Создание экземпляра пользовательского компонента.</span><span class="sxs-lookup"><span data-stu-id="54c89-113">Creating an instance of a custom component.</span></span>  
  
-   <span data-ttu-id="54c89-114">Выгрузка и повторная загрузка пользовательского компонента.</span><span class="sxs-lookup"><span data-stu-id="54c89-114">Unloading and reloading a custom component.</span></span>  
  
 <span data-ttu-id="54c89-115">Когда вы закончите, вы увидите, что **элементов** заполняется только что созданный компонент.</span><span class="sxs-lookup"><span data-stu-id="54c89-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54c89-116">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="54c89-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="54c89-117">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="54c89-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="54c89-118">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="54c89-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="54c89-119">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="54c89-119">Creating the Project</span></span>  
 <span data-ttu-id="54c89-120">Первым шагом являются создание проекта и настройка формы.</span><span class="sxs-lookup"><span data-stu-id="54c89-120">The first step is to create the project and to set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="54c89-121">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="54c89-121">To create the project</span></span>  
  
1.  <span data-ttu-id="54c89-122">Создайте проект приложения Windows с именем `ToolboxExample`.</span><span class="sxs-lookup"><span data-stu-id="54c89-122">Create a Windows-based application project called `ToolboxExample`.</span></span>  
  
     <span data-ttu-id="54c89-123">Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта приложения WPF](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="54c89-123">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="54c89-124">Добавьте новый компонент в проект.</span><span class="sxs-lookup"><span data-stu-id="54c89-124">Add a new component to the project.</span></span> <span data-ttu-id="54c89-125">Она вызывается `DemoComponent`.</span><span class="sxs-lookup"><span data-stu-id="54c89-125">Call it `DemoComponent`.</span></span>  
  
     <span data-ttu-id="54c89-126">Дополнительные сведения см. в разделе [NIB: Практическое: Добавление новых элементов проекта](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span><span class="sxs-lookup"><span data-stu-id="54c89-126">For more information, see [NIB:How to: Add New Project Items](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span>  
  
3.  <span data-ttu-id="54c89-127">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="54c89-127">Build the project.</span></span>  
  
4.  <span data-ttu-id="54c89-128">Из **средства** меню, нажмите кнопку **параметры** элемента.</span><span class="sxs-lookup"><span data-stu-id="54c89-128">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="54c89-129">Нажмите кнопку **Общие** под **конструктор Windows Forms** элемента и убедитесь, что **AutoToolboxPopulate** включен режим **True**.</span><span class="sxs-lookup"><span data-stu-id="54c89-129">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>  
  
## <a name="creating-an-instance-of-a-custom-component"></a><span data-ttu-id="54c89-130">Создание экземпляра пользовательского компонента</span><span class="sxs-lookup"><span data-stu-id="54c89-130">Creating an Instance of a Custom Component</span></span>  
 <span data-ttu-id="54c89-131">Следующим шагом является создание экземпляра пользовательского компонента в форме.</span><span class="sxs-lookup"><span data-stu-id="54c89-131">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="54c89-132">Поскольку **элементов** автоматически учетные записи для нового компонента, это так же легко, как создание любого компонента или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="54c89-132">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a><span data-ttu-id="54c89-133">Для создания экземпляра пользовательского компонента</span><span class="sxs-lookup"><span data-stu-id="54c89-133">To create an instance of a custom component</span></span>  
  
1.  <span data-ttu-id="54c89-134">Откройте форму проекта в **конструктор форм**.</span><span class="sxs-lookup"><span data-stu-id="54c89-134">Open the project's form in the **Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="54c89-135">В **элементов**, щелкните вкладку новый вызывается **ToolboxExample компонентов**.</span><span class="sxs-lookup"><span data-stu-id="54c89-135">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>  
  
     <span data-ttu-id="54c89-136">После выбора закладки, вы увидите **DemoComponent**.</span><span class="sxs-lookup"><span data-stu-id="54c89-136">Once you click the tab, you will see **DemoComponent**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="54c89-137">Из соображений производительности компонентов в области автоматически заполняемая **элементов** не отображать пользовательские растровые изображения и <xref:System.Drawing.ToolboxBitmapAttribute> не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="54c89-137">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="54c89-138">Для отображения значка для пользовательского компонента в **элементов**, используйте **Выбор элементов панели элементов** диалогового загрузить компонент.</span><span class="sxs-lookup"><span data-stu-id="54c89-138">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>  
  
3.  <span data-ttu-id="54c89-139">Перетащите компонент в форме.</span><span class="sxs-lookup"><span data-stu-id="54c89-139">Drag your component onto your form.</span></span>  
  
     <span data-ttu-id="54c89-140">Создается и добавляется в экземпляр компонента **область компонентов**.</span><span class="sxs-lookup"><span data-stu-id="54c89-140">An instance of the component is created and added to the **Component Tray**.</span></span>  
  
## <a name="unloading-and-reloading-a-custom-component"></a><span data-ttu-id="54c89-141">Выгрузка и повторная загрузка пользовательского компонента</span><span class="sxs-lookup"><span data-stu-id="54c89-141">Unloading and Reloading a Custom Component</span></span>  
 <span data-ttu-id="54c89-142">**Элементов** принимает учетной записи компонентов в каждом загружен проект, а при выгрузке проекта ссылки на компоненты проекта удаляются.</span><span class="sxs-lookup"><span data-stu-id="54c89-142">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a><span data-ttu-id="54c89-143">Чтобы поэкспериментировать с последствиями для выгрузки и загрузки компонентов на панель элементов</span><span class="sxs-lookup"><span data-stu-id="54c89-143">To experiment with the effect on the Toolbox of unloading and reloading components</span></span>  
  
1.  <span data-ttu-id="54c89-144">Выгрузите проект из решения.</span><span class="sxs-lookup"><span data-stu-id="54c89-144">Unload the project from the solution.</span></span>  
  
     <span data-ttu-id="54c89-145">Дополнительные сведения о выгрузке проектов см. в разделе [NIB: Практическое: выгрузка и перезагрузка проектов](http://msdn.microsoft.com/library/abc0155b-8fcb-4ffc-95b6-698518a7100b).</span><span class="sxs-lookup"><span data-stu-id="54c89-145">For more information about unloading projects, see [NIB:How to: Unload and Reload Projects](http://msdn.microsoft.com/library/abc0155b-8fcb-4ffc-95b6-698518a7100b).</span></span> <span data-ttu-id="54c89-146">Если будет предложено сохранить, выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="54c89-146">If you are prompted to save, choose **Yes**.</span></span>  
  
2.  <span data-ttu-id="54c89-147">Добавьте новый **приложение Windows** проекта в решение.</span><span class="sxs-lookup"><span data-stu-id="54c89-147">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="54c89-148">Откройте форму в **конструктор**.</span><span class="sxs-lookup"><span data-stu-id="54c89-148">Open the form in the **Designer**.</span></span>  
  
     <span data-ttu-id="54c89-149">**ToolboxExample компоненты** вкладку из предыдущего проекта теперь является исчезнут.</span><span class="sxs-lookup"><span data-stu-id="54c89-149">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>  
  
3.  <span data-ttu-id="54c89-150">Перезагрузить `ToolboxExample` проекта.</span><span class="sxs-lookup"><span data-stu-id="54c89-150">Reload the `ToolboxExample` project.</span></span>  
  
     <span data-ttu-id="54c89-151">**Компоненты ToolboxExample** вкладке теперь отобразится.</span><span class="sxs-lookup"><span data-stu-id="54c89-151">The **ToolboxExample Components** tab now reappears.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="54c89-152">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="54c89-152">Next Steps</span></span>  
 <span data-ttu-id="54c89-153">В этом пошаговом руководстве показано, что **элементов** компонентов проекта, но **элементов** также является учетной записью принимает элементов управления.</span><span class="sxs-lookup"><span data-stu-id="54c89-153">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="54c89-154">Поэкспериментируйте с пользовательским элементам управления, добавляя и удаляя управления проектами в решении.</span><span class="sxs-lookup"><span data-stu-id="54c89-154">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54c89-155">См. также</span><span class="sxs-lookup"><span data-stu-id="54c89-155">See Also</span></span>  
 [<span data-ttu-id="54c89-156">Общие, конструктор Windows Forms, диалоговое окно «Параметры»</span><span class="sxs-lookup"><span data-stu-id="54c89-156">General, Windows Forms Designer, Options Dialog Box</span></span>](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834)  
 [<span data-ttu-id="54c89-157">Практическое руководство. Управление вкладками панели элементов</span><span class="sxs-lookup"><span data-stu-id="54c89-157">How to: Manipulate Toolbox Tabs</span></span>](http://msdn.microsoft.com/library/21285050-cadd-455a-b1f5-a2289a89c4db)  
 [<span data-ttu-id="54c89-158">Диалоговое окно "Выбор элементов панели элементов" (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="54c89-158">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [<span data-ttu-id="54c89-159">Размещение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="54c89-159">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)
