---
title: Практическое руководство. Фильтрация данных в представлении
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: f15bcfd1e3c4175f8b4b97244f120d5edbdec9b8
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453082"
---
# <a name="how-to-filter-data-in-a-view"></a>Практическое руководство. Фильтрация данных в представлении
В этом примере показано, как фильтровать данные в представлении.  
  
## <a name="example"></a>Пример  
 Чтобы создать фильтр, определите метод, который предоставляет логику фильтрации. Метод используется в качестве обратного вызова и принимает параметр типа `object`. Следующий метод возвращает все объекты `Order` со свойством `filled`, для которого задано значение "нет", отфильтровывая остальные объекты.  
  
 [!code-csharp[SortFilter#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 Затем можно применить фильтр, как показано в следующем примере. В этом примере `myCollectionView` является объектом <xref:System.Windows.Data.ListCollectionView>.  
  
 [!code-csharp[SortFilter#Filter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 Чтобы отменить фильтрацию, можно задать для свойства <xref:System.Windows.Data.CollectionView.Filter%2A> значение `null`.  
  
 [!code-csharp[SortFilter#Unfilter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 Сведения о создании или получении представления см. [в разделе Получение представления по умолчанию для коллекции данных](how-to-get-the-default-view-of-a-data-collection.md). Полный пример см. в разделе [Сортировка и фильтрация элементов в образце представления](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/SortFilter).  
  
 Если объект представления поступает из <xref:System.Windows.Data.CollectionViewSource> объекта, логику фильтрации необходимо задать с помощью обработчика событий для события <xref:System.Windows.Data.CollectionViewSource.Filter>. В следующем примере `listingDataView` является экземпляром <xref:System.Windows.Data.CollectionViewSource>.  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 Ниже показана реализация примера обработчика событий фильтра `ShowOnlyBargainsFilter`. Этот обработчик событий использует свойство <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> для фильтрации `AuctionItem` объектов, имеющих `CurrentPrice` $25 или более.  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Сортировка данных в представлении](how-to-sort-data-in-a-view.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
