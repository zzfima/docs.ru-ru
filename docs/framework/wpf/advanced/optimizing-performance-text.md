---
title: 'Оптимизация производительности: отображение текста'
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
ms.openlocfilehash: 3e729458538353499f27f95ea2ca37fea1335238
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740350"
---
# <a name="optimizing-performance-text"></a>Оптимизация производительности: отображение текста

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]включает поддержку представления текстового контента с помощью многофункциональных элементов управления [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. В целом можно разделить отрисовку текста на три уровня.

1. Непосредственное использование объектов <xref:System.Windows.Documents.Glyphs> и <xref:System.Windows.Media.GlyphRun>.

2. Использование объекта <xref:System.Windows.Media.FormattedText>.

3. Использование элементов управления высокого уровня, таких как объекты <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Documents.FlowDocument>.

В этом разделе даются рекомендации по повышению производительности отрисовки текста.

<a name="Glyph_Level"></a>

## <a name="rendering-text-at-the-glyph-level"></a>Отрисовка текста на уровне глифа

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] обеспечивает расширенную поддержку текста, включая разметку на уровне глифов с прямым доступом к <xref:System.Windows.Documents.Glyphs> для клиентов, которым требуется перехватывать и сохранять текст после форматирования. Эти функции обеспечивают критически важную поддержку различных требований к отрисовке текста в каждом из следующих сценариев.

- Отображение на экране документов фиксированного формата.

- Сценарии печати.

  - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] как язык принтера.

  - Средство записи документов XPS (Майкрософт).

  - Предыдущие драйверы принтера, вывод из приложений Win32 в фиксированный формат.

  - Формат очереди печати.

- Представление документов фиксированного формата, включая клиенты предыдущих версий Windows и других вычислительных устройств.

> [!NOTE]
> <xref:System.Windows.Documents.Glyphs> и <xref:System.Windows.Media.GlyphRun> предназначены для представления документов фиксированного формата и сценариев печати. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет несколько элементов для общего макета и [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] сценариев, таких как <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.TextBlock>. Дополнительные сведения о макете и сценариях [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] см. в статье [Оформление в WPF](typography-in-wpf.md).

В следующих примерах показано, как определить свойства объекта <xref:System.Windows.Documents.Glyphs> в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Объект <xref:System.Windows.Documents.Glyphs> представляет выходные данные <xref:System.Windows.Media.GlyphRun> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. В примерах предполагается, что шрифты Arial, Courier New и Times New Roman устанавливаются в папку **C:\WINDOWS\Fonts** на локальном компьютере.

[!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]

### <a name="using-drawglyphrun"></a>Использование DrawGlyphRun

Если у вас есть пользовательский элемент управления и вы хотите визуализировать глифы, используйте метод <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A>.

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также предоставляет службы более низкого уровня для пользовательского форматирования текста с помощью объекта <xref:System.Windows.Media.FormattedText>. Наиболее эффективный способ отрисовки текста в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] — создание текстового содержимого на уровне глифа с помощью <xref:System.Windows.Documents.Glyphs> и <xref:System.Windows.Media.GlyphRun>. Однако стоимость этой эффективности заключается в снижении простоты использования форматированного текста, который является встроенными функциями элементов управления [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], таких как <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Documents.FlowDocument>.

<a name="FormattedText_Object"></a>

## <a name="formattedtext-object"></a>Объект FormattedText

Объект <xref:System.Windows.Media.FormattedText> позволяет рисовать многострочный текст, в котором каждый символ в тексте можно форматировать отдельно. Дополнительные сведения см. в разделе [Рисование форматированного текста](drawing-formatted-text.md).

Чтобы создать форматированный текст, вызовите конструктор <xref:System.Windows.Media.FormattedText.%23ctor%2A>, чтобы создать <xref:System.Windows.Media.FormattedText> объект. После создания исходной строки форматированного текста можно применить ряд стилей форматирования. Если приложению требуется реализовать собственный макет, то <xref:System.Windows.Media.FormattedText> объект лучше предпочтительнее, чем использование элемента управления, например <xref:System.Windows.Controls.TextBlock>. Дополнительные сведения об объекте <xref:System.Windows.Media.FormattedText> см. в разделе [Рисование форматированного текста](drawing-formatted-text.md) .

Объект <xref:System.Windows.Media.FormattedText> предоставляет возможность низкоуровневого форматирования текста. К одному или более символам можно применить несколько стилей форматирования. Например, можно вызвать методы <xref:System.Windows.Media.FormattedText.SetFontSize%2A> и <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A>, чтобы изменить форматирование первых пяти символов в тексте.

В следующем примере кода создается объект <xref:System.Windows.Media.FormattedText> и готовится к просмотру.

[!code-csharp[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
[!code-vb[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]

<a name="FlowDocument_TextBlock_Label"></a>

## <a name="flowdocument-textblock-and-label-controls"></a>Элементы управления FlowDocument, TextBlock и Label

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет множество элементов управления для отображения текста на экране. Каждый элемент управления предназначен для своего сценария и имеет собственный список функций и ограничений.

### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>FlowDocument влияет на производительность больше, чем TextBlock и Label

Как правило, элемент <xref:System.Windows.Controls.TextBlock> следует использовать, если требуется ограниченная поддержка текста, например краткое предложение в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> можно использовать, если требуется минимальная поддержка текста. Элемент <xref:System.Windows.Documents.FlowDocument> является контейнером для повторно передокументированных документов, поддерживающих представление содержимого, и поэтому имеет больше влияния на производительность, чем использование элементов управления <xref:System.Windows.Controls.TextBlock> или <xref:System.Windows.Controls.Label>.

Дополнительные сведения о <xref:System.Windows.Documents.FlowDocument>см. в разделе [Общие сведения о потоковых документах](flow-document-overview.md).

### <a name="avoid-using-textblock-in-flowdocument"></a>Избегайте использования TextBlock в FlowDocument

Элемент <xref:System.Windows.Controls.TextBlock> является производным от <xref:System.Windows.UIElement>. Элемент <xref:System.Windows.Documents.Run> является производным от <xref:System.Windows.Documents.TextElement>, который менее затратен для использования, чем объект, производный от <xref:System.Windows.UIElement>. По возможности используйте <xref:System.Windows.Documents.Run>, а не <xref:System.Windows.Controls.TextBlock> для отображения текстового содержимого в <xref:System.Windows.Documents.FlowDocument>.

В следующем примере разметки показаны два способа установки текстового содержимого в <xref:System.Windows.Documents.FlowDocument>.

[!code-xaml[Performance#PerformanceSnippet13](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]

### <a name="avoid-using-run-to-set-text-properties"></a>Избегайте использования Run для задания свойств текста

Как правило, использование <xref:System.Windows.Documents.Run> в <xref:System.Windows.Controls.TextBlock> более интенсивно, чем использование явного объекта <xref:System.Windows.Documents.Run>. Если вы используете <xref:System.Windows.Documents.Run>, чтобы задать свойства текста, задайте эти свойства непосредственно в <xref:System.Windows.Controls.TextBlock>.

В следующем примере разметки показаны два способа задания свойства текста, в данном случае свойство <xref:System.Windows.Controls.TextBlock.FontWeight%2A>:

[!code-xaml[Performance#PerformanceSnippet12](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]

В следующей таблице показаны затраты на отображение объектов 1000 <xref:System.Windows.Controls.TextBlock> с явно за<xref:System.Windows.Documents.Run>и без них.

|**Тип TextBlock**|**Время создания (мс)**|**Время отрисовки (мс)**|
|------------------------|------------------------------|----------------------------|
|Установка свойств текста с помощью Run|146|540|
|Установка свойств текста с помощью TextBlock|43|453|

### <a name="avoid-databinding-to-the-labelcontent-property"></a>Избегайте привязки данных к свойству Label.Content

Представьте себе ситуацию, когда у вас есть объект <xref:System.Windows.Controls.Label>, который часто обновляется из источника <xref:System.String>. При привязке данных к свойству <xref:System.Windows.Controls.ContentControl.Content%2A> элемента <xref:System.Windows.Controls.Label> к исходному объекту <xref:System.String> может наблюдаться низкая производительность. При каждом обновлении источника <xref:System.String> старый объект <xref:System.String> удаляется и создается новое <xref:System.String> — поскольку объект <xref:System.String> является неизменяемым, его нельзя изменить. Это, в свою очередь, приводит к тому, что <xref:System.Windows.Controls.ContentPresenter> объекта <xref:System.Windows.Controls.Label> удаляет его старое содержимое и повторно создает новое содержимое для вывода нового <xref:System.String>.

Решение этой проблемы довольно простое. Если <xref:System.Windows.Controls.Label> не задано значение пользовательского <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>, замените <xref:System.Windows.Controls.Label> на <xref:System.Windows.Controls.TextBlock> и данные Привяжите свойство <xref:System.Windows.Controls.TextBlock.Text%2A> к исходной строке.

|**Свойство с привязкой данных**|**Время обновления (мс)**|
|-----------------------------|----------------------------|
|Label.Content|835|
|TextBlock.Text|242|

<a name="Hyperlink"></a>

## <a name="hyperlink"></a>Гиперссылка

Объект <xref:System.Windows.Documents.Hyperlink> является элементом содержимого потока встроенного уровня, который позволяет размещать гиперссылки в содержимом нефиксированного формата.

### <a name="combine-hyperlinks-in-one-textblock-object"></a>Объединение гиперссылок в одном объекте TextBlock

Можно оптимизировать использование нескольких элементов <xref:System.Windows.Documents.Hyperlink>, группируя их вместе в одном <xref:System.Windows.Controls.TextBlock>. Это позволяет минимизировать число объектов, создаваемых в приложении. Например, может потребоваться отобразить несколько гиперссылок, как показано ниже.

Домашняя страница MSN | Мой MSN

В следующем примере разметки показано несколько элементов <xref:System.Windows.Controls.TextBlock>, используемых для отображения гиперссылок:

[!code-xaml[Performance#PerformanceSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]

В следующем примере разметки показан более эффективный способ отображения гиперссылок на этот раз с помощью одного <xref:System.Windows.Controls.TextBlock>:

[!code-xaml[Performance#PerformanceSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]

### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>Отображение подчеркивания гиперссылок только при возникновении события MouseEnter

Объект <xref:System.Windows.TextDecoration> — это визуальное украшение, которое можно добавить в текст; Однако создание экземпляра может задержаться в высокой производительности. Если элементы <xref:System.Windows.Documents.Hyperlink> широко используются, рассмотрите возможность отображения подчеркивания только при срабатывании события, например события <xref:System.Windows.ContentElement.MouseEnter>. Дополнительные сведения см. в разделе [Определение того, подчеркнута ли ссылка](how-to-specify-whether-a-hyperlink-is-underlined.md).

На следующем рисунке показано, как событие MouseEnter запускает подчеркнутую гиперссылку:

![Гиперссылки, отображающие TextDecorations](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)

В следующем примере разметки показан <xref:System.Windows.Documents.Hyperlink>, определенный с подчеркиванием и без него:

[!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]

В следующей таблице показаны затраты на производительность при отображении элементов 1000 <xref:System.Windows.Documents.Hyperlink> с подчеркиванием и без него.

|**Гиперссылка**|**Время создания (мс)**|**Время отрисовки (мс)**|
|-------------------|------------------------------|----------------------------|
|С подчеркиванием|289|1130|
|Без подчеркивания|299|776|

<a name="Text_Formatting_Features"></a>

## <a name="text-formatting-features"></a>Возможности форматирования текста

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет службы форматирования RTF, такие как автоматическая расстановка переносов. Эти службы могут влиять на производительность приложения и должны использоваться только при необходимости.

### <a name="avoid-unnecessary-use-of-hyphenation"></a>Избегайте излишнего использования расстановки переносов

Автоматическая расстановка переносов находит точки с дефисами для строк текста и позволяет добавлять дополнительные позиции разрыва строк в <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Documents.FlowDocument> объекты. По умолчанию возможность автоматического переноса в этих объектах отключена. Эту функцию можно включить, установив свойство IsHyphenationEnabled объекта в значение `true`. Однако включение этой функции приводит к тому, что [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] инициировать взаимодействие с моделью COM, что может повлиять на производительность приложения. Рекомендуется не использовать автоматическую расстановку переносов, если это не является обязательным.

### <a name="use-figures-carefully"></a>Внимательно используйте рисунки

Элемент <xref:System.Windows.Documents.Figure> представляет часть содержимого нефиксированного формата, которая может быть абсолютно размещена на странице содержимого. В некоторых случаях <xref:System.Windows.Documents.Figure> может вызвать автоматическое переформатирование всей страницы, если ее расположение конфликтует с уже размещенным содержимым. Можно уменьшить вероятность ненужного переформатирования, группируя <xref:System.Windows.Documents.Figure> элементы рядом друг с другом или объявляя их ближе к началу содержимого в сценарии фиксированного размера страницы.

### <a name="optimal-paragraph"></a>Оптимальный абзац

Функция оптимального абзаца объекта <xref:System.Windows.Documents.FlowDocument> размещает абзацы так, чтобы пробелы были равномерно распределены по мере возможности. По умолчанию средство оптимального абзаца отключено. Эту функцию можно включить, присвоив свойству <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> объекта значение `true`. Однако включение этой функции влияет на производительность приложения. Рекомендуется не использовать средство оптимального абзаца без необходимости.

## <a name="see-also"></a>См. также:

- [Улучшение производительности приложений WPF](optimizing-wpf-application-performance.md)
- [Планирование производительности приложения](planning-for-application-performance.md)
- [Использование преимуществ оборудования](optimizing-performance-taking-advantage-of-hardware.md)
- [Разметка и разработка](optimizing-performance-layout-and-design.md)
- [Двумерная графика и изображения](optimizing-performance-2d-graphics-and-imaging.md)
- [Поведение объекта](optimizing-performance-object-behavior.md)
- [Ресурсы приложений](optimizing-performance-application-resources.md)
- [Привязка данных](optimizing-performance-data-binding.md)
- [Дополнительные рекомендации по повышению производительности](optimizing-performance-other-recommendations.md)
