---
title: Практическое руководство. Создание таблицы программным способом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables [WPF], creating programmatically
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
ms.openlocfilehash: 9c9061d3c4d6b3de5e1ab42a6b98c20813835ba8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964159"
---
# <a name="how-to-build-a-table-programmatically"></a>Практическое руководство. Создание таблицы программным способом
В следующих примерах показано, как программным <xref:System.Windows.Documents.Table> способом создать и заполнить его содержимым. Содержимое таблицы делится на пять строк (представленные <xref:System.Windows.Documents.TableRow> объектами, содержащимися <xref:System.Windows.Documents.Table.RowGroups%2A> в объекте) и <xref:System.Windows.Documents.TableColumn> шесть столбцов (представленных объектами). Строки используются для различных целей представления, включая строку названия, предназначенную для заголовка всей таблицы, строку заголовка для описания столбцов данных в таблице и строку нижнего колонтитула для сводной информации.  Обратите внимание, что строки "title", "header" и "footer" не встроены в таблицу. Это просто строки с разными характеристиками. Ячейки таблицы содержат фактическое содержимое, которое может состоять из текста, изображений или практически любого другого [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] элемента.  
  
## <a name="example"></a>Пример  
 Во <xref:System.Windows.Documents.FlowDocument> -первых, создается для <xref:System.Windows.Documents.Table>размещения, а новый <xref:System.Windows.Documents.Table> <xref:System.Windows.Documents.FlowDocument>создается и добавляется к содержимому.  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## <a name="example"></a>Пример  
 Затем создается шесть <xref:System.Windows.Documents.TableColumn> объектов и добавляется в <xref:System.Windows.Documents.Table.Columns%2A> коллекцию таблицы с применением определенного форматирования.  
  
> [!NOTE]
> Обратите внимание, что <xref:System.Windows.Documents.Table.Columns%2A> в коллекции таблицы используется стандартная индексация, начинающаяся с нуля.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## <a name="example"></a>Пример  
 Затем создается строка заголовка и добавляется в таблицу с определенным форматированием.  Строка названия содержит одну ячейку, охватывающую все шесть столбцов таблицы.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## <a name="example"></a>Пример  
 Далее создается и добавляется в таблицу строка заголовка, а ячейки в строке заголовка создаются и заполняются содержимым.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## <a name="example"></a>Пример  
 Затем создается и добавляется в таблицу ряд данных, а ячейки в этой строке создаются и заполняются содержимым.  Построение этой строки аналогично построению строки заголовка с применением немного другого форматирования.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## <a name="example"></a>Пример  
 Наконец, создается, добавляется и форматируется строка нижнего колонтитула.  Как и строка названия, нижний колонтитул содержит одну ячейку, которая включает все шесть столбцов в таблице.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о таблицах](table-overview.md)
