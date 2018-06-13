---
title: Общие сведения о таблицах
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], Table
- documents [WPF], tables
- tables [WPF]
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
ms.openlocfilehash: 631a14ae8eb17713186f7db66700026cc476024e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549374"
---
# <a name="table-overview"></a>Общие сведения о таблицах
<xref:System.Windows.Documents.Table> Представляет элемент уровня блока, поддерживающий представление на основе сетки содержимого документа. Гибкость этого элемента делает его очень полезным, но также и более сложным для понимания и правильного использования.  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Основные сведения о таблицах](#table_basics)  
  
-   [Отличие таблицы от сетки](#table_vs_Grid)  
  
-   [Основная структура таблицы](#basic_table_structure)  
  
-   [Вложения таблицы](#table_containment)  
  
-   [Группирование строк](#row_groupings)  
  
-   [Приоритет отрисовки фона](#rendering_precedence)  
  
-   [Объединение строк или столбцов](#spanning_rows_or_columns)  
  
-   [Создание таблицы с помощью кода](#building_a_table_with_code)  
  
-   [Связанные разделы] 
  
<a name="table_basics"></a>   
## <a name="table-basics"></a>Основные сведения о таблицах  
  
<a name="table_vs_Grid"></a>   
### <a name="how-is-table-different-then-grid"></a>Отличие таблицы от сетки  
 <xref:System.Windows.Documents.Table> и <xref:System.Windows.Controls.Grid> совместно используют некоторые общие функциональные возможности, но каждый из них лучше всего подходят для различных сценариев. Объект <xref:System.Windows.Documents.Table> предназначен для использования в содержимом нефиксированного формата (см. [Обзор передачи документа](../../../../docs/framework/wpf/advanced/flow-document-overview.md) Дополнительные сведения о содержимом потока). Сетки лучше всего использовать внутри форм (по сути в любом месте вне потокового содержимого). В пределах <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> поддерживает потока такие возможности, как разбиение на страницы, обратный порядок столбцов и Выбор содержимого во время <xref:System.Windows.Controls.Grid> — нет. Объект <xref:System.Windows.Controls.Grid> с другой стороны лучше всего использовать за пределами <xref:System.Windows.Documents.FlowDocument> по многим причинам, в том числе <xref:System.Windows.Controls.Grid> добавляет элементы на основе строк и столбцов индекса, <xref:System.Windows.Documents.Table> — нет. <xref:System.Windows.Controls.Grid> Элемент позволяет слоев дочернее содержимое, что позволяет более одного элемента в одной «ячейки». <xref:System.Windows.Documents.Table> не поддерживает иерархическое представление. Дочерние элементы <xref:System.Windows.Controls.Grid> могут быть расположены абсолютно относительно границы «ячейки». <xref:System.Windows.Documents.Table> не поддерживает эту функцию. Наконец <xref:System.Windows.Controls.Grid> требует меньше ресурсов, а затем <xref:System.Windows.Documents.Table> поэтому рассмотрите возможность использования <xref:System.Windows.Controls.Grid> для повышения производительности.  
  
<a name="basic_table_structure"></a>   
### <a name="basic-table-structure"></a>Основная структура таблицы  
 <xref:System.Windows.Documents.Table> предоставляет представления на основе сетки, состоящий из столбцов (представленного <xref:System.Windows.Documents.TableColumn> элементы) и строки (представленного <xref:System.Windows.Documents.TableRow> элементов). <xref:System.Windows.Documents.TableColumn> не размещайте элементов содержимого; они просто определяют столбцы и их характеристики. <xref:System.Windows.Documents.TableRow> элементы должны размещаться в <xref:System.Windows.Documents.TableRowGroup> элемент, который определяет группирование строк в таблице. <xref:System.Windows.Documents.TableCell> элементы, которые содержат фактические данные, отображаемые в таблице, должны размещаться в <xref:System.Windows.Documents.TableRow> элемент. <xref:System.Windows.Documents.TableCell> может содержать только элементы, которые являются производными от <xref:System.Windows.Documents.Block>.  Допустимые дочерние элементы для <xref:System.Windows.Documents.TableCell> включают.  
  
-   <xref:System.Windows.Documents.BlockUIContainer>  
  
-   <xref:System.Windows.Documents.List>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
>  <xref:System.Windows.Documents.TableCell> элементы не могут содержать текстовых данных. Дополнительные сведения о правила вместимости потока содержимого элементы, такие как <xref:System.Windows.Documents.TableCell>, в разделе [Обзор передачи документа](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Table> Аналогично <xref:System.Windows.Controls.Grid> элемент но имеет больше возможностей и, следовательно, требует больше ресурсов.  
  
 В следующем примере определяется простой таблицы 2 x 3 с [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 На следующем рисунке показана отрисовка этого примера.  
  
 ![Снимок экрана: отрисовка базовой таблицы](../../../../docs/framework/wpf/advanced/media/basictablerrender.png "BasicTablerRender")  
  
<a name="table_containment"></a>   
### <a name="table-containment"></a>Вложения таблицы  
 <xref:System.Windows.Documents.Table> является производным от <xref:System.Windows.Documents.Block> элемент и наследует общие правила для <xref:System.Windows.Documents.Block> элементов уровня.  Объект <xref:System.Windows.Documents.Table> элемент могут содержаться каким-либо из следующих элементов:  
  
-   <xref:System.Windows.Documents.FlowDocument>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### <a name="row-groupings"></a>Группирование строк  
 <xref:System.Windows.Documents.TableRowGroup> Элемент предоставляет способ произвольной группировки строк в таблицу, каждая строка в таблице должна принадлежать группе строк.  Строки в группе часто имеют общее назначение и могут быть стилизованы в виде группы.  Обычно группирование строк используется для отделения строк специального назначения, например строк названия, заголовка и нижнего колонтитула, от основного содержимого, находящегося в таблице.  
  
 В следующем примере используется [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] определение таблицы с примененным стилем строки верхнего и нижнего колонтитулов.  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 На следующем рисунке показана отрисовка этого примера.  
  
 ![Снимок экрана: группы строк таблицы](../../../../docs/framework/wpf/advanced/media/table-rowgroups.png "Table_RowGroups")  
  
<a name="rendering_precedence"></a>   
### <a name="background-rendering-precedence"></a>Приоритет отрисовки фона  
 Элементы таблицы отрисовываются в следующем порядке (z-порядок от нижнего к верхнему). Этот порядок нельзя изменить. Например, для этих элементов не существует свойства "Z-порядок", которое можно использовать для переопределения этого установленного порядка.  
  
1.  <xref:System.Windows.Documents.Table>  
  
2.  <xref:System.Windows.Documents.TableColumn>  
  
3.  <xref:System.Windows.Documents.TableRowGroup>  
  
4.  <xref:System.Windows.Documents.TableRow>  
  
5.  <xref:System.Windows.Documents.TableCell>  
  
 Рассмотрим следующий пример, в котором задается цвет фона для каждого из этих элементов в таблице.  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 На следующем рисунке показана отрисовка этого примера (показаны только фоновые цвета).  
  
 ![Снимок экрана: Z-порядок таблицы](../../../../docs/framework/wpf/advanced/media/table-zorder.png "Table_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>   
### <a name="spanning-rows-or-columns"></a>Объединение строк или столбцов  
 Ячейки таблицы могут быть настроены для охватывать несколько строк или столбцов с помощью <xref:System.Windows.Documents.TableCell.RowSpan%2A> или <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> соответственно.  
  
 Рассмотрим следующий пример, в котором ячейка включает три столбца.  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 На следующем рисунке показана отрисовка этого примера.  
  
 ![Снимок экрана: ячейка, охватывающая три столбца](../../../../docs/framework/wpf/advanced/media/table-columnspan.png "Table_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>   
## <a name="building-a-table-with-code"></a>Построение таблицы с помощью кода  
 Следующие примеры показывают, как программным способом создать <xref:System.Windows.Documents.Table> и заполнить ее содержимым. Содержимое таблицы распределено по пяти строк (представленного <xref:System.Windows.Documents.TableRow> объектов, содержащихся в <xref:System.Windows.Documents.Table.RowGroups%2A> объекта) и шесть столбцов (представленного <xref:System.Windows.Documents.TableColumn> объектов). Строки используются для различных целей представления, включая строку названия, предназначенную для заголовка всей таблицы, строку заголовка для описания столбцов данных в таблице и строку нижнего колонтитула для сводной информации.  Обратите внимание, что строки "title", "header" и "footer" не встроены в таблицу. Это просто строки с разными характеристиками. Ячейки таблицы содержат фактическое содержимое, которое может включать текст, изображения или практически любых других [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] элемента.  
  
 Во-первых, <xref:System.Windows.Documents.FlowDocument> создается узел <xref:System.Windows.Documents.Table>и новый <xref:System.Windows.Documents.Table> создается и добавляется к содержимому <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 Далее, шести <xref:System.Windows.Documents.TableColumn> объекты создаются и добавляются в таблицу <xref:System.Windows.Documents.Table.Columns%2A> коллекции с применением некоторого форматирования.  
  
> [!NOTE]
>  Обратите внимание, что таблицы <xref:System.Windows.Documents.Table.Columns%2A> коллекция использует стандартную индексацию с нуля.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 Затем создается строка заголовка и добавляется в таблицу с определенным форматированием.  Строка названия содержит одну ячейку, охватывающую все шесть столбцов таблицы.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 Далее создается и добавляется в таблицу строка заголовка, а ячейки в строке заголовка создаются и заполняются содержимым.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 Затем создается и добавляется в таблицу строка для данных, создаются ячейки в этой строке и заполняются содержимым.  Построение этой строки аналогично построению строки заголовка с применением немного другого форматирования.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 Наконец, создается, добавляется и форматируется строка нижнего колонтитула.  Как и строка названия, нижний колонтитул содержит одну ячейку, которая включает все шесть столбцов в таблице.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о документе нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [Определение таблицы с помощью XAML](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)  
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Использование элементов потокового содержимого](../../../../docs/framework/wpf/advanced/how-to-use-flow-content-elements.md)
