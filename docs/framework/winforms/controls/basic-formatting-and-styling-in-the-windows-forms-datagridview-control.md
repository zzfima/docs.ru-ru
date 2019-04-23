---
title: Базовое форматирование и оформление элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: 5e967c1bbe54095cc11e48b014600158da7fe6a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189902"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="6318b-102">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6318b-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="6318b-103">`DataGridView` Управления упрощает определение основного внешнего вида ячеек и форматирования отображения значений ячеек.</span><span class="sxs-lookup"><span data-stu-id="6318b-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="6318b-104">Вы можете определить внешний вид и стили форматирования для отдельных ячеек, для ячеек в определенных столбцах и строках или для всех ячеек в элементе управления, задав свойства `DataGridViewCellStyle` объектов, доступных через различные `DataGridView` свойства элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6318b-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="6318b-105">Кроме того, можно изменить эти стили, динамически на основе таких факторов значение ячейки, обрабатывая `CellFormatting` событий.</span><span class="sxs-lookup"><span data-stu-id="6318b-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6318b-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6318b-106">In This Section</span></span>  
 [<span data-ttu-id="6318b-107">Практическое руководство. Изменения границ и стили линий сетки в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6318b-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="6318b-108">Описывает способ задания `DataGridView` свойств, которые определяют внешний вид границы элемента управления и разделительных линий между ячейками.</span><span class="sxs-lookup"><span data-stu-id="6318b-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="6318b-109">Стили ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6318b-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6318b-110">Описывает `DataGridViewCellStyle` класс и взаимодействии свойства этого типа для определения, способ отображения ячеек в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="6318b-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="6318b-111">Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6318b-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6318b-112">Описывает использование `DataGridViewCellStyle` свойства, которые определяют внешний вид ячейки по умолчанию в определенных строках и столбцах и весь элемент управления.</span><span class="sxs-lookup"><span data-stu-id="6318b-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="6318b-113">Практическое руководство. Форматирование данных в Windows Forms элемента управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="6318b-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6318b-114">Описание форматирования отображения значений ячеек с помощью `DataGridViewCellStyle` свойства.</span><span class="sxs-lookup"><span data-stu-id="6318b-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="6318b-115">Практическое руководство. Настройка шрифтов и цветов в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6318b-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6318b-116">Описывает использование `DefaultCellStyle` свойство, чтобы задать основные отобразить характеристики всех ячеек в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="6318b-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="6318b-117">Практическое руководство. Установка стилей чередующихся строк для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6318b-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6318b-118">В этой статье описывается создание силу подобном бухгалтерским книгам: в элементе управления с помощью чередующихся строк, отображаемых по-разному.</span><span class="sxs-lookup"><span data-stu-id="6318b-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="6318b-119">Практическое руководство. Применение шаблонов строк для настройки отображения строк в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6318b-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="6318b-120">Описывает использование `RowTemplate` свойства для настройки свойств строки, которые будут использоваться для всех строк в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="6318b-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6318b-121">Ссылка</span><span class="sxs-lookup"><span data-stu-id="6318b-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="6318b-122">Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="6318b-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="6318b-123">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewCellStyle> класса.</span><span class="sxs-lookup"><span data-stu-id="6318b-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="6318b-124">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.CellFormatting> событий.</span><span class="sxs-lookup"><span data-stu-id="6318b-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="6318b-125">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="6318b-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6318b-126">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6318b-126">Related Sections</span></span>  
 [<span data-ttu-id="6318b-127">Настройка элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6318b-127">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6318b-128">Разделы, описывающие пользовательскую отрисовку ячеек и строк <xref:System.Windows.Forms.DataGridView>, а также создание производных ячеек, столбцов и типов строк.</span><span class="sxs-lookup"><span data-stu-id="6318b-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="6318b-129">Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6318b-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="6318b-130">Содержит разделы, описывающие часто используемые свойства ячеек, строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="6318b-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6318b-131">См. также</span><span class="sxs-lookup"><span data-stu-id="6318b-131">See also</span></span>

- [<span data-ttu-id="6318b-132">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="6318b-132">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
