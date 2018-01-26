---
title: "Оптимизация производительности: отображение текста"
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
- rendering text [WPF]
- hyperlinks [WPF]
- formatted text [WPF]
- text [WPF], performance
- glyphs [WPF]
ms.assetid: 66b1b9a7-8618-48db-b616-c57ea4327b98
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f345893ca79d820ebb066d920cb49c6c46c47297
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="optimizing-performance-text"></a>Оптимизация производительности: отображение текста
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]включает поддержку представления текстового контента с помощью многофункциональных элементов управления [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. В целом можно разделить отрисовку текста на три уровня.  
  
1.  С помощью <xref:System.Windows.Documents.Glyphs> и <xref:System.Windows.Media.GlyphRun> объекты непосредственно.  
  
2.  С помощью <xref:System.Windows.Media.FormattedText> объекта.  
  
3.  С помощью элементов управления верхнего уровня, таких как <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Documents.FlowDocument> объектов.  
  
 В этом разделе даются рекомендации по повышению производительности отрисовки текста.  
  
  
<a name="Glyph_Level"></a>   
## <a name="rendering-text-at-the-glyph-level"></a>Отрисовка текста на уровне глифа  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]предоставляет поддержку дополнительных текста, включая разметку на уровне глифа с прямым доступом к <xref:System.Windows.Documents.Glyphs> для клиентов, которые требуется перехватывать и сохранять текст после форматирования. Эти функции обеспечивают критически важную поддержку различных требований к отрисовке текста в каждом из следующих сценариев.  
  
-   Отображение на экране документов фиксированного формата.  
  
-   Сценарии печати.  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] как язык принтера.  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)].  
  
    -   Предыдущие драйверы принтера, вывод из приложений [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] в фиксированный формат.  
  
    -   Формат очереди печати.  
  
-   Представление документов фиксированного формата, включая клиенты предыдущих версий [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] и другие вычислительные устройства.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Glyphs>и <xref:System.Windows.Media.GlyphRun> предназначены для представления документа фиксированного формата и сценариев печати. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]предоставляет несколько элементов для общего макета и [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] сценариях, например <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.TextBlock>. Дополнительные сведения о макете и сценариях [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] см. в статье [Оформление в WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).  
  
 Следующие примеры показывают, как можно задать свойства для <xref:System.Windows.Documents.Glyphs> объекта в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. <xref:System.Windows.Documents.Glyphs> Объект представляет выходные данные <xref:System.Windows.Media.GlyphRun> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. В примерах предполагается, что шрифты Arial, Courier New и Times New Roman устанавливаются в папку **C:\WINDOWS\Fonts** на локальном компьютере.  
  
 [!code-xaml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
### <a name="using-drawglyphrun"></a>Использование DrawGlyphRun  
 Если имеется пользовательский элемент управления, и вы хотите отобразить глифы, используйте <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> метод.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]также предоставляет службы более низкого уровня для пользовательского форматирования с помощью объекта текста <xref:System.Windows.Media.FormattedText> объекта. Наиболее эффективный способ отображения текста в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] является создание содержимого текста на уровне глифа с помощью <xref:System.Windows.Documents.Glyphs> и <xref:System.Windows.Media.GlyphRun>. Однако ценой этой эффективности означает потерю удобные форматированный текст, который встроенными функциональными возможностями для [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] элементы управления, такие как <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Documents.FlowDocument>.  
  
<a name="FormattedText_Object"></a>   
## <a name="formattedtext-object"></a>Объект FormattedText  
 <xref:System.Windows.Media.FormattedText> Позволяет рисовать многострочный текст, в котором каждый символ в тексте можно форматировать отдельно. Дополнительные сведения см. в разделе [Рисование форматированного текста](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md).  
  
 Чтобы создать форматированный текст, вызовите <xref:System.Windows.Media.FormattedText.%23ctor%2A> конструктор для создания <xref:System.Windows.Media.FormattedText> объекта. После создания исходной строки форматированного текста можно применить ряд стилей форматирования. Если в приложении требуется реализовать собственный макет, то <xref:System.Windows.Media.FormattedText> объект является более предпочтительной, чем с помощью элемента управления, такие как <xref:System.Windows.Controls.TextBlock>. Дополнительные сведения о <xref:System.Windows.Media.FormattedText> см. в разделе [Рисование текста в формате](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md) .  
  
 <xref:System.Windows.Media.FormattedText> Объект предоставляет возможность низкоуровневого форматирования текста. К одному или более символам можно применить несколько стилей форматирования. Например, можно вызвать как <xref:System.Windows.Media.FormattedText.SetFontSize%2A> и <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> методов, чтобы изменить форматирование первые пять символов в тексте.  
  
 В следующем примере кода создается <xref:System.Windows.Media.FormattedText> объекта и отображает его.  
  
 [!code-csharp[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
<a name="FlowDocument_TextBlock_Label"></a>   
## <a name="flowdocument-textblock-and-label-controls"></a>Элементы управления FlowDocument, TextBlock и Label  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеется множество элементов управления для рисования текста на экране. Каждый элемент управления предназначен для различных сценариев и имеет свой собственный список функций и ограничений.  
  
### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>FlowDocument влияет на производительность больше, чем TextBlock и Label  
 Как правило <xref:System.Windows.Controls.TextBlock> элемент должен использоваться, если требуется ограниченная поддержка текста, например краткие предложения в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label>можно использовать, когда требуется Минимальная поддержка текста. <xref:System.Windows.Documents.FlowDocument> Элемент является контейнером для повторно форматируемых документов, которые поддерживают форматированного представления содержимого и таким образом, может повлиять на производительность больше, чем при использовании <xref:System.Windows.Controls.TextBlock> или <xref:System.Windows.Controls.Label> элементов управления.  
  
 Дополнительные сведения о <xref:System.Windows.Documents.FlowDocument>, в разделе [Общие сведения о документа нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
### <a name="avoid-using-textblock-in-flowdocument"></a>Избегайте использования TextBlock в FlowDocument  
 <xref:System.Windows.Controls.TextBlock> Элемент является производным от <xref:System.Windows.UIElement>. <xref:System.Windows.Documents.Run> Элемент является производным от <xref:System.Windows.Documents.TextElement>, который является менее затратным по сравнению с <xref:System.Windows.UIElement>-производного объекта. По возможности используйте <xref:System.Windows.Documents.Run> вместо <xref:System.Windows.Controls.TextBlock> для отображения текстового содержимого в <xref:System.Windows.Documents.FlowDocument>.  
  
 В следующем примере разметки показано два способа настройки текстового содержимого в <xref:System.Windows.Documents.FlowDocument>:  
  
 [!code-xaml[Performance#PerformanceSnippet13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]  
  
### <a name="avoid-using-run-to-set-text-properties"></a>Избегайте использования Run для задания свойств текста  
 В целом, использование <xref:System.Windows.Documents.Run> в <xref:System.Windows.Controls.TextBlock> является более производительным, чем неиспользование явных <xref:System.Windows.Documents.Run> объекта вообще. Если вы используете <xref:System.Windows.Documents.Run> для установки свойств текста, задайте эти свойства непосредственно в <xref:System.Windows.Controls.TextBlock> вместо него.  
  
 В следующем примере разметки показаны два способа задания свойства текста, в этом случае <xref:System.Windows.Controls.TextBlock.FontWeight%2A> свойство:  
  
 [!code-xaml[Performance#PerformanceSnippet12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]  
  
 В следующей таблице показаны производительность отображения 1000 <xref:System.Windows.Controls.TextBlock> объектов с и без явного <xref:System.Windows.Documents.Run>.  
  
|**Тип TextBlock**|**Время создания (мс)**|**Время отрисовки (мс)**|  
|------------------------|------------------------------|----------------------------|  
|Установка свойств текста с помощью Run|146|540|  
|Установка свойств текста с помощью TextBlock|43|453|  
  
### <a name="avoid-databinding-to-the-labelcontent-property"></a>Избегайте привязки данных к свойству Label.Content  
 Представьте себе ситуацию, когда имеется <xref:System.Windows.Controls.Label> объект, который часто обновляется из <xref:System.String> источника. При привязке данных <xref:System.Windows.Controls.Label> элемента <xref:System.Windows.Controls.ContentControl.Content%2A> свойства <xref:System.String> исходный объект, может наблюдаться низкая производительность. Источник при каждом запуске <xref:System.String> обновляется, старый <xref:System.String> объект удаляется, а новый <xref:System.String> создается заново, так как <xref:System.String> является неизменяемым, его невозможно изменить. Это, в свою очередь, вызовет переход <xref:System.Windows.Controls.ContentPresenter> из <xref:System.Windows.Controls.Label> объект удаляет устаревшее содержимое и создает новое содержимое для отображения нового <xref:System.String>.  
  
 Решение этой проблемы довольно простое. Если <xref:System.Windows.Controls.Label> не установлено пользовательское <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> значений, замените <xref:System.Windows.Controls.Label> с <xref:System.Windows.Controls.TextBlock> и выполните привязку данных его <xref:System.Windows.Controls.TextBlock.Text%2A> свойство исходную строку.  
  
|**Свойство с привязкой данных**|**Время обновления (мс)**|  
|-----------------------------|----------------------------|  
|Label.Content|835|  
|TextBlock.Text|242|  
  
<a name="Hyperlink"></a>   
## <a name="hyperlink"></a>Гиперссылка  
 <xref:System.Windows.Documents.Hyperlink> Объект является элемент содержимого потока встроенного уровня, позволяющий размещать гиперссылки в содержимом потока.  
  
### <a name="combine-hyperlinks-in-one-textblock-object"></a>Объединение гиперссылок в одном объекте TextBlock  
 Можно оптимизировать использование нескольких <xref:System.Windows.Documents.Hyperlink> элементов, группируя их вместе в одном <xref:System.Windows.Controls.TextBlock>. Это позволяет минимизировать число объектов, создаваемых в приложении. Например, может потребоваться отобразить несколько гиперссылок, как показано ниже.  
  
 Домашняя страница MSN | Мой MSN  
  
 В следующем примере разметки показано несколько <xref:System.Windows.Controls.TextBlock> элементы, используемые для отображения гиперссылок:  
  
 [!code-xaml[Performance#PerformanceSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]  
  
 В следующем примере разметки показан более эффективный способ отображения гиперссылок, на этот раз с помощью одного <xref:System.Windows.Controls.TextBlock>:  
  
 [!code-xaml[Performance#PerformanceSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]  
  
### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>Отображение подчеркивания гиперссылок только при возникновении события MouseEnter  
 Объект <xref:System.Windows.TextDecoration> объект — это визуальное украшение, можно добавить в текст, однако он может быть производительность при создании. Если предусматривают широкое использование <xref:System.Windows.Documents.Hyperlink> элементов, рассмотрите возможность отображать подчеркивание только при возникновении события, такие как <xref:System.Windows.ContentElement.MouseEnter> событий. Дополнительные сведения см. в разделе [Определение того, подчеркнута ли ссылка](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
 ![Гиперссылки, отображающие TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Гиперссылка, появляющаяся при возникновении события MouseEnter  
  
 В следующем примере демонстрируется разметки <xref:System.Windows.Documents.Hyperlink> определен с подчеркиванием и без него:  
  
 [!code-xaml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 В следующей таблице показаны снижение производительности при отображении 1000 <xref:System.Windows.Documents.Hyperlink> элементы с подчеркиванием и без него.  
  
|**Гиперссылка**|**Время создания (мс)**|**Время отрисовки (мс)**|  
|-------------------|------------------------------|----------------------------|  
|С подчеркиванием|289|1130|  
|Без подчеркивания|299|776|  
  
<a name="Text_Formatting_Features"></a>   
## <a name="text-formatting-features"></a>Возможности форматирования текста  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет службы форматирования RTF, такие как автоматическая расстановка переносов. Эти службы могут влиять на производительность приложения и должны использоваться только при необходимости.  
  
### <a name="avoid-unnecessary-use-of-hyphenation"></a>Избегайте излишнего использования расстановки переносов  
 Автоматическая расстановка переносов находит дефис точки останова для строк текста и разрешает дополнительные позиции разрыва строк в <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Documents.FlowDocument> объектов. По умолчанию возможность автоматического переноса в этих объектах отключена. Эту функцию можно включить, установив свойство IsHyphenationEnabled объекта в значение `true`. Однако включение этой функции заставляет [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] инициировать взаимодействие [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], которое может повлиять на производительность приложения. Рекомендуется не использовать автоматическую расстановку переносов, если это не является обязательным.  
  
### <a name="use-figures-carefully"></a>Внимательно используйте рисунки  
 Объект <xref:System.Windows.Documents.Figure> элемент представляет часть растягиваемого содержимого, которое может быть абсолютно позиционировано внутри страницы содержимого. В некоторых случаях <xref:System.Windows.Documents.Figure> может вызвать автоматическое переформатирование, если ее положение конфликтует с уже размещенным содержимым всей страницы. Можно свести к минимуму вероятность ненужного переформатирования либо путем группировки <xref:System.Windows.Documents.Figure> элементов рядом с друг с другом, либо объявлением их в верхней части содержимого в сценарии фиксированного размера страницы.  
  
### <a name="optimal-paragraph"></a>Оптимальный абзац  
 Средство оптимального абзаца из <xref:System.Windows.Documents.FlowDocument> размещает абзацы, чтобы максимально равномерно распределяется пробелы. По умолчанию средство оптимального абзаца отключено. Эту функцию можно включить, задав объекта <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> свойства `true`. Однако включение этой функции влияет на производительность приложения. Рекомендуется не использовать средство оптимального абзаца без необходимости.  
  
## <a name="see-also"></a>См. также  
 [Улучшение производительности приложений WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Планирование производительности приложения](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Использование преимуществ оборудования](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Разметка и разработка](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [Двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Поведение объекта](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Ресурсы приложений](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [Привязка данных](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Дополнительные рекомендации по повышению производительности](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
