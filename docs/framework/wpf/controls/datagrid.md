---
title: "DataGrid | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "элементы управления [WPF], DataGrid"
  - "DataGrid [WPF], обычные задачи"
  - "DataGrid [WPF], настройка внешнего вида"
  - "DataGrid, типы столбцов [WPF]"
  - "DataGrid, столбцы [WPF], использование"
  - "DataGrid - элемент управления [WPF]"
  - "DataGrid, сценарии [WPF]"
ms.assetid: bf89ea63-79b6-422b-bc9f-0485ad803216
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# DataGrid
Элемент управления <xref:System.Windows.Controls.DataGrid> позволяет отображать и редактировать данные из множества различных источников, таких как база данных SQL, запрос LINQ и любые другие источники данных с возможностью привязки.  Дополнительные сведения см. в разделе [Общие сведения об источниках привязки](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
 Столбцы могут отображать текст, элементы управления, такие как <xref:System.Windows.Controls.ComboBox>, или любое другое содержимое WPF, такое как изображения, кнопки или любое содержимое из шаблона.  Для отображения данных, определенных в шаблоне, можно использовать <xref:System.Windows.Controls.DataGridTemplateColumn>.  В следующей таблице перечислены типы столбцов, предоставляемые по умолчанию.  
  
|Тип создаваемого столбца|Тип данных|  
|------------------------------|----------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 Можно настраивать внешний вид элемента управления <xref:System.Windows.Controls.DataGrid>, например изменять шрифт, цвет и размер ячейки.  Элемент управления <xref:System.Windows.Controls.DataGrid> поддерживает всю функциональность стилей и шаблонов других элементов управления WPF.  <xref:System.Windows.Controls.DataGrid> также включает как установленные по умолчанию, так и настраиваемые расширения функциональности для редактирования, сортировки и проверки.  
  
 В следующей таблице приведены некоторые из распространенных задач для элемента управления <xref:System.Windows.Controls.DataGrid> и порядок их выполнения.  Просматривая соответствующий API, можно найти дополнительные сведения и примеры кода.  
  
|Сценарий|Подход|  
|--------------|------------|  
|Переменные цвета фона|Установите для свойства <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> значение 2 или более, а затем назначьте элемент <xref:System.Windows.Media.Brush> свойствам <xref:System.Windows.Controls.DataGrid.RowBackground%2A> и <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A>.|  
|Определение поведения при выборе ячейки и строки|Установите свойства <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> и <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A>.|  
|Настройка внешнего вида заголовков, ячеек и строк|Примените новый <xref:System.Windows.Style> к свойству <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.CellStyle%2A> или <xref:System.Windows.Controls.DataGrid.RowStyle%2A>.|  
|Задание параметров изменения размера|Задайте свойства <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A> или <xref:System.Windows.FrameworkElement.MinWidth%2A>.  Дополнительные сведения см. в разделе [Параметры изменения размеров элемента управления DataGrid](../../../../docs/framework/wpf/controls/sizing-options-in-the-datagrid-control.md).|  
|Доступ к выбранным элементам|Проверьте свойство <xref:System.Windows.Controls.DataGrid.SelectedCells%2A> для получения выбранных ячеек и свойство <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A> для получения выбранных строк.  Дополнительные сведения см. в разделе <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>.|  
|Настройка взаимодействия с пользователем|Установите свойства <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A> и <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A>.|  
|Отмена или изменение автоматически созданных столбцов|Обработайте событие <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn>.|  
|Заморозка столбца|Установите для свойства <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> значение 1 и переместите столбец в крайнюю левую позицию, задав для свойства <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A> значение 0.|  
|Использование данных XML в качестве источника данных.|Привяжите свойство <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> элемента управления <xref:System.Windows.Controls.DataGrid> к запросу XPath, представляющему коллекцию элементов.  Создайте каждый столбец в элементе <xref:System.Windows.Controls.DataGrid>.  Произведите привязку каждого столбца, задав для XPath привязки запрос, получающий свойство источника элемента.  Пример см. в разделе <xref:System.Windows.Controls.DataGridTextColumn>.|  
  
## Связанные разделы  
  
|Заголовок|Описание|  
|---------------|--------------|  
|[Пошаговое руководство. Отображение данных из базы данных SQL Server в элементе управления DataGrid](../../../../docs/framework/wpf/controls/walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|Описание следующих задач: настройка нового проекта WPF, добавления элемента Entity Framework, установка источника и отображение данных в элементе управления <xref:System.Windows.Controls.DataGrid>.|  
|[Добавление сведений о строках в элемент управления DataGrid](../../../../docs/framework/wpf/controls/how-to-add-row-details-to-a-datagrid-control.md)|Описание способов создания сведений о строках для элемента управления <xref:System.Windows.Controls.DataGrid>.|  
|[Практическое руководство. реализация проверки с помощью элемента управления DataGrid](../../../../docs/framework/wpf/controls/how-to-implement-validation-with-the-datagrid-control.md)|Описание способов проверки значений в ячейках и строках <xref:System.Windows.Controls.DataGrid> и отображения результатов проверки.|  
|[Поведение мыши и клавиатуры по умолчанию в элементе управления DataGrid](../../../../docs/framework/wpf/controls/default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|Описание способов взаимодействия с элементом управления <xref:System.Windows.Controls.DataGrid> посредством клавиатуры и мыши.|  
|[Практическое руководство. Группировка, сортировка и фильтрация данных в элементе управления DataGrid](../../../../docs/framework/wpf/controls/how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|Описание различных способов просмотра данных в элементе управления <xref:System.Windows.Controls.DataGrid> с помощью группировки, сортировки и фильтрации.|  
|[Параметры изменения размеров элемента управления DataGrid](../../../../docs/framework/wpf/controls/sizing-options-in-the-datagrid-control.md)|Описание способов управления абсолютным и автоматическим заданием размера элемента управления <xref:System.Windows.Controls.DataGrid>.|  
  
## См. также  
 <xref:System.Windows.Controls.DataGrid>   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Элементы управления](../../../../docs/framework/wpf/controls/index.md)   
 [Модель содержимого WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md)