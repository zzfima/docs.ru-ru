---
title: Знакомство с объектом GlyphRun и элементом Glyphs
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], Glyphs element
- Glyphs elements [WPF]
- GlyphRun object [WPF]
- text [WPF], glyphs
- glyphs [WPF]
- typography [WPF], GlyphRun object
ms.assetid: 746ca769-a331-4435-9b95-f72a883b67c1
ms.openlocfilehash: 9af07d48877fee0e94f8e5fa2556c4361795df6a
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740353"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a>Знакомство с объектом GlyphRun и элементом Glyphs
В этом разделе описывается объект <xref:System.Windows.Media.GlyphRun> и элемент <xref:System.Windows.Documents.Glyphs>.  

<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a>Общие сведения о GlyphRun  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] обеспечивает расширенную поддержку текста, включая разметку на уровне глифов с прямым доступом к <xref:System.Windows.Documents.Glyphs> для клиентов, которым требуется перехватывать и сохранять текст после форматирования. Эти функции обеспечивают критически важную поддержку различных требований к отрисовке текста в каждом из следующих сценариев.  
  
1. Отображение на экране документов фиксированного формата.  
  
2. Сценарии печати.  
  
    - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] как язык принтера.  
  
    - Средство записи документов XPS (Майкрософт).  
  
    - Предыдущие драйверы принтера, вывод из приложений Win32 в фиксированный формат.  
  
    - Формат очереди печати.  
  
3. Представление документов фиксированного формата, включая клиенты предыдущих версий Windows и других вычислительных устройств.  
  
> [!NOTE]
> <xref:System.Windows.Documents.Glyphs> и <xref:System.Windows.Media.GlyphRun> предназначены для представления документов фиксированного формата и сценариев печати. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет несколько элементов для общего макета и [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] сценариев, таких как <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.TextBlock>. Дополнительные сведения о макете и сценариях [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] см. в статье [Оформление в WPF](typography-in-wpf.md).  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a>Объект GlyphRun  
 Объект <xref:System.Windows.Media.GlyphRun> представляет последовательность глифов из одной грани одного шрифта с одним размером и с одним стилем отрисовки.  
  
 <xref:System.Windows.Media.GlyphRun> включает как сведения о шрифтах, такие как <xref:System.Windows.Documents.Glyphs.Indices%2A> глифов, так и отдельные позиции глифов. Он также включает исходные кодовые точки Юникода, из которых был создан запуск, сведения о сопоставлении смещения буфера символов и глифов, а также флаги отдельных символов и глифов.  
  
 <xref:System.Windows.Media.GlyphRun> имеет соответствующий высокоуровневый <xref:System.Windows.FrameworkElement><xref:System.Windows.Documents.Glyphs>. <xref:System.Windows.Documents.Glyphs> можно использовать в дереве элементов и в разметке [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для представления выходных данных <xref:System.Windows.Media.GlyphRun>.  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a>Элемент Glyphs  
 Элемент <xref:System.Windows.Documents.Glyphs> представляет выходные данные <xref:System.Windows.Media.GlyphRun> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Для описания элемента <xref:System.Windows.Documents.Glyphs> используется следующий синтаксис разметки.  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 Следующие определения свойств соответствуют первым четырем атрибутам в примере разметки.  
  
|Идентификаторы|Описание|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|Указывает идентификатор ресурса: имя файла, универсальный код ресурса (URI) или ссылку на ресурс в файле Application. exe или контейнере.|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|Указывает размер шрифта в единицах графической поверхности (по умолчанию — 0,96 дюйма).|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|Задает флаги для полужирного шрифта и курсива.|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|Задает уровень двунаправленного макета. Четные и нулевые значения подразумевают макет слева направо; нечетные значения подразумевают макет справа налево.|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a>Свойство Indices  
 Свойство <xref:System.Windows.Documents.Glyphs.Indices%2A> — это строка спецификаций глифов. Если последовательность глифов образует единый кластер, спецификации первого глифа в кластере предшествует спецификация того, сколько глифов и сколько кодовых точек объединяются для формирования кластера. Свойство <xref:System.Windows.Documents.Glyphs.Indices%2A> собирает в одной строке следующие свойства.  
  
- Индексы глифов  
  
- Дополнительная ширина глифа  
  
- Объединение векторов присоединения глифа  
  
- Сопоставление кластера от кодовых точек к глифам  
  
- Флаги глифов  
  
 Спецификация глифа имеет следующий вид.  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a>Метрики глифа  
 Каждый глиф определяет метрики, указывающие, как оно соответствует другим <xref:System.Windows.Documents.Glyphs>. На следующем рисунке определяются различные типографические качества двух разных символов глифа.  
  
 ![Схема измерений глифов](./media/glyph-example.png "glyph_example")  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a>Разметка глифа  
 В следующем примере кода показано, как использовать различные свойства элемента <xref:System.Windows.Documents.Glyphs> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>См. также:

- [Оформление в WPF](typography-in-wpf.md)
- [Документы в WPF](documents-in-wpf.md)
- [Text](optimizing-performance-text.md)
