---
title: Практическое руководство. Выполнение пользовательских действий на основе изменений в ячейке элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: ad1c60c34fc5461de21e2ad5d4d02f5b2abd6dfd
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705588"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a><span data-ttu-id="390d1-102">Практическое руководство. Выполнение пользовательских действий на основе изменений в ячейке элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="390d1-102">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="390d1-103"><xref:System.Windows.Forms.DataGridView> Элемент управления имеет ряд событий, которые можно использовать для обнаружения изменений в состоянии <xref:System.Windows.Forms.DataGridView> ячеек.</span><span class="sxs-lookup"><span data-stu-id="390d1-103">The <xref:System.Windows.Forms.DataGridView> control has a number of events you can use to detect changes in the state of <xref:System.Windows.Forms.DataGridView> cells.</span></span> <span data-ttu-id="390d1-104">Два из наиболее часто используемым <xref:System.Windows.Forms.DataGridView.CellValueChanged> и <xref:System.Windows.Forms.DataGridView.CellStateChanged> события.</span><span class="sxs-lookup"><span data-stu-id="390d1-104">Two of the most commonly used are the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a><span data-ttu-id="390d1-105">Для обнаружения изменений значений ячеек элемента управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="390d1-105">To detect changes in the values of DataGridView cells</span></span>  
  
-   <span data-ttu-id="390d1-106">Создайте обработчик для <xref:System.Windows.Forms.DataGridView.CellValueChanged> событий.</span><span class="sxs-lookup"><span data-stu-id="390d1-106">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellValueChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a><span data-ttu-id="390d1-107">Для обнаружения изменений в состояния ячеек элемента управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="390d1-107">To detect changes in the states of DataGridView cells</span></span>  
  
-   <span data-ttu-id="390d1-108">Создайте обработчик для <xref:System.Windows.Forms.DataGridView.CellStateChanged> событий.</span><span class="sxs-lookup"><span data-stu-id="390d1-108">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellStateChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="390d1-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="390d1-109">Compiling the Code</span></span>  
 <span data-ttu-id="390d1-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="390d1-110">This example requires:</span></span>  
  
-   <span data-ttu-id="390d1-111">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="390d1-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span> <span data-ttu-id="390d1-112">Для C#, обработчики событий должны быть подключены к соответствующие события.</span><span class="sxs-lookup"><span data-stu-id="390d1-112">For C#, the event handlers must be connected to the corresponding events.</span></span>  
  
-   <span data-ttu-id="390d1-113">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="390d1-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="390d1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="390d1-114">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>
- [<span data-ttu-id="390d1-115">Программирование с использованием ячеек, строк и столбцов в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="390d1-115">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
- [<span data-ttu-id="390d1-116">Пошаговое руководство: Проверка данных в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="390d1-116">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
