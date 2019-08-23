---
title: Практическое руководство. Управление группами строк таблицы пользователя с помощью свойства RowGroups
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- row groups [WPF], manipulating through RowGroups property
- RowGroups property [WPF], manipulating row groups
- documents [WPF], manipulating row groups through RowGroups property
- properties [WPF], RowGroups [WPF], manipulating row groups
ms.assetid: ea61440f-08ae-44ed-b314-5716aaaae3ed
ms.openlocfilehash: 195920af64888bd3671b45befc0fe4cde463ae7b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913562"
---
# <a name="how-to-manipulate-a-tables-row-groups-through-the-rowgroups-property"></a><span data-ttu-id="5c2d0-102">Практическое руководство. Управление группами строк таблицы пользователя с помощью свойства RowGroups</span><span class="sxs-lookup"><span data-stu-id="5c2d0-102">How to: Manipulate a Table's Row Groups through the RowGroups Property</span></span>
<span data-ttu-id="5c2d0-103">В этом примере демонстрируются некоторые из наиболее распространенных операций, которые можно выполнить с группами строк таблицы через <xref:System.Windows.Documents.Table.RowGroups%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="5c2d0-103">This example demonstrates some of the more common operations that can be performed on a table's row groups through the <xref:System.Windows.Documents.Table.RowGroups%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c2d0-104">Пример</span><span class="sxs-lookup"><span data-stu-id="5c2d0-104">Example</span></span>  
 <span data-ttu-id="5c2d0-105">В следующем примере создается новая таблица, а затем используется <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> метод для добавления столбцов в <xref:System.Windows.Documents.Table.RowGroups%2A> коллекцию таблицы.</span><span class="sxs-lookup"><span data-stu-id="5c2d0-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.RowGroups%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_add)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_add)]  
  
## <a name="example"></a><span data-ttu-id="5c2d0-106">Пример</span><span class="sxs-lookup"><span data-stu-id="5c2d0-106">Example</span></span>  
 <span data-ttu-id="5c2d0-107">В следующем примере вставляется новый <xref:System.Windows.Documents.TableRowGroup>объект.</span><span class="sxs-lookup"><span data-stu-id="5c2d0-107">The following example inserts a new <xref:System.Windows.Documents.TableRowGroup>.</span></span>  <span data-ttu-id="5c2d0-108">Новый столбец вставляется в позиции индекса 0, делая ее новой первой группой строк в таблице.</span><span class="sxs-lookup"><span data-stu-id="5c2d0-108">The new column is inserted at index position 0, making it the new first row group in the table.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c2d0-109">В <xref:System.Windows.Documents.TableRowGroupCollection> коллекции используется стандартная индексация, начинающаяся с нуля.</span><span class="sxs-lookup"><span data-stu-id="5c2d0-109">The <xref:System.Windows.Documents.TableRowGroupCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_insert)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_insert)]  
  
## <a name="example"></a><span data-ttu-id="5c2d0-110">Пример</span><span class="sxs-lookup"><span data-stu-id="5c2d0-110">Example</span></span>  
 <span data-ttu-id="5c2d0-111">В следующем примере в таблицу добавляется несколько строк <xref:System.Windows.Documents.TableRowGroup> в определенное значение (указанное по индексу).</span><span class="sxs-lookup"><span data-stu-id="5c2d0-111">The following example adds several rows to a particular <xref:System.Windows.Documents.TableRowGroup> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddRows](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addrows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddRows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addrows)]  
  
## <a name="example"></a><span data-ttu-id="5c2d0-112">Пример</span><span class="sxs-lookup"><span data-stu-id="5c2d0-112">Example</span></span>  
 <span data-ttu-id="5c2d0-113">В следующем примере осуществляется доступ к некоторым произвольным свойствам строк в первой группе строк в таблице.</span><span class="sxs-lookup"><span data-stu-id="5c2d0-113">The following example accesses some arbitrary properties on rows in the first row group in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipRows](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_maniprows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipRows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_maniprows)]  
  
## <a name="example"></a><span data-ttu-id="5c2d0-114">Пример</span><span class="sxs-lookup"><span data-stu-id="5c2d0-114">Example</span></span>  
 <span data-ttu-id="5c2d0-115">В приведенном ниже примере в таблице добавляются <xref:System.Windows.Documents.TableRow> несколько ячеек с определенным индексом (заданным параметром index).</span><span class="sxs-lookup"><span data-stu-id="5c2d0-115">The following example adds several cells to a particular <xref:System.Windows.Documents.TableRow> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddCells](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddCells](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addcells)]  
  
## <a name="example"></a><span data-ttu-id="5c2d0-116">Пример</span><span class="sxs-lookup"><span data-stu-id="5c2d0-116">Example</span></span>  
 <span data-ttu-id="5c2d0-117">В следующем примере осуществляется доступ к некоторым произвольным методам и свойствам ячеек в первой строке первой группы строк.</span><span class="sxs-lookup"><span data-stu-id="5c2d0-117">The following example access some arbitrary methods and properties on cells in the first row in the first row group.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipCells](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_manipcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipCells](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_manipcells)]  
  
## <a name="example"></a><span data-ttu-id="5c2d0-118">Пример</span><span class="sxs-lookup"><span data-stu-id="5c2d0-118">Example</span></span>  
 <span data-ttu-id="5c2d0-119">В следующем примере возвращается количество <xref:System.Windows.Documents.TableRowGroup> элементов, размещенных в таблице.</span><span class="sxs-lookup"><span data-stu-id="5c2d0-119">The following example returns the number of <xref:System.Windows.Documents.TableRowGroup> elements hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_count)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_count)]  
  
## <a name="example"></a><span data-ttu-id="5c2d0-120">Пример</span><span class="sxs-lookup"><span data-stu-id="5c2d0-120">Example</span></span>  
 <span data-ttu-id="5c2d0-121">В следующем примере удаляется определенная группа строк по ссылке.</span><span class="sxs-lookup"><span data-stu-id="5c2d0-121">The following example removes a particular row group by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delref)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delref)]  
  
## <a name="example"></a><span data-ttu-id="5c2d0-122">Пример</span><span class="sxs-lookup"><span data-stu-id="5c2d0-122">Example</span></span>  
 <span data-ttu-id="5c2d0-123">В следующем примере удаляется определенная группа строк по индексу.</span><span class="sxs-lookup"><span data-stu-id="5c2d0-123">The following example removes a particular row group by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delindex)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delindex)]  
  
## <a name="example"></a><span data-ttu-id="5c2d0-124">Пример</span><span class="sxs-lookup"><span data-stu-id="5c2d0-124">Example</span></span>  
 <span data-ttu-id="5c2d0-125">В следующем примере удаляются все группы строк из коллекции групп строк таблицы.</span><span class="sxs-lookup"><span data-stu-id="5c2d0-125">The following example removes all row groups from the table's row groups collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_clear)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="5c2d0-126">См. также</span><span class="sxs-lookup"><span data-stu-id="5c2d0-126">See also</span></span>

- [<span data-ttu-id="5c2d0-127">Практическое руководство. Обработка элементов растягиваемого содержимого с помощью свойства Inlines</span><span class="sxs-lookup"><span data-stu-id="5c2d0-127">How-to: Manipulate Flow Content Elements through the Inlines Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="5c2d0-128">Управление FlowDocument с помощью свойства Blocks</span><span class="sxs-lookup"><span data-stu-id="5c2d0-128">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="5c2d0-129">Управление столбцами таблицы с помощью свойства Columns</span><span class="sxs-lookup"><span data-stu-id="5c2d0-129">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
