---
title: "Практическое руководство. Перемещение по объектам в Data CollectionView | Microsoft Docs"
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
  - "CollectionView, переходы по объектам"
  - "привязка данных, перемещение по объектам в data CollectionView"
  - "перемещение по объектам в data CollectionView"
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Перемещение по объектам в Data CollectionView
Представления позволяют просматривать одну коллекцию данных различными способами, в зависимости от сортировки, фильтрации или группировки.  Представления также предоставляют концепцию указателя на текущую запись и включают перемещение указателя.  В этом примере демонстрируется получение текущего объекта и перемещение по объектам в коллекции данных с помощью функциональных возможностей, предоставленных в классе <xref:System.Windows.Data.CollectionView>.  
  
## Пример  
 В этом примере `myCollectionView` является объектом <xref:System.Windows.Data.CollectionView>, который является представлением присоединенной коллекции.  
  
 В следующем примере `OnButton` является обработчиком событий для кнопок `Previous` `Next` в приложении, которые представляют собой кнопки, позволяющие пользователю перемещаться по коллекции данных.  Обратите внимание, что свойства <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> и <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> сообщают о том, установлен ли указатель текущей записи в начало и конец списка, чтобы <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> и <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> могли быть вызваны соответствующим образом.  
  
 Свойство <xref:System.Windows.Data.CollectionView.CurrentItem%2A> представления приводится в качестве `Order` для возврата текущего элемента коллекции.  
  
 [!code-csharp[CollectionView#OnButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## См. также  
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Сортировка данных в представлении](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)   
 [Фильтрация данных в представлении](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)   
 [Сортировка и группировка данных с помощью представления в XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)