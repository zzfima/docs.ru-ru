---
title: Общие сведения о документе нефиксированного формата
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], flow documents [WPF], , '
- ', '
- flow documents [WPF]
ms.assetid: ef236a50-d44f-43c8-ba7c-82b0c733c0b7
ms.openlocfilehash: 0cf8944298af62a512599fc52998a046c66fed9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549741"
---
# <a name="flow-document-overview"></a>Общие сведения о документе нефиксированного формата
Документы нефиксированного формата предназначены для более удобного просмотра и чтения. Вместо того чтобы использовать какой-либо определенный макет, документы нефиксированного формата динамически корректируют и перемещают содержимое с учетом переменных времени выполнения, таких как размер окна, разрешение устройства и дополнительные пользовательские настройки. Кроме того, в документах нефиксированного формата предоставляются дополнительные возможности работы с документами, такие как разбивка на страницы и столбцы. В этом разделе представлены общие сведения о документах нефиксированного формата и способах их создания.  
  

  
<a name="what_is_a_flow_document"></a>   
## <a name="what-is-a-flow-document"></a>Что такое документ нефиксированного формата  
 Документ нефиксированного формата предназначен для "переформатирования содержимого" в зависимости от размера окна, разрешения устройства и других переменных среды. Кроме того, документы нефиксированного формата имеют несколько встроенных возможностей, включая поиск, режимы просмотра, оптимизирующие читаемость, и возможность менять размер и внешний вид шрифта. Документы нефиксированного формата следует использовать, если удобство чтения является основным приоритетом. Напротив, документы фиксированного формата предназначены для статического представления. Документы фиксированного формата полезны в тех случаях, когда важна точная передача содержимого источника. В разделе [документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md) Дополнительные сведения о различных типах документов.  
  
 Ниже показан образец документа нефиксированного формата, отображенного в нескольких окнах разных размеров. При изменении области отображения содержимое переформатируется для оптимального использования доступного пространства.  
  
 ![Переформатирование содержимого в документе нефиксированного формата](../../../../docs/framework/wpf/advanced/media/edocs-flowdocument.png "eDocs_FlowDocument")  
  
 Как показано на рисунке выше, содержимое нефиксированного формата может включать многие компоненты, такие как абзацы, списки, изображения и др. Эти компоненты соответствуют элементам в разметке и объектам в процедурном коде. Мы будет отправлена в дальнейшем эти классы подробно [потока связанные классы](#flow_related_classes) разделе этого обзора. Теперь ниже приведен простой пример кода, создающий документ нефиксированного формата, состоящий из абзаца с жирным текстом и списка.
  
 [!code-xaml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]  
  
 На рисунке ниже представлен результат выполнения этого фрагмента кода.  
  
 ![Снимок экрана: отображение примера FlowDocument](../../../../docs/framework/wpf/advanced/media/flow-ovw-first-example.png "Flow_Ovw_First_Example")  
  
 В этом примере <xref:System.Windows.Controls.FlowDocumentReader> управления используется для размещения содержимого нефиксированного формата. В разделе [типов документов потока](#flow_document_types) Дополнительные сведения о содержимом нефиксированного формата, размещение элементов управления. <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, и <xref:System.Windows.Documents.Bold> элементы используются для управления форматированием содержимого на основе их порядка в разметке. Например <xref:System.Windows.Documents.Bold> элемент охватывает только часть текста в абзаце; в результате только эта часть текста полужирным шрифтом. Если вы когда-либо работали с HTML, такой сценарий будет вам знаком.  
  
 Как видно на приведенном выше рисунке есть несколько функций, встроенных в документы нефиксированного формата:
  
-   Поиск: позволяет пользователю выполнять полнотекстовый поиск по всему документу.  
  
-   Режим просмотра: пользователь может выбрать предпочтительный режим просмотра, включая постраничный (одна страница), двухстраничный (книжный формат чтения) и непрерывную прокрутку (документ без нижнего края).  Дополнительные сведения об этих режимах просмотра см. в разделе <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  
  
-   Элементы управления навигацией по страницам: если в режиме просмотра документа используются страницы, элементы управления перемещением по страницам включают кнопку для перехода на следующую страницу (стрелка вниз) или предыдущую страницу (стрелка вверх), а также индикаторы номера текущей страницы и общего числа страниц. Пролистывание страниц может также выполняться с помощью клавиши со стрелками.  
  
-   Увеличение: элементы управления масштабом позволяют пользователю увеличить или уменьшить масштаб, нажав кнопку "плюс" или "минус", соответственно. Элементы управления масштабом также включают ползунок для изменения масштаба. Дополнительные сведения см. в разделе <xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>.  
  
 Эти функции можно изменять с учетом элемента управления, используемого для размещения содержимого нефиксированного формата. В следующем разделе описываются различные элементы управления.  
  
<a name="flow_document_types"></a>   
## <a name="flow-document-types"></a>Типы документов нефиксированного формата  
 Отображение содержимого документа нефиксированного формата и его вид зависят от того, какой объект используется для размещения содержимого нефиксированного формата. Существуют четыре элемента управления, которые поддерживают просмотр содержимого нефиксированного формата: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.RichTextBox>, и <xref:System.Windows.Controls.FlowDocumentScrollViewer>. Эти элементы управления кратко описаны ниже.  
  
 **Примечание:** <xref:System.Windows.Documents.FlowDocument> требуется напрямую содержимое потока узлов, поэтому все эти элементы управления для просмотра занимать <xref:System.Windows.Documents.FlowDocument> для размещения содержимого нефиксированного формата.  
  
### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> включает в себя функции, которые позволяют пользователю динамически выбирать различные режимы просмотра, включая одностраничный (страницы в раз), две страницы в раз (книжный формат) режиме постоянной прокрутки (без дна) и режим просмотра. Дополнительные сведения об этих режимах просмотра см. в разделе <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>. Если не требуется возможность динамически переключаться между режимами просмотра <xref:System.Windows.Controls.FlowDocumentPageViewer> и <xref:System.Windows.Controls.FlowDocumentScrollViewer> предоставляют облегченные средства просмотра содержимого, которые исправлены в режиме просмотра.  
  
### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer и FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer> Отображает содержимое в страницы во время режима просмотра, а <xref:System.Windows.Controls.FlowDocumentScrollViewer> отображает содержимое в режиме постоянной прокрутки. Оба <xref:System.Windows.Controls.FlowDocumentPageViewer> и <xref:System.Windows.Controls.FlowDocumentScrollViewer> фиксированной для определенного режима просмотра. Сравнить с <xref:System.Windows.Controls.FlowDocumentReader>, которая содержит функции, которые позволяют пользователю динамически выбирать различные режимы просмотра (в соответствии со <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> перечисления), за счет его более ресурсоемким, чем <xref:System.Windows.Controls.FlowDocumentPageViewer> или <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 По умолчанию вертикальная полоса прокрутки отображается всегда, а горизонтальная полоса прокрутки становится видимой при необходимости. Значение по умолчанию пользовательский Интерфейс для <xref:System.Windows.Controls.FlowDocumentScrollViewer> не включает панель инструментов, однако <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> свойство может использоваться для включения встроенной панели инструментов.  
  
### <a name="richtextbox"></a>RichTextBox  
 Используется <xref:System.Windows.Controls.RichTextBox> при необходимости разрешить пользователю изменение содержимого потока. Например, если вы хотите создать редактор, который позволял пользователю управлять действия, как таблицы, курсив и полужирным шрифтом, форматирование и т. д, следует использовать <xref:System.Windows.Controls.RichTextBox>. В разделе [Обзор RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md) для получения дополнительной информации.  
  
 **Примечание:** содержимое внутри потока <xref:System.Windows.Controls.RichTextBox> работает не так же, как и содержимого нефиксированного формата, содержащихся в других элементах управления. Например, может быть не указаны столбцы в <xref:System.Windows.Controls.RichTextBox> и поэтому не автоматического изменения размеров. Кроме того, обычно встроенные возможности потока содержимого, например поиск, режим просмотра, навигацию по страницам и масштабирование недоступны в <xref:System.Windows.Controls.RichTextBox>.  
  
<a name="creating_flow_content"></a>   
## <a name="creating-flow-content"></a>Создание содержимого нефиксированного формата  
 Плавающее содержимое может быть сложной задачей, состоящая из различных элементов, включая текст, изображения, таблицы и даже <xref:System.Windows.UIElement> производных классов, таких как элементы управления. Чтобы понять, как создать сложное содержимое нефиксированного формата, нужно учитывать следующее:  
  
-   **Классы, связанные с содержимым нефиксированного формата**: каждый класс, используемый в содержимом нефиксированного формата, имеет особое назначение. Кроме того, иерархическая связь между классами нефиксированного формата помогает понять, как они используются. Например, классы, производные от <xref:System.Windows.Documents.Block> позволяют содержат другие объекты, а классы, производные от класса <xref:System.Windows.Documents.Inline> содержат отображаемых объектов.  
  
-   **Схема содержимого**: документ нефиксированного формата может потребовать значительного числа вложенных элементов. Схема содержимого задает возможные отношения типа "родительский-дочерний" между элементами.  
  
 В следующих разделах все эти вопросы будут рассмотрены более подробно.  
  
<a name="flow_related_classes"></a>   
## <a name="flow-related-classes"></a>Классы, связанные с содержимым нефиксированного формата  
 На приведенной ниже схеме показаны объекты, которые чаще всего используется с содержимым нефиксированного формата:  
  
 ![Схема: иерархия классов элементов содержимого нефиксированного формата](../../../../docs/framework/wpf/advanced/media/flow-class-hierarchy.png "Flow_Class_Hierarchy")  
  
 В работе с содержимым нефиксированного формата используются две важные категории:  
  
1.  **Классы, производные от блока**: также называются "блоковыми элементами содержимого" или просто "блоковыми элементами". Элементы, которые наследуют от <xref:System.Windows.Documents.Block> можно использовать для группировки элементов одного родителя или применения общих атрибутов в группу.  
  
2.  **Встроенные производные классы**: также называются "встроенными элементами содержимого" или просто "встроенными элементами". Элементы, которые наследуют от <xref:System.Windows.Documents.Inline> либо содержащихся в элементе блока или другой встроенного элемента. Встроенные элементы часто используются в качестве непосредственного контейнера содержимого, отображаемого на экране. Например <xref:System.Windows.Documents.Paragraph> (блок) может содержать <xref:System.Windows.Documents.Run> (встроенный элемент), но <xref:System.Windows.Documents.Run> фактически содержит текст, отображаемый на экране.  
  
 Ниже кратко описан каждый класс этих категорий.  
  
### <a name="block-derived-classes"></a>Классы, производные от блока  
 **Paragraph**  
  
 <xref:System.Windows.Documents.Paragraph> обычно используется для группировки содержимого в абзац. Самый простой и распространенный способ использования класса Paragraph — составление текстового абзаца.  
  
 [!code-xaml[FlowOvwSnippets_snip#ParagraphExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]  
  
 Однако также может содержать другие встроенные элементы, как будет показано ниже. 
  
 **Раздел**  
  
 <xref:System.Windows.Documents.Section> используется только для того, чтобы содержать другие <xref:System.Windows.Documents.Block>-элементов, производных. Он не применяет никакого форматирования по умолчанию к содержащимся в нем элементам. Тем не менее, любое свойство данные, установленные на <xref:System.Windows.Documents.Section> применяется к его дочерние элементы. Раздел также позволяет программным способом перебирать свою дочернюю коллекцию. <xref:System.Windows.Documents.Section> используется так же, как для \<DIV > тег в HTML.  
  
 В следующем примере три абзаца определяются под одним <xref:System.Windows.Documents.Section>. В разделе о <xref:System.Windows.Documents.TextElement.Background%2A> значение свойства Red, поэтому цвет фона абзацев также — красным.  
  
 [!code-xaml[FlowOvwSnippets_snip#SectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]  
  
 **BlockUIContainer**  
  
 <xref:System.Windows.Documents.BlockUIContainer> включает <xref:System.Windows.UIElement> элементы (т. е. <xref:System.Windows.Controls.Button>) для внедрения в блочное потоковое содержимое. <xref:System.Windows.Documents.InlineUIContainer> (см. ниже) используется для внедрения <xref:System.Windows.UIElement> элементы в содержимом нефиксированного формата встроенные. <xref:System.Windows.Documents.BlockUIContainer> и <xref:System.Windows.Documents.InlineUIContainer> важны, так как другие способы использования <xref:System.Windows.UIElement> потока содержимого, если он не содержится в одном из этих элементов.  
  
 В следующем примере показано, как использовать <xref:System.Windows.Documents.BlockUIContainer> для размещения элемента <xref:System.Windows.UIElement> объекты в содержимом нефиксированного формата.  
  
 [!code-xaml[SpanSnippets#_BlockUIXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]  
  
 На следующем рисунке показана отрисовка этого примера.  
  
 ![Снимок экрана: элемент UIElement, встроенный в содержимое нефиксированного формата](../../../../docs/framework/wpf/advanced/media/blockuicontainer.png "BlockUIContainer")  
  
 **List**  
  
 <xref:System.Windows.Documents.List> используется для создания маркированного или нумерованного списка. Задать <xref:System.Windows.Documents.List.MarkerStyle%2A> свойства <xref:System.Windows.TextMarkerStyle> значение перечисления для определения стиля списка. В приведенном ниже примере показано, как создать простой список.  
  
 [!code-xaml[FlowOvwSnippets_snip#ListExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]  
  
 **Примечание:** <xref:System.Windows.Documents.List> является единственным элементом потока, который использует <xref:System.Windows.Documents.ListItemCollection> для дочерних элементов управления.  
  
 **Таблица**  
  
 <xref:System.Windows.Documents.Table> используется для создания таблицы. <xref:System.Windows.Documents.Table> Аналогично <xref:System.Windows.Controls.Grid> элемент, но имеет больше возможностей и, следовательно, требует больше ресурсов. Поскольку <xref:System.Windows.Controls.Grid> — <xref:System.Windows.UIElement>, его нельзя использовать в содержимом нефиксированного формата, если он содержится в <xref:System.Windows.Documents.BlockUIContainer> или <xref:System.Windows.Documents.InlineUIContainer>. Дополнительные сведения о <xref:System.Windows.Documents.Table>, в разделе [Общие сведения о таблицах](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
### <a name="inline-derived-classes"></a>Встроенные классы  
 **Выполнить**  
  
 <xref:System.Windows.Documents.Run> используется для хранения неформатированного текста. Можно ожидать <xref:System.Windows.Documents.Run> содержимое потока в широко использовать объекты. Однако в разметке <xref:System.Windows.Documents.Run> элементы не обязательно должны использоваться явным образом. <xref:System.Windows.Documents.Run> требуется для использования при создании и управлении ими документы нефиксированного формата с помощью кода. Например, в разметке ниже первого <xref:System.Windows.Documents.Paragraph> указывает <xref:System.Windows.Documents.Run> элемент явно, а второй — нет. Оба абзаца создают идентичные выходные данные.  
  
 [!code-xaml[FlowOvwSnippets_snip#RunExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]  
  
 **Примечание:** начиная с версии [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], <xref:System.Windows.Documents.Run.Text%2A> свойство <xref:System.Windows.Documents.Run> объекта является свойством зависимостей. Можно привязать <xref:System.Windows.Documents.Run.Text%2A> источника свойства данных, такие как <xref:System.Windows.Controls.TextBlock>. <xref:System.Windows.Documents.Run.Text%2A> Свойство полностью поддерживает односторонние привязки. <xref:System.Windows.Documents.Run.Text%2A> Свойство также поддерживает двустороннюю привязку, за исключением <xref:System.Windows.Controls.RichTextBox>. Пример см. в разделе <xref:System.Windows.Documents.Run.Text%2A?displayProperty=nameWithType>.  
  
 **Span**  
  
 <xref:System.Windows.Documents.Span> Группирует другие элементы встроенного содержимого. Никакая обязательная отрисовка применяется к содержимому <xref:System.Windows.Documents.Span> элемента. Тем не менее, элементы, которые наследуются от <xref:System.Windows.Documents.Span> включая <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Italic> и <xref:System.Windows.Documents.Underline> применить форматирование к тексту.  
  
 Ниже приведен пример <xref:System.Windows.Documents.Span> , используемого для хранения встроенного содержимого, включая текст, <xref:System.Windows.Documents.Bold> элемент и <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[FlowOvwSnippets_snip#SpanExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]  
  
 На следующем снимке экрана показана отрисовка этого примера.  
  
 ![Снимок экрана: пример отрисовки элемента Span](../../../../docs/framework/wpf/advanced/media/flow-spanexample.gif "Flow_SpanExample")  
  
 **InlineUIContainer**  
  
 <xref:System.Windows.Documents.InlineUIContainer> включает <xref:System.Windows.UIElement> элементы (т. е. элемент управления, например <xref:System.Windows.Controls.Button>) для внедрения в <xref:System.Windows.Documents.Inline> содержимого элемента. Этот элемент является встроенным эквивалентом <xref:System.Windows.Documents.BlockUIContainer> описано выше. Ниже приведен пример, использующий <xref:System.Windows.Documents.InlineUIContainer> для вставки <xref:System.Windows.Controls.Button> , встроенный в <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xaml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]  
  
 **Примечание:** <xref:System.Windows.Documents.InlineUIContainer> не требуется явно использования в разметке. Если не указан, <xref:System.Windows.Documents.InlineUIContainer> будет создаваться несмотря на это, при компиляции кода.  
  
 **Figure и Floater**  
  
 <xref:System.Windows.Documents.Figure> и <xref:System.Windows.Documents.Floater> используются для включения содержимого в документах потока с помощью свойства размещения, которые могут быть настроены независимо от первичного потока содержимого. <xref:System.Windows.Documents.Figure> или <xref:System.Windows.Documents.Floater> элементы часто используются для выделения или подчеркивания частей содержимого, для размещения сопровождающих изображений или другого содержимого в рамках основного потока содержимого или для вставки такого содержимого, например объявления.  
  
 В следующем примере показано, как внедрить <xref:System.Windows.Documents.Figure> в абзац текста.  
  
 [!code-xaml[FlowOvwSnippets_snip#FigureExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]  
  
 На рисунке ниже показано, как будет выглядеть этот пример.  
  
 ![Снимок экрана: пример элемента Figure](../../../../docs/framework/wpf/advanced/media/flow-ovw-figure-example.png "Flow_Ovw_Figure_Example")  
  
 <xref:System.Windows.Documents.Figure> и <xref:System.Windows.Documents.Floater> немного отличаются и используются для различных сценариев.  
  
 **Figure:**  
  
-   Можно указывать местоположение: с помощью горизонтальных и вертикальных якорей можно закрепить элемент относительно страницы. содержимого, столбца или абзаца. Можно также использовать его <xref:System.Windows.Documents.Figure.HorizontalOffset%2A> и <xref:System.Windows.Documents.Figure.VerticalOffset%2A> свойства для указания произвольного смещения.  
  
-   Возможность изменения размера до более чем одного столбца: можно задать <xref:System.Windows.Documents.Figure> высоты и ширины для нескольких страниц, разместить столбцах. Обратите внимание, что в случае страницы и содержимого кратность более 1 не поддерживается. Например, можно задать ширину <xref:System.Windows.Documents.Figure> «0,5 страница» или «0.25 содержимого» или «Column 2». Также можно задать высоту и ширину в абсолютных пиксельных значениях.  
  
-   Разбивается на страницы: Если содержимое внутри <xref:System.Windows.Documents.Figure> не помещается <xref:System.Windows.Documents.Figure>, он будет отображать в соответствии с любым содержимым и остальное содержимое теряется.  
  
 **Floater:**  
  
-   Невозможно указать местоположение, отрисовывается в любом доступном пространстве. Невозможно задать смещение или значение привязки <xref:System.Windows.Documents.Floater>.  
  
-   Не меняются для более чем одного столбца: по умолчанию <xref:System.Windows.Documents.Floater> размеры в один столбец. Он имеет <xref:System.Windows.Documents.Floater.Width%2A> свойство, которое может быть присвоено абсолютное значение в пикселях, но если это значение превышает ширину одного столбца, оно игнорируется и размер плавающего объекта размера одного столбца. Размер меньше, чем один столбец, задав правильную ширину в пикселях, но нельзя относительно столбца, поэтому «0.5Column» не является допустимым выражением для <xref:System.Windows.Documents.Floater> ширины. <xref:System.Windows.Documents.Floater> Свойства высоты и является высота не может быть задано, его высота зависит от содержимого  
  
-   <xref:System.Windows.Documents.Floater> разбиение на страницы: если его содержимое с указанной шириной распространяется на высоту более 1 столбца, плавающий объект прерывается и разрывается следующий столбец, следующую страницу и т. д.  
  
 <xref:System.Windows.Documents.Figure> удобен для размещения отдельного содержимого, где вы хотите контролировать размер и размещение и уверены, что содержимое разместится в указанный размер. <xref:System.Windows.Documents.Floater> является хорошо подходит для размещения более свободного содержимого, расположенного подобно содержимому главной страницы, но отделен от нее.  
  
 **LineBreak**  
  
 <xref:System.Windows.Documents.LineBreak> вызывает разрыв строки в содержимом нефиксированного формата. В следующем примере показано использование функции <xref:System.Windows.Documents.LineBreak>.  
  
 [!code-xaml[FlowOvwSnippets_snip#LineBreakExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]  
  
 На следующем снимке экрана показана отрисовка этого примера.  
  
 ![Снимок экрана: пример LineBreak](../../../../docs/framework/wpf/advanced/media/flow-ovw-linebreakexample.png "Flow_Ovw_LineBreakExample")  
  
### <a name="flow-collection-elements"></a>Элементы коллекции нефиксированного формата  
 Во многих из приведенных выше примеров <xref:System.Windows.Documents.BlockCollection> и <xref:System.Windows.Documents.InlineCollection> используются для создания содержимого нефиксированного формата программными средствами. Например, чтобы добавить элементы в <xref:System.Windows.Documents.Paragraph>, используется следующий синтаксис:  
  
 `…`  
  
 `myParagraph.Inlines.Add(new Run("Some text"));`  
  
 `…`  
  
 Это добавляет <xref:System.Windows.Documents.Run> для <xref:System.Windows.Documents.InlineCollection> из <xref:System.Windows.Documents.Paragraph>.  Это то же самое, как неявный <xref:System.Windows.Documents.Run> внутри <xref:System.Windows.Documents.Paragraph> в разметке:  
  
 `…`  
  
 `<Paragraph>`  
  
 `Some Text`  
  
 `</Paragraph>`  
  
 `…`  
  
 В качестве примера использования <xref:System.Windows.Documents.BlockCollection>, в следующем примере создается новый <xref:System.Windows.Documents.Section> , а затем использует **добавить** метод, чтобы добавить новый <xref:System.Windows.Documents.Paragraph> для <xref:System.Windows.Documents.Section> содержимое.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
 Помимо добавления элементов в коллекцию нефиксированного формата элементы также можно удалять.  В следующем примере удаляется последний <xref:System.Windows.Documents.Inline> элемент в <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 В следующем примере удаляются все содержимое (<xref:System.Windows.Documents.Inline> элементы) из <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
 При работе с содержимым нефиксированного формата программными средствами эти коллекции, скорее всего, будут использоваться довольно активно.  
  
 Использует ли элемент потока <xref:System.Windows.Documents.InlineCollection> (встроенных элементов) или <xref:System.Windows.Documents.BlockCollection> (блоков) для хранения своих дочерних элементов зависит от типа дочерних элементов (<xref:System.Windows.Documents.Block> или <xref:System.Windows.Documents.Inline>) может содержаться в родительском. Правила включения для элементов содержимого нефиксированного формата обобщаются в схеме содержимого в следующем разделе.  
  
 **Примечание:** третий тип коллекции, используемой с содержимого нефиксированного формата <xref:System.Windows.Documents.ListItemCollection>, но эта коллекция используется только с <xref:System.Windows.Documents.List>. Кроме того, существует несколько коллекций, используемых с <xref:System.Windows.Documents.Table>. В разделе [Общие сведения о таблицах](../../../../docs/framework/wpf/advanced/table-overview.md) для получения дополнительной информации.  
  
<a name="content_schema"></a>   
## <a name="content-schema"></a>Схема содержимого  
 Учитывая количество различных элементов содержимого нефиксированного формата, может быть очень сложно отследить, какой тип дочерних элементов может содержать тот или иной элемент. На схеме ниже представлены правила включения для элементов нефиксированного формата. Стрелки указывают возможные связи "родитель-потомок".  
  
 ![Схема: схема вместимости потока содержимого](../../../../docs/framework/wpf/advanced/media/flow-content-schema.png "Flow_Content_Schema")  
  
 Как видно из диаграммы выше, потомки для элемента не обязательно определяются тем, является ли <xref:System.Windows.Documents.Block> элемент или <xref:System.Windows.Documents.Inline> элемент. Например <xref:System.Windows.Documents.Span> ( <xref:System.Windows.Documents.Inline> элемент) может иметь только <xref:System.Windows.Documents.Inline> дочерние элементы при <xref:System.Windows.Documents.Figure> (также <xref:System.Windows.Documents.Inline> элемент) может иметь только <xref:System.Windows.Documents.Block> дочерних элементов. Таким образом, схему можно использовать для быстрого определения элемента, который может содержаться в другом элементе. Например, используем диаграмму, чтобы определить способ создания потока содержимого <xref:System.Windows.Controls.RichTextBox>.  
  
 **1.** Объект <xref:System.Windows.Controls.RichTextBox> должен содержать <xref:System.Windows.Documents.FlowDocument> которой в свою очередь содержать <xref:System.Windows.Documents.Block>-производного объекта. Ниже приведен соответствующий сегмент из предыдущей диаграммы.  
  
 ![Схема: правила вместимости RichTextBox](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
 Разметка может выглядеть следующим образом.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
 **2.** Согласно схеме, существует ряд <xref:System.Windows.Documents.Block> элементы, включая выбор <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, и <xref:System.Windows.Documents.BlockUIContainer> (см. выше классы, производные от блока). Предположим, что мы хотим <xref:System.Windows.Documents.Table>. Согласно приведенной выше схеме <xref:System.Windows.Documents.Table> содержит <xref:System.Windows.Documents.TableRowGroup> содержащий <xref:System.Windows.Documents.TableRow> элементы, которые содержат <xref:System.Windows.Documents.TableCell> элементы, которые содержат <xref:System.Windows.Documents.Block>-производного объекта. Ниже приведен соответствующий сегмент для <xref:System.Windows.Documents.Table> взяты из приведенной выше схеме.  
  
 ![Схема: схема родительских/дочерних элементов для таблицы](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
 Ниже приводится соответствующая разметка.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
 **3.** Опять же один или несколько <xref:System.Windows.Documents.Block> элементы являются обязательными под <xref:System.Windows.Documents.TableCell>. Для удобства поместим часть текста в ячейку. Это можно сделать с помощью <xref:System.Windows.Documents.Paragraph> с <xref:System.Windows.Documents.Run> элемента. Ниже приведен соответствующий сегмент из диаграммы, показывающий, что <xref:System.Windows.Documents.Paragraph> может занять <xref:System.Windows.Documents.Inline> элемент, который <xref:System.Windows.Documents.Run> ( <xref:System.Windows.Documents.Inline> элемент) может принять только обычный текст.  
  
 ![Схема: схема родительских/дочерних элементов для абзаца](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
 ![Схема: схема родительских/дочерних элементов для запуска](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Ниже приведен полный пример в виде разметки.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="customizing_text"></a>   
## <a name="customizing-text"></a>Настройка текста  
 Обычно текст является наиболее распространенным типом содержимого в документе нефиксированного формата. Хотя представленные выше объекты могут использоваться для управления большинством аспектов отображения текста, существуют и другие методы для настройки текста, описанные в этом разделе.  
  
### <a name="text-decorations"></a>Оформление текста  
 Оформление текста позволяет применять к тексту эффекты подчеркивания, надчеркивания, нижней линии и зачеркивания (см. рисунки ниже). Эти эффекты оформления добавляются с помощью <xref:System.Windows.Documents.Inline.TextDecorations%2A> свойство, которое предоставляется ряд объектов, включая <xref:System.Windows.Documents.Inline>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Controls.TextBlock>, и <xref:System.Windows.Controls.TextBox>.  
  
 В следующем примере показано, как задать свойство <xref:System.Windows.Documents.Paragraph.TextDecorations%2A> объекта <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xaml[InlineSnippets#_Paragraph_TextDecXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]  
  
 [!code-csharp[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
 [!code-vb[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]  
  
 На следующем рисунке показана отрисовка этого примера.  
  
 ![Снимок экрана: текст с эффектом зачеркивания по умолчанию](../../../../docs/framework/wpf/advanced/media/inline-textdec-strike.png "Inline_TextDec_Strike")  
  
 Следующие схемы Показать как **надчеркивание**, **базового**, и **подчеркивание** украшения.  
  
 ![Снимок экрана: надчеркивание TextDecorator](../../../../docs/framework/wpf/advanced/media/inline-textdec-over.png "Inline_TextDec_Over")  
  
 ![Снимок экрана: текстовое оформление по умолчанию — нижняя линия](../../../../docs/framework/wpf/advanced/media/inline-textdec-base.png "Inline_TextDec_Base")  
  
 ![Снимок экрана: текст с оформлением "подчеркивание" по умолчанию](../../../../docs/framework/wpf/advanced/media/inline-textdec-under.png "Inline_TextDec_Under")  
  
### <a name="typography"></a>Типографская разметка  
 <xref:System.Windows.Documents.TextElement.Typography%2A> Свойство представляется включением большинство связанных потока содержимого <xref:System.Windows.Documents.TextElement>, <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Controls.TextBlock>, и <xref:System.Windows.Controls.TextBox>. Это свойство используется для управления типографскими характеристиками текста (т. е. малыми прописными или строчными буквами, надстрочными и подстрочными символами и т. д.).  
  
 Следующий пример показывает, как задать <xref:System.Windows.Documents.TextElement.Typography%2A> атрибута с помощью <xref:System.Windows.Documents.Paragraph> как пример элемента.  
  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 На следующем рисунке показана отрисовка этого примера.  
  
 ![Снимок экрана: текст с измененной типографией](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement_Typog")  
  
 Напротив, на следующем рисунке показано, как отрисовывается аналогичный пример с типографскими характеристиками по умолчанию.  
  
 ![Снимок экрана: текст с измененной типографией](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement_Typog_Default")  
  
 Следующий пример показывает, как задать <xref:System.Windows.Controls.TextBox.Typography%2A> свойства программными средствами.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
 В разделе [оформление в WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md) Дополнительные сведения о типографской разметке текста.  
  
## <a name="see-also"></a>См. также  
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Оформление в WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/advanced/flow-content-elements-how-to-topics.md)  
 [Общие сведения о модели содержимого TextElement](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md)  
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Общие сведения о таблицах](../../../../docs/framework/wpf/advanced/table-overview.md)  
 [Общие сведения о заметках](../../../../docs/framework/wpf/advanced/annotations-overview.md)
