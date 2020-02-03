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
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms
Можно настроить внешний вид любой ячейки, обрабатывая событие <xref:System.Windows.Forms.DataGridView.CellPainting> элемента управления <xref:System.Windows.Forms.DataGridView>. <xref:System.Drawing.Graphics> <xref:System.Windows.Forms.DataGridView> элемента управления можно извлечь из свойства <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>. С помощью этого <xref:System.Drawing.Graphics>можно повлиять на внешний вид всего элемента управления <xref:System.Windows.Forms.DataGridView>, но обычно требуется повлиять только на внешний вид ячейки, нарисованной в данный момент. Свойство <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> позволяет ограничить операции рисования до ячейки, нарисованной в данный момент.  
  
 В следующем примере кода все ячейки в `ContactName` столбце будут перерисовываться с помощью цветовой схемы элемента управления <xref:System.Windows.Forms.DataGridView>. Текстовое содержимое каждой ячейки рисуется в <xref:System.Drawing.Color.Crimson%2A>, а прямоугольник отступа выводится в том же цвете, что и свойство <xref:System.Windows.Forms.DataGridView.GridColor%2A> элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1` со столбцом `ContactName`, например, в таблице Customers в образце базы данных Northwind.  
  
- ссылки на сборки System, System.Windows.Forms и System.Drawing.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [Настройка элементов управления DataGridView в Windows Forms](customizing-the-windows-forms-datagridview-control.md)
