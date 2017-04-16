---
title: "Общие сведения о таблицах | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "документы, таблицы"
  - "элементы растягиваемого содержимого [WPF], Таблица"
  - "таблицы"
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Общие сведения о таблицах
<xref:System.Windows.Documents.Table> ― это элемент уровня блока, который поддерживает представление содержимого документа в виде сетки.  Гибкость этого элемента делает его очень полезным, но также делает более сложным для понимания и для правильного использования.  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Основные сведения о таблицах](#table_basics)  
  
-   [Отличие таблицы от сетки](#table_vs_Grid)  
  
-   [Основная структура таблицы](#basic_table_structure)  
  
-   [Вложенность таблицы](#table_containment)  
  
-   [Группировки строк](#row_groupings)  
  
-   [Приоритет отрисовки фона](#rednering_precedence)  
  
-   [Объединение строк или столбцов](#spanning_rows_or_columns)  
  
-   [Создание таблицы с помощью кода](#building_a_table_with_code)  
  
-   [Связанные разделы](#see_also)  
  
<a name="table_basics"></a>   
## Основные сведения о таблицах  
  
<a name="table_vs_Grid"></a>   
### Отличие таблицы от сетки  
 <xref:System.Windows.Documents.Table> и <xref:System.Windows.Controls.Grid> совместно используют некоторые общие функциональные возможности, но каждый наилучшим образом подходит для различных скриптов.  <xref:System.Windows.Documents.Table> предназначена для использования внутри содержимого потока \(см. раздел [Общие сведения о документе нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md) для получения дополнительных сведений о содержимом потока\).  Сетку лучше всего использовать внутри форм \(главным образом, где\-либо вне содержимого потока\).  Внутри <xref:System.Windows.Documents.FlowDocument> элемент <xref:System.Windows.Documents.Table> поддерживает такие возможности, как разбиение на страницы, обратный порядок столбцов и выделение содержимого, в то время как <xref:System.Windows.Controls.Grid> их не поддерживает.  С другой стороны элемент <xref:System.Windows.Controls.Grid> лучше всего использовать вне <xref:System.Windows.Documents.FlowDocument> по многим причинам, включая то, что <xref:System.Windows.Controls.Grid> добавляет элементы на основе индексов строки и столбца, в то время как <xref:System.Windows.Documents.Table> ― нет.  Элемент <xref:System.Windows.Controls.Grid> позволяет послойно размещать дочернее содержимое, что дает возможность разместить в одной "ячейке" несколько элементов. Элемент <xref:System.Windows.Documents.Table> не поддерживает послойное размещение.  Дочерние элементы элемента управления <xref:System.Windows.Controls.Grid> могут быть расположены относительно границы "ячейки" абсолютно.  Элемент <xref:System.Windows.Documents.Table> не поддерживает эту возможность.  Наконец, для элемента <xref:System.Windows.Controls.Grid> требуется меньше ресурсов, чем для <xref:System.Windows.Documents.Table>, поэтому рассмотрите возможность использования <xref:System.Windows.Controls.Grid> для повышения производительности.  
  
<a name="basic_table_structure"></a>   
### Основная структура таблицы  
 <xref:System.Windows.Documents.Table> предоставляет сеточное представление, состоящее из столбцов \(представленных элементами <xref:System.Windows.Documents.TableColumn>\) и строк \(представленных элементами <xref:System.Windows.Documents.TableRow>\).  В элементах <xref:System.Windows.Documents.TableColumn> нет содержимого, они просто определяют столбцы и их характеристики.  Элементы <xref:System.Windows.Documents.TableRow> должны размещаться в элементе <xref:System.Windows.Documents.TableRowGroup>, который определяет группировку строк таблицы.  Элементы <xref:System.Windows.Documents.TableCell>, содержащие фактические данные, отображаемые в таблице, должны быть расположены в элементе <xref:System.Windows.Documents.TableRow>.  <xref:System.Windows.Documents.TableCell> может содержать только элементы, производные от <xref:System.Windows.Documents.Block>.  Допустимые дочерние элементы для <xref:System.Windows.Documents.TableCell>.  
  
-   <xref:System.Windows.Documents.BlockUIContainer>  
  
-   <xref:System.Windows.Documents.List>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
>  Элементы <xref:System.Windows.Documents.TableCell> могут не содержать текстовых данных.  Дополнительные сведения об ограничительных правилах для элементов потока содержимого, таких, как <xref:System.Windows.Documents.TableCell>, см. в разделе [Общие сведения о документе нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Table> подобна элементу <xref:System.Windows.Controls.Grid>, но обладает дополнительными возможностями и, следовательно, требует больше ресурсов.  
  
 В следующем примере задается простая таблица 2 х 3 с помощью [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].  
  
 [!code-xml[TableSnippets2#_Table_BasicLayout](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 На следующем рисунке показан результат выполнения этого примера.  
  
 ![Снимок экрана: отображение простой таблицы](../../../../docs/framework/wpf/advanced/media/basictablerrender.png "BasicTablerRender")  
  
<a name="table_containment"></a>   
### Вложенность таблицы  
 <xref:System.Windows.Documents.Table> является производной от элемента <xref:System.Windows.Documents.Block> и наследует общие правила для элементов уровня <xref:System.Windows.Documents.Block>.  Элемент <xref:System.Windows.Documents.Table> может быть содержимым любого из следующих элементов:  
  
-   <xref:System.Windows.Documents.FlowDocument>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### Группировки строк  
 Элемент <xref:System.Windows.Documents.TableRowGroup> предоставляет способ произвольной группировки строк в таблице; каждая строка в таблице должна принадлежать группе строк.  Строки в группе обычно имеют общее назначение, и для строк в группе может быть применен общий стиль.  Чаще всего группировки строк используются для отделения строк специального назначения, например строк названия, заголовка и нижнего колонтитула, от основного содержимого, находящегося в таблице.  
  
 В следующем примере с помощью [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] задается таблица с типовыми строками заголовка и колонтитула.  
  
 [!code-xml[TableSnippets2#_Table_RowGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 На следующем рисунке показан результат выполнения этого примера.  
  
 ![Снимок экрана: группы строк таблицы](../../../../docs/framework/wpf/advanced/media/table-rowgroups.png "Table\_RowGroups")  
  
<a name="renderning_precedence"></a>   
### Приоритет отрисовки фона  
 Элементы таблицы отображаются в следующем порядке \([в z\-порядке](GTMT) от нижнего к верхнему\).  Этот порядок изменить нельзя.  Например, для этих элементов не существует свойства "Z\-порядок", которое можно было бы использовать для переопределения установленного порядка.  
  
1.  <xref:System.Windows.Documents.Table>  
  
2.  <xref:System.Windows.Documents.TableColumn>  
  
3.  <xref:System.Windows.Documents.TableRowGroup>  
  
4.  <xref:System.Windows.Documents.TableRow>  
  
5.  <xref:System.Windows.Documents.TableCell>  
  
 Рассмотрим следующий пример, в котором задается цвет фона для каждого из этих элементов в пределах таблицы.  
  
 [!code-xml[TableSnippets2#_Table_ZOrder](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 На следующем рисунке показан результат выполнения этого примера \(отображение только цветов фона\).  
  
 ![Снимок экрана: z&#45;порядок таблицы](../../../../docs/framework/wpf/advanced/media/table-zorder.png "Table\_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>   
### Объединение строк или столбцов  
 Можно настроить ячейки таблицы для объединения нескольких строк или столбцов с помощью свойств <xref:System.Windows.Documents.TableCell.RowSpan%2A> или <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> соответственно.  
  
 Рассмотрим следующий пример, в котором ячейка объединяет три столбца.  
  
 [!code-xml[TableSnippets2#_Table_ColumnSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 На следующем рисунке показан результат выполнения этого примера.  
  
 ![Снимок экрана: интервал ячеек в трех столбцах](../../../../docs/framework/wpf/advanced/media/table-columnspan.png "Table\_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>   
## Создание таблицы с помощью кода  
 В следующих примерах показано, как программно создать <xref:System.Windows.Documents.Table> и заполнить ее содержимым.  Содержимое таблицы распределено по пяти строкам \(представленным объектами <xref:System.Windows.Documents.TableRow>, содержащимися в объекте <xref:System.Windows.Documents.Table.RowGroups%2A>\) и шести столбцам \(представленным объектами <xref:System.Windows.Documents.TableColumn>\).  Строки используются для различных целей представления, включая строку названия, предназначенную для заголовка всей таблицы, строку заголовка для описания столбцов данных в таблице, и строку нижнего колонтитула для итоговой информации.  Обратите внимание, что строки "название", "заголовок" и "примечания" не встроены в таблицу, а просто являются строками с разными характеристиками.  Ячейки таблицы содержат фактическое содержимое, которое может состоять из текста, изображений или практически любых других элементов [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
 Вначале создается <xref:System.Windows.Documents.FlowDocument> для размещения <xref:System.Windows.Documents.Table>, а также новая таблица <xref:System.Windows.Documents.Table>, в которую добавляется содержимое из <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 Далее с применением некоторого форматирования создаются шесть объектов <xref:System.Windows.Documents.TableColumn>, которые добавляются в коллекцию таблицы <xref:System.Windows.Documents.Table.Columns%2A>.  
  
> [!NOTE]
>  Обратите внимание, что коллекция таблицы <xref:System.Windows.Documents.Table.Columns%2A> использует стандартное индексирование начиная с нуля.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 Далее создается строка названия и добавляется к таблице с применением некоторого форматирования.  Строка названия будет содержать одну ячейку, объединяющую все шесть столбцов таблицы.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 Далее создается и добавляется в таблицу строка заголовка, а ее ячейки создаются и заполняются содержимым.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 Далее создается и добавляется в таблицу строка для данных, ячейки этой строки также создаются и заполняются содержимым.  Построение этой строки аналогично построению строки заголовка за исключением слегка отличающегося форматирования.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 После этого создается, добавляется и форматируется строка нижнего колонтитула.  Как и строка названия, нижний колонтитул содержит одну ячейку, объединяющую все шесть столбцов таблицы.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## См. также  
 [Общие сведения о документе нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md)   
 [Определение таблицы с помощью XAML](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)   
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Использование элементов нефиксированного формата](../../../../docs/framework/wpf/advanced/how-to-use-flow-content-elements.md)