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
ms.openlocfilehash: 21df7228f8dca884c5f36be23ae1aced7b31cc9a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942220"
---
# <a name="textelement-content-model-overview"></a>Общие сведения о модели содержимого TextElement
В этом обзоре модели содержимого описывается поддерживаемое содержимое для <xref:System.Windows.Documents.TextElement>. <xref:System.Windows.Documents.Paragraph> Класс является <xref:System.Windows.Documents.TextElement>типом. Модель содержимого описывает объекты/элементы, которые могут содержаться в других объектах. В этом обзоре представлена модель содержимого, используемая для объектов <xref:System.Windows.Documents.TextElement>, производных от. Дополнительные сведения см. в разделе [Общие сведения о потоковых документах](flow-document-overview.md).  

<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a>Схема модели содержимого  
 На следующей диаграмме представлена модель содержимого для классов, производных <xref:System.Windows.Documents.TextElement> от, а также объясняется, `TextElement` как другие классы, не являющиеся классами, помещаются в эту модель.  
  
 ![Схема: Схема]вложения содержимого Flow(./media/flow-content-schema.png "Flow_Content_Schema")  
  
 Как видно из предыдущей диаграммы, дочерние элементы, разрешенные для элемента, не обязательно определяются, является ли класс производным от <xref:System.Windows.Documents.Block> класса <xref:System.Windows.Documents.Inline> или класса. Например, <xref:System.Windows.Documents.Span> класс <xref:System.Windows.Documents.Inline> <xref:System.Windows.Documents.Inline> <xref:System.Windows.Documents.Inline>(производный от класса) может иметь только дочерние элементы, но <xref:System.Windows.Documents.Figure> (также производный класс) может иметь <xref:System.Windows.Documents.Block> только дочерние элементы. Таким образом, схему можно использовать для быстрого определения элемента, который может содержаться в другом элементе. В качестве примера рассмотрим схему, чтобы определить, как создать содержимое <xref:System.Windows.Controls.RichTextBox>нефиксированного формата.  
  
1. Объект должен содержать, который, в свою очередь, <xref:System.Windows.Documents.Block>должен содержать объект, производный от. <xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.Controls.RichTextBox> Ниже приведен соответствующий сегмент из предыдущей диаграммы.  
  
     ![Схема: Правила]включения RichTextBox(./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     Разметка может выглядеть следующим образом.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. В соответствии с диаграммой существует несколько <xref:System.Windows.Documents.Block> элементов, которые можно выбрать, включая <xref:System.Windows.Documents.Section> <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, и <xref:System.Windows.Documents.BlockUIContainer> (см. раздел классы, производные от блока на предыдущей схеме). Предположим, <xref:System.Windows.Documents.Table>нам нужно. В соответствии с предыдущей <xref:System.Windows.Documents.Table> схемой <xref:System.Windows.Documents.TableRowGroup> содержит <xref:System.Windows.Documents.TableRow> элементы,<xref:System.Windows.Documents.TableCell> содержащие элементы, которые содержатобъект,производныйот.<xref:System.Windows.Documents.Block> Ниже приведен соответствующий сегмент <xref:System.Windows.Documents.Table> , взятый из предыдущей диаграммы.  
  
     ![Схема: Схема&#47;родительского дочернего]элемента для таблицы(./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     Ниже приведена соответствующая разметка.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. Опять же, один или <xref:System.Windows.Documents.Block> несколько элементов должны находиться <xref:System.Windows.Documents.TableCell>под. Для удобства поместим часть текста в ячейку. Это можно сделать с помощью <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Documents.Run> элемента. Ниже приводятся соответствующие сегменты из схемы, показывающие, <xref:System.Windows.Documents.Paragraph> что может <xref:System.Windows.Documents.Inline> принимать элемент <xref:System.Windows.Documents.Inline> и что <xref:System.Windows.Documents.Run> (элемент) может принимать только обычный текст.  
  
     ![Схема: Схема&#47;родительского дочернего]элемента для(./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3") абзаца  
  
     ![Схема: Схема&#47;родительского дочернего]элемента для запуска(./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Ниже приведен полный пример в виде разметки.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a>Работа с содержимым TextElement с помощью программных средств  
 Содержимое <xref:System.Windows.Documents.TextElement> объекта создается коллекциями, поэтому программное управление <xref:System.Windows.Documents.TextElement> содержимым объектов осуществляется путем работы с этими коллекциями. Существуют три различные коллекции, <xref:System.Windows.Documents.TextElement> используемые производными классами:  
  
- <xref:System.Windows.Documents.InlineCollection>: Представляет коллекцию элементов <xref:System.Windows.Documents.Inline>. <xref:System.Windows.Documents.InlineCollection> определяет допустимое дочернее содержимое элементов <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span> и <xref:System.Windows.Controls.TextBlock>.  
  
- <xref:System.Windows.Documents.BlockCollection>: Представляет коллекцию элементов <xref:System.Windows.Documents.Block>. <xref:System.Windows.Documents.BlockCollection> определяет допустимое дочернее содержимое элементов <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> и <xref:System.Windows.Documents.Figure>.  
  
- <xref:System.Windows.Documents.ListItemCollection>: Элемент растягиваемого содержимого, представляющий определенный элемент содержимого в упорядоченном или неупорядоченном <xref:System.Windows.Documents.List>виде.  
  
 Вы можете управлять (добавлять или удалять элементы) из этих коллекций, используя соответствующие свойства **встроенных**элементов, **блоков**и элементов **ListItem**. В следующих примерах показано, как управлять содержимым span с помощью свойства **Inlines** .  
  
> [!NOTE]
> В таблице используется несколько коллекций для управления содержимым, но они не рассматриваются в данном руководстве. Дополнительные сведения см. в разделе [Общие сведения о таблице](table-overview.md).  
  
 В следующем примере создается новый <xref:System.Windows.Documents.Span> объект, а затем `Add` используется метод для добавления двух текстовых запусков в <xref:System.Windows.Documents.Span>качестве дочерних элементов содержимого объекта.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 В следующем примере создается новый <xref:System.Windows.Documents.Run> элемент и вставляется в начало. <xref:System.Windows.Documents.Span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 В следующем примере удаляется последний <xref:System.Windows.Documents.Inline> элемент <xref:System.Windows.Documents.Span>в.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 В следующем примере удаляется все содержимое (<xref:System.Windows.Documents.Inline> элементы) <xref:System.Windows.Documents.Span>из.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a>Типы, совместно использующие модель содержимого  
 Следующие типы наследуют от <xref:System.Windows.Documents.TextElement> класса и могут использоваться для вывода содержимого, описанного в этом обзоре.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 Обратите внимание, что этот список включает только неабстрактные [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]типы, распространяемые с. Вы можете использовать другие типы, наследуемые от <xref:System.Windows.Documents.TextElement>.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a>Типы, которые могут содержать объекты TextElement  
 См. раздел [модель содержимого WPF](../controls/wpf-content-model.md).  
  
## <a name="see-also"></a>См. также

- [Управление FlowDocument с помощью свойства Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Управление элементами потокового содержимого с помощью свойства Blocks](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [Управление FlowDocument с помощью свойства Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Управление столбцами таблицы с помощью свойства Columns](how-to-manipulate-table-columns-through-the-columns-property.md)
- [Управление группами строк таблицы пользователя с помощью свойства RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
