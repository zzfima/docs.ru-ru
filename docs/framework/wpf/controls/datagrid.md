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
ms.openlocfilehash: f0887f36990de483139a9fde1472a78737cb7b72
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460385"
---
# <a name="datagrid"></a>DataGrid
Элемент управления <xref:System.Windows.Controls.DataGrid> позволяет отображать и изменять данные из множества различных источников, например из базы данных SQL, запроса LINQ или любого другого источника данных, доступного для привязки. Дополнительные сведения см. в разделе [Общие сведения об источниках привязки](../data/binding-sources-overview.md).  
  
 Столбцы могут отображать текст, элементы управления, такие как <xref:System.Windows.Controls.ComboBox>, или любое другое содержимое WPF, например изображения, кнопки или любое содержимое, содержащееся в шаблоне. Для вывода данных, определенных в шаблоне, можно использовать <xref:System.Windows.Controls.DataGridTemplateColumn>. В следующей таблице перечислены типы столбцов, предоставляемые по умолчанию.  
  
|Созданный тип столбца|Тип данных|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid> можно настроить по внешнему виду, например шрифту, цвету и размеру ячейки. <xref:System.Windows.Controls.DataGrid> поддерживает все функциональные возможности стилизации и создания шаблонов других элементов управления WPF. <xref:System.Windows.Controls.DataGrid> также включает настройки по умолчанию и настраиваемые поведения для редактирования, сортировки и проверки.  
  
 В следующей таблице перечислены некоторые распространенные задачи для <xref:System.Windows.Controls.DataGrid> и способы их выполнения. Просмотрев связанный API, можно найти дополнительные сведения и пример кода.  
  
|Сценарий|Подход|  
|--------------|--------------|  
|Чередующиеся цвета фона|Задайте для свойства <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> значение 2 или более, а затем назначьте <xref:System.Windows.Media.Brush> свойствам <xref:System.Windows.Controls.DataGrid.RowBackground%2A> и <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A>.|  
|Определение поведения выбора ячеек и строк|Задайте свойства <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> и <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A>.|  
|Настройка внешнего вида заголовков, ячеек и строк|Примените новый <xref:System.Windows.Style> к свойствам <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.CellStyle%2A>или <xref:System.Windows.Controls.DataGrid.RowStyle%2A>.|  
|Задать параметры изменения размера|Задайте свойства <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>или <xref:System.Windows.FrameworkElement.MinWidth%2A>. Дополнительные сведения см. [в разделе Параметры изменения размера в элементе управления DataGrid](sizing-options-in-the-datagrid-control.md).|  
|Доступ к выбранным элементам|Проверьте свойство <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>, чтобы получить выбранные ячейки, и свойство <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A>, чтобы получить выбранные строки. Для получения дополнительной информации см. <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>.|  
|Настройка взаимодействия с конечным пользователем|Задайте свойства <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A>и <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A>.|  
|Отмена или изменение автоматически созданных столбцов|Обрабатывает событие <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn>.|  
|Закрепить столбец|Присвойте свойству <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> значение 1 и переместите столбец в крайне левое положение, задав свойству <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A> значение 0.|  
|Использование XML-данных в качестве источника данных|Привяжите <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> к <xref:System.Windows.Controls.DataGrid> к запросу XPath, представляющему коллекцию элементов. Создайте каждый столбец в <xref:System.Windows.Controls.DataGrid>. Привяжите каждый столбец, задав XPath для привязки к запросу, который получает свойство в источнике элемента. Пример см. в разделе <xref:System.Windows.Controls.DataGridTextColumn>.|  
  
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Пошаговое руководство. Отображение данных из базы данных SQL Server в элементе управления DataGrid](walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|Описывает настройку нового проекта WPF, Добавление элемента Entity Framework, задание источника и отображение данных в <xref:System.Windows.Controls.DataGrid>.|  
|[Добавление сведений о строках в элемент управления DataGrid](how-to-add-row-details-to-a-datagrid-control.md)|Описание создания сведений о строках для <xref:System.Windows.Controls.DataGrid>.|  
|[Практическое руководство. реализация проверки с помощью элемента управления DataGrid](how-to-implement-validation-with-the-datagrid-control.md)|Описывает, как проверить значения в <xref:System.Windows.Controls.DataGrid> ячейках и строках, а затем отобразить отзыв о проверке.|  
|[Поведение мыши и клавиатуры по умолчанию в элементе управления DataGrid](default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|Описывает, как взаимодействовать с элементом управления <xref:System.Windows.Controls.DataGrid> с помощью клавиатуры и мыши.|  
|[Практическое руководство. Группировка, сортировка и фильтрация данных в элементе управления DataGrid](how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|Описание способов просмотра данных в <xref:System.Windows.Controls.DataGrid> различными способами путем группирования, сортировки и фильтрации данных.|  
|[Параметры изменения размеров элемента управления DataGrid](sizing-options-in-the-datagrid-control.md)|Описывает, как управлять абсолютным и автоматическим изменением размеров в <xref:System.Windows.Controls.DataGrid>.|  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.DataGrid>
- [Стилизация и использование шаблонов](styling-and-templating.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Общие сведения о шаблонах данных](../data/data-templating-overview.md)
- [Элементы управления](index.md)
- [Модель содержимого WPF](wpf-content-model.md)
