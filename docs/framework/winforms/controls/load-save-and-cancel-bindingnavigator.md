---
title: Добавление кнопок загрузки, сохранения и отмены в элемент управления BindingNavigator
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: 0305df5e7566f9441ce09fa3346a8b2dc67c8943
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627972"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="e9716-102">Практическое руководство. Добавление кнопок загрузки, сохранения и отмены в элемент управления BindingNavigator в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e9716-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>

<span data-ttu-id="e9716-103">Элемент управления <xref:System.Windows.Forms.BindingNavigator> — это специальный <xref:System.Windows.Forms.ToolStrip>ный элемент управления, предназначенный для навигации по элементам управления формы, которые привязаны к данным, и манипуляций с ними.</span><span class="sxs-lookup"><span data-stu-id="e9716-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>

<span data-ttu-id="e9716-104">Поскольку это элемент управления <xref:System.Windows.Forms.ToolStrip>, компонент <xref:System.Windows.Forms.BindingNavigator> можно легко изменить, чтобы включить дополнительные или альтернативные команды для пользователя.</span><span class="sxs-lookup"><span data-stu-id="e9716-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>

<span data-ttu-id="e9716-105">В следующей процедуре элемент управления <xref:System.Windows.Forms.TextBox> привязан к данным, а элемент управления <xref:System.Windows.Forms.ToolStrip>, добавляемый в форму, изменяется для включения кнопок загрузки, сохранения и отмены.</span><span class="sxs-lookup"><span data-stu-id="e9716-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="e9716-106">Добавление кнопок загрузки, сохранения и отмены в компонент BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="e9716-106">Add load, save, and cancel buttons to the BindingNavigator component</span></span>

1. <span data-ttu-id="e9716-107">В Visual Studio добавьте в форму элемент управления <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="e9716-107">In Visual Studio, add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>

2. <span data-ttu-id="e9716-108">Привяжите его к <xref:System.Windows.Forms.BindingSource>, привязанному к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="e9716-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="e9716-109">В этом примере <xref:System.Windows.Forms.BindingSource> привязан к базе данных.</span><span class="sxs-lookup"><span data-stu-id="e9716-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>

3. <span data-ttu-id="e9716-110">После создания набора данных и адаптера таблицы перетащите элемент управления <xref:System.Windows.Forms.BindingNavigator> в форму.</span><span class="sxs-lookup"><span data-stu-id="e9716-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>

4. <span data-ttu-id="e9716-111">Задайте для свойства <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> элемента управления <xref:System.Windows.Forms.BindingNavigator> <xref:System.Windows.Forms.BindingSource> в форме, привязанной к элементам управления.</span><span class="sxs-lookup"><span data-stu-id="e9716-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>

5. <span data-ttu-id="e9716-112">Выберите элемент управления <xref:System.Windows.Forms.BindingNavigator>.</span><span class="sxs-lookup"><span data-stu-id="e9716-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>

6. <span data-ttu-id="e9716-113">Щелкните глиф действия конструктора (![маленькая черная стрелка](./media/designer-actions-glyph.gif)), чтобы появилась диалоговое окно **Задачи BindingNavigator** , и выберите **изменить элементы**.</span><span class="sxs-lookup"><span data-stu-id="e9716-113">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>

     <span data-ttu-id="e9716-114">Откроется **Редактор коллекции элементов** .</span><span class="sxs-lookup"><span data-stu-id="e9716-114">The **Items Collection Editor** appears.</span></span>

7. <span data-ttu-id="e9716-115">В **редакторе коллекции элементов**выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e9716-115">In the **Items Collection Editor**, complete the following:</span></span>

    1. <span data-ttu-id="e9716-116">Добавьте <xref:System.Windows.Forms.ToolStripSeparator> и три <xref:System.Windows.Forms.ToolStripButton> элементы, выбрав соответствующий тип <xref:System.Windows.Forms.ToolStripItem> и нажав кнопку **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="e9716-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>

    2. <span data-ttu-id="e9716-117">Задайте для свойства <xref:System.Windows.Forms.ToolStripItem.Name%2A> кнопок значение **лоадбуттон**, **савебуттон**и **CancelButton**соответственно.</span><span class="sxs-lookup"><span data-stu-id="e9716-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to **LoadButton**, **SaveButton**, and **CancelButton**, respectively.</span></span>

    3. <span data-ttu-id="e9716-118">Задайте для свойства <xref:System.Windows.Forms.ToolStripItem.Text%2A> кнопок значение **загружать**, **сохранять**и **отменять**.</span><span class="sxs-lookup"><span data-stu-id="e9716-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to **Load**, **Save**, and **Cancel**.</span></span>

    4. <span data-ttu-id="e9716-119">Присвойте свойству <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> для каждой кнопки значение **Text**.</span><span class="sxs-lookup"><span data-stu-id="e9716-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to **Text**.</span></span> <span data-ttu-id="e9716-120">Кроме того, можно задать для этого свойства значение **Image** или **имажеандтекст**и задать отображение изображения в свойстве <xref:System.Windows.Forms.ToolStripItem.Image%2A>.</span><span class="sxs-lookup"><span data-stu-id="e9716-120">Alternatively, you can set this property to **Image** or **ImageAndText**, and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>

    5. <span data-ttu-id="e9716-121">Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="e9716-121">Click **OK** to close the dialog box.</span></span> <span data-ttu-id="e9716-122">Кнопки добавляются в <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="e9716-122">The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>

8. <span data-ttu-id="e9716-123">Щелкните форму правой кнопкой мыши и выберите команду **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="e9716-123">Right-click the form and choose **View Code**.</span></span>

9. <span data-ttu-id="e9716-124">В редакторе кода найдите строку кода, которая загружает данные в адаптер таблицы.</span><span class="sxs-lookup"><span data-stu-id="e9716-124">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="e9716-125">Этот код был создан при настройке привязки данных на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="e9716-125">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="e9716-126">Код должен иметь следующий вид: `TableAdapterName.Fill(DataSetName.TableName)`.</span><span class="sxs-lookup"><span data-stu-id="e9716-126">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="e9716-127">Скорее всего, это будет событие <xref:System.Windows.Forms.Form.Load> формы.</span><span class="sxs-lookup"><span data-stu-id="e9716-127">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>

10. <span data-ttu-id="e9716-128">Создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click>ного события **нагрузки** <xref:System.Windows.Forms.ToolStripButton>, созданного ранее, и переместите этот код загрузки данных в него.</span><span class="sxs-lookup"><span data-stu-id="e9716-128">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Load** <xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>

     <span data-ttu-id="e9716-129">Теперь ваш код должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e9716-129">Your code should now look similar to the following:</span></span>

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

11. <span data-ttu-id="e9716-130">Создайте обработчик события <xref:System.Windows.Forms.ToolStripItem.Click> для события<xref:System.Windows.Forms.ToolStripButton>, созданного **ранее, и** напишите код для обновления данных в таблице, к которой привязан элемент управления.</span><span class="sxs-lookup"><span data-stu-id="e9716-130">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>

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
    > <span data-ttu-id="e9716-131">В некоторых случаях в <xref:System.Windows.Forms.BindingNavigator> компонент уже есть кнопка **сохранить** , но в конструктор Windows Forms не был создан код.</span><span class="sxs-lookup"><span data-stu-id="e9716-131">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component already has a **Save** button, but no code has been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="e9716-132">В этом случае можно поместить приведенный выше код в обработчик событий <xref:System.Windows.Forms.ToolStripItem.Click> для этой кнопки, а не создавать совершенно новую кнопку на <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="e9716-132">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="e9716-133">Однако кнопка по умолчанию отключена, поэтому необходимо задать для свойства <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> кнопки значение `true`, чтобы функция кнопки была правильной.</span><span class="sxs-lookup"><span data-stu-id="e9716-133">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>

12. <span data-ttu-id="e9716-134">Создайте обработчик событий <xref:System.Windows.Forms.ToolStripItem.Click> события **Cancel** <xref:System.Windows.Forms.ToolStripButton>, созданного ранее, и напишите код, чтобы отменить все изменения в отображаемой записи данных.</span><span class="sxs-lookup"><span data-stu-id="e9716-134">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Cancel** <xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>

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
    > <span data-ttu-id="e9716-135">Метод <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> ограничивается строкой данных.</span><span class="sxs-lookup"><span data-stu-id="e9716-135">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="e9716-136">Сохраните все изменения, внесенные при просмотре отдельной записи, прежде чем переходить к следующей записи.</span><span class="sxs-lookup"><span data-stu-id="e9716-136">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9716-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e9716-137">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="e9716-138">Элемент управления BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="e9716-138">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="e9716-139">Общие сведения о компоненте BindingSource</span><span class="sxs-lookup"><span data-stu-id="e9716-139">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)
