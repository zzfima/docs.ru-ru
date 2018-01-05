---
title: "Практическое руководство. Построение таблицы программным способом"
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
helpviewer_keywords: tables [WPF], creating programmatically
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fca6a304ea12dd90a71f8718fed5f1595f4cd4b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-build-a-table-programmatically"></a><span data-ttu-id="7ab53-102">Практическое руководство. Построение таблицы программным способом</span><span class="sxs-lookup"><span data-stu-id="7ab53-102">How to: Build a Table Programmatically</span></span>
<span data-ttu-id="7ab53-103">Следующие примеры показывают, как программным способом создать <xref:System.Windows.Documents.Table> и заполнить ее содержимым.</span><span class="sxs-lookup"><span data-stu-id="7ab53-103">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="7ab53-104">Содержимое таблицы распределено по пяти строк (представленного <xref:System.Windows.Documents.TableRow> объектов, содержащихся в <xref:System.Windows.Documents.Table.RowGroups%2A> объекта) и шесть столбцов (представленного <xref:System.Windows.Documents.TableColumn> объектов).</span><span class="sxs-lookup"><span data-stu-id="7ab53-104">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="7ab53-105">Строки используются для различных целей представления, включая строку названия, предназначенную для заголовка всей таблицы, строку заголовка для описания столбцов данных в таблице и строку нижнего колонтитула для сводной информации.</span><span class="sxs-lookup"><span data-stu-id="7ab53-105">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="7ab53-106">Обратите внимание, что строки "title", "header" и "footer" не встроены в таблицу. Это просто строки с разными характеристиками.</span><span class="sxs-lookup"><span data-stu-id="7ab53-106">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="7ab53-107">Ячейки таблицы содержат фактическое содержимое, которое может включать текст, изображения или практически любых других [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] элемента.</span><span class="sxs-lookup"><span data-stu-id="7ab53-107">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ab53-108">Пример</span><span class="sxs-lookup"><span data-stu-id="7ab53-108">Example</span></span>  
 <span data-ttu-id="7ab53-109">Во-первых, <xref:System.Windows.Documents.FlowDocument> создается узел <xref:System.Windows.Documents.Table>и новый <xref:System.Windows.Documents.Table> создается и добавляется к содержимому <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="7ab53-109">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## <a name="example"></a><span data-ttu-id="7ab53-110">Пример</span><span class="sxs-lookup"><span data-stu-id="7ab53-110">Example</span></span>  
 <span data-ttu-id="7ab53-111">Далее, шести <xref:System.Windows.Documents.TableColumn> объекты создаются и добавляются в таблицу <xref:System.Windows.Documents.Table.Columns%2A> коллекции с применением некоторого форматирования.</span><span class="sxs-lookup"><span data-stu-id="7ab53-111">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ab53-112">Обратите внимание, что таблицы <xref:System.Windows.Documents.Table.Columns%2A> коллекция использует стандартную индексацию с нуля.</span><span class="sxs-lookup"><span data-stu-id="7ab53-112">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## <a name="example"></a><span data-ttu-id="7ab53-113">Пример</span><span class="sxs-lookup"><span data-stu-id="7ab53-113">Example</span></span>  
 <span data-ttu-id="7ab53-114">Затем создается строка заголовка и добавляется в таблицу с определенным форматированием.</span><span class="sxs-lookup"><span data-stu-id="7ab53-114">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="7ab53-115">Строка названия содержит одну ячейку, охватывающую все шесть столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="7ab53-115">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## <a name="example"></a><span data-ttu-id="7ab53-116">Пример</span><span class="sxs-lookup"><span data-stu-id="7ab53-116">Example</span></span>  
 <span data-ttu-id="7ab53-117">Далее создается и добавляется в таблицу строка заголовка, а ячейки в строке заголовка создаются и заполняются содержимым.</span><span class="sxs-lookup"><span data-stu-id="7ab53-117">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## <a name="example"></a><span data-ttu-id="7ab53-118">Пример</span><span class="sxs-lookup"><span data-stu-id="7ab53-118">Example</span></span>  
 <span data-ttu-id="7ab53-119">Затем создается и добавляется в таблицу ряд данных, а ячейки в этой строке создаются и заполняются содержимым.</span><span class="sxs-lookup"><span data-stu-id="7ab53-119">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="7ab53-120">Построение этой строки аналогично построению строки заголовка с применением немного другого форматирования.</span><span class="sxs-lookup"><span data-stu-id="7ab53-120">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## <a name="example"></a><span data-ttu-id="7ab53-121">Пример</span><span class="sxs-lookup"><span data-stu-id="7ab53-121">Example</span></span>  
 <span data-ttu-id="7ab53-122">Наконец, создается, добавляется и форматируется строка нижнего колонтитула.</span><span class="sxs-lookup"><span data-stu-id="7ab53-122">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="7ab53-123">Как и строка названия, нижний колонтитул содержит одну ячейку, которая включает все шесть столбцов в таблице.</span><span class="sxs-lookup"><span data-stu-id="7ab53-123">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="7ab53-124">См. также</span><span class="sxs-lookup"><span data-stu-id="7ab53-124">See Also</span></span>  
 [<span data-ttu-id="7ab53-125">Общие сведения о таблицах</span><span class="sxs-lookup"><span data-stu-id="7ab53-125">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)
