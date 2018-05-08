---
title: Практическое руководство. Определение режима редактирования для элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: 5117dfe2e017cf4af1d352fdbf23c6599c0e56a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a>Практическое руководство. Определение режима редактирования для элемента управления DataGridView в Windows Forms
По умолчанию пользователи могут редактировать содержимое текущего <xref:System.Windows.Forms.DataGridView> ячейки текстового поля, введя в него или нажав клавишу F2. Ячейка переключается в режим редактирования при выполнении всех следующих условий:  
  
-   Базовый источник данных поддерживает редактирование.  
  
-   <xref:System.Windows.Forms.DataGridView> Элемент управления включен.  
  
-   <xref:System.Windows.Forms.DataGridView.EditMode%2A> Значение свойства не является <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.  
  
-   `ReadOnly` Свойства ячеек, строк, столбцов и элемента управления имеют значение `false`.  
  
 В режиме редактирования пользователь может изменить значение ячейки и нажмите клавишу ВВОД, чтобы внести изменения или ESC, чтобы вернуть исходное значение ячейки.  
  
 Можно настроить <xref:System.Windows.Forms.DataGridView> управления ячейку в режим редактирования, как только она становится текущей ячейкой. В этом случае поведение клавиш ввод и ESC не изменяется, но ячейка остается в режиме редактирования после подтверждения или возврата значения. Можно также настроить элемент управления, чтобы ячейки режим редактирования только в том случае, когда пользователи вводят в ячейке или только при нажатии клавиши F2. Наконец, можно предотвратить ячеек в режим редактирования, за исключением того, при вызове <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> метода.  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a>Чтобы изменить режим редактирования элемента управления DataGridView  
  
-   Задать <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> свойство к соответствующему <xref:System.Windows.Forms.DataGridViewEditMode> перечисления.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
-   ссылки на сборки <xref:System> и <xref:System.Windows.Forms>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>  
 [Ввод данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)
