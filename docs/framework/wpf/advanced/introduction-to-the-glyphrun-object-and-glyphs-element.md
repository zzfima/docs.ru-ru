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
ms.openlocfilehash: 5750177c03cf859ebb884c5774b7ded03fa60628
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a><span data-ttu-id="757da-102">Знакомство с объектом GlyphRun и элементом Glyphs</span><span class="sxs-lookup"><span data-stu-id="757da-102">Introduction to the GlyphRun Object and Glyphs Element</span></span>
<span data-ttu-id="757da-103">В этом разделе описывается <xref:System.Windows.Media.GlyphRun> объекта и <xref:System.Windows.Documents.Glyphs> элемента.</span><span class="sxs-lookup"><span data-stu-id="757da-103">This topic describes the <xref:System.Windows.Media.GlyphRun> object and the <xref:System.Windows.Documents.Glyphs> element.</span></span>  
  
  
<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a><span data-ttu-id="757da-104">Общие сведения о GlyphRun</span><span class="sxs-lookup"><span data-stu-id="757da-104">Introduction to GlyphRun</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="757da-105"> предоставляет поддержку дополнительных текста, включая разметку на уровне глифа с прямым доступом к <xref:System.Windows.Documents.Glyphs> для клиентов, которые требуется перехватывать и сохранять текст после форматирования.</span><span class="sxs-lookup"><span data-stu-id="757da-105"> provides advanced text support including glyph-level markup with direct access to <xref:System.Windows.Documents.Glyphs> for customers who want to intercept and persist text after formatting.</span></span> <span data-ttu-id="757da-106">Эти функции обеспечивают критически важную поддержку различных требований к отрисовке текста в каждом из следующих сценариев.</span><span class="sxs-lookup"><span data-stu-id="757da-106">These features provide critical support for the different text rendering requirements in each of the following scenarios.</span></span>  
  
1.  <span data-ttu-id="757da-107">Отображение на экране документов фиксированного формата.</span><span class="sxs-lookup"><span data-stu-id="757da-107">Screen display of fixed-format documents.</span></span>  
  
2.  <span data-ttu-id="757da-108">Сценарии печати.</span><span class="sxs-lookup"><span data-stu-id="757da-108">Print scenarios.</span></span>  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]<span data-ttu-id="757da-109"> как язык принтера.</span><span class="sxs-lookup"><span data-stu-id="757da-109"> as a device printer language.</span></span>  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)]<span data-ttu-id="757da-110">.</span><span class="sxs-lookup"><span data-stu-id="757da-110">.</span></span>  
  
    -   <span data-ttu-id="757da-111">Предыдущие драйверы принтера, вывод из приложений [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] в фиксированный формат.</span><span class="sxs-lookup"><span data-stu-id="757da-111">Previous printer drivers, output from [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications to the fixed format.</span></span>  
  
    -   <span data-ttu-id="757da-112">Формат очереди печати.</span><span class="sxs-lookup"><span data-stu-id="757da-112">Print spool format.</span></span>  
  
3.  <span data-ttu-id="757da-113">Представление документов фиксированного формата, включая клиенты предыдущих версий [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] и другие вычислительные устройства.</span><span class="sxs-lookup"><span data-stu-id="757da-113">Fixed-format document representation, including clients for previous versions of [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] and other computing devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="757da-114"><xref:System.Windows.Documents.Glyphs> и <xref:System.Windows.Media.GlyphRun> предназначены для представления документа фиксированного формата и сценариев печати.</span><span class="sxs-lookup"><span data-stu-id="757da-114"><xref:System.Windows.Documents.Glyphs> and <xref:System.Windows.Media.GlyphRun> are designed for fixed-format document presentation and print scenarios.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="757da-115"> предоставляет несколько элементов для общего макета и [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] сценариях, например <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="757da-115"> provides several elements for general layout and [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenarios such as <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="757da-116">Дополнительные сведения о макете и сценариях [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] см. в статье [Оформление в WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="757da-116">For more information on layout and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios, see the [Typography in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).</span></span>  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a><span data-ttu-id="757da-117">Объект GlyphRun</span><span class="sxs-lookup"><span data-stu-id="757da-117">The GlyphRun Object</span></span>  
 <span data-ttu-id="757da-118"><xref:System.Windows.Media.GlyphRun> Объект представляет последовательность глифов из одного гарнитуру одного шрифта одного размера и с одним стилем отрисовки.</span><span class="sxs-lookup"><span data-stu-id="757da-118">The <xref:System.Windows.Media.GlyphRun> object represents a sequence of glyphs from a single face of a single font at a single size, and with a single rendering style.</span></span>  
  
 <span data-ttu-id="757da-119"><xref:System.Windows.Media.GlyphRun> включает детали шрифта, такие как глиф <xref:System.Windows.Documents.Glyphs.Indices%2A> и отдельные позиции глифов.</span><span class="sxs-lookup"><span data-stu-id="757da-119"><xref:System.Windows.Media.GlyphRun> includes both font details such as glyph <xref:System.Windows.Documents.Glyphs.Indices%2A> and individual glyph positions.</span></span> <span data-ttu-id="757da-120">Он также включает в себя исходный [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] кодовые точки был сгенерирован из сведения о сопоставлении смещения буфера символ глиф и флаги каждого символа и глифа.</span><span class="sxs-lookup"><span data-stu-id="757da-120">It also includes the original [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] code points the run was generated from, character-to-glyph buffer offset mapping information, and per-character and per-glyph flags.</span></span>  
  
 <span data-ttu-id="757da-121"><xref:System.Windows.Media.GlyphRun> имеет соответствующий высокого уровня <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span><span class="sxs-lookup"><span data-stu-id="757da-121"><xref:System.Windows.Media.GlyphRun> has a corresponding high-level <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="757da-122"><xref:System.Windows.Documents.Glyphs> может использоваться в дерево элементов и [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметку, представляющую <xref:System.Windows.Media.GlyphRun> выходных данных.</span><span class="sxs-lookup"><span data-stu-id="757da-122"><xref:System.Windows.Documents.Glyphs> can be used in the element tree and in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup to represent <xref:System.Windows.Media.GlyphRun> output.</span></span>  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a><span data-ttu-id="757da-123">Элемент Glyphs</span><span class="sxs-lookup"><span data-stu-id="757da-123">The Glyphs Element</span></span>  
 <span data-ttu-id="757da-124"><xref:System.Windows.Documents.Glyphs> Элемент представляет выходные данные <xref:System.Windows.Media.GlyphRun> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="757da-124">The <xref:System.Windows.Documents.Glyphs> element represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="757da-125">Используется следующий синтаксис разметки для описания <xref:System.Windows.Documents.Glyphs> элемента.</span><span class="sxs-lookup"><span data-stu-id="757da-125">The following markup syntax is used to describe the <xref:System.Windows.Documents.Glyphs> element.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="757da-126">Следующие определения свойств соответствуют первым четырем атрибутам в примере разметки.</span><span class="sxs-lookup"><span data-stu-id="757da-126">The following property definitions correspond to the first four attributes in the sample markup.</span></span>  
  
|<span data-ttu-id="757da-127">Свойство.</span><span class="sxs-lookup"><span data-stu-id="757da-127">Property</span></span>|<span data-ttu-id="757da-128">Описание</span><span class="sxs-lookup"><span data-stu-id="757da-128">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|<span data-ttu-id="757da-129">Указывает идентификатор ресурса: имя файла, [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], или ссылку на ресурс в приложение .exe или контейнера.</span><span class="sxs-lookup"><span data-stu-id="757da-129">Specifies a resource identifier: file name, Web [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], or resource reference in the application .exe or container.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|<span data-ttu-id="757da-130">Указывает размер шрифта в единицах графической поверхности (по умолчанию — 0,96 дюйма).</span><span class="sxs-lookup"><span data-stu-id="757da-130">Specifies the font size in drawing surface units (default is .96 inches).</span></span>|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|<span data-ttu-id="757da-131">Задает флаги для полужирного шрифта и курсива.</span><span class="sxs-lookup"><span data-stu-id="757da-131">Specifies flags for bold and Italic styles.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|<span data-ttu-id="757da-132">Задает уровень двунаправленного макета.</span><span class="sxs-lookup"><span data-stu-id="757da-132">Specifies the bidirectional layout level.</span></span> <span data-ttu-id="757da-133">Четные и нулевые значения подразумевают макет слева направо; нечетные значения подразумевают макет справа налево.</span><span class="sxs-lookup"><span data-stu-id="757da-133">Even-numbered and zero values imply left-to-right layout; odd-numbered values imply right-to-left layout.</span></span>|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a><span data-ttu-id="757da-134">Свойство Indices</span><span class="sxs-lookup"><span data-stu-id="757da-134">Indices property</span></span>  
 <span data-ttu-id="757da-135"><xref:System.Windows.Documents.Glyphs.Indices%2A> Свойство является строкой спецификаций глифа.</span><span class="sxs-lookup"><span data-stu-id="757da-135">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property is a string of glyph specifications.</span></span> <span data-ttu-id="757da-136">Если последовательность глифов образует единый кластер, спецификации первого глифа в кластере предшествует спецификация того, сколько глифов и сколько кодовых точек объединяются для формирования кластера.</span><span class="sxs-lookup"><span data-stu-id="757da-136">Where a sequence of glyphs forms a single cluster, the specification of the first glyph in the cluster is preceded by a specification of how many glyphs and how many code points combine to form the cluster.</span></span> <span data-ttu-id="757da-137"><xref:System.Windows.Documents.Glyphs.Indices%2A> Свойство собирает в одной строке следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="757da-137">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property collects in one string the following properties.</span></span>  
  
-   <span data-ttu-id="757da-138">Индексы глифов</span><span class="sxs-lookup"><span data-stu-id="757da-138">Glyph indices</span></span>  
  
-   <span data-ttu-id="757da-139">Дополнительная ширина глифа</span><span class="sxs-lookup"><span data-stu-id="757da-139">Glyph advance widths</span></span>  
  
-   <span data-ttu-id="757da-140">Объединение векторов присоединения глифа</span><span class="sxs-lookup"><span data-stu-id="757da-140">Combining glyph attachment vectors</span></span>  
  
-   <span data-ttu-id="757da-141">Сопоставление кластера от кодовых точек к глифам</span><span class="sxs-lookup"><span data-stu-id="757da-141">Cluster mapping from code points to glyphs</span></span>  
  
-   <span data-ttu-id="757da-142">Флаги глифов</span><span class="sxs-lookup"><span data-stu-id="757da-142">Glyph flags</span></span>  
  
 <span data-ttu-id="757da-143">Спецификация глифа имеет следующий вид.</span><span class="sxs-lookup"><span data-stu-id="757da-143">Each glyph specification has the following form.</span></span>  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a><span data-ttu-id="757da-144">Метрики глифа</span><span class="sxs-lookup"><span data-stu-id="757da-144">Glyph Metrics</span></span>  
 <span data-ttu-id="757da-145">Каждый глиф определяет метрику, задающую способ выравнивания с другими <xref:System.Windows.Documents.Glyphs>.</span><span class="sxs-lookup"><span data-stu-id="757da-145">Each glyph defines metrics that specify how it aligns with other <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="757da-146">На следующем рисунке определяются различные типографические качества двух разных символов глифа.</span><span class="sxs-lookup"><span data-stu-id="757da-146">The following graphic defines the various typographic qualities of two different glyph characters.</span></span>  
  
 <span data-ttu-id="757da-147">![Схема измерений глифа](../../../../docs/framework/wpf/advanced/media/glyph-example.png "glyph_example")</span><span class="sxs-lookup"><span data-stu-id="757da-147">![Diagraph of glyph measurements](../../../../docs/framework/wpf/advanced/media/glyph-example.png "glyph_example")</span></span>  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a><span data-ttu-id="757da-148">Разметка глифа</span><span class="sxs-lookup"><span data-stu-id="757da-148">Glyphs Markup</span></span>  
 <span data-ttu-id="757da-149">В следующем примере кода показано, как использовать различные свойства <xref:System.Windows.Documents.Glyphs> элемент в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="757da-149">The following code example shows how to use various properties of the <xref:System.Windows.Documents.Glyphs> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="757da-150">См. также</span><span class="sxs-lookup"><span data-stu-id="757da-150">See Also</span></span>  
 [<span data-ttu-id="757da-151">Оформление в WPF</span><span class="sxs-lookup"><span data-stu-id="757da-151">Typography in WPF</span></span>](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [<span data-ttu-id="757da-152">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="757da-152">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="757da-153">Text</span><span class="sxs-lookup"><span data-stu-id="757da-153">Text</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)
