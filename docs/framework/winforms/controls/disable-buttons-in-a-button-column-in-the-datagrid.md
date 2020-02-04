---
title: Отключение кнопок в столбце кнопки в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], disabling buttons
- buttons [Windows Forms], disabling in button columns
- DataGridView control [Windows Forms], disabling button cells
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
ms.openlocfilehash: 691781a43005d66e13029ab8110eb7f9daacc35f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745949"
---
# <a name="how-to-disable-buttons-in-a-button-column-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Отключение кнопок в кнопочном столбе элемента управления DataGridView в Windows Forms
Элемент управления <xref:System.Windows.Forms.DataGridView> включает класс <xref:System.Windows.Forms.DataGridViewButtonCell> для отображения ячеек с пользовательским интерфейсом, похожим на кнопку. Однако элемент управления <xref:System.Windows.Forms.DataGridViewButtonCell> не дает возможности отключить показ кнопки в ячейке.  
  
 В примере кода ниже показано, как настроить класс <xref:System.Windows.Forms.DataGridViewButtonCell> для отображения кнопок, которые выглядят как отключенные. В этом примере определен новый тип ячейки, `DataGridViewDisableButtonCell`, производный от <xref:System.Windows.Forms.DataGridViewButtonCell>. Этот тип предоставляет новое свойство `Enabled`, которому можно присвоить значение `false` для отрисовки отключенной кнопки в ячейке. В этом примере также определен новый тип столбца, `DataGridViewDisableButtonColumn`, в котором отображаются объекты `DataGridViewDisableButtonCell`. Для демонстрации этих новых типов ячеек и столбцов текущее значение каждого объекта <xref:System.Windows.Forms.DataGridViewCheckBoxCell> в родительском элементе <xref:System.Windows.Forms.DataGridView> определяет значение свойства `Enabled` элемента `DataGridViewDisableButtonCell` в одной и той же строке: `true` или `false`.  
  
> [!NOTE]
> При наследовании от класса <xref:System.Windows.Forms.DataGridViewCell> или <xref:System.Windows.Forms.DataGridViewColumn> и добавлении новых свойств к производному классу необходимо переопределить метод `Clone`, чтобы скопировать новые свойства во время операций копирования. Кроме того, необходимо вызвать метод `Clone` базового класса, чтобы свойства базового класса скопировались в новую ячейку или столбец.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- ссылки на сборки System, System.Drawing, System.Windows.Forms и System.Windows.Forms.VisualStyles.  
  
## <a name="see-also"></a>См. также раздел

- [Настройка элементов управления DataGridView в Windows Forms](customizing-the-windows-forms-datagridview-control.md)
- [Архитектура элементов управления DataGridView](datagridview-control-architecture-windows-forms.md)
- [Типы столбцов элемента управления DataGridView в Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
