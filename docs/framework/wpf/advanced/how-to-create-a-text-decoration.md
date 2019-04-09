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
ms.openlocfilehash: d586eef8d1308070da38a0a54c63c3ba64d30c8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133839"
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="cc294-102">Практическое руководство. Создание оформления текста</span><span class="sxs-lookup"><span data-stu-id="cc294-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="cc294-103">Объект <xref:System.Windows.TextDecoration> объект представляет визуальную орнаментацию, можно добавить в текст.</span><span class="sxs-lookup"><span data-stu-id="cc294-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="cc294-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span><span class="sxs-lookup"><span data-stu-id="cc294-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="cc294-105">Пример расположения оформления текста относительно текста.</span><span class="sxs-lookup"><span data-stu-id="cc294-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 ![Схема типов оформления текста](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 <span data-ttu-id="cc294-107">Чтобы добавить оформление текста в текст, создайте <xref:System.Windows.TextDecoration> объекта и измените его свойства.</span><span class="sxs-lookup"><span data-stu-id="cc294-107">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="cc294-108">Используйте <xref:System.Windows.TextDecoration.Location%2A> свойство, чтобы указать, где отображается оформления текста, такие как подчеркивание.</span><span class="sxs-lookup"><span data-stu-id="cc294-108">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="cc294-109">Используйте <xref:System.Windows.TextDecoration.Pen%2A> свойство, чтобы указать внешний вид оформления текста, например сплошная заливка или цвет градиента.</span><span class="sxs-lookup"><span data-stu-id="cc294-109">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="cc294-110">Если не указать значение для <xref:System.Windows.TextDecoration.Pen%2A> свойство, оформление будет по умолчанию цвет текста.</span><span class="sxs-lookup"><span data-stu-id="cc294-110">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="cc294-111">После определения <xref:System.Windows.TextDecoration> объекта, добавьте ее в <xref:System.Windows.TextDecorations> коллекции объекта нужный текст.</span><span class="sxs-lookup"><span data-stu-id="cc294-111">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="cc294-112">Пример с кисти линейного градиента и штрихового пера оформление текста.</span><span class="sxs-lookup"><span data-stu-id="cc294-112">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 ![Украшение текста с подчеркиванием линейным градиентом](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 <span data-ttu-id="cc294-114"><xref:System.Windows.Documents.Hyperlink> Объект — это элемент содержимого потока встроенного уровня, позволяющим размещать гиперссылки в содержимом потока.</span><span class="sxs-lookup"><span data-stu-id="cc294-114">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="cc294-115">По умолчанию <xref:System.Windows.Documents.Hyperlink> использует <xref:System.Windows.TextDecoration> объекта для отображения подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="cc294-115">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <xref:System.Windows.TextDecoration> <span data-ttu-id="cc294-116">объекты могут быть производительность при создании, особенно в том случае, если имеется много <xref:System.Windows.Documents.Hyperlink> объектов.</span><span class="sxs-lookup"><span data-stu-id="cc294-116">objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="cc294-117">При внесении широкое использование <xref:System.Windows.Documents.Hyperlink> элементов, может потребоваться отображать подчеркивание только при возникновении события, такие как <xref:System.Windows.ContentElement.MouseEnter> событий.</span><span class="sxs-lookup"><span data-stu-id="cc294-117">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="cc294-118">В следующем примере подчеркивание ссылки «Мой MSN» является динамическим — оно появляется только при <xref:System.Windows.ContentElement.MouseEnter> активируется событие.</span><span class="sxs-lookup"><span data-stu-id="cc294-118">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 ![Гиперссылки, отображающие TextDecorations](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  
   
 <span data-ttu-id="cc294-120">Дополнительные сведения см. в разделе [Определение того, подчеркнута ли ссылка](how-to-specify-whether-a-hyperlink-is-underlined.md).</span><span class="sxs-lookup"><span data-stu-id="cc294-120">For more information, see [Specify Whether a Hyperlink is Underlined](how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc294-121">Пример</span><span class="sxs-lookup"><span data-stu-id="cc294-121">Example</span></span>  
 <span data-ttu-id="cc294-122">В следующем примере кода подчеркивание текста использует шрифт по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cc294-122">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="cc294-123">В следующем примере кода подчеркивание текста создается с Одноцветная кисть для пера.</span><span class="sxs-lookup"><span data-stu-id="cc294-123">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="cc294-124">В следующем примере кода подчеркивание текста создается с помощью кисти линейного градиента для пунктирного пера.</span><span class="sxs-lookup"><span data-stu-id="cc294-124">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="cc294-125">См. также</span><span class="sxs-lookup"><span data-stu-id="cc294-125">See also</span></span>

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="cc294-126">Определение того, подчеркнута ли ссылка</span><span class="sxs-lookup"><span data-stu-id="cc294-126">Specify Whether a Hyperlink is Underlined</span></span>](how-to-specify-whether-a-hyperlink-is-underlined.md)
