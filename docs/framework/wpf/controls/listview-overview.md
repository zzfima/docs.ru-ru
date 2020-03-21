---
title: Общие сведения об элементе управления ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ListView
- ListView controls [WPF], about ListView control
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
ms.openlocfilehash: 2f336d1eb8dcdfec3c3c8059ba865147c6b6c825
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187523"
---
# <a name="listview-overview"></a>Общие сведения об элементе управления ListView
Элемент <xref:System.Windows.Controls.ListView> управления обеспечивает инфраструктуру для отображения набора элементов данных в различных макетах или представлениях. Например, у пользователя может возникнуть необходимость в отображении элементов данных в таблице, а также в сортировке ее столбцов.  

<a name="WhatisaListView"></a>
## <a name="what-is-a-listview"></a>Понятие об элементе управления ListView  
 Контроль <xref:System.Windows.Controls.ListView> является <xref:System.Windows.Controls.ItemsControl> то, что <xref:System.Windows.Controls.ListBox>происходит от . Как правило, его элементы являются членами <xref:System.Windows.Controls.ListViewItem> сбора данных и представлены в качестве объектов. A <xref:System.Windows.Controls.ListViewItem> является <xref:System.Windows.Controls.ContentControl> и может содержать только один элемент ребенка. Но дочерним может быть любой визуальный элемент.  
  
<a name="DefiningaListViewView"></a>
## <a name="defining-a-view-mode-for-a-listview"></a>Определение режима представления для элемента управления ListView  
 Чтобы указать режим представления для <xref:System.Windows.Controls.ListView> содержимого элемента управления, вы установите свойство. <xref:System.Windows.Controls.ListView.View%2A> Один режим [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] представления, <xref:System.Windows.Controls.GridView>который обеспечивает, который отображает сбор элементов данных в таблице, которая имеет настраиваемые столбцы.  
  
 В следующем примере показано, <xref:System.Windows.Controls.ListView> как определить <xref:System.Windows.Controls.GridView> элемент управления, отображая информацию о сотрудниках.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 На следующем рисунке показано, как будут отображаться данные для предыдущего примера.  
  
 ![Скриншот, на который показан ListView с выходом GridView.](./media/gridview-overview/listview-gridview-output.jpg)  
  
 Можно создать пользовательский режим представления, определив <xref:System.Windows.Controls.ViewBase> класс, который наследует из класса. Класс <xref:System.Windows.Controls.ViewBase> предоставляет инфраструктуру, необходимую для создания пользовательского представления. Дополнительные сведения о создании пользовательского представления см. в разделе [Создание пользовательского режима представления для ListView](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="BindingDatatoaListView"></a>
## <a name="binding-data-to-a-listview"></a>Привязка данных к элементу управления ListView  
 Используйте <xref:System.Windows.Controls.ItemsControl.Items%2A> <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> и свойства для <xref:System.Windows.Controls.ListView> указания элементов для элемента управления. Следующий пример <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> устанавливает свойство к сбору данных, который называется `EmployeeInfoDataSource`.  
  
 [!code-xaml[ListViewCode#ItemsSource](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 В <xref:System.Windows.Controls.GridView>объекты <xref:System.Windows.Controls.GridViewColumn> связываются с указанными полями данных. Следующий пример связывает <xref:System.Windows.Controls.GridViewColumn> объект с полем данных, указывая <xref:System.Windows.Data.Binding> для <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> свойства.  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 Можно также указать <xref:System.Windows.Data.Binding> как <xref:System.Windows.DataTemplate> часть определения, которое используется для стилизации ячеек в столбце. <xref:System.Windows.DataTemplate> В следующем примере, что идентифицируется с наборами <xref:System.Windows.ResourceKey> <xref:System.Windows.Data.Binding> для . <xref:System.Windows.Controls.GridViewColumn> Обратите внимание, что этот <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> пример не определяет, потому <xref:System.Windows.DataTemplate>что это переопределяет привязку, указанную .  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>
## <a name="styling-a-listview-that-implements-a-gridview"></a>Задание стиля ListView, который реализует GridView  
 Элемент <xref:System.Windows.Controls.ListView> ыи управления содержит <xref:System.Windows.Controls.ListViewItem> объекты, представляющие отображаемые элементы данных. Можно использовать следующие свойства для определения содержимого и стиля элементов данных:  
  
- На <xref:System.Windows.Controls.ListView> элементе <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>управления, <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>используйте, и <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> свойства.  
  
- На <xref:System.Windows.Controls.ListViewItem> элементе управления <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> используйте и свойства.  
  
 Чтобы избежать проблем выравнивания <xref:System.Windows.Controls.GridView>между ячейками <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> в, не используйте для установки свойств <xref:System.Windows.Controls.ListView>или добавления содержимого, которое влияет на ширину элемента в . Например, при установке <xref:System.Windows.FrameworkElement.Margin%2A> свойства в <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>заранее может возникнуть проблема выравнивания Чтобы указать свойства или определить содержимое, <xref:System.Windows.Controls.GridView>которое влияет на <xref:System.Windows.Controls.GridView> ширину элементов в, используйте свойства класса и связанные с ним классы, такие как. <xref:System.Windows.Controls.GridViewColumn>  
  
 Для получения дополнительной информации о том, как использовать <xref:System.Windows.Controls.GridView> и его вспомогательные классы, см. [GridView Overview](gridview-overview.md)  
  
 Если вы <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> определяете <xref:System.Windows.Controls.ListView> для управления, <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>а также <xref:System.Windows.Controls.ContentPresenter> определить, вы должны <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> включить в стиле для того, чтобы работать правильно.  
  
 Не используйте <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> свойства <xref:System.Windows.Controls.ListView> и свойства для содержимого, <xref:System.Windows.Controls.GridView>отображаемого с помощью . Чтобы указать выравнивание содержимого <xref:System.Windows.Controls.GridView>в <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>столбце, определить .  
  
<a name="UsingtheSameViewMoreThanOnce"></a>
## <a name="sharing-the-same-view-mode"></a>Совместное использование одного режима представления  
 Два <xref:System.Windows.Controls.ListView> элемента управления не могут совместно снимить один и тот же режим представления одновременно. Если вы попытаетесь использовать один и <xref:System.Windows.Controls.ListView> тот же режим представления с более чем одним элементом управления, происходит исключение.  
  
 Чтобы указать режим представления, который может <xref:System.Windows.Controls.ListView>быть одновременно использован более чем одним, используйте шаблоны или стили.
  
<a name="CreatingaCustomView"></a>
## <a name="creating-a-custom-view-mode"></a>Создание пользовательского режима представления  
 Индивидуальные представления, как <xref:System.Windows.Controls.GridView> являются <xref:System.Windows.Controls.ViewBase> производными от абстрактного класса, <xref:System.Windows.Controls.ListViewItem> который предоставляет инструменты для отображения элементов данных, которые представлены в качестве объектов.
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.GridView>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Data.Binding>
- [Общие сведения о GridView](gridview-overview.md)
- [Как-к темам](listview-how-to-topics.md)
- [Управление](../advanced/optimizing-performance-controls.md)
