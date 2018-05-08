---
title: Практическое руководство. Группировка, сортировка и фильтрация данных в элементе управления DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
ms.openlocfilehash: 675c1441201fa1578023d6ed758f389a38f3b79a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a>Практическое руководство. Группировка, сортировка и фильтрация данных в элементе управления DataGrid
Часто полезно просматривать данные в <xref:System.Windows.Controls.DataGrid> путем группирования, сортировки и фильтрации данных различными способами. Группировать, сортировать и фильтровать данные в <xref:System.Windows.Controls.DataGrid>, привяжите его к <xref:System.Windows.Data.CollectionView> который поддерживает эти функции. Вы можете работать с данными в <xref:System.Windows.Data.CollectionView> без изменения базового источника данных. Изменения в представлении коллекции отражены в <xref:System.Windows.Controls.DataGrid> пользовательского интерфейса (UI).  
  
 <xref:System.Windows.Data.CollectionView> Класс предоставляет функции для источника данных, который реализует группировки и сортировки <xref:System.Collections.IEnumerable> интерфейса. <xref:System.Windows.Data.CollectionViewSource> Позволяет задать свойства <xref:System.Windows.Data.CollectionView> из XAML.  
  
 В этом примере коллекция `Task` объектов привязан к <xref:System.Windows.Data.CollectionViewSource>. <xref:System.Windows.Data.CollectionViewSource> Используется в качестве <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для <xref:System.Windows.Controls.DataGrid>. Группирование, сортировка и фильтрация выполняются на <xref:System.Windows.Data.CollectionViewSource> и отображаются в <xref:System.Windows.Controls.DataGrid> пользовательского интерфейса.  
  
 ![Сгруппированные данные в элементе управления DataGrid](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF_DataGridGroups")  
Сгруппированные данные в элементе управления DataGrid  
  
## <a name="using-a-collectionviewsource-as-an-itemssource"></a>С помощью CollectionViewSource как ItemsSource  
 Для группирования, сортировки и фильтрации данных в <xref:System.Windows.Controls.DataGrid> привязать элемент управления, <xref:System.Windows.Controls.DataGrid> для <xref:System.Windows.Data.CollectionView> который поддерживает эти функции. В этом примере <xref:System.Windows.Controls.DataGrid> привязан к <xref:System.Windows.Data.CollectionViewSource> , предоставляет эти функции для <xref:System.Collections.Generic.List%601> из `Task` объектов.  
  
#### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a>Для привязки элемента управления DataGrid к CollectionViewSource  
  
1.  Создайте коллекцию данных, который реализует <xref:System.Collections.IEnumerable> интерфейса.  
  
     Если вы используете <xref:System.Collections.Generic.List%601> для создания коллекции, следует создать новый класс, наследующий от <xref:System.Collections.Generic.List%601> вместо экземпляра <xref:System.Collections.Generic.List%601>. Это позволит вам для привязки данных к коллекции в языке XAML.  
  
    > [!NOTE]
    >  Объекты в коллекции должны реализовывать <xref:System.ComponentModel.INotifyPropertyChanged> измененный интерфейс и <xref:System.ComponentModel.IEditableObject> интерфейса в порядке для <xref:System.Windows.Controls.DataGrid> правильно реагировать на изменения свойства. Дополнительные сведения см. в разделе [Реализация уведомления об изменении свойств](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
     [!code-csharp[DataGrid_GroupSortFilter#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
     [!code-vb[DataGrid_GroupSortFilter#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]  
  
2.  В XAML, создайте экземпляр класса коллекции и задайте [директива x: Key](../../../../docs/framework/xaml-services/x-key-directive.md).  
  
3.  В языке XAML, создайте экземпляр класса <xref:System.Windows.Data.CollectionViewSource> класса, задайте [директива x: Key](../../../../docs/framework/xaml-services/x-key-directive.md)и установите экземпляр класса коллекции как <xref:System.Windows.Data.CollectionViewSource.Source%2A>.  
  
     [!code-xaml[DataGrid_GroupSortFilter#201](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]  
  
4.  Создайте экземпляр класса <xref:System.Windows.Controls.DataGrid> и укажите <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойства <xref:System.Windows.Data.CollectionViewSource>.  
  
     [!code-xaml[DataGrid_GroupSortFilter#002](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]  
  
5.  Чтобы получить доступ к <xref:System.Windows.Data.CollectionViewSource> в коде, используйте <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> метод позволяет получить ссылку на <xref:System.Windows.Data.CollectionViewSource>.  
  
     [!code-csharp[DataGrid_GroupSortFilter#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
     [!code-vb[DataGrid_GroupSortFilter#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]  
  
## <a name="grouping-items-in-a-datagrid"></a>Группирование элементов в элементе управления DataGrid  
 Чтобы указать способ группировки элементов в <xref:System.Windows.Controls.DataGrid>, использовании <xref:System.Windows.Data.PropertyGroupDescription> типа, чтобы сгруппировать элементы в представлении источника.  
  
#### <a name="to-group-items-in-a-datagrid-using-xaml"></a>Для группирования элементов в элементе управления DataGrid, с помощью XAML  
  
1.  Создание <xref:System.Windows.Data.PropertyGroupDescription> , указывающее свойство, которое должно быть выполнено группирование. Можно указать свойства в XAML или в коде.  
  
    1.  В XAML задайте <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> имя свойства должно быть выполнено группирование.  
  
    2.  В коде передайте имя свойства для группирования по конструктору.  
  
2.  Добавить <xref:System.Windows.Data.PropertyGroupDescription> для <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> коллекции.  
  
3.  Добавьте дополнительные экземпляры <xref:System.Windows.Data.PropertyGroupDescription> для <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> коллекции для добавления большего количества уровней группировки.  
  
     [!code-xaml[DataGrid_GroupSortFilter#012](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#112](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
     [!code-vb[DataGrid_GroupSortFilter#112](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]  
  
4.  Чтобы удалить группу, удалите <xref:System.Windows.Data.PropertyGroupDescription> из <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> коллекции.  
  
5.  Чтобы удалить все группы, вызовите <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> метод <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> коллекции.  
  
     [!code-csharp[DataGrid_GroupSortFilter#114](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
     [!code-vb[DataGrid_GroupSortFilter#114](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]  
  
 Если элементы группируются в <xref:System.Windows.Controls.DataGrid>, можно определить <xref:System.Windows.Controls.GroupStyle> , определяет внешний вид каждой группы. Можно применить <xref:System.Windows.Controls.GroupStyle> путем добавления его в <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> коллекцию DataGrid. Если у вас есть несколько уровней группирования, можно применить различные стили для каждого уровня. Стили применяются в том порядке, в котором они определены. Например если определить два стиля, первый применяются к группам строк верхнего уровня. Второй стиль будет применен ко всем группам строк на втором уровне и ниже. <xref:System.Windows.FrameworkElement.DataContext%2A> Из <xref:System.Windows.Controls.GroupStyle> — <xref:System.Windows.Data.CollectionViewGroup> , представляющий группу.  
  
#### <a name="to-change-the-appearance-of-row-group-headers"></a>Чтобы изменить внешний вид заголовки групп строк  
  
1.  Создание <xref:System.Windows.Controls.GroupStyle> , определяет внешний вид группы строк.  
  
2.  Поместите <xref:System.Windows.Controls.GroupStyle> внутри `<DataGrid.GroupStyle>` тегов.  
  
     [!code-xaml[DataGrid_GroupSortFilter#003](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]  
  
## <a name="sorting-items-in-a-datagrid"></a>Режим сортировки элементов в элементе управления DataGrid  
 Чтобы указать способ сортировки элементов в <xref:System.Windows.Controls.DataGrid>, использовании <xref:System.ComponentModel.SortDescription> типа для сортировки элементов в представлении источника.  
  
#### <a name="to-sort-items-in-a-datagrid"></a>Для сортировки элементов в элементе управления DataGrid  
  
1.  Создание <xref:System.ComponentModel.SortDescription> , указывающее свойство, по которому выполняется сортировка. Можно указать свойства в XAML или в коде.  
  
    1.  В XAML задайте <xref:System.ComponentModel.SortDescription.PropertyName%2A> имя свойства, по которому выполняется сортировка.  
  
    2.  В коде, передать имя свойства, по которому выполняется сортировка и <xref:System.ComponentModel.ListSortDirection> в конструктор.  
  
2.  Добавить <xref:System.ComponentModel.SortDescription> для <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> коллекции.  
  
3.  Добавьте дополнительные экземпляры <xref:System.ComponentModel.SortDescription> для <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> коллекции для сортировки по дополнительным свойствам.  
  
     [!code-xaml[DataGrid_GroupSortFilter#011](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#211](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
     [!code-vb[DataGrid_GroupSortFilter#211](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]  
  
## <a name="filtering-items-in-a-datagrid"></a>Фильтрация элементов в элементе управления DataGrid  
 Для фильтрации элементов в <xref:System.Windows.Controls.DataGrid> с помощью <xref:System.Windows.Data.CollectionViewSource>, предоставляют логику фильтрации в обработчике <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> событий.  
  
#### <a name="to-filter-items-in-a-datagrid"></a>Чтобы отфильтровать элементы в элементе управления DataGrid  
  
1.  Добавление обработчика для <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> события.  
  
2.  В <xref:System.Windows.Data.CollectionViewSource.Filter> обработчик событий определите логику фильтрации.  
  
     Каждый раз при обновлении представления, будет применяться фильтр.  
  
     [!code-xaml[DataGrid_GroupSortFilter#013](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#113](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
     [!code-vb[DataGrid_GroupSortFilter#113](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]  
  
 Кроме того, можно отфильтровать элементы в <xref:System.Windows.Controls.DataGrid> путем создания метода, который предоставляет логику фильтрации и параметр <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> свойство, чтобы применить фильтр. Пример этого метода см. в разделе [данные фильтра в представлении](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано группирование, сортировка и фильтрация `Task` данные в <xref:System.Windows.Data.CollectionViewSource> и отображение сгруппированных, сортировать и фильтровать `Task` данные в <xref:System.Windows.Controls.DataGrid>. <xref:System.Windows.Data.CollectionViewSource> Используется в качестве <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для <xref:System.Windows.Controls.DataGrid>. Группирование, сортировка и фильтрация выполняются на <xref:System.Windows.Data.CollectionViewSource> и отображаются в <xref:System.Windows.Controls.DataGrid> пользовательского интерфейса.  
  
 Чтобы протестировать этот пример, необходимо изменить имя DGGroupSortFilterExample в соответствии с именем проекта. Если вы используете Visual Basic, необходимо изменить имя класса для <xref:System.Windows.Window> следующее.  
  
 `<Window x:Class="MainWindow"`  
  
 [!code-xaml[DataGrid_GroupSortFilter#000](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]  
  
 [!code-csharp[DataGrid_GroupSortFilter#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
 [!code-vb[DataGrid_GroupSortFilter#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-  
  
## <a name="robust-programming"></a>Отказоустойчивость  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Создание и привязка ObservableCollection](../../../../docs/framework/wpf/data/how-to-create-and-bind-to-an-observablecollection.md)  
 [Фильтрация данных в представлении](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [Сортировка данных в представлении](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [Сортировка и группировка данных с помощью представления в XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
