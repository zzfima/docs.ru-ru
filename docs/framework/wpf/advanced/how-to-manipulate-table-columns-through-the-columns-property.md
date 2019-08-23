---
title: Практическое руководство. Управление столбцами таблицы с помощью свойства Columns
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
ms.openlocfilehash: 18a26c76688ebf668293cb1254404d6d2cf15208
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913596"
---
# <a name="how-to-manipulate-a-tables-columns-through-the-columns-property"></a>Практическое руководство. Управление столбцами таблицы с помощью свойства Columns
В этом примере демонстрируются некоторые из наиболее распространенных операций, которые можно выполнять с столбцами таблицы через <xref:System.Windows.Documents.Table.Columns%2A> свойство.  
  
## <a name="example"></a>Пример  
 В следующем примере создается новая таблица, а затем используется <xref:System.Windows.Documents.TableColumnCollection.Add%2A> метод для добавления столбцов в <xref:System.Windows.Documents.Table.Columns%2A> коллекцию таблицы.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a>Пример  
 В следующем примере вставляется новый <xref:System.Windows.Documents.TableColumn>объект.  Новый столбец вставляется в позиции индекса 0, что делает его новым первым столбцом в таблице.  
  
> [!NOTE]
> В <xref:System.Windows.Documents.TableColumnCollection> коллекции используется стандартная индексация, начинающаяся с нуля.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a>Пример  
 В следующем примере осуществляется доступ к некоторым произвольным свойствам в <xref:System.Windows.Documents.TableColumnCollection> столбцах коллекции, которые ссылаются на определенные столбцы по индексу.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано получение количества столбцов, размещенных в настоящее время в таблице.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a>Пример  
 В следующем примере удаляется определенный столбец по ссылке.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a>Пример  
 В следующем примере удаляется определенный столбец по индексу.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a>Пример  
 В следующем примере удаляются все столбцы из коллекции Columns таблицы.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о таблицах](table-overview.md)
- [Определение таблицы с помощью XAML](how-to-define-a-table-with-xaml.md)
- [Создание таблицы программным способом](how-to-build-a-table-programmatically.md)
- [Управление группами строк таблицы пользователя с помощью свойства RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [Управление FlowDocument с помощью свойства Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Управление группами строк таблицы пользователя с помощью свойства RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
