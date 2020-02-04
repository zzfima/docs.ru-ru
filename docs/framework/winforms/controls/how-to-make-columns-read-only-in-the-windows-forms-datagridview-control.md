---
title: Сделать столбцы доступны только для чтения в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
ms.openlocfilehash: 11d008d47ec5edb594d3d862c68ff3b9920e0e25
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736184"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Определение столбцов элемента управления DataGridView как доступных только для чтения в Windows Forms
Не все данные допускается изменять. В элементе управления <xref:System.Windows.Forms.DataGridView> значение свойства <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> столбца определяет, могут ли пользователи редактировать ячейки в этом столбце. Сведения о том, как сделать элемент управления доступным только для чтения, см. в разделе [инструкции. Предотвращение добавления и удаления строк в элементе управления Windows Forms DataGridView](prevent-row-addition-and-deletion-datagridview.md).  
  
 Эта задача поддерживается в Visual Studio.  Также см. [статью как сделать столбцы доступны только для чтения в элементе управления Windows Forms DataGridView с помощью конструктора](make-columns-read-only-in-the-datagrid-using-the-designer.md).  
  
### <a name="to-make-a-column-read-only-programmatically"></a>Программное определение столбца как доступного только для чтения  
  
- Установите свойство <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> в значение `true`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1` и столбцом с именем `CompanyName`;  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms](prevent-row-addition-and-deletion-datagridview.md)
