---
title: Практическое руководство. Получение информации о выделенных пользователем ячейках, строках и столбцах элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: 25b3ed50081add77b9f522ca8e597f2b3306cb2e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960519"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Получение информации о выделенных пользователем ячейках, строках и столбцах элемента управления DataGridView в Windows Forms
Выбранные ячейки, <xref:System.Windows.Forms.DataGridView> строки или столбцы из элемента управления можно получить с помощью соответствующих свойств: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>и <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>. В следующих процедурах будут получены выбранные ячейки и отображены их индексы строк и столбцов в <xref:System.Windows.Forms.MessageBox>.  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a>Получение выбранных ячеек в элементе управления DataGridView  
  
- Используйте свойство <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>.  
  
    > [!NOTE]
    > <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> Используйте метод, чтобы избежать отображения потенциального большого количества ячеек.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a>Получение выбранных строк в элементе управления DataGridView  
  
- Используйте свойство <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>. Чтобы разрешить пользователям выбирать строки, необходимо задать <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> для <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> свойства значение или <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a>Получение выбранных столбцов в элементе управления DataGridView  
  
- Используйте свойство <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>. Чтобы разрешить пользователям выбирать столбцы, необходимо задать <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> для <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> свойства значение или <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- <xref:System.Windows.Forms.Button>элементы управления `selectedCellsButton`с `selectedRowsButton`именами, `selectedColumnsButton`и, каждый из <xref:System.Windows.Forms.Control.Click> которых имеет обработчики для присоединенного события.  
  
- элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> и <xref:System.Text?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Коллекции, описанные в этом разделе, не работают эффективно при выборе большого количества ячеек, строк или столбцов. Дополнительные сведения об использовании этих коллекций с большими объемами данных см. в разделе рекомендации [по масштабированию элемента управления Windows Forms DataGridView](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
