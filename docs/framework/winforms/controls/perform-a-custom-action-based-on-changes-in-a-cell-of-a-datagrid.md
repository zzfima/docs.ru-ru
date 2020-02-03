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
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a>Практическое руководство. Выполнение пользовательских действий в ответ на изменение состояния ячеек элемента управления DataGridView в Windows Forms
Элемент управления <xref:System.Windows.Forms.DataGridView> имеет ряд событий, которые можно использовать для обнаружения изменений в состоянии <xref:System.Windows.Forms.DataGridView>ных ячеек. Двумя наиболее часто используемыми являются события <xref:System.Windows.Forms.DataGridView.CellValueChanged> и <xref:System.Windows.Forms.DataGridView.CellStateChanged>.  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a>Обнаружение изменений в значениях ячеек DataGridView  
  
- Напишите обработчик для события <xref:System.Windows.Forms.DataGridView.CellValueChanged>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a>Обнаружение изменений в состояниях ячеек DataGridView  
  
- Напишите обработчик для события <xref:System.Windows.Forms.DataGridView.CellStateChanged>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`; Для C#обработчики событий должны быть подключены к соответствующим событиям.  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>
- [Программирование с использованием ячеек, строк и столбцов в элементе управления DataGridView в Windows Forms](programming-with-cells-rows-and-columns-in-the-datagrid.md)
- [Пример. Проверка данных элемента управления DataGridView в Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
