---
title: "Практическое руководство. Сортировка данных в представлении | Microsoft Docs"
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
  - "привязка данных, группировка данных в представлениях"
  - "привязка данных, сортировка данных в представлениях"
  - "группировка данных в представлениях"
  - "сортировка данных в представлениях"
  - "представления, группирование данных"
  - "представления, сортировка данных"
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Практическое руководство. Сортировка данных в представлении
В этом примере описывается сортировка данных в представлении.  
  
## Пример  
 В следующем примере создаются <xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[ListBoxSort_snip#HowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 Обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> кнопки содержит логику для сортировки элементов в <xref:System.Windows.Controls.ListBox> по убыванию.  Это можно сделать, так как добавление элементов в <xref:System.Windows.Controls.ListBox> таким образом добавляет их в <xref:System.Windows.Controls.ItemCollection> <xref:System.Windows.Controls.ListBox>, и <xref:System.Windows.Controls.ItemCollection> является производным от класса <xref:System.Windows.Data.CollectionView>.  При привязывании <xref:System.Windows.Controls.ListBox> к коллекцию с помощью свойства <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, можно использовать одинаковые технологии для сортировки.  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 До тех пор, пока имеется ссылка на объект представления, можно использовать одинаковые технологии для сортировки содержимого других представлений коллекции.  Пример получения представления см. в разделе [Получение представления по умолчанию для коллекции данных](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).  Другой пример см. в разделе [Сортировка столбцов GridView при нажатии на заголовок](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).  Для получения дополнительных сведений о представлениях см. раздел Привязка к коллекции в [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Пример применения логики сортировки в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] см. в разделе [Сортировка и группировка данных с помощью представления в XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).  
  
## См. также  
 <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>   
 [Сортировка столбцов GridView при нажатии на заголовок](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Фильтрация данных в представлении](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)