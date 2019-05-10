---
title: Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 876de650f9c182c0f82a02d1c5b356faa4f7f118
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211159"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="86dc6-102">Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами</span><span class="sxs-lookup"><span data-stu-id="86dc6-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>

<span data-ttu-id="86dc6-103">Если компоненты определяются в проекте в настоящее время в открытом решении, они автоматически будут отображаться в **элементов**, не выполняя никаких действий от вас требуется.</span><span class="sxs-lookup"><span data-stu-id="86dc6-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="86dc6-104">Можно также вручную заполнять **элементов** компонентами с помощью [выберите элементов элементов-диалоговое окно (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), но **элементов** принимает учетную запись элементов в своем решении выходные данные сборки со следующими характеристиками:</span><span class="sxs-lookup"><span data-stu-id="86dc6-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>

- <span data-ttu-id="86dc6-105">Реализует <xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="86dc6-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>

- <span data-ttu-id="86dc6-106">Не поддерживает <xref:System.ComponentModel.ToolboxItemAttribute> присвоено `false`;</span><span class="sxs-lookup"><span data-stu-id="86dc6-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>

- <span data-ttu-id="86dc6-107">Не поддерживает <xref:System.ComponentModel.DesignTimeVisibleAttribute> присвоено `false`.</span><span class="sxs-lookup"><span data-stu-id="86dc6-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>

> [!NOTE]
> <span data-ttu-id="86dc6-108">**Элементов** не отслеживает цепочки ссылок, поэтому оно не будет отображаться элементы, которые не были собраны проекта в решении.</span><span class="sxs-lookup"><span data-stu-id="86dc6-108">The **Toolbox** does not follow reference chains, so it won't display items that are not built by a project in your solution.</span></span>

<span data-ttu-id="86dc6-109">В этом пошаговом руководстве показано, как пользовательский компонент автоматически появится в **элементов** после создания компонента.</span><span class="sxs-lookup"><span data-stu-id="86dc6-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="86dc6-110">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="86dc6-110">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="86dc6-111">Создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="86dc6-111">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="86dc6-112">Создание пользовательского компонента.</span><span class="sxs-lookup"><span data-stu-id="86dc6-112">Creating a custom component.</span></span>

- <span data-ttu-id="86dc6-113">Создание экземпляра пользовательского компонента.</span><span class="sxs-lookup"><span data-stu-id="86dc6-113">Creating an instance of a custom component.</span></span>

- <span data-ttu-id="86dc6-114">Выгрузке и перезагрузке пользовательского компонента.</span><span class="sxs-lookup"><span data-stu-id="86dc6-114">Unloading and reloading a custom component.</span></span>

<span data-ttu-id="86dc6-115">Когда вы закончите, вы увидите, что **элементов** заполняется компонентом, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="86dc6-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="86dc6-116">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="86dc6-116">Create the project</span></span>

1. <span data-ttu-id="86dc6-117">В Visual Studio создайте проект приложения на основе Windows с именем `ToolboxExample` (**файл** > **New** > **проекта**  >  **Visual C#**  или **Visual Basic** > **классический рабочий стол** > **Windows Forms Приложение**).</span><span class="sxs-lookup"><span data-stu-id="86dc6-117">In Visual Studio, create a Windows-based application project called `ToolboxExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="86dc6-118">Добавьте новый компонент в проект.</span><span class="sxs-lookup"><span data-stu-id="86dc6-118">Add a new component to the project.</span></span> <span data-ttu-id="86dc6-119">Назовите его `DemoComponent`.</span><span class="sxs-lookup"><span data-stu-id="86dc6-119">Call it `DemoComponent`.</span></span>

     <span data-ttu-id="86dc6-120">Дополнительные сведения см. в разделе [Как Добавление новых элементов проекта](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="86dc6-120">For more information, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span>

3. <span data-ttu-id="86dc6-121">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="86dc6-121">Build the project.</span></span>

4. <span data-ttu-id="86dc6-122">Из **средства** меню, щелкните **параметры** элемента.</span><span class="sxs-lookup"><span data-stu-id="86dc6-122">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="86dc6-123">Нажмите кнопку **Общие** под **конструктор Windows Forms** элемента и убедитесь, что **AutoToolboxPopulate** параметру присваивается **True**.</span><span class="sxs-lookup"><span data-stu-id="86dc6-123">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>

## <a name="create-an-instance-of-a-custom-component"></a><span data-ttu-id="86dc6-124">Создание экземпляра пользовательского компонента</span><span class="sxs-lookup"><span data-stu-id="86dc6-124">Create an instance of a custom component</span></span>

<span data-ttu-id="86dc6-125">Следующим шагом является создание экземпляра пользовательского компонента в форме.</span><span class="sxs-lookup"><span data-stu-id="86dc6-125">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="86dc6-126">Так как **элементов** автоматически учетных записей для нового компонента, это так же просто, как создание любого компонента или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="86dc6-126">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>

1. <span data-ttu-id="86dc6-127">Откройте форму проекта в **конструктора**.</span><span class="sxs-lookup"><span data-stu-id="86dc6-127">Open the project's form in the **Forms Designer**.</span></span>

2. <span data-ttu-id="86dc6-128">В **элементов**, щелкните новый вкладку с именем **компоненты ToolboxExample**.</span><span class="sxs-lookup"><span data-stu-id="86dc6-128">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>

     <span data-ttu-id="86dc6-129">После нажатия кнопки вкладке вы увидите **DemoComponent**.</span><span class="sxs-lookup"><span data-stu-id="86dc6-129">Once you click the tab, you will see **DemoComponent**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="86dc6-130">Для повышения производительности компонентов в области автоматически заполняемая **элементов** не имеют пользовательских точечных рисунков и <xref:System.Drawing.ToolboxBitmapAttribute> не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="86dc6-130">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="86dc6-131">Для отображения значка для пользовательского компонента в **элементов**, использовать **Выбор элементов панели элементов** диалоговое окно, чтобы загрузить компонент.</span><span class="sxs-lookup"><span data-stu-id="86dc6-131">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>

3. <span data-ttu-id="86dc6-132">Перетащите в форму компонента.</span><span class="sxs-lookup"><span data-stu-id="86dc6-132">Drag your component onto your form.</span></span>

     <span data-ttu-id="86dc6-133">Экземпляр компонента создается и добавляется к **область компонентов**.</span><span class="sxs-lookup"><span data-stu-id="86dc6-133">An instance of the component is created and added to the **Component Tray**.</span></span>

## <a name="unload-and-reload-a-custom-component"></a><span data-ttu-id="86dc6-134">Выгрузите и перезагрузите пользовательского компонента</span><span class="sxs-lookup"><span data-stu-id="86dc6-134">Unload and reload a custom component</span></span>

<span data-ttu-id="86dc6-135">**Элементов** принимает учетной записи компонентов в каждом загрузки проекта, а при выгрузке проекта ссылки на компоненты проекта удаляются.</span><span class="sxs-lookup"><span data-stu-id="86dc6-135">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>

1. <span data-ttu-id="86dc6-136">Выгрузите проект из решения.</span><span class="sxs-lookup"><span data-stu-id="86dc6-136">Unload the project from the solution.</span></span>

     <span data-ttu-id="86dc6-137">Дополнительные сведения о выгрузке проектов см. в разделе [как: Выгрузите и перезагрузите проекты](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="86dc6-137">For more information about unloading projects, see [How to: Unload and Reload Projects](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span></span> <span data-ttu-id="86dc6-138">Если вам будет предложено сохранить, выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="86dc6-138">If you are prompted to save, choose **Yes**.</span></span>

2. <span data-ttu-id="86dc6-139">Добавьте новый **приложения Windows** проекта к решению.</span><span class="sxs-lookup"><span data-stu-id="86dc6-139">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="86dc6-140">Откройте форму в **конструктор**.</span><span class="sxs-lookup"><span data-stu-id="86dc6-140">Open the form in the **Designer**.</span></span>

     <span data-ttu-id="86dc6-141">**Компоненты ToolboxExample** вкладка из предыдущего проекта — теперь больше нет.</span><span class="sxs-lookup"><span data-stu-id="86dc6-141">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>

3. <span data-ttu-id="86dc6-142">Перезагрузить `ToolboxExample` проекта.</span><span class="sxs-lookup"><span data-stu-id="86dc6-142">Reload the `ToolboxExample` project.</span></span>

     <span data-ttu-id="86dc6-143">**Компоненты ToolboxExample** вкладке теперь отобразится.</span><span class="sxs-lookup"><span data-stu-id="86dc6-143">The **ToolboxExample Components** tab now reappears.</span></span>

## <a name="next-steps"></a><span data-ttu-id="86dc6-144">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="86dc6-144">Next steps</span></span>

<span data-ttu-id="86dc6-145">В этом пошаговом руководстве показано, что **элементов** компонентов проекта, но **элементов** учетная запись также принимает элементов управления.</span><span class="sxs-lookup"><span data-stu-id="86dc6-145">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="86dc6-146">Поэкспериментируйте с собственные пользовательские элементы управления, добавляя и удаляя управления проекты из решения.</span><span class="sxs-lookup"><span data-stu-id="86dc6-146">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>

## <a name="see-also"></a><span data-ttu-id="86dc6-147">См. также</span><span class="sxs-lookup"><span data-stu-id="86dc6-147">See also</span></span>

- <span data-ttu-id="86dc6-148">[Страница "Общие", конструктор Windows Forms, диалоговое окно "Параметры](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="86dc6-148">[General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- <span data-ttu-id="86dc6-149">[Практическое руководство. Управление вкладками панели элементов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="86dc6-149">[How to: Manipulate Toolbox Tabs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span></span>
- <span data-ttu-id="86dc6-150">[Диалоговое окно "Выбор элементов панели элементов" (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="86dc6-150">[Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span></span>
- [<span data-ttu-id="86dc6-151">Размещение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="86dc6-151">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
