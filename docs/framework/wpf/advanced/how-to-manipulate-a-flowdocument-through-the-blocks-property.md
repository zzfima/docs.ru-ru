---
title: Практическое руководство. Управление FlowDocument через свойство блоков
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], manipulating FlowDocuments through Blocks property [WPF], , '
- ', '
ms.assetid: cbb7291e-3f1b-433e-9e16-f4d93ced14e8
ms.openlocfilehash: 0190a5c0e343d625f9aa9e896a581dd54bf822dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-manipulate-a-flowdocument-through-the-blocks-property"></a><span data-ttu-id="e09b1-102">Практическое руководство. Управление FlowDocument через свойство блоков</span><span class="sxs-lookup"><span data-stu-id="e09b1-102">How to: Manipulate a FlowDocument through the Blocks Property</span></span>
<span data-ttu-id="e09b1-103">Эти примеры демонстрируют некоторые из наиболее распространенных операций, которые могут быть выполнены на <xref:System.Windows.Documents.FlowDocument> через <xref:System.Windows.Documents.FlowDocument.Blocks%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="e09b1-103">These examples demonstrate some of the more common operations that can be performed on a <xref:System.Windows.Documents.FlowDocument> through the <xref:System.Windows.Documents.FlowDocument.Blocks%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e09b1-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e09b1-104">Example</span></span>  
 <span data-ttu-id="e09b1-105">В следующем примере создается новый <xref:System.Windows.Documents.FlowDocument> , а затем добавляет новый <xref:System.Windows.Documents.Paragraph> элемент <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="e09b1-105">The following example creates a new <xref:System.Windows.Documents.FlowDocument> and then appends a new <xref:System.Windows.Documents.Paragraph> element to the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksadd)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="e09b1-106">Пример</span><span class="sxs-lookup"><span data-stu-id="e09b1-106">Example</span></span>  
 <span data-ttu-id="e09b1-107">В следующем примере создается новый <xref:System.Windows.Documents.Paragraph> элемент и вставляет его в начале <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="e09b1-107">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="e09b1-108">Пример</span><span class="sxs-lookup"><span data-stu-id="e09b1-108">Example</span></span>  
 <span data-ttu-id="e09b1-109">В следующем примере возвращается количество верхнего уровня <xref:System.Windows.Documents.Block> элементов, содержащихся в <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="e09b1-109">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblockscount)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblockscount)]  
  
## <a name="example"></a><span data-ttu-id="e09b1-110">Пример</span><span class="sxs-lookup"><span data-stu-id="e09b1-110">Example</span></span>  
 <span data-ttu-id="e09b1-111">В следующем примере удаляется последний <xref:System.Windows.Documents.Block> элемент в <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="e09b1-111">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="e09b1-112">Пример</span><span class="sxs-lookup"><span data-stu-id="e09b1-112">Example</span></span>  
 <span data-ttu-id="e09b1-113">В следующем примере удаляются все содержимое (<xref:System.Windows.Documents.Block> элементы) из <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="e09b1-113">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksclear)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="e09b1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e09b1-114">See Also</span></span>  
 [<span data-ttu-id="e09b1-115">Управление группами строк таблицы пользователя с помощью свойства RowGroups</span><span class="sxs-lookup"><span data-stu-id="e09b1-115">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [<span data-ttu-id="e09b1-116">Управление столбцами таблицы с помощью свойства Columns</span><span class="sxs-lookup"><span data-stu-id="e09b1-116">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [<span data-ttu-id="e09b1-117">Управление группами строк таблицы пользователя с помощью свойства RowGroups</span><span class="sxs-lookup"><span data-stu-id="e09b1-117">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
