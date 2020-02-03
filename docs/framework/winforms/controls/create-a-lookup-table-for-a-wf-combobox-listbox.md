---
title: Создание таблицы подстановок для элемента управления ComboBox, ListBox или CheckedListBox
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
ms.openlocfilehash: 4bbbc66a56c7ce269c2dabd593db88f96907d755
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737371"
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="75eb0-102">Практическое руководство. Создание таблицы подстановки для элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="75eb0-102">How to: Create a Lookup Table for a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="75eb0-103">Иногда полезно отображать данные в удобном для пользователя формате в форме Windows Forms и при этом сохранять их в формате, требуемом в используемой программе.</span><span class="sxs-lookup"><span data-stu-id="75eb0-103">Sometimes it is useful to display data in a user-friendly format on a Windows Form, but store the data in a format that is more meaningful to your program.</span></span> <span data-ttu-id="75eb0-104">Например, в бланке заказа продуктов питания могут отображаться элементы меню с названиями продуктов в списке.</span><span class="sxs-lookup"><span data-stu-id="75eb0-104">For example, an order form for food might display the menu items by name in a list box.</span></span> <span data-ttu-id="75eb0-105">Однако таблица данных регистрации заказа будет содержать уникальные идентификаторы, представляющие продукты питания.</span><span class="sxs-lookup"><span data-stu-id="75eb0-105">However, the data table recording the order would contain the unique ID numbers representing the food.</span></span> <span data-ttu-id="75eb0-106">В таблице ниже представлен пример хранения и отображения данных бланка заказа продуктов питания.</span><span class="sxs-lookup"><span data-stu-id="75eb0-106">The following tables show an example of how to store and display order-form data for food.</span></span>  
  
### <a name="orderdetailstable"></a><span data-ttu-id="75eb0-107">OrderDetailsTable</span><span class="sxs-lookup"><span data-stu-id="75eb0-107">OrderDetailsTable</span></span>  
  
|<span data-ttu-id="75eb0-108">OrderID</span><span class="sxs-lookup"><span data-stu-id="75eb0-108">OrderID</span></span>|<span data-ttu-id="75eb0-109">Код элемента</span><span class="sxs-lookup"><span data-stu-id="75eb0-109">ItemID</span></span>|<span data-ttu-id="75eb0-110">Количество</span><span class="sxs-lookup"><span data-stu-id="75eb0-110">Quantity</span></span>|  
|-------------|------------|--------------|  
|<span data-ttu-id="75eb0-111">4085</span><span class="sxs-lookup"><span data-stu-id="75eb0-111">4085</span></span>|<span data-ttu-id="75eb0-112">12</span><span class="sxs-lookup"><span data-stu-id="75eb0-112">12</span></span>|<span data-ttu-id="75eb0-113">1</span><span class="sxs-lookup"><span data-stu-id="75eb0-113">1</span></span>|  
|<span data-ttu-id="75eb0-114">4086</span><span class="sxs-lookup"><span data-stu-id="75eb0-114">4086</span></span>|<span data-ttu-id="75eb0-115">13</span><span class="sxs-lookup"><span data-stu-id="75eb0-115">13</span></span>|<span data-ttu-id="75eb0-116">3</span><span class="sxs-lookup"><span data-stu-id="75eb0-116">3</span></span>|  
  
### <a name="itemtable"></a><span data-ttu-id="75eb0-117">ItemTable</span><span class="sxs-lookup"><span data-stu-id="75eb0-117">ItemTable</span></span>  
  
|<span data-ttu-id="75eb0-118">ID</span><span class="sxs-lookup"><span data-stu-id="75eb0-118">ID</span></span>|<span data-ttu-id="75eb0-119">Имя</span><span class="sxs-lookup"><span data-stu-id="75eb0-119">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="75eb0-120">12</span><span class="sxs-lookup"><span data-stu-id="75eb0-120">12</span></span>|<span data-ttu-id="75eb0-121">Картофель</span><span class="sxs-lookup"><span data-stu-id="75eb0-121">Potato</span></span>|  
|<span data-ttu-id="75eb0-122">13</span><span class="sxs-lookup"><span data-stu-id="75eb0-122">13</span></span>|<span data-ttu-id="75eb0-123">Цыпленок</span><span class="sxs-lookup"><span data-stu-id="75eb0-123">Chicken</span></span>|  
  
 <span data-ttu-id="75eb0-124">В этом сценарии одна таблица, **ордердетаилстабле**, хранит фактические сведения, которые будут связаны с отображением и сохранением.</span><span class="sxs-lookup"><span data-stu-id="75eb0-124">In this scenario, one table, **OrderDetailsTable**, stores the actual information you are concerned with displaying and saving.</span></span> <span data-ttu-id="75eb0-125">Однако с целью экономии места они представлены в неудобном для восприятия виде.</span><span class="sxs-lookup"><span data-stu-id="75eb0-125">But to save space, it does so in a fairly cryptic fashion.</span></span> <span data-ttu-id="75eb0-126">Другая таблица, **итемтабле**, содержит только сведения о том, какой идентификационный номер эквивалентен имени нектара, и ничего о фактическом заказе на возврат.</span><span class="sxs-lookup"><span data-stu-id="75eb0-126">The other table, **ItemTable**, contains only appearance-related information about which ID number is equivalent to which food name, and nothing about the actual food orders.</span></span>  
  
 <span data-ttu-id="75eb0-127">**Итемтабле** подключается к <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>или <xref:System.Windows.Forms.CheckedListBox> управления через три свойства.</span><span class="sxs-lookup"><span data-stu-id="75eb0-127">The **ItemTable** is connected to the <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control through three properties.</span></span> <span data-ttu-id="75eb0-128">Свойство `DataSource` содержит имя этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="75eb0-128">The `DataSource` property contains the name of this table.</span></span> <span data-ttu-id="75eb0-129">Свойство `DisplayMember` содержит столбец данных этой таблицы, который необходимо отобразить в элементе управления (имя пищи).</span><span class="sxs-lookup"><span data-stu-id="75eb0-129">The `DisplayMember` property contains the data column of that table that you want to display in the control (the food name).</span></span> <span data-ttu-id="75eb0-130">Свойство `ValueMember` содержит столбец данных этой таблицы с сохраненными данными (ИДЕНТИФИКАТОРом).</span><span class="sxs-lookup"><span data-stu-id="75eb0-130">The `ValueMember` property contains the data column of that table with the stored information (the ID number).</span></span>  
  
 <span data-ttu-id="75eb0-131">**Ордердетаилстабле** подключается к элементу управления по коллекции привязок, доступ к которому осуществляется через свойство <xref:System.Windows.Forms.Control.DataBindings%2A>.</span><span class="sxs-lookup"><span data-stu-id="75eb0-131">The **OrderDetailsTable** is connected to the control by its bindings collection, accessed through the <xref:System.Windows.Forms.Control.DataBindings%2A> property.</span></span> <span data-ttu-id="75eb0-132">При добавлении объекта привязки в коллекцию свойство элемента управления подключается к определенному элементу данных (столбцу с ИДЕНТИФИКАЦИОНными номерами) в источнике данных ( **ордердетаилстабле**).</span><span class="sxs-lookup"><span data-stu-id="75eb0-132">When you add a binding object to the collection, you connect a control property to a specific data member (the column of ID numbers) in a data source (the **OrderDetailsTable**).</span></span> <span data-ttu-id="75eb0-133">Когда в элементе управления делается выбор, в этой таблице сохраняются вводимые данные.</span><span class="sxs-lookup"><span data-stu-id="75eb0-133">When a selection is made in the control, this table is where the form input is saved.</span></span>  
  
### <a name="to-create-a-lookup-table"></a><span data-ttu-id="75eb0-134">Создание таблицы подстановок</span><span class="sxs-lookup"><span data-stu-id="75eb0-134">To create a lookup table</span></span>  
  
1. <span data-ttu-id="75eb0-135">Добавьте на форму элемент управления <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> или <xref:System.Windows.Forms.CheckedListBox>.</span><span class="sxs-lookup"><span data-stu-id="75eb0-135">Add a <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control to the form.</span></span>  
  
2. <span data-ttu-id="75eb0-136">Произведите подключение к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="75eb0-136">Connect to your data source.</span></span>  
  
3. <span data-ttu-id="75eb0-137">Установите связь между данными в двух таблицах.</span><span class="sxs-lookup"><span data-stu-id="75eb0-137">Establish a data relation between the two tables.</span></span> <span data-ttu-id="75eb0-138">См. статью [Общие сведения об объектах DataRelation](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="75eb0-138">See [Introduction to DataRelation Objects](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120)).</span></span>  
  
4. <span data-ttu-id="75eb0-139">Задайте перечисленные ниже свойства.</span><span class="sxs-lookup"><span data-stu-id="75eb0-139">Set the following properties.</span></span> <span data-ttu-id="75eb0-140">Их можно задать в коде или в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="75eb0-140">They can be set in code or in the designer.</span></span>  
  
    |<span data-ttu-id="75eb0-141">Свойство</span><span class="sxs-lookup"><span data-stu-id="75eb0-141">Property</span></span>|<span data-ttu-id="75eb0-142">Параметр</span><span class="sxs-lookup"><span data-stu-id="75eb0-142">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|<span data-ttu-id="75eb0-143">Таблица, в которой содержатся сведения о том, какому коду соответствует тот или иной элемент.</span><span class="sxs-lookup"><span data-stu-id="75eb0-143">The table that contains information about which ID number is equivalent to which item.</span></span> <span data-ttu-id="75eb0-144">В предыдущем сценарии это `ItemTable`.</span><span class="sxs-lookup"><span data-stu-id="75eb0-144">In the previous scenario, this is `ItemTable`.</span></span>|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|<span data-ttu-id="75eb0-145">Столбец таблицы источника данных, который необходимо отобразить в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="75eb0-145">The column of the data source table that you want to display in the control.</span></span> <span data-ttu-id="75eb0-146">В предыдущем сценарии это `"Name"` (для задания в коде используйте кавычки).</span><span class="sxs-lookup"><span data-stu-id="75eb0-146">In the previous scenario, this is `"Name"` (to set in code, use quotation marks).</span></span>|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|<span data-ttu-id="75eb0-147">Столбец таблицы источника данных, который содержит сохраняемую информацию.</span><span class="sxs-lookup"><span data-stu-id="75eb0-147">The column of the data source table that contains the stored information.</span></span> <span data-ttu-id="75eb0-148">В предыдущем сценарии это `"ID"` (для задания в коде используйте кавычки).</span><span class="sxs-lookup"><span data-stu-id="75eb0-148">In the previous scenario, this is `"ID"` (to set in code, use quotation marks).</span></span>|  
  
5. <span data-ttu-id="75eb0-149">В процедуре вызовите метод <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> класса <xref:System.Windows.Forms.ControlBindingsCollection> для привязки свойства <xref:System.Windows.Forms.ListControl.SelectedValue%2A> элемента управления к таблице, в которой регистрируются данные, вводимые в форме.</span><span class="sxs-lookup"><span data-stu-id="75eb0-149">In a procedure, call the <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> method of the <xref:System.Windows.Forms.ControlBindingsCollection> class to bind the control's <xref:System.Windows.Forms.ListControl.SelectedValue%2A> property to the table recording the form input.</span></span> <span data-ttu-id="75eb0-150">Это также можно сделать в конструкторе, а не в коде, обратившись к свойству <xref:System.Windows.Forms.Control.DataBindings%2A> элемента управления в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="75eb0-150">You can also do this in the Designer instead of in code, by accessing the control's <xref:System.Windows.Forms.Control.DataBindings%2A> property in the **Properties** window.</span></span> <span data-ttu-id="75eb0-151">В предыдущем сценарии это `OrderDetailsTable`, а столбец — `"ItemID"`.</span><span class="sxs-lookup"><span data-stu-id="75eb0-151">In the previous scenario, this is `OrderDetailsTable`, and the column is `"ItemID"`.</span></span>  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="75eb0-152">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="75eb0-152">See also</span></span>

- [<span data-ttu-id="75eb0-153">Привязка данных и Windows Forms</span><span class="sxs-lookup"><span data-stu-id="75eb0-153">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="75eb0-154">Общие сведения об элементе управления ListBox</span><span class="sxs-lookup"><span data-stu-id="75eb0-154">ListBox Control Overview</span></span>](listbox-control-overview-windows-forms.md)
- [<span data-ttu-id="75eb0-155">Общие сведения об элементе управления ComboBox</span><span class="sxs-lookup"><span data-stu-id="75eb0-155">ComboBox Control Overview</span></span>](combobox-control-overview-windows-forms.md)
- [<span data-ttu-id="75eb0-156">Общие сведения об элементе управления CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="75eb0-156">CheckedListBox Control Overview</span></span>](checkedlistbox-control-overview-windows-forms.md)
- [<span data-ttu-id="75eb0-157">Создание списка для выбора элементов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="75eb0-157">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
