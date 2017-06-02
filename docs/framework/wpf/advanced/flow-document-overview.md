---
title: "Общие сведения о документе нефиксированного формата | Microsoft Docs"
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
  - "схема содержимого"
  - "документы, документы нефиксированного формата"
  - "элементы растягиваемого содержимого [WPF], документы нефиксированного формата"
  - "документы нефиксированного формата"
ms.assetid: ef236a50-d44f-43c8-ba7c-82b0c733c0b7
caps.latest.revision: 39
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# Общие сведения о документе нефиксированного формата
Документы нефиксированного формата разработаны для оптимизации просмотра и удобства чтения.  Документы нефиксированного формата не зависят от предварительно определенного макета, а динамически изменяют и переформатируют свое содержимое на основе переменных времени выполнения \(например, размера окна и разрешения устройства\) и дополнительных пользовательских настроек.  Кроме того, документы нефиксированного формата предоставляют дополнительные возможности, например, разбиение на страницы и столбцы.  В этом разделе представлен обзор документов нефиксированного формата и способов их создания.  
  
   
  
<a name="what_is_a_flow_document"></a>   
## Что такое документ нефиксированного формата  
 Документ нефиксированного формата предназначен для «переформатирования содержимого» в зависимости от размера окна, разрешения устройства и других переменных среды.  Кроме того, документы нефиксированного формата имеют множество встроенных возможностей, включая поиск, просмотр режимов оптимизации удобочитаемости и возможность изменения размера и вида шрифтов.  Документы нефиксированного формата лучше всего подходят для тех случаев, когда удобочитаемость является определяющей при использовании документа.  Форматы фиксированного документа, напротив, разработаны для статического представления.  Форматы фиксированного документа полезны в тех случаях, когда важна точность содержимого источника.  Дополнительные сведения о различных типах документов см. в разделе [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
 Ниже показан образец документа нефиксированного формата, отображенного в нескольких окнах различных размеров.  При изменении области отображения содержимое переформатируется, чтобы обеспечить наилучшее использование доступного места.  
  
 ![Повторный поток содержимого документа нефиксированного формата](../../../../docs/framework/wpf/advanced/media/edocs-flowdocument.png "eDocs\_FlowDocument")  
  
 Как показано на рисунке выше, содержимое нефиксированного формата может включать многие компоненты, в том числе абзацы, списки, изображения и др.  Эти компоненты соответствуют элементам в разметке и объектам в процедуре кода.  Подробнее эти классы будут рассмотрены далее в разделе [Классы, связанные с нефиксированным форматом](#flow_related_classes) этого обзора.  Здесь представлен простой пример кода, который создает документ нефиксированного формата, состоящий из абзаца с жирным текстом и списка.  
  
 [!code-xml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]  
  
 На рисунке ниже показан этот фрагмент кода.  
  
 ![Снимок экрана: пример отображенного документа нефиксированного формата](../../../../docs/framework/wpf/advanced/media/flow-ovw-first-example.png "Flow\_Ovw\_First\_Example")  
  
 В этом примере элемент управления <xref:System.Windows.Controls.FlowDocumentReader> используется для размещения содержимого нефиксированного формата.  См. раздел [Типы документов нефиксированного формата](#flow_document_types) для получения дополнительных сведений об элементах управления, размещающих поточное содержимое.  Элементы <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem> и <xref:System.Windows.Documents.Bold> используются для управления форматированием содержимого в зависимости от их порядка в разметке.  Например, элемент <xref:System.Windows.Documents.Bold> охватывает только часть текста в абзаце; в результате только эта часть текста будет выделена жирным шрифтом.  Пользователям HTML это поведение будет знакомо.  
  
 Как показано на рисунке выше, документы нефиксированного формата имеют несколько встроенных возможностей:  
  
-   Поиск: позволяет пользователю выполнять полнотекстовый поиск по всему документу.  
  
-   Режим просмотра: пользователь может выбрать для себя предпочтительный режим просмотра, например постраничный режим просмотра \(просмотр страницы целиком\), двустраничный режим просмотра \(книжный формат\) и режим просмотра с непрерывной прокруткой \(«без дна»\).  Дополнительные сведения об этих режимах просмотра содержатся в разделе <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  
  
-   Элементы управления постраничной навигации: если режим просмотра документа использует страницы, то элементы управления навигацией по страницам содержат кнопку для перехода к следующей странице \(стрелка вниз\) или к предыдущей странице \(стрелка вверх\), а также индикаторы текущего номера страницы и общего количества страниц.  Пролистывание страниц также может быть выполнено с помощью клавиш со стрелками на клавиатуре.  
  
-   Увеличение: элементы управления масштабом позволяют пользователю увеличить или уменьшить масштаб, щелкнув кнопки со знаками «плюс» или «минус» соответственно.  Элементы управления масштабом также включают ползунок для изменения масштаба.  Дополнительные сведения см. в разделе <xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>.  
  
 Эти возможности могут быть в зависимости от элемента управления, используемого для размещения содержимого нефиксированного формата.  В следующем разделе описаны различные элементы управления.  
  
<a name="flow_document_types"></a>   
## Типы документов нефиксированного формата  
 Отображение содержимого документа нефиксированного формата и его вид зависят от того, какой объект используется для размещения содержимого нефиксированного формата.  Существуют четыре элемента управления, поддерживающие просмотр содержимого нефиксированного формата: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.RichTextBox> и <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  Эти элементы управления кратко описаны ниже.  
  
 **Обратите внимание:** для непосредственного размещения содержимого нефиксированного формата необходим <xref:System.Windows.Documents.FlowDocument>. Таким образом, все эти элементы управления просмотром используют <xref:System.Windows.Documents.FlowDocument> для размещения содержимого нефиксированного формата.  
  
### Элемент управления FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> включает возможности, позволяющие пользователю динамически выбирать различные режимы просмотра, включая одностраничный \(постраничный\), двухстраничный \(книжный формат\) и режим просмотра непрерывной прокрутки \(«без дна»\).  Дополнительные сведения об этих режимах просмотра содержатся в разделе <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  Если динамическое переключение между режимами просмотра не требуется, элементы управления <xref:System.Windows.Controls.FlowDocumentPageViewer> и <xref:System.Windows.Controls.FlowDocumentScrollViewer> предоставляют облегченные средства просмотра содержимого документа нефиксированного формата, закрепленные для определенного режима просмотра.  
  
### FlowDocumentPageViewer и FlowDocumentScrollViewer  
 Элемент управления <xref:System.Windows.Controls.FlowDocumentPageViewer> отображает содержимое в режиме постраничного просмотра, а <xref:System.Windows.Controls.FlowDocumentScrollViewer> отображает содержимое в режиме непрерывной прокрутки.  Оба элемента управления <xref:System.Windows.Controls.FlowDocumentPageViewer> и <xref:System.Windows.Controls.FlowDocumentScrollViewer> предназначены только для конкретного режима просмотра.  Это отличает их от элемента управления <xref:System.Windows.Controls.FlowDocumentReader>, который включает в себя возможности, позволяющие пользователю динамически выбирать различные режимы просмотра \(представленные перечислением <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>\), что делает его более ресурсоемким, чем элементы управления <xref:System.Windows.Controls.FlowDocumentPageViewer> или <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 По умолчанию вертикальная полоса прокрутки отображается всегда, а горизонтальная становится видимой при необходимости.  Пользовательский интерфейс по умолчанию для объекта <xref:System.Windows.Controls.FlowDocumentScrollViewer> не содержит панели инструментов, но для включения встроенной панели инструментов можно использовать свойство <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A>.  
  
### RichTextBox  
 Если необходимо разрешить пользователю изменять содержимое нефиксированного формата, используйте <xref:System.Windows.Controls.RichTextBox>.  Например, чтобы создать редактор, который позволял бы пользователю манипулировать такими элементами, как таблицы, форматирование курсива и жирного шрифта и т.д,, следует использовать <xref:System.Windows.Controls.RichTextBox>.  Дополнительные сведения см. в разделе [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md).  
  
 **Примечание** Содержимое потока внутри <xref:System.Windows.Controls.RichTextBox> ведет себя не так, как содержимое потока, имеющееся в других элементах управления.  Например, в <xref:System.Windows.Controls.RichTextBox> нет столбцов и, следовательно, нет автоматического изменения размеров.  Кроме того, в <xref:System.Windows.Controls.RichTextBox> недоступны обычные встроенные возможности поточного содержимого, например поиск, режим просмотра, навигация по страницам и увеличение.  
  
<a name="creating_flow_content"></a>   
## Создание содержимого нефиксированного формата  
 Содержимое нефиксированного формата может быть сложным, т.е. состоящим из различных элементов, включая текст, изображения, таблицы и даже <xref:System.Windows.UIElement> производных классов \(например, элементов управления\).  Чтобы понять, как создать сложное поточное содержимое, важно понимать следующее:  
  
-   **Классы, связанные с нефиксированным форматом**: каждый класс, используемый в содержимом нефиксированного формата, имеет особое назначение.  Кроме того, иерархическая связь между классами нефиксированного формата помогает понять, как они используются.  Например, классы, производные от класса <xref:System.Windows.Documents.Block>, используются для размещения других объектов, а классы, производные от <xref:System.Windows.Documents.Inline>, содержат отображаемые объекты.  
  
-   **Схема содержимого**: документ нефиксированного формата может потребовать значительное число вложенных элементов.  Схема содержимого указывает возможные связи «родитель\/потомок» между элементами.  
  
 В следующих разделах каждый из этих пунктов будет рассмотрена более подробно.  
  
<a name="flow_related_classes"></a>   
## Классы, связанные с нефиксированным форматом  
 Представленная ниже диаграмма показывает объекты, чаще всего использующиеся вместе с содержимым нефиксированного формата:  
  
 ![Схема: иерархия класса элемента потока содержимого](../../../../docs/framework/wpf/advanced/media/flow-class-hierarchy.png "Flow\_Class\_Hierarchy")  
  
 Для содержимого нефиксированного формата существуют две важные категории:  
  
1.  **Классы, производные от блока**: также называющиеся «элементы блок\-содержимого» или просто «блок\-элементы».  Элементы, которые наследуются от <xref:System.Windows.Documents.Block>, можно использовать для группировки элементов по общему родителю или для применения к группе общих атрибутов.  
  
2.  **Классы, производные от встроенных элементов**: также называющиеся «элементы встроенного содержимого» или просто «встроенные элементы».  Элементы, которые наследуются от <xref:System.Windows.Documents.Inline>, содержатся в блок\-элементе или в другом встроенном элементе.  Встроенные элементы часто используются в качестве непосредственного контейнера содержимого, отображаемого на экране.  Например, <xref:System.Windows.Documents.Paragraph> \(блок\-элемент\) может содержать <xref:System.Windows.Documents.Run> \(встроенный элемент\), но <xref:System.Windows.Documents.Run> фактически содержит текст, отображаемый на экране.  
  
 Ниже кратко описан каждый класс этих категорий.  
  
### Классы, производные от блоков  
 **Paragraph**  
  
 <xref:System.Windows.Documents.Paragraph> обычно используется для группировки содержимого в абзаце.  Чаще всего Paragraph используется для создания абзаца текста.  
  
 [!code-xml[FlowOvwSnippets_snip#ParagraphExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]  
  
 Тем не менее, здесь можно включить и другие встроенные элементы, как будет показано ниже.  
  
 **Раздел**  
  
 <xref:System.Windows.Documents.Section> используется только для размещения других элементов, производных от <xref:System.Windows.Documents.Block>.  Не применяет никакого форматирования по умолчанию к содержащимся в нем элементам.  В то же время, любые значения свойства, установленные на <xref:System.Windows.Documents.Section>, применяются к его дочерним элементам.  Раздел также позволяет программно перебирать свою дочернюю коллекцию.  Элемент <xref:System.Windows.Documents.Section> используется таким же образом, как тег \<DIV\> в HTML.  
  
 В приведенном ниже примере три абзаца определяются под одним <xref:System.Windows.Documents.Section>.  Значение свойства <xref:System.Windows.Documents.TextElement.Background%2A> раздела равно Red, поэтому цвет фона абзаца тоже красный.  
  
 [!code-xml[FlowOvwSnippets_snip#SectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]  
  
 **BlockUIContainer**  
  
 Элемент <xref:System.Windows.Documents.BlockUIContainer> позволяет элементам <xref:System.Windows.UIElement> \(например,  элементам <xref:System.Windows.Controls.Button>\) встраиваться в блочное потоковое содержимое.  Элемент <xref:System.Windows.Documents.InlineUIContainer> \(см. ниже\) используется для внедрения элементов <xref:System.Windows.UIElement> во встроенное поточное содержимое.  Элементы <xref:System.Windows.Documents.BlockUIContainer> и <xref:System.Windows.Documents.InlineUIContainer> важны, поскольку использовать элемент <xref:System.Windows.UIElement> в потоке содержимого можно, только заключив его в один из двух этих элементов.  
  
 В следующем примере показано использование элемента <xref:System.Windows.Documents.BlockUIContainer> для размещения объектов <xref:System.Windows.UIElement> в содержимом нефиксированного формата.  
  
 [!code-xml[SpanSnippets#_BlockUIXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]  
  
 На следующем рисунке показан результат выполнения этого примера.  
  
 ![Снимок экрана: UIElement вставленный в поток содержимого](../../../../docs/framework/wpf/advanced/media/blockuicontainer.png "BlockUIContainer")  
  
 **List**  
  
 <xref:System.Windows.Documents.List> используется для создания маркированного или нумерованного списка.  Задайте свойству <xref:System.Windows.Documents.List.MarkerStyle%2A> значение перечисления <xref:System.Windows.TextMarkerStyle> для определения стиля в списке.  Следующий пример показывает, как создать простой список.  
  
 [!code-xml[FlowOvwSnippets_snip#ListExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]  
  
 **Обратите внимание:** <xref:System.Windows.Documents.List> является единственным элементом нефиксированного формата, использующим <xref:System.Windows.Documents.ListItemCollection> для управления дочерними элементами.  
  
 **Таблица**  
  
 Элемент <xref:System.Windows.Documents.Table> используется для создания таблицы.  Элемент <xref:System.Windows.Documents.Table> аналогичен элементу <xref:System.Windows.Controls.Grid>, однако имеет больше возможностей и, таким образом, требует больших ресурсов.  Поскольку <xref:System.Windows.Controls.Grid> является <xref:System.Windows.UIElement>, то он не может использоваться в содержимом нефиксированного формата за исключением того случая, когда он содержится в <xref:System.Windows.Documents.BlockUIContainer> или <xref:System.Windows.Documents.InlineUIContainer>.  Дополнительные сведения о <xref:System.Windows.Documents.Table> см. в разделе [Общие сведения о таблицах](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
### Классы, производные от встроенных  
 **Запуск**  
  
 <xref:System.Windows.Documents.Run> используется для хранения неформатированного текста.  Объекты <xref:System.Windows.Documents.Run> обычно интенсивно используются в нефиксированном содержимом.  Впрочем, в разметке не требуется явное использование элементов <xref:System.Windows.Documents.Run>.  При создании документов нефиксированного формата и управлении ими с помощью кода необходимо использовать класс <xref:System.Windows.Documents.Run>.  Например, в приведенной ниже разметке первый <xref:System.Windows.Documents.Paragraph> в явном виде задает элемент <xref:System.Windows.Documents.Run>, а второй — не задает его.  Оба абзаца создают идентичные выходные данные.  
  
 [!code-xml[FlowOvwSnippets_snip#RunExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]  
  
 **Примечание.** В [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] и более новых версиях свойство <xref:System.Windows.Documents.Run.Text%2A> объекта <xref:System.Windows.Documents.Run> является свойством зависимости.  Свойство <xref:System.Windows.Documents.Run.Text%2A> можно привязать к источнику данных, такому как <xref:System.Windows.Controls.TextBlock>.  Свойство <xref:System.Windows.Documents.Run.Text%2A> полностью поддерживает одностороннюю привязку.  Свойство <xref:System.Windows.Documents.Run.Text%2A> также поддерживает двустороннюю привязку, за исключением <xref:System.Windows.Controls.RichTextBox>.  Пример см. в разделе <xref:System.Windows.Documents.Run.Text%2A?displayProperty=fullName>.  
  
 **Span**  
  
 <xref:System.Windows.Documents.Span> группирует друг с другом другие элементы встроенного содержимого.  К содержимому в элементе <xref:System.Windows.Documents.Span> не применяется никакая обязательная отрисовка.  В то же время, элементы, которые наследуются от <xref:System.Windows.Documents.Span> \(включая <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Italic> и <xref:System.Windows.Documents.Underline>\), применяют форматирование к тексту.  
  
 Ниже приведен пример использования <xref:System.Windows.Documents.Span> для хранения встроенного содержимого, в том числе текста, элемента <xref:System.Windows.Documents.Bold> и <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[FlowOvwSnippets_snip#SpanExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]  
  
 На следующем рисунке показан результат отображения этого примера.  
  
 ![Снимок экрана: пример отображенного элемента Span](../../../../docs/framework/wpf/advanced/media/flow-spanexample.png "Flow\_SpanExample")  
  
 **InlineUIContainer**  
  
 Элемент <xref:System.Windows.Documents.InlineUIContainer> позволяет <xref:System.Windows.UIElement> элементам \(например,  элементу управления <xref:System.Windows.Controls.Button>\) внедряться в элемент содержимого <xref:System.Windows.Documents.Inline>.  Этот элемент является встроенным эквивалентом описанного выше <xref:System.Windows.Documents.BlockUIContainer>.  Ниже приведен пример, который использует <xref:System.Windows.Documents.InlineUIContainer> для вставки встроенных <xref:System.Windows.Controls.Button> в <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]  
  
 **Обратите внимание**: в разметке не требуется в явном виде использовать <xref:System.Windows.Documents.InlineUIContainer>.  Если им пренебречь, то при компиляции кода в любом случае будет создан <xref:System.Windows.Documents.InlineUIContainer>.  
  
 **Figure и Floater**  
  
 Элементы <xref:System.Windows.Documents.Figure> и <xref:System.Windows.Documents.Floater> используются для внедрения содержимого в документ нефиксированного формата; при этом свойства размещения могут быть настроены независимо от основного потока содержимого.  Элементы <xref:System.Windows.Documents.Figure> или <xref:System.Windows.Documents.Floater> часто используются для выделения или подчеркивания частей содержимого, для размещения сопровождающих изображений или другого содержимого в рамках основного потока или для добавления не связанного с основным документом содержимого, например рекламы.  
  
 Следующий пример показывает, как внедрить <xref:System.Windows.Documents.Figure> в абзац текста.  
  
 [!code-xml[FlowOvwSnippets_snip#FigureExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]  
  
 Следующий рисунок показывает результат отображения этого примера.  
  
 ![Снимок экрана: пример фигуры](../../../../docs/framework/wpf/advanced/media/flow-ovw-figure-example.png "Flow\_Ovw\_Figure\_Example")  
  
 <xref:System.Windows.Documents.Figure> и <xref:System.Windows.Documents.Floater> немного отличаются и используются для различных скриптов.  
  
 **Figure:**  
  
-   Для элемента можно определить местоположение. Для закрепления относительно страницы, содержимого, столбца или абзаца можно задать горизонтальные и вертикальные точки привязки.  Также для указания произвольного смещения можно использовать его свойства <xref:System.Windows.Documents.Figure.HorizontalOffset%2A> и <xref:System.Windows.Documents.Figure.VerticalOffset%2A>.  
  
-   Элемент можно разместить в нескольких столбцах. Можно установить высоту и ширину <xref:System.Windows.Documents.Figure> в значения, кратные странице, содержимому, высоте или ширине столбца.  Обратите внимание, что в случае страницы и содержимого, кратности больше 1 не допускаются.  Например, можно установить значение ширины <xref:System.Windows.Documents.Figure> равным «0.5 страницы», «0.25 содержимого» или «2 столбца».  Значения высоты и ширины также можно установить в абсолютных пиксельных значениях.  
  
-   Элемент не разбивается постранично. Если содержимое в <xref:System.Windows.Documents.Figure> не помещается внутри <xref:System.Windows.Documents.Figure>, будет отображаться все поместившееся содержимое, а не помещающаяся часть будет утеряна  
  
 **Floater:**  
  
-   Для элемента невозможно определить местоположение, и он будет отображаться в любом доступном для него месте.  Задать смещение или значение привязки <xref:System.Windows.Documents.Floater> невозможно.  
  
-   Не может изменяться по размеру до размера большего, чем один столбец. По умолчанию <xref:System.Windows.Documents.Floater> имеет размер, равный одному столбцу.  Свойство элемента <xref:System.Windows.Documents.Floater.Width%2A> может быть задано в абсолютных пикселях, но в случае если это значение превышает ширину одного столбца, оно будет игнорироваться, а размеры плавающего объекта изменятся до размера одного столбца.  Можно сделать его уже, чем один столбец, задав правильную ширину в пикселях, но нельзя задать ширину относительно ширины столбца; "0.5 столбца" — неправильное значение ширины элемента <xref:System.Windows.Documents.Floater>.  Элемент <xref:System.Windows.Documents.Floater> лишен свойства высоты; его высота не может быть указана, она зависит от содержимого.  
  
-   <xref:System.Windows.Documents.Floater> переносится постранично. Если его содержимое в заданной ширине расширяется на более чем 1 высоту столбца, плавающий объект прерывается и переходит в следующий столбец, страницу и т.д.  
  
 Элемент <xref:System.Windows.Documents.Figure> хорошо подходит для размещения обособленного содержимого, если необходимо контролировать его размер и размещение, и можно быть уверенным в том, что он поместится в заданные размеры.  Элемент <xref:System.Windows.Documents.Floater> больше подходит для размещения более свободного содержимого, расположенного подобно содержимому основной страницы, но отделенного от него.  
  
 **LineBreak**  
  
 <xref:System.Windows.Documents.LineBreak> вызывает разрыв строки в содержимом нефиксированного формата.  В следующем примере показано использование <xref:System.Windows.Documents.LineBreak>.  
  
 [!code-xml[FlowOvwSnippets_snip#LineBreakExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]  
  
 На следующем рисунке показан результат отображения этого примера.  
  
 ![Снимок экрана: пример LineBreak](../../../../docs/framework/wpf/advanced/media/flow-ovw-linebreakexample.png "Flow\_Ovw\_LineBreakExample")  
  
### Элементы коллекции нефиксированного формата  
 В большинстве приведенных выше примеров <xref:System.Windows.Documents.BlockCollection> и <xref:System.Windows.Documents.InlineCollection> используются для построения содержимого нефиксированного формата программными средствами.  Например, чтобы добавить элементы в <xref:System.Windows.Documents.Paragraph>, можно использовать следующий синтаксис:  
  
 `…`  
  
 `myParagraph.Inlines.Add(new Run("Some text"));`  
  
 `…`  
  
 Это добавляет <xref:System.Windows.Documents.Run> в <xref:System.Windows.Documents.InlineCollection> абзаца <xref:System.Windows.Documents.Paragraph>.  Этот пример совпадает со случаем, когда в разметке найден неявный <xref:System.Windows.Documents.Run> внутри <xref:System.Windows.Documents.Paragraph>:  
  
 `…`  
  
 `<Paragraph>`  
  
 `Some Text`  
  
 `</Paragraph>`  
  
 `…`  
  
 В качестве примера использования <xref:System.Windows.Documents.BlockCollection>, в следующем примере создается новый <xref:System.Windows.Documents.Section>. Затем метод **Add** используется для добавления нового <xref:System.Windows.Documents.Paragraph> в содержимое <xref:System.Windows.Documents.Section>.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
 Помимо добавления элементов в коллекцию нефиксированного формата, элементы из нее можно также удалять.  В следующем примере удаляется последний элемент <xref:System.Windows.Documents.Inline> в объекте <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 В следующем примере удаляется все содержимое \(элементы <xref:System.Windows.Documents.Inline>\) из объекта <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
 При работе с содержимым нефиксированного формата программными средствами эти коллекции будут постоянно использоваться.  
  
 Использование элементом нефиксированного формата <xref:System.Windows.Documents.InlineCollection> \(встроенных элементов\) или <xref:System.Windows.Documents.BlockCollection> \(блоков\) для хранения своих дочерних элементов зависит от того, какой тип дочерних элементов могут содержать родители \(<xref:System.Windows.Documents.Block> или <xref:System.Windows.Documents.Inline>\).  Правила включения для элементов содержимого нефиксированного формата приводятся в схеме содержимого в следующем разделе.  
  
 **Обратите внимание**: существует третий тип коллекции, используемый с содержимым нефиксированного формата — <xref:System.Windows.Documents.ListItemCollection>. Эта коллекция используется только с <xref:System.Windows.Documents.List>.  Кроме того, существует несколько коллекций, используемых с <xref:System.Windows.Documents.Table>.  Дополнительные сведения см. в разделе [Общие сведения о таблицах](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
<a name="content_schema"></a>   
## Схема содержимого  
 Учитывая число различных элементов содержимого нефиксированного формата, отслеживание того, какие типы дочерних элементов может содержать элемент, может быть достаточно сложной задачей.  На схеме ниже представлены правила включения для элементов нефиксированного формата.  Стрелки показывают возможные связи «родитель\/потомок».  
  
 ![Схема: схема вместимости потока содержимого](../../../../docs/framework/wpf/advanced/media/flow-content-schema.png "Flow\_Content\_Schema")  
  
 Как видно из диаграммы выше, потомки для элемента не обязательно определяются элементами <xref:System.Windows.Documents.Block> или <xref:System.Windows.Documents.Inline>.  Например, <xref:System.Windows.Documents.Span> \(элемент <xref:System.Windows.Documents.Inline>\) может иметь только дочерние элементы <xref:System.Windows.Documents.Inline>, в то время как <xref:System.Windows.Documents.Figure> \(также элемент <xref:System.Windows.Documents.Inline>\) может иметь только дочерние элементы <xref:System.Windows.Documents.Block>.  Таким образом, диаграмма может служить для быстрого определения элемента, который может содержаться в другом элементе.  Для примера используем диаграмму, чтобы определить, как создать содержимое нефиксированного формата <xref:System.Windows.Controls.RichTextBox>.  
  
 **1.** Объект <xref:System.Windows.Controls.RichTextBox> должен содержать <xref:System.Windows.Documents.FlowDocument>, который в свою очередь должен содержать объект, производный от <xref:System.Windows.Documents.Block>.  Ниже приведен соответствующий сегмент из схемы.  
  
 ![Схема: правила вместимости RichTextBox](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough1.png "Flow\_Ovw\_SchemaWalkThrough1")  
  
 Разметка может выглядеть следующим образом:  
  
 [!code-xml[FlowOvwSnippets_snip#SchemaWalkThrough1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
 **2.** В соответствии с диаграммой существует несколько элементов класса <xref:System.Windows.Documents.Block> для выбора, в том числе: <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List> и <xref:System.Windows.Documents.BlockUIContainer> \(см. выше классы, производные от блока\).  Предположим, нам требуется <xref:System.Windows.Documents.Table>.  В соответствии с предыдущей диаграммой, <xref:System.Windows.Documents.Table> содержит <xref:System.Windows.Documents.TableRowGroup>, которая содержит элементы <xref:System.Windows.Documents.TableRow>, которые в свою очередь содержат элементы, содержащие объект, производный от <xref:System.Windows.Documents.TableCell> <xref:System.Windows.Documents.Block>.  Ниже приводится соответствующий сегмент для <xref:System.Windows.Documents.Table>, взятый из предыдущей диаграммы.  
  
 ![Схема: схема родительский&#47;дочерний элементы для таблицы](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough2.png "Flow\_Ovw\_SchemaWalkThrough2")  
  
 Ниже приведена соответствующая разметка.  
  
 [!code-xml[FlowOvwSnippets_snip#SchemaWalkThrough2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
 **3.** Предположим, что для <xref:System.Windows.Documents.TableCell> снова требуется один или несколько элементов <xref:System.Windows.Documents.Block>.   Для удобства поместим часть текста в ячейку.  Это можно сделать, используя <xref:System.Windows.Documents.Paragraph> с элементом <xref:System.Windows.Documents.Run>.  Ниже приводится соответствующий сегмент из диаграммы, показывающий, что <xref:System.Windows.Documents.Paragraph> может принять элемент <xref:System.Windows.Documents.Inline>, а также что <xref:System.Windows.Documents.Run> \(элемент <xref:System.Windows.Documents.Inline>\) может принять только обычный текст.  
  
 ![Схема: схема родительский&#47;дочерний элементы для параграфа](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough3.png "Flow\_Ovw\_SchemaWalkThrough3")  
  
 ![Схема: схема родительский&#47;дочерний элементы для запуска](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough4.png "Flow\_Ovw\_SchemaWalkThrough4")  
  
 Ниже в разметке приведен полный пример.  
  
 [!code-xml[FlowOvwSnippets_snip#SchemaExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="customizing_text"></a>   
## Настройка текста  
 Обычно текст является наиболее распространенным типом содержимого в документе нефиксированного формата.  Хотя представленные выше объекты могут использоваться для управления большинством аспектов отображения текста, существуют и другие методы для настройки текста, рассматривающегося в этом разделе.  
  
### Оформление текста  
 Оформление текста позволяет применять к тексту эффекты подчеркивания, надчеркивания, базового плана и зачеркивания \(см. рисунки ниже\).  Эти эффекты оформления добавляются с помощью свойства <xref:System.Windows.Documents.Inline.TextDecorations%2A>, которое отображается числом объектов, включающих <xref:System.Windows.Documents.Inline>, <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Controls.TextBox>.  
  
 В следующем примере показано, как задать свойство <xref:System.Windows.Documents.Paragraph.TextDecorations%2A> абзаца <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xml[InlineSnippets#_Paragraph_TextDecXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]  
  
 [!code-csharp[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
 [!code-vb[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]  
  
 На следующем рисунке показан результат выполнения этого примера.  
  
 ![Снимок экрана: текст с эффектом зачеркивания по умолчанию](../../../../docs/framework/wpf/advanced/media/inline-textdec-strike.png "Inline\_TextDec\_Strike")  
  
 Следующие иллюстрации показывают отображения эффектов оформления **Overline**, **Baseline** и **Underline** соответственно.  
  
 ![Снимок экрана: надстрочный TextDecorator](../../../../docs/framework/wpf/advanced/media/inline-textdec-over.png "Inline\_TextDec\_Over")  
  
 ![Снимок экрана: эффект базового плана для текста по умолчанию](../../../../docs/framework/wpf/advanced/media/inline-textdec-base.png "Inline\_TextDec\_Base")  
  
 ![Снимок экрана: текст с эффектом подчеркивания по умолчанию](../../../../docs/framework/wpf/advanced/media/inline-textdec-under.png "Inline\_TextDec\_Under")  
  
### Типографская разметка  
 Свойство <xref:System.Windows.Documents.TextElement.Typography%2A> предоставляется большей частью содержимого, связанного с нефиксированным форматом, в том числе <xref:System.Windows.Documents.TextElement>, <xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Controls.TextBox>.  Это свойство используется для контроля типографских характеристик текста \(т. е.  прописных или строчных букв, надстрочных и подстрочных символов и т. д.\).  
  
 В следующем примере показано, как установить атрибут <xref:System.Windows.Documents.TextElement.Typography%2A> с помощью <xref:System.Windows.Documents.Paragraph> в качестве элемента примера  
  
 [!code-xml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 На следующем рисунке показан результат выполнения этого примера.  
  
 ![Снимок экрана: текст с измененной типографией](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement\_Typog")  
  
 На следующем рисунке показано выполнение похожего примера с типографическими свойствами по умолчанию.  
  
 ![Снимок экрана: текст с измененной типографией](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement\_Typog\_Default")  
  
 В следующем примере показано, как программно задать свойство <xref:System.Windows.Controls.TextBox.Typography%2A>.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
 Дополнительные сведения о типографской разметке текста см. в разделе [Оформление в WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).  
  
## См. также  
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Оформление в WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)   
 [Практические руководства](../../../../docs/framework/wpf/advanced/flow-content-elements-how-to-topics.md)   
 [Общие сведения о модели содержимого TextElement](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md)   
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Общие сведения о таблицах](../../../../docs/framework/wpf/advanced/table-overview.md)   
 [Общие сведения о заметках](../../../../docs/framework/wpf/advanced/annotations-overview.md)