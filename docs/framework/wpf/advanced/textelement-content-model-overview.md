---
title: "Общие сведения о модели содержимого TextElement | Microsoft Docs"
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
  - "документы, документы нефиксированного формата"
  - "элементы растягиваемого содержимого [WPF], TextElement - модель содержимого"
  - "документы нефиксированного формата"
  - "TextElement - модель содержимого"
ms.assetid: d0a7791c-b090-438c-812f-b9d009d83ee9
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Общие сведения о модели содержимого TextElement
Данный раздел содержит основные сведения о поддерживаемом содержимом для модели <xref:System.Windows.Documents.TextElement>.  Класс <xref:System.Windows.Documents.Paragraph> является типом <xref:System.Windows.Documents.TextElement>.  Модель содержимого описывает объекты\/элементы, которые могут содержаться в других объектах.  В разделе содержится обобщение модели содержимого для объектов, являющихся производными от <xref:System.Windows.Documents.TextElement>.  Дополнительные сведения см. в разделе [Общие сведения о документе нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
   
  
<a name="text_element_classes"></a>   
## Диаграмма модели содержимого  
 На следующей диаграмме представлена модель содержимого для классов, производных от <xref:System.Windows.Documents.TextElement>, и других классов, отличных от `TextElement`, соответствующих этой модели.  
  
 ![Схема: схема вместимости потока содержимого](../../../../docs/framework/wpf/advanced/media/flow-content-schema.png "Flow\_Content\_Schema")  
  
 Как видно из предыдущей диаграммы, дочерние элементы не обязательно определяются тем, является ли класс производным от класса <xref:System.Windows.Documents.Block> или <xref:System.Windows.Documents.Inline>.  Например, класс <xref:System.Windows.Documents.Span> \(производный от <xref:System.Windows.Documents.Inline>\) может иметь только дочерние элементы <xref:System.Windows.Documents.Inline>, но класс <xref:System.Windows.Documents.Figure> \(также производный от <xref:System.Windows.Documents.Inline>\) может иметь только дочерние элементы <xref:System.Windows.Documents.Block>.  Таким образом, диаграмма может служить для быстрого определения элемента, который может содержаться в другом элементе.  Для примера используем диаграмму, чтобы определить, как создать содержимое нефиксированного формата <xref:System.Windows.Controls.RichTextBox>.  
  
1.  Объект <xref:System.Windows.Controls.RichTextBox> должен содержать <xref:System.Windows.Documents.FlowDocument>, который в свою очередь должен содержать объект, производный от <xref:System.Windows.Documents.Block>.  Ниже приводится соответствующий сегмент из предыдущей диаграммы.  
  
     ![Схема: правила вместимости RichTextBox](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough1.png "Flow\_Ovw\_SchemaWalkThrough1")  
  
     Разметка может выглядеть следующим образом:  
  
     [!code-xml[FlowOvwSnippets_snip#SchemaWalkThrough1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2.  В соответствии с диаграммой существует несколько элементов класса <xref:System.Windows.Documents.Block> для выбора, в том числе: <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List> и <xref:System.Windows.Documents.BlockUIContainer> \(см. классы, производные от Block, в предыдущей диаграмме\).  Предположим, нам требуется <xref:System.Windows.Documents.Table>.  В соответствии с предыдущей диаграммой класс <xref:System.Windows.Documents.Table> содержит <xref:System.Windows.Documents.TableRowGroup>, содержащий элементы <xref:System.Windows.Documents.TableRow>, которые содержат элементы <xref:System.Windows.Documents.TableCell>, содержащие объект, производный от класса <xref:System.Windows.Documents.Block>.  Ниже приводится соответствующий сегмент для класса <xref:System.Windows.Documents.Table>, взятый из предыдущей диаграммы.  
  
     ![Схема: схема родительский&#47;дочерний элементы для таблицы](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough2.png "Flow\_Ovw\_SchemaWalkThrough2")  
  
     Ниже приводится соответствующая разметка.  
  
     [!code-xml[FlowOvwSnippets_snip#SchemaWalkThrough2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3.  Предположим, что для <xref:System.Windows.Documents.TableCell> снова требуется один или несколько элементов <xref:System.Windows.Documents.Block>.   Для удобства поместим часть текста в ячейку.  Это можно сделать, используя <xref:System.Windows.Documents.Paragraph> с элементом <xref:System.Windows.Documents.Run>.  Ниже приводится соответствующий сегмент из диаграммы, показывающий, что <xref:System.Windows.Documents.Paragraph> может принять элемент <xref:System.Windows.Documents.Inline> и что <xref:System.Windows.Documents.Run> \(элемент <xref:System.Windows.Documents.Inline>\) может принять только обычный текст.  
  
     ![Схема: схема родительский&#47;дочерний элементы для параграфа](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough3.png "Flow\_Ovw\_SchemaWalkThrough3")  
  
     ![Схема: схема родительский&#47;дочерний элементы для запуска](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough4.png "Flow\_Ovw\_SchemaWalkThrough4")  
  
 Ниже приведен полный пример в виде разметки.  
  
 [!code-xml[FlowOvwSnippets_snip#SchemaExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## Работа с содержимым TextElement программными средствами  
 Содержимое <xref:System.Windows.Documents.TextElement> строится с помощью коллекций и поэтому программное управление содержимым объектов <xref:System.Windows.Documents.TextElement> выполняется с использованием этих коллекций.  Существуют три различные коллекции, используемые классами, производными от <xref:System.Windows.Documents.TextElement>:  
  
-   <xref:System.Windows.Documents.InlineCollection>. Представляет коллекцию элементов <xref:System.Windows.Documents.Inline>.  <xref:System.Windows.Documents.InlineCollection> определяет допустимое дочернее содержимое элементов <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span> и <xref:System.Windows.Controls.TextBlock>.  
  
-   <xref:System.Windows.Documents.BlockCollection>. Представляет коллекцию элементов <xref:System.Windows.Documents.Block>.  <xref:System.Windows.Documents.BlockCollection> определяет допустимое дочернее содержимое элементов <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> и <xref:System.Windows.Documents.Figure>.  
  
-   <xref:System.Windows.Documents.ListItemCollection>. Элемент содержимого нефиксированного формата, представляющий конкретную единицу содержимого в виде упорядоченного или неупорядоченного списка <xref:System.Windows.Documents.List>.  
  
 Существует возможность управления \(добавления или удаления элементов\) из этих коллекций с помощью соответствующих свойств **Inlines**,  **Blocks** и **ListItems**.  В следующих примерах показано, как управлять содержимым Span с помощью свойства **Inlines**.  
  
> [!NOTE]
>  В таблице используется несколько коллекций для управления содержимым, но они не рассматриваются в данном руководстве.  Дополнительные сведения см. в разделе [Общие сведения о таблицах](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
 В следующем примере создается новый объект <xref:System.Windows.Documents.Span>, а затем вызывается метод `Add` для добавления двух текстовых выполнений в качестве дочернего содержимого объекта <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 В следующем примере создается новый элемент <xref:System.Windows.Documents.Run>, который вставляется в начало объекта <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 В следующем примере удаляется последний элемент <xref:System.Windows.Documents.Inline> в объекте <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 В следующем примере удаляется все содержимое \(элементы <xref:System.Windows.Documents.Inline>\) из объекта <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## Типы, совместно использующие модель содержимого  
 Следующие типы наследуют от класса <xref:System.Windows.Documents.TextElement> и могут быть использованы для отображения содержимого, описанного в этом обзоре.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 Учтите, что этот список включает только неабстрактные типы, распространяемые с набором [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].  Можно использовать другие типы, наследуемые от <xref:System.Windows.Documents.TextElement>.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## Типы, которые могут содержать объекты TextElement  
 См. раздел [Модель содержимого WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
## См. также  
 [Управление FlowDocument через свойство блоков](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)   
 [Управление элементами потокового содержимого через свойство Blocks](../../../../docs/framework/wpf/advanced/how-to-manipulate-flow-content-elements-through-the-blocks-property.md)   
 [Управление FlowDocument через свойство блоков](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)   
 [Управление столбцами таблицы с помощью свойства Columns](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)   
 [Управление группами строк таблицы пользователя с помощью свойства RowGroups](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)