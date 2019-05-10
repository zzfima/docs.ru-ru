---
title: Пошаговое руководство. Создание формы MDI путем слияния меню и элементов управления ToolStrip
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
ms.openlocfilehash: 5853760231cbece27805923c009d83e16c9b0a5e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211562"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="564b5-102">Пошаговое руководство. Создание формы MDI путем слияния меню и элементов управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="564b5-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>

<span data-ttu-id="564b5-103">Пространство имен <xref:System.Windows.Forms?displayProperty=nameWithType> поддерживает приложения с интерфейсом MDI, а элемент управления <xref:System.Windows.Forms.MenuStrip> поддерживает слияние меню.</span><span class="sxs-lookup"><span data-stu-id="564b5-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="564b5-104">Формы MDI также могут содержать элементы управления <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="564b5-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="564b5-105">В этом пошаговом руководстве демонстрируется использование <xref:System.Windows.Forms.ToolStripPanel> элементов управления с формой MDI.</span><span class="sxs-lookup"><span data-stu-id="564b5-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="564b5-106">Форма также поддерживает слияние меню с вложенными меню.</span><span class="sxs-lookup"><span data-stu-id="564b5-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="564b5-107">В этом пошаговом руководстве показаны следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="564b5-107">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="564b5-108">Создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="564b5-108">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="564b5-109">Создание главного меню для формы.</span><span class="sxs-lookup"><span data-stu-id="564b5-109">Creating the main menu for your form.</span></span> <span data-ttu-id="564b5-110">Фактическое имя меню будет отличаться.</span><span class="sxs-lookup"><span data-stu-id="564b5-110">The actual name of the menu will vary.</span></span>

- <span data-ttu-id="564b5-111">Добавление <xref:System.Windows.Forms.ToolStripPanel> управления **элементов**.</span><span class="sxs-lookup"><span data-stu-id="564b5-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>

- <span data-ttu-id="564b5-112">Создание дочерней формы.</span><span class="sxs-lookup"><span data-stu-id="564b5-112">Creating a child form.</span></span>

- <span data-ttu-id="564b5-113">Упорядочение <xref:System.Windows.Forms.ToolStripPanel> элементов управления по оси z.</span><span class="sxs-lookup"><span data-stu-id="564b5-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>

<span data-ttu-id="564b5-114">Когда вы закончите, вы получите формы MDI, которая поддерживает слияние меню и movable <xref:System.Windows.Forms.ToolStrip> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="564b5-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="564b5-115">Чтобы скопировать код из этого раздела единым блоком, см. раздел [Практическое руководство. Создание формы MDI путем слияния меню и элементов управления ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="564b5-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="564b5-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="564b5-116">Prerequisites</span></span>

<span data-ttu-id="564b5-117">Вам потребуется Visual Studio для выполнения этого пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="564b5-117">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="564b5-118">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="564b5-118">Create the project</span></span>

1. <span data-ttu-id="564b5-119">В Visual Studio создайте проект приложения Windows с именем **MdiForm** (**файл** > **New** > **проекта**  >  **Visual C#**  или **Visual Basic** > **классический рабочий стол**  >   **Windows Forms Application**).</span><span class="sxs-lookup"><span data-stu-id="564b5-119">In Visual Studio, create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="564b5-120">В конструкторе Windows Forms выберите форму.</span><span class="sxs-lookup"><span data-stu-id="564b5-120">In the Windows Forms Designer, select the form.</span></span>

3. <span data-ttu-id="564b5-121">В окне свойств установите для параметра <xref:System.Windows.Forms.Form.IsMdiContainer%2A> для `true`.</span><span class="sxs-lookup"><span data-stu-id="564b5-121">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>

## <a name="create-the-main-menu"></a><span data-ttu-id="564b5-122">Создание главного меню</span><span class="sxs-lookup"><span data-stu-id="564b5-122">Create the main menu</span></span>

<span data-ttu-id="564b5-123">Родительская форма MDI содержит главное меню.</span><span class="sxs-lookup"><span data-stu-id="564b5-123">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="564b5-124">В главном меню есть один под названием **окно**.</span><span class="sxs-lookup"><span data-stu-id="564b5-124">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="564b5-125">С помощью **окно** пункта меню, можно создать дочерние формы.</span><span class="sxs-lookup"><span data-stu-id="564b5-125">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="564b5-126">Элементы меню из дочерних форм объединяются в главном меню.</span><span class="sxs-lookup"><span data-stu-id="564b5-126">Menu items from child forms are merged into the main menu.</span></span>

1. <span data-ttu-id="564b5-127">Из **элементов**, перетащите <xref:System.Windows.Forms.MenuStrip> на форму.</span><span class="sxs-lookup"><span data-stu-id="564b5-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>

2. <span data-ttu-id="564b5-128">Добавить <xref:System.Windows.Forms.ToolStripMenuItem> для <xref:System.Windows.Forms.MenuStrip> управления и назовите его **окно**.</span><span class="sxs-lookup"><span data-stu-id="564b5-128">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>

3. <span data-ttu-id="564b5-129">Выберите элемент управления <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="564b5-129">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

4. <span data-ttu-id="564b5-130">В окне свойств установите для параметра <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> свойства `ToolStripMenuItem1`.</span><span class="sxs-lookup"><span data-stu-id="564b5-130">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>

5. <span data-ttu-id="564b5-131">Добавьте подэлемент для **окно** пункта меню, а затем имя вложенного элемента **New**.</span><span class="sxs-lookup"><span data-stu-id="564b5-131">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>

6. <span data-ttu-id="564b5-132">В окне «Свойства» щелкните **события**.</span><span class="sxs-lookup"><span data-stu-id="564b5-132">In the Properties window, click **Events**.</span></span>

7. <span data-ttu-id="564b5-133">Дважды щелкните <xref:System.Windows.Forms.ToolStripItem.Click> событий.</span><span class="sxs-lookup"><span data-stu-id="564b5-133">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

     <span data-ttu-id="564b5-134">В конструкторе Windows Forms создает обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> событий.</span><span class="sxs-lookup"><span data-stu-id="564b5-134">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

8. <span data-ttu-id="564b5-135">Вставьте следующий код в обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="564b5-135">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="564b5-136">Добавить на панель элементов управления ToolStripPanel</span><span class="sxs-lookup"><span data-stu-id="564b5-136">Add the ToolStripPanel control to the Toolbox</span></span>

<span data-ttu-id="564b5-137">При использовании <xref:System.Windows.Forms.MenuStrip> элементов управления с формой MDI, необходимо иметь <xref:System.Windows.Forms.ToolStripPanel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="564b5-137">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="564b5-138">Необходимо добавить <xref:System.Windows.Forms.ToolStripPanel> управления **элементов** для создания формы MDI в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="564b5-138">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="564b5-139">Откройте **элементов**, а затем нажмите кнопку **все формы Windows Forms** вкладка для отображения доступных элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="564b5-139">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>

2. <span data-ttu-id="564b5-140">Щелкните правой кнопкой мыши, чтобы открыть контекстное меню и выберите **Выбор элементов**.</span><span class="sxs-lookup"><span data-stu-id="564b5-140">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>

3. <span data-ttu-id="564b5-141">В **Выбор элементов панели элементов** диалоговое окно, прокрутите вниз **имя** столбца, пока не найдете **ToolStripPanel**.</span><span class="sxs-lookup"><span data-stu-id="564b5-141">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>

4. <span data-ttu-id="564b5-142">Установите флажок рядом с **ToolStripPanel**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="564b5-142">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>

     <span data-ttu-id="564b5-143"><xref:System.Windows.Forms.ToolStripPanel> Появился на **элементов**.</span><span class="sxs-lookup"><span data-stu-id="564b5-143">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>

## <a name="create-a-child-form"></a><span data-ttu-id="564b5-144">Создание дочерней формы</span><span class="sxs-lookup"><span data-stu-id="564b5-144">Create a child form</span></span>

<span data-ttu-id="564b5-145">В этой процедуре мы определим отдельный дочерний класс формы, имеет свой собственный <xref:System.Windows.Forms.MenuStrip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="564b5-145">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="564b5-146">Пункты меню для этой формы объединяются с соответствующими родительской формы.</span><span class="sxs-lookup"><span data-stu-id="564b5-146">The menu items for this form are merged with those of the parent form.</span></span>

1. <span data-ttu-id="564b5-147">Добавьте новую форму с именем `ChildForm` в проект.</span><span class="sxs-lookup"><span data-stu-id="564b5-147">Add a new form named `ChildForm` to the project.</span></span>

     <span data-ttu-id="564b5-148">Дополнительные сведения см. в разделе [Как Добавление в проект Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="564b5-148">For more information, see [How to: Add Windows Forms to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span></span>

2. <span data-ttu-id="564b5-149">Из **элементов**, перетащите <xref:System.Windows.Forms.MenuStrip> управления дочерней формы.</span><span class="sxs-lookup"><span data-stu-id="564b5-149">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>

3. <span data-ttu-id="564b5-150">Нажмите кнопку <xref:System.Windows.Forms.MenuStrip> глиф смарт-тега элемента управления (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), а затем выберите **изменение элементов**.</span><span class="sxs-lookup"><span data-stu-id="564b5-150">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>

4. <span data-ttu-id="564b5-151">В **редактор коллекции элементов** диалоговое окно, добавьте новый <xref:System.Windows.Forms.ToolStripMenuItem> с именем **ChildMenuItem** в меню "дочерний".</span><span class="sxs-lookup"><span data-stu-id="564b5-151">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>

     <span data-ttu-id="564b5-152">Дополнительные сведения см. в разделе [редактор коллекции элементов ToolStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="564b5-152">For more information, see [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span></span>

## <a name="test-the-form"></a><span data-ttu-id="564b5-153">Проверить форму</span><span class="sxs-lookup"><span data-stu-id="564b5-153">Test the form</span></span>

1. <span data-ttu-id="564b5-154">Нажмите клавишу **F5** для компиляции и запуска в форму.</span><span class="sxs-lookup"><span data-stu-id="564b5-154">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="564b5-155">Нажмите кнопку **окно** пункт меню, чтобы открыть меню и нажмите кнопку **New**.</span><span class="sxs-lookup"><span data-stu-id="564b5-155">Click the **Window** menu item to open the menu, and then click **New**.</span></span>

     <span data-ttu-id="564b5-156">Вы создадите новую дочернюю форму в клиентской области формы MDI.</span><span class="sxs-lookup"><span data-stu-id="564b5-156">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="564b5-157">Меню дочерней формы объединяется с главного меню.</span><span class="sxs-lookup"><span data-stu-id="564b5-157">The child form's menu is merged with the main menu.</span></span>

3. <span data-ttu-id="564b5-158">Закройте дочерней формы.</span><span class="sxs-lookup"><span data-stu-id="564b5-158">Close the child form.</span></span>

     <span data-ttu-id="564b5-159">Меню дочерней формы удаляется из главного меню.</span><span class="sxs-lookup"><span data-stu-id="564b5-159">The child form's menu is removed from the main menu.</span></span>

4. <span data-ttu-id="564b5-160">Нажмите кнопку **New** несколько раз.</span><span class="sxs-lookup"><span data-stu-id="564b5-160">Click **New** several times.</span></span>

     <span data-ttu-id="564b5-161">Дочерние формы автоматически отображаются в категории **окно** пункт меню, поскольку <xref:System.Windows.Forms.MenuStrip> элемента управления <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> назначается свойство.</span><span class="sxs-lookup"><span data-stu-id="564b5-161">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>

## <a name="add-toolstrip-support"></a><span data-ttu-id="564b5-162">Добавить поддержку элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="564b5-162">Add ToolStrip support</span></span>

<span data-ttu-id="564b5-163">В этой процедуре вы добавите четыре <xref:System.Windows.Forms.ToolStrip> элементы управления для родительской формы MDI.</span><span class="sxs-lookup"><span data-stu-id="564b5-163">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="564b5-164">Каждый <xref:System.Windows.Forms.ToolStrip> будет добавлен элемент управления внутри <xref:System.Windows.Forms.ToolStripPanel> элемент управления, который присоединяется к краю формы.</span><span class="sxs-lookup"><span data-stu-id="564b5-164">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>

1. <span data-ttu-id="564b5-165">Из **элементов**, перетащите <xref:System.Windows.Forms.ToolStripPanel> на форму.</span><span class="sxs-lookup"><span data-stu-id="564b5-165">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>

2. <span data-ttu-id="564b5-166">С помощью <xref:System.Windows.Forms.ToolStripPanel> выбран элемент управления, дважды щелкните <xref:System.Windows.Forms.ToolStrip> контролировать **элементов**.</span><span class="sxs-lookup"><span data-stu-id="564b5-166">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>

     <span data-ttu-id="564b5-167">Объект <xref:System.Windows.Forms.ToolStrip> создается элемент управления в <xref:System.Windows.Forms.ToolStripPanel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="564b5-167">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

3. <span data-ttu-id="564b5-168">Выберите элемент управления <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="564b5-168">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

4. <span data-ttu-id="564b5-169">В окне «Свойства» измените значение элемента управления <xref:System.Windows.Forms.Control.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="564b5-169">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>

     <span data-ttu-id="564b5-170"><xref:System.Windows.Forms.ToolStripPanel> Управления фиксирует элемент управления у левого края формы под главным меню.</span><span class="sxs-lookup"><span data-stu-id="564b5-170">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="564b5-171">Изменяет размер клиентской области MDI <xref:System.Windows.Forms.ToolStripPanel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="564b5-171">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

5. <span data-ttu-id="564b5-172">Повторите шаги 1 – 4.</span><span class="sxs-lookup"><span data-stu-id="564b5-172">Repeat steps 1 through 4.</span></span>

     <span data-ttu-id="564b5-173">Закрепите новые <xref:System.Windows.Forms.ToolStripPanel> элемента управления в верхней части формы.</span><span class="sxs-lookup"><span data-stu-id="564b5-173">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>

     <span data-ttu-id="564b5-174"><xref:System.Windows.Forms.ToolStripPanel> Прикреплен данный элемент управления под главным меню, но справа от первого <xref:System.Windows.Forms.ToolStripPanel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="564b5-174">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="564b5-175">В этом разделе рассмотрены важность z порядка в правильной позиционирование <xref:System.Windows.Forms.ToolStripPanel> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="564b5-175">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

6. <span data-ttu-id="564b5-176">Повторите шаги 1 – 4 для два раза <xref:System.Windows.Forms.ToolStripPanel> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="564b5-176">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

     <span data-ttu-id="564b5-177">Закрепите новые <xref:System.Windows.Forms.ToolStripPanel> элементы управления справа и внизу формы.</span><span class="sxs-lookup"><span data-stu-id="564b5-177">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>

## <a name="arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="564b5-178">Размещение элементов управления ToolStripPanel по оси Z</span><span class="sxs-lookup"><span data-stu-id="564b5-178">Arrange ToolStripPanel controls by Z-order</span></span>

<span data-ttu-id="564b5-179">Положение закрепленного <xref:System.Windows.Forms.ToolStripPanel> управления в форме MDI определяется положением элемента управления в z порядке.</span><span class="sxs-lookup"><span data-stu-id="564b5-179">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="564b5-180">Можно легко упорядочить z порядок элементов управления в окне "Структура документа".</span><span class="sxs-lookup"><span data-stu-id="564b5-180">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>

1. <span data-ttu-id="564b5-181">В **представление** меню, щелкните **Other Windows**, а затем нажмите кнопку **Структура документа**.</span><span class="sxs-lookup"><span data-stu-id="564b5-181">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>

     <span data-ttu-id="564b5-182">Расположение вашего <xref:System.Windows.Forms.ToolStripPanel> нестандартные элементы управления из предыдущей процедуры.</span><span class="sxs-lookup"><span data-stu-id="564b5-182">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="564b5-183">Это обусловлено z порядок не верна.</span><span class="sxs-lookup"><span data-stu-id="564b5-183">This is because the z-order is not correct.</span></span> <span data-ttu-id="564b5-184">Используйте окно "Структура документа" для изменения z порядок элементов управления.</span><span class="sxs-lookup"><span data-stu-id="564b5-184">Use the Document Outline window to change the z-order of the controls.</span></span>

2. <span data-ttu-id="564b5-185">В окне «Структура документа» выберите **ToolStripPanel4**.</span><span class="sxs-lookup"><span data-stu-id="564b5-185">In the Document Outline window, select **ToolStripPanel4**.</span></span>

3. <span data-ttu-id="564b5-186">Нажмите кнопку со стрелкой вниз, пока **ToolStripPanel4** находится в нижней части списка.</span><span class="sxs-lookup"><span data-stu-id="564b5-186">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>

     <span data-ttu-id="564b5-187">**ToolStripPanel4** прикреплен данный элемент управления в нижней части формы, под другими элементами управления.</span><span class="sxs-lookup"><span data-stu-id="564b5-187">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>

4. <span data-ttu-id="564b5-188">Выберите **ToolStripPanel2**.</span><span class="sxs-lookup"><span data-stu-id="564b5-188">Select **ToolStripPanel2**.</span></span>

5. <span data-ttu-id="564b5-189">Нажмите кнопку со стрелкой вниз один раз для размещения элемента управления в-третьих, в списке.</span><span class="sxs-lookup"><span data-stu-id="564b5-189">Click the down-arrow button one time to position the control third in the list.</span></span>

     <span data-ttu-id="564b5-190">**ToolStripPanel2** прикреплен данный элемент управления в верхней части формы под главным меню и над другими элементами управления.</span><span class="sxs-lookup"><span data-stu-id="564b5-190">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>

6. <span data-ttu-id="564b5-191">Выберите различные элементы управления в **Структура документа** окно и переместите их в разные положения в z порядка.</span><span class="sxs-lookup"><span data-stu-id="564b5-191">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="564b5-192">Обратите внимание на результат z порядка при размещении закрепленных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="564b5-192">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="564b5-193">Нажмите CTRL-z или **отменить** на **изменить** меню, чтобы отменить внесенные изменения.</span><span class="sxs-lookup"><span data-stu-id="564b5-193">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>

## <a name="checkpoint---test-your-form"></a><span data-ttu-id="564b5-194">CHECKPOINT - тестирования в форму</span><span class="sxs-lookup"><span data-stu-id="564b5-194">Checkpoint - test your form</span></span>

1. <span data-ttu-id="564b5-195">Нажмите клавишу **F5** для компиляции и запуска в форму.</span><span class="sxs-lookup"><span data-stu-id="564b5-195">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="564b5-196">Нажмите кнопку захвата <xref:System.Windows.Forms.ToolStrip> управления и перетащите элемент управления в различных положениях на форме.</span><span class="sxs-lookup"><span data-stu-id="564b5-196">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>

     <span data-ttu-id="564b5-197">Можно перетащить <xref:System.Windows.Forms.ToolStrip> управления от одного <xref:System.Windows.Forms.ToolStripPanel> элемента управления в другой.</span><span class="sxs-lookup"><span data-stu-id="564b5-197">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>

## <a name="next-steps"></a><span data-ttu-id="564b5-198">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="564b5-198">Next steps</span></span>

<span data-ttu-id="564b5-199">В этом пошаговом руководстве вы создали родительской формы MDI с <xref:System.Windows.Forms.ToolStrip> элементы управления и слияние меню.</span><span class="sxs-lookup"><span data-stu-id="564b5-199">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="564b5-200">Можно использовать <xref:System.Windows.Forms.ToolStrip> семейства элементов управления, для многих других целей:</span><span class="sxs-lookup"><span data-stu-id="564b5-200">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="564b5-201">Создать контекстное меню для элементов управления с <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="564b5-201">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="564b5-202">Дополнительные сведения см. в разделе [Общие сведения о компоненте ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="564b5-202">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="564b5-203">Создать форму с автоматически заполненные стандартным меню.</span><span class="sxs-lookup"><span data-stu-id="564b5-203">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="564b5-204">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание стандартных пунктов меню для формы](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="564b5-204">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="564b5-205">Предоставить вашей <xref:System.Windows.Forms.ToolStrip> управляет профессиональный вид.</span><span class="sxs-lookup"><span data-stu-id="564b5-205">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="564b5-206">Дополнительные сведения см. в разделе [Как Назначение средства визуализации компоненту ToolStrip для приложения](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="564b5-206">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="564b5-207">См. также</span><span class="sxs-lookup"><span data-stu-id="564b5-207">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="564b5-208">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="564b5-208">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="564b5-209">Практическое руководство. Создание дочерних MDI-форм</span><span class="sxs-lookup"><span data-stu-id="564b5-209">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="564b5-210">Практическое руководство. Вставка элемента MenuStrip в раскрывающееся меню интерфейса MDI</span><span class="sxs-lookup"><span data-stu-id="564b5-210">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [<span data-ttu-id="564b5-211">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="564b5-211">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
