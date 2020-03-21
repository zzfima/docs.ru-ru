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
ms.openlocfilehash: cf3b3c3bcb75153a0be4f7ced03b38134b79a930
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185923"
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="d0f9e-102">Практическое руководство. Создание оформления текста</span><span class="sxs-lookup"><span data-stu-id="d0f9e-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="d0f9e-103">Объект <xref:System.Windows.TextDecoration> представляет собой визуальное украшение, что можно добавить в текст.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="d0f9e-104">Существует четыре типа текстовых декораций: подчеркивание, базовый, ударный и оверлайн.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="d0f9e-105">В следующем примере показаны расположение текстовых декораций относительно текста.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 ![Диаграмма типов оформления текста](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 <span data-ttu-id="d0f9e-107">Чтобы добавить текстовое оформление в текст, создайте <xref:System.Windows.TextDecoration> объект и измените его свойства.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-107">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="d0f9e-108">Используйте <xref:System.Windows.TextDecoration.Location%2A> свойство, чтобы указать, где появляется текстовое украшение, например, подчеркивание.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-108">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="d0f9e-109">Используйте <xref:System.Windows.TextDecoration.Pen%2A> свойство, чтобы указать внешний вид текстового оформления, например, цельного цвета заполнения или градиента.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-109">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="d0f9e-110">Если вы не указываете <xref:System.Windows.TextDecoration.Pen%2A> значение для свойства, украшения по умолчанию по умолчанию к тому же цвету, как текст.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-110">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="d0f9e-111">После того как <xref:System.Windows.TextDecoration> вы определили <xref:System.Windows.TextDecorations> объект, добавьте его в коллекцию желаемого объекта текста.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-111">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="d0f9e-112">Ниже приводится текстовое украшение, которое было оформлено с линейной градиентной кистью и пунктирной ручкой.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-112">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 ![Украшение текста с подчеркиванием линейным градиентом](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 <span data-ttu-id="d0f9e-114">Объект <xref:System.Windows.Documents.Hyperlink> представляет собой элемент содержимого потока уровня, который позволяет размещать гиперссылки в содержимом потока.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-114">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="d0f9e-115">По умолчанию <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.TextDecoration> используется объект для отображения подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-115">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="d0f9e-116"><xref:System.Windows.TextDecoration>объекты могут быть интенсивными для мгновенного выполнения <xref:System.Windows.Documents.Hyperlink> объектов, особенно если у вас есть много объектов.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-116"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="d0f9e-117">Если вы широко <xref:System.Windows.Documents.Hyperlink> используете элементы, вы можете рассмотреть возможность показа подчеркивания только при запуске события, например <xref:System.Windows.ContentElement.MouseEnter> события.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-117">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="d0f9e-118">В следующем примере подчеркивание для ссылки "My MSN" <xref:System.Windows.ContentElement.MouseEnter> является динамическим — оно появляется только при срабатывании события.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-118">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 ![Гиперссылки, отображающие TextDecorations](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  

 <span data-ttu-id="d0f9e-120">Дополнительные сведения см. в разделе [Определение того, подчеркнута ли ссылка](how-to-specify-whether-a-hyperlink-is-underlined.md).</span><span class="sxs-lookup"><span data-stu-id="d0f9e-120">For more information, see [Specify Whether a Hyperlink is Underlined](how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0f9e-121">Пример</span><span class="sxs-lookup"><span data-stu-id="d0f9e-121">Example</span></span>  
 <span data-ttu-id="d0f9e-122">В следующем примере кода в выделении текста используется значение шрифта по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-122">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="d0f9e-123">В следующем примере кода, подчеркивая текст украшения создается с твердой цветовой кистью для пера.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-123">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="d0f9e-124">В следующем примере кода, подчеркивающее текстовое украшение создается с линейной градиентной кистью для пунктирной ручки.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-124">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="d0f9e-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d0f9e-125">See also</span></span>

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="d0f9e-126">Определение того, подчеркнута ли ссылка</span><span class="sxs-lookup"><span data-stu-id="d0f9e-126">Specify Whether a Hyperlink is Underlined</span></span>](how-to-specify-whether-a-hyperlink-is-underlined.md)
