---
title: "Практическое руководство. Изменение порядка выравнивания столбцов в элементе управления ListView по горизонтали | Microsoft Docs"
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
  - "ListView - элементы управления, горизонтальное выравнивание"
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Практическое руководство. Изменение порядка выравнивания столбцов в элементе управления ListView по горизонтали
По умолчанию содержимое столбцов объекта <xref:System.Windows.Controls.ListViewItem> выравнивается по левому краю.  Чтобы изменить порядок выравнивания столбцов, определите шаблон <xref:System.Windows.DataTemplate> и установите значение свойства <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> элемента в шаблоне <xref:System.Windows.DataTemplate>.  В этом разделе описывается используемый по умолчанию порядок выравнивания содержимого объекта <xref:System.Windows.Controls.ListView>, а также порядок изменения выравнивания в отдельном столбце объекта <xref:System.Windows.Controls.ListView>.  
  
## Пример  
 В следующем примере содержимое столбцов `Title` и `ISBN` выравнивается по левому краю.  
  
 [!code-xml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Чтобы изменить порядок выравнивания в столбце `ISBN`, установите для свойства <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> каждого объекта <xref:System.Windows.Controls.ListViewItem> значение <xref:System.Windows.HorizontalAlignment>. Это позволяет располагать элементы объекта <xref:System.Windows.Controls.ListViewItem> по всей ширине каждого столбца.  Поскольку объект <xref:System.Windows.Controls.ListView> привязан к источнику данных, необходимо создать стиль, в котором устанавливается свойство <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.  Затем для отображения содержимого необходимо использовать шаблон <xref:System.Windows.DataTemplate> вместо свойства <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>.  Чтобы отобразить значение `ISBN` каждого шаблона, достаточно включить в шаблон <xref:System.Windows.DataTemplate> объект <xref:System.Windows.Controls.TextBlock>, свойству <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> которого присвоено значение <xref:System.Windows.HorizontalAlignment>.  
  
 В следующем примере определяются стиль и шаблон <xref:System.Windows.DataTemplate>, необходимые для выравнивания столбца `ISBN` по правому краю. Кроме того, к объекту <xref:System.Windows.Controls.GridViewColumn> добавляется ссылка на шаблон <xref:System.Windows.DataTemplate>.  
  
 [!code-xml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## См. также  
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Привязка к XML\-данным с помощью XMLDataProvider и запросов XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)   
 [Общие сведения об элементе управления ListView](../../../../docs/framework/wpf/controls/listview-overview.md)