---
title: "Практическое руководство. Группировка, сортировка и фильтрация данных в элементе управления DataGrid | Microsoft Docs"
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
  - "DataGrid [WPF], фильтр"
  - "DataGrid [WPF], группа"
  - "DataGrid [WPF], сортировать"
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Группировка, сортировка и фильтрация данных в элементе управления DataGrid
Часто бывает полезно создавать различные представления данных в элементе управления <xref:System.Windows.Controls.DataGrid> путем их группировки, сортировки и фильтрации.  Для группировки, сортировки и фильтрации данных в элементе управления <xref:System.Windows.Controls.DataGrid> необходимо создать их привязку к классу <xref:System.Windows.Data.CollectionView>, который поддерживает эти функции.  Затем можно работать с данными в классе <xref:System.Windows.Data.CollectionView>, не оказывая влияния на базовые исходные данные.  Изменения представления коллекции отображаются в пользовательском интерфейсе <xref:System.Windows.Controls.DataGrid>.  
  
 Класс <xref:System.Windows.Data.CollectionView> предоставляет функции группировки и сортировки для источника данных, который реализует интерфейс <xref:System.Collections.IEnumerable>.  Класс <xref:System.Windows.Data.CollectionViewSource> позволяет задавать свойства класса <xref:System.Windows.Data.CollectionView> из кода XAML.  
  
 В данном примере коллекция объектов `Task` привязывается к классу <xref:System.Windows.Data.CollectionViewSource>.  Класс <xref:System.Windows.Data.CollectionViewSource> используется в качестве свойства <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для элемента управления <xref:System.Windows.Controls.DataGrid>.  Группировка, сортировка и фильтрация выполняются в классе <xref:System.Windows.Data.CollectionViewSource> и отображаются в пользовательском интерфейсе элемента управления <xref:System.Windows.Controls.DataGrid>.  
  
 ![Сгруппированные данные в DataGrid](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF\_DataGridGroups")  
Сгруппированные данные в элементе управления DataGrid  
  
## Использование класса CollectionViewSource в качестве свойства ItemsSource  
 Для группировки, сортировки и фильтрации данных в элементе управления <xref:System.Windows.Controls.DataGrid> необходимо привязать элемент управления <xref:System.Windows.Controls.DataGrid> к классу <xref:System.Windows.Data.CollectionView>, который поддерживает эти функции.  В данном примере элемент управления <xref:System.Windows.Controls.DataGrid> привязан к классу <xref:System.Windows.Data.CollectionViewSource>, который предоставляет эти функции для коллекции <xref:System.Collections.Generic.List%601> объектов `Task`.  
  
#### Создание привязки элемента управления DataGrid к классу CollectionViewSource  
  
1.  Создайте коллекцию данных, реализующую интерфейс <xref:System.Collections.IEnumerable>.  
  
     Если для создания коллекции используется класс <xref:System.Collections.Generic.List%601>, необходимо создать новый класс, производный от <xref:System.Collections.Generic.List%601>, а не создавать экземпляр класса <xref:System.Collections.Generic.List%601>.  Это позволит привязать данные к коллекции в коде XAML.  
  
    > [!NOTE]
    >  Объекты коллекции должны реализовать измененный интерфейс <xref:System.ComponentModel.INotifyPropertyChanged> и интерфейс <xref:System.ComponentModel.IEditableObject>, чтобы элемент управления <xref:System.Windows.Controls.DataGrid> правильно реагировал на изменения свойства.  Дополнительные сведения см. в разделе [Реализация уведомления об изменении свойства](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
     [!code-csharp[DataGrid_GroupSortFilter#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
     [!code-vb[DataGrid_GroupSortFilter#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]  
  
2.  В коде XAML создайте экземпляр класса коллекции и задайте директиву [Директива x:Key](../../../../docs/framework/xaml-services/x-key-directive.md).  
  
3.  В коде XAML создайте экземпляр класса <xref:System.Windows.Data.CollectionViewSource>, задайте директиву [Директива x:Key](../../../../docs/framework/xaml-services/x-key-directive.md) и установите экземпляр класса коллекции в качестве свойства <xref:System.Windows.Data.CollectionViewSource.Source%2A>.  
  
     [!code-xml[DataGrid_GroupSortFilter#201](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]  
  
4.  Создайте экземпляр класса <xref:System.Windows.Controls.DataGrid> и задайте для свойства <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> значение <xref:System.Windows.Data.CollectionViewSource>.  
  
     [!code-xml[DataGrid_GroupSortFilter#002](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]  
  
5.  Чтобы получить доступ к классу <xref:System.Windows.Data.CollectionViewSource> из кода, воспользуйтесь методом <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> для получения ссылки на класс <xref:System.Windows.Data.CollectionViewSource>.  
  
     [!code-csharp[DataGrid_GroupSortFilter#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
     [!code-vb[DataGrid_GroupSortFilter#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]  
  
## Группировка элементов в DataGrid  
 Чтобы указать способ группировки элементов в элементе управления <xref:System.Windows.Controls.DataGrid>, используйте тип <xref:System.Windows.Data.PropertyGroupDescription> для группировки элементов в представлении источника.  
  
#### Группировка элементов в DataGrid с использованием XAML  
  
1.  Создайте объект <xref:System.Windows.Data.PropertyGroupDescription>, задающий свойство, по которому выполняется группировка.  Это свойство можно задать в XAML или в коде.  
  
    1.  В XAML задайте для свойства <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> имя свойства, по которому выполняется группировка.  
  
    2.  В коде передайте в конструктор имя свойства, по которому выполняется группировка.  
  
2.  Добавьте объект <xref:System.Windows.Data.PropertyGroupDescription> в коллекцию <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=fullName>.  
  
3.  Добавьте дополнительные экземпляры <xref:System.Windows.Data.PropertyGroupDescription> в коллекцию <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> для добавления большего количества уровней группировки.  
  
     [!code-xml[DataGrid_GroupSortFilter#012](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#112](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
     [!code-vb[DataGrid_GroupSortFilter#112](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]  
  
4.  Для отмены одной группировки удалите соответствующий объект <xref:System.Windows.Data.PropertyGroupDescription> из коллекции <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A>.  
  
5.  Для отмены всех группировок вызовите метод <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> коллекции <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A>.  
  
     [!code-csharp[DataGrid_GroupSortFilter#114](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
     [!code-vb[DataGrid_GroupSortFilter#114](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]  
  
 Сгруппировав элементы в элементе управления <xref:System.Windows.Controls.DataGrid>, можно определить объект <xref:System.Windows.Controls.GroupStyle>, который задает внешний вид каждой группы.  Для применения объекта <xref:System.Windows.Controls.GroupStyle> необходимо добавить его в коллекцию <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> элемента управления DataGrid.  При наличии нескольких уровней группировки можно применить различные стили к каждому уровню группировки.  Стили применяются в порядке их определения.  Например, если определить два стиля, первый будет применяться к группам строк верхнего уровня.  Второй стиль будет применен ко всем группам строк на втором уровне и ниже.  Свойство <xref:System.Windows.FrameworkElement.DataContext%2A> объекта <xref:System.Windows.Controls.GroupStyle> является объектом <xref:System.Windows.Data.CollectionViewGroup>, который представляет группу.  
  
#### Изменение внешнего вида заголовков групп строк  
  
1.  Создайте объект <xref:System.Windows.Controls.GroupStyle>, который определяет внешний вид группы строк.  
  
2.  Поместите объект <xref:System.Windows.Controls.GroupStyle> между тегами `<DataGrid.GroupStyle>`.  
  
     [!code-xml[DataGrid_GroupSortFilter#003](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]  
  
## Сортировка элементов в DataGrid  
 Чтобы указать способ сортировки элементов в элементе управления <xref:System.Windows.Controls.DataGrid>, используйте тип <xref:System.ComponentModel.SortDescription> для сортировки элементов в представлении источника.  
  
#### Сортировка элементов в DataGrid  
  
1.  Создайте объект <xref:System.ComponentModel.SortDescription>, задающий свойство, по которому выполняется сортировка.  Это свойство можно задать в XAML или в коде.  
  
    1.  В XAML задайте для свойства <xref:System.ComponentModel.SortDescription.PropertyName%2A> имя свойства, по которому выполняется сортировка.  
  
    2.  В коде передайте в конструктор имя свойства, по которому выполняется сортировка, и объект <xref:System.ComponentModel.ListSortDirection>.  
  
2.  Добавьте объект <xref:System.ComponentModel.SortDescription> в коллекцию <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=fullName>.  
  
3.  Добавьте дополнительные экземпляры <xref:System.ComponentModel.SortDescription> в коллекцию <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> для сортировки по дополнительным свойствам.  
  
     [!code-xml[DataGrid_GroupSortFilter#011](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#211](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
     [!code-vb[DataGrid_GroupSortFilter#211](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]  
  
## Фильтрация элементов в DataGrid  
 Для фильтрации элементов в элементе управления <xref:System.Windows.Controls.DataGrid> с помощью класса <xref:System.Windows.Data.CollectionViewSource> необходимо предоставить логику фильтрации в обработчике событий <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=fullName>.  
  
#### Фильтрация элементов в DataGrid  
  
1.  Добавьте обработчик событий <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=fullName>.  
  
2.  В обработчике событий <xref:System.Windows.Data.CollectionViewSource.Filter> определите логику фильтрации.  
  
     Фильтр будет применяться при каждом обновлении представления.  
  
     [!code-xml[DataGrid_GroupSortFilter#013](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#113](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
     [!code-vb[DataGrid_GroupSortFilter#113](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]  
  
 Кроме того, элементы <xref:System.Windows.Controls.DataGrid> можно фильтровать путем создания метода, который предоставляет логику фильтрации, и задания свойства <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=fullName> для применения фильтра.  Пример этого метода см. в разделе [Фильтрация данных в представлении](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).  
  
## Пример  
 В следующем примере демонстрируется группировка, сортировка и фильтрация данных `Task` в классе <xref:System.Windows.Data.CollectionViewSource> и отображение сгруппированных, отсортированных и отфильтрованных данных `Task` в элементе управления <xref:System.Windows.Controls.DataGrid>.  Класс <xref:System.Windows.Data.CollectionViewSource> используется в качестве свойства <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для элемента управления <xref:System.Windows.Controls.DataGrid>.  Группировка, сортировка и фильтрация выполняются в классе <xref:System.Windows.Data.CollectionViewSource> и отображаются в пользовательском интерфейсе элемента управления <xref:System.Windows.Controls.DataGrid>.  
  
 Для проверки работы этого примера необходимо изменить имя DGGroupSortFilterExample на имя проекта.  При использовании Visual Basic необходимо изменить имя класса для <xref:System.Windows.Window> на следующее значение.  
  
 `<Window x:Class="MainWindow"`  
  
 [!code-xml[DataGrid_GroupSortFilter#000](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]  
  
 [!code-csharp[DataGrid_GroupSortFilter#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
 [!code-vb[DataGrid_GroupSortFilter#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]  
  
## Компиляция кода  
  
## Отказоустойчивость  
  
## Безопасность платформы .NET Framework  
  
## См. также  
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Создание и привязка ObservableCollection](../../../../docs/framework/wpf/data/how-to-create-and-bind-to-an-observablecollection.md)   
 [Фильтрация данных в представлении](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)   
 [Сортировка данных в представлении](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)   
 [Сортировка и группировка данных с помощью представления в XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)