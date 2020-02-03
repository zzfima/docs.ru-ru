---
title: Настройка внешнего вида ячеек в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 754932427a365a7b032c1ac9627d3237d1f7d0c6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744052"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2c751-102">Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c751-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2c751-103">Можно настроить внешний вид любой ячейки, обрабатывая событие <xref:System.Windows.Forms.DataGridView.CellPainting> элемента управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="2c751-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="2c751-104"><xref:System.Drawing.Graphics> <xref:System.Windows.Forms.DataGridView> элемента управления можно извлечь из свойства <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="2c751-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="2c751-105">С помощью этого <xref:System.Drawing.Graphics>можно повлиять на внешний вид всего элемента управления <xref:System.Windows.Forms.DataGridView>, но обычно требуется повлиять только на внешний вид ячейки, нарисованной в данный момент.</span><span class="sxs-lookup"><span data-stu-id="2c751-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="2c751-106">Свойство <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> позволяет ограничить операции рисования до ячейки, нарисованной в данный момент.</span><span class="sxs-lookup"><span data-stu-id="2c751-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="2c751-107">В следующем примере кода все ячейки в `ContactName` столбце будут перерисовываться с помощью цветовой схемы элемента управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="2c751-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="2c751-108">Текстовое содержимое каждой ячейки рисуется в <xref:System.Drawing.Color.Crimson%2A>, а прямоугольник отступа выводится в том же цвете, что и свойство <xref:System.Windows.Forms.DataGridView.GridColor%2A> элемента управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="2c751-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c751-109">Пример</span><span class="sxs-lookup"><span data-stu-id="2c751-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2c751-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="2c751-110">Compiling the Code</span></span>  
 <span data-ttu-id="2c751-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="2c751-111">This example requires:</span></span>  
  
- <span data-ttu-id="2c751-112">Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1` со столбцом `ContactName`, например, в таблице Customers в образце базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="2c751-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
- <span data-ttu-id="2c751-113">ссылки на сборки System, System.Windows.Forms и System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="2c751-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c751-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2c751-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [<span data-ttu-id="2c751-115">Настройка элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c751-115">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
