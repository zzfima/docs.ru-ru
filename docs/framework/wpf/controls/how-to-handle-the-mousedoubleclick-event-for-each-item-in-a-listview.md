---
title: Практическое руководство. Обработка события MouseDoubleClick для каждого элемента в ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 25308ee87fb387787e20c8a8887ae8e4e60742b9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460231"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Практическое руководство. Обработка события MouseDoubleClick для каждого элемента в ListView
Для обработки события для элемента в <xref:System.Windows.Controls.ListView>необходимо добавить обработчик событий для каждой <xref:System.Windows.Controls.ListViewItem>. Если <xref:System.Windows.Controls.ListView> привязан к источнику данных, то <xref:System.Windows.Controls.ListViewItem>не создается явным образом, но можно Обрабатывайте событие для каждого элемента, добавив <xref:System.Windows.EventSetter> к стилю <xref:System.Windows.Controls.ListViewItem>.  
  
## <a name="example"></a>Пример  
 В следующем примере создается <xref:System.Windows.Controls.ListView> с привязкой к данным и создается <xref:System.Windows.Style> для добавления обработчика событий в каждый <xref:System.Windows.Controls.ListViewItem>.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 В следующем примере обрабатывается событие <xref:System.Windows.Controls.Control.MouseDoubleClick>.  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> Несмотря на то, что наиболее распространена привязка <xref:System.Windows.Controls.ListView> к источнику данных, можно использовать стиль, чтобы добавить обработчик событий в каждый <xref:System.Windows.Controls.ListViewItem> в <xref:System.Windows.Controls.ListView>, не привязанном к данным, независимо от того, явно ли создается <xref:System.Windows.Controls.ListViewItem>.  Дополнительные сведения о явном и неявном создании <xref:System.Windows.Controls.ListViewItem>ных элементов управления см. в разделе <xref:System.Windows.Controls.ItemsControl>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.XmlElement>
- [Общие сведения о привязке данных](../data/data-binding-overview.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Практическое руководство. Привязка к XML-данным с помощью XMLDataProvider и запросов XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Общие сведения об элементе управления ListView](listview-overview.md)
