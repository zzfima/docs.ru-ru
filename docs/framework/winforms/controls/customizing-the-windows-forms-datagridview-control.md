---
title: Настройка элементов управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 901b221f74fa76221ed3f19e9eb4c5f17c6534fa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559558"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a>Настройка элементов управления DataGridView в Windows Forms
`DataGridView` Управления предоставляет несколько свойств, которые можно использовать для настройки внешнего вида и базовое поведение (оформление) его ячеек, строк и столбцов. Если у вас есть особые потребности, которые выходят за рамки возможностей <xref:System.Windows.Forms.DataGridViewCellStyle> класса, однако можно также реализовать пользовательское рисование элемента управления или расширяют ее возможности, создав пользовательские ячейки, строки и столбцы.  
  
 Для закрашивания ячейки и строки самостоятельно, можно обработать различные `DataGridView` события рисования. Чтобы изменить существующие функциональные возможности или предоставить новые функциональные возможности, можно создать собственные типы, производные от существующих `DataGridViewCell`, `DataGridViewColumn`, и `DataGridViewRow` типы. Можно также предоставить новые возможности редактирования путем создания производных типов, отображение элемента управления по своему выбору, если ячейка находится в режиме правки.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 Описание способов обработки <xref:System.Windows.Forms.DataGridView.CellPainting> событий для рисования ячейки вручную.  
  
 [Практическое руководство. Настройка внешнего вида строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 Описание способов обработки <xref:System.Windows.Forms.DataGridView.RowPrePaint> и <xref:System.Windows.Forms.DataGridView.RowPostPaint> события для закрашивания строк с помощью пользовательских, градиента фона и содержимого, которое охватывает несколько столбцов.  
  
 [Практическое руководство. Настройка ячеек и столбцов в элементе управления DataGridView Windows Forms, расширяя их поведение и внешний вид](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 Описывает способы создания пользовательских типов, производных от `DataGridViewCell` и `DataGridViewColumn` для выделения ячеек на них указателя мыши.  
  
 [Практическое руководство. Отключение кнопок в кнопочном столбце в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 Описывает способы создания пользовательских типов, производных от <xref:System.Windows.Forms.DataGridViewButtonCell> и <xref:System.Windows.Forms.DataGridViewButtonColumn> для отображения кнопок в кнопочном столбе.  
  
 [Практическое руководство. Элементы управления ведущего приложения в ячеек элемента управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 Описывается реализация `IDataGridViewEditingControl` интерфейса и создания пользовательских типов, производных от `DataGridViewCell` и `DataGridViewColumn` для отображения <xref:System.Windows.Forms.DateTimePicker> управления, когда ячейка находится в режиме редактирования.  
  
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
 Содержит справочную документацию по <xref:System.Windows.Forms.IDataGridViewEditingControl> интерфейс.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие способы изменения базового внешнего вида элемента управления и форматирования отображаемых данных ячейки.  
  
## <a name="see-also"></a>См. также
- [Элемент управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
- [Типы столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
