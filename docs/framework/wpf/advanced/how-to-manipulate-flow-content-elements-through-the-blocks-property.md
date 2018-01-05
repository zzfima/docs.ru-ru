---
title: "Практическое руководство. Управление элементами потокового содержимого через свойство Blocks"
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
- documents [WPF], manipulating flow content elements through Blocks property
- flow content elements [WPF], manipulating through Blocks property
- properties [WPF], Blocks [WPF], manipulating flow content elements
- Blocks property [WPF], manipulating flow content elements
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d995e9a3a50e733a87a203f94b97a937560a0141
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manipulate-flow-content-elements-through-the-blocks-property"></a><span data-ttu-id="6b472-102">Практическое руководство. Управление элементами потокового содержимого через свойство Blocks</span><span class="sxs-lookup"><span data-stu-id="6b472-102">How to: Manipulate Flow Content Elements through the Blocks Property</span></span>
<span data-ttu-id="6b472-103">Эти примеры демонстрируют некоторые из наиболее распространенных операций, которые могут быть выполнены в элементах потока содержимого с помощью **блоки** свойство.</span><span class="sxs-lookup"><span data-stu-id="6b472-103">These examples demonstrate some of the more common operations that can be performed on flow content elements through the **Blocks** property.</span></span> <span data-ttu-id="6b472-104">Это свойство используется для добавления и удаления элементов из <xref:System.Windows.Documents.BlockCollection>.</span><span class="sxs-lookup"><span data-stu-id="6b472-104">This property is used to add and remove items from <xref:System.Windows.Documents.BlockCollection>.</span></span> <span data-ttu-id="6b472-105">Элементы содержимого на поток, эта функция **блоки** свойства включают:</span><span class="sxs-lookup"><span data-stu-id="6b472-105">Flow content elements that feature a **Blocks** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Figure>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.ListItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="6b472-106">Для использования этих примерах <xref:System.Windows.Documents.Section> поток содержимого элемента, но эти методы применяются ко всем элементам, на которых размещена коллекция элемент содержимого потока.</span><span class="sxs-lookup"><span data-stu-id="6b472-106">These examples happen to use <xref:System.Windows.Documents.Section> as the flow content element, but these techniques are applicable to all elements that host a flow content element collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b472-107">Пример</span><span class="sxs-lookup"><span data-stu-id="6b472-107">Example</span></span>  
 <span data-ttu-id="6b472-108">В следующем примере создается новый <xref:System.Windows.Documents.Section> , а затем использует **добавить** метод, чтобы добавить новый абзац в **раздел** содержимое.</span><span class="sxs-lookup"><span data-stu-id="6b472-108">The following example creates a new <xref:System.Windows.Documents.Section> and then uses the **Add** method to add a new Paragraph to the **Section** contents.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="6b472-109">Пример</span><span class="sxs-lookup"><span data-stu-id="6b472-109">Example</span></span>  
 <span data-ttu-id="6b472-110">В следующем примере создается новый <xref:System.Windows.Documents.Paragraph> элемент и вставляет его в начале <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="6b472-110">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="6b472-111">Пример</span><span class="sxs-lookup"><span data-stu-id="6b472-111">Example</span></span>  
 <span data-ttu-id="6b472-112">В следующем примере возвращается количество верхнего уровня <xref:System.Windows.Documents.Block> элементов, содержащихся в <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="6b472-112">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## <a name="example"></a><span data-ttu-id="6b472-113">Пример</span><span class="sxs-lookup"><span data-stu-id="6b472-113">Example</span></span>  
 <span data-ttu-id="6b472-114">В следующем примере удаляется последний <xref:System.Windows.Documents.Block> элемент в <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="6b472-114">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="6b472-115">Пример</span><span class="sxs-lookup"><span data-stu-id="6b472-115">Example</span></span>  
 <span data-ttu-id="6b472-116">В следующем примере удаляются все содержимое (<xref:System.Windows.Documents.Block> элементы) из <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="6b472-116">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="6b472-117">См. также</span><span class="sxs-lookup"><span data-stu-id="6b472-117">See Also</span></span>  
 <xref:System.Windows.Documents.BlockCollection>  
 <xref:System.Windows.Documents.InlineCollection>  
 <xref:System.Windows.Documents.ListItemCollection>  
 [<span data-ttu-id="6b472-118">Общие сведения о документе нефиксированного формата</span><span class="sxs-lookup"><span data-stu-id="6b472-118">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="6b472-119">Управление группами строк таблицы пользователя с помощью свойства RowGroups</span><span class="sxs-lookup"><span data-stu-id="6b472-119">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [<span data-ttu-id="6b472-120">Управление столбцами таблицы с помощью свойства Columns</span><span class="sxs-lookup"><span data-stu-id="6b472-120">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [<span data-ttu-id="6b472-121">Управление группами строк таблицы пользователя с помощью свойства RowGroups</span><span class="sxs-lookup"><span data-stu-id="6b472-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
