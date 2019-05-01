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
ms.openlocfilehash: a58522cc17ac379897a89a8e61485a1e271438a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011493"
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="a5c8f-102">Практическое руководство. Создание таблицы подстановки для элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5c8f-102">How to: Create a Lookup Table for a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="a5c8f-103">Иногда полезно отображать данные в удобном для пользователя формате в форме Windows Forms и при этом сохранять их в формате, требуемом в используемой программе.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-103">Sometimes it is useful to display data in a user-friendly format on a Windows Form, but store the data in a format that is more meaningful to your program.</span></span> <span data-ttu-id="a5c8f-104">Например, в бланке заказа продуктов питания могут отображаться элементы меню с названиями продуктов в списке.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-104">For example, an order form for food might display the menu items by name in a list box.</span></span> <span data-ttu-id="a5c8f-105">Однако таблица данных регистрации заказа будет содержать уникальные идентификаторы, представляющие продукты питания.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-105">However, the data table recording the order would contain the unique ID numbers representing the food.</span></span> <span data-ttu-id="a5c8f-106">В таблице ниже представлен пример хранения и отображения данных бланка заказа продуктов питания.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-106">The following tables show an example of how to store and display order-form data for food.</span></span>  
  
### <a name="orderdetailstable"></a><span data-ttu-id="a5c8f-107">OrderDetailsTable</span><span class="sxs-lookup"><span data-stu-id="a5c8f-107">OrderDetailsTable</span></span>  
  
|<span data-ttu-id="a5c8f-108">OrderID</span><span class="sxs-lookup"><span data-stu-id="a5c8f-108">OrderID</span></span>|<span data-ttu-id="a5c8f-109">Код элемента</span><span class="sxs-lookup"><span data-stu-id="a5c8f-109">ItemID</span></span>|<span data-ttu-id="a5c8f-110">Количество</span><span class="sxs-lookup"><span data-stu-id="a5c8f-110">Quantity</span></span>|  
|-------------|------------|--------------|  
|<span data-ttu-id="a5c8f-111">4085</span><span class="sxs-lookup"><span data-stu-id="a5c8f-111">4085</span></span>|<span data-ttu-id="a5c8f-112">12</span><span class="sxs-lookup"><span data-stu-id="a5c8f-112">12</span></span>|<span data-ttu-id="a5c8f-113">1</span><span class="sxs-lookup"><span data-stu-id="a5c8f-113">1</span></span>|  
|<span data-ttu-id="a5c8f-114">4086</span><span class="sxs-lookup"><span data-stu-id="a5c8f-114">4086</span></span>|<span data-ttu-id="a5c8f-115">13</span><span class="sxs-lookup"><span data-stu-id="a5c8f-115">13</span></span>|<span data-ttu-id="a5c8f-116">3</span><span class="sxs-lookup"><span data-stu-id="a5c8f-116">3</span></span>|  
  
### <a name="itemtable"></a><span data-ttu-id="a5c8f-117">ItemTable</span><span class="sxs-lookup"><span data-stu-id="a5c8f-117">ItemTable</span></span>  
  
|<span data-ttu-id="a5c8f-118">ID</span><span class="sxs-lookup"><span data-stu-id="a5c8f-118">ID</span></span>|<span data-ttu-id="a5c8f-119">name</span><span class="sxs-lookup"><span data-stu-id="a5c8f-119">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="a5c8f-120">12</span><span class="sxs-lookup"><span data-stu-id="a5c8f-120">12</span></span>|<span data-ttu-id="a5c8f-121">Картофель</span><span class="sxs-lookup"><span data-stu-id="a5c8f-121">Potato</span></span>|  
|<span data-ttu-id="a5c8f-122">13</span><span class="sxs-lookup"><span data-stu-id="a5c8f-122">13</span></span>|<span data-ttu-id="a5c8f-123">Цыпленок</span><span class="sxs-lookup"><span data-stu-id="a5c8f-123">Chicken</span></span>|  
  
 <span data-ttu-id="a5c8f-124">В этом случае одна таблица **OrderDetailsTable**, содержит фактические сведения, важные с отображения и сохранения.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-124">In this scenario, one table, **OrderDetailsTable**, stores the actual information you are concerned with displaying and saving.</span></span> <span data-ttu-id="a5c8f-125">Однако с целью экономии места они представлены в неудобном для восприятия виде.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-125">But to save space, it does so in a fairly cryptic fashion.</span></span> <span data-ttu-id="a5c8f-126">Другая таблица, **ItemTable**, содержит только связанные сведения о том, какой идентификатор номер эквивалент для определения имени качества пищевых продуктов и ничего о заказах на фактический качества пищевых продуктов.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-126">The other table, **ItemTable**, contains only appearance-related information about which ID number is equivalent to which food name, and nothing about the actual food orders.</span></span>  
  
 <span data-ttu-id="a5c8f-127">**ItemTable** подключен к <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, или <xref:System.Windows.Forms.CheckedListBox> управления с помощью трех свойств.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-127">The **ItemTable** is connected to the <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control through three properties.</span></span> <span data-ttu-id="a5c8f-128">`DataSource` Свойство содержит имя этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-128">The `DataSource` property contains the name of this table.</span></span> <span data-ttu-id="a5c8f-129">`DisplayMember` Свойство содержит столбец данных таблицы, который будет отображаться в элементе управления (название продукта).</span><span class="sxs-lookup"><span data-stu-id="a5c8f-129">The `DisplayMember` property contains the data column of that table that you want to display in the control (the food name).</span></span> <span data-ttu-id="a5c8f-130">`ValueMember` Свойство содержит столбец данных таблицы, в которой хранится информация (номер идентификатора).</span><span class="sxs-lookup"><span data-stu-id="a5c8f-130">The `ValueMember` property contains the data column of that table with the stored information (the ID number).</span></span>  
  
 <span data-ttu-id="a5c8f-131">**OrderDetailsTable** подключен к элементу управления с помощью коллекции привязок, через <xref:System.Windows.Forms.Control.DataBindings%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-131">The **OrderDetailsTable** is connected to the control by its bindings collection, accessed through the <xref:System.Windows.Forms.Control.DataBindings%2A> property.</span></span> <span data-ttu-id="a5c8f-132">При добавлении объекта привязки в коллекцию свойство элемента управления соединиться элемент данных (столбец идентификаторов) в источнике данных ( **OrderDetailsTable**).</span><span class="sxs-lookup"><span data-stu-id="a5c8f-132">When you add a binding object to the collection, you connect a control property to a specific data member (the column of ID numbers) in a data source (the **OrderDetailsTable**).</span></span> <span data-ttu-id="a5c8f-133">Когда в элементе управления делается выбор, в этой таблице сохраняются вводимые данные.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-133">When a selection is made in the control, this table is where the form input is saved.</span></span>  
  
### <a name="to-create-a-lookup-table"></a><span data-ttu-id="a5c8f-134">Создание таблицы подстановок</span><span class="sxs-lookup"><span data-stu-id="a5c8f-134">To create a lookup table</span></span>  
  
1. <span data-ttu-id="a5c8f-135">Добавьте на форму элемент управления <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> или <xref:System.Windows.Forms.CheckedListBox>.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-135">Add a <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control to the form.</span></span>  
  
2. <span data-ttu-id="a5c8f-136">Произведите подключение к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-136">Connect to your data source.</span></span>  
  
3. <span data-ttu-id="a5c8f-137">Установите связь между данными в двух таблицах.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-137">Establish a data relation between the two tables.</span></span> <span data-ttu-id="a5c8f-138">См. в разделе [Знакомство с объектами DataRelation](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="a5c8f-138">See [Introduction to DataRelation Objects](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120)).</span></span>  
  
4. <span data-ttu-id="a5c8f-139">Задайте перечисленные ниже свойства.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-139">Set the following properties.</span></span> <span data-ttu-id="a5c8f-140">Их можно задать в коде или в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-140">They can be set in code or in the designer.</span></span>  
  
    |<span data-ttu-id="a5c8f-141">Свойство</span><span class="sxs-lookup"><span data-stu-id="a5c8f-141">Property</span></span>|<span data-ttu-id="a5c8f-142">Параметр</span><span class="sxs-lookup"><span data-stu-id="a5c8f-142">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|<span data-ttu-id="a5c8f-143">Таблица, в которой содержатся сведения о том, какому коду соответствует тот или иной элемент.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-143">The table that contains information about which ID number is equivalent to which item.</span></span> <span data-ttu-id="a5c8f-144">В приведенном выше сценарии это `ItemTable`.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-144">In the previous scenario, this is `ItemTable`.</span></span>|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|<span data-ttu-id="a5c8f-145">Столбец таблицы источника данных, который необходимо отобразить в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-145">The column of the data source table that you want to display in the control.</span></span> <span data-ttu-id="a5c8f-146">В приведенном выше сценарии это `"Name"` (Чтобы задать в коде, используйте кавычки).</span><span class="sxs-lookup"><span data-stu-id="a5c8f-146">In the previous scenario, this is `"Name"` (to set in code, use quotation marks).</span></span>|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|<span data-ttu-id="a5c8f-147">Столбец таблицы источника данных, который содержит сохраняемую информацию.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-147">The column of the data source table that contains the stored information.</span></span> <span data-ttu-id="a5c8f-148">В приведенном выше сценарии это `"ID"` (Чтобы задать в коде, используйте кавычки).</span><span class="sxs-lookup"><span data-stu-id="a5c8f-148">In the previous scenario, this is `"ID"` (to set in code, use quotation marks).</span></span>|  
  
5. <span data-ttu-id="a5c8f-149">В процедуре вызовите метод <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> класса <xref:System.Windows.Forms.ControlBindingsCollection> для привязки свойства <xref:System.Windows.Forms.ListControl.SelectedValue%2A> элемента управления к таблице, в которой регистрируются данные, вводимые в форме.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-149">In a procedure, call the <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> method of the <xref:System.Windows.Forms.ControlBindingsCollection> class to bind the control's <xref:System.Windows.Forms.ListControl.SelectedValue%2A> property to the table recording the form input.</span></span> <span data-ttu-id="a5c8f-150">Также это можно сделать в конструкторе, а не в коде, обратившись к элемента управления <xref:System.Windows.Forms.Control.DataBindings%2A> свойство в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-150">You can also do this in the Designer instead of in code, by accessing the control's <xref:System.Windows.Forms.Control.DataBindings%2A> property in the **Properties** window.</span></span> <span data-ttu-id="a5c8f-151">В приведенном выше сценарии это `OrderDetailsTable`, а столбец `"ItemID"`.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-151">In the previous scenario, this is `OrderDetailsTable`, and the column is `"ItemID"`.</span></span>  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a5c8f-152">См. также</span><span class="sxs-lookup"><span data-stu-id="a5c8f-152">See also</span></span>

- [<span data-ttu-id="a5c8f-153">Привязка данных и Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5c8f-153">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="a5c8f-154">Общие сведения об элементе управления ListBox</span><span class="sxs-lookup"><span data-stu-id="a5c8f-154">ListBox Control Overview</span></span>](listbox-control-overview-windows-forms.md)
- [<span data-ttu-id="a5c8f-155">Общие сведения об элементе управления ComboBox</span><span class="sxs-lookup"><span data-stu-id="a5c8f-155">ComboBox Control Overview</span></span>](combobox-control-overview-windows-forms.md)
- [<span data-ttu-id="a5c8f-156">Общие сведения об элементе управления CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="a5c8f-156">CheckedListBox Control Overview</span></span>](checkedlistbox-control-overview-windows-forms.md)
- [<span data-ttu-id="a5c8f-157">Создание списка для выбора элементов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5c8f-157">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
