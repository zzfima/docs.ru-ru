---
title: "Практическое руководство. Анимация объектов по всему пути (Матричная анимации с накоплением смещения)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8a9fd282d3ca4603eadd0ed10436944f7e9ab593
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a><span data-ttu-id="e8890-102">Практическое руководство. Анимация объектов по всему пути (Матричная анимации с накоплением смещения)</span><span class="sxs-lookup"><span data-stu-id="e8890-102">How to: Animate an Object Along a Path (Matrix Animation with Offset Accumulation)</span></span>
<span data-ttu-id="e8890-103">В этом примере показано, как использовать <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> класса, чтобы анимация объекта вдоль пути анимации накапливаются его смещение значения при повторе его.</span><span class="sxs-lookup"><span data-stu-id="e8890-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path and have that animation accumulate its offset values as it repeats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8890-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e8890-104">Example</span></span>  
 <span data-ttu-id="e8890-105">В следующем примере используется <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> анимируемый объект <xref:System.Windows.Media.MatrixTransform.Matrix%2A> свойство <xref:System.Windows.Media.MatrixTransform> применяется к кнопке.</span><span class="sxs-lookup"><span data-stu-id="e8890-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> applied to a button.</span></span> <span data-ttu-id="e8890-106">В результате кнопка перемещается вдоль изогнутого пути.</span><span class="sxs-lookup"><span data-stu-id="e8890-106">As a result, a button moves along a curved path.</span></span>  
  
 <span data-ttu-id="e8890-107">Кроме того, в этом примере <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> свойства `true`, чего смещение анимированной матрицы накапливаться при повторе анимации.</span><span class="sxs-lookup"><span data-stu-id="e8890-107">In addition, the example sets the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property to `true`, which causes the offset of the animated matrix to accumulate as the animation repeats.</span></span> <span data-ttu-id="e8890-108">Поскольку смещение накапливается, при повторении анимации кнопка перемещается все дальше по экрану, а не возвращается в начальную позицию.</span><span class="sxs-lookup"><span data-stu-id="e8890-108">Because the offset accumulates, the button moves farther across the screen when the animation repeats, rather than resetting to the starting position.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 <span data-ttu-id="e8890-109">Обратите внимание, что, несмотря на то что <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> свойство вызывает накопление значений смещения, оно не вызывает накопления значений поворота.</span><span class="sxs-lookup"><span data-stu-id="e8890-109">Note that, although the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property causes offset values to accumulate over repetitions, it doesn't cause rotation values to accumulate.</span></span> <span data-ttu-id="e8890-110">Чтобы значения вращения накапливаться, задайте анимации <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> и <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="e8890-110">To make rotation values accumulate, set the animation's <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> and <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> properties to `true`.</span></span>  
  
 <span data-ttu-id="e8890-111">Полный пример см. в разделе [Пример анимации пути](http://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="e8890-111">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="e8890-112">Пример, показывающий, как анимировать <xref:System.Windows.Media.Matrix> значение пути без накапливания смещения см. в разделе [анимация объекта вдоль пути (матрица анимации)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="e8890-112">For an example showing how to animate a <xref:System.Windows.Media.Matrix> value along a path without offset accumulation, see [Animate an Object Along a Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8890-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e8890-113">See Also</span></span>  
 [<span data-ttu-id="e8890-114">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="e8890-114">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="e8890-115">Практические руководства, посвященные анимации по контуру</span><span class="sxs-lookup"><span data-stu-id="e8890-115">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
