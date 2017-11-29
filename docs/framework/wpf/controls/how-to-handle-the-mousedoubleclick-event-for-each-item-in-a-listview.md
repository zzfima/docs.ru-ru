---
title: "Практическое руководство. Обработка события MouseDoubleClick для каждого элемента в ListView"
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
helpviewer_keywords: ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 53c40e9e3b02bdf33a073a93d28b619e399e375f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="52027-102">Практическое руководство. Обработка события MouseDoubleClick для каждого элемента в ListView</span><span class="sxs-lookup"><span data-stu-id="52027-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="52027-103">Чтобы обработать событие для элемента в <xref:System.Windows.Controls.ListView>, необходимо добавить обработчик событий к каждому <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="52027-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="52027-104">При <xref:System.Windows.Controls.ListView> привязан к источнику данных, не требуется явное создание <xref:System.Windows.Controls.ListViewItem>, но можно обработать событие для каждого элемента, добавляя <xref:System.Windows.EventSetter> стиль <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="52027-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52027-105">Пример</span><span class="sxs-lookup"><span data-stu-id="52027-105">Example</span></span>  
 <span data-ttu-id="52027-106">В следующем примере создается привязкой к данным <xref:System.Windows.Controls.ListView> и создает <xref:System.Windows.Style> для добавления обработчика событий в каждый <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="52027-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="52027-107">В следующем примере показана обработка <xref:System.Windows.Controls.Control.MouseDoubleClick> событий.</span><span class="sxs-lookup"><span data-stu-id="52027-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  <span data-ttu-id="52027-108">Несмотря на то, что чаще всего используется для привязки <xref:System.Windows.Controls.ListView> к источнику данных можно использовать для добавления обработчика событий в каждый стиль <xref:System.Windows.Controls.ListViewItem> в не привязкой к данным <xref:System.Windows.Controls.ListView> независимо от того, необходимо явно создать <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="52027-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="52027-109">Дополнительные сведения о явно и неявно созданных <xref:System.Windows.Controls.ListViewItem> элементов управления, в разделе <xref:System.Windows.Controls.ItemsControl>.</span><span class="sxs-lookup"><span data-stu-id="52027-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52027-110">См. также</span><span class="sxs-lookup"><span data-stu-id="52027-110">See Also</span></span>  
 <xref:System.Xml.XmlElement>  
 [<span data-ttu-id="52027-111">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="52027-111">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="52027-112">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="52027-112">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="52027-113">Практическое руководство. Привязка к XML-данным с помощью XMLDataProvider и запросов XPath</span><span class="sxs-lookup"><span data-stu-id="52027-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [<span data-ttu-id="52027-114">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="52027-114">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
