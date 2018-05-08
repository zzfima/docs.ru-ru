---
title: Практическое руководство. Разрешение переупорядочивания столбцов элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], reordering columns
- columns [Windows Forms], reordering
ms.assetid: cc20eae3-e4db-493f-95ce-a4215e29472a
ms.openlocfilehash: fbcafae2cb4e4cc320c31794269355d6312b95b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Разрешение переупорядочивания столбцов элемента управления DataGridView в Windows Forms
При разрешении изменения порядка столбцов в элементе управления <xref:System.Windows.Forms.DataGridView> пользователи могут переместить столбец в новое местоположение, перетащив заголовок столбца с помощью мыши. В элементе управления <xref:System.Windows.Forms.DataGridView> значение свойства <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> определяет, могут ли пользователи перемещать столбцы.  
  
 Эта задача поддерживается в Visual Studio.  См. также [как: Разрешить изменение порядка столбцов в Windows Forms управления DataGridView с помощью конструктора](http://msdn.microsoft.com/library/8xwtyc86\(v=vs.110\))  
  
### <a name="to-enable-column-reordering-programmatically"></a>Разрешение изменения порядка столбцов программным путем  
  
-   Задайте для свойства <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> значение `true`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#060)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#060)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
-   ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>  
 [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [Практическое руководство. Замораживание столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)
