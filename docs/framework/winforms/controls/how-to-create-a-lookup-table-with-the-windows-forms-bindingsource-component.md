---
title: Создание таблицы подстановок с помощью компонента BindingSource
ms.date: 03/30/2017
helpviewer_keywords:
- lookup tables
- tables [Windows Forms], creating lookup tables
- BindingSource component [Windows Forms], creating a lookup table
- BindingSource component [Windows Forms], examples
ms.assetid: 622fce80-879d-44be-abbf-8350ec22ca2b
ms.openlocfilehash: ccf2bfa6cf3f56a38b55f8c87004c42a46172891
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736811"
---
# <a name="how-to-create-a-lookup-table-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="cb5c6-102">Практическое руководство. Создание таблицы подстановок с помощью компонента BindingSource в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb5c6-102">How to: Create a Lookup Table with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="cb5c6-103">Таблица подстановки — это таблица данных, в одном из столбцов которой отображаются данные из записей в связанной таблице.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-103">A lookup table is a table of data that has a column that displays data from records in a related table.</span></span> <span data-ttu-id="cb5c6-104">В следующих процедурах для отображения поля с отношением по внешнему ключу от родительской к дочерней таблице используется элемент управления <xref:System.Windows.Forms.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-104">In the following procedures, a <xref:System.Windows.Forms.ComboBox> control is used to display the field with the foreign-key relationship from the parent to the child table.</span></span>  
  
 <span data-ttu-id="cb5c6-105">Чтобы вы могли представить это отношение, приведем пример родительской и дочерней таблицы.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-105">To help visualize these two tables and this relationship, here is an example of a parent and child table:</span></span>  
  
 <span data-ttu-id="cb5c6-106">CustomersTable (родительская таблица)</span><span class="sxs-lookup"><span data-stu-id="cb5c6-106">CustomersTable (parent table)</span></span>  
  
|<span data-ttu-id="cb5c6-107">CustomerID</span><span class="sxs-lookup"><span data-stu-id="cb5c6-107">CustomerID</span></span>|<span data-ttu-id="cb5c6-108">CustomerName</span><span class="sxs-lookup"><span data-stu-id="cb5c6-108">CustomerName</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="cb5c6-109">712</span><span class="sxs-lookup"><span data-stu-id="cb5c6-109">712</span></span>|<span data-ttu-id="cb5c6-110">Павел Кох</span><span class="sxs-lookup"><span data-stu-id="cb5c6-110">Paul Koch</span></span>|  
|<span data-ttu-id="cb5c6-111">713</span><span class="sxs-lookup"><span data-stu-id="cb5c6-111">713</span></span>|<span data-ttu-id="cb5c6-112">Тамара Иванова</span><span class="sxs-lookup"><span data-stu-id="cb5c6-112">Tamara Johnston</span></span>|  
  
 <span data-ttu-id="cb5c6-113">OrdersTable (дочерняя таблица)</span><span class="sxs-lookup"><span data-stu-id="cb5c6-113">OrdersTable (child table)</span></span>  
  
|<span data-ttu-id="cb5c6-114">OrderID</span><span class="sxs-lookup"><span data-stu-id="cb5c6-114">OrderID</span></span>|<span data-ttu-id="cb5c6-115">OrderDate</span><span class="sxs-lookup"><span data-stu-id="cb5c6-115">OrderDate</span></span>|<span data-ttu-id="cb5c6-116">CustomerID</span><span class="sxs-lookup"><span data-stu-id="cb5c6-116">CustomerID</span></span>|  
|-------------|---------------|----------------|  
|<span data-ttu-id="cb5c6-117">903</span><span class="sxs-lookup"><span data-stu-id="cb5c6-117">903</span></span>|<span data-ttu-id="cb5c6-118">12 февраля 2004 г.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-118">February 12, 2004</span></span>|<span data-ttu-id="cb5c6-119">712</span><span class="sxs-lookup"><span data-stu-id="cb5c6-119">712</span></span>|  
|<span data-ttu-id="cb5c6-120">904</span><span class="sxs-lookup"><span data-stu-id="cb5c6-120">904</span></span>|<span data-ttu-id="cb5c6-121">13 февраля 2004 г.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-121">February 13, 2004</span></span>|<span data-ttu-id="cb5c6-122">713</span><span class="sxs-lookup"><span data-stu-id="cb5c6-122">713</span></span>|  
  
 <span data-ttu-id="cb5c6-123">В данном случае одна таблица, CustomersTable, содержит актуальную информацию, которую необходимо отобразить и сохранить.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-123">In this scenario, one table, CustomersTable, stores the actual information you want to display and save.</span></span> <span data-ttu-id="cb5c6-124">Для экономии места в таблице опущены пояснения.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-124">But to save space, the table leaves out data that adds clarity.</span></span> <span data-ttu-id="cb5c6-125">Другая таблица, OrdersTable, содержит только внешнюю информацию о том, какой номер идентификатора клиента соответствует тем или иным данным и идентификатору заказа.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-125">The other table, OrdersTable, contains only appearance-related information about which customer ID number is equivalent to which order date and order ID.</span></span> <span data-ttu-id="cb5c6-126">При этом имена клиентов не указываются.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-126">There is no mention of the customers' names.</span></span>  
  
 <span data-ttu-id="cb5c6-127">Чтобы создать таблицу подстановки, в элементе управления [ComboBox](combobox-control-windows-forms.md) устанавливаются четыре важных свойства.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-127">Four important properties are set on the [ComboBox Control](combobox-control-windows-forms.md) control to create the lookup table.</span></span>  
  
- <span data-ttu-id="cb5c6-128">Свойство <xref:System.Windows.Forms.ComboBox.DataSource%2A> содержит имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-128">The <xref:System.Windows.Forms.ComboBox.DataSource%2A> property contains the name of the table.</span></span>  
  
- <span data-ttu-id="cb5c6-129">Свойство <xref:System.Windows.Forms.ListControl.DisplayMember%2A> содержит столбец данных таблицы, из которого нужно взять текст для элемента управления (имя клиента).</span><span class="sxs-lookup"><span data-stu-id="cb5c6-129">The <xref:System.Windows.Forms.ListControl.DisplayMember%2A> property contains the data column of that table that you want to display for the control text (the customer's name).</span></span>  
  
- <span data-ttu-id="cb5c6-130">Свойство <xref:System.Windows.Forms.ListControl.ValueMember%2A> содержит столбец данных таблицы, в которой хранится информация (номер идентификатора в родительской таблице).</span><span class="sxs-lookup"><span data-stu-id="cb5c6-130">The <xref:System.Windows.Forms.ListControl.ValueMember%2A> property contains the data column of that table with the stored information (the ID number in the parent table).</span></span>  
  
- <span data-ttu-id="cb5c6-131">Свойство <xref:System.Windows.Forms.ListControl.SelectedValue%2A> предоставляет значение подстановки для дочерней таблицы на основании свойства <xref:System.Windows.Forms.ListControl.ValueMember%2A>.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-131">The <xref:System.Windows.Forms.ListControl.SelectedValue%2A> property provides the lookup value for the child table, based on the <xref:System.Windows.Forms.ListControl.ValueMember%2A>.</span></span>  
  
 <span data-ttu-id="cb5c6-132">Представленные ниже процедуры показывают, как разместить форму в виде таблицы подстановки и привязать данные к ее элементам управления.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-132">The procedures below show you how to lay out your form as a lookup table and bind data to the controls on it.</span></span> <span data-ttu-id="cb5c6-133">Для успешного завершения процедур необходим источник данных с родительской и дочерней таблицами, связанными по внешнему ключу, как это уже говорилось выше.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-133">To successfully complete the procedures, you must have a data source with parent and child tables that have a foreign-key relationship, as mentioned previously.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="cb5c6-134">Создание пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="cb5c6-134">To create the user interface</span></span>  
  
1. <span data-ttu-id="cb5c6-135">Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.ComboBox> на форму.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-135">From the **ToolBox**, drag a <xref:System.Windows.Forms.ComboBox> control onto the form.</span></span>  
  
     <span data-ttu-id="cb5c6-136">Этот элемент управления будет отображать столбец из родительской таблицы.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-136">This control will display the column from parent table.</span></span>  
  
2. <span data-ttu-id="cb5c6-137">Перетащите другие элементы управления для отображения сведений из дочерней таблицы.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-137">Drag other controls to display details from the child table.</span></span> <span data-ttu-id="cb5c6-138">Формат данных в таблице следует определить, исходя из выбранных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-138">The format of the data in the table should determine which controls you choose.</span></span> <span data-ttu-id="cb5c6-139">Дополнительные сведения см. в разделе [Функциональная классификация элементов управления Windows Forms](windows-forms-controls-by-function.md).</span><span class="sxs-lookup"><span data-stu-id="cb5c6-139">For more information, see [Windows Forms Controls by Function](windows-forms-controls-by-function.md).</span></span>  
  
3. <span data-ttu-id="cb5c6-140">Перетащите в форму элемент управления <xref:System.Windows.Forms.BindingNavigator>. Это позволит перемещаться по данным в дочерней таблице.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-140">Drag a <xref:System.Windows.Forms.BindingNavigator> control onto the form; this will allow you to navigate the data in the child table.</span></span>  
  
### <a name="to-connect-to-the-data-and-bind-it-to-controls"></a><span data-ttu-id="cb5c6-141">Подключение к данным и их привязка к элементам управления</span><span class="sxs-lookup"><span data-stu-id="cb5c6-141">To connect to the data and bind it to controls</span></span>  
  
1. <span data-ttu-id="cb5c6-142">Выберите элемент управления <xref:System.Windows.Forms.ComboBox> и нажмите на глиф "Быстрые действия", чтобы открыть одноименное диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-142">Select the <xref:System.Windows.Forms.ComboBox> and click the Smart Task glyph to display the Smart Task dialog box.</span></span>  
  
2. <span data-ttu-id="cb5c6-143">Выберите элемент **Использовать элементы, привязанные к данным**.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-143">Select **Use data bound items**.</span></span>  
  
3. <span data-ttu-id="cb5c6-144">Щелкните стрелку рядом с раскрывающимся списком **Источник данных**.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-144">Click the arrow next to the **Data Source** drop-down box.</span></span> <span data-ttu-id="cb5c6-145">Если источник данных ранее был настроен для проекта или формы, он отобразится. В противном случае выполните следующие действия (в этом примере используются таблицы Customers и Orders учебной базы данных Борей, а ссылки на них приводятся в круглых скобках).</span><span class="sxs-lookup"><span data-stu-id="cb5c6-145">If a data source has previously been configured for the project or form, it will appear; otherwise, complete the following steps (This example uses the Customers and Orders tables of the Northwind sample database and refers to them in parentheses).</span></span>  
  
    1. <span data-ttu-id="cb5c6-146">Щелкните элемент **Добавить источник данных проекта**, чтобы подключиться к данным и создать источник данных.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-146">Click **Add Project Data Source** to connect to data and create a data source.</span></span>  
  
    2. <span data-ttu-id="cb5c6-147">На странице приветствия **Мастер настройки источника данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-147">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>  
  
    3. <span data-ttu-id="cb5c6-148">На странице **Выбор типа источника данных** выберите элемент **База данных**.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-148">Select **Database** on the **Choose a Data Source Type** page.</span></span>  
  
    4. <span data-ttu-id="cb5c6-149">На странице **Выбор подключения к базе данных** выберите тип подключения данных из списка доступных подключений.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-149">Select a data connection from the list of available connections on the **Choose Your Data Connection** page.</span></span> <span data-ttu-id="cb5c6-150">Если необходимое подключение данных недоступно, выберите элемент **Создать подключение**, чтобы создать новое подключение данных.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-150">If your desired data connection is not available, select **New Connection** to create a new data connection.</span></span>  
  
    5. <span data-ttu-id="cb5c6-151">Нажмите кнопку **Да, сохранить подключение**, чтобы сохранить строку подключения в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-151">Click **Yes, save the connection** to save the connection string in the application configuration file.</span></span>  
  
    6. <span data-ttu-id="cb5c6-152">Выберите объекты базы данных, чтобы перенести их в приложение.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-152">Select the database objects to bring into your application.</span></span> <span data-ttu-id="cb5c6-153">В данном случае выберите родительскую и дочернюю таблицы (например, таблицы Customers и Orders) с отношением по внешнему ключу.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-153">In this case, select a parent table and child table (for example, Customers and Orders) with a foreign key relationship.</span></span>  
  
    7. <span data-ttu-id="cb5c6-154">Если необходимо, замените имя набора данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-154">Replace the default dataset name if you want.</span></span>  
  
    8. <span data-ttu-id="cb5c6-155">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-155">Click **Finish**.</span></span>  
  
4. <span data-ttu-id="cb5c6-156">В раскрывающемся списке **Отобразить участника** выберите имя столбца (например, ContactName) для его отображения в поле со списком.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-156">In the **Display Member** drop-down box, select the column name (for example, ContactName) to be displayed in the combo box.</span></span>  
  
5. <span data-ttu-id="cb5c6-157">В раскрывающемся списке **Значение участника** выберите столбец (например, CustomerID), чтобы выполнить операции подстановки в дочерней таблице.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-157">In the **Value Member** drop-down box, select the column (for example, CustomerID) to perform the lookup operation in the child table.</span></span>  
  
6. <span data-ttu-id="cb5c6-158">В раскрывающемся списке **Выбранное значение** перейдите к элементу **Источники данных проекта** и только что созданному набору данных, который содержит родительскую и дочернюю таблицы.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-158">In the **Selected Value** drop-down box, navigate to **Project Data Sources** and the dataset you just created that contains the parent and child tables.</span></span> <span data-ttu-id="cb5c6-159">Выберите такое же свойство дочерней таблицы, которое является значением участника родительской таблицы (например, Orders.CustomerID).</span><span class="sxs-lookup"><span data-stu-id="cb5c6-159">Select the same property of the child table that is the Value Member of the parent table (for example, Orders.CustomerID).</span></span> <span data-ttu-id="cb5c6-160">Будут созданы и добавлены в форму соответствующие <xref:System.Windows.Forms.BindingSource>, набор данных и компоненты адаптера таблицы.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-160">The appropriate <xref:System.Windows.Forms.BindingSource> , data set, and table adapter components will be created and added to the form.</span></span>  
  
7. <span data-ttu-id="cb5c6-161">Свяжите элемент управления <xref:System.Windows.Forms.BindingNavigator> с элементом <xref:System.Windows.Forms.BindingSource> дочерней таблицы (например, `OrdersBindingSource`).</span><span class="sxs-lookup"><span data-stu-id="cb5c6-161">Bind the <xref:System.Windows.Forms.BindingNavigator> control to the <xref:System.Windows.Forms.BindingSource> of the child table (for example, `OrdersBindingSource`).</span></span>  
  
8. <span data-ttu-id="cb5c6-162">Свяжите элементы управления, кроме <xref:System.Windows.Forms.ComboBox> и <xref:System.Windows.Forms.BindingNavigator>, с полями сведений из элемента <xref:System.Windows.Forms.BindingSource> дочерней таблицы (например, `OrdersBindingSource`), которые необходимо отобразить.</span><span class="sxs-lookup"><span data-stu-id="cb5c6-162">Bind the controls other than the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.BindingNavigator> control to the details fields from the child table's <xref:System.Windows.Forms.BindingSource> (for example, `OrdersBindingSource`) that you want to display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb5c6-163">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cb5c6-163">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="cb5c6-164">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="cb5c6-164">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="cb5c6-165">Элемент управления ComboBox</span><span class="sxs-lookup"><span data-stu-id="cb5c6-165">ComboBox Control</span></span>](combobox-control-windows-forms.md)
- [<span data-ttu-id="cb5c6-166">Привязка элементов управления к данным в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cb5c6-166">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
