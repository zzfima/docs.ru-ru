---
title: Практическое руководство. Определение текста всплывающих подсказок для отдельных ячеек элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
ms.openlocfilehash: 50eb02a8f6e9a987fad074c173ab6711fa91143f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527704"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a>Практическое руководство. Определение текста всплывающих подсказок для отдельных ячеек элемента управления DataGridView в Windows Forms
По умолчанию всплывающие подсказки используются для отображения значений <xref:System.Windows.Forms.DataGridView> ячеек, которые слишком малы, чтобы отображать их полное содержимое. Это поведение можно переопределить тем не менее, чтобы задать значения текст всплывающей подсказки для отдельных ячеек. Это полезно для отображения дополнительных сведений пользователям о ячейке, или для предоставления пользователям дополнительного описания о содержимом ячейки. Например при наличии строку, отображающую значки состояния может потребоваться предоставить текстовых пояснений по использованию всплывающих подсказок.  
  
 Можно также отключить отображение всплывающих подсказок на уровне ячейки, установив <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> свойства `false`.  
  
### <a name="to-add-a-tooltip-to-a-cell"></a>Добавление всплывающей подсказки в ячейку  
  
-   Задайте свойство <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Для этого примера требуются:  
  
-   A <xref:System.Windows.Forms.DataGridView> управления с именем `dataGridView1` , содержащий столбец с именем `Rating` для отображения строковых значений от одного до четырех звездочки («*») символов. <xref:System.Windows.Forms.DataGridView.CellFormatting> События элемента управления должен быть связан с показано в примере метода обработчика событий.  
  
-   ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При привязке <xref:System.Windows.Forms.DataGridView> управления к внешнему источнику данных или предоставить свой собственный источник данных, реализация виртуального режима, могут возникнуть проблемы производительности. Чтобы избежать снижения производительности при работе с большими объемами данных, необходимо обработать событие <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> событий, а не <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> свойство нескольких ячеек. При обработке этого события, получение значения ячейки <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> свойство вызывает событие и возвращает значение <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> свойства в виде событий задан обработчик.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>  
 [Программирование с использованием ячеек, строк и столбцов в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)
