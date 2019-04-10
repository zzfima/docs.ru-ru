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
ms.openlocfilehash: 62e137df53d06f5aedb2701b5727c25e52f35614
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59319070"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="6ab57-102">Пошаговое руководство. Создание формы MDI путем слияния меню и элементов управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="6ab57-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="6ab57-103">Пространство имен <xref:System.Windows.Forms?displayProperty=nameWithType> поддерживает приложения с интерфейсом MDI, а элемент управления <xref:System.Windows.Forms.MenuStrip> поддерживает слияние меню.</span><span class="sxs-lookup"><span data-stu-id="6ab57-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="6ab57-104">Формы MDI также могут содержать элементы управления <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="6ab57-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="6ab57-105">В этом пошаговом руководстве демонстрируется использование <xref:System.Windows.Forms.ToolStripPanel> элементов управления с формой MDI.</span><span class="sxs-lookup"><span data-stu-id="6ab57-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="6ab57-106">Форма также поддерживает слияние меню с вложенными меню.</span><span class="sxs-lookup"><span data-stu-id="6ab57-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="6ab57-107">В этом пошаговом руководстве показаны следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="6ab57-107">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="6ab57-108">Создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6ab57-108">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="6ab57-109">Создание главного меню для формы.</span><span class="sxs-lookup"><span data-stu-id="6ab57-109">Creating the main menu for your form.</span></span> <span data-ttu-id="6ab57-110">Фактическое имя меню будет отличаться.</span><span class="sxs-lookup"><span data-stu-id="6ab57-110">The actual name of the menu will vary.</span></span>  
  
-   <span data-ttu-id="6ab57-111">Добавление <xref:System.Windows.Forms.ToolStripPanel> управления **элементов**.</span><span class="sxs-lookup"><span data-stu-id="6ab57-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>  
  
-   <span data-ttu-id="6ab57-112">Создание дочерней формы.</span><span class="sxs-lookup"><span data-stu-id="6ab57-112">Creating a child form.</span></span>  
  
-   <span data-ttu-id="6ab57-113">Упорядочение <xref:System.Windows.Forms.ToolStripPanel> элементов управления по оси z.</span><span class="sxs-lookup"><span data-stu-id="6ab57-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>  
  
 <span data-ttu-id="6ab57-114">Когда вы закончите, вы получите формы MDI, которая поддерживает слияние меню и movable <xref:System.Windows.Forms.ToolStrip> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="6ab57-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="6ab57-115">Чтобы скопировать код из этого раздела единым блоком, см. раздел [Практическое руководство. Создание формы MDI путем слияния меню и элементов управления ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="6ab57-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ab57-116">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="6ab57-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6ab57-117">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="6ab57-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6ab57-118">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="6ab57-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6ab57-119">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="6ab57-119">Prerequisites</span></span>  
 <span data-ttu-id="6ab57-120">Для выполнения данного пошагового руководства требуется:</span><span class="sxs-lookup"><span data-stu-id="6ab57-120">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="6ab57-121">Разрешения, необходимые для создания и выполнения проектов приложений Windows Forms на компьютере, на котором установлена Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6ab57-121">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="6ab57-122">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="6ab57-122">Creating the Project</span></span>  
 <span data-ttu-id="6ab57-123">Первым шагом является создание проекта и настройка формы.</span><span class="sxs-lookup"><span data-stu-id="6ab57-123">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="6ab57-124">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="6ab57-124">To create the project</span></span>  
  
1. <span data-ttu-id="6ab57-125">Создайте проект приложения Windows с именем **MdiForm** (**файл** > **New** > **проекта**  >  **Visual C#** или **Visual Basic** > **классический рабочий стол** > **Windows Forms Application**).</span><span class="sxs-lookup"><span data-stu-id="6ab57-125">Create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2. <span data-ttu-id="6ab57-126">В конструкторе Windows Forms выберите форму.</span><span class="sxs-lookup"><span data-stu-id="6ab57-126">In the Windows Forms Designer, select the form.</span></span>  
  
3. <span data-ttu-id="6ab57-127">В окне свойств установите для параметра <xref:System.Windows.Forms.Form.IsMdiContainer%2A> для `true`.</span><span class="sxs-lookup"><span data-stu-id="6ab57-127">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>  
  
## <a name="creating-the-main-menu"></a><span data-ttu-id="6ab57-128">Создание главного меню</span><span class="sxs-lookup"><span data-stu-id="6ab57-128">Creating the Main Menu</span></span>  
 <span data-ttu-id="6ab57-129">Родительская форма MDI содержит главное меню.</span><span class="sxs-lookup"><span data-stu-id="6ab57-129">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="6ab57-130">В главном меню есть один под названием **окно**.</span><span class="sxs-lookup"><span data-stu-id="6ab57-130">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="6ab57-131">С помощью **окно** пункта меню, можно создать дочерние формы.</span><span class="sxs-lookup"><span data-stu-id="6ab57-131">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="6ab57-132">Элементы меню из дочерних форм объединяются в главном меню.</span><span class="sxs-lookup"><span data-stu-id="6ab57-132">Menu items from child forms are merged into the main menu.</span></span>  
  
#### <a name="to-create-the-main-menu"></a><span data-ttu-id="6ab57-133">Чтобы создать главное меню</span><span class="sxs-lookup"><span data-stu-id="6ab57-133">To create the Main menu</span></span>  
  
1. <span data-ttu-id="6ab57-134">Из **элементов**, перетащите <xref:System.Windows.Forms.MenuStrip> на форму.</span><span class="sxs-lookup"><span data-stu-id="6ab57-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>  
  
2. <span data-ttu-id="6ab57-135">Добавить <xref:System.Windows.Forms.ToolStripMenuItem> для <xref:System.Windows.Forms.MenuStrip> управления и назовите его **окно**.</span><span class="sxs-lookup"><span data-stu-id="6ab57-135">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>  
  
3. <span data-ttu-id="6ab57-136">Выберите элемент управления <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="6ab57-136">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
4. <span data-ttu-id="6ab57-137">В окне свойств установите для параметра <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> свойства `ToolStripMenuItem1`.</span><span class="sxs-lookup"><span data-stu-id="6ab57-137">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>  
  
5. <span data-ttu-id="6ab57-138">Добавьте подэлемент для **окно** пункта меню, а затем имя вложенного элемента **New**.</span><span class="sxs-lookup"><span data-stu-id="6ab57-138">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>  
  
6. <span data-ttu-id="6ab57-139">В окне «Свойства» щелкните **события**.</span><span class="sxs-lookup"><span data-stu-id="6ab57-139">In the Properties window, click **Events**.</span></span>  
  
7. <span data-ttu-id="6ab57-140">Дважды щелкните <xref:System.Windows.Forms.ToolStripItem.Click> событий.</span><span class="sxs-lookup"><span data-stu-id="6ab57-140">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
     <span data-ttu-id="6ab57-141">В конструкторе Windows Forms создает обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> событий.</span><span class="sxs-lookup"><span data-stu-id="6ab57-141">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
8. <span data-ttu-id="6ab57-142">Вставьте следующий код в обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="6ab57-142">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="6ab57-143">Добавление на панель элементов управления ToolStripPanel</span><span class="sxs-lookup"><span data-stu-id="6ab57-143">Adding the ToolStripPanel Control to the Toolbox</span></span>  
 <span data-ttu-id="6ab57-144">При использовании <xref:System.Windows.Forms.MenuStrip> элементов управления с формой MDI, необходимо иметь <xref:System.Windows.Forms.ToolStripPanel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6ab57-144">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="6ab57-145">Необходимо добавить <xref:System.Windows.Forms.ToolStripPanel> управления **элементов** для создания формы MDI в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6ab57-145">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="6ab57-146">Чтобы добавить на панель элементов управления ToolStripPanel</span><span class="sxs-lookup"><span data-stu-id="6ab57-146">To add the ToolStripPanel control to the Toolbox</span></span>  
  
1. <span data-ttu-id="6ab57-147">Откройте **элементов**, а затем нажмите кнопку **все формы Windows Forms** вкладка для отображения доступных элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6ab57-147">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>  
  
2. <span data-ttu-id="6ab57-148">Щелкните правой кнопкой мыши, чтобы открыть контекстное меню и выберите **Выбор элементов**.</span><span class="sxs-lookup"><span data-stu-id="6ab57-148">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>  
  
3. <span data-ttu-id="6ab57-149">В **Выбор элементов панели элементов** диалоговое окно, прокрутите вниз **имя** столбца, пока не найдете **ToolStripPanel**.</span><span class="sxs-lookup"><span data-stu-id="6ab57-149">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>  
  
4. <span data-ttu-id="6ab57-150">Установите флажок рядом с **ToolStripPanel**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6ab57-150">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="6ab57-151"><xref:System.Windows.Forms.ToolStripPanel> Появился на **элементов**.</span><span class="sxs-lookup"><span data-stu-id="6ab57-151">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>  
  
## <a name="creating-a-child-form"></a><span data-ttu-id="6ab57-152">Создание дочерней формы</span><span class="sxs-lookup"><span data-stu-id="6ab57-152">Creating a Child Form</span></span>  
 <span data-ttu-id="6ab57-153">В этой процедуре мы определим отдельный дочерний класс формы, имеет свой собственный <xref:System.Windows.Forms.MenuStrip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6ab57-153">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="6ab57-154">Пункты меню для этой формы объединяются с соответствующими родительской формы.</span><span class="sxs-lookup"><span data-stu-id="6ab57-154">The menu items for this form are merged with those of the parent form.</span></span>  
  
#### <a name="to-define-a-child-form"></a><span data-ttu-id="6ab57-155">Для определения дочерней формы</span><span class="sxs-lookup"><span data-stu-id="6ab57-155">To define a child form</span></span>  
  
1. <span data-ttu-id="6ab57-156">Добавьте новую форму с именем `ChildForm` в проект.</span><span class="sxs-lookup"><span data-stu-id="6ab57-156">Add a new form named `ChildForm` to the project.</span></span>  
  
     <span data-ttu-id="6ab57-157">Дополнительные сведения см. в разделе [Как Добавление в проект Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="6ab57-157">For more information, see [How to: Add Windows Forms to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="6ab57-158">Из **элементов**, перетащите <xref:System.Windows.Forms.MenuStrip> управления дочерней формы.</span><span class="sxs-lookup"><span data-stu-id="6ab57-158">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>  
  
3. <span data-ttu-id="6ab57-159">Нажмите кнопку <xref:System.Windows.Forms.MenuStrip> глиф смарт-тега элемента управления (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), а затем выберите **изменение элементов**.</span><span class="sxs-lookup"><span data-stu-id="6ab57-159">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>  
  
4. <span data-ttu-id="6ab57-160">В **редактор коллекции элементов** диалоговое окно, добавьте новый <xref:System.Windows.Forms.ToolStripMenuItem> с именем **ChildMenuItem** в меню "дочерний".</span><span class="sxs-lookup"><span data-stu-id="6ab57-160">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>  
  
     <span data-ttu-id="6ab57-161">Дополнительные сведения см. в разделе [редактор коллекции элементов ToolStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="6ab57-161">For more information, see [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span></span>  
  
## <a name="testing-the-form"></a><span data-ttu-id="6ab57-162">Тестирование формы</span><span class="sxs-lookup"><span data-stu-id="6ab57-162">Testing the Form</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="6ab57-163">Для проверки формы</span><span class="sxs-lookup"><span data-stu-id="6ab57-163">To test your form</span></span>  
  
1. <span data-ttu-id="6ab57-164">Нажмите клавишу F5, чтобы скомпилировать и запустить в форму.</span><span class="sxs-lookup"><span data-stu-id="6ab57-164">Press F5 to compile and run your form.</span></span>  
  
2. <span data-ttu-id="6ab57-165">Нажмите кнопку **окно** пункт меню, чтобы открыть меню и нажмите кнопку **New**.</span><span class="sxs-lookup"><span data-stu-id="6ab57-165">Click the **Window** menu item to open the menu, and then click **New**.</span></span>  
  
     <span data-ttu-id="6ab57-166">Вы создадите новую дочернюю форму в клиентской области формы MDI.</span><span class="sxs-lookup"><span data-stu-id="6ab57-166">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="6ab57-167">Меню дочерней формы объединяется с главного меню.</span><span class="sxs-lookup"><span data-stu-id="6ab57-167">The child form's menu is merged with the main menu.</span></span>  
  
3. <span data-ttu-id="6ab57-168">Закройте дочерней формы.</span><span class="sxs-lookup"><span data-stu-id="6ab57-168">Close the child form.</span></span>  
  
     <span data-ttu-id="6ab57-169">Меню дочерней формы удаляется из главного меню.</span><span class="sxs-lookup"><span data-stu-id="6ab57-169">The child form's menu is removed from the main menu.</span></span>  
  
4. <span data-ttu-id="6ab57-170">Нажмите кнопку **New** несколько раз.</span><span class="sxs-lookup"><span data-stu-id="6ab57-170">Click **New** several times.</span></span>  
  
     <span data-ttu-id="6ab57-171">Дочерние формы автоматически отображаются в категории **окно** пункт меню, поскольку <xref:System.Windows.Forms.MenuStrip> элемента управления <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> назначается свойство.</span><span class="sxs-lookup"><span data-stu-id="6ab57-171">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>  
  
## <a name="adding-toolstrip-support"></a><span data-ttu-id="6ab57-172">Добавление поддержки элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="6ab57-172">Adding ToolStrip Support</span></span>  
 <span data-ttu-id="6ab57-173">В этой процедуре вы добавите четыре <xref:System.Windows.Forms.ToolStrip> элементы управления для родительской формы MDI.</span><span class="sxs-lookup"><span data-stu-id="6ab57-173">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="6ab57-174">Каждый <xref:System.Windows.Forms.ToolStrip> будет добавлен элемент управления внутри <xref:System.Windows.Forms.ToolStripPanel> элемент управления, который присоединяется к краю формы.</span><span class="sxs-lookup"><span data-stu-id="6ab57-174">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a><span data-ttu-id="6ab57-175">Для добавления элементов управления ToolStrip в родительскую форму MDI</span><span class="sxs-lookup"><span data-stu-id="6ab57-175">To add ToolStrip controls to the MDI parent form</span></span>  
  
1. <span data-ttu-id="6ab57-176">Из **элементов**, перетащите <xref:System.Windows.Forms.ToolStripPanel> на форму.</span><span class="sxs-lookup"><span data-stu-id="6ab57-176">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>  
  
2. <span data-ttu-id="6ab57-177">С помощью <xref:System.Windows.Forms.ToolStripPanel> выбран элемент управления, дважды щелкните <xref:System.Windows.Forms.ToolStrip> контролировать **элементов**.</span><span class="sxs-lookup"><span data-stu-id="6ab57-177">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>  
  
     <span data-ttu-id="6ab57-178">Объект <xref:System.Windows.Forms.ToolStrip> создается элемент управления в <xref:System.Windows.Forms.ToolStripPanel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6ab57-178">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
3. <span data-ttu-id="6ab57-179">Выберите элемент управления <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="6ab57-179">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
4. <span data-ttu-id="6ab57-180">В окне «Свойства» измените значение элемента управления <xref:System.Windows.Forms.Control.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="6ab57-180">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>  
  
     <span data-ttu-id="6ab57-181"><xref:System.Windows.Forms.ToolStripPanel> Управления фиксирует элемент управления у левого края формы под главным меню.</span><span class="sxs-lookup"><span data-stu-id="6ab57-181">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="6ab57-182">Изменяет размер клиентской области MDI <xref:System.Windows.Forms.ToolStripPanel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6ab57-182">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
5. <span data-ttu-id="6ab57-183">Повторите шаги 1 – 4.</span><span class="sxs-lookup"><span data-stu-id="6ab57-183">Repeat steps 1 through 4.</span></span>  
  
     <span data-ttu-id="6ab57-184">Закрепите новые <xref:System.Windows.Forms.ToolStripPanel> элемента управления в верхней части формы.</span><span class="sxs-lookup"><span data-stu-id="6ab57-184">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>  
  
     <span data-ttu-id="6ab57-185"><xref:System.Windows.Forms.ToolStripPanel> Прикреплен данный элемент управления под главным меню, но справа от первого <xref:System.Windows.Forms.ToolStripPanel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6ab57-185">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="6ab57-186">В этом разделе рассмотрены важность z порядка в правильной позиционирование <xref:System.Windows.Forms.ToolStripPanel> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="6ab57-186">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
6. <span data-ttu-id="6ab57-187">Повторите шаги 1 – 4 для два раза <xref:System.Windows.Forms.ToolStripPanel> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="6ab57-187">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
     <span data-ttu-id="6ab57-188">Закрепите новые <xref:System.Windows.Forms.ToolStripPanel> элементы управления справа и внизу формы.</span><span class="sxs-lookup"><span data-stu-id="6ab57-188">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="6ab57-189">Упорядочение элементов управления ToolStripPanel по оси Z</span><span class="sxs-lookup"><span data-stu-id="6ab57-189">Arranging ToolStripPanel Controls by Z-order</span></span>  
 <span data-ttu-id="6ab57-190">Положение закрепленного <xref:System.Windows.Forms.ToolStripPanel> управления в форме MDI определяется положением элемента управления в z порядке.</span><span class="sxs-lookup"><span data-stu-id="6ab57-190">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="6ab57-191">Можно легко упорядочить z порядок элементов управления в окне "Структура документа".</span><span class="sxs-lookup"><span data-stu-id="6ab57-191">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="6ab57-192">Размещение элементов управления ToolStripPanel по оси Z</span><span class="sxs-lookup"><span data-stu-id="6ab57-192">To arrange ToolStripPanel controls by Z-order</span></span>  
  
1. <span data-ttu-id="6ab57-193">В **представление** меню, щелкните **Other Windows**, а затем нажмите кнопку **Структура документа**.</span><span class="sxs-lookup"><span data-stu-id="6ab57-193">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>  
  
     <span data-ttu-id="6ab57-194">Расположение вашего <xref:System.Windows.Forms.ToolStripPanel> нестандартные элементы управления из предыдущей процедуры.</span><span class="sxs-lookup"><span data-stu-id="6ab57-194">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="6ab57-195">Это обусловлено z порядок не верна.</span><span class="sxs-lookup"><span data-stu-id="6ab57-195">This is because the z-order is not correct.</span></span> <span data-ttu-id="6ab57-196">Используйте окно "Структура документа" для изменения z порядок элементов управления.</span><span class="sxs-lookup"><span data-stu-id="6ab57-196">Use the Document Outline window to change the z-order of the controls.</span></span>  
  
2. <span data-ttu-id="6ab57-197">В окне «Структура документа» выберите **ToolStripPanel4**.</span><span class="sxs-lookup"><span data-stu-id="6ab57-197">In the Document Outline window, select **ToolStripPanel4**.</span></span>  
  
3. <span data-ttu-id="6ab57-198">Нажмите кнопку со стрелкой вниз, пока **ToolStripPanel4** находится в нижней части списка.</span><span class="sxs-lookup"><span data-stu-id="6ab57-198">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>  
  
     <span data-ttu-id="6ab57-199">**ToolStripPanel4** прикреплен данный элемент управления в нижней части формы, под другими элементами управления.</span><span class="sxs-lookup"><span data-stu-id="6ab57-199">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>  
  
4. <span data-ttu-id="6ab57-200">Выберите **ToolStripPanel2**.</span><span class="sxs-lookup"><span data-stu-id="6ab57-200">Select **ToolStripPanel2**.</span></span>  
  
5. <span data-ttu-id="6ab57-201">Нажмите кнопку со стрелкой вниз один раз для размещения элемента управления в-третьих, в списке.</span><span class="sxs-lookup"><span data-stu-id="6ab57-201">Click the down-arrow button one time to position the control third in the list.</span></span>  
  
     <span data-ttu-id="6ab57-202">**ToolStripPanel2** прикреплен данный элемент управления в верхней части формы под главным меню и над другими элементами управления.</span><span class="sxs-lookup"><span data-stu-id="6ab57-202">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>  
  
6. <span data-ttu-id="6ab57-203">Выберите различные элементы управления в **Структура документа** окно и переместите их в разные положения в z порядка.</span><span class="sxs-lookup"><span data-stu-id="6ab57-203">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="6ab57-204">Обратите внимание на результат z порядка при размещении закрепленных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="6ab57-204">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="6ab57-205">Нажмите CTRL-z или **отменить** на **изменить** меню, чтобы отменить внесенные изменения.</span><span class="sxs-lookup"><span data-stu-id="6ab57-205">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="6ab57-206">Контрольная точка</span><span class="sxs-lookup"><span data-stu-id="6ab57-206">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="6ab57-207">Для проверки формы</span><span class="sxs-lookup"><span data-stu-id="6ab57-207">To test your form</span></span>  
  
1. <span data-ttu-id="6ab57-208">Нажмите клавишу F5, чтобы скомпилировать и запустить в форму.</span><span class="sxs-lookup"><span data-stu-id="6ab57-208">Press F5 to compile and run your form.</span></span>  
  
2. <span data-ttu-id="6ab57-209">Нажмите кнопку захвата <xref:System.Windows.Forms.ToolStrip> управления и перетащите элемент управления в различных положениях на форме.</span><span class="sxs-lookup"><span data-stu-id="6ab57-209">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>  
  
     <span data-ttu-id="6ab57-210">Можно перетащить <xref:System.Windows.Forms.ToolStrip> управления от одного <xref:System.Windows.Forms.ToolStripPanel> элемента управления в другой.</span><span class="sxs-lookup"><span data-stu-id="6ab57-210">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6ab57-211">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="6ab57-211">Next Steps</span></span>  
 <span data-ttu-id="6ab57-212">В этом пошаговом руководстве вы создали родительской формы MDI с <xref:System.Windows.Forms.ToolStrip> элементы управления и слияние меню.</span><span class="sxs-lookup"><span data-stu-id="6ab57-212">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="6ab57-213">Можно использовать <xref:System.Windows.Forms.ToolStrip> семейства элементов управления, для многих других целей:</span><span class="sxs-lookup"><span data-stu-id="6ab57-213">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="6ab57-214">Создать контекстное меню для элементов управления с <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="6ab57-214">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="6ab57-215">Дополнительные сведения см. в разделе [Общие сведения о компоненте ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6ab57-215">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="6ab57-216">Создать форму с автоматически заполненные стандартным меню.</span><span class="sxs-lookup"><span data-stu-id="6ab57-216">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="6ab57-217">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание стандартных пунктов меню для формы](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="6ab57-217">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="6ab57-218">Предоставить вашей <xref:System.Windows.Forms.ToolStrip> управляет профессиональный вид.</span><span class="sxs-lookup"><span data-stu-id="6ab57-218">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="6ab57-219">Дополнительные сведения см. в разделе [Как Назначение средства визуализации компоненту ToolStrip для приложения](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="6ab57-219">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ab57-220">См. также</span><span class="sxs-lookup"><span data-stu-id="6ab57-220">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="6ab57-221">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="6ab57-221">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="6ab57-222">Практическое руководство. Создание дочерних форм MDI</span><span class="sxs-lookup"><span data-stu-id="6ab57-222">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="6ab57-223">Практическое руководство. Вставка элемента MenuStrip в раскрывающееся меню интерфейса MDI</span><span class="sxs-lookup"><span data-stu-id="6ab57-223">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [<span data-ttu-id="6ab57-224">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="6ab57-224">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
