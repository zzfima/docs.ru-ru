---
title: "Практическое руководство. Группировка, сортировка и фильтрация данных в элементе управления DataGrid"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3c8afacfafbe14794bf17a4e9a4df7c175a3668
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a><span data-ttu-id="3a246-102">Практическое руководство. Группировка, сортировка и фильтрация данных в элементе управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="3a246-102">How to: Group, Sort, and Filter Data in the DataGrid Control</span></span>
<span data-ttu-id="3a246-103">Часто полезно просматривать данные в <xref:System.Windows.Controls.DataGrid> путем группирования, сортировки и фильтрации данных различными способами.</span><span class="sxs-lookup"><span data-stu-id="3a246-103">It is often useful to view data in a <xref:System.Windows.Controls.DataGrid> in different ways by grouping, sorting, and filtering the data.</span></span> <span data-ttu-id="3a246-104">Группировать, сортировать и фильтровать данные в <xref:System.Windows.Controls.DataGrid>, привяжите его к <xref:System.Windows.Data.CollectionView> который поддерживает эти функции.</span><span class="sxs-lookup"><span data-stu-id="3a246-104">To group, sort, and filter the data in a <xref:System.Windows.Controls.DataGrid>, you bind it to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="3a246-105">Вы можете работать с данными в <xref:System.Windows.Data.CollectionView> без изменения базового источника данных.</span><span class="sxs-lookup"><span data-stu-id="3a246-105">You can then work with the data in the <xref:System.Windows.Data.CollectionView> without affecting the underlying source data.</span></span> <span data-ttu-id="3a246-106">Изменения в представлении коллекции отражены в <xref:System.Windows.Controls.DataGrid> пользовательского интерфейса (UI).</span><span class="sxs-lookup"><span data-stu-id="3a246-106">The changes in the collection view are reflected in the <xref:System.Windows.Controls.DataGrid> user interface (UI).</span></span>  
  
 <span data-ttu-id="3a246-107"><xref:System.Windows.Data.CollectionView> Класс предоставляет функции для источника данных, который реализует группировки и сортировки <xref:System.Collections.IEnumerable> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3a246-107">The <xref:System.Windows.Data.CollectionView> class provides grouping and sorting functionality for a data source that implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="3a246-108"><xref:System.Windows.Data.CollectionViewSource> Позволяет задать свойства <xref:System.Windows.Data.CollectionView> из XAML.</span><span class="sxs-lookup"><span data-stu-id="3a246-108">The <xref:System.Windows.Data.CollectionViewSource> class enables you to set the properties of a <xref:System.Windows.Data.CollectionView> from XAML.</span></span>  
  
 <span data-ttu-id="3a246-109">В этом примере коллекция `Task` объектов привязан к <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="3a246-109">In this example, a collection of `Task` objects is bound to a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="3a246-110"><xref:System.Windows.Data.CollectionViewSource> Используется в качестве <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="3a246-110">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="3a246-111">Группирование, сортировка и фильтрация выполняются на <xref:System.Windows.Data.CollectionViewSource> и отображаются в <xref:System.Windows.Controls.DataGrid> пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3a246-111">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>  
  
 <span data-ttu-id="3a246-112">![Сгруппированные данные в элементе управления DataGrid](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF_DataGridGroups")</span><span class="sxs-lookup"><span data-stu-id="3a246-112">![Grouped data in a DataGrid](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF_DataGridGroups")</span></span>  
<span data-ttu-id="3a246-113">Сгруппированные данные в элементе управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="3a246-113">Grouped Data in a DataGrid</span></span>  
  
## <a name="using-a-collectionviewsource-as-an-itemssource"></a><span data-ttu-id="3a246-114">С помощью CollectionViewSource как ItemsSource</span><span class="sxs-lookup"><span data-stu-id="3a246-114">Using a CollectionViewSource as an ItemsSource</span></span>  
 <span data-ttu-id="3a246-115">Для группирования, сортировки и фильтрации данных в <xref:System.Windows.Controls.DataGrid> привязать элемент управления, <xref:System.Windows.Controls.DataGrid> для <xref:System.Windows.Data.CollectionView> который поддерживает эти функции.</span><span class="sxs-lookup"><span data-stu-id="3a246-115">To group, sort, and filter data in a <xref:System.Windows.Controls.DataGrid> control, you bind the <xref:System.Windows.Controls.DataGrid> to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="3a246-116">В этом примере <xref:System.Windows.Controls.DataGrid> привязан к <xref:System.Windows.Data.CollectionViewSource> , предоставляет эти функции для <xref:System.Collections.Generic.List%601> из `Task` объектов.</span><span class="sxs-lookup"><span data-stu-id="3a246-116">In this example, the <xref:System.Windows.Controls.DataGrid> is bound to a <xref:System.Windows.Data.CollectionViewSource> that provides these functions for a <xref:System.Collections.Generic.List%601> of `Task` objects.</span></span>  
  
#### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a><span data-ttu-id="3a246-117">Для привязки элемента управления DataGrid к CollectionViewSource</span><span class="sxs-lookup"><span data-stu-id="3a246-117">To bind a DataGrid to a CollectionViewSource</span></span>  
  
1.  <span data-ttu-id="3a246-118">Создайте коллекцию данных, который реализует <xref:System.Collections.IEnumerable> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3a246-118">Create a data collection that implements the <xref:System.Collections.IEnumerable> interface.</span></span>  
  
     <span data-ttu-id="3a246-119">Если вы используете <xref:System.Collections.Generic.List%601> для создания коллекции, следует создать новый класс, наследующий от <xref:System.Collections.Generic.List%601> вместо экземпляра <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="3a246-119">If you use <xref:System.Collections.Generic.List%601> to create your collection, you should create a new class that inherits from <xref:System.Collections.Generic.List%601> instead of instantiating an instance of <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="3a246-120">Это позволит вам для привязки данных к коллекции в языке XAML.</span><span class="sxs-lookup"><span data-stu-id="3a246-120">This enables you to data bind to the collection in XAML.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a246-121">Объекты в коллекции должны реализовывать <xref:System.ComponentModel.INotifyPropertyChanged> измененный интерфейс и <xref:System.ComponentModel.IEditableObject> интерфейса в порядке для <xref:System.Windows.Controls.DataGrid> правильно реагировать на изменения свойства.</span><span class="sxs-lookup"><span data-stu-id="3a246-121">The objects in the collection must implement the <xref:System.ComponentModel.INotifyPropertyChanged> changed interface and the <xref:System.ComponentModel.IEditableObject> interface in order for the <xref:System.Windows.Controls.DataGrid> to respond correctly to property changes and edits.</span></span> <span data-ttu-id="3a246-122">Дополнительные сведения см. в разделе [Реализация уведомления об изменении свойств](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span><span class="sxs-lookup"><span data-stu-id="3a246-122">For more information, see [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
     [!code-vb[DataGrid_GroupSortFilter#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]  
  
2.  <span data-ttu-id="3a246-123">В XAML, создайте экземпляр класса коллекции и задайте [директива x: Key](../../../../docs/framework/xaml-services/x-key-directive.md).</span><span class="sxs-lookup"><span data-stu-id="3a246-123">In XAML, create an instance of the collection class and set the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md).</span></span>  
  
3.  <span data-ttu-id="3a246-124">В языке XAML, создайте экземпляр класса <xref:System.Windows.Data.CollectionViewSource> класса, задайте [директива x: Key](../../../../docs/framework/xaml-services/x-key-directive.md)и установите экземпляр класса коллекции как <xref:System.Windows.Data.CollectionViewSource.Source%2A>.</span><span class="sxs-lookup"><span data-stu-id="3a246-124">In XAML, create an instance of the <xref:System.Windows.Data.CollectionViewSource> class, set the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md), and set the instance of your collection class as the <xref:System.Windows.Data.CollectionViewSource.Source%2A>.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#201](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]  
  
4.  <span data-ttu-id="3a246-125">Создайте экземпляр класса <xref:System.Windows.Controls.DataGrid> и укажите <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойства <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="3a246-125">Create an instance of the <xref:System.Windows.Controls.DataGrid> class, and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#002](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]  
  
5.  <span data-ttu-id="3a246-126">Чтобы получить доступ к <xref:System.Windows.Data.CollectionViewSource> в коде, используйте <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> метод позволяет получить ссылку на <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="3a246-126">To access the <xref:System.Windows.Data.CollectionViewSource> from your code, use the <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> method to get a reference to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
     [!code-vb[DataGrid_GroupSortFilter#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]  
  
## <a name="grouping-items-in-a-datagrid"></a><span data-ttu-id="3a246-127">Группирование элементов в элементе управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="3a246-127">Grouping items in a DataGrid</span></span>  
 <span data-ttu-id="3a246-128">Чтобы указать способ группировки элементов в <xref:System.Windows.Controls.DataGrid>, использовании <xref:System.Windows.Data.PropertyGroupDescription> типа, чтобы сгруппировать элементы в представлении источника.</span><span class="sxs-lookup"><span data-stu-id="3a246-128">To specify how items are grouped in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.Windows.Data.PropertyGroupDescription> type to group the items in the source view.</span></span>  
  
#### <a name="to-group-items-in-a-datagrid-using-xaml"></a><span data-ttu-id="3a246-129">Для группирования элементов в элементе управления DataGrid, с помощью XAML</span><span class="sxs-lookup"><span data-stu-id="3a246-129">To group items in a DataGrid using XAML</span></span>  
  
1.  <span data-ttu-id="3a246-130">Создание <xref:System.Windows.Data.PropertyGroupDescription> , указывающее свойство, которое должно быть выполнено группирование.</span><span class="sxs-lookup"><span data-stu-id="3a246-130">Create a <xref:System.Windows.Data.PropertyGroupDescription> that specifies the property to group by.</span></span> <span data-ttu-id="3a246-131">Можно указать свойства в XAML или в коде.</span><span class="sxs-lookup"><span data-stu-id="3a246-131">You can specify the property in XAML or in code.</span></span>  
  
    1.  <span data-ttu-id="3a246-132">В XAML задайте <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> имя свойства должно быть выполнено группирование.</span><span class="sxs-lookup"><span data-stu-id="3a246-132">In XAML, set the <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> to the name of the property to group by.</span></span>  
  
    2.  <span data-ttu-id="3a246-133">В коде передайте имя свойства для группирования по конструктору.</span><span class="sxs-lookup"><span data-stu-id="3a246-133">In code, pass the name of the property to group by to the constructor.</span></span>  
  
2.  <span data-ttu-id="3a246-134">Добавить <xref:System.Windows.Data.PropertyGroupDescription> для <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> коллекции.</span><span class="sxs-lookup"><span data-stu-id="3a246-134">Add the <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> collection.</span></span>  
  
3.  <span data-ttu-id="3a246-135">Добавьте дополнительные экземпляры <xref:System.Windows.Data.PropertyGroupDescription> для <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> коллекции для добавления большего количества уровней группировки.</span><span class="sxs-lookup"><span data-stu-id="3a246-135">Add additional instances of <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection to add more levels of grouping.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#012](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#112](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
     [!code-vb[DataGrid_GroupSortFilter#112](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]  
  
4.  <span data-ttu-id="3a246-136">Чтобы удалить группу, удалите <xref:System.Windows.Data.PropertyGroupDescription> из <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="3a246-136">To remove a group, remove the <xref:System.Windows.Data.PropertyGroupDescription> from the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>  
  
5.  <span data-ttu-id="3a246-137">Чтобы удалить все группы, вызовите <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> метод <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="3a246-137">To remove all groups, call the <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> method of the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#114](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
     [!code-vb[DataGrid_GroupSortFilter#114](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]  
  
 <span data-ttu-id="3a246-138">Если элементы группируются в <xref:System.Windows.Controls.DataGrid>, можно определить <xref:System.Windows.Controls.GroupStyle> , определяет внешний вид каждой группы.</span><span class="sxs-lookup"><span data-stu-id="3a246-138">When items are grouped in the <xref:System.Windows.Controls.DataGrid>, you can define a <xref:System.Windows.Controls.GroupStyle> that specifies the appearance of each group.</span></span> <span data-ttu-id="3a246-139">Можно применить <xref:System.Windows.Controls.GroupStyle> путем добавления его в <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> коллекцию DataGrid.</span><span class="sxs-lookup"><span data-stu-id="3a246-139">You apply the <xref:System.Windows.Controls.GroupStyle> by adding it to the <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> collection of the DataGrid.</span></span> <span data-ttu-id="3a246-140">Если у вас есть несколько уровней группирования, можно применить различные стили для каждого уровня.</span><span class="sxs-lookup"><span data-stu-id="3a246-140">If you have multiple levels of grouping, you can apply different styles to each group level.</span></span> <span data-ttu-id="3a246-141">Стили применяются в том порядке, в котором они определены.</span><span class="sxs-lookup"><span data-stu-id="3a246-141">Styles are applied in the order in which they are defined.</span></span> <span data-ttu-id="3a246-142">Например если определить два стиля, первый применяются к группам строк верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="3a246-142">For example, if you define two styles, the first will be applied to top level row groups.</span></span> <span data-ttu-id="3a246-143">Второй стиль будет применен ко всем группам строк на втором уровне и ниже.</span><span class="sxs-lookup"><span data-stu-id="3a246-143">The second style will be applied to all row groups at the second level and lower.</span></span> <span data-ttu-id="3a246-144"><xref:System.Windows.FrameworkElement.DataContext%2A> Из <xref:System.Windows.Controls.GroupStyle> — <xref:System.Windows.Data.CollectionViewGroup> , представляющий группу.</span><span class="sxs-lookup"><span data-stu-id="3a246-144">The <xref:System.Windows.FrameworkElement.DataContext%2A> of the <xref:System.Windows.Controls.GroupStyle> is the <xref:System.Windows.Data.CollectionViewGroup> that the group represents.</span></span>  
  
#### <a name="to-change-the-appearance-of-row-group-headers"></a><span data-ttu-id="3a246-145">Чтобы изменить внешний вид заголовки групп строк</span><span class="sxs-lookup"><span data-stu-id="3a246-145">To change the appearance of row group headers</span></span>  
  
1.  <span data-ttu-id="3a246-146">Создание <xref:System.Windows.Controls.GroupStyle> , определяет внешний вид группы строк.</span><span class="sxs-lookup"><span data-stu-id="3a246-146">Create a <xref:System.Windows.Controls.GroupStyle> that defines the appearance of the row group.</span></span>  
  
2.  <span data-ttu-id="3a246-147">Поместите <xref:System.Windows.Controls.GroupStyle> внутри `<DataGrid.GroupStyle>` тегов.</span><span class="sxs-lookup"><span data-stu-id="3a246-147">Put the <xref:System.Windows.Controls.GroupStyle> inside the `<DataGrid.GroupStyle>` tags.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#003](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]  
  
## <a name="sorting-items-in-a-datagrid"></a><span data-ttu-id="3a246-148">Режим сортировки элементов в элементе управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="3a246-148">Sorting items in a DataGrid</span></span>  
 <span data-ttu-id="3a246-149">Чтобы указать способ сортировки элементов в <xref:System.Windows.Controls.DataGrid>, использовании <xref:System.ComponentModel.SortDescription> типа для сортировки элементов в представлении источника.</span><span class="sxs-lookup"><span data-stu-id="3a246-149">To specify how items are sorted in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.ComponentModel.SortDescription> type to sort the items in the source view.</span></span>  
  
#### <a name="to-sort-items-in-a-datagrid"></a><span data-ttu-id="3a246-150">Для сортировки элементов в элементе управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="3a246-150">To sort items in a DataGrid</span></span>  
  
1.  <span data-ttu-id="3a246-151">Создание <xref:System.ComponentModel.SortDescription> , указывающее свойство, по которому выполняется сортировка.</span><span class="sxs-lookup"><span data-stu-id="3a246-151">Create a <xref:System.ComponentModel.SortDescription> that specifies the property to sort by.</span></span> <span data-ttu-id="3a246-152">Можно указать свойства в XAML или в коде.</span><span class="sxs-lookup"><span data-stu-id="3a246-152">You can specify the property in XAML or in code.</span></span>  
  
    1.  <span data-ttu-id="3a246-153">В XAML задайте <xref:System.ComponentModel.SortDescription.PropertyName%2A> имя свойства, по которому выполняется сортировка.</span><span class="sxs-lookup"><span data-stu-id="3a246-153">In XAML, set the <xref:System.ComponentModel.SortDescription.PropertyName%2A> to the name of the property to sort by.</span></span>  
  
    2.  <span data-ttu-id="3a246-154">В коде, передать имя свойства, по которому выполняется сортировка и <xref:System.ComponentModel.ListSortDirection> в конструктор.</span><span class="sxs-lookup"><span data-stu-id="3a246-154">In code, pass the name of the property to sort by and the <xref:System.ComponentModel.ListSortDirection> to the constructor.</span></span>  
  
2.  <span data-ttu-id="3a246-155">Добавить <xref:System.ComponentModel.SortDescription> для <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> коллекции.</span><span class="sxs-lookup"><span data-stu-id="3a246-155">Add the <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> collection.</span></span>  
  
3.  <span data-ttu-id="3a246-156">Добавьте дополнительные экземпляры <xref:System.ComponentModel.SortDescription> для <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> коллекции для сортировки по дополнительным свойствам.</span><span class="sxs-lookup"><span data-stu-id="3a246-156">Add additional instances of <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> collection to sort by additional properties.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#011](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#211](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
     [!code-vb[DataGrid_GroupSortFilter#211](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]  
  
## <a name="filtering-items-in-a-datagrid"></a><span data-ttu-id="3a246-157">Фильтрация элементов в элементе управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="3a246-157">Filtering items in a DataGrid</span></span>  
 <span data-ttu-id="3a246-158">Для фильтрации элементов в <xref:System.Windows.Controls.DataGrid> с помощью <xref:System.Windows.Data.CollectionViewSource>, предоставляют логику фильтрации в обработчике <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> событий.</span><span class="sxs-lookup"><span data-stu-id="3a246-158">To filter items in a <xref:System.Windows.Controls.DataGrid> using a <xref:System.Windows.Data.CollectionViewSource>, you provide the filtering logic in the handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>  
  
#### <a name="to-filter-items-in-a-datagrid"></a><span data-ttu-id="3a246-159">Чтобы отфильтровать элементы в элементе управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="3a246-159">To filter items in a DataGrid</span></span>  
  
1.  <span data-ttu-id="3a246-160">Добавление обработчика для <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> события.</span><span class="sxs-lookup"><span data-stu-id="3a246-160">Add a handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>  
  
2.  <span data-ttu-id="3a246-161">В <xref:System.Windows.Data.CollectionViewSource.Filter> обработчик событий определите логику фильтрации.</span><span class="sxs-lookup"><span data-stu-id="3a246-161">In the <xref:System.Windows.Data.CollectionViewSource.Filter> event handler, define the filtering logic.</span></span>  
  
     <span data-ttu-id="3a246-162">Каждый раз при обновлении представления, будет применяться фильтр.</span><span class="sxs-lookup"><span data-stu-id="3a246-162">The filter will be applied every time the view is refreshed.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#013](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#113](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
     [!code-vb[DataGrid_GroupSortFilter#113](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]  
  
 <span data-ttu-id="3a246-163">Кроме того, можно отфильтровать элементы в <xref:System.Windows.Controls.DataGrid> путем создания метода, который предоставляет логику фильтрации и параметр <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> свойство, чтобы применить фильтр.</span><span class="sxs-lookup"><span data-stu-id="3a246-163">Alternatively, you can filter items in a <xref:System.Windows.Controls.DataGrid> by creating a method that provides the filtering logic and setting the <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> property to apply the filter.</span></span> <span data-ttu-id="3a246-164">Пример этого метода см. в разделе [данные фильтра в представлении](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).</span><span class="sxs-lookup"><span data-stu-id="3a246-164">To see an example of this method, see [Filter Data in a View](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a246-165">Пример</span><span class="sxs-lookup"><span data-stu-id="3a246-165">Example</span></span>  
 <span data-ttu-id="3a246-166">В следующем примере показано группирование, сортировка и фильтрация `Task` данные в <xref:System.Windows.Data.CollectionViewSource> и отображение сгруппированных, сортировать и фильтровать `Task` данные в <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="3a246-166">The following example demonstrates grouping, sorting, and filtering `Task` data in a <xref:System.Windows.Data.CollectionViewSource> and displaying the grouped, sorted, and filtered `Task` data in a <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="3a246-167"><xref:System.Windows.Data.CollectionViewSource> Используется в качестве <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="3a246-167">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="3a246-168">Группирование, сортировка и фильтрация выполняются на <xref:System.Windows.Data.CollectionViewSource> и отображаются в <xref:System.Windows.Controls.DataGrid> пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3a246-168">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>  
  
 <span data-ttu-id="3a246-169">Чтобы протестировать этот пример, необходимо изменить имя DGGroupSortFilterExample в соответствии с именем проекта.</span><span class="sxs-lookup"><span data-stu-id="3a246-169">To test this example, you will need to adjust the DGGroupSortFilterExample name to match your project name.</span></span> <span data-ttu-id="3a246-170">Если вы используете Visual Basic, необходимо изменить имя класса для <xref:System.Windows.Window> следующее.</span><span class="sxs-lookup"><span data-stu-id="3a246-170">If you are using Visual Basic, you will need to change the class name for <xref:System.Windows.Window> to the following.</span></span>  
  
 `<Window x:Class="MainWindow"`  
  
 [!code-xaml[DataGrid_GroupSortFilter#000](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]  
  
 [!code-csharp[DataGrid_GroupSortFilter#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
 [!code-vb[DataGrid_GroupSortFilter#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3a246-171">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="3a246-171">Compiling the Code</span></span>  
  
-  
  
## <a name="robust-programming"></a><span data-ttu-id="3a246-172">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="3a246-172">Robust Programming</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="3a246-173">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3a246-173">.NET Framework Security</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a246-174">См. также</span><span class="sxs-lookup"><span data-stu-id="3a246-174">See Also</span></span>  
 [<span data-ttu-id="3a246-175">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="3a246-175">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="3a246-176">Создание и привязка ObservableCollection</span><span class="sxs-lookup"><span data-stu-id="3a246-176">Create and Bind to an ObservableCollection</span></span>](../../../../docs/framework/wpf/data/how-to-create-and-bind-to-an-observablecollection.md)  
 [<span data-ttu-id="3a246-177">Фильтрация данных в представлении</span><span class="sxs-lookup"><span data-stu-id="3a246-177">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [<span data-ttu-id="3a246-178">Сортировка данных в представлении</span><span class="sxs-lookup"><span data-stu-id="3a246-178">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [<span data-ttu-id="3a246-179">Сортировка и группировка данных с помощью представления в XAML</span><span class="sxs-lookup"><span data-stu-id="3a246-179">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
