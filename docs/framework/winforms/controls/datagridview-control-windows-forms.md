---
title: элемент управления DataGridView (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- tables [Windows Forms]
- data grids [Windows Forms
- data [Windows Forms], displaying in tabular format
- grid controls [Windows Forms]
- datasets [Windows Forms], user interface
- Windows Forms, displaying data
- data presentation
- tabular data [Windows Forms], displaying on Windows Forms
- datasets [Windows Forms], displaying in DataGridView control
- DataGridView control [Windows Forms]
ms.assetid: dbee73f2-bba6-4874-9389-cd21d44309be
ms.openlocfilehash: 2ef387437befe3df67e261b719140456a3fde9dd
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43397223"
---
# <a name="datagridview-control-windows-forms"></a>элемент управления DataGridView (Windows Forms)
Элемент управления `DataGridView` предоставляет мощный и гибкий способ отображения данных в табличном формате. Элемент управления `DataGridView` можно использовать для отображения представлений небольшого объема данных только для чтения, либо можно масштабировать его для отображения редактируемого представления очень больших наборов данных.  
  
 Для того чтобы реализовать пользовательское поведение в приложениях, элемент управления `DataGridView` можно расширить несколькими способами. Например, можно программно задать собственные алгоритмы сортировки, можно создать собственные типы ячеек. Внешний вид элемента управления `DataGridView` легко настраивается заданием значений нескольких свойств. В качестве источника данных могут использоваться хранилища данных различных типов, также элемент управления `DataGridView` может работать без привязанного к нему  источника данных.  
  
 В подразделах данного раздела описываются принципы и методы применения возможностей `DataGridView` в приложениях.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Общие сведения об элементе управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 Содержит разделы с описанием назначения и основных понятий элемента управления `DataGridView` Windows Forms.  
  
 [Стандартная функциональность элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/default-functionality-in-the-windows-forms-datagridview-control.md)  
 Описание внешнего вида и поведения элемента управления `DataGridView` Windows Forms по умолчанию, когда он привязан к источнику данных.  
  
 [Типы столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 Описание типов столбцов элемента управления `DataGridView` Windows Forms, используемых для отображения данных, и разрешения пользователям изменять или добавлять данные.  
  
 [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 Разделы, описывающие часто используемые свойства ячеек, строк и столбцов.  
  
 [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие способы изменения базового внешнего вида элемента управления и форматирования отображаемых данных ячейки.  
  
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие заполнение элемента управления данными вручную или из внешнего источника данных.  
  
 [Изменение размера столбцов и строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие автоматическую корректировку размера строк и столбцов в соответствии с содержимым ячейки или доступной шириной элемента управления.  
  
 [Сортировка данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие возможности сортировки в элементе управления.  
  
 [Ввод данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 Разделы, в которых описывается изменение способов добавления и изменения данных в элементе управления.  
  
 [Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие возможности выбора ячеек, строк и столбцов в элементе управления.  
  
 [Программирование с использованием ячеек, строк и столбцов в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 Разделы, описывающие программирование объектов ячеек, строк и столбцов.  
  
 [Настройка элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие пользовательскую отрисовку ячеек и строк `DataGridView`, а также создание производных ячеек, столбцов и типов строк.  
  
 [Оптимизация производительности элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие, как эффективно использовать элемент управления, чтобы избежать снижения производительности при работе с большими объемами данных.  
  
 [Выполняемая по умолчанию обработка событий мыши и клавиатуры элементом управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)  
 Описание способов взаимодействия пользователей с элементом управления `DataGridView` посредством клавиатуры и мыши.  
  
 [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)  
 Описывает расширение возможностей и улучшения элемента управления `DataGridView`, который заменяет элемент управления <xref:System.Windows.Forms.DataGrid>.  
  
 Также см. в разделе [с помощью конструктора с помощью элемента управления DataGridView в Windows Forms](using-the-designer-with-the-windows-forms-datagridview-control.md).  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Forms.DataGridView>  
 Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.BindingSource>  
 Содержит справочную документацию по компоненту <xref:System.Windows.Forms.BindingSource>. Элемент управления <xref:System.Windows.Forms.DataGridView> и компонент <xref:System.Windows.Forms.BindingSource> предназначены для совместной работы.  
  
## <a name="see-also"></a>См. также  
 [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
