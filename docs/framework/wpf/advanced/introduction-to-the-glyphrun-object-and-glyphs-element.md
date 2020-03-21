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
ms.openlocfilehash: 32e8ab7104b8ea2f985395065868ed154ca1e378
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181966"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a><span data-ttu-id="d053f-102">Знакомство с объектом GlyphRun и элементом Glyphs</span><span class="sxs-lookup"><span data-stu-id="d053f-102">Introduction to the GlyphRun Object and Glyphs Element</span></span>
<span data-ttu-id="d053f-103">Эта тема <xref:System.Windows.Media.GlyphRun> описывает объект <xref:System.Windows.Documents.Glyphs> и элемент.</span><span class="sxs-lookup"><span data-stu-id="d053f-103">This topic describes the <xref:System.Windows.Media.GlyphRun> object and the <xref:System.Windows.Documents.Glyphs> element.</span></span>  

<a name="text_glyphrunovw_intro"></a>
## <a name="introduction-to-glyphrun"></a><span data-ttu-id="d053f-104">Общие сведения о GlyphRun</span><span class="sxs-lookup"><span data-stu-id="d053f-104">Introduction to GlyphRun</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="d053f-105">обеспечивает расширенную поддержку текста, включая разметку на уровне глифов с прямым доступом для <xref:System.Windows.Documents.Glyphs> клиентов, которые хотят перехватить и упорствовать текст после форматирования.</span><span class="sxs-lookup"><span data-stu-id="d053f-105">provides advanced text support including glyph-level markup with direct access to <xref:System.Windows.Documents.Glyphs> for customers who want to intercept and persist text after formatting.</span></span> <span data-ttu-id="d053f-106">Эти функции обеспечивают критически важную поддержку различных требований к отрисовке текста в каждом из следующих сценариев.</span><span class="sxs-lookup"><span data-stu-id="d053f-106">These features provide critical support for the different text rendering requirements in each of the following scenarios.</span></span>  
  
1. <span data-ttu-id="d053f-107">Отображение на экране документов фиксированного формата.</span><span class="sxs-lookup"><span data-stu-id="d053f-107">Screen display of fixed-format documents.</span></span>  
  
2. <span data-ttu-id="d053f-108">Сценарии печати.</span><span class="sxs-lookup"><span data-stu-id="d053f-108">Print scenarios.</span></span>  
  
    - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <span data-ttu-id="d053f-109">как язык принтера.</span><span class="sxs-lookup"><span data-stu-id="d053f-109">as a device printer language.</span></span>  
  
    - <span data-ttu-id="d053f-110">Автор документов Microsoft XPS.</span><span class="sxs-lookup"><span data-stu-id="d053f-110">Microsoft XPS Document Writer.</span></span>  
  
    - <span data-ttu-id="d053f-111">Предыдущие драйверы принтера, выход из приложений Win32 в фиксированный формат.</span><span class="sxs-lookup"><span data-stu-id="d053f-111">Previous printer drivers, output from Win32 applications to the fixed format.</span></span>  
  
    - <span data-ttu-id="d053f-112">Формат очереди печати.</span><span class="sxs-lookup"><span data-stu-id="d053f-112">Print spool format.</span></span>  
  
3. <span data-ttu-id="d053f-113">Представление документов с фиксированным форматом, включая клиентов для предыдущих версий Windows и других вычислительных устройств.</span><span class="sxs-lookup"><span data-stu-id="d053f-113">Fixed-format document representation, including clients for previous versions of Windows and other computing devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d053f-114"><xref:System.Windows.Documents.Glyphs>и <xref:System.Windows.Media.GlyphRun> предназначены для сценариев представления документов с фиксированным форматом и печати.</span><span class="sxs-lookup"><span data-stu-id="d053f-114"><xref:System.Windows.Documents.Glyphs> and <xref:System.Windows.Media.GlyphRun> are designed for fixed-format document presentation and print scenarios.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="d053f-115">предоставляет несколько элементов [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] для общего <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.TextBlock>макета и сценариев, таких как и .</span><span class="sxs-lookup"><span data-stu-id="d053f-115">provides several elements for general layout and [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenarios such as <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="d053f-116">Для получения дополнительной информации о [Typography in WPF](typography-in-wpf.md)макете и [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] сценариях см.</span><span class="sxs-lookup"><span data-stu-id="d053f-116">For more information on layout and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios, see the [Typography in WPF](typography-in-wpf.md).</span></span>  
  
<a name="text_glyphrunovw_glyphrunobject"></a>
## <a name="the-glyphrun-object"></a><span data-ttu-id="d053f-117">Объект GlyphRun</span><span class="sxs-lookup"><span data-stu-id="d053f-117">The GlyphRun Object</span></span>  
 <span data-ttu-id="d053f-118">Объект <xref:System.Windows.Media.GlyphRun> представляет собой последовательность глифов из одного лица одного шрифта в одном размере и с единым стилем визуализации.</span><span class="sxs-lookup"><span data-stu-id="d053f-118">The <xref:System.Windows.Media.GlyphRun> object represents a sequence of glyphs from a single face of a single font at a single size, and with a single rendering style.</span></span>  
  
 <span data-ttu-id="d053f-119"><xref:System.Windows.Media.GlyphRun>включает в себя как детали <xref:System.Windows.Documents.Glyphs.Indices%2A> шрифта, такие как глиф и отдельные позиции глифов.</span><span class="sxs-lookup"><span data-stu-id="d053f-119"><xref:System.Windows.Media.GlyphRun> includes both font details such as glyph <xref:System.Windows.Documents.Glyphs.Indices%2A> and individual glyph positions.</span></span> <span data-ttu-id="d053f-120">Он также включает в себя исходные точки кода Unicode, которые был сгенерирован из запуска, офсетную информацию от отображения буфера от персонажа от символов и одного символа.</span><span class="sxs-lookup"><span data-stu-id="d053f-120">It also includes the original Unicode code points the run was generated from, character-to-glyph buffer offset mapping information, and per-character and per-glyph flags.</span></span>  
  
 <span data-ttu-id="d053f-121"><xref:System.Windows.Media.GlyphRun>имеет соответствующий высокий уровень <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span><span class="sxs-lookup"><span data-stu-id="d053f-121"><xref:System.Windows.Media.GlyphRun> has a corresponding high-level <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="d053f-122"><xref:System.Windows.Documents.Glyphs>может быть использован в дереве элементов и в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметке для представления <xref:System.Windows.Media.GlyphRun> вывода.</span><span class="sxs-lookup"><span data-stu-id="d053f-122"><xref:System.Windows.Documents.Glyphs> can be used in the element tree and in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup to represent <xref:System.Windows.Media.GlyphRun> output.</span></span>  
  
<a name="text_glyphrunovw_glyphselement"></a>
## <a name="the-glyphs-element"></a><span data-ttu-id="d053f-123">Элемент Glyphs</span><span class="sxs-lookup"><span data-stu-id="d053f-123">The Glyphs Element</span></span>  
 <span data-ttu-id="d053f-124">Элемент <xref:System.Windows.Documents.Glyphs> представляет выход дюйма <xref:System.Windows.Media.GlyphRun> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d053f-124">The <xref:System.Windows.Documents.Glyphs> element represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="d053f-125">Для описания элемента используется следующий <xref:System.Windows.Documents.Glyphs> синтаксис разметки.</span><span class="sxs-lookup"><span data-stu-id="d053f-125">The following markup syntax is used to describe the <xref:System.Windows.Documents.Glyphs> element.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="d053f-126">Следующие определения свойств соответствуют первым четырем атрибутам в примере разметки.</span><span class="sxs-lookup"><span data-stu-id="d053f-126">The following property definitions correspond to the first four attributes in the sample markup.</span></span>  
  
|<span data-ttu-id="d053f-127">Свойство</span><span class="sxs-lookup"><span data-stu-id="d053f-127">Property</span></span>|<span data-ttu-id="d053f-128">Описание</span><span class="sxs-lookup"><span data-stu-id="d053f-128">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|<span data-ttu-id="d053f-129">Определяети идентификатор ресурса: имя файла, идентификатор web-единого ресурса (URI) или ссылку на ресурсы в приложении .exe или контейнере.</span><span class="sxs-lookup"><span data-stu-id="d053f-129">Specifies a resource identifier: file name, Web uniform resource identifier (URI), or resource reference in the application .exe or container.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|<span data-ttu-id="d053f-130">Указывает размер шрифта в единицах графической поверхности (по умолчанию — 0,96 дюйма).</span><span class="sxs-lookup"><span data-stu-id="d053f-130">Specifies the font size in drawing surface units (default is .96 inches).</span></span>|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|<span data-ttu-id="d053f-131">Задает флаги для полужирного шрифта и курсива.</span><span class="sxs-lookup"><span data-stu-id="d053f-131">Specifies flags for bold and Italic styles.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|<span data-ttu-id="d053f-132">Задает уровень двунаправленного макета.</span><span class="sxs-lookup"><span data-stu-id="d053f-132">Specifies the bidirectional layout level.</span></span> <span data-ttu-id="d053f-133">Четные и нулевые значения подразумевают макет слева направо; нечетные значения подразумевают макет справа налево.</span><span class="sxs-lookup"><span data-stu-id="d053f-133">Even-numbered and zero values imply left-to-right layout; odd-numbered values imply right-to-left layout.</span></span>|  
  
<a name="text_glyphrunovw_indicesproperty"></a>
### <a name="indices-property"></a><span data-ttu-id="d053f-134">Свойство Indices</span><span class="sxs-lookup"><span data-stu-id="d053f-134">Indices property</span></span>  
 <span data-ttu-id="d053f-135">Свойство <xref:System.Windows.Documents.Glyphs.Indices%2A> представляет собой строку спецификаций глифа.</span><span class="sxs-lookup"><span data-stu-id="d053f-135">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property is a string of glyph specifications.</span></span> <span data-ttu-id="d053f-136">Если последовательность глифов образует единый кластер, спецификации первого глифа в кластере предшествует спецификация того, сколько глифов и сколько кодовых точек объединяются для формирования кластера.</span><span class="sxs-lookup"><span data-stu-id="d053f-136">Where a sequence of glyphs forms a single cluster, the specification of the first glyph in the cluster is preceded by a specification of how many glyphs and how many code points combine to form the cluster.</span></span> <span data-ttu-id="d053f-137">Свойство <xref:System.Windows.Documents.Glyphs.Indices%2A> собирает в одной строке следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="d053f-137">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property collects in one string the following properties.</span></span>  
  
- <span data-ttu-id="d053f-138">Индексы глифов</span><span class="sxs-lookup"><span data-stu-id="d053f-138">Glyph indices</span></span>  
  
- <span data-ttu-id="d053f-139">Дополнительная ширина глифа</span><span class="sxs-lookup"><span data-stu-id="d053f-139">Glyph advance widths</span></span>  
  
- <span data-ttu-id="d053f-140">Объединение векторов присоединения глифа</span><span class="sxs-lookup"><span data-stu-id="d053f-140">Combining glyph attachment vectors</span></span>  
  
- <span data-ttu-id="d053f-141">Сопоставление кластера от кодовых точек к глифам</span><span class="sxs-lookup"><span data-stu-id="d053f-141">Cluster mapping from code points to glyphs</span></span>  
  
- <span data-ttu-id="d053f-142">Флаги глифов</span><span class="sxs-lookup"><span data-stu-id="d053f-142">Glyph flags</span></span>  
  
 <span data-ttu-id="d053f-143">Спецификация глифа имеет следующий вид.</span><span class="sxs-lookup"><span data-stu-id="d053f-143">Each glyph specification has the following form.</span></span>  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>
## <a name="glyph-metrics"></a><span data-ttu-id="d053f-144">Метрики глифа</span><span class="sxs-lookup"><span data-stu-id="d053f-144">Glyph Metrics</span></span>  
 <span data-ttu-id="d053f-145">Каждый глиф определяет метрики, определяющие, как он выравнивается с другими. <xref:System.Windows.Documents.Glyphs></span><span class="sxs-lookup"><span data-stu-id="d053f-145">Each glyph defines metrics that specify how it aligns with other <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="d053f-146">На следующем рисунке определяются различные типографические качества двух разных символов глифа.</span><span class="sxs-lookup"><span data-stu-id="d053f-146">The following graphic defines the various typographic qualities of two different glyph characters.</span></span>  
  
 <span data-ttu-id="d053f-147">![Схема измерений глифа](./media/glyph-example.png "glyph_example")</span><span class="sxs-lookup"><span data-stu-id="d053f-147">![Diagraph of glyph measurements](./media/glyph-example.png "glyph_example")</span></span>  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>
## <a name="glyphs-markup"></a><span data-ttu-id="d053f-148">Разметка глифа</span><span class="sxs-lookup"><span data-stu-id="d053f-148">Glyphs Markup</span></span>  
 <span data-ttu-id="d053f-149">Следующий пример кода показывает, как <xref:System.Windows.Documents.Glyphs> использовать [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]различные свойства элемента в.</span><span class="sxs-lookup"><span data-stu-id="d053f-149">The following code example shows how to use various properties of the <xref:System.Windows.Documents.Glyphs> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d053f-150">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d053f-150">See also</span></span>

- [<span data-ttu-id="d053f-151">Оформление в WPF</span><span class="sxs-lookup"><span data-stu-id="d053f-151">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="d053f-152">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="d053f-152">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="d053f-153">Текст</span><span class="sxs-lookup"><span data-stu-id="d053f-153">Text</span></span>](optimizing-performance-text.md)
