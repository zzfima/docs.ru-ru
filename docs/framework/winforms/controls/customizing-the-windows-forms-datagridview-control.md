---
title: "Настройка элементов управления DataGridView в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 348651784ef2b4d99679038a1875fc6650688a6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="a5260-102">Настройка элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5260-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a5260-103">`DataGridView` Управления предоставляет несколько свойств, которые можно использовать для настройки внешнего вида и базовое поведение ячеек, строк и столбцов (Вид).</span><span class="sxs-lookup"><span data-stu-id="a5260-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="a5260-104">При наличии особых требований, выходящих за рамки возможностей <xref:System.Windows.Forms.DataGridViewCellStyle> класса, однако также можно реализовать пользовательское отображение для элемента управления или расширить его возможности, создав пользовательские ячейки, строки и столбцы.</span><span class="sxs-lookup"><span data-stu-id="a5260-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="a5260-105">Для рисования ячейки и строки самостоятельно, можно обработать различные `DataGridView` события рисования.</span><span class="sxs-lookup"><span data-stu-id="a5260-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="a5260-106">Чтобы изменить существующие функциональные возможности или предоставить новые функциональные возможности, можно создать собственные типы, производные от существующих `DataGridViewCell`, `DataGridViewColumn`, и `DataGridViewRow` типы.</span><span class="sxs-lookup"><span data-stu-id="a5260-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="a5260-107">Можно также предоставить новые возможности редактирования, создав производные типы, которые отображение элемента управления по своему выбору, когда ячейка находится в режиме редактирования.</span><span class="sxs-lookup"><span data-stu-id="a5260-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a5260-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a5260-108">In This Section</span></span>  
 [<span data-ttu-id="a5260-109">Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5260-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="a5260-110">Описывает способы обработки <xref:System.Windows.Forms.DataGridView.CellPainting> событий для рисования ячейки вручную.</span><span class="sxs-lookup"><span data-stu-id="a5260-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="a5260-111">Практическое руководство. Настройка внешнего вида строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5260-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="a5260-112">Описывает способы обработки <xref:System.Windows.Forms.DataGridView.RowPrePaint> и <xref:System.Windows.Forms.DataGridView.RowPostPaint> событий для рисования строки с настраиваемым, градиента фона и содержимого, которое охватывает несколько столбцов.</span><span class="sxs-lookup"><span data-stu-id="a5260-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="a5260-113">Практическое руководство. Дополнительные возможности управления внешним видом и поведением ячеек и столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5260-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="a5260-114">Описывает способ создания пользовательских типов, производных от `DataGridViewCell` и `DataGridViewColumn` для выделения ячеек при наведении указателя мыши на них.</span><span class="sxs-lookup"><span data-stu-id="a5260-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="a5260-115">Практическое руководство. Отключение кнопок в кнопочном столбце элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5260-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="a5260-116">Описывает способ создания пользовательских типов, производных от <xref:System.Windows.Forms.DataGridViewButtonCell> и <xref:System.Windows.Forms.DataGridViewButtonColumn> для отображения отключенных кнопок в столбце кнопок.</span><span class="sxs-lookup"><span data-stu-id="a5260-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="a5260-117">Практическое руководство. Размещение элементов управления в ячейках элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5260-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="a5260-118">Описывает, как реализовать `IDataGridViewEditingControl` интерфейса и создания пользовательских типов, производных от `DataGridViewCell` и `DataGridViewColumn` для отображения <xref:System.Windows.Forms.DateTimePicker> управления, если ячейка находится в режиме редактирования.</span><span class="sxs-lookup"><span data-stu-id="a5260-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a5260-119">Ссылка</span><span class="sxs-lookup"><span data-stu-id="a5260-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="a5260-120">Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="a5260-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="a5260-121">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewCell> класса.</span><span class="sxs-lookup"><span data-stu-id="a5260-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="a5260-122">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewRow> класса.</span><span class="sxs-lookup"><span data-stu-id="a5260-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="a5260-123">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewColumn> класса.</span><span class="sxs-lookup"><span data-stu-id="a5260-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="a5260-124">Содержит справочную документацию по <xref:System.Windows.Forms.IDataGridViewEditingControl> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a5260-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a5260-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a5260-125">Related Sections</span></span>  
 [<span data-ttu-id="a5260-126">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5260-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a5260-127">Разделы, описывающие способы изменения базового внешнего вида элемента управления и форматирования отображаемых данных ячейки.</span><span class="sxs-lookup"><span data-stu-id="a5260-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5260-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a5260-128">See Also</span></span>  
 [<span data-ttu-id="a5260-129">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="a5260-129">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="a5260-130">Типы столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5260-130">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
