---
title: Пример. Создание формы MDI путем слияния меню и с применением и элементов управления ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
ms.openlocfilehash: e0343b98cb71521b35418e70550a93e0bfe20fa8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628791"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="85888-102">Пример. Создание формы MDI путем слияния меню и с применением и элементов управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="85888-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>

<span data-ttu-id="85888-103">Пространство имен <xref:System.Windows.Forms?displayProperty=nameWithType> поддерживает приложения с интерфейсом MDI, а элемент управления <xref:System.Windows.Forms.MenuStrip> поддерживает слияние меню.</span><span class="sxs-lookup"><span data-stu-id="85888-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="85888-104">Формы MDI также могут содержать элементы управления <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="85888-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="85888-105">В этом пошаговом руководстве показано, как использовать элементы управления <xref:System.Windows.Forms.ToolStripPanel> с формой MDI.</span><span class="sxs-lookup"><span data-stu-id="85888-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="85888-106">Форма также поддерживает слияние меню с вложенными меню.</span><span class="sxs-lookup"><span data-stu-id="85888-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="85888-107">В этом пошаговом руководстве показаны следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="85888-107">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="85888-108">Создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="85888-108">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="85888-109">Создание главного меню для формы.</span><span class="sxs-lookup"><span data-stu-id="85888-109">Creating the main menu for your form.</span></span> <span data-ttu-id="85888-110">Фактическое имя меню будет разным.</span><span class="sxs-lookup"><span data-stu-id="85888-110">The actual name of the menu will vary.</span></span>

- <span data-ttu-id="85888-111">Добавление элемента управления <xref:System.Windows.Forms.ToolStripPanel> на **панель элементов**.</span><span class="sxs-lookup"><span data-stu-id="85888-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>

- <span data-ttu-id="85888-112">Создание дочерней формы.</span><span class="sxs-lookup"><span data-stu-id="85888-112">Creating a child form.</span></span>

- <span data-ttu-id="85888-113">Упорядочение элементов управления <xref:System.Windows.Forms.ToolStripPanel> по z-порядку.</span><span class="sxs-lookup"><span data-stu-id="85888-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>

<span data-ttu-id="85888-114">По завершении у вас будет форма MDI, поддерживающая слияние меню и перемещаемые элементы управления <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="85888-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="85888-115">Чтобы скопировать код из этого раздела в виде одного списка, см. раздел [как создать форму MDI с помощью слияния меню и элементов управления ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="85888-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="85888-116">предварительные требования</span><span class="sxs-lookup"><span data-stu-id="85888-116">Prerequisites</span></span>

<span data-ttu-id="85888-117">Для выполнения этого пошагового руководства потребуется Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="85888-117">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="85888-118">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="85888-118">Create the project</span></span>

1. <span data-ttu-id="85888-119">В Visual Studio создайте проект приложения Windows с именем **мдиформ** (**File** > **New** > **Project** > **Visual C#**  или **Visual Basic** > **классический Настольный компьютер** > **приложение**).</span><span class="sxs-lookup"><span data-stu-id="85888-119">In Visual Studio, create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="85888-120">В конструктор Windows Forms выберите форму.</span><span class="sxs-lookup"><span data-stu-id="85888-120">In the Windows Forms Designer, select the form.</span></span>

3. <span data-ttu-id="85888-121">В окно свойств задайте для <xref:System.Windows.Forms.Form.IsMdiContainer%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="85888-121">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>

## <a name="create-the-main-menu"></a><span data-ttu-id="85888-122">Создание главного меню</span><span class="sxs-lookup"><span data-stu-id="85888-122">Create the main menu</span></span>

<span data-ttu-id="85888-123">Родительская форма MDI содержит главное меню.</span><span class="sxs-lookup"><span data-stu-id="85888-123">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="85888-124">Главное меню содержит один пункт меню « **окно»** .</span><span class="sxs-lookup"><span data-stu-id="85888-124">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="85888-125">С помощью пункта меню « **окно** » можно создавать дочерние формы.</span><span class="sxs-lookup"><span data-stu-id="85888-125">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="85888-126">Пункты меню из дочерних форм объединяются в главное меню.</span><span class="sxs-lookup"><span data-stu-id="85888-126">Menu items from child forms are merged into the main menu.</span></span>

1. <span data-ttu-id="85888-127">Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.MenuStrip> на форму.</span><span class="sxs-lookup"><span data-stu-id="85888-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>

2. <span data-ttu-id="85888-128">Добавьте <xref:System.Windows.Forms.ToolStripMenuItem> в элемент управления <xref:System.Windows.Forms.MenuStrip> и присвойте ему имя **Window**.</span><span class="sxs-lookup"><span data-stu-id="85888-128">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>

3. <span data-ttu-id="85888-129">Выберите элемент управления <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="85888-129">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

4. <span data-ttu-id="85888-130">В окно свойств задайте для свойства <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> значение `ToolStripMenuItem1`.</span><span class="sxs-lookup"><span data-stu-id="85888-130">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>

5. <span data-ttu-id="85888-131">Добавьте подэлемент в пункт меню **окно** , а затем назовите **Новый**подэлемент.</span><span class="sxs-lookup"><span data-stu-id="85888-131">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>

6. <span data-ttu-id="85888-132">В окно свойств щелкните **события**.</span><span class="sxs-lookup"><span data-stu-id="85888-132">In the Properties window, click **Events**.</span></span>

7. <span data-ttu-id="85888-133">Дважды щелкните событие <xref:System.Windows.Forms.ToolStripItem.Click>.</span><span class="sxs-lookup"><span data-stu-id="85888-133">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

     <span data-ttu-id="85888-134">Конструктор Windows Forms создает обработчик событий для события <xref:System.Windows.Forms.ToolStripItem.Click>.</span><span class="sxs-lookup"><span data-stu-id="85888-134">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

8. <span data-ttu-id="85888-135">Вставьте следующий код в обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="85888-135">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="85888-136">Добавление элемента управления ToolStripPanel на панель элементов</span><span class="sxs-lookup"><span data-stu-id="85888-136">Add the ToolStripPanel control to the Toolbox</span></span>

<span data-ttu-id="85888-137">При использовании <xref:System.Windows.Forms.MenuStrip> элементов управления с формой MDI необходимо иметь элемент управления <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="85888-137">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="85888-138">Чтобы создать форму MDI в конструктор Windows Forms, необходимо добавить элемент управления <xref:System.Windows.Forms.ToolStripPanel> на **панель элементов** .</span><span class="sxs-lookup"><span data-stu-id="85888-138">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="85888-139">Откройте **панель элементов**и перейдите на вкладку **все Windows Forms** , чтобы отобразить доступные элементы управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="85888-139">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>

2. <span data-ttu-id="85888-140">Щелкните правой кнопкой мыши, чтобы открыть контекстное меню, и выберите **пункт Выбрать элементы**.</span><span class="sxs-lookup"><span data-stu-id="85888-140">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>

3. <span data-ttu-id="85888-141">В диалоговом окне **Выбор элементов панели элементов** прокрутите вниз столбец **имя** , пока не найдете элемент **ToolStripPanel**.</span><span class="sxs-lookup"><span data-stu-id="85888-141">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>

4. <span data-ttu-id="85888-142">Установите **флажок рядом с полем, а**затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="85888-142">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>

     <span data-ttu-id="85888-143">Элемент управления <xref:System.Windows.Forms.ToolStripPanel> появится в **области элементов**.</span><span class="sxs-lookup"><span data-stu-id="85888-143">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>

## <a name="create-a-child-form"></a><span data-ttu-id="85888-144">Создание дочерней формы</span><span class="sxs-lookup"><span data-stu-id="85888-144">Create a child form</span></span>

<span data-ttu-id="85888-145">В этой процедуре будет определен отдельный класс дочерней формы, имеющий собственный элемент управления <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="85888-145">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="85888-146">Элементы меню для этой формы объединяются с элементами родительской формы.</span><span class="sxs-lookup"><span data-stu-id="85888-146">The menu items for this form are merged with those of the parent form.</span></span>

1. <span data-ttu-id="85888-147">Добавьте в проект новую форму с именем `ChildForm`.</span><span class="sxs-lookup"><span data-stu-id="85888-147">Add a new form named `ChildForm` to the project.</span></span>

     <span data-ttu-id="85888-148">Дополнительные сведения см. [в разделе инструкции. добавление Windows Forms в проект](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="85888-148">For more information, see [How to: Add Windows Forms to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span></span>

2. <span data-ttu-id="85888-149">Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.MenuStrip> на дочернюю форму.</span><span class="sxs-lookup"><span data-stu-id="85888-149">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>

3. <span data-ttu-id="85888-150">Щелкните глиф действий конструктора <xref:System.Windows.Forms.MenuStrip> элемента управления (![маленькая черная стрелка](./media/designer-actions-glyph.gif)), а затем выберите **изменить элементы**.</span><span class="sxs-lookup"><span data-stu-id="85888-150">Click the <xref:System.Windows.Forms.MenuStrip> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)), and then select **Edit Items**.</span></span>

4. <span data-ttu-id="85888-151">В диалоговом окне **Редактор коллекции элементов** добавьте новый <xref:System.Windows.Forms.ToolStripMenuItem> с именем **чилдменуитем** в дочернее меню.</span><span class="sxs-lookup"><span data-stu-id="85888-151">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>

     <span data-ttu-id="85888-152">Дополнительные сведения см. в статье [Редактор коллекции элементов ToolStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="85888-152">For more information, see [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span></span>

## <a name="test-the-form"></a><span data-ttu-id="85888-153">Тестирование формы</span><span class="sxs-lookup"><span data-stu-id="85888-153">Test the form</span></span>

1. <span data-ttu-id="85888-154">Нажмите клавишу **F5** , чтобы скомпилировать и запустить форму.</span><span class="sxs-lookup"><span data-stu-id="85888-154">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="85888-155">Щелкните пункт меню **окно** , чтобы открыть меню, и выберите пункт **создать**.</span><span class="sxs-lookup"><span data-stu-id="85888-155">Click the **Window** menu item to open the menu, and then click **New**.</span></span>

     <span data-ttu-id="85888-156">Новая дочерняя форма создается в клиентской области MDI формы.</span><span class="sxs-lookup"><span data-stu-id="85888-156">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="85888-157">Меню дочерней формы объединяется с главным меню.</span><span class="sxs-lookup"><span data-stu-id="85888-157">The child form's menu is merged with the main menu.</span></span>

3. <span data-ttu-id="85888-158">Закройте дочернюю форму.</span><span class="sxs-lookup"><span data-stu-id="85888-158">Close the child form.</span></span>

     <span data-ttu-id="85888-159">Меню дочерней формы удаляется из главного меню.</span><span class="sxs-lookup"><span data-stu-id="85888-159">The child form's menu is removed from the main menu.</span></span>

4. <span data-ttu-id="85888-160">Нажмите кнопку **создать** несколько раз.</span><span class="sxs-lookup"><span data-stu-id="85888-160">Click **New** several times.</span></span>

     <span data-ttu-id="85888-161">Дочерние формы автоматически перечисляются под элементом меню « **окно»** , поскольку назначено свойство <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> <xref:System.Windows.Forms.MenuStrip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="85888-161">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>

## <a name="add-toolstrip-support"></a><span data-ttu-id="85888-162">Добавление поддержки ToolStrip</span><span class="sxs-lookup"><span data-stu-id="85888-162">Add ToolStrip support</span></span>

<span data-ttu-id="85888-163">В этой процедуре в родительскую MDI-форму будут добавлены четыре элемента управления <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="85888-163">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="85888-164">Каждый элемент управления <xref:System.Windows.Forms.ToolStrip> добавляется в элемент управления <xref:System.Windows.Forms.ToolStripPanel>, закрепленный за границей формы.</span><span class="sxs-lookup"><span data-stu-id="85888-164">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>

1. <span data-ttu-id="85888-165">Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.ToolStripPanel> на форму.</span><span class="sxs-lookup"><span data-stu-id="85888-165">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>

2. <span data-ttu-id="85888-166">Выбрав элемент управления <xref:System.Windows.Forms.ToolStripPanel>, дважды щелкните элемент управления <xref:System.Windows.Forms.ToolStrip> на **панели элементов**.</span><span class="sxs-lookup"><span data-stu-id="85888-166">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>

     <span data-ttu-id="85888-167">Элемент управления <xref:System.Windows.Forms.ToolStrip> создается в элементе управления <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="85888-167">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

3. <span data-ttu-id="85888-168">Выберите элемент управления <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="85888-168">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

4. <span data-ttu-id="85888-169">В окно свойств измените значение свойства <xref:System.Windows.Forms.Control.Dock%2A> элемента управления на <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="85888-169">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>

     <span data-ttu-id="85888-170">Элемент управления <xref:System.Windows.Forms.ToolStripPanel> закрепляется в левой части формы под главным меню.</span><span class="sxs-lookup"><span data-stu-id="85888-170">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="85888-171">Размер клиентской области MDI изменяется в соответствии с элементом управления <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="85888-171">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

5. <span data-ttu-id="85888-172">Повторите шаги с 1 по 4.</span><span class="sxs-lookup"><span data-stu-id="85888-172">Repeat steps 1 through 4.</span></span>

     <span data-ttu-id="85888-173">Закрепите новый элемент управления <xref:System.Windows.Forms.ToolStripPanel> в верхней части формы.</span><span class="sxs-lookup"><span data-stu-id="85888-173">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>

     <span data-ttu-id="85888-174">Элемент управления <xref:System.Windows.Forms.ToolStripPanel> закреплен под главным меню, а справа от первого элемента управления <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="85888-174">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="85888-175">Этот шаг иллюстрирует важность z-порядка при правильном размещении <xref:System.Windows.Forms.ToolStripPanel> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="85888-175">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

6. <span data-ttu-id="85888-176">Повторите шаги с 1 по 4 для двух дополнительных <xref:System.Windows.Forms.ToolStripPanel> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="85888-176">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

     <span data-ttu-id="85888-177">Закрепите новые элементы управления <xref:System.Windows.Forms.ToolStripPanel> в правой и нижней части формы.</span><span class="sxs-lookup"><span data-stu-id="85888-177">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>

## <a name="arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="85888-178">Упорядочить элементы управления ToolStripPanel по Z-порядку</span><span class="sxs-lookup"><span data-stu-id="85888-178">Arrange ToolStripPanel controls by Z-order</span></span>

<span data-ttu-id="85888-179">Положение закрепленного <xref:System.Windows.Forms.ToolStripPanel> элемента управления в форме MDI определяется положением элемента управления в z-порядке.</span><span class="sxs-lookup"><span data-stu-id="85888-179">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="85888-180">Z-порядок элементов управления можно легко упорядочить в окне "Структура документа".</span><span class="sxs-lookup"><span data-stu-id="85888-180">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>

1. <span data-ttu-id="85888-181">В меню **вид** выберите **другие окна**, а затем щелкните **Структура документа**.</span><span class="sxs-lookup"><span data-stu-id="85888-181">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>

     <span data-ttu-id="85888-182">Размещение элементов управления <xref:System.Windows.Forms.ToolStripPanel> из предыдущей процедуры является нестандартным.</span><span class="sxs-lookup"><span data-stu-id="85888-182">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="85888-183">Это обусловлено неправильным z-порядком.</span><span class="sxs-lookup"><span data-stu-id="85888-183">This is because the z-order is not correct.</span></span> <span data-ttu-id="85888-184">Используйте окно "Структура документа", чтобы изменить z-порядок элементов управления.</span><span class="sxs-lookup"><span data-stu-id="85888-184">Use the Document Outline window to change the z-order of the controls.</span></span>

2. <span data-ttu-id="85888-185">В окне Структура документа выберите **ToolStripPanel4**.</span><span class="sxs-lookup"><span data-stu-id="85888-185">In the Document Outline window, select **ToolStripPanel4**.</span></span>

3. <span data-ttu-id="85888-186">Несколько раз нажмите кнопку со стрелкой вниз, чтобы **ToolStripPanel4** в нижней части списка.</span><span class="sxs-lookup"><span data-stu-id="85888-186">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>

     <span data-ttu-id="85888-187">Элемент управления **ToolStripPanel4** закрепляется в нижней части формы под другими элементами управления.</span><span class="sxs-lookup"><span data-stu-id="85888-187">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>

4. <span data-ttu-id="85888-188">Выберите **ToolStripPanel2**.</span><span class="sxs-lookup"><span data-stu-id="85888-188">Select **ToolStripPanel2**.</span></span>

5. <span data-ttu-id="85888-189">Нажмите кнопку со стрелкой вниз один раз, чтобы разместить третий элемент управления в списке.</span><span class="sxs-lookup"><span data-stu-id="85888-189">Click the down-arrow button one time to position the control third in the list.</span></span>

     <span data-ttu-id="85888-190">Элемент управления **ToolStripPanel2** закрепляется в верхней части формы, под главным меню и над другими элементами управления.</span><span class="sxs-lookup"><span data-stu-id="85888-190">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>

6. <span data-ttu-id="85888-191">Выберите различные элементы управления в окне " **Структура документа** " и переместите их в различные позиции в z-порядке.</span><span class="sxs-lookup"><span data-stu-id="85888-191">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="85888-192">Обратите внимание на результат z-порядка размещения закрепленных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="85888-192">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="85888-193">Для отмены изменений используйте сочетание клавиш CTRL-Z или **отменить** в меню **Правка** .</span><span class="sxs-lookup"><span data-stu-id="85888-193">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>

## <a name="checkpoint---test-your-form"></a><span data-ttu-id="85888-194">Контрольная точка — тестирование формы</span><span class="sxs-lookup"><span data-stu-id="85888-194">Checkpoint - test your form</span></span>

1. <span data-ttu-id="85888-195">Нажмите клавишу **F5** , чтобы скомпилировать и запустить форму.</span><span class="sxs-lookup"><span data-stu-id="85888-195">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="85888-196">Щелкните захват элемента управления <xref:System.Windows.Forms.ToolStrip> и перетащите элемент управления в другое положение в форме.</span><span class="sxs-lookup"><span data-stu-id="85888-196">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>

     <span data-ttu-id="85888-197">Элемент управления <xref:System.Windows.Forms.ToolStrip> можно перетащить из одного элемента управления <xref:System.Windows.Forms.ToolStripPanel> в другой.</span><span class="sxs-lookup"><span data-stu-id="85888-197">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>

## <a name="next-steps"></a><span data-ttu-id="85888-198">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="85888-198">Next steps</span></span>

<span data-ttu-id="85888-199">В этом пошаговом руководстве вы создали родительскую MDI-форму с <xref:System.Windows.Forms.ToolStrip> элементами управления и слиянием меню.</span><span class="sxs-lookup"><span data-stu-id="85888-199">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="85888-200">Семейство элементов управления <xref:System.Windows.Forms.ToolStrip> можно использовать для многих других целей:</span><span class="sxs-lookup"><span data-stu-id="85888-200">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="85888-201">Создайте контекстные меню для элементов управления с помощью <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="85888-201">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="85888-202">Дополнительные сведения см. в разделе [Общие сведения о компоненте ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="85888-202">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="85888-203">Создана форма с автоматически заполненным стандартным меню.</span><span class="sxs-lookup"><span data-stu-id="85888-203">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="85888-204">Дополнительные сведения см. в разделе [Пошаговое руководство. предоставление стандартных пунктов меню в форме](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="85888-204">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="85888-205">Придайте <xref:System.Windows.Forms.ToolStrip> элементам управления профессиональный внешний вид.</span><span class="sxs-lookup"><span data-stu-id="85888-205">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="85888-206">Дополнительные сведения см. [в разделе как задать модуль подготовки отчетов ToolStrip для приложения](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="85888-206">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="85888-207">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="85888-207">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="85888-208">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="85888-208">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="85888-209">Практическое руководство. Создание дочерних MDI-форм</span><span class="sxs-lookup"><span data-stu-id="85888-209">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="85888-210">Практическое руководство. Вставка элемента MenuStrip в раскрывающееся меню интерфейса MDI</span><span class="sxs-lookup"><span data-stu-id="85888-210">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [<span data-ttu-id="85888-211">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="85888-211">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
