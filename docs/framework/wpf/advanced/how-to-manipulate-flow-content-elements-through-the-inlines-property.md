---
title: Практическое руководство. Управление элементами потокового содержимого через свойство Inlines
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], manipulating through Inlines property
- documents [WPF], manipulating flow Content elements through Inlines property
- Inlines property [WPF], manipulating flow Content elements
- properties [WPF], Inlines [WPF], manipulating flow Content elements
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
ms.openlocfilehash: 2631d088d677c5edb1ae73a3cb40d15bf4beb71f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361815"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a><span data-ttu-id="c5004-102">Практическое руководство. Управление элементами потокового содержимого через свойство Inlines</span><span class="sxs-lookup"><span data-stu-id="c5004-102">How to: Manipulate Flow Content Elements through the Inlines Property</span></span>
<span data-ttu-id="c5004-103">Эти примеры демонстрируют некоторые из наиболее распространенных операций, которые могут быть выполнены для элементов содержимого нефиксированного формата встроенного (и контейнерами таких элементов, таких как <xref:System.Windows.Controls.TextBlock>) через **Inlines** свойство.</span><span class="sxs-lookup"><span data-stu-id="c5004-103">These examples demonstrate some of the more common operations that can be performed on inline flow content elements (and containers of such elements, such as <xref:System.Windows.Controls.TextBlock>) through the **Inlines** property.</span></span> <span data-ttu-id="c5004-104">Это свойство используется для добавления и удаления элементов из <xref:System.Windows.Documents.InlineCollection>.</span><span class="sxs-lookup"><span data-stu-id="c5004-104">This property is used to add and remove items from <xref:System.Windows.Documents.InlineCollection>.</span></span> <span data-ttu-id="c5004-105">Элементы содержимого на поток, эта функция **Inlines** свойства включают:</span><span class="sxs-lookup"><span data-stu-id="c5004-105">Flow content elements that feature an **Inlines** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Bold>  
  
-   <xref:System.Windows.Documents.Hyperlink>  
  
-   <xref:System.Windows.Documents.Italic>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Span>  
  
-   <xref:System.Windows.Documents.Underline>  
  
 <span data-ttu-id="c5004-106">Для использования этих примерах <xref:System.Windows.Documents.Span> поток элемент содержимого, но эти методы применимы ко всем элементам или элементы управления, на которых размещены <xref:System.Windows.Documents.InlineCollection> коллекции.</span><span class="sxs-lookup"><span data-stu-id="c5004-106">These examples happen to use <xref:System.Windows.Documents.Span> as the flow content element, but these techniques are applicable to all elements or controls that host an <xref:System.Windows.Documents.InlineCollection> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5004-107">Пример</span><span class="sxs-lookup"><span data-stu-id="c5004-107">Example</span></span>  
 <span data-ttu-id="c5004-108">В следующем примере создается новый <xref:System.Windows.Documents.Span> объекта, а затем используется **добавить** метод для добавления двух текстовых выполняется как дочернего содержимого объекта <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="c5004-108">The following example creates a new <xref:System.Windows.Documents.Span> object, and then uses the **Add** method to add two text runs as content children of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a><span data-ttu-id="c5004-109">Пример</span><span class="sxs-lookup"><span data-stu-id="c5004-109">Example</span></span>  
 <span data-ttu-id="c5004-110">В следующем примере создается новый <xref:System.Windows.Documents.Run> элемент и вставляет его в начале <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="c5004-110">The following example creates a new <xref:System.Windows.Documents.Run> element and inserts it at the beginning of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a><span data-ttu-id="c5004-111">Пример</span><span class="sxs-lookup"><span data-stu-id="c5004-111">Example</span></span>  
 <span data-ttu-id="c5004-112">В следующем примере возвращается количество верхнего уровня <xref:System.Windows.Documents.Inline> элементов, содержащихся в <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="c5004-112">The following example gets the number of top-level <xref:System.Windows.Documents.Inline> elements contained in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a><span data-ttu-id="c5004-113">Пример</span><span class="sxs-lookup"><span data-stu-id="c5004-113">Example</span></span>  
 <span data-ttu-id="c5004-114">В следующем примере удаляется последний <xref:System.Windows.Documents.Inline> элемент <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="c5004-114">The following example deletes the last <xref:System.Windows.Documents.Inline> element in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a><span data-ttu-id="c5004-115">Пример</span><span class="sxs-lookup"><span data-stu-id="c5004-115">Example</span></span>  
 <span data-ttu-id="c5004-116">В следующем примере удаляется все содержимое (<xref:System.Windows.Documents.Inline> элементы) из <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="c5004-116">The following example clears all of the contents (<xref:System.Windows.Documents.Inline> elements) from the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a><span data-ttu-id="c5004-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c5004-117">See also</span></span>
- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [<span data-ttu-id="c5004-118">Общие сведения о документах нефиксированного формата</span><span class="sxs-lookup"><span data-stu-id="c5004-118">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="c5004-119">Управление FlowDocument с помощью свойства Blocks</span><span class="sxs-lookup"><span data-stu-id="c5004-119">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="c5004-120">Управление столбцами таблицы с помощью свойства Columns</span><span class="sxs-lookup"><span data-stu-id="c5004-120">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="c5004-121">Управление группами строк таблицы пользователя с помощью свойства RowGroups</span><span class="sxs-lookup"><span data-stu-id="c5004-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
