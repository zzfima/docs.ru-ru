---
title: Добавление всплывающих подсказок в отдельные ячейки элемента управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
ms.openlocfilehash: ac86db5fa27a95adb20888cd59b5e236941d9177
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732177"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a><span data-ttu-id="4fc0e-102">Практическое руководство. Определение текста всплывающих подсказок для отдельных ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4fc0e-102">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4fc0e-103">По умолчанию подсказки используются для отображения значений <xref:System.Windows.Forms.DataGridView>ных ячеек, которые слишком малы для отображения всего содержимого.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-103">By default, ToolTips are used to display the values of <xref:System.Windows.Forms.DataGridView> cells that are too small to show their entire contents.</span></span> <span data-ttu-id="4fc0e-104">Однако это поведение можно переопределить, чтобы задать текстовые значения ToolTip для отдельных ячеек.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-104">You can override this behavior, however, to set ToolTip-text values for individual cells.</span></span> <span data-ttu-id="4fc0e-105">Это полезно для вывода дополнительных сведений о ячейке или для предоставления пользователям альтернативного описания содержимого ячейки.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-105">This is useful to display to users additional information about a cell or to provide to users an alternate description of the cell contents.</span></span> <span data-ttu-id="4fc0e-106">Например, если имеется строка, отображающая значки состояния, может потребоваться написать текстовые объяснения с помощью всплывающих подсказок.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-106">For example, if you have a row that displays status icons, you may want to provide text explanations using ToolTips.</span></span>  
  
 <span data-ttu-id="4fc0e-107">Можно также отключить отображение подсказок на уровне ячейки, задав для свойства <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-107">You can also disable the display of cell-level ToolTips by setting the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
### <a name="to-add-a-tooltip-to-a-cell"></a><span data-ttu-id="4fc0e-108">Добавление подсказки в ячейку</span><span class="sxs-lookup"><span data-stu-id="4fc0e-108">To add a ToolTip to a cell</span></span>  
  
- <span data-ttu-id="4fc0e-109">Задайте свойство <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-109">Set the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4fc0e-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="4fc0e-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="4fc0e-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="4fc0e-111">This example requires:</span></span>  
  
- <span data-ttu-id="4fc0e-112">Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`, содержащий столбец с именем `Rating` для отображения строковых значений из одного до четырех символов звездочки ("\*").</span><span class="sxs-lookup"><span data-stu-id="4fc0e-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Rating` for displaying string values of one through four asterisk ("\*") symbols.</span></span> <span data-ttu-id="4fc0e-113">Событие <xref:System.Windows.Forms.DataGridView.CellFormatting> элемента управления должно быть связано с методом обработчика событий, показанным в примере.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-113">The <xref:System.Windows.Forms.DataGridView.CellFormatting> event of the control must be associated with the event handler method shown in the example.</span></span>  
  
- <span data-ttu-id="4fc0e-114">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-114">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4fc0e-115">Надежное программирование</span><span class="sxs-lookup"><span data-stu-id="4fc0e-115">Robust Programming</span></span>  
 <span data-ttu-id="4fc0e-116">При привязке элемента управления <xref:System.Windows.Forms.DataGridView> к внешнему источнику данных или предоставлении собственного источника данных путем реализации виртуального режима могут возникнуть проблемы с производительностью.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-116">When you bind the <xref:System.Windows.Forms.DataGridView> control to an external data source or provide your own data source by implementing virtual mode, you might encounter performance issues.</span></span> <span data-ttu-id="4fc0e-117">Чтобы избежать снижения производительности при работе с большими объемами данных, обрабатывайте <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> событие, а не устанавливая <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> свойства нескольких ячеек.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-117">To avoid a performance penalty when working with large amounts of data, handle the <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> event rather than setting the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property of multiple cells.</span></span> <span data-ttu-id="4fc0e-118">При обработке этого события получение значения ячейки <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> свойство вызывает событие и возвращает значение свойства <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType>, как указано в обработчике событий.</span><span class="sxs-lookup"><span data-stu-id="4fc0e-118">When you handle this event, getting the value of a cell <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property raises the event and returns the value of the <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> property as specified in the event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc0e-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="4fc0e-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4fc0e-120">Программирование с использованием ячеек, строк и столбцов в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4fc0e-120">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
