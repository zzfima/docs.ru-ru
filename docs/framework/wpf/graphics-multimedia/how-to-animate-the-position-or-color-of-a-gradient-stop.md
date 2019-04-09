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
ms.openlocfilehash: eeaea4732855155bf711912644f2f5b3f5a4f8d0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134814"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="e754e-102">Практическое руководство. Анимация положения или цвета ограничения градиента</span><span class="sxs-lookup"><span data-stu-id="e754e-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="e754e-103">В этом примере демонстрируется анимация <xref:System.Windows.Media.GradientStop.Color%2A> и <xref:System.Windows.Media.GradientStop.Offset%2A> из <xref:System.Windows.Media.GradientStop> объектов.</span><span class="sxs-lookup"><span data-stu-id="e754e-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e754e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e754e-104">Example</span></span>  
 <span data-ttu-id="e754e-105">Следующий пример анимирует три градиента внутри <xref:System.Windows.Media.LinearGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="e754e-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="e754e-106">В примере используется три анимации, каждый из которых выполняет анимацию различных градиента:</span><span class="sxs-lookup"><span data-stu-id="e754e-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
-   <span data-ttu-id="e754e-107">Первая анимация, <xref:System.Windows.Media.Animation.DoubleAnimation>, анимирует первого градиента <xref:System.Windows.Media.GradientStop.Offset%2A> от 0,0 до 1,0, а затем снова 0,0.</span><span class="sxs-lookup"><span data-stu-id="e754e-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="e754e-108">Таким образом первый цвет градиента перемещается из левой части правую сторону прямоугольника и затем обратно в левой части.</span><span class="sxs-lookup"><span data-stu-id="e754e-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
-   <span data-ttu-id="e754e-109">Второй анимации, <xref:System.Windows.Media.Animation.ColorAnimation>, анимирует второй градиента <xref:System.Windows.Media.GradientStop.Color%2A> из <xref:System.Windows.Media.Colors.Purple%2A> для <xref:System.Windows.Media.Colors.Yellow%2A> и затем обратно до <xref:System.Windows.Media.Colors.Purple%2A>.</span><span class="sxs-lookup"><span data-stu-id="e754e-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="e754e-110">В результате Средний цвет градиента изменяется от фиолетового на желтый и обратно.</span><span class="sxs-lookup"><span data-stu-id="e754e-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
-   <span data-ttu-id="e754e-111">Третий анимации, другой <xref:System.Windows.Media.Animation.ColorAnimation>, анимирует прозрачность третий градиента <xref:System.Windows.Media.GradientStop.Color%2A> -1, а затем снова.</span><span class="sxs-lookup"><span data-stu-id="e754e-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="e754e-112">Таким образом третий цвет в градиенте исчезает, а затем снова становится непрозрачным.</span><span class="sxs-lookup"><span data-stu-id="e754e-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="e754e-113">Несмотря на то, что в этом примере используется <xref:System.Windows.Media.LinearGradientBrush>, процесс одинаков для анимации <xref:System.Windows.Media.GradientStop> объектов внутри <xref:System.Windows.Media.RadialGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="e754e-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="e754e-114">Дополнительные примеры см. в разделе [пример использования кистей](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="e754e-114">For additional examples, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e754e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e754e-115">See also</span></span>

- <xref:System.Windows.Media.GradientStop>
- [<span data-ttu-id="e754e-116">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="e754e-116">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="e754e-117">Общие сведения о Storyboard</span><span class="sxs-lookup"><span data-stu-id="e754e-117">Storyboards Overview</span></span>](storyboards-overview.md)
