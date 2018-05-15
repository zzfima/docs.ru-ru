---
title: Практическое руководство. Добавление кнопок загрузки, сохранения и отмены в элемент управления BindingNavigator в формах Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: 8f331c67dd22a6a9e2382ecc11d23c67cd2a5cbc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="5e83d-102">Практическое руководство. Добавление кнопок загрузки, сохранения и отмены в элемент управления BindingNavigator в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5e83d-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="5e83d-103"><xref:System.Windows.Forms.BindingNavigator> Управления является специализированным <xref:System.Windows.Forms.ToolStrip> элемент управления, который предназначен для навигации и управления элементами управления в форме, привязанных к данным.</span><span class="sxs-lookup"><span data-stu-id="5e83d-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>  
  
 <span data-ttu-id="5e83d-104">Так как это <xref:System.Windows.Forms.ToolStrip> управления <xref:System.Windows.Forms.BindingNavigator> компонента можно легко изменить для включения дополнительных или альтернативных команд для пользователя.</span><span class="sxs-lookup"><span data-stu-id="5e83d-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>  
  
 <span data-ttu-id="5e83d-105">В следующей процедуре <xref:System.Windows.Forms.TextBox> элемент управления привязан к данным и <xref:System.Windows.Forms.ToolStrip> элемента управления, который добавляется в форму изменяются так, чтобы включить загрузки, сохранения и кнопки отмены.</span><span class="sxs-lookup"><span data-stu-id="5e83d-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="5e83d-106">Чтобы добавить нагрузки, сохранить и Отмена кнопки для компонента BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="5e83d-106">To add load, save, and cancel buttons to the BindingNavigator component</span></span>  
  
1.  <span data-ttu-id="5e83d-107">Добавьте элемент управления <xref:System.Windows.Forms.TextBox> в форму.</span><span class="sxs-lookup"><span data-stu-id="5e83d-107">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
2.  <span data-ttu-id="5e83d-108">Привяжите его к <xref:System.Windows.Forms.BindingSource>, который привязан к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="5e83d-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="5e83d-109">В этом примере <xref:System.Windows.Forms.BindingSource> привязан к базе данных.</span><span class="sxs-lookup"><span data-stu-id="5e83d-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>  
  
3.  <span data-ttu-id="5e83d-110">После создания набора данных и адаптер таблицы перетащите <xref:System.Windows.Forms.BindingNavigator> на форму элемент управления.</span><span class="sxs-lookup"><span data-stu-id="5e83d-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>  
  
4.  <span data-ttu-id="5e83d-111">Задать <xref:System.Windows.Forms.BindingNavigator> элемента управления <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> свойства <xref:System.Windows.Forms.BindingSource> формы, который привязан к элементам управления.</span><span class="sxs-lookup"><span data-stu-id="5e83d-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>  
  
5.  <span data-ttu-id="5e83d-112">Выберите элемент управления <xref:System.Windows.Forms.BindingNavigator>.</span><span class="sxs-lookup"><span data-stu-id="5e83d-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
6.  <span data-ttu-id="5e83d-113">Щелкните глиф смарт-тега (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) таким образом **задачи BindingNavigator** диалоговое окно и выберите пункт **изменение элементов**.</span><span class="sxs-lookup"><span data-stu-id="5e83d-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>  
  
     <span data-ttu-id="5e83d-114">**Редактор коллекции элементов** отображается.</span><span class="sxs-lookup"><span data-stu-id="5e83d-114">The **Items Collection Editor** appears.</span></span>  
  
7.  <span data-ttu-id="5e83d-115">В **редактор коллекции элементов**, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5e83d-115">In the **Items Collection Editor**, complete the following:</span></span>  
  
    1.  <span data-ttu-id="5e83d-116">Добавить <xref:System.Windows.Forms.ToolStripSeparator> и три <xref:System.Windows.Forms.ToolStripButton> элементы, выбрав соответствующий тип <xref:System.Windows.Forms.ToolStripItem> и щелкнув **добавить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="5e83d-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>  
  
    2.  <span data-ttu-id="5e83d-117">Задать <xref:System.Windows.Forms.ToolStripItem.Name%2A> свойства кнопки, чтобы**LoadButton**,**SaveButton**, и**CancelButton**соответственно.</span><span class="sxs-lookup"><span data-stu-id="5e83d-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to**LoadButton**,**SaveButton**, and**CancelButton**, respectively.</span></span>  
  
    3.  <span data-ttu-id="5e83d-118">Задать <xref:System.Windows.Forms.ToolStripItem.Text%2A> свойства кнопки, чтобы**нагрузки** `,` **Сохранить**, и**отменить**.</span><span class="sxs-lookup"><span data-stu-id="5e83d-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to**Load**`,` **Save**, and**Cancel**.</span></span>  
  
    4.  <span data-ttu-id="5e83d-119">Задать <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> для каждой из кнопок, чтобы**текст**.</span><span class="sxs-lookup"><span data-stu-id="5e83d-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to**Text**.</span></span> <span data-ttu-id="5e83d-120">Кроме того, можно задать это свойство**изображения**или**ImageAndText**и задать изображение, отображаемое в <xref:System.Windows.Forms.ToolStripItem.Image%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="5e83d-120">Alternatively, you can set this property to**Image**or**ImageAndText**and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>  
  
    5.  <span data-ttu-id="5e83d-121">Нажмите кнопку **ОК** чтобы закрыть диалоговое окно. Добавляются кнопки <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="5e83d-121">Click **OK** to close the dialog box.The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
8.  <span data-ttu-id="5e83d-122">Щелкните форму правой кнопкой мыши и выберите **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="5e83d-122">Right-click the form and choose **View Code**.</span></span>  
  
9. <span data-ttu-id="5e83d-123">В редакторе кода найдите строку кода, которая загружает данные в адаптер таблицы.</span><span class="sxs-lookup"><span data-stu-id="5e83d-123">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="5e83d-124">Этот код был создан при настройке привязки данных в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="5e83d-124">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="5e83d-125">Код должен быть примерно следующего содержания: `TableAdapterName.Fill(DataSetName.TableName)`.</span><span class="sxs-lookup"><span data-stu-id="5e83d-125">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="5e83d-126">Он будет большинство скорее всего, в форме <xref:System.Windows.Forms.Form.Load> событий.</span><span class="sxs-lookup"><span data-stu-id="5e83d-126">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>  
  
10. <span data-ttu-id="5e83d-127">Создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> событие**нагрузки** <xref:System.Windows.Forms.ToolStripButton> созданной ранее и переместите этот код загрузки данных в нее.</span><span class="sxs-lookup"><span data-stu-id="5e83d-127">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the**Load**<xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>  
  
     <span data-ttu-id="5e83d-128">Код должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5e83d-128">Your code should now look similar to the following:</span></span>  
  
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
  
11. <span data-ttu-id="5e83d-129">Создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> событие **Сохранить** <xref:System.Windows.Forms.ToolStripButton> созданную ранее, и напишите код для обновления данных в таблице элемент управления привязан к.</span><span class="sxs-lookup"><span data-stu-id="5e83d-129">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>  
  
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
    >  <span data-ttu-id="5e83d-130">В некоторых случаях <xref:System.Windows.Forms.BindingNavigator> компонент уже будет иметь**Сохранить** кнопки, но код не будет были созданы с помощью конструктора Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5e83d-130">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component will already have a**Save** button, but no code will have been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="5e83d-131">В этом случае можно поместить приведенного выше кода в <xref:System.Windows.Forms.ToolStripItem.Click> обработчик событий для кнопки, а не создавать полностью новой кнопки на <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="5e83d-131">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="5e83d-132">Однако кнопка становится недоступной, по умолчанию, поэтому необходимо задать <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> свойства кнопки, чтобы `true` иметь кнопка работала правильно.</span><span class="sxs-lookup"><span data-stu-id="5e83d-132">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>  
  
12. <span data-ttu-id="5e83d-133">Создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> событие**отменить** <xref:System.Windows.Forms.ToolStripButton> созданной ранее и написать код для отмены любых изменений отображаемой записи данных.</span><span class="sxs-lookup"><span data-stu-id="5e83d-133">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the**Cancel**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>  
  
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
    >  <span data-ttu-id="5e83d-134"><xref:System.Windows.Forms.BindingSource.CancelEdit%2A> Метод распространяется на строку данных.</span><span class="sxs-lookup"><span data-stu-id="5e83d-134">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="5e83d-135">Сохраните все изменения, внесенные во время просмотра этой отдельной записи до перехода к следующей записи.</span><span class="sxs-lookup"><span data-stu-id="5e83d-135">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e83d-136">См. также</span><span class="sxs-lookup"><span data-stu-id="5e83d-136">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.ToolStrip>  
 [<span data-ttu-id="5e83d-137">Элемент управления BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="5e83d-137">BindingNavigator Control</span></span>](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [<span data-ttu-id="5e83d-138">Общие сведения о компоненте BindingSource</span><span class="sxs-lookup"><span data-stu-id="5e83d-138">BindingSource Component Overview</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)
