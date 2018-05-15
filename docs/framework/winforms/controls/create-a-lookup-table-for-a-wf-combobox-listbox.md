---
title: Практическое руководство. Создание таблицы подстановки для элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CheckedListBox control [Windows Forms], creating lookup tables
- lookup tables
- list boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], lookup tables
- ComboBox control [Windows Forms], lookup table
- lookup tables [Windows Forms], creating for controls
- combo boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], creating lookup tables
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
ms.openlocfilehash: 212cc229d8a496be11c84e30dbf3a0eedb952006
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="df6c1-102">Практическое руководство. Создание таблицы подстановки для элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="df6c1-102">How to: Create a Lookup Table for a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="df6c1-103">Иногда полезно отображать данные в удобном для пользователя формате в форме Windows Forms и при этом сохранять их в формате, требуемом в используемой программе.</span><span class="sxs-lookup"><span data-stu-id="df6c1-103">Sometimes it is useful to display data in a user-friendly format on a Windows Form, but store the data in a format that is more meaningful to your program.</span></span> <span data-ttu-id="df6c1-104">Например, в бланке заказа продуктов питания могут отображаться элементы меню с названиями продуктов в списке.</span><span class="sxs-lookup"><span data-stu-id="df6c1-104">For example, an order form for food might display the menu items by name in a list box.</span></span> <span data-ttu-id="df6c1-105">Однако таблица данных регистрации заказа будет содержать уникальные идентификаторы, представляющие продукты питания.</span><span class="sxs-lookup"><span data-stu-id="df6c1-105">However, the data table recording the order would contain the unique ID numbers representing the food.</span></span> <span data-ttu-id="df6c1-106">В таблице ниже представлен пример хранения и отображения данных бланка заказа продуктов питания.</span><span class="sxs-lookup"><span data-stu-id="df6c1-106">The following tables show an example of how to store and display order-form data for food.</span></span>  
  
### <a name="orderdetailstable"></a><span data-ttu-id="df6c1-107">OrderDetailsTable</span><span class="sxs-lookup"><span data-stu-id="df6c1-107">OrderDetailsTable</span></span>  
  
|<span data-ttu-id="df6c1-108">OrderID</span><span class="sxs-lookup"><span data-stu-id="df6c1-108">OrderID</span></span>|<span data-ttu-id="df6c1-109">Код элемента</span><span class="sxs-lookup"><span data-stu-id="df6c1-109">ItemID</span></span>|<span data-ttu-id="df6c1-110">Количество</span><span class="sxs-lookup"><span data-stu-id="df6c1-110">Quantity</span></span>|  
|-------------|------------|--------------|  
|<span data-ttu-id="df6c1-111">4085</span><span class="sxs-lookup"><span data-stu-id="df6c1-111">4085</span></span>|<span data-ttu-id="df6c1-112">12</span><span class="sxs-lookup"><span data-stu-id="df6c1-112">12</span></span>|<span data-ttu-id="df6c1-113">1</span><span class="sxs-lookup"><span data-stu-id="df6c1-113">1</span></span>|  
|<span data-ttu-id="df6c1-114">4086</span><span class="sxs-lookup"><span data-stu-id="df6c1-114">4086</span></span>|<span data-ttu-id="df6c1-115">13</span><span class="sxs-lookup"><span data-stu-id="df6c1-115">13</span></span>|<span data-ttu-id="df6c1-116">3</span><span class="sxs-lookup"><span data-stu-id="df6c1-116">3</span></span>|  
  
### <a name="itemtable"></a><span data-ttu-id="df6c1-117">ItemTable</span><span class="sxs-lookup"><span data-stu-id="df6c1-117">ItemTable</span></span>  
  
|<span data-ttu-id="df6c1-118">ID</span><span class="sxs-lookup"><span data-stu-id="df6c1-118">ID</span></span>|<span data-ttu-id="df6c1-119">name</span><span class="sxs-lookup"><span data-stu-id="df6c1-119">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="df6c1-120">12</span><span class="sxs-lookup"><span data-stu-id="df6c1-120">12</span></span>|<span data-ttu-id="df6c1-121">Картофель</span><span class="sxs-lookup"><span data-stu-id="df6c1-121">Potato</span></span>|  
|<span data-ttu-id="df6c1-122">13</span><span class="sxs-lookup"><span data-stu-id="df6c1-122">13</span></span>|<span data-ttu-id="df6c1-123">Цыпленок</span><span class="sxs-lookup"><span data-stu-id="df6c1-123">Chicken</span></span>|  
  
 <span data-ttu-id="df6c1-124">В этом сценарии одна таблица **OrderDetailsTable**, содержит фактические сведения, которые вас интересуют отображения и сохранения.</span><span class="sxs-lookup"><span data-stu-id="df6c1-124">In this scenario, one table, **OrderDetailsTable**, stores the actual information you are concerned with displaying and saving.</span></span> <span data-ttu-id="df6c1-125">Однако с целью экономии места они представлены в неудобном для восприятия виде.</span><span class="sxs-lookup"><span data-stu-id="df6c1-125">But to save space, it does so in a fairly cryptic fashion.</span></span> <span data-ttu-id="df6c1-126">Другая таблица, **ItemTable**, содержит только связанные информацию о какой идентификатор номер эквивалентные какие название продукта и ничего о заказах на фактическое пищевых продуктов.</span><span class="sxs-lookup"><span data-stu-id="df6c1-126">The other table, **ItemTable**, contains only appearance-related information about which ID number is equivalent to which food name, and nothing about the actual food orders.</span></span>  
  
 <span data-ttu-id="df6c1-127">**ItemTable** подключен к <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, или <xref:System.Windows.Forms.CheckedListBox> управление с помощью трех свойств.</span><span class="sxs-lookup"><span data-stu-id="df6c1-127">The **ItemTable** is connected to the <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control through three properties.</span></span> <span data-ttu-id="df6c1-128">`DataSource` Свойство содержит имя этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="df6c1-128">The `DataSource` property contains the name of this table.</span></span> <span data-ttu-id="df6c1-129">`DisplayMember` Свойство содержит столбец данных таблицы, который будет отображаться в элементе управления (название продукта).</span><span class="sxs-lookup"><span data-stu-id="df6c1-129">The `DisplayMember` property contains the data column of that table that you want to display in the control (the food name).</span></span> <span data-ttu-id="df6c1-130">`ValueMember` Свойство содержит столбец данных таблицы с сохраняемыми данными (идентификатор).</span><span class="sxs-lookup"><span data-stu-id="df6c1-130">The `ValueMember` property contains the data column of that table with the stored information (the ID number).</span></span>  
  
 <span data-ttu-id="df6c1-131">**OrderDetailsTable** подключен к элементу управления с помощью коллекции привязок, доступных через <xref:System.Windows.Forms.Control.DataBindings%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="df6c1-131">The **OrderDetailsTable** is connected to the control by its bindings collection, accessed through the <xref:System.Windows.Forms.Control.DataBindings%2A> property.</span></span> <span data-ttu-id="df6c1-132">При добавлении объекта привязки в коллекцию свойство элемента управления подключиться к члену данных (столбцом кодов) в источнике данных ( **OrderDetailsTable**).</span><span class="sxs-lookup"><span data-stu-id="df6c1-132">When you add a binding object to the collection, you connect a control property to a specific data member (the column of ID numbers) in a data source (the **OrderDetailsTable**).</span></span> <span data-ttu-id="df6c1-133">Когда в элементе управления делается выбор, в этой таблице сохраняются вводимые данные.</span><span class="sxs-lookup"><span data-stu-id="df6c1-133">When a selection is made in the control, this table is where the form input is saved.</span></span>  
  
### <a name="to-create-a-lookup-table"></a><span data-ttu-id="df6c1-134">Создание таблицы подстановок</span><span class="sxs-lookup"><span data-stu-id="df6c1-134">To create a lookup table</span></span>  
  
1.  <span data-ttu-id="df6c1-135">Добавьте на форму элемент управления <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> или <xref:System.Windows.Forms.CheckedListBox>.</span><span class="sxs-lookup"><span data-stu-id="df6c1-135">Add a <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control to the form.</span></span>  
  
2.  <span data-ttu-id="df6c1-136">Произведите подключение к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="df6c1-136">Connect to your data source.</span></span>  
  
3.  <span data-ttu-id="df6c1-137">Установите связь между данными в двух таблицах.</span><span class="sxs-lookup"><span data-stu-id="df6c1-137">Establish a data relation between the two tables.</span></span> <span data-ttu-id="df6c1-138">В разделе [Знакомство с объектами DataRelation](http://msdn.microsoft.com/library/89d8a881-8265-41f2-a88b-61311ab06192).</span><span class="sxs-lookup"><span data-stu-id="df6c1-138">See [Introduction to DataRelation Objects](http://msdn.microsoft.com/library/89d8a881-8265-41f2-a88b-61311ab06192).</span></span>  
  
4.  <span data-ttu-id="df6c1-139">Задайте перечисленные ниже свойства.</span><span class="sxs-lookup"><span data-stu-id="df6c1-139">Set the following properties.</span></span> <span data-ttu-id="df6c1-140">Их можно задать в коде или в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="df6c1-140">They can be set in code or in the designer.</span></span>  
  
    |<span data-ttu-id="df6c1-141">Свойство.</span><span class="sxs-lookup"><span data-stu-id="df6c1-141">Property</span></span>|<span data-ttu-id="df6c1-142">Параметр</span><span class="sxs-lookup"><span data-stu-id="df6c1-142">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|<span data-ttu-id="df6c1-143">Таблица, в которой содержатся сведения о том, какому коду соответствует тот или иной элемент.</span><span class="sxs-lookup"><span data-stu-id="df6c1-143">The table that contains information about which ID number is equivalent to which item.</span></span> <span data-ttu-id="df6c1-144">В приведенном выше сценарии это `ItemTable`.</span><span class="sxs-lookup"><span data-stu-id="df6c1-144">In the previous scenario, this is `ItemTable`.</span></span>|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|<span data-ttu-id="df6c1-145">Столбец таблицы источника данных, который необходимо отобразить в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="df6c1-145">The column of the data source table that you want to display in the control.</span></span> <span data-ttu-id="df6c1-146">В приведенном выше сценарии это `"Name"` (для задания в коде используйте кавычки).</span><span class="sxs-lookup"><span data-stu-id="df6c1-146">In the previous scenario, this is `"Name"` (to set in code, use quotation marks).</span></span>|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|<span data-ttu-id="df6c1-147">Столбец таблицы источника данных, который содержит сохраняемую информацию.</span><span class="sxs-lookup"><span data-stu-id="df6c1-147">The column of the data source table that contains the stored information.</span></span> <span data-ttu-id="df6c1-148">В приведенном выше сценарии это `"ID"` (для задания в коде используйте кавычки).</span><span class="sxs-lookup"><span data-stu-id="df6c1-148">In the previous scenario, this is `"ID"` (to set in code, use quotation marks).</span></span>|  
  
5.  <span data-ttu-id="df6c1-149">В процедуре вызовите метод <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> класса <xref:System.Windows.Forms.ControlBindingsCollection> для привязки свойства <xref:System.Windows.Forms.ListControl.SelectedValue%2A> элемента управления к таблице, в которой регистрируются данные, вводимые в форме.</span><span class="sxs-lookup"><span data-stu-id="df6c1-149">In a procedure, call the <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> method of the <xref:System.Windows.Forms.ControlBindingsCollection> class to bind the control's <xref:System.Windows.Forms.ListControl.SelectedValue%2A> property to the table recording the form input.</span></span> <span data-ttu-id="df6c1-150">Также это можно сделать в конструкторе, а не в коде, обратившись к элемента управления <xref:System.Windows.Forms.Control.DataBindings%2A> свойство в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="df6c1-150">You can also do this in the Designer instead of in code, by accessing the control's <xref:System.Windows.Forms.Control.DataBindings%2A> property in the **Properties** window.</span></span> <span data-ttu-id="df6c1-151">В приведенном выше сценарии это `OrderDetailsTable`, а столбец — `"ItemID"`.</span><span class="sxs-lookup"><span data-stu-id="df6c1-151">In the previous scenario, this is `OrderDetailsTable`, and the column is `"ItemID"`.</span></span>  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="df6c1-152">См. также</span><span class="sxs-lookup"><span data-stu-id="df6c1-152">See Also</span></span>  
 [<span data-ttu-id="df6c1-153">Привязка данных и Windows Forms</span><span class="sxs-lookup"><span data-stu-id="df6c1-153">Data Binding and Windows Forms</span></span>](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [<span data-ttu-id="df6c1-154">Общие сведения об элементе управления ListBox</span><span class="sxs-lookup"><span data-stu-id="df6c1-154">ListBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="df6c1-155">Общие сведения об элементе управления ComboBox</span><span class="sxs-lookup"><span data-stu-id="df6c1-155">ComboBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)  
 [<span data-ttu-id="df6c1-156">Общие сведения об элементе управления CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="df6c1-156">CheckedListBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="df6c1-157">Создание списка для выбора элементов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="df6c1-157">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
