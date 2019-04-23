---
title: Практическое руководство. Анимация объекта вдоль контура (точечная анимация)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: 4ef28118975d02500916676ca50e0f9622c7a3e2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129594"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a><span data-ttu-id="133c0-102">Практическое руководство. Анимация объекта вдоль контура (точечная анимация)</span><span class="sxs-lookup"><span data-stu-id="133c0-102">How to: Animate an Object Along a Path (Point Animation)</span></span>
<span data-ttu-id="133c0-103">В этом примере показано, как использовать <xref:System.Windows.Media.Animation.PointAnimationUsingPath> анимируемого объекта <xref:System.Windows.Point> вдоль изогнутого пути.</span><span class="sxs-lookup"><span data-stu-id="133c0-103">This example shows how to use a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> object to animate a <xref:System.Windows.Point> along a curved path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="133c0-104">Пример</span><span class="sxs-lookup"><span data-stu-id="133c0-104">Example</span></span>  
 <span data-ttu-id="133c0-105">В следующем примере выполняется перемещение <xref:System.Windows.Media.EllipseGeometry> вдоль пути, определенного с <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="133c0-105">The following example moves an <xref:System.Windows.Media.EllipseGeometry> along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="133c0-106">Эллипс <xref:System.Windows.Media.EllipseGeometry.Center%2A> свойство, которое принимает <xref:System.Windows.Point> значение, указывающее его положение; для перемещения эллипса, можно анимировать его <xref:System.Windows.Media.EllipseGeometry.Center%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="133c0-106">The ellipse geometry's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property, which takes a <xref:System.Windows.Point> value, specifies its position; to move the ellipse geometry, you animate its <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span> <span data-ttu-id="133c0-107">В примере используется <xref:System.Windows.Media.Animation.PointAnimationUsingPath> для анимации <xref:System.Windows.Media.EllipseGeometry> объекта <xref:System.Windows.Media.EllipseGeometry.Center%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="133c0-107">The example uses a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> to animate the <xref:System.Windows.Media.EllipseGeometry> object's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 <span data-ttu-id="133c0-108">Полный пример см. в разделе [Пример анимации вдоль пути](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="133c0-108">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="133c0-109">В версии кода в предыдущем примере используется <xref:System.Windows.Media.Animation.Storyboard> для анимации <xref:System.Windows.Media.EllipseGeometry>, несмотря на то, что была применена всего одна анимация.</span><span class="sxs-lookup"><span data-stu-id="133c0-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="133c0-110">Объект <xref:System.Windows.Media.Animation.Storyboard> часто является самым простым способом применения нескольких анимаций, так как эти анимации можно управлять тем же <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="133c0-110">A <xref:System.Windows.Media.Animation.Storyboard> is often the easiest way to apply multiple animations because these animations can be controlled by the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="133c0-111">Тем не менее, более простой способ применения одной анимации к свойству, при использовании кода является использование <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="133c0-111">However, an easier way to apply a single animation to a property when using code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="133c0-112">Пример см. в разделе [Анимация свойства без использования раскадровки](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="133c0-112">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="133c0-113">См. также</span><span class="sxs-lookup"><span data-stu-id="133c0-113">See also</span></span>

- [<span data-ttu-id="133c0-114">Пример анимации вдоль пути</span><span class="sxs-lookup"><span data-stu-id="133c0-114">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)
- [<span data-ttu-id="133c0-115">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="133c0-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="133c0-116">Практические руководства, посвященные анимации по контуру</span><span class="sxs-lookup"><span data-stu-id="133c0-116">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
