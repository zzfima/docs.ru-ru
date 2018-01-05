---
title: "Как: управлять таблицы &#39; s группы строк свойства RowGroups"
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
- row groups [WPF], manipulating through RowGroups property
- RowGroups property [WPF], manipulating row groups
- documents [WPF], manipulating row groups through RowGroups property
- properties [WPF], RowGroups [WPF], manipulating row groups
ms.assetid: ea61440f-08ae-44ed-b314-5716aaaae3ed
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f084819c3a5c39ea9d94a5741f8fb4a005d6040c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manipulate-a-table39s-row-groups-through-the-rowgroups-property"></a><span data-ttu-id="f0ad4-102">Как: управлять таблицы &#39; s группы строк свойства RowGroups</span><span class="sxs-lookup"><span data-stu-id="f0ad4-102">How to: Manipulate a Table&#39;s Row Groups through the RowGroups Property</span></span>
<span data-ttu-id="f0ad4-103">В этом примере показаны некоторые из наиболее распространенных операций, которые могут выполняться над группами строк таблицы <xref:System.Windows.Documents.Table.RowGroups%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f0ad4-103">This example demonstrates some of the more common operations that can be performed on a table's row groups through the <xref:System.Windows.Documents.Table.RowGroups%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0ad4-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f0ad4-104">Example</span></span>  
 <span data-ttu-id="f0ad4-105">В следующем примере создается новая таблица и затем использует <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> метод для добавления столбцов в таблице <xref:System.Windows.Documents.Table.RowGroups%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="f0ad4-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.RowGroups%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_add)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_add)]  
  
## <a name="example"></a><span data-ttu-id="f0ad4-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f0ad4-106">Example</span></span>  
 <span data-ttu-id="f0ad4-107">Следующий пример вставляет новый <xref:System.Windows.Documents.TableRowGroup>.</span><span class="sxs-lookup"><span data-stu-id="f0ad4-107">The following example inserts a new <xref:System.Windows.Documents.TableRowGroup>.</span></span>  <span data-ttu-id="f0ad4-108">Вставить новый столбец по индексу 0, сделав его новый первую строку в таблице.</span><span class="sxs-lookup"><span data-stu-id="f0ad4-108">The new column is inserted at index position 0, making it the new first row group in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0ad4-109"><xref:System.Windows.Documents.TableRowGroupCollection> Коллекция использует стандартную индексацию с нуля.</span><span class="sxs-lookup"><span data-stu-id="f0ad4-109">The <xref:System.Windows.Documents.TableRowGroupCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_insert)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_insert)]  
  
## <a name="example"></a><span data-ttu-id="f0ad4-110">Пример</span><span class="sxs-lookup"><span data-stu-id="f0ad4-110">Example</span></span>  
 <span data-ttu-id="f0ad4-111">В следующем примере добавляется несколько строк в конкретную <xref:System.Windows.Documents.TableRowGroup> (указанную индексом) в таблице.</span><span class="sxs-lookup"><span data-stu-id="f0ad4-111">The following example adds several rows to a particular <xref:System.Windows.Documents.TableRowGroup> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addrows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addrows)]  
  
## <a name="example"></a><span data-ttu-id="f0ad4-112">Пример</span><span class="sxs-lookup"><span data-stu-id="f0ad4-112">Example</span></span>  
 <span data-ttu-id="f0ad4-113">Следующий пример получает доступ к некоторым произвольным свойствам строк в первой группе строк в таблице.</span><span class="sxs-lookup"><span data-stu-id="f0ad4-113">The following example accesses some arbitrary properties on rows in the first row group in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_maniprows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_maniprows)]  
  
## <a name="example"></a><span data-ttu-id="f0ad4-114">Пример</span><span class="sxs-lookup"><span data-stu-id="f0ad4-114">Example</span></span>  
 <span data-ttu-id="f0ad4-115">В следующем примере добавляется несколько ячеек в конкретную <xref:System.Windows.Documents.TableRow> (указанную индексом) в таблице.</span><span class="sxs-lookup"><span data-stu-id="f0ad4-115">The following example adds several cells to a particular <xref:System.Windows.Documents.TableRow> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addcells)]  
  
## <a name="example"></a><span data-ttu-id="f0ad4-116">Пример</span><span class="sxs-lookup"><span data-stu-id="f0ad4-116">Example</span></span>  
 <span data-ttu-id="f0ad4-117">Следующий пример доступ к некоторым произвольным методам и свойствам ячеек в первой строке в первой строке группы.</span><span class="sxs-lookup"><span data-stu-id="f0ad4-117">The following example access some arbitrary methods and properties on cells in the first row in the first row group.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_manipcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_manipcells)]  
  
## <a name="example"></a><span data-ttu-id="f0ad4-118">Пример</span><span class="sxs-lookup"><span data-stu-id="f0ad4-118">Example</span></span>  
 <span data-ttu-id="f0ad4-119">Следующий пример возвращает количество <xref:System.Windows.Documents.TableRowGroup> элементы, размещенные в таблице.</span><span class="sxs-lookup"><span data-stu-id="f0ad4-119">The following example returns the number of <xref:System.Windows.Documents.TableRowGroup> elements hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_count)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_count)]  
  
## <a name="example"></a><span data-ttu-id="f0ad4-120">Пример</span><span class="sxs-lookup"><span data-stu-id="f0ad4-120">Example</span></span>  
 <span data-ttu-id="f0ad4-121">Следующий пример удаляет определенная группа строк по ссылке.</span><span class="sxs-lookup"><span data-stu-id="f0ad4-121">The following example removes a particular row group by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delref)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delref)]  
  
## <a name="example"></a><span data-ttu-id="f0ad4-122">Пример</span><span class="sxs-lookup"><span data-stu-id="f0ad4-122">Example</span></span>  
 <span data-ttu-id="f0ad4-123">Следующий пример удаляет определенная группа строк по индексу.</span><span class="sxs-lookup"><span data-stu-id="f0ad4-123">The following example removes a particular row group by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delindex)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delindex)]  
  
## <a name="example"></a><span data-ttu-id="f0ad4-124">Пример</span><span class="sxs-lookup"><span data-stu-id="f0ad4-124">Example</span></span>  
 <span data-ttu-id="f0ad4-125">Следующий пример удаляет все группы строк из коллекции групп строк таблицы.</span><span class="sxs-lookup"><span data-stu-id="f0ad4-125">The following example removes all row groups from the table's row groups collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_clear)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="f0ad4-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f0ad4-126">See Also</span></span>  
 [<span data-ttu-id="f0ad4-127">Практическое руководство: Управление элементами потокового содержимого через свойство внутристрочных элементов</span><span class="sxs-lookup"><span data-stu-id="f0ad4-127">How-to: Manipulate Flow Content Elements through the Inlines Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [<span data-ttu-id="f0ad4-128">Управление FlowDocument с помощью свойства Blocks</span><span class="sxs-lookup"><span data-stu-id="f0ad4-128">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="f0ad4-129">Управление столбцами таблицы с помощью свойства Columns</span><span class="sxs-lookup"><span data-stu-id="f0ad4-129">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)
