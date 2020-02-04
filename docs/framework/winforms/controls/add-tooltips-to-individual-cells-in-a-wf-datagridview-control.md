---
title: Добавление всплывающих подсказок в отдельные ячейки элемента управления DataGridView
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
ms.openlocfilehash: ac86db5fa27a95adb20888cd59b5e236941d9177
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732177"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a>Практическое руководство. Определение текста всплывающих подсказок для отдельных ячеек элемента управления DataGridView в Windows Forms
По умолчанию подсказки используются для отображения значений <xref:System.Windows.Forms.DataGridView>ных ячеек, которые слишком малы для отображения всего содержимого. Однако это поведение можно переопределить, чтобы задать текстовые значения ToolTip для отдельных ячеек. Это полезно для вывода дополнительных сведений о ячейке или для предоставления пользователям альтернативного описания содержимого ячейки. Например, если имеется строка, отображающая значки состояния, может потребоваться написать текстовые объяснения с помощью всплывающих подсказок.  
  
 Можно также отключить отображение подсказок на уровне ячейки, задав для свойства <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> значение `false`.  
  
### <a name="to-add-a-tooltip-to-a-cell"></a>Добавление подсказки в ячейку  
  
- Задайте свойство <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
- Для этого примера требуются:  
  
- Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`, содержащий столбец с именем `Rating` для отображения строковых значений из одного до четырех символов звездочки ("*"). Событие <xref:System.Windows.Forms.DataGridView.CellFormatting> элемента управления должно быть связано с методом обработчика событий, показанным в примере.  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При привязке элемента управления <xref:System.Windows.Forms.DataGridView> к внешнему источнику данных или предоставлении собственного источника данных путем реализации виртуального режима могут возникнуть проблемы с производительностью. Чтобы избежать снижения производительности при работе с большими объемами данных, обрабатывайте <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> событие, а не устанавливая <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> свойства нескольких ячеек. При обработке этого события получение значения ячейки <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> свойство вызывает событие и возвращает значение свойства <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType>, как указано в обработчике событий.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [Программирование с использованием ячеек, строк и столбцов в элементе управления DataGridView в Windows Forms](programming-with-cells-rows-and-columns-in-the-datagrid.md)
