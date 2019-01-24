---
title: элемент управления DataGridView (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- tables [Windows Forms]
- data grids [Windows Forms
- data [Windows Forms], displaying in tabular format
- grid controls [Windows Forms]
- datasets [Windows Forms], user interface
- Windows Forms, displaying data
- data presentation
- tabular data [Windows Forms], displaying on Windows Forms
- datasets [Windows Forms], displaying in DataGridView control
- DataGridView control [Windows Forms]
ms.assetid: dbee73f2-bba6-4874-9389-cd21d44309be
ms.openlocfilehash: 14ba24b414de0732be418210ec44613f840136d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639124"
---
# <a name="datagridview-control-windows-forms"></a><span data-ttu-id="4555d-102">элемент управления DataGridView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4555d-102">DataGridView Control (Windows Forms)</span></span>
<span data-ttu-id="4555d-103">Элемент управления `DataGridView` предоставляет мощный и гибкий способ отображения данных в табличном формате.</span><span class="sxs-lookup"><span data-stu-id="4555d-103">The `DataGridView` control provides a powerful and flexible way to display data in a tabular format.</span></span> <span data-ttu-id="4555d-104">Элемент управления `DataGridView` можно использовать для отображения представлений небольшого объема данных только для чтения, либо можно масштабировать его для отображения редактируемого представления очень больших наборов данных.</span><span class="sxs-lookup"><span data-stu-id="4555d-104">You can use the `DataGridView` control to show read-only views of a small amount of data, or you can scale it to show editable views of very large sets of data.</span></span>  
  
 <span data-ttu-id="4555d-105">Для того чтобы реализовать пользовательское поведение в приложениях, элемент управления `DataGridView` можно расширить несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="4555d-105">You can extend the `DataGridView` control in a number of ways to build custom behaviors into your applications.</span></span> <span data-ttu-id="4555d-106">Например, можно программно задать собственные алгоритмы сортировки, можно создать собственные типы ячеек.</span><span class="sxs-lookup"><span data-stu-id="4555d-106">For example, you can programmatically specify your own sorting algorithms, and you can create your own types of cells.</span></span> <span data-ttu-id="4555d-107">Внешний вид элемента управления `DataGridView` легко настраивается заданием значений нескольких свойств.</span><span class="sxs-lookup"><span data-stu-id="4555d-107">You can easily customize the appearance of the `DataGridView` control by choosing among several properties.</span></span> <span data-ttu-id="4555d-108">В качестве источника данных могут использоваться хранилища данных различных типов, также элемент управления `DataGridView` может работать без привязанного к нему  источника данных.</span><span class="sxs-lookup"><span data-stu-id="4555d-108">Many types of data stores can be used as a data source, or the `DataGridView` control can operate with no data source bound to it.</span></span>  
  
 <span data-ttu-id="4555d-109">В подразделах данного раздела описываются принципы и методы применения возможностей `DataGridView` в приложениях.</span><span class="sxs-lookup"><span data-stu-id="4555d-109">The topics in this section describe the concepts and techniques that you can use to build `DataGridView` features into your applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4555d-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="4555d-110">In This Section</span></span>  
 [<span data-ttu-id="4555d-111">Общие сведения об элементе управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="4555d-111">DataGridView Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 <span data-ttu-id="4555d-112">Содержит разделы с описанием назначения и основных понятий элемента управления `DataGridView` Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4555d-112">Provides topics that describe the architecture and core concepts of the Windows Forms `DataGridView` control.</span></span>  
  
 [<span data-ttu-id="4555d-113">Стандартная функциональность элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4555d-113">Default Functionality in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/default-functionality-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4555d-114">Описание внешнего вида и поведения элемента управления `DataGridView` Windows Forms по умолчанию, когда он привязан к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="4555d-114">Describes the default appearance and behavior of the Windows Forms `DataGridView` control when it is bound to a data source.</span></span>  
  
 [<span data-ttu-id="4555d-115">Типы столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4555d-115">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4555d-116">Описание типов столбцов элемента управления `DataGridView` Windows Forms, используемых для отображения данных, и разрешения пользователям изменять или добавлять данные.</span><span class="sxs-lookup"><span data-stu-id="4555d-116">Describes the column types in the Windows Forms `DataGridView` control used to display data and allow users to modify or add data.</span></span>  
  
 [<span data-ttu-id="4555d-117">Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4555d-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="4555d-118">Разделы, описывающие часто используемые свойства ячеек, строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="4555d-118">Provides topics that describe commonly-used cell, row, and column properties.</span></span>  
  
 [<span data-ttu-id="4555d-119">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4555d-119">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4555d-120">Разделы, описывающие способы изменения базового внешнего вида элемента управления и форматирования отображаемых данных ячейки.</span><span class="sxs-lookup"><span data-stu-id="4555d-120">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="4555d-121">Отображение данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4555d-121">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4555d-122">Разделы, описывающие заполнение элемента управления данными вручную или из внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="4555d-122">Provides topics that describe how to populate the control with data either manually, or from an external data source.</span></span>  
  
 [<span data-ttu-id="4555d-123">Изменение размера столбцов и строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4555d-123">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4555d-124">Разделы, описывающие автоматическую корректировку размера строк и столбцов в соответствии с содержимым ячейки или доступной шириной элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4555d-124">Provides topics that describe how the size of rows and columns can be adjusted automatically to fit cell content or to fit the available width of the control.</span></span>  
  
 [<span data-ttu-id="4555d-125">Сортировка данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4555d-125">Sorting Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4555d-126">Разделы, описывающие возможности сортировки в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="4555d-126">Provides topics that describe the sorting features in the control.</span></span>  
  
 [<span data-ttu-id="4555d-127">Ввод данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4555d-127">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4555d-128">Разделы, в которых описывается изменение способов добавления и изменения данных в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="4555d-128">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
 [<span data-ttu-id="4555d-129">Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4555d-129">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4555d-130">Разделы, описывающие возможности выбора ячеек, строк и столбцов в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="4555d-130">Provides topics that describe the cell, row, and column selection features in the control.</span></span>  
  
 [<span data-ttu-id="4555d-131">Программирование с использованием ячеек, строк и столбцов в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4555d-131">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="4555d-132">Разделы, описывающие программирование объектов ячеек, строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="4555d-132">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
 [<span data-ttu-id="4555d-133">Настройка элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4555d-133">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4555d-134">Разделы, описывающие пользовательскую отрисовку ячеек и строк `DataGridView`, а также создание производных ячеек, столбцов и типов строк.</span><span class="sxs-lookup"><span data-stu-id="4555d-134">Provides topics that describe custom painting `DataGridView` cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="4555d-135">Оптимизация производительности элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4555d-135">Performance Tuning in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4555d-136">Разделы, описывающие, как эффективно использовать элемент управления, чтобы избежать снижения производительности при работе с большими объемами данных.</span><span class="sxs-lookup"><span data-stu-id="4555d-136">Provides topics that describe how to use the control efficiently to avoid performance problems when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="4555d-137">Выполняемая по умолчанию обработка событий мыши и клавиатуры элементом управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4555d-137">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4555d-138">Описание способов взаимодействия пользователей с элементом управления `DataGridView` посредством клавиатуры и мыши.</span><span class="sxs-lookup"><span data-stu-id="4555d-138">Describes how users can interact with the `DataGridView` control through a keyboard and a mouse.</span></span>  
  
 [<span data-ttu-id="4555d-139">Различия элементов управления DataGridView и DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4555d-139">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)  
 <span data-ttu-id="4555d-140">Описывает расширение возможностей и улучшения элемента управления `DataGridView`, который заменяет элемент управления <xref:System.Windows.Forms.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="4555d-140">Describes how the `DataGridView` control improves upon and replaces the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
 <span data-ttu-id="4555d-141">Также см. в разделе [с помощью конструктора с помощью элемента управления DataGridView в Windows Forms](using-the-designer-with-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="4555d-141">Also see [Using the Designer with the Windows Forms DataGridView Control](using-the-designer-with-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4555d-142">Ссылка</span><span class="sxs-lookup"><span data-stu-id="4555d-142">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="4555d-143">Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="4555d-143">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="4555d-144">Содержит справочную документацию по компоненту <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="4555d-144">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="4555d-145">Элемент управления <xref:System.Windows.Forms.DataGridView> и компонент <xref:System.Windows.Forms.BindingSource> предназначены для совместной работы.</span><span class="sxs-lookup"><span data-stu-id="4555d-145">The <xref:System.Windows.Forms.DataGridView> control and the <xref:System.Windows.Forms.BindingSource> component are designed to work closely together.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4555d-146">См. также</span><span class="sxs-lookup"><span data-stu-id="4555d-146">See also</span></span>
- [<span data-ttu-id="4555d-147">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4555d-147">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
