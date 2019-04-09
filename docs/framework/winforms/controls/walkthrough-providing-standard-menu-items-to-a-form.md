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
ms.openlocfilehash: f9e54ecd49fc3bd295f236292715393358bab0b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094883"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="f7402-102">Пошаговое руководство. Связывание стандартных элементов меню с формой</span><span class="sxs-lookup"><span data-stu-id="f7402-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>
<span data-ttu-id="f7402-103">С помощью элемента управления <xref:System.Windows.Forms.MenuStrip> можно создавать стандартные меню для форм.</span><span class="sxs-lookup"><span data-stu-id="f7402-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="f7402-104">В этом пошаговом руководстве демонстрируется использование <xref:System.Windows.Forms.MenuStrip> элементу управления создавать стандартные меню.</span><span class="sxs-lookup"><span data-stu-id="f7402-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="f7402-105">Также форма изменяется при выборе пользователем пункта меню.</span><span class="sxs-lookup"><span data-stu-id="f7402-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="f7402-106">В этом пошаговом руководстве показаны следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="f7402-106">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="f7402-107">Создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f7402-107">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="f7402-108">Создание стандартного меню.</span><span class="sxs-lookup"><span data-stu-id="f7402-108">Creating a standard menu.</span></span>  
  
-   <span data-ttu-id="f7402-109">Создание <xref:System.Windows.Forms.StatusStrip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f7402-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
-   <span data-ttu-id="f7402-110">Управление выбором элементов меню.</span><span class="sxs-lookup"><span data-stu-id="f7402-110">Handling menu item selection.</span></span>  
  
 <span data-ttu-id="f7402-111">Когда вы закончите, вы получите формы, содержащей стандартное меню, в котором отображаются выбранные элементы меню в <xref:System.Windows.Forms.StatusStrip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f7402-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 <span data-ttu-id="f7402-112">Чтобы скопировать код из этого раздела единым блоком, см. раздел [Практическое руководство. Обеспечивают стандартные пункты меню к форме](how-to-provide-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="f7402-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7402-113">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="f7402-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f7402-114">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="f7402-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f7402-115">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="f7402-115">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f7402-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f7402-116">Prerequisites</span></span>  
 <span data-ttu-id="f7402-117">Для выполнения данного пошагового руководства требуется:</span><span class="sxs-lookup"><span data-stu-id="f7402-117">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="f7402-118">Разрешения, необходимые для создания и выполнения проектов приложений Windows Forms на компьютере, на котором установлена Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f7402-118">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="f7402-119">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="f7402-119">Creating the Project</span></span>  
 <span data-ttu-id="f7402-120">Первым шагом является создание проекта и настройка формы.</span><span class="sxs-lookup"><span data-stu-id="f7402-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="f7402-121">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="f7402-121">To create the project</span></span>  
  
1.  <span data-ttu-id="f7402-122">Создайте проект приложения Windows с именем **StandardMenuForm** (**файл** > **New** > **проекта**  >  **Visual C#** или **Visual Basic** > **классический рабочий стол** > **Windows Forms Приложение**).</span><span class="sxs-lookup"><span data-stu-id="f7402-122">Create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="f7402-123">В конструкторе Windows Forms выберите форму.</span><span class="sxs-lookup"><span data-stu-id="f7402-123">In the Windows Forms Designer, select the form.</span></span>  
  
## <a name="creating-a-standard-menu"></a><span data-ttu-id="f7402-124">Создание стандартного меню</span><span class="sxs-lookup"><span data-stu-id="f7402-124">Creating a Standard Menu</span></span>  
 <span data-ttu-id="f7402-125">В конструкторе Windows Forms позволяет автоматически заполнять <xref:System.Windows.Forms.MenuStrip> элемента управления с помощью стандартных элементов меню.</span><span class="sxs-lookup"><span data-stu-id="f7402-125">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>  
  
#### <a name="to-create-a-standard-menu"></a><span data-ttu-id="f7402-126">Создание стандартного меню</span><span class="sxs-lookup"><span data-stu-id="f7402-126">To create a standard menu</span></span>  
  
1.  <span data-ttu-id="f7402-127">Из **элементов**, перетащите <xref:System.Windows.Forms.MenuStrip> управления на форму.</span><span class="sxs-lookup"><span data-stu-id="f7402-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>  
  
2.  <span data-ttu-id="f7402-128">Нажмите кнопку <xref:System.Windows.Forms.MenuStrip> глиф смарт-тега элемента управления (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) и выберите **вставить стандартные элементы**.</span><span class="sxs-lookup"><span data-stu-id="f7402-128">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>  
  
     <span data-ttu-id="f7402-129"><xref:System.Windows.Forms.MenuStrip> Заполнением стандартные пункты меню элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f7402-129">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>  
  
3.  <span data-ttu-id="f7402-130">Нажмите кнопку **файл** элемент меню, чтобы увидеть его элементы меню по умолчанию и соответствующие значки.</span><span class="sxs-lookup"><span data-stu-id="f7402-130">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>  
  
## <a name="creating-a-statusstrip-control"></a><span data-ttu-id="f7402-131">Создание элемента управления StatusStrip</span><span class="sxs-lookup"><span data-stu-id="f7402-131">Creating a StatusStrip Control</span></span>  
 <span data-ttu-id="f7402-132">Используйте <xref:System.Windows.Forms.StatusStrip> управления для отображения состояния для приложений Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f7402-132">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="f7402-133">В этом примере элементы меню, выбранный пользователем отображаются в <xref:System.Windows.Forms.StatusStrip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f7402-133">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
#### <a name="to-create-a-statusstrip-control"></a><span data-ttu-id="f7402-134">Создание элемента управления StatusStrip</span><span class="sxs-lookup"><span data-stu-id="f7402-134">To create a StatusStrip control</span></span>  
  
1.  <span data-ttu-id="f7402-135">Из **элементов**, перетащите <xref:System.Windows.Forms.StatusStrip> управления на форму.</span><span class="sxs-lookup"><span data-stu-id="f7402-135">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>  
  
     <span data-ttu-id="f7402-136"><xref:System.Windows.Forms.StatusStrip> Автоматически прикреплен к нижней части формы.</span><span class="sxs-lookup"><span data-stu-id="f7402-136">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>  
  
2.  <span data-ttu-id="f7402-137">Нажмите кнопку <xref:System.Windows.Forms.StatusStrip> кнопку раскрывающегося списка элемента управления и выберите **StatusLabel** добавление <xref:System.Windows.Forms.ToolStripStatusLabel> управления <xref:System.Windows.Forms.StatusStrip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f7402-137">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="handling-item-selection"></a><span data-ttu-id="f7402-138">Управление выбором элементов</span><span class="sxs-lookup"><span data-stu-id="f7402-138">Handling Item Selection</span></span>  
 <span data-ttu-id="f7402-139">Обрабатывать <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> событий, чтобы ответить, когда пользователь выбирает пункт меню.</span><span class="sxs-lookup"><span data-stu-id="f7402-139">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>  
  
#### <a name="to-handle-item-selection"></a><span data-ttu-id="f7402-140">Чтобы управлять выбором элементов</span><span class="sxs-lookup"><span data-stu-id="f7402-140">To handle item selection</span></span>  
  
1.  <span data-ttu-id="f7402-141">Нажмите кнопку **файл** пункт меню, который вы создали при создании стандартного раздела меню.</span><span class="sxs-lookup"><span data-stu-id="f7402-141">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>  
  
2.  <span data-ttu-id="f7402-142">В окне **Свойства** выберите **События**.</span><span class="sxs-lookup"><span data-stu-id="f7402-142">In the **Properties** window, click **Events**.</span></span>  
  
3.  <span data-ttu-id="f7402-143">Дважды щелкните <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> событий.</span><span class="sxs-lookup"><span data-stu-id="f7402-143">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
     <span data-ttu-id="f7402-144">В конструкторе Windows Forms создает обработчик событий для <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> событий.</span><span class="sxs-lookup"><span data-stu-id="f7402-144">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
4.  <span data-ttu-id="f7402-145">Вставьте следующий код в обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="f7402-145">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  <span data-ttu-id="f7402-146">Вставить `UpdateStatus` определение служебного метода в форму.</span><span class="sxs-lookup"><span data-stu-id="f7402-146">Insert the `UpdateStatus` utility method definition into the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a><span data-ttu-id="f7402-147">Контрольная точка</span><span class="sxs-lookup"><span data-stu-id="f7402-147">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="f7402-148">Для проверки формы</span><span class="sxs-lookup"><span data-stu-id="f7402-148">To test your form</span></span>  
  
1.  <span data-ttu-id="f7402-149">Нажмите клавишу F5, чтобы скомпилировать и запустить в форму.</span><span class="sxs-lookup"><span data-stu-id="f7402-149">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="f7402-150">Нажмите кнопку **файл** пункт меню, чтобы открыть меню.</span><span class="sxs-lookup"><span data-stu-id="f7402-150">Click the **File** menu item to open the menu.</span></span>  
  
3.  <span data-ttu-id="f7402-151">На **файл** меню, выберите один из элементов, чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="f7402-151">On the **File** menu, click one of the items to select it.</span></span>  
  
     <span data-ttu-id="f7402-152"><xref:System.Windows.Forms.StatusStrip> Элемент управления отображает выбранный элемент.</span><span class="sxs-lookup"><span data-stu-id="f7402-152">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f7402-153">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="f7402-153">Next Steps</span></span>  
 <span data-ttu-id="f7402-154">В этом пошаговом руководстве вы создали формы, содержащей стандартное меню.</span><span class="sxs-lookup"><span data-stu-id="f7402-154">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="f7402-155">Можно использовать <xref:System.Windows.Forms.ToolStrip> семейства элементов управления, для многих других целей:</span><span class="sxs-lookup"><span data-stu-id="f7402-155">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="f7402-156">Создать контекстное меню для элементов управления с <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="f7402-156">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="f7402-157">Дополнительные сведения см. в разделе [Общие сведения о компоненте ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f7402-157">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="f7402-158">Создайте форму многодокументного интерфейса (MDI) закрепленный <xref:System.Windows.Forms.ToolStrip> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="f7402-158">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="f7402-159">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание формы MDI путем слияния меню и элементов управления ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="f7402-159">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
-   <span data-ttu-id="f7402-160">Предоставить вашей <xref:System.Windows.Forms.ToolStrip> управляет профессиональный вид.</span><span class="sxs-lookup"><span data-stu-id="f7402-160">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="f7402-161">Дополнительные сведения см. в разделе [Как Назначение средства визуализации компоненту ToolStrip для приложения](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="f7402-161">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7402-162">См. также</span><span class="sxs-lookup"><span data-stu-id="f7402-162">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="f7402-163">Элемент управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="f7402-163">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
