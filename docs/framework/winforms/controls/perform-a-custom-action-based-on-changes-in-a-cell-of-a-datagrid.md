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
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a>Практическое руководство. Выполнение пользовательских действий на основе изменений в ячейке элемента управления DataGridView в Windows Forms
<xref:System.Windows.Forms.DataGridView> Элемент управления имеет ряд событий, которые можно использовать для обнаружения изменений в состоянии <xref:System.Windows.Forms.DataGridView> ячеек. Два из наиболее часто используемым <xref:System.Windows.Forms.DataGridView.CellValueChanged> и <xref:System.Windows.Forms.DataGridView.CellStateChanged> события.  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a>Для обнаружения изменений значений ячеек элемента управления DataGridView  
  
-   Создайте обработчик для <xref:System.Windows.Forms.DataGridView.CellValueChanged> событий.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a>Для обнаружения изменений в состояния ячеек элемента управления DataGridView  
  
-   Создайте обработчик для <xref:System.Windows.Forms.DataGridView.CellStateChanged> событий.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`; Для C#, обработчики событий должны быть подключены к соответствующие события.  
  
-   ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>
- [Программирование с использованием ячеек, строк и столбцов в элементе управления DataGridView в Windows Forms](programming-with-cells-rows-and-columns-in-the-datagrid.md)
- [Пошаговое руководство: Проверка данных в элементе управления DataGridView Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
