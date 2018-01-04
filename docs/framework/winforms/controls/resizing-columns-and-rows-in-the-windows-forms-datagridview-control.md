---
title: "Изменение размера столбцов и строк элемента управления DataGridView в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c1c11ca487003e57a499b3ff46178350e6aad404
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="9ab85-102">Изменение размера столбцов и строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ab85-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="9ab85-103">`DataGridView` Элемент управления предоставляет множество возможностей для настройки поведения изменения размеров его столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="9ab85-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="9ab85-104">Как правило `DataGridView` размер ячейки не изменяется в зависимости от их содержимого.</span><span class="sxs-lookup"><span data-stu-id="9ab85-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="9ab85-105">Вместо этого они обрезает все отображаемое значение, превышающее ячейки.</span><span class="sxs-lookup"><span data-stu-id="9ab85-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="9ab85-106">Содержимое можно отобразить в виде строки, в ячейке отображается во всплывающей подсказке.</span><span class="sxs-lookup"><span data-stu-id="9ab85-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="9ab85-107">По умолчанию пользователи могут перетаскивать строк, столбцов и разделители заголовка с помощью мыши для отображения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="9ab85-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="9ab85-108">Пользователей можно также дважды щелкнуть разделитель для автоматического изменения размера связанного внешнего строки, столбца или заголовка, в зависимости от его содержимого.</span><span class="sxs-lookup"><span data-stu-id="9ab85-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="9ab85-109">`DataGridView` Элемент управления предоставляет свойства, методы и события, которые позволяют настроить или отключить такое поведение, управляемое пользователем.</span><span class="sxs-lookup"><span data-stu-id="9ab85-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="9ab85-110">Кроме того можно программно изменить размер строк, столбцов и заголовков в соответствии с содержимым, или можно настроить их автоматическое изменение при изменении содержимого.</span><span class="sxs-lookup"><span data-stu-id="9ab85-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="9ab85-111">Можно также настроить столбцы для автоматического распределения ширины элемента управления в пропорций, указанных вами.</span><span class="sxs-lookup"><span data-stu-id="9ab85-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9ab85-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="9ab85-112">In This Section</span></span>  
 [<span data-ttu-id="9ab85-113">Изменение размеров управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ab85-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9ab85-114">Описание параметров для изменения размеров строк, столбцов и заголовков.</span><span class="sxs-lookup"><span data-stu-id="9ab85-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="9ab85-115">Также предоставляет подробные сведения о связанных изменения размера свойства и методы и описываются распространенные сценарии использования.</span><span class="sxs-lookup"><span data-stu-id="9ab85-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="9ab85-116">Установка режимов заполнения для столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ab85-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9ab85-117">Описание режима заполнения подробно, а также демонстрационный код, который можно использовать для экспериментов с режим заполнения столбцов и другие режимы.</span><span class="sxs-lookup"><span data-stu-id="9ab85-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="9ab85-118">Практическое руководство. Режимы изменения размеров элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ab85-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9ab85-119">Описываются способы настройки режима изменения размеров для общих целей.</span><span class="sxs-lookup"><span data-stu-id="9ab85-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="9ab85-120">Практическое руководство. Программное изменение размера ячеек элемента управления DataGridView в соответствии с размером отображаемых данных в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ab85-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="9ab85-121">Предоставляет демонстрационный код, который можно использовать для экспериментов с программного изменения размеров.</span><span class="sxs-lookup"><span data-stu-id="9ab85-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="9ab85-122">Практическое руководство. Автоматическое изменение размера ячеек при изменении содержимого в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ab85-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="9ab85-123">Предоставляет демонстрационный код, который можно использовать для экспериментов с режима автоматического изменения размеров.</span><span class="sxs-lookup"><span data-stu-id="9ab85-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9ab85-124">Ссылка</span><span class="sxs-lookup"><span data-stu-id="9ab85-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="9ab85-125">Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="9ab85-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab85-126">См. также</span><span class="sxs-lookup"><span data-stu-id="9ab85-126">See Also</span></span>  
 [<span data-ttu-id="9ab85-127">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="9ab85-127">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
