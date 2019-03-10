---
title: Практическое руководство. Добавление загрузки, сохранения и кнопки "Отмена" для Windows Forms элемента управления BindingNavigator
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: d86ded0b93d876eac4b97938678cafbb22c3ac8a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722442"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="88825-102">Практическое руководство. Добавление загрузки, сохранения и кнопки "Отмена" для Windows Forms элемента управления BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="88825-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="88825-103"><xref:System.Windows.Forms.BindingNavigator> Элемент управления является специализированным <xref:System.Windows.Forms.ToolStrip> элемент управления, который предназначен для навигации и управление элементами управления в форме, привязанных к данным.</span><span class="sxs-lookup"><span data-stu-id="88825-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>  
  
 <span data-ttu-id="88825-104">Так как это <xref:System.Windows.Forms.ToolStrip> управления <xref:System.Windows.Forms.BindingNavigator> компонента можно легко изменить для включения дополнительных или альтернативных команд для пользователя.</span><span class="sxs-lookup"><span data-stu-id="88825-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>  
  
 <span data-ttu-id="88825-105">В следующей процедуре <xref:System.Windows.Forms.TextBox> управления привязкой к данным и <xref:System.Windows.Forms.ToolStrip> изменен элемент управления, который добавляется в форму, чтобы включают загрузку, сохранить и «Отмена».</span><span class="sxs-lookup"><span data-stu-id="88825-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="88825-106">Чтобы добавить нагрузки, сохранить и Отмена кнопок к компоненту BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="88825-106">To add load, save, and cancel buttons to the BindingNavigator component</span></span>  
  
1.  <span data-ttu-id="88825-107">Добавьте элемент управления <xref:System.Windows.Forms.TextBox> в форму.</span><span class="sxs-lookup"><span data-stu-id="88825-107">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
2.  <span data-ttu-id="88825-108">Привяжите его к <xref:System.Windows.Forms.BindingSource>, который привязан к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="88825-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="88825-109">В этом примере <xref:System.Windows.Forms.BindingSource> привязан к базе данных.</span><span class="sxs-lookup"><span data-stu-id="88825-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>  
  
3.  <span data-ttu-id="88825-110">После создания набора данных и адаптер таблицы, перетащите <xref:System.Windows.Forms.BindingNavigator> на форму элемент управления.</span><span class="sxs-lookup"><span data-stu-id="88825-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>  
  
4.  <span data-ttu-id="88825-111">Задайте <xref:System.Windows.Forms.BindingNavigator> элемента управления <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> свойства <xref:System.Windows.Forms.BindingSource> на форме, которая привязывается к элементам управления.</span><span class="sxs-lookup"><span data-stu-id="88825-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>  
  
5.  <span data-ttu-id="88825-112">Выберите элемент управления <xref:System.Windows.Forms.BindingNavigator>.</span><span class="sxs-lookup"><span data-stu-id="88825-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
6.  <span data-ttu-id="88825-113">Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) поэтому **задачи BindingNavigator** диалоговое окно и выберите пункт **изменение элементов**.</span><span class="sxs-lookup"><span data-stu-id="88825-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>  
  
     <span data-ttu-id="88825-114">**Редактор коллекции элементов** отображается.</span><span class="sxs-lookup"><span data-stu-id="88825-114">The **Items Collection Editor** appears.</span></span>  
  
7.  <span data-ttu-id="88825-115">В **редактор коллекции элементов**, воспользуйтесь одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="88825-115">In the **Items Collection Editor**, complete the following:</span></span>  
  
    1.  <span data-ttu-id="88825-116">Добавить <xref:System.Windows.Forms.ToolStripSeparator> и три <xref:System.Windows.Forms.ToolStripButton> элементы, выбрав соответствующий тип <xref:System.Windows.Forms.ToolStripItem> и щелкнув **добавить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="88825-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>  
  
    2.  <span data-ttu-id="88825-117">Задайте <xref:System.Windows.Forms.ToolStripItem.Name%2A> свойство кнопки для **LoadButton**, **SaveButton**, и **CancelButton**, соответственно.</span><span class="sxs-lookup"><span data-stu-id="88825-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to **LoadButton**, **SaveButton**, and **CancelButton**, respectively.</span></span>  
  
    3.  <span data-ttu-id="88825-118">Задайте <xref:System.Windows.Forms.ToolStripItem.Text%2A> свойство кнопки для **нагрузки**, **Сохранить**, и **отменить**.</span><span class="sxs-lookup"><span data-stu-id="88825-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to **Load**, **Save**, and **Cancel**.</span></span>  
  
    4.  <span data-ttu-id="88825-119">Задайте <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> для каждой из кнопок, чтобы **текст**.</span><span class="sxs-lookup"><span data-stu-id="88825-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to **Text**.</span></span> <span data-ttu-id="88825-120">Кроме того, это свойство можно задать **изображение** или **ImageAndText**и задать изображение для отображения в <xref:System.Windows.Forms.ToolStripItem.Image%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="88825-120">Alternatively, you can set this property to **Image** or **ImageAndText**, and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>  
  
    5.  <span data-ttu-id="88825-121">Нажмите кнопку **ОК** чтобы закрыть диалоговое окно. Добавляются кнопки <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="88825-121">Click **OK** to close the dialog box.The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
8.  <span data-ttu-id="88825-122">Щелкните форму правой кнопкой мыши и выберите **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="88825-122">Right-click the form and choose **View Code**.</span></span>  
  
9. <span data-ttu-id="88825-123">В редакторе кода найдите строку кода, который загружает данные в адаптер таблицы.</span><span class="sxs-lookup"><span data-stu-id="88825-123">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="88825-124">Этот код был создан при настройке привязки данных на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="88825-124">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="88825-125">Код должен быть следующего вида: `TableAdapterName.Fill(DataSetName.TableName)`.</span><span class="sxs-lookup"><span data-stu-id="88825-125">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="88825-126">Он, скорее всего может быть в форме <xref:System.Windows.Forms.Form.Load> событий.</span><span class="sxs-lookup"><span data-stu-id="88825-126">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>  
  
10. <span data-ttu-id="88825-127">Создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> событие **нагрузки** <xref:System.Windows.Forms.ToolStripButton> созданной ранее и переместить этот код для загрузки данных в него.</span><span class="sxs-lookup"><span data-stu-id="88825-127">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Load** <xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>  
  
     <span data-ttu-id="88825-128">Код теперь должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="88825-128">Your code should now look similar to the following:</span></span>  
  
    ```vb  
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click  
        TableAdapterName.Fill(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Fill(DataSetName.TableName);  
    }  
    ```  
  
11. <span data-ttu-id="88825-129">Создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> событие **Сохранить** <xref:System.Windows.Forms.ToolStripButton> созданную ранее, и напишите код для обновления данных в таблице элемент управления привязывается к.</span><span class="sxs-lookup"><span data-stu-id="88825-129">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>  
  
    ```vb  
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click  
        TableAdapterName.Update(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void SaveButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Update(DataSetName.TableName);  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="88825-130">В некоторых случаях <xref:System.Windows.Forms.BindingNavigator> компоненты уже имеют **Сохранить** кнопки, но код не будет были созданы с помощью конструктора Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="88825-130">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component will already have a **Save** button, but no code will have been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="88825-131">В этом случае можно поместить приведенного выше кода в <xref:System.Windows.Forms.ToolStripItem.Click> обработчик событий для этой кнопки, а не создавать полностью новой кнопки на <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="88825-131">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="88825-132">Тем не менее, кнопка отключена по умолчанию, поэтому вам нужно задать <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> свойство кнопки `true` иметь кнопка работала правильно.</span><span class="sxs-lookup"><span data-stu-id="88825-132">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>
  
12. <span data-ttu-id="88825-133">Создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> событие **отменить** <xref:System.Windows.Forms.ToolStripButton> созданной ранее и написать код, чтобы отменить все изменения отображаемой записи данных.</span><span class="sxs-lookup"><span data-stu-id="88825-133">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Cancel** <xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>  
  
    ```vb  
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click  
        BindingSourceName.CancelEdit()  
    End Sub  
    ```  
  
    ```csharp  
    private void CancelButton_Click(System.Object sender, System.EventArgs e)  
    {  
        BindingSourceName.CancelEdit();  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="88825-134"><xref:System.Windows.Forms.BindingSource.CancelEdit%2A> Метод ограничивается строки данных.</span><span class="sxs-lookup"><span data-stu-id="88825-134">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="88825-135">Сохраните все изменения, внесенные во время просмотра этой отдельной записи до перехода к следующей записи.</span><span class="sxs-lookup"><span data-stu-id="88825-135">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88825-136">См. также</span><span class="sxs-lookup"><span data-stu-id="88825-136">See also</span></span>
- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="88825-137">Элемент управления BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="88825-137">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="88825-138">Общие сведения о компоненте BindingSource</span><span class="sxs-lookup"><span data-stu-id="88825-138">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)
