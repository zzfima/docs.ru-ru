---
title: 'Как: управлять таблицы&#39;s столбцов с помощью свойства столбцов'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating table columns
- properties [WPF], Columns [WPF], manipulating table columns
- tables [WPF], manipulating columns
- Columns property [WPF]
ms.assetid: 3f8884f4-7e1f-456b-be06-fbd3cf469bf3
ms.openlocfilehash: 916764c621738ddc651580f1232e1f579a17e6f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545302"
---
# <a name="how-to-manipulate-a-table39s-columns-through-the-columns-property"></a><span data-ttu-id="f3edb-102">Как: управлять таблицы&#39;s столбцов с помощью свойства столбцов</span><span class="sxs-lookup"><span data-stu-id="f3edb-102">How to: Manipulate a Table&#39;s Columns through the Columns Property</span></span>
<span data-ttu-id="f3edb-103">В этом примере показаны некоторые из наиболее распространенных операций, которые могут выполняться над столбцами таблицы с помощью <xref:System.Windows.Documents.Table.Columns%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f3edb-103">This example demonstrates some of the more common operations that can be performed on a table's columns through the <xref:System.Windows.Documents.Table.Columns%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3edb-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f3edb-104">Example</span></span>  
 <span data-ttu-id="f3edb-105">В следующем примере создается новая таблица и затем использует <xref:System.Windows.Documents.TableColumnCollection.Add%2A> метод для добавления столбцов в таблице <xref:System.Windows.Documents.Table.Columns%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="f3edb-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableColumnCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a><span data-ttu-id="f3edb-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f3edb-106">Example</span></span>  
 <span data-ttu-id="f3edb-107">Следующий пример вставляет новый <xref:System.Windows.Documents.TableColumn>.</span><span class="sxs-lookup"><span data-stu-id="f3edb-107">The following example inserts a new <xref:System.Windows.Documents.TableColumn>.</span></span>  <span data-ttu-id="f3edb-108">Новый столбец вставляется в позиции индекса 0, что делает его первым столбцом в таблице.</span><span class="sxs-lookup"><span data-stu-id="f3edb-108">The new column is inserted at index position 0, making it the new first column in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3edb-109"><xref:System.Windows.Documents.TableColumnCollection> Коллекция использует стандартную индексацию с нуля.</span><span class="sxs-lookup"><span data-stu-id="f3edb-109">The <xref:System.Windows.Documents.TableColumnCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a><span data-ttu-id="f3edb-110">Пример</span><span class="sxs-lookup"><span data-stu-id="f3edb-110">Example</span></span>  
 <span data-ttu-id="f3edb-111">Следующий пример получает доступ к некоторым произвольным свойствам столбцов в <xref:System.Windows.Documents.TableColumnCollection> коллекции, ссылающиеся на определенных столбцов с помощью индекса.</span><span class="sxs-lookup"><span data-stu-id="f3edb-111">The following example accesses some arbitrary properties on columns in the <xref:System.Windows.Documents.TableColumnCollection> collection, referring to particular columns by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a><span data-ttu-id="f3edb-112">Пример</span><span class="sxs-lookup"><span data-stu-id="f3edb-112">Example</span></span>  
 <span data-ttu-id="f3edb-113">В следующем примере возвращается количество столбцов, в настоящее время размещены в таблице.</span><span class="sxs-lookup"><span data-stu-id="f3edb-113">The following example gets the number of columns currently hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a><span data-ttu-id="f3edb-114">Пример</span><span class="sxs-lookup"><span data-stu-id="f3edb-114">Example</span></span>  
 <span data-ttu-id="f3edb-115">Следующий пример удаляет определенный столбец по ссылке.</span><span class="sxs-lookup"><span data-stu-id="f3edb-115">The following example removes a particular column by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a><span data-ttu-id="f3edb-116">Пример</span><span class="sxs-lookup"><span data-stu-id="f3edb-116">Example</span></span>  
 <span data-ttu-id="f3edb-117">Следующий пример удаляет определенный столбец по индексу.</span><span class="sxs-lookup"><span data-stu-id="f3edb-117">The following example removes a particular column by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a><span data-ttu-id="f3edb-118">Пример</span><span class="sxs-lookup"><span data-stu-id="f3edb-118">Example</span></span>  
 <span data-ttu-id="f3edb-119">Следующий пример удаляет все столбцы из коллекции столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="f3edb-119">The following example removes all columns from the table's columns collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="f3edb-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f3edb-120">See Also</span></span>  
 [<span data-ttu-id="f3edb-121">Общие сведения о таблицах</span><span class="sxs-lookup"><span data-stu-id="f3edb-121">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)  
 [<span data-ttu-id="f3edb-122">Определение таблицы с помощью XAML</span><span class="sxs-lookup"><span data-stu-id="f3edb-122">Define a Table with XAML</span></span>](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)  
 [<span data-ttu-id="f3edb-123">Создание таблицы программным способом</span><span class="sxs-lookup"><span data-stu-id="f3edb-123">Build a Table Programmatically</span></span>](../../../../docs/framework/wpf/advanced/how-to-build-a-table-programmatically.md)  
 [<span data-ttu-id="f3edb-124">Управление группами строк таблицы пользователя с помощью свойства RowGroups</span><span class="sxs-lookup"><span data-stu-id="f3edb-124">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [<span data-ttu-id="f3edb-125">Управление FlowDocument с помощью свойства Blocks</span><span class="sxs-lookup"><span data-stu-id="f3edb-125">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="f3edb-126">Управление группами строк таблицы пользователя с помощью свойства RowGroups</span><span class="sxs-lookup"><span data-stu-id="f3edb-126">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
