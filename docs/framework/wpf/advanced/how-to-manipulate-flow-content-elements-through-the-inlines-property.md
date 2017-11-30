---
title: "Практическое руководство. Управление элементами потокового содержимого через свойство Inlines"
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
- flow content elements [WPF], manipulating through Inlines property
- documents [WPF], manipulating flow Content elements through Inlines property
- Inlines property [WPF], manipulating flow Content elements
- properties [WPF], Inlines [WPF], manipulating flow Content elements
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 77b6d75b48fd137092600a7e2316cbcf7099de76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a><span data-ttu-id="a2bdf-102">Практическое руководство. Управление элементами потокового содержимого через свойство Inlines</span><span class="sxs-lookup"><span data-stu-id="a2bdf-102">How to: Manipulate Flow Content Elements through the Inlines Property</span></span>
<span data-ttu-id="a2bdf-103">Этих примерах показаны некоторые из наиболее распространенных операций, которые могут выполняться над встроенными элементами потокового содержимого (и контейнерами таких элементов, таких как <xref:System.Windows.Controls.TextBlock>) через **внутристрочных элементов** свойство.</span><span class="sxs-lookup"><span data-stu-id="a2bdf-103">These examples demonstrate some of the more common operations that can be performed on inline flow content elements (and containers of such elements, such as <xref:System.Windows.Controls.TextBlock>) through the **Inlines** property.</span></span> <span data-ttu-id="a2bdf-104">Это свойство используется для добавления и удаления элементов из <xref:System.Windows.Documents.InlineCollection>.</span><span class="sxs-lookup"><span data-stu-id="a2bdf-104">This property is used to add and remove items from <xref:System.Windows.Documents.InlineCollection>.</span></span> <span data-ttu-id="a2bdf-105">Элементы содержимого на поток, эта функция **внедряет** свойства включают:</span><span class="sxs-lookup"><span data-stu-id="a2bdf-105">Flow content elements that feature an **Inlines** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Bold>  
  
-   <xref:System.Windows.Documents.Hyperlink>  
  
-   <xref:System.Windows.Documents.Italic>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Span>  
  
-   <xref:System.Windows.Documents.Underline>  
  
 <span data-ttu-id="a2bdf-106">Для использования этих примерах <xref:System.Windows.Documents.Span> поток элемент содержимого, но эти методы применимы ко всем элементам или элементов управления, на которых размещены <xref:System.Windows.Documents.InlineCollection> коллекции.</span><span class="sxs-lookup"><span data-stu-id="a2bdf-106">These examples happen to use <xref:System.Windows.Documents.Span> as the flow content element, but these techniques are applicable to all elements or controls that host an <xref:System.Windows.Documents.InlineCollection> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2bdf-107">Пример</span><span class="sxs-lookup"><span data-stu-id="a2bdf-107">Example</span></span>  
 <span data-ttu-id="a2bdf-108">В следующем примере создается новый <xref:System.Windows.Documents.Span> объекта, а затем используется **добавить** метод для добавления двух текстовых выполняется как содержимого дочерних элементов <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="a2bdf-108">The following example creates a new <xref:System.Windows.Documents.Span> object, and then uses the **Add** method to add two text runs as content children of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a><span data-ttu-id="a2bdf-109">Пример</span><span class="sxs-lookup"><span data-stu-id="a2bdf-109">Example</span></span>  
 <span data-ttu-id="a2bdf-110">В следующем примере создается новый <xref:System.Windows.Documents.Run> элемент и вставляет его в начале <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="a2bdf-110">The following example creates a new <xref:System.Windows.Documents.Run> element and inserts it at the beginning of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a><span data-ttu-id="a2bdf-111">Пример</span><span class="sxs-lookup"><span data-stu-id="a2bdf-111">Example</span></span>  
 <span data-ttu-id="a2bdf-112">В следующем примере возвращается количество верхнего уровня <xref:System.Windows.Documents.Inline> элементов, содержащихся в <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="a2bdf-112">The following example gets the number of top-level <xref:System.Windows.Documents.Inline> elements contained in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a><span data-ttu-id="a2bdf-113">Пример</span><span class="sxs-lookup"><span data-stu-id="a2bdf-113">Example</span></span>  
 <span data-ttu-id="a2bdf-114">В следующем примере удаляется последний <xref:System.Windows.Documents.Inline> элемент в <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="a2bdf-114">The following example deletes the last <xref:System.Windows.Documents.Inline> element in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a><span data-ttu-id="a2bdf-115">Пример</span><span class="sxs-lookup"><span data-stu-id="a2bdf-115">Example</span></span>  
 <span data-ttu-id="a2bdf-116">В следующем примере удаляются все содержимое (<xref:System.Windows.Documents.Inline> элементы) из <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="a2bdf-116">The following example clears all of the contents (<xref:System.Windows.Documents.Inline> elements) from the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a><span data-ttu-id="a2bdf-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a2bdf-117">See Also</span></span>  
 <xref:System.Windows.Documents.BlockCollection>  
 <xref:System.Windows.Documents.InlineCollection>  
 <xref:System.Windows.Documents.ListItemCollection>  
 [<span data-ttu-id="a2bdf-118">Общие сведения о документе нефиксированного формата</span><span class="sxs-lookup"><span data-stu-id="a2bdf-118">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="a2bdf-119">Управление FlowDocument с помощью свойства Blocks</span><span class="sxs-lookup"><span data-stu-id="a2bdf-119">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="a2bdf-120">Управление столбцами таблицы с помощью свойства Columns</span><span class="sxs-lookup"><span data-stu-id="a2bdf-120">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [<span data-ttu-id="a2bdf-121">Управление группами строк таблицы пользователя с помощью свойства RowGroups</span><span class="sxs-lookup"><span data-stu-id="a2bdf-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
