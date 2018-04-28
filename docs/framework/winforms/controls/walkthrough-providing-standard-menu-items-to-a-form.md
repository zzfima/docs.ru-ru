---
title: Пошаговое руководство. Создание стандартных пунктов меню для формы
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 00988266804207e85bc715342f888fd29348066e
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="6e4b6-102">Пошаговое руководство. Создание стандартных пунктов меню для формы</span><span class="sxs-lookup"><span data-stu-id="6e4b6-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>
<span data-ttu-id="6e4b6-103">С помощью элемента управления <xref:System.Windows.Forms.MenuStrip> можно создавать стандартные меню для форм.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="6e4b6-104">В этом пошаговом руководстве демонстрируется использование <xref:System.Windows.Forms.MenuStrip> управления создавать стандартные меню.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="6e4b6-105">Также форма изменяется, когда пользователь выбирает пункт меню.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="6e4b6-106">В этом пошаговом руководстве представлены следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="6e4b6-106">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="6e4b6-107">Создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-107">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="6e4b6-108">Создание стандартного меню.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-108">Creating a standard menu.</span></span>  
  
-   <span data-ttu-id="6e4b6-109">Создание <xref:System.Windows.Forms.StatusStrip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
-   <span data-ttu-id="6e4b6-110">Управление выбором элементов меню.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-110">Handling menu item selection.</span></span>  
  
 <span data-ttu-id="6e4b6-111">По завершении вы получите формы, содержащей стандартное меню, в котором отображаются выбранные элементы меню в <xref:System.Windows.Forms.StatusStrip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 <span data-ttu-id="6e4b6-112">Скопируйте код из этой темы, в разделе [как: предоставляют стандартных пунктов меню для формы](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="6e4b6-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e4b6-113">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6e4b6-114">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="6e4b6-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6e4b6-115">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="6e4b6-115">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6e4b6-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="6e4b6-116">Prerequisites</span></span>  
 <span data-ttu-id="6e4b6-117">Для выполнения данного пошагового руководства требуется:</span><span class="sxs-lookup"><span data-stu-id="6e4b6-117">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="6e4b6-118">Разрешения, необходимые для создания и выполнения проектов приложений Windows Forms на компьютере, где установлена среда Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-118">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="6e4b6-119">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="6e4b6-119">Creating the Project</span></span>  
 <span data-ttu-id="6e4b6-120">Первым шагом является создание проекта и настройка формы.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="6e4b6-121">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="6e4b6-121">To create the project</span></span>  
  
1.  <span data-ttu-id="6e4b6-122">Создайте проект приложения Windows с именем **StandardMenuForm**.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-122">Create a Windows application project called **StandardMenuForm**.</span></span>  
  
     <span data-ttu-id="6e4b6-123">Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта приложения WPF](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="6e4b6-123">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="6e4b6-124">В конструкторе Windows Forms выберите форму.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-124">In the Windows Forms Designer, select the form.</span></span>  
  
## <a name="creating-a-standard-menu"></a><span data-ttu-id="6e4b6-125">Создание стандартного меню</span><span class="sxs-lookup"><span data-stu-id="6e4b6-125">Creating a Standard Menu</span></span>  
 <span data-ttu-id="6e4b6-126">Конструктор Windows Forms может автоматически заполнять <xref:System.Windows.Forms.MenuStrip> элемента управления с помощью стандартных элементов меню.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-126">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>  
  
#### <a name="to-create-a-standard-menu"></a><span data-ttu-id="6e4b6-127">Создание стандартного меню</span><span class="sxs-lookup"><span data-stu-id="6e4b6-127">To create a standard menu</span></span>  
  
1.  <span data-ttu-id="6e4b6-128">Из **элементов**, перетащите <xref:System.Windows.Forms.MenuStrip> управления на форму.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-128">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>  
  
2.  <span data-ttu-id="6e4b6-129">Нажмите кнопку <xref:System.Windows.Forms.MenuStrip> глиф смарт-тега элемента управления (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) и выберите **вставить стандартные элементы**.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-129">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>  
  
     <span data-ttu-id="6e4b6-130"><xref:System.Windows.Forms.MenuStrip> Управления заполняется стандартных элементов меню.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-130">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>  
  
3.  <span data-ttu-id="6e4b6-131">Нажмите кнопку **файл** элемента меню, чтобы увидеть его элементы меню по умолчанию и соответствующие значки.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-131">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>  
  
## <a name="creating-a-statusstrip-control"></a><span data-ttu-id="6e4b6-132">Создание элемента управления StatusStrip</span><span class="sxs-lookup"><span data-stu-id="6e4b6-132">Creating a StatusStrip Control</span></span>  
 <span data-ttu-id="6e4b6-133">Используйте <xref:System.Windows.Forms.StatusStrip> элемента управления для отображения состояния для приложений Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-133">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="6e4b6-134">В этом примере отображаются элементы меню, выбранный пользователем в <xref:System.Windows.Forms.StatusStrip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-134">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
#### <a name="to-create-a-statusstrip-control"></a><span data-ttu-id="6e4b6-135">Создание элемента управления StatusStrip</span><span class="sxs-lookup"><span data-stu-id="6e4b6-135">To create a StatusStrip control</span></span>  
  
1.  <span data-ttu-id="6e4b6-136">Из **элементов**, перетащите <xref:System.Windows.Forms.StatusStrip> управления на форму.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-136">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>  
  
     <span data-ttu-id="6e4b6-137"><xref:System.Windows.Forms.StatusStrip> Автоматически прикреплен к нижней части формы.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-137">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>  
  
2.  <span data-ttu-id="6e4b6-138">Нажмите кнопку <xref:System.Windows.Forms.StatusStrip> разворачивающуюся кнопку элемента управления и выберите **StatusLabel** добавление <xref:System.Windows.Forms.ToolStripStatusLabel> управления <xref:System.Windows.Forms.StatusStrip> управления.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-138">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="handling-item-selection"></a><span data-ttu-id="6e4b6-139">Управление выбором элементов</span><span class="sxs-lookup"><span data-stu-id="6e4b6-139">Handling Item Selection</span></span>  
 <span data-ttu-id="6e4b6-140">Обрабатывать <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> событий, чтобы ответить, когда пользователь выбирает пункт меню.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-140">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>  
  
#### <a name="to-handle-item-selection"></a><span data-ttu-id="6e4b6-141">Чтобы управлять выбором элементов</span><span class="sxs-lookup"><span data-stu-id="6e4b6-141">To handle item selection</span></span>  
  
1.  <span data-ttu-id="6e4b6-142">Нажмите кнопку **файл** пункт меню, который был создан при создании стандартного раздела меню.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-142">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>  
  
2.  <span data-ttu-id="6e4b6-143">В **свойства** окно, нажмите кнопку **события**.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-143">In the **Properties** window, click **Events**.</span></span>  
  
3.  <span data-ttu-id="6e4b6-144">Дважды щелкните <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> событий.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-144">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
     <span data-ttu-id="6e4b6-145">Конструктор Windows Forms создает обработчик событий для <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> события.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-145">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
4.  <span data-ttu-id="6e4b6-146">Вставьте следующий код в обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-146">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  <span data-ttu-id="6e4b6-147">Вставить `UpdateStatus` программа определение метода в форму.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-147">Insert the `UpdateStatus` utility method definition into the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a><span data-ttu-id="6e4b6-148">Контрольная точка</span><span class="sxs-lookup"><span data-stu-id="6e4b6-148">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="6e4b6-149">Чтобы проверить работоспособность формы</span><span class="sxs-lookup"><span data-stu-id="6e4b6-149">To test your form</span></span>  
  
1.  <span data-ttu-id="6e4b6-150">Нажмите клавишу F5, чтобы скомпилировать и запустить форму.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-150">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="6e4b6-151">Нажмите кнопку **файл** пункт меню, чтобы открыть меню.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-151">Click the **File** menu item to open the menu.</span></span>  
  
3.  <span data-ttu-id="6e4b6-152">На **файл** меню, выберите один из элементов, чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-152">On the **File** menu, click one of the items to select it.</span></span>  
  
     <span data-ttu-id="6e4b6-153"><xref:System.Windows.Forms.StatusStrip> Элемент управления отображает выбранный элемент.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-153">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6e4b6-154">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="6e4b6-154">Next Steps</span></span>  
 <span data-ttu-id="6e4b6-155">В этом пошаговом руководстве вы создали формы, содержащей стандартное меню.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-155">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="6e4b6-156">Можно использовать <xref:System.Windows.Forms.ToolStrip> семейства элементов управления для других целей:</span><span class="sxs-lookup"><span data-stu-id="6e4b6-156">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="6e4b6-157">Создать контекстное меню для элементов управления с <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-157">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="6e4b6-158">Дополнительные сведения см. в разделе [Общие сведения о компоненте ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6e4b6-158">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="6e4b6-159">Создайте форму многодокументного интерфейса (MDI) с закрепление <xref:System.Windows.Forms.ToolStrip> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-159">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="6e4b6-160">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание формы MDI ПУТЕМ слияния меню и элементов управления ToolStrip с](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="6e4b6-160">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
-   <span data-ttu-id="6e4b6-161">Предоставьте вашей <xref:System.Windows.Forms.ToolStrip> управляет профессиональный вид.</span><span class="sxs-lookup"><span data-stu-id="6e4b6-161">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="6e4b6-162">Дополнительные сведения см. в разделе [как: задать средство отрисовки элемента управления ToolStrip для приложения](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="6e4b6-162">For more information, see [How to: Set the ToolStrip Renderer for an Application](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e4b6-163">См. также</span><span class="sxs-lookup"><span data-stu-id="6e4b6-163">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="6e4b6-164">Элемент управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="6e4b6-164">MenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
