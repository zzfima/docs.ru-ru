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
ms.openlocfilehash: e82d252ed82e4d2e6d641e8b60e890cc93bb0427
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459128"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>Практическое руководство. Получение представления по умолчанию для коллекции данных
Представления позволяют просматривать одну и ту же коллекцию данных различными способами в зависимости от критериев сортировки, фильтрации или группирования. Каждая коллекция имеет одно общее представление по умолчанию, которое используется в качестве фактического источника привязки, когда привязка указывает коллекцию в качестве источника. В этом примере показано, как получить представление коллекции по умолчанию.  
  
## <a name="example"></a>Пример  
 Чтобы создать представление, требуется ссылка на объект коллекции. Этот объект данных можно получить, обратившись к собственному объекту кода программной части, получая контекст данных, получая свойство источника данных или получая свойство привязки. В этом примере показано, как получить <xref:System.Windows.FrameworkElement.DataContext%2A> объекта данных и использовать его для непосредственного получения представления коллекции по умолчанию для этой коллекции.  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 В этом примере корневым элементом является <xref:System.Windows.Controls.StackPanel>. Для <xref:System.Windows.FrameworkElement.DataContext%2A> задано значение *myDataSource*, которое ссылается на поставщик данных, который является <xref:System.Collections.ObjectModel.ObservableCollection%601> объектов *Order* .  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 Кроме того, можно создать экземпляр и выполнить привязку к собственному представлению коллекции с помощью класса <xref:System.Windows.Data.CollectionViewSource>. Это представление коллекции совместно используется только элементами управления, которые привязаны непосредственно к нему. Пример см. в разделе Создание представления в статье [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md).  
  
 Примеры функциональных возможностей, предоставляемых представлением коллекции, см. в разделе [Сортировка данных в](how-to-sort-data-in-a-view.md)представлении, [Фильтрация данных в представлении](how-to-filter-data-in-a-view.md)и [Перемещение по объектам в CollectionView данных](how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## <a name="see-also"></a>См. также

- [Сортировка и группировка данных с помощью представления в XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
