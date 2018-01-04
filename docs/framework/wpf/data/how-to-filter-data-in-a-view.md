---
title: "Практическое руководство. Фильтрация данных в представлении"
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
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 17b7fc68319552a7b31d5eaf7826146de5c41aa5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-filter-data-in-a-view"></a>Практическое руководство. Фильтрация данных в представлении
В этом примере показано, как для фильтрации данных в представлении.  
  
## <a name="example"></a>Пример  
 Чтобы создать фильтр, следует определите метод, который предоставляет логику фильтрации. Метод используется в качестве обратного вызова и принимает аргумент типа `object`. Следующий метод возвращает все `Order` объекты с `filled` свойством, имеющим значение «Нет», отфильтровывая остальные объекты.  
  
 [!code-csharp[SortFilter#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 Затем можно применить фильтр, как показано в следующем примере. В этом примере `myCollectionView` — <xref:System.Windows.Data.ListCollectionView> объекта.  
  
 [!code-csharp[SortFilter#Filter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 Чтобы отменить фильтрацию, можно задать <xref:System.Windows.Data.CollectionView.Filter%2A> свойства `null`:  
  
 [!code-csharp[SortFilter#Unfilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 Сведения о создании или получении представления см. в разделе [просмотреть представление по умолчанию сбор данных](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md). Полный пример см. в разделе [Сортировка и фильтрация элементов в просмотр результата](http://go.microsoft.com/fwlink/?LinkID=160040).  
  
 Если объект представления генерируется из <xref:System.Windows.Data.CollectionViewSource> объекта применять логику фильтрации, установив обработчик событий для <xref:System.Windows.Data.CollectionViewSource.Filter> события. В следующем примере `listingDataView` является экземпляром класса <xref:System.Windows.Data.CollectionViewSource>.  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 Ниже показан пример реализации `ShowOnlyBargainsFilter` обработчика событий фильтра. Использует этот обработчик событий <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> свойство, чтобы отфильтровать `AuctionItem` объектов, у которых `CurrentPrice` $ 25 или выше.  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Data.CollectionView.CanFilter%2A>  
 <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Сортировка данных в представлении](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
