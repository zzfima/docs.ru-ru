---
title: "Общие сведения об элементе управления ListView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ListView
- ListView controls [WPF], about ListView control
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62144217199a62da3e41bf381162c94c91d00e72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="listview-overview"></a>Общие сведения об элементе управления ListView
<xref:System.Windows.Controls.ListView> Управления предоставляет инфраструктуру для отображения набора элементов данных в различных макетах или представлениях. Например, у пользователя может возникнуть необходимость в отображении элементов данных в таблице, а также в сортировке ее столбцов.  
  
  
<a name="WhatisaListView"></a>   
## <a name="what-is-a-listview"></a>Понятие об элементе управления ListView  
 <xref:System.Windows.Controls.ListView> Управления <xref:System.Windows.Controls.ItemsControl> , производный от <xref:System.Windows.Controls.ListBox>. Как правило, его элементы являются элементами коллекции данных и представляются в виде <xref:System.Windows.Controls.ListViewItem> объектов. Объект <xref:System.Windows.Controls.ListViewItem> — <xref:System.Windows.Controls.ContentControl> и может содержать только один дочерний элемент. Но дочерним может быть любой визуальный элемент.  
  
<a name="DefiningaListViewView"></a>   
## <a name="defining-a-view-mode-for-a-listview"></a>Определение режима представления для элемента управления ListView  
 Чтобы задать режим просмотра содержимого <xref:System.Windows.Controls.ListView> управления, задать <xref:System.Windows.Controls.ListView.View%2A> свойства. Одним из режимов, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет является <xref:System.Windows.Controls.GridView>, который отображает коллекцию элементов данных в таблице с настраиваемыми столбцами.  
  
 В следующем примере показан способ определения <xref:System.Windows.Controls.GridView> для <xref:System.Windows.Controls.ListView> элемент управления, отображающий сведения о сотрудниках.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 На следующем рисунке показано, как будут отображаться данные для предыдущего примера.  
  
 ![ListView с выходными данными GridView](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")  
  
 Можно создать настраиваемого режима, определив класс, наследующий от <xref:System.Windows.Controls.ViewBase> класса. <xref:System.Windows.Controls.ViewBase> Класс предоставляет инфраструктуру, необходимо создать пользовательское представление. Дополнительные сведения о создании пользовательского представления см. в разделе [Создание пользовательского режима представления для ListView](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="BindingDatatoaListView"></a>   
## <a name="binding-data-to-a-listview"></a>Привязка данных к элементу управления ListView  
 Используйте <xref:System.Windows.Controls.ItemsControl.Items%2A> и <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойства, чтобы указать элементы для <xref:System.Windows.Controls.ListView> элемента управления. В следующем примере задается <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойство коллекции данных, которая называется `EmployeeInfoDataSource`.  
  
 [!code-xaml[ListViewCode#ItemsSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 В <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn> объекты привязки к полям указанных данных. Следующий пример привязывает <xref:System.Windows.Controls.GridViewColumn> объект для поля данных, указав <xref:System.Windows.Data.Binding> для <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> свойства.  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 Можно также указать <xref:System.Windows.Data.Binding> как часть <xref:System.Windows.DataTemplate> определение, которое используется для стиля ячеек в столбце. В следующем примере <xref:System.Windows.DataTemplate> , отмечаются <xref:System.Windows.ResourceKey> задает <xref:System.Windows.Data.Binding> для <xref:System.Windows.Controls.GridViewColumn>. Обратите внимание, что в этом примере не определяет <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> , так как это переопределяет привязки, который задается параметром <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>   
## <a name="styling-a-listview-that-implements-a-gridview"></a>Задание стиля ListView, который реализует GridView  
 <xref:System.Windows.Controls.ListView> Управления содержит <xref:System.Windows.Controls.ListViewItem> объектов, которые представляют элементы данных, которые отображаются. Можно использовать следующие свойства для определения содержимого и стиля элементов данных:  
  
-   На <xref:System.Windows.Controls.ListView> управления, используйте <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>, и <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> свойства.  
  
-   На <xref:System.Windows.Controls.ListViewItem> управления, используйте <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> и <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> свойства.  
  
 Чтобы избежать проблем с выравниванием между ячейками в <xref:System.Windows.Controls.GridView>, не используйте <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> для установки свойства или добавьте содержимое, которое влияет на ширину элемента в <xref:System.Windows.Controls.ListView>. Например, может возникнуть проблема выравнивания при установке <xref:System.Windows.FrameworkElement.Margin%2A> свойства <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>. Для указания свойств или определить содержимое, которое влияет на ширину элементов в <xref:System.Windows.Controls.GridView>, используйте свойства <xref:System.Windows.Controls.GridView> класс и его связанных классов, таких как <xref:System.Windows.Controls.GridViewColumn>.  
  
 Дополнительные сведения об использовании <xref:System.Windows.Controls.GridView> и вспомогательные классы, в разделе [GridView Обзор](../../../../docs/framework/wpf/controls/gridview-overview.md).  
  
 При определении <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> для <xref:System.Windows.Controls.ListView> управления, а также определяют <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, необходимо включить <xref:System.Windows.Controls.ContentPresenter> в стиле в порядке для <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> для правильной работы.  
  
 Не используйте <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> и <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> свойства <xref:System.Windows.Controls.ListView> содержимое, которое отображается с помощью <xref:System.Windows.Controls.GridView>. Чтобы задать выравнивание содержимого в столбце <xref:System.Windows.Controls.GridView>, определить <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>.  
  
<a name="UsingtheSameViewMoreThanOnce"></a>   
## <a name="sharing-the-same-view-mode"></a>Совместное использование одного режима представления  
 Два <xref:System.Windows.Controls.ListView> элементы управления не могут совместно использовать один режим, в то же время. При попытке использовать один и тот же режим представления с более чем одним <xref:System.Windows.Controls.ListView> управления, возникает исключение.  
  
 Чтобы указать режим представления, который может использоваться одновременно более чем одной <xref:System.Windows.Controls.ListView>, используйте шаблоны или стили. Пример определения представления как <xref:System.Windows.FrameworkElement.Resources%2A>, в разделе [ListView с несколькими представлениями пример](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
<a name="CreatingaCustomView"></a>   
## <a name="creating-a-custom-view-mode"></a>Создание пользовательского режима представления  
 Настраиваемые представления, такие как <xref:System.Windows.Controls.GridView> являются производными от <xref:System.Windows.Controls.ViewBase> абстрактный класс, который предоставляет средства для отображения элементов данных, которые представлены в виде <xref:System.Windows.Controls.ListViewItem> объектов.  
  
 Пример пользовательского режима представления см. в разделе [Пример ListView с возможностью нескольких представлений](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.GridView>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.ListViewItem>  
 <xref:System.Windows.Data.Binding>  
 [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Элементы управления](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
