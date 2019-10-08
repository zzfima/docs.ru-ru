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
ms.openlocfilehash: fa7106207c69f19b647ba80ab7e724e9aad174c1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005075"
---
# <a name="table-overview"></a>Общие сведения о таблицах
<xref:System.Windows.Documents.Table> — это элемент уровня блока, поддерживающий представление содержимого нефиксированного документа на основе сетки. Гибкость этого элемента делает его очень полезным, но также и более сложным для понимания и правильного использования.  
  
 В этом разделе содержатся следующие подразделы.  
  
- [Основные сведения о таблицах](#table_basics)  
  
- [Отличие таблицы от сетки](#table_vs_Grid)  
  
- [Основная структура таблицы](#basic_table_structure)  
  
- [Вложения таблицы](#table_containment)  
  
- [Группирование строк](#row_groupings)  
  
- [Приоритет отрисовки фона](#rendering_precedence)  
  
- [Объединение строк или столбцов](#spanning_rows_or_columns)  
  
- [Создание таблицы с помощью кода](#building_a_table_with_code)  
  
- [Связанные разделы] 
  
<a name="table_basics"></a>   
## <a name="table-basics"></a>Основные сведения о таблицах  
  
<a name="table_vs_Grid"></a>   
### <a name="how-is-table-different-then-grid"></a>Отличие таблицы от сетки  
 <xref:System.Windows.Documents.Table> и <xref:System.Windows.Controls.Grid> совместно используют некоторые общие функции, но каждый из них лучше всего подходит для различных сценариев. @No__t-0 предназначен для использования в содержимом нефиксированного формата (Дополнительные сведения о нефиксированном содержимом см. в разделе [Общие сведения о документе](flow-document-overview.md) нефиксированного формата). Сетки лучше всего использовать внутри форм (по сути в любом месте вне потокового содержимого). В <xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.Documents.Table> поддерживает поведение нефиксированного содержимого, например разбивку на страницы, перекомпоновку столбцов и выбор содержимого, а <xref:System.Windows.Controls.Grid> — нет. @No__t-0 с другой стороны лучше использовать за пределами <xref:System.Windows.Documents.FlowDocument> по многим причинам, включая <xref:System.Windows.Controls.Grid> добавляет элементы на основе индекса строки и столбца, <xref:System.Windows.Documents.Table> — нет. Элемент <xref:System.Windows.Controls.Grid> позволяет разложить разслойировать дочернее содержимое, допуская наличие в одной "ячейке" более одного элемента. <xref:System.Windows.Documents.Table> не поддерживает многоуровневые слои. Дочерние элементы <xref:System.Windows.Controls.Grid> могут быть абсолютно расположены относительно области их границ "ячейка". <xref:System.Windows.Documents.Table> не поддерживает эту функцию. Наконец, <xref:System.Windows.Controls.Grid> требует меньше ресурсов, а <xref:System.Windows.Documents.Table>, поэтому рекомендуется использовать <xref:System.Windows.Controls.Grid> для повышения производительности.  
  
<a name="basic_table_structure"></a>   
### <a name="basic-table-structure"></a>Основная структура таблицы  
 <xref:System.Windows.Documents.Table> предоставляет представление на основе сетки, состоящее из столбцов (представленных элементами <xref:System.Windows.Documents.TableColumn>) и строк (представленных элементами <xref:System.Windows.Documents.TableRow>). элементы <xref:System.Windows.Documents.TableColumn> не размещают содержимое; они просто определяют столбцы и характеристики столбцов. элементы <xref:System.Windows.Documents.TableRow> должны размещаться в элементе <xref:System.Windows.Documents.TableRowGroup>, который определяет группирование строк для таблицы. элементы <xref:System.Windows.Documents.TableCell>, которые содержат реальное содержимое, которое должно быть представлено таблицей, должны размещаться в элементе <xref:System.Windows.Documents.TableRow>. <xref:System.Windows.Documents.TableCell> может содержать только элементы, производные от <xref:System.Windows.Documents.Block>.  Допустимые дочерние элементы для <xref:System.Windows.Documents.TableCell> include.  
  
- <xref:System.Windows.Documents.BlockUIContainer>  
  
- <xref:System.Windows.Documents.List>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
> элементы <xref:System.Windows.Documents.TableCell> не могут напрямую размещать текстовое содержимое. Дополнительные сведения о правилах включения для элементов содержимого нефиксированного формата, таких как <xref:System.Windows.Documents.TableCell>, см. в разделе [Общие сведения о документе нефиксированного формата](flow-document-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Documents.Table> аналогична элементу <xref:System.Windows.Controls.Grid>, но имеет больше возможностей и, следовательно, требует большего объема ресурсов.  
  
 В следующем примере определяется простая таблица 2 x 3 с XAML.  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 На следующем рисунке показана отрисовка этого примера.  
  
 ![Снимок экрана, показывающий, как отображается базовая таблица.](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>   
### <a name="table-containment"></a>Вложения таблицы  
 <xref:System.Windows.Documents.Table> является производным от элемента <xref:System.Windows.Documents.Block> и соответствует общим правилам для элементов уровня <xref:System.Windows.Documents.Block>.  Элемент <xref:System.Windows.Documents.Table> может содержаться в одном из следующих элементов:  
  
- <xref:System.Windows.Documents.FlowDocument>  
  
- <xref:System.Windows.Documents.TableCell>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### <a name="row-groupings"></a>Группирование строк  
 Элемент <xref:System.Windows.Documents.TableRowGroup> предоставляет возможность произвольного группирования строк в таблице; Каждая строка в таблице должна принадлежать к группированию строк.  Строки в группе часто имеют общее назначение и могут быть стилизованы в виде группы.  Обычно группирование строк используется для отделения строк специального назначения, например строк названия, заголовка и нижнего колонтитула, от основного содержимого, находящегося в таблице.  
  
 В следующем примере XAML используется для определения таблицы со строками верхнего и нижнего колонтитулов.  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 На следующем рисунке показана отрисовка этого примера.  
  
 @no__t 0Screenshot: Группы строк таблицы @ no__t-0(./media/table-rowgroups.png "Table_RowGroups")  
  
<a name="rendering_precedence"></a>   
### <a name="background-rendering-precedence"></a>Приоритет отрисовки фона  
 Элементы таблицы отрисовываются в следующем порядке (z-порядок от нижнего к верхнему). Этот порядок нельзя изменить. Например, для этих элементов не существует свойства "Z-порядок", которое можно использовать для переопределения этого установленного порядка.  
  
1. <xref:System.Windows.Documents.Table>  
  
2. <xref:System.Windows.Documents.TableColumn>  
  
3. <xref:System.Windows.Documents.TableRowGroup>  
  
4. <xref:System.Windows.Documents.TableRow>  
  
5. <xref:System.Windows.Documents.TableCell>  
  
 Рассмотрим следующий пример, в котором задается цвет фона для каждого из этих элементов в таблице.  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 На следующем рисунке показана отрисовка этого примера (показаны только фоновые цвета).  
  
 @no__t 0Screenshot: Таблица z&#45;Order @ no__t-1(./media/table-zorder.png "Table_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>   
### <a name="spanning-rows-or-columns"></a>Объединение строк или столбцов  
 Ячейки таблицы могут быть настроены на охват нескольких строк или столбцов с помощью атрибутов <xref:System.Windows.Documents.TableCell.RowSpan%2A> или <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> соответственно.  
  
 Рассмотрим следующий пример, в котором ячейка включает три столбца.  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 На следующем рисунке показана отрисовка этого примера.  
  
 @no__t 0Screenshot: Ячейка, охватывающая все три столбца @ no__t-0(./media/table-columnspan.png "Table_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>   
## <a name="building-a-table-with-code"></a>Построение таблицы с помощью кода  
 В следующих примерах показано, как программным способом создать <xref:System.Windows.Documents.Table> и заполнить его содержимым. Содержимое таблицы распределено по пяти строкам (представленным объектами <xref:System.Windows.Documents.TableRow>, содержащимся в объекте <xref:System.Windows.Documents.Table.RowGroups%2A>) и шести столбцах (представленных объектами <xref:System.Windows.Documents.TableColumn>). Строки используются для различных целей представления, включая строку названия, предназначенную для заголовка всей таблицы, строку заголовка для описания столбцов данных в таблице и строку нижнего колонтитула для сводной информации.  Обратите внимание, что строки "title", "header" и "footer" не встроены в таблицу. Это просто строки с разными характеристиками. Ячейки таблицы содержат фактическое содержимое, которое может состоять из текста, изображений или практически любого другого элемента [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
 Во-первых, создается <xref:System.Windows.Documents.FlowDocument> для размещения <xref:System.Windows.Documents.Table>, а также создается новый <xref:System.Windows.Documents.Table>, который добавляется к содержимому <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 Затем создается шесть объектов <xref:System.Windows.Documents.TableColumn> и добавляется в коллекцию <xref:System.Windows.Documents.Table.Columns%2A> с применением определенного форматирования.  
  
> [!NOTE]
> Обратите внимание, что коллекция <xref:System.Windows.Documents.Table.Columns%2A> таблицы использует стандартную индексацию, начинающуюся с нуля.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 Затем создается строка заголовка и добавляется в таблицу с определенным форматированием.  Строка названия содержит одну ячейку, охватывающую все шесть столбцов таблицы.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 Далее создается и добавляется в таблицу строка заголовка, а ячейки в строке заголовка создаются и заполняются содержимым.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 Затем создается и добавляется в таблицу строка для данных, создаются ячейки в этой строке и заполняются содержимым.  Построение этой строки аналогично построению строки заголовка с применением немного другого форматирования.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 Наконец, создается, добавляется и форматируется строка нижнего колонтитула.  Как и строка названия, нижний колонтитул содержит одну ячейку, которая включает все шесть столбцов в таблице.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о документах нефиксированного формата](flow-document-overview.md)
- [Определение таблицы с помощью XAML](how-to-define-a-table-with-xaml.md)
- [Документы в WPF](documents-in-wpf.md)
- [Использование элементов потокового содержимого](how-to-use-flow-content-elements.md)
