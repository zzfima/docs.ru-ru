---
title: Практическое руководство. Создание оформления текста
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], baseline
- text [WPF], decorations
- fonts [WPF], underline
- fonts [WPF], overline
- strikethrough type [WPF]
- fonts [WPF], strikethrough
- overline type [WPF]
- underline type [WPF]
- typography [WPF], text decorations
- baseline type [WPF]
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
ms.openlocfilehash: c16073dd2413c1258f4875ac4118e0656d29b171
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545413"
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="8dbda-102">Практическое руководство. Создание оформления текста</span><span class="sxs-lookup"><span data-stu-id="8dbda-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="8dbda-103">Объект <xref:System.Windows.TextDecoration> объект является визуальным декоративным элементом, можно добавить в текст.</span><span class="sxs-lookup"><span data-stu-id="8dbda-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="8dbda-104">Существует четыре типа оформления текста: подчеркивание, базовых показателей, зачеркивания и надчеркивания.</span><span class="sxs-lookup"><span data-stu-id="8dbda-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="8dbda-105">В следующем примере показано расположений украшений текста относительно текста.</span><span class="sxs-lookup"><span data-stu-id="8dbda-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 <span data-ttu-id="8dbda-106">![Схема расположений украшений текста](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")</span><span class="sxs-lookup"><span data-stu-id="8dbda-106">![Diagram of text decoration locations](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")</span></span>  
<span data-ttu-id="8dbda-107">Пример типов оформления текста</span><span class="sxs-lookup"><span data-stu-id="8dbda-107">Example of text decoration types</span></span>  
  
 <span data-ttu-id="8dbda-108">Чтобы добавить оформление текста в текст, создайте <xref:System.Windows.TextDecoration> объекта и измените его свойства.</span><span class="sxs-lookup"><span data-stu-id="8dbda-108">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="8dbda-109">Используйте <xref:System.Windows.TextDecoration.Location%2A> свойство, чтобы указать, где отображается оформления текста, такие как подчеркивание.</span><span class="sxs-lookup"><span data-stu-id="8dbda-109">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="8dbda-110">Используйте <xref:System.Windows.TextDecoration.Pen%2A> свойство для определения внешнего вида оформления текста, например сплошной заливки или цвет градиента.</span><span class="sxs-lookup"><span data-stu-id="8dbda-110">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="8dbda-111">Если не указать значение для <xref:System.Windows.TextDecoration.Pen%2A> свойства, оформление будет по умолчанию совпадает с цветом текста.</span><span class="sxs-lookup"><span data-stu-id="8dbda-111">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="8dbda-112">После того как определен <xref:System.Windows.TextDecoration> объекта, добавьте ее в <xref:System.Windows.TextDecorations> коллекцию нужного объекта текста.</span><span class="sxs-lookup"><span data-stu-id="8dbda-112">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="8dbda-113">Следующий пример показывает оформление текста с линейной градиентной кисти и пунктирного пера.</span><span class="sxs-lookup"><span data-stu-id="8dbda-113">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 <span data-ttu-id="8dbda-114">![Украшение текста с подчеркиванием линейным градиентом](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")</span><span class="sxs-lookup"><span data-stu-id="8dbda-114">![Text decoration with linear gradient underline](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")</span></span>  
<span data-ttu-id="8dbda-115">Пример подчеркивания со стилем линейной градиентной кисти и пунктирного пера</span><span class="sxs-lookup"><span data-stu-id="8dbda-115">Example of an underline styled with a linear gradient brush and dashed pen</span></span>  
  
 <span data-ttu-id="8dbda-116"><xref:System.Windows.Documents.Hyperlink> Объект является элемент содержимого потока встроенного уровня, позволяющий размещать гиперссылки в содержимом потока.</span><span class="sxs-lookup"><span data-stu-id="8dbda-116">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="8dbda-117">По умолчанию <xref:System.Windows.Documents.Hyperlink> использует <xref:System.Windows.TextDecoration> объекта для отображения подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="8dbda-117">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="8dbda-118"><xref:System.Windows.TextDecoration> объекты могут быть производительность при создании, особенно в том случае, если имеется много <xref:System.Windows.Documents.Hyperlink> объектов.</span><span class="sxs-lookup"><span data-stu-id="8dbda-118"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="8dbda-119">Если предусматривают широкое использование <xref:System.Windows.Documents.Hyperlink> элементов, может потребоваться отображать подчеркивание только при возникновении события, такие как <xref:System.Windows.ContentElement.MouseEnter> событий.</span><span class="sxs-lookup"><span data-stu-id="8dbda-119">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="8dbda-120">В следующем примере подчеркивание ссылки «Мой MSN» является динамическим — оно появляется только при <xref:System.Windows.ContentElement.MouseEnter> события.</span><span class="sxs-lookup"><span data-stu-id="8dbda-120">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 <span data-ttu-id="8dbda-121">![Гиперссылки, отображающие TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span><span class="sxs-lookup"><span data-stu-id="8dbda-121">![Hyperlinks displaying TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span></span>  
<span data-ttu-id="8dbda-122">Гиперссылки, определенные с TextDecorations</span><span class="sxs-lookup"><span data-stu-id="8dbda-122">Hyperlinks defined with TextDecorations</span></span>  
  
 <span data-ttu-id="8dbda-123">Дополнительные сведения см. в разделе [Определение того, подчеркнута ли ссылка](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).</span><span class="sxs-lookup"><span data-stu-id="8dbda-123">For more information, see [Specify Whether a Hyperlink is Underlined](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8dbda-124">Пример</span><span class="sxs-lookup"><span data-stu-id="8dbda-124">Example</span></span>  
 <span data-ttu-id="8dbda-125">В следующем примере кода подчеркивание текста используется значение шрифта по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8dbda-125">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="8dbda-126">В следующем примере кода подчеркивание текста создается с помощью кисти сплошной цвет пера.</span><span class="sxs-lookup"><span data-stu-id="8dbda-126">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="8dbda-127">В следующем примере кода подчеркивание текста создается с помощью кисти линейного градиента для пунктирного пера.</span><span class="sxs-lookup"><span data-stu-id="8dbda-127">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="8dbda-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8dbda-128">See Also</span></span>  
 <xref:System.Windows.TextDecoration>  
 <xref:System.Windows.Documents.Hyperlink>  
 [<span data-ttu-id="8dbda-129">Определение того, подчеркнута ли ссылка</span><span class="sxs-lookup"><span data-stu-id="8dbda-129">Specify Whether a Hyperlink is Underlined</span></span>](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)
