---
title: Практическое руководство. Создание дочерних форм MDI
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: 83f94830eec1d82112719a48e8ea98e2503f4542
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124531"
---
# <a name="how-to-create-mdi-child-forms"></a><span data-ttu-id="23112-102">Практическое руководство. Создание дочерних форм MDI</span><span class="sxs-lookup"><span data-stu-id="23112-102">How to: Create MDI Child Forms</span></span>
<span data-ttu-id="23112-103">Дочерние формы MDI являются важным элементом [приложений многодокументного интерфейса (MDI)](multiple-document-interface-mdi-applications.md), как эти находятся в центре взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="23112-103">MDI child forms are an essential element of [Multiple-Document Interface (MDI) Applications](multiple-document-interface-mdi-applications.md), as these forms are the center of user interaction.</span></span>  
  
 <span data-ttu-id="23112-104">С помощью описанной ниже процедуры создаются дочерние формы MDI, отображающие элемент управления <xref:System.Windows.Forms.RichTextBox> аналогично большинству текстовых приложений.</span><span class="sxs-lookup"><span data-stu-id="23112-104">In the following procedure, you will create MDI child form that displays a <xref:System.Windows.Forms.RichTextBox> control, similar to most word-processing applications.</span></span> <span data-ttu-id="23112-105">Замена элемента управления <xref:System.Windows.Forms> на другие элементы управления, такие как <xref:System.Windows.Forms.DataGridView>, или на сочетание элементов управления позволяет создавать дочерние окна MDI (а также приложения MDI) с различными возможностями.</span><span class="sxs-lookup"><span data-stu-id="23112-105">Substituting the <xref:System.Windows.Forms> control with other controls, such as the <xref:System.Windows.Forms.DataGridView> control, or a mixture of controls enables you to create MDI child windows (and, by extension, MDI applications) with diverse possibilities.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23112-106">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="23112-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="23112-107">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="23112-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="23112-108">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="23112-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-mdi-child-forms"></a><span data-ttu-id="23112-109">Создание дочерних форм MDI</span><span class="sxs-lookup"><span data-stu-id="23112-109">To create MDI child forms</span></span>  
  
1.  <span data-ttu-id="23112-110">Создайте проект Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="23112-110">Create a new Windows Forms project.</span></span> <span data-ttu-id="23112-111">В **Windows свойства** формы, задать его <xref:System.Windows.Forms.Form.IsMdiContainer%2A> свойства `true`и его `WindowsState` свойства `Maximized`.</span><span class="sxs-lookup"><span data-stu-id="23112-111">In **the Properties Windows** for the form, set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`, and its `WindowsState` property to `Maximized`.</span></span>  
  
     <span data-ttu-id="23112-112">При этом форма назначается в качестве MDI-контейнера для дочерних окон.</span><span class="sxs-lookup"><span data-stu-id="23112-112">This designates the form as an MDI container for child windows.</span></span>  
  
2.  <span data-ttu-id="23112-113">Из `Toolbox` перетащите элемент управления <xref:System.Windows.Forms.MenuStrip> в форму.</span><span class="sxs-lookup"><span data-stu-id="23112-113">From the `Toolbox`, drag a <xref:System.Windows.Forms.MenuStrip> control to the form.</span></span> <span data-ttu-id="23112-114">Задайте его `Text` свойства **файл**.</span><span class="sxs-lookup"><span data-stu-id="23112-114">Set its `Text` property to **File**.</span></span>  
  
3.  <span data-ttu-id="23112-115">Нажмите кнопку с многоточием (...) рядом с полем **элементы** свойство и нажмите кнопку **добавить** добавить два пункта меню дочерние средство ленты.</span><span class="sxs-lookup"><span data-stu-id="23112-115">Click the ellipses (…) next to the **Items** property, and click **Add** to add two child tool strip menu items.</span></span> <span data-ttu-id="23112-116">Задайте `Text` свойства этих элементов значения **New** и **окно**.</span><span class="sxs-lookup"><span data-stu-id="23112-116">Set the `Text` property for these items to **New** and **Window**.</span></span>  
  
4.  <span data-ttu-id="23112-117">В **обозревателе решений**, щелкните правой кнопкой мыши проект, выберите пункт **добавить**, а затем выберите **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="23112-117">In **Solution Explorer**, right-click the project, point to **Add**, and then select **Add New Item**.</span></span>  
  
5.  <span data-ttu-id="23112-118">В **Добавление нового элемента** выберите **формы Windows** (в Visual Basic или Visual C#) или **приложение Windows Forms (.NET)** (в [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) из  **Шаблоны** области.</span><span class="sxs-lookup"><span data-stu-id="23112-118">In the **Add New Item** dialog box, select **Windows Form** (in Visual Basic or in Visual C#) or **Windows Forms Application (.NET)** (in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) from the **Templates** pane.</span></span> <span data-ttu-id="23112-119">В **имя** окне имя формы **Form2**.</span><span class="sxs-lookup"><span data-stu-id="23112-119">In the **Name** box, name the form **Form2**.</span></span> <span data-ttu-id="23112-120">Нажмите кнопку **откройте** кнопку, чтобы добавить форму в проект.</span><span class="sxs-lookup"><span data-stu-id="23112-120">Click the **Open** button to add the form to the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="23112-121">Дочерняя форма MDI, созданная на этом этапе, является стандартной формой Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="23112-121">The MDI child form you created in this step is a standard Windows Form.</span></span> <span data-ttu-id="23112-122">Таким образом, у нее есть свойство <xref:System.Windows.Forms.Form.Opacity%2A>, которое позволяет управлять прозрачностью формы.</span><span class="sxs-lookup"><span data-stu-id="23112-122">As such, it has an <xref:System.Windows.Forms.Form.Opacity%2A> property, which enables you to control the transparency of the form.</span></span> <span data-ttu-id="23112-123">Однако свойство <xref:System.Windows.Forms.Form.Opacity%2A> предназначено для окон верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="23112-123">However, the <xref:System.Windows.Forms.Form.Opacity%2A> property was designed for top-level windows.</span></span> <span data-ttu-id="23112-124">Его не следует использовать в дочерних формах MDI, иначе могут возникнуть проблемы с рисованием.</span><span class="sxs-lookup"><span data-stu-id="23112-124">Do not use it with MDI child forms, as painting problems can occur.</span></span>  
  
     <span data-ttu-id="23112-125">Эта форма будет шаблоном для дочерних форм MDI.</span><span class="sxs-lookup"><span data-stu-id="23112-125">This form will be the template for your MDI child forms.</span></span>  
  
     <span data-ttu-id="23112-126">**Конструктор Windows Forms** откроется, отображение **Form2**.</span><span class="sxs-lookup"><span data-stu-id="23112-126">The **Windows Forms Designer** opens, displaying **Form2**.</span></span>  
  
6.  <span data-ttu-id="23112-127">Из **элементов**, перетащите **RichTextBox** на форму элемент управления.</span><span class="sxs-lookup"><span data-stu-id="23112-127">From the **Toolbox**, drag a **RichTextBox** control to the form.</span></span>  
  
7.  <span data-ttu-id="23112-128">В **свойства** окне `Anchor` свойства **верхней, левой** и `Dock` свойства **заполнения**.</span><span class="sxs-lookup"><span data-stu-id="23112-128">In the **Properties** window, set the `Anchor` property to **Top, Left** and the `Dock` property to **Fill**.</span></span>  
  
     <span data-ttu-id="23112-129">В результате элемент управления <xref:System.Windows.Forms.RichTextBox> будет целиком заполнять область дочерней формы MDI, даже если ее размеры изменятся.</span><span class="sxs-lookup"><span data-stu-id="23112-129">This causes the <xref:System.Windows.Forms.RichTextBox> control to completely fill the area of the MDI child form, even when the form is resized.</span></span>  
  
8.  <span data-ttu-id="23112-130">Дважды щелкните **New** пункт меню, чтобы создать <xref:System.Windows.Forms.Control.Click> для него обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="23112-130">Double click the **New** menu item to create a <xref:System.Windows.Forms.Control.Click> event handler for it.</span></span>  
  
9. <span data-ttu-id="23112-131">Вставьте код, аналогичный приведенному ниже, чтобы создать новую дочернюю форму MDI, когда пользователь щелкает **New** пункта меню.</span><span class="sxs-lookup"><span data-stu-id="23112-131">Insert code similar to the following to create a new MDI child form when the user clicks the **New** menu item.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="23112-132">В примере ниже обработчик событий обрабатывает событие <xref:System.Windows.Forms.Control.Click> для `MenuItem2`.</span><span class="sxs-lookup"><span data-stu-id="23112-132">In the following example, the event handler handles the <xref:System.Windows.Forms.Control.Click> event for `MenuItem2`.</span></span> <span data-ttu-id="23112-133">Имейте в виду, что в зависимости от особенностей архитектуры приложения, ваш **New** пункт меню может быть `MenuItem2`.</span><span class="sxs-lookup"><span data-stu-id="23112-133">Be aware that, depending on the specifics of your application architecture, your **New** menu item may not be `MenuItem2`.</span></span>  
  
    ```vb  
    Protected Sub MDIChildNew_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MenuItem2.Click  
       Dim NewMDIChild As New Form2()  
       'Set the Parent Form of the Child window.  
       NewMDIChild.MdiParent = Me  
       'Display the new form.  
       NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    protected void MDIChildNew_Click(object sender, System.EventArgs e){  
       Form2 newMDIChild = new Form2();  
       // Set the Parent Form of the Child window.  
       newMDIChild.MdiParent = this;  
       // Display the new form.  
       newMDIChild.Show();  
    }  
    ```  
  
    ```cpp  
    private:  
       void menuItem2_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          Form2^ newMDIChild = gcnew Form2();  
          // Set the Parent Form of the Child window.  
          newMDIChild->MdiParent = this;  
          // Display the new form.  
          newMDIChild->Show();  
       }  
    ```  
  
     <span data-ttu-id="23112-134">При использовании [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)] добавьте следующую директиву `#include` в начало формы Form1.h:</span><span class="sxs-lookup"><span data-stu-id="23112-134">In [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], add the following `#include` directive at the top of Form1.h:</span></span>  
  
    ```cpp  
    #include "Form2.h"  
    ```  
  
10. <span data-ttu-id="23112-135">В раскрывающемся списке в верхней части **свойства** окно, выберите пункт меню, соответствующий **файл** меню и набор <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> свойство в окно <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="23112-135">In the drop-down list at the top of the **Properties** window, select the menu strip that corresponds to the **File** menu strip and set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to the Window <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
     <span data-ttu-id="23112-136">Это позволит **окно** меню, чтобы поддерживать список открытых дочерних окон MDI с флажком рядом с активным окном.</span><span class="sxs-lookup"><span data-stu-id="23112-136">This will enable the **Window** menu to maintain a list of open MDI child windows with a check mark next to the active child window.</span></span>  
  
11. <span data-ttu-id="23112-137">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="23112-137">Press F5 to run the application.</span></span> <span data-ttu-id="23112-138">Выбрав **New** из **файл** меню, можно создать дочерние формы MDI, которыми будут храниться в **окно** пункта меню.</span><span class="sxs-lookup"><span data-stu-id="23112-138">By selecting **New** from the **File** menu, you can create new MDI child forms, which are kept track of in the **Window** menu item.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="23112-139">Когда в дочерней форме MDI есть компонент <xref:System.Windows.Forms.MainMenu> (обычно обладающий структурой пунктов меню) и он открыт внутри родительской формы MDI, также имеющей компонент <xref:System.Windows.Forms.MainMenu> (обычно обладающий структурой пунктов меню), пункты меню будут объединены автоматически, если задано свойство <xref:System.Windows.Forms.MenuItem.MergeType%2A> (и, возможно, свойство <xref:System.Windows.Forms.MenuItem.MergeOrder%2A>).</span><span class="sxs-lookup"><span data-stu-id="23112-139">When an MDI child form has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items) and it is opened within an MDI parent form that has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items), the menu items will merge automatically if you have set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property (and optionally, the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property).</span></span> <span data-ttu-id="23112-140">Установите для свойства <xref:System.Windows.Forms.MenuItem.MergeType%2A> обоих компонентов <xref:System.Windows.Forms.MainMenu> и всех пунктов меню дочерней формы значение <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span><span class="sxs-lookup"><span data-stu-id="23112-140">Set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property of both <xref:System.Windows.Forms.MainMenu> components and all of the menu items of the child form to <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span></span> <span data-ttu-id="23112-141">Кроме того, установите свойство <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> таким образом, чтобы пункты обоих меню приводились в нужном порядке.</span><span class="sxs-lookup"><span data-stu-id="23112-141">Additionally, set the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property so that the menu items from both menus appear in the desired order.</span></span> <span data-ttu-id="23112-142">Необходимо помнить, что при закрытии родительской формы MDI каждая из дочерних форм MDI создает событие <xref:System.Windows.Forms.Form.Closing> до создания события <xref:System.Windows.Forms.Form.Closing> для родительской формы MDI.</span><span class="sxs-lookup"><span data-stu-id="23112-142">Moreover, keep in mind that when you close an MDI parent form, each of the MDI child forms raises a <xref:System.Windows.Forms.Form.Closing> event before the <xref:System.Windows.Forms.Form.Closing> event for the MDI parent is raised.</span></span> <span data-ttu-id="23112-143">Отмена события <xref:System.Windows.Forms.Form.Closing> дочерней формы MDI не отменяет событие <xref:System.Windows.Forms.Form.Closing> родительской формы MDI. Однако для аргумента <xref:System.ComponentModel.CancelEventArgs> для события <xref:System.Windows.Forms.Form.Closing> родительской формы MDI будет установлено значение `true`.</span><span class="sxs-lookup"><span data-stu-id="23112-143">Canceling an MDI child's <xref:System.Windows.Forms.Form.Closing> event will not prevent the MDI parent's <xref:System.Windows.Forms.Form.Closing> event from being raised; however, the <xref:System.ComponentModel.CancelEventArgs> argument for the MDI parent's <xref:System.Windows.Forms.Form.Closing> event will now be set to `true`.</span></span> <span data-ttu-id="23112-144">Чтобы принудительно закрыть родительскую и все дочерние формы MDI, задайте для аргумента <xref:System.ComponentModel.CancelEventArgs> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="23112-144">You can force the MDI parent and all MDI child forms to close by setting the <xref:System.ComponentModel.CancelEventArgs> argument to `false`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23112-145">См. также</span><span class="sxs-lookup"><span data-stu-id="23112-145">See also</span></span>

- [<span data-ttu-id="23112-146">Приложения с интерфейсом MDI</span><span class="sxs-lookup"><span data-stu-id="23112-146">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="23112-147">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="23112-147">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="23112-148">Практическое руководство. Определение активной дочерней MDI-формы</span><span class="sxs-lookup"><span data-stu-id="23112-148">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="23112-149">Практическое руководство. Отправка данных в активную дочернюю MDI-форму</span><span class="sxs-lookup"><span data-stu-id="23112-149">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="23112-150">Практическое руководство. Упорядочение дочерних MDI-форм</span><span class="sxs-lookup"><span data-stu-id="23112-150">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
