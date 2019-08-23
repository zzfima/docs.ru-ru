---
title: Практическое руководство. Форматирование элемента управления DataGrid в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
ms.openlocfilehash: 99acef0a7b29228ddf0406352ff5a88b77294b00
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966667"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a><span data-ttu-id="0f0f2-102">Практическое руководство. Форматирование элемента управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f0f2-102">How to: Format the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="0f0f2-103">Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="0f0f2-104">Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="0f0f2-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="0f0f2-105">Применение различных цветов к различным частям <xref:System.Windows.Forms.DataGrid> элемента управления помогает упростить чтение и анализ информации.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-105">Applying different colors to various parts of a <xref:System.Windows.Forms.DataGrid> control can help to make the information in it easier to read and interpret.</span></span> <span data-ttu-id="0f0f2-106">Цвет может применяться к строкам и столбцам.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-106">Color can be applied to rows and columns.</span></span> <span data-ttu-id="0f0f2-107">Строки и столбцы также можно скрыть или показать по собственному усмотрению.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-107">Rows and columns can also be hidden or shown at your discretion.</span></span>  
  
 <span data-ttu-id="0f0f2-108">Существует три основных аспекта форматирования <xref:System.Windows.Forms.DataGrid> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-108">There are three basic aspects of formatting the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="0f0f2-109">Можно задать свойства, чтобы установить стиль по умолчанию, в котором будут отображаться данные.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-109">You can set properties to establish a default style in which data is displayed.</span></span> <span data-ttu-id="0f0f2-110">С этого основания можно настроить способ отображения определенных таблиц во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-110">From that base, you can then customize the way certain tables are displayed at run time.</span></span> <span data-ttu-id="0f0f2-111">Наконец, можно изменить столбцы, отображаемые в сетке данных, а также цвета и другие отображаемые параметры форматирования.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-111">Finally, you can modify which columns are displayed in the data grid as well as the colors and other formatting that is shown.</span></span>  
  
 <span data-ttu-id="0f0f2-112">В качестве начального шага при форматировании сетки данных можно задать свойства <xref:System.Windows.Forms.DataGrid> самого себя.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-112">As an initial step in formatting a data grid, you can set the properties of the <xref:System.Windows.Forms.DataGrid> itself.</span></span> <span data-ttu-id="0f0f2-113">Эти варианты цвета и формата образуют основу, из которой можно вносить изменения в зависимости от отображаемых таблиц и столбцов данных.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-113">These color and format choices form a base from which you can then make changes depending on the data tables and columns displayed.</span></span>  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a><span data-ttu-id="0f0f2-114">Установка стиля по умолчанию для элемента управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="0f0f2-114">To establish a default style for the DataGrid control</span></span>  
  
1. <span data-ttu-id="0f0f2-115">При необходимости задайте следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="0f0f2-115">Set the following properties as appropriate:</span></span>  
  
    |<span data-ttu-id="0f0f2-116">Свойство.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-116">Property</span></span>|<span data-ttu-id="0f0f2-117">Описание</span><span class="sxs-lookup"><span data-stu-id="0f0f2-117">Description</span></span>|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<span data-ttu-id="0f0f2-118"><xref:System.Windows.Forms.DataGrid.BackColor%2A> Свойство определяет цвет строк сетки с четными номерами.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-118">The <xref:System.Windows.Forms.DataGrid.BackColor%2A> property defines the color of the even-numbered rows of the grid.</span></span> <span data-ttu-id="0f0f2-119">Если для <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> свойства задан другой цвет, для каждой другой строки задается этот новый цвет (строки 1, 3, 5 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="0f0f2-119">When you set the <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> property to a different color, every other row is set to this new color (rows 1, 3, 5, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|<span data-ttu-id="0f0f2-120">Цвет фона строк сетки с четными номерами (строки 0, 2, 4, 6 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="0f0f2-120">The background color of the even-numbered rows of the grid (rows 0, 2, 4, 6, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|<span data-ttu-id="0f0f2-121">В то время как <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> свойства <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> <xref:System.Windows.Forms.DataGrid.BackColor%2A> и определяют цвет строк в сетке, свойство определяет цвет области нонров, которая отображается только при прокрутке сетки вниз, или если в таблице содержатся только несколько строк. Сетка.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-121">Whereas the <xref:System.Windows.Forms.DataGrid.BackColor%2A> and <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> properties determines the color of rows in the grid, the <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> property determines the color of the nonrow area, which is only visible when the grid is scrolled to the bottom, or if only a few rows are contained in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|<span data-ttu-id="0f0f2-122">Стиль границы сетки, одно из <xref:System.Windows.Forms.BorderStyle> значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-122">The grid's border style, one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|<span data-ttu-id="0f0f2-123">Цвет фона заголовка окна сетки, который появляется непосредственно над сеткой.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-123">The background color of the grid's window caption which appears immediately above the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|<span data-ttu-id="0f0f2-124">Шрифт заголовка в верхней части сетки.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-124">The font of the caption at the top of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|<span data-ttu-id="0f0f2-125">Цвет фона заголовка окна сетки.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-125">The background color of the grid's window caption.</span></span>|  
    |<xref:System.Windows.Forms.Control.Font%2A>|<span data-ttu-id="0f0f2-126">Шрифт, используемый для вывода текста в сетке.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-126">The font used to display the text in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|<span data-ttu-id="0f0f2-127">Цвет шрифта, отображаемого данными в строках сетки данных.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-127">The color of the font displayed by the data in the rows of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|<span data-ttu-id="0f0f2-128">Цвет линий сетки сетки данных.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-128">The color of the grid lines of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|<span data-ttu-id="0f0f2-129">Стиль строк, разделяющих ячейки сетки, одно из <xref:System.Windows.Forms.DataGridLineStyle> значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-129">The style of the lines separating the cells of the grid, one of the <xref:System.Windows.Forms.DataGridLineStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|<span data-ttu-id="0f0f2-130">Цвет фона заголовков строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-130">The background color of row and column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|<span data-ttu-id="0f0f2-131">Шрифт, используемый для заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-131">The font used for the column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|<span data-ttu-id="0f0f2-132">Цвет переднего плана для заголовков столбцов сетки, включая текст заголовка столбца и знаки плюса/минуса (для расширения строк при отображении нескольких связанных таблиц).</span><span class="sxs-lookup"><span data-stu-id="0f0f2-132">The foreground color of the grid's column headers, including the column header text and the plus/minus glyphs (to expand rows when multiple related tables are displayed).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|<span data-ttu-id="0f0f2-133">Цвет текста всех ссылок в сетке данных, включая ссылки на дочерние таблицы, имя связи и т. д.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-133">The color of text of all the links in the data grid, including links to child tables, the relation name, and so on.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|<span data-ttu-id="0f0f2-134">В дочерней таблице это цвет фона родительских строк.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-134">In a child table, this is the background color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|<span data-ttu-id="0f0f2-135">В дочерней таблице это цвет переднего плана для родительских строк.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-135">In a child table, this is the foreground color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|<span data-ttu-id="0f0f2-136">Определяет, отображаются ли имена таблиц и столбцов в родительской строке с помощью <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> перечисления.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-136">Determines whether the table and column names are displayed in the parent row, by means of the <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> enumeration.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|<span data-ttu-id="0f0f2-137">Стандартная ширина (в пикселях) столбцов сетки.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-137">The default width (in pixels) of columns in the grid.</span></span> <span data-ttu-id="0f0f2-138">Установите это свойство перед сбросом <xref:System.Windows.Forms.DataGrid.DataSource%2A> свойств и <xref:System.Windows.Forms.DataGrid.DataMember%2A> ( <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> отдельно или с помощью метода), либо свойство не будет действовать.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-138">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="0f0f2-139">Свойству нельзя присвоить значение меньше 0.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-139">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|<span data-ttu-id="0f0f2-140">Высота строки (в пикселях) в сетке.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-140">The row height (in pixels) of rows in the grid.</span></span> <span data-ttu-id="0f0f2-141">Установите это свойство перед сбросом <xref:System.Windows.Forms.DataGrid.DataSource%2A> свойств и <xref:System.Windows.Forms.DataGrid.DataMember%2A> ( <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> отдельно или с помощью метода), либо свойство не будет действовать.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-141">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="0f0f2-142">Свойству нельзя присвоить значение меньше 0.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-142">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|<span data-ttu-id="0f0f2-143">Ширина заголовков строк сетки.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-143">The width of the row headers of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|<span data-ttu-id="0f0f2-144">Если выбрана строка или ячейка, это цвет фона.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-144">When a row or cell is selected, this is the background color.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|<span data-ttu-id="0f0f2-145">Если выбрана строка или ячейка, это цвет переднего плана.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-145">When a row or cell is selected, this is the foreground color.</span></span>|  
  
    > [!NOTE]
    > <span data-ttu-id="0f0f2-146">Помните, что при настройке цветов элементов управления можно сделать элемент управления недоступным из-за плохого выбора цвета (например, красный и зеленый).</span><span class="sxs-lookup"><span data-stu-id="0f0f2-146">Keep in mind, when customizing the colors of controls, that it is possible to make the control inaccessible, due to poor color choice (for example, red and green).</span></span> <span data-ttu-id="0f0f2-147">Чтобы избежать этой проблемы, используйте цвета, доступные в палитре **системные цвета** .</span><span class="sxs-lookup"><span data-stu-id="0f0f2-147">Use the colors available on the **System Colors** palette to avoid this issue.</span></span>  
  
     <span data-ttu-id="0f0f2-148">В следующих процедурах предполагается, что <xref:System.Windows.Forms.DataGrid> форма имеет элемент управления, привязанный к таблице данных.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-148">The following procedures assume your form has a <xref:System.Windows.Forms.DataGrid> control bound to a data table.</span></span> <span data-ttu-id="0f0f2-149">Дополнительные сведения см. [в разделе привязка Windows Forms элемента управления DataGrid к источнику данных](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="0f0f2-149">For more information, see [Binding the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a><span data-ttu-id="0f0f2-150">Задание стиля таблицы и столбца таблицы данных программным способом</span><span class="sxs-lookup"><span data-stu-id="0f0f2-150">To set the table and column style of a data table programmatically</span></span>  
  
1. <span data-ttu-id="0f0f2-151">Создайте новый стиль таблицы и задайте его свойства.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-151">Create a new table style and set its properties.</span></span>  
  
2. <span data-ttu-id="0f0f2-152">Создайте стиль столбца и задайте его свойства.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-152">Create a column style and set its properties.</span></span>  
  
3. <span data-ttu-id="0f0f2-153">Добавьте стиль столбца в коллекцию стилей столбцов стиля таблицы.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-153">Add the column style to the table style's column styles collection.</span></span>  
  
4. <span data-ttu-id="0f0f2-154">Добавьте стиль таблицы в коллекцию табличных стилей сетки данных.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-154">Add the table style to the data grid's table styles collection.</span></span>  
  
5. <span data-ttu-id="0f0f2-155">В приведенном ниже примере создайте экземпляр нового <xref:System.Windows.Forms.DataGridTableStyle> и задайте его <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-155">In the example below, create an instance of a new <xref:System.Windows.Forms.DataGridTableStyle> and set its <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property.</span></span>  
  
6. <span data-ttu-id="0f0f2-156">Создайте новый экземпляр **гридколумнстиле** и задайте его **MappingName** (и другие свойства макета и экрана).</span><span class="sxs-lookup"><span data-stu-id="0f0f2-156">Create a new instance of a **GridColumnStyle** and set its **MappingName** (and some other layout and display properties).</span></span>  
  
7. <span data-ttu-id="0f0f2-157">Повторите шаги с 2 по 6 для каждого стиля столбца, который нужно создать.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-157">Repeat steps 2 through 6 for each column style you want to create.</span></span>  
  
     <span data-ttu-id="0f0f2-158">В следующем примере показано, как <xref:System.Windows.Forms.DataGridTextBoxColumn> создается, поскольку имя отображается в столбце.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-158">The following example illustrates how a <xref:System.Windows.Forms.DataGridTextBoxColumn> is created, because a name is to be displayed in the column.</span></span> <span data-ttu-id="0f0f2-159">Кроме того, вы добавляете стиль столбца к <xref:System.Windows.Forms.GridColumnStylesCollection> стилю таблицы и добавляете стиль <xref:System.Windows.Forms.GridTableStylesCollection> таблицы в сетку данных.</span><span class="sxs-lookup"><span data-stu-id="0f0f2-159">Additionally, you add the column style to the <xref:System.Windows.Forms.GridColumnStylesCollection> of the table style, and you add the table style to the <xref:System.Windows.Forms.GridTableStylesCollection> of the data grid.</span></span>  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName   
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName   
       ' to the name of a DataColumn in the DataTable.   
       ' Set the HeaderText and Width properties.   
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to   
       ' the GridTableStylesCollection.   
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName   
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName   
       // to the name of a DataColumn in the DataTable.   
       // Set the HeaderText and Width properties.   
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to   
       // the GridTableStylesCollection.   
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName   
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName   
          // to the name of a DataColumn in the DataTable.   
          // Set the HeaderText and Width properties.   
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to   
          // the GridTableStylesCollection.   
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0f0f2-160">См. также</span><span class="sxs-lookup"><span data-stu-id="0f0f2-160">See also</span></span>

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [<span data-ttu-id="0f0f2-161">Практическое руководство. Удаление или скрытие столбцов в элементе управления Windows Forms DataGrid</span><span class="sxs-lookup"><span data-stu-id="0f0f2-161">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="0f0f2-162">Элемент управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="0f0f2-162">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
