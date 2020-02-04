---
title: Получение выбранных ячеек, строк и столбцов в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: 0079c590ee6e4732523fd50be157bd58ec1bfb1b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743080"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Получение информации о выделенных пользователем ячейках, строках и столбцах элемента управления DataGridView в Windows Forms
Выбранные ячейки, строки или столбцы из элемента управления <xref:System.Windows.Forms.DataGridView> можно получить с помощью соответствующих свойств: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>и <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>. В следующих процедурах будут получены выбранные ячейки и отображены их индексы строк и столбцов в <xref:System.Windows.Forms.MessageBox>.  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a>Получение выбранных ячеек в элементе управления DataGridView  
  
- Используйте свойство <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>.  
  
    > [!NOTE]
    > Используйте метод <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>, чтобы не показывать потенциально большое количество ячеек.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a>Получение выбранных строк в элементе управления DataGridView  
  
- Используйте свойство <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>. Чтобы разрешить пользователям выбирать строки, необходимо задать для свойства <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> значение <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a>Получение выбранных столбцов в элементе управления DataGridView  
  
- Используйте свойство <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>. Чтобы разрешить пользователям выбирать столбцы, необходимо задать для свойства <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> значение <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- <xref:System.Windows.Forms.Button> элементы управления с именами `selectedCellsButton`, `selectedRowsButton`и `selectedColumnsButton`, каждый из которых имеет обработчики для присоединенного события <xref:System.Windows.Forms.Control.Click>.  
  
- элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> и <xref:System.Text?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Коллекции, описанные в этом разделе, не работают эффективно при выборе большого количества ячеек, строк или столбцов. Дополнительные сведения об использовании этих коллекций с большими объемами данных см. в разделе рекомендации [по масштабированию элемента управления Windows Forms DataGridView](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
