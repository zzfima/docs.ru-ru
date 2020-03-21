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
ms.openlocfilehash: 4bd747cea43755116c56b16f1de9a6ffb59935ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187272"
---
# <a name="table-overview"></a>Общие сведения о таблицах
<xref:System.Windows.Documents.Table>— это элемент уровня блока, поддерживающий презентацию содержимого документа Flow на основе сетки. Гибкость этого элемента делает его очень полезным, но также и более сложным для понимания и правильного использования.  
  
 Эта тема описана в следующих разделах.  
  
- [Основные сведения о таблицах](#table_basics)  
  
- [Отличие таблицы от сетки](#table_vs_Grid)  
  
- [Основная структура таблицы](#basic_table_structure)  
  
- [Вложения таблицы](#table_containment)  
  
- [Группирование строк](#row_groupings)  
  
- [Приоритет отрисовки фона](#rendering_precedence)  
  
- [Объединение строк или столбцов](#spanning_rows_or_columns)  
  
- [Построение таблицы с помощью кода](#building_a_table_with_code)  
  
- [Связанные разделы]
  
<a name="table_basics"></a>
## <a name="table-basics"></a>Основные сведения о таблицах  
  
<a name="table_vs_Grid"></a>
### <a name="how-is-table-different-then-grid"></a>Отличие таблицы от сетки  
 <xref:System.Windows.Documents.Table>и <xref:System.Windows.Controls.Grid> имеют некоторые общие функциональные возможности, но каждый из них лучше всего подходит для различных сценариев. A <xref:System.Windows.Documents.Table> предназначен для использования в содержимом потока (см. [Обзор документов потока](flow-document-overview.md) для получения дополнительной информации о содержимом потока). Сетки лучше всего использовать внутри форм (по сути, в любом месте вне потокового содержимого). <xref:System.Windows.Documents.FlowDocument>В рамках, <xref:System.Windows.Documents.Table> поддерживает поведение содержимого потока, как pagination, колонка reflow, и выбор содержимого в то время как <xref:System.Windows.Controls.Grid> нет. A <xref:System.Windows.Controls.Grid> с другой стороны, лучше <xref:System.Windows.Documents.FlowDocument> всего использовать <xref:System.Windows.Controls.Grid> за пределами по многим <xref:System.Windows.Documents.Table> причинам, включая добавленные элементы, основанные на строке и индексе столбца, не делает. Элемент <xref:System.Windows.Controls.Grid> позволяет наслоение содержимого ребенка, позволяя более чем одному элементу существовать в одной "клетке". <xref:System.Windows.Documents.Table>не поддерживает наслоение. Детские элементы а <xref:System.Windows.Controls.Grid> могут быть абсолютно расположены относительно области их "клеточных" границ. <xref:System.Windows.Documents.Table>не поддерживает эту функцию. Наконец, <xref:System.Windows.Controls.Grid> требуется меньше <xref:System.Windows.Documents.Table> ресурсов, <xref:System.Windows.Controls.Grid> то так рассмотреть возможность использования для повышения производительности.  
  
<a name="basic_table_structure"></a>
### <a name="basic-table-structure"></a>Основная структура таблицы  
 <xref:System.Windows.Documents.Table>обеспечивает представление на основе сетки, состоящее <xref:System.Windows.Documents.TableColumn> из столбцов (представленных <xref:System.Windows.Documents.TableRow> элементами) и строк (представленных элементами). <xref:System.Windows.Documents.TableColumn>элементы не размещают контент; они просто определяют столбцы и характеристики столбцов. <xref:System.Windows.Documents.TableRow>элементы должны размещаться в элементе, <xref:System.Windows.Documents.TableRowGroup> который определяет группировку строк для таблицы. <xref:System.Windows.Documents.TableCell>элементы, содержащие фактическое содержание, представленное таблицей, <xref:System.Windows.Documents.TableRow> должны быть размещены в элементе. <xref:System.Windows.Documents.TableCell>может содержать только элементы, которые вытекают из <xref:System.Windows.Documents.Block>.  Действительные элементы <xref:System.Windows.Documents.TableCell> ребенка для включения.  
  
- <xref:System.Windows.Documents.BlockUIContainer>  
  
- <xref:System.Windows.Documents.List>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
> <xref:System.Windows.Documents.TableCell>элементы не могут напрямую размещать текстовое содержимое. Для получения дополнительной информации о правилах <xref:System.Windows.Documents.TableCell>сдерживания для элементов содержания потока, таких как, [см.](flow-document-overview.md)  
  
> [!NOTE]
> <xref:System.Windows.Documents.Table>похож на <xref:System.Windows.Controls.Grid> элемент, но имеет больше возможностей и, следовательно, требует больших накладных расходов ресурсов.  
  
 Следующий пример определяет простую таблицу 2 x 3 с XAML.  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 На следующем рисунке показано, как этот пример отрисовывается.  
  
 ![Скриншот, который показывает, как отображается базовая таблица.](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>
### <a name="table-containment"></a>Вложения таблицы  
 <xref:System.Windows.Documents.Table>вытекает из <xref:System.Windows.Documents.Block> элемента и придерживается общих правил для <xref:System.Windows.Documents.Block> элементов уровня.  Элемент <xref:System.Windows.Documents.Table> может содержаться любым из следующих элементов:  
  
- <xref:System.Windows.Documents.FlowDocument>  
  
- <xref:System.Windows.Documents.TableCell>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>
### <a name="row-groupings"></a>Группирование строк  
 Элемент <xref:System.Windows.Documents.TableRowGroup> обеспечивает способ произвольного группового ряда в таблице; каждая строка в таблице должна принадлежать группе строки.  Строки в группе часто имеют общее назначение и могут быть стилизованы в виде группы.  Обычно группирование строк используется для отделения строк специального назначения, например строк названия, заголовка и нижнего колонтитула, от основного содержимого, находящегося в таблице.  
  
 В следующем примере используется XAML для определения таблицы со стилизованными строками заголовка и колонтитула.  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 На следующем рисунке показано, как этот пример отрисовывается.  
  
 ![Снимок экрана: группы строк таблицы](./media/table-rowgroups.png "Table_RowGroups")  
  
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
  
 ![Скриншот: Таблица z&#45;заказ](./media/table-zorder.png "Table_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>
### <a name="spanning-rows-or-columns"></a>Объединение строк или столбцов  
 Ячейки таблицы могут быть настроены для охвата <xref:System.Windows.Documents.TableCell.RowSpan%2A> <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> нескольких строк или столбцов с помощью или атрибутов, соответственно.  
  
 Рассмотрим следующий пример, в котором ячейка включает три столбца.  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 На следующем рисунке показано, как этот пример отрисовывается.  
  
 ![Снимок экрана: интервал ячеек в трех столбцах](./media/table-columnspan.png "Table_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>
## <a name="building-a-table-with-code"></a>Построение таблицы с помощью кода  
 Следующие примеры показывают, как <xref:System.Windows.Documents.Table> программно создать и заселить его с содержанием. Содержимое таблицы распределяется по пяти рядам (представленным <xref:System.Windows.Documents.TableRow> объектами, содержащимися в <xref:System.Windows.Documents.Table.RowGroups%2A> объекте) и шести столбцов (представленных <xref:System.Windows.Documents.TableColumn> объектами). Строки используются для различных целей представления, включая строку названия, предназначенную для заголовка всей таблицы, строку заголовка для описания столбцов данных в таблице и строку нижнего колонтитула для сводной информации.  Обратите внимание, что строки "title", "header" и "footer" не встроены в таблицу. Это просто строки с разными характеристиками. Ячейки таблиц содержат фактическое содержимое, которое может состоять [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] из текста, изображений или почти любого другого элемента.  
  
 Во-первых, <xref:System.Windows.Documents.FlowDocument> создается <xref:System.Windows.Documents.Table>для размещения, <xref:System.Windows.Documents.Table> и новый создается <xref:System.Windows.Documents.FlowDocument>и добавляется к содержимому .  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 Далее <xref:System.Windows.Documents.TableColumn> создаются и добавляются шесть <xref:System.Windows.Documents.Table.Columns%2A> объектов в коллекцию таблицы, при этом применяется некоторая форманформа.  
  
> [!NOTE]
> Обратите внимание, что <xref:System.Windows.Documents.Table.Columns%2A> в коллекции таблицы используется стандартная индексация на нулевой основе.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 Затем создается строка заголовка и добавляется в таблицу с определенным форматированием.  Строка названия содержит одну ячейку, охватывающую все шесть столбцов таблицы.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 Далее создается и добавляется в таблицу строка заголовка, а ячейки в строке заголовка создаются и заполняются содержимым.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 Затем создается и добавляется в таблицу ряд данных, а ячейки в этой строке создаются и заполняются содержимым.  Построение этой строки аналогично построению строки заголовка с применением немного другого форматирования.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 Наконец, создается, добавляется и форматируется строка нижнего колонтитула.  Как и строка названия, нижний колонтитул содержит одну ячейку, которая включает все шесть столбцов в таблице.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения о документах нефиксированного формата](flow-document-overview.md)
- [Определение таблицы с помощью XAML](how-to-define-a-table-with-xaml.md)
- [Документы в WPF](documents-in-wpf.md)
- [Использование элементов потокового содержимого](how-to-use-flow-content-elements.md)
