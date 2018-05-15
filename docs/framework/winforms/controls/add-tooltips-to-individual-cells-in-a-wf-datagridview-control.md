---
title: Практическое руководство. Определение текста всплывающих подсказок для отдельных ячеек элемента управления DataGridView в Windows Forms
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
ms.openlocfilehash: 50eb02a8f6e9a987fad074c173ab6711fa91143f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a><span data-ttu-id="6f454-102">Практическое руководство. Определение текста всплывающих подсказок для отдельных ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f454-102">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="6f454-103">По умолчанию всплывающие подсказки используются для отображения значений <xref:System.Windows.Forms.DataGridView> ячеек, которые слишком малы, чтобы отображать их полное содержимое.</span><span class="sxs-lookup"><span data-stu-id="6f454-103">By default, ToolTips are used to display the values of <xref:System.Windows.Forms.DataGridView> cells that are too small to show their entire contents.</span></span> <span data-ttu-id="6f454-104">Это поведение можно переопределить тем не менее, чтобы задать значения текст всплывающей подсказки для отдельных ячеек.</span><span class="sxs-lookup"><span data-stu-id="6f454-104">You can override this behavior, however, to set ToolTip-text values for individual cells.</span></span> <span data-ttu-id="6f454-105">Это полезно для отображения дополнительных сведений пользователям о ячейке, или для предоставления пользователям дополнительного описания о содержимом ячейки.</span><span class="sxs-lookup"><span data-stu-id="6f454-105">This is useful to display to users additional information about a cell or to provide to users an alternate description of the cell contents.</span></span> <span data-ttu-id="6f454-106">Например при наличии строку, отображающую значки состояния может потребоваться предоставить текстовых пояснений по использованию всплывающих подсказок.</span><span class="sxs-lookup"><span data-stu-id="6f454-106">For example, if you have a row that displays status icons, you may want to provide text explanations using ToolTips.</span></span>  
  
 <span data-ttu-id="6f454-107">Можно также отключить отображение всплывающих подсказок на уровне ячейки, установив <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="6f454-107">You can also disable the display of cell-level ToolTips by setting the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
### <a name="to-add-a-tooltip-to-a-cell"></a><span data-ttu-id="6f454-108">Добавление всплывающей подсказки в ячейку</span><span class="sxs-lookup"><span data-stu-id="6f454-108">To add a ToolTip to a cell</span></span>  
  
-   <span data-ttu-id="6f454-109">Задайте свойство <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6f454-109">Set the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6f454-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="6f454-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="6f454-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="6f454-111">This example requires:</span></span>  
  
-   <span data-ttu-id="6f454-112">A <xref:System.Windows.Forms.DataGridView> управления с именем `dataGridView1` , содержащий столбец с именем `Rating` для отображения строковых значений от одного до четырех звездочки («\*») символов.</span><span class="sxs-lookup"><span data-stu-id="6f454-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Rating` for displaying string values of one through four asterisk ("\*") symbols.</span></span> <span data-ttu-id="6f454-113"><xref:System.Windows.Forms.DataGridView.CellFormatting> События элемента управления должен быть связан с показано в примере метода обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="6f454-113">The <xref:System.Windows.Forms.DataGridView.CellFormatting> event of the control must be associated with the event handler method shown in the example.</span></span>  
  
-   <span data-ttu-id="6f454-114">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6f454-114">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6f454-115">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="6f454-115">Robust Programming</span></span>  
 <span data-ttu-id="6f454-116">При привязке <xref:System.Windows.Forms.DataGridView> управления к внешнему источнику данных или предоставить свой собственный источник данных, реализация виртуального режима, могут возникнуть проблемы производительности.</span><span class="sxs-lookup"><span data-stu-id="6f454-116">When you bind the <xref:System.Windows.Forms.DataGridView> control to an external data source or provide your own data source by implementing virtual mode, you might encounter performance issues.</span></span> <span data-ttu-id="6f454-117">Чтобы избежать снижения производительности при работе с большими объемами данных, необходимо обработать событие <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> событий, а не <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> свойство нескольких ячеек.</span><span class="sxs-lookup"><span data-stu-id="6f454-117">To avoid a performance penalty when working with large amounts of data, handle the <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> event rather than setting the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property of multiple cells.</span></span> <span data-ttu-id="6f454-118">При обработке этого события, получение значения ячейки <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> свойство вызывает событие и возвращает значение <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> свойства в виде событий задан обработчик.</span><span class="sxs-lookup"><span data-stu-id="6f454-118">When you handle this event, getting the value of a cell <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property raises the event and returns the value of the <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> property as specified in the event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f454-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6f454-119">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="6f454-120">Программирование с использованием ячеек, строк и столбцов в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f454-120">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)
