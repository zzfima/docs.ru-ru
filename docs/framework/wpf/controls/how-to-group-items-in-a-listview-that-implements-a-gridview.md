---
title: "Практическое руководство. Группировка элементов в объекте ListView, реализующем GridView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 30808e8ee0223c31085a65ff025fb188c0132057
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="b0c4d-102">Практическое руководство. Группировка элементов в объекте ListView, реализующем GridView</span><span class="sxs-lookup"><span data-stu-id="b0c4d-102">How to: Group Items in a ListView That Implements a GridView</span></span>
<span data-ttu-id="b0c4d-103">В этом примере показано, как для отображения групп элементов в <xref:System.Windows.Controls.GridView> режим просмотра для <xref:System.Windows.Controls.ListView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b0c4d-103">This example shows how to display groups of items in the <xref:System.Windows.Controls.GridView> view mode of a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0c4d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b0c4d-104">Example</span></span>  
 <span data-ttu-id="b0c4d-105">Для отображения групп элементов в <xref:System.Windows.Controls.ListView>, определить <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="b0c4d-105">To display groups of items in a <xref:System.Windows.Controls.ListView>, define a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="b0c4d-106">В следующем примере показан <xref:System.Windows.Data.CollectionViewSource> , группирует элементы данных согласно значению `Catalog` поля данных.</span><span class="sxs-lookup"><span data-stu-id="b0c4d-106">The following example shows a <xref:System.Windows.Data.CollectionViewSource> that groups data items according to the value of the `Catalog` data field.</span></span>  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 <span data-ttu-id="b0c4d-107">В следующем примере задается <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для <xref:System.Windows.Controls.ListView> для <xref:System.Windows.Data.CollectionViewSource> , определяется в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="b0c4d-107">The following example sets the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.ListView> to the <xref:System.Windows.Data.CollectionViewSource> that the previous example defines.</span></span> <span data-ttu-id="b0c4d-108">В примере также определяется <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> , реализующий <xref:System.Windows.Controls.Expander> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b0c4d-108">The example also defines a <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> that implements an <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a><span data-ttu-id="b0c4d-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b0c4d-109">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="b0c4d-110">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="b0c4d-110">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="b0c4d-111">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="b0c4d-111">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="b0c4d-112">Общие сведения о GridView</span><span class="sxs-lookup"><span data-stu-id="b0c4d-112">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
