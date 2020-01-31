---
title: Настройка сортировки в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], sorting
- data grids [Windows Forms], customizing sorting
ms.assetid: 92fb5c14-afab-4cf5-a97e-924fd9cb99f5
ms.openlocfilehash: 20f581b2df6fd172a0a1998aed60c56b0306f2eb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743178"
---
# <a name="how-to-customize-sorting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2a35c-102">Практическое руководство. Настройка сортировки данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a35c-102">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2a35c-103">Элемент управления <xref:System.Windows.Forms.DataGridView> обеспечивает автоматическую сортировку, но в определенных ситуациях может потребоваться настроить операции сортировки.</span><span class="sxs-lookup"><span data-stu-id="2a35c-103">The <xref:System.Windows.Forms.DataGridView> control provides automatic sorting but, depending on your needs, you might need to customize sort operations.</span></span> <span data-ttu-id="2a35c-104">Например, с помощью программной сортировки можно создать альтернативный пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="2a35c-104">For example, you can use programmatic sorting to create an alternate user interface (UI).</span></span> <span data-ttu-id="2a35c-105">Кроме того, можно обработать событие <xref:System.Windows.Forms.DataGridView.SortCompare> или вызвать перегрузку `Sort(IComparer)` метода <xref:System.Windows.Forms.DataGridView.Sort%2A> для обеспечения большей гибкости сортировки, например для сортировки нескольких столбцов.</span><span class="sxs-lookup"><span data-stu-id="2a35c-105">Alternatively, you can handle the <xref:System.Windows.Forms.DataGridView.SortCompare> event or call the `Sort(IComparer)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method for greater sorting flexibility, such as sorting multiple columns.</span></span>  
  
 <span data-ttu-id="2a35c-106">В приведенных ниже примерах кода демонстрируются эти три подхода к пользовательской сортировке.</span><span class="sxs-lookup"><span data-stu-id="2a35c-106">The following code examples demonstrate these three approaches to custom sorting.</span></span> <span data-ttu-id="2a35c-107">Дополнительные сведения см. в разделе [Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms](column-sort-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="2a35c-107">For more information, see [Column Sort Modes in the Windows Forms DataGridView Control](column-sort-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="programmatic-sorting"></a><span data-ttu-id="2a35c-108">Программная сортировка</span><span class="sxs-lookup"><span data-stu-id="2a35c-108">Programmatic Sorting</span></span>  
 <span data-ttu-id="2a35c-109">В примере кода ниже демонстрируется программная сортировка с использованием свойств <xref:System.Windows.Forms.DataGridView.SortOrder%2A> и <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> для определения направления сортировки и свойства <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> для ручной установки глифа сортировки.</span><span class="sxs-lookup"><span data-stu-id="2a35c-109">The following code example demonstrates a programmatic sort using the <xref:System.Windows.Forms.DataGridView.SortOrder%2A> and <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> properties to determine the direction of the sort, and the <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> property to manually set the sort glyph.</span></span> <span data-ttu-id="2a35c-110">Перегрузка `Sort(DataGridViewColumn,ListSortDirection)` метода <xref:System.Windows.Forms.DataGridView.Sort%2A> используется для сортировки данных только в одном столбце.</span><span class="sxs-lookup"><span data-stu-id="2a35c-110">The `Sort(DataGridViewColumn,ListSortDirection)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method is used to sort data only in a single column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-sortcompare-event"></a><span data-ttu-id="2a35c-111">Пользовательская сортировка с помощью события SortCompare</span><span class="sxs-lookup"><span data-stu-id="2a35c-111">Custom Sorting Using the SortCompare Event</span></span>  
 <span data-ttu-id="2a35c-112">В примере кода ниже демонстрируется пользовательская сортировка с использованием обработчика событий <xref:System.Windows.Forms.DataGridView.SortCompare>.</span><span class="sxs-lookup"><span data-stu-id="2a35c-112">The following code example demonstrates custom sorting using a <xref:System.Windows.Forms.DataGridView.SortCompare> event handler.</span></span> <span data-ttu-id="2a35c-113">Выбранный столбец <xref:System.Windows.Forms.DataGridViewColumn> сортируется, а при обнаружении в нем повторяющихся значений столбец ID используется для определения конечного порядка.</span><span class="sxs-lookup"><span data-stu-id="2a35c-113">The selected <xref:System.Windows.Forms.DataGridViewColumn> is sorted and, if there are duplicate values in the column, the ID column is used to determine the final order.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-icomparer-interface"></a><span data-ttu-id="2a35c-114">Пользовательская сортировка с помощью интерфейса IComparer</span><span class="sxs-lookup"><span data-stu-id="2a35c-114">Custom Sorting Using the IComparer Interface</span></span>  
 <span data-ttu-id="2a35c-115">В примере кода ниже демонстрируется пользовательская сортировка с помощью перегрузки `Sort(IComparer)` метода <xref:System.Windows.Forms.DataGridView.Sort%2A>, которая принимает реализацию интерфейса <xref:System.Collections.IComparer> для выполнения сортировки по нескольким столбцам.</span><span class="sxs-lookup"><span data-stu-id="2a35c-115">The following code example demonstrates custom sorting using the `Sort(IComparer)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method, which takes an implementation of the <xref:System.Collections.IComparer> interface to perform a multiple-column sort.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/VB/form1.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2a35c-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="2a35c-116">Compiling the Code</span></span>  
 <span data-ttu-id="2a35c-117">Для этих примеров требуются:</span><span class="sxs-lookup"><span data-stu-id="2a35c-117">These examples require:</span></span>  
  
- <span data-ttu-id="2a35c-118">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="2a35c-118">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a35c-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="2a35c-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="2a35c-120">Сортировка данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a35c-120">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="2a35c-121">Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a35c-121">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="2a35c-122">Практическое руководство. Определение режимов сортировки для столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a35c-122">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)
