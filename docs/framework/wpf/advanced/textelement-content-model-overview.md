---
title: Общие сведения о модели содержимого TextElement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], flow documents
- TextElement content model [WPF]
- flow content elements [WPF], TextElement content model
ms.assetid: d0a7791c-b090-438c-812f-b9d009d83ee9
ms.openlocfilehash: acd67dd870c6912eddc368bf674804d98dba2db8
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740759"
---
# <a name="textelement-content-model-overview"></a>Общие сведения о модели содержимого TextElement
В этом обзоре модели содержимого описывается поддерживаемое содержимое для <xref:System.Windows.Documents.TextElement>. Класс <xref:System.Windows.Documents.Paragraph> является типом <xref:System.Windows.Documents.TextElement>. Модель содержимого описывает объекты/элементы, которые могут содержаться в других объектах. В этом обзоре представлена модель содержимого, используемая для объектов, производных от <xref:System.Windows.Documents.TextElement>. Дополнительные сведения см. в разделе [Общие сведения о потоковых документах](flow-document-overview.md).  

<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a>Схема модели содержимого  
 На следующей схеме представлена модель содержимого для классов, производных от <xref:System.Windows.Documents.TextElement>, а также сведения о том, как другие классы, не относящиеся к `TextElement`, помещаются в эту модель.  
  
 ![Схема: схема включения содержимого потока](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 Как видно из предыдущей диаграммы, дочерние элементы, разрешенные для элемента, не обязательно определяются тем, является ли класс производным от класса <xref:System.Windows.Documents.Block> или класса <xref:System.Windows.Documents.Inline>. Например, <xref:System.Windows.Documents.Span> (производный от <xref:System.Windows.Documents.Inline>класс) может иметь только <xref:System.Windows.Documents.Inline> дочерние элементы, но <xref:System.Windows.Documents.Figure> (также производный от <xref:System.Windows.Documents.Inline>класс) может иметь только <xref:System.Windows.Documents.Block> дочерние элементы. Таким образом, схему можно использовать для быстрого определения элемента, который может содержаться в другом элементе. В качестве примера рассмотрим схему, чтобы определить, как создать содержимое нефиксированного формата <xref:System.Windows.Controls.RichTextBox>.  
  
1. <xref:System.Windows.Controls.RichTextBox> должен содержать <xref:System.Windows.Documents.FlowDocument>, который, в свою очередь, должен содержать объект, производный от <xref:System.Windows.Documents.Block>. Ниже приведен соответствующий сегмент из предыдущей диаграммы.  
  
     ![Схема: правила включения элемента RichTextBox](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     Разметка может выглядеть следующим образом.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. В соответствии с схемой можно выбрать несколько <xref:System.Windows.Documents.Block> элементов, включая <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>и <xref:System.Windows.Documents.BlockUIContainer> (см. раздел классы, производные от блока на предыдущей схеме). Предположим, нам нужен <xref:System.Windows.Documents.Table>. В соответствии с предыдущей схемой <xref:System.Windows.Documents.Table> содержит <xref:System.Windows.Documents.TableRowGroup>, содержащий элементы <xref:System.Windows.Documents.TableRow>, которые содержат элементы <xref:System.Windows.Documents.TableCell>, содержащие объект, производный от <xref:System.Windows.Documents.Block>. Ниже приведен соответствующий сегмент для <xref:System.Windows.Documents.Table>, взятых из предыдущей диаграммы.  
  
     ![Схема: схема&#47;родительского дочернего элемента для таблицы](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     Ниже приведена соответствующая разметка.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. Опять же, в <xref:System.Windows.Documents.TableCell>требуется один или несколько элементов <xref:System.Windows.Documents.Block>. Для удобства поместим часть текста в ячейку. Это можно сделать с помощью <xref:System.Windows.Documents.Paragraph> с элементом <xref:System.Windows.Documents.Run>. Ниже приведены соответствующие сегменты из схемы, показывающие, что <xref:System.Windows.Documents.Paragraph> может взять <xref:System.Windows.Documents.Inline> элемент, а <xref:System.Windows.Documents.Run> (элемент <xref:System.Windows.Documents.Inline>) может принимать только обычный текст.  
  
     ![Схема: родительская схема родительского&#47;элемента для абзаца](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![Схема: схема&#47;родительского дочернего элемента для запуска](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Ниже приведен полный пример в виде разметки.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a>Работа с содержимым TextElement с помощью программных средств  
 Содержимое <xref:System.Windows.Documents.TextElement> состоит из коллекций, поэтому программное управление содержимым <xref:System.Windows.Documents.TextElement> объектов выполняется путем работы с этими коллекциями. Существуют три различные коллекции, используемые классами, производными от <xref:System.Windows.Documents.TextElement>:  
  
- <xref:System.Windows.Documents.InlineCollection>: представляет коллекцию элементов <xref:System.Windows.Documents.Inline>. <xref:System.Windows.Documents.InlineCollection> определяет допустимое дочернее содержимое элементов <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span> и <xref:System.Windows.Controls.TextBlock>.  
  
- <xref:System.Windows.Documents.BlockCollection>: представляет коллекцию элементов <xref:System.Windows.Documents.Block>. <xref:System.Windows.Documents.BlockCollection> определяет допустимое дочернее содержимое элементов <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> и <xref:System.Windows.Documents.Figure>.  
  
- <xref:System.Windows.Documents.ListItemCollection>: элемент содержимого нефиксированного формата, представляющий определенный элемент содержимого в упорядоченном или неупорядоченном <xref:System.Windows.Documents.List>.  
  
 Вы можете управлять (добавлять или удалять элементы) из этих коллекций, используя соответствующие свойства **встроенных**элементов, **блоков**и элементов **ListItem**. В следующих примерах показано, как управлять содержимым span с помощью свойства **Inlines** .  
  
> [!NOTE]
> В таблице используется несколько коллекций для управления содержимым, но они не рассматриваются в данном руководстве. Дополнительные сведения см. в разделе [Общие сведения о таблице](table-overview.md).  
  
 В следующем примере создается новый объект <xref:System.Windows.Documents.Span>, а затем используется метод `Add` для добавления двух текстовых запусков в качестве дочерних элементов содержимого <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 В следующем примере создается новый элемент <xref:System.Windows.Documents.Run> и вставляется в начало <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 В следующем примере удаляется последний элемент <xref:System.Windows.Documents.Inline> в <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 В следующем примере из <xref:System.Windows.Documents.Span>удаляется все содержимое (<xref:System.Windows.Documents.Inline> элементы).  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a>Типы, совместно использующие модель содержимого  
 Следующие типы наследуют от класса <xref:System.Windows.Documents.TextElement> и могут использоваться для вывода содержимого, описанного в этом обзоре.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 Обратите внимание, что этот список включает только неабстрактные типы, распространяемые с Windows SDK. Вы можете использовать другие типы, которые наследуются от <xref:System.Windows.Documents.TextElement>.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a>Типы, которые могут содержать объекты TextElement  
 См. раздел [модель содержимого WPF](../controls/wpf-content-model.md).  
  
## <a name="see-also"></a>См. также

- [Управление FlowDocument с помощью свойства Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Управление элементами потокового содержимого с помощью свойства Blocks](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [Управление FlowDocument с помощью свойства Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Управление столбцами таблицы с помощью свойства Columns](how-to-manipulate-table-columns-through-the-columns-property.md)
- [Управление группами строк таблицы пользователя с помощью свойства RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
