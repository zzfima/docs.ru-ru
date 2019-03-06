---
title: Практическое руководство. Группировка элементов в объекте ListView, реализующем GridView
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
ms.openlocfilehash: 3989f0fcdaf2e3d3003aca9feb27cbf02f949389
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364480"
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a>Практическое руководство. Группировка элементов в объекте ListView, реализующем GridView
В этом примере показано, как для отображения групп элементов в <xref:System.Windows.Controls.GridView> режим просмотра <xref:System.Windows.Controls.ListView> элемента управления.  
  
## <a name="example"></a>Пример  
 Для отображения групп элементов в <xref:System.Windows.Controls.ListView>, определить <xref:System.Windows.Data.CollectionViewSource>. В следующем примере показан <xref:System.Windows.Data.CollectionViewSource> , группирует элементы данных согласно значению `Catalog` поля данных.  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 В следующем примере задается <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для <xref:System.Windows.Controls.ListView> для <xref:System.Windows.Data.CollectionViewSource> , определяется в предыдущем примере. В примере также определяется <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> , реализующий <xref:System.Windows.Controls.Expander> элемента управления.  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Разделы практического руководства](listview-how-to-topics.md)
- [Общие сведения об элементе управления ListView](listview-overview.md)
- [Общие сведения о GridView](gridview-overview.md)
