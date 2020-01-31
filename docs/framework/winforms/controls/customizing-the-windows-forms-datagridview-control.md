---
title: Настройка элемента управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 348c78d091679418f2452326555d49229bd2a8ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744021"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a>Настройка элементов управления DataGridView в Windows Forms
Элемент управления `DataGridView` предоставляет несколько свойств, которые можно использовать для настройки внешнего вида и основного поведения (внешнего вида) своих ячеек, строк и столбцов. Однако при наличии особых потребностей, которые выходят за пределы возможностей класса <xref:System.Windows.Forms.DataGridViewCellStyle>, можно также реализовать рисование владельцем для элемента управления или расширить его возможности путем создания пользовательских ячеек, столбцов и строк.  
  
 Для самостоятельного заполнения ячеек и строк можно обрабатывать различные события рисования `DataGridView`. Чтобы изменить существующие функциональные возможности или предоставить новые функциональные возможности, можно создать собственные типы, производные от существующих типов `DataGridViewCell`, `DataGridViewColumn`и `DataGridViewRow`. Можно также предоставить новые возможности редактирования, создав производные типы, которые отображают выбираемый элемент управления, когда ячейка находится в режиме редактирования.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms](customize-the-appearance-of-cells-in-the-datagrid.md)  
 Описывает, как обрабатывать событие <xref:System.Windows.Forms.DataGridView.CellPainting> для ручного заполнения ячеек.  
  
 [Практическое руководство. Настройка внешнего вида строк элемента управления DataGridView в Windows Forms](customize-the-appearance-of-rows-in-the-datagrid.md)  
 Описывает, как обрабатывать события <xref:System.Windows.Forms.DataGridView.RowPrePaint> и <xref:System.Windows.Forms.DataGridView.RowPostPaint>, чтобы закрасить строки с помощью пользовательского градиентного фона и содержимого, охватывающего несколько столбцов.  
  
 [Практическое руководство. Дополнительные возможности управления внешним видом и поведением ячеек и столбцов элемента управления DataGridView в Windows Forms](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 Описывает создание пользовательских типов, производных от `DataGridViewCell` и `DataGridViewColumn`, для выделения ячеек при помещении на них указателя мыши.  
  
 [Практическое руководство. Отключение кнопок в кнопочном столбце элемента управления DataGridView в Windows Forms](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 Описывает создание пользовательских типов, производных от <xref:System.Windows.Forms.DataGridViewButtonCell> и <xref:System.Windows.Forms.DataGridViewButtonColumn>, для отображения отключенных кнопок в столбце кнопки.  
  
 [Практическое руководство. Размещение элементов управления в ячейках элемента управления DataGridView в Windows Forms](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 Описывает, как реализовать интерфейс `IDataGridViewEditingControl` и создавать пользовательские типы, производные от `DataGridViewCell` и `DataGridViewColumn` для отображения элемента управления <xref:System.Windows.Forms.DateTimePicker>, когда ячейка находится в режиме редактирования.  
  
## <a name="reference"></a>Справочные сведения  
 <xref:System.Windows.Forms.DataGridView>  
 Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 Содержит справочную документацию по классу <xref:System.Windows.Forms.DataGridViewCell>.  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 Содержит справочную документацию по классу <xref:System.Windows.Forms.DataGridViewRow>.  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 Содержит справочную документацию по классу <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 Содержит справочную документацию по интерфейсу <xref:System.Windows.Forms.IDataGridViewEditingControl>.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие способы изменения базового внешнего вида элемента управления и форматирования отображаемых данных ячейки.  
  
## <a name="see-also"></a>См. также:

- [Элемент управления DataGridView](datagridview-control-windows-forms.md)
- [Типы столбцов элемента управления DataGridView в Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
