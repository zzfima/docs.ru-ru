---
title: "Практическое руководство. Группировка элементов в объекте ListView, реализующем GridView | Microsoft Docs"
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
  - "GridView - элементы управления, группирование элементов"
  - "группировка элементов в ListView, реализующих GridView"
  - "ListView - элементы управления, группировка элементов в GridView"
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Группировка элементов в объекте ListView, реализующем GridView
В этом примере демонстрируется отображение групп элементов в режиме представления <xref:System.Windows.Controls.GridView> элемента управления <xref:System.Windows.Controls.ListView> .  
  
## Пример  
 Чтобы отобразить группы элементов в <xref:System.Windows.Controls.ListView>, определите <xref:System.Windows.Data.CollectionViewSource>.  В следующем примере показан <xref:System.Windows.Data.CollectionViewSource>, который группирует элементы данных согласно значению поля данных `Catalog`.  
  
 [!code-xml[GridViewWithGroups#GroupingCollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 В следующем примере <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> устанавливается для <xref:System.Windows.Controls.ListView> в <xref:System.Windows.Data.CollectionViewSource>, который определяется в предыдущем примере.  В примере также определяется <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A>, реализующий элемент управления <xref:System.Windows.Controls.Expander>.  
  
 [!code-xml[GridViewWithGroups#ListViewGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xml[GridViewWithGroups#ListViewEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## См. также  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Практические руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Общие сведения об элементе управления ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)