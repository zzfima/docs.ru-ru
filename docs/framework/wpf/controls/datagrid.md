---
title: DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid column types [WPF]
- DataGrid scenarios [WPF]
- DataGrid control [WPF]
- controls [WPF], DataGrid
- DataGrid [WPF], common tasks for
- DataGrid [WPF], customizing the appearance of
- DataGrid columns [WPF], using
ms.assetid: bf89ea63-79b6-422b-bc9f-0485ad803216
ms.openlocfilehash: a8f267706c1ace02b091329360779711981d01e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557086"
---
# <a name="datagrid"></a>DataGrid
<xref:System.Windows.Controls.DataGrid> Элемент управления позволяет отображать и редактировать данные из множества различных источников, таких как базы данных SQL, запрос LINQ и любые другие источники данных. Дополнительные сведения см. в разделе [Общие сведения об источниках привязки](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
 Столбцы могут отображать текст, элементы управления, такие как <xref:System.Windows.Controls.ComboBox>, или любое другое содержимое WPF, таких как изображения, кнопки или любое содержимое, содержащихся в шаблоне. Можно использовать <xref:System.Windows.Controls.DataGridTemplateColumn> для отображения данных, определенных в шаблоне. Ниже перечислены типы столбцов, предоставляемые по умолчанию.  
  
|Тип создаваемого столбца|Тип данных|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid> можно настроить внешний вид, например ячейки шрифт, цвет и размер. <xref:System.Windows.Controls.DataGrid> поддерживает все функциональные возможности Стилизация и использование шаблонов других элементов управления WPF. <xref:System.Windows.Controls.DataGrid> также включены по умолчанию и настраиваемые расширения функциональности для редактирования, сортировки и проверки.  
  
 В следующей таблице перечислены некоторые распространенные задачи по <xref:System.Windows.Controls.DataGrid> и порядок их выполнения. Просматривая соответствующий API, можно найти дополнительные сведения и пример кода.  
  
|Сценарий|Подход|  
|--------------|--------------|  
|Чередующиеся фоновые цвета|Задать <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> значение 2 или более и назначьте <xref:System.Windows.Media.Brush> для <xref:System.Windows.Controls.DataGrid.RowBackground%2A> и <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A> свойства.|  
|Определение режима выделения ячеек и строк|Задайте свойства <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> и <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A>.|  
|Настройка внешнего вида заголовков, ячеек и строк|Применить новый <xref:System.Windows.Style> для <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.CellStyle%2A>, или <xref:System.Windows.Controls.DataGrid.RowStyle%2A> свойства.|  
|Задание параметров изменения размера|Задать <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, или <xref:System.Windows.FrameworkElement.MinWidth%2A> свойства. Дополнительные сведения см. в разделе [параметры изменения размера в элементе управления DataGrid](../../../../docs/framework/wpf/controls/sizing-options-in-the-datagrid-control.md).|  
|Доступ к выбранным элементам|Проверьте <xref:System.Windows.Controls.DataGrid.SelectedCells%2A> свойства выбранной ячейки и <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A> свойства выбранных строк. Дополнительные сведения см. в разделе <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>.|  
|Настройка взаимодействия|Задать <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A>, и <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A> свойства.|  
|Отмена или изменение автоматически созданных столбцов|Обрабатывать <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn> событий.|  
|Закрепить столбец|Задать <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> 1 и переместите столбец в крайней левой позиции, задав свойству <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A> значение 0.|  
|Использование XML-данных в качестве источника данных|Привязать <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> на <xref:System.Windows.Controls.DataGrid> запрос XPath, который представляет коллекцию элементов. Создайте каждый столбец в <xref:System.Windows.Controls.DataGrid>. Каждый столбец связать, задав выражение XPath в привязке запроса, который возвращает свойство источника элемента. Пример см. в разделе <xref:System.Windows.Controls.DataGridTextColumn>.|  
  
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Пошаговое руководство. Отображение данных из базы данных SQL Server в элементе управления DataGrid](../../../../docs/framework/wpf/controls/walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|Описывает, как настроить новый проект WPF, добавьте элемент Entity Framework, установите в качестве источника и отображения данных в <xref:System.Windows.Controls.DataGrid>.|  
|[Добавление сведений о строках в элемент управления DataGrid](../../../../docs/framework/wpf/controls/how-to-add-row-details-to-a-datagrid-control.md)|Описание способов создания сведений о строках для <xref:System.Windows.Controls.DataGrid>.|  
|[Практическое руководство. реализация проверки с помощью элемента управления DataGrid](../../../../docs/framework/wpf/controls/how-to-implement-validation-with-the-datagrid-control.md)|Описание способов проверки значений в <xref:System.Windows.Controls.DataGrid> ячеек и строк и отображения результатов проверки.|  
|[Поведение мыши и клавиатуры по умолчанию в элементе управления DataGrid](../../../../docs/framework/wpf/controls/default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|Описывает, как взаимодействовать с <xref:System.Windows.Controls.DataGrid> управления с помощью клавиатуры и мыши.|  
|[Практическое руководство. Группировка, сортировка и фильтрация данных в элементе управления DataGrid](../../../../docs/framework/wpf/controls/how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|Описывает, как просматривать данные в <xref:System.Windows.Controls.DataGrid> путем группирования, сортировки и фильтрации данных различными способами.|  
|[Параметры изменения размеров элемента управления DataGrid](../../../../docs/framework/wpf/controls/sizing-options-in-the-datagrid-control.md)|Описание способов управления абсолютным и автоматического изменения размеров в <xref:System.Windows.Controls.DataGrid>.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.DataGrid>  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Элементы управления](../../../../docs/framework/wpf/controls/index.md)  
 [Модель содержимого WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md)
