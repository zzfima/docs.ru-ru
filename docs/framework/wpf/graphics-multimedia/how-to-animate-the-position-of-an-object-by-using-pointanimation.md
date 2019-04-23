---
title: Практическое руководство. Анимация расположения объекта с помощью PointAnimation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: 1ef3f77e551affaa7e61d2aabf95f10c29275417
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111310"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a><span data-ttu-id="075d8-102">Практическое руководство. Анимация расположения объекта с помощью PointAnimation</span><span class="sxs-lookup"><span data-stu-id="075d8-102">How to: Animate the Position of an Object by Using PointAnimation</span></span>
<span data-ttu-id="075d8-103">В этом примере показано, как использовать <xref:System.Windows.Media.Animation.PointAnimation> класс для анимации объекта вдоль <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="075d8-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimation> class to animate an object along a <xref:System.Windows.Shapes.Path>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="075d8-104">Пример</span><span class="sxs-lookup"><span data-stu-id="075d8-104">Example</span></span>  
 <span data-ttu-id="075d8-105">В следующем примере эллипс перемещается <xref:System.Windows.Shapes.Path> из одной точки на экране в другой.</span><span class="sxs-lookup"><span data-stu-id="075d8-105">The following example moves an ellipse along a <xref:System.Windows.Shapes.Path> from one point on the screen to another.</span></span> <span data-ttu-id="075d8-106">Пример анимирует положение <xref:System.Windows.Media.EllipseGeometry> с помощью <xref:System.Windows.Media.Animation.PointAnimation> для анимации <xref:System.Windows.Media.EllipseGeometry.Center%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="075d8-106">The example animates the position of an <xref:System.Windows.Media.EllipseGeometry> by using <xref:System.Windows.Media.Animation.PointAnimation> to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="075d8-107">См. также</span><span class="sxs-lookup"><span data-stu-id="075d8-107">See also</span></span>

- <xref:System.Windows.Media.Animation.PointAnimation>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.EllipseGeometry>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A>
- [<span data-ttu-id="075d8-108">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="075d8-108">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="075d8-109">Графика и мультимедиа</span><span class="sxs-lookup"><span data-stu-id="075d8-109">Graphics and Multimedia</span></span>](index.md)
- [<span data-ttu-id="075d8-110">Разделы руководства, посвященные графики</span><span class="sxs-lookup"><span data-stu-id="075d8-110">Graphics How-to Topics</span></span>](graphics-how-to-topics.md)
- [<span data-ttu-id="075d8-111">Анимации и практические руководства</span><span class="sxs-lookup"><span data-stu-id="075d8-111">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
