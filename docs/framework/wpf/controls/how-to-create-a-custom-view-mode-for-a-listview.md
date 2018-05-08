---
title: Практическое руководство. Создание пользовательского режима представления для ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: b8600a2e201fdbcb566e6a322e3ecdabbe1641ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>Практическое руководство. Создание пользовательского режима представления для ListView
В этом примере показано, как создать настраиваемый <xref:System.Windows.Controls.ListView.View%2A> режим для <xref:System.Windows.Controls.ListView> элемента управления.  
  
## <a name="example"></a>Пример  
 Необходимо использовать <xref:System.Windows.Controls.ViewBase> класса при создании настраиваемого представления для <xref:System.Windows.Controls.ListView> элемента управления. В следующем примере показан режим просмотра, который называется `PlainView`, который является производным от <xref:System.Windows.Controls.ViewBase> класса.  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 Чтобы применить стиль к пользовательскому представлению, используйте <xref:System.Windows.Style> класса. В следующем примере определяется <xref:System.Windows.Style> для `PlainView` режим просмотра. В предыдущем примере задан в качестве значения <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> свойство, которое определено для `PlainView`.  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 Чтобы определить макет данных в режиме представления, определите <xref:System.Windows.DataTemplate> объекта. В следующем примере определяется <xref:System.Windows.DataTemplate> может использоваться для отображения данных в `PlainView` режиме.  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 В следующем примере показан способ определения <xref:System.Windows.ResourceKey> для `PlainView` режим просмотра, который использует <xref:System.Windows.DataTemplate> , определенный в предыдущем примере.  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 Объект <xref:System.Windows.Controls.ListView> управления можно использовать пользовательское представление, если задать <xref:System.Windows.Controls.ListView.View%2A> свойства ключа ресурса. В следующем примере показано, как указать `PlainView` в режиме отображения для <xref:System.Windows.Controls.ListView>.  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 Полный пример см. в разделе [ListView с несколькими представлениями пример](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Общие сведения об элементе управления ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
