---
title: Практическое руководство. Анимация объекта вдоль пути (точечная анимация)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: eff0c24a9369ffaa0cfca1cc46af4eff39f58a38
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452900"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a><span data-ttu-id="37cad-102">Практическое руководство. Анимация объекта вдоль пути (точечная анимация)</span><span class="sxs-lookup"><span data-stu-id="37cad-102">How to: Animate an Object Along a Path (Point Animation)</span></span>
<span data-ttu-id="37cad-103">В этом примере показано, как использовать объект <xref:System.Windows.Media.Animation.PointAnimationUsingPath> для анимации <xref:System.Windows.Point> вдоль криволинейного пути.</span><span class="sxs-lookup"><span data-stu-id="37cad-103">This example shows how to use a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> object to animate a <xref:System.Windows.Point> along a curved path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37cad-104">Пример</span><span class="sxs-lookup"><span data-stu-id="37cad-104">Example</span></span>  
 <span data-ttu-id="37cad-105">В следующем примере перемещается <xref:System.Windows.Media.EllipseGeometry> вдоль пути, определенного <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="37cad-105">The following example moves an <xref:System.Windows.Media.EllipseGeometry> along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="37cad-106">Свойство <xref:System.Windows.Media.EllipseGeometry.Center%2A>, представляющее собой геометрию эллипса, которое принимает значение <xref:System.Windows.Point>, задает его расположение. чтобы переместить фигуру эллипса, необходимо анимировать ее свойство <xref:System.Windows.Media.EllipseGeometry.Center%2A>.</span><span class="sxs-lookup"><span data-stu-id="37cad-106">The ellipse geometry's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property, which takes a <xref:System.Windows.Point> value, specifies its position; to move the ellipse geometry, you animate its <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span> <span data-ttu-id="37cad-107">В примере используется <xref:System.Windows.Media.Animation.PointAnimationUsingPath> для анимации свойства <xref:System.Windows.Media.EllipseGeometry.Center%2A> объекта <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="37cad-107">The example uses a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> to animate the <xref:System.Windows.Media.EllipseGeometry> object's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 <span data-ttu-id="37cad-108">Полный пример см. в разделе [Пример анимации по путям](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span><span class="sxs-lookup"><span data-stu-id="37cad-108">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="37cad-109">Версия кода предыдущего примера использовала <xref:System.Windows.Media.Animation.Storyboard> для анимации <xref:System.Windows.Media.EllipseGeometry>, несмотря на то, что применена только одна анимация.</span><span class="sxs-lookup"><span data-stu-id="37cad-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="37cad-110"><xref:System.Windows.Media.Animation.Storyboard> часто является самым простым способом применения нескольких анимаций, так как эти анимации могут управляться одним и тем же <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="37cad-110">A <xref:System.Windows.Media.Animation.Storyboard> is often the easiest way to apply multiple animations because these animations can be controlled by the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="37cad-111">Однако более простым способом применения одной анимации к свойству при использовании кода является использование метода <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>.</span><span class="sxs-lookup"><span data-stu-id="37cad-111">However, an easier way to apply a single animation to a property when using code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="37cad-112">Пример см. в разделе [Анимация свойства без использования раскадровки](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="37cad-112">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37cad-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="37cad-113">See also</span></span>

- [<span data-ttu-id="37cad-114">Пример анимации вдоль пути</span><span class="sxs-lookup"><span data-stu-id="37cad-114">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [<span data-ttu-id="37cad-115">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="37cad-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="37cad-116">Практические руководства, посвященные анимации вдоль пути</span><span class="sxs-lookup"><span data-stu-id="37cad-116">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
