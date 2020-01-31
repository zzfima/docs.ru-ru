---
title: Задание режимов сортировки для столбцов в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 45ee1e7d82f826cddbd3492fed0f63e7a9c2cf1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742994"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="f60cc-102">Практическое руководство. Определение режимов сортировки для столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f60cc-102">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f60cc-103">В столбцах текстового поля элемента управления <xref:System.Windows.Forms.DataGridView> по умолчанию используется автоматическая сортировка, в то время как другие типы столбцов не сортируются автоматически.</span><span class="sxs-lookup"><span data-stu-id="f60cc-103">In the <xref:System.Windows.Forms.DataGridView> control, text box columns use automatic sorting by default, while other column types are not sorted automatically.</span></span> <span data-ttu-id="f60cc-104">Иногда потребуется переопределить эти значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f60cc-104">Sometimes you will want to override these defaults.</span></span> <span data-ttu-id="f60cc-105">Например, можно отображать изображения вместо текста, чисел или значений ячеек перечисления.</span><span class="sxs-lookup"><span data-stu-id="f60cc-105">For example, you can display images in place of text, numbers, or enumeration cell values.</span></span> <span data-ttu-id="f60cc-106">Хотя изображения не могут быть отсортированы, базовые значения, которые они представляют, можно сортировать.</span><span class="sxs-lookup"><span data-stu-id="f60cc-106">While the images cannot be sorted, the underlying values that they represent can be sorted.</span></span>  
  
 <span data-ttu-id="f60cc-107">В элементе управления <xref:System.Windows.Forms.DataGridView> значение свойства <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> столбца определяет его порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="f60cc-107">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property value of a column determines its sorting behavior.</span></span>  
  
 <span data-ttu-id="f60cc-108">В следующей процедуре показан столбец `Priority`, из которого [: Настройка форматирования данных в элементе управления Windows Forms DataGridView](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="f60cc-108">The following procedure shows the `Priority` column from [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="f60cc-109">Этот столбец является столбцом изображений и не может быть отсортирован по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f60cc-109">This column is an image column and is not sortable by default.</span></span> <span data-ttu-id="f60cc-110">Он содержит фактические значения ячеек, которые являются строками, однако их можно сортировать автоматически.</span><span class="sxs-lookup"><span data-stu-id="f60cc-110">It contains actual cell values that are strings, however, so it can be sorted automatically.</span></span>  
  
### <a name="to-set-the-sort-mode-for-a-column"></a><span data-ttu-id="f60cc-111">Задание режима сортировки для столбца</span><span class="sxs-lookup"><span data-stu-id="f60cc-111">To set the sort mode for a column</span></span>  
  
- <span data-ttu-id="f60cc-112">Задайте свойство <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f60cc-112">Set the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f60cc-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f60cc-113">Compiling the Code</span></span>  
 <span data-ttu-id="f60cc-114">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="f60cc-114">This example requires:</span></span>  
  
- <span data-ttu-id="f60cc-115">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`, содержащий столбец с именем `Priority`;</span><span class="sxs-lookup"><span data-stu-id="f60cc-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Priority`.</span></span>  
  
- <span data-ttu-id="f60cc-116">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f60cc-116">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f60cc-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="f60cc-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f60cc-118">Сортировка данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f60cc-118">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f60cc-119">Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f60cc-119">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f60cc-120">Практическое руководство. Настройка сортировки данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f60cc-120">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
