---
title: "Базовое форматирование и оформление элемента управления DataGridView в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1c6ae9c4159f8f9eafd73608e4fc3f4a646c1eaa
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="61051-102">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="61051-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="61051-103">`DataGridView` Управления упрощает определение основного внешнего вида ячеек и форматирования отображения значений ячеек.</span><span class="sxs-lookup"><span data-stu-id="61051-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="61051-104">Можно задать внешний вид и стили форматирования для отдельных ячеек, для ячеек в определенных столбцах и строках или для всех ячеек в элементе управления, задав свойства `DataGridViewCellStyle` объектов, доступных через различные `DataGridView` свойств элемента управления.</span><span class="sxs-lookup"><span data-stu-id="61051-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="61051-105">Кроме того, можно изменить эти стили, динамически на основе таких факторов значение ячейки, обрабатывая `CellFormatting` событий.</span><span class="sxs-lookup"><span data-stu-id="61051-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="61051-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="61051-106">In This Section</span></span>  
 [<span data-ttu-id="61051-107">Практическое руководство. Изменение внешнего вида границ и линий сетки элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="61051-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="61051-108">Описывает, как задать `DataGridView` свойства, определяющие внешний вид границы элемента управления и разделительных линий между ячейками.</span><span class="sxs-lookup"><span data-stu-id="61051-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="61051-109">Стили ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="61051-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="61051-110">Описывает `DataGridViewCellStyle` класса и взаимодействие свойств этого типа, чтобы определить способ отображения ячеек в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="61051-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="61051-111">Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="61051-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="61051-112">Описывает использование `DataGridViewCellStyle` свойства, определяющие внешний вид ячеек по умолчанию в определенных строках и столбцах и всего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="61051-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="61051-113">Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="61051-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="61051-114">Описание форматирования отображения значений ячеек с помощью `DataGridViewCellStyle` свойства.</span><span class="sxs-lookup"><span data-stu-id="61051-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="61051-115">Практическое руководство. Настройка шрифтов и цветов в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="61051-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="61051-116">Описывает использование `DefaultCellStyle` свойство, чтобы задать основные отобразить характеристики всех ячеек в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="61051-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="61051-117">Практическое руководство. Настройка формата отображения четных строк для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="61051-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="61051-118">Описывает, как для создания эффекта подобном бухгалтерским книгам: в элементе управления с помощью чередующихся строк, которые отображаются по-разному.</span><span class="sxs-lookup"><span data-stu-id="61051-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="61051-119">Практическое руководство. Применение шаблонов строк для настройки отображения строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="61051-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="61051-120">Описывает использование `RowTemplate` свойства для настройки свойств строки, которые будут использоваться для всех строк в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="61051-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="61051-121">Ссылка</span><span class="sxs-lookup"><span data-stu-id="61051-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="61051-122">Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="61051-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="61051-123">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewCellStyle> класса.</span><span class="sxs-lookup"><span data-stu-id="61051-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="61051-124">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.CellFormatting> событий.</span><span class="sxs-lookup"><span data-stu-id="61051-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="61051-125">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="61051-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="61051-126">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="61051-126">Related Sections</span></span>  
 [<span data-ttu-id="61051-127">Настройка элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="61051-127">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="61051-128">Разделы, описывающие пользовательскую отрисовку ячеек и строк <xref:System.Windows.Forms.DataGridView>, а также создание производных ячеек, столбцов и типов строк.</span><span class="sxs-lookup"><span data-stu-id="61051-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="61051-129">Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="61051-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="61051-130">Содержит разделы, описывающие часто используемые свойства ячеек, строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="61051-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61051-131">См. также</span><span class="sxs-lookup"><span data-stu-id="61051-131">See Also</span></span>  
 [<span data-ttu-id="61051-132">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="61051-132">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
