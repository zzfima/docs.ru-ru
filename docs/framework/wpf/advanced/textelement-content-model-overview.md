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
ms.openlocfilehash: ddb2613dc924424b5f4b9d90f06d44b45b7b5e77
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186904"
---
# <a name="textelement-content-model-overview"></a>Общие сведения о модели содержимого TextElement
В этом обзоре модели содержимого <xref:System.Windows.Documents.TextElement>описывается поддерживаемое содержимое для . Класс <xref:System.Windows.Documents.Paragraph> является одним <xref:System.Windows.Documents.TextElement>из видов . Модель содержимого описывает объекты/элементы, которые могут содержаться в других объектах. В этом обзоре кратко излагается модель <xref:System.Windows.Documents.TextElement>содержимого, используемая для объектов, полученных из . Для получения дополнительной [Flow Document Overview](flow-document-overview.md)информации см.  

<a name="text_element_classes"></a>
## <a name="content-model-diagram"></a>Схема модели содержимого  
 На следующей диаграмме кратко излагается <xref:System.Windows.Documents.TextElement> модель содержимого классов, `TextElement` полученных из классов, а также то, как другие неклассы вписываются в эту модель.  
  
 ![Схема: схема вместимости потока содержимого](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 Как видно из предыдущей диаграммы, дети, допущенные к элементу, не обязательно определяются тем, является ли класс выведен из <xref:System.Windows.Documents.Block> класса или <xref:System.Windows.Documents.Inline> класса. Например, <xref:System.Windows.Documents.Span> a <xref:System.Windows.Documents.Inline>(класс - производный) <xref:System.Windows.Documents.Inline> может <xref:System.Windows.Documents.Figure> иметь только <xref:System.Windows.Documents.Inline>элементы ребенка, <xref:System.Windows.Documents.Block> но (также -производный класс) может иметь только элементы ребенка. Таким образом, схему можно использовать для быстрого определения элемента, который может содержаться в другом элементе. В качестве примера давайте рассмотрим диаграмму, чтобы определить, <xref:System.Windows.Controls.RichTextBox>как построить содержимое потока в.  
  
1. A <xref:System.Windows.Controls.RichTextBox> должен <xref:System.Windows.Documents.FlowDocument> содержать объект, который, в свою очередь, должен содержать объект, полученный <xref:System.Windows.Documents.Block>в результате. Ниже приведен соответствующий сегмент из предыдущей диаграммы.  
  
     ![Схема: правила вместимости RichTextBox](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     Разметка может выглядеть следующим образом.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. Согласно <xref:System.Windows.Documents.Block> диаграмме, есть несколько элементов <xref:System.Windows.Documents.Paragraph>на <xref:System.Windows.Documents.Section> <xref:System.Windows.Documents.Table>выбор, включая , , , <xref:System.Windows.Documents.List>и <xref:System.Windows.Documents.BlockUIContainer> (см. Блок-производных классов в предыдущей диаграмме). Допустим, мы хотим <xref:System.Windows.Documents.Table>. Согласно предыдущей диаграмме, <xref:System.Windows.Documents.Table> а, <xref:System.Windows.Documents.TableRowGroup> в <xref:System.Windows.Documents.TableRow> котором <xref:System.Windows.Documents.TableCell> содержатся <xref:System.Windows.Documents.Block>элементы, содержащие элементы, содержащие объект, полученный. Ниже приводится соответствующий <xref:System.Windows.Documents.Table> сегмент, взятый из предыдущей диаграммы.  
  
     ![Диаграмма: Родительная&#47;детская схема для таблицы](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     Ниже приведена соответствующая разметка.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. Опять же, <xref:System.Windows.Documents.Block> один или несколько элементов требуется под <xref:System.Windows.Documents.TableCell>. Для удобства поместим часть текста в ячейку. Мы можем сделать <xref:System.Windows.Documents.Paragraph> это <xref:System.Windows.Documents.Run> с помощью элемента. Ниже приведены соответствующие сегменты диаграммы, <xref:System.Windows.Documents.Paragraph> показывающие, что может взять <xref:System.Windows.Documents.Inline> элемент и что <xref:System.Windows.Documents.Run> <xref:System.Windows.Documents.Inline> (элемент) может принимать только простой текст.  
  
     ![Диаграмма: Родитель&#47;детская схема для параграфа](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![Диаграмма: Схема&#47;ребенка для запуска](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Ниже приведен полный пример в виде разметки.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>
## <a name="working-with-textelement-content-programmatically"></a>Работа с содержимым TextElement с помощью программных средств  
 Содержимое <xref:System.Windows.Documents.TextElement> а состоит из коллекций и поэтому программное <xref:System.Windows.Documents.TextElement> манипулирование содержимым объектов осуществляется путем работы с этими коллекциями. Существуют три различных <xref:System.Windows.Documents.TextElement> коллекции, используемые классами, полученными:  
  
- <xref:System.Windows.Documents.InlineCollection>: Представляет собой <xref:System.Windows.Documents.Inline> набор элементов. <xref:System.Windows.Documents.InlineCollection> определяет допустимое дочернее содержимое элементов <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span> и <xref:System.Windows.Controls.TextBlock>.  
  
- <xref:System.Windows.Documents.BlockCollection>: Представляет собой <xref:System.Windows.Documents.Block> набор элементов. <xref:System.Windows.Documents.BlockCollection> определяет допустимое дочернее содержимое элементов <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> и <xref:System.Windows.Documents.Figure>.  
  
- <xref:System.Windows.Documents.ListItemCollection>: Элемент содержимого потока, представляющий определенный элемент <xref:System.Windows.Documents.List>содержимого в заказном или неупорядоченном элементе.  
  
 Вы можете манипулировать (добавить или удалить элементы) из этих коллекций, используя соответствующие свойства **Inlines,** **блоки,** и **ListItems**. Ниже приведены следующие примеры, как манипулировать содержимым span с помощью свойства **Inlines.**  
  
> [!NOTE]
> В таблице используется несколько коллекций для управления содержимым, но они не рассматриваются в данном руководстве. Для получения дополнительной информации [см.](table-overview.md)  
  
 Следующий пример создает <xref:System.Windows.Documents.Span> новый объект, `Add` а затем использует метод для <xref:System.Windows.Documents.Span>добавления двух текстовых запусков в качестве содержимого детей .  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 Следующий пример создает <xref:System.Windows.Documents.Run> новый элемент и вставляет его в начале <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 Следующий пример удаляет <xref:System.Windows.Documents.Inline> последний <xref:System.Windows.Documents.Span>элемент в .  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 Следующий пример очищает все содержимое (элементы)<xref:System.Windows.Documents.Inline> от . <xref:System.Windows.Documents.Span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>
## <a name="types-that-share-this-content-model"></a>Типы, совместно использующие модель содержимого  
 Следующие типы <xref:System.Windows.Documents.TextElement> наследуют сяизм из класса и могут использоваться для отображения содержимого, описанного в этом обзоре.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 Обратите внимание, что этот список включает только неабсотрактные типы, распространяемые с Windows SDK. Вы можете использовать другие <xref:System.Windows.Documents.TextElement>типы, которые наследуют от .  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>
## <a name="types-that-can-contain-textelement-objects"></a>Типы, которые могут содержать объекты TextElement  
 Смотрите [модель контента WPF](../controls/wpf-content-model.md).  
  
## <a name="see-also"></a>См. также раздел

- [Управление FlowDocument с помощью свойства Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Управление элементами потокового содержимого с помощью свойства Blocks](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [Управление FlowDocument с помощью свойства Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Управление столбцами таблицы с помощью свойства Columns](how-to-manipulate-table-columns-through-the-columns-property.md)
- [Управление группами строк таблицы пользователя с помощью свойства RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
