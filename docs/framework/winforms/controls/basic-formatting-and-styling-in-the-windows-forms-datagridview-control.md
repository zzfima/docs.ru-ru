---
title: "Базовое форматирование и оформление элемента управления DataGridView в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "таблицы данных, форматирование"
  - "DataGridView - элемент управления [Windows Forms], форматирование и применение стилей"
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Базовое форматирование и оформление элемента управления DataGridView в Windows Forms
Элемент управления `DataGridView` упрощает определение основного внешнего вида ячеек и форматирования отображения значений ячеек.  Можно задать внешний вид и стили форматирования для отдельных ячеек, для ячеек в определенных столбцах и строках, а также для всех ячеек в элементе управления, настроив нужным образом значения свойств объектов `DataGridViewCellStyle`, доступ к которым осуществляется через различные свойства элемента управления `DataGridView`.  Кроме того, путем обработки события `CellFormatting` можно динамически менять эти стили в зависимости, например, от значения ячейки.  
  
## В этом подразделе  
 [Практическое руководство. Изменение внешнего вида границ и линий сетки элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)  
 Описание настройки свойств `DataGridView`, определяющих внешний вид границы элемента управления и разделительных линий между ячейками.  
  
 [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 Описание класса `DataGridViewCellStyle` и влияния свойств этого типа на определение внешнего вида ячеек в элементе управления.  
  
 [Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 Описание использования свойств `DataGridViewCellStyle` для определения внешнего вида по умолчанию ячеек в определенных строках и столбцах, а также во всем элементе управления.  
  
 [Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 Описание форматирования отображения значений ячеек с помощью свойств `DataGridViewCellStyle`.  
  
 [Практическое руководство. Настройка шрифтов и цветов в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 Описание использования свойства `DefaultCellStyle` для настройки основных характеристик отображения для всех ячеек в элементе управления.  
  
 [Практическое руководство. Настройка формата отображения четных строк для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 Описание использования в элементе управления эффекта бухгалтерской книги, при котором чередующиеся строки отображаются по\-разному.  
  
 [Практическое руководство. Применение шаблонов строк для настройки отображения строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 Описание использования свойства `RowTemplate` для настройки свойств строки, которые будут использоваться для всех строк элемента управления.  
  
## Ссылка  
 <xref:System.Windows.Forms.DataGridView>  
 Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 Справочная документация по классу <xref:System.Windows.Forms.DataGridViewCellStyle>.  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 Справочная документация по событию <xref:System.Windows.Forms.DataGridView.CellFormatting>.  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 Справочная документация по свойству <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>.  
  
## Связанные подразделы  
 [Настройка элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 Список разделов, в которых описывается пользовательская окраска ячеек и строк <xref:System.Windows.Forms.DataGridView> и создание производных типов ячеек, строк и столбцов.  
  
 [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 Разделы, описывающие часто используемые свойства ячеек, строк и столбцов.  
  
## См. также  
 [Элемент управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)