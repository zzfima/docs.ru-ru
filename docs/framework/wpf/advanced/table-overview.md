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
# <a name="table-overview"></a><span data-ttu-id="89945-102">Общие сведения о таблицах</span><span class="sxs-lookup"><span data-stu-id="89945-102">Table Overview</span></span>
<span data-ttu-id="89945-103"><xref:System.Windows.Documents.Table> — это элемент уровня блока, поддерживающий представление содержимого нефиксированного документа на основе сетки.</span><span class="sxs-lookup"><span data-stu-id="89945-103"><xref:System.Windows.Documents.Table> is a block level element that supports grid-based presentation of Flow document content.</span></span> <span data-ttu-id="89945-104">Гибкость этого элемента делает его очень полезным, но также и более сложным для понимания и правильного использования.</span><span class="sxs-lookup"><span data-stu-id="89945-104">The flexibility of this element makes it very useful, but also makes it more complicated to understand and use correctly.</span></span>  
  
 <span data-ttu-id="89945-105">В этом разделе содержатся следующие подразделы:</span><span class="sxs-lookup"><span data-stu-id="89945-105">This topic contains the following sections.</span></span>  
  
- [<span data-ttu-id="89945-106">Основные сведения о таблицах</span><span class="sxs-lookup"><span data-stu-id="89945-106">Table Basics</span></span>](#table_basics)  
  
- [<span data-ttu-id="89945-107">Отличие таблицы от сетки</span><span class="sxs-lookup"><span data-stu-id="89945-107">How is Table Different then Grid?</span></span>](#table_vs_Grid)  
  
- [<span data-ttu-id="89945-108">Основная структура таблицы</span><span class="sxs-lookup"><span data-stu-id="89945-108">Basic Table Structure</span></span>](#basic_table_structure)  
  
- [<span data-ttu-id="89945-109">Вложения таблицы</span><span class="sxs-lookup"><span data-stu-id="89945-109">Table Containment</span></span>](#table_containment)  
  
- [<span data-ttu-id="89945-110">Группирование строк</span><span class="sxs-lookup"><span data-stu-id="89945-110">Row Groupings</span></span>](#row_groupings)  
  
- [<span data-ttu-id="89945-111">Приоритет отрисовки фона</span><span class="sxs-lookup"><span data-stu-id="89945-111">Background Rendering Precedence</span></span>](#rendering_precedence)  
  
- [<span data-ttu-id="89945-112">Объединение строк или столбцов</span><span class="sxs-lookup"><span data-stu-id="89945-112">Spanning Rows or Columns</span></span>](#spanning_rows_or_columns)  
  
- [<span data-ttu-id="89945-113">Создание таблицы с помощью кода</span><span class="sxs-lookup"><span data-stu-id="89945-113">Building a Table With Code</span></span>](#building_a_table_with_code)  
  
- <span data-ttu-id="89945-114">[Связанные разделы]</span><span class="sxs-lookup"><span data-stu-id="89945-114">[Related Topics]</span></span> 
  
<a name="table_basics"></a>   
## <a name="table-basics"></a><span data-ttu-id="89945-115">Основы таблиц</span><span class="sxs-lookup"><span data-stu-id="89945-115">Table Basics</span></span>  
  
<a name="table_vs_Grid"></a>   
### <a name="how-is-table-different-then-grid"></a><span data-ttu-id="89945-116">Отличие таблицы от сетки</span><span class="sxs-lookup"><span data-stu-id="89945-116">How is Table Different then Grid?</span></span>  
 <span data-ttu-id="89945-117"><xref:System.Windows.Documents.Table> и <xref:System.Windows.Controls.Grid> обладают некоторыми общими функциями, но они лучше всего подходят для различных сценариев.</span><span class="sxs-lookup"><span data-stu-id="89945-117"><xref:System.Windows.Documents.Table> and <xref:System.Windows.Controls.Grid> share some common functionality, but each is best suited for different scenarios.</span></span> <span data-ttu-id="89945-118"><xref:System.Windows.Documents.Table> предназначен для использования в содержимом нефиксированного формата (Дополнительные сведения о содержимом нефиксированного формата см. в разделе [Общие сведения о документе](flow-document-overview.md) ).</span><span class="sxs-lookup"><span data-stu-id="89945-118">A <xref:System.Windows.Documents.Table> is designed for use within flow content (see [Flow Document Overview](flow-document-overview.md) for more information on flow content).</span></span> <span data-ttu-id="89945-119">Сетки лучше всего использовать внутри форм (по сути в любом месте вне потокового содержимого).</span><span class="sxs-lookup"><span data-stu-id="89945-119">Grids are best used inside of forms (basically anywhere outside of flow content).</span></span> <span data-ttu-id="89945-120">В <xref:System.Windows.Documents.FlowDocument><xref:System.Windows.Documents.Table> поддерживает поведение нефиксированного содержимого, например разбивку на страницы, перекомпоновку столбцов и выбор содержимого, когда в <xref:System.Windows.Controls.Grid> нет.</span><span class="sxs-lookup"><span data-stu-id="89945-120">Within a <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> supports flow content behaviors like pagination, column reflow, and content selection while a <xref:System.Windows.Controls.Grid> does not.</span></span> <span data-ttu-id="89945-121"><xref:System.Windows.Controls.Grid> с другой стороны лучше использовать за пределами <xref:System.Windows.Documents.FlowDocument> по многим причинам, включая <xref:System.Windows.Controls.Grid> добавляет элементы на основе индекса строки и столбца, <xref:System.Windows.Documents.Table> — нет.</span><span class="sxs-lookup"><span data-stu-id="89945-121">A <xref:System.Windows.Controls.Grid> on the other hand is best used outside of a <xref:System.Windows.Documents.FlowDocument> for many reasons including <xref:System.Windows.Controls.Grid> adds elements based on a row and column index, <xref:System.Windows.Documents.Table> does not.</span></span> <span data-ttu-id="89945-122">Элемент <xref:System.Windows.Controls.Grid> позволяет разложить разслойировать дочернее содержимое, разрешив существование в одной "ячейке" более одного элемента.</span><span class="sxs-lookup"><span data-stu-id="89945-122">The <xref:System.Windows.Controls.Grid> element allows layering of child content, allowing more than one element to exist within a single "cell."</span></span> <span data-ttu-id="89945-123"><xref:System.Windows.Documents.Table> не поддерживает многоуровневые слои.</span><span class="sxs-lookup"><span data-stu-id="89945-123"><xref:System.Windows.Documents.Table> does not support layering.</span></span> <span data-ttu-id="89945-124">Дочерние элементы <xref:System.Windows.Controls.Grid> могут быть абсолютно расположены относительно области их границ "ячейка".</span><span class="sxs-lookup"><span data-stu-id="89945-124">Child elements of a <xref:System.Windows.Controls.Grid> can be absolutely positioned relative to the area of their "cell" boundaries.</span></span> <span data-ttu-id="89945-125"><xref:System.Windows.Documents.Table> не поддерживает эту функцию.</span><span class="sxs-lookup"><span data-stu-id="89945-125"><xref:System.Windows.Documents.Table> does not support this feature.</span></span> <span data-ttu-id="89945-126">Наконец, <xref:System.Windows.Controls.Grid> требует меньше ресурсов, а <xref:System.Windows.Documents.Table> поэтому рекомендуется использовать <xref:System.Windows.Controls.Grid> для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="89945-126">Finally, a <xref:System.Windows.Controls.Grid> requires less resources then a <xref:System.Windows.Documents.Table> so consider using a <xref:System.Windows.Controls.Grid> to improve performance.</span></span>  
  
<a name="basic_table_structure"></a>   
### <a name="basic-table-structure"></a><span data-ttu-id="89945-127">Основная структура таблицы</span><span class="sxs-lookup"><span data-stu-id="89945-127">Basic Table Structure</span></span>  
 <span data-ttu-id="89945-128"><xref:System.Windows.Documents.Table> предоставляет представление на основе сетки, состоящее из столбцов (представленных <xref:System.Windows.Documents.TableColumn> элементами) и строк (представленных элементами <xref:System.Windows.Documents.TableRow>).</span><span class="sxs-lookup"><span data-stu-id="89945-128"><xref:System.Windows.Documents.Table> provides a grid-based presentation consisting of columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and rows (represented by <xref:System.Windows.Documents.TableRow> elements).</span></span> <span data-ttu-id="89945-129">элементы <xref:System.Windows.Documents.TableColumn> не размещают содержимое; они просто определяют столбцы и характеристики столбцов.</span><span class="sxs-lookup"><span data-stu-id="89945-129"><xref:System.Windows.Documents.TableColumn> elements do not host content; they simply define columns and characteristics of columns.</span></span> <span data-ttu-id="89945-130"><xref:System.Windows.Documents.TableRow> элементы должны размещаться в элементе <xref:System.Windows.Documents.TableRowGroup>, который определяет группирование строк для таблицы.</span><span class="sxs-lookup"><span data-stu-id="89945-130"><xref:System.Windows.Documents.TableRow> elements must be hosted in a <xref:System.Windows.Documents.TableRowGroup> element, which defines a grouping of rows for the table.</span></span> <span data-ttu-id="89945-131"><xref:System.Windows.Documents.TableCell> элементы, которые содержат реальное содержимое, которое должно быть представлено таблицей, должны размещаться в элементе <xref:System.Windows.Documents.TableRow>.</span><span class="sxs-lookup"><span data-stu-id="89945-131"><xref:System.Windows.Documents.TableCell> elements, which contain the actual content to be presented by the table, must be hosted in a <xref:System.Windows.Documents.TableRow> element.</span></span> <span data-ttu-id="89945-132"><xref:System.Windows.Documents.TableCell> могут содержать только элементы, производные от <xref:System.Windows.Documents.Block>.</span><span class="sxs-lookup"><span data-stu-id="89945-132"><xref:System.Windows.Documents.TableCell> may only contain elements that derive from <xref:System.Windows.Documents.Block>.</span></span>  <span data-ttu-id="89945-133">Допустимые дочерние элементы для <xref:System.Windows.Documents.TableCell> включают.</span><span class="sxs-lookup"><span data-stu-id="89945-133">Valid child elements for a <xref:System.Windows.Documents.TableCell> include.</span></span>  
  
- <xref:System.Windows.Documents.BlockUIContainer>  
  
- <xref:System.Windows.Documents.List>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
> <span data-ttu-id="89945-134">элементы <xref:System.Windows.Documents.TableCell> могут не размещать текстовое содержимое напрямую.</span><span class="sxs-lookup"><span data-stu-id="89945-134"><xref:System.Windows.Documents.TableCell> elements may not directly host text content.</span></span> <span data-ttu-id="89945-135">Дополнительные сведения о правилах включения для элементов содержимого нефиксированного формата, таких как <xref:System.Windows.Documents.TableCell>, см. в разделе [Общие сведения о потоковых документах](flow-document-overview.md).</span><span class="sxs-lookup"><span data-stu-id="89945-135">For more information about the containment rules for flow content elements like <xref:System.Windows.Documents.TableCell>, see [Flow Document Overview](flow-document-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="89945-136"><xref:System.Windows.Documents.Table> похож на элемент <xref:System.Windows.Controls.Grid>, но имеет больше возможностей и, следовательно, требует большего объема ресурсов.</span><span class="sxs-lookup"><span data-stu-id="89945-136"><xref:System.Windows.Documents.Table> is similar to the <xref:System.Windows.Controls.Grid> element but has more capabilities and, therefore, requires greater resource overhead.</span></span>  
  
 <span data-ttu-id="89945-137">В следующем примере определяется простая таблица 2 x 3 с XAML.</span><span class="sxs-lookup"><span data-stu-id="89945-137">The following example defines a simple 2 x 3 table with XAML.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 <span data-ttu-id="89945-138">На следующем рисунке показана отрисовка этого примера.</span><span class="sxs-lookup"><span data-stu-id="89945-138">The following figure shows how this example renders.</span></span>  
  
 ![Снимок экрана, показывающий, как отображается базовая таблица.](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>   
### <a name="table-containment"></a><span data-ttu-id="89945-140">Вложения таблицы</span><span class="sxs-lookup"><span data-stu-id="89945-140">Table Containment</span></span>  
 <span data-ttu-id="89945-141"><xref:System.Windows.Documents.Table> является производным от элемента <xref:System.Windows.Documents.Block> и соответствует общим правилам для элементов <xref:System.Windows.Documents.Block> уровня.</span><span class="sxs-lookup"><span data-stu-id="89945-141"><xref:System.Windows.Documents.Table> derives from the <xref:System.Windows.Documents.Block> element, and adheres to the common rules for <xref:System.Windows.Documents.Block> level elements.</span></span>  <span data-ttu-id="89945-142">Элемент <xref:System.Windows.Documents.Table> может содержаться в одном из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="89945-142">A <xref:System.Windows.Documents.Table> element may be contained by any of the following elements:</span></span>  
  
- <xref:System.Windows.Documents.FlowDocument>  
  
- <xref:System.Windows.Documents.TableCell>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### <a name="row-groupings"></a><span data-ttu-id="89945-143">Группирование строк</span><span class="sxs-lookup"><span data-stu-id="89945-143">Row Groupings</span></span>  
 <span data-ttu-id="89945-144">Элемент <xref:System.Windows.Documents.TableRowGroup> предоставляет возможность произвольного группирования строк в таблице; Каждая строка в таблице должна принадлежать к группированию строк.</span><span class="sxs-lookup"><span data-stu-id="89945-144">The <xref:System.Windows.Documents.TableRowGroup> element provides a way to arbitrarily group rows within a table; every row in a table must belong to a row grouping.</span></span>  <span data-ttu-id="89945-145">Строки в группе часто имеют общее назначение и могут быть стилизованы в виде группы.</span><span class="sxs-lookup"><span data-stu-id="89945-145">Rows within a row group often share a common intent, and may be styled as a group.</span></span>  <span data-ttu-id="89945-146">Обычно группирование строк используется для отделения строк специального назначения, например строк названия, заголовка и нижнего колонтитула, от основного содержимого, находящегося в таблице.</span><span class="sxs-lookup"><span data-stu-id="89945-146">A common use for row groupings is to separate special-purpose rows, such as a title, header, and footer rows, from the primary content contained by the table.</span></span>  
  
 <span data-ttu-id="89945-147">В следующем примере XAML используется для определения таблицы со строками верхнего и нижнего колонтитулов.</span><span class="sxs-lookup"><span data-stu-id="89945-147">The following example uses XAML to define a table with styled header and footer rows.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 <span data-ttu-id="89945-148">На следующем рисунке показана отрисовка этого примера.</span><span class="sxs-lookup"><span data-stu-id="89945-148">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="89945-149">![Снимок экрана: группы строк таблицы](./media/table-rowgroups.png "Table_RowGroups")</span><span class="sxs-lookup"><span data-stu-id="89945-149">![Screenshot: Table row groups](./media/table-rowgroups.png "Table_RowGroups")</span></span>  
  
<a name="rendering_precedence"></a>   
### <a name="background-rendering-precedence"></a><span data-ttu-id="89945-150">Приоритет отрисовки фона</span><span class="sxs-lookup"><span data-stu-id="89945-150">Background Rendering Precedence</span></span>  
 <span data-ttu-id="89945-151">Элементы таблицы отрисовываются в следующем порядке (z-порядок от нижнего к верхнему).</span><span class="sxs-lookup"><span data-stu-id="89945-151">Table elements render in the following order (z-order from lowest to highest).</span></span> <span data-ttu-id="89945-152">Этот порядок нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="89945-152">This order cannot be changed.</span></span> <span data-ttu-id="89945-153">Например, для этих элементов не существует свойства "Z-порядок", которое можно использовать для переопределения этого установленного порядка.</span><span class="sxs-lookup"><span data-stu-id="89945-153">For example, there is no "Z-order" property for these elements that you can use to override this established order.</span></span>  
  
1. <xref:System.Windows.Documents.Table>  
  
2. <xref:System.Windows.Documents.TableColumn>  
  
3. <xref:System.Windows.Documents.TableRowGroup>  
  
4. <xref:System.Windows.Documents.TableRow>  
  
5. <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="89945-154">Рассмотрим следующий пример, в котором задается цвет фона для каждого из этих элементов в таблице.</span><span class="sxs-lookup"><span data-stu-id="89945-154">Consider the following example, which defines background colors for each of these elements within a table.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 <span data-ttu-id="89945-155">На следующем рисунке показана отрисовка этого примера (показаны только фоновые цвета).</span><span class="sxs-lookup"><span data-stu-id="89945-155">The following figure shows how this example renders (showing background colors only).</span></span>  
  
 <span data-ttu-id="89945-156">![Снимок экрана: Z-порядок таблицы](./media/table-zorder.png "Table_ZOrder")</span><span class="sxs-lookup"><span data-stu-id="89945-156">![Screenshot: Table z&#45;order](./media/table-zorder.png "Table_ZOrder")</span></span>  
  
<a name="spanning_rows_or_columns"></a>   
### <a name="spanning-rows-or-columns"></a><span data-ttu-id="89945-157">Объединение строк или столбцов</span><span class="sxs-lookup"><span data-stu-id="89945-157">Spanning Rows or Columns</span></span>  
 <span data-ttu-id="89945-158">Ячейки таблицы могут быть настроены на охват нескольких строк или столбцов с помощью <xref:System.Windows.Documents.TableCell.RowSpan%2A> или <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> атрибутов соответственно.</span><span class="sxs-lookup"><span data-stu-id="89945-158">Table cells may be configured to span multiple rows or columns by using the <xref:System.Windows.Documents.TableCell.RowSpan%2A> or <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> attributes, respectively.</span></span>  
  
 <span data-ttu-id="89945-159">Рассмотрим следующий пример, в котором ячейка включает три столбца.</span><span class="sxs-lookup"><span data-stu-id="89945-159">Consider the following example, in which a cell spans three columns.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 <span data-ttu-id="89945-160">На следующем рисунке показана отрисовка этого примера.</span><span class="sxs-lookup"><span data-stu-id="89945-160">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="89945-161">![Снимок экрана: ячейка, охватывающая три столбца](./media/table-columnspan.png "Table_ColumnSpan")</span><span class="sxs-lookup"><span data-stu-id="89945-161">![Screenshot: Cell spanning all three columns](./media/table-columnspan.png "Table_ColumnSpan")</span></span>  
  
<a name="building_a_table_with_code"></a>   
## <a name="building-a-table-with-code"></a><span data-ttu-id="89945-162">Построение таблицы с помощью кода</span><span class="sxs-lookup"><span data-stu-id="89945-162">Building a Table With Code</span></span>  
 <span data-ttu-id="89945-163">В следующих примерах показано, как программным способом создать <xref:System.Windows.Documents.Table> и заполнить его содержимым.</span><span class="sxs-lookup"><span data-stu-id="89945-163">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="89945-164">Содержимое таблицы делится на пять строк (представленные <xref:System.Windows.Documents.TableRow> объектами, содержащимися в <xref:System.Windows.Documents.Table.RowGroups%2A> объекте) и шесть столбцов (представленных <xref:System.Windows.Documents.TableColumn>ными объектами).</span><span class="sxs-lookup"><span data-stu-id="89945-164">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="89945-165">Строки используются для различных целей представления, включая строку названия, предназначенную для заголовка всей таблицы, строку заголовка для описания столбцов данных в таблице, и строку нижнего колонтитула для сводных данных.</span><span class="sxs-lookup"><span data-stu-id="89945-165">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="89945-166">Обратите внимание, что понятия "название", "заголовок" и "нижний колонтитул" строк, не встроены в таблицу. Это просто строки с разными характеристиками.</span><span class="sxs-lookup"><span data-stu-id="89945-166">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="89945-167">Ячейки таблицы содержат фактическое содержимое, которое может состоять из текста, изображений или практически любого другого элемента [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89945-167">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
 <span data-ttu-id="89945-168">Сначала создается <xref:System.Windows.Documents.FlowDocument> для размещения <xref:System.Windows.Documents.Table>, а также создается новая <xref:System.Windows.Documents.Table> и добавляется к содержимому <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="89945-168">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 <span data-ttu-id="89945-169">Затем создаются шесть <xref:System.Windows.Documents.TableColumn>ных объектов и добавляются в коллекцию <xref:System.Windows.Documents.Table.Columns%2A> таблицы с применением определенного форматирования.</span><span class="sxs-lookup"><span data-stu-id="89945-169">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="89945-170">Обратите внимание, что коллекция <xref:System.Windows.Documents.Table.Columns%2A> таблицы использует нулевое индексирование, начинающееся с нуля.</span><span class="sxs-lookup"><span data-stu-id="89945-170">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 <span data-ttu-id="89945-171">Затем создается строка заголовка и добавляется в таблицу с определенным форматированием.</span><span class="sxs-lookup"><span data-stu-id="89945-171">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="89945-172">Строка названия содержит одну ячейку, охватывающую все шесть столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="89945-172">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 <span data-ttu-id="89945-173">Далее создается и добавляется в таблицу строка заголовка, а ячейки в строке заголовка создаются и заполняются содержимым.</span><span class="sxs-lookup"><span data-stu-id="89945-173">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 <span data-ttu-id="89945-174">Затем создается и добавляется в таблицу ряд данных, а ячейки в этой строке создаются и заполняются содержимым.</span><span class="sxs-lookup"><span data-stu-id="89945-174">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="89945-175">Построение этой строки аналогично построению строки заголовка с применением немного другого форматирования.</span><span class="sxs-lookup"><span data-stu-id="89945-175">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 <span data-ttu-id="89945-176">Наконец, создается, добавляется и форматируется строка нижнего колонтитула.</span><span class="sxs-lookup"><span data-stu-id="89945-176">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="89945-177">Как и строка названия, нижний колонтитул содержит одну ячейку, которая включает все шесть столбцов в таблице.</span><span class="sxs-lookup"><span data-stu-id="89945-177">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="89945-178">См. также:</span><span class="sxs-lookup"><span data-stu-id="89945-178">See also</span></span>

- [<span data-ttu-id="89945-179">Общие сведения о документах нефиксированного формата</span><span class="sxs-lookup"><span data-stu-id="89945-179">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="89945-180">Определение таблицы с помощью XAML</span><span class="sxs-lookup"><span data-stu-id="89945-180">Define a Table with XAML</span></span>](how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="89945-181">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="89945-181">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="89945-182">Использование элементов потокового содержимого</span><span class="sxs-lookup"><span data-stu-id="89945-182">Use Flow Content Elements</span></span>](how-to-use-flow-content-elements.md)
