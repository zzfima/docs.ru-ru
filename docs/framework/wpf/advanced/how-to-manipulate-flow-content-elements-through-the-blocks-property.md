---
title: Практическое руководство. Управление элементами потокового содержимого с помощью свойства Blocks
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating flow content elements through Blocks property
- flow content elements [WPF], manipulating through Blocks property
- properties [WPF], Blocks [WPF], manipulating flow content elements
- Blocks property [WPF], manipulating flow content elements
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
ms.openlocfilehash: e0e1e1333a54946f3bdf474e353de0301eb42447
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150141"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-blocks-property"></a><span data-ttu-id="5f6ed-102">Практическое руководство. Управление элементами потокового содержимого с помощью свойства Blocks</span><span class="sxs-lookup"><span data-stu-id="5f6ed-102">How to: Manipulate Flow Content Elements through the Blocks Property</span></span>
<span data-ttu-id="5f6ed-103">Эти примеры демонстрируют некоторые из наиболее распространенных операций, которые могут выполняться над элементами потокового содержимого через **блоки** свойство.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-103">These examples demonstrate some of the more common operations that can be performed on flow content elements through the **Blocks** property.</span></span> <span data-ttu-id="5f6ed-104">Это свойство используется для добавления и удаления элементов из <xref:System.Windows.Documents.BlockCollection>.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-104">This property is used to add and remove items from <xref:System.Windows.Documents.BlockCollection>.</span></span> <span data-ttu-id="5f6ed-105">Элементы содержимого на поток, эта функция **блоки** свойства включают:</span><span class="sxs-lookup"><span data-stu-id="5f6ed-105">Flow content elements that feature a **Blocks** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Figure>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.ListItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="5f6ed-106">Для использования этих примерах <xref:System.Windows.Documents.Section> поток элемент содержимого, но эти методы применяются ко всем элементам, на которых размещены коллекцию элемент содержимого нефиксированного формата.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-106">These examples happen to use <xref:System.Windows.Documents.Section> as the flow content element, but these techniques are applicable to all elements that host a flow content element collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f6ed-107">Пример</span><span class="sxs-lookup"><span data-stu-id="5f6ed-107">Example</span></span>  
 <span data-ttu-id="5f6ed-108">В следующем примере создается новый <xref:System.Windows.Documents.Section> , а затем использует **добавить** метод, чтобы добавить новый абзац в **разделе** содержимое.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-108">The following example creates a new <xref:System.Windows.Documents.Section> and then uses the **Add** method to add a new Paragraph to the **Section** contents.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="5f6ed-109">Пример</span><span class="sxs-lookup"><span data-stu-id="5f6ed-109">Example</span></span>  
 <span data-ttu-id="5f6ed-110">В следующем примере создается новый <xref:System.Windows.Documents.Paragraph> элемент и вставляет его в начале <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-110">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="5f6ed-111">Пример</span><span class="sxs-lookup"><span data-stu-id="5f6ed-111">Example</span></span>  
 <span data-ttu-id="5f6ed-112">В следующем примере возвращается количество верхнего уровня <xref:System.Windows.Documents.Block> элементов, содержащихся в <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-112">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## <a name="example"></a><span data-ttu-id="5f6ed-113">Пример</span><span class="sxs-lookup"><span data-stu-id="5f6ed-113">Example</span></span>  
 <span data-ttu-id="5f6ed-114">В следующем примере удаляется последний <xref:System.Windows.Documents.Block> элемент <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-114">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="5f6ed-115">Пример</span><span class="sxs-lookup"><span data-stu-id="5f6ed-115">Example</span></span>  
 <span data-ttu-id="5f6ed-116">В следующем примере удаляется все содержимое (<xref:System.Windows.Documents.Block> элементы) из <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-116">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="5f6ed-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5f6ed-117">See also</span></span>

- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [<span data-ttu-id="5f6ed-118">Общие сведения о документах нефиксированного формата</span><span class="sxs-lookup"><span data-stu-id="5f6ed-118">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="5f6ed-119">Управление группами строк таблицы пользователя с помощью свойства RowGroups</span><span class="sxs-lookup"><span data-stu-id="5f6ed-119">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="5f6ed-120">Управление столбцами таблицы с помощью свойства Columns</span><span class="sxs-lookup"><span data-stu-id="5f6ed-120">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="5f6ed-121">Управление группами строк таблицы пользователя с помощью свойства RowGroups</span><span class="sxs-lookup"><span data-stu-id="5f6ed-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
