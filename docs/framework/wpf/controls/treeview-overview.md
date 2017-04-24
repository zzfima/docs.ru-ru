---
title: "Обзор элемента управления &quot;TreeView&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Control - класс, TreeView"
  - "расширение узла"
  - "TreeView - элемент управления, об элементе управления TreeView"
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 32
---
# Обзор элемента управления &quot;TreeView&quot;
Элемент управления <xref:System.Windows.Controls.TreeView> предоставляет способ для отображения данных в виде иерархической структуры с помощью сворачиваемых узлов.  В этом разделе рассматриваются элементы управления <xref:System.Windows.Controls.TreeView> и <xref:System.Windows.Controls.TreeViewItem> и даны простые примеры их использования.  
  
   
  
<a name="Simple_TreeView_Control"></a>   
## Что такое элемент управления "TreeView"?  
 Элемент управления <xref:System.Windows.Controls.TreeView> — это объект <xref:System.Windows.Controls.ItemsControl>, который выполняет вложение элементов с помощью элементов управления <xref:System.Windows.Controls.TreeViewItem>.  В следующем примере создается объект <xref:System.Windows.Controls.TreeView>.  
  
 [!code-xml[TreeViewSnips#EmbeddedTVIs](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>   
## Создание элемента управления "TreeView"  
 Элемент управления <xref:System.Windows.Controls.TreeView> содержит иерархию элементов управления <xref:System.Windows.Controls.TreeViewItem>.  Элемент управления <xref:System.Windows.Controls.TreeViewItem> — это объект <xref:System.Windows.Controls.HeaderedItemsControl>, который имеет свойство <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> и содержит коллекцию <xref:System.Windows.Controls.ItemsControl.Items%2A>.  
  
 При определении <xref:System.Windows.Controls.TreeView> с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] можно явно определить содержимое <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> элемента управления <xref:System.Windows.Controls.TreeViewItem> и элементы, составляющие его коллекцию.  На предыдущем рисунке показан этот метод.  
  
 Можно также указать <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> в качестве источника данных и затем указать свойства <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> и <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> для определения содержимого <xref:System.Windows.Controls.TreeViewItem>.  
  
 Для определения макета элемента управления <xref:System.Windows.Controls.TreeViewItem> можно также использовать объекты <xref:System.Windows.HierarchicalDataTemplate>.  Дополнительные сведения и пример см. в разделе [Использование SelectedValue, SelectedValuePath и SelectedItem](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Если элемент не является элементом управления <xref:System.Windows.Controls.TreeViewItem>, он автоматически включается в элемент управления <xref:System.Windows.Controls.TreeViewItem> при отображении элемента управления <xref:System.Windows.Controls.TreeView>.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>   
## Развертывание и свертывание узлов "TreeViewItem"  
 Если пользователь разворачивает узел <xref:System.Windows.Controls.TreeViewItem>, для свойства <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> устанавливается значение `true`.  Можно также развернуть или свернуть <xref:System.Windows.Controls.TreeViewItem> без участия пользователя, установив для свойства <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> значение `true` \(развернуть\) или `false` \(свернуть\).  При изменении этого свойства создается событие <xref:System.Windows.Controls.TreeViewItem.Expanded> или <xref:System.Windows.Controls.TreeViewItem.Collapsed>.  
  
 При вызове метода <xref:System.Windows.FrameworkElement.BringIntoView%2A> в элементе управления <xref:System.Windows.Controls.TreeViewItem>, <xref:System.Windows.Controls.TreeViewItem> и его родительский элемент управления <xref:System.Windows.Controls.TreeViewItem> разворачиваются.  Если элемент управления <xref:System.Windows.Controls.TreeViewItem> скрыт или частично скрыт, элемент управления <xref:System.Windows.Controls.TreeView> прокручивается, чтобы сделать его видимым.  
  
<a name="TreeViewItem_Selection"></a>   
## Выбор элемента управления "TreeViewItem"  
 Когда пользователь щелкает элемент управления <xref:System.Windows.Controls.TreeViewItem>, чтобы его выделить, создается событие <xref:System.Windows.Controls.TreeViewItem.Selected>, и для свойства <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> элемента управления устанавливается значение `true`.  Элемент <xref:System.Windows.Controls.TreeViewItem> также становится свойством <xref:System.Windows.Controls.TreeView.SelectedItem%2A> элемента управления <xref:System.Windows.Controls.TreeView>.  И наоборот, при изменении выбора элемента управления <xref:System.Windows.Controls.TreeViewItem> создается событие <xref:System.Windows.Controls.TreeViewItem.Unselected> и для свойства <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> устанавливается значение `false`.  
  
 Свойство <xref:System.Windows.Controls.TreeView.SelectedItem%2A> элемента управления <xref:System.Windows.Controls.TreeView> доступно только для чтения; поэтому его нельзя установить явно.  Свойство <xref:System.Windows.Controls.TreeView.SelectedItem%2A> устанавливается, если пользователь щелкает элемент управления <xref:System.Windows.Controls.TreeViewItem> или свойству <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> элемента управления <xref:System.Windows.Controls.TreeViewItem> присваивается значение `true`.  
  
 Используйте свойство <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> для указания <xref:System.Windows.Controls.TreeView.SelectedValue%2A> свойства <xref:System.Windows.Controls.TreeView.SelectedItem%2A>.  Дополнительные сведения см. в разделе [Использование SelectedValue, SelectedValuePath и SelectedItem](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Можно зарегистрировать обработчик событий для события <xref:System.Windows.Controls.TreeView.SelectedItemChanged>, чтобы определить, когда изменяется выбранный объект <xref:System.Windows.Controls.TreeViewItem>.  Параметр <xref:System.Windows.RoutedPropertyChangedEventArgs%601>, который предоставляется обработчику событий, указывает значение <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>, которое является предыдущим выбором, и значение <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, представляющее текущий выбор.  Любое из двух значений может быть `null`, если предыдущий или текущий выбор не выполнен приложением или пользователем.  
  
<a name="TreeView_Style"></a>   
## Стиль элемента управления "TreeView"  
 По умолчанию стиль элемента управления <xref:System.Windows.Controls.TreeView> помещает его в объект <xref:System.Windows.Controls.StackPanel>, содержащий элемент управления <xref:System.Windows.Controls.ScrollViewer>.  При установке свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> для элемента управления <xref:System.Windows.Controls.TreeView> эти значения используются для изменения размера объекта <xref:System.Windows.Controls.StackPanel>, отображающего элемент управления <xref:System.Windows.Controls.TreeView>.  Если содержимое для отображения больше, чем область отображения, автоматически отображается элемент управления <xref:System.Windows.Controls.ScrollViewer>, чтобы пользователь мог прокручивать содержимое <xref:System.Windows.Controls.TreeView>.  
  
 Для настройки внешнего вида элемента управления <xref:System.Windows.Controls.TreeViewItem> установите для свойства <xref:System.Windows.FrameworkElement.Style%2A> пользовательский класс <xref:System.Windows.Style>.  
  
 В следующем примере показано, как установить значения свойств <xref:System.Windows.Controls.Control.Foreground%2A> и <xref:System.Windows.Controls.Control.FontSize%2A> для элемента управления <xref:System.Windows.Controls.TreeViewItem> с помощью свойства <xref:System.Windows.FrameworkElement.Style%2A>.  
  
 [!code-xml[TreeViewSimple#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>   
## Добавление изображений и другого содержимого в элементы "TreeView"  
 В содержимое <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> элемента управления <xref:System.Windows.Controls.TreeViewItem> можно включить несколько объектов.  Чтобы включить несколько объектов в содержимое <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>, разместите объекты внутри элемента управления макета, такого как <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.StackPanel>.  
  
 В следующем примере показано определение свойства <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> для элемента управления <xref:System.Windows.Controls.TreeViewItem> в качестве объектов <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.TextBlock>, которые включены в элемент управления <xref:System.Windows.Controls.DockPanel>.  
  
 [!code-xml[TreeViewSnips#TVIHeader](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 В следующем примере показано определение объекта <xref:System.Windows.DataTemplate>, содержащего объекты <xref:System.Windows.Controls.Image> и <xref:System.Windows.Controls.TextBlock>, включенные в элемент управления <xref:System.Windows.Controls.DockPanel>.  Чтобы установить свойство <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> или <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> для элемента управления <xref:System.Windows.Controls.TreeViewItem>, можно использовать объект <xref:System.Windows.DataTemplate>.  
  
 [!code-xml[TreeViewDataBinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## См. также  
 <xref:System.Windows.Controls.TreeView>   
 <xref:System.Windows.Controls.TreeViewItem>   
 [Практические руководства](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)   
 [Модель содержимого WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md)