---
title: Выполнение настраиваемого действия на основе изменений в ячейке элемента управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: a809134b0a79bc9685c5b84acce58b4c61b5c526
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744283"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a><span data-ttu-id="94a41-102">Практическое руководство. Выполнение пользовательских действий в ответ на изменение состояния ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="94a41-102">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="94a41-103">Элемент управления <xref:System.Windows.Forms.DataGridView> имеет ряд событий, которые можно использовать для обнаружения изменений в состоянии <xref:System.Windows.Forms.DataGridView>ных ячеек.</span><span class="sxs-lookup"><span data-stu-id="94a41-103">The <xref:System.Windows.Forms.DataGridView> control has a number of events you can use to detect changes in the state of <xref:System.Windows.Forms.DataGridView> cells.</span></span> <span data-ttu-id="94a41-104">Двумя наиболее часто используемыми являются события <xref:System.Windows.Forms.DataGridView.CellValueChanged> и <xref:System.Windows.Forms.DataGridView.CellStateChanged>.</span><span class="sxs-lookup"><span data-stu-id="94a41-104">Two of the most commonly used are the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a><span data-ttu-id="94a41-105">Обнаружение изменений в значениях ячеек DataGridView</span><span class="sxs-lookup"><span data-stu-id="94a41-105">To detect changes in the values of DataGridView cells</span></span>  
  
- <span data-ttu-id="94a41-106">Напишите обработчик для события <xref:System.Windows.Forms.DataGridView.CellValueChanged>.</span><span class="sxs-lookup"><span data-stu-id="94a41-106">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellValueChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a><span data-ttu-id="94a41-107">Обнаружение изменений в состояниях ячеек DataGridView</span><span class="sxs-lookup"><span data-stu-id="94a41-107">To detect changes in the states of DataGridView cells</span></span>  
  
- <span data-ttu-id="94a41-108">Напишите обработчик для события <xref:System.Windows.Forms.DataGridView.CellStateChanged>.</span><span class="sxs-lookup"><span data-stu-id="94a41-108">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellStateChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="94a41-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="94a41-109">Compiling the Code</span></span>  
 <span data-ttu-id="94a41-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="94a41-110">This example requires:</span></span>  
  
- <span data-ttu-id="94a41-111">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="94a41-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span> <span data-ttu-id="94a41-112">Для C#обработчики событий должны быть подключены к соответствующим событиям.</span><span class="sxs-lookup"><span data-stu-id="94a41-112">For C#, the event handlers must be connected to the corresponding events.</span></span>  
  
- <span data-ttu-id="94a41-113">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="94a41-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94a41-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="94a41-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>
- [<span data-ttu-id="94a41-115">Программирование с использованием ячеек, строк и столбцов в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="94a41-115">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
- [<span data-ttu-id="94a41-116">Пример. Проверка данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="94a41-116">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
