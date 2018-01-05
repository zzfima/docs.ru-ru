---
title: "Практическое руководство. Анимация объекта вдоль пути (точечная анимация)"
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
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 399d6b8028b8715f38335089a723707657df4a98
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a><span data-ttu-id="8d1d1-102">Практическое руководство. Анимация объекта вдоль пути (точечная анимация)</span><span class="sxs-lookup"><span data-stu-id="8d1d1-102">How to: Animate an Object Along a Path (Point Animation)</span></span>
<span data-ttu-id="8d1d1-103">В этом примере показано, как использовать <xref:System.Windows.Media.Animation.PointAnimationUsingPath> анимируемый объект <xref:System.Windows.Point> вдоль пути кривой.</span><span class="sxs-lookup"><span data-stu-id="8d1d1-103">This example shows how to use a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> object to animate a <xref:System.Windows.Point> along a curved path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d1d1-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8d1d1-104">Example</span></span>  
 <span data-ttu-id="8d1d1-105">В следующем примере перемещается <xref:System.Windows.Media.EllipseGeometry> вдоль пути, заданного с <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="8d1d1-105">The following example moves an <xref:System.Windows.Media.EllipseGeometry> along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="8d1d1-106">Эллипс <xref:System.Windows.Media.EllipseGeometry.Center%2A> свойства, которое принимает <xref:System.Windows.Point> значений, определяет его положение; Чтобы переместить эллипс, анимация вы его <xref:System.Windows.Media.EllipseGeometry.Center%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="8d1d1-106">The ellipse geometry's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property, which takes a <xref:System.Windows.Point> value, specifies its position; to move the ellipse geometry, you animate its <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span> <span data-ttu-id="8d1d1-107">В этом примере <xref:System.Windows.Media.Animation.PointAnimationUsingPath> для анимации <xref:System.Windows.Media.EllipseGeometry> объекта <xref:System.Windows.Media.EllipseGeometry.Center%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="8d1d1-107">The example uses a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> to animate the <xref:System.Windows.Media.EllipseGeometry> object's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 <span data-ttu-id="8d1d1-108">Полный пример см. в разделе [Пример анимации пути](http://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="8d1d1-108">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="8d1d1-109">В версии кода в предыдущем примере используется <xref:System.Windows.Media.Animation.Storyboard> для анимации <xref:System.Windows.Media.EllipseGeometry>, несмотря на то, что была применена только одна анимация.</span><span class="sxs-lookup"><span data-stu-id="8d1d1-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="8d1d1-110">Объект <xref:System.Windows.Media.Animation.Storyboard> часто является самым простым способом применения нескольких эффектов анимации, так как эти анимации можно управлять одним и тем же <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="8d1d1-110">A <xref:System.Windows.Media.Animation.Storyboard> is often the easiest way to apply multiple animations because these animations can be controlled by the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="8d1d1-111">Однако, более простой способ применить одну анимацию к свойству при использовании кода является использование <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="8d1d1-111">However, an easier way to apply a single animation to a property when using code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="8d1d1-112">Пример см. в разделе [Анимация свойства без использования раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="8d1d1-112">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d1d1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8d1d1-113">See Also</span></span>  
 [<span data-ttu-id="8d1d1-114">Пример анимации вдоль пути</span><span class="sxs-lookup"><span data-stu-id="8d1d1-114">Path Animation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [<span data-ttu-id="8d1d1-115">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="8d1d1-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="8d1d1-116">Практические руководства, посвященные анимации по контуру</span><span class="sxs-lookup"><span data-stu-id="8d1d1-116">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
