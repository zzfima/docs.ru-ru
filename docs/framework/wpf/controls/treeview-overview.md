---
title: Обзор элемента управления "TreeView"
ms.date: 03/30/2017
helpviewer_keywords:
- expanding node [WPF]
- TreeView control [WPF], about TreeView control
- Control class [WPF], TreeView
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
ms.openlocfilehash: 267e870e13d26439e4fbcbba3c5741ff84cabe3c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187372"
---
# <a name="treeview-overview"></a>Обзор элемента управления "TreeView"
Элемент <xref:System.Windows.Controls.TreeView> управления обеспечивает способ отображения информации в иерархической структуре с помощью складных узлов. Эта тема представляет <xref:System.Windows.Controls.TreeView> <xref:System.Windows.Controls.TreeViewItem> и элементы управления, и предоставляет простые примеры их использования.  

<a name="Simple_TreeView_Control"></a>
## <a name="what-is-a-treeview"></a>Что такое элемент управления TreeView?  
 <xref:System.Windows.Controls.TreeView>является, <xref:System.Windows.Controls.ItemsControl> что гнезда элементов с помощью <xref:System.Windows.Controls.TreeViewItem> элементов управления. Следующий пример <xref:System.Windows.Controls.TreeView>создает .  
  
 [!code-xaml[TreeViewSnips#EmbeddedTVIs](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>
## <a name="creating-a-treeview"></a>Создание элемента управления TreeView  
 Элемент <xref:System.Windows.Controls.TreeView> управления содержит иерархию элементов <xref:System.Windows.Controls.TreeViewItem> управления. Контроль <xref:System.Windows.Controls.TreeViewItem> — <xref:System.Windows.Controls.HeaderedItemsControl> это элемент, который имеет <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> и коллекцию. <xref:System.Windows.Controls.ItemsControl.Items%2A>  
  
 Если вы <xref:System.Windows.Controls.TreeView> определяете [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]с помощью, вы <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> можете <xref:System.Windows.Controls.TreeViewItem> четко определить содержимое элемента управления и элементы, которые составляют его коллекцию. Этот способ был показан на предыдущем рисунке.  
  
 Вы также можете <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> указать в качестве <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> источника <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> данных, а затем указать и определить содержимое. <xref:System.Windows.Controls.TreeViewItem>  
  
 Чтобы определить расположение элемента <xref:System.Windows.Controls.TreeViewItem> управления, можно <xref:System.Windows.HierarchicalDataTemplate> также использовать объекты. Дополнительные сведения и пример см. в разделе [Использование свойств SelectedValue, SelectedValuePath и SelectedItem](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Если элемент не <xref:System.Windows.Controls.TreeViewItem> является элементом управления, он <xref:System.Windows.Controls.TreeViewItem> автоматически <xref:System.Windows.Controls.TreeView> прилагается элементом управления при отображении элемента.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>
## <a name="expanding-and-collapsing-a-treeviewitem"></a>Развертывание и свертывание элемента TreeViewItem  
 Если пользователь <xref:System.Windows.Controls.TreeViewItem>расширяет, свойство <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> настроено `true`на . Вы также можете расширить <xref:System.Windows.Controls.TreeViewItem> или свернуть без <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> каких-либо прямых действий пользователя, установив свойство `true` (расширить) или `false` (коллапс). При изменении этого <xref:System.Windows.Controls.TreeViewItem.Expanded> <xref:System.Windows.Controls.TreeViewItem.Collapsed> свойства происходит событие или событие.  
  
 При <xref:System.Windows.FrameworkElement.BringIntoView%2A> вызове метода <xref:System.Windows.Controls.TreeViewItem> управления <xref:System.Windows.Controls.TreeViewItem> контроль и <xref:System.Windows.Controls.TreeViewItem> его родительские элементы расширяются. Если <xref:System.Windows.Controls.TreeViewItem> a не виден или частично <xref:System.Windows.Controls.TreeView> не виден, свитки делают его видимым.  
  
<a name="TreeViewItem_Selection"></a>
## <a name="treeviewitem-selection"></a>Выбор элемента TreeViewItem  
 Когда пользователь <xref:System.Windows.Controls.TreeViewItem> нажимает элемент управления, чтобы выбрать его, `true` <xref:System.Windows.Controls.TreeViewItem.Selected> происходит событие, и его <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> свойство устанавливается. Также <xref:System.Windows.Controls.TreeViewItem> становится <xref:System.Windows.Controls.TreeView.SelectedItem%2A> элементом <xref:System.Windows.Controls.TreeView> управления. И наоборот, когда выбор <xref:System.Windows.Controls.TreeViewItem> изменяется из элемента элемента управления, происходит его <xref:System.Windows.Controls.TreeViewItem.Unselected> событие и его <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> свойство устанавливается. `false`  
  
 Свойство <xref:System.Windows.Controls.TreeView.SelectedItem%2A> на <xref:System.Windows.Controls.TreeView> управлении свойство прочитанное-только; следовательно, вы не можете явно установить его. <xref:System.Windows.Controls.TreeView.SelectedItem%2A> Свойство устанавливается, если пользователь <xref:System.Windows.Controls.TreeViewItem> нажимает <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> на элемент `true` управления <xref:System.Windows.Controls.TreeViewItem> или когда свойство настроено на элемент управления.  
  
 Используйте <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> свойство, <xref:System.Windows.Controls.TreeView.SelectedValue%2A> чтобы <xref:System.Windows.Controls.TreeView.SelectedItem%2A>указать a . Подробнее см. в разделе [Использование свойств SelectedValue, SelectedValuePath и SelectedItem](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Обработчик события можно <xref:System.Windows.Controls.TreeView.SelectedItemChanged> зарегистрировать для определения выбранных <xref:System.Windows.Controls.TreeViewItem> изменений. В <xref:System.Windows.RoutedPropertyChangedEventArgs%601> том, что предоставляется обработчику событий, <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>указывается, <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>что является предыдущим выбором, и , который является текущим выбором. Каждое из этих значений может быть равно `null`, если ни предыдущий, ни текущий выбор не были сделаны ни пользователем, ни в приложении.  
  
<a name="TreeView_Style"></a>
## <a name="treeview-style"></a>Стиль элемента управления TreeView  
 Стиль по умолчанию для элемента <xref:System.Windows.Controls.TreeView> управления помещает его внутри <xref:System.Windows.Controls.StackPanel> объекта, содержащего <xref:System.Windows.Controls.ScrollViewer> элемент управления. При установке <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> и свойств <xref:System.Windows.Controls.TreeView>для объекта эти значения <xref:System.Windows.Controls.StackPanel> используются для <xref:System.Windows.Controls.TreeView>размера объекта, отображаемого. Если содержимое для отображения <xref:System.Windows.Controls.ScrollViewer> больше, чем область дисплея, <xref:System.Windows.Controls.TreeView> автоматически отображается, так что пользователь может прокрутить содержимое.  
  
 Чтобы настроить внешний <xref:System.Windows.Controls.TreeViewItem> вид элемента <xref:System.Windows.FrameworkElement.Style%2A> управления, <xref:System.Windows.Style>установите свойство на пользовательский.  
  
 <xref:System.Windows.Controls.Control.Foreground%2A> Ниже приводится следующий <xref:System.Windows.Controls.Control.FontSize%2A> <xref:System.Windows.Controls.TreeViewItem> <xref:System.Windows.FrameworkElement.Style%2A>пример, как установить значения и свойства для управления с помощью .  
  
 [!code-xaml[TreeViewSimple#8](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>
## <a name="adding-images-and-other-content-to-treeview-items"></a>Добавление изображений и другого содержимого в элемент управления TreeView  
 В <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> содержание <xref:System.Windows.Controls.TreeViewItem>. Чтобы включить несколько объектов в <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> содержимое, приложите <xref:System.Windows.Controls.Panel> объекты к элементу управления макета, такие как или <xref:System.Windows.Controls.StackPanel>.  
  
 Следующий пример показывает, <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> как <xref:System.Windows.Controls.TreeViewItem> определить <xref:System.Windows.Controls.CheckBox> как <xref:System.Windows.Controls.TextBlock> и которые заключены <xref:System.Windows.Controls.DockPanel> в элемент управления.  
  
 [!code-xaml[TreeViewSnips#TVIHeader](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 В следующем примере показано, <xref:System.Windows.DataTemplate> как <xref:System.Windows.Controls.Image> определить, содержащее элемент и <xref:System.Windows.Controls.TextBlock> элемент, заключенный <xref:System.Windows.Controls.DockPanel> в элемент управления. Вы можете <xref:System.Windows.DataTemplate> использовать для <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> установки <xref:System.Windows.Controls.TreeViewItem>или для .  
  
 [!code-xaml[TreeViewDataBinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Как-к темам](treeview-how-to-topics.md)
- [Модель содержимого WPF](wpf-content-model.md)
