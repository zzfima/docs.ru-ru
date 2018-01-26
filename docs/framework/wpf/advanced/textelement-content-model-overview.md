---
title: "Общие сведения о модели содержимого TextElement"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], flow documents
- TextElement content model [WPF]
- flow content elements [WPF], TextElement content model
ms.assetid: d0a7791c-b090-438c-812f-b9d009d83ee9
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 95d25ff6819ba913b7e9270bc2d87dd77032c5c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="textelement-content-model-overview"></a>Общие сведения о модели содержимого TextElement
Здесь описывается модель содержимого поддерживаемых содержимое <xref:System.Windows.Documents.TextElement>. <xref:System.Windows.Documents.Paragraph> Класс — это тип <xref:System.Windows.Documents.TextElement>. Модель содержимого описывает объекты/элементы, которые могут содержаться в других объектах. Обобщение модели содержимого для объектов, производных от <xref:System.Windows.Documents.TextElement>. Дополнительные сведения см. в разделе [Общие сведения о документа нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
  
<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a>Схема модели содержимого  
 На следующей диаграмме представлена модель содержимого для классов, производных от <xref:System.Windows.Documents.TextElement> а также тем, как другие отличных `TextElement` классов, соответствующих этой модели.  
  
 ![Схема: схема вместимости потока содержимого](../../../../docs/framework/wpf/advanced/media/flow-content-schema.png "Flow_Content_Schema")  
  
 Как видно из предыдущей диаграммы, потомки для элемента не обязательно определяются класс, производный от <xref:System.Windows.Documents.Block> класса или <xref:System.Windows.Documents.Inline> класса. Например <xref:System.Windows.Documents.Span> ( <xref:System.Windows.Documents.Inline>-производного класса) может иметь только <xref:System.Windows.Documents.Inline> дочерние элементы, но <xref:System.Windows.Documents.Figure> (также <xref:System.Windows.Documents.Inline>-производного класса) может иметь только <xref:System.Windows.Documents.Block> дочерних элементов. Таким образом, схему можно использовать для быстрого определения элемента, который может содержаться в другом элементе. Например, используем диаграмму, чтобы определить способ создания потока содержимого <xref:System.Windows.Controls.RichTextBox>.  
  
1.  Объект <xref:System.Windows.Controls.RichTextBox> должен содержать <xref:System.Windows.Documents.FlowDocument> которой в свою очередь содержать <xref:System.Windows.Documents.Block>-производного объекта. Ниже приведен соответствующий сегмент из предыдущей диаграммы.  
  
     ![Схема: правила вместимости RichTextBox](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     Разметка может выглядеть следующим образом.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2.  Согласно схеме, существует ряд <xref:System.Windows.Documents.Block> элементы, включая выбор <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, и <xref:System.Windows.Documents.BlockUIContainer> (см. классы, производные от блока на предыдущей схеме). Предположим, что мы хотим <xref:System.Windows.Documents.Table>. В соответствии с предыдущей схеме <xref:System.Windows.Documents.Table> содержит <xref:System.Windows.Documents.TableRowGroup> содержащий <xref:System.Windows.Documents.TableRow> элементы, которые содержат <xref:System.Windows.Documents.TableCell> элементы, которые содержат <xref:System.Windows.Documents.Block>-производного объекта. Ниже приведен соответствующий сегмент для <xref:System.Windows.Documents.Table> взяты из предыдущей диаграммы.  
  
     ![Схема: схема родительских/дочерних элементов для таблицы](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     Ниже приведена соответствующая разметка.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3.  Опять же один или несколько <xref:System.Windows.Documents.Block> элементы являются обязательными под <xref:System.Windows.Documents.TableCell>. Для удобства поместим часть текста в ячейку. Это можно сделать с помощью <xref:System.Windows.Documents.Paragraph> с <xref:System.Windows.Documents.Run> элемента. Ниже приведен соответствующий сегмент из диаграммы, показывающий, что <xref:System.Windows.Documents.Paragraph> может занять <xref:System.Windows.Documents.Inline> элемент, который <xref:System.Windows.Documents.Run> ( <xref:System.Windows.Documents.Inline> элемент) может принять только обычный текст.  
  
     ![Схема: схема родительских/дочерних элементов для абзаца](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![Схема: схема родительских/дочерних элементов для запуска](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Ниже приведен полный пример в виде разметки.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a>Работа с содержимым TextElement с помощью программных средств  
 Содержимое <xref:System.Windows.Documents.TextElement> состоит с помощью коллекций и поэтому программное управление содержимое <xref:System.Windows.Documents.TextElement> объектов можно сделать, работая с этими коллекциями. Существуют три различные коллекции, используемые <xref:System.Windows.Documents.TextElement> -производные классы:  
  
-   <xref:System.Windows.Documents.InlineCollection>: Представляет коллекцию <xref:System.Windows.Documents.Inline> элементов. <xref:System.Windows.Documents.InlineCollection>Определяет допустимое дочернее содержимое элементов <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span>, и <xref:System.Windows.Controls.TextBlock> элементы.  
  
-   <xref:System.Windows.Documents.BlockCollection>: Представляет коллекцию <xref:System.Windows.Documents.Block> элементов. <xref:System.Windows.Documents.BlockCollection>Определяет допустимое дочернее содержимое элементов <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater>, и <xref:System.Windows.Documents.Figure> элементы.  
  
-   <xref:System.Windows.Documents.ListItemCollection>: Элемент содержимого потока, представляющий определенный элемент содержимого в упорядоченную или неупорядоченную <xref:System.Windows.Documents.List>.  
  
 Можно управлять (добавления или удаления элементов) из этих коллекций с помощью соответствующих свойств **внедряет**, **блоки**, и **элементов ListItem**. Следующие примеры показывают, как управлять содержимым Span с помощью **внедряет** свойство.  
  
> [!NOTE]
>  В таблице используется несколько коллекций для управления содержимым, но они не рассматриваются в данном руководстве. Дополнительные сведения см. в разделе [Общие сведения о таблицах](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
 В следующем примере создается новый <xref:System.Windows.Documents.Span> объекта, а затем используется `Add` метод для добавления двух текстовых выполняется как содержимого дочерних элементов <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 В следующем примере создается новый <xref:System.Windows.Documents.Run> элемент и вставляет его в начале <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 В следующем примере удаляется последний <xref:System.Windows.Documents.Inline> элемент в <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 В следующем примере удаляются все содержимое (<xref:System.Windows.Documents.Inline> элементы) из <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a>Типы, совместно использующие модель содержимого  
 Следующие типы наследуют от <xref:System.Windows.Documents.TextElement> класса и могут быть использованы для отображения содержимого, описанные в этом обзоре.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 Обратите внимание, что этот список включает только неабстрактные типы, распространяемые с [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]. Вы можете использовать другие типы, которые наследуют от <xref:System.Windows.Documents.TextElement>.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a>Типы, которые могут содержать объекты TextElement  
 В разделе [модель содержимого WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
## <a name="see-also"></a>См. также  
 [Управление FlowDocument с помощью свойства Blocks](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [Управление элементами потокового содержимого с помощью свойства Blocks](../../../../docs/framework/wpf/advanced/how-to-manipulate-flow-content-elements-through-the-blocks-property.md)  
 [Управление FlowDocument с помощью свойства Blocks](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [Управление столбцами таблицы с помощью свойства Columns](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [Управление группами строк таблицы пользователя с помощью свойства RowGroups](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
