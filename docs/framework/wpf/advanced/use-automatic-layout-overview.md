---
title: Обзор использования автоматической разметки
ms.date: 03/30/2017
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
ms.openlocfilehash: 0253c57f080705b648d9f416368d0fe974ac83ab
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834671"
---
# <a name="use-automatic-layout-overview"></a><span data-ttu-id="3118b-102">Обзор использования автоматической разметки</span><span class="sxs-lookup"><span data-stu-id="3118b-102">Use Automatic Layout Overview</span></span>

<span data-ttu-id="3118b-103">В этом разделе представлены рекомендации для разработчиков по написанию приложений [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] с возможностью локализации [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3118b-103">This topic introduces guidelines for developers on how to write [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications with localizable [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)].</span></span> <span data-ttu-id="3118b-104">В прошлом процесс локализации пользовательского интерфейса осуществлялся в течение длительного времени.</span><span class="sxs-lookup"><span data-stu-id="3118b-104">In the past, localization of a UI was a time consuming process.</span></span> <span data-ttu-id="3118b-105">Каждый язык, для которого был адаптирован пользовательский интерфейс, требовал коррекции пикселя в пикселях.</span><span class="sxs-lookup"><span data-stu-id="3118b-105">Each language that the UI was adapted for required a pixel by pixel adjustment.</span></span> <span data-ttu-id="3118b-106">На сегодняшний день с верным стандартом проектирования и написания кода [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] может быть создан таким образом, чтобы локализаторы имели меньше изменений и их расположения.</span><span class="sxs-lookup"><span data-stu-id="3118b-106">Today with the right design and right coding standards, [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] can be constructed so that localizers have less resizing and repositioning to do.</span></span> <span data-ttu-id="3118b-107">Подход к написанию приложений, которые могут быть более легко изменять размер и положение, называется автоматическим макетом и может быть достигнут с помощью конструкции приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3118b-107">The approach to writing applications that can be more easily resized and repositioned is called automatic layout, and can be achieved by using [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application design.</span></span>

<a name="advantages_of_autolayout"></a>

## <a name="advantages-of-using-automatic-layout"></a><span data-ttu-id="3118b-108">Преимущества использования автоматической разметки</span><span class="sxs-lookup"><span data-stu-id="3118b-108">Advantages of Using Automatic Layout</span></span>

<span data-ttu-id="3118b-109">Поскольку система презентации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] является мощным и гибкой, она обеспечивает возможность разметки элементов в приложении, которые могут быть скорректированы в соответствии с требованиями различных языков.</span><span class="sxs-lookup"><span data-stu-id="3118b-109">Because the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presentation system is powerful and flexible, it provides the ability to layout elements in an application that can be adjusted to fit the requirements of different languages.</span></span> <span data-ttu-id="3118b-110">В следующем списке отмечены преимущества автоматической разметки.</span><span class="sxs-lookup"><span data-stu-id="3118b-110">The following list points out some of the advantages of automatic layout.</span></span>

- <span data-ttu-id="3118b-111">Пользовательский интерфейс отображается хорошо на любом языке.</span><span class="sxs-lookup"><span data-stu-id="3118b-111">UI displays well  in any language.</span></span>

- <span data-ttu-id="3118b-112">Снижается необходимость перенастраивать расположение и размер элементов управления после перевода текста.</span><span class="sxs-lookup"><span data-stu-id="3118b-112">Reduces the need to readjust position and size of controls after text is translated.</span></span>

- <span data-ttu-id="3118b-113">Снижается необходимость перенастраивать размер окна.</span><span class="sxs-lookup"><span data-stu-id="3118b-113">Reduces the need to readjust window size.</span></span>

- <span data-ttu-id="3118b-114">Макет пользовательского интерфейса правильно отображается на любом языке.</span><span class="sxs-lookup"><span data-stu-id="3118b-114">UI layout renders properly in any language.</span></span>

- <span data-ttu-id="3118b-115">Локализация может быть сведена не многим более чем к переводу строки.</span><span class="sxs-lookup"><span data-stu-id="3118b-115">Localization can be reduced to the point that it is little more than string translation.</span></span>

<a name="autolayout_controls"></a>

## <a name="automatic-layout-and-controls"></a><span data-ttu-id="3118b-116">Автоматическая разметка и элементы управления</span><span class="sxs-lookup"><span data-stu-id="3118b-116">Automatic Layout and Controls</span></span>

<span data-ttu-id="3118b-117">Автоматическая разметка позволяет приложению устанавливать размер элемента управления автоматически.</span><span class="sxs-lookup"><span data-stu-id="3118b-117">Automatic layout enables an application to adjust the size of a control automatically.</span></span> <span data-ttu-id="3118b-118">Например, элемент управления может измениться, чтобы вместить строку целиком.</span><span class="sxs-lookup"><span data-stu-id="3118b-118">For example, a control can change to accommodate the length of a string.</span></span> <span data-ttu-id="3118b-119">Эта возможность позволяет локализаторам перевести строку; больше не требуется изменять размер элемента управления, чтобы полностью отобразить переведенный текст.</span><span class="sxs-lookup"><span data-stu-id="3118b-119">This capability enables  localizers to translate the string; they no longer need to resize the control to fit the translated text.</span></span> <span data-ttu-id="3118b-120">В следующем примере создается кнопка с текстом на английском языке.</span><span class="sxs-lookup"><span data-stu-id="3118b-120">The following example creates a button with English content.</span></span>

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]

<span data-ttu-id="3118b-121">В этом примере все, что нужно сделать, чтобы подпись кнопки была на испанском языке, — это изменить текст.</span><span class="sxs-lookup"><span data-stu-id="3118b-121">In the example, all you have to do to make a Spanish button is change the text.</span></span> <span data-ttu-id="3118b-122">Например, примененная к объекту директива</span><span class="sxs-lookup"><span data-stu-id="3118b-122">For example,</span></span>

[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]

<span data-ttu-id="3118b-123">На следующем рисунке показаны выходные данные примеров кода:</span><span class="sxs-lookup"><span data-stu-id="3118b-123">The following graphic shows the output of the code samples:</span></span>

![Та же кнопка с текстовой подписью на различных языках](./media/use-automatic-layout-overview/auto-resizable-button.png)

<a name="autolayout_coding"></a>

## <a name="automatic-layout-and-coding-standards"></a><span data-ttu-id="3118b-125">Автоматическая разметка и стандарты кодирования</span><span class="sxs-lookup"><span data-stu-id="3118b-125">Automatic Layout and Coding Standards</span></span>

<span data-ttu-id="3118b-126">При использовании автоматического макета требуется набор стандартов и правил разработки кода и проектирования для создания полностью локализуемого пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3118b-126">Using the automatic layout approach requires a set of coding and design standards and rules to produce a fully localizable UI.</span></span> <span data-ttu-id="3118b-127">Следующие рекомендации предназначены для помощи в кодировании автоматической разметки.</span><span class="sxs-lookup"><span data-stu-id="3118b-127">The following guidelines will aid your automatic layout coding.</span></span>

<span data-ttu-id="3118b-128">**Не использовать абсолютные позиции**</span><span class="sxs-lookup"><span data-stu-id="3118b-128">**Do not use absolute positions**</span></span>

- <span data-ttu-id="3118b-129">Не используйте <xref:System.Windows.Controls.Canvas>, так как он размещает элементы абсолютно.</span><span class="sxs-lookup"><span data-stu-id="3118b-129">Do not use <xref:System.Windows.Controls.Canvas> because it positions elements absolutely.</span></span>

- <span data-ttu-id="3118b-130">Для позиционирования элементов управления используйте <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel> и <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="3118b-130">Use <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, and <xref:System.Windows.Controls.Grid> to position controls.</span></span>

<span data-ttu-id="3118b-131">Обсуждение различных типов панелей см. в разделе [Общие сведения о панелях](../controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3118b-131">For a discussion about various types of panels, see [Panels Overview](../controls/panels-overview.md).</span></span>

<span data-ttu-id="3118b-132">**Не устанавливайте фиксированный размер окна**</span><span class="sxs-lookup"><span data-stu-id="3118b-132">**Do not set a fixed size for a window**</span></span>

- <span data-ttu-id="3118b-133">Используйте ключевое слово <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3118b-133">Use <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3118b-134">Пример:</span><span class="sxs-lookup"><span data-stu-id="3118b-134">For example:</span></span>

  [!code-xaml[LocalizationGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]

<span data-ttu-id="3118b-135">**Добавление <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span><span class="sxs-lookup"><span data-stu-id="3118b-135">**Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span></span>

- <span data-ttu-id="3118b-136">Добавьте <xref:System.Windows.FrameworkElement.FlowDirection%2A> в корневой элемент приложения.</span><span class="sxs-lookup"><span data-stu-id="3118b-136">Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A> to the root element of your application.</span></span>

  <span data-ttu-id="3118b-137">WPF предоставляет удобный способ поддержки горизонтальных, двунаправленных и вертикальных макетов.</span><span class="sxs-lookup"><span data-stu-id="3118b-137">WPF provides a convenient way to support horizontal, bidirectional, and vertical layouts.</span></span> <span data-ttu-id="3118b-138">В платформе Presentation Framework свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A> можно использовать для определения макета.</span><span class="sxs-lookup"><span data-stu-id="3118b-138">In presentation framework, the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property can be used to define layout.</span></span> <span data-ttu-id="3118b-139">Ниже перечислены шаблоны направления текста.</span><span class="sxs-lookup"><span data-stu-id="3118b-139">The flow-direction patterns are:</span></span>

  - <span data-ttu-id="3118b-140"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (Лртб) — горизонтальный макет для латиницы, восточноазиатских языков и т. д.</span><span class="sxs-lookup"><span data-stu-id="3118b-140"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb) — horizontal layout for Latin, East Asian, and so forth.</span></span>

  - <span data-ttu-id="3118b-141"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (Рлтб) — двунаправленный для арабского, иврита и т. д.</span><span class="sxs-lookup"><span data-stu-id="3118b-141"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb) — bidirectional for Arabic, Hebrew, and so forth.</span></span>

<span data-ttu-id="3118b-142">**Использование составных шрифтов вместо физических шрифтов**</span><span class="sxs-lookup"><span data-stu-id="3118b-142">**Use composite fonts instead of physical fonts**</span></span>

- <span data-ttu-id="3118b-143">При использовании составных шрифтов свойство <xref:System.Windows.Controls.Control.FontFamily%2A> не обязательно должно быть локализовано.</span><span class="sxs-lookup"><span data-stu-id="3118b-143">With composite fonts, the <xref:System.Windows.Controls.Control.FontFamily%2A> property does not need to be localized.</span></span>

- <span data-ttu-id="3118b-144">Разработчики могут использовать один из следующих шрифтов или создать свой собственный.</span><span class="sxs-lookup"><span data-stu-id="3118b-144">Developers can use one of the following fonts or create their own.</span></span>

  - <span data-ttu-id="3118b-145">Глобальный пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="3118b-145">Global User Interface</span></span>
  - <span data-ttu-id="3118b-146">Global San Serif</span><span class="sxs-lookup"><span data-stu-id="3118b-146">Global San Serif</span></span>
  - <span data-ttu-id="3118b-147">Global Serif</span><span class="sxs-lookup"><span data-stu-id="3118b-147">Global Serif</span></span>

<span data-ttu-id="3118b-148">**Добавить XML: lang**</span><span class="sxs-lookup"><span data-stu-id="3118b-148">**Add xml:lang**</span></span>

- <span data-ttu-id="3118b-149">Добавьте атрибут `xml:lang` в корневой элемент пользовательского интерфейса, например `xml:lang="en-US"` для приложения на английском языке.</span><span class="sxs-lookup"><span data-stu-id="3118b-149">Add the `xml:lang` attribute in the root element of your UI, such as `xml:lang="en-US"` for an English application.</span></span>

- <span data-ttu-id="3118b-150">Поскольку составные шрифты используют `xml:lang` для определения используемого шрифта, установите это свойство для поддержки многоязычных сценариев.</span><span class="sxs-lookup"><span data-stu-id="3118b-150">Because composite fonts use `xml:lang` to determine what font to use, set this property to support multilingual scenarios.</span></span>

<a name="autolay_grids"></a>

## <a name="automatic-layout-and-grids"></a><span data-ttu-id="3118b-151">Автоматическая разметка и сетки</span><span class="sxs-lookup"><span data-stu-id="3118b-151">Automatic Layout and Grids</span></span>

<span data-ttu-id="3118b-152">Элемент <xref:System.Windows.Controls.Grid> полезен для автоматической разметки, так как он позволяет разработчику располагать элементы.</span><span class="sxs-lookup"><span data-stu-id="3118b-152">The <xref:System.Windows.Controls.Grid> element, is useful for automatic layout because it enables a developer to position elements.</span></span> <span data-ttu-id="3118b-153">Элемент управления <xref:System.Windows.Controls.Grid> способен распределять доступное пространство между его дочерними элементами с помощью упорядочения по столбцам и строкам.</span><span class="sxs-lookup"><span data-stu-id="3118b-153">A <xref:System.Windows.Controls.Grid> control is capable of distributing the available space among its child elements, using a column and row arrangement.</span></span> <span data-ttu-id="3118b-154">Элементы пользовательского интерфейса могут охватывать несколько ячеек, и можно использовать сетки в сетках.</span><span class="sxs-lookup"><span data-stu-id="3118b-154">The UI elements can span multiple cells, and it is possible to have grids within grids.</span></span> <span data-ttu-id="3118b-155">Сетки полезны, так как они позволяют создавать и позиционировать сложный пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="3118b-155">Grids are useful because they enable you to create and position complex UI.</span></span> <span data-ttu-id="3118b-156">В следующем примере демонстрируется использование сетки для размещения нескольких кнопок и текста.</span><span class="sxs-lookup"><span data-stu-id="3118b-156">The following example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="3118b-157">Обратите внимание, что для высоты и ширины ячеек задано значение <xref:System.Windows.GridUnitType.Auto>; Таким образом, ячейка, содержащая кнопку с изображением, изменяется в соответствии с изображением.</span><span class="sxs-lookup"><span data-stu-id="3118b-157">Notice that the height and width of the cells are set to <xref:System.Windows.GridUnitType.Auto>; therefore, the cell that contains the button with an image adjusts to fit the image.</span></span>

[!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]

<span data-ttu-id="3118b-158">На приведенном ниже рисунке показана сетка, созданная с помощью предыдущего кода.</span><span class="sxs-lookup"><span data-stu-id="3118b-158">The following graphic shows the grid produced by the previous code.</span></span>

<span data-ttu-id="3118b-159">![Пример]сетки(./media/glob-grid.png "glob_grid") Grid</span><span class="sxs-lookup"><span data-stu-id="3118b-159">![Grid example](./media/glob-grid.png "glob_grid") Grid</span></span>

<a name="autolay_grids_issharedsizescope"></a>

## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a><span data-ttu-id="3118b-160">Автоматическая разметка и сетки, использующие свойство IsSharedSizeScope</span><span class="sxs-lookup"><span data-stu-id="3118b-160">Automatic Layout and Grids Using the IsSharedSizeScope Property</span></span>

<span data-ttu-id="3118b-161">Элемент <xref:System.Windows.Controls.Grid> полезен в локализуемых приложениях для создания элементов управления, которые корректируются в соответствии с содержимым.</span><span class="sxs-lookup"><span data-stu-id="3118b-161">A <xref:System.Windows.Controls.Grid> element is useful in localizable applications to create controls that adjust to fit content.</span></span> <span data-ttu-id="3118b-162">Однако иногда требуется, чтобы элемент управления сохранял определенный размер, независимо от содержимого.</span><span class="sxs-lookup"><span data-stu-id="3118b-162">However, at times you want controls to maintain a particular size regardless of content.</span></span> <span data-ttu-id="3118b-163">Например, если имеются кнопки ОК, "Отмена" и "Обзор", то, возможно, не требуется выравнивать размер этих кнопок по размеру содержимого.</span><span class="sxs-lookup"><span data-stu-id="3118b-163">For example, if you have "OK", "Cancel" and "Browse" buttons you probably do not want the buttons sized to fit the content.</span></span> <span data-ttu-id="3118b-164">В этом случае присоединенное свойство <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> полезно для совместного использования одного и того же размера между несколькими элементами сетки.</span><span class="sxs-lookup"><span data-stu-id="3118b-164">In this case the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> attached property is useful for sharing the same sizing among multiple grid elements.</span></span> <span data-ttu-id="3118b-165">В следующем примере показано, как совместно использовать данные о размере столбцов и строк между несколькими элементами <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="3118b-165">The following example demonstrates how to share column and row sizing data between multiple <xref:System.Windows.Controls.Grid> elements.</span></span>

[!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]

> [!NOTE]
> <span data-ttu-id="3118b-166">Полный пример кода см. в разделе [совместное использование свойств размера между сетками](../controls/how-to-share-sizing-properties-between-grids.md).</span><span class="sxs-lookup"><span data-stu-id="3118b-166">For the complete code sample, see [Share Sizing Properties Between Grids](../controls/how-to-share-sizing-properties-between-grids.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3118b-167">См. также</span><span class="sxs-lookup"><span data-stu-id="3118b-167">See also</span></span>

- [<span data-ttu-id="3118b-168">Глобализация для WPF</span><span class="sxs-lookup"><span data-stu-id="3118b-168">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="3118b-169">Использование автоматической разметки для создания кнопки</span><span class="sxs-lookup"><span data-stu-id="3118b-169">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
- [<span data-ttu-id="3118b-170">Использование сетки для автоматической разметки</span><span class="sxs-lookup"><span data-stu-id="3118b-170">Use a Grid for Automatic Layout</span></span>](how-to-use-a-grid-for-automatic-layout.md)
