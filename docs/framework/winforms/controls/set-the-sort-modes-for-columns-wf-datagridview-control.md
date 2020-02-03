---
title: Задание режимов сортировки для столбцов в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 45ee1e7d82f826cddbd3492fed0f63e7a9c2cf1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742994"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Определение режимов сортировки для столбцов элемента управления DataGridView в Windows Forms
В столбцах текстового поля элемента управления <xref:System.Windows.Forms.DataGridView> по умолчанию используется автоматическая сортировка, в то время как другие типы столбцов не сортируются автоматически. Иногда потребуется переопределить эти значения по умолчанию. Например, можно отображать изображения вместо текста, чисел или значений ячеек перечисления. Хотя изображения не могут быть отсортированы, базовые значения, которые они представляют, можно сортировать.  
  
 В элементе управления <xref:System.Windows.Forms.DataGridView> значение свойства <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> столбца определяет его порядок сортировки.  
  
 В следующей процедуре показан столбец `Priority`, из которого [: Настройка форматирования данных в элементе управления Windows Forms DataGridView](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md). Этот столбец является столбцом изображений и не может быть отсортирован по умолчанию. Он содержит фактические значения ячеек, которые являются строками, однако их можно сортировать автоматически.  
  
### <a name="to-set-the-sort-mode-for-a-column"></a>Задание режима сортировки для столбца  
  
- Задайте свойство <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`, содержащий столбец с именем `Priority`;  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- [Сортировка данных в элементе управления DataGridView в Windows Forms](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Настройка сортировки данных элемента управления DataGridView в Windows Forms](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
