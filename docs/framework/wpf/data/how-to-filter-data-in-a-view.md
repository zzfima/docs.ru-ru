---
title: "Практическое руководство. Фильтрация данных в представлении | Microsoft Docs"
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
  - "привязка данных, фильтрация данных в представлениях"
  - "фильтрация данных в представлениях"
  - "представления, фильтрация данных"
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Фильтрация данных в представлении
В этом примере демонстрируется фильтрация данных в представлении.  
  
## Пример  
 Для создания фильтра требуется определить метод, обеспечивающий логику фильтрации.  Метод используется в качестве обратного вызова и принимает аргумент типа `object`.  Следующий метод возвращает все объекты `Order` со свойством `filled`, установленным в «Нет», отфильтровывая остальные объекты.  
  
 [!code-csharp[SortFilter#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 Затем можно применить фильтр, как показано в следующем примере.  В этом примере `myCollectionView` является объектом <xref:System.Windows.Data.ListCollectionView>.  
  
 [!code-csharp[SortFilter#Filter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 Чтобы отменить фильтрацию, следует установить свойство <xref:System.Windows.Data.CollectionView.Filter%2A> в значение `null`:  
  
 [!code-csharp[SortFilter#Unfilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 Сведения о создании или получении представления см. в разделе [Получение представления по умолчанию для коллекции данных](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).  Полный пример см. на веб\-странице [Пример сортировки и фильтрации элементов в представлении](http://go.microsoft.com/fwlink/?LinkID=160040).  
  
 Если объект представления генерируется из объекта <xref:System.Windows.Data.CollectionViewSource>, примените логику фильтрации, установив обработчик событий для события <xref:System.Windows.Data.CollectionViewSource.Filter>.  В следующем примере `listingDataView` представляет собой экземпляр <xref:System.Windows.Data.CollectionViewSource>.  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 Ниже приведена реализация примера обработчика событий фильтра `ShowOnlyBargainsFilter`.  Этот обработчик событий использует свойство <xref:System.Windows.Data.FilterEventArgs.Accepted%2A>, чтобы отфильтровать объекты `AuctionItem`, у которых значение свойства `CurrentPrice` больше или равно $25.  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## См. также  
 <xref:System.Windows.Data.CollectionView.CanFilter%2A>   
 <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Сортировка данных в представлении](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)