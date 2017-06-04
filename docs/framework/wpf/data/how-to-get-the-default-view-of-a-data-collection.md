---
title: "Практическое руководство. Получение представления по умолчанию для коллекции данных | Microsoft Docs"
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
  - "создание, представления коллекций данных"
  - "привязка данных, создание представлений коллекций данных"
  - "коллекции данных, создание представлений"
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Получение представления по умолчанию для коллекции данных
Представления позволяют просматривать одну коллекцию данных различными способами, в зависимости от условий сортировки, фильтрации или группировки.  Для каждой коллекции имеется одно общее представление по умолчанию, которое используется в качестве фактического источника привязки, когда в качестве источника привязки указывается коллекция.  В данном примере показано, как получить представление коллекции по умолчанию.  
  
## Пример  
 Для создания представления требуется ссылка на коллекцию.  Этот объект данных может быть получен с помощью ссылки на объект с выделенным кодом, а также посредством получения контекста данных, свойства источника данных или свойства привязки.  В данном примере показано, как получить контекст <xref:System.Windows.FrameworkElement.DataContext%2A> объекта данных и использовать его для непосредственного получения представления по умолчанию для указанной коллекции.  
  
 [!code-csharp[CollectionView#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 В этом примере корневым элементом является объект <xref:System.Windows.Controls.StackPanel>.  Для свойства <xref:System.Windows.FrameworkElement.DataContext%2A> установлено значение *myDataSource*, которое ссылается на поставщик данных, представляющий собой коллекцию <xref:System.Collections.ObjectModel.ObservableCollection%601> объектов *Order*.  
  
 [!code-xml[CollectionView#CollectionViewDataContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 Кроме того, можно создать экземпляр и выполнить привязку к собственному представлению коллекции с помощью класса <xref:System.Windows.Data.CollectionViewSource>.  Это представление коллекции совместно используется только элементами управления, которые привязаны к нему непосредственно.  Пример см. в разделе "Создание представления" раздела [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Примеры функциональных возможностей, обеспечиваемых представлением коллекции, см. в разделах [Сортировка данных в представлении](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [Фильтрация данных в представлении](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md) и [Перемещение по объектам в Data CollectionView](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## См. также  
 [Сортировка и группировка данных с помощью представления в XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)