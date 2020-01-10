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
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a><span data-ttu-id="0ae85-102">Знакомство с объектом GlyphRun и элементом Glyphs</span><span class="sxs-lookup"><span data-stu-id="0ae85-102">Introduction to the GlyphRun Object and Glyphs Element</span></span>
<span data-ttu-id="0ae85-103">В этом разделе описывается объект <xref:System.Windows.Media.GlyphRun> и элемент <xref:System.Windows.Documents.Glyphs>.</span><span class="sxs-lookup"><span data-stu-id="0ae85-103">This topic describes the <xref:System.Windows.Media.GlyphRun> object and the <xref:System.Windows.Documents.Glyphs> element.</span></span>  

<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a><span data-ttu-id="0ae85-104">Общие сведения о GlyphRun</span><span class="sxs-lookup"><span data-stu-id="0ae85-104">Introduction to GlyphRun</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="0ae85-105">обеспечивает расширенную поддержку текста, включая разметку на уровне глифов с прямым доступом к <xref:System.Windows.Documents.Glyphs> для клиентов, которым требуется перехватывать и сохранять текст после форматирования.</span><span class="sxs-lookup"><span data-stu-id="0ae85-105">provides advanced text support including glyph-level markup with direct access to <xref:System.Windows.Documents.Glyphs> for customers who want to intercept and persist text after formatting.</span></span> <span data-ttu-id="0ae85-106">Эти функции обеспечивают критически важную поддержку различных требований к отрисовке текста в каждом из следующих сценариев.</span><span class="sxs-lookup"><span data-stu-id="0ae85-106">These features provide critical support for the different text rendering requirements in each of the following scenarios.</span></span>  
  
1. <span data-ttu-id="0ae85-107">Отображение на экране документов фиксированного формата.</span><span class="sxs-lookup"><span data-stu-id="0ae85-107">Screen display of fixed-format documents.</span></span>  
  
2. <span data-ttu-id="0ae85-108">Сценарии печати.</span><span class="sxs-lookup"><span data-stu-id="0ae85-108">Print scenarios.</span></span>  
  
    - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <span data-ttu-id="0ae85-109">как язык принтера.</span><span class="sxs-lookup"><span data-stu-id="0ae85-109">as a device printer language.</span></span>  
  
    - <span data-ttu-id="0ae85-110">Средство записи документов XPS (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="0ae85-110">Microsoft XPS Document Writer.</span></span>  
  
    - <span data-ttu-id="0ae85-111">Предыдущие драйверы принтера, вывод из приложений Win32 в фиксированный формат.</span><span class="sxs-lookup"><span data-stu-id="0ae85-111">Previous printer drivers, output from Win32 applications to the fixed format.</span></span>  
  
    - <span data-ttu-id="0ae85-112">Формат очереди печати.</span><span class="sxs-lookup"><span data-stu-id="0ae85-112">Print spool format.</span></span>  
  
3. <span data-ttu-id="0ae85-113">Представление документов фиксированного формата, включая клиенты предыдущих версий Windows и других вычислительных устройств.</span><span class="sxs-lookup"><span data-stu-id="0ae85-113">Fixed-format document representation, including clients for previous versions of Windows and other computing devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ae85-114"><xref:System.Windows.Documents.Glyphs> и <xref:System.Windows.Media.GlyphRun> предназначены для представления документов фиксированного формата и сценариев печати.</span><span class="sxs-lookup"><span data-stu-id="0ae85-114"><xref:System.Windows.Documents.Glyphs> and <xref:System.Windows.Media.GlyphRun> are designed for fixed-format document presentation and print scenarios.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="0ae85-115">предоставляет несколько элементов для общего макета и [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] сценариев, таких как <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="0ae85-115">provides several elements for general layout and [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenarios such as <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="0ae85-116">Дополнительные сведения о макете и сценариях [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] см. в статье [Оформление в WPF](typography-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="0ae85-116">For more information on layout and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios, see the [Typography in WPF](typography-in-wpf.md).</span></span>  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a><span data-ttu-id="0ae85-117">Объект GlyphRun</span><span class="sxs-lookup"><span data-stu-id="0ae85-117">The GlyphRun Object</span></span>  
 <span data-ttu-id="0ae85-118">Объект <xref:System.Windows.Media.GlyphRun> представляет последовательность глифов из одной грани одного шрифта с одним размером и с одним стилем отрисовки.</span><span class="sxs-lookup"><span data-stu-id="0ae85-118">The <xref:System.Windows.Media.GlyphRun> object represents a sequence of glyphs from a single face of a single font at a single size, and with a single rendering style.</span></span>  
  
 <span data-ttu-id="0ae85-119"><xref:System.Windows.Media.GlyphRun> включает как сведения о шрифтах, такие как <xref:System.Windows.Documents.Glyphs.Indices%2A> глифов, так и отдельные позиции глифов.</span><span class="sxs-lookup"><span data-stu-id="0ae85-119"><xref:System.Windows.Media.GlyphRun> includes both font details such as glyph <xref:System.Windows.Documents.Glyphs.Indices%2A> and individual glyph positions.</span></span> <span data-ttu-id="0ae85-120">Он также включает исходные кодовые точки Юникода, из которых был создан запуск, сведения о сопоставлении смещения буфера символов и глифов, а также флаги отдельных символов и глифов.</span><span class="sxs-lookup"><span data-stu-id="0ae85-120">It also includes the original Unicode code points the run was generated from, character-to-glyph buffer offset mapping information, and per-character and per-glyph flags.</span></span>  
  
 <span data-ttu-id="0ae85-121"><xref:System.Windows.Media.GlyphRun> имеет соответствующий высокоуровневый <xref:System.Windows.FrameworkElement><xref:System.Windows.Documents.Glyphs>.</span><span class="sxs-lookup"><span data-stu-id="0ae85-121"><xref:System.Windows.Media.GlyphRun> has a corresponding high-level <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="0ae85-122"><xref:System.Windows.Documents.Glyphs> можно использовать в дереве элементов и в разметке [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для представления выходных данных <xref:System.Windows.Media.GlyphRun>.</span><span class="sxs-lookup"><span data-stu-id="0ae85-122"><xref:System.Windows.Documents.Glyphs> can be used in the element tree and in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup to represent <xref:System.Windows.Media.GlyphRun> output.</span></span>  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a><span data-ttu-id="0ae85-123">Элемент Glyphs</span><span class="sxs-lookup"><span data-stu-id="0ae85-123">The Glyphs Element</span></span>  
 <span data-ttu-id="0ae85-124">Элемент <xref:System.Windows.Documents.Glyphs> представляет выходные данные <xref:System.Windows.Media.GlyphRun> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ae85-124">The <xref:System.Windows.Documents.Glyphs> element represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="0ae85-125">Для описания элемента <xref:System.Windows.Documents.Glyphs> используется следующий синтаксис разметки.</span><span class="sxs-lookup"><span data-stu-id="0ae85-125">The following markup syntax is used to describe the <xref:System.Windows.Documents.Glyphs> element.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="0ae85-126">Следующие определения свойств соответствуют первым четырем атрибутам в примере разметки.</span><span class="sxs-lookup"><span data-stu-id="0ae85-126">The following property definitions correspond to the first four attributes in the sample markup.</span></span>  
  
|<span data-ttu-id="0ae85-127">Идентификаторы</span><span class="sxs-lookup"><span data-stu-id="0ae85-127">Property</span></span>|<span data-ttu-id="0ae85-128">Описание</span><span class="sxs-lookup"><span data-stu-id="0ae85-128">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|<span data-ttu-id="0ae85-129">Указывает идентификатор ресурса: имя файла, универсальный код ресурса (URI) или ссылку на ресурс в файле Application. exe или контейнере.</span><span class="sxs-lookup"><span data-stu-id="0ae85-129">Specifies a resource identifier: file name, Web uniform resource identifier (URI), or resource reference in the application .exe or container.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|<span data-ttu-id="0ae85-130">Указывает размер шрифта в единицах графической поверхности (по умолчанию — 0,96 дюйма).</span><span class="sxs-lookup"><span data-stu-id="0ae85-130">Specifies the font size in drawing surface units (default is .96 inches).</span></span>|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|<span data-ttu-id="0ae85-131">Задает флаги для полужирного шрифта и курсива.</span><span class="sxs-lookup"><span data-stu-id="0ae85-131">Specifies flags for bold and Italic styles.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|<span data-ttu-id="0ae85-132">Задает уровень двунаправленного макета.</span><span class="sxs-lookup"><span data-stu-id="0ae85-132">Specifies the bidirectional layout level.</span></span> <span data-ttu-id="0ae85-133">Четные и нулевые значения подразумевают макет слева направо; нечетные значения подразумевают макет справа налево.</span><span class="sxs-lookup"><span data-stu-id="0ae85-133">Even-numbered and zero values imply left-to-right layout; odd-numbered values imply right-to-left layout.</span></span>|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a><span data-ttu-id="0ae85-134">Свойство Indices</span><span class="sxs-lookup"><span data-stu-id="0ae85-134">Indices property</span></span>  
 <span data-ttu-id="0ae85-135">Свойство <xref:System.Windows.Documents.Glyphs.Indices%2A> — это строка спецификаций глифов.</span><span class="sxs-lookup"><span data-stu-id="0ae85-135">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property is a string of glyph specifications.</span></span> <span data-ttu-id="0ae85-136">Если последовательность глифов образует единый кластер, спецификации первого глифа в кластере предшествует спецификация того, сколько глифов и сколько кодовых точек объединяются для формирования кластера.</span><span class="sxs-lookup"><span data-stu-id="0ae85-136">Where a sequence of glyphs forms a single cluster, the specification of the first glyph in the cluster is preceded by a specification of how many glyphs and how many code points combine to form the cluster.</span></span> <span data-ttu-id="0ae85-137">Свойство <xref:System.Windows.Documents.Glyphs.Indices%2A> собирает в одной строке следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="0ae85-137">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property collects in one string the following properties.</span></span>  
  
- <span data-ttu-id="0ae85-138">Индексы глифов</span><span class="sxs-lookup"><span data-stu-id="0ae85-138">Glyph indices</span></span>  
  
- <span data-ttu-id="0ae85-139">Дополнительная ширина глифа</span><span class="sxs-lookup"><span data-stu-id="0ae85-139">Glyph advance widths</span></span>  
  
- <span data-ttu-id="0ae85-140">Объединение векторов присоединения глифа</span><span class="sxs-lookup"><span data-stu-id="0ae85-140">Combining glyph attachment vectors</span></span>  
  
- <span data-ttu-id="0ae85-141">Сопоставление кластера от кодовых точек к глифам</span><span class="sxs-lookup"><span data-stu-id="0ae85-141">Cluster mapping from code points to glyphs</span></span>  
  
- <span data-ttu-id="0ae85-142">Флаги глифов</span><span class="sxs-lookup"><span data-stu-id="0ae85-142">Glyph flags</span></span>  
  
 <span data-ttu-id="0ae85-143">Спецификация глифа имеет следующий вид.</span><span class="sxs-lookup"><span data-stu-id="0ae85-143">Each glyph specification has the following form.</span></span>  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a><span data-ttu-id="0ae85-144">Метрики глифа</span><span class="sxs-lookup"><span data-stu-id="0ae85-144">Glyph Metrics</span></span>  
 <span data-ttu-id="0ae85-145">Каждый глиф определяет метрики, указывающие, как оно соответствует другим <xref:System.Windows.Documents.Glyphs>.</span><span class="sxs-lookup"><span data-stu-id="0ae85-145">Each glyph defines metrics that specify how it aligns with other <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="0ae85-146">На следующем рисунке определяются различные типографические качества двух разных символов глифа.</span><span class="sxs-lookup"><span data-stu-id="0ae85-146">The following graphic defines the various typographic qualities of two different glyph characters.</span></span>  
  
 <span data-ttu-id="0ae85-147">![Схема измерений глифов](./media/glyph-example.png "glyph_example")</span><span class="sxs-lookup"><span data-stu-id="0ae85-147">![Diagraph of glyph measurements](./media/glyph-example.png "glyph_example")</span></span>  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a><span data-ttu-id="0ae85-148">Разметка глифа</span><span class="sxs-lookup"><span data-stu-id="0ae85-148">Glyphs Markup</span></span>  
 <span data-ttu-id="0ae85-149">В следующем примере кода показано, как использовать различные свойства элемента <xref:System.Windows.Documents.Glyphs> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ae85-149">The following code example shows how to use various properties of the <xref:System.Windows.Documents.Glyphs> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0ae85-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="0ae85-150">See also</span></span>

- [<span data-ttu-id="0ae85-151">Оформление в WPF</span><span class="sxs-lookup"><span data-stu-id="0ae85-151">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="0ae85-152">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="0ae85-152">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="0ae85-153">Text</span><span class="sxs-lookup"><span data-stu-id="0ae85-153">Text</span></span>](optimizing-performance-text.md)
