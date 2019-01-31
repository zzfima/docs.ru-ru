---
title: Как выполнить Управление столбцами таблицы с помощью свойства Columns
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
ms.openlocfilehash: e3327b59cb8c387cb554206d1b17c2cd7002ef80
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258101"
---
# <a name="how-to-manipulate-a-tables-columns-through-the-columns-property"></a><span data-ttu-id="48740-102">Как выполнить Управление столбцами таблицы с помощью свойства Columns</span><span class="sxs-lookup"><span data-stu-id="48740-102">How to: Manipulate a Table's Columns through the Columns Property</span></span>
<span data-ttu-id="48740-103">В этом примере показаны некоторые из наиболее распространенных операций, которые могут выполняться над столбцами таблицы с помощью <xref:System.Windows.Documents.Table.Columns%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="48740-103">This example demonstrates some of the more common operations that can be performed on a table's columns through the <xref:System.Windows.Documents.Table.Columns%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48740-104">Пример</span><span class="sxs-lookup"><span data-stu-id="48740-104">Example</span></span>  
 <span data-ttu-id="48740-105">В следующем примере создается новая таблица и затем использует <xref:System.Windows.Documents.TableColumnCollection.Add%2A> метод для добавления столбцов в таблицу <xref:System.Windows.Documents.Table.Columns%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="48740-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableColumnCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a><span data-ttu-id="48740-106">Пример</span><span class="sxs-lookup"><span data-stu-id="48740-106">Example</span></span>  
 <span data-ttu-id="48740-107">В следующем примере вставляется новый <xref:System.Windows.Documents.TableColumn>.</span><span class="sxs-lookup"><span data-stu-id="48740-107">The following example inserts a new <xref:System.Windows.Documents.TableColumn>.</span></span>  <span data-ttu-id="48740-108">Новый столбец вставляется в позиции индекса 0, делая его первым столбцом в таблице.</span><span class="sxs-lookup"><span data-stu-id="48740-108">The new column is inserted at index position 0, making it the new first column in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48740-109"><xref:System.Windows.Documents.TableColumnCollection> Коллекция использует стандартную индексацию с нуля.</span><span class="sxs-lookup"><span data-stu-id="48740-109">The <xref:System.Windows.Documents.TableColumnCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a><span data-ttu-id="48740-110">Пример</span><span class="sxs-lookup"><span data-stu-id="48740-110">Example</span></span>  
 <span data-ttu-id="48740-111">Следующий пример обращается к некоторые произвольные свойства для столбцов в <xref:System.Windows.Documents.TableColumnCollection> коллекции, ссылающийся на определенных столбцов по индексу.</span><span class="sxs-lookup"><span data-stu-id="48740-111">The following example accesses some arbitrary properties on columns in the <xref:System.Windows.Documents.TableColumnCollection> collection, referring to particular columns by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a><span data-ttu-id="48740-112">Пример</span><span class="sxs-lookup"><span data-stu-id="48740-112">Example</span></span>  
 <span data-ttu-id="48740-113">Следующий пример возвращает количество столбцов, в настоящий момент размещенные в таблице.</span><span class="sxs-lookup"><span data-stu-id="48740-113">The following example gets the number of columns currently hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a><span data-ttu-id="48740-114">Пример</span><span class="sxs-lookup"><span data-stu-id="48740-114">Example</span></span>  
 <span data-ttu-id="48740-115">Следующий пример удаляет определенный столбец по ссылке.</span><span class="sxs-lookup"><span data-stu-id="48740-115">The following example removes a particular column by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a><span data-ttu-id="48740-116">Пример</span><span class="sxs-lookup"><span data-stu-id="48740-116">Example</span></span>  
 <span data-ttu-id="48740-117">Следующий пример удаляет определенный столбец по индексу.</span><span class="sxs-lookup"><span data-stu-id="48740-117">The following example removes a particular column by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a><span data-ttu-id="48740-118">Пример</span><span class="sxs-lookup"><span data-stu-id="48740-118">Example</span></span>  
 <span data-ttu-id="48740-119">Следующий пример удаляет все столбцы из коллекции столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="48740-119">The following example removes all columns from the table's columns collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="48740-120">См. также</span><span class="sxs-lookup"><span data-stu-id="48740-120">See also</span></span>
- [<span data-ttu-id="48740-121">Общие сведения о таблицах</span><span class="sxs-lookup"><span data-stu-id="48740-121">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)
- [<span data-ttu-id="48740-122">Определение таблицы с помощью XAML</span><span class="sxs-lookup"><span data-stu-id="48740-122">Define a Table with XAML</span></span>](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="48740-123">Создание таблицы программным способом</span><span class="sxs-lookup"><span data-stu-id="48740-123">Build a Table Programmatically</span></span>](../../../../docs/framework/wpf/advanced/how-to-build-a-table-programmatically.md)
- [<span data-ttu-id="48740-124">Управление группами строк таблицы пользователя с помощью свойства RowGroups</span><span class="sxs-lookup"><span data-stu-id="48740-124">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="48740-125">Управление FlowDocument с помощью свойства Blocks</span><span class="sxs-lookup"><span data-stu-id="48740-125">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="48740-126">Управление группами строк таблицы пользователя с помощью свойства RowGroups</span><span class="sxs-lookup"><span data-stu-id="48740-126">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
