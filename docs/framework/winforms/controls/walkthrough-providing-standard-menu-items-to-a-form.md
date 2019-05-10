---
title: Пошаговое руководство. Связывание стандартных элементов меню с формой
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
ms.openlocfilehash: ebfacadfee3ea069359a72ea0402751e9e6280d7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211495"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="ca3ed-102">Пошаговое руководство. Связывание стандартных элементов меню с формой</span><span class="sxs-lookup"><span data-stu-id="ca3ed-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>

<span data-ttu-id="ca3ed-103">С помощью элемента управления <xref:System.Windows.Forms.MenuStrip> можно создавать стандартные меню для форм.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="ca3ed-104">В этом пошаговом руководстве демонстрируется использование <xref:System.Windows.Forms.MenuStrip> элементу управления создавать стандартные меню.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="ca3ed-105">Также форма изменяется при выборе пользователем пункта меню.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="ca3ed-106">В этом пошаговом руководстве показаны следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="ca3ed-106">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="ca3ed-107">Создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-107">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="ca3ed-108">Создание стандартного меню.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-108">Creating a standard menu.</span></span>

- <span data-ttu-id="ca3ed-109">Создание <xref:System.Windows.Forms.StatusStrip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

- <span data-ttu-id="ca3ed-110">Управление выбором элементов меню.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-110">Handling menu item selection.</span></span>

<span data-ttu-id="ca3ed-111">Когда вы закончите, вы получите формы, содержащей стандартное меню, в котором отображаются выбранные элементы меню в <xref:System.Windows.Forms.StatusStrip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

<span data-ttu-id="ca3ed-112">Чтобы скопировать код из этого раздела единым блоком, см. раздел [Практическое руководство. Обеспечивают стандартные пункты меню к форме](how-to-provide-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="ca3ed-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ca3ed-113">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="ca3ed-113">Prerequisites</span></span>

<span data-ttu-id="ca3ed-114">Вам потребуется Visual Studio для выполнения этого пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-114">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="ca3ed-115">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="ca3ed-115">Create the project</span></span>

1. <span data-ttu-id="ca3ed-116">В Visual Studio создайте проект приложения Windows с именем **StandardMenuForm** (**файл** > **New** > **проекта**   >  **Visual C#**  или **Visual Basic** > **классический рабочий стол**  >  **Windows Forms Application**).</span><span class="sxs-lookup"><span data-stu-id="ca3ed-116">In Visual Studio, create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="ca3ed-117">В конструкторе Windows Forms выберите форму.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-117">In the Windows Forms Designer, select the form.</span></span>

## <a name="create-a-standard-menu"></a><span data-ttu-id="ca3ed-118">Создание стандартного меню</span><span class="sxs-lookup"><span data-stu-id="ca3ed-118">Create a standard menu</span></span>

<span data-ttu-id="ca3ed-119">В конструкторе Windows Forms позволяет автоматически заполнять <xref:System.Windows.Forms.MenuStrip> элемента управления с помощью стандартных элементов меню.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-119">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>

1. <span data-ttu-id="ca3ed-120">Из **элементов**, перетащите <xref:System.Windows.Forms.MenuStrip> управления на форму.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-120">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>

2. <span data-ttu-id="ca3ed-121">Нажмите кнопку <xref:System.Windows.Forms.MenuStrip> глиф смарт-тега элемента управления (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) и выберите **вставить стандартные элементы**.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-121">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>

     <span data-ttu-id="ca3ed-122"><xref:System.Windows.Forms.MenuStrip> Заполнением стандартные пункты меню элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-122">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>

3. <span data-ttu-id="ca3ed-123">Нажмите кнопку **файл** элемент меню, чтобы увидеть его элементы меню по умолчанию и соответствующие значки.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-123">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>

## <a name="create-a-statusstrip-control"></a><span data-ttu-id="ca3ed-124">Создание элемента управления StatusStrip</span><span class="sxs-lookup"><span data-stu-id="ca3ed-124">Create a StatusStrip control</span></span>

<span data-ttu-id="ca3ed-125">Используйте <xref:System.Windows.Forms.StatusStrip> управления для отображения состояния для приложений Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-125">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="ca3ed-126">В этом примере элементы меню, выбранный пользователем отображаются в <xref:System.Windows.Forms.StatusStrip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-126">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

1. <span data-ttu-id="ca3ed-127">Из **элементов**, перетащите <xref:System.Windows.Forms.StatusStrip> управления на форму.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>

     <span data-ttu-id="ca3ed-128"><xref:System.Windows.Forms.StatusStrip> Автоматически прикреплен к нижней части формы.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-128">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>

2. <span data-ttu-id="ca3ed-129">Нажмите кнопку <xref:System.Windows.Forms.StatusStrip> кнопку раскрывающегося списка элемента управления и выберите **StatusLabel** добавление <xref:System.Windows.Forms.ToolStripStatusLabel> управления <xref:System.Windows.Forms.StatusStrip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-129">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>

## <a name="handle-item-selection"></a><span data-ttu-id="ca3ed-130">Управлять выбором элементов</span><span class="sxs-lookup"><span data-stu-id="ca3ed-130">Handle item selection</span></span>

<span data-ttu-id="ca3ed-131">Обрабатывать <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> событий, чтобы ответить, когда пользователь выбирает пункт меню.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-131">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>

1. <span data-ttu-id="ca3ed-132">Нажмите кнопку **файл** пункт меню, который вы создали при создании стандартного раздела меню.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-132">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>

2. <span data-ttu-id="ca3ed-133">В окне **Свойства** выберите **События**.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-133">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="ca3ed-134">Дважды щелкните <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> событий.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-134">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

     <span data-ttu-id="ca3ed-135">В конструкторе Windows Forms создает обработчик событий для <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> событий.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-135">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

4. <span data-ttu-id="ca3ed-136">Вставьте следующий код в обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-136">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. <span data-ttu-id="ca3ed-137">Вставить `UpdateStatus` определение служебного метода в форму.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-137">Insert the `UpdateStatus` utility method definition into the form.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a><span data-ttu-id="ca3ed-138">CHECKPOINT-тестирования в форму</span><span class="sxs-lookup"><span data-stu-id="ca3ed-138">Checkpoint -test your form</span></span>

1. <span data-ttu-id="ca3ed-139">Нажмите клавишу **F5** для компиляции и запуска в форму.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-139">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="ca3ed-140">Нажмите кнопку **файл** пункт меню, чтобы открыть меню.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-140">Click the **File** menu item to open the menu.</span></span>

3. <span data-ttu-id="ca3ed-141">На **файл** меню, выберите один из элементов, чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-141">On the **File** menu, click one of the items to select it.</span></span>

     <span data-ttu-id="ca3ed-142"><xref:System.Windows.Forms.StatusStrip> Элемент управления отображает выбранный элемент.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-142">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ca3ed-143">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="ca3ed-143">Next steps</span></span>

<span data-ttu-id="ca3ed-144">В этом пошаговом руководстве вы создали формы, содержащей стандартное меню.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-144">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="ca3ed-145">Можно использовать <xref:System.Windows.Forms.ToolStrip> семейства элементов управления, для многих других целей:</span><span class="sxs-lookup"><span data-stu-id="ca3ed-145">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="ca3ed-146">Создать контекстное меню для элементов управления с <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-146">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="ca3ed-147">Дополнительные сведения см. в разделе [Общие сведения о компоненте ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ca3ed-147">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="ca3ed-148">Создайте форму многодокументного интерфейса (MDI) закрепленный <xref:System.Windows.Forms.ToolStrip> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-148">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="ca3ed-149">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание формы MDI путем слияния меню и элементов управления ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ca3ed-149">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

- <span data-ttu-id="ca3ed-150">Предоставить вашей <xref:System.Windows.Forms.ToolStrip> управляет профессиональный вид.</span><span class="sxs-lookup"><span data-stu-id="ca3ed-150">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="ca3ed-151">Дополнительные сведения см. в разделе [Как Назначение средства визуализации компоненту ToolStrip для приложения](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="ca3ed-151">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ca3ed-152">См. также</span><span class="sxs-lookup"><span data-stu-id="ca3ed-152">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="ca3ed-153">Элемент управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="ca3ed-153">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
