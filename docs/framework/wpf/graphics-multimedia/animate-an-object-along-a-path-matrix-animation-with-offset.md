---
title: Практическое руководство. Анимация объектов по всему пути (матричная анимации с накоплением смещения)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: 3e7b892e2a2215d26512850477844d71bce7fe09
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207374"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a><span data-ttu-id="d57e3-102">Практическое руководство. Анимация объектов по всему пути (матричная анимации с накоплением смещения)</span><span class="sxs-lookup"><span data-stu-id="d57e3-102">How to: Animate an Object Along a Path (Matrix Animation with Offset Accumulation)</span></span>
<span data-ttu-id="d57e3-103">В этом примере показано, как использовать <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> класс для анимации объекта вдоль пути и с накоплением смещения анимацией значения при повторении.</span><span class="sxs-lookup"><span data-stu-id="d57e3-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path and have that animation accumulate its offset values as it repeats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d57e3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d57e3-104">Example</span></span>  
 <span data-ttu-id="d57e3-105">В следующем примере используется <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> анимируемого объекта <xref:System.Windows.Media.MatrixTransform.Matrix%2A> свойство <xref:System.Windows.Media.MatrixTransform> , примененного к кнопке.</span><span class="sxs-lookup"><span data-stu-id="d57e3-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> applied to a button.</span></span> <span data-ttu-id="d57e3-106">В результате кнопка перемещается вдоль изогнутого пути.</span><span class="sxs-lookup"><span data-stu-id="d57e3-106">As a result, a button moves along a curved path.</span></span>  
  
 <span data-ttu-id="d57e3-107">Кроме того, в этом примере <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> свойства `true`, который вызывает смещения анимированной матрицы накапливаться при повторе анимации.</span><span class="sxs-lookup"><span data-stu-id="d57e3-107">In addition, the example sets the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property to `true`, which causes the offset of the animated matrix to accumulate as the animation repeats.</span></span> <span data-ttu-id="d57e3-108">Поскольку смещение накапливается, при повторении анимации кнопка перемещается все дальше по экрану, а не возвращается в начальную позицию.</span><span class="sxs-lookup"><span data-stu-id="d57e3-108">Because the offset accumulates, the button moves farther across the screen when the animation repeats, rather than resetting to the starting position.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 <span data-ttu-id="d57e3-109">Обратите внимание, что, несмотря на то что <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> свойство приводит к накоплению значений смещения, оно не вызывает накопления значений поворота.</span><span class="sxs-lookup"><span data-stu-id="d57e3-109">Note that, although the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property causes offset values to accumulate over repetitions, it doesn't cause rotation values to accumulate.</span></span> <span data-ttu-id="d57e3-110">Чтобы сделать накопления значений поворота, установите анимации <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> и <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="d57e3-110">To make rotation values accumulate, set the animation's <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> and <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> properties to `true`.</span></span>  
  
 <span data-ttu-id="d57e3-111">Полный пример см. в разделе [Пример анимации вдоль пути](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="d57e3-111">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="d57e3-112">Пример, показывающий, как анимировать <xref:System.Windows.Media.Matrix> значение вдоль пути без накопления смещения, см. в разделе [анимация объекта вдоль пути (матричная анимация)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="d57e3-112">For an example showing how to animate a <xref:System.Windows.Media.Matrix> value along a path without offset accumulation, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d57e3-113">См. также</span><span class="sxs-lookup"><span data-stu-id="d57e3-113">See also</span></span>

- [<span data-ttu-id="d57e3-114">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="d57e3-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="d57e3-115">Практические руководства, посвященные анимации пути</span><span class="sxs-lookup"><span data-stu-id="d57e3-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
