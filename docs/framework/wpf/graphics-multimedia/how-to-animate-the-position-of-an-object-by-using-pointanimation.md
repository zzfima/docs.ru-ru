---
title: "Практическое руководство. Анимация расположения объекта с помощью PointAnimation"
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
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9f741770077a90bef33d75640726019496fe8eb8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a><span data-ttu-id="ccb45-102">Практическое руководство. Анимация расположения объекта с помощью PointAnimation</span><span class="sxs-lookup"><span data-stu-id="ccb45-102">How to: Animate the Position of an Object by Using PointAnimation</span></span>
<span data-ttu-id="ccb45-103">В этом примере показано, как использовать <xref:System.Windows.Media.Animation.PointAnimation> класса для анимации объекта вдоль <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="ccb45-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimation> class to animate an object along a <xref:System.Windows.Shapes.Path>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccb45-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ccb45-104">Example</span></span>  
 <span data-ttu-id="ccb45-105">В следующем примере эллипс перемещается <xref:System.Windows.Shapes.Path> из одной точки на экране к другой.</span><span class="sxs-lookup"><span data-stu-id="ccb45-105">The following example moves an ellipse along a <xref:System.Windows.Shapes.Path> from one point on the screen to another.</span></span> <span data-ttu-id="ccb45-106">В примере анимируется положение <xref:System.Windows.Media.EllipseGeometry> с помощью <xref:System.Windows.Media.Animation.PointAnimation> для анимации <xref:System.Windows.Media.EllipseGeometry.Center%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="ccb45-106">The example animates the position of an <xref:System.Windows.Media.EllipseGeometry> by using <xref:System.Windows.Media.Animation.PointAnimation> to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="ccb45-107">См. также</span><span class="sxs-lookup"><span data-stu-id="ccb45-107">See Also</span></span>  
 <xref:System.Windows.Media.Animation.PointAnimation>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.EllipseGeometry>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A>  
 [<span data-ttu-id="ccb45-108">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="ccb45-108">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="ccb45-109">Графика и мультимедиа</span><span class="sxs-lookup"><span data-stu-id="ccb45-109">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
 [<span data-ttu-id="ccb45-110">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="ccb45-110">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)  
 [<span data-ttu-id="ccb45-111">Анимация и расчет времени</span><span class="sxs-lookup"><span data-stu-id="ccb45-111">Animation and Timing</span></span>](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="ccb45-112">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="ccb45-112">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
