---
title: "Оптимизация производительности: отображение текста | Microsoft Docs"
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
  - "отрисовка текста"
  - "гиперссылки"
  - "форматированный текст [WPF]"
  - "текст, производительность"
  - "глифы"
ms.assetid: 66b1b9a7-8618-48db-b616-c57ea4327b98
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Оптимизация производительности: отображение текста
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]включает поддержку представления содержимого текста с помощью многофункциональных [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] элементов управления. В целом можно разделить отрисовку текста на три уровня:  
  
1.  С помощью <xref:System.Windows.Documents.Glyphs> и <xref:System.Windows.Media.GlyphRun> объекты непосредственно.  
  
2.  С помощью <xref:System.Windows.Media.FormattedText> объекта.  
  
3.  С помощью элементов управления верхнего уровня, таких как <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Documents.FlowDocument> объектов.  
  
 Этот раздел содержит рекомендации по повышению производительности отрисовки текста.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Glyph_Level"></a>   
## <a name="rendering-text-at-the-glyph-level"></a>Отрисовка текста на уровне глифа  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]обеспечивает поддержку дополнительного текста, включая разметку на уровне глифа с прямым доступом к <xref:System.Windows.Documents.Glyphs> для клиентов, которым требуется перехватывать и сохранять текст после форматирования. Эти функции обеспечивают важную поддержку различных текст требований к отрисовке в каждом из следующих сценариев.  
  
-   Отображение документов в фиксированных форматах.  
  
-   Сценарии печати.  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]как язык принтера.  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)].  
  
    -   Предыдущие драйверы принтера, приведенные из [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] приложения в фиксированный формат.  
  
    -   Формат очереди печати.  
  
-   Представление документов фиксированного формата, включая клиенты предыдущих версий [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] и другие вычислительные устройства.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Glyphs> и <xref:System.Windows.Media.GlyphRun> предназначены для представления документа фиксированного формата и сценариев печати. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]предоставляет несколько элементов для общего макета и [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] сценарии, такие как <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.TextBlock>. Дополнительные сведения о макете и [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] сценарии, в статье [оформление в WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).  
  
 Следующие примеры показывают, как можно задать свойства для <xref:System.Windows.Documents.Glyphs> объекта в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. <xref:System.Windows.Documents.Glyphs> объект представляет выходные данные <xref:System.Windows.Media.GlyphRun> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. В примерах предполагается, что шрифты Arial, Courier New и Times New Roman устанавливаются в **C:\WINDOWS\Fonts** папка на локальном компьютере.  
  
 [!code-xml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
### <a name="using-drawglyphrun"></a>С помощью DrawGlyphRun  
 Если имеется пользовательский элемент управления и требуется отобразить глифы, используйте <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> метод.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]также предоставляет службы более низкого уровня для пользовательского форматирования с помощью текста <xref:System.Windows.Media.FormattedText> объекта. Наиболее эффективный способ отображения текста в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] является создание содержимого текста на уровне глифов с помощью <xref:System.Windows.Documents.Glyphs> и <xref:System.Windows.Media.GlyphRun>. Однако ценой этой эффективности будет потеря удобный формат RTF, поддерживаемого встроенными функциональными возможностями для [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] элементы управления, такие как <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Documents.FlowDocument>.  
  
<a name="FormattedText_Object"></a>   
## <a name="formattedtext-object"></a>Объект FormattedText  
 <xref:System.Windows.Media.FormattedText> объект позволяет рисовать многострочный текст, в котором каждый символ в текст можно форматировать отдельно. Дополнительные сведения см. в разделе [Рисование текста в формате](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md).  
  
 Чтобы создать форматированный текст, вызовите <xref:System.Windows.Media.FormattedText.%23ctor%2A> конструктор для создания <xref:System.Windows.Media.FormattedText> объекта. После создания первоначально отформатированной текстовой строки можно применить весь диапазон стилей форматирования. Если в приложении требуется реализовать собственный макет, то <xref:System.Windows.Media.FormattedText> объект является лучшим выбором, чем при использовании элемента управления, такие как <xref:System.Windows.Controls.TextBlock>. Дополнительные сведения о <xref:System.Windows.Media.FormattedText> объекта см. в разделе [Рисование текста в формате](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md) .  
  
 <xref:System.Windows.Media.FormattedText> объект предоставляет возможность низкоуровневого форматирования текста. Можно применить несколько стилей форматирования к одному или нескольким символам. Например, можно вызвать оба <xref:System.Windows.Media.FormattedText.SetFontSize%2A> и <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> методов, чтобы изменить форматирование первые пять символов в тексте.  
  
 В следующем примере кода создается <xref:System.Windows.Media.FormattedText> объекта и готовит его к просмотру.  
  
 [!code-csharp[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
<a name="FlowDocument_TextBlock_Label"></a>   
## <a name="flowdocument-textblock-and-label-controls"></a>Документ нефиксированного формата, TextBlock и элементы управления Label  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]содержит несколько элементов управления для рисования текста на экране. Каждый элемент управления предназначен для различных сценариев и имеет свой собственный список функций и ограничений.  
  
### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>Документ нефиксированного формата, влияет на производительность более чем TextBlock или метки  
 Как правило <xref:System.Windows.Controls.TextBlock> элемент должен использоваться, если требуется ограниченная поддержка текста, например краткое предложения в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> может использоваться, если необходима Минимальная поддержка текста. <xref:System.Windows.Documents.FlowDocument> элемент является контейнером для повторно форматируемых документов, поддерживающих представление форматированного содержимого и, следовательно, повлиять на производительность больше, чем при использовании <xref:System.Windows.Controls.TextBlock> или <xref:System.Windows.Controls.Label> элементов управления.  
  
 Дополнительные сведения о <xref:System.Windows.Documents.FlowDocument>, в разделе [Общие сведения о документе нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
### <a name="avoid-using-textblock-in-flowdocument"></a>Избегайте использования TextBlock в документ нефиксированного формата  
 <xref:System.Windows.Controls.TextBlock> является производным от <xref:System.Windows.UIElement>. <xref:System.Windows.Documents.Run> является производным от <xref:System.Windows.Documents.TextElement>, который является менее затратным в использовании, чем <xref:System.Windows.UIElement>-производный объект. По возможности используйте <xref:System.Windows.Documents.Run> вместо <xref:System.Windows.Controls.TextBlock> для отображения текстового содержимого в <xref:System.Windows.Documents.FlowDocument>.  
  
 В следующем примере разметки показано два способа настройки текстового содержимого в <xref:System.Windows.Documents.FlowDocument>:  
  
 [!code-xml[Performance#PerformanceSnippet13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]  
  
### <a name="avoid-using-run-to-set-text-properties"></a>Избегайте выполнения для задания свойств текста  
 В общем случае использование <xref:System.Windows.Documents.Run> в <xref:System.Windows.Controls.TextBlock> является более производительным, чем неиспользование явных <xref:System.Windows.Documents.Run> объекта вообще. Если вы используете <xref:System.Windows.Documents.Run> для установки свойств текста, задайте эти свойства непосредственно на <xref:System.Windows.Controls.TextBlock> вместо.  
  
 В следующем примере разметки показаны два способа задания свойства текста, в данном случае <xref:System.Windows.Controls.TextBlock.FontWeight%2A> свойство:  
  
 [!code-xml[Performance#PerformanceSnippet12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]  
  
 В следующей таблице показаны производительность отображения 1000 <xref:System.Windows.Controls.TextBlock> объектов с и без явного <xref:System.Windows.Documents.Run>.  
  
|**Тип TextBlock**|**Время создания (мс)**|**Время отображения (мс)**|  
|------------------------|------------------------------|----------------------------|  
|Текст свойства параметров запуска|146|540|  
|Задание свойств текста TextBlock|43|453|  
  
### <a name="avoid-databinding-to-the-labelcontent-property"></a>Избегайте привязки данных к свойству Label.Content  
 Представьте себе ситуацию, в которой имеется <xref:System.Windows.Controls.Label> объект, часто обновляется из <xref:System.String> источника. При привязки данных <xref:System.Windows.Controls.Label> элемента <xref:System.Windows.Controls.ContentControl.Content%2A> свойства <xref:System.String> исходного объекта, может наблюдаться низкая производительность. Источник при каждом запуске <xref:System.String> обновляется, старый <xref:System.String> объект удаляется, а новый <xref:System.String> воссоздается — поскольку <xref:System.String> объект является неизменяемым, его нельзя изменить. Это, в свою очередь, вызывает <xref:System.Windows.Controls.ContentPresenter> из <xref:System.Windows.Controls.Label> , который удаляет устаревшее содержимое и создает новое содержимое для отображения новых <xref:System.String>.  
  
 Решения этой проблемы является простой. Если <xref:System.Windows.Controls.Label> не установлено пользовательское <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> значение, замените <xref:System.Windows.Controls.Label> с <xref:System.Windows.Controls.TextBlock> и выполните привязку данных его <xref:System.Windows.Controls.TextBlock.Text%2A> свойство исходную строку.  
  
|**Свойство с привязкой к данным**|**Время обновления (мс)**|  
|-----------------------------|----------------------------|  
|Label.Content|835|  
|TextBlock.Text|242|  
  
<a name="Hyperlink"></a>   
## <a name="hyperlink"></a>Гиперссылка  
 <xref:System.Windows.Documents.Hyperlink> объект является элементом содержимого потока встроенного уровня, позволяющим размещать гиперссылки в содержимом потока.  
  
### <a name="combine-hyperlinks-in-one-textblock-object"></a>Объединение гиперссылок в одном объекте TextBlock  
 Можно оптимизировать использование нескольких <xref:System.Windows.Documents.Hyperlink> элементов, группируя их вместе в одном <xref:System.Windows.Controls.TextBlock>. Это позволяет минимизировать число объектов, создаваемых в приложении. Например может потребоваться отобразить несколько гиперссылок, например следующие:  
  
 Домашняя страница MSN | Мой MSN  
  
 В следующем примере разметки показано несколько <xref:System.Windows.Controls.TextBlock> элементов, используемых для отображения гиперссылок:  
  
 [!code-xml[Performance#PerformanceSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]  
  
 В следующем примере разметки показан более эффективный способ отображения гиперссылок, на этот раз с помощью одного <xref:System.Windows.Controls.TextBlock>:  
  
 [!code-xml[Performance#PerformanceSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]  
  
### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>Отображение подчеркивания гиперссылок только при возникновении события MouseEnter  
 Объект <xref:System.Windows.TextDecoration> объекта визуальное украшение, можно добавить в текст; тем не менее, он может быть производительность при создании. Если более широко использовать <xref:System.Windows.Documents.Hyperlink> элементов, рассмотрите возможность отображать подчеркивание только при возникновении события, такие как <xref:System.Windows.ContentElement.MouseEnter> события. Дополнительные сведения см. в разделе [укажите ли подчеркнута](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
 ![Гиперссылки, отображающие TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Гиперссылка, появляющаяся при возникновении события MouseEnter  
  
 В следующем примере демонстрируется разметка <xref:System.Windows.Documents.Hyperlink> определенный с подчеркиванием и без него:  
  
 [!code-xml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 В следующей таблице показана производительность отображения 1000 <xref:System.Windows.Documents.Hyperlink> элементы с подчеркиванием и без него.  
  
|**Гиперссылки**|**Время создания (мс)**|**Время отображения (мс)**|  
|-------------------|------------------------------|----------------------------|  
|С подчеркиванием|289|1130|  
|Без подчеркивания|299|776|  
  
<a name="Text_Formatting_Features"></a>   
## <a name="text-formatting-features"></a>Возможности форматирования текста  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет службы, такие как автоматическая расстановка переносов форматирование текста. Эти службы могут влиять на производительность приложения и должен использоваться только при необходимости.  
  
### <a name="avoid-unnecessary-use-of-hyphenation"></a>Избегать необязательной расстановки переносов  
 Автоматическая расстановка переносов находит точки останова дефис строк текста и разрешает дополнительные позиции разрыва строк в <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Documents.FlowDocument> объектов. По умолчанию возможность автоматического переноса отключена в этих объектах. Эту функцию можно включить, установив свойство IsHyphenationEnabled объекта в `true`. Тем не менее, включение этой функции приводит к [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для инициирования [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)] взаимодействие, которое может повлиять на производительность приложения. Рекомендуется не использовать автоматическую расстановку переносов, если это не требуется.  
  
### <a name="use-figures-carefully"></a>Внимательно использовать рисунки  
 Объект <xref:System.Windows.Documents.Figure> элемент представляет часть растягиваемого содержимого, которое может быть абсолютно позиционировано внутри страницы содержимого. В некоторых случаях <xref:System.Windows.Documents.Figure> может вызвать автоматическое переформатирование, если ее положение конфликтует с уже размещенным содержимым всей страницы. Можно свести к минимуму вероятность ненужного переформатирования либо путем группировки <xref:System.Windows.Documents.Figure> элементы рядом друг с другом, либо объявлением их в верхней части содержимого в сценарии фиксированного размера страницы.  
  
### <a name="optimal-paragraph"></a>Оптимальный абзац  
 Средство оптимального абзаца из <xref:System.Windows.Documents.FlowDocument> размещает абзацы, чтобы максимально равномерно распределяется пробелы. По умолчанию средство оптимального абзаца отключено. Эту функцию можно включить, задав объект <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> свойства `true`. Тем не менее Включение этой функции влияет на производительность приложения. Рекомендуется не использовать средство оптимального абзаца, если это не требуется.  
  
## <a name="see-also"></a>См. также  
 [Улучшение производительности приложений WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Планирование производительности приложения](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Использование преимуществ оборудования](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Разметка и разработка](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [Двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Поведение объекта](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Ресурсы приложения](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Привязка данных](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Другие рекомендации по повышению производительности](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)