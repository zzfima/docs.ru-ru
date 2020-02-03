---
title: Получение выбранных ячеек, строк и столбцов в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: 0079c590ee6e4732523fd50be157bd58ec1bfb1b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743080"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="560c2-102">Практическое руководство. Получение информации о выделенных пользователем ячейках, строках и столбцах элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="560c2-102">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="560c2-103">Выбранные ячейки, строки или столбцы из элемента управления <xref:System.Windows.Forms.DataGridView> можно получить с помощью соответствующих свойств: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>и <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span><span class="sxs-lookup"><span data-stu-id="560c2-103">You can get the selected cells, rows, or columns from a <xref:System.Windows.Forms.DataGridView> control by using the corresponding properties: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, and <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span></span> <span data-ttu-id="560c2-104">В следующих процедурах будут получены выбранные ячейки и отображены их индексы строк и столбцов в <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="560c2-104">In the following procedures, you will get the selected cells and display their row and column indexes in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a><span data-ttu-id="560c2-105">Получение выбранных ячеек в элементе управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="560c2-105">To get the selected cells in a DataGridView control</span></span>  
  
- <span data-ttu-id="560c2-106">Используйте свойство <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>.</span><span class="sxs-lookup"><span data-stu-id="560c2-106">Use the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> property.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="560c2-107">Используйте метод <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>, чтобы не показывать потенциально большое количество ячеек.</span><span class="sxs-lookup"><span data-stu-id="560c2-107">Use the <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> method to avoid showing a potentially large number of cells.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a><span data-ttu-id="560c2-108">Получение выбранных строк в элементе управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="560c2-108">To get the selected rows in a DataGridView control</span></span>  
  
- <span data-ttu-id="560c2-109">Используйте свойство <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>.</span><span class="sxs-lookup"><span data-stu-id="560c2-109">Use the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> property.</span></span> <span data-ttu-id="560c2-110">Чтобы разрешить пользователям выбирать строки, необходимо задать для свойства <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> значение <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span><span class="sxs-lookup"><span data-stu-id="560c2-110">To enable users to select rows, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a><span data-ttu-id="560c2-111">Получение выбранных столбцов в элементе управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="560c2-111">To get the selected columns in a DataGridView control</span></span>  
  
- <span data-ttu-id="560c2-112">Используйте свойство <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span><span class="sxs-lookup"><span data-stu-id="560c2-112">Use the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> property.</span></span> <span data-ttu-id="560c2-113">Чтобы разрешить пользователям выбирать столбцы, необходимо задать для свойства <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> значение <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span><span class="sxs-lookup"><span data-stu-id="560c2-113">To enable users to select columns, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="560c2-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="560c2-114">Compiling the Code</span></span>  
 <span data-ttu-id="560c2-115">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="560c2-115">This example requires:</span></span>  
  
- <span data-ttu-id="560c2-116"><xref:System.Windows.Forms.Button> элементы управления с именами `selectedCellsButton`, `selectedRowsButton`и `selectedColumnsButton`, каждый из которых имеет обработчики для присоединенного события <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="560c2-116"><xref:System.Windows.Forms.Button> controls named `selectedCellsButton`, `selectedRowsButton`, and `selectedColumnsButton`, each with handlers for the <xref:System.Windows.Forms.Control.Click> event attached.</span></span>  
  
- <span data-ttu-id="560c2-117">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="560c2-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="560c2-118">ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> и <xref:System.Text?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="560c2-118">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Text?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="560c2-119">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="560c2-119">Robust Programming</span></span>  
 <span data-ttu-id="560c2-120">Коллекции, описанные в этом разделе, не работают эффективно при выборе большого количества ячеек, строк или столбцов.</span><span class="sxs-lookup"><span data-stu-id="560c2-120">The collections described in this topic do not perform efficiently when large numbers of cells, rows, or columns are selected.</span></span> <span data-ttu-id="560c2-121">Дополнительные сведения об использовании этих коллекций с большими объемами данных см. в разделе рекомендации [по масштабированию элемента управления Windows Forms DataGridView](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="560c2-121">For more information about using these collections with large amounts of data, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="560c2-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="560c2-122">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [<span data-ttu-id="560c2-123">Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="560c2-123">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
