---
title: "Практическое руководство. Обработка события MouseDoubleClick для каждого элемента в ListView | Microsoft Docs"
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
  - "ListView - элементы управления, MouseDoubleClick - событие"
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Обработка события MouseDoubleClick для каждого элемента в ListView
Чтобы обработать событие для элемента <xref:System.Windows.Controls.ListView>, необходимо добавить обработчик событий в каждый <xref:System.Windows.Controls.ListViewItem>.  Если <xref:System.Windows.Controls.ListView> привязан к источнику данных, не требуется явное создание <xref:System.Windows.Controls.ListViewItem>, однако, чтобы обработать событие для каждого элемента, добавьте <xref:System.Windows.EventSetter> в стиль <xref:System.Windows.Controls.ListViewItem>.  
  
## Пример  
 В приведенном ниже примере создается <xref:System.Windows.Controls.ListView> с привязкой к данным, а также создается <xref:System.Windows.Style> для добавления обработчика событий в каждый <xref:System.Windows.Controls.ListViewItem>.  
  
 [!code-xml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xml[ListViewHowTos#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 В следующем примере показана обработка события <xref:System.Windows.Controls.Control.MouseDoubleClick>.  
  
 [!code-csharp[ListViewHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  Хотя чаще всего используется привязка <xref:System.Windows.Controls.ListView> к источнику данных, вы можете использовать стиль для добавления обработчика событий в каждый <xref:System.Windows.Controls.ListViewItem> в списке <xref:System.Windows.Controls.ListView> без привязки к данным независимо от того, создан ли <xref:System.Windows.Controls.ListViewItem> явным образом.  Дополнительные сведения о явно и неявно созданных элементах управления <xref:System.Windows.Controls.ListViewItem> см. в разделе <xref:System.Windows.Controls.ItemsControl>.  
  
## См. также  
 <xref:System.Xml.XmlElement>   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Привязка к XML\-данным с помощью XMLDataProvider и запросов XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)   
 [Общие сведения об элементе управления ListView](../../../../docs/framework/wpf/controls/listview-overview.md)