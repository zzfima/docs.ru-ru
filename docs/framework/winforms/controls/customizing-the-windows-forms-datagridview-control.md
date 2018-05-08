---
title: Настройка элементов управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 92bbace4d0869aca67025f1e4ac8c451fe073219
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="customizing-the-windows-forms-datagridview-control"></a>Настройка элементов управления DataGridView в Windows Forms
`DataGridView` Управления предоставляет несколько свойств, которые можно использовать для настройки внешнего вида и базовое поведение ячеек, строк и столбцов (Вид). При наличии особых требований, выходящих за рамки возможностей <xref:System.Windows.Forms.DataGridViewCellStyle> класса, однако также можно реализовать пользовательское отображение для элемента управления или расширить его возможности, создав пользовательские ячейки, строки и столбцы.  
  
 Для рисования ячейки и строки самостоятельно, можно обработать различные `DataGridView` события рисования. Чтобы изменить существующие функциональные возможности или предоставить новые функциональные возможности, можно создать собственные типы, производные от существующих `DataGridViewCell`, `DataGridViewColumn`, и `DataGridViewRow` типы. Можно также предоставить новые возможности редактирования, создав производные типы, которые отображение элемента управления по своему выбору, когда ячейка находится в режиме редактирования.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 Описывает способы обработки <xref:System.Windows.Forms.DataGridView.CellPainting> событий для рисования ячейки вручную.  
  
 [Практическое руководство. Настройка внешнего вида строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 Описывает способы обработки <xref:System.Windows.Forms.DataGridView.RowPrePaint> и <xref:System.Windows.Forms.DataGridView.RowPostPaint> событий для рисования строки с настраиваемым, градиента фона и содержимого, которое охватывает несколько столбцов.  
  
 [Практическое руководство. Дополнительные возможности управления внешним видом и поведением ячеек и столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 Описывает способ создания пользовательских типов, производных от `DataGridViewCell` и `DataGridViewColumn` для выделения ячеек при наведении указателя мыши на них.  
  
 [Практическое руководство. Отключение кнопок в кнопочном столбце элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 Описывает способ создания пользовательских типов, производных от <xref:System.Windows.Forms.DataGridViewButtonCell> и <xref:System.Windows.Forms.DataGridViewButtonColumn> для отображения отключенных кнопок в столбце кнопок.  
  
 [Практическое руководство. Размещение элементов управления в ячейках элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 Описывает, как реализовать `IDataGridViewEditingControl` интерфейса и создания пользовательских типов, производных от `DataGridViewCell` и `DataGridViewColumn` для отображения <xref:System.Windows.Forms.DateTimePicker> управления, если ячейка находится в режиме редактирования.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Forms.DataGridView>  
 Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewCell> класса.  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewRow> класса.  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewColumn> класса.  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 Содержит справочную документацию по <xref:System.Windows.Forms.IDataGridViewEditingControl> интерфейса.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие способы изменения базового внешнего вида элемента управления и форматирования отображаемых данных ячейки.  
  
## <a name="see-also"></a>См. также  
 [Элемент управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Типы столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
