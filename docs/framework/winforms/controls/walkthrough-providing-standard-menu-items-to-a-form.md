---
title: Пошаговое руководство. Создание стандартных пунктов меню для формы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: ee80aad445c00bb4b98b49c80495fa512150bcef
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628778"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="55232-102">Пошаговое руководство. Создание стандартных пунктов меню для формы</span><span class="sxs-lookup"><span data-stu-id="55232-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>

<span data-ttu-id="55232-103">С помощью элемента управления <xref:System.Windows.Forms.MenuStrip> можно создавать стандартные меню для форм.</span><span class="sxs-lookup"><span data-stu-id="55232-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="55232-104">В этом пошаговом руководстве показано, как использовать элемент управления <xref:System.Windows.Forms.MenuStrip> для создания стандартного меню.</span><span class="sxs-lookup"><span data-stu-id="55232-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="55232-105">Форма также реагирует, когда пользователь выбирает пункт меню.</span><span class="sxs-lookup"><span data-stu-id="55232-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="55232-106">В этом пошаговом руководстве показаны следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="55232-106">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="55232-107">Создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="55232-107">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="55232-108">Создание стандартного меню.</span><span class="sxs-lookup"><span data-stu-id="55232-108">Creating a standard menu.</span></span>

- <span data-ttu-id="55232-109">Создание элемента управления <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="55232-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

- <span data-ttu-id="55232-110">Обработка выбора пунктов меню.</span><span class="sxs-lookup"><span data-stu-id="55232-110">Handling menu item selection.</span></span>

<span data-ttu-id="55232-111">По завершении у вас будет форма со стандартным меню, которое отображает элементы меню, выделенные в элементе управления <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="55232-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

<span data-ttu-id="55232-112">Чтобы скопировать код из этого раздела в виде одного списка, см. раздел [как предоставить стандартные пункты меню в форме](how-to-provide-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="55232-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="55232-113">предварительные требования</span><span class="sxs-lookup"><span data-stu-id="55232-113">Prerequisites</span></span>

<span data-ttu-id="55232-114">Для выполнения этого пошагового руководства потребуется Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="55232-114">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="55232-115">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="55232-115">Create the project</span></span>

1. <span data-ttu-id="55232-116">В Visual Studio создайте проект приложения Windows с именем **стандардменуформ** (**File** > **New** > **Project** > **Visual C#**  или **Visual Basic** > **классический Настольный компьютер** > **приложение**).</span><span class="sxs-lookup"><span data-stu-id="55232-116">In Visual Studio, create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="55232-117">В конструктор Windows Forms выберите форму.</span><span class="sxs-lookup"><span data-stu-id="55232-117">In the Windows Forms Designer, select the form.</span></span>

## <a name="create-a-standard-menu"></a><span data-ttu-id="55232-118">Создание стандартного меню</span><span class="sxs-lookup"><span data-stu-id="55232-118">Create a standard menu</span></span>

<span data-ttu-id="55232-119">Конструктор Windows Forms может автоматически заполнять элемент управления <xref:System.Windows.Forms.MenuStrip> с помощью стандартных пунктов меню.</span><span class="sxs-lookup"><span data-stu-id="55232-119">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>

1. <span data-ttu-id="55232-120">Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.MenuStrip> на форму.</span><span class="sxs-lookup"><span data-stu-id="55232-120">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>

2. <span data-ttu-id="55232-121">Щелкните глиф действий конструктора <xref:System.Windows.Forms.MenuStrip> элемента управления (![маленькая черная стрелка](./media/designer-actions-glyph.gif)) и выберите **Вставить стандартные элементы**.</span><span class="sxs-lookup"><span data-stu-id="55232-121">Click the <xref:System.Windows.Forms.MenuStrip> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) and select **Insert Standard Items**.</span></span>

     <span data-ttu-id="55232-122">Элемент управления <xref:System.Windows.Forms.MenuStrip> заполняется стандартными элементами меню.</span><span class="sxs-lookup"><span data-stu-id="55232-122">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>

3. <span data-ttu-id="55232-123">Щелкните пункт меню **файл** , чтобы просмотреть элементы меню по умолчанию и соответствующие значки.</span><span class="sxs-lookup"><span data-stu-id="55232-123">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>

## <a name="create-a-statusstrip-control"></a><span data-ttu-id="55232-124">Создание элемента управления StatusStrip</span><span class="sxs-lookup"><span data-stu-id="55232-124">Create a StatusStrip control</span></span>

<span data-ttu-id="55232-125">Используйте элемент управления <xref:System.Windows.Forms.StatusStrip> для просмотра состояния приложений Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="55232-125">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="55232-126">В текущем примере пункты меню, выбранные пользователем, отображаются в элементе управления <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="55232-126">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

1. <span data-ttu-id="55232-127">Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.StatusStrip> на форму.</span><span class="sxs-lookup"><span data-stu-id="55232-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>

     <span data-ttu-id="55232-128">Элемент управления <xref:System.Windows.Forms.StatusStrip> автоматически закрепляется в нижней части формы.</span><span class="sxs-lookup"><span data-stu-id="55232-128">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>

2. <span data-ttu-id="55232-129">Нажмите кнопку раскрывающегося списка <xref:System.Windows.Forms.StatusStrip> элемента управления и выберите **значение statuslabel как** , чтобы добавить элемент управления <xref:System.Windows.Forms.ToolStripStatusLabel> в элемент управления <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="55232-129">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>

## <a name="handle-item-selection"></a><span data-ttu-id="55232-130">Выбор элементов в обработке</span><span class="sxs-lookup"><span data-stu-id="55232-130">Handle item selection</span></span>

<span data-ttu-id="55232-131">Обработка события <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> для реагирования, когда пользователь выбирает пункт меню.</span><span class="sxs-lookup"><span data-stu-id="55232-131">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>

1. <span data-ttu-id="55232-132">Щелкните элемент меню **файл** , созданный в разделе Создание стандартного меню.</span><span class="sxs-lookup"><span data-stu-id="55232-132">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>

2. <span data-ttu-id="55232-133">В окне **Свойства** выберите **События**.</span><span class="sxs-lookup"><span data-stu-id="55232-133">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="55232-134">Дважды щелкните событие <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>.</span><span class="sxs-lookup"><span data-stu-id="55232-134">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

     <span data-ttu-id="55232-135">Конструктор Windows Forms создает обработчик событий для события <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>.</span><span class="sxs-lookup"><span data-stu-id="55232-135">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

4. <span data-ttu-id="55232-136">Вставьте следующий код в обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="55232-136">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. <span data-ttu-id="55232-137">Вставьте в форму определение метода служебной программы `UpdateStatus`.</span><span class="sxs-lookup"><span data-stu-id="55232-137">Insert the `UpdateStatus` utility method definition into the form.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a><span data-ttu-id="55232-138">Контрольная точка — тестирование формы</span><span class="sxs-lookup"><span data-stu-id="55232-138">Checkpoint -test your form</span></span>

1. <span data-ttu-id="55232-139">Нажмите клавишу **F5** , чтобы скомпилировать и запустить форму.</span><span class="sxs-lookup"><span data-stu-id="55232-139">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="55232-140">Щелкните пункт меню **файл** , чтобы открыть меню.</span><span class="sxs-lookup"><span data-stu-id="55232-140">Click the **File** menu item to open the menu.</span></span>

3. <span data-ttu-id="55232-141">В меню **файл** выберите один из элементов, чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="55232-141">On the **File** menu, click one of the items to select it.</span></span>

     <span data-ttu-id="55232-142">Элемент управления <xref:System.Windows.Forms.StatusStrip> отображает выбранный элемент.</span><span class="sxs-lookup"><span data-stu-id="55232-142">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="55232-143">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="55232-143">Next steps</span></span>

<span data-ttu-id="55232-144">В этом пошаговом руководстве вы создали форму со стандартным меню.</span><span class="sxs-lookup"><span data-stu-id="55232-144">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="55232-145">Семейство элементов управления <xref:System.Windows.Forms.ToolStrip> можно использовать для многих других целей:</span><span class="sxs-lookup"><span data-stu-id="55232-145">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="55232-146">Создайте контекстные меню для элементов управления с помощью <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="55232-146">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="55232-147">Дополнительные сведения см. в разделе [Общие сведения о компоненте ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="55232-147">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="55232-148">Создание формы многодокументного интерфейса (MDI) с закреплением <xref:System.Windows.Forms.ToolStrip> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="55232-148">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="55232-149">Дополнительные сведения см. в разделе [Пошаговое руководство. Создание формы MDI с помощью слияния меню и элементов управления ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="55232-149">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

- <span data-ttu-id="55232-150">Придайте <xref:System.Windows.Forms.ToolStrip> элементам управления профессиональный внешний вид.</span><span class="sxs-lookup"><span data-stu-id="55232-150">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="55232-151">Дополнительные сведения см. [в разделе как задать модуль подготовки отчетов ToolStrip для приложения](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="55232-151">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="55232-152">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="55232-152">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="55232-153">Элемент управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="55232-153">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
