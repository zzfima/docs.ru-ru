---
title: Практическое руководство. Закраска области сплошным цветом
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: 017c685139979ec3aa411be6e6b5fdf0e91657de
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43878448"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="642e5-102">Практическое руководство. Закраска области сплошным цветом</span><span class="sxs-lookup"><span data-stu-id="642e5-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="642e5-103">Чтобы закрасить область сплошным цветом, можно использовать стандартную системную кисть, например <xref:System.Windows.Media.Brushes.Red%2A> или <xref:System.Windows.Media.Brushes.Blue%2A>, или создать новый <xref:System.Windows.Media.SolidColorBrush> и описать его <xref:System.Windows.Media.SolidColorBrush.Color%2A> с помощью значений альфа, красного, зеленого и синего.</span><span class="sxs-lookup"><span data-stu-id="642e5-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="642e5-104">В XAML можно также закрасить область сплошным цветом, используя шестнадцатеричную нотацию.</span><span class="sxs-lookup"><span data-stu-id="642e5-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="642e5-105">В следующих примерах используется каждый из этих приемов для закрашивания <xref:System.Windows.Shapes.Rectangle> синий.</span><span class="sxs-lookup"><span data-stu-id="642e5-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="642e5-106">Пример</span><span class="sxs-lookup"><span data-stu-id="642e5-106">Example</span></span>  
 <span data-ttu-id="642e5-107">**Использование стандартной кисти**</span><span class="sxs-lookup"><span data-stu-id="642e5-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="642e5-108">В следующем примере используется стандартная кисть <xref:System.Windows.Media.Brushes.Blue%2A> для закрашивания прямоугольника синим цветом.</span><span class="sxs-lookup"><span data-stu-id="642e5-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="642e5-109">**Использование шестнадцатеричной нотации**</span><span class="sxs-lookup"><span data-stu-id="642e5-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="642e5-110">В следующем примере используется шестнадцатеричная нотация из 8 цифр для закрашивания прямоугольника синим цветом.</span><span class="sxs-lookup"><span data-stu-id="642e5-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="642e5-111">**Использование значений ARGB**</span><span class="sxs-lookup"><span data-stu-id="642e5-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="642e5-112">В следующем примере создается <xref:System.Windows.Media.SolidColorBrush> и описывает его <xref:System.Windows.Media.SolidColorBrush.Color%2A> использование ARGB значений для получения синего цвета.</span><span class="sxs-lookup"><span data-stu-id="642e5-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="642e5-113">Другие способы описания цвета см. в разделе <xref:System.Windows.Media.Color> структуры.</span><span class="sxs-lookup"><span data-stu-id="642e5-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="642e5-114">**См. также**</span><span class="sxs-lookup"><span data-stu-id="642e5-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="642e5-115">Дополнительные сведения о <xref:System.Windows.Media.SolidColorBrush> и Дополнительные примеры см. в разделе [закраске сплошным цветом и градиентом Обзор](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) Обзор.</span><span class="sxs-lookup"><span data-stu-id="642e5-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="642e5-116">Данный пример кода является частью большего примера для <xref:System.Windows.Media.SolidColorBrush> класса.</span><span class="sxs-lookup"><span data-stu-id="642e5-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="642e5-117">Полный пример см. в разделе [Пример использования кистей](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="642e5-117">For the complete sample, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="642e5-118">См. также</span><span class="sxs-lookup"><span data-stu-id="642e5-118">See Also</span></span>  
 <xref:System.Windows.Media.Brushes>
