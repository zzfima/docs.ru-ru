---
title: Практическое руководство. Получение выделенных ячеек, строк и столбцов в элементе управления DataGridView Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: ad6e704b64e3f25f456b98691dfe12c13f8440a2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713310"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="7b118-102">Практическое руководство. Получение выделенных ячеек, строк и столбцов в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7b118-102">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="7b118-103">Можно получить выделенных ячеек, строк или столбцов из <xref:System.Windows.Forms.DataGridView> элемента управления с помощью соответствующих свойств: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, и <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span><span class="sxs-lookup"><span data-stu-id="7b118-103">You can get the selected cells, rows, or columns from a <xref:System.Windows.Forms.DataGridView> control by using the corresponding properties: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, and <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span></span> <span data-ttu-id="7b118-104">В следующих процедурах будет получить выделенных ячеек и отображать их индексы строки и столбца в <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="7b118-104">In the following procedures, you will get the selected cells and display their row and column indexes in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a><span data-ttu-id="7b118-105">Для получения выделенных ячеек в элементе управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="7b118-105">To get the selected cells in a DataGridView control</span></span>  
  
-   <span data-ttu-id="7b118-106">Используйте свойство <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>.</span><span class="sxs-lookup"><span data-stu-id="7b118-106">Use the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7b118-107">Используйте <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> метод, чтобы не происходило отображение потенциально большое количество ячеек.</span><span class="sxs-lookup"><span data-stu-id="7b118-107">Use the <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> method to avoid showing a potentially large number of cells.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a><span data-ttu-id="7b118-108">Чтобы получить выделенные строки в элементе управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="7b118-108">To get the selected rows in a DataGridView control</span></span>  
  
-   <span data-ttu-id="7b118-109">Используйте свойство <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>.</span><span class="sxs-lookup"><span data-stu-id="7b118-109">Use the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> property.</span></span> <span data-ttu-id="7b118-110">Чтобы пользователи могли выбрать строки, необходимо задать <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> свойства <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span><span class="sxs-lookup"><span data-stu-id="7b118-110">To enable users to select rows, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a><span data-ttu-id="7b118-111">Чтобы получить из выбранных столбцов в элементе управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="7b118-111">To get the selected columns in a DataGridView control</span></span>  
  
-   <span data-ttu-id="7b118-112">Используйте свойство <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span><span class="sxs-lookup"><span data-stu-id="7b118-112">Use the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> property.</span></span> <span data-ttu-id="7b118-113">Чтобы пользователи могли выбрать столбцы, необходимо задать <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> свойства <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span><span class="sxs-lookup"><span data-stu-id="7b118-113">To enable users to select columns, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7b118-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="7b118-114">Compiling the Code</span></span>  
 <span data-ttu-id="7b118-115">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="7b118-115">This example requires:</span></span>  
  
-   <span data-ttu-id="7b118-116"><xref:System.Windows.Forms.Button> элементы управления с именем `selectedCellsButton`, `selectedRowsButton`, и `selectedColumnsButton`, каждый из которых обработчики для <xref:System.Windows.Forms.Control.Click> присоединенного события.</span><span class="sxs-lookup"><span data-stu-id="7b118-116"><xref:System.Windows.Forms.Button> controls named `selectedCellsButton`, `selectedRowsButton`, and `selectedColumnsButton`, each with handlers for the <xref:System.Windows.Forms.Control.Click> event attached.</span></span>  
  
-   <span data-ttu-id="7b118-117">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="7b118-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="7b118-118">ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> и <xref:System.Text?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7b118-118">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Text?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7b118-119">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="7b118-119">Robust Programming</span></span>  
 <span data-ttu-id="7b118-120">Коллекций, описанных в этом разделе не осуществляют эффективно, когда выбраны большое количество ячеек, строк или столбцов.</span><span class="sxs-lookup"><span data-stu-id="7b118-120">The collections described in this topic do not perform efficiently when large numbers of cells, rows, or columns are selected.</span></span> <span data-ttu-id="7b118-121">Дополнительные сведения об использовании этих коллекций с большими объемами данных, см. в разделе [масштабирование элемента управления DataGridView в Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="7b118-121">For more information about using these collections with large amounts of data, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b118-122">См. также</span><span class="sxs-lookup"><span data-stu-id="7b118-122">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [<span data-ttu-id="7b118-123">Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7b118-123">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
