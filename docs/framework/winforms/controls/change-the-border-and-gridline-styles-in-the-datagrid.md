---
title: Практическое руководство. Изменение внешнего вида границ и линий сетки элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gridlines [Windows Forms], changing styles
- data grids [Windows Forms], changing gridline styles
- DataGridView control [Windows Forms], border styles
- data grids [Windows Forms], changing border styles
- DataGridView control [Windows Forms], gridline styles
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
ms.openlocfilehash: ebeca5f933eac4da2bf3d4f300866fd2ff52b32a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917674"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Изменение внешнего вида границ и линий сетки элемента управления DataGridView в Windows Forms
С помощью <xref:System.Windows.Forms.DataGridView> элемента управления можно настроить внешний вид границ и линий сетки элемента управления, чтобы улучшить взаимодействие с пользователем. В дополнение к стилям границ для ячеек внутри элемента управления можно изменить цвет сетки и стиль границы элемента управления. Можно также применить различные стили границ ячеек для обычных ячеек, ячеек заголовка строки и ячеек заголовков столбцов.  
  
> [!NOTE]
> Цвет линий сетки используется только с <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single> <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> значениями <xref:System.Windows.Forms.DataGridViewCellBorderStyle> перечисления <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal> <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> ,, и значения перечисления. <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> Другие значения этих перечислений используют цвета, заданные операционной системой. Кроме того, если стили оформления включены в Windows XP и семействе Windows Server 2003 с помощью <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> метода <xref:System.Windows.Forms.DataGridView.GridColor%2A> , значение свойства не используется.  
  
### <a name="to-change-the-gridline-color-programmatically"></a>Изменение цвета линий сетки программными средствами  
  
- Задайте свойство <xref:System.Windows.Forms.DataGridView.GridColor%2A>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a>Изменение стиля границы всего элемента управления DataGridView программным способом  
  
- Присвойте свойству <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> одно из значений перечисления <xref:System.Windows.Forms.BorderStyle>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a>Изменение стилей границ для ячеек DataGridView программным способом  
  
- Задайте свойства <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>и <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> .  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> и <xref:System.Drawing?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.BorderStyle>
- <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellBorderStyle>
- <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>
- [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
