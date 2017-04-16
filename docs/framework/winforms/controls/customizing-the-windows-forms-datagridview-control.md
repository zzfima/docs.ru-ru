---
title: "Настройка элементов управления DataGridView в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "таблицы данных, настройка"
  - "DataGridView - элемент управления [Windows Forms], настройка"
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Настройка элементов управления DataGridView в Windows Forms
Элемент управления `DataGridView` предоставляет несколько свойств, которые можно использовать для изменения внешнего вида и основного поведения ячеек, строк и столбцов.  В случае особых требований, выходящих за пределы возможностей класса <xref:System.Windows.Forms.DataGridViewCellStyle>, можно реализовать пользовательское отображение для элемента управления или создать пользовательские ячейки, строки и столбцы для расширения возможностей класса.  
  
 Чтобы прорисовать ячейки и строки самостоятельно, можно обработать различные события рисования `DataGridView`.  Чтобы изменить существующие функциональные возможности или предоставить новые функциональные возможности, можно создать собственные типы, являющиеся производными от существующих типов `DataGridViewCell`, `DataGridViewColumn` и `DataGridViewRow`.  Можно также предоставить новые возможности редактирования путем создания производных типов, отображающих выбранный элемент управления в режиме редактирования ячейки.  
  
## В этом подразделе  
 [Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 Описывает способы обработки события <xref:System.Windows.Forms.DataGridView.CellPainting> для ручной прорисовки ячеек.  
  
 [Практическое руководство. Настройка внешнего вида строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 Описывает способы обработки событий <xref:System.Windows.Forms.DataGridView.RowPrePaint> и <xref:System.Windows.Forms.DataGridView.RowPostPaint> для ручной прорисовки строк с использованием градиентного фона и содержимого, общего для нескольких столбцов.  
  
 [Практическое руководство. Дополнительные возможности управления внешним видом и поведением ячеек и столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 Содержит описание способов создания пользовательских типов, производных от `DataGridViewCell` и `DataGridViewColumn`, с целью выделения ячеек, на которые наведен указатель мыши.  
  
 [Практическое руководство. Отключение кнопок в кнопочном столбе элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 Содержит описание способов создания пользовательских типов, производных от <xref:System.Windows.Forms.DataGridViewButtonCell> и <xref:System.Windows.Forms.DataGridViewButtonColumn>, с целью отображения отключенных кнопок в столбце кнопок.  
  
 [Практическое руководство. Размещение элементов управления в ячейках элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 Содержит описание реализации интерфейса `IDataGridViewEditingControl` и создания пользовательских типов, производных от `DataGridViewCell` и `DataGridViewColumn` с целью отображения элемента управления <xref:System.Windows.Forms.DateTimePicker> в режиме редактирования ячейки.  
  
## Ссылка  
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
  
## Связанные подразделы  
 [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 Содержит список разделов, в которых описаны способы изменения основного внешнего вида элемента управления и отображения форматирования данных ячейки.  
  
## См. также  
 [Элемент управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Типы столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)