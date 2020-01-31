---
title: Изменение размера столбцов и строк в элементе управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
ms.openlocfilehash: 8f8394a837ccc11c469f9ad4feeb60464d0014fe
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742413"
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="bfdbd-102">Изменение размера столбцов и строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bfdbd-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="bfdbd-103">Элемент управления `DataGridView` предоставляет множество параметров для настройки режима изменения размера столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="bfdbd-104">Обычно размеры ячеек `DataGridView` не изменяются в зависимости от их содержимого.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="bfdbd-105">Вместо этого они обрезает все отображаемые значения, превышающие ячейку.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="bfdbd-106">Если содержимое можно отобразить в виде строки, ячейка отобразится в подсказке.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="bfdbd-107">По умолчанию пользователи могут перетаскивать разделители строк, столбцов и заголовков с помощью мыши для отображения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="bfdbd-108">Пользователи также могут дважды щелкнуть разделитель, чтобы автоматически изменить размер связанного диапазона строк, столбцов или заголовков в зависимости от его содержимого.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="bfdbd-109">Элемент управления `DataGridView` предоставляет свойства, методы и события, позволяющие настраивать или отключать все эти перенаправленные пользователем поведения.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="bfdbd-110">Кроме того, можно программным путем изменить размер строк, столбцов и заголовков, чтобы они соответствовали их содержимому, или настроить их для автоматического изменения размера при изменении содержимого.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="bfdbd-111">Можно также настроить столбцы для автоматического разделения доступной ширины элемента управления в указанных пропорциях.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bfdbd-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="bfdbd-112">In This Section</span></span>  
 [<span data-ttu-id="bfdbd-113">Изменение размеров управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bfdbd-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="bfdbd-114">Описывает параметры изменения размера строк, столбцов и заголовков.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="bfdbd-115">Также содержит сведения о свойствах и методах, связанных с изменением размеров, и описываются распространенные сценарии использования.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="bfdbd-116">Установка режимов заполнения для столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bfdbd-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="bfdbd-117">Подробное описание режима заполнения столбца и предоставление демонстрационного кода, который можно использовать для экспериментирования с режимом заполнения столбца и другими режимами.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="bfdbd-118">Практическое руководство. Режимы изменения размеров элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bfdbd-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="bfdbd-119">Описывает, как настроить режимы изменения размера для распространенных целей.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="bfdbd-120">Практическое руководство. Программное изменение размера ячеек элемента управления DataGridView в соответствии с размером отображаемых данных в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bfdbd-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="bfdbd-121">Предоставляет демонстрационный код, который можно использовать для экспериментов с программным изменением размера.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="bfdbd-122">Практическое руководство. Автоматическое изменение размера ячеек при изменении содержимого в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bfdbd-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="bfdbd-123">Предоставляет демонстрационный код, который можно использовать для экспериментов с режимами автоматического изменения размера.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="bfdbd-124">Справочные сведения</span><span class="sxs-lookup"><span data-stu-id="bfdbd-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="bfdbd-125">Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfdbd-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="bfdbd-126">See also</span></span>

- [<span data-ttu-id="bfdbd-127">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="bfdbd-127">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
