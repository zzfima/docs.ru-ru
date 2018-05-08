---
title: Базовое форматирование и оформление элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: d38620c321fb12b9f489fd086e222b7780337ab3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a>Базовое форматирование и оформление элемента управления DataGridView в Windows Forms
`DataGridView` Управления упрощает определение основного внешнего вида ячеек и форматирования отображения значений ячеек. Можно задать внешний вид и стили форматирования для отдельных ячеек, для ячеек в определенных столбцах и строках или для всех ячеек в элементе управления, задав свойства `DataGridViewCellStyle` объектов, доступных через различные `DataGridView` свойств элемента управления. Кроме того, можно изменить эти стили, динамически на основе таких факторов значение ячейки, обрабатывая `CellFormatting` событий.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Изменение внешнего вида границ и линий сетки элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)  
 Описывает, как задать `DataGridView` свойства, определяющие внешний вид границы элемента управления и разделительных линий между ячейками.  
  
 [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 Описывает `DataGridViewCellStyle` класса и взаимодействие свойств этого типа, чтобы определить способ отображения ячеек в элементе управления.  
  
 [Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 Описывает использование `DataGridViewCellStyle` свойства, определяющие внешний вид ячеек по умолчанию в определенных строках и столбцах и всего элемента управления.  
  
 [Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 Описание форматирования отображения значений ячеек с помощью `DataGridViewCellStyle` свойства.  
  
 [Практическое руководство. Настройка шрифтов и цветов в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 Описывает использование `DefaultCellStyle` свойство, чтобы задать основные отобразить характеристики всех ячеек в элементе управления.  
  
 [Практическое руководство. Настройка формата отображения четных строк для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 Описывает, как для создания эффекта подобном бухгалтерским книгам: в элементе управления с помощью чередующихся строк, которые отображаются по-разному.  
  
 [Практическое руководство. Применение шаблонов строк для настройки отображения строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 Описывает использование `RowTemplate` свойства для настройки свойств строки, которые будут использоваться для всех строк в элементе управления.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Forms.DataGridView>  
 Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewCellStyle> класса.  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.CellFormatting> событий.  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> свойство.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Настройка элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие пользовательскую отрисовку ячеек и строк <xref:System.Windows.Forms.DataGridView>, а также создание производных ячеек, столбцов и типов строк.  
  
 [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 Содержит разделы, описывающие часто используемые свойства ячеек, строк и столбцов.  
  
## <a name="see-also"></a>См. также  
 [Элемент управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
