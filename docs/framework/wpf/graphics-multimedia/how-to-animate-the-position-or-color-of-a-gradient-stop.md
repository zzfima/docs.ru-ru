---
title: Практическое руководство. Анимация положения или цвета ограничения градиента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
ms.openlocfilehash: aeae33f5f3c8016808988f58d61969e9b6f05039
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452848"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="640c4-102">Практическое руководство. Анимация положения или цвета ограничения градиента</span><span class="sxs-lookup"><span data-stu-id="640c4-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="640c4-103">В этом примере показано, как анимировать <xref:System.Windows.Media.GradientStop.Color%2A> и <xref:System.Windows.Media.GradientStop.Offset%2A> объектов <xref:System.Windows.Media.GradientStop>.</span><span class="sxs-lookup"><span data-stu-id="640c4-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="640c4-104">Пример</span><span class="sxs-lookup"><span data-stu-id="640c4-104">Example</span></span>  
 <span data-ttu-id="640c4-105">В следующем примере анимируется три остановки градиента внутри <xref:System.Windows.Media.LinearGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="640c4-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="640c4-106">В этом примере используется три анимации, каждая из которых анимирует другую точку градиента:</span><span class="sxs-lookup"><span data-stu-id="640c4-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
- <span data-ttu-id="640c4-107">Первая анимация, <xref:System.Windows.Media.Animation.DoubleAnimation>, выполняет анимацию первого ограничителя градиента <xref:System.Windows.Media.GradientStop.Offset%2A> с 0,0 до 1,0, а затем обратно в 0,0.</span><span class="sxs-lookup"><span data-stu-id="640c4-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="640c4-108">В результате первый цвет градиента смещается с левой стороны к правой части прямоугольника, а затем обратно на левую сторону.</span><span class="sxs-lookup"><span data-stu-id="640c4-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
- <span data-ttu-id="640c4-109">Вторая анимация, <xref:System.Windows.Media.Animation.ColorAnimation>, анимирует <xref:System.Windows.Media.GradientStop.Color%2A> второй ограничитель градиента от <xref:System.Windows.Media.Colors.Purple%2A> до <xref:System.Windows.Media.Colors.Yellow%2A>, а затем обратно в <xref:System.Windows.Media.Colors.Purple%2A>.</span><span class="sxs-lookup"><span data-stu-id="640c4-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="640c4-110">В результате средний цвет в градиенте меняется с пурпурного на желтый и обратно на сиреневый.</span><span class="sxs-lookup"><span data-stu-id="640c4-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
- <span data-ttu-id="640c4-111">Третья анимация, другая <xref:System.Windows.Media.Animation.ColorAnimation>, анимирует непрозрачность третьего <xref:System.Windows.Media.GradientStop.Color%2A> ограничителя градиента на-1, а затем обратно.</span><span class="sxs-lookup"><span data-stu-id="640c4-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="640c4-112">В результате третий цвет в градиенте плавно исчезает, а затем снова становится непрозрачным.</span><span class="sxs-lookup"><span data-stu-id="640c4-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="640c4-113">Несмотря на то, что в этом примере используется <xref:System.Windows.Media.LinearGradientBrush>, процесс анимации <xref:System.Windows.Media.GradientStop> объектов внутри <xref:System.Windows.Media.RadialGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="640c4-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="640c4-114">Дополнительные примеры см. в [образце кистей](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="640c4-114">For additional examples, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="640c4-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="640c4-115">See also</span></span>

- <xref:System.Windows.Media.GradientStop>
- [<span data-ttu-id="640c4-116">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="640c4-116">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="640c4-117">Общие сведения о раскадровке</span><span class="sxs-lookup"><span data-stu-id="640c4-117">Storyboards Overview</span></span>](storyboards-overview.md)
