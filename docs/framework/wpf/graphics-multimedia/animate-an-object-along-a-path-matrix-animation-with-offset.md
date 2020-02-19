---
title: Практическое руководство. Анимация объектов по всему пути (Матричная анимации с накоплением смещения)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: 8b3975ef5031b50381dfa9baf7f34a58fc05ab4e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453108"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a><span data-ttu-id="676b2-102">Практическое руководство. Анимация объектов по всему пути (Матричная анимации с накоплением смещения)</span><span class="sxs-lookup"><span data-stu-id="676b2-102">How to: Animate an Object Along a Path (Matrix Animation with Offset Accumulation)</span></span>
<span data-ttu-id="676b2-103">В этом примере показано, как использовать класс <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> для анимации объекта вдоль пути и, чтобы эта анимация настроила значения смещения по мере повторения.</span><span class="sxs-lookup"><span data-stu-id="676b2-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path and have that animation accumulate its offset values as it repeats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="676b2-104">Пример</span><span class="sxs-lookup"><span data-stu-id="676b2-104">Example</span></span>  
 <span data-ttu-id="676b2-105">В следующем примере объект <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> используется для анимации свойства <xref:System.Windows.Media.MatrixTransform.Matrix%2A> <xref:System.Windows.Media.MatrixTransform>, применяемого к кнопке.</span><span class="sxs-lookup"><span data-stu-id="676b2-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> applied to a button.</span></span> <span data-ttu-id="676b2-106">В результате кнопка перемещается вдоль изогнутого пути.</span><span class="sxs-lookup"><span data-stu-id="676b2-106">As a result, a button moves along a curved path.</span></span>  
  
 <span data-ttu-id="676b2-107">Кроме того, в примере свойству <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> присваивается значение `true`, что приводит к накоплению смещения анимированной матрицы при повторении анимации.</span><span class="sxs-lookup"><span data-stu-id="676b2-107">In addition, the example sets the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property to `true`, which causes the offset of the animated matrix to accumulate as the animation repeats.</span></span> <span data-ttu-id="676b2-108">Поскольку смещение накапливается, при повторении анимации кнопка перемещается все дальше по экрану, а не возвращается в начальную позицию.</span><span class="sxs-lookup"><span data-stu-id="676b2-108">Because the offset accumulates, the button moves farther across the screen when the animation repeats, rather than resetting to the starting position.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 <span data-ttu-id="676b2-109">Обратите внимание, что, хотя свойство <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> приводит к накоплению значений смещения при повторении, это не приводит к накоплению значений вращения.</span><span class="sxs-lookup"><span data-stu-id="676b2-109">Note that, although the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property causes offset values to accumulate over repetitions, it doesn't cause rotation values to accumulate.</span></span> <span data-ttu-id="676b2-110">Чтобы значения вращения были накоплены, задайте для свойств <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> и <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> анимации значение `true`.</span><span class="sxs-lookup"><span data-stu-id="676b2-110">To make rotation values accumulate, set the animation's <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> and <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> properties to `true`.</span></span>  
  
 <span data-ttu-id="676b2-111">Полный пример см. в разделе [Пример анимации по путям](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span><span class="sxs-lookup"><span data-stu-id="676b2-111">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span> <span data-ttu-id="676b2-112">Пример, демонстрирующий анимацию <xref:System.Windows.Media.Matrix>ного значения вдоль пути без накопления смещения, см. в разделе [анимация объекта вдоль пути (матричная анимация)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="676b2-112">For an example showing how to animate a <xref:System.Windows.Media.Matrix> value along a path without offset accumulation, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="676b2-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="676b2-113">See also</span></span>

- [<span data-ttu-id="676b2-114">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="676b2-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="676b2-115">Практические руководства, посвященные анимации вдоль пути</span><span class="sxs-lookup"><span data-stu-id="676b2-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
