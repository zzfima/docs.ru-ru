---
title: Практическое руководство. Закраска области сплошным цветом
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: be28a0af04c4e43cdf745a5429468aee99e34c40
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849526"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="70d70-102">Практическое руководство. Закраска области сплошным цветом</span><span class="sxs-lookup"><span data-stu-id="70d70-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="70d70-103">Чтобы нарисовать область с твердым цветом, вы можете <xref:System.Windows.Media.Brushes.Red%2A> <xref:System.Windows.Media.Brushes.Blue%2A>использовать предопределенные системные кисти, такие как или , или вы можете создать новый <xref:System.Windows.Media.SolidColorBrush> и описать его <xref:System.Windows.Media.SolidColorBrush.Color%2A> с помощью альфа, красный, зеленый и синий значения.</span><span class="sxs-lookup"><span data-stu-id="70d70-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="70d70-104">В XAML можно также закрасить область сплошным цветом, используя шестнадцатеричную нотацию.</span><span class="sxs-lookup"><span data-stu-id="70d70-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="70d70-105">Следующие примеры используют каждый <xref:System.Windows.Shapes.Rectangle> из этих методов, чтобы покрасить синий.</span><span class="sxs-lookup"><span data-stu-id="70d70-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70d70-106">Пример</span><span class="sxs-lookup"><span data-stu-id="70d70-106">Example</span></span>  
 <span data-ttu-id="70d70-107">**Использование стандартной кисти**</span><span class="sxs-lookup"><span data-stu-id="70d70-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="70d70-108">В следующем примере используется <xref:System.Windows.Media.Brushes.Blue%2A> предопределенная кисть для рисования прямоугольника синего цвета.</span><span class="sxs-lookup"><span data-stu-id="70d70-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="70d70-109">**Использование шестнадцатеричной нотации**</span><span class="sxs-lookup"><span data-stu-id="70d70-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="70d70-110">В следующем примере используется шестнадцатеричная нотация из 8 цифр для закрашивания прямоугольника синим цветом.</span><span class="sxs-lookup"><span data-stu-id="70d70-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="70d70-111">**Использование значений ARGB**</span><span class="sxs-lookup"><span data-stu-id="70d70-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="70d70-112">Следующий пример <xref:System.Windows.Media.SolidColorBrush> создает и <xref:System.Windows.Media.SolidColorBrush.Color%2A> описывает его использование значений ARGB для синего цвета.</span><span class="sxs-lookup"><span data-stu-id="70d70-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="70d70-113">Для других способов описания <xref:System.Windows.Media.Color> цвета, увидеть структуру.</span><span class="sxs-lookup"><span data-stu-id="70d70-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="70d70-114">**Похожие темы**</span><span class="sxs-lookup"><span data-stu-id="70d70-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="70d70-115">Для получения <xref:System.Windows.Media.SolidColorBrush> дополнительной информации и дополнительных примеров смотрите обзор [обзора картины с твердыми цветами и градиентами.](painting-with-solid-colors-and-gradients-overview.md)</span><span class="sxs-lookup"><span data-stu-id="70d70-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="70d70-116">Этот пример кода является частью более <xref:System.Windows.Media.SolidColorBrush> крупного примера, предусмотренного для класса.</span><span class="sxs-lookup"><span data-stu-id="70d70-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="70d70-117">Для полного образца [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)см.</span><span class="sxs-lookup"><span data-stu-id="70d70-117">For the complete sample, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70d70-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="70d70-118">See also</span></span>

- <xref:System.Windows.Media.Brushes>
