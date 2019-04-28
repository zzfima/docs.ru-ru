---
title: Практическое руководство. Определение режимов сортировки для столбцов элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 4894de00a323f70ca244ea877101a5af1cbb37e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012195"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="93705-102">Практическое руководство. Определение режимов сортировки для столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="93705-102">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="93705-103">В <xref:System.Windows.Forms.DataGridView> элемент управления, поле текстовых столбцов использовать автоматическую сортировку по умолчанию, а другие типы столбцов не имеют автоматической сортировки.</span><span class="sxs-lookup"><span data-stu-id="93705-103">In the <xref:System.Windows.Forms.DataGridView> control, text box columns use automatic sorting by default, while other column types are not sorted automatically.</span></span> <span data-ttu-id="93705-104">Иногда требуется переопределить эти значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="93705-104">Sometimes you will want to override these defaults.</span></span> <span data-ttu-id="93705-105">Например можно отобразить изображения вместо текста, чисел и значений перечисления ячейки.</span><span class="sxs-lookup"><span data-stu-id="93705-105">For example, you can display images in place of text, numbers, or enumeration cell values.</span></span> <span data-ttu-id="93705-106">Хотя нельзя отсортировать изображения, можно сортировать значения, которые они представляют.</span><span class="sxs-lookup"><span data-stu-id="93705-106">While the images cannot be sorted, the underlying values that they represent can be sorted.</span></span>  
  
 <span data-ttu-id="93705-107">В <xref:System.Windows.Forms.DataGridView> элемента управления, <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> значение свойства столбца определяет поведение сортировки.</span><span class="sxs-lookup"><span data-stu-id="93705-107">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property value of a column determines its sorting behavior.</span></span>  
  
 <span data-ttu-id="93705-108">В следующей процедуре показан `Priority` столбец из [как: Настройка форматирования данных в элементе управления DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="93705-108">The following procedure shows the `Priority` column from [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="93705-109">Этот столбец является столбцом образа и не поддерживает сортировку по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="93705-109">This column is an image column and is not sortable by default.</span></span> <span data-ttu-id="93705-110">Он содержит фактические значения ячеек, которые представляют собой строки, однако, поэтому его можно сортировать по алфавиту.</span><span class="sxs-lookup"><span data-stu-id="93705-110">It contains actual cell values that are strings, however, so it can be sorted automatically.</span></span>  
  
### <a name="to-set-the-sort-mode-for-a-column"></a><span data-ttu-id="93705-111">Чтобы задать режим сортировки для столбца</span><span class="sxs-lookup"><span data-stu-id="93705-111">To set the sort mode for a column</span></span>  
  
- <span data-ttu-id="93705-112">Задайте свойство <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="93705-112">Set the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="93705-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="93705-113">Compiling the Code</span></span>  
 <span data-ttu-id="93705-114">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="93705-114">This example requires:</span></span>  
  
- <span data-ttu-id="93705-115">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`, содержащий столбец с именем `Priority`;</span><span class="sxs-lookup"><span data-stu-id="93705-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Priority`.</span></span>  
  
- <span data-ttu-id="93705-116">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="93705-116">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93705-117">См. также</span><span class="sxs-lookup"><span data-stu-id="93705-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="93705-118">Сортировка данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="93705-118">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="93705-119">Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="93705-119">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="93705-120">Практическое руководство. Настройка сортировки в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="93705-120">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
