---
title: "Знакомство с объектом GlyphRun и элементом Glyphs | Microsoft Docs"
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
  - "Оформление и элемент глифов"
  - "Glyphs - элементы"
  - "GlyphRun - объект"
  - "текст, глифов"
  - "глифы [WPF]"
  - "Оформление и GlyphRun-объект"
ms.assetid: 746ca769-a331-4435-9b95-f72a883b67c1
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Знакомство с объектом GlyphRun и элементом Glyphs
В этом разделе описывается <xref:System.Windows.Media.GlyphRun> объекта и <xref:System.Windows.Documents.Glyphs> элемента.  
  
   
  
<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a>Введение в GlyphRun  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]обеспечивает поддержку дополнительного текста, включая разметку на уровне глифа с прямым доступом к <xref:System.Windows.Documents.Glyphs> для клиентов, которым требуется перехватывать и сохранять текст после форматирования. Эти функции обеспечивают важную поддержку различных текст требований к отрисовке в каждом из следующих сценариев.  
  
1.  Отображение документов в фиксированных форматах.  
  
2.  Сценарии печати.  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]как язык принтера.  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)].  
  
    -   Предыдущие драйверы принтера, приведенные из [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] приложения в фиксированный формат.  
  
    -   Формат очереди печати.  
  
3.  Представление документов фиксированного формата, включая клиенты предыдущих версий [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] и другие вычислительные устройства.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Glyphs> и <xref:System.Windows.Media.GlyphRun> предназначены для представления документа фиксированного формата и сценариев печати.                      [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]предоставляет несколько элементов для общего макета и [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] сценарии, такие как <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.TextBlock>. Дополнительные сведения о макете и [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] сценарии, в статье [оформление в WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a>GlyphRun-объект  
 <xref:System.Windows.Media.GlyphRun> объект представляет последовательность глифов из одной грани одного шрифта одного размера и с одним стилем отрисовки.  
  
 <xref:System.Windows.Media.GlyphRun> включает детали шрифта, такие как глиф <xref:System.Windows.Documents.Glyphs.Indices%2A> и отдельные позиции глифов. Он также включает исходные [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] кодовые точки был сгенерирован запуск, сведения о сопоставлении смещения буфера символ в глиф и флаги каждого символа и глифа.  
  
 <xref:System.Windows.Media.GlyphRun> имеет соответствующий общий <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.                  <xref:System.Windows.Documents.Glyphs> может использоваться в дереве элементов и в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметку, представляющую <xref:System.Windows.Media.GlyphRun> выходные данные.  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a>Элемент глифов  
 <xref:System.Windows.Documents.Glyphs> элемент представляет выходные данные <xref:System.Windows.Media.GlyphRun> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Следующий синтаксис разметки используется для описания <xref:System.Windows.Documents.Glyphs> элемента.  
  
 [!code-xml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 Следующие определения свойств соответствуют первым четырем атрибутам в примере разметки.  
  
|Свойство|Описание|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|Указывает идентификатор ресурса: имя файла, [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], или ссылку на ресурс в приложение .exe или контейнера.|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|Указывает размер шрифта в единицах графической поверхности (по умолчанию —.96 дюймов).|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|Задает флаги для полужирного шрифта и курсива стилей.|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|Задает уровень двунаправленного макета. Четные и нулевые значения подразумевают макет справа налево; нечетные значения подразумевают макет справа налево.|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a>Свойство индексов  
 <xref:System.Windows.Documents.Glyphs.Indices%2A> свойство является строкой спецификаций глифа. Где последовательность глифов формирует один кластер, спецификации первого глифа в кластере предшествует Указание количества глифов и кодовых точек объединяются в кластер. <xref:System.Windows.Documents.Glyphs.Indices%2A> свойство собирает в одной строке следующие свойства.  
  
-   Индексы глифов  
  
-   Дополнительная ширина глифа  
  
-   Объединение векторов присоединения глифа  
  
-   Сопоставление кластера из точек кода глифы  
  
-   Флаги глифа  
  
 Каждая спецификация глифа имеет следующий вид.  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a>Метрики глифа  
 Каждый глиф определяет метрику, задающую способ выравнивания с другими <xref:System.Windows.Documents.Glyphs>. На следующем рисунке определяются различные типографические качества для символов двух различных глифов.  
  
 ![Схема измерений глифа](../../../../docs/framework/wpf/advanced/media/glyph-example.png "glyph_example")  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a>Разметка глифа  
 В следующем примере кода показано, как использовать различные свойства <xref:System.Windows.Documents.Glyphs> элемент в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[GlyphsOvwSamp2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>См. также  
 [Оформление в WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)   
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Текст](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)