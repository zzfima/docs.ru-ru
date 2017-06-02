---
title: "Общие сведения об элементе управления ListView | Microsoft Docs"
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
  - "элементы управления, ListView"
  - "ListView - элементы управления [WPF], об элементе управления ListView"
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Общие сведения об элементе управления ListView
Элемент управления <xref:System.Windows.Controls.ListView> предоставляет инфраструктуру для отображения набора элементов данных в различных макетах или представлениях.  Например, у пользователя может возникнуть потребность в отображении элементов данных в таблице, а также в сортировке ее столбцов.  
  
   
  
<a name="WhatisaListView"></a>   
## Понятие об элементе управления ListView  
 Элемент управления <xref:System.Windows.Controls.ListView> является <xref:System.Windows.Controls.ItemsControl>, который является производным от <xref:System.Windows.Controls.ListBox>.  Как правило, его элементы являются членами коллекции данных и представляются как объекты <xref:System.Windows.Controls.ListViewItem>.  <xref:System.Windows.Controls.ListViewItem> является <xref:System.Windows.Controls.ContentControl> и может содержать только один дочерний элемент.  Однако дочерним элементом может быть любой визуальный элемент.  
  
<a name="DefiningaListViewView"></a>   
## Определение режима представления для элемента управления ListView  
 Чтобы задать режим просмотра содержимого элемента управления <xref:System.Windows.Controls.ListView>, необходимо задать значение свойства <xref:System.Windows.Controls.ListView.View%2A>.  Одним из режимов, предоставляемых [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], является <xref:System.Windows.Controls.GridView>, отображающий коллекцию элементов данных в таблице с настраиваемыми столбцами.  
  
 В следующем примере показано определение <xref:System.Windows.Controls.GridView> для элемента управления <xref:System.Windows.Controls.ListView>, в котором отображаются сведения о сотруднике.  
  
 [!code-xml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 На следующем рисунке показано, как будут отображаться данные для предыдущего примера.  
  
 ![ListView с выводом GridView](../../../../docs/framework/wpf/controls/media/listviewgridview.png "ListViewGridView")  
  
 Можно создать пользовательский режим представления путем определения класса, наследуемого от класса <xref:System.Windows.Controls.ViewBase>.  Класс <xref:System.Windows.Controls.ViewBase> предоставляет инфраструктуру, которая необходима для создания пользовательского режима представления.  Дополнительные сведения о создании пользовательского представления см. в разделе [Создание пользовательского режима представления для ListView](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="BindingDatatoaListView"></a>   
## Привязка данных к элементу управления ListView  
 Используйте свойства <xref:System.Windows.Controls.ItemsControl.Items%2A> и <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, чтобы указать элементы для элемента управления <xref:System.Windows.Controls.ListView>.  В следующем примере свойству <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> присваивается значение коллекции данных, которая называется `EmployeeInfoDataSource`.  
  
 [!code-xml[ListViewCode#ItemsSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 В <xref:System.Windows.Controls.GridView> объекты <xref:System.Windows.Controls.GridViewColumn> привязаны к заданным полям данных.  В следующем примере объект <xref:System.Windows.Controls.GridViewColumn> привязывается к полю данных путем указания <xref:System.Windows.Data.Binding> для свойства <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>.  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xml[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 Можно также указать <xref:System.Windows.Data.Binding> как часть определения <xref:System.Windows.DataTemplate>, предназначенного для применения стиля к ячейкам столбца.  В следующем примере <xref:System.Windows.DataTemplate>, который идентифицируется с помощью ключа <xref:System.Windows.ResourceKey>, задает <xref:System.Windows.Data.Binding> для <xref:System.Windows.Controls.GridViewColumn>.  Обратите внимание, что в этом примере не определен <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>, так как это переопределяет привязку, заданную <xref:System.Windows.DataTemplate>.  
  
 [!code-xml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>   
## Применение стилей к ListView, реализующему GridView  
 Элемент управления <xref:System.Windows.Controls.ListView> содержит объекты <xref:System.Windows.Controls.ListViewItem>, представляющие отображаемые элементы данных.  Можно использовать следующие свойства для определения содержимого и стиля элементов данных:  
  
-   Для элемента управления <xref:System.Windows.Controls.ListView> используйте свойства <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> и <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>.  
  
-   Для элемента управления <xref:System.Windows.Controls.ListViewItem> используйте свойства <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> и <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>.  
  
 Чтобы избежать проблем выравнивания между ячейками в <xref:System.Windows.Controls.GridView>, не используйте <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> для задания свойств или добавление содержимого, которое влияет на ширину элемента в <xref:System.Windows.Controls.ListView>.  Например, может возникнуть проблема выравнивания при задании свойства <xref:System.Windows.FrameworkElement.Margin%2A> в <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>.  Чтобы задать свойства или определить содержимое, которое влияет на ширину элементов в <xref:System.Windows.Controls.GridView>, используйте свойства класса <xref:System.Windows.Controls.GridView> и его связанных классов, таких как <xref:System.Windows.Controls.GridViewColumn>.  
  
 Дополнительные сведения о том, как использовать <xref:System.Windows.Controls.GridView> и его вспомогательные классы, см. в разделе [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md).  
  
 Если определить <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> для элемента управления <xref:System.Windows.Controls.ListView> и также определить <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, необходимо включить <xref:System.Windows.Controls.ContentPresenter> в стиль для правильной работы <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.  
  
 Не используйте свойства <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> и <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> для содержимого <xref:System.Windows.Controls.ListView>, которое отображается с помощью <xref:System.Windows.Controls.GridView>.  Чтобы задать выравнивание содержимого в столбце <xref:System.Windows.Controls.GridView>, определите свойство <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>.  
  
<a name="UsingtheSameViewMoreThanOnce"></a>   
## Совместное использование одного режима представления  
 Два элемента управления <xref:System.Windows.Controls.ListView> не могут совместно использовать один режим в одно и то же время.  При попытке использования одного режима более, чем одним элементом управления <xref:System.Windows.Controls.ListView> возникает исключение.  
  
 Чтобы указать режим представления, который может одновременно использоваться более, чем одним <xref:System.Windows.Controls.ListView>, используйте шаблоны или стили.  Пример определения представления как свойства <xref:System.Windows.FrameworkElement.Resources%2A> см. в разделе [Пример "ListView with Multiple Views"](http://go.microsoft.com/fwlink/?LinkID=160013.).  
  
<a name="CreatingaCustomView"></a>   
## Создание настраиваемого режима представления  
 Настраиваемые представления, такие как <xref:System.Windows.Controls.GridView>, являются производными от абстрактного класса <xref:System.Windows.Controls.ViewBase>, который предоставляет средства для отображения элементов данных, представленных как объекты <xref:System.Windows.Controls.ListViewItem>.  
  
 Пример настраиваемого режима представления см. в разделе [Пример "ListView with Multiple Views"](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
## См. также  
 <xref:System.Windows.Controls.GridView>   
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.ListViewItem>   
 <xref:System.Windows.Data.Binding>   
 [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Элементы управления](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)