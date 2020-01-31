---
title: Указание режима редактирования для элемента управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: c0318202a80f9a43f1b656201732ef032f430b5b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743763"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a>Практическое руководство. Определение режима редактирования для элемента управления DataGridView в Windows Forms
По умолчанию пользователи могут изменять содержимое ячейки текстового поля <xref:System.Windows.Forms.DataGridView>, вводя ее или нажав клавишу F2. Это приведет к помещению ячейки в режим редактирования, если выполняются все перечисленные ниже условия.  
  
- Базовый источник данных поддерживает редактирование.  
  
- Элемент управления <xref:System.Windows.Forms.DataGridView> включен.  
  
- Значение свойства <xref:System.Windows.Forms.DataGridView.EditMode%2A> не <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.  
  
- Для свойств `ReadOnly` ячейки, строки, столбца и элемента управления устанавливается значение `false`.  
  
 В режиме редактирования пользователь может изменить значение ячейки и нажать клавишу ВВОД для фиксации изменения или ESC для возврата ячейки к исходному значению.  
  
 Можно настроить <xref:System.Windows.Forms.DataGridView> элемент управления таким образом, чтобы ячейка перейдет в режим правки сразу после того, как она станет текущей ячейкой. Поведение клавиш ENTER и ESC в этом случае не меняется, но после фиксации или возврата ячейки остаются в режиме редактирования. Можно также настроить элемент управления таким образом, чтобы ячейки перейдет в режим редактирования только тогда, когда пользователи вводят в ячейку или только когда пользователь нажмет клавишу F2. Наконец, можно предотвратить переход ячеек в режим правки, кроме случая вызова метода <xref:System.Windows.Forms.DataGridView.BeginEdit%2A>.  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a>Изменение режима редактирования элемента управления DataGridView  
  
- Задайте для свойства <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> соответствующее перечисление <xref:System.Windows.Forms.DataGridViewEditMode>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
- ссылки на сборки <xref:System> и <xref:System.Windows.Forms>.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [Ввод данных с помощью элемента управления DataGridView в Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
