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
ms.openlocfilehash: 9e40a9656bd1d89203b167860ef6951d5e30377c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918402"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a>Знакомство с объектом GlyphRun и элементом Glyphs
В <xref:System.Windows.Media.GlyphRun> этом разделе описывается объект <xref:System.Windows.Documents.Glyphs> и элемент.  

<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a>Общие сведения о GlyphRun  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]обеспечивает расширенную поддержку текста, включая разметку на уровне глифов <xref:System.Windows.Documents.Glyphs> с прямым доступом к клиентам, желающим перехватывать и сохранять текст после форматирования. Эти функции обеспечивают критически важную поддержку различных требований к отрисовке текста в каждом из следующих сценариев.  
  
1. Отображение на экране документов фиксированного формата.  
  
2. Сценарии печати.  
  
    - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] как язык принтера.  
  
    - Средство записи документов XPS (Майкрософт).  
  
    - Предыдущие драйверы принтера, вывод из приложений [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] в фиксированный формат.  
  
    - Формат очереди печати.  
  
3. Представление документов фиксированного формата, включая клиенты предыдущих версий Windows и других вычислительных устройств.  
  
> [!NOTE]
> <xref:System.Windows.Documents.Glyphs>и <xref:System.Windows.Media.GlyphRun> предназначены для представления документов фиксированного формата и сценариев печати. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]предоставляет несколько элементов для общего макета и [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] сценариев, таких <xref:System.Windows.Controls.Label> как <xref:System.Windows.Controls.TextBlock>и. Дополнительные сведения о макете и сценариях [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] см. в статье [Оформление в WPF](typography-in-wpf.md).  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a>Объект GlyphRun  
 <xref:System.Windows.Media.GlyphRun> Объект представляет последовательность глифов из одной грани одного шрифта с одним размером и с одним стилем отрисовки.  
  
 <xref:System.Windows.Media.GlyphRun>включает как сведения о шрифтах, <xref:System.Windows.Documents.Glyphs.Indices%2A> такие как глифы, так и отдельные позиции глифов. Он также включает исходные [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] кодовые точки, из которых был создан запуск, сведения о сопоставлении смещения буфера символьного и глифа и флаги для каждого символа и глифа.  
  
 <xref:System.Windows.Media.GlyphRun>имеет соответствующий высокий уровень <xref:System.Windows.FrameworkElement>,. <xref:System.Windows.Documents.Glyphs> <xref:System.Windows.Documents.Glyphs>может использоваться в дереве элементов и в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметке для представления <xref:System.Windows.Media.GlyphRun> выходных данных.  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a>Элемент Glyphs  
 Элемент представляет выходные данные <xref:System.Windows.Media.GlyphRun> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. <xref:System.Windows.Documents.Glyphs> Для описания <xref:System.Windows.Documents.Glyphs> элемента используется следующий синтаксис разметки.  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 Следующие определения свойств соответствуют первым четырем атрибутам в примере разметки.  
  
|Свойство.|Описание|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|Указывает идентификатор ресурса: имя файла, веб- [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]адрес или ссылка на ресурс в файле Application. exe или контейнере.|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|Указывает размер шрифта в единицах графической поверхности (по умолчанию — 0,96 дюйма).|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|Задает флаги для полужирного шрифта и курсива.|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|Задает уровень двунаправленного макета. Четные и нулевые значения подразумевают макет слева направо; нечетные значения подразумевают макет справа налево.|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a>Свойство Indices  
 <xref:System.Windows.Documents.Glyphs.Indices%2A> Свойство является строкой спецификаций глифов. Если последовательность глифов образует единый кластер, спецификации первого глифа в кластере предшествует спецификация того, сколько глифов и сколько кодовых точек объединяются для формирования кластера. <xref:System.Windows.Documents.Glyphs.Indices%2A> Свойство собирает в одной строке следующие свойства.  
  
- Индексы глифов  
  
- Дополнительная ширина глифа  
  
- Объединение векторов присоединения глифа  
  
- Сопоставление кластера от кодовых точек к глифам  
  
- Флаги глифов  
  
 Спецификация глифа имеет следующий вид.  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a>Метрики глифа  
 Каждый глиф определяет метрики, указывающие, как оно соответствует другому <xref:System.Windows.Documents.Glyphs>. На следующем рисунке определяются различные типографические качества двух разных символов глифа.  
  
 ![Схема измерений глифа](./media/glyph-example.png "glyph_example")  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a>Разметка глифа  
 В следующем примере кода показано, как использовать различные свойства <xref:System.Windows.Documents.Glyphs> элемента в. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>См. также

- [Оформление в WPF](typography-in-wpf.md)
- [Документы в WPF](documents-in-wpf.md)
- [Text](optimizing-performance-text.md)
