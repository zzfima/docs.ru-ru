---
title: Практическое руководство. Обработка события MouseDoubleClick для каждого элемента в ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: a4a93ffdf7c9cf2737c41a7fd196d8cfff716ea1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377207"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Практическое руководство. Обработка события MouseDoubleClick для каждого элемента в ListView
Чтобы обработать событие для элемента в <xref:System.Windows.Controls.ListView>, необходимо добавить обработчик событий к каждому <xref:System.Windows.Controls.ListViewItem>. При <xref:System.Windows.Controls.ListView> привязан к источнику данных, не требуется явно создавать <xref:System.Windows.Controls.ListViewItem>, но можно обрабатывать событие для каждого элемента, добавив <xref:System.Windows.EventSetter> порождает стиль <xref:System.Windows.Controls.ListViewItem>.  
  
## <a name="example"></a>Пример  
 В следующем примере создается привязкой к данным <xref:System.Windows.Controls.ListView> и создает <xref:System.Windows.Style> для добавления обработчика событий к каждому <xref:System.Windows.Controls.ListViewItem>.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 В следующем примере показана обработка <xref:System.Windows.Controls.Control.MouseDoubleClick> событий.  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  Несмотря на то, что чаще всего используется для привязки <xref:System.Windows.Controls.ListView> к источнику данных можно использовать стиль для добавления обработчика событий к каждому <xref:System.Windows.Controls.ListViewItem> в не привязанный к данным <xref:System.Windows.Controls.ListView> независимо от того, могут ли явно создавать <xref:System.Windows.Controls.ListViewItem>.  Дополнительные сведения о создании явно и неявно <xref:System.Windows.Controls.ListViewItem> элементов управления, см. в разделе <xref:System.Windows.Controls.ItemsControl>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Xml.XmlElement>
- [Общие сведения о привязке данных](../data/data-binding-overview.md)
- [Стилизация и использование шаблонов](styling-and-templating.md)
- [Практическое руководство. Привязка к XML-данным с помощью XMLDataProvider и запросов XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Общие сведения об элементе управления ListView](listview-overview.md)
