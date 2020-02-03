---
title: Базовое форматирование и стилизация в элементе управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: d295718b7bd4f3bc4c5f63b6e6cb911f733525fe
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731998"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="133a6-102">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="133a6-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="133a6-103">Элемент управления `DataGridView` позволяет легко определить базовый вид ячеек и формат отображения значений ячеек.</span><span class="sxs-lookup"><span data-stu-id="133a6-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="133a6-104">Можно определить стили оформления и форматирования для отдельных ячеек, для ячеек в определенных столбцах и строках или для всех ячеек в элементе управления, задав свойства `DataGridViewCellStyle` объектов, доступ к которым осуществляется через различные свойства элемента управления `DataGridView`.</span><span class="sxs-lookup"><span data-stu-id="133a6-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="133a6-105">Кроме того, эти стили можно динамически изменить на основе таких факторов, как значение ячейки, обрабатывая событие `CellFormatting`.</span><span class="sxs-lookup"><span data-stu-id="133a6-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="133a6-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="133a6-106">In This Section</span></span>  
 [<span data-ttu-id="133a6-107">Практическое руководство. Изменение внешнего вида границ и линий сетки элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="133a6-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="133a6-108">Описывает, как задать свойства `DataGridView`, определяющие внешний вид границы элемента управления и линий границ между ячейками.</span><span class="sxs-lookup"><span data-stu-id="133a6-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="133a6-109">Стили ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="133a6-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="133a6-110">Описывает класс `DataGridViewCellStyle` и способ взаимодействия свойств этого типа для определения способа отображения ячеек в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="133a6-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="133a6-111">Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="133a6-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="133a6-112">Описывает использование `DataGridViewCellStyle` свойств для определения стандартного вида ячеек в определенных строках и столбцах, а также во всем элементе управления.</span><span class="sxs-lookup"><span data-stu-id="133a6-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="133a6-113">Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="133a6-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="133a6-114">Описание форматирования отображаемых значений ячеек с помощью `DataGridViewCellStyle` свойств.</span><span class="sxs-lookup"><span data-stu-id="133a6-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="133a6-115">Практическое руководство. Настройка шрифтов и цветов в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="133a6-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="133a6-116">Описывает использование свойства `DefaultCellStyle` для задания основных характеристик отображения для всех ячеек в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="133a6-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="133a6-117">Практическое руководство. Настройка формата отображения четных строк для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="133a6-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="133a6-118">Описывает, как создать в элементе управления воздействие, аналогичное, с помощью чередующихся строк, которые отображаются по-разному.</span><span class="sxs-lookup"><span data-stu-id="133a6-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="133a6-119">Практическое руководство. Применение шаблонов строк для настройки отображения строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="133a6-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="133a6-120">Описывает использование свойства `RowTemplate` для задания свойств строки, которые будут использоваться для всех строк в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="133a6-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="133a6-121">Справочник</span><span class="sxs-lookup"><span data-stu-id="133a6-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="133a6-122">Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="133a6-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="133a6-123">Содержит справочную документацию по классу <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="133a6-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="133a6-124">Содержит справочную документацию по событию <xref:System.Windows.Forms.DataGridView.CellFormatting>.</span><span class="sxs-lookup"><span data-stu-id="133a6-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="133a6-125">Содержит справочную документацию по свойству <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="133a6-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="133a6-126">См. также</span><span class="sxs-lookup"><span data-stu-id="133a6-126">Related Sections</span></span>  
 [<span data-ttu-id="133a6-127">Настройка элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="133a6-127">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="133a6-128">Разделы, описывающие пользовательскую отрисовку ячеек и строк <xref:System.Windows.Forms.DataGridView>, а также создание производных ячеек, столбцов и типов строк.</span><span class="sxs-lookup"><span data-stu-id="133a6-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="133a6-129">Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="133a6-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="133a6-130">Содержит разделы, описывающие часто используемые свойства ячеек, строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="133a6-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="133a6-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="133a6-131">See also</span></span>

- [<span data-ttu-id="133a6-132">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="133a6-132">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
