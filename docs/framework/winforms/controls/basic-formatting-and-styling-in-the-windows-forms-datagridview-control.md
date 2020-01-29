---
title: Базовое форматирование и стилизация в элементе управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: d295718b7bd4f3bc4c5f63b6e6cb911f733525fe
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731998"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a>Стандартная функциональность элемента управления DataGridView в Windows Forms
Элемент управления `DataGridView` позволяет легко определить базовый вид ячеек и формат отображения значений ячеек. Можно определить стили оформления и форматирования для отдельных ячеек, для ячеек в определенных столбцах и строках или для всех ячеек в элементе управления, задав свойства `DataGridViewCellStyle` объектов, доступ к которым осуществляется через различные свойства элемента управления `DataGridView`. Кроме того, эти стили можно динамически изменить на основе таких факторов, как значение ячейки, обрабатывая событие `CellFormatting`.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Изменение внешнего вида границ и линий сетки элемента управления DataGridView в Windows Forms](change-the-border-and-gridline-styles-in-the-datagrid.md)  
 Описывает, как задать свойства `DataGridView`, определяющие внешний вид границы элемента управления и линий границ между ячейками.  
  
 [Стили ячеек элемента управления DataGridView в Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)  
 Описывает класс `DataGridViewCellStyle` и способ взаимодействия свойств этого типа для определения способа отображения ячеек в элементе управления.  
  
 [Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 Описывает использование `DataGridViewCellStyle` свойств для определения стандартного вида ячеек в определенных строках и столбцах, а также во всем элементе управления.  
  
 [Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms](how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 Описание форматирования отображаемых значений ячеек с помощью `DataGridViewCellStyle` свойств.  
  
 [Практическое руководство. Настройка шрифтов и цветов в элементе управления DataGridView в Windows Forms](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 Описывает использование свойства `DefaultCellStyle` для задания основных характеристик отображения для всех ячеек в элементе управления.  
  
 [Практическое руководство. Настройка формата отображения четных строк для элемента управления DataGridView в Windows Forms](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 Описывает, как создать в элементе управления воздействие, аналогичное, с помощью чередующихся строк, которые отображаются по-разному.  
  
 [Практическое руководство. Применение шаблонов строк для настройки отображения строк элемента управления DataGridView в Windows Forms](use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 Описывает использование свойства `RowTemplate` для задания свойств строки, которые будут использоваться для всех строк в элементе управления.  
  
## <a name="reference"></a>Справочные сведения  
 <xref:System.Windows.Forms.DataGridView>  
 Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 Содержит справочную документацию по классу <xref:System.Windows.Forms.DataGridViewCellStyle>.  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 Содержит справочную документацию по событию <xref:System.Windows.Forms.DataGridView.CellFormatting>.  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 Содержит справочную документацию по свойству <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Настройка элементов управления DataGridView в Windows Forms](customizing-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие пользовательскую отрисовку ячеек и строк <xref:System.Windows.Forms.DataGridView>, а также создание производных ячеек, столбцов и типов строк.  
  
 [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 Содержит разделы, описывающие часто используемые свойства ячеек, строк и столбцов.  
  
## <a name="see-also"></a>См. также:

- [Элемент управления DataGridView](datagridview-control-windows-forms.md)
