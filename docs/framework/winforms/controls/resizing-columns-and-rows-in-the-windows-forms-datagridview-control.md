---
title: Изменение размера столбцов и строк элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
ms.openlocfilehash: 8eae5dafa314bb293f55a780f6be67d06f376004
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709664"
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2635d-102">Изменение размера столбцов и строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2635d-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2635d-103">`DataGridView` Элемент управления предоставляет множество возможностей для настройки поведения изменения размеров его столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="2635d-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="2635d-104">Как правило `DataGridView` не меняют размер ячеек на основе их содержимого.</span><span class="sxs-lookup"><span data-stu-id="2635d-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="2635d-105">Вместо этого они клипов любой отображаемого значения, которое больше, чем ячейки.</span><span class="sxs-lookup"><span data-stu-id="2635d-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="2635d-106">Содержимое может отображаться в виде строки, в ячейке отображается во всплывающей подсказке.</span><span class="sxs-lookup"><span data-stu-id="2635d-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="2635d-107">По умолчанию пользователи смогут перетаскивать строк, столбцов и разделителей заголовка с помощью мыши, чтобы показать больше сведений.</span><span class="sxs-lookup"><span data-stu-id="2635d-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="2635d-108">Пользователей можно также дважды щелкнуть разделитель автоматическое изменение размера связанного внешнего строки, столбца или заголовок, основываясь на его содержимом.</span><span class="sxs-lookup"><span data-stu-id="2635d-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="2635d-109">`DataGridView` Элемент управления предоставляет свойства, методы и события, которые позволяют настроить или отключить такое поведение, управляемое пользователем.</span><span class="sxs-lookup"><span data-stu-id="2635d-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="2635d-110">Кроме того можно программно изменить размер строк, столбцов и заголовков в соответствии с содержимым, или можно настроить их автоматическое изменение при изменении содержимого.</span><span class="sxs-lookup"><span data-stu-id="2635d-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="2635d-111">Можно также настроить столбцы для автоматического распределения доступную ширину элемента управления в пропорций.</span><span class="sxs-lookup"><span data-stu-id="2635d-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2635d-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="2635d-112">In This Section</span></span>  
 [<span data-ttu-id="2635d-113">Изменение размеров управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2635d-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2635d-114">Описывает параметры для изменения размеров строк, столбцов и заголовков.</span><span class="sxs-lookup"><span data-stu-id="2635d-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="2635d-115">Также содержит сведения о связанных с изменения размера свойства и методы и описываются распространенные сценарии использования.</span><span class="sxs-lookup"><span data-stu-id="2635d-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="2635d-116">Установка режимов заполнения для столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2635d-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2635d-117">Описание режима заполнения подробно, а также демонстрационный код, который можно использовать для экспериментов с помощью режима заполнения и другие режимы.</span><span class="sxs-lookup"><span data-stu-id="2635d-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="2635d-118">Практическое руководство. Режимы изменения размеров элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2635d-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2635d-119">В этой статье описывается настройка режимы установки размеров для общих целей.</span><span class="sxs-lookup"><span data-stu-id="2635d-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="2635d-120">Практическое руководство. Программное изменение размера ячеек в соответствии с размером в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2635d-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="2635d-121">Предоставляет демонстрационный код, который можно использовать для экспериментов с программного изменения размеров.</span><span class="sxs-lookup"><span data-stu-id="2635d-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="2635d-122">Практическое руководство. Автоматическое изменение размера ячеек при изменении содержимого в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2635d-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="2635d-123">Предоставляет демонстрационный код, который можно использовать для экспериментов с режимами автоматического изменения размера.</span><span class="sxs-lookup"><span data-stu-id="2635d-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2635d-124">Ссылка</span><span class="sxs-lookup"><span data-stu-id="2635d-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="2635d-125">Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="2635d-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2635d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="2635d-126">See also</span></span>
- [<span data-ttu-id="2635d-127">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="2635d-127">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
