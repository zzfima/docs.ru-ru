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
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="37679-102">Практическое руководство. Обработка события MouseDoubleClick для каждого элемента в ListView</span><span class="sxs-lookup"><span data-stu-id="37679-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="37679-103">Для обработки события элемента в <xref:System.Windows.Controls.ListView>необходимо добавить в каждый из них <xref:System.Windows.Controls.ListViewItem>обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="37679-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="37679-104">Если привязка привязана к источнику данных, то вы не <xref:System.Windows.Controls.ListViewItem>создаете, но можете Обрабатывайте событие для <xref:System.Windows.EventSetter> каждого элемента, добавив в стиль <xref:System.Windows.Controls.ListViewItem>. <xref:System.Windows.Controls.ListView></span><span class="sxs-lookup"><span data-stu-id="37679-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37679-105">Пример</span><span class="sxs-lookup"><span data-stu-id="37679-105">Example</span></span>  
 <span data-ttu-id="37679-106">В следующем примере создается привязка <xref:System.Windows.Controls.ListView> <xref:System.Windows.Style> к данным и создается, чтобы добавить в каждый <xref:System.Windows.Controls.ListViewItem>обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="37679-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="37679-107">В следующем примере обрабатывается <xref:System.Windows.Controls.Control.MouseDoubleClick> событие.</span><span class="sxs-lookup"><span data-stu-id="37679-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> <span data-ttu-id="37679-108">Несмотря на то, что наиболее распространена <xref:System.Windows.Controls.ListView> привязка к источнику данных, можно использовать стиль для добавления обработчика событий в каждый <xref:System.Windows.Controls.ListViewItem> объект в не привязанных к <xref:System.Windows.Controls.ListView> данным данных <xref:System.Windows.Controls.ListViewItem>независимо от того, был ли явно создан.</span><span class="sxs-lookup"><span data-stu-id="37679-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="37679-109">Дополнительные сведения о явно и неявно созданных <xref:System.Windows.Controls.ListViewItem> элементах управления см. в разделе. <xref:System.Windows.Controls.ItemsControl></span><span class="sxs-lookup"><span data-stu-id="37679-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37679-110">См. также</span><span class="sxs-lookup"><span data-stu-id="37679-110">See also</span></span>

- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="37679-111">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="37679-111">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="37679-112">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="37679-112">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="37679-113">Практическое руководство. Привязка к XML-данным с помощью XMLDataProvider и запросов XPath</span><span class="sxs-lookup"><span data-stu-id="37679-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="37679-114">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="37679-114">ListView Overview</span></span>](listview-overview.md)
