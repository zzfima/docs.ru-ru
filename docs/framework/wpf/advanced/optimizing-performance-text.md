---
title: 'Оптимизация производительности: Текст'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rendering text [WPF]
- hyperlinks [WPF]
- formatted text [WPF]
- text [WPF], performance
- glyphs [WPF]
ms.assetid: 66b1b9a7-8618-48db-b616-c57ea4327b98
ms.openlocfilehash: 318972c20f6461489226e19b3e517ba0ac069b28
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933361"
---
# <a name="optimizing-performance-text"></a>Оптимизация производительности: Текст

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]включает поддержку представления текстового контента с помощью многофункциональных элементов управления [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. В целом можно разделить отрисовку текста на три уровня.

1. Использование объектов <xref:System.Windows.Media.GlyphRun>инапрямую. <xref:System.Windows.Documents.Glyphs>

2. С помощью <xref:System.Windows.Media.FormattedText> объекта.

3. Использование элементов управления высокого уровня, таких как <xref:System.Windows.Controls.TextBlock> объекты и. <xref:System.Windows.Documents.FlowDocument>

В этом разделе даются рекомендации по повышению производительности отрисовки текста.

<a name="Glyph_Level"></a>

## <a name="rendering-text-at-the-glyph-level"></a>Отрисовка текста на уровне глифа

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]обеспечивает расширенную поддержку текста, включая разметку на уровне глифов <xref:System.Windows.Documents.Glyphs> с прямым доступом к клиентам, желающим перехватывать и сохранять текст после форматирования. Эти функции обеспечивают критически важную поддержку различных требований к отрисовке текста в каждом из следующих сценариев.

- Отображение на экране документов фиксированного формата.

- Сценарии печати.

  - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] как язык принтера.

  - Средство записи документов XPS (Майкрософт).

  - Предыдущие драйверы принтера, вывод из приложений [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] в фиксированный формат.

  - Формат очереди печати.

- Представление документов фиксированного формата, включая клиенты предыдущих версий Windows и других вычислительных устройств.

> [!NOTE]
> <xref:System.Windows.Documents.Glyphs>и <xref:System.Windows.Media.GlyphRun> предназначены для представления документов фиксированного формата и сценариев печати. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]предоставляет несколько элементов для общего макета и [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] сценариев, таких <xref:System.Windows.Controls.Label> как <xref:System.Windows.Controls.TextBlock>и. Дополнительные сведения о макете и сценариях [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] см. в статье [Оформление в WPF](typography-in-wpf.md).

В следующих примерах показано, как определить свойства для <xref:System.Windows.Documents.Glyphs> объекта в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Объект представляет выходные данные <xref:System.Windows.Media.GlyphRun> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. <xref:System.Windows.Documents.Glyphs> В примерах предполагается, что шрифты Arial, Courier New и Times New Roman устанавливаются в папку **C:\WINDOWS\Fonts** на локальном компьютере.

[!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]

### <a name="using-drawglyphrun"></a>Использование DrawGlyphRun

Если у вас есть пользовательский элемент управления и вы хотите визуализировать глифы, <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> используйте метод.

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]также предоставляет службы более низкого уровня для пользовательского форматирования текста с помощью <xref:System.Windows.Media.FormattedText> объекта. Самым эффективным способом отрисовки текста в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] является создание текстового содержимого на уровне глифа с помощью <xref:System.Windows.Documents.Glyphs> и <xref:System.Windows.Media.GlyphRun>. Однако стоимость этой эффективности заключается в снижении простоты использования форматирования форматированного текста, который является встроенными функциями [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] элементов управления, таких как <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Documents.FlowDocument>.

<a name="FormattedText_Object"></a>

## <a name="formattedtext-object"></a>Объект FormattedText

<xref:System.Windows.Media.FormattedText> Объект позволяет рисовать многострочный текст, в котором каждый символ в тексте можно форматировать отдельно. Дополнительные сведения см. в разделе [Рисование форматированного текста](drawing-formatted-text.md).

Чтобы создать форматированный текст, вызовите <xref:System.Windows.Media.FormattedText.%23ctor%2A> конструктор, чтобы <xref:System.Windows.Media.FormattedText> создать объект. После создания исходной строки форматированного текста можно применить ряд стилей форматирования. Если приложению требуется реализовать собственный макет, <xref:System.Windows.Media.FormattedText> то объект является лучшим выбором, чем использование элемента управления, <xref:System.Windows.Controls.TextBlock>например. Дополнительные сведения <xref:System.Windows.Media.FormattedText> об объекте см. в разделе [Рисование форматированного текста](drawing-formatted-text.md) .

<xref:System.Windows.Media.FormattedText> Объект предоставляет возможность низкоуровневого форматирования текста. К одному или более символам можно применить несколько стилей форматирования. Например, можно вызвать <xref:System.Windows.Media.FormattedText.SetFontSize%2A> методы и <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> , чтобы изменить форматирование первых пяти символов в тексте.

В следующем примере кода создается объект <xref:System.Windows.Media.FormattedText> и готовится к просмотру.

[!code-csharp[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
[!code-vb[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]

<a name="FlowDocument_TextBlock_Label"></a>

## <a name="flowdocument-textblock-and-label-controls"></a>Элементы управления FlowDocument, TextBlock и Label

В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеется множество элементов управления для рисования текста на экране. Каждый элемент управления предназначен для различных сценариев и имеет свой собственный список функций и ограничений.

### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>FlowDocument влияет на производительность больше, чем TextBlock и Label

Как правило <xref:System.Windows.Controls.TextBlock> , элемент следует использовать, если требуется ограниченная поддержка текста, например краткое предложение [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]в. <xref:System.Windows.Controls.Label>может использоваться, если требуется минимальная поддержка текста. Элемент является контейнером для повторно передокументированных документов, поддерживающих богатое представление содержимого, и, следовательно, существенно влияет на производительность, чем <xref:System.Windows.Controls.TextBlock> использование элементов <xref:System.Windows.Controls.Label> управления или. <xref:System.Windows.Documents.FlowDocument>

Дополнительные сведения о см <xref:System.Windows.Documents.FlowDocument>. в разделе [Общие сведения о потоковых документах](flow-document-overview.md).

### <a name="avoid-using-textblock-in-flowdocument"></a>Избегайте использования TextBlock в FlowDocument

Элемент является производным от <xref:System.Windows.UIElement>. <xref:System.Windows.Controls.TextBlock> Элемент является производным от, что менее <xref:System.Windows.UIElement>затратно для использования, чем объект, производный от <xref:System.Windows.Documents.TextElement>. <xref:System.Windows.Documents.Run> По возможности используйте <xref:System.Windows.Documents.Run> <xref:System.Windows.Controls.TextBlock> вместо для <xref:System.Windows.Documents.FlowDocument>отображения текстового содержимого в.

В следующем примере разметки показаны два способа установки текстового содержимого в <xref:System.Windows.Documents.FlowDocument>:

[!code-xaml[Performance#PerformanceSnippet13](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]

### <a name="avoid-using-run-to-set-text-properties"></a>Избегайте использования Run для задания свойств текста

Как <xref:System.Windows.Documents.Run> правило, использование в <xref:System.Windows.Controls.TextBlock> среде более эффективно, чем использование явного <xref:System.Windows.Documents.Run> объекта. Если вы используете <xref:System.Windows.Documents.Run> , чтобы задать свойства текста, задайте эти свойства непосредственно <xref:System.Windows.Controls.TextBlock> вместо.

В следующем примере разметки показаны два способа установки свойства Text, в данном случае <xref:System.Windows.Controls.TextBlock.FontWeight%2A> свойство:

[!code-xaml[Performance#PerformanceSnippet12](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]

В следующей таблице показаны затраты на отображение объектов 1000 <xref:System.Windows.Controls.TextBlock> с явным <xref:System.Windows.Documents.Run>использованием и без него.

|**Тип TextBlock**|**Время создания (мс)**|**Время отрисовки (мс)**|
|------------------------|------------------------------|----------------------------|
|Установка свойств текста с помощью Run|146|540|
|Установка свойств текста с помощью TextBlock|43|453|

### <a name="avoid-databinding-to-the-labelcontent-property"></a>Избегайте привязки данных к свойству Label.Content

Представьте себе ситуацию, когда у вас <xref:System.Windows.Controls.Label> есть объект, который часто обновляется <xref:System.String> из источника. При связывании <xref:System.Windows.Controls.Label> данных <xref:System.Windows.Controls.ContentControl.Content%2A> свойства элемента с <xref:System.String> исходным объектом может снизиться производительность. При каждом обновлении источника <xref:System.String> старый <xref:System.String> объект удаляется, а новый <xref:System.String> создается повторно, так как <xref:System.String> объект является неизменяемым, его нельзя изменить. Это, в свою очередь, приводит <xref:System.Windows.Controls.ContentPresenter> к тому <xref:System.Windows.Controls.Label> , что объект удаляет старое содержимое и повторно создает новое содержимое для вывода нового <xref:System.String>содержимого.

Решение этой проблемы довольно простое. <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <xref:System.Windows.Controls.TextBlock.Text%2A> <xref:System.Windows.Controls.TextBlock> Если для не задано пользовательское значение, замените значением и привяжите его свойство к исходной строке. <xref:System.Windows.Controls.Label>

|**Свойство с привязкой данных**|**Время обновления (мс)**|
|-----------------------------|----------------------------|
|Label.Content|835|
|TextBlock.Text|242|

<a name="Hyperlink"></a>

## <a name="hyperlink"></a>Hyperlink

<xref:System.Windows.Documents.Hyperlink> Объект является элементом содержимого потока встроенного уровня, который позволяет размещать гиперссылки в содержимом нефиксированного формата.

### <a name="combine-hyperlinks-in-one-textblock-object"></a>Объединение гиперссылок в одном объекте TextBlock

Можно оптимизировать использование нескольких <xref:System.Windows.Documents.Hyperlink> элементов, группируя их вместе внутри одного. <xref:System.Windows.Controls.TextBlock> Это позволяет минимизировать число объектов, создаваемых в приложении. Например, может потребоваться отобразить несколько гиперссылок, как показано ниже.

Домашняя страница MSN | Мой MSN

В следующем примере разметки показано <xref:System.Windows.Controls.TextBlock> несколько элементов, используемых для отображения гиперссылок:

[!code-xaml[Performance#PerformanceSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]

В следующем примере разметки показан более эффективный способ отображения гиперссылок, на этот раз с помощью одного <xref:System.Windows.Controls.TextBlock>:

[!code-xaml[Performance#PerformanceSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]

### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>Отображение подчеркивания гиперссылок только при возникновении события MouseEnter

<xref:System.Windows.TextDecoration> Объект — это визуальное украшение, которое можно добавить к тексту, однако это может потребовать большого объема производительности при создании экземпляра. При широком использовании <xref:System.Windows.Documents.Hyperlink> элементов рассмотрите возможность отображения подчеркивания только при срабатывании события, например <xref:System.Windows.ContentElement.MouseEnter> события. Дополнительные сведения см. в разделе [Определение того, подчеркнута ли ссылка](how-to-specify-whether-a-hyperlink-is-underlined.md).

На следующем рисунке показано, как событие MouseEnter запускает подчеркнутую гиперссылку:

![Гиперссылки, отображающие TextDecorations](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)

В следующем примере разметки показано <xref:System.Windows.Documents.Hyperlink> , что определено с подчеркиванием и без него:

[!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]

В следующей таблице показаны затраты на производительность при отображении <xref:System.Windows.Documents.Hyperlink> элементов 1000 с подчеркиванием и без него.

|**Гиперссылка**|**Время создания (мс)**|**Время отрисовки (мс)**|
|-------------------|------------------------------|----------------------------|
|С подчеркиванием|289|1130|
|Без подчеркивания|299|776|

<a name="Text_Formatting_Features"></a>

## <a name="text-formatting-features"></a>Возможности форматирования текста

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет службы форматирования RTF, такие как автоматическая расстановка переносов. Эти службы могут влиять на производительность приложения и должны использоваться только при необходимости.

### <a name="avoid-unnecessary-use-of-hyphenation"></a>Избегайте излишнего использования расстановки переносов

Автоматическая расстановка переносов находит точки с дефисами для строк текста и позволяет добавлять дополнительные позиции разрыва <xref:System.Windows.Documents.FlowDocument> для линий в <xref:System.Windows.Controls.TextBlock> объектах и. По умолчанию возможность автоматического переноса в этих объектах отключена. Эту функцию можно включить, установив свойство IsHyphenationEnabled объекта в значение `true`. Однако включение этой функции приводит [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] к инициации взаимодействия модели COM, что может повлиять на производительность приложения. Рекомендуется не использовать автоматическую расстановку переносов, если это не является обязательным.

### <a name="use-figures-carefully"></a>Внимательно используйте рисунки

<xref:System.Windows.Documents.Figure> Элемент представляет часть содержимого нефиксированного формата, которая может быть абсолютно размещена на странице содержимого. В некоторых случаях a <xref:System.Windows.Documents.Figure> может вызвать автоматическое переформатирование всей страницы, если ее расположение конфликтует с уже размещенным содержимым. Можно уменьшить вероятность ненужных переформатирования, либо сгруппировать <xref:System.Windows.Documents.Figure> элементы рядом друг с другом, либо объявить их ближе к началу содержимого в сценарии фиксированного размера страницы.

### <a name="optimal-paragraph"></a>Оптимальный абзац

Функция оптимального абзаца <xref:System.Windows.Documents.FlowDocument> объекта размещает абзацы так, чтобы пробелы были равномерно распределены по мере возможности. По умолчанию средство оптимального абзаца отключено. Эту функцию можно включить, задав <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> `true`свойству объекта значение. Однако включение этой функции влияет на производительность приложения. Рекомендуется не использовать средство оптимального абзаца без необходимости.

## <a name="see-also"></a>См. также

- [Улучшение производительности приложений WPF](optimizing-wpf-application-performance.md)
- [Планирование производительности приложения](planning-for-application-performance.md)
- [Использование преимуществ оборудования](optimizing-performance-taking-advantage-of-hardware.md)
- [Разметка и разработка](optimizing-performance-layout-and-design.md)
- [Двумерная графика и изображения](optimizing-performance-2d-graphics-and-imaging.md)
- [Поведение объекта](optimizing-performance-object-behavior.md)
- [Ресурсы приложений](optimizing-performance-application-resources.md)
- [Привязка данных](optimizing-performance-data-binding.md)
- [Дополнительные рекомендации по повышению производительности](optimizing-performance-other-recommendations.md)
