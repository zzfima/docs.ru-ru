---
title: Практическое руководство. Создание элемента Spin
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: 2e72389a11e48629c2763fcbd9f7b1945ffff5dd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452796"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="b63a7-102">Практическое руководство. Создание элемента Spin</span><span class="sxs-lookup"><span data-stu-id="b63a7-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="b63a7-103">В этом примере показано, как выполнить вращение элемента с помощью <xref:System.Windows.Media.RotateTransform> и <xref:System.Windows.Media.Animation.DoubleAnimation>.</span><span class="sxs-lookup"><span data-stu-id="b63a7-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="b63a7-104">В следующем примере <xref:System.Windows.Media.RotateTransform> применяется к свойству <xref:System.Windows.UIElement.RenderTransform%2A> элемента.</span><span class="sxs-lookup"><span data-stu-id="b63a7-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="b63a7-105">В примере используется <xref:System.Windows.Media.Animation.DoubleAnimation> для анимации <xref:System.Windows.Media.RotateTransform.Angle%2A> <xref:System.Windows.Media.RotateTransform>.</span><span class="sxs-lookup"><span data-stu-id="b63a7-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="b63a7-106">Чтобы сделать элемент прокруткой, в примере свойству <xref:System.Windows.UIElement.RenderTransformOrigin%2A> элемента присваивается значение Point (0,5, 0,5).</span><span class="sxs-lookup"><span data-stu-id="b63a7-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b63a7-107">Пример</span><span class="sxs-lookup"><span data-stu-id="b63a7-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="b63a7-108">Полный пример, в состав которого входят дополнительные примеры преобразования, см. в разделе [Пример двумерных](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)преобразований.</span><span class="sxs-lookup"><span data-stu-id="b63a7-108">For the complete sample, which includes more transformation examples, see [2-D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b63a7-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b63a7-109">See also</span></span>

- [<span data-ttu-id="b63a7-110">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="b63a7-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="b63a7-111">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="b63a7-111">Transforms Overview</span></span>](transforms-overview.md)
