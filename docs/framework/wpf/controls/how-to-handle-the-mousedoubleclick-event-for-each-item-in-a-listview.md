---
title: Практическое руководство. Обработка события MouseDoubleClick для каждого элемента в ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 7e51c810a2e1e4bf4157aa1311255c5547021b60
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962065"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Практическое руководство. Обработка события MouseDoubleClick для каждого элемента в ListView
Для обработки события элемента в <xref:System.Windows.Controls.ListView>необходимо добавить в каждый из них <xref:System.Windows.Controls.ListViewItem>обработчик событий. Если привязка привязана к источнику данных, то вы не <xref:System.Windows.Controls.ListViewItem>создаете, но можете Обрабатывайте событие для <xref:System.Windows.EventSetter> каждого элемента, добавив в стиль <xref:System.Windows.Controls.ListViewItem>. <xref:System.Windows.Controls.ListView>  
  
## <a name="example"></a>Пример  
 В следующем примере создается привязка <xref:System.Windows.Controls.ListView> <xref:System.Windows.Style> к данным и создается, чтобы добавить в каждый <xref:System.Windows.Controls.ListViewItem>обработчик событий.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 В следующем примере обрабатывается <xref:System.Windows.Controls.Control.MouseDoubleClick> событие.  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> Несмотря на то, что наиболее распространена <xref:System.Windows.Controls.ListView> привязка к источнику данных, можно использовать стиль для добавления обработчика событий в каждый <xref:System.Windows.Controls.ListViewItem> объект в не привязанных к <xref:System.Windows.Controls.ListView> данным данных <xref:System.Windows.Controls.ListViewItem>независимо от того, был ли явно создан.  Дополнительные сведения о явно и неявно созданных <xref:System.Windows.Controls.ListViewItem> элементах управления см. в разделе. <xref:System.Windows.Controls.ItemsControl>  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.XmlElement>
- [Общие сведения о привязке данных](../data/data-binding-overview.md)
- [Стилизация и использование шаблонов](styling-and-templating.md)
- [Практическое руководство. Привязка к XML-данным с помощью XMLDataProvider и запросов XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Общие сведения об элементе управления ListView](listview-overview.md)
