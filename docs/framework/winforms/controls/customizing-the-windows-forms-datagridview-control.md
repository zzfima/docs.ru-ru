---
title: Настройка элемента управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 348c78d091679418f2452326555d49229bd2a8ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744021"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="2bc30-102">Настройка элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2bc30-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2bc30-103">Элемент управления `DataGridView` предоставляет несколько свойств, которые можно использовать для настройки внешнего вида и основного поведения (внешнего вида) своих ячеек, строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="2bc30-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="2bc30-104">Однако при наличии особых потребностей, которые выходят за пределы возможностей класса <xref:System.Windows.Forms.DataGridViewCellStyle>, можно также реализовать рисование владельцем для элемента управления или расширить его возможности путем создания пользовательских ячеек, столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="2bc30-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="2bc30-105">Для самостоятельного заполнения ячеек и строк можно обрабатывать различные события рисования `DataGridView`.</span><span class="sxs-lookup"><span data-stu-id="2bc30-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="2bc30-106">Чтобы изменить существующие функциональные возможности или предоставить новые функциональные возможности, можно создать собственные типы, производные от существующих типов `DataGridViewCell`, `DataGridViewColumn`и `DataGridViewRow`.</span><span class="sxs-lookup"><span data-stu-id="2bc30-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="2bc30-107">Можно также предоставить новые возможности редактирования, создав производные типы, которые отображают выбираемый элемент управления, когда ячейка находится в режиме редактирования.</span><span class="sxs-lookup"><span data-stu-id="2bc30-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2bc30-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="2bc30-108">In This Section</span></span>  
 [<span data-ttu-id="2bc30-109">Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2bc30-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="2bc30-110">Описывает, как обрабатывать событие <xref:System.Windows.Forms.DataGridView.CellPainting> для ручного заполнения ячеек.</span><span class="sxs-lookup"><span data-stu-id="2bc30-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="2bc30-111">Практическое руководство. Настройка внешнего вида строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2bc30-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="2bc30-112">Описывает, как обрабатывать события <xref:System.Windows.Forms.DataGridView.RowPrePaint> и <xref:System.Windows.Forms.DataGridView.RowPostPaint>, чтобы закрасить строки с помощью пользовательского градиентного фона и содержимого, охватывающего несколько столбцов.</span><span class="sxs-lookup"><span data-stu-id="2bc30-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="2bc30-113">Практическое руководство. Дополнительные возможности управления внешним видом и поведением ячеек и столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2bc30-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="2bc30-114">Описывает создание пользовательских типов, производных от `DataGridViewCell` и `DataGridViewColumn`, для выделения ячеек при помещении на них указателя мыши.</span><span class="sxs-lookup"><span data-stu-id="2bc30-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="2bc30-115">Практическое руководство. Отключение кнопок в кнопочном столбце элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2bc30-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="2bc30-116">Описывает создание пользовательских типов, производных от <xref:System.Windows.Forms.DataGridViewButtonCell> и <xref:System.Windows.Forms.DataGridViewButtonColumn>, для отображения отключенных кнопок в столбце кнопки.</span><span class="sxs-lookup"><span data-stu-id="2bc30-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="2bc30-117">Практическое руководство. Размещение элементов управления в ячейках элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2bc30-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="2bc30-118">Описывает, как реализовать интерфейс `IDataGridViewEditingControl` и создавать пользовательские типы, производные от `DataGridViewCell` и `DataGridViewColumn` для отображения элемента управления <xref:System.Windows.Forms.DateTimePicker>, когда ячейка находится в режиме редактирования.</span><span class="sxs-lookup"><span data-stu-id="2bc30-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2bc30-119">Справочные сведения</span><span class="sxs-lookup"><span data-stu-id="2bc30-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="2bc30-120">Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="2bc30-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="2bc30-121">Содержит справочную документацию по классу <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="2bc30-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="2bc30-122">Содержит справочную документацию по классу <xref:System.Windows.Forms.DataGridViewRow>.</span><span class="sxs-lookup"><span data-stu-id="2bc30-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="2bc30-123">Содержит справочную документацию по классу <xref:System.Windows.Forms.DataGridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="2bc30-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="2bc30-124">Содержит справочную документацию по интерфейсу <xref:System.Windows.Forms.IDataGridViewEditingControl>.</span><span class="sxs-lookup"><span data-stu-id="2bc30-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2bc30-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="2bc30-125">Related Sections</span></span>  
 [<span data-ttu-id="2bc30-126">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2bc30-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2bc30-127">Разделы, описывающие способы изменения базового внешнего вида элемента управления и форматирования отображаемых данных ячейки.</span><span class="sxs-lookup"><span data-stu-id="2bc30-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc30-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="2bc30-128">See also</span></span>

- [<span data-ttu-id="2bc30-129">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="2bc30-129">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="2bc30-130">Типы столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2bc30-130">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
