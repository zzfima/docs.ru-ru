---
title: Практическое руководство. Получение представления по умолчанию для коллекции данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: e8e6928391a98a132f1dbb39edfda0d73d2eebdb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>Практическое руководство. Получение представления по умолчанию для коллекции данных
Представления позволяют просматривать различными способами, в зависимости от сортировки, фильтрации и группирования критерии одну коллекцию данных. Каждая коллекция имеет одно общее представление по умолчанию, который используется в качестве фактического источника привязки, если привязка задает коллекцию в качестве источника. В этом примере показано, как получить представление коллекции по умолчанию.  
  
## <a name="example"></a>Пример  
 Для создания представления требуется ссылка на объект в коллекцию. Этот объект данных можно получить с помощью ссылки на собственный объект кода путем получения контекста данных, свойства источника данных или свойства привязки. В этом примере показано, как получить <xref:System.Windows.FrameworkElement.DataContext%2A> объекта данных и использовать его для непосредственного получения коллекции по умолчанию просмотра для данной коллекции.  
  
 [!code-csharp[CollectionView#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 В этом примере корневым элементом является <xref:System.Windows.Controls.StackPanel>. <xref:System.Windows.FrameworkElement.DataContext%2A> Задано значение *myDataSource*, которая относится к поставщику данных, <xref:System.Collections.ObjectModel.ObservableCollection%601> из *порядок* объектов.  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 Можно также создать и привязать собственную коллекцию представления с помощью <xref:System.Windows.Data.CollectionViewSource> класса. Это представление коллекции совместно используется только элементами управления, которые привязаны непосредственно к нему. Пример см. в разделе способы создания представления статьи [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Примеры функциональных возможностей, предоставляемых представления коллекции, в разделе [сортировка данных в представлении](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [фильтрации данных в представлении](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md), и [перейдите через объекты данных CollectionView](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## <a name="see-also"></a>См. также  
 [Сортировка и группировка данных с помощью представления в XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
