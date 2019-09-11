---
title: Общие сведения о документах нефиксированного формата
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], flow documents [WPF], , '
- ', '
- flow documents [WPF]
ms.assetid: ef236a50-d44f-43c8-ba7c-82b0c733c0b7
ms.openlocfilehash: 1dcba034dd934cb0e103cd131fcaa2088e2f93d3
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856148"
---
# <a name="flow-document-overview"></a>Общие сведения о документах нефиксированного формата

Документы нефиксированного формата предназначены для более удобного просмотра и чтения. Вместо того чтобы использовать какой-либо определенный макет, документы нефиксированного формата динамически корректируют и перемещают содержимое с учетом переменных времени выполнения, таких как размер окна, разрешение устройства и дополнительные пользовательские настройки. Кроме того, в документах нефиксированного формата доступны расширенные возможности, такие как разбивка на страницы и столбцы. В этом разделе представлены общие сведения о документах нефиксированного формата и способах их создания.

<a name="what_is_a_flow_document"></a>

## <a name="what-is-a-flow-document"></a>Что такое документ нефиксированного формата

Документ нефиксированного формата предназначен для "переформатирования содержимого" в зависимости от размера окна, разрешения устройства и других переменных среды. Кроме того, документы нефиксированного формата имеют несколько встроенных возможностей, включая поиск, режимы просмотра, оптимизирующие читаемость, и возможность менять размер и внешний вид шрифта. Документы нефиксированного формата следует использовать, если удобство чтения является основным приоритетом. Напротив, документы фиксированного формата предназначены для статического представления. Документы фиксированного формата полезны в тех случаях, когда важна точная передача содержимого источника. Дополнительные сведения о различных типах документов см. [в разделе документы в WPF](documents-in-wpf.md) .

Ниже показан образец документа нефиксированного формата, отображенного в нескольких окнах разных размеров. При изменении области отображения содержимое переформатируется для оптимального использования доступного пространства.

![Переформатирование содержимого в документе нефиксированного формата](./media/edocs-flowdocument.png "eDocs_FlowDocument")

Как показано на рисунке выше, содержимое нефиксированного формата может включать многие компоненты, такие как абзацы, списки, изображения и др. Эти компоненты соответствуют элементам в разметке и объектам в процедурном коде. Более подробно эти классы будут рассмотрены далее в разделе [классы, связанные с потоками](#flow_related_classes) этого обзора. Сейчас вот простой пример кода, который создает документ нефиксированного формата, состоящий из абзаца с полужирным текстом и списком.

[!code-xaml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]

На рисунке ниже представлен результат выполнения этого фрагмента кода.

![Снимок экрана Подготовленный пример]FlowDocument(./media/flow-ovw-first-example.png "Flow_Ovw_First_Example")

В этом примере <xref:System.Windows.Controls.FlowDocumentReader> элемент управления используется для размещения содержимого нефиксированного формата. Дополнительные сведения об элементах управления размещением содержимого нефиксированного формата см. в разделе [типы документов Flow](#flow_document_types) . <xref:System.Windows.Documents.Paragraph>элементы <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, и<xref:System.Windows.Documents.Bold> используются для управления форматированием содержимого в зависимости от их порядка в разметке. Например, <xref:System.Windows.Documents.Bold> элемент охватывает только часть текста в абзаце; в результате только эта часть текста выделяется полужирным шрифтом. Если вы когда-либо работали с HTML, такой сценарий будет вам знаком.

Как видно на рисунке выше, в документах нефиксированного формата есть несколько встроенных функций:

- Поиск: Позволяет пользователю выполнять полнотекстовый поиск по всему документу.

- Режим просмотра: Пользователь может выбрать предпочтительный режим просмотра, включая одностраничный (страничный) режим просмотра, два страничных режима (формат чтения книги), режим просмотра с непрерывной прокруткой (без нижнего).  Дополнительные сведения об этих режимах просмотра см. <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>в разделе.

- Элементы управления навигацией по страницам: Если в режиме просмотра документа используются страницы, элементы управления навигацией на странице включают кнопку для перехода на следующую страницу (стрелка вниз) или предыдущую страницу (стрелка вверх), а также индикаторы для текущего номера страницы и общего количества страниц. Пролистывание страниц может также выполняться с помощью клавиши со стрелками.

- Масштаб: Элементы управления масштабом позволяют пользователю увеличивать или уменьшать масштаб, нажимая кнопки «плюс» или «минус» соответственно. Элементы управления масштабом также включают ползунок для изменения масштаба. Дополнительные сведения см. в разделе <xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>.

Эти функции можно изменять с учетом элемента управления, используемого для размещения содержимого. В следующем разделе описываются различные элементы управления.

<a name="flow_document_types"></a>

## <a name="flow-document-types"></a>Типы документов нефиксированного формата

Отображение содержимого документа нефиксированного формата и его вид зависят от того, какой объект используется для размещения содержимого. Существует четыре элемента управления, поддерживающих просмотр содержимого нефиксированного формата <xref:System.Windows.Controls.RichTextBox>: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentScrollViewer> <xref:System.Windows.Controls.FlowDocumentPageViewer>, и. Эти элементы управления кратко описаны ниже.

> [!NOTE]
> <xref:System.Windows.Documents.FlowDocument>требуется для непосредственного размещения содержимого нефиксированного формата, поэтому все эти элементы управления <xref:System.Windows.Documents.FlowDocument> просмотра используют для включения размещения содержимого нефиксированного формата.

### <a name="flowdocumentreader"></a>FlowDocumentReader

<xref:System.Windows.Controls.FlowDocumentReader>включает функции, позволяющие пользователю динамически выбирать между различными режимами просмотра, включая одностраничный (страничный) режим просмотра, два страничных режима (формат чтения книги) и непрерывный режим просмотра (без нижнего прокрутки). Дополнительные сведения об этих режимах просмотра см. <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>в разделе. Если не требуется возможность динамически переключаться между разными режимами <xref:System.Windows.Controls.FlowDocumentPageViewer> просмотра и <xref:System.Windows.Controls.FlowDocumentScrollViewer> предоставить облегченные средства просмотра содержимого нефиксированного формата, исправленные в определенном режиме просмотра.

### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer и FlowDocumentScrollViewer

<xref:System.Windows.Controls.FlowDocumentPageViewer>показывает содержимое в режиме просмотра на странице, в то время как <xref:System.Windows.Controls.FlowDocumentScrollViewer> отображает содержимое в режиме непрерывной прокрутки. И, <xref:System.Windows.Controls.FlowDocumentScrollViewer> и исправляются в определенный режим просмотра. <xref:System.Windows.Controls.FlowDocumentPageViewer> Сравните с <xref:System.Windows.Controls.FlowDocumentReader>, который включает функции, позволяющие пользователю динамически выбирать между различными режимами просмотра (в соответствии <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> с перечислением), за счет более ресурсоемких ресурсов, чем <xref:System.Windows.Controls.FlowDocumentPageViewer> или <xref:System.Windows.Controls.FlowDocumentScrollViewer>.

По умолчанию вертикальная полоса прокрутки отображается всегда, а горизонтальная полоса прокрутки становится видимой при необходимости. Пользовательский интерфейс по умолчанию для <xref:System.Windows.Controls.FlowDocumentScrollViewer> не включает панель инструментов <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> , однако свойство можно использовать для включения встроенной панели инструментов.

### <a name="richtextbox"></a>RichTextBox

Используйте, <xref:System.Windows.Controls.RichTextBox> если вы хотите разрешить пользователю изменять содержимое нефиксированного формата. Например, если вы хотите создать редактор, который позволял бы пользователю манипулировать такими элементами, как таблицы, курсивом и полужирным шрифтом и т <xref:System.Windows.Controls.RichTextBox>. д., следует использовать. Дополнительные сведения см. в [обзоре RichTextBox](../controls/richtextbox-overview.md) .

> [!NOTE]
> Содержимое нефиксированного <xref:System.Windows.Controls.RichTextBox> формата внутри не работает точно так же, как и содержимое потока, содержащееся в других элементах управления. Например, отсутствуют столбцы в <xref:System.Windows.Controls.RichTextBox> и, следовательно, автоматическое изменение размера не выполняется. Кроме того, обычно встроенные функции содержимого нефиксированного формата, такие как поиск, режим просмотра, Навигация по страницам и масштаб <xref:System.Windows.Controls.RichTextBox>, недоступны в.

<a name="creating_flow_content"></a>

## <a name="creating-flow-content"></a>Создание содержимого нефиксированного формата

Содержимое нефиксированного формата может быть сложным, состоящим из различных элементов, включая текст, изображения, <xref:System.Windows.UIElement> таблицы и даже производные классы, такие как элементы управления. Чтобы понять, как создавать сложное размещение содержимого, нужно учитывать следующее:

- **Классы, связанные с потоком**: Каждый класс, используемый в содержимом нефиксированного формата, имеет определенную цель. Кроме того, иерархическая связь между классами нефиксированного формата помогает понять, как они используются. Например, классы, производные от <xref:System.Windows.Documents.Block> класса, используются для хранения других объектов, в то время <xref:System.Windows.Documents.Inline> как классы, производные от, содержат объекты, которые отображаются.

- **Схема содержимого**: Документ нефиксированного формата может потребовать значительного количества вложенных элементов. Схема содержимого задает возможные отношения типа "родительский-дочерний" между элементами.

В следующих разделах все эти вопросы будут рассмотрены более подробно.

<a name="flow_related_classes"></a>

## <a name="flow-related-classes"></a>Классы, связанные с содержимым нефиксированного формата

На приведенной ниже схеме показаны объекты, которые чаще всего используется с содержимым нефиксированного формата:

![Схема: Иерархия]класса элементов содержимого Flow(./media/flow-class-hierarchy.png "Flow_Class_Hierarchy")

В работе с размещением содержимого используются две важные категории:

1. **Классы, производные от блока**: Также называется "блочные элементы содержимого" или просто "блочные элементы". Элементы, наследующие <xref:System.Windows.Documents.Block> от, могут использоваться для группирования элементов в общем родительском объекте или для применения общих атрибутов к группе.

2. **Производные от встроенных классов**: Также называется "встроенными элементами содержимого" или просто "встроенными элементами". Элементы, наследующие <xref:System.Windows.Documents.Inline> от, либо содержатся в элементе Block, либо в другом встроенном элементе. Встроенные элементы часто используются в качестве непосредственного контейнера содержимого, отображаемого на экране. Например, <xref:System.Windows.Documents.Paragraph> (блочный элемент) может <xref:System.Windows.Documents.Run> содержать ( <xref:System.Windows.Documents.Run> встроенный элемент), но фактически содержит текст, отображаемый на экране.

Ниже кратко описан каждый класс этих категорий.

### <a name="block-derived-classes"></a>Классы, производные от блока

**Paragraph**

<xref:System.Windows.Documents.Paragraph>обычно используется для группирования содержимого в абзац. Самый простой и распространенный способ использования класса Paragraph — составление текстового абзаца.

[!code-xaml[FlowOvwSnippets_snip#ParagraphExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]

Однако можно также включить другие элементы, производные от встроенного кода, как показано ниже.

**Раздел**

<xref:System.Windows.Documents.Section>используется только для хранения других <xref:System.Windows.Documents.Block>элементов, производных от. Он не применяет никакого форматирования по умолчанию к содержащимся в нем элементам. Однако все значения свойств, заданные для <xref:System.Windows.Documents.Section> , применяются к его дочерним элементам. Раздел также позволяет программным способом перебирать свою дочернюю коллекцию. <xref:System.Windows.Documents.Section>используется аналогичным образом \<тега div > в HTML.

В приведенном ниже примере в одном из них <xref:System.Windows.Documents.Section>определены три абзаца. Раздел имеет <xref:System.Windows.Documents.TextElement.Background%2A> свойство со значением Red, поэтому цвет фона абзацев также красный.

[!code-xaml[FlowOvwSnippets_snip#SectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]

**BlockUIContainer**

<xref:System.Windows.Documents.BlockUIContainer>позволяет <xref:System.Windows.UIElement> внедрять элементы (т <xref:System.Windows.Controls.Button>. е.) в содержимое потока, производное от блока. <xref:System.Windows.Documents.InlineUIContainer>(см. ниже) используется для внедрения <xref:System.Windows.UIElement> элементов во встроенное содержимое потока. <xref:System.Windows.Documents.BlockUIContainer>и <xref:System.Windows.Documents.InlineUIContainer> важны, поскольку нет другого способа использовать в нефиксированном <xref:System.Windows.UIElement> содержимом, если он не содержится в одном из этих двух элементов.

В следующем примере показано, как использовать <xref:System.Windows.Documents.BlockUIContainer> элемент для размещения <xref:System.Windows.UIElement> объектов в содержимом нефиксированного формата.

[!code-xaml[SpanSnippets#_BlockUIXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]

На следующем рисунке показано, как отображается этот пример.

![Снимок экрана, показывающий UIElement, внедренный в нефиксированное содержимое.](./media/flow-document-overview/embedded-blockuicontainer.png)

**List**

<xref:System.Windows.Documents.List>используется для создания маркированного или нумерованного списка. Присвойте <xref:System.Windows.TextMarkerStyle> свойству значение перечисления, чтобы определить стиль списка. <xref:System.Windows.Documents.List.MarkerStyle%2A> В приведенном ниже примере показано, как создать простой список.

[!code-xaml[FlowOvwSnippets_snip#ListExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]

> [!NOTE]
> <xref:System.Windows.Documents.List>— Это единственный элемент Flow, использующий <xref:System.Windows.Documents.ListItemCollection> для управления дочерними элементами.

**Таблица**

<xref:System.Windows.Documents.Table>используется для создания таблицы. <xref:System.Windows.Documents.Table>функция похожа <xref:System.Windows.Controls.Grid> на элемент, но имеет больше возможностей и, следовательно, требует большего объема ресурсов. Поскольку <xref:System.Windows.Controls.Grid> <xref:System.Windows.Documents.BlockUIContainer> является, он не может использоваться в потоке содержимого, если он не содержится в или <xref:System.Windows.Documents.InlineUIContainer>. <xref:System.Windows.UIElement> Дополнительные сведения о см <xref:System.Windows.Documents.Table>. в разделе [Общие сведения о таблице](table-overview.md).

### <a name="inline-derived-classes"></a>Встроенные классы

**Выполнить**

<xref:System.Windows.Documents.Run>используется для хранения неформатированного текста. Вы можете ожидать <xref:System.Windows.Documents.Run> , что объекты будут широко использоваться в содержимом нефиксированного формата. Однако в разметке <xref:System.Windows.Documents.Run> элементы не обязательно должны использоваться явным образом. <xref:System.Windows.Documents.Run>необходимо использовать при создании документов нефиксированного формата или управлении ими с помощью кода. Например, в разметке, приведенной ниже <xref:System.Windows.Documents.Paragraph> , первый <xref:System.Windows.Documents.Run> указывает элемент явным образом, а второй — нет. Оба абзаца создают идентичные выходные данные.

[!code-xaml[FlowOvwSnippets_snip#RunExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]

> [!NOTE]
> Начиная с .NET Framework 4, <xref:System.Windows.Documents.Run.Text%2A> свойство <xref:System.Windows.Documents.Run> объекта является свойством зависимостей. Можно привязать <xref:System.Windows.Documents.Run.Text%2A> свойство к источнику данных, например к <xref:System.Windows.Controls.TextBlock>. <xref:System.Windows.Documents.Run.Text%2A> Свойство полностью поддерживает одностороннюю привязку. Свойство также поддерживает двустороннюю привязку, <xref:System.Windows.Controls.RichTextBox>за исключением. <xref:System.Windows.Documents.Run.Text%2A> Пример см. в разделе <xref:System.Windows.Documents.Run.Text%2A?displayProperty=nameWithType>.

**Span**

<xref:System.Windows.Documents.Span>группирует другие встроенные элементы содержимого вместе. К содержимому внутри <xref:System.Windows.Documents.Span> элемента не применяется встроенная отрисовка. Однако элементы, унаследованные от <xref:System.Windows.Documents.Span> , <xref:System.Windows.Documents.Hyperlink>включают <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Italic> и <xref:System.Windows.Documents.Underline> , применяют форматирование к тексту.

Ниже приведен пример <xref:System.Windows.Documents.Span> использования для включения встроенного содержимого <xref:System.Windows.Documents.Bold> , включая текст, элемент и <xref:System.Windows.Controls.Button>.

[!code-xaml[FlowOvwSnippets_snip#SpanExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]

На следующем снимке экрана показана отрисовка этого примера.

![Снимок экрана Пример]отображаемого диапазона(./media/flow-spanexample.gif "Flow_SpanExample")

**InlineUIContainer**

<xref:System.Windows.Documents.InlineUIContainer>позволяет <xref:System.Windows.UIElement> внедрять элементы (например, <xref:System.Windows.Controls.Button>элемент управления) в <xref:System.Windows.Documents.Inline> элемент содержимого. Этот элемент является встроенным эквивалентом <xref:System.Windows.Documents.BlockUIContainer> , описанным выше. Ниже приведен пример использования <xref:System.Windows.Documents.InlineUIContainer> для <xref:System.Windows.Controls.Button> вставки встроенного элемента в <xref:System.Windows.Documents.Paragraph>.

[!code-xaml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]

> [!NOTE]
> <xref:System.Windows.Documents.InlineUIContainer>не нужно явно использовать в разметке. Если опустить его, будет создано <xref:System.Windows.Documents.InlineUIContainer> исключение при компиляции кода.

**Figure и Floater**

<xref:System.Windows.Documents.Figure>и <xref:System.Windows.Documents.Floater> используются для внедрения содержимого в документы нефиксированного формата со свойствами размещения, которые могут быть настроены независимо от основного потока содержимого. <xref:System.Windows.Documents.Figure>элементы <xref:System.Windows.Documents.Floater> или часто используются для выделения или акцентирования частей содержимого, для размещения вспомогательных изображений или другого содержимого в основном потоке содержимого или для вставки слабо связанного содержимого, такого как объявления.

В следующем примере показано, как внедрить <xref:System.Windows.Documents.Figure> в абзац текста.

[!code-xaml[FlowOvwSnippets_snip#FigureExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]

На рисунке ниже показано, как будет выглядеть этот пример.

![Снимок экрана Рис.]пример(./media/flow-ovw-figure-example.png "Flow_Ovw_Figure_Example")

<xref:System.Windows.Documents.Figure>и <xref:System.Windows.Documents.Floater> различаются несколькими способами и используются для различных сценариев.

**Figure:**

- Может быть размещено: Можно задать горизонтальную и вертикальную привязки, чтобы закрепить ее относительно страницы, содержимого, столбца или абзаца. Также можно использовать <xref:System.Windows.Documents.Figure.HorizontalOffset%2A> свойства и <xref:System.Windows.Documents.Figure.VerticalOffset%2A> для указания произвольных смещений.

- Имеет размер более чем для одного столбца: Можно задать <xref:System.Windows.Documents.Figure> высоту и ширину для кратности страницы, содержимого или высоты или ширины столбца. Обратите внимание, что в случае страницы и содержимого кратность более 1 не поддерживается. Например, можно задать ширину a <xref:System.Windows.Documents.Figure> равную «0,5 Page» или «0,25» или «2 столбца». Также можно задать высоту и ширину в абсолютных пиксельных значениях.

- Не выполняется разбиение на страницы: Если содержимое внутри <xref:System.Windows.Documents.Figure> не помещается <xref:System.Windows.Documents.Figure>в, будет отображаться любое содержимое, а оставшееся содержимое будет потеряно.

**Floater:**

- Невозможно указать местоположение, отрисовывается в любом доступном пространстве. Нельзя задать смещение или привязку a <xref:System.Windows.Documents.Floater>.

- Не может иметь размер более чем для одного столбца: По умолчанию <xref:System.Windows.Documents.Floater> размеры находятся в одном столбце. Он имеет <xref:System.Windows.Documents.Floater.Width%2A> свойство, которому можно присвоить абсолютное значение в пикселях, но если это значение больше, чем одна ширина столбца, оно игнорируется, а размер плавающего объекта изменяется на один столбец. Его можно сделать менее чем одним столбцом, установив правильную ширину в пикселях, но при этом размер не должен относиться к столбцам, поэтому "0,5 Column" <xref:System.Windows.Documents.Floater> не является допустимым выражением для ширины. <xref:System.Windows.Documents.Floater>не имеет свойства высоты и не может быть задана высота, ее высота зависит от содержимого

- <xref:System.Windows.Documents.Floater>разбиение Если его содержимое с заданной шириной превышает 1 высоту столбца, плавающий элемент прерывает и разбиение к следующему столбцу, следующей странице и т. д.

 <xref:System.Windows.Documents.Figure>является хорошим местом для размещения автономного содержимого, в котором требуется управлять размером и положением, и уверенным в том, что содержимое будет помещаться в указанный размер. <xref:System.Windows.Documents.Floater>— хорошее место для размещения более свободного содержимого, которое напоминает содержимое главной страницы, но отделяется от него.

**LineBreak**

<xref:System.Windows.Documents.LineBreak>вызывает разрыв строки в содержимом нефиксированного формата. В следующем примере показано использование функции <xref:System.Windows.Documents.LineBreak>.

[!code-xaml[FlowOvwSnippets_snip#LineBreakExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]

На следующем снимке экрана показана отрисовка этого примера.

![Снимок экрана LineBreak,]пример(./media/flow-ovw-linebreakexample.png "Flow_Ovw_LineBreakExample")

### <a name="flow-collection-elements"></a>Элементы коллекции нефиксированного формата

Во многих примерах, приведенных выше <xref:System.Windows.Documents.BlockCollection> , <xref:System.Windows.Documents.InlineCollection> и используются для создания содержимого нефиксированного формата программным образом. Например, чтобы добавить элементы в <xref:System.Windows.Documents.Paragraph>, можно использовать синтаксис:

```csharp
myParagraph.Inlines.Add(new Run("Some text"));
```

При этом добавляется <xref:System.Windows.Documents.Run> <xref:System.Windows.Documents.InlineCollection> в коллекцию <xref:System.Windows.Documents.Paragraph>.  Это аналогично неявному <xref:System.Windows.Documents.Run> обнаружению <xref:System.Windows.Documents.Paragraph> в разметке:

```xml
<Paragraph>
Some Text
</Paragraph>
```

В качестве примера использования <xref:System.Windows.Documents.BlockCollection>, приведенный ниже пример создает новый <xref:System.Windows.Documents.Section> объект, а затем использует <xref:System.Windows.Documents.Section> метод **Add** , чтобы добавить новый <xref:System.Windows.Documents.Paragraph> объект к содержимому.

[!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
[!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]

Помимо добавления элементов в коллекцию нефиксированного формата элементы также можно удалять.  В следующем примере удаляется последний <xref:System.Windows.Documents.Inline> элемент <xref:System.Windows.Documents.Span>в.

[!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
[!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]

В следующем примере удаляется все содержимое (<xref:System.Windows.Documents.Inline> элементы) <xref:System.Windows.Documents.Span>из.

[!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
[!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]

При работе с содержимым нефиксированного формата программными средствами эти коллекции, скорее всего, будут использоваться довольно активно.

Использует <xref:System.Windows.Documents.InlineCollection> ли элемент Flow (Inlines) или <xref:System.Windows.Documents.BlockCollection> (Blocks) для хранения своих дочерних элементов, зависит от того, какой тип дочерних элементов (<xref:System.Windows.Documents.Block> или <xref:System.Windows.Documents.Inline>) может содержаться в родительском элементе. Правила включения для элементов размещения содержимого обобщаются в схеме содержимого в следующем разделе.

> [!NOTE]
> Существует третий тип коллекции, используемый с содержимым <xref:System.Windows.Documents.ListItemCollection>нефиксированного формата, но эта коллекция используется только <xref:System.Windows.Documents.List>с. Кроме того, существует несколько коллекций, используемых с <xref:System.Windows.Documents.Table>. Дополнительные сведения см. в разделе [Общие сведения о таблице](table-overview.md) .

<a name="content_schema"></a>

## <a name="content-schema"></a>Схема содержимого

Учитывая количество различных элементов в документах нефиксированного формата, может быть очень сложно отследить, какой тип дочерних элементов может содержать тот или иной элемент. На схеме ниже представлены правила включения для элементов нефиксированного формата. Стрелки указывают возможные связи "родитель-потомок".

![Схема: Схема]вложения содержимого Flow(./media/flow-content-schema.png "Flow_Content_Schema")

Как видно из приведенной выше схемы, дочерние элементы, разрешенные для элемента, не обязательно определяются тем, <xref:System.Windows.Documents.Block> является ли он <xref:System.Windows.Documents.Inline> элементом или элементом. Например <xref:System.Windows.Documents.Span> , <xref:System.Windows.Documents.Inline> элемент (element) может <xref:System.Windows.Documents.Figure> иметь <xref:System.Windows.Documents.Inline> только дочерние элементы, тогда как (также <xref:System.Windows.Documents.Inline> элемент) может иметь <xref:System.Windows.Documents.Block> только дочерние элементы. Таким образом, схему можно использовать для быстрого определения элемента, который может содержаться в другом элементе. В качестве примера рассмотрим схему, чтобы определить, как создать содержимое <xref:System.Windows.Controls.RichTextBox>нефиксированного формата.

**1.** Объект должен содержать, который, в свою очередь, <xref:System.Windows.Documents.Block>должен содержать объект, производный от. <xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.Controls.RichTextBox> Ниже приведен соответствующий сегмент из предыдущей диаграммы.

![Схема: Правила]включения RichTextBox(./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")

Разметка может выглядеть следующим образом.

[!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]

**2.** В соответствии с диаграммой существует несколько <xref:System.Windows.Documents.Block> элементов, из которых можно выбирать, включая <xref:System.Windows.Documents.Table> <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.List>,, <xref:System.Windows.Documents.BlockUIContainer> и (см. раздел классы, <xref:System.Windows.Documents.Section>производные от блока выше). Предположим, <xref:System.Windows.Documents.Table>нам нужно. <xref:System.Windows.Documents.Table> В соответствии с приведенной выше схемой <xref:System.Windows.Documents.TableRowGroup> содержит <xref:System.Windows.Documents.TableRow> <xref:System.Windows.Documents.Block>элементы, содержащие элементы, <xref:System.Windows.Documents.TableCell> которые содержат объект, производный от. Ниже приведен соответствующий сегмент <xref:System.Windows.Documents.Table> , взятый из диаграммы выше.

![Схема: Схема&#47;родительского дочернего]элемента для таблицы(./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")

Ниже приводится соответствующая разметка.

[!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]

**3.** Опять же, один или <xref:System.Windows.Documents.Block> несколько элементов должны находиться <xref:System.Windows.Documents.TableCell>под. Для удобства поместим часть текста в ячейку. Это можно сделать с помощью <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Documents.Run> элемента. Ниже приводятся соответствующие сегменты из схемы, показывающие <xref:System.Windows.Documents.Paragraph> , что может <xref:System.Windows.Documents.Inline> принимать элемент <xref:System.Windows.Documents.Inline> и что <xref:System.Windows.Documents.Run> (элемент) может принимать только обычный текст.

![Схема: Схема&#47;родительского дочернего]элемента для(./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3") абзаца

![Схема: Схема&#47;родительского дочернего]элемента для запуска(./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")

Ниже приведен полный пример в виде разметки.

[!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]

<a name="customizing_text"></a>

## <a name="customizing-text"></a>Настройка текста

Обычно текст является наиболее распространенным типом содержимого в документе нефиксированного формата. Хотя представленные выше объекты могут использоваться для управления большинством аспектов отображения текста, существуют и другие методы для настройки текста, описанные в этом разделе.

### <a name="text-decorations"></a>Оформление текста

Оформление текста позволяет применять к тексту эффекты подчеркивания, надчеркивания, нижней линии и зачеркивания (см. рисунки ниже). Эти украшения добавляются с помощью <xref:System.Windows.Documents.Inline.TextDecorations%2A> свойства, предоставляемого несколькими объектами, включая <xref:System.Windows.Documents.Inline>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Controls.TextBlock>и <xref:System.Windows.Controls.TextBox>.

В следующем примере показано, как задать свойство <xref:System.Windows.Documents.Paragraph.TextDecorations%2A> объекта <xref:System.Windows.Documents.Paragraph>.

[!code-xaml[InlineSnippets#_Paragraph_TextDecXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]

[!code-csharp[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
[!code-vb[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]

На следующем рисунке показана отрисовка этого примера.

![Снимок экрана Текст с зачеркиванием]по умолчанию(./media/inline-textdec-strike.png "Inline_TextDec_Strike")

На следующих рисунках показано, как выводятся элементы назначений « **линия**», « **Базовая линия**» и « **Подчеркивание** » соответственно.

![Снимок экрана Перелинейка]TextDecorator(./media/inline-textdec-over.png "Inline_TextDec_Over")

![Снимок экрана Воздействие на базовые показатели по]умолчанию для текста(./media/inline-textdec-base.png "Inline_TextDec_Base")

![Снимок экрана Текст с действием]подчеркивания по умолчанию(./media/inline-textdec-under.png "Inline_TextDec_Under")

### <a name="typography"></a>Типографская разметка

<xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.Documents.TextElement> <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBlock>Свойство предоставляется большинством связанных с потоком содержимого, включая,, и. <xref:System.Windows.Documents.TextElement.Typography%2A> Это свойство используется для управления типографскими характеристиками текста (т. е. малыми прописными или строчными буквами, надстрочными и подстрочными символами и т. д.).

В следующем примере показано, как задать <xref:System.Windows.Documents.TextElement.Typography%2A> атрибут, используя <xref:System.Windows.Documents.Paragraph> в качестве элемента example.

[!code-xaml[TextElementSnippets#_TextElement_TypogXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]

На следующем рисунке показана отрисовка этого примера.

![Снимок экрана Текст с измененным]типографским(./media/textelement-typog.png "TextElement_Typogом")

Напротив, на следующем рисунке показано, как отрисовывается аналогичный пример с типографскими характеристиками по умолчанию.

![Снимок экрана Текст с измененным]типографским(./media/textelement-typog-default.png "TextElement_Typog_Defaultом")

В следующем примере показано, как задать <xref:System.Windows.Controls.TextBox.Typography%2A> свойство программным способом.

[!code-csharp[TextElementSnippets#_TextElement_Typog](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
[!code-vb[TextElementSnippets#_TextElement_Typog](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]

Дополнительные сведения о типографском оформлении см. [в разделе типографские в WPF](typography-in-wpf.md) .

## <a name="see-also"></a>См. также

- [Text](optimizing-performance-text.md)
- [Оформление в WPF](typography-in-wpf.md)
- [Разделы практического руководства](flow-content-elements-how-to-topics.md)
- [Общие сведения о модели содержимого TextElement](textelement-content-model-overview.md)
- [Общие сведения о RichTextBox](../controls/richtextbox-overview.md)
- [Документы в WPF](documents-in-wpf.md)
- [Общие сведения о таблицах](table-overview.md)
- [Общие сведения о заметках](annotations-overview.md)
