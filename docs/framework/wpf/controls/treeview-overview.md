---
title: Обзор элемента управления "TreeView"
ms.date: 03/30/2017
helpviewer_keywords:
- expanding node [WPF]
- TreeView control [WPF], about TreeView control
- Control class [WPF], TreeView
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
ms.openlocfilehash: f8c49013bc34671ec590f0bd9f84a0f2cf3f9aaf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="treeview-overview"></a>Обзор элемента управления "TreeView"
<xref:System.Windows.Controls.TreeView> Управления обеспечивает способ отображения данных в виде иерархической структуры с использованием свертываемых узлов. В этом разделе описываются <xref:System.Windows.Controls.TreeView> и <xref:System.Windows.Controls.TreeViewItem> элементов управления и простые примеры их использования.  
  
  
<a name="Simple_TreeView_Control"></a>   
## <a name="what-is-a-treeview"></a>Что такое элемент управления TreeView?  
 <xref:System.Windows.Controls.TreeView> — <xref:System.Windows.Controls.ItemsControl> , создает вложенные элементы с помощью <xref:System.Windows.Controls.TreeViewItem> элементов управления. В следующем примере создается <xref:System.Windows.Controls.TreeView>.  
  
 [!code-xaml[TreeViewSnips#EmbeddedTVIs](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>   
## <a name="creating-a-treeview"></a>Создание элемента управления TreeView  
 <xref:System.Windows.Controls.TreeView> Управления содержит иерархию <xref:System.Windows.Controls.TreeViewItem> элементов управления. Объект <xref:System.Windows.Controls.TreeViewItem> управления <xref:System.Windows.Controls.HeaderedItemsControl> с <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> и <xref:System.Windows.Controls.ItemsControl.Items%2A> коллекции.  
  
 При определении <xref:System.Windows.Controls.TreeView> с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], можно явно определять <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> содержимое <xref:System.Windows.Controls.TreeViewItem> элемента управления и элементов, составляющих его коллекции. Этот способ был показан на предыдущем рисунке.  
  
 Можно также указать <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> как данных источника, а затем укажите <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> и <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> для определения <xref:System.Windows.Controls.TreeViewItem> содержимого.  
  
 Чтобы определить макет <xref:System.Windows.Controls.TreeViewItem> управления, можно также использовать <xref:System.Windows.HierarchicalDataTemplate> объектов. Дополнительные сведения и пример см. в разделе [Использование свойств SelectedValue, SelectedValuePath и SelectedItem](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Если элемент не <xref:System.Windows.Controls.TreeViewItem> управления, он автоматически включается в <xref:System.Windows.Controls.TreeViewItem> управления <xref:System.Windows.Controls.TreeView> отображается элемент управления.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>   
## <a name="expanding-and-collapsing-a-treeviewitem"></a>Развертывание и свертывание элемента TreeViewItem  
 Если пользователь разворачивает <xref:System.Windows.Controls.TreeViewItem>, <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> свойству `true`. Можно также развернуть или свернуть <xref:System.Windows.Controls.TreeViewItem> без вмешательства пользователя direct, задав <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> свойства `true` (развернуть) или `false` (свернуть). При изменении этого свойства, <xref:System.Windows.Controls.TreeViewItem.Expanded> или <xref:System.Windows.Controls.TreeViewItem.Collapsed> событием.  
  
 При <xref:System.Windows.FrameworkElement.BringIntoView%2A> метод будет вызван на <xref:System.Windows.Controls.TreeViewItem> управления <xref:System.Windows.Controls.TreeViewItem> и его родительским элементом <xref:System.Windows.Controls.TreeViewItem> разверните элементы управления. Если <xref:System.Windows.Controls.TreeViewItem> не является видимым или частично видимой <xref:System.Windows.Controls.TreeView> прокручивается, чтобы сделать его видимым.  
  
<a name="TreeViewItem_Selection"></a>   
## <a name="treeviewitem-selection"></a>Выбор элемента TreeViewItem  
 Когда пользователь щелкает <xref:System.Windows.Controls.TreeViewItem> управления, чтобы выделить ее, <xref:System.Windows.Controls.TreeViewItem.Selected> происходит событие и его <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> свойству `true`. <xref:System.Windows.Controls.TreeViewItem> Также становится <xref:System.Windows.Controls.TreeView.SelectedItem%2A> из <xref:System.Windows.Controls.TreeView> элемента управления. И наоборот, при изменении выбора из <xref:System.Windows.Controls.TreeViewItem> управления, его <xref:System.Windows.Controls.TreeViewItem.Unselected> событием и его <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> свойству `false`.  
  
 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> Свойства <xref:System.Windows.Controls.TreeView> элемента управления — это свойство только для чтения; таким образом, нельзя явно задать его. <xref:System.Windows.Controls.TreeView.SelectedItem%2A> Свойство имеет значение, если пользователь щелкает <xref:System.Windows.Controls.TreeViewItem> управления или когда <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> свойству `true` на <xref:System.Windows.Controls.TreeViewItem> элемента управления.  
  
 Используйте <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> свойство, чтобы указать <xref:System.Windows.Controls.TreeView.SelectedValue%2A> из <xref:System.Windows.Controls.TreeView.SelectedItem%2A>. Подробнее см. в разделе [Использование свойств SelectedValue, SelectedValuePath и SelectedItem](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Можно зарегистрировать обработчик событий на <xref:System.Windows.Controls.TreeView.SelectedItemChanged> событий, чтобы определить, когда выбранный <xref:System.Windows.Controls.TreeViewItem> изменения. <xref:System.Windows.RoutedPropertyChangedEventArgs%601> , Предоставляется на событие обработчика указывает <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>, это выделение предыдущего элемента и <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, являющееся текущее выделение. Каждое из этих значений может быть равно `null`, если ни предыдущий, ни текущий выбор не были сделаны ни пользователем, ни в приложении.  
  
<a name="TreeView_Style"></a>   
## <a name="treeview-style"></a>Стиль элемента управления TreeView  
 Стиль по умолчанию для <xref:System.Windows.Controls.TreeView> управления помещает его в <xref:System.Windows.Controls.StackPanel> , содержащий <xref:System.Windows.Controls.ScrollViewer> элемента управления. При задании <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства <xref:System.Windows.Controls.TreeView>, эти значения используются для размера <xref:System.Windows.Controls.StackPanel> объекта, который отображает <xref:System.Windows.Controls.TreeView>. Если содержимое для отображения больше, чем область отображения <xref:System.Windows.Controls.ScrollViewer> автоматически отображает, чтобы пользователь мог прокручивать <xref:System.Windows.Controls.TreeView> содержимого.  
  
 Чтобы настроить внешний вид <xref:System.Windows.Controls.TreeViewItem> установите <xref:System.Windows.FrameworkElement.Style%2A> свойства для пользовательского <xref:System.Windows.Style>.  
  
 Следующий пример показывает, как задать <xref:System.Windows.Controls.Control.Foreground%2A> и <xref:System.Windows.Controls.Control.FontSize%2A> значения свойств для <xref:System.Windows.Controls.TreeViewItem> управления с помощью <xref:System.Windows.FrameworkElement.Style%2A>.  
  
 [!code-xaml[TreeViewSimple#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>   
## <a name="adding-images-and-other-content-to-treeview-items"></a>Добавление изображений и другого содержимого в элемент управления TreeView  
 Можно включить несколько объектов в <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> содержимое <xref:System.Windows.Controls.TreeViewItem>. Чтобы включить несколько объектов в <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> содержимое, разместите объекты внутри элемента управления макета, такие как <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.StackPanel>.  
  
 В следующем примере показан способ определения <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> из <xref:System.Windows.Controls.TreeViewItem> как <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.TextBlock> , которые включены в <xref:System.Windows.Controls.DockPanel> элемента управления.  
  
 [!code-xaml[TreeViewSnips#TVIHeader](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 В следующем примере показан способ определения <xref:System.Windows.DataTemplate> , содержащий <xref:System.Windows.Controls.Image> и <xref:System.Windows.Controls.TextBlock> , заключенные в <xref:System.Windows.Controls.DockPanel> элемента управления. Можно использовать <xref:System.Windows.DataTemplate> для задания <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> или <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> для <xref:System.Windows.Controls.TreeViewItem>.  
  
 [!code-xaml[TreeViewDataBinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.TreeView>  
 <xref:System.Windows.Controls.TreeViewItem>  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)  
 [Модель содержимого WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md)
